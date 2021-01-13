---
title: Teams에서 일선 작업자에 대한 교대 근무 기반 액세스 관리
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 일선 작업자용 Teams에서 교대 근무 기반 액세스를 관리하는 방법을 배워야 합니다.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b73fe9b3c4b39e7d3fa7b31427f563c47e5a737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823018"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a>Teams에서 일선 작업자에 대한 교대 근무 기반 액세스 관리

> [!IMPORTANT]
> 2020년 6월 30일부로 Microsoft StaffHub가 사용 중지됩니다. Microsoft Teams에 StaffHub 기능을 구축하고 있습니다. 현재 Teams에는 일정 관리를 위한 Shifts 앱이 포함되어 있으며 시간이 지날 때 추가 기능이 출시됩니다. StaffHub는 2020년 6월 30일 모든 사용자에 대한 작업을 중지했습니다. StaffHub를 열려고 하는 모든 사람이 Teams를 다운로드할 수 있는 메시지를 보여 주게 됩니다. 자세한 내용은 [Microsoft StaffHub가](microsoft-staffhub-to-be-retired.md)사용 중지된 것을 참조합니다.  

## <a name="overview"></a>개요

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams의 현재 상태는 사용자의 현재 상태와 다른 사용자에게 상태를 나타냅니다. 일선 직원의 존재는 일반적으로 매일 동일하지 않은 다른 직원보다 예측하기가 더 낮습니다. 관리자는 조직의 일선 직원에 대한 교대 근무 기반 현재 상태 집합을 표시하도록 Teams를 구성하여 교대 근무 중 및 벗어날 때를 나타낼 수 있습니다.

이러한 교대 근무 기반 현재 상태는 단색 녹색 확인 표시로, Shift 시 시프트 시 회색 원, Shift를 끄는 회색 원, 단색 빨간색 원, 다른 사용 중이 Teams의 기본 현재 상태 집합과 별개인 경우를 &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; 나타냅니다. [](../../presence-admins.md) 이러한 두 현재 상태 집합을 사용하면 해당 역할에 따라 조직의 사용자에 대해 서로 다른 환경을 구성할 수 있습니다.

교대 근무 기반 액세스를 사용하면 일선 작업자가 교대 근무 중일 때 Teams에 대한 액세스를 관리할 수 있습니다. 예를 들어 일선 작업자가 예약된 교대 근무에 있지 않을 때 Teams를 사용하기 전에 먼저 일선 작업자가 인정해야 하는 메시지를 표시하는 Teams를 설정할 수 있습니다.  

## <a name="scenario"></a>시나리오

다음은 조직에서 교대 근무 기반 액세스를 관리하는 방법의 예입니다.

조직의 일선 작업자는 관리자가 예약하고 승인한 교대 근무 시간에 한해 지급해야 합니다. Teams 앱 사용을 포함하는 예약된 교대 근무 외부에서 작업하는 데 소요된 시간으로는 지불하면 안 됩니다. 일선 작업자가 교대 근무 중일 때 Teams에 액세스하려고 할 때 표시되는 사용자 지정 메시지를 설정하면 "근무 시간에는 지불할 수 있는 시간에 계산되지 않습니다."라는 사용자 지정 메시지를 설정할 수 있습니다. Teams를 사용하기로 선택한 경우  이 시간 동안 지불되지 않는 것으로 이해하면 동의를 클릭합니다.

또한 급여를 받는 정보 근로자가 있으며 근무하지 않는 정보 근로자가 있습니다. 일선 작업자의 교대 근무 기반 현재 상태는 제공하면서 Teams의 기본 현재 상태 사용을 정보 근로자가 구성합니다.

## <a name="shift-based-presence-states"></a>Shift 기반 현재 상태

교대 기반 현재 상태는 다음과 같습니다.

|앱이 구성함 |사용자가 구성함  |추가 정보  |
|---------|---------|---------|
|![단색 녹색 확인 표시, 시프트 표시](../../media/flw-presence-on-shift.png) 교대 근무 중     |         |교대 근무 시작 시 자동으로 설정         |
|![회색 원(x, 끄기 이동 표시)](../../media/flw-presence-off-shift.png) 끄기 교대 근무     |         |교대 근무 끝에 자동으로 설정         |
|![채워진 빨간색 원, 다른 용무 중 표시](../../media/flw-presence-busy.png) 다른 용무 중      | ![채워진 빨간색 원, 다른 용무 중 표시](../../media/flw-presence-busy.png) 다른 용무 중         |자동으로 설정됩니다. 일선 근무가 교대 근무 중일 때 수동으로 설정할 수도 있습니다.|

## <a name="off-shift-access-to-teams"></a>Teams에 대한 교대 근무 액세스 해제

