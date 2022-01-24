---
title: 교대 근무자에 대한 교대 근무 기반 액세스 관리 Teams
author: HowlinWolf-92
ms.author: v-mahoffman
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 Frontline 작업자에 대한 Teams 교대 근무 기반 액세스를 관리하는 방법에 대해 자세히 알아보습니다.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01ef7d91b0119501a3f7570b85ea902c0ebbb7a4
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2022
ms.locfileid: "62180881"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>교대 근무자에 대한 교대 근무 기반 액세스 관리 Teams
## <a name="overview"></a>개요

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams 상태는 사용자의 현재 가용성 및 다른 사용자에게 상태를 나타냅니다. 일선 직원의 존재는 일반적으로 다른 직원보다 예측하기가 더 낮기 때문에 근무 시간이 매일 동일하지 않습니다. 관리자는 조직의 Teams 근무 중일 때를 나타내도록 교대 근무 기반 상태 집합을 표시하도록 구성할 수 있습니다.

이러한 교대 근무 기반 현재 &mdash; ![ 상태는 단색 녹색 확인 표시, 시프트 시를 나타냅니다.](../../media/flw-presence-on-shift.png) **Shift의** ![ 경우 x가 있는 회색 원이 이동 해제를 나타냅니다.](../../media/flw-presence-off-shift.png) **끄기 이동**, 단색 빨간색 원은 사용 중 사용 중이 현재 상태의 기본 집합과 ![ ](../../media/flw-presence-busy.png)  &mdash; [](../../presence-admins.md) Teams. 이 두 가지 현재 상태 집합을 사용하면 해당 역할에 따라 조직의 사용자에 대해 서로 다른 환경을 구성할 수 있습니다.

교대 근무 기반 액세스를 사용하면 일선 작업자가 교대 근무를 Teams 경우 액세스 권한을 관리할 수 있습니다. 예를 들어 일선 Teams 근무자가 예약된 교대 근무에 없는 경우 Teams 전에 확인해야 하는 메시지를 표시할 수 있습니다.  

## <a name="scenario"></a>시나리오

조직에서 교대 근무 기반 액세스를 관리하는 방법에 대한 예제는 다음과 같습니다.

조직에는 관리자가 예약하고 승인한 교대 근무 시간 동안만 지불해야 하는 프런트라인 작업자가 있습니다. 예약된 교대 근무 외부에서 작업하는 데 소요되는 시간(앱 사용 포함)에 대한 Teams 없습니다. "교대 근무 중일 때 Teams 지급 가능 시간으로 계산되지 않습니다"라는 사용자 지정 메시지를 설정했습니다. 이 메시지는 일선 작업자가 교대 근무를 벗어날 때 Teams 표시됩니다. 해당 사용자가 Teams 경우 이 시간  동안 지급되지 않습니다는 것을 이해하여 동의를 클릭합니다.

또한 조직에 급여를 받는 정보 근로자가 있으며 교대 근무를 하지 않는 사용자도 있습니다. 프런트라인 작업자에게 교대 근무 기반 Teams 상태의 기본 상태 사용을 위해 정보 작업자를 구성합니다.

## <a name="shift-based-presence-states"></a>Shift 기반 현재 상태

교대 근무 기반 상태는 다음과 같습니다.

|앱이 구성함 |사용자가 구성함  |추가 정보  |
|---------|---------|---------|
|![단색 녹색 확인 표시는 교대 근무를 나타냅니다.](../../media/flw-presence-on-shift.png) 교대 근무 중     |         |교대 근무 시작 시 자동으로 설정         |
|![x가 있는 회색 원은 이동 해제를 나타냅니다.](../../media/flw-presence-off-shift.png) 교대 근무 해제     |         |교대 근무가 끝날 때 자동으로 설정         |
|![채워진 빨간색 원, 다른 용무 중 표시.](../../media/flw-presence-busy.png) 다른 용무 중      | ![채워진 빨간색 원, 다른 용무 중 표시](../../media/flw-presence-busy.png) 다른 용무 중         |자동으로 설정됩니다. 프런트라인 작업원이 교대 근무 중일 때 수동으로 설정할 수도 있습니다.|

## <a name="off-shift-access-to-teams"></a>다른 사용자에 대한 교대 근무 Teams

