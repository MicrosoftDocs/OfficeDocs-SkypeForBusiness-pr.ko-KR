---
title: 온-프레미스 비즈니스용 Skype Microsoft Teams 업그레이드
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype 온-프레미스 배포에서 Microsoft Teams 조직을 업그레이드하는 방법을 알아봅니다.
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
ms.openlocfilehash: c4b233978b9f9edf0aabbdfb8f9b24ff55a234cc
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681369"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>비즈니스용 Skype 온-프레미스에서 Teams 업그레이드

![배포 및 구현을 강조하는 업그레이드 경험 다이어그램](media/upgrade-banner-deployment.png "배포 및 구현 단계에 중점을 둔 업그레이드 과정의 단계")

이 문서는 업그레이드 과정의 배포 및 구현 단계의 일부입니다. 계속하기 전에 다음 작업을 완료했는지 확인합니다.

- [프로젝트 관련자 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](./upgrade-define-project-scope.md)
- [비즈니스용 Skype 및 Teams 공존 및 상호 운용성 이해](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [업그레이드 경험 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [환경 준비](./upgrade-prepare-environment.md)
- [조직 준비](./upgrade-prepare-organization.md)
- [파일럿 수행](./pilot-essentials.md)

비즈니스용 Skype 서버 또는 Microsoft Lync Server 온-프레미스를 배포했고 조직에서 Teams 업그레이드하려는 경우 이 문서의 지침을 따르세요. 비즈니스용 Skype 서버 Teams [간의 하이브리드 연결 계획에 설명된 대로 Microsoft 365 조직과의 하이브리드 연결을](/skypeforbusiness/hybrid/plan-hybrid-connectivity) 설정해야 합니다.

시작하기 전에 이 문서의 뒷부분에 비즈니스용 Skype 서버 [온-프레미스를 사용하는 조직에 대한 중요한 고려 사항](#important-considerations-for-organizations-with-skype-for-business-server-on-premises)도 검토해야 합니다.

> [!IMPORTANT]
> 비즈니스용 Skype Online은 2021년 7월 31일에 은퇴했습니다. 혜택 실현을 최대화하고 조직에서 업그레이드를 구현할 적절한 시간을 갖도록 하려면 오늘 Microsoft Teams 위한 여정을 시작하는 것이 좋습니다. 성공적인 업그레이드는 기술 및 사용자 준비 상태를 조정하므로 Microsoft Teams 여정을 탐색할 때 이 지침을 활용해야 합니다.

## <a name="step-1-configure-hybrid-connectivity"></a>1단계: 하이브리드 연결 구성

온-프레미스 사용자를 Teams 업그레이드하기 위한 주요 필수 구성 요소는 비즈니스용 Skype 서버 온-프레미스 배포에 대한 하이브리드 연결을 구성하는 것입니다.

먼저 [계획 하이브리드 연결을](/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=%2fSkypeForBusiness%2fsfbhybridtoc%2ftoc.json) 읽은 다음 하이브리드 [연결 구성](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)에 설명된 작업을 따릅니다.

## <a name="step-2-set-transitional-coexistence-mode-optional"></a>2단계: 과도기 공존 모드 설정(선택 사항)

비즈니스용 Skype 클라이언트와 Teams 클라이언트와 사용자 간의 공존 및 상호 운용성은 [공존 모드](migration-interop-guidance-for-teams-with-skype.md)로 정의됩니다. 하이브리드 조직은 기본적으로 아일랜드 모드입니다. 아일랜드 모드를 사용하면 Teams 클라이언트와 비즈니스용 Skype 클라이언트를 함께 사용할 수 있습니다. 조직은 필요에 따라 다른 공존 모드를 사용하여 조직이 비즈니스용 Skype Teams 전환함에 따라 최종 사용자에게 예측 가능한 환경을 제공할 수 있습니다. 조직에서 온-프레미스 사용자에 대해 사용하는 모드에 관계없이 해당 사용자가 온-프레미스에서 클라우드로 이동하면 TeamsOnly가 됩니다(다른 모드는 사용할 수 없음).  사용자가 여전히 비즈니스용 Skype 서버 사용하는 한 TeamsOnly 이외의 모드로 할당할 수 있습니다. 필요한 경우 TeamsOnly 사용자를 온-프레미스로 다시 이동할 수 있으므로 테넌트의 TeamsUpgradePolicy 글로벌 정책을 받게 됩니다.

사용자가 비즈니스용 Skype 모드에 있으면 들어오는 모든 채팅 및 통화가 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다. 최종 사용자 혼동을 방지하고 적절한 라우팅을 보장하기 위해 Teams 클라이언트의 통화 및 채팅 기능은 *비즈니스용 Skype 모드가 할당된 사용자에 대해 사용하지 않도록 설정됩니다*. Teams 모임 예약은 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있을 때 *사용하지 않도록 설정* 되고 사용자가 SfBWithTeamsCollabAndMeetings 모드에 있을 때 사용하도록 설정됩니다.

요구 사항에 따라 조직에서 선택한 업그레이드 경로에 따라 적절한 공존 모드를 할당할 수 있습니다. 자세한 내용은 비즈니스용 Skype 및 [공존 및 업그레이드 설정 설정](./setting-your-coexistence-and-upgrade-settings.md)[과 함께 Teams 사용하는 조직에 대한 마이그레이션 및 상호 운용성 지침을](migration-interop-guidance-for-teams-with-skype.md) 참조하세요.

## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>3단계: 비즈니스용 Skype 온-프레미스에서 Teams 전용으로 사용자 이동

Microsoft는 최근에 사용자를 TeamsOnly로 이동하는 프로세스를 간소화했습니다. 이 프로세스는 사용 중인 비즈니스용 Skype 서버 또는 Lync Server 2013 버전에 관계없이 단일 단계입니다. 자세한 내용은 [온-프레미스와 클라우드 간에 사용자 이동 및](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) [온-프레미스에서 Teams 사용자 이동](/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)을 참조하세요.

## <a name="step-4-complete-your-migration-to-the-cloud-by-disabling-hybrid-and-decommissioning-on-premises-skype-for-business"></a>4단계: 하이브리드를 사용하지 않도록 설정하여 클라우드로 마이그레이션 완료 및 온-프레미스 비즈니스용 Skype

온-프레미스에서 클라우드로 모든 사용자를 이동한 후 온-프레미스 비즈니스용 Skype 배포를 해제할 수 있습니다. 자세한 내용은 [온-프레미스 비즈니스용 Skype 환경 서비스 해제를 참조하세요](/skypeforbusiness/hybrid/decommission-on-prem-overview).

## <a name="phone-system-and-pstn-connectivity-options"></a>전화 시스템 및 PSTN 연결 옵션

Teams 전화 시스템 사용자가 TeamsOnly 모드에 있으면 지원됩니다. (사용자가 아일랜드 모드인 경우 전화 시스템 비즈니스용 Skype만 지원됩니다.)

### <a name="pstn-connectivity-options"></a>PSTN 연결 옵션

PSTN(공중 전화망) 연결 옵션을 고려할 때 비즈니스용 Skype 온-프레미스에서 TeamsOnly 모드로 이동할 때 두 가지 가능한 시나리오가 있습니다.

- Enterprise Voice 온-프레미스에 비즈니스용 Skype 사용자는 온라인으로 전환하고 Microsoft 통화 플랜을 사용합니다. 이 사용자를 Teams 마이그레이션하려면 사용자의 온-프레미스 비즈니스용 Skype 계정을 클라우드로 이동하고 A) 해당 사용자의 전화 번호 포트를 Microsoft 통화 플랜 또는 B로 이동하도록 조정해야 합니다. 사용 가능한 지역에서 새 구독자 번호를 할당합니다.  자세한 내용은 [Enterprise Voice 비즈니스용 Skype 서버 온-프레미스에서 Microsoft 통화 플랜까지를 참조하세요](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).

- Enterprise Voice 온-프레미스에 비즈니스용 Skype 사용자는 온라인으로 이동하고 온-프레미스 PSTN 연결을 유지합니다. 이 사용자를 Teams 마이그레이션하려면 사용자의 온-프레미스 비즈니스용 Skype 계정을 클라우드로 이동하고 사용자를 직접 라우팅으로 마이그레이션하는 작업을 조정해야 합니다. 자세한 내용은 [Enterprise Voice 비즈니스용 Skype 서버 온-프레미스에서 직접 라우팅까지를 참조하세요](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).

## <a name="important-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>비즈니스용 Skype 서버 온-프레미스를 사용하는 조직에 대한 중요한 고려 사항

- 비즈니스용 Skype 하이브리드 설정은 TeamsOnly 모드로 마이그레이션하기 위한 필수 구성 요소입니다. 온-프레미스 비즈니스용 Skype 서버 사용자가 하이브리드 없이 아일랜드 모드에서 Teams 사용할 수 있습니다. 그러나 하이브리드 연결이 필요한 [Move-CsUser](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)를 사용하여 사용자를 클라우드로 이동하지 않고는 TeamsOnly 모드로 전환할 수 없습니다. 자세한 내용은 [하이브리드 연결 구성을 참조하세요](/skypeforbusiness/hybrid/configure-hybrid-connectivity). 비즈니스용 Skype Online의 향후 사용 중지는 이 요구 사항을 변경하지 않습니다. 조직에서 비즈니스용 Skype 서버 Teams 이동하려면 *사용 중지 전과 똑같은* 도구 집합을 사용하여 하이브리드를 설정하고 구성해야 합니다.

- 온-프레미스 사용자를 클라우드로 이동하려면 온-프레미스 관리 도구에서 사용합니다 `Move-CsUser` . 더 이상 사용자를 온-프레미스에서 TeamsOnly로 직접 이동하는 스위치를 지정할 `-MoveToTeams` 필요가 없습니다. 사용자에게 TeamsOnly 모드가 자동으로 할당되고 해당 온-프레미스 모임은 스위치가 지정되었는지 여부에 `-MoveToTeams` 관계없이 Teams 모임으로 자동으로 변환됩니다.

- 조직에 비즈니스용 Skype 서버 있고 하이브리드 연결을 구성하지 않았지만 여전히 Teams 사용하려는 경우 Teams 기능을 관리하려면 .onmicrosoft.com 도메인이 있는 관리 계정을 사용해야 합니다. 하이브리드 연결이 없으면 관리 도구가 온-프레미스 도메인을 인식하지 못합니다.

- 온-프레미스에 비즈니스용 Skype 계정이 있는 Teams 사용자(즉, Move-CsUser를 사용하여 클라우드로 아직 이동되지 않은 사용자)는 비즈니스용 Skype 사용자와 상호 운용할 수 없으며 외부 사용자와 페더레이션할 수도 없습니다. 이 기능은 사용자가 클라우드로 이동되고 TeamsOnly 사용자인 경우에만 사용할 수 있습니다.

- 온-프레미스에 비즈니스용 Skype 계정이 있는 사용자가 있거나 온-프레미스 배포에 대한 lyncdiscover DNS 레코드가 여전히 있는 경우 테넌트 수준에서 TeamsOnly 모드를 할당할 수 없습니다. 먼저 온-프레미스 비즈니스용 Skype 계정이 있는 모든 사용자를 사용하여 `Move-CsUser`클라우드로 이동해야 합니다. 그런 다음 [하이브리드 사용 안 함](/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)에서 설명한 단계에 따라 DNS 항목 제거를 포함하여 클라우드로의 마이그레이션을 완료합니다. `Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams`는 Office 365 이외의 위치를 가리키는 lyncdiscover DNS 레코드가 검색되면 테넌트 수준에서 작동하지 않습니다.

- 사용자가 올바른 비즈니스용 Skype 특성을 사용하여 Azure AD 올바르게 동기화되었는지 확인해야 합니다. 이러한 특성은 모두 "msRTCSIP-"가 있는 접두사입니다. 사용자가 Azure AD 제대로 동기화되지 않은 경우 Teams 관리 도구는 이러한 사용자를 관리할 수 없습니다. 예를 들어 이러한 특성을 제대로 동기화하지 않는 한 온-프레미스 사용자에게 Teams 정책을 할당할 수 없습니다. 자세한 내용은 [Teams 및 비즈니스용 Skype 대한 Azure AD 커넥트 구성](/SkypeForBusiness/hybrid/configure-azure-ad-connect)을 참조하세요.

- 하이브리드 조직에서 새 TeamsOnly를 만들려면 *먼저 비즈니스용 Skype 서버 온-프레미스에서 사용자를 사용하도록 설정한* 다음 Move-CsUser를 사용하여 온-프레미스에서 클라우드로 사용자를 이동해야 합니다.  먼저 온-프레미스에서 사용자를 만들면 나머지 온-프레미스 비즈니스용 Skype 사용자가 새로 만든 사용자로 라우팅할 수 있습니다. *모든* 사용자가 온라인으로 이동되면 더 이상 온-프레미스에서 사용자를 먼저 사용하도록 설정할 필요가 없습니다.

- 온-프레미스 사용자에 대한 비즈니스용 Skype 클라이언트에 알림을 표시하려면 온-프레미스 도구 집합에서 TeamsUpgradePolicy를 사용해야 합니다. NotifySfbUsers 매개 변수만 온-프레미스 사용자와 관련이 있습니다.  온-프레미스 사용자는 TeamsUpgradePolicy의 온라인 인스턴스에서 모드를 받습니다. [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)의 참고 사항을 참조하세요.

> [!NOTE]
> 2019년 9월 3일 이후에 만들어진 모든 새 테넌트는 조직에 이미 비즈니스용 Skype 서버 온-프레미스 배포가 없는 한 TeamsOnly 테넌트로 만들어집니다. Microsoft는 DNS 레코드를 사용하여 온-프레미스 비즈니스용 Skype 서버 조직을 식별합니다. 자세한 내용은 [하이브리드가 되는 온-프레미스 조직에 대한 DNS 영향을](/SkypeForBusiness/hybrid/configure-hybrid-connectivity#dns-implications-for-on-premises-organizations-that-become-hybrid) 참조하세요.

- 다음 문서에서는 중요한 업그레이드 개념 및 공존 동작에 대해 설명합니다.
  - [Teams 및 비즈니스용 Skype 공존](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
  - [공존 모드 - 참조](migration-interop-guidance-for-teams-with-skype.md)
  - [Teams 클라이언트 환경 및 공존 모드 준수](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="related-links"></a>관련 링크

[비즈니스용 Skype 함께 Teams 사용하는 조직을 위한 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md)

[비즈니스용 Skype 서버 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[MMS(모임 마이그레이션 서비스) 사용](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
