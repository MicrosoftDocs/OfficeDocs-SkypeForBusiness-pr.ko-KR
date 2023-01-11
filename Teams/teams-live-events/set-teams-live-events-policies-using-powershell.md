---
title: PowerShell을 사용하여 라이브 이벤트 정책 설정
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: PowerShell을 사용하여 Teams에서 정책을 설정하여 조직에서 라이브 이벤트를 보유할 수 있는 사용자와 이벤트에서 사용할 수 있는 기능을 제어하는 방법의 예입니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ef243860ea1450dcd5539d3d5b01025e7eac55cd
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767578"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>PowerShell을 사용하여 Microsoft Teams에서 라이브 이벤트 정책 설정

다음 Windows PowerShell cmdlet을 사용하여 Teams에서 라이브 이벤트에 대한 정책 설정을 설정하고 할당할 수 있습니다.

- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)

다음은 몇 가지 예입니다.

> [!NOTE]
> 이러한 cmdlet을 실행하려면 먼저 비즈니스용 Skype Online PowerShell에 연결해야 합니다. 자세한 내용은 [Microsoft 365를 사용하여 비즈니스용 Skype Online 관리 또는 PowerShell Office 365 참조하세요](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

## <a name="allow-users-to-schedule-live-events"></a>사용자가 라이브 이벤트를 예약할 수 있도록 허용

> [!NOTE]
> 이러한 예제는 Teams에서 생성된 이벤트에 대한 것입니다.

### <a name="allow-a-user-to-schedule-live-events"></a>사용자가 라이브 이벤트를 예약할 수 있도록 허용

사용자에게 전역 정책이 할당된 경우 *를 실행하고 AllowBroadcastScheduling* 매개 변수가 *True* 로 설정되어 있는지 확인합니다.

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```

그런 다음, 사용자를 전역 정책에 할당하고 다음을 실행합니다.

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>사용자 시나리오

#### <a name="you-want-all-users-in-your-organization-to-be-able-to-schedule-live-events"></a>조직의 모든 사용자가 라이브 이벤트를 예약할 수 있도록 합니다.

사용자에게 글로벌 정책이 할당된 경우 를 실행하고 *AllowBroadcastScheduling* 이 True로 설정되어 있는지 확인 *합니다*.

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```

사용자에게 전역 정책 이외의 정책이 할당된 경우 *를 실행하고 -AllowBroadcastScheduling* 이 True로 설정되어 있는지 확인 *합니다*.

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

#### <a name="you-want-live-events-scheduling-to-be-disabled-across-your-organization"></a>조직 전체에서 라이브 이벤트 예약을 사용하지 않도록 설정하려고 합니다.

라이브 이벤트 예약을 사용하지 않도록 설정하고 다음을 실행합니다.

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```

조직의 모든 사용자를 전역 정책에 할당하고 다음을 실행합니다.

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="you-want-a-large-number-of-users-to-be-able-to-schedule-live-events-and-prevent-a-set-of-users-from-scheduling-them"></a>많은 수의 사용자가 라이브 이벤트를 예약하고 사용자 집합의 예약을 방지할 수 있기를 원합니다.

*를 실행하고 AllowBroadcastScheduling* 이 *True* 로 설정되어 있는지 확인합니다.

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```

그런 다음, 전역 정책에 사용자 또는 사용자를 할당하고 다음을 실행합니다.

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

라이브 이벤트 예약을 허용하지 않는 새 정책을 만들고 다음을 실행합니다.

```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```

라이브 이벤트 예약을 사용하지 않도록 설정하고 다음을 실행합니다.

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```

그런 다음, 이 정책에 사용자를 할당하고 다음을 실행합니다.

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```

#### <a name="you-want-to-disable-live-event-scheduling-for-a-large-number-of-the-users-and-allow-a-set-of-users-to-schedule-them"></a>많은 수의 사용자에 대한 라이브 이벤트 예약을 사용하지 않도록 설정하고 사용자 집합이 예약하도록 허용하려고 합니다.

라이브 이벤트 예약을 사용하지 않도록 설정하고 다음을 실행합니다.

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```

그런 다음, 해당 사용자를 전역 정책에 할당하고 다음을 실행합니다.

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

라이브 이벤트 예약을 허용하는 정책을 만들고 다음을 실행합니다.

```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```

라이브 이벤트 예약을 사용하도록 설정하고 다음을 실행합니다.

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```

그런 다음, 이 정책에 사용자를 할당하고 다음을 실행합니다.

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

## <a name="set-who-can-join-live-events"></a>라이브 이벤트에 참가할 수 있는 사용자 설정

사용자가 익명 사용자를 포함하여 모든 사용자가 참석할 수 있는 이벤트를 만들 수 있도록 전역 정책을 설정합니다.

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```

## <a name="set-the-recording-option-for-live-events"></a>라이브 이벤트에 대한 기록 옵션 설정

> [!NOTE]
> 이 설정은 Teams에서 생성된 이벤트에만 적용됩니다.

라이브 이벤트에 대한 기록을 사용하지 않도록 설정하려면 전역 정책을 설정합니다.

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```

## <a name="set-live-captions-and-subtitles-in-live-events"></a>라이브 이벤트에서 라이브 캡션 및 자막 설정

> [!NOTE]
> 이 설정은 Teams에서 생성된 이벤트에만 적용됩니다.

이벤트 참석자에 대한 라이브 캡션 및 자막(전사)을 켜도록 전역 정책을 설정합니다.

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>관련 주제

- [Teams 라이브 이벤트 설정하기](set-up-for-teams-live-events.md)
- [Teams PowerShell 개요](../teams-powershell-overview.md)
