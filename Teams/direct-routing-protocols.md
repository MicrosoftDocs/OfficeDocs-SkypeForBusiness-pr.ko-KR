---
title: 'Teams 시스템 직접 라우팅: 정의 및 RFC 표준'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
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
description: 시스템 Microsoft 전화 라우팅에서 RFC 표준 프로토콜을 구현하는 방법
appliesto:
- Microsoft Teams
ms.openlocfilehash: 26178fa52105f43ce9f7f18c0058a2ead3ef1c02
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235343"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>직접 라우팅 - 정의 및 RFC 표준

이 문서에서는 시스템 Microsoft 전화 라우팅에서 RFC 표준 프로토콜을 구현하는 방법을 설명합니다. 이 문서는 SBC(On-Premises Session Border Controller)와 SIP(세션 시작 프로토콜) 프록시 서비스 간의 연결을 구성할 책임이 있는 음성 관리자를 위한 문서입니다.

고객 SBC는 백end의 다음 구성 요소와 Microsoft Teams 인터페이스합니다. 

- **신호에 대한 SIP** 프록시입니다. SBC와 직접 라우팅 간의 SIP(TLS) 연결을 처리하는 직접 라우팅의 인터넷 연결 구성 요소입니다.

- **미디어용** 미디어 프로세서입니다. 미디어 트래픽을 처리하는 직접 라우팅의 인터넷 연결 구성 요소입니다. 이 구성 요소는 SRTP 및 SRTCP 프로토콜을 사용합니다.


직접 라우팅에 대한 자세한 내용은 직접 [라우팅 전화 시스템 참조하세요.](direct-routing-landing-page.md)

직접 라우팅이 SIP 프로토콜을 구현하는 방법에 대한 자세한 내용은 직접 라우팅 [- SIP 프로토콜 을 참조하세요.](direct-routing-protocols-sip.md)

## <a name="rfc-standards"></a>RFC 표준

직접 라우팅은 RFC 표준을 준수합니다.  직접 라우팅에 연결된 SBC도 다음 RFC(또는 해당 후속자)를 준수해야 합니다. 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>비미디어 우회 모드를 지원하는 디바이스에 적용되는 표준 

다음 표준은 비미디어 우회 모드만 지원하는 디바이스에 적용할 수 있습니다.

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): 세션 시작 프로토콜
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). 신뢰할 수 있는 네트워크 내의 ID에 대한 세션 시작 프로토콜에 대한 개인 확장--P-Asserted-Identity 헤더 처리에 대한 섹션입니다. 직접 라우팅은 개인 정보 ID 헤더를 통해 P-Asserted-Identity를 전송합니다. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) 필수 기록 정보에 대한 SIP(세션 시작 프로토콜)에 대한 확장입니다. 자세한 내용은 라우팅 SIP 프로토콜 설명을 참조하세요.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) 세션 시작 프로토콜 Referred-By 메커니즘
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) SIP(세션 시작 프로토콜) "대체" 헤더 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) 제품/답변 모델의 SIP(세션 시작 프로토콜) 사용.
  "RFC의 일차" 섹션을 참조하세요.
- [RFC 3711](https://tools.ietf.org/html/rfc3711) 및 [RFC 4771](https://tools.ietf.org/html/rfc4771). SRTP를 사용하여 RTP 트래픽을 보호합니다. SBC는 SDES를 사용하여 키를 설정할 수 있어야 합니다. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) RTP/RTCP 다중화에 대한 SDP(세션 설명 프로토콜) 제품/답변 설명

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>미디어 우회 모드를 지원하는 디바이스에 적용되는 표준

비우회 모드에 적용되는 표준 외에도 미디어 우회 모드에 다음 표준이 사용됩니다.

- [미디어 우회에 대한 RFC 5245 ICE(대화형 연결 설치)입니다.](https://tools.ietf.org/html/rfc5245)  SBC는 다음을 지원해야 합니다.
  - ICE Lite - Teams 클라이언트가 전체 ICE 클라이언트입니다.
  - [ICE가 다시 시작됩니다.](https://tools.ietf.org/html/rfc5245#section-9.1.1.1) ICE 다시 시작 사용 사례 및 ICE 다시 시작의 예제에 대한 자세한 내용은 미디어 우회를 지원하지 않는 엔드포인트로 전송된 미디어 우회 호출을 참조합니다.   
- [RFC RFC 5589 SIP(세션 시작 프로토콜) 호출 제어 - 전송.](https://tools.ietf.org/html/rfc5589) 
- [RFC 3960](https://tools.ietf.org/html/rfc3960)세션 시작 프로토콜(SIP)의 초기 미디어 및 벨링 톤 생성 , 3.1, 포킹 및 3.2 섹션, 벨킹 톤 생성을 참조하세요. 
- [NAT(STUN)에 대한 RFC 5389 세션 트래버스널 유틸리티](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 NAT 주변 릴레이 사용(TURN): NAT용 세션 트래버스 유틸리티로 릴레이 확장(STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>E911 공급자에 위치 정보를 전달하는 데 적용되는 표준

- [RFC 6442, 세션 시작 프로토콜에 대한 위치 전달](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>RFC의 일차

다음 표에서는 Microsoft의 SIP 또는 미디어 스택 구현이 표준에서 을 이연하는 RFC의 섹션을 나열합니다.

| RFC 및 섹션 | 설명 | 일차 |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, 섹션 5.3 미디어 보유 및 재개](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC를 사용하면 "a=inactive", "a=sendonly", a=recvonly"를 사용하여 통화를 보류할 수 있습니다. |SIP 프록시는 "a=비활성"만 지원하며 SBC에서 "a=sendonly" 또는 "a=recvonly"를 보내는지 이해하지 못합니다.
| [RFC 6337, 섹션 5.4 "c=0.0.0.0을 사용하여 SDP 수신 동작](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264는](https://tools.ietf.org/html/rfc3264) 에이전트가 0.0.0.0의 연결 주소로 SDP를 받을 수 있도록 요구합니다. 이 경우 RTP 또는 RTCP를 피어로 보내지 말아야 합니다. | SIP 프록시는 이 옵션을 지원하지 않습니다. |

## <a name="operational-modes"></a>작동 모드

직접 라우팅에는 두 가지 운영 모드가 있습니다.

- **모든** RTP 트래픽이 클라이언트, 미디어 Teams SBC 간에 흐르는 미디어 우회가 없습니다.  

- **모든** RTP 미디어가 Teams 엔드포인트와 SBC 간에 흐르는 미디어 우회. 

SIP 트래픽은 항상 SIP 프록시를 통해 흐를 수 있습니다. 

## <a name="dtmf"></a>DTMF
대역 내 DTMF는 미디어 스택에서 지원되지 않습니다.
