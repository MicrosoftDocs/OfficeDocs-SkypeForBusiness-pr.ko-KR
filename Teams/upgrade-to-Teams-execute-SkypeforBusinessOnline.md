---
title: 비즈니스용 Skype Online에서 Microsoft Teams로 업그레이드
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 비즈니스용 Skype Online 배포에서 Microsoft Teams로 조직을 업그레이드하는 방법을 알아봅니다.
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
ms.openlocfilehash: 5da45fcc5a9459b909e03f0d4e904b57d9a3f0fa
ms.sourcegitcommit: 9a9168d5c40bbb0cceaf3ffd11eb104c137f26b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67590215"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>비즈니스용 Skype Online에서 Teams로 업그레이드

![배포 및 구현을 강조하는 업그레이드 경험 다이어그램](media/upgrade-banner-deployment.png "배포 및 구현 단계에 중점을 둔 업그레이드 과정의 단계")

이 문서는 업그레이드 과정의 배포 및 구현 단계의 일부입니다. 계속하기 전에 다음 작업을 완료했는지 확인합니다.

- [프로젝트 관련자 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](./upgrade-define-project-scope.md)
- [비즈니스용 Skype 및 Teams의 공존 및 상호 운용성 이해](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [업그레이드 경험 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [환경 준비](./upgrade-prepare-environment.md)
- [조직 준비](./upgrade-prepare-organization.md)
- [파일럿 수행](./pilot-essentials.md)

비즈니스용 Skype Online을 완전히 배포하고 사용자를 비즈니스용 Skype Teams로 업그레이드하려는 경우 이 문서의 지침을 따릅니다. 사용자에게 적절한 공존 및 업그레이드 모드를 할당하여 조직에서 선택한 업그레이드 경험에 따라 사용자를 선택적으로 또는 올인할 수 있습니다.

> [!IMPORTANT]
> 비즈니스용 Skype Online은 2021년 7월 31일에 은퇴했습니다. 혜택 실현을 최대화하고 조직에서 업그레이드를 구현할 적절한 시간을 갖도록 하려면 현재 Microsoft Teams로의 여정을 시작하는 것이 좋습니다. 성공적인 업그레이드는 기술 및 사용자 준비 상태를 조정하므로 Microsoft Teams로의 여정을 탐색할 때 여기에 있는 지침을 활용해야 합니다.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>공존 및 업그레이드 모드 할당

Microsoft Teams 관리 센터 또는 비즈니스용 Skype 원격 Windows PowerShell 세션을 사용하여 수행할 수 있는 TeamsUpgradePolicy의 UpgradeToTeams 인스턴스를 할당하여 사용자를 TeamsOnly 모드로 업그레이드할 수 있습니다. 한 단계에서 전체 테넌트 업그레이드를 하려는 경우 사용자별로 또는 테넌트 전체에서 이 작업을 수행할 수 있습니다. 

자세한 내용은 [공존 및 업그레이드 설정 및](./setting-your-coexistence-and-upgrade-settings.md) [TeamsUpgradePolicy 설정: 마이그레이션 및 공존 관리를](upgrade-to-teams-on-prem-tools.md) 참조하세요.

## <a name="upgrade-all-users-to-teams-at-one-time"></a>모든 사용자를 Teams로 한 번에 업그레이드

다음 단계에 따라 모든 사용자를 Teams로 한 번에 업그레이드합니다.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>1단계: 사용자에게 변경 내용 알림(선택 사항)

1. Microsoft Teams 관리 센터에서 **Teams Teams** > **업그레이드 설정을** 선택합니다.
2. **공존 모드** 에서 **Teams로의 업그레이드를 사용할 수 있음을 비즈니스용 Skype 사용자에게 알리기** 스위치를 켜기로 변경 **합니다**.

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>2단계: 조직의 TeamsOnly에 공존 모드 설정

1. Microsoft Teams 관리 센터에서 **Teams Teams** > **업그레이드 설정을** 선택합니다.
2. **공존** 모드 드롭다운 목록에서 **Teams 전용** 모드를 선택합니다.

## <a name="upgrade-users-in-stages"></a>단계별로 사용자 업그레이드

사용자를 TeamsOnly로 점진적으로 업그레이드하려면 다음 단계를 수행합니다.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>1단계: 업그레이드할 사용자 그룹 식별

종종 조직은 사용자의 성공 물결에서 조직을 업그레이드하도록 선택할 수 있습니다.  이러한 사용자를 먼저 식별하여 Microsoft Teams 관리 센터에서 쉽게 검색할 수 있습니다. 또는 PowerShell을 사용하여 이 작업을 보다 효율적으로 수행할 수 있습니다. 지정된 업그레이드 웨이브에 대한 사용자 집합을 확인한 후 나머지 단계를 계속 진행합니다.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>2단계: 현재 업그레이드 웨이브의 사용자에 대한 알림 설정(선택 사항)

Microsoft Teams 관리 센터를 사용하는 경우 한 번에 최대 20명의 사용자에 대해 TeamsUpgradePolicy를 구성할 수 있습니다.
1. Microsoft Teams 관리 센터에서 **사용자를** 선택하고 업그레이드해야 하는 최대 20명의 사용자에 대한 확인란을 찾아서 다중 선택합니다. 
2. listview의 왼쪽 위 모서리에서 **설정 편집** 을 선택합니다. 
3. 오른쪽의 **편집 설정** 창에서 **Teams 업그레이드** 에서 **비즈니스용 Skype 사용자에게 알리** 기 스위치를 켜기로 변경 **합니다**. 참고: 공존 모드의 값이 "조직 전체 설정 사용"인 경우 이 스위치가 표시되지 않으므로 먼저 이러한 사용자의 공존 모드를 조직의 기본값으로 명시적으로 설정해야 합니다.

또는 PowerShell을 사용하여 사용자 그룹에 대한 알림을 한 번에 사용하도록 설정하는 것이 더 쉬울 수 있습니다. 자세한 내용은 [Grant-CsTeamsUpgradePolicy를 참조하세요](/powershell/module/skype/grant-csteamsupgradepolicy).

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>3단계: 사용자의 공존 모드를 Teams 전용으로 설정

Teams를 유일한 애플리케이션으로 사용하도록 현재 웨이브의 사용자를 업그레이드할 준비가 되면 사용자의 공존 모드를 Teams 전용으로 설정합니다.

Microsoft Teams 관리 센터를 사용하는 경우 한 번에 최대 20명의 사용자에 대해 TeamsUpgradePolicy를 구성할 수 있습니다.
1. Microsoft Teams 관리 센터에서 **사용자를** 선택한 다음 최대 20명의 사용자에 대한 확인란을 선택합니다.
2. listview의 왼쪽 위 모서리에서 **설정 편집** 을 선택합니다.
3. 오른쪽의 **[편집] 설정** 창의 **Teams 업그레이드** 섹션에서 공존 모드를 드롭다운 목록에서 **Teams만** 으로 설정합니다.

또는 PowerShell을 사용하여 사용자 그룹을 한 번에 업그레이드하는 것이 더 쉬울 수 있습니다. 자세한 내용은 [Grant-CsTeamsUpgradePolicy를 참조하세요](/powershell/module/skype/grant-csteamsupgradepolicy).

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>4단계: 연속 사용자 웨이브에 대해 1-3단계 반복

Teams 전용 모드로 업그레이드하고 확장할 준비가 되면 이전 단계를 반복하여 TeamsOnly를 더 많은 사용자에게 적용합니다.  


## <a name="phone-system-and-pstn-connectivity-options"></a>전화 시스템 및 PSTN 연결 옵션

Teams를 사용한 전화 시스템은 사용자가 TeamsOnly 모드에 있는 후에 지원됩니다. (사용자가 아일랜드 모드인 경우 전화 시스템은 비즈니스용 Skype만 지원됩니다.)  

### <a name="pstn-connectivity-options"></a>PSTN 연결 옵션

PSTN(공중 전화망) 연결 옵션을 고려할 때 비즈니스용 Skype Online에서 TeamsOnly 모드로 이동할 때 두 가지 가능한 시나리오가 있습니다.

- Microsoft 통화 플랜을 사용하는 비즈니스용 Skype Online의 사용자입니다. 업그레이드 시 이 사용자는 계속해서 Microsoft 통화 계획을 갖습니다. 이 시나리오는 몇 단계만 필요한 가장 간단한 시나리오입니다. 자세한 내용은 [Microsoft 통화 플랜을 사용한 비즈니스용 Skype Online을 참조하세요](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).

- 비즈니스용 Skype 온-프레미스 또는 Cloud Connector Edition을 통해 온-프레미스 음성 기능을 사용하는 비즈니스용 Skype Online의 사용자입니다. Teams에 대한 사용자의 업그레이드는 TeamsOnly 사용자에게 PSTN 기능이 있는지 확인하기 위해 사용자를 직접 라우팅으로 마이그레이션하는 작업과 조정되어야 합니다.  자세한 내용은 [온-프레미스 음성이 있는 비즈니스용 Skype Online을 참조하세요](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).
