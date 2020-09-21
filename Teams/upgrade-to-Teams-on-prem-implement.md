---
title: 비즈니스용 Skype 온-프레미스 배포에서 팀으로 업그레이드-Microsoft 팀
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 Teams로 업그레이드
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8239d1fdbda10a61cd0846a0d56b1f1ffa62f597
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955905"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>비즈니스용 Skype에서 IT 관리자를 위한 팀으로 업그레이드 구현 &mdash;

이 문서에서는 업그레이드를 구현 하는 방법을 설명 합니다. 이 문서는 IT 관리자의 업그레이드 개념 및 구현에 대해 설명 하는 몇 째의 다섯 번째 항목입니다.  

- [개요](upgrade-to-teams-on-prem-overview.md)
- [업그레이드 방법](upgrade-to-teams-on-prem-upgrade-methods.md)
- [업그레이드 관리 도구](upgrade-to-teams-on-prem-tools.md)
- [비즈니스용 Skype 온-프레미스를 사용 하는 조직에 대 한 추가 고려 사항](upgrade-to-teams-on-prem-considerations.md)
- **업그레이드 구현** (이 문서)
- [PSTN (공개 통신 네트워크) 고려 사항](upgrade-to-teams-on-prem-pstn-considerations.md)

또한 다음 문서에서는 중요 한 업그레이드 개념 및 공존 동작에 대해 설명 합니다.

