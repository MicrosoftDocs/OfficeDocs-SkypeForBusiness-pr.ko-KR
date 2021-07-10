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
description: PSTN Teams(PSTN 연결) 옵션 및 조직에 대해 결정해야 하는 결정에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b1b06178b269529b1d0227ff02d529c91ba1480
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354524"
---
# <a name="pstn-connectivity-options"></a>PSTN 연결 옵션

Microsoft는 조직에 대한 PBX(Exchange)의 완전한 개인 분기 전화 시스템. 그러나 사용자가 조직 외부에서 전화를 걸 수 있도록 설정하려면 PSTN(공용 전화 시스템 전화 네트워크)에 연결해야 합니다.

이 문서에서는 PSTN 연결 옵션에 중점을 Microsoft 음성 솔루션에 대한 자세한 내용은 음성 솔루션의 전화 시스템 세부 정보를 Teams [참조하세요.](cloud-voice-landing-page.md)

PSTN에 전화 시스템 다음 옵션에서 선택할 수 있습니다.

- [**요금제 호출 입니다.**](#phone-system-with-calling-plan) PSTN 통신사로 Microsoft를 사용할 수 있는 올인원 클라우드 솔루션입니다.

- [**SBC(세션**](#phone-system-with-direct-routing)테두리 컨트롤러)를 연결하여 사용자 자신의 PSTN 캐리어를 사용할 수 있는 직접 라우팅을 전화 시스템.

- [**연산자 커넥트**](#phone-system-with-operator-connect)현재 공개 미리 보기에서만 사용할 **수 있습니다.**  연산자 커넥트 경우 기존 통신사가 Microsoft 연산자 커넥트 프로그램에 참여하는 경우 PSTN 호출 및 SBC(세션 테두리 컨트롤러)를 관리할 수 있습니다. 

복잡한 환경에 대한 솔루션을 디자인하거나 다단계 마이그레이션을 관리할 수 있는 옵션 조합을 선택할 수도 있습니다.

선택한 옵션 또는 옵션은 일부 기능 구성 방식에 전화 시스템 있습니다. 자세한 내용은 이 문서의 나중에 [구성](#configuration-considerations) 고려 사항을 참조하세요.


## <a name="phone-system-with-calling-plan"></a>전화 시스템 계획과 함께 사용할 수 있습니다. 

전화 시스템 요금제는 Microsoft의 모든 클라우드 음성 솔루션으로 사용자에 Teams 있습니다. 이 옵션은 PSTN에 전화 시스템 가장 간단한 옵션입니다. 이 옵션을 사용하면 다음 다이어그램과 같이 Microsoft는 PSTN 통신 사업자 역할을 합니다.

![다이어그램 1은 전화 시스템 계획과 함께 표시](media/voice-solutions-simple.png)

다음에 대한 예에 대답하면 전화 시스템 계획이 적합한 솔루션입니다.

- 통화 요금제는 지역에서 사용할 수 있습니다.
- 현재 PSTN 캐리어를 유지할 필요가 없습니다.
- PSTN에 대한 Microsoft 관리 액세스를 사용하려는 경우

이 옵션을 사용합니다. 

- 전 세계 Microsoft 전화 전화로 전화를 걸 수 있는 추가된 국내 또는 국제 통화 요금제가 있는 시스템(라이선스가 부여되는 서비스 수준에 따라 다를 수 있습니다.

- 호출 계획이 프레미스에서 작동하기 때문에 프레미스 배포의 배포 또는 유지 관리가 &mdash; Microsoft 365.

- 참고: 필요한 경우 SBC에서 지원하는 타사 PBX, 아날로그 디바이스 및 기타 타사 전화 통신 장비와 상호 연동성을 위해 직접 라우팅을 통해 지원되는 SBC(세션 경계 컨트롤러)를 연결할 수 있습니다.

이 옵션을 사용하려면 연결에 끊기지 Microsoft 365.

통화 계획에 대한 자세한 내용은 다음 문서를 참조하세요.

- [사용자에게 적합한 통화 플랜은 무엇인가요?](calling-plan-landing-page.md)
- [통화 플랜을 구입하는 방법](calling-plans-for-office-365.md)
- [통화 플랜의 국가 및 지역 가용성](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [통화 계획 설정](set-up-calling-plans.md)


## <a name="phone-system-with-direct-routing"></a>전화 시스템 라우팅을 통해 연결

이 옵션은 전화 시스템 다이어그램과 같이 직접 라우팅을 사용하여 전화 통신 네트워크에 연결합니다. 

![다이어그램 5에서는 직접 전화 시스템 사용하여 전화 시스템 표시](media/voice-solution-with-direct-routing.png)

다음 질문에 예로 대답하면 직접 전화 시스템 올바른 솔루션입니다.

- 사용자와 함께 Teams 전화 시스템.
- 현재 PSTN 캐리어를 유지해야 합니다.
- 라우팅을 혼합하고, 일부 호출은 통신사를 통해 통화 계획을 통해 진행됩니다.
- 타사 PBX 및/또는 오버헤드 페이지, 아날로그 디바이스 등의 장비와 상호 협력해야 합니다.

이 옵션을 사용합니다.

- 추가 프레미스 소프트웨어 없이도 지원되는 SBC(세션 전화 시스템 컨트롤러)를 연결합니다.

- 가상으로 모든 전화 통신 통신을 사용할 수 전화 시스템.

- 이 옵션을 구성하고 관리하도록 선택하거나 이동통신사 또는 파트너가 구성하고 관리할 수 있습니다(이동통신사 또는 파트너가 이 옵션을 제공하는지 묻는 질문).

- 타사 PBX와 아날로그 디바이스와 같은 전화 통신 장비와 아날로그 장치 간에 상호 &mdash; &mdash; 전화 시스템.

이 옵션에는 다음이 필요합니다.

- 연결에 대한 Microsoft 365.

- 지원되는 SBC를 배포하고 유지 관리합니다.

- 타사 통신사와의 계약입니다.
  (타사 PBX, 아날로그 디바이스 또는 기타 전화 통신 장비에 대한 연결을 제공하는 옵션으로 배포되지 않는 한, 통화 계획에 전화 시스템 있습니다.)

직접 라우팅에 대한 자세한 내용은 다음 문서를 참조하세요.

- [직접 라우팅 계획](direct-routing-plan.md)
- [직접 라우팅 구성](direct-routing-configure.md)
- [직접 라우팅에서 사용할 음성 라우팅 정책 관리](manage-voice-routing-policies.md)
- [직접 라우팅으로 전달되는 위치 기반 라우팅 계획](location-based-routing-plan.md)
- [직접 라우팅으로 인증된 SBC(Session Border Controller) 목록](direct-routing-border-controllers.md)


## <a name="phone-system-with-operator-connect"></a>전화 시스템 커넥트

연산자 커넥트 현재 공개 미리 보기에서 기존 통신업체가 Microsoft Operator 커넥트 프로그램에 참여하는 경우 PSTN 호출을 사용자에 가져오기 위한 서비스를 관리할 수 Teams. 통신사는 PSTN 호출 서비스 및 SBC(세션 테두리 컨트롤러)를 관리하므로 하드웨어 구매 및 관리를 저장할 수 있습니다.

운영자는 커넥트 경우 조직에 적합한 솔루션일 수 있습니다.

- Microsoft 통화 요금제는 지리적 위치에서 사용할 수 없습니다.
- 선호하는 통신사는 Microsoft Operator 커넥트 참여자입니다.
- 새 통신사에서 통화를 사용하도록 설정하려는 Teams.

운영자의 혜택 및 요구 사항에 대한 커넥트 이 프로그램에 참여하는 항공사 목록에 대한 자세한 내용은 [요금제 운영자](operator-connect-plan.md)커넥트. 연산자를 구성하는 방법에 대한 자세한 내용은 연산자 커넥트 [구성을 커넥트.](operator-connect-configure.md)

## <a name="configuration-considerations"></a>구성 고려 사항

대부분의 전화 시스템 기능은 선택한 PSTN 연결 옵션에 관계없이 동일합니다. 예를 들어 통화가 지원되지 않는 및 전달 설정, 통화 전송, 사용자 지정 음악 보류, 통화 공원, 공유 줄 및 음성 앱을 모두 사용할 수 있습니다. 전체 기능 목록은 전화 시스템 [전화 시스템](here-s-what-you-get-with-phone-system.md)를 참조하세요.

그러나 기능에는 몇 가지 차이점이 있습니다. 그러나 특정 기능을 구성하는 방법에 전화 시스템 있습니다. 예를 들어 직접 라우팅에는 호출 라우팅을 구성하는 추가 단계가 필요합니다. 또 다른 예로, 직접 라우팅은 LBR(Location-Based-Routing)을 제공하여 허용되지 않는 특정 지리적 위치에서 무료 우회를 제한할 수 있습니다. 


### <a name="phone-number-management"></a>전화 번호 관리

Microsoft에는 구독자(사용자) 번호와 조직의 사용자에게 할당할 수 있는 전화 번호와 무료 서비스 번호로 사용할 수 있는 서비스 번호의 두 가지 유형이 있습니다. 서비스 번호는 구독자 번호보다 동시 호출 용량이 높고 오디오 회의, 자동 참석자 또는 통화 큐와 같은 서비스에 할당할 수 있습니다.

다음을 결정해야 합니다.

- Microsoft에서 새 전화 번호가 필요한 사용자 위치는 무엇입니까?
- 어떤 유형의 전화 번호(구독자 또는 서비스)가 필요한가요?
- 기존 전화 번호를 이식하기 위해 어떻게 Teams?

전화 번호를 획득하고 관리하는 방법은 PSTN 연결 옵션에 따라 다릅니다.

- 전화 요금제에 대한 전화 번호 관리에 대한 자세한 내용은 조직의 전화 번호 [관리를 참조하세요.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- 직접 라우팅에 대한 전화 번호 관리에 대한 자세한 내용은 전화 번호 구성 및 엔터프라이즈 음성 및 음성 을 사용하도록 설정 을 [참조하세요.](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online)

- 연산자를 통해 전화 번호 관리에 대한 자세한 내용은 커넥트 로 전화 번호 설정 을 [커넥트.](operator-connect-configure.md#set-up-phone-numbers)


### <a name="call-routing-and-dial-plans"></a>통화 라우팅 및 전화 걸기 계획

호출 라우팅을 구성하는 방법은 PSTN 연결 옵션에 따라 다릅니다.  

- 호출 요금제의 경우 대부분의 통화 라우팅은 Microsoft Calling Plan 인프라에서 처리됩니다. 통화 권한 부여 및 통화 라우팅을 위해 번호 변환을 위해 사용자 다이얼 계획을 구성합니다. 자세한 내용은 전화 [요금제란?](what-are-dial-plans.md)을 참조하세요.

- 직접 라우팅의 경우 음성 경로를 지정하고 사용자에게 음성 라우팅 정책을 할당하여 통화 라우팅을 구성해야 합니다. SBC(Session Border Controller)와의 상호 연동성을 보장하기 위해 트렁크 수준에서 번호 변환을 위한 다이얼 플랜을 구성할 수 있습니다. 자세한 내용은 [직접](direct-routing-voice-routing.md)라우팅에 대한 음성 라우팅 [구성,](manage-voice-routing-policies.md) 음성 라우팅 정책 관리 및 전화 [번호 번역을 참조하세요.](direct-routing-translate-numbers.md) 

- 연산자 커넥트 대부분의 호출 라우팅은 통신사가 관리합니다.  통화 권한 부여 및 통화 라우팅을 위해 번호 변환을 위해 사용자 다이얼 계획을 구성합니다. 자세한 내용은 전화 [요금제란?](what-are-dial-plans.md)을 참조하세요.


### <a name="location-based-routing-for-direct-routing"></a>Location-Based 라우팅에 대한 Location-Based 라우팅

일부 국가 및 지역에서는 PSTN 통신업체를 우회하여 장거리 통화 비용을 절감하는 것이 불법입니다. Location-Based LBR(직접 라우팅)을 사용하면 해당 지리적 위치에 따라 사용자에 대한 Teams 우회를 제한할 수 있습니다. LBR을 계획하고 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [직접 라우팅으로 전달되는 위치 기반 라우팅 계획](location-based-routing-plan.md)
- [위치 기반 라우팅의 네트워크 설정 구성](location-based-routing-configure-network-settings.md)
- [직접 라우팅에 위치 기반 라우팅 사용](location-based-routing-enable.md)
- [Contoso 사례 연구: Location-Based 라우팅](voice-case-study-location-based-routing.md)<br>
  소설 다국적 기업인 Contoso가 조직에 대한 라우팅을 Location-Based 방법을 설명합니다.


### <a name="emergency-calling"></a>비상 전화

긴급 호출을 구성하는 방법은 PSTN 연결 옵션에 따라 다릅니다.

- 통화 요금제의 경우 각 사용자가 긴급 통화를 위해 자동으로 사용하도록 설정되며, 지정된 전화 번호와 연결된 등록된 긴급 주소가 필요합니다. 동적 긴급 호출(클라이언트의 위치에 Teams)이 지원됩니다.  

- 직접 라우팅 Teams의 경우 긴급 통화 라우팅 정책(TeamsEmergencyCallRoutingPolicy)을 사용하여 긴급 번호 및 관련 라우팅 대상을 정의하여 사용자에 대한 긴급 호출 정책을 정의해야 합니다. 등록된 긴급 위치는 직접 라우팅 사용자에 대해 지원되지 않습니다. 동적 긴급 호출의 경우 긴급 통화 라우팅 및 파트너 연결에 대한 추가 구성이 필요합니다.

- 연산자 커넥트 경우 각 사용자가 긴급 통화를 위해 자동으로 사용하도록 설정되며, 등록된 긴급 주소가 할당된 전화 번호와 연결된 데 필요하지만 통신사 파트너에서만 설정할 수 있습니다. 동적 긴급 호출(클라이언트의 위치에 Teams)이 지원됩니다.

긴급 호출 개념 및 용어에 대한 자세한 내용 및 긴급 호출 및 동적 긴급 호출을 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [동적인 긴급 전화 계획 및 구성](configure-dynamic-emergency-calling.md)
- [긴급 전화 정책 관리](manage-emergency-calling-policies.md)
- [직접 라우팅에 대한 긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)
- [Contoso 사례 연구: 긴급 통화](voice-case-study-emergency-calling.md)<br>
  소설적 다국적 기업 Contoso가 조직에 대한 긴급 호출을 구현하는 방법을 설명합니다.


### <a name="network-topology-for-voice-features"></a>음성 기능에 대한 네트워크 토폴로지

동적 긴급 통화를 배포하거나 직접 라우팅에 대한 Location-Based 라우팅을 배포하는 경우 이러한 기능을 사용할 네트워크 설정을 구성해야 Microsoft Teams. 네트워크 지역, 네트워크 사이트, 네트워크 서브넷 및 신뢰할 수 있는 IP 주소에 대한 네트워크 설정을 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [클라우드의 클라우드 음성 기능에 대한 네트워크 Microsoft Teams - 개념 및 용어](cloud-voice-network-settings.md)
- [클라우드 음성 기능에 대한 네트워크 토폴로지 관리 Microsoft Teams](manage-your-network-topology.md)