이 기능을 사용하면 일선 작업자가 교대 근무 중일 때 Teams에 대한 액세스를 관리할 수 있습니다. 근무 중일 때 Teams에 액세스하는 경우 일선 작업자에게 메시지를 표시하는 Teams를 설정할 수 있습니다. 일선 작업자가  Teams를 사용하려면 먼저 메시지를 승인하려면 동의를 클릭해야 합니다.

기본 메시지를 사용하거나 미리 정의된 메시지 집합에서 선택하거나 원하는 텍스트를 표시하는 메시지를 사용자 지정할 수 있습니다. 기본 메시지는 다음과 같습니다.

![기본 메시지 스크린샷](../../media/shifts-presence-message.png)

메시지가 표시될 때 빈도를 설정하고 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 Teams에 대한 액세스가 제한되는 시기 사이의 유예 기간을 설정할 수도 있습니다.

## <a name="manage-shift-based-access"></a>교대 근무 기반 액세스 관리

관리자는 정책을 사용하여 조직의 일선 직원에 대한 교대 근무 기반 현재 상태 제어 다음 PowerShell cmdlet을 사용하여 이러한 정책을 관리합니다.

- [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

New-CsTeamsShiftsPolicy cmdlet을 사용하여 새 정책을 만들고, 원하는 정책 설정을 설정한 다음, Grant-CsTeamsShiftsPolicy cmdlet을 사용하여 사용자에게 정책을 할당합니다.

다음은 몇 가지 예입니다. 선택할 수 있는 미리 정의한 교대 근무 메시지 목록을 포함하여 각 정책 설정 및 매개 변수에 대한 자세한 내용은 [New-CsTeamsShiftsPolicy를](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)참조하세요.

### <a name="example-1"></a>예제 1

이 예제에서는 Shift Teams 액세스 기본 메시지 해제라는 새 정책을 만들겠습니다. 이 정책에서는 교대 근무 기반 현재 상태가 켜져 있으며 이 정책이 할당된 사용자가 교대 근무 중일 때 Teams에 액세스할 때마다 기본 메시지가 표시됩니다. 사용자는 메시지를 수락하는 경우 교대 근무를 해제할 때 Teams를 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 액세스가 제한되는 시기 사이의 유예 기간은 10분입니다.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> **ShiftNoticeMessageType** 매개 변수를 사용하여 표시할 메시지를 설정할 수 있습니다. 이 매개 변수에 대해 선택할 수 있는 미리 정의된 메시지 목록을 확인한 다음 [New-CsTeamsShiftsPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-2"></a>예제 2 

이 예제에서는 Shift Teams 액세스 사용자 지정 메시지 해제라는 새 정책을 만들겠습니다. 이 정책에서는 교대 근무 기반 현재 상태가 켜져 있으며 이 정책이 할당된 사용자가 교대 근무 중일 때 Teams에 액세스할 때마다 사용자 지정 메시지가 표시됩니다. 사용자는 메시지를 수락하는 경우 교대 근무를 해제할 때 Teams를 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 액세스가 제한되는 시기 사이의 유예 기간은 15분입니다.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> **ShiftNoticeMessageType** 매개 변수를 사용하여 표시할 메시지를 설정할 수 있습니다. 자세한 내용은 [New-CsTeamsShiftsPolicy를 참조합니다.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-3"></a>예제 3

이 예제에서는 Shift Teams Access Message1이라는 새 정책을 만들어 보겠습니다. 이 정책에서는 교대 근무 기반 현재 상태가 켜져 있으며 이 정책이 할당된 사용자가 교대 근무 중일 때 Teams에 액세스할 때마다 다음과 같은 미리 정의된 메시지가 표시됩니다.

  "고용주가 비면제 또는 시간당 직원이 근무하지 않는 시간 동안 네트워크, 애플리케이션, 시스템 또는 도구의 사용을 승인하거나 승인하지 않습니다. 수락하면 교대 근무 중 Teams를 사용할 수 있는 권한이 부여되지 않은 것을 인정하고 보상을 하지 않습니다." 

사용자는 메시지를 수락하는 경우 교대 근무를 해제할 때 Teams를 사용할 수 있으며, 첫 번째 교대 근무가 시작되거나 마지막 교대 근무가 종료되는 시기와 액세스가 제한되는 시기 사이의 유예 기간은 3분입니다.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> **ShiftNoticeMessageType** 매개 변수를 사용하여 표시할 메시지를 설정할 수 있습니다. 이 매개 변수에 대해 선택할 수 있는 미리 정의된 메시지 목록을 확인한 다음 [New-CsTeamsShiftsPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-4"></a>예제 4

이 예제에서는 Shift Teams Access 사용자 지정 메시지 해제라는 정책을 사용자 지정 remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>관련 항목

- [Teams에서 조직의 교대 근무 앱 관리](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 개요](../../teams-powershell-overview.md)