이 기능을 사용하면 프런트라인 작업자가 교대 근무를 Teams 경우 액세스 권한을 관리할 수 있습니다. 교대 근무 Teams 액세스하는 경우 일선 작업자에게 메시지를 표시하기 위해 Teams 수 있습니다. 프런트라인 작업자가  메시지를 사용하기 전에 동의를 클릭하여 메시지를 Teams.

기본 메시지를 사용하거나 미리 정의된 메시지 집합에서 선택하거나 메시지를 사용자 지정하여 원하는 텍스트를 표시할 수 있습니다. 기본 메시지는 다음과 같습니다.

![기본 메시지 스크린샷.](../../media/shifts-presence-message.png)

또한 메시지가 표시될 때 빈도를 설정하고 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료될 때와 교대 근무에 대한 액세스가 제한되는 Teams 유예 기간을 설정할 수 있습니다.

## <a name="manage-shift-based-access"></a>교대 근무 기반 액세스 관리

관리자는 정책을 사용하여 조직의 프런트라인 작업자에 대한 교대 근무 기반 현재 상태 제어를 사용할 수 있습니다. 다음 PowerShell cmdlet을 사용하여 이러한 정책을 관리합니다.

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

New-CsTeamsShiftsPolicy cmdlet을 사용하여 새 정책을 만들고, 원하는 정책 설정을 설정한 다음, Grant-CsTeamsShiftsPolicy cmdlet을 사용하여 사용자에게 정책을 할당합니다.

예를 들면 다음과 같습니다. 선택할 수 있는 미리 정의된 교대 근무 메시지 목록을 비롯한 각 정책 설정 및 매개 변수에 대한 자세한 내용은 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)를 참조하세요.

### <a name="example-1"></a>예제 1

이 예제에서는 Access 기본 메시지에 대해 Shift Teams 새 정책을 생성합니다. 이 정책에서는 교대 근무 기반 현재 상태가 켜져 있으며, 이 정책에 할당된 사용자가 교대 근무를 벗어날 때 Teams 때마다 기본 메시지가 표시됩니다. 사용자가 메시지를 Teams 경우 교대 근무를 해제할 때 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 액세스가 제한된 경우의 유예 기간은 10분입니다.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> **ShiftNoticeMessageType 매개** 변수를 사용하여 표시할 메시지를 설정합니다. 이 매개 변수에서 선택할 수 있는 미리 정의된 메시지 목록을 확인한 경우 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)를 참조하세요.

### <a name="example-2"></a>예제 2 

이 예제에서는 Access Custom Message에서 Off Shift라는 Teams 만들 수 있습니다. 이 정책에서는 교대 근무 기반 존재가 켜져 있으며, 이 정책에 할당된 사용자가 교대 근무를 벗어날 때 사용자 지정 Teams 표시됩니다. 사용자가 메시지를 Teams 경우 교대 근무를 해제할 때 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 액세스가 제한된 경우의 유예 기간은 15분입니다.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> **ShiftNoticeMessageType 매개** 변수를 사용하여 표시할 메시지를 설정합니다. 자세한 내용은 [New-CsTeamsShiftsPolicy 를 참조합니다.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-3"></a>예제 3

이 예제에서는 Access Message1에서 Off Shift라는 새 정책을 Teams 있습니다. 이 정책에서는 교대 근무 기반 현재 상태가 켜져 있으며, 이 정책에 할당된 사용자가 교대 근무를 벗어날 때 이 정책에 액세스할 때마다 다음과 같은 미리 Teams 표시됩니다.

  "고용주는 비영업 시간 동안 비면제 또는 시간당 직원의 네트워크, 애플리케이션, 시스템 또는 도구 사용을 승인하거나 승인하지 않습니다. 수락을 통해 교대 근무하는 동안 Teams 사용이 승인되지 않은 것을 인정하며 보상되지 않습니다." 

사용자가 메시지를 Teams 경우 교대 근무를 해제할 때 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 액세스가 제한된 경우의 유예 기간은 3분입니다.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> **ShiftNoticeMessageType 매개** 변수를 사용하여 표시할 메시지를 설정합니다. 이 매개 변수에서 선택할 수 있는 미리 정의된 메시지 목록을 확인한 경우 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)를 참조하세요.

### <a name="example-4"></a>예제 4

이 예제에서는 Off Shift라는 정책을 Teams 사용자 지정 메시지에 액세스 사용자 지정 메시지를 remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>관련 항목

- [Teams에서 조직의 교대 근무 앱 관리](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 개요](../../teams-powershell-overview.md)