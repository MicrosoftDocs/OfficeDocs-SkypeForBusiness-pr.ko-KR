---
title: 비즈니스용 Skype Online에서 Microsoft Teams로 업그레이드
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 비즈니스용 Skype Online 배포에서 조직을 Microsoft Teams로 업그레이드하는 방법을 배워보는 것이 좋습니다.
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
ms.openlocfilehash: ca99c193a17547943018eba75004f0ec0a1a92f3
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578261"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>비즈니스용 Skype Online에서 Teams로 업그레이드

![배포 및 구현을 강조하는 업그레이드 여정 다이어그램](media/upgrade-banner-deployment.png "배포 및 구현 단계에 강조를 두는 업그레이드 단계")

이 문서는 업그레이드 여정의 배포 및 구현 단계의 일부입니다. 계속하기 전에 다음 활동을 완료해야 합니다.

- [프로젝트 관련자에 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)
- [비즈니스용 Skype 및 Teams의 공존 및 상호 연동성 이해](https://aka.ms/SkypeToTeams-Coexist)
- [업그레이드 여정 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [환경 준비](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [조직 준비](https://aka.ms/SkypeToTeams-UserReadiness)
- [파일럿 수행](https://aka.ms/SkypeToTeams-Pilot)

비즈니스용 Skype Online을 모두 배포하고 사용자를 비즈니스용 Skype에서 Teams로 업그레이드하려는 경우 이 문서의 지침을 따르하세요. 조직에서 선택한 업그레이드 여정에 따라 사용자에게 적절한 공존 및 업그레이드 모드를 할당하여 사용자를 선택적으로 또는 전체적으로 업그레이드할 수 있습니다.

> [!IMPORTANT]
> 비즈니스용 Skype Online은 2021년 7월 31일에 서비스가 종료되며 이후에는 더 이상 액세스할 수 없게 되거나 지원되지 않습니다. 혜택 구현을 극대화하고 조직이 업그레이드를 구현할 수 있는 적절한 시간을 확보하려면 지금 Microsoft Teams로의 여정을 시작하는 것이 권장됩니다. 성공적인 업그레이드는 기술 및 사용자 준비를 맞추기 때문에 Microsoft Teams로의 여정을 탐색할 때 여기에 설명된 지침을 활용해야 합니다.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>공존 및 업그레이드 모드 할당

Microsoft Teams 관리 센터 또는 비즈니스용 Skype 원격 액세스 세션을 사용하여 수행할 수 있는 TeamsUpgradePolicy의 UpgradeToTeams 인스턴스를 할당하여 사용자를 TeamsOnly 모드로 업그레이드할 Windows PowerShell 있습니다. 사용자별 또는 테넌트 전체를 한 단계로 업그레이드하려는 경우 테넌트 전체에서 이 작업을 할 수 있습니다. 

자세한 내용은 마이그레이션 [](https://aka.ms/SkypeToTeams-SetCoexistence) 및 공존 관리와 같은 공존 및 업그레이드 설정 및 [TeamsUpgradePolicy 설정을 참조하세요.](upgrade-to-teams-on-prem-tools.md)

## <a name="upgrade-all-users-to-teams-at-one-time"></a>모든 사용자를 Teams로 한 번 업그레이드

다음 단계에 따라 모든 사용자를 한 번씩 Teams로 업그레이드합니다.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>1단계: 사용자에게 변경 알림(선택 사항)

1. Microsoft Teams 관리 센터에서 Teams **업그레이드를** 전체  >  **설정으로 선택합니다.**
2. 공존 모드에서 Teams로 업그레이드할 수 있는 비즈니스용 Skype 사용자에게 **알림 설정으로**  **전환합니다.**

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>2단계: 조직의 TeamsOnly에 공존 모드 설정

1. Microsoft Teams 관리 센터에서 **전체 설정을 선택합니다.**
2. 공존 모드 **드롭다운** 목록에서 Teams 전용 모드를 선택합니다. 

## <a name="upgrade-users-in-stages"></a>단계적 사용자 업그레이드

사용자를 TeamsOnly로 점진적으로 업그레이드하려면 다음 단계를 수행합니다.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>1단계: 업그레이드할 사용자 그룹 식별

종종 조직은 사용자의 성공 웨이브에서 조직을 업그레이드할 수 있습니다.  Microsoft Teams 관리 센터에서 쉽게 검색할 수 있도록 이러한 사용자를 먼저 식별할 수 있습니다. 또는 PowerShell을 사용하여 이 작업을 보다 효율적으로 할 수 있습니다. 특정 업그레이드 웨이브에 대한 사용자 집합을 확인한 후 나머지 단계를 계속 진행합니다.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>2단계: 현재 업그레이드 웨이브의 사용자에 대한 알림 설정(선택 사항)

Microsoft Teams 관리 센터를 사용하는 경우 동시에 최대 20명까지 TeamsUpgradePolicy를 구성할 수 있습니다.
1. Microsoft Teams 관리 센터에서 사용자를 선택하고 업그레이드해야 하는 최대 20명에 대한 확인란을 찾아 다중 선택합니다. 
2. 목록 **보기의** 왼쪽 위 모서리에서 설정 편집을 선택합니다. 
3. 오른쪽의 설정 **편집 창에서** **Teams** 업그레이드 아래에서 비즈니스용 Skype 사용자 알림 **스위치를** 켜기로 **변경합니다.** 참고: 공존 모드의 값이 "전체 설정 사용"인 경우 이 스위치가 표시되지 않습니다. 따라서 먼저 이러한 사용자에 대한 공존 모드를 구성의 기본값으로 명시적으로 설정해야 합니다.

또는 PowerShell을 사용하여 사용자 그룹에 대한 알림을 한 번 더 쉽게 사용하도록 설정할 수 있습니다. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>3단계: 사용자를 Teams로만 공존 모드 설정

현재 웨이브의 사용자를 업그레이드하여 Teams를 유일한 응용 프로그램으로 사용할 준비가 된 경우 사용자의 공존 모드를 Teams로만 설정합니다.

Microsoft Teams 관리 센터를 사용하는 경우 동시에 최대 20명까지 TeamsUpgradePolicy를 구성할 수 있습니다.
1. Microsoft Teams 관리 센터에서 사용자를 선택한 다음 최대 20명까지 확인란을 선택합니다.
2. 목록 **보기의** 왼쪽 위 모서리에서 설정 편집을 선택합니다.
3. 오른쪽의  설정 편집 창의 **Teams** 업그레이드 섹션 아래 드롭다운 목록에서만 공존 모드를 **Teams로** 설정하세요.

또는 PowerShell을 사용하여 사용자 그룹을 한 번 더 쉽게 업그레이드할 수 있습니다. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>4단계: 연속적인 사용자 웨이브에 대해 1-3단계 반복

Teams 전용 모드로 업그레이드의 유효성을 검사하고 확장할 준비가 됐을 때 이전 단계를 반복하여 TeamsOnly를 더 많은 사용자에게 적용합니다.  


## <a name="phone-system-and-pstn-connectivity-options"></a>전화 시스템 및 PSTN 연결 옵션

Teams가 있는 전화 시스템은 사용자가 TeamsOnly 모드에 있는 후에 지원됩니다. 사용자가 제도 모드인 경우 전화 시스템은 비즈니스용 Skype에서만 지원됩니다.  

### <a name="pstn-connectivity-options"></a>PSTN 연결 옵션

PSTN(Public Switched Telephone Network) 연결 옵션을 고려할 때 비즈니스용 Skype Online에서 TeamsOnly 모드로 전환할 때 다음과 같은 두 가지 시나리오가 있습니다.

- Microsoft 통화 요금제가 있는 비즈니스용 Skype Online의 사용자입니다. 업그레이드 시 이 사용자는 계속해서 Microsoft 통화 요금제가 있습니다. 이 시나리오는 몇 단계만 필요한 가장 간단한 시나리오입니다. 자세한 내용은 [비즈니스용 Skype Online에서 Microsoft 통화 플랜을 참조하세요.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)

- 비즈니스용 Skype Online의 사용자는 비즈니스용 Skype-프레미스 또는 클라우드 커넥터 에디션을 통해 비즈니스용 Skype 음성 기능을 사용할 수 있습니다. Teams로의 사용자의 업그레이드는 TeamsOnly 사용자에게 PSTN 기능이 있도록 사용자를 직접 라우팅으로 마이그레이션하는 데 조정해야 합니다.  자세한 내용은 비즈니스용 Skype Online에서 주문형 음성을 [참조하세요.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)


