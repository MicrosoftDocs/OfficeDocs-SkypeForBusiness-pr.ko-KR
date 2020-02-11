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
description: 다이렉트 라우팅 프로토콜
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

이 문서에서는 [RFC 5245](https://tools.ietf.org/html/rfc5245)에서 설명한 대로 ICE Lite에 대해 사용 하도록 설정 된 SBC (세션 경계 컨트롤러)의 직접 라우팅이 미디어 바이패스를 지원 하는 방법을 설명 합니다. 이 문서는 온-프레미스 SBC 및 SIP 프록시 서비스 간 연결 구성을 담당 하는 음성 관리자를 대상으로 합니다.

이 문서에서는 얼음 Lite 시나리오 및 상호 운용성 요구 사항에 대 한 개요를 제공 합니다. 이 문서에서는 신뢰할 수 있는 통화와 미디어 흐름을 보장 하기 위한 메시지 형식과 필요한 상태 시스템 전환에 대해 설명 합니다.

## <a name="terminology"></a>용어

- 첫 번째 Hello – 호출자와 호출 수신자가 말한 첫 번째 단어입니다. 끝점의 첫 번째 패킷이 대부분의 사용 사례에 대해 안정적으로 전달 되도록 하기 위해 모든 작업을 수행할 수 있어야 합니다.

- 포크 – 호출 수신자를 여러 장치에서 사용할 수 있는 경우 호출자의 제공이 여러 호출 수신자 끝점으로 전달 될 수 있습니다 (예를 들어 팀 사용자가 Windows 및 Android 또는 iPhone 용 팀으로 로그인 할 수 있는 경우).

- Provisional Answer (183) – 빠른 호출 설정에 대 한 피호출자 끝점은 미디어 흐름을 설정 하는 데 필요한 후보와 키를 사용 하 여 응답을 보냅니다. 이 작업은 사용자가 해당 특정 호출 수신자 인스턴스에서 전화 (200OK)에 응답 하는 것으로 예상 되는 경우에 대비 합니다. 분기를 사용 하는 경우 호출자는 여러 provisional 답변을 받을 준비가 됩니다.

- 재 초대 – ICE 제어 끝점에 의해 선택 된 최종 후보자에 게 제공 됩니다. 이것은 a = 원격 후보 특성을 사용 하 여 여러 포크를 처리 하는 경합 상태를 해결 합니다.

- 팀 끝점 – 서버 (미디어 프로세서, 전송 릴레이) 또는 팀 클라이언트 중 하나일 수 있습니다.

## <a name="message-format"></a>메시지 형식

팀 인프라는 ICE 용 RFC 5245을 따릅니다. 이는 모든 STUN 메시지가 [RFC 5389](https://tools.ietf.org/html/rfc5389)을 준수 한다는 것을 의미 합니다.

RFC 5389에 필요한 SBCs는 인식 하지 못하는 모든 STUN 특성을 무시 하 고 알려진 특성을 사용 하 여 메시지를 계속 처리 합니다. 

형식이 잘못 된 패킷이 수신 되 면 미디어 세션 설정에 영향을 주지 않고 패킷을 취소 해야 합니다.

## <a name="ice-lite-requirements"></a>얼음 라이트 요구 사항

이 섹션에서는 얼음 Lite에 대 한 요구 사항을 간략하게 포착 합니다.

### <a name="candidate-gathering"></a>후보자 수집

SBC는 공개적으로 접근할 수 있는 하나의 후보만 제공 해야 합니다. 현재 IPV4 후보자만 지원 됩니다.


#### <a name="connectivity-checks"></a>연결 검사

ICE Lite 구현은 수신 된 모든 연결 검사에 응답 해야 합니다. ICE Lite 끝점은 연결 확인 요청을 보내지 않아야 합니다. 연결 검사가 위반으로 전송 되는 경우 전체 구현이 응답 하 여 예기치 않은 피어 파생 후보가 검색 되 고 잠재적으로 호출 오류가 발생할 수 있습니다.

#### <a name="nominations"></a>Nominations

ICE full 구현 끝점은 항상 제어 끝점 이며 미디어 흐름에 사용할 최종 후보를 선택 하기 위해 "일반" nominations을 따릅니다. ICE Lite 끝점은 nominations를 사용 하 여 미디어에 사용 되는 경로를 마무리 하 고 통화 설정을 완료할 수 있습니다.

참고: 183 provisional 응답을 보내는 피어 끝점으로 포크 하는 경우 SBC는 여러 끝점에서 검사에 응답할 준비가 되어 있어야 하며 nominations이 200OK 이전에 발생 하는 경우 여러 끝점에서 nominations 수 있습니다. 최종 경로와 사용자의 응답 타이밍에 대 한 ICE state 시스템의 수렴에 따라 nominations는 200OK 전이나 후에 발생할 수 있습니다. SBC는 두 경우를 모두 처리할 수 있어야 합니다.

#### <a name="converging-for-forking"></a>포크에 대 한 수렴

SBC의 제안이 여러 팀 끝점으로 포크 되는 경우 팀 끝점은 provisional answer로 응답 하 고 연결성 검사를 시작할 수 있습니다. SBC는 연결 검사를 받고 여러 피어 끝점의 연결 검사에 응답할 수 있도록 준비 되어야 합니다. 예를 들어 팀 사용자는 데스크톱과 휴대폰으로 모두 로그인 할 수 있습니다. 두 장치 모두에서 인바운드 호출에 대 한 알림을 받게 되며 SBC에 대 한 연결 확인을 시도 합니다.

결국에는 끝점 중 하나만 통화에 응답 합니다 (200OK). 200OK를 받으면 SBC는 미디어 패킷을 처리 하는 데 적합 한 컨텍스트를 설정할 수 있습니다.

## <a name="scenarios"></a>시나리오

###  <a name="inbound-call-from-sbc"></a>SBC 로부터의 인바운드 통화

이 시나리오의 경우 SBC에서 처리 해야 하는 가능한 여러 피어 끝점은 다음과 같습니다.

- 일반적으로 서버 끝점은 200OK를 사용 하 여 직접 응답 합니다. 일반적으로 보이스 메일, 통화 대기열 및 자동 전화 교환 시나리오와 관련 된 정식 ICE 끝점입니다.

- 클라이언트 끝점은/To 태그 (183)와 다른 여러 개의 provisional 대답을 보낼 수 있으며, 통화에 응답 하는 끝점에서 200OK가 나옵니다. 일반적으로 최종 사용자 클라이언트를 나타내는 전체 ICE 끝점입니다.

- 다른 SBC 끝점 이러한 끝점은 일반적으로 클라이언트 끝점과 다른 전화 번호를 동시에 링 하는 시나리오와 관련 된 ICE Lite 종점입니다.

SBC는 전체 ICE 끝점에서 받은 유효한 모든 연결 확인 요청에 응답 해야 합니다. RFC 별로 전체 ICE 끝점이 끝점을 제어 하 게 됩니다. 팀 (클라이언트/서버) 끝점은 연결 검사를 완료 하기 위해 "일반" nominations을 수행 합니다. 마지막 200Ok는 초기 미디어를 전송한 끝점 또는 다른 끝점에서 확인할 수 있습니다. 200Ok를 받을 때 SBC는 미디어 흐름에 적합 한 컨텍스트를 설정 해야 합니다. 

###  <a name="early-media"></a>초기 미디어

초기 미디어 흐름이 있는 경우 SBC는 스트리밍 미디어를 시작 하는 첫 번째 끝점으로 래치 해야 합니다. 후보자가 만들어지기 전에 미디어 흐름이 시작 될 수 있습니다. 이 단계 중에는 IVR/보이스 메일 시나리오를 사용 하기 위해 SBC에서 DTMF 전송을 지원 해야 합니다. SBC는 nominations가 완료 되지 않은 경우 검사를 받은 가장 높은 우선 순위 경로를 사용 해야 합니다.

### <a name="outbound-call-to-sbc"></a>SBC로 나가는 호출

팀 끝점은이 시나리오에 대 한 호출자 이며 제어 종점이 됩니다. Provisional answer (183) 또는 최종 응답 (200OK)을 받은 경우 팀 끝점은 연결 검사를 시작 하 고 "일반" nominations으로 이동 하 여 연결 검사를 완료 합니다.

참고: SBC에서 provisional answer (183)를 보내는 경우 SBC는 연결 검사 요청을 받을 준비가 되어 있으며 SBC가 200OK를 보내기 전에 nominations를 완료할 수 있어야 합니다. 200OK를 받기 전에 검사 및/또는 nominations가 완료 되 면 200OK를 받은 후에는 검사 및/또는 nominations가 다시 수행 되지 않습니다. SBC는 183과 200 간의 ICE, 암호 및 ufrag (사용자 이름 조각)를 변경 하지 않아야 합니다.

초기 미디어를 지원 하기 위해 SBC는 nominations이 팀 끝점에 의해 완료 되기 전에도 수신 된 연결 검사에 따라 우선 순위가 가장 높은 피어 ICE 후보로 미디어 스트리밍을 시작할 수 있습니다. SBC는 nominations 완료 될 때까지 모든 후보의 팀의 미디어를 예상 해야 합니다. 후보를 지정한 후에는 SBC를 올바른 컨텍스트로 다시 설정 해야 미디어 패킷을 보내고 받을 수 있습니다.

## <a name="srtp-support-requirements"></a>SRTP 지원 요구 사항

SBC는 다음 형식으로 제공 및 answer에 대 한 SRTP 암호화 암호 AES_CM_128_HMAC_SHA1_80를 지원 해야 합니다.

```console
"inline:" <key||salt> ["|" lifetime]
```

다음은 SBC의 SDP 제안에 있는 crypto 특성의 예입니다.

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

MKI 및 Length 매개 변수는 필요 하지 않습니다.

자세한 내용은 [RFC 4568, 섹션 6.1](https://tools.ietf.org/html/rfc4568#section-6.1)을 참조 하세요.

## <a name="sdes-support-requirements"></a>SDES 지원 요구 사항

장치는 아래 설명 된 형식으로 SDES을 제공할 수 있어야 합니다. Microsoft 미디어 프로세서는 항상 SDES를 선호 합니다.

- 비 미디어 바이패스를 사용 하는 경우 클라이언트가 DTLS만 지 원하는 경우에도 미디어 프로세서는 SDES로 변환 됩니다.

- 미디어 바이패스를 사용 하 여 클라이언트가 DTLS (이후 Google Chrome 상태) 경우 다이렉트 라우팅이 경로에 MP를 삽입 하 고 미디어 바이패스에서 미디어 바이패스로의 통화를 변환 합니다. 직접 라우팅의 SBC 및 미디어 프로세서 구성 요소 간에는 항상 SDES 사용 됩니다.

현재 DTLS만 제공 하는 팀 클라이언트는 없습니다. 그러나 Google에서는 SDES 지원 중지 시점에이를 발표 했습니다.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>우회 모드의 SBC에서 제공 하는 서식 

SDES를 포함 하 고 다음 형식으로 DTLS optional을 포함할 수 있는 제안이 있어야 합니다.

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>SDES를 포함 하 여 SBC에 대 한 응답 형식

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>팀에서 제공 하는 SBC에 대 한 형식 

### <a name="format-for-sdes-only-offer-to-sbc"></a>SBC에 대 한 SDES에 대 한 형식 제공

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

