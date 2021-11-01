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
ms.openlocfilehash: 01748c0e344cbadf2d771d2ab4bf6ad1f9b14dfb
ms.sourcegitcommit: 813f1e44bd094bd997dd7423cda7e685ff61498f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2021
ms.locfileid: "60633524"
---
# <a name="direct-routing---sip-protocol"></a>직접 라우팅 - SIP 프로토콜

이 문서에서는 직접 라우팅이 SIP(세션 시작 프로토콜)를 구현하는 방법을 설명합니다. SBC(세션 테두리 컨트롤러)와 SIP 프록시 간에 트래픽을 올바르게 라우팅하려면 일부 SIP 매개 변수에 특정 값이 있어야 합니다. 이 문서는 프레미스 SBC와 SIP 프록시 서비스 간의 연결을 구성할 책임이 있는 음성 관리자를 위한 문서입니다.

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a>들어오는 요청 처리: 테넌트 및 사용자 찾기

수신 또는 아웃바운드 호출을 처리하기 전에 옵션 메시지는 SIP 프록시와 SBC 간에 교환됩니다. 이러한 옵션 메시지를 통해 SIP 프록시는 SBC에 허용된 기능을 제공할 수 있습니다. 옵션 협상이 성공해야 합니다(200OK 응답), 호출을 설정하기 위해 SBC와 SIP 프록시 간의 추가 통신을 허용합니다. SIP 프록시에 대한 OPTIONS 메시지의 SIP 헤더는 아래 예제로 제공됩니다.

| 매개 변수 이름 | 값의 예 | 
| :---------------------  |:---------------------- |
| Request-URI | OPTIONS sip:sip.pstnhub.microsoft.com:5061 SIP /2.0 |
| 헤더를 통해 | Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards 헤더 | Max-Forwards:68 |
| 헤더에서 | 헤더에서: <sip:sbc1.adatum.biz:5058> |
| 헤더로 | 받는 사람: <sip:sip.pstnhub.microsoft.com:5061> |
| CSeq 헤더 | CSeq: 1 INVITE | 
| 헤더에 문의 | 연락처: <sip:sbc1.adatum.biz:50588;transport=tls> |

