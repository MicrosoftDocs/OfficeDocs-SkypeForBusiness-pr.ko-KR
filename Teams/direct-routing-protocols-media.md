---
title: 전화 시스템 직접 라우팅
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: 직접 라우팅 프로토콜
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43673c2b6a1928ab2ca21579339324f01d5ada9e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888577"
---
# <a name="overview"></a>개요

이 문서에서는 [RFC 5245에서](https://tools.ietf.org/html/rfc5245)설명한 바와 같이 ICE Lite에 대해 사용하도록 설정된 SBC(세션 테두리 컨트롤러)를 사용하여 직접 라우팅이 미디어 우회를 지원하는 방법을 설명합니다. 이 문서는 프레미스 SBC와 SIP 프록시 서비스 간의 연결을 구성할 책임이 있는 음성 관리자를 위한 문서입니다.

이 문서에서는 ICE Lite 시나리오 및 상호 작동성에 대한 요구 사항에 대한 개요를 제공합니다. 이 문서에서는 신뢰할 수 있는 호출 및 미디어 흐름을 보장하기 위해 메시지 형식 및 필요한 상태 머신 전환을 설명합니다.

## <a name="terminology"></a>용어

- 첫 번째 안녕하세요 - 발신자 및 호출자에서 말한 첫 번째 단어입니다. 엔드포인트의 첫 번째 패킷이 대부분의 사용 사례에 대해 안정적으로 전달되도록 모든 노력을 기울이는 것이 중요합니다.

- 포킹 – 호출자를 여러 장치에서 사용할 수 있는 경우 발신자로부터의 제안이 여러 발신자 엔드포인트에 전달될 수 있습니다(예: Teams 사용자가 Android 또는 Teams Windows Teams 수 iPhone.

- 잠정 답변(183) – 빠른 통화 설정을 위한 발신자 엔드포인트는 미디어 흐름을 설정하는 데 필요한 후보 및 키와 함께 답변을 전송합니다. 이는 사용자가 해당 특정 호출자 인스턴스에서 호출(200OK)에 잠재적으로 응답할 수 있도록 예상하기 위해 수행됩니다. 포크를 사용하여 호출자는 여러 임시 답변을 받을 준비가 돼야 합니다.

- Re-Invite – ICE 제어 엔드포인트에서 선택한 최종 후보가 있는 제품입니다. 여기에는 여러 포크를 처리하지 못하게 하는 모든 레이스 조건을 해결하는 a=remote-candidate 특성이 있습니다.

- Teams 엔드포인트 – 서버(Media Processor, 전송 릴레이) 또는 클라이언트 Teams 수 있습니다.

## <a name="message-format"></a>메시지 형식

이 Teams 인프라는 ICE-Lite용 RFC 5245를 따르고 있습니다. 이는 모든 STUN 메시지가 [RFC 5389를 준수할 것임을 암시합니다.](https://tools.ietf.org/html/rfc5389)

RFC 5389에서 요구하는 SBC는 인식할 수 없는 STUN 특성을 무시하고 알려진 특성으로 메시지를 계속 처리해야 합니다. 

변형된 패킷이 수신되는 경우 미디어 세션 설치에 영향을주지 않고 패킷을 삭제해야 합니다.

## <a name="ice-lite-requirements"></a>ICE Lite 요구 사항

이 섹션에서는 ICE Lite에 대한 요구 사항을 간략하게 설명합니다.

### <a name="candidate-gathering"></a>후보자 모임

SBC는 공개적으로 도달할 수 있는 하나의 후보만 제공해야 합니다. 현재 IPV4 후보만 지원됩니다.


#### <a name="connectivity-checks"></a>연결 확인

ICE Lite 구현은 수신된 모든 연결 검사에 응답해야 합니다. ICE Lite 엔드포인트는 연결 확인 요청을 보내면 안 됩니다. (연결 검사가 위반으로 전송되는 경우 전체 구현이 응답하여 예기치 않은 피어 파생 후보가 검색되고 호출 실패가 발생할 수 있습니다.)

#### <a name="nominations"></a>후보

ICE 전체 구현 엔드포인트는 항상 제어 엔드포인트가 며 미디어 흐름에 사용할 최종 후보를 선택하는 "일반" 지명을 따르게 됩니다. ICE Lite 엔드포인트는 지명을 사용하여 미디어에 사용할 경로를 마무리하고 통화를 완료할 수 있습니다.

참고: 183개 임시 답변을 보내는 피어 엔드포인트를 사용하는 포크의 경우 SBC는 200OK 전에 지명이 발생하면 여러 엔드포인트의 검사 및 여러 엔드포인트의 지명에 응답할 준비가 되어 있어야 합니다. 사용자의 최종 경로 및 응답 타이밍에 있는 ICE 상태 머신의 수렴에 따라 200OK 전후에 지명될 수 있습니다. SBC는 두 사례를 모두 처리할 수 있어야 합니다.

#### <a name="converging-for-forking"></a>포크 수렴

SBC 포크에서 여러 엔드포인트로의 Teams 엔드포인트가 Teams 응답하고 연결 검사를 시작할 수 있습니다. SBC는 연결 검사를 수신하고 여러 피어 엔드포인트에서 연결 검사에 응답할 준비가 되어야 합니다. 예를 들어 데스크톱 Teams 휴대폰에 모두 로그인할 수 있습니다. 두 디바이스 모두 인바운드 호출에 대한 알림을 제공하고 SBC를 통해 연결 검사를 시도합니다.

결국 엔드포인트 중 하나만 호출에 응답합니다(200OK). 200OK를 수신할 때 SBC는 미디어 패킷을 처리하는 데 적합한 컨텍스트를 설정할 수 있습니다.

## <a name="scenarios"></a>시나리오

###  <a name="inbound-call-from-sbc"></a>SBC에서 인바운드 호출

이 시나리오의 경우 SBC에서 처리해야 하는 몇 가지 피어 엔드포인트가 있습니다.

- 서버 엔드포인트는 일반적으로 200OK로 직접 응답합니다. 일반적으로 Voicemail, 통화 큐 및 자동 참석 시나리오에 관련된 전체 ICE 엔드포인트입니다.

- 클라이언트 엔드포인트는 다른 From/To 태그(183)와 통화에 응답하는 엔드포인트에서 200OK를 사용하여 여러 임시 답변을 보낼 수 있습니다. 일반적으로 최종 사용자 클라이언트를 나타내는 전체 ICE 엔드포인트입니다.

- 다른 SBC 엔드포인트. 일반적으로 클라이언트 엔드포인트와 다른 전화 번호를 동시에 울리는 시나리오에 관련된 ICE Lite 엔드포인트입니다.

SBC는 전체 ICE 엔드포인트에서 수신된 모든 유효한 연결 검사 요청에 응답해야 합니다. RFC당 전체 ICE 엔드포인트가 제어 엔드포인트가 됩니다. Teams(클라이언트/서버) 엔드포인트는 "일반" 지명을 수행하여 연결 검사를 완료합니다. 최종 200Ok는 초기 미디어를 전송한 엔드포인트 또는 다른 엔드포인트에서 사용할 수 있습니다. 200Ok를 수신할 때 SBC는 미디어 흐름에 적합한 컨텍스트를 설정해야 합니다. 

###  <a name="early-media"></a>초기 미디어

초기 미디어 흐름이 있는 경우 SBC는 스트리밍 미디어를 시작하는 첫 번째 엔드포인트로 래치해야 합니다. 후보가 지명되기 전에 미디어 흐름을 시작할 수 있습니다. SBC는 IVR/voicemail 시나리오를 사용하도록 설정하기 위해 이 단계에서 DTMF를 보내기 위한 지원이 있습니다. SBC는 지명을 완료하지 않은 경우 확인을 받은 가장 높은 우선 순위 경로를 사용해야 합니다.

### <a name="outbound-call-to-sbc"></a>SBC에 대한 아웃바운드 호출

Teams 엔드포인트는 이 시나리오의 호출자이며 제어 엔드포인트가 됩니다. 임시 답변(183) 또는 최종 답변(200OK)을 수신할 때 Teams 엔드포인트는 연결 검사를 시작하고 "일반" 지명을 진행하여 연결 검사를 완료합니다.

참고: SBC에서 잠정 답변(183)을 보내는 경우 SBC는 SBC에서 200OK를 보내기 전에 연결 검사 요청을 수신하고 지명을 완료할 준비가 되어 있어야 합니다. 200OK가 수신되기 전에 확인 및/또는 지명을 완료하면 200OK가 수신된 후 다시 검사 및/또는 지명이 수행되지 않습니다. SBC는 183에서 200 사이의 ICE 후보, 암호 및 ufrag(사용자 이름 조각)를 변경하지 말아야 합니다.

초기 미디어를 지원하기 위해 SBC는 최종 엔드포인트에서 지명을 완료하기 전에 수신된 연결 검사에 따라 가장 높은 우선 순위를 가지는 피어 ICE 후보로 미디어 스트리밍을 시작할 Teams 있습니다. SBC는 후보가 완료될 Teams 모든 후보에 대한 미디어를 예상해야 합니다. 후보가 지명되면 SBC는 미디어 패킷을 보내고 받기 위해 올바른 컨텍스트로 다시 설정해야 합니다.

## <a name="srtp-support-requirements"></a>SRTP 지원 요구 사항

SBC는 제품 및 답변을 위해 SRTP 암호화 AES_CM_128_HMAC_SHA1_80 암호화 암호화를 지원해야 합니다.

```console
"inline:" <key||salt> ["|" lifetime]
```

다음은 SBC의 SDP 제품에서 암호화 특성의 예입니다.

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

MKI 및 길이 매개 변수는 필요하지 않습니다.

자세한 내용은 [RFC 4568, 섹션 6.1 을 참조하세요.](https://tools.ietf.org/html/rfc4568#section-6.1)

## <a name="sdes-support-requirements"></a>SDES 지원 요구 사항

디바이스는 아래 설명된 형식으로 SDES를 제공할 수 있어야 합니다. Microsoft Media Processor는 항상 SDES를 선호합니다.

- 비미디어 우회를 통해 클라이언트가 DTLS만 지원하는 경우에도 Media Processor는 SDES로 변환됩니다.

- 미디어 우회를 사용하여 클라이언트가 DTLS(향후 Google Chrome 상태)인 경우 직접 라우팅은 경로에 MP를 삽입하여 미디어 우회에서 비미디어 우회로로 호출을 변환합니다. 직접 라우팅의 SBC와 미디어 프로세서 구성 요소 간에는 SDES가 항상 사용됩니다.

현재 DTLS만 제공하는 Teams 클라이언트는 없습니다. 그러나 Google은 어떤 시점에 SDES 지원이 중지될 것으로 발표했습니다.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>우회 모드에서 SBC의 제품 서식 

제품에는 SDES가 포함되어야 합니다. DTLS 선택적 형식은 다음 형식으로 포함할 수 있습니다.

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>SDES가 포함된 SBC에 대한 답변 서식

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>SBC로의 Teams 형식 

### <a name="format-for-sdes-only-offer-to-sbc"></a>SDES에 대한 형식만 SBC에 제공

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

