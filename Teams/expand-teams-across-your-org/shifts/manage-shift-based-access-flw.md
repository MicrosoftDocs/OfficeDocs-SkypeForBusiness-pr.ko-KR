---
title: 팀의 Firstline Worker에 대 한 shift 기반 액세스 관리
author: LanaChin
ms.author: v-lanac
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 조직의 Firstline Worker에 대 한 팀에서 교대 근무 액세스를 관리 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01180f95766412b82d9df7986c3667298f24d5b4
ms.sourcegitcommit: 8a345ca9a8ddc6a84f9e270ab55f1b28f6ba49c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48486878"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a>팀의 Firstline Worker에 대 한 shift 기반 액세스 관리

> [!IMPORTANT]
> 유효 2020 년 6 월 30 일에 Microsoft StaffHub 사용이 중지 되었습니다. Microsoft 팀에 StaffHub 접근 권한 값을 구축 하 고 있습니다. 현재 팀에는 일정 관리를 위해 교대 근무 앱이 포함 되어 있으며 추가 기능이 시간에 따라 롤아웃 됩니다. StaffHub에서 2020 년 6 월 30 일에 모든 사용자의 작동이 중지 되었습니다. StaffHub를 열려고 하는 모든 사용자에 게 팀을 다운로드 하도록 지시 하는 메시지가 표시 됩니다. 자세한 내용은 [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)을 사용 중지 하세요.  

## <a name="overview"></a>개요

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft 팀에는 사용자의 현재 사용 가능 시간 및 다른 사용자에 대 한 상태가 표시 됩니다. 다른 직원이 근무 시간이 매번 동일 하지 않기 때문에 Firstline Worker의 현재 상태는 예측 하기 어렵습니다. 관리자는 조직의 Firstline Worker에 대 한 교대 근무 상태의 현재 상태 집합을 표시 하도록 팀을 구성 하 여 shift 키를 사용 하거나 사용 하지 않을 시점을 나타낼 수 있습니다.

이러한 교대 근무 현재 상태에 &mdash; ![ 는 녹색 체크 표시, ](../../media/flw-presence-on-shift.png) **shift**키, ![ x가 있는 회색 원 ](../../media/flw-presence-off-shift.png) **Off shift**, ![ ](../../media/flw-presence-busy.png) **Busy** &mdash; [default set of presence states](../../presence-admins.md) shift 키를 사용 하 여 교대 근무 시간 표시, 빨간색 실선이 있는 것을 나타냅니다. 이러한 두 가지 현재 상태 집합을 사용 하 여 조직 내 사용자의 역할에 따라 다른 환경을 구성할 수 있습니다.

Shift 기반 액세스를 사용 하면 Firstline Worker가 교대 근무 중일 때 팀에 대 한 액세스를 관리할 수 있습니다. 예를 들어 팀에서 예정 된 교대 근무에 있지 않은 팀을 사용할 수 있도록 하기 전에 Firstline Worker가 승인 해야 하는 메시지를 표시 하도록 팀을 설정할 수 있습니다.  

## <a name="scenario"></a>시나리오

다음은 조직에서 shift 기반 액세스를 관리 하는 방법의 예입니다.

조직의 Firstline Worker를 보유 하 고 있으며, 관리자가 작업을 예약 하 고 승인 하는 시간 동안만 지불 해야 합니다. 팀 앱을 사용 하는 것을 포함 하 여 예정 된 교대 근무 범위를 벗어나는 시간에 대해 지급 되지 않습니다. "교대 근무 시간이 지난 후에는 팀에 시간을 초과 하지 않습니다." 라는 사용자 지정 메시지를 설정 하 여 Firstline Worker가 shift 키를 끄면 팀에 액세스 하려고 할 때 표시 됩니다. 팀을 사용 하기로 선택 하는 경우에는 해당 시간에 지불 되지 않는다는 것을 이해 하는 것으로 **승인** 됨을 클릭 합니다.

또한 조직의 정보 근로자와 함께 salaried 작업을 수행 하지 않는 사람을 할 수 있습니다. 팀에서 Firstline Worker를 이동 하는 동안 기본 현재 상태를 사용 하도록 정보 근로자를 구성 합니다.

## <a name="shift-based-presence-states"></a>Shift 기반 현재 상태

다음은 shift 기반 현재 상태입니다.

|앱이 구성함 |사용자가 구성함  |추가 정보  |
|---------|---------|---------|
|![녹색 확인 표시가 있고 shift 키를 나타냄](../../media/flw-presence-on-shift.png) Shift 키     |         |교대 근무 시작 시 자동으로 설정         |
|![X가 있는 회색 원은 shift 키를 표시 합니다.](../../media/flw-presence-off-shift.png) Shift 키 해제     |         |자동으로 교대 근무의 끝에 설정 됩니다.         |
|![채워진 빨간색 원, 다른 용무 중 표시](../../media/flw-presence-busy.png) 다른 용무 중      | ![채워진 빨간색 원, 다른 용무 중 표시](../../media/flw-presence-busy.png) 다른 용무 중         |자동으로 설정 됩니다. Firstline Worker가 shift에 있는 경우 수동으로 설정할 수도 있습니다.|

## <a name="off-shift-access-to-teams"></a>팀에 대 한 shift 액세스 해제

