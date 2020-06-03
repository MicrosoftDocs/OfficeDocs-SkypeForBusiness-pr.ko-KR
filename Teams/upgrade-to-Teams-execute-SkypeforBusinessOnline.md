---
title: 비즈니스용 Skype Online을 Microsoft 팀으로 업그레이드 | 배치
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 비즈니스용 Skype Online deployement 통해 조직을 Microsoft 팀으로 업그레이드 하는 방법을 알아봅니다.
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
ms.openlocfilehash: 29dc02a88efe533f9a43a110c357203b87a890d6
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523171"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>비즈니스용 Skype Online에서 팀으로 업그레이드

![여행 다이어그램 업그레이드, 배포 및 구현 강조](media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점을 두어 업그레이드 여행 단계")

이 문서는 업그레이드 여행 배포 및 구현 단계의 일부입니다. 계속 하기 전에 다음 활동을 완료 했는지 확인 합니다.

- [프로젝트 이해 관계자 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)
- [비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해](https://aka.ms/SkypeToTeams-Coexist)
- [업그레이드 여행 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [환경 준비](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [조직 준비](https://aka.ms/SkypeToTeams-UserReadiness)
- [파일럿 수행](https://aka.ms/SkypeToTeams-Pilot)

Skype for business Online을 완전히 구축한 경우 비즈니스용 Skype에서 팀으로 사용자를 업그레이드 하려면이 문서의 지침을 따르세요. 사용자에 게 적절 한 공존 및 업그레이드 모드를 지정 하 여 조직에서 선택한 업그레이드 여행에 따라 사용자를 선택적으로 또는 모두 in으로 업그레이드할 수 있습니다.

> [!IMPORTANT]
> 비즈니스용 Skype Online은 2021년 7월 31일에 서비스가 종료되며 이후에는 더 이상 액세스할 수 없게 되거나 지원되지 않습니다. 조직의 혜택 실현을 최대화 하 고 업그레이드를 구현 하는 데 적절 한 시간을 확보 하려면 지금 Microsoft 팀으로 여행을 시작 하는 것이 좋습니다. 성공적으로 업그레이드 하면 기술 및 사용자의 준비가 정렬 되므로 Microsoft 팀으로 여행을 이동할 때이 가이드의 지침을 활용 해야 합니다.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>공존 및 업그레이드 모드 지정

Microsoft 팀 관리 센터 또는 비즈니스용 Skype 원격 Windows Powershell 세션을 사용 하 여 수행할 수 있는 TeamsUpgradePolicy의 UpgradeToTeams 인스턴스를 할당 하 여 사용자를 TeamsOnly 모드로 업그레이드할 수 있습니다. 이 작업은 사용자별로 수행 하거나 전체 테 넌 트를 한 번에 업그레이드 하려는 경우 테 넌 트를 기준으로 할 수 있습니다. 

자세한 내용은 [공존 및 업그레이드 설정](https://aka.ms/SkypeToTeams-SetCoexistence) 및 TeamsUpgradePolicy 설정 ( [마이그레이션 및 공존 관리](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence))을 참조 하세요.

## <a name="upgrade-all-users-to-teams-at-one-time"></a>한 번에 모든 사용자를 팀으로 업그레이드

모든 사용자를 한 번에 팀으로 업그레이드 하려면 다음 단계를 따르세요.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>1 단계: 사용자에 게 변경 내용 알리기 (선택 사항)

1. Microsoft 팀 관리 센터에서 **조직 전체 설정**  >  **팀 업그레이드**를 선택 합니다.
2. **공존 모드**에서 **비즈니스용 Skype 사용자에 게 업그레이드를 사용할 수 있는 사람에 게 알림** ( **On**으로 전환)을 변경 합니다.

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>2 단계: 조직에 대해서만 공존 모드를 TeamsOnly로 설정

1. Microsoft 팀 관리 센터에서 **조직 전체 설정을**선택 합니다.
2. **공존 모드** 드롭다운 목록에서 **팀 전용** 모드를 선택 합니다.

## <a name="upgrade-users-in-stages"></a>단계에서 사용자 업그레이드

사용자를 팀 전용으로 점진적으로 업그레이드 하려는 경우 다음 단계를 따르세요.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>1 단계: 업그레이드할 사용자 그룹 식별

조직에서 사용자의 성공으로 조직에 대 한 업그레이드를 선택 하는 경우가 있습니다.  Microsoft 팀 관리 센터에서 이러한 사용자를 쉽게 검색할 수 있도록 먼저 해당 사용자를 식별 하는 것이 좋습니다. 또는 PowerShell을 사용 하 여 더 효율적으로 수행할 수도 있습니다. 지정 된 업그레이드 웨이브에 대 한 사용자 집합을 식별 한 후 나머지 단계를 계속 진행 합니다.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>2 단계: 현재 업그레이드 웨이브의 사용자에 대 한 알림 설정 (선택 사항)

Microsoft 팀 관리 센터를 사용 하는 경우 한 번에 최대 20 명의 사용자에 대해 TeamsUpgradePolicy을 구성할 수 있습니다.
1. Microsoft 팀 관리 센터에서 **사용자**를 선택 하 고, 업그레이드 해야 하는 최대 20 명의 사용자에 대 한 확인란을 선택 하 고 확인 합니다. 
2. Listview의 왼쪽 위 모서리에서 **설정 편집** 을 선택 합니다. 
3. 오른쪽의 **설정 편집** 창에서 **팀 업그레이드**아래에서 **비즈니스용 Skype 사용자 전환 알림을** **설정**으로 변경 합니다. 참고: 공존 모드의 값이 "조직 전체 설정 사용" 인 경우에는이 스위치가 표시 되지 않으므로 먼저 해당 사용자의 공존 모드를 조직에 대 한 기본값에 대 한 기본 값으로 명시적으로 설정 해야 합니다.

또는 사용자 그룹에 대해 PowerShell을 사용 하 여 한 번에 알림을 사용 하는 것이 더 쉬울 수 있습니다. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>3 단계: 사용자에 대 한 공존 모드를 팀에만 설정

팀을 유일한 응용 프로그램으로 사용 하도록 현재 웨이브의 사용자를 업그레이드할 준비가 되었으면 사용자의 공존 모드를 팀 전용으로 설정 합니다.

Microsoft 팀 관리 센터를 사용 하는 경우 한 번에 최대 20 명의 사용자에 대해 TeamsUpgradePolicy을 구성할 수 있습니다.
1. Microsoft 팀 관리 센터에서 **사용자**를 선택한 다음 최대 20 명의 사용자에 대 한 확인란을 선택 합니다.
2. Listview의 왼쪽 위 모서리에서 **설정 편집** 을 선택 합니다.
3. 오른쪽의 **설정 편집** 창에서 **팀 업그레이드** 섹션의 드롭다운 목록에 있는 **팀에만** 공존 모드를 설정 합니다.

또는 PowerShell을 사용 하 여 한 번에 사용자 그룹을 업그레이드 하는 것이 더 쉬울 수 있습니다. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>4 단계: 후속 사용자를 위해 1-3 단계를 반복 합니다.

팀 전용 모드로의 업그레이드를 확인 하 고 확장할 준비가 되 면 이전 단계를 반복 하 여 다른 사용자 에게만 팀을 적용 합니다.  


## <a name="phone-system-and-teams-upgrade"></a>전화 시스템 및 팀 업그레이드

비즈니스용 Skype Online 배포에 전화 요금제가 포함 되어 있고 Microsoft가 공공 교환 통신망 (PSTN) 인 경우 팀으로의 사용자 업그레이드는 자동으로 인바운드 PSTN 통화를 팀으로 전환 합니다.

비즈니스용 Skype Online 배포에 클라우드 커넥터 버전이 있는 전화 시스템이 포함 된 경우 [전화 시스템 다이렉트 라우팅에 대 한 추가 고려 사항을](2-envision-make-my-service-decisions-direct-routing.md)참조 하세요.
