---
title: IT 관리자를 위한 업그레이드 전략
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 이 문서는 IT 관리자를 위한 것이며 비즈니스용 Skype Teams 업그레이드를 구현하기 위한 전략을 설명합니다.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f403b12ffc8cabbfebe8a30268eb3e6dad468f32
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681739"
---
# <a name="upgrade-strategies-for-it-administrators"></a>IT 관리자를 위한 업그레이드 전략

![배포 및 구현 단계에 중점을 둔 업그레이드 과정의 단계입니다.](media/upgrade-banner-deployment.png "배포 및 구현 단계에 중점을 둔 업그레이드 과정의 단계")

이 문서는 비즈니스용 Skype Teams 업그레이드를 구현하려는 IT 관리자를 위한 것입니다.

업그레이드를 구현하기 전에 중요한 업그레이드 개념 및 공존 동작을 설명하는 다음 문서를 사용하는 것이 좋습니다.

- [Microsoft Teams 및 비즈니스용 Skype 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [공존 모드 - 참조](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 클라이언트 환경 및 공존 모드 준수](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a>업그레이드 옵션

이 섹션에서는 다음 업그레이드 옵션 중 하나를 사용하여 업그레이드를 구현하는 방법을 설명합니다.

- [겹치는 기능 업그레이드(아일랜드 모드 사용)](#overlapping-capabilities-upgrade-using-islands-mode)
- [아직 Teams 사용을 시작하지 않은 조직의 선택 기능 업그레이드](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [아일랜드 모드에서 이미 Teams 사용하고 있는 조직의 선택 기능 업그레이드](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

옵션에 대한 자세한 정보가 필요한 경우 [비즈니스용 Skype Teams 업그레이드 경험 선택을](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) 이미 읽었는지 확인합니다.

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>겹치는 기능 업그레이드(아일랜드 모드 사용)

겹치는 기능 업그레이드 옵션의 경우:

- 전체 조직에 대해 빠른 업그레이드를 수행할 수 있는 경우 이 옵션을 고려하세요.  두 클라이언트를 모두 실행하는 최종 사용자에게 혼동이 발생할 수 있으므로 사용자가 두 클라이언트를 모두 실행해야 하는 기간을 최소화할 수 있는 것이 가장 좋습니다. 사용자가 두 클라이언트를 모두 실행하는 것을 알고 있어야 합니다.

- 이 옵션은 기본 모델이며, Microsoft 365 또는 Office 365 라이선스를 할당하는 것 외에는 관리자 작업이 Teams 시작할 필요가 없습니다. 사용자가 이미 비즈니스용 Skype Online이 있는 경우 이미 이 모델에 있을 수 있습니다.

- 겹치는 기능 모드에서 벗어나 TeamsOnly로 전환하는 것은 어려울 수 있습니다. 업그레이드된 사용자는 Teams 통해서만 통신하므로 해당 사용자와 통신하는 조직의 다른 사용자는 Teams 사용해야 합니다.  Teams 사용하기 시작하지 않은 사용자가 있는 경우 누락된 메시지에 노출됩니다. 또한 비즈니스용 Skype TeamsOnly 사용자가 온라인으로 표시되지 않습니다. 일부 조직에서는 이를 방지하기 위해 테넌트 전역 정책을 사용하여 테넌트 전체 업그레이드를 수행하도록 선택하지만, 모든 사용자를 업그레이드할 준비가 될 때까지 미리 계획하고 대기해야 합니다.

## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>아직 Teams 사용을 시작하지 않은 조직의 선택 기능 업그레이드

조직에 아직 Teams 활성 사용자가 없는 경우 첫 번째 단계는 TeamsUpgradePolicy에 대한 기본 테넌트 차원 정책을 비즈니스용 Skype 모드(예: SfbWithTeamsCollab) 중 하나로 설정하는 것입니다.  아직 Teams 사용을 시작하지 않은 사용자는 동작의 차이를 알 수 없습니다. 그러나 테넌트 수준에서 이 정책을 설정하면 사용자를 TeamsOnly 모드로 업그레이드할 수 있으며 업그레이드된 사용자가 업그레이드되지 않은 사용자와 계속 통신할 수 있습니다.  파일럿 사용자를 확인한 후에는 TeamsOnly로 업그레이드할 수 있습니다.  온-프레미스인 경우 Move-CsUser를 사용합니다. 온라인 상태인 경우 Grant-CsTeamsUpgradePolicy를 사용하여 TeamsOnly 모드를 할당하기만 하면 됩니다. 기본적으로 이러한 사용자가 예약한 모든 비즈니스용 Skype 모임은 Teams 마이그레이션됩니다.

다음은 주요 명령입니다.

1. 다음과 같이 테넌트 전체 기본값을 모드 SfbWithTeamsCollab으로 설정합니다.

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. 다음과 같이 파일럿 사용자를 TeamsOnly로 업그레이드합니다.

   - 온라인 사용자:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username
     ```

   - 온-프레미스 사용자:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
     ```

**참고**:

- 테넌트 전체 정책을 SfbWithTeamsCollab으로 설정하는 대신 SfbWithTeamsCollabAndMeetings로 설정할 수 있습니다. 이렇게 하면 모든 사용자가 Teams 모든 새 모임을 예약할 수 있습니다.
- 기본적으로 비즈니스용 Skype 모임은 TeamsOnly 모드로 업그레이드하거나 SfbWithTeamsCollabAndMeetings 모드를 할당할 때 Teams 마이그레이션됩니다.

> [!NOTE]
> 비즈니스용 Skype Online의 향후 사용 중지를 준비하기 위해 Microsoft는 조직이 Teams 이동하는 방식을 간소화했습니다. 사용자를 온-프레미스에서 `Move-CsUser` TeamsOnly로 직접 이동하기 위해 스위치를 더 이상 지정할 `-MoveToTeams` 필요가 없습니다. 이전에는 이 스위치를 지정하지 않은 경우 사용자가 비즈니스용 Skype 서버 온-프레미스에서 비즈니스용 Skype Online으로 전환되었으며 해당 모드는 변경되지 않은 상태로 유지되었습니다. 이제 사용자를 온-프레미스에서 클라우드로 `Move-CsUser`이동할 때 자동으로 TeamsOnly 모드가 할당되고 온-프레미스에서의 모임은 스위치가 실제로 지정되었는지 여부에 관계없이 자동으로 Teams 모임으로 `-MoveToTeams switch had been specified`변환됩니다. 이 동작은 비즈니스용 Skype 및 Lync Server 2013의 모든 버전에서 사용할 수 있습니다(지원`-MoveToTeams`되지 않은 경우).

아래 다이어그램은 이전에 Teams 사용하지 않는 조직에 대한 선택 기능 업그레이드의 개념적 단계를 보여 줍니다. 막대의 높이는 사용자 수를 나타냅니다. 업그레이드 단계에서는 모든 사용자가 서로 통신할 수 있습니다.  비즈니스용 Skype 사용자는 Interop을 사용하여 TeamsOnly 사용자와 통신하고 그 반대의 경우도 마찬가지입니다. 아일랜드 모드의 사용자는 두 클라이언트를 모두 실행해야 합니다.

![Teams 이전에 사용하지 않고 선택 기능 업그레이드를 보여 주는 다이어그램](media/teams-upgrade-1.png)

## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>아일랜드 모드에서 이미 Teams 사용하고 있는 조직의 선택 기능 업그레이드

조직의 일부 사용자가 아일랜드 모드에서 Teams 적극적으로 사용하는 경우 기존 사용자로부터 기능을 제거하지 않으려는 것일 수 있습니다. 따라서 테넌트 전체 정책을 변경하기 전에 추가 단계가 필요합니다. 솔루션은 테넌트 차원의 정책을 SfbWithTeamsCollab으로 설정하기 전에 이러한 기존 활성 Teams 사용자를 아일랜드 모드로 "할아버지"하는 것입니다.  이렇게 하면 위와 같이 배포를 진행할 수 있지만 TeamsOnly로 이동하는 두 명의 사용자 그룹이 있습니다. Teams 활성 상태였던 사용자는 아일랜드 모드에 있고 나머지 사용자는 SfbWithTeamsCollab 모드에 있게 됩니다. 이러한 사용자를 TeamsOnly 모드로 점진적으로 이동할 수 있습니다.

1. 다음과 같이 Teams 활성 상태인 사용자를 찾습니다.

   1. Microsoft 365 관리 센터 왼쪽 탐색 영역에서 보고서로 이동한 다음 사용량으로 이동합니다.
   2. "보고서 선택" 드롭다운에서 Microsoft Teams 선택한 다음 사용자 활동을 선택합니다. 그러면 Teams 활성화된 사용자의 내보낼 수 있는 테이블이 표시됩니다.
   3. 내보내기를 클릭하고 Excel 열고 필터링하여 Teams 활성 상태인 사용자만 표시합니다.

2. 1단계에서 찾은 각 활성 Teams 사용자에 대해 원격 PowerShell에서 아일랜드 모드를 할당합니다. 이렇게 하면 다음 단계로 이동하여 사용자 환경을 변경하지 않도록 할 수 있습니다.

   ```PowerShell
   $users=get-content "C:\MyPath\users.txt"
    foreach ($user in $users){
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands}
   ```

3. 테넌트 전체 정책을 SfbWithTeamsCollab으로 설정합니다.

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab
   ```

4. 선택한 사용자를 TeamsOnly 모드로 업그레이드합니다. 아일랜드 모드 또는 SfbWithTeamsCollab 모드에서 사용자를 업그레이드하도록 선택할 수 있지만, 사용자가 아일랜드 모드에 있을 때 발생할 수 있는 혼동 가능성을 최소화하기 위해 먼저 아일랜드 모드에서 사용자를 업그레이드하는 우선 순위를 지정할 수 있습니다.

   비즈니스용 Skype Online에 있는 사용자의 경우:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams
   ```

   비즈니스용 Skype 서버 온-프레미스에 있는 사용자의 경우:

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
   ```

아래 다이어그램은 처음에 활성 아일랜드 사용자가 있는 선택 기능 전환의 개념적 단계를 보여 줍니다. 막대의 높이는 사용자 수를 나타냅니다. 업그레이드 단계에서는 모든 사용자가 서로 통신할 수 있습니다.  비즈니스용 Skype 사용자는 interop을 사용하여 TeamsOnly 사용자와 통신하고 그 반대의 경우도 마찬가지입니다.

![아일랜드 모드에서 활성 사용자로 업그레이드하는 선택 기능을 보여 주는 다이어그램.](media/teams-upgrade-2.png)

## <a name="related-links"></a>관련 링크

[비즈니스용 Skype 함께 Teams 사용하는 조직을 위한 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md)

[비즈니스용 Skype 서버 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[MMS(모임 마이그레이션 서비스) 사용](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
