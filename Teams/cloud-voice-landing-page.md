---
title: Microsoft Teams에서 음성 솔루션 계획
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/29/2020
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
description: Microsoft Teams 클라우드 음성 기능 및 조직에 대해 수행할 배포 결정에 대해 자세히 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba61d1ccbaeda26834b31a321aebfccbe23243
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999353"
---
# <a name="plan-your-teams-voice-solution"></a>Teams 음성 솔루션 계획

이 문서는 조직에 적합한 Microsoft 음성 솔루션을 결정하는 데 도움이 됩니다. 결정한 후 이 문서에서는 선택한 솔루션을 구현할 수 있는 콘텐츠에 대한 로드맵을 제공합니다.

통화 플랜을 사용하는 가장 간단한 솔루션&mdash;전화 시스템을 원할 수 있습니다. 이 옵션은 다음 다이어그램과 같이 PBX(Private Branch Exchange) 기능 및 PSTN(공중 전화망) 호출을 제공하는 Microsoft의 클라우드 내 솔루션입니다. 이 솔루션을 통해 Microsoft는 PSTN 운송업체입니다.

![다이어그램 1은 통화 플랜이 있는 전화 시스템을 보여줍니다.](media/voice-solutions-simple.png)

다음에 '예'라고 대답하면 통화 플랜이 있는 전화 시스템이 적합한 솔루션입니다.

- 통화 플랜은 해당 지역에서 사용할 수 있습니다.
- 현재 PSTN 이동 통신 사업자를 유지할 필요가 없습니다.
- PSTN에 대한 Microsoft 관리형 액세스를 사용하려고 합니다.

그러나 상황이 더 복잡할 수 있습니다. 예를 들어 통화 플랜을 사용할 수 없는 위치에 사무실이 있을 수 있습니다. 또는 지리적 위치에 대한 요구 사항이 서로 다른 복잡한 다중 국가 배포를 지원하는 조합 솔루션이 필요할 수 있습니다. Microsoft는 다음과 같은 솔루션 조합을 지원합니다.

- 통화 플랜이 있는 전화 시스템
- Operator Connect를 사용하여 사용자 고유의 PSTN 이동 통신 사업자가 있는 전화 시스템
- 운영자 연결 모바일 있는 자체 PSTN 이동 통신 사업자가 있는 전화 시스템(공개 미리 보기 릴리스)
- 직접 라우팅을 사용하여 자체 PSTN 이동 통신 사업자가 있는 전화 시스템
- 통화 플랜이 있는 전화 시스템, 운영자 연결이 있는 전화 시스템 및/또는 직접 라우팅을 사용하는 전화 시스템을 사용하는 조합 솔루션

모든 음성 솔루션 옵션에 대한 시각적 요약은 음성 솔루션 포스터를 참조하세요.

