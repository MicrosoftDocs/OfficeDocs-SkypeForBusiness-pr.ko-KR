---
title: PowerShell을 사용 하 여 라이브 이벤트 정책 설정
author: lanachin
ms.author: v-lanac
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
description: PowerShell을 사용 하 여 조직에서 실시간 이벤트를 보유할 수 있는 사용자와 이벤트에서 사용할 수 있는 기능을 제어 하기 위해 팀에서 정책을 설정 하는 방법을 보여 주는 예입니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1c1131790e36fe451444a8c8a3fb25259d5741da
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691574"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="52893-103">PowerShell을 사용 하 여 Microsoft 팀에서 실시간 이벤트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="52893-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="52893-104">다음 Windows PowerShell cmdlet을 사용 하 여 팀에서 라이브 이벤트에 대 한 정책 설정을 설정 하 고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52893-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="52893-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="52893-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="52893-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="52893-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="52893-107">새로운 CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="52893-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="52893-108">부여-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="52893-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="52893-109">몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="52893-109">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="52893-110">이러한 cmdlet을 실행 하려면 비즈니스용 Skype Online PowerShell에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-110">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="52893-111">자세한 내용은 [Microsoft 365 또는 Office 365 PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="52893-111">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="52893-112">사용자가 라이브 이벤트를 예약할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="52893-112">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="52893-113">이러한 예제는 팀에서 생성 된 이벤트에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="52893-113">These examples are for events produced in Teams.</span></span> <span data-ttu-id="52893-114">외부 앱 또는 장치에서 생성 된 이벤트의 경우 수행 해야 할 추가 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52893-114">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="52893-115">자세한 내용은 [사용자가 외부 앱 또는 장치를 사용 하 여 생성 된 이벤트를 예약할 수 있도록 설정을](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="52893-115">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="52893-116">**사용자가 라이브 이벤트를 예약할 수 있도록 허용**</span><span class="sxs-lookup"><span data-stu-id="52893-116">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="52893-117">사용자에 게 전역 정책이 할당 되 면 실행 하 고 *AllowBroadcastScheduling* 매개 변수가 *True*로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-117">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="52893-118">그런 다음 글로벌 정책에 사용자를 할당 하 고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-118">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="52893-119">사용자 시나리오</span><span class="sxs-lookup"><span data-stu-id="52893-119">User scenarios</span></span>
<span data-ttu-id="52893-120">**조직의 모든 사용자가 라이브 이벤트를 예약할 수 있게 하려는 경우**</span><span class="sxs-lookup"><span data-stu-id="52893-120">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="52893-121">사용자에 게 전역 정책이 할당 되 면 *AllowBroadcastScheduling* \*가 *True*로 설정 되어 있는지 확인 하 고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-121">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="52893-122">사용자에 게 전역 정책 이외의 정책이 할당 되 면 *-AllowBroadcastScheduling* 가 *True*로 설정 되어 있는지 확인 하 고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-122">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="52893-123">**조직에서 실시간 이벤트 일정을 사용 하지 않도록 설정 하려는 경우**</span><span class="sxs-lookup"><span data-stu-id="52893-123">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="52893-124">라이브 이벤트 일정을 사용 하지 않도록 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-124">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="52893-125">조직의 모든 사용자를 전역 정책에 할당 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-125">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="52893-126">**많은 사용자가 라이브 이벤트를 예약 하 고 사용자 집합이 일정을 예약 하지 못하도록 하려는 경우**</span><span class="sxs-lookup"><span data-stu-id="52893-126">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="52893-127">를 실행 하 고 *AllowBroadcastScheduling* 이 *True*로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-127">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="52893-128">그런 다음 글로벌 정책에 사용자 또는 사용자를 할당 하 고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-128">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="52893-129">라이브 이벤트 스케줄링을 허용 하지 않는 새 정책 만들기, 실행:</span><span class="sxs-lookup"><span data-stu-id="52893-129">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="52893-130">라이브 이벤트 일정을 사용 하지 않도록 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-130">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="52893-131">그런 다음이 정책에 사용자를 할당 하 고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-131">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="52893-132">**많은 수의 사용자에 대 한 라이브 이벤트 일정을 사용 하지 않도록 설정 하 고 사용자가 일정을 예약할 수 있도록 하려는 경우**</span><span class="sxs-lookup"><span data-stu-id="52893-132">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="52893-133">라이브 이벤트 일정을 사용 하지 않도록 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-133">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="52893-134">그런 다음 해당 사용자를 전역 정책에 할당 하 고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-134">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="52893-135">라이브 이벤트 일정을 허용 하는 정책을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-135">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="52893-136">라이브 이벤트 일정 사용을 설정 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-136">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="52893-137">그런 다음이 정책에 사용자를 할당 하 고 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-137">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="52893-138">라이브 이벤트에 참가할 수 있는 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="52893-138">Set who can join live events</span></span>
 
<span data-ttu-id="52893-139">사용자가 익명 사용자를 포함 하 여 모든 사용자가 참석할 수 있는 이벤트를 만드는 것을 허용 하도록 전역 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-139">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="52893-140">라이브 이벤트의 기록 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="52893-140">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="52893-141">이 설정은 팀에서 생성 된 이벤트에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52893-141">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="52893-142">라이브 이벤트 기록을 사용 하지 않도록 전역 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-142">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="52893-143">라이브 이벤트에서 실시간 캡션 및 자막 설정</span><span class="sxs-lookup"><span data-stu-id="52893-143">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="52893-144">이 설정은 팀에서 생성 된 이벤트에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52893-144">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="52893-145">이벤트 참석자에 대 한 실시간 캡션과 자막 (기록)을 설정 하도록 전역 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52893-145">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="52893-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="52893-146">Related topics</span></span>
- [<span data-ttu-id="52893-147">Teams 라이브 이벤트 설정하기</span><span class="sxs-lookup"><span data-stu-id="52893-147">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="52893-148">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="52893-148">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)

