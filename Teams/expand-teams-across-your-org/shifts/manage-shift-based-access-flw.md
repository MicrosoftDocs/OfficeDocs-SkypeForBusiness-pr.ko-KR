---
title: Teams 일선 작업자에 대한 교대 근무 기반 액세스 관리
author: SerdarSoysal
ms.author: serdars
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 최전방 작업자를 위한 Teams 교대 근무 기반 액세스를 관리하는 방법을 알아봅니다.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9cb488dfb95647079b51269059ee5c0b120cb9cc
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675220"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Teams 일선 작업자에 대한 교대 근무 기반 액세스 관리
## <a name="overview"></a>개요

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams 현재 상태는 사용자의 현재 가용성 및 다른 사용자의 상태를 나타냅니다. 일선 근로자의 존재는 근무 시간이 일반적으로 매일 동일하지 않기 때문에 다른 직원보다 예측하기 어렵습니다. 관리자는 조직의 일선 작업자가 교대 근무 중일 때를 나타내도록 일련의 교대 근무 기반 현재 상태 집합을 표시하도록 Teams 구성할 수 있습니다.

이러한 시프트 기반 현재 상태의&mdash;![녹색 확인 표시는 시프트를 나타냅니다.](../../media/flw-presence-on-shift.png) **시프트 시** X가 ![있는 회색 원은 끄기 시프트를 나타냅니다.](../../media/flw-presence-off-shift.png) **오프 시프트**( ![단색 빨간색 원)는 **사용 중인 없음**&mdash;](../../media/flw-presence-busy.png)이 Teams [있는 기본 현재 상태 집합](../../presence-admins.md)과 별개임을 나타냅니다. 이러한 두 가지 현재 상태 집합을 사용하면 자신의 역할에 따라 조직의 사용자에 대해 서로 다른 환경을 구성할 수 있습니다.

교대 근무 기반 액세스를 사용하면 일선 작업자가 근무하지 않는 경우 Teams 대한 액세스를 관리할 수 있습니다. 예를 들어 Teams 설정하여 일선 작업자가 예정된 교대 근무에 있지 않을 때 Teams 사용하기 전에 먼저 승인해야 한다는 메시지를 표시할 수 있습니다.  

## <a name="scenario"></a>시나리오

다음은 조직에서 교대 근무 기반 액세스를 관리하는 방법의 예입니다.

조직에는 관리자가 예약하고 승인한 교대 근무 시간 동안만 지불해야 하는 일선 직원이 있습니다. Teams 앱을 사용하는 것을 포함하여 예약된 교대 근무 외부에서 작업하는 데 소요된 시간에 대해 비용을 지불해서는 안 됩니다. 근무 중일 때 Teams 액세스하려고 할 때 표시되는 "Teams 근무 시간은 지불 가능한 시간에 포함되지 않습니다."라는 사용자 지정 메시지를 설정합니다. 그들은 Teams 사용하기로 선택하는 경우, 그들은 그들이이 시간에 대한 지불되지 않습니다 이해와 함께 **동의** 클릭.

또한 조직에 급여를 받고 교대 근무를 하지 않는 정보 근로자도 있습니다. Teams 기본 현재 상태를 사용하도록 정보 근로자를 구성하고 일선 작업자에게 교대 근무 기반의 현재 상태를 제공합니다.

## <a name="shift-based-presence-states"></a>Shift 기반 현재 상태

다음은 시프트 기반 현재 상태입니다.

|앱이 구성함 |사용자가 구성함  |추가 정보  |
|---------|---------|---------|
|![단색 녹색 확인 표시는 시프트 시를 나타냅니다.](../../media/flw-presence-on-shift.png) 시프트 시     |         |교대 근무 시작 시 자동으로 설정         |
|![X가 있는 회색 원, 끄기 시프트를 나타냅니다.](../../media/flw-presence-off-shift.png) 끄기 시프트     |         |교대 근무가 끝날 때 자동으로 설정         |
|![채워진 빨간색 원, 다른 용무 중 표시.](../../media/flw-presence-busy.png) 다른 용무 중      | ![채워진 빨간색 원, 다른 용무 중 표시](../../media/flw-presence-busy.png) 다른 용무 중         |자동으로 설정됩니다. 일선 작업자가 교대 근무 중일 때 수동으로 설정할 수도 있습니다.|

## <a name="off-shift-access-to-teams"></a>Teams 대한 오프 시프트 액세스