- [팀과 비즈니스용 Skype의 공존](upgrade-to-teams-on-prem-coexistence.md)
- [공존 모드-참조](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 클라이언트 환경 및 공존 모드 준수](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>업그레이드 옵션

이 섹션에서는 다음 업그레이드 옵션 중 하나를 사용 하 여 업그레이드를 구현 하는 방법을 설명 합니다.

- [겹치는 기능 업그레이드 (아일랜드 모드 사용)](#overlapping-capabilities-upgrade-using-islands-mode)
- [아직 팀 사용을 시작 하지 않은 조직에 대 한 선택 기능 업그레이드](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [이미 아일랜드 모드에서 팀을 사용 중인 조직에 대 한 선택 기능 업그레이드](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

옵션에 대 한 자세한 정보가 필요한 경우 [업그레이드 방법을](upgrade-to-teams-on-prem-upgrade-methods.md)이미 읽어 두세요.

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>겹치는 기능 업그레이드 (아일랜드 모드 사용)

겹치는 기능 업그레이드 옵션:

- 전체 조직에 대해 빠른 업그레이드를 수행할 수 있는 경우이 옵션을 고려 하세요.  최종 사용자가 두 클라이언트를 모두 실행 하는 데 혼란을 초래할 수 있으므로 사용자가 두 클라이언트를 모두 실행 해야 하는 기간을 최소화 하는 것이 가장 좋습니다. 사용자가 두 클라이언트를 모두 실행 한다는 것을 확인 해야 합니다.

- 이 옵션은 box 모델 이며 Microsoft 365 또는 Office 365 라이선스를 할당 하는 경우를 제외 하 고 팀을 시작 하는 데 관리자 작업이 필요 하지 않습니다. 사용자가 이미 비즈니스용 Skype Online을 사용 하 고 있는 경우이 모델에 이미 있을 수 있습니다.

- 접근 권한 모드를 종료 하 고 팀 전용으로 이동 하는 것은 어려울 수 있습니다. 업그레이드 된 사용자는 팀을 통해서만 통신 하기 때문에 해당 사용자와 통신 하는 조직의 다른 사용자는 팀을 사용 해야 합니다.  팀 사용을 시작 하지 않은 사용자가 있는 경우에는 누락 된 메시지에 노출 됩니다. 또한 비즈니스용 Skype에서 온라인 으로만 팀에 있는 사용자만 볼 수 있습니다. 일부 조직에서는이 문제를 방지 하기 위해 테 넌 트 전역 정책을 사용 하 여, 전체 사용자를 업그레이드할 준비가 될 때까지 대기 해야 하는 선행 계획을 수행 하도록 선택 합니다.


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>아직 팀 사용을 시작 하지 않은 조직에 대 한 선택 기능 업그레이드

조직에서 아직 팀에 활성 사용자가 없는 경우 첫 번째 단계는 TeamsUpgradePolicy에 대 한 기본 테 넌 트 전역 정책을 비즈니스용 Skype 모드 중 하나 (예: SfbWithTeamsCollab)로 설정 하는 것입니다.  팀 사용을 아직 시작 하지 않은 사용자는 동작의 차이를 볼 수 없습니다. 그러나 테 넌 트 수준에서이 정책을 설정 하면 사용자를 팀 전용 모드로 업그레이드 하 고 업그레이드 된 사용자가 업그레이드 되지 않은 사용자와 계속 통신할 수 있습니다.  파일럿 사용자를 식별 한 후에는이를 팀 전용으로 업그레이드할 수 있습니다.  온-프레미스 인 경우 CsUser Move를 사용 합니다. 온라인 상태인 경우에는 CsTeamsUpgradePolicy를 사용 하 여 팀 전용 모드를 할당 하면 됩니다. 기본적으로 이러한 사용자가 예약한 모든 비즈니스용 Skype 모임은 팀으로 마이그레이션됩니다.

다음은 주요 명령입니다.

1. 다음과 같이 테 넌 트 전체 기본값을 mode SfbWithTeamsCollab로 설정 합니다.

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. 다음과 같은 경우에만 파일럿 사용자를 TeamsOnly로 업그레이드 합니다.

   - 온라인 상태인 사용자의 경우:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - 온-프레미스 사용자의 경우:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

상속자
 
- 테 넌 트 전체 정책을 SfbWithTeamsCollab로 설정 하는 대신 SfbWithTeamsCollabAndMeetings로 설정할 수 있습니다. 이렇게 하면 모든 사용자가 팀의 모든 새 모임을 예약 합니다.
- `Move-CsUser` 온-프레미스 도구의 cmdlet입니다. 이 `MoveToTeams` 스위치를 사용 하려면 비즈니스용 Skype server 2019 또는 CU8 이상과 비즈니스용 Skype server 2015이 필요 합니다. 이전 버전을 사용 하는 경우 먼저 사용자를 비즈니스용 Skype Online으로 이동한 다음 해당 사용자에 게 팀의 유일한 모드를 부여할 수 있습니다.
- 기본적으로 비즈니스용 Skype 모임은 팀의 유일한 모드로 업그레이드 하거나 SfbWithTeamsCollabAndMeetings 모드를 할당할 때로 마이그레이션됩니다.  

아래 다이어그램은 이전에 팀을 사용 하지 않은 조직의 조직에 대 한 선택 기능 업그레이드의 구상 단계를 보여 줍니다. 막대의 높이는 사용자 수를 나타냅니다. 업그레이드 단계 중에는 모든 사용자가 서로 통신할 수 있습니다.  비즈니스용 Skype 사용자는 Interop를 사용 하는 사용자만 통신 하며 그 반대의 경우도 마찬가지입니다. 아일랜드 모드의 사용자는 두 클라이언트를 모두 실행 해야 합니다.

![팀을 이전에 사용 하지 않고 선택 기능을 표시 하는 다이어그램](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>이미 아일랜드 모드에서 팀을 사용 중인 조직에 대 한 선택 기능 업그레이드

조직의 일부 사용자가 아일랜드 모드에서 활발 하 게 팀을 사용 하 고 있는 경우 기존 사용자의 기능을 제거 하는 것이 원하지 않을 수 있습니다. 따라서 테 넌 트 전체 정책을 변경 하기 전에 추가 단계가 필요 합니다. 이 솔루션은 테 넌 트 전체 정책을 SfbWithTeamsCollab로 설정 하기 전에 이러한 기존 활성 팀 사용자를 아일랜드 모드로 "grandfather" 하는 것입니다.  이 작업을 완료 한 후에는 위에서 설명한 대로 배포를 진행할 수 있지만, 팀에서 활성 상태인 사용자는 아일랜드 모드에 있고 나머지 사용자는 SfbWithTeamsCollab 모드에 있는 두 그룹의 사용자가 있습니다. 이러한 사용자를 TeamsOnly 모드로 점진적으로 이동할 수 있습니다.

1. 다음과 같이 팀에서 활성 상태인 사용자를 찾습니다.

   1. Microsoft 365 관리 센터의 왼쪽 탐색 창에서 보고서로 이동한 다음 사용 현황을 클릭 합니다. 
   2. "보고서 선택" 드롭다운에서 Microsoft 팀, 사용자 활동을 차례로 선택 합니다. 팀에서 활성화 된 내보낼 수 있는 사용자 테이블을 제공 합니다. 
   3. 내보내기, Excel 열기, 필터링을 차례로 클릭 하 여 팀에서 활성 상태인 사용자만 표시 합니다.

2. 1 단계에서 찾은 각 활성 팀 사용자에 대해 원격 PowerShell에 아일랜드 모드를 할당 합니다. 이를 통해 다음 단계로 이동 하 여 사용자 환경을 변경 하지 않도록 할 수 있습니다.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. SfbWithTeamsCollab에 대해 테 넌 트 전체 정책을 설정 합니다.

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. 선택한 사용자를 TeamsOnly 모드로 업그레이드 합니다. 아일랜드 모드에서 사용자를 업그레이드 하 여 사용자가 아일랜드 모드일 때 발생할 수 있는 혼동을 최소화 하는 것이 좋지만,이 경우에는 아일랜드 모드 또는 SfbWithTeamsCollab 모드에서 사용자를 업그레이드할 수 있습니다.   

   비즈니스용 Skype Online에 속한 사용자의 경우:  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   비즈니스용 Skype Server 온-프레미스에 속한 사용자의 경우:  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

아래 다이어그램에서는 시작에 활성 제도 사용자가 있는 선택 기능 전환의 개념적인 단계를 보여 줍니다. 막대의 높이는 사용자 수를 나타냅니다. 업그레이드 단계 중에는 모든 사용자가 서로 통신할 수 있습니다.  비즈니스용 Skype 사용자는 interop를 사용 하는 사용자만 통신 하며 그 반대의 경우도 마찬가지입니다. 


![아일랜드 모드에서 활성 사용자와의 선택 기능 업그레이드를 보여 주는 다이어그램](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>관련 링크

[비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간 하이브리드 연결 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[부여-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS (모임 마이그레이션 서비스) 사용](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

