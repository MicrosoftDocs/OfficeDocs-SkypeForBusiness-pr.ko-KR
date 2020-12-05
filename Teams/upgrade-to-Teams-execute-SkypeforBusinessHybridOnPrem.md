---
title: 비즈니스용 Skype-프레미스를 Microsoft Teams로 업그레이드
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype-프레미스 배포에서 Microsoft Teams로 조직을 업그레이드하는 방법을 배워야 합니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 961ac4f9bcce3c24d62ec1c744d2c9cd15e2ee1b
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578171"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>비즈니스용 Skype-프레미스에서 Teams로 업그레이드

![배포 및 구현을 강조하는 업그레이드 여정 다이어그램](media/upgrade-banner-deployment.png "배포 및 구현 단계에 강조를 두는 업그레이드 단계")

이 문서는 업그레이드 여정의 배포 및 구현 단계의 일부입니다. 계속하기 전에 다음 활동을 완료해야 합니다.

-   [프로젝트 관련자에 참여](upgrade-enlist-stakeholders.md)
-   [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)
-   [비즈니스용 Skype 및 Teams의 공존 및 상호 연동성 이해](https://aka.ms/SkypeToTeams-Coexist)
-   [업그레이드 여정 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [환경 준비](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [조직 준비](https://aka.ms/SkypeToTeams-UserReadiness)
-   [파일럿 수행](https://aka.ms/SkypeToTeams-Pilot)

비즈니스용 Skype Server 또는 Microsoft Lync 온-프레미스를 배포하고 조직에서 Teams로 업그레이드하려는 경우 이 문서의 지침을 따르하세요. 단계적으로 사용자를 Teams로 이동하는 경우 Microsoft 365 또는 Office 365 조직과 하이브리드 연결을 설정하고 공존 요구 사항을 결정해야 합니다. 

> [!IMPORTANT]
> 비즈니스용 Skype Online은 2021년 7월 31일에 서비스가 종료되며 이후에는 더 이상 액세스할 수 없게 되거나 지원되지 않습니다. 혜택 구현을 극대화하고 조직이 업그레이드를 구현할 수 있는 적절한 시간을 확보하려면 지금 Microsoft Teams로의 여정을 시작하는 것이 권장됩니다. 성공적인 업그레이드는 기술 및 사용자 준비를 맞추기 때문에 Microsoft Teams로의 여정을 탐색할 때 여기에 설명된 지침을 활용해야 합니다.

## <a name="step-1-configure-hybrid-connectivity"></a>1단계: 하이브리드 연결 구성 

온라인 프레미스 사용자를 Teams로 업그레이드하기 위한 주요 구성 구성은 비즈니스용 Skype 서버의 온라인 배포에 대한 하이브리드 연결을 구성하는 것입니다. 

하이브리드 연결 [계획부터 시작한](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) 다음 하이브리드 연결 구성에 설명된 [작업을 수행합니다.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>2단계: 전환 공존 모드 설정(선택 사항)

비즈니스용 Skype와 Teams 클라이언트와 사용자 간의 공존 및 상호 운영성은 Teams 업그레이드 모드로 정의됩니다.  기본적으로 조직은 사용자가 Teams 및 비즈니스용 Skype 클라이언트를 나란히 사용할 수 있도록 하는 제도 모드입니다.

Teams로 전환하는 조직의 경우 TeamsOnly 모드는 각 사용자의 최종 대상입니다. 하지만 모든 사용자에게 TeamsOnly(또는 다른 모드)를 동시에 할당해야 하는 것은 아닙니다.

사용자가 TeamsOnly 모드에 도달하기 전에 조직은 선택적으로 비즈니스용 Skype 공존 모드를 사용하여 TeamsOnly 모드에 있는 사용자와 아직 그렇지 않은 사용자 간에 예측 가능한 통신을 보장할 수 있습니다.  비즈니스용 Skype 공존 모드(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)의 목적은 조직이 비즈니스용 Skype에서 Teams로 전환할 때 최종 사용자에게 간단하고 예측 가능한 환경을 제공하는 것입니다. 

사용자가 비즈니스용 Skype 모드에 있는 경우 들어오는 모든 채팅 및 통화가 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다. 최종 사용자 혼동을 방지하고 적절한 라우팅을 보장하기 위해 사용자가 비즈니스용 Skype 모드에 있는 경우 Teams 클라이언트의 통화 및 채팅 기능이 비활성화됩니다. 마찬가지로 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있는 경우 Teams의 모임 예정이 명시적으로 비활성화되어 사용자가 SfBWithTeamsCollabAndMeetings 모드에 있는 경우 명시적으로 사용하도록 설정됩니다.

요구 사항에 따라 조직에서 선택한 업그레이드 경로에 따라 적절한 공존 모드를 할당할 수 있습니다. 자세한 내용은 비즈니스용 Skype와 함께 [Teams를](migration-interop-guidance-for-teams-with-skype.md) 사용하는 조직에 대한 마이그레이션 및 상호 운영성 지침 및 공존 및 업그레이드 설정을 [참조하세요.](https://aka.ms/SkypeToTeams-SetCoexistence)


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>3단계: 비즈니스용 Skype의 사용자를 비즈니스용 Skype-프레미스에서 Teams로만 이동

궁극적으로 사용자를 TeamsOnly 모드로 이동해야 합니다. 여기에는 한 두 단계가 수행될 수 있습니다.  

자세한 내용은 [사용자를](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) 프레미스와 클라우드 간에 이동하고 사용자를 프레미스에서 [Teams로 이동을 참조하세요.](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>4단계: 하이브리드를 사용하지 않도록 설정하여 클라우드로 마이그레이션 완료

모든 사용자를 프레미스에서 클라우드로 이동한 후, 비즈니스용 Skype 배포를 해제할 수 있습니다. 자세한 내용은 클라우드로 마이그레이션을 완료하기 위해 하이브리드 사용 안 [을 참조하세요.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)


## <a name="phone-system-and-pstn-connectivity-options"></a>전화 시스템 및 PSTN 연결 옵션

Teams가 있는 전화 시스템은 사용자가 TeamsOnly 모드에 있는 후에 지원됩니다. 사용자가 제도 모드인 경우 전화 시스템은 비즈니스용 Skype에서만 지원됩니다. 

### <a name="pstn-connectivity-options"></a>PSTN 연결 옵션

PSTN(Public Switched Telephone Network) 연결 옵션을 고려할 때 비즈니스용 Skype에서 프레미스 비즈니스용 Skype에서 TeamsOnly 모드로 전환하는 경우 다음과 같은 두 가지 시나리오가 있습니다.

- 온라인으로 이동하고 Microsoft 통화 요금제로 Enterprise Voice 비즈니스용 Skype의 사용자입니다. 이 사용자를 Teams로 마이그레이션하려면 사용자의 비즈니스용 Skype 계정을 클라우드로 이동하고 A) 사용자의 전화 번호 포트를 Microsoft 통화 요금제로 이동하거나 B) 사용 가능한 지역에서 새 구독자 번호를 할당하도록 조정해야 합니다.  자세한 내용은 비즈니스용 Skype Server와 함께 Enterprise Voice Microsoft 통화 플랜을 [참조하세요.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)

- 온라인으로 이동하고 Enterprise Voice PSTN 연결을 유지할 수 있는 비즈니스용 Skype의 Enterprise Voice 사용자입니다. 이 사용자를 Teams로 마이그레이션하려면 사용자의 비즈니스용 Skype 계정을 클라우드로 이동하고 사용자의 마이그레이션과 직접 라우팅을 조정해야 합니다. 자세한 내용은 비즈니스용 Skype Server와 함께 Enterprise Voice [라우팅을 참조하세요.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)