이 기능을 사용하면 일선 작업자가 교대 근무를 하지 않는 경우 Teams 대한 액세스를 관리할 수 있습니다. 근무 중일 때 Teams 액세스하는 경우 최전방 작업자에게 메시지를 표시하도록 Teams 설정할 수 있습니다. 일선 근로자는 Teams 사용하기 전에 메시지를 승인하려면 **동의** 를 클릭해야 합니다.

기본 메시지를 사용하거나 미리 정의된 메시지 집합 중에서 선택하거나 원하는 텍스트를 표시하도록 메시지를 사용자 지정할 수 있습니다. 기본 메시지는 다음과 같습니다.

![기본 메시지의 스크린샷.](../../media/shifts-presence-message.png)

메시지가 표시되는 빈도를 설정하고 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시점과 Teams 대한 액세스가 제한된 시점 사이의 유예 기간을 설정할 수도 있습니다.

## <a name="manage-shift-based-access"></a>교대 근무 기반 액세스 관리

관리자는 정책을 사용하여 조직의 일선 작업자에 대한 교대 근무를 제어합니다. 다음 PowerShell cmdlet을 사용하여 이러한 정책을 관리합니다.

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

New-CsTeamsShiftsPolicy cmdlet을 사용하여 새 정책을 만들고, 원하는 정책 설정을 설정한 다음, Grant-CsTeamsShiftsPolicy cmdlet을 사용하여 사용자에게 정책을 할당합니다.

예를 들면 다음과 같습니다. 선택할 수 있는 미리 정의된 오프 시프트 메시지 목록을 포함하여 각 정책 설정 및 매개 변수에 대한 자세한 내용은 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)를 참조하세요.

### <a name="example-1"></a>예제 1

이 예제에서는 기본 메시지에 액세스하기 Teams Off Shift라는 새 정책을 만듭니다. 이 정책에서 교대 근무 기반의 현재 상태가 켜지고 이 정책이 할당된 사용자가 근무 중일 때 Teams 액세스할 때마다 기본 메시지가 표시됩니다. 사용자는 메시지를 수락하는 경우 교대 근무를 해제할 때 Teams 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시점과 액세스가 제한된 시점 사이의 유예 기간은 10분입니다.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> **ShiftNoticeMessageType** 매개 변수를 사용하여 표시할 메시지를 설정합니다. 이 매개 변수에 대해 선택할 수 있는 미리 정의된 메시지 목록을 보려면 [New-CsTeamsShiftsPolicy를](/powershell/module/teams/new-csteamsshiftspolicy) 참조하세요.

### <a name="example-2"></a>예제 2 

이 예제에서는 Off Shift Teams Access Custom Message라는 새 정책을 만듭니다. 이 정책에서 교대 근무 기반의 현재 상태가 켜지고 이 정책이 할당된 사용자가 교대 근무 중일 때 Teams 액세스할 때마다 사용자 지정 메시지가 표시됩니다. 사용자는 메시지를 수락하는 경우 끄기 시프트 시 Teams 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시점과 액세스가 제한된 시점 사이의 유예 기간은 15분입니다.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> **ShiftNoticeMessageType** 매개 변수를 사용하여 표시할 메시지를 설정합니다. 자세한 내용은 [New-CsTeamsShiftsPolicy를 참조하세요](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>예제 3

이 예제에서는 Off Shift Teams Access Message1이라는 새 정책을 만듭니다. 이 정책에서 교대 근무 기반의 현재 상태가 켜지고 이 정책이 할당된 사용자가 근무 중일 때 Teams 액세스할 때마다 다음과 같은 미리 정의된 메시지가 표시됩니다.

  "귀하의 고용주는 비근무 시간 동안 비면제 또는 시간당 직원의 네트워크, 응용 프로그램, 시스템 또는 도구 사용을 승인하거나 승인하지 않습니다. 수락함으로써, 당신은 오프 교대 동안 Teams 사용은 권한이 없으며 보상되지 않습니다 것을 인정합니다." 

사용자는 메시지를 수락하는 경우 Teams 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시점과 액세스가 제한된 시점 사이의 유예 기간은 3분입니다.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> **ShiftNoticeMessageType** 매개 변수를 사용하여 표시할 메시지를 설정합니다. 이 매개 변수에 대해 선택할 수 있는 미리 정의된 메시지 목록을 보려면 [New-CsTeamsShiftsPolicy를](/powershell/module/teams/new-csteamsshiftspolicy) 참조하세요.

### <a name="example-4"></a>예제 4

이 예제에서는 Remy@contoso.com 사용자에게 Off Shift Teams Access Custom Message라는 정책을 할당합니다.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>관련 항목

- [Teams에서 조직의 교대 근무 앱 관리](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 개요](../../teams-powershell-overview.md)