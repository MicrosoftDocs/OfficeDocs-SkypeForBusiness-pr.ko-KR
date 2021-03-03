---
title: IT 관리자를 위한 업그레이드 전략
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 이 문서는 IT 관리자를 위한 것이고 비즈니스용 Skype에서 Teams로 업그레이드를 구현하기 위한 전략을 설명합니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb884f26862466dcd70c9efe81e5293d277adbde
ms.sourcegitcommit: b0753baa55841a2c6c5dc006dcdd117704af3b42
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2021
ms.locfileid: "50401349"
---
# <a name="upgrade-strategies-for-it-administrators"></a>IT 관리자를 위한 업그레이드 전략

![배포 및 구현 단계에 주안점 있는 업그레이드 여정의 단계](media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점 있는 업그레이드 여정의 단계")

이 문서는 비즈니스용 Skype에서 Teams로 업그레이드를 구현하려는 IT 관리자를 위한 문서입니다.

업그레이드를 구현하기 전에 중요한 업그레이드 개념 및 공존 동작을 설명하는 다음 문서를 추천합니다.

- [Microsoft Teams 및 비즈니스용 Skype 공존 및 상호 연동성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [공존 모드 - 참조](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 클라이언트 환경 및 공존 모드 준수](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>업그레이드 옵션

이 섹션에서는 다음 업그레이드 옵션 중 하나를 사용하여 업그레이드를 구현하는 방법을 설명합니다.

- [겹치는 기능 업그레이드(제도 모드 사용)](#overlapping-capabilities-upgrade-using-islands-mode)
- [Teams 사용을 아직 시작하지 않은 조직의 선택 기능 업그레이드](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [제도 모드에서 Teams를 이미 사용하고 있는 조직의 선택 기능 업그레이드](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

옵션에 대한 자세한 정보가 필요한 경우 비즈니스용 [Skype에서 Teams로](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)업그레이드 여정 선택을 이미 읽은지 확인하세요.

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>겹치는 기능 업그레이드(제도 모드 사용)

겹치는 기능 업그레이드 옵션의 경우:

- 전체 조직에 대해 빠른 업그레이드를 할 수 있는 경우 이 옵션을 고려하세요.  두 클라이언트를 모두 실행하는 최종 사용자에게 혼동이 발생할 수 있는 위험이 있는 경우 두 클라이언트를 모두 실행해야 하는 기간을 최소화할 수 있는 것이 가장 최선입니다. 사용자가 두 클라이언트를 모두 실행하도록 해야 합니다.

- 이 옵션은 바로 사용할 수 있는 모델로, Microsoft 365 또는 Office 365 라이선스를 할당하는 것 외에 Teams를 시작하는 관리자 작업이 필요하지 않습니다. 사용자에게 비즈니스용 Skype Online이 이미 있는 경우 이 모델에 이미 있을 수 있습니다.

- 겹치는 기능 모드에서 겹치고 TeamsOnly로 이동하는 것이 어려울 수 있습니다. 업그레이드된 사용자는 Teams를 통해서만 통신하기 때문에 해당 사용자와 통신하는 조직의 다른 사용자는 Teams를 사용해야 합니다.  Teams를 사용하지 않은 사용자가 있는 경우 누락된 메시지에 노출됩니다. 또한 비즈니스용 Skype에서 TeamsOnly 사용자가 온라인으로 표시되지 않습니다. 일부 조직에서는 이를 방지하기 위해 테넌트 전역 정책을 사용하여 테넌트 전체 업그레이드를 수행하기로 하지만, 모든 사용자가 업그레이드할 준비가 될 때까지 기다리는 것뿐만 아니라 선행 계획이 필요합니다.


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Teams 사용을 아직 시작하지 않은 조직의 선택 기능 업그레이드

조직에 아직 Teams에 활성 사용자가 없는 경우 첫 번째 단계는 TeamsUpgradePolicy에 대한 기본 테넌트 전체 정책을 비즈니스용 Skype 모드 중 하나(예: SfbWithTeamsCollab)로 설정하는 것입니다.  Teams 사용을 아직 시작하지 않은 사용자는 동작의 차이를 알 수 없습니다. 그러나 테넌트 수준에서 이 정책을 설정하면 사용자를 TeamsOnly 모드로 업그레이드할 수 있으며 업그레이드된 사용자가 업그레이드되지 않은 사용자와 계속 통신할 수 있습니다.  파일럿 사용자를 확인한 후 TeamsOnly로 업그레이드할 수 있습니다.  이러한 사용자가 On-Premises인 경우 Move-CsUser를 사용 합니다. 온라인이면 Grant-CsTeamsUpgradePolicy를 사용하여 TeamsOnly 모드를 할당하기만 합니다. 기본적으로 이러한 사용자가 예약한 비즈니스용 Skype 모임은 Teams로 마이그레이션됩니다.

주요 명령은 다음과 같습니다.

1. 다음과 같이 테넌트 전체 기본값을 모드 SfbWithTeamsCollab으로 설정합니다.

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. 다음과 같이 파일럿 사용자를 TeamsOnly로 업그레이드합니다.

   - 온라인인 사용자의 경우:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - 프레미스에 있는 사용자의 경우:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

참고
 
- 테넌트 전체 정책을 SfbWithTeamsCollab으로 설정하는 대신 SfbWithTeamsCollabAndMeetings로 설정할 수 있습니다. 이렇게 하면 모든 사용자가 Teams에서 모든 새 모임을 예약할 수 있습니다.
- `Move-CsUser` 는 는 프레미스 도구의 cmdlet입니다. 스위치에는 `MoveToTeams` 비즈니스용 Skype Server 2019 또는 CU8 이상이 있는 비즈니스용 Skype Server 2015가 필요합니다. 이전 버전을 사용하는 경우 먼저 사용자를 비즈니스용 Skype Online으로 이동한 다음 TeamsOnly 모드를 해당 사용자에게 부여할 수 있습니다.
- 기본적으로 비즈니스용 Skype 모임은 TeamsOnly 모드로 업그레이드하거나 SfbWithTeamsCollabAndMeetings 모드를 할당할 때 Teams로 마이그레이션됩니다.  

아래 다이어그램에서는 Teams를 사전 사용하지 아니한 조직에 대한 선택 기능 업그레이드의 개념 단계를 보여 줍니다. 막대의 높이는 사용자 수를 나타 내는 것입니다. 업그레이드의 모든 단계에서 모든 사용자가 서로 통신할 수 있습니다.  비즈니스용 Skype 사용자는 Interop을 사용하여 TeamsOnly 사용자와 통신하고 그 반대의 경우도 마찬가지입니다. 아일랜드 모드의 사용자는 두 클라이언트를 모두 실행해야 합니다.

![Teams를 사용하지 않습니다. 선택 기능 업그레이드를 보여주는 다이어그램](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>제도 모드에서 Teams를 이미 사용하고 있는 조직의 선택 기능 업그레이드

조직의 일부 사용자가 제도 모드에서 Teams를 적극적으로 사용하는 경우 기존 사용자에서 기능을 제거하지 않을 수 있습니다. 따라서 테넌트 전체 정책을 변경하기 전에 추가 단계가 필요합니다. 이 솔루션은 테넌트 전체 정책을 SfbWithTeamsCollab으로 설정하기 전에 이러한 기존 활성 Teams 사용자를 제도 모드로 "할아버지"하는 것입니다.  이 경우 위에서와 같은 배포를 진행할 수 있습니다. 그러나 TeamsOnly로 이동하는 두 개의 사용자 그룹이 있습니다. Teams에서 활성 상태인 사용자는 제도 모드이고 나머지 사용자는 SfbWithTeamsCollab 모드에 있습니다. 이러한 사용자를 TeamsOnly 모드로 점진적으로 이동할 수 있습니다.

1. Teams에서 활성 상태인 사용자를 다음과 같이 찾을 수 있습니다.

   1. Microsoft 365 관리 센터의 왼쪽 탐색에서 보고서로 이동한 다음 사용량으로 이동합니다. 
   2. "보고서 선택" 드롭다운에서 Microsoft Teams를 선택한 다음 사용자 활동을 선택합니다. 이렇게 하면 Teams에서 활성 상태인 사용자의 내보낼 수 있는 테이블이 표시됩니다. 
   3. 내보내기, Excel 열기 및 필터를 클릭하여 Teams에서 활성 상태인 사용자만 표시합니다.

2. 1단계에 있는 각 활성 Teams 사용자에 대해 원격 PowerShell에서 섬 모드를 할당합니다. 이렇게 하면 다음 단계로 이동하여 사용자 환경을 변경하지 않도록 할 수 있습니다.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. 테넌트 전체 정책을 SfbWithTeamsCollab으로 설정합니다.

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. 선택한 사용자를 TeamsOnly 모드로 업그레이드합니다. 아일랜드 모드 또는 SfbWithTeamsCollab 모드에서 사용자를 업그레이드하도록 선택할 수 있습니다. 먼저 아일랜드 모드에서 사용자를 업그레이드하는 우선 순위를 지정하여 사용자가 섬 모드에 있을 때 발생할 수 있는 혼동 가능성을 최소화할 수 있습니다.   

   비즈니스용 Skype Online에 있는 사용자의 경우:  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   비즈니스용 Skype Server에 홈을 프레미스에 있는 사용자의 경우:  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

아래 다이어그램에서는 시작 시 활성 Islands 사용자가 있는 선택 기능 전환의 개념 단계를 보여줍니다. 막대의 높이는 사용자 수를 나타 내는 것입니다. 업그레이드의 모든 단계에서 모든 사용자가 서로 통신할 수 있습니다.  비즈니스용 Skype 사용자는 Interop을 사용하여 TeamsOnly 사용자와 통신하고 그 반대의 경우도 마찬가지입니다. 


![아일랜드 모드에서 활성 사용자와 함께 선택한 기능 업그레이드를 보여주는 다이어그램](media/teams-upgrade-2.png)

   



## <a name="related-links"></a>관련 링크

[비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 연동성 지침](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간에 하이브리드 연결 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS(모임 마이그레이션 서비스) 사용](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

