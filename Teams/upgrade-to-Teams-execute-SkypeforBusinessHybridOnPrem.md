---
title: 비즈니스용 Skype 프레미스를 Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 조직을 프레미스 Microsoft Teams 배포에서 비즈니스용 Skype 방법을 설명합니다.
ms.localizationpriority: medium
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
ms.openlocfilehash: d5ad5bc82771a3a8f020600a48848a074b88aec4
ms.sourcegitcommit: d3c48f0c147cf0c47d5eb4ea1128b5bca13be718
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2022
ms.locfileid: "62299063"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>비즈니스용 Skype 프레미스에서 Teams

![배포 및 구현을 강조하는 업그레이드 여정 다이어그램입니다.](media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점 있는 업그레이드 여정의 단계")

이 문서는 업그레이드 단계의 배포 및 구현 단계의 일부입니다. 계속하기 전에 다음 작업을 완료한지 확인합니다.

-   [프로젝트 관계자 인리스트](upgrade-enlist-stakeholders.md)
-   [프로젝트 범위 정의](./upgrade-define-project-scope.md)
-   [비즈니스용 Skype 및 상호운용성을 Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
-   [업그레이드 여정을 선택했습니다.](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [환경 준비](./upgrade-prepare-environment.md)
-   [조직 준비](./upgrade-prepare-organization.md)
-   [파일럿 수행](./pilot-essentials.md)

온-프레미스 또는 Microsoft Lync Server를 비즈니스용 Skype 서버 조직에서 업그레이드하려는 경우 Teams 이 문서의 지침을 따르하세요. 사용자와 사용자 간의 하이브리드 연결 계획에 설명된 Microsoft 365 조직과 하이브리드 연결을 비즈니스용 Skype 서버 [Teams](/skypeforbusiness/hybrid/plan-hybrid-connectivity).

시작하기 전에 이 문서 의 2부에서 [](#important-considerations-for-organizations-with-skype-for-business-server-on-premises) 비즈니스용 Skype 서버 조직에 대한 중요한 고려 사항도 검토해야 합니다.

> [!IMPORTANT]
> 비즈니스용 Skype 온라인이 2021년 7월 31일 사용 중지됩니다. 혜택 현실화를 최대화하고 조직에서 업그레이드를 구현할 적절한 시간을 확보하기 위해 현재 업그레이드를 위한 여정을 Microsoft Teams 권장됩니다. 업그레이드가 성공하면 기술 및 사용자 준비가 일치하기 때문에 이 지침을 활용하여 업그레이드를 진행하는 Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>1단계: 하이브리드 연결 구성 

프레미스 사용자를 업그레이드하기 위한 주요 Teams 구성하는 것은 비즈니스용 Skype 서버 배포에 대한 하이브리드 연결을 비즈니스용 Skype 서버 것입니다. 

먼저 [Plan 하이브리드 연결을 읽고](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json) 하이브리드 연결 구성에 설명된 작업을 [수행합니다](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>2단계: 전환 공존 모드 설정(선택 사항)

클라이언트와 사용자 간의 공존 및 비즈니스용 Skype Teams 상호 연동성은 공존 모드로 [정의됩니다](migration-interop-guidance-for-teams-with-skype.md). 하이브리드 조직은 기본적으로 제도 모드입니다. 섬 모드를 사용하면 사용자가 클라이언트와 Teams 비즈니스용 Skype 둘 다 사용할 수 있습니다. 조직은 선택적으로 다른 공존 모드를 사용하여 조직에서 다른 사용자로 전환할 때 최종 사용자에게 예측 가능한 환경을 비즈니스용 Skype Teams. 조직에서 해당온-프레미스 사용자에 대해 사용하는 모든 모드로, 해당 사용자가온-프레미스에서 클라우드로 이동하면 TeamsOnly(다른 모드는 사용할 수 없습니다)가 됩니다.  사용자가 여전히 비즈니스용 Skype 서버 TeamsOnly가 아니라 다른 모드를 할당할 수 있습니다. 필요한 경우 TeamsOnly 사용자를 다시 프레미스로 이동할 수 있습니다. 이로 인해 테넌트가 TeamsUpgradePolicy의 전역 정책을 수신하게 됩니다.

사용자가 모든 비즈니스용 Skype 있는 경우 들어오는 모든 채팅 및 호출이 사용자의 비즈니스용 Skype 라우팅됩니다. 최종 사용자 혼동을 방지하고 적절한 라우팅을 보장하기 위해 Teams 모드 중 비즈니스용 Skype 클라이언트의 호출 및 채팅 기능을 사용하지 않도록 설정 *됩니다*. 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있는 경우 사용자가 SfBWithTeamsCollabAndMeetings 모드  에 있는 경우 모임일정이 비활성화됩니다. Teams

요구 사항에 따라 조직에서 선택한 업그레이드 경로에 따라 적절한 공존 모드를 할당할 수 있습니다. 자세한 [내용은 공유 및](migration-interop-guidance-for-teams-with-skype.md) 업그레이드 설정과 함께 Teams 조직에 비즈니스용 Skype 및 상호운용성 지침을 [참조하세요](./setting-your-coexistence-and-upgrade-settings.md).


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>3단계: 사용자 비즈니스용 Skype 프레미스에서 Teams 전용으로 이동

Microsoft는 최근에 사용자를 TeamsOnly로 이동하는 프로세스를 간소화했습니다. 이 프로세스는 현재 사용 중인 비즈니스용 Skype 서버 Lync Server 2013 버전에 관계없이 단일 단계입니다. 자세한 내용은 프레미스 [](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)와 클라우드 간에 사용자모브를 참조하고, 사용자 이동을 프레미스[에서](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 프레미스로 Teams. 

## <a name="step-4-complete-your-migration-to-the-cloud-by-disabling-hybrid-and-decommissioning-on-premises-skype-for-business"></a>4단계: 하이브리드를 사용 안 하게 하여 클라우드로 마이그레이션을 완료하고, 프레미스에서 하이브리드를 해제하고 비즈니스용 Skype

모든 사용자를 On-프레미스에서 클라우드로 이동한 후, 모든 프레미스 배포를 비즈니스용 Skype 있습니다. 자세한 내용은 On-프레미스 환경 해제를 비즈니스용 Skype [참조하세요](/skypeforbusiness/hybrid/decommission-on-prem-overview).


## <a name="phone-system-and-pstn-connectivity-options"></a>전화 시스템 및 PSTN 연결 옵션

전화 시스템 Teams TeamsOnly 모드에 있는 후에 지원됩니다. (사용자가 제도 모드인 경우 전화 시스템 지원되는 비즈니스용 Skype.) 

### <a name="pstn-connectivity-options"></a>PSTN 연결 옵션

PSTN(공용 전환 전화 네트워크) 연결 옵션을 고려할 때 프레미스에서 TeamsOnly 모드로 비즈니스용 Skype 두 가지 시나리오가 있습니다.

- 온라인으로 비즈니스용 Skype Microsoft 통화 계획을 사용하는 Enterprise Voice 프레미스를 사용하는 사용자입니다. 이 사용자를 Teams 클라우드로 사용자의 비즈니스용 Skype 이동하고 A) 해당 사용자의 전화 번호 포트를 Microsoft 호출 계획 또는 B로 이동하도록 조정해야 합니다. 사용 가능한 지역에서 새 구독자 번호를 할당해야 합니다.  자세한 내용은 비즈니스용 Skype 서버 프레미스에서 Microsoft Enterprise Voice 계획으로 [을 참조하세요](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- 온라인으로 비즈니스용 Skype PSTN 연결을 유지하는 Enterprise Voice 사용자와 함께온-프레미스를 사용할 수 있습니다. 이 사용자를 Teams 사용자온-프레미스 비즈니스용 Skype 클라우드로 이동하고, 사용자 마이그레이션을 통해 직접 라우팅으로 이동하는 조정이 필요합니다. 자세한 내용은 비즈니스용 Skype 서버 및 Enterprise Voice 프레미스에서 직접 라우팅을 [참조하세요](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).


## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>프레미스가 있는 조직에 비즈니스용 Skype 서버 중요 고려 사항

- 하이브리드 비즈니스용 Skype 설정은 TeamsOnly 모드로 마이그레이션하기 위한 전제입니다. 모든 사용자가 하이브리드 없이 비즈니스용 Skype 서버 섬 모드에서 Teams 사용할 수 있습니다. 그러나 하이브리드 연결이 필요한 [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)를 사용하여 사용자를 클라우드로 이동하지 않고 TeamsOnly 모드로 전환할 수 없습니다. 자세한 내용은 하이브리드 연결 [구성을 참조하세요](/skypeforbusiness/hybrid/configure-hybrid-connectivity). 예정된 온라인 비즈니스용 Skype 이 요구 사항은 변경되지 않습니다. 조직에서 비즈니스용 Skype 서버 Teams 이전과 동일한 도구 집합을 사용하여 하이브리드를 설정하고 구성 *해야 합니다*.

- 프레미스 사용자를 `Move-CsUser` 클라우드로 이동하기 위해 프레미스 관리 도구에서 사용합니다. 더 이상 `-MoveToTeams` 사용자를 On-프레미스에서 TeamsOnly로 직접 이동하기 위해 스위치를 지정할 필요가 없습니다. 사용자는 TeamsOnly `-MoveToTeams` 모드가 자동으로 할당되며, 스위치가 지정되어 있는지에 관계없이 해당 Teams 모임으로 자동 변환됩니다.

- 조직에 비즈니스용 Skype 서버 하이브리드 연결을 구성하지 않은 경우 여전히 Teams 기능을 관리하려면 .Teams 도메인이 있는 관리 계정을 onmicrosoft.com 있습니다. 하이브리드 연결이 없는 경우 관리 도구는 프레미스 도메인을 인식하지 못합니다. 

- Teams 계정이 비즈니스용 Skype 사용자(즉, Move-CsUser를 사용하여 클라우드로 아직 이동되지 않은 사용자)는 모든 사용자와 상호 비즈니스용 Skype 수 없으며 외부 사용자와 페더리트할 수 없습니다. 이 기능은 사용자가 클라우드로 이동하고 TeamsOnly 사용자인 경우만 사용할 수 있습니다. 

- 온-프레미스 비즈니스용 Skype 사용자가 있는 경우 또는 온-프레미스 배포에 대한 lyncdiscover DNS 레코드가 있는 경우 테넌트 수준에서 TeamsOnly 모드를 할당할 수 없습니다. 먼저 를 사용하여 프레미스 계정이 있는 비즈니스용 Skype 클라우드로 이동해야 합니다`Move-CsUser`. 그런 다음 하이브리드 사용 안 에 설명된 단계를 수행 [하여](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid) DNS 항목 제거를 포함하는 클라우드로의 마이그레이션을 완료합니다. `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`lyncdiscover Office 365 DNS 레코드가 검색되면 테넌트 수준에서 작동하지 않습니다.

- 사용자가 올바른 특성으로 Azure AD에 비즈니스용 Skype 해야 합니다. 이러한 특성은 모두 "msRTCSIP-"가 있는 도두입니다. 사용자가 Azure AD에 제대로 동기화되지 않은 경우 해당 Teams 관리 도구는 이러한 사용자를 관리할 수 없습니다. (예를 들어 이러한 특성을 제대로 동기화하지 않으면 Teams 정책을 할당할 수 없습니다.) 자세한 내용은 Azure AD 커넥트 및 Teams [비즈니스용 Skype](/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- 하이브리드 조직에서 새 TeamsOnly를 만들하려면 먼저 사용자가 비즈니스용 Skype 서버 설정한 다음 Move-CsUser를 사용하여 사용자를온-프레미스 *에서* 클라우드로 이동해야 합니다.  먼저, 사용자가 새로 만든 사용자로 라우팅할 수 있도록 비즈니스용 Skype 다른 모든 비즈니스용 Skype 사용자를 만들 수 있습니다. 모든 *사용자가* 온라인으로 이동된 후, 먼저 온라인에서 사용자를 사용하도록 설정하는 것이 더 이상 필요하지 않습니다.

- 프레미스 사용자에 대한 비즈니스용 Skype 클라이언트에 알림을 표시하려면 On-Premises 도구세트에서 TeamsUpgradePolicy를 사용해야 합니다. NotifySfbUsers 매개 변수만이 프레미스 사용자와 관련이 있습니다.  On-Premises 사용자는 TeamsUpgradePolicy의 온라인 인스턴스에서 해당 모드를 수신합니다. [Grant-CsTeamsUpgradePolicy의 노트를 참조합니다](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> 조직에 이미 프레미스 배포가 없는 경우 2019년 3월 3일 이후 생성된 모든 새 테넌트가 TeamsOnly 테넌트로 비즈니스용 Skype 서버. Microsoft는 DNS 레코드를 사용하여 조직에서 비즈니스용 Skype 서버 식별합니다. 자세한 내용은 하이브리드가 되는 프레미스 [조직에 대한 DNS 의미를 참조하세요](/SkypeForBusiness/hybrid/configure-hybrid-connectivity#dns-implications-for-on-premises-organizations-that-become-hybrid). 

- 다음 문서에서는 중요한 업그레이드 개념 및 공존 동작을 설명합니다.
    - [Teams 및 비즈니스용 Skype](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
    - [공존 모드 - 참조](migration-interop-guidance-for-teams-with-skype.md)
    - [Teams 클라이언트 환경 및 공존 모드 준수](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="related-links"></a>관련 링크

[조직과 함께 Teams 조직에 대한 마이그레이션 및 상호 비즈니스용 Skype](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype 서버 및 Microsoft 365 Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS(모임 마이그레이션 서비스) 사용](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
