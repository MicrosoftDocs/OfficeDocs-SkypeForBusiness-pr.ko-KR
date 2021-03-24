---
title: Teams의 프런트라인 작업자에 대한 교대 근무 기반 액세스 관리
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 프런트라인 작업자를 위한 Teams에서 교대 근무 기반 액세스를 관리하는 방법에 대해 자세히 알아보습니다.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: c69f5678b2a3884f52dd3dc676fce21e2ee67f4f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092546"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Teams의 프런트라인 작업자에 대한 교대 근무 기반 액세스 관리

> [!IMPORTANT]
> 2020년 6월 30일부터 Microsoft StaffHub는 사용 중지됩니다. Microsoft Teams에 StaffHub 기능을 구축하고 있습니다. 현재 Teams에는 일정 관리를 위한 교대 근무 앱이 포함되어 있으며 시간이 지날 때 추가 기능이 배포될 것입니다. 2020년 6월 30일 StaffHub에서 모든 사용자에 대해 작동이 중지되었습니다. StaffHub를 여는 모든 사용자에게 Teams를 다운로드하라는 메시지가 표시됩니다. 자세한 내용은 [Microsoft StaffHub는 사용 중지됨](microsoft-staffhub-to-be-retired.md)을 참조하세요.  

## <a name="overview"></a>개요

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams의 현재 상태는 다른 사용자에게 사용자의 현재 가용성 및 상태를 나타냅니다. 프런트라인 작업자의 근무 시간은 일반적으로 매일 동일하지기 때문에 다른 직원보다 예측할 수 없는 경우가 종종 있습니다. 관리자는 팀을 구성하여 조직의 프런트라인 작업자에 대한 교대 근무 기반 상태 집합을 표시하여 교대 근무 중 및 해제 시를 나타낼 수 있습니다.

이러한 교대 근무 기반 현재 상태 단색 확인 표시, Shift On Shift, 회색 원을 나타내며, Shift &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ ](../../media/flw-presence-off-shift.png) **Off** Shift, 단색 빨간색 ![ 원, ](../../media/flw-presence-busy.png)  &mdash; [](../../presence-admins.md) 사용 중이 Teams의 기본 상태 집합과 구분되어 있습니다. 이 두 가지 현재 상태 집합을 사용하면 해당 역할에 따라 조직의 사용자에 대해 서로 다른 환경을 구성할 수 있습니다.

Shift 기반 액세스를 사용하면 프런트라인 작업자가 교대 근무를 해제할 때 Teams에 대한 액세스를 관리할 수 있습니다. 예를 들어, 예약된 교대 근무가 아닌 경우 Teams를 사용하기 전에 프런트라인 작업자가 인정해야 하는 메시지를 표시하기 위해 Teams를 설정할 수 있습니다.  

## <a name="scenario"></a>시나리오

조직에서 교대 근무 기반 액세스를 관리하는 방법에 대한 예제는 다음과 같습니다.

조직에는 관리자가 예약하고 승인한 교대 근무 시간 동안만 지불해야 하는 프런트라인 작업자가 있습니다. Teams 앱 사용이 포함된 예약된 교대 근무 외부에서 작업하는 데 소요된 시간 동안 지불하면 안 됩니다. "근무 중일 때 Teams에서 근무하는 시간은 지급 가능한 시간으로 계산되지 않습니다"라는 사용자 지정 메시지를 설정합니다. 이 메시지는 근무 중일 때 프런트라인 작업자가 Teams에 액세스하려고 할 때 표시됩니다. Teams를 사용하기로 선택한 경우  이 시간 동안 지불되지 않습니다는 것을 이해하여 동의를 클릭합니다.

또한 조직에 급여를 받는 정보 근로자가 있으며 교대 근무를 하지 않는 사용자도 있습니다. Frontline Workers 교대 근무 기반의 현재 상태는 제공하면서 Teams의 기본 현재 상태 사용을 위해 정보 작업자를 구성합니다.

## <a name="shift-based-presence-states"></a>Shift 기반 현재 상태

교대 근무 기반 상태는 다음과 같습니다.

|앱이 구성함 |사용자가 구성함  |추가 정보  |
|---------|---------|---------|
|![단색 녹색 확인 표시, 이동 중을 나타냅니다.](../../media/flw-presence-on-shift.png) 교대 근무 중     |         |교대 근무 시작 시 자동으로 설정         |
|![x가 있는 회색 원은 이동 해제를 나타냅니다.](../../media/flw-presence-off-shift.png) 교대 근무 해제     |         |교대 근무가 끝날 때 자동으로 설정         |
|![채워진 빨간색 원, 다른 용무 중 표시](../../media/flw-presence-busy.png) 다른 용무 중      | ![채워진 빨간색 원, 다른 용무 중 표시](../../media/flw-presence-busy.png) 다른 용무 중         |자동으로 설정됩니다. Frontline Worker가 교대 근무 중일 때 수동으로 설정할 수도 있습니다.|