[![Microsoft Voice Solutions 포스터.](media/microsoft-voice-solutions-thumb.png)](https://download.microsoft.com/download/4/3/5/435cd4e9-ca56-4fd1-acb6-d1fda7952320/microsoft-voice-solutions.pdf) <br> [PDF](https://download.microsoft.com/download/4/3/5/435cd4e9-ca56-4fd1-acb6-d1fda7952320/microsoft-voice-solutions.pdf) <br>[Visio](https://download.microsoft.com/download/7/5/c/75c13012-e20c-48bd-a6dd-ea49d1a3420d/microsoft-voice-solutions.vsdx) 
<br>

>[!NOTE]
>중소기업(300명 이하)인 경우 Microsoft는 이제 전화 시스템을 국내 통화 플랜과 번들로 묶습니다. 자세한 내용은 음성 솔루션을 계획, 설정 및 관리하는 데 도움이 되는 [중소기업의 전화 시스템 지침을](/microsoftteams/business-voice/whats-business-voice) 참조하세요.

## <a name="what-do-you-need-to-read"></a>무엇을 읽어야 합니까?

**모두에 필요합니다.** 이 문서의 일부 섹션은 모든 조직과 관련이 있습니다. 예를 들어 모든 사용자가 전화 시스템에 대해 읽고 PSTN(공중 전화망)에 연결하는 옵션을 이해해야 합니다.


| 모두에 필요 | 설명 |
| :------------|:-------|
| [**전화 시스템**](#phone-system) | Microsoft Teams를 사용하여 Microsoft 365 클라우드에서 통화 제어 및 PBX(Private Branch Exchange) 기능을 사용하도록 설정하는 Microsoft의 기술입니다. |
| [**PSTN(공중 전화망) 연결 옵션**](#public-switched-telephone-network-connectivity-options) | 전화 통신 사업자로 Microsoft를 선택하거나 운영자 연결 또는 직접 라우팅을 사용하여 Microsoft Teams에 자체 전화 통신 사업자를 연결합니다. 전화 시스템과 결합된 PSTN 연결 옵션을 사용하면 사용자가 전 세계에서 전화를 걸 수 있습니다.|

**요구 사항에 따라 다릅니다.** 이 문서 및 관련 문서의 일부 섹션은 기존 배포 및 요구 사항에 따라 관련이 있습니다. 예를 들어 Location-Based 라우팅은 통행료 우회를 허용하지 않는 지리적 위치의 직접 라우팅 고객에게만 필요합니다.

다음 구성 중 필요한 구성을 고려합니다.

![다이어그램 2는 Microsoft의 전화 번호, 전화 걸기 플랜, 통화 라우팅 등과 같은 다른 음성 구성 요소를 보여 줍니다.](media/voice-consider-additional-components.png)

| 요구 사항에 따라 | 설명 |
| :------------|:-------|
| [**전화 번호 관리**](pstn-connectivity.md#phone-number-management) | 전화 번호를 얻고 관리하는 방법은 PSTN 연결 옵션에 따라 다릅니다. 전화 번호를 받고, 기존 번호를 전송하고, 서비스 번호를 가져오는 등의 작업을 수행해야 하는 경우 이 섹션을 읽어 보세요. |
| [**통화 라우팅 및 전화 걸기 플랜**](pstn-connectivity.md#call-routing-and-dial-plans) | 전화 권한 부여 및 통화 라우팅을 위해 전화 걸기 전화 번호를 대체 형식(일반적으로 E.164 형식)으로 변환하는 다이얼 플랜을 구성하고 관리하는 방법입니다. 다이얼 플랜이 무엇인지, 조직의 다이얼 플랜을 지정해야 하는지 여부를 이해해야 하는 경우 이 섹션을 읽어 보세요.|
| [**긴급 통화**](pstn-connectivity.md#emergency-calling) | 긴급 통화를 관리하고 구성하는 방법은 PSTN 연결 옵션에 따라 다릅니다. 조직에 대한 긴급 통화를 관리하는 방법을 이해해야 하는 경우 이 섹션을 읽어 보세요. |
| [**직접 라우팅을 위한 위치 기반 라우팅**](pstn-connectivity.md#location-based-routing-for-direct-routing) |LBR(Location-Based 라우팅)을 사용하여 지리적 위치에 따라 Microsoft Teams 사용자의 통행료 우회를 제한하는 방법입니다. 조직에서 통행료 우회를 허용하지 않는 위치에서 직접 라우팅을 사용하는 경우 이 섹션을 읽어 보세요.
| [**클라우드 음성 기능에 대한 네트워크 토폴로지**](pstn-connectivity.md#network-topology-for-voice-features) | 조직에서 직접 라우팅 또는 동적 긴급 통화에 LBR(Location-Based 라우팅)을 배포하는 경우 Microsoft Teams에서 이러한 기능에 대한 네트워크 설정을 구성해야 합니다. 직접 라우팅을 위해 LBR을 구현하거나 통화 플랜 또는 직접 라우팅을 사용하여 동적 긴급 통화를 구현하는 경우 이 섹션을 읽어보십시오. |
| [**기존 음성 솔루션 마이그레이션**](#migrate-your-existing-voice-solution-to-teams) | 음성 솔루션을 Teams로 마이그레이션할 때 고려해야 할 사항  기존 음성 솔루션에서 Teams로 마이그레이션하는 경우 이 섹션을 참조하세요. 

> [!Important]
> 이 문서에서는 Microsoft Teams의 음성 솔루션에 중점을 둡니다. 2021년 7월 31일에 비즈니스용 Skype Online이 사용 중지되어 비즈니스용 Skype 서버 또는 Cloud Connector Edition&mdash;과 비즈니스용 Skype Online을 통한 온-프레미스 환경&mdash;간의 PSTN 연결은 더 이상 지원되지 않습니다. 이 문서에서는 Teams 음성 솔루션과 필요한 경우 운영자 연결 또는 직접 라우팅을 사용하여 온-프레미스 전화 통신 네트워크를 Teams에 연결하는 방법을 소개합니다.


## <a name="phone-system"></a>전화 시스템

전화 시스템은 Microsoft Teams를 사용하여 Microsoft 365 클라우드에서 통화 제어 및 PBX(Private Branch Exchange) 기능을 사용하도록 설정하는 Microsoft의 기술입니다.

전화 시스템은 Teams 클라이언트 및 인증된 디바이스에서 작동합니다. 전화 시스템을 사용하면 기존 PBX 시스템을 Microsoft 365에서 직접 제공되는 기능 집합으로 바꿀 수 있습니다. 

지리적 영역에 관계없이 조직의 사용자 간 통화는 전화 시스템 내에서 내부적으로 처리됩니다. 이러한 내부 통화는 PSTN(공중 전화망)으로 이동하지 않으므로 회사에서 장거리 요금을 방지합니다.

이 문서에서는 다음과 같은 전화 시스템 주요 기능과 고려해야 할 배포 결정을 소개합니다.

- [자동 전화 교환 및 통화 큐](#auto-attendants-and-call-queues)
- [클라우드 음성 메일](#cloud-voicemail)
- [ID 호출](#calling-identity)

![다이어그램 3에서는 전화 시스템에 자동 전화 교환 및 통화 쿼리, 클라우드 음성 메일 및 통화 ID가 포함되어 있습니다.](media/phone-system-contains.png)

모든 전화 시스템 기능 및 전화 시스템을 설정하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [다음은 통화 시스템 기능입니다.](here-s-what-you-get-with-phone-system.md)
- [조직에서 전화 시스템 설정](setting-up-your-phone-system.md)<br>
  전화 시스템 라이선스를 구입 및 할당하고, 전화 번호를 관리하고, 무료 번호에 대한 통신 크레딧을 설정하는 방법을 설명합니다. 

지원되는 디바이스 관리에 대한 자세한 내용은 Microsoft Teams 및 [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)[에서 디바이스 관리를 참조하세요](devices/device-management.md).


### <a name="auto-attendants-and-call-queues"></a>자동 전화 교환 및 통화 큐

자동 전화 교환을 사용하면 호출자 입력에 따라 통화를 라우팅하는 메뉴 옵션을 설정할 수 있습니다. 통화 큐는 발신자를 위한 대기 영역입니다. 자동 전화 교환 및 통화 큐를 함께 사용하면 발신자를 조직의 적절한 담당자 또는 부서로 쉽게 라우팅할 수 있습니다.

자동 전화 교환 및 통화 큐에 대한 자세한 내용은 다음 문서를 참조하세요.

- [Teams 자동 전화 교환 및 통화 큐 계획](plan-auto-attendant-call-queue.md)
- [자동 전화 교환 설정](create-a-phone-system-auto-attendant.md)
- [통화 큐 만들기](create-a-phone-system-call-queue.md) 
- [Contoso 사례 연구: 자동 전화 교환 및 통화 큐](voice-case-study-call-queues.md)<br>
  가상의 다국적 기업인 Contoso가 음성 솔루션에 대한 자동 전화 교환 및 통화 큐를 구현하는 방법을 설명합니다.

### <a name="cloud-voicemail"></a>클라우드 음성 메일

Azure Voicemail 서비스에서 제공하는 클라우드 음성 사서함 Exchange 사서함에 대한 음성 메일 예금만 지원합니다. 타사 전자 메일 시스템을 지원하지 않습니다. 

클라우드 음성 사서함에는 기본적으로 조직의 모든 사용자가 사용할 수 있는 음성 메일 기록이 포함됩니다. 비즈니스 요구 사항에 따라 조직 전체의 특정 사용자 또는 모든 사용자에 대해 음성 메일 기록을 사용하지 않도록 설정해야 할 수 있습니다.

클라우드 음성 사서함 Teams 사용자를 위해 자동으로 설정 및 프로비전됩니다.  

클라우드 음성 사서함 및 해당 구성에 대한 자세한 내용은 다음 문서를 참조하세요.

- [클라우드 음성 사서함 설정](set-up-phone-system-voicemail.md)
- [조직에서 음성 메일 정책 설정](manage-voicemail-policies.md)


### <a name="calling-identity"></a>ID 호출

기본적으로 모든 아웃바운드 통화는 할당된 전화 번호를 호출 ID(발신자 ID)로 사용합니다. 전화 수신자는 발신자를 빠르게 확인하고 통화를 수락할지 거부할지를 결정할 수 있습니다. 호출자 ID를 구성하거나 호출자 ID를 변경하거나 차단하는 방법에 대한 자세한 내용은 [사용자의 호출자 ID 설정을 참조하세요](set-the-caller-id-for-a-user.md). 

## <a name="public-switched-telephone-network-connectivity-options"></a>공중 전화 네트워크 연결 옵션

전화 시스템은 조직에 완전한 PBX 기능을 제공합니다. 그러나 사용자가 조직 외부에서 전화를 걸 수 있도록 하려면 전화 시스템을 PSTN(공중 전화망)에 연결해야 합니다. 전화 시스템을 PSTN에 연결하려면 다음 옵션 중 하나를 선택할 수 있습니다.

- [**통화 플랜이 있는 전화 시스템**](pstn-connectivity.md#phone-system-with-calling-plan). Microsoft를 PSTN 이동 통신 사업자로 사용하는 클라우드 전체 솔루션입니다.

- [**Operator Connect를 사용하여 사용자 고유의 PSTN 이동 통신 사업자가 있는 전화 시스템**](operator-connect-plan.md)입니다. Operator Connect를 사용하면 기존 운영자가 Microsoft Operator Connect 프로그램에 참여하는 경우 PSTN 통화를 Teams로 가져오기 위한 서비스를 관리할 수 있습니다. 

- **운영자 연결 모바일 공개 검토 릴리스**[**를 사용하여 자신의 PSTN 이동 통신 사업자와 전화 시스템**](operator-connect-mobile-plan.md). 운영자 연결 모바일 사용하면 기존 운영자가 Microsoft 운영자 연결 모바일 프로그램에 참여하는 경우 Teams에서 SIM 지원 휴대폰 번호를 사용하기 위한 서비스를 관리할 수 있습니다. 

- 직접 라우팅을 사용하여 온-프레미스 환경을 Teams [**에 연결하여 자체 PSTN 이동 통신 사업자가 있는 전화 시스템**](pstn-connectivity.md#phone-system-with-direct-routing)입니다.


복잡한 환경에 대한 솔루션을 설계하거나 다단계 마이그레이션을 관리할 수 있는 옵션 조합을 선택할 수 있습니다. 나중에 마이그레이션에 대해 자세히 알아봅니다.

대부분의 전화 시스템 기능은 선택한 PSTN 연결 옵션에 관계없이 동일합니다. 그러나 통화 라우팅 및 긴급 통화와 같은 특정 전화 시스템 기능을 구성하는 방법에는 몇 가지 차이점이 있습니다. PSTN 연결 옵션 및 구성 고려 사항에 대한 자세한 내용은 [PSTN 연결 옵션을 참조하세요](pstn-connectivity.md).


## <a name="migrate-your-existing-voice-solution-to-teams"></a>기존 음성 솔루션을 Teams로 마이그레이션

> [!NOTE]
> 비즈니스용 Skype 서버 Teams로 업그레이드하는 전체 계획의 일부로 Teams 음성 솔루션을 계획하는 방법에 대한 지침은 비즈니스용 Skype [온-프레미스에서 Teams로 업그레이드하기 위한 PSTN 고려 사항을 참조하세요](upgrade-to-teams-on-prem-pstn-considerations.md).

Teams로 업그레이드하는 조직의 경우 최종 목표는 모든 사용자를 TeamsOnly 모드로 이동하는 것입니다. 전화 시스템 사용은 사용자가 TeamsOnly 모드에 있는 경우에만 지원됩니다. Teams로 업그레이드하는 방법에 대한 기본 정보가 필요한 경우 다음을 시작합니다.

- [Microsoft Teams 업그레이드 시작하기](upgrade-start-here.md)
- [업그레이드 프레임워크 정보](upgrade-framework.md)
- [IT 관리자를 위한 업그레이드 전략](upgrade-to-teams-on-prem-implement.md)

음성 솔루션을 마이그레이션할 때 TeamsOnly 모드로 전환할 때 다음과 같은 4가지 호출 시나리오가 있습니다.

- [**Microsoft 통화 플랜을 사용하는 비즈니스용 Skype Online의 사용자**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)입니다. 업그레이드 시 이 사용자는 계속해서 Microsoft 통화 플랜을 갖게 됩니다.

- **비즈니스용 Skype 온-프레미스 또는 Cloud Connector Edition [을 통해 온-프레미스 음성 기능을](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) 사용하는 비즈니스용 Skype Online의 사용자** 입니다. Teams에 대한 사용자의 업그레이드는 TeamsOnly 사용자에게 PSTN 기능이 있는지 확인하기 위해 사용자를 직접 라우팅으로 마이그레이션하는 작업과 조정되어야 합니다.

- **[Enterprise Voice 온-프레미스에 비즈니스용 Skype 사용자는](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing) 온라인으로 이동하고 온-프레미스 PSTN 연결을 유지합니다**. 이 사용자를 Teams로 마이그레이션하려면 사용자의 온-프레미스 비즈니스용 Skype 계정을 클라우드로 이동하고 사용자를 직접 라우팅으로 마이그레이션하는 작업을 조정해야 합니다. 

- **[Enterprise Voice 온-프레미스를 비즈니스용 Skype 사용자는](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan) 온라인으로 전환하고 Microsoft 통화 플랜을 사용합니다**.  이 사용자를 Teams로 마이그레이션하려면 사용자의 온-프레미스 비즈니스용 Skype 계정을 클라우드로 이동하고 A) 해당 사용자의 전화 번호 포트를 Microsoft 통화 플랜 또는 B로 이동하도록 조정해야 합니다. 사용 가능한 지역에서 새 구독자 번호를 할당합니다.

이러한 각 시나리오에 대해 음성 마이그레이션을 구현하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- [IT 관리자를 위해 Teams로 업그레이드할 때 PSTN 고려 사항](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Contoso 음성 마이그레이션 사례 연구](voice-case-study-overview.md)<br>
  사례 연구는 가상의 다국적 기업인 Contoso가 조직을 위해 Teams 음성 솔루션을 구현한 방법을 설명합니다. 여기에는 다음 문서가 포함되어 있습니다.

  - [Teams 업그레이드 계획](voice-case-study-migration-plan.md)
  - [전화 시스템 및 PSTN 연결 옵션](voice-case-study-phone-system.md)
  - [위치 기반 라우팅 구현](voice-case-study-location-based-routing.md)
  - [긴급 통화](voice-case-study-emergency-calling.md)
  - [자동 전화 교환 및 통화 큐](voice-case-study-call-queues.md)
  - [오디오 회의](voice-case-study-audio-conferencing.md)