> [!NOTE]
> SIP 헤더에는 사용 중인 SIP URI에 userinfo가 포함되어 있지 않습니다. [RFC 3261, 섹션 19.1.1에](https://tools.ietf.org/html/rfc3261#section-19.1.1)따라 URI의 userinfo 부분은 선택 사항이며 대상 호스트에 사용자에 대한 생각이 없는 경우 또는 호스트 자체가 식별되는 리소스인 경우 부재할 수 있습니다. @ 기호가 SIP URI에 있는 경우 사용자 필드가 비어 있어야 합니다.

들어오는 호출에서 SIP 프록시는 호출이 예정된 테넌트를 찾고 이 테넌트 내에서 특정 사용자를 찾아야 합니다. 테넌트 관리자는 여러 테넌트에서 비 DID 번호(예: +1001)를 구성할 수 있습니다. 따라서 DID가 아닌 숫자가 여러 조직 또는 조직에서 동일할 수 있으므로 숫자 검색을 수행할 특정 테넌트 Microsoft 365 Office 365 중요합니다.  

이 섹션에서는 SIP 프록시가 테넌트와 사용자를 찾고 들어오는 연결에서 SBC의 인증을 수행하는 방법을 설명합니다.

다음은 들어오는 호출의 SIP 초대 메시지의 예입니다.

| 매개 변수 이름 | 값의 예 | 
| :---------------------  |:---------------------- |
| Request-URI | INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0 |
| 헤더를 통해 | Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978 | 
| Max-Forwards 헤더 | Max-Forwards:68 |
| 헤더에서 | 헤더에서: <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679 |
| 헤더로 | to: sip:+183338006777@sbc1.adatum.biz | 
| CSeq 헤더 | CSeq: 1 INVITE | 
| 헤더에 문의 | 연락처: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls> | 

초대를 받을 때 SIP 프록시는 다음 단계를 수행합니다.

1. 인증서를 검사합니다. 초기 연결에서 직접 라우팅 서비스는 연락처 헤더에 제시된 FQDN 이름을 사용하여 제시된 인증서의 일반 이름 또는 주체 대체 이름과 일치합니다. SBC 이름은 다음 옵션 중 하나와 일치해야 합니다.

   - 옵션 1. 연락처 헤더에 제시된 전체 FQDN 이름은 제시된 인증서의 일반 이름/주체 대체 이름과 일치해야 합니다.  

   - 옵션 2. 연락처 헤더에 제시된 FQDN 이름의 도메인 부분(예: FQDN adatum.biz 이름의 sbc1.adatum.biz)은 일반 이름/주체 대체 이름(예: *.adatum.biz)의 와일드카드 값과 일치해야 합니다.

2. 연락처 헤더에 제시된 전체 FQDN 이름을 사용하여 테넌트를 찾으려고 합니다.  

   연락처 헤더(sbc1.adatum.biz)의 FQDN 이름이 모든 조직에서 DNS 이름으로 Microsoft 365 Office 365 합니다. 발견된 경우 사용자의 검색은 SBC FQDN이 도메인 이름으로 등록된 테넌트에서 수행됩니다. 찾을 수 없는 경우 3단계가 적용됩니다.   

3. 3단계는 2단계가 실패한 경우만 적용됩니다. 

   호스트 부분을 제거한 후 FQDN(FQDN: sbc12.adatum.biz)에 있는 호스트 부분을 제거하고 adatum.biz 이 이름이 모든 조직 또는 조직에서 DNS 이름으로 등록되어 Microsoft 365 Office 365. 찾은 경우 이 테넌트에서 사용자 보기가 수행됩니다. 찾을 수 없는 경우 호출이 실패합니다.

4. Request-URI에 제공된 전화 번호를 사용하여 2단계 또는 3단계에 있는 테넌트 내에서 역 번호 보기를 수행합니다. 이전 단계에서 발견된 테넌트 내의 사용자 SIP URI에 제시된 전화 번호를 일치합니다.

5. 트렁크 설정을 적용합니다. 이 SBC에 대한 테넌트 관리자가 설정한 매개 변수를 찾을 수 있습니다.

   Microsoft는 Microsoft SIP 프록시와 페어링된 SBC 간에 타사 SIP 프록시 또는 사용자 에이전트 서버가 있는 경우를 지원하지 않습니다. 이는 쌍을 이루는 SBC에서 만든 요청 URI를 수정할 수 있습니다.

   한 SBC가 여러 테넌트(통신사 시나리오)에 상호 연결되는 시나리오에 필요한 두 가지 보기(2단계 및 3단계)에 대한 요구 사항은 이 문서의 나중에 설명합니다.

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a>연락처 헤더 및 Request-URI에 대한 자세한 요구 사항

#### <a name="contact-header"></a>연락처 헤더

Microsoft SIP 프록시에 들어오는 모든 SIP 메시지(OPTIONS, INVITE)의 경우 연락처 헤더에 다음과 같이 URI 호스트 이름에 쌍이 있는 SBC FQDN이 있어야 합니다.

구문: 연락처: <sip:phone 또는 sip address@FQDN SBC;transport=tls> 

[RFC 3261, 섹션 11.1에](https://tools.ietf.org/html/rfc3261#section-11.1)따라 옵션 메시지에 연락처 헤더 필드가 있을 수 있습니다. 직접 라우팅에서 연락처 헤더가 필요합니다. 위의 형식의 INVITE 메시지의 경우 옵션 메시지의 경우 SIP URI에서 userinfo를 제거할 수 있으며 다음과 같이 FQDN 형식으로만 전송할 수 있습니다.

구문: 연락처: <sip:FQDN의 SBC;transport=tls>

이 이름(FQDN)은 제시된 인증서의 공통 이름 또는 주체 대체 이름 필드에 있어야 합니다. Microsoft는 인증서의 일반 이름 또는 주체 대체 이름 필드에서 이름의 와일드카드 값을 사용할 수 있습니다.   

와일드카드에 대한 지원은 [RFC 2818, 섹션 3.1에 설명되어 있습니다.](https://tools.ietf.org/html/rfc2818#section-3.1) 특히:

*"이름에는 단일 도메인 이름 구성 요소 또는 구성 요소 조각과 일치하는 것으로 간주되는 와일드카드 \* 문자가 포함될 수 있습니다. 예: .a.com 일치하지만 foo.a.com \* bar.foo.a.com. f .com은 foo.com 일치하지만 \* bar.com."*

SIP 메시지에 있는 연락처 헤더에 두 개 이상의 값이 SBC에서 전송되는 경우 연락처 헤더의 첫 번째 값의 FQDN 부분만 사용됩니다.

직접 라우팅의 경우 원칙적으로 FQDN을 사용하여 IP 대신 SIP URI를 채우는 것이 중요합니다. 호스트 이름을 FQDN이 아닌 IP로 표시하는 연락처 헤더를 사용하여 SIP 프록시에 들어오는 INVITE 또는 OPTIONS 메시지는 403 금지된 연결로 거부됩니다.

#### <a name="request-uri"></a>Request-URI 

들어오는 모든 호출의 경우 Request-URI를 사용하여 전화 번호를 사용자와 일치합니다.   

현재 전화 번호는 다음 예제와 같이 더하기 기호(+)를 포함해야 합니다. 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```
#### <a name="from-header"></a>헤더에서

들어오는 모든 통화의 경우 From 헤더는 발신자의 전화 번호와 발신자 차단된 전화 번호 목록과 일치하는 데 사용됩니다.

전화 번호는 다음 예제와 같이 +를 포함해야 합니다.

```console
From: <sip:+17168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679
```

## <a name="contact-and-record-route-headers-considerations"></a>연락처 및 Record-Route 고려 사항

SIP 프록시는 새 대화 상자 클라이언트 트랜잭션(예: Bye 또는 다시 초대) 및 SIP 옵션에 회신할 때 다음 홉 FQDN을 계산해야 합니다. 연락처 또는 Record-Route 사용됩니다. 

[RFC 3261, 섹션 8.1.1.8에](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)따라 연락처 헤더는 새 대화 상자가 될 수 있는 모든 요청에 필요합니다. Record-Route 프록시가 대화 상자에서 향후 요청 경로에 유지하려는 경우만 필요합니다. 프록시 SBC가 직접 라우팅에 대한 [로컬 미디어](./direct-routing-media-optimization.md)최적화와 함께 사용 중이면 프록시 SBC가 경로에 유지해야 하여 레코드 경로를 구성해야 합니다. 

프록시 SBC를 사용하지 않는 경우 연락처 헤더만 사용하는 것이 좋습니다.

- [RFC 3261, 섹션 20.30](https://tools.ietf.org/html/rfc3261#section-20.30), Record-Route 프록시가 대화 상자의 향후 요청 경로를 유지하려는 경우 사용됩니다. 모든 트래픽이 Microsoft SIP 프록시와 페어링된 SBC 간에 진행될 때 프록시 SBC가 구성되지 않는 경우 필수는 없습니다. 

- Microsoft SIP 프록시는 아웃바운드 ping 옵션을 보낼 때 다음 홉을 결정하기 위해 연락처 헤더(레코드-경로 아 아닌)만 사용합니다. 프록시 SBC를 사용하지 않는 경우 두 매개 변수(연락처 및 레코드 경로)가 아닌 하나의 매개 변수(연락처)를 구성하면 관리가 간소화됩니다. 

다음 홉을 계산하기 위해 SIP 프록시는 다음을 사용 합니다.

- 우선 순위 1. 최상위 레코드 경로입니다. 최상위 수준 Record-Route FQDN 이름이 포함된 경우 FQDN 이름은 아웃바운드 대화 상자 연결을 만드는 데 사용됩니다.

- 우선 순위 2. 연락처 헤더입니다. Record-Route 없는 경우 SIP 프록시는 연락처 헤더 값을 찾아 아웃바운드 연결을 확인합니다. (권장되는 구성입니다.)

연락처 및 Record-Route 모두 사용하는 경우 SBC 관리자는 해당 값을 동일하게 유지해야 하여 관리 오버헤드가 발생합니다. 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a>연락처 또는 연락처에서 FQDN 이름을 Record-Route

IP 주소의 사용은 연락처 또는 연락처에서 Record-Route 없습니다. 지원되는 유일한 옵션은 SBC 인증서의 일반 이름 또는 주체 대체 이름과 일치해야 하는 FQDN입니다(인증서의 와일드카드 값이 지원됩니다).

- IP 주소가 레코드 경로 또는 연락처에 있는 경우 인증서 검사가 실패하고 호출이 실패합니다.

- FQDN이 제시된 인증서의 일반 또는 주체 대체 이름 값과 일치하지 않는 경우 호출이 실패합니다. 

## <a name="inbound-call-sip-dialog-description"></a>인바운드 호출: SIP 대화 상자 설명

아래 표에서는 비우회 모드와 우회 모드 간의 호출 흐름 차이 및 유사성에 대한 요약을 요약합니다.

| 매개 변수 이름 | 비우회 모드 | 우회 모드
| :---------------------  |:---------------------- |:----------------|
| 183개 및 200개 메시지의 미디어 후보 | 미디어 프로세서 | 클라이언트 | 
| SBC에서 받을 수 있는 메시지 수 183개 | 세션당 1개 | 다중 | 
| 잠정 답변(183)으로 통화할 수 있습니다. | 예 | 예 |
| 잠정 응답 없이 통화할 수 있습니다(183) | 예 | 예 |

###  <a name="non-media-bypass-flow"></a>비미디어 우회 흐름

Teams 여러 엔드포인트가 동시에 있을 수 있습니다. 예를 들어 Teams 클라이언트에 Windows 클라이언트에 대해 Teams iPhone 및 Teams 전화(Teams Android 클라이언트). 각 엔드포인트는 다음과 같이 HTTP 나머지를 신호할 수 있습니다.

-   호출 진행률 - SIP 프록시에서 SIP 메시지 180으로 변환됩니다. 메시지 180을 수신할 때 SBC는 로컬 벨소리를 생성해야 합니다.

-   미디어 답변 - SDP(세션 설명 프로토콜)에서 미디어 후보를 사용하여 SIP 프록시에서 메시지 183으로 변환됩니다. 메시지 183을 수신할 때 SBC는 SDP 메시지에 수신된 미디어 후보에 연결할 것으로 예상합니다. 

    > [!NOTE]
    > 경우에 따라 미디어 답변이 생성되지 않을 수 있으며, 엔드포인트가 "수락된 통화" 메시지로 응답할 수 있습니다.

-   수락된 호출 - SIP 프록시에서 SDP를 사용하여 SIP 메시지 200으로 변환됩니다. 메시지 200을 수신할 때 SBC는 제공된 SDP 후보에게 미디어를 보내고 받을 것으로 예상됩니다.

    > [!NOTE]
    > 직접 라우팅은 지연된 제품 초대(SDP 없이 초대)를 지원하지 않습니다.

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a>잠정 답변으로 울리는 여러 엔드포인트

1.  SBC에서 첫 번째 초대를 받을 때 SIP 프록시는 "SIP SIP/2.0 100 Trying"을 보내고 들어오는 호출에 대한 모든 최종 사용자 엔드포인트를 알림합니다. 

2.  알림이 표시될 때 각 엔드포인트가 울리기 시작하고 SIP 프록시에 "통화 진행률" 메시지를 보내기 시작합니다. 사용자가 Teams 엔드포인트가 여러 개 있을 수 있기 때문에 SIP 프록시는 여러 통화 진행률 메시지를 수신할 수 있습니다.

3.  클라이언트에서 받은 모든 호출 진행률 메시지에 대해 SIP 프록시는 호출 진행률 메시지를 SIP 메시지 "SIP SIP/2.0 180 시도"로 변환합니다. 이러한 메시지를 보내는 간격은 통화 컨트롤러에서 메시지를 받는 간격으로 정의됩니다. 다음 다이어그램에는 SIP 프록시에 의해 생성된 180개의 메시지가 두 개 있습니다. 이러한 메시지는 사용자의 두 Teams 엔드포인트에서 나타납니다. 클라이언트마다 고유한 태그 ID가 있습니다.  다른 엔드포인트에서 오는 모든 메시지는 별도의 세션입니다("To" 필드의 매개 변수 "태그"는 다를 수 있습니다). 그러나 엔드포인트는 다음 다이어그램과 같이 메시지 180을 생성하고 메시지 183을 바로 보내지 않을 수 있습니다.

4.  엔드포인트가 엔드포인트 미디어 후보의 IP 주소가 있는 미디어 응답 메시지를 생성하면 SIP 프록시는 받은 메시지를 클라이언트의 SDP로 "SIP 183 세션 진행률" 메시지로 변환하여 미디어 프로세서의 SDP로 바 대체합니다. 다음 다이어그램에서 Fork 2의 엔드포인트가 호출에 응답합니다. 트렁크를 무시하지 않은 경우 183 SIP 메시지는 한 번만 생성됩니다(링 봇 또는 클라이언트 엔드포인트). 183은 기존 포크에 오거나 새 포크를 시작할 수 있습니다.

5.  호출 수락 메시지는 호출을 수락한 엔드포인트의 최종 후보와 함께 전송됩니다. 호출 수락 메시지는 SIP 메시지 200으로 변환됩니다. 

> [!div class="mx-imgBorder"]
> ![잠정 답변으로 울리는 여러 엔드포인트를 보여주는 다이어그램입니다.](media/direct-routing-protocols-1.png)

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a>잠정 답변 없이 울리는 여러 엔드포인트

1.  SBC에서 첫 번째 초대를 받을 때 SIP 프록시는 "SIP SIP/2.0 100 Trying"을 보내고 들어오는 호출에 대한 모든 최종 사용자 엔드포인트를 알림합니다. 

2.  알림이 표시될 때 각 엔드포인트가 울리기 시작하고 SIP 프록시에 "통화 진행률"을 보내기 시작할 것입니다. 사용자가 Teams 엔드포인트가 여러 개 있을 수 있기 때문에 SIP 프록시는 여러 통화 진행률 메시지를 수신할 수 있습니다.

3.  클라이언트에서 받은 모든 호출 진행률 메시지에 대해 SIP 프록시는 호출 진행률 메시지를 SIP 메시지 "SIP SIP/2.0 180 시도"로 변환합니다.  메시지를 보내는 간격은 통화 컨트롤러에서 메시지를 받는 간격으로 정의됩니다. 아래 그림에는 SIP 프록시에서 생성된 2개의 180개의 메시지가 있습니다. 즉, 사용자가 3개의 클라이언트에 Teams 각 클라이언트가 호출 진행률을 전송합니다. 모든 메시지는 별도의 세션이 됩니다("To" 필드의 매개 변수 "tag"가 다를 수 있습니다.

4.  호출 수락 메시지는 호출을 수락한 엔드포인트의 최종 후보와 함께 전송됩니다. 호출 수락 메시지는 SIP 메시지 200으로 변환됩니다. 

> [!div class="mx-imgBorder"]
> ![잠정 답변 없이 울리는 여러 엔드포인트를 보여주는 다이어그램입니다.](media/direct-routing-protocols-2.png)

### <a name="media-bypass-flow"></a>미디어 우회 흐름

미디어 우회 시나리오에서 동일한 메시지(100 시도, 180, 183)가 사용됩니다. 

아래 schema는 우회 호출 흐름의 예제를 보여줍니다. 

> [!NOTE]
> 미디어 후보는 서로 다른 엔드포인트에서 올 수 있습니다. 

> [!div class="mx-imgBorder"]
> ![잠정 답변으로 울리는 여러 엔드포인트를 보여주는 다이어그램입니다.](media/direct-routing-protocols-3.png)

## <a name="replaces-option"></a>대체 옵션

SBC는 Replaces로 초대를 지원해야 합니다.

## <a name="size-of-sdp-considerations"></a>SDP 고려 사항의 크기

직접 라우팅 인터페이스는 1,500 byte를 초과하는 SIP 메시지를 보낼 수 있습니다.  SDP의 크기는 주로 이로 인해 발생합니다. 그러나 SBC 뒤에 UDP 트렁크가 있는 경우 Microsoft SIP 프록시에서 변경되지 않은 트렁크로 전달된 경우 메시지를 거부할 수 있습니다. 메시지를 UDP 트렁크로 보낼 때 SBC의 SDP에서 일부 값을 제거하는 것이 좋습니다. 예를 들어 ICE 후보 또는 사용되지 않는 코덱을 제거할 수 있습니다.

## <a name="call-transfer"></a>통화 전환

직접 라우팅은 통화 전송에 대한 두 가지 방법을 지원합니다.

- 옵션 1. SIP 프록시 프로세스는 클라이언트에서 로컬로 참조하고 RFC 3892의 섹션 7.1에 설명된 바와 같이 심판 역할을 합니다.

  이 옵션을 사용하면 SIP 프록시가 전송을 종료하고 새 초대를 추가합니다. 


- 옵션 2. SIP 프록시는 SBC 참조를 보내고 RFC 5589의 섹션 6에서 설명하는 전송자 역할을 합니다.

  이 옵션을 사용하면 SIP 프록시는 SBC 참조를 보내고 SBC가 전송을 완전히 처리하기를 기대합니다.

SIP 프록시는 SBC에서 보고하는 기능에 따라 메서드를 선택합니다. SBC가 메서드 "참조"를 지원하고 있는 경우 SIP 프록시는 통화 전송에 옵션 2를 사용합니다.

다음은 참조 메서드가 지원되는 메시지를 보내는 SBC의 예입니다.

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

SBC에서 지원되는 메서드로 참조를 나타내지 않는 경우 직접 라우팅은 Option 1(SIP 프록시는 심판 역할을 합니다)을 사용합니다. 또한 SBC는 알림 메서드를 지원하는지 신호해야 합니다.

참조 메서드가 지원되지 않는다는 것을 나타내는 SBC의 예:

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a>SIP 프록시 프로세스는 클라이언트에서 로컬로 참조하고 심판 역할을 합니다.

SBC에서 참조 메서드가 지원되지 않는다고 표시한 경우 SIP 프록시는 심판 역할을 합니다. 

클라이언트에서 오는 참조 요청은 SIP 프록시에서 종료됩니다. (클라이언트의 참조 요청은 다음 다이어그램에서 "Dave로 전화 전송"으로 표시됩니다.  자세한 내용은 [RFC 3892의 7.1 섹션을 참조하세요.](https://www.ietf.org/rfc/rfc3892.txt) 

> [!div class="mx-imgBorder"]
> ![잠정 답변으로 울리는 여러 엔드포인트를 보여주는 다이어그램입니다.](media/direct-routing-protocols-4.png)

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a>SIP 프록시는 SBC 참조를 보내고 전송자 역할을 합니다.

이 방법은 통화 전송에 선호되는 방법으로, 미디어 우회 인증을 찾는 디바이스에 필수입니다. 참조를 처리할 수 있는 SBC가 없는 통화 전송은 미디어 우회 모드에서 지원되지 않습니다. 

표준은 RFC 5589의 섹션 6에 설명됩니다. 관련 RFC는:

- [SIP(세션 시작 프로토콜) 호출 제어 - 전송](https://tools.ietf.org/html/rfc5589)

- [SIP(세션 시작 프로토콜) "대체" 헤더](https://tools.ietf.org/html/rfc3891)

- [세션 시작 프로토콜(SIP) "Referred-By" 메커니즘](https://tools.ietf.org/html/rfc3892)

이 옵션은 SIP 프록시가 전송자 역할을 하여 SBC에 참조 메시지를 보낸 것으로 가정합니다. SBC는 전송자 역할을 하며 참조를 처리하여 새 전송 제안을 생성합니다. 두 가지 가능한 경우가 있습니다.

- 호출은 외부 PSTN 참가자로 전송됩니다. 
- 호출은 SBC를 통해 동일한 Teams 사용자로 Teams 다른 사용자로 전송됩니다. 

호출이 SBC를 통해 다른 사용자로 Teams 경우 SBC는 참조 메시지에 수신된 정보를 사용하여 전송 대상(Teams 사용자)에 대한 새 초대(새 대화 상자 시작)를 발급해야 합니다. 

요청 트랜잭션에 대한 To/Transferor 필드를 내부적으로 채우기 위해 SIP 프록시는 REFER-TO/REFERRED-BY 헤더 내에서 이 정보를 전달해야 합니다. 

SIP 프록시는 호스트 이름의 SIP 프록시 FQDN으로 구성된 SIP URI로 REFER-TO를 형성하고 다음 중 하나를 형성합니다.

- 전송 대상이 전화 번호인 경우 URI의 사용자 이름 부분의 E.164 전화 번호

- 전체 전송 대상 MRI 및 테넌트 ID를 각각 인코딩하는 x-m 및 x-t 매개 변수 

REFERRED-BY 헤더는 다음 표와 같이 전송자 테넌트 ID 및 기타 전송 컨텍스트 매개 변수뿐만 아니라 전송자 MRI가 인코딩된 SIP URI입니다.

| 매개 변수 | 값 | 설명 |  
|:---------------------  |:---------------------- |:---------------------- |
| x-m | MRI | CC에 의해 채워진 전송기/전송 대상의 전체 MRI |
| x-t | 테넌트 ID | x-t 테넌트 ID 선택적 테넌트 ID가 CC로 채워진 경우 |
| x-ti | 전송자 상관 관계 ID | 전송자에 대한 호출의 상관 관계 ID |
| x-tt | 전송 대상 호출 URI | 인코딩된 호출 대체 URI |

참조 헤더의 크기는 이 경우 최대 400개 기호일 수 있습니다. SBC는 최대 400개 기호 크기의 참조 메시지 처리를 지원해야 합니다.

> [!div class="mx-imgBorder"]
> ![잠정 답변으로 울리는 여러 엔드포인트를 보여주는 다이어그램입니다.](media/direct-routing-protocols-5.png)

## <a name="session-timer"></a>세션 시간

SIP 프록시는 비우회 호출에서 세션 시간(항상 제공)을 지원하지만, 우회 호출에서는 제공되지 않습니다. SBC에서 세션 시간(Session Timer)을 사용하는 것은 필수가 아닙니다.

##  <a name="use-of-request-uri-parameter-userphone"></a>Request-URI 매개 변수 user=phone 사용

SIP 프록시는 Request-URI를 분석하고 매개 변수 user=phone이 있는 경우 서비스는 Request-URI를 전화 번호로 처리하여 사용자와 번호가 일치합니다. 매개 변수가 없는 경우 SIP 프록시는 요청-URI 사용자 유형(전화 번호 또는 SIP 주소)을 결정하기 위해 heuristics를 적용합니다.

호출 설정 프로세스를 간소화하기 위해 항상 user=phone 매개 변수를 적용하는 것이 좋습니다.

## <a name="history-info-header"></a>History-Info 헤더

History-Info 헤더는 SIP 요청을 리타게팅하는 데 사용됩니다. "제공(을) 네트워크 및 최종 사용자에 대한 다양한 서비스를 사용하도록 요청 기록 정보를 캡처하기 위한 표준 메커니즘"입니다. 자세한 내용은 [RFC 4244 – 섹션 1.1 을 참조하세요.](http://www.ietf.org/rfc/rfc4244.txt) Microsoft 전화 시스템의 경우 이 헤더는 Simulring 및 Call Forwarding 시나리오에서 사용됩니다.  

보내는 경우 다음과 History-Info 활성화됩니다.

- SIP 프록시는 PSTN 컨트롤러로 전송된 History-Info 구성하는 개별 History-Info 전화 번호가 포함된 매개 변수를 삽입합니다.  전화 번호 매개 변수가 있는 항목만 사용하여 PSTN 컨트롤러는 새 History-Info 헤더를 다시 작성하고 SIP 프록시를 통해 SIP 트렁크 공급자에 전달합니다.

- History-Info 링 및 통화 전달 사례에 대한 추가 헤더가 추가됩니다.

- History-Info 전송 사례에 대해 헤더가 추가되지 않습니다.

- 재구성된 History-Info 헤더의 개별 기록 항목에는 URI의 호스트 부분으로 설정된 직접 라우팅 FQDN(sip.pstnhub.microsoft.com)과 함께 제공되는 전화 번호 매개 변수가 있습니다. 'user=phone'의 매개 변수가 SIP URI의 일부로 추가됩니다.  전화 컨텍스트 매개 변수를 제외한 원래 History-Info 다른 매개 변수는 다시 생성된 History-Info 전달됩니다.  

  > [!NOTE]
  > 개인 항목(RFC 4244의 섹션 3.3에 정의된 메커니즘에 따라 결정)은 SIP 트렁크 공급자가 신뢰할 수 있는 피어이기 때문에 전달됩니다.

- 인바운드 History-Info 무시됩니다.

다음은 SIP 프록시에서 보낸 기록 정보 헤더의 형식입니다.

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

호출이 여러 번 리디렉션된 경우 모든 리디렉션에 대한 정보가 시간 순서대로 적절한 이유에 포함됩니다.


헤더 예제:

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

History-Info TLS 메커니즘으로 보호됩니다. 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a>직접 라우팅 및 장애 조치 메커니즘에 대한 SBC 연결

직접 라우팅 계획의 SIP 신호에 대한 장애 조치 메커니즘 [섹션을 참조하세요.](direct-routing-plan.md#failover-mechanism-for-sip-signaling)

## <a name="retry-after"></a>Retry-After

직접 라우팅 데이터 센터가 사용 중이면 서비스는 1초 간격으로 Retry-After 메시지를 SBC로 보낼 수 있습니다. SBC에서 INVITE에 대한 응답으로 Retry-After 503 메시지를 수신하면 SBC는 해당 연결을 종료하고 사용 가능한 다음 Microsoft 데이터 센터를 시도해야 합니다.

## <a name="handling-retries-603-response"></a>재시도 처리(603 응답)
최종 사용자가 들어오는 호출을 감소한 후에 하나의 호출에 대해 여러 번 누락된 호출을 관찰하는 경우 SBC 또는 PSTN 트렁크 공급자의 재시도 메커니즘이 잘못 구성됩니다. 603 응답에서 재시도 노력을 중지하려면 SBC를 다시 구성해야 합니다.

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a>ICE 다시 시작: 미디어 우회를 지원하지 않는 엔드포인트로 전송된 미디어 우회 호출

SBC는 [RFC 5245 섹션 9.1.1.1에](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)설명된 바와 같이 ICE 다시 시작을 지원해야 합니다.

직접 라우팅에서 다시 시작은 RFC의 다음 단락에 따라 구현됩니다.

*ICE를 다시 시작하려면 에이전트가 제안의 미디어 스트림에 대한 ice-pwd 및 ice-ufrag를 모두 변경해야 합니다.  한 제안에서 세션 수준 특성을 사용할 수 있지만, 후속 제안에서 미디어 수준 특성으로 동일한 ice-pwd 또는 ice-ufrag를 제공하는 것이 제한됩니다.  이는 암호의 변경이 아니라 표현의 변경일 뿐만 아니라 ICE 다시 시작을 유발하지 않습니다.*

*에이전트는 이 미디어 스트림의 초기 제안에서와 같은 이 미디어 스트림에 대한 SDP의 나머지 필드를 설정합니다(섹션 4.3 참조).  따라서 후보 집합에는 해당 스트림에 대한 일부, 없음 또는 모든 이전 후보가 포함될 수 있으며, 4.1.1 섹션에 설명된 바와 같이 수집된 완전히 새로운 후보 집합이 포함될 수 있습니다.*

처음에 미디어 우회를 사용하여 호출이 설정되어 호출이 비즈니스용 Skype 경우 직접 라우팅은 미디어 프로세서를 삽입해야 합니다. 직접 라우팅은 미디어 우회가 있는 비즈니스용 Skype 사용할 수 있기 때문에입니다. 직접 라우팅은 ice-pwd 및 ice-ufrag를 변경하고 새로운 미디어 후보를 다시 시작하여 ICE 다시 시작 프로세스를 시작합니다.
