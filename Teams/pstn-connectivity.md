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
- highpri
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Teams 통화(PSTN 연결) 옵션 및 조직에 대해 내릴 결정에 대해 자세히 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 974418a6a1cf963b66b1f0a8667c5ed75b73f72b
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551702"
---
# <a name="pstn-connectivity-options"></a>PSTN 연결 옵션

Microsoft는 전화 시스템을 통해 조직에 완전한 PBX(Private Branch Exchange) 기능을 제공합니다. 그러나 사용자가 조직 외부에서 전화를 걸 수 있도록 하려면 전화 시스템을 PSTN(공중 전화망)에 연결해야 합니다.

이 문서에서는 PSTN 연결 옵션에 중점을 둡니다. 전화 시스템 기능에 대한 세부 정보를 포함하여 Microsoft 음성 솔루션에 대한 자세한 내용은 [Teams 음성 솔루션 계획을 참조하세요](cloud-voice-landing-page.md).

전화 시스템을 PSTN에 연결하려면 다음 옵션 중에서 선택할 수 있습니다.

- [**통화 플랜**](#phone-system-with-calling-plan). Microsoft를 PSTN 이동 통신 사업자로 사용하는 클라우드 전체 솔루션입니다.

- [**연산자 연결**](#phone-system-with-operator-connect)입니다. Operator Connect를 사용하면 기존 통신 사업자가 Microsoft Operator Connect 프로그램에 참여하는 경우 PSTN 통화 및 SCC(세션 테두리 컨트롤러)를 관리할 수 있습니다.

- [**Teams Phone Mobile**](#phone-system-with-teams-phone-mobile). Microsoft Teams 전화 Mobile에서는 사용자의 SIM 사용 전화 번호도 Teams 전화 번호입니다. 기존 이동 통신 사업자가 Microsoft Teams 전화 Mobile 프로그램에 참여하는 경우 PSTN 통화를 Teams로 가져오기 위한 서비스를 관리할 수 있습니다.  

- [**직접 라우팅**](#phone-system-with-direct-routing)- SBC(Session Border Controller)를 전화 시스템에 연결하여 자체 PSTN 이동 통신 사업자를 사용할 수 있습니다.

복잡한 환경에 대한 솔루션을 설계하거나 다단계 마이그레이션을 관리할 수 있는 옵션 조합을 선택할 수도 있습니다.

선택한 옵션 또는 옵션은 일부 전화 시스템 기능을 구성하는 방법에 영향을  미칩니다. 자세한 내용은 이 문서의 뒷 [부분에 있는 구성 고려 사항을](#configuration-considerations) 참조하세요.

## <a name="phone-system-with-calling-plan"></a>통화 플랜이 있는 전화 시스템

통화 플랜이 있는 전화 시스템은 Teams 사용자를 위한 Microsoft의 클라우드 내 음성 솔루션입니다. 이 솔루션은 전화 시스템을 PSTN에 연결하는 가장 간단한 옵션입니다. 이 옵션을 사용하면 다음 다이어그램과 같이 Microsoft가 PSTN 이동 통신 사업자 역할을 합니다.

![다이어그램 1은 통화 플랜이 있는 전화 시스템을 보여줍니다.](media/voice-solutions-simple.png)

다음에 '예'라고 대답하면 통화 플랜이 있는 전화 시스템이 적합한 솔루션입니다.

- 통화 플랜은 해당 지역에서 사용할 수 있습니다.
- 현재 PSTN 이동 통신 사업자를 유지할 필요가 없습니다.
- PSTN에 대한 Microsoft 관리형 액세스를 사용하려고 합니다.

이 옵션을 사용하여 다음을 수행합니다.

- 사용이 허가되는 서비스 수준에 따라 전 세계 휴대폰으로 전화를 걸 수 있는 국내 또는 국제 통화 플랜이 추가된 전화 시스템을 사용할 수 있습니다.

- 통화 플랜은 Microsoft 365에서 작동하므로 온-프레미스 배포의 배포&mdash;또는 유지 관리가 필요하지 않습니다.

- 참고: 타사 PBX, 아날로그 디바이스 및 SBC에서 지원하는 기타 전화 통신 장비와의 상호 운용성을 위해 직접 라우팅을 통해 지원되는 SBC(세션 테두리 컨트롤러)를 연결할 수 있습니다.

이 옵션을 사용하려면 Microsoft 365에 대한 중단 없는 연결이 필요합니다.

통화 플랜에 대한 자세한 내용은 다음 문서를 참조하세요.

- [사용자에게 적합한 통화 플랜은 무엇인가요?](calling-plan-landing-page.md)
- [통화 플랜을 구입하는 방법](calling-plans-for-office-365.md)
- [통화 플랜의 국가 및 지역 가용성](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [통화 플랜 설정](set-up-calling-plans.md)

## <a name="phone-system-with-operator-connect"></a>운영자 연결이 있는 전화 시스템

Operator Connect를 사용하면 기존 이동 통신 사업자가 Microsoft Operator Connect 프로그램에 참여하는 경우 PSTN 통화를 Teams로 가져오기 위한 서비스를 관리할 수 있습니다. 이동 통신 사업자는 PSTN 통화 서비스 및 SCC(세션 테두리 컨트롤러)를 관리하여 하드웨어 구매 및 관리를 저장할 수 있습니다.

다음과 같은 경우 운영자 연결이 조직에 적합한 솔루션일 수 있습니다.

- 지리적 위치에서는 Microsoft 통화 플랜을 사용할 수 없습니다.
- 선호하는 이동 통신 사업자는 Microsoft Operator Connect 프로그램에 참여합니다.
- Teams에서 통화를 사용할 수 있는 새 이동 통신 사업자를 찾으려고 합니다.

Operator Connect의 이점 및 요구 사항 및 이 프로그램에 참여하는 통신 사업자 목록에 대한 자세한 내용은 [플랜 운영자 연결을](operator-connect-plan.md) 참조하세요. Operator Connect를 구성하는 방법에 대한 자세한 내용은 [Operator Connect 구성](operator-connect-configure.md)을 참조하세요.

## <a name="phone-system-with-teams-phone-mobile"></a>Teams Phone Mobile을 사용한 전화 시스템

기존 이동 통신 사업자가 Microsoft Teams 전화 Mobile 프로그램에 참여하는 경우 PSTN 통화를 Teams로 가져오기 위한 서비스를 관리할 수 있습니다. Teams Phone Mobile을 사용하면 사용자의 SIM 사용 전화 번호도 Teams 전화 번호입니다.  사용자는 모바일 서비스와 책상 줄 모두에서 Microsoft Teams에서 단일 전화 번호를 사용할 수 있습니다.  

서비스의 조합을 고려할 수 있습니다. 예를 들어 모바일 지원이 필요한 영업 및 현장 조직에 Teams Phone Mobile을 선택할 수 있지만, 책상 전화를 사용하는 현장 콜 센터 조직에 대한 또 다른 솔루션입니다. 

다음과 같은 경우 Teams Phone Mobile이 조직에 적합한 솔루션일 수 있습니다.

- Teams Phone에 대해 회사 소유의 기본 SIM 사용 휴대폰 번호를 단일 번호 솔루션으로 사용하려고 합니다.
- 선호하는 운영자는 Microsoft Teams 전화 Mobile 프로그램에 참여합니다.
- Teams에서 통화를 사용하도록 설정하는 새 운영자를 찾으려고 합니다.

Teams Phone Mobile의 이점 및 요구 사항 및 이 프로그램에 참여하는 이동 통신 사업자에 대한 링크에 대한 자세한 내용은 [Teams Phone Mobile 계획을 참조하세요](operator-connect-mobile-plan.md). Teams Phone Mobile을 구성하는 방법에 대한 자세한 내용은 [Teams Phone Mobile 구성을 참조하세요](operator-connect-mobile-configure.md).

## <a name="phone-system-with-direct-routing"></a>직접 라우팅이 있는 전화 시스템

이 옵션은 다음 다이어그램과 같이 직접 라우팅을 사용하여 전화 시스템을 전화 통신 네트워크에 연결합니다. 

![다이어그램 5는 직접 라우팅이 있는 전화 시스템을 보여줍니다.](media/voice-solution-with-direct-routing.png)

다음 질문에 예라고 대답하면 직접 라우팅을 사용하는 전화 시스템이 적합한 솔루션입니다.

- 전화 시스템에서 Teams를 사용하려고 합니다.
- 현재 PSTN 이동 통신 사업자를 유지해야 합니다.
- 통신 사업자를 통해 통화 플랜을 통과하는 일부 통화와 라우팅을 혼합하려고 합니다.
- 타사 PBX 및/또는 오버헤드 호출기, 아날로그 디바이스 등의 장비와 상호 운용해야 합니다.

이 옵션을 사용하여 다음을 수행합니다.

- 추가 온-프레미스 소프트웨어 없이도 지원되는 SBC(세션 테두리 컨트롤러)를 전화 시스템에 연결합니다.

- 전화 시스템에서 거의 모든 전화 통신 통신 사업자를 사용할 수 있습니다.

- 이 옵션을 구성하고 관리할 수 있습니다. 또는 이동 통신 사업자 또는 파트너가 구성하고 관리할 수 있습니다(이동 통신 사업자 또는 파트너가 이 옵션을 제공하는지 물어보세요).

- 타사 PBX, 아날로그 디바이스 및 전화 시스템과 같은 전화 통신 장비&mdash;&mdash;간의 상호 운용성을 구성할 수 있습니다.

이 옵션을 사용하려면 다음이 필요합니다.

- Microsoft 365에 대한 중단 없는 연결

- 지원되는 SBC 배포 및 유지 관리

- 타사 운송업체와의 계약입니다.
  (통화 플랜이 있는 전화 시스템에 있는 사용자를 위해 타사 PBX, 아날로그 디바이스 또는 기타 전화 통신 장비에 대한 연결을 제공하는 옵션으로 배포되지 않는 한)

직접 라우팅에 대한 자세한 내용은 다음 문서를 참조하세요.

- [직접 라우팅 계획](direct-routing-plan.md)
- [직접 라우팅 구성](direct-routing-configure.md)
- [직접 라우팅에 사용할 음성 라우팅 정책 관리](manage-voice-routing-policies.md)
- [직접 라우팅으로 전달되는 위치 기반 라우팅 계획](location-based-routing-plan.md)
- [직접 라우팅으로 인증된 SBC(Session Border Controller) 목록](direct-routing-border-controllers.md)

## <a name="configuration-considerations"></a>구성 고려 사항

대부분의 전화 시스템 기능은 선택한 PSTN 연결 옵션에 관계없이 동일합니다. 예를 들어 응답되지 않은 통화 및 전달 설정, 통화 전송, 대기 중인 사용자 지정 음악, 통화 대기, 공유 회선 및 음성 앱을 모두 사용할 수 있습니다. 전화 시스템 기능의 전체 목록은 [전화 시스템을 사용하여 얻을 수 있는 항목을 참조](here-s-what-you-get-with-phone-system.md)하세요.

그러나 특정 전화 시스템 기능을 구성하는 방법에는 몇 가지 차이점이 있습니다. 예를 들어 직접 라우팅에는 호출 라우팅을 구성하는 추가 단계가 필요합니다. 또 다른 예로 직접 라우팅은 LBR(위치 기반 라우팅)을 제공합니다. LBR을 사용하면 허용되지 않는 특정 지리적 위치에서 통행료 우회를 제한할 수 있습니다. 

다음 표에서는 기본 구성 차이점을 강조 표시합니다. 표 다음에 나오는 섹션에서는 자세한 내용과 세부 정보에 대한 링크를 제공합니다.

| 옵션 | 설명 | 전화 번호 관리 | 통화 라우팅 | 긴급 통화 가용성 |
| :------------| :-------| :-------| :-------| :-------| 
| 통화 플랜 | -Microsoft는 PSTN 이동 통신 사업자 역할을 합니다.<br>- SCC를 구입하거나 관리할 필요가 없습니다.| Microsoft를 통해 가져옵니다.| -Microsoft에서 관리합니다. <br> -관리 번호 변환에 대한 사용자 다이얼 플랜을 구성합니다. | -Microsoft에서 사용하도록 설정 <br> -관리 주소를 등록합니다. <br> -동적 호출이 지원됨 |
| 연산자 연결 | -Carrier는 PSTN 연결 및 SCC를 관리합니다. <br> - SCC를 구입하거나 관리할 필요가 없습니다. | -이동 통신 사업자를 통해 획득. <br> - 운송업체에서 관리하는 긴급 주소와 관련된 숫자입니다. | -운송업체에서 관리합니다. <br>-관리 번호 변환에 대한 사용자 다이얼 플랜을 구성합니다. | - 이동 통신 사업자가 사용하도록 설정합니다. <br> -관리 주소를 등록합니다. <br> -동적 호출이 지원됨 |
| Teams 휴대폰 모바일 | -Carrier는 SIM-Enabled 모바일 번호, PSTN 연결 및 SCC를 관리합니다. <br> - SCC를 구입하거나 관리할 필요가 없습니다. | -이동 통신 사업자를 통해 획득. <br> -운송업체에서 관리하는 긴급 주소와 연결된 숫자입니다. | -운송업체에서 관리합니다. <br> 관리 번호 변환에 대한 사용자 다이얼 플랜을 구성합니다. |- 이동 통신 사업자가 사용하도록 설정합니다. <br> - 관리 주소를 등록합니다. <br> - 동적 호출이 지원됨 <br> - 캐리어는 네이티브 다이얼러 긴급 통화를 지원했습니다. |
| 직접 라우팅 | -타사 공급업체에서 구입한 인증된 SBC가 필요합니다.<br>- 전화 시스템에 SBC를 연결합니다.<br> -기존 PSTN 이동 통신 사업자를 사용합니다. | 이동 통신 사업자를 통해 획득. | - 관리자의 추가 구성이 필요합니다.<br>-관리 번호 변환에 대한 트렁크 다이얼 플랜을 구성합니다. <br>-LBR을 사용하여 통행료 우회를 제한할 수 있습니다. | - 관리자의 추가 구성이 필요합니다. <br>-등록된 주소는 지원되지 않습니다. <br>-동적 호출이 지원되지만 추가 구성이 필요합니다. |


### <a name="phone-number-management"></a>전화 번호 관리

Microsoft에는 두 가지 유형의 전화 번호, 즉 조직의 사용자에게 할당할 수 있는 구독자(사용자) 번호와 유료 및 무료 서비스 번호로 사용할 수 있는 서비스 번호가 있습니다. 서비스 번호는 구독자 번호보다 동시 호출 용량이 높으며 오디오 회의, 자동 전화 교환 또는 통화 큐와 같은 서비스에 할당할 수 있습니다.

다음을 결정해야 합니다.

- Microsoft의 새 전화 번호가 필요한 사용자 위치는 무엇인가요?
- 어떤 유형의 전화 번호(구독자 또는 서비스)가 필요한가요?
- 기존 전화 번호를 Teams로 어떻게 할까요??

전화 번호를 획득하고 관리하는 방법은 PSTN 연결 옵션에 따라 다릅니다.

- 통화 플랜의 전화 번호를 관리하는 방법에 대한 자세한 내용은 통화 [플랜의 전화 번호 관리를 참조하세요](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Operator Connect를 사용하여 전화 번호를 관리하는 방법에 대한 자세한 내용은 [Operator Connect를 사용하여 전화 번호 설정을](operator-connect-configure.md#set-up-phone-numbers) 참조하세요.

- Teams Phone Mobile을 사용하여 전화 번호를 관리하는 방법에 대한 자세한 내용은 [Teams Phone Mobile을 사용하여 전화 번호 설정을 참조하세요](operator-connect-mobile-configure.md#set-up-phone-numbers).

- 직접 라우팅을 위해 전화 번호를 관리하는 방법에 대한 자세한 내용은 [전화 번호 구성 및 엔터프라이즈 음성 사용을](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice) 참조하세요.

### <a name="call-routing-and-dial-plans"></a>통화 라우팅 및 전화 걸기 플랜

통화 라우팅을 구성하는 방법은 PSTN 연결 옵션에 따라 다릅니다.  

- 통화 플랜의 경우 대부분의 통화 라우팅은 Microsoft 통화 계획 인프라에서 처리됩니다. 통화 권한 부여 및 통화 라우팅을 위해 번호 변환을 위해 사용자 다이얼 플랜을 구성합니다. 자세한 내용은 [다이얼 플랜이란?](what-are-dial-plans.md)을 참조하세요.

- 운영자 연결 및 Teams Phone Mobile의 경우 대부분의 통화 라우팅은 통신 사업자가 관리합니다. 통화 권한 부여 및 통화 라우팅을 위해 번호 변환을 위해 사용자 다이얼 플랜을 구성합니다. 자세한 내용은 [다이얼 플랜이란?](what-are-dial-plans.md)을 참조하세요.

- 직접 라우팅의 경우 음성 경로를 지정하고 사용자에게 음성 라우팅 정책을 할당하여 통화 라우팅을 구성해야 합니다. SCC(세션 테두리 컨트롤러)와의 상호 운용성을 보장하기 위해 트렁크 수준에서 번호 변환에 대한 다이얼 플랜을 구성할 수 있습니다. 자세한 내용은 [직접 라우팅에 대한 음성 라우팅 구성](direct-routing-voice-routing.md), [음성 라우팅 정책 관리](manage-voice-routing-policies.md) 및 [전화 번호 번역](direct-routing-translate-numbers.md)을 참조하세요. 

### <a name="location-based-routing-for-direct-routing"></a>직접 라우팅에 대한 Location-Based 라우팅

일부 국가 및 지역에서는 장거리 통화 비용을 줄이기 위해 PSTN 운송업체를 우회하는 것은 불법입니다. 직접 라우팅을 위한 LBR(Location-Based 라우팅)을 사용하면 지리적 위치에 따라 Teams 사용자의 통행료 우회를 제한할 수 있습니다. LBR을 계획하고 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [직접 라우팅으로 전달되는 위치 기반 라우팅 계획](location-based-routing-plan.md)
- [위치 기반 라우팅의 네트워크 설정 구성](location-based-routing-configure-network-settings.md)
- [직접 라우팅에 위치 기반 라우팅 사용](location-based-routing-enable.md)
- [Contoso 사례 연구: Location-Based 라우팅](voice-case-study-location-based-routing.md)<br>
  가상의 다국적 기업인 Contoso가 조직에 Location-Based 라우팅을 구현하는 방법을 설명합니다.

### <a name="emergency-calling"></a>비상 전화

긴급 통화를 구성하는 방법은 PSTN 연결 옵션에 따라 다릅니다.

- 통화 플랜의 경우 각 사용자는 긴급 통화에 대해 자동으로 사용하도록 설정됩니다. 사용자는 할당된 전화 번호와 연결된 등록된 긴급 주소가 있어야 합니다. Teams 클라이언트의 위치에 따라 동적 긴급 통화가 지원됩니다. 자세한 내용은 [통화 플랜에 대한 고려 사항을](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) 참조하세요. 

- 운영자 연결의 경우 각 사용자는 긴급 통화에 대해 자동으로 사용하도록 설정됩니다. 사용자에게 할당된 전화 번호와 연결된 등록된 긴급 주소가 있어야 합니다. Teams 클라이언트의 위치에 따라 동적 긴급 통화가 지원됩니다. 자세한 내용은 [Operator Connect에 대한 고려 사항을](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-operator-connect) 참조하세요. 

- Teams Phone Mobile의 경우 각 사용자는 긴급 통화에 대해 자동으로 사용하도록 설정됩니다. 긴급 통화는 지정된 번호로 Teams Phone Mobile Carrier로 자동으로 라우팅됩니다. Teams 클라이언트의 위치에 따라 동적 긴급 통화가 지원됩니다. 자세한 내용은 [Teams Phone Mobile에 대한 고려 사항을 참조하세요](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-teams-phone-mobile). 

- 직접 라우팅의 경우 Teams 긴급 통화 라우팅 정책(TeamsEmergencyCallRoutingPolicy)을 사용하여 사용자에 대한 긴급 통화 정책을 정의해야 합니다. 정책은 긴급 번호 및 관련 라우팅 대상을 정의합니다. 등록된 응급 위치는 직접 라우팅 사용자에 대해 지원되지 않습니다. 동적 긴급 통화의 경우 긴급 통화를 라우팅하고 파트너 연결을 위해 추가 구성이 필요합니다. 자세한 내용은 [직접 라우팅에 대한 고려 사항을 참조하세요](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).

#### <a name="for-more-information"></a>자세한 내용은

긴급 통화 개념 및 용어 및 긴급 통화 및 동적 긴급 통화를 구성하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [긴급 통화 관리](what-are-emergency-locations-addresses-and-call-routing.md)
- [동적인 긴급 전화 계획 및 구성](configure-dynamic-emergency-calling.md)
- [긴급 전화 정책 관리](manage-emergency-calling-policies.md)
- [직접 라우팅에 대한 긴급 통화 라우팅 정책 관리](manage-emergency-call-routing-policies.md)
- [Contoso 사례 연구: 긴급 통화](voice-case-study-emergency-calling.md)<br>
  가상의 다국적 기업인 Contoso가 조직에 긴급 통화를 구현한 방법을 설명합니다.

### <a name="network-topology-for-voice-features"></a>음성 기능에 대한 네트워크 토폴로지

직접 라우팅을 위해 동적 긴급 통화 또는 Location-Based 라우팅을 배포하는 경우 Microsoft Teams에서 이러한 기능에 대한 네트워크 설정을 구성해야 합니다. 네트워크 지역, 네트워크 사이트, 네트워크 서브넷 및 신뢰할 수 있는 IP 주소에 대한 네트워크 설정을 구성하는 방법을 알아보려면 다음 문서를 참조하세요.

- [Microsoft Teams의 클라우드 음성 기능에 대한 네트워크 설정 - 개념 및 용어](cloud-voice-network-settings.md)
- [Microsoft Teams에서 클라우드 음성 기능에 대한 네트워크 토폴로지 관리](manage-your-network-topology.md)
