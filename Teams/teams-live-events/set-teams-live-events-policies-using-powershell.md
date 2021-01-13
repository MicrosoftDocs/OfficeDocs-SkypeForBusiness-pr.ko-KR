---
title: PowerShell을 사용하여 라이브 이벤트 정책 설정
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: PowerShell을 사용하여 Teams에서 조직에서 라이브 이벤트를 보유할 수 있는 사용자 및 이벤트에서 사용할 수 있는 기능을 제어하는 정책을 설정하는 방법의 예입니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ece22b6debd3c7d6209df96983d1d66ed5f6f3ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815628"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>PowerShell을 사용하여 Microsoft Teams에서 라이브 이벤트 정책 설정

다음 Windows PowerShell cmdlet을 사용하여 Teams에서 라이브 이벤트에 대한 정책 설정을 설정하고 할당할 수 있습니다. 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

다음은 몇 가지 예입니다.

> [!NOTE]
> 이러한 cmdlet을 실행하려면 먼저 비즈니스용 Skype Online PowerShell에 연결해야 합니다. 자세한 내용은 [Microsoft 365 또는 Office 365 PowerShell을](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)사용하여 비즈니스용 Skype Online 관리를 참조하세요.

## <a name="allow-users-to-schedule-live-events"></a>사용자가 라이브 이벤트를 예약할 수 있도록 허용 

> [!NOTE]
> 이러한 예제는 Teams에서 생성되는 이벤트에 대한 것입니다. 외부 앱 또는 디바이스로 생성되는 이벤트의 경우 추가 단계를 수행해야 합니다. 자세한 내용은 사용자가 외부 앱 또는 디바이스로 생성한 이벤트를 예약할 [수 있도록 합니다.](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)

**사용자가 라이브 이벤트를 예약할 수 있도록 허용**

사용자에게 전역 정책이 할당된 경우 *AllowBroadcastScheduling* 매개 변수가 True로 설정되어 있는지 실행하고 *확인해야 합니다.*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
그런 다음 전역 정책에 사용자를 할당하고 다음을 실행합니다.
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>사용자 시나리오
**조직의 모든 사용자가 라이브 이벤트를 예약할 수 있도록 하려는 경우**

사용자에게 전역 정책이 할당된 경우 *AllowBroadcastScheduling* *이 True로 설정되어 있는지 확인하고 *실행합니다.*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
사용자에게 전역 정책이 다른 정책이 할당된 경우 *-AllowBroadcastScheduling이 True로* 설정되어 있는지 실행하고 *확인해야 합니다.*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**조직 전체에서 라이브 이벤트 일정을 사용하지 않도록 설정하려는 경우**

라이브 이벤트 일정을 사용하지 않도록 설정하고 다음을 실행합니다.
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
조직의 모든 사용자를 전역 정책에 할당하고 다음을 실행합니다.
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**많은 수의 사용자가 라이브 이벤트를 예약하고 사용자 집합이 이벤트를 예약하지 못하게 하려는 경우**

*AllowBroadcastScheduling이 True로* 설정되어 있는지 실행하고 *확인:*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
그런 다음, 전역 정책에 사용자 또는 사용자를 할당하고 다음을 실행합니다.
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

라이브 이벤트의 일정을 허용하지 않는 새 정책을 만들고 다음을 실행합니다.
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
라이브 이벤트 일정을 사용하지 않도록 설정하고 다음을 실행합니다.
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
그런 다음, 이 정책에 사용자를 할당하고 다음을 실행합니다.
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**많은 수의 사용자에 대해 라이브 이벤트 예약을 사용하지 않도록 설정하고 사용자 집합이 이벤트를 예약하도록 허용하려는 경우**

라이브 이벤트 일정을 사용하지 않도록 설정하고 다음을 실행합니다.
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
그런 다음 해당 사용자를 전역 정책에 할당하고 다음을 실행합니다.
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
라이브 이벤트 일정을 허용하는 정책을 만들고 다음을 실행합니다.
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
라이브 이벤트 일정을 사용하도록 설정하고 다음을 실행합니다.
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
그런 다음, 이 정책에 사용자를 할당하고 다음을 실행합니다.
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>라이브 이벤트에 참가할 수 있는 사용자 설정
 
사용자가 익명 사용자를 포함하여 모든 사용자가 참석하고 실행할 수 있는 이벤트를 만들 수 있도록 전역 정책을 설정합니다.
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>라이브 이벤트에 대한 기록 옵션 설정
> [!NOTE]
> 이 설정은 Teams에서 생성되는 이벤트에만 적용됩니다.

라이브 이벤트에 대한 기록을 사용하지 않도록 전역 정책을 설정합니다.
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>라이브 이벤트에서 라이브 캡션 및 자막 설정
> [!NOTE]
> 이 설정은 Teams에서 생성되는 이벤트에만 적용됩니다. 

이벤트 참석자에 대한 라이브 캡션 및 자막(전사)을 설정하는 전역 정책을 설정합니다.
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>관련 항목
- [Teams 라이브 이벤트 설정하기](set-up-for-teams-live-events.md)
- [Teams PowerShell 개요](../teams-powershell-overview.md)

