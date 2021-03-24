---
title: 비즈니스용 Skype-프레미스를 Microsoft Teams로 업그레이드
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype-프레미스 배포에서 조직을 Microsoft Teams로 업그레이드하는 방법에 대해 설명합니다.
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
ms.openlocfilehash: b35a757ecd70fbf2926e668bef86cb21e51d8b8e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093788"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>비즈니스용 Skype에서 프레미스에서 Teams로 업그레이드

![배포 및 구현을 강조하는 업그레이드 여정 다이어그램](media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점 있는 업그레이드 여정의 단계")

이 문서는 업그레이드 단계의 배포 및 구현 단계의 일부입니다. 계속하기 전에 다음 작업을 완료한지 확인합니다.

-   [프로젝트 관계자 인리스트](upgrade-enlist-stakeholders.md)
-   [프로젝트 범위 정의](./upgrade-define-project-scope.md)
-   [비즈니스용 Skype 및 Teams의 공존성 및 상호 연동성 이해](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [업그레이드 여정을 선택했습니다.](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [환경 준비](./upgrade-prepare-environment.md)
-   [조직 준비](./upgrade-prepare-organization.md)
-   [파일럿 수행](./pilot-essentials.md)

비즈니스용 Skype Server 또는 Microsoft Lync 온-프레미스를 배포하고 조직에서 Teams로 업그레이드하려는 경우 이 문서의 지침을 따르하세요. Microsoft 365 또는 Office 365 조직과 하이브리드 연결을 설정하고 단계적으로 사용자를 Teams로 이동하는 경우 공존 요구 사항을 결정해야 합니다.

시작하기 전에 IT Pros 및 관리자는 이 문서의 1부 의 의 프레미스에서 [비즈니스용 Skype Server를](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) 통해 조직에 대한 중요한 고려 사항을 검토해야 합니다.

> [!IMPORTANT]
> 비즈니스용 Skype Online은 2021년 7월 31일에 서비스가 종료되며 이후에는 더 이상 액세스할 수 없게 되거나 지원되지 않습니다. 혜택 구현을 최대화하고 조직에서 업그레이드를 구현할 적절한 시간을 확보하려면 오늘 Microsoft Teams로의 여정을 시작하는 것이 권장됩니다. 성공적인 업그레이드는 기술 및 사용자 준비를 정렬하기 때문에 Microsoft Teams로의 여정을 탐색할 때 여기에 있는 지침을 활용해야 합니다.

## <a name="step-1-configure-hybrid-connectivity"></a>1단계: 하이브리드 연결 구성 

프레미스 사용자를 Teams로 업그레이드하기 위한 핵심 구성은 비즈니스용 Skype 서버의 온라인 배포에 대한 하이브리드 연결을 구성하는 것입니다. 

먼저 하이브리드 연결 계획 을 [읽고](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json) 하이브리드 연결 구성에 설명된 [작업을 수행합니다.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>2단계: 전환 공존 모드 설정(선택 사항)

비즈니스용 Skype 및 Teams 클라이언트와 사용자 간의 공존 및 상호 운영성은 Teams 업그레이드 모드로 정의됩니다.  기본적으로 조직은 사용자가 Teams 및 Skype for Business 클라이언트를 나란히 사용할 수 있는 제도 모드입니다.

Teams로 이동하는 조직의 경우 TeamsOnly 모드는 각 사용자의 최종 대상입니다. 하지만 모든 사용자가 TeamsOnly(또는 다른 모드)를 동시에 할당해야 하는 것은 아닙니다.

TeamsOnly 모드에 도달하기 전에 조직은 선택적으로 비즈니스용 Skype 공존 모드를 사용하여 TeamsOnly 모드에 있는 사용자와 아직 그렇지 않은 사용자 간에 예측 가능한 통신을 보장할 수 있습니다.  비즈니스용 Skype 공존 모드(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)는 조직이 비즈니스용 Skype에서 Teams로 전환할 때 최종 사용자에게 간단하고 예측 가능한 환경을 제공하기 위한 것입니다. 

사용자가 비즈니스용 Skype 모드에 있는 경우 들어오는 모든 채팅 및 통화가 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다. 최종 사용자 혼동을 방지하고 적절한 라우팅을 보장하기 위해 사용자가 비즈니스용 Skype 모드에 있는 경우 Teams 클라이언트에서 호출 및 채팅 기능을 사용하지 않도록 설정됩니다. 마찬가지로 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있는 경우 Teams의 모임 예정이 명시적으로 비활성화되어 사용자가 SfBWithTeamsCollabAndMeetings 모드에 있는 경우 명시적으로 사용하도록 설정됩니다.

요구 사항에 따라 조직에서 선택한 업그레이드 경로에 따라 적절한 공존 모드를 할당할 수 있습니다. 자세한 내용은 비즈니스용 Skype와 함께 [Teams를](migration-interop-guidance-for-teams-with-skype.md) 사용하는 조직에 대한 마이그레이션 및 상호 운영성 지침을 참조하고 공존 및 업그레이드 설정 설정을 [참조하세요.](./setting-your-coexistence-and-upgrade-settings.md)


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>3단계: 비즈니스용 Skype에서 프레미스에서 Teams 전용으로 사용자 이동

궁극적으로 사용자를 TeamsOnly 모드로 이동해야 합니다. 여기에는 프레미스 환경에 따라 한 두 단계가 있을 수 있습니다.  

자세한 내용은 사용자 이동을 [On-프레미스와](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) 클라우드 간에 이동하고 사용자를 [프레미스에서 Teams로 이동을 참조하세요.](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>4단계: 하이브리드 사용 안 하여 클라우드로 마이그레이션을 완료합니다.

모든 사용자를 프레미스에서 클라우드로 이동한 후 비즈니스용 Skype 배포를 해제할 수 있습니다. 자세한 내용은 하이브리드 사용 안 하여 [클라우드로 마이그레이션을 완료합니다.](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)


## <a name="phone-system-and-pstn-connectivity-options"></a>전화 시스템 및 PSTN 연결 옵션

Teams가 있는 전화 시스템은 사용자가 TeamsOnly 모드에 있는 후에 지원됩니다. (사용자가 제도 모드인 경우 전화 시스템은 비즈니스용 Skype에서만 지원됩니다.) 

### <a name="pstn-connectivity-options"></a>PSTN 연결 옵션

PSTN(공용 전환 전화 네트워크) 연결 옵션을 고려할 때 비즈니스용 Skype에서 TeamsOnly 모드로 전환할 때 두 가지 가능한 시나리오가 있습니다.

- 비즈니스용 Skype온-프레미스에 Enterprise Voice 사용자가 온라인으로 이동하고 Microsoft 통화 계획을 사용할 것입니다. 이 사용자를 Teams로 마이그레이션하려면 사용자의 비즈니스용 Skype 계정을 클라우드로 이동하고 A) 해당 사용자의 전화 번호 포트를 Microsoft 통화 계획 또는 B로 이동하도록 조정해야 합니다. 사용 가능한 지역에서 새 구독자 번호를 할당합니다.  자세한 내용은 비즈니스용 Skype 서버의 모든 Enterprise Voice [Microsoft Calling Plan 을 참조하세요.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)

- 비즈니스용 Skype온-프레미스에서 온라인로 Enterprise Voice PSTN 연결을 유지하게 됩니다. 이 사용자를 Teams로 마이그레이션하려면 사용자의 비즈니스용 Skype 계정을 클라우드로 이동하고, 사용자의 마이그레이션을 통해 직접 라우팅으로 이동하는 조정이 필요합니다. 자세한 내용은 비즈니스용 Skype 서버의 프레미스와 함께 Enterprise Voice 라우팅 [을 참조하세요.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>비즈니스용 Skype 서버가 있는 조직에 대한 중요한 고려 사항

- 다음 문서에서는 중요한 업그레이드 개념 및 공존 동작을 설명합니다.
    - [Teams 및 비즈니스용 Skype의 공존](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [공존 모드 - 참조](migration-interop-guidance-for-teams-with-skype.md)
    - [Teams 클라이언트 환경 및 공존 모드 준수](teams-client-experience-and-conformance-to-coexistence-modes.md)

- 비즈니스용 Skype 하이브리드 설정은 TeamsOnly 모드로 마이그레이션하기 위한 전제입니다. 하이브리드 없이 제도 모드에서 Teams를 사용할 수 있는 반면, 사용자가 비즈니스용 Skype에서 비즈니스용 Skype Online으로 [이동(Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)사용)까지 TeamsOnly 모드로 전환할 수 없습니다. 자세한 내용은 하이브리드 연결 [구성을 참조하세요.](/skypeforbusiness/hybrid/configure-hybrid-connectivity)

- 조직에 비즈니스용 Skype 서버가 있으며 하이브리드 연결을 구성하지 않은 경우 Teams 기능을 관리하려면 .onmicrosoft.com 계정이 있어야 합니다. 

- 비즈니스용 Skype 계정이 있는 팀 사용자(즉, Move-CsUser를 사용하여 클라우드로 이동되지 않은 경우)는 비즈니스용 Skype 사용자와 상호 협력할 수 없으며 외부 사용자와 페더러트할 수 없습니다. 이 기능은 사용자가 섬 모드 또는 TeamsOnly 사용자로 클라우드로 이동한 후만 사용할 수 있습니다. 

- 비즈니스용 Skype 계정이 있는 사용자가 있는 경우 테넌트 수준에서 TeamsOnly 모드를 할당할 수 없습니다. 먼저 비즈니스용 Skype 계정을 사용하여 모든 사용자를 클라우드로 이동한 다음 하이브리드를 사용하지 않도록 설정하여 클라우드로의 마이그레이션을 `Move-CsUser` [완료해야 합니다.](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)  `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` Office 365가 아닌 위치를 지적하는 lyncdiscover DNS 레코드가 검색되면 테넌트 수준에서 작동하지 않습니다.

- 사용자가 올바른 비즈니스용 Skype 특성으로 Azure AD에 올바르게 동기화되었는지 확인해야 합니다. 이러한 특성은 모두 "msRTCSIP-"가 있는 도두입니다. 사용자가 Azure AD에 제대로 동기화되지 않은 경우 Teams의 관리 도구는 이러한 사용자를 관리할 수 없습니다. (예를 들어 이러한 특성을 제대로 동기화하지 않으면 Teams 정책을 On-프레미스 사용자에게 할당할 수 없습니다.) 자세한 내용은 Teams 및 [비즈니스용 Skype에 대한 Azure AD Connect 구성을 참조하세요.](/SkypeForBusiness/hybrid/configure-azure-ad-connect)

- 하이브리드 조직에서 새 TeamsOnly 또는 비즈니스용 Skype Online 사용자를 만들하려면 먼저 비즈니스용 Skype Server온-프레미스에서 사용자를 사용하도록 설정한 다음 Move-CsUser를 사용하여 사용자를 프레미스에서 클라우드로 이동해야 합니다.   먼저 사용자 만들기는 먼저 나머지 모든 다른 비즈니스용 Skype for Business 사용자가 새로 만든 사용자로 라우팅할 수 있도록 합니다. 모든 사용자가 온라인으로 이동된 후, 먼저 온라인에서 사용자를 사용하도록 설정하는 것이 더 이상 필요하지 않습니다.

- 사용자가온-프레미스에서 클라우드로 이동하면 해당 사용자가 구성한 모임은 -MoveToTeams 스위치를 지정하는지 여부에 따라 비즈니스용 Skype Online 또는 Teams로 마이그레이션됩니다.

- 비즈니스용 Skype 클라이언트에서 프레미스 사용자에 대한 알림을 표시하려면 On-프레미스 도구ET에서 TeamsUpgradePolicy를 사용해야 합니다. NotifySfbUsers 매개 변수만이 프레미스 사용자와 관련이 있습니다.  On-Premises 사용자는 TeamsUpgradePolicy의 온라인 인스턴스에서 해당 모드를 수신합니다. [Grant-CsTeamsUpgradePolicy의 노트를 참조합니다.](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) 

>[!NOTE]
> 조직이 비즈니스용 Skype 서버의 이미 프레미스 배포가 없는 경우 2019년 Sept 3 이후에 만든 모든 새 테넌트가 TeamsOnly 테넌트로 만들어집니다. Microsoft는 DNS 레코드를 사용하여 비즈니스용 비즈니스용 Skype 조직을 식별합니다. 조직에 공용 DNS 항목이 없는 비즈니스용 Skype Server가 있는 경우 새 테넌트 다운그레이드를 설정하려면 Microsoft 지원에 전화해야 합니다. 

## <a name="related-links"></a>관련 링크

[비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간에 하이브리드 연결 구성](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS(모임 마이그레이션 서비스) 사용](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)