---
title: PSTN 연결 옵션
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: 자세한 내용은 Teams(PSTN 연결) 옵션 및 조직에 대해 내릴 결정에 대해 자세히 알아보하세요.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c53b553a83349c3d4fd20a926f29b4c727175c73aba5ba0f5e352cf19a53f9e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54285944"
---
# <a name="pstn-connectivity-options"></a>PSTN 연결 옵션

Microsoft는 조직을 위해 Exchange PBX(Private Branch 전화 시스템) 기능을 전화 시스템. 그러나 사용자가 조직 외부에서 전화를 걸 수 있도록 설정하려면 PSTN(전화 시스템 전화망)에 연결해야 합니다.

이 문서에서는 PSTN 연결 옵션에 초점을 맞추고 있습니다. Microsoft 음성 솔루션에 대한 자세한 내용은 전화 시스템 음성 솔루션 계획을 Teams [참조하세요.](cloud-voice-landing-page.md)

PSTN에 전화 시스템 연결하기 위해 다음 옵션 중 선택할 수 있습니다.

- [**통화 플랜**](#phone-system-with-calling-plan). PSTN 통신 사업자인 Microsoft와 클라우드에서 모두 사용할 수 있는 솔루션입니다.

- [**연산자는 커넥트**](#phone-system-with-operator-connect)현재 공개 미리 보기에서만 사용할 **수 있습니다.**  통신사 커넥트 Microsoft Operator 커넥트 프로그램의 참가자인 경우 PSTN 통화 및 SC(Session Border Controller)를 관리할 수 있습니다. 

- [**직접 라우팅**](#phone-system-with-direct-routing)- SBC(Session Border Controller)를 연결하여 자체 PSTN 통신 사업자만 사용할 수 전화 시스템.


복잡한 환경에 대한 솔루션을 디자인하거나 다단계 마이그레이션을 관리할 수 있는 옵션 조합을 선택할 수도 있습니다.

선택하는 옵션 또는 옵션은 일부 구성 전화 시스템 영향을 받도록 합니다. 자세한 내용은 이 문서 의 [부분에 있는 구성](#configuration-considerations) 고려 사항을 참조하십시오.


## <a name="phone-system-with-calling-plan"></a>통화 요금제의 전화 시스템 

전화 시스템 플랜을 통해 사용자는 Microsoft의 클라우드 내 모든 음성 Teams 있습니다. 이 옵션은 PSTN에 전화 시스템 가장 간단한 옵션입니다. 이 옵션을 사용하면 Microsoft는 다음 다이어그램과 같이 PSTN 통신 사업자 역할을 합니다.

![다이어그램 1은 전화 시스템 플랜을 보여 주며,](media/voice-solutions-simple.png)

다음에 대해 예라고 대답하면 전화 시스템 플랜을 사용할 수 있는 것이 가장 적합한 솔루션입니다.

- 통화 플랜은 사용자 지역에서 사용할 수 있습니다.
- 현재 PSTN 통신 사업자만 보유할 필요는 없습니다.
- PSTN에 대한 Microsoft 관리 액세스를 사용하려는 경우

이 옵션을 사용하는 경우: 

- Microsoft 전화 시스템에는 라이선스가 부여된 서비스 수준에 따라 전 세계 전화기로 전화를 걸 수 있는 국내 또는 국제 통화 플랜이 추가되었습니다.

- 통화 플랜은 프레미스 배포에서만 작동하기 때문에 배포 또는 유지 관리가 &mdash; Microsoft 365.

- 참고: 필요한 경우 타사 PBX, 아날로그 장치 및 SBC에서 지원하는 기타 타사 전화 통신 장비와의 상호 연동을 위해 직접 라우팅을 통해 지원되는 SBC(Session Border Controller)를 연결하기로 선택할 수 있습니다.

이 옵션을 사용하려면 Microsoft 365에 중단 없이 연결해야 합니다.

통화 플랜에 대한 자세한 내용은 다음 문서를 참조하세요.

- [사용자에게 적합한 통화 플랜은 무엇인가요?](calling-plan-landing-page.md)
- [통화 플랜을 구입하는 방법](calling-plans-for-office-365.md)
- [통화 플랜의 국가 및 지역 가용성](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [통화 플랜 설정](set-up-calling-plans.md)


## <a name="phone-system-with-operator-connect"></a>전화 시스템 연산자를 커넥트

통신사 커넥트 현재 공개 미리 보기에서 기존 통신사가 Microsoft Operator 커넥트 프로그램의 참가자인 경우 PSTN 통화를 다른 통신사로 가져오기 위한 서비스를 관리할 Teams. 통신 사업자에서 PSTN 통화 서비스 및 SC(Session Border Controller)를 관리하므로 하드웨어 구매 및 관리를 저장할 수 있습니다.

연산자 커넥트 조직에 적합한 솔루션이 될 수 있습니다.

- Microsoft 통화 플랜은 지리적 위치에서 사용할 수 없습니다.
- 기본 통신사는 Microsoft Operator 커넥트 프로그램의 참가자입니다.
- 새 통신 사업자(통신사)를 찾아 해당 통신사에서 통화를 사용하도록 Teams.

통신사 서비스 혜택 및 요구 사항에 대한 자세한 커넥트 이 프로그램에 참여하는 통신사 목록은 [Plan Operator 커넥트.](operator-connect-plan.md) 연산자 설정을 구성하는 방법에 대한 자세한 내용은 커넥트 연산자 구성을 [커넥트.](operator-connect-configure.md)


## <a name="phone-system-with-direct-routing"></a>전화 시스템 라우팅을 통해 연결

이 옵션은 전화 시스템 다이어그램과 같이 직접 라우팅을 사용하여 전화 통신 네트워크에 연결합니다. 

![다이어그램 5에는 직접 전화 시스템 있는 사용자 수가 표시됩니다.](media/voice-solution-with-direct-routing.png)

다음 질문에 예라고 대답할 경우 직접 라우팅을 사용하는 전화 시스템이 가장 적합한 솔루션입니다.

- 전화 시스템이 있는 Teams를 사용하려고 합니다.
- 현재 PSTN 이동 통신 사업자를 유지해야 합니다.
- 일부 통화는 통화 플랜을 통과하고 일부는 이동 통신 사업자를 통해 라우팅하는 방식을 혼합하려고 합니다.
- 오버헤드 페이지, 아날로그 장치 등의 타사 PBX 및/또는 장비와 상호 연결해야 합니다.

이 옵션을 사용하는 경우:

- 지원되는 SBC(Session Border Controller)를 추가 전화 시스템 없이도 지원되는 SBC(Session Border Controller)를 연결합니다.

- 가상의 모든 전화 통신 통신 사업자 및 통신사와 함께 전화 시스템.

- 이 옵션을 구성 및 관리하도록 선택할 수도 있고, 통신사나 파트너가 구성 및 관리할 수도 있습니다(통신사 또는 파트너가 이 옵션을 제공하는지 확인).

- 타사 PBX와 아날로그 장치와 같은 전화 통신 장비와 장치 간의 상호 &mdash; &mdash; 전화 시스템.

이 옵션을 사용하려면 다음이 필요합니다.

- Microsoft 365에 대한 무중단 연결

- 지원되는 SBC를 배포 및 유지 관리

- 타 이동 통신 사업자와 체결한 계약(통화 플랜을 통해 전화 시스템을 사용하는 사용자를 위해 타사 PBX, 아날로그 장치 또는 다른 전화 통신 장비에 대한 연결을 제공하는 옵션으로 배포하는 경우 제외)

직접 라우팅에 대한 자세한 내용은 다음 문서를 참조하세요.

- [직접 라우팅 계획](direct-routing-plan.md)
- [직접 라우팅 구성](direct-routing-configure.md)
- [직접 라우팅에 사용할 음성 라우팅 정책 관리](manage-voice-routing-policies.md)
- [직접 라우팅으로 전달되는 위치 기반 라우팅 계획](location-based-routing-plan.md)
- [직접 라우팅으로 인증된 SBC(Session Border Controller) 목록](direct-routing-border-controllers.md)



## <a name="configuration-considerations"></a>구성 고려 사항

대부분의 전화 시스템 기능은 선택한 PSTN 연결 옵션에 관계없이 동일합니다. 예를 들어, 지원되지 않는 통화 및 전달 설정, 통화 전송, 사용자 지정 보류 음악, 통화 파킹된 통화, 공유 라인 및 음성 앱을 모두 사용할 수 있습니다. 전체 전화 시스템 목록은 에서 사용할 수 있는 [전화 시스템.](here-s-what-you-get-with-phone-system.md)

그러나 특정 구성 기능 구성 방법에 영향을 주는 몇 가지 기능 전화 시스템 있습니다. 예를 들어 직접 라우팅에는 통화 라우팅을 구성하기 위한 추가 단계가 필요합니다. 또 다른 예로, 직접 라우팅은 LBR(Location-Based-Routing)을 제공하여 허용되지 않는 특정 지리적 위치에서는 무료 우회를 제한할 수 있습니다. 

다음 표에는 주요 구성 차이점이 강조되어 있습니다. 표 다음에 있는 섹션에서는 추가 정보 및 세부 정보에 대한 링크를 제공합니다.

| 옵션 | 설명 | 전화 번호 관리 | 통화 라우팅 | 긴급 통화 가용성 |
| :------------| :-------| :-------| :-------| :-------| 
| 통화 플랜 | -Microsoft는 PSTN 통신 사업자 역할을 합니다.<br>-SC를 구입하거나 관리할 필요가 없습니다.| Microsoft를 통해 획득합니다.| -Managed by Microsoft. <br> -Admin은 번호 변환을 위해 사용자 다이얼 플랜을 구성합니다. | -Microsoft에서 사용 가능. <br> -Admin은 주소를 등록합니다. <br> -동적 호출이 지원됩니다. |
| 운영자 연결 | -통신 사업자에서 PSTN 연결 및 SBC를 관리합니다. <br> -SC를 구입하거나 관리할 필요가 없습니다. | -이동 통신 사업자에서 획득합니다. <br> - 통신 사업자에 의해 관리되는 응급 주소와 관련된 번호입니다.  | -통신 사업자에 의해 관리됩니다. <br>-Admin은 번호 변환을 위해 사용자 다이얼 플랜을 구성합니다. | -통신 사업자에 의해 사용 가능. <br> -Admin은 주소를 등록합니다. <br> -동적 호출이 지원됩니다. |
| 직접 라우팅 | -타사 공급업체에서 구입한 인증된 SBC가 필요합니다.<br>-커넥트 SBC를 전화 시스템.<br> -기존 PSTN 통신 사업자 사용. | 이동 통신 사업자에서 획득합니다. | -관리자가 추가 구성을 요구합니다.<br>-Admin은 번호 변환을 위해 트렁크 다이얼 플랜을 구성합니다. <br>-LBR을 통해 이용자 우회를 제한할 수 있습니다. | -관리자가 추가 구성을 요구합니다. <br>-등록된 주소가 지원되지 않습니다. <br>-동적 호출은 지원되지만 추가 구성이 필요합니다. |
|||||


### <a name="phone-number-management"></a>전화 번호 관리

Microsoft에는 두 가지 유형의 전화 번호를 사용할 수 있습니다. 즉, 조직의 사용자에게 할당할 수 있는 구독자(사용자) 번호와 무료 서비스 번호로 사용할 수 있는 서비스 번호가 있습니다. 서비스 번호는 구독자 번호보다 동시 통화 용량이 높고 오디오 회의, 자동 전화 번호 또는 통화 큐와 같은 서비스에 할당할 수 있습니다.

다음을 결정해야 합니다.

- Microsoft의 새 전화 번호가 필요한 사용자 위치는 무엇입니까?
- 어떤 유형의 전화 번호(구독자 또는 서비스)가 필요한가요?
- 기존 전화 번호를 이식하여 이식하는 Teams?

전화 번호를 획득하고 관리하는 방법은 PSTN 연결 옵션에 따라 다릅니다.

- 통화 플랜의 전화 번호를 관리하는 데 대한 자세한 내용은 조직의 전화 [번호 관리를 참조하세요.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Operator를 통해 전화 번호를 관리하는 커넥트 연산자를 통해 전화 번호 [커넥트.](operator-connect-configure.md#set-up-phone-numbers)

- 직접 라우팅의 전화 번호를 관리하는 데 대한 자세한 내용은 전화 번호 구성 및 Enterprise Voice 및 음성메일 사용 을 [참조하세요.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)


### <a name="call-routing-and-dial-plans"></a>통화 라우팅 및 다이얼 플랜

통화 라우팅을 구성하는 방법은 PSTN 연결 옵션에 따라 다릅니다.  

- 통화 플랜의 경우 대부분의 통화 라우팅은 Microsoft 통화 플랜 인프라에서 처리됩니다. 통화 권한 부여 및 통화 라우팅을 위한 번호 변환을 위해 사용자 다이얼 플랜을 구성합니다. 자세한 내용은 [다이얼 플랜이란? 을 참조하세요.](what-are-dial-plans.md)

- 통신사 커넥트 대부분의 통화 라우팅은 통신사에서 관리합니다.  통화 권한 부여 및 통화 라우팅을 위한 번호 변환을 위해 사용자 다이얼 플랜을 구성합니다. 자세한 내용은 [다이얼 플랜이란? 을 참조하세요.](what-are-dial-plans.md)

- 직접 라우팅의 경우 음성 경로를 지정하고 사용자에게 음성 라우팅 정책을 할당하여 통화 라우팅을 구성해야 합니다. SC(Session Border Controller)와의 상호 연동성을 보장하기 위해 트렁크 수준에서 번호 변환에 대한 다이얼 플랜을 구성할 수 있습니다. 자세한 내용은 [직접](direct-routing-voice-routing.md)라우팅에 대한 음성 라우팅 [구성,](manage-voice-routing-policies.md) 음성 라우팅 정책 관리 및 전화 번호 [번역을 참조하세요.](direct-routing-translate-numbers.md) 


### <a name="location-based-routing-for-direct-routing"></a>직접 라우팅을 위한 위치 기반 라우팅

일부 국가 및 지역에서는 장거리 통화 비용을 절감하기 위해 PSTN 통신 사업자 우회를 우회하는 것이 불법입니다. Location-Based 라우팅용 LBR(Teams 라우팅)을 사용하면 해당 지리적 위치에 따라 사용자에 대해 Teams 우회를 제한할 수 있습니다. LBR을 계획 및 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [직접 라우팅으로 전달되는 위치 기반 라우팅 계획](location-based-routing-plan.md)
- [위치 기반 라우팅의 네트워크 설정 구성](location-based-routing-configure-network-settings.md)
- [직접 라우팅에 위치 기반 라우팅 사용](location-based-routing-enable.md)
- [Contoso 사례 연구: Location-Based 라우팅](voice-case-study-location-based-routing.md)<br>
  다국적 기업인 Contoso가 조직에 대한 라우팅을 Location-Based 방법에 대해 설명하고 있습니다.


### <a name="emergency-calling"></a>비상 전화

긴급 통화를 구성하는 방법은 PSTN 연결 옵션에 따라 다릅니다.

- 통화 플랜의 경우 각 사용자가 긴급 통화를 할 수 있도록 자동으로 설정되며, 등록된 긴급 주소가 할당된 전화 번호와 연결되어야 합니다. 동적 긴급 통화(Teams 클라이언트의 위치에 따라)가 지원됩니다.  

- 통신사 커넥트 경우 각 사용자가 긴급 통화를 할 수 있도록 자동으로 설정되며, 등록된 긴급 주소가 할당된 전화 번호와 연결되어 있는 데 필요하지만 통신 회사 파트너만 설정할 수 있습니다. 동적 긴급 통화(Teams 클라이언트의 위치에 따라)가 지원됩니다.

- 직접 라우팅의 경우 긴급 번호 및 연결된 라우팅 대상을 정의하기 위해 Teams 긴급 통화 라우팅 정책(TeamsEmergencyCallRoutingPolicy)을 사용하여 사용자에 대한 긴급 통화 정책을 정의해야 합니다. 직접 라우팅 사용자에 대해 등록된 긴급 위치가 지원되지 않습니다. 동적 긴급 통화의 경우 긴급 통화를 라우팅하고 파트너 연결을 위해 추가 구성이 필요합니다.

긴급 통화 개념 및 용어와 긴급 통화 및 동적 긴급 통화를 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [동적인 긴급 통화 플랜 및 구성](configure-dynamic-emergency-calling.md)
- [긴급 전화 정책 관리](manage-emergency-calling-policies.md)
- [직접 라우팅에 대한 긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)
- [Contoso 사례 연구: 긴급 통화](voice-case-study-emergency-calling.md)<br>
  소설 다국적 기업인 Contoso가 조직에 대한 긴급 통화를 구현한 방법에 대해 설명하고 있습니다.


### <a name="network-topology-for-voice-features"></a>음성 기능에 대한 네트워크 토폴로지

동적 긴급 통화 또는 직접 라우팅에 대한 Location-Based 라우팅을 배포하는 경우 이 기능에서 이러한 기능과 함께 사용하도록 네트워크 설정을 구성해야 Microsoft Teams. 네트워크 지역, 네트워크 사이트, 네트워크 서브넷 및 신뢰할 수 있는 IP 주소에 대한 네트워크 설정을 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [Microsoft Teams 클라우드 음성 기능에 대한 네트워크 설정 - 개념 및 용어](cloud-voice-network-settings.md)
- [Microsoft Teams에서 클라우드 음성 기능에 대한 네트워크 토폴로지 관리](manage-your-network-topology.md)



