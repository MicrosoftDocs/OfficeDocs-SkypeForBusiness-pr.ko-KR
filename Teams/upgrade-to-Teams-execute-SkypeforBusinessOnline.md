---
title: 온라인에서 비즈니스용 Skype 온라인에서 Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 조직을 온라인 배포에서 Microsoft Teams 업그레이드하는 비즈니스용 Skype 설명합니다.
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
ms.openlocfilehash: 8bb2924dfe6bab5afedda2b02b1027de057c9e86
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733937"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>온라인에서 비즈니스용 Skype 업그레이드합니다Teams

![배포 및 구현을 강조하는 업그레이드 여정 다이어그램입니다.](media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점 있는 업그레이드 여정의 단계")

이 문서는 업그레이드 단계의 배포 및 구현 단계의 일부입니다. 계속하기 전에 다음 작업을 완료한지 확인합니다.

- [프로젝트 관계자 인리스트](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](./upgrade-define-project-scope.md)
- [비즈니스용 Skype 및 상호운용성을 Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [업그레이드 여정을 선택했습니다.](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [환경 준비](./upgrade-prepare-environment.md)
- [조직 준비](./upgrade-prepare-organization.md)
- [파일럿 수행](./pilot-essentials.md)

온라인에서 전체적으로 배포한 비즈니스용 Skype 사용자 업그레이드를 원하는 경우 이 문서의 지침을 비즈니스용 Skype Teams. 조직에서 선택한 업그레이드 여정에 따라 사용자에게 적절한 공존 및 업그레이드 모드를 할당하여 사용자를 선택적으로 또는 올인할 수 있습니다.

> [!IMPORTANT]
> 비즈니스용 Skype Online은 2021년 7월 31일에 서비스가 종료되며 이후에는 더 이상 액세스할 수 없게 되거나 지원되지 않습니다. 혜택 현실화를 최대화하고 조직에서 업그레이드를 구현할 적절한 시간을 확보하기 위해 현재 업그레이드를 위한 여정을 Microsoft Teams 권장됩니다. 성공적인 업그레이드는 기술 및 사용자 준비를 일치시 하도록 설정하기 때문에 다음 지침을 활용하여 업그레이드를 진행하는 Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>공존 및 업그레이드 모드 할당

TeamsUpgradePolicy의 UpgradeToTeams 인스턴스를 할당하여 사용자를 TeamsOnly 모드로 업그레이드할 수 있습니다. 이 인스턴스는 Microsoft Teams 관리 센터 또는 원격 비즈니스용 Skype Windows PowerShell 있습니다. 한 단계로 전체 테넌트를 업그레이드하려는 경우 사용자당 또는 테넌트 전체에서 이 작업을 할 수 있습니다. 

자세한 내용은 [공존](./setting-your-coexistence-and-upgrade-settings.md) 및 업그레이드 설정 및 [TeamsUpgradePolicy:](upgrade-to-teams-on-prem-tools.md)마이그레이션 및 공존 관리 를 참조하세요.

## <a name="upgrade-all-users-to-teams-at-one-time"></a>모든 사용자를 한 Teams 업그레이드

다음 단계를 수행하여 모든 사용자를 한 Teams 업그레이드합니다.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>1단계: 변경 내용을 사용자에게 알릴 수 있습니다(선택 사항)

1. Microsoft Teams 관리 센터에서 업그레이드 에서 **org-wide**  >  **Teams 선택합니다.**
2. **공존** 모드 아래에서 비즈니스용 Skype 업그레이드가 켜지도록 Teams 사용자에게 알림 **을 으로** **변경합니다.**

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>2단계: 조직에 대해 TeamsOnly에 공존 모드 설정

1. Microsoft Teams 관리 센터에서 **Org-wide 설정을 선택합니다.**
2. 공존 **Teams** 드롭다운 목록에서 전용 모드를 선택합니다. 

## <a name="upgrade-users-in-stages"></a>단계적 사용자 업그레이드

사용자를 TeamsOnly로 점진적으로 업그레이드하려는 경우 다음 단계를 따릅니다.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>1단계: 업그레이드할 사용자 그룹 식별

종종 조직은 사용자의 성공을 위해 조직을 업그레이드할 수 있습니다.  관리 센터에서 쉽게 검색할 수 있도록 먼저 이러한 사용자를 Microsoft Teams 합니다. 또는 PowerShell을 사용하여 이 작업을 보다 효율적으로 할 수 있습니다. 특정 업그레이드 웨이브에 대한 사용자 집합을 확인한 후 나머지 단계를 계속 진행합니다.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>2단계: 현재 업그레이드 웨이브의 사용자에 대한 알림 설정(선택 사항)

관리 센터를 Microsoft Teams 경우 최대 20명까지 한 번씩 TeamsUpgradePolicy를 구성할 수 있습니다.
1. Microsoft Teams 관리 센터에서 사용자 **및** 를 선택하고 업그레이드해야 하는 최대 20명에 대한 확인란을 찾아 다중으로 선택합니다. 
2. 목록 **보기의** 왼쪽 위 모서리에서 설정 편집을 선택합니다. 
3. 오른쪽의  설정 편집 창에서 업그레이드 Teams **에서**  사용자 비즈니스용 Skype 으로 **변경합니다.** 참고: 공존 모드 값이 "Org-wide 설정 사용"인 경우 이 스위치가 표시되지 않습니다. 따라서 먼저 이러한 사용자에 대한 공존 모드를 기본적으로 설정해야 합니다.

또는 PowerShell을 사용하여 한 번씩 사용자 그룹에 대한 알림을 사용하도록 설정하는 것이 더 쉬워집니다. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>3단계: 사용자만 사용할 수 있도록 공존 모드 Teams 설정

현재 웨이브에서 사용자를 유일한 애플리케이션으로 사용할 수 있도록 Teams 경우 사용자에 대한 공존 모드를 Teams만 설정합니다.

관리 센터를 Microsoft Teams 경우 최대 20명까지 한 번씩 TeamsUpgradePolicy를 구성할 수 있습니다.
1. 관리 Microsoft Teams 관리 센터에서 사용자를 선택한 다음 최대 20명에 대한 확인란을 선택합니다.
2. 목록 **보기의** 왼쪽 위 모서리에서 설정 편집을 선택합니다.
3. 오른쪽의  설정 편집 창에서 업그레이드  Teams 섹션에서 공존 모드를 드롭다운 **목록에서만** Teams 설정합니다.

또는 PowerShell을 사용하여 한 번씩 사용자 그룹을 업그레이드하는 것이 더 쉬워집니다. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>4단계: 연속된 사용자 파동에 대해 1-3단계 반복

전용 모드로 Teams 업그레이드의 유효성을 검사하고 확장할 준비가 되면 이전 단계를 반복하여 TeamsOnly를 더 많은 사용자에게 적용합니다.  


## <a name="phone-system-and-pstn-connectivity-options"></a>전화 시스템 및 PSTN 연결 옵션

전화 시스템 Teams TeamsOnly 모드에 있는 후에 지원됩니다. (사용자가 제도 모드인 경우 전화 시스템 지원되는 비즈니스용 Skype.)  

### <a name="pstn-connectivity-options"></a>PSTN 연결 옵션

PSTN(공용 전환 전화 네트워크) 연결 옵션을 고려할 때 온라인에서 TeamsOnly 모드로 이동하는 비즈니스용 Skype 가능한 두 가지 시나리오가 있습니다.

- Microsoft 통화 비즈니스용 Skype 있는 온라인 사용자입니다. 업그레이드 시 이 사용자는 Microsoft 통화 계획을 계속 하게 됩니다. 이 시나리오는 몇 단계만 요구하는 가장 간단한 시나리오입니다. 자세한 내용은 Microsoft 호출 [비즈니스용 Skype 온라인에서 를 참조하세요.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)

- 프레미스 비즈니스용 Skype Cloud Connector Edition을 통해 비즈니스용 Skype 음성 기능이 있는 온라인 사용자입니다. 사용자의 업그레이드를 Teams 직접 라우팅으로의 마이그레이션과 조정해야 TeamsOnly 사용자에게 PSTN 기능이 있습니다.  자세한 내용은 온라인에서 비즈니스용 Skype [음성을 참조하세요.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)