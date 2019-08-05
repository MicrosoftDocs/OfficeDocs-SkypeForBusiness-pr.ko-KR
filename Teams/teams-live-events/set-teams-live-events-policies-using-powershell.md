---
title: PowerShell을 사용 하 여 Microsoft 팀에서 실시간 이벤트 정책 설정
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: PowerShell을 사용 하 여 조직에서 실시간 이벤트를 보유할 수 있는 사용자 및 자신이 만드는 이벤트에서 사용할 수 있는 기능을 제어 하도록 팀에서 정책을 설정 하는 방법의 예
appliesto:
- Microsoft Teams
ms.openlocfilehash: 825fe7e7e80b2653d35c8b0752124b50386395d6
ms.sourcegitcommit: 5faa89ea686448d5b339178f1330edc63e21a52f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2019
ms.locfileid: "36184751"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="332b7-103">PowerShell을 사용 하 여 Microsoft 팀에서 실시간 이벤트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="332b7-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="332b7-104">다음 Windows PowerShell cmdlet을 사용 하 여 팀에서 라이브 이벤트에 대 한 정책 설정을 설정 하 고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="332b7-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="332b7-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="332b7-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="332b7-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="332b7-107">새로운 CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="332b7-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="332b7-108">부여-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="332b7-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="332b7-109">몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-109">Here are some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="332b7-110">사용자가 라이브 이벤트를 예약할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="332b7-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="332b7-111">이러한 예제는 팀에서 생성 된 이벤트에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-111">These examples are for events produced in Teams.</span></span> <span data-ttu-id="332b7-112">외부 앱 또는 장치에서 생성 된 이벤트의 경우 수행 해야 할 추가 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-112">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="332b7-113">자세한 내용은 [사용자가 외부 앱 또는 장치를 사용 하 여 생성 된 이벤트를 예약할 수 있도록 설정을](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="332b7-113">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="332b7-114">**사용자가 라이브 이벤트를 예약할 수 있도록 허용**</span><span class="sxs-lookup"><span data-stu-id="332b7-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="332b7-115">사용자에 게 전역 정책이 할당 되 면 실행 하 고 *AllowBroadcastScheduling* 매개 변수가 *True*로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="332b7-116">그런 다음 글로벌 정책에 사용자를 할당 하 고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="332b7-117">사용자 시나리오</span><span class="sxs-lookup"><span data-stu-id="332b7-117">User scenarios</span></span>
<span data-ttu-id="332b7-118">**조직의 모든 사용자가 라이브 이벤트를 예약할 수 있게 하려는 경우**</span><span class="sxs-lookup"><span data-stu-id="332b7-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="332b7-119">사용자에 게 전역 정책이 할당 되 면 *AllowBroadcastScheduling* \*가 *True*로 설정 되어 있는지 확인 하 고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="332b7-120">사용자에 게 전역 정책 이외의 정책이 할당 되 면 *-AllowBroadcastScheduling* 가 *True*로 설정 되어 있는지 확인 하 고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="332b7-121">**조직에서 실시간 이벤트 일정을 사용 하지 않도록 설정 하려는 경우**</span><span class="sxs-lookup"><span data-stu-id="332b7-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="332b7-122">라이브 이벤트 일정을 사용 하지 않도록 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="332b7-123">조직의 모든 사용자를 전역 정책에 할당 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="332b7-124">**많은 사용자가 라이브 이벤트를 예약 하 고 사용자 집합이 일정을 예약 하지 못하도록 하려는 경우**</span><span class="sxs-lookup"><span data-stu-id="332b7-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="332b7-125">를 실행 하 고 *AllowBroadcastScheduling* 이 *True*로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="332b7-126">그런 다음 글로벌 정책에 사용자 또는 사용자를 할당 하 고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="332b7-127">라이브 이벤트 스케줄링을 허용 하지 않는 새 정책 만들기, 실행:</span><span class="sxs-lookup"><span data-stu-id="332b7-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="332b7-128">라이브 이벤트 일정을 사용 하지 않도록 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="332b7-129">그런 다음이 정책에 사용자를 할당 하 고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="332b7-130">**많은 수의 사용자에 대 한 라이브 이벤트 일정을 사용 하지 않도록 설정 하 고 사용자가 일정을 예약할 수 있도록 하려는 경우**</span><span class="sxs-lookup"><span data-stu-id="332b7-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="332b7-131">라이브 이벤트 일정을 사용 하지 않도록 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="332b7-132">그런 다음 해당 사용자를 전역 정책에 할당 하 고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="332b7-133">라이브 이벤트 일정을 허용 하는 정책을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="332b7-134">라이브 이벤트 일정 사용을 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="332b7-135">그런 다음이 정책에 사용자를 할당 하 고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="332b7-136">라이브 이벤트에 참가할 수 있는 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="332b7-136">Set who can join live events</span></span>
 
<span data-ttu-id="332b7-137">사용자가 익명 사용자를 포함 하 여 모든 사용자가 참석할 수 있는 이벤트를 만드는 것을 허용 하도록 전역 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="332b7-138">라이브 이벤트의 기록 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="332b7-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="332b7-139">이 설정은 팀에서 생성 된 이벤트에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-139">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="332b7-140">라이브 이벤트 기록을 사용 하지 않도록 전역 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="332b7-141">라이브 이벤트에서 실시간 캡션 및 자막 설정</span><span class="sxs-lookup"><span data-stu-id="332b7-141">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="332b7-142">이 설정은 팀에서 생성 된 이벤트에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-142">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="332b7-143">이벤트 참석자에 대 한 실시간 캡션과 자막 (기록)을 설정 하도록 전역 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="332b7-143">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="332b7-144">관련 항목</span><span class="sxs-lookup"><span data-stu-id="332b7-144">Related topics</span></span>
- [<span data-ttu-id="332b7-145">팀에 대 한 라이브 이벤트 설정</span><span class="sxs-lookup"><span data-stu-id="332b7-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)


