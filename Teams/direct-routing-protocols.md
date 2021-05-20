---
title: 전화 시스템 직접 라우팅
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
description: 직접 라우팅 프로토콜
appliesto:
- Microsoft Teams
ms.openlocfilehash: 88fb4459192ad9ff5af8702878d1cbf6a59d8e9d
ms.sourcegitcommit: 6227667c9941cc3289029099b7b6781581f16ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52569206"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>직접 라우팅 - 정의 및 RFC 표준

이 문서에서는 시스템 직접 라우팅Microsoft 전화 RFC 표준 프로토콜을 구현하는 방법에 대해 설명합니다. 이 문서는 온-프레미스 세션 테두리 컨트롤러(SBC)와 세션 개시 프로토콜(SIP) 프록시 서비스 간의 연결을 구성하는 음성 관리자를 대상으로 합니다.

고객 SBC는 Microsoft Teams 백엔드에서 다음 구성 요소와 인터페이스합니다. 

- 시그널링을 위한 **SIP 프록시입니다.** SBC와 직접 라우팅 간의 SIP(TLS) 연결을 처리하는 직접 라우팅의 인터넷 을 향한 구성 요소입니다.

- 미디어를 위한 **미디어 프로세서입니다.** 미디어 트래픽을 처리하는 직접 라우팅의 인터넷 을 향한 구성 요소입니다. 이 구성 요소는 SRTP 및 SRTCP 프로토콜을 사용합니다.


직접 라우팅에 대한 자세한 내용은 [전화 시스템 직접 라우팅을](direct-routing-landing-page.md)참조하십시오.

직접 라우팅이 SIP 프로토콜을 구현하는 방법에 대한 자세한 내용은 [직접 라우팅 - SIP 프로토콜을](direct-routing-protocols-sip.md)참조하십시오.

## <a name="rfc-standards"></a>RFC 표준

직접 라우팅은 RFC 표준을 준수합니다.  직접 라우팅에 연결된 SBC는 다음 RFC(또는 후속자)도 준수해야 합니다. 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>비미디어 바이패스 모드를 지원하는 장치에 적용되는 표준 

다음 표준은 비미디어 바이패스 모드만 지원하는 장치에 적용됩니다.

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): 세션 개시 프로토콜
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). 신뢰할 수 있는 네트워크 내에서 주장되는 ID에 대한 세션 개시 프로토콜에 대한 비공개 확장-P-어설션-ID 헤더 처리에 관한 섹션. 직접 라우팅은 개인 정보 ID 헤더로 P-어설션-ID를 보냅니다. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) 필요한 기록 정보에 대한 세션 개시 프로토콜(SIP)에 대한 확장입니다. 자세한 내용은 SIP 프로토콜 설명을 라우팅합니다.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) 세션 개시 프로토콜 Referred-By 메커니즘
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) 세션 개시 프로토콜(SIP) "대체" 헤더 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) 세션 개시 프로토콜(SIP) 오퍼/답변 모델의 사용.
  "RFC의 편차" 섹션을 참조하십시오.
- [RFC 3711](https://tools.ietf.org/html/rfc3711) 및 [RFC 4771](https://tools.ietf.org/html/rfc4771). SRTP를 사용하여 RTP 트래픽을 보호합니다. SBC는 SDES를 사용하여 키를 설정할 수 있어야 합니다. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) 세션 설명 프로토콜(SDP) RTP/RTCP 멀티플렉스에 대한 제안/답변 설명

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>미디어 우회 모드를 지원하는 장치에 적용되는 표준

바이패스 모드에 적용할 수 있는 표준 외에도 미디어 바이패스 모드에는 다음 표준이 사용됩니다.

- [RFC 5245 미디어 바이패스에 대한 대화형 연결 구축(ICE)](https://tools.ietf.org/html/rfc5245)  SBC는 다음을 지원해야 합니다.
  - ICE 라이트 - Teams 클라이언트는 전체 ICE 클라이언트입니다
  - [ICE 다시 시작](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). ICE 재시작 사례 및 ICE 재시작 사례 에 대한 자세한 보기: 미디어 바이패스를 지원하지 않는 끝점으로 전송된 미디어 바이패스 호출   
- [RFC RFC 5589 세션 개시 프로토콜 (SIP) 통화 제어 – 전송](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 세션 개시 프로토콜(SIP)에서 초기 미디어 및 링링 톤 생성,](https://tools.ietf.org/html/rfc3960)섹션 3.1, 포크 및 3.2, 링톤 생성 
- [NAT (STUN)에 대한 RFC 5389 세션 트래버스 유틸리티](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 NAT 주변 릴레이 사용 트래버스 (TURN): NAT (STUN)에 대한 세션 횡단 유틸리티에 릴레이 확장](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>E911 제공업체에 위치 정보 전달을 지원하는 데 적용되는 표준

- [RFC 6442, 세션 개시 프로토콜의 위치 이송](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>RFC의 편차

다음 표에는 Microsoft의 SIP 또는 미디어 스택 구현이 표준에서 벗어난 RFC(들)의 섹션이 나열됩니다.

| RFC 및 섹션 | 설명 | 편차 |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, 섹션 5.3 미디어의 보류 및 재개](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC는 "a=비활성", "a=sendonly", a=recvonly"를 사용하여 통화를 보류할 수 있습니다. |SIP 프록시는 "a=비활성"만 지원하며 SBC가 "a=sendonly" 또는 "a=recvonly"를 보내는지 이해하지 못합니다.
| [RFC 6337, 섹션 5.4 "c=0.0.0.0.0으로 SDP 수신에 대한 동작](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264는](https://tools.ietf.org/html/rfc3264) 상담원이 0.0.0.0의 연결 주소로 SDP를 수신할 수 있어야 하며, 이 경우 RTP나 RTCP를 피어로 보내야 합니다. | SIP 프록시는 이 옵션을 지원하지 않습니다. |

## <a name="operational-modes"></a>운영 모드

직접 라우팅을 위한 두 가지 운영 모드가 있습니다.

- 모든 RTP 트래픽이 Teams 클라이언트, 미디어 프로세서 및 SBC 간에 흐르는 **미디어 바이패스가 없습니다.**  

- 모든 RTP 미디어가 Teams 엔드포인트와 SBC 사이에 흐르는 **미디어 우회를 통해.** 

SIP 트래픽은 항상 SIP 프록시를 통해 흐릅니다. 

## <a name="dtmf"></a>DTMF
인밴드 DTMF는 미디어 스택에 의해 지원되지 않습니다.