## <a name="off-shift-access-to-teams"></a>Teams에 대한 교대 근무 액세스 해제

이 기능을 사용하면 프런트라인 작업자가 교대 근무를 벗어날 때 Teams에 대한 액세스를 관리할 수 있습니다. 근무 중일 때 Teams에 액세스하는 경우 Teams를 프런트라인 작업자에게 표시할 수 있도록 Teams를 설정할 수 있습니다. 프런트라인 작업자는  팀을 사용하기 전에 수락을 클릭하여 메시지를 승인해야 합니다.

기본 메시지를 사용하거나 미리 정의된 메시지 집합에서 선택하거나 메시지를 사용자 지정하여 원하는 텍스트를 표시할 수 있습니다. 기본 메시지는 다음과 같습니다.

![기본 메시지 스크린샷](../../media/shifts-presence-message.png)

메시지가 표시될 때 빈도를 설정하고 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 Teams에 대한 액세스가 제한되는 시기 간에 유예 기간을 설정할 수도 있습니다.

## <a name="manage-shift-based-access"></a>교대 근무 기반 액세스 관리

관리자는 정책을 사용하여 조직의 Frontline Workers에 대한 교대 근무 기반 현재 상태 제어를 사용할 수 있습니다. 다음 PowerShell cmdlet을 사용하여 이러한 정책을 관리합니다.

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

New-CsTeamsShiftsPolicy cmdlet을 사용하여 새 정책을 만들고, 원하는 정책 설정을 설정한 다음, Grant-CsTeamsShiftsPolicy cmdlet을 사용하여 사용자에게 정책을 할당합니다.

다음은 몇 가지 예입니다. 선택할 수 있는 미리 정의된 교대 근무 메시지 목록을 비롯한 각 정책 설정 및 매개 변수에 대한 자세한 내용은 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)를 참조하세요.

### <a name="example-1"></a>예제 1

이 예제에서는 Shift Teams 액세스 기본 메시지라는 새 정책을 생성합니다. 이 정책에서는 교대 근무 기반 현재 상태가 켜져 있으며 이 정책에 할당된 사용자가 교대 근무를 해제할 때 Teams에 액세스할 때마다 기본 메시지가 표시됩니다. 사용자가 메시지를 수락하는 경우 교대 근무를 해제할 때 Teams를 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 액세스가 제한된 경우의 유예 기간은 10분입니다.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> **ShiftNoticeMessageType 매개** 변수를 사용하여 표시할 메시지를 설정합니다. 이 매개 변수에서 선택할 수 있는 미리 정의된 메시지 목록을 확인한 경우 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)를 참조하세요.

### <a name="example-2"></a>예제 2 

이 예제에서는 Shift Teams Access Custom Message라는 새 정책을 생성합니다. 이 정책에서는 교대 근무 기반 현재 상태가 켜져 있으며 이 정책을 할당한 사용자가 교대 근무를 벗어날 때 Teams에 액세스할 때마다 사용자 지정 메시지가 표시됩니다. 사용자가 메시지를 수락하는 경우 교대 근무를 해제할 때 Teams를 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 액세스가 제한된 경우의 유예 기간은 15분입니다.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> **ShiftNoticeMessageType 매개** 변수를 사용하여 표시할 메시지를 설정합니다. 자세한 내용은 [New-CsTeamsShiftsPolicy 를 참조합니다.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-3"></a>예제 3

이 예제에서는 Shift Teams Access Message1이라는 새 정책을 생성합니다. 이 정책에서 Shift 기반 현재 상태는 켜져 있으며, 이 정책에 할당된 사용자가 교대 근무 중일 때 Teams에 액세스할 때마다 미리 정의된 메시지가 표시됩니다.

  "고용주는 비영업 시간 동안 비면제 또는 시간당 직원의 네트워크, 애플리케이션, 시스템 또는 도구 사용을 승인하거나 승인하지 않습니다. 수락하면 교대 근무 중 Teams 사용이 승인되지 않은 것을 인정하며 보상되지 않습니다." 

사용자가 메시지를 수락하는 경우 교대 근무를 해제할 때 Teams를 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 액세스가 제한되는 경우의 유예 기간은 3분입니다.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> **ShiftNoticeMessageType 매개** 변수를 사용하여 표시할 메시지를 설정합니다. 이 매개 변수에서 선택할 수 있는 미리 정의된 메시지 목록을 확인한 경우 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)를 참조하세요.

### <a name="example-4"></a>예제 4

이 예제에서는 Shift Teams 액세스 사용자 지정 메시지 끄기라는 정책을 remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>관련 항목

- [Teams에서 조직의 교대 근무 앱 관리](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 개요](../../teams-powershell-overview.md)