---
title: 전화 시스템 직접 라우팅 개요
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: hHw 직접 라우팅은 ICE Lite에 대해 사용하도록 설정된 세션 테두리 컨트롤러를 사용하여 미디어 바이패스를 지원합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59ea283069c6fc37590d6329aeac46e40484f8ca
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267763"
---
# <a name="overview"></a>개요

이 문서에서는 [RFC 5245](https://tools.ietf.org/html/rfc5245)에 설명된 대로 직접 라우팅이 ICE Lite에 사용하도록 설정된 SBC(세션 테두리 컨트롤러)를 사용하여 미디어 바이패스를 지원하는 방법을 설명합니다. 이 문서는 온-프레미스 SBC와 SIP 프록시 서비스 간의 연결을 구성할 책임이 있는 음성 관리자를 위한 것입니다.

이 문서에서는 ICE Lite 시나리오 및 상호 운용성에 대한 요구 사항에 대한 개요를 제공합니다. 이 문서에서는 신뢰할 수 있는 호출 및 미디어 흐름을 보장하기 위한 메시지 형식 및 필요한 상태 컴퓨터 전환에 대해 설명합니다.

## <a name="terminology"></a>용어

- 첫 번째 Hello – 호출자와 발신자가 말한 첫 번째 단어입니다. 엔드포인트의 첫 번째 패킷이 대부분의 사용 사례에 대해 안정적으로 전달되도록 모든 노력을 기울여야 합니다.

- 포크 – 호출 수신자가 여러 디바이스에서 사용할 수 있는 경우 발신자의 제안이 여러 수신자 엔드포인트로 배달될 수 있습니다(예: Teams 사용자가 Windows용 Teams 및 Android 또는 iPhone용 Teams에 로그인할 수 있음).

- 임시 응답(183) – 더 빠른 통화 설정을 위한 수신자 엔드포인트는 미디어 흐름을 설정하는 데 필요한 후보 및 키를 사용하여 답변을 보냅니다. 이는 특정 호출 수신자 인스턴스에서 잠재적으로 통화(200OK)에 응답하는 사용자를 예상하여 수행됩니다. 포크를 사용하면 호출자가 여러 임시 답변을 받을 준비가 되어 있어야 합니다.

- Re-Invite – ICE 제어 엔드포인트에서 선택한 최종 후보와 함께 제공합니다. 이렇게 하면 여러 포크 처리에서 모든 경합 조건을 해결할 수 있는 a=remote-candidate 특성이 있습니다.

- Teams 엔드포인트 – 서버(미디어 프로세서, 전송 릴레이) 또는 Teams 클라이언트일 수 있습니다.

## <a name="message-format"></a>메시지 형식

Teams 인프라는 ICE-Lite용 RFC 5245를 따릅니다. 이는 모든 STUN 메시지가 [RFC 5389](https://tools.ietf.org/html/rfc5389)를 준수한다는 것을 의미합니다.

RFC 5389에 필요한 SCC는 인식할 수 없는 모든 STUN 특성을 무시하고 알려진 특성을 사용하여 메시지를 계속 처리해야 합니다. 

잘못된 형식의 패킷이 수신되면 미디어 세션 설정에 영향을 주지 않고 패킷을 삭제해야 합니다.

## <a name="ice-lite-requirements"></a>ICE Lite 요구 사항

이 섹션에서는 ICE Lite에 대한 요구 사항을 간략하게 설명합니다.

### <a name="candidate-gathering"></a>후보 모임

SBC는 공개적으로 연결할 수 있는 후보를 하나만 제공해야 합니다. 현재 IPV4 후보만 지원됩니다.


#### <a name="connectivity-checks"></a>연결 검사

ICE Lite 구현은 수신된 모든 연결 검사에 응답해야 합니다. ICE Lite 엔드포인트는 연결 확인 요청을 보내지 않아야 합니다. (연결 검사가 위반으로 전송되면 전체 구현이 응답하므로 예기치 않은 피어 파생 후보가 검색되고 잠재적으로 호출 실패가 발생할 수 있습니다.)

#### <a name="nominations"></a>후보

ICE 전체 구현 엔드포인트는 항상 제어 엔드포인트이며 미디어 흐름에 사용할 최종 후보를 선택하기 위해 "일반" 후보를 따릅니다. ICE Lite 엔드포인트는 추천을 사용하여 미디어 및 전체 통화 설정에 사용할 경로를 마무리할 수 있습니다.

참고: 183개의 임시 답변을 보내는 피어 엔드포인트를 사용하여 포크하는 경우 SBC는 200OK 이전에 추천이 발생하는 경우 여러 엔드포인트의 검사와 여러 엔드포인트의 추천에 응답할 준비가 되어 있어야 합니다. 최종 경로에 ICE 상태 컴퓨터의 수렴과 사용자 응답의 타이밍에 따라, 추천은 200OK 전후에 발생할 수 있습니다. SBC는 두 경우 모두 처리할 수 있어야 합니다.

#### <a name="converging-for-forking"></a>포크 수렴

SBC의 제품이 여러 Teams 엔드포인트로 포크되는 경우 Teams 엔드포인트는 임시 답변으로 응답하고 연결 검사를 시작할 수 있습니다. SBC는 연결 검사를 받고 여러 피어 엔드포인트에서 연결 검사에 응답할 준비가 되어 있어야 합니다. 예를 들어 Teams 사용자는 데스크톱과 휴대폰 모두에 로그온할 수 있습니다. 두 디바이스 모두 인바운드 호출에 대한 알림을 받고 SBC와의 연결 검사를 시도합니다.

결국 엔드포인트 중 하나만 통화에 응답합니다(200OK). 200OK를 수신할 때 SBC는 미디어 패킷을 처리하기 위한 올바른 컨텍스트를 설정할 수 있습니다.

## <a name="scenarios"></a>시나리오

###  <a name="inbound-call-from-sbc"></a>SBC의 인바운드 호출

이 시나리오에서는 SBC에서 처리해야 하는 몇 가지 가능한 피어 엔드포인트가 있습니다.

- 서버 엔드포인트는 일반적으로 200OK로 직접 응답합니다. 이러한 엔드포인트는 일반적으로 음성 메일, 통화 큐 및 자동 전화 교환 시나리오와 관련된 전체 ICE 엔드포인트입니다.

- 클라이언트 엔드포인트는 서로 다른 From/To 태그(183)와 통화에 응답하는 엔드포인트에서 200OK를 사용하여 여러 임시 답변을 보낼 수 있습니다. 이러한 엔드포인트는 일반적으로 최종 사용자 클라이언트를 나타내는 전체 ICE 엔드포인트입니다.

- 기타 SBC 엔드포인트. 일반적으로 클라이언트 엔드포인트와 다른 전화 번호를 동시에 울리는 시나리오와 관련된 ICE Lite 엔드포인트입니다.

SBC는 전체 ICE 엔드포인트에서 받은 모든 유효한 연결 확인 요청에 응답해야 합니다. RFC에 따라 전체 ICE 엔드포인트는 제어 엔드포인트가 됩니다. Teams(클라이언트/서버) 엔드포인트는 "일반" 추천을 수행하여 연결 검사를 완료합니다. 최종 200Ok는 초기 미디어를 보낸 엔드포인트 또는 다른 엔드포인트에서 사용할 수 있습니다. 200Ok를 수신할 때 SBC는 미디어 흐름에 적합한 컨텍스트를 설정해야 합니다. 

###  <a name="early-media"></a>초기 미디어

초기 미디어 흐름이 있는 경우 SBC는 스트리밍 미디어를 시작하는 첫 번째 엔드포인트로 래치해야 합니다. 후보자가 지명되기 전에 미디어 흐름이 시작될 수 있습니다. SBC는 IVR/음성 메일 시나리오를 사용하도록 설정하기 위해 이 단계에서 DTMF를 보낼 수 있도록 지원해야 합니다. SBC는 공천이 완료되지 않은 경우 검사를 받은 가장 높은 우선 순위 경로를 사용해야 합니다.

### <a name="outbound-call-to-sbc"></a>SBC에 대한 아웃바운드 호출

Teams 엔드포인트는 이 시나리오의 호출자이며 제어 엔드포인트가 됩니다. 임시 답변(183) 또는 최종 답변(200OK)을 받으면 Teams 엔드포인트는 연결 검사를 시작하고 "일반" 추천으로 진행하여 연결 검사를 완료합니다.

참고: SBC가 임시 답변(183)을 보내는 경우 SBC는 SBC에서 200OK를 보내기 전에 연결 확인 요청을 수신하고 잠재적으로 추천을 완료할 준비가 되어 있어야 합니다. 200OK를 받기 전에 검사 및/또는 추천이 완료되면 200OK가 수신된 후 검사 및/또는 추천이 다시 수행되지 않습니다. SBC는 ICE 후보, 암호 및 ufrag(사용자 이름 조각)를 183에서 200 사이로 변경해서는 안 됩니다.

초기 미디어를 지원하기 위해 SBC는 Teams 엔드포인트에서 지명을 완료하기 전에 수신된 연결 검사를 기반으로 가장 높은 우선 순위로 피어 ICE 후보에게 미디어 스트리밍을 시작할 수 있습니다. SBC는 지명이 완료될 때까지 모든 후보자의 Teams 미디어를 예상해야 합니다. 후보가 지명되면 SBC는 미디어 패킷을 보내고 받기 위해 올바른 컨텍스트로 다시 설정해야 합니다.

## <a name="srtp-support-requirements"></a>SRTP 지원 요구 사항

SBC는 제품 및 답변에 대한 SRTP 암호화 AES_CM_128_HMAC_SHA1_80 다음 형식으로 지원해야 합니다.

```console
"inline:" <key||salt> ["|" lifetime]
```

다음은 SBC의 SDP 제품에 있는 암호화 특성의 예입니다.

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

MKI 및 길이 매개 변수는 필요하지 않습니다.

자세한 내용은 [RFC 4568, 섹션 6.1](https://tools.ietf.org/html/rfc4568#section-6.1)을 참조하세요.

## <a name="sdes-support-requirements"></a>SDES 지원 요구 사항

디바이스는 아래 설명된 형식으로 SDES를 제공할 수 있어야 합니다. Microsoft 미디어 프로세서는 항상 SDES를 선호합니다.

- 비미디어 바이패스를 사용하면 클라이언트가 DTLS만 지원하더라도 미디어 프로세서는 SDES로 변환됩니다.

- 미디어 바이패스를 사용하면 클라이언트가 DTLS만(향후 Google Chrome 상태)인 경우 직접 라우팅은 경로에 MP를 삽입하여 미디어 바이패스에서 비미디어 바이패스로 통화를 변환합니다. 직접 라우팅의 SBC 및 미디어 프로세서 구성 요소 사이에는 항상 SDES가 사용됩니다.

현재 DTLS만 제공하는 Teams 클라이언트는 없습니다. 그러나 구글은 어떤 시점에서 그들은 SDES 지원을 중지합니다 발표했다.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>바이패스 모드의 SBC 제품 형식 

제품에는 SDES가 포함되어야 하며 다음 형식으로 선택적으로 DTLS를 포함할 수 있습니다.

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>SDES에서 SBC로의 응답 형식

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Teams에서 SBC로의 제품 형식 

### <a name="format-for-sdes-only-offer-to-sbc"></a>SDES 제품만 SBC에 대한 형식

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

