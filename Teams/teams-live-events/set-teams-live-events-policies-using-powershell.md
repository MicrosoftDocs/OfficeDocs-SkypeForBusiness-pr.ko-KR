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
description: PowerShell을 사용하여 조직에서 라이브 Teams 수 있는 사용자 및 이벤트에서 사용할 수 있는 기능을 제어하는 정책을 설정하는 방법의 예입니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2b55589a3cabf1b696c1034ce4e20cd7a56af3444f7fa51e0f81f44430ead6bb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54328933"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>PowerShell을 사용하여 라이브 이벤트 정책을 Microsoft Teams

다음 Windows PowerShell cmdlet을 사용하여 라이브 이벤트에 대한 정책 설정을 설정하고 할당할 Teams. 
- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

다음은 몇 가지 예입니다.

> [!NOTE]
> 이러한 cmdlet을 실행하려면 먼저 온라인 PowerShell에 비즈니스용 Skype 있어야 합니다. 자세한 내용은 [PowerShell에서](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)비즈니스용 Skype 온라인 Microsoft 365 Office 365 참조하세요.

## <a name="allow-users-to-schedule-live-events"></a>사용자가 라이브 이벤트를 예약할 수 있도록 허용 

> [!NOTE]
> 이러한 예제는 에서 생성되는 이벤트에 Teams. 외부 앱 또는 디바이스로 생성되는 이벤트의 경우 추가 단계를 수행해야 합니다. 자세한 내용은 외부 앱 또는 디바이스로 생성된 이벤트를 예약할 수 있도록 사용자를 사용하도록 [설정 을 참조하세요.](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)

**사용자가 라이브 이벤트를 예약할 수 있도록 허용**

사용자가 전역 정책을 할당하는 경우 *AllowBroadcastScheduling* 매개 변수가 True로 설정되어 있는지 *확인하고 실행합니다.*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
그런 다음 전역 정책에 사용자를 할당하고 다음을 실행합니다.
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>사용자 시나리오
**조직의 모든 사용자가 라이브 이벤트를 예약할 수 있도록 하려는 경우**

사용자가 전역 정책을 할당하는 경우 *AllowBroadcastScheduling* *이 True로 설정되어 있는지 *확인하고 실행합니다.*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
사용자가 전역 정책이외의 정책을 할당하는 경우 *-AllowBroadcastScheduling이 True로* 설정되어 있는지 *확인하고 실행합니다.*
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

**많은 수의 사용자가 라이브 이벤트를 예약하고 사용자 집합이 일정을 예약하지 못하게 하려는 경우**

*AllowBroadcastScheduling이 True로* 설정되어 있는지 *확인하고 실행합니다.*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
그런 다음 전역 정책에 사용자 또는 사용자를 할당하고 다음을 실행합니다.
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

라이브 이벤트 일정을 허용하지 않는 새 정책을 만들고 다음을 실행합니다.
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
라이브 이벤트 일정을 사용하지 않도록 설정하고 다음을 실행합니다.
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
그런 다음 이 정책에 사용자를 할당하고 다음을 실행합니다.
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**많은 수의 사용자에 대해 라이브 이벤트 예약을 사용하지 않도록 설정하고 사용자 집합에서 일정을 예약하도록 허용하려는 경우**

라이브 이벤트 일정을 사용하지 않도록 설정하고 다음을 실행합니다.
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
그런 다음 전역 정책에 해당 사용자를 할당하고 다음을 실행합니다.
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
라이브 이벤트 일정을 허용하고 다음을 실행하도록 정책을 만들 수 있습니다.
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
라이브 이벤트 일정을 사용하도록 설정하고 다음을 실행합니다.
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
그런 다음 이 정책에 사용자를 할당하고 다음을 실행합니다.
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
> 이 설정은 해당 이벤트에서 생성되는 이벤트에만 Teams.

라이브 이벤트에 대한 기록을 사용하지 않도록 설정하는 전역 정책을 설정합니다.
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>라이브 이벤트에서 라이브 캡션 및 자막 설정
> [!NOTE]
> 이 설정은 해당 이벤트에서 생성되는 이벤트에만 Teams. 

전역 정책을 설정하여 이벤트 참석자에 대한 라이브 캡션 및 자막(전사)을 설정합니다.
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>관련 항목
- [Teams 라이브 이벤트 설정하기](set-up-for-teams-live-events.md)
- [Teams PowerShell 개요](../teams-powershell-overview.md)