이 기능을 사용 하면 Firstline Worker가 교대 근무 중일 때 팀에 대 한 액세스를 관리할 수 있습니다. Shift 키를 사용 하지 않을 때 팀에 액세스 하는 경우 Firstline Worker에 게 메시지를 표시 하도록 팀을 설정할 수 있습니다. Firstline Worker는 팀을 사용할 수 있도록 메시지를 승인 하기 위해 **수락** 을 클릭 해야 합니다.

기본 메시지를 사용 하거나, 미리 정의 된 메시지 집합에서 선택 하거나, 메시지를 사용자 지정 하 여 원하는 텍스트를 표시할 수 있습니다. 기본 메시지는 다음과 같습니다.

![기본 메시지 스크린샷](../../media/shifts-presence-message.png)

메시지가 표시 되는 빈도를 설정 하 고 첫 번째 교대조가 시작 되는 동안 또는 마지막으로 이동 하는 경우와 팀에 대 한 액세스가 제한 되는 경우의 유예 기간을 설정할 수도 있습니다.

## <a name="manage-shift-based-access"></a>Shift 기반 액세스 관리

관리자는 정책을 사용 하 여 조직의 Firstline Worker에 대 한 shift 기반 현재 상태를 제어 합니다. 다음 PowerShell cmdlet을 사용 하 여 이러한 정책을 관리할 수 있습니다.

- [새로운 CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [부여-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [제거-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

New-CsTeamsShiftsPolicy cmdlet을 사용 하 여 새 정책을 만들고 원하는 정책 설정을 설정한 다음 Grant-CsTeamsShiftsPolicy cmdlet을 사용 하 여 정책을 사용자에 게 할당 합니다.

몇 가지 예를 살펴보겠습니다. 선택할 수 있는 미리 정의 된 오프 라인 이동 메시지 목록을 비롯 한 각 정책 설정 및 매개 변수에 대 한 자세한 내용은 [CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)을 참조 하세요.

### <a name="example-1"></a>예제 1

이 예제에서는 Off Shift 팀 이라는 새 정책을 만들어 기본 메시지에 액세스 합니다. 이 정책에서 shift 기반 현재 상태는 설정 되어 있으며,이 정책이 할당 된 사용자가 shift 키를 끄면 팀에 액세스할 때마다 기본 메시지가 표시 됩니다. 사용자가 메시지를 수락 하는 경우에는 팀을 사용할 수 있으며, 첫 번째 교대조가 시작 되는 동안 또는 마지막으로 이동 하는 동안 유예 기간이 10 분으로 제한 됩니다.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> **ShiftNoticeMessageType** 매개 변수를 사용 하 여 표시 하려는 메시지를 설정 합니다. 이 매개 변수에 대해 선택할 수 있는 미리 정의 된 메시지의 목록을 보려면 [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)을 참조 하세요.

### <a name="example-2"></a>예제 2 

이 예제에서는 사용자 지정 메시지에 대 한 외부 전환 팀 이라는 새 정책을 만듭니다. 이 정책에서 shift 기반 현재 상태는 설정 되어 있으며,이 정책이 할당 된 사용자가 shift 키를 끄면 팀에 액세스할 때마다 사용자 지정 메시지가 표시 됩니다. 사용자가 메시지를 수락 하는 경우에는 팀을 사용할 수 있고, 첫 번째 교대조가 시작 되는 동안 또는 마지막으로 이동 하는 경우와 access가 제한 되는 경우에는 15 분 간의 유예 기간이 종료 됩니다.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> **ShiftNoticeMessageType** 매개 변수를 사용 하 여 표시 하려는 메시지를 설정 합니다. 자세한 내용은 [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)를 참조 하세요.

### <a name="example-3"></a>예제 3

이 예제에서는 Off Shift 팀에 게 Message1 액세스 라는 새 정책을 만듭니다. 이 정책에서 shift 기반 현재 상태는 설정 되어 있으며,이 정책이 할당 된 사용자가 shift 키를 끄면 팀에 액세스할 때마다 미리 정의 된 다음 메시지가 표시 됩니다.

  "고용주는 근무 시간 중 비 면제 또는 시간당 직원에의 한 네트워크, 응용 프로그램, 시스템 또는 도구 사용을 허가 하거나 승인 하지 않습니다. 수락 하면 교대 근무를 해제 하는 동안 팀을 사용 하는 것이 승인 되지 않았으므로 사용자는 보정 되지 않습니다. " 

사용자가 메시지를 수락 하는 경우에는 팀을 사용할 수 있고, 첫 번째 교대조가 시작 되는 동안 또는 마지막으로 이동 하는 경우와 access가 제한 되는 시간 사이에 유예 기간이 3 분입니다.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> **ShiftNoticeMessageType** 매개 변수를 사용 하 여 표시 하려는 메시지를 설정 합니다. 이 매개 변수에 대해 선택할 수 있는 미리 정의 된 메시지의 목록을 보려면 New-TeamsShiftPolicy을 참조 하세요.

### <a name="example-4"></a>예제 4

이 예제에서는 remy@contoso.com 라는 사용자에 게 사용자 지정 메시지에 대 한 외부 교대 팀의 정책을 할당 합니다.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>관련 항목

- [Teams에서 조직의 교대 근무 앱 관리](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 개요](../../teams-powershell-overview.md)
