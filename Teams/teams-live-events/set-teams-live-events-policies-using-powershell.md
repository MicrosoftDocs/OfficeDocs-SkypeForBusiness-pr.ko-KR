---
title: PowerShell을 사용 하 여 Microsoft 팀에서 실시간 이벤트 정책 설정
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: PowerShell을 사용 하 여 조직에서 실시간 이벤트를 보유할 수 있는 사용자 및 자신이 만드는 이벤트에서 사용할 수 있는 기능을 제어 하도록 팀에서 정책을 설정 하는 방법의 예
appliesto:
- Microsoft Teams
ms.openlocfilehash: d9f96adcf4aa40b93b89b99013b9bc5ca466c25b
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "37570171"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>PowerShell을 사용 하 여 Microsoft 팀에서 실시간 이벤트 정책 설정

다음 Windows PowerShell cmdlet을 사용 하 여 팀에서 라이브 이벤트에 대 한 정책 설정을 설정 하 고 할당할 수 있습니다. 
- [Get-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [새로운 CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [부여-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

몇 가지 예는 다음과 같습니다.

## <a name="allow-users-to-schedule-live-events"></a>사용자가 라이브 이벤트를 예약할 수 있도록 허용 

> [!NOTE]
> 이러한 예제는 팀에서 생성 된 이벤트에 대 한 것입니다. 외부 앱 또는 장치에서 생성 된 이벤트의 경우 수행 해야 할 추가 단계가 있습니다. 자세한 내용은 [사용자가 외부 앱 또는 장치를 사용 하 여 생성 된 이벤트를 예약할 수 있도록 설정을](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)참조 하세요.

**사용자가 라이브 이벤트를 예약할 수 있도록 허용**

사용자에 게 전역 정책이 할당 되 면 실행 하 고 *AllowBroadcastScheduling* 매개 변수가 *True*로 설정 되어 있는지 확인 합니다.
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
그런 다음 글로벌 정책에 사용자를 할당 하 고 다음을 실행 합니다.
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>사용자 시나리오
**조직의 모든 사용자가 라이브 이벤트를 예약할 수 있게 하려는 경우**

사용자에 게 전역 정책이 할당 되 면 *AllowBroadcastScheduling* *가 *True*로 설정 되어 있는지 확인 하 고 실행 합니다.
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
사용자에 게 전역 정책 이외의 정책이 할당 되 면 *-AllowBroadcastScheduling* 가 *True*로 설정 되어 있는지 확인 하 고 실행 합니다.
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**조직에서 실시간 이벤트 일정을 사용 하지 않도록 설정 하려는 경우**

라이브 이벤트 일정을 사용 하지 않도록 설정 하려면 다음을 실행 합니다.
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
조직의 모든 사용자를 전역 정책에 할당 하려면 다음을 실행 합니다.
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**많은 사용자가 라이브 이벤트를 예약 하 고 사용자 집합이 일정을 예약 하지 못하도록 하려는 경우**

를 실행 하 고 *AllowBroadcastScheduling* 이 *True*로 설정 되어 있는지 확인 합니다.
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
그런 다음 글로벌 정책에 사용자 또는 사용자를 할당 하 고 다음을 실행 합니다.
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

라이브 이벤트 스케줄링을 허용 하지 않는 새 정책 만들기, 실행:
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
라이브 이벤트 일정을 사용 하지 않도록 설정 하려면 다음을 실행 합니다.
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
그런 다음이 정책에 사용자를 할당 하 고 다음을 실행 합니다.
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**많은 수의 사용자에 대 한 라이브 이벤트 일정을 사용 하지 않도록 설정 하 고 사용자가 일정을 예약할 수 있도록 하려는 경우**

라이브 이벤트 일정을 사용 하지 않도록 설정 하려면 다음을 실행 합니다.
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
그런 다음 해당 사용자를 전역 정책에 할당 하 고 다음을 실행 합니다.
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
라이브 이벤트 일정을 허용 하는 정책을 만들려면 다음을 실행 합니다.
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
라이브 이벤트 일정 사용을 설정 하려면 다음을 실행 합니다.
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
그런 다음이 정책에 사용자를 할당 하 고 다음을 실행 합니다.
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>라이브 이벤트에 참가할 수 있는 사용자 설정
 
사용자가 익명 사용자를 포함 하 여 모든 사용자가 참석할 수 있는 이벤트를 만드는 것을 허용 하도록 전역 정책을 설정 합니다.
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>라이브 이벤트의 기록 옵션 설정
> [!NOTE]
> 이 설정은 팀에서 생성 된 이벤트에만 적용 됩니다.

라이브 이벤트 기록을 사용 하지 않도록 전역 정책을 설정 합니다.
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>라이브 이벤트에서 실시간 캡션 및 자막 설정
> [!NOTE]
> 이 설정은 팀에서 생성 된 이벤트에만 적용 됩니다. 

이벤트 참석자에 대 한 실시간 캡션과 자막 (기록)을 설정 하도록 전역 정책을 설정 합니다.
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>관련 항목
- [팀에 대 한 라이브 이벤트 설정](set-up-for-teams-live-events.md)


