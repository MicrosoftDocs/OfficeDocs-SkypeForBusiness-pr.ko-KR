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
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="054d8-103">PowerShell을 사용하여 Microsoft Teams에서 라이브 이벤트 정책 설정</span><span class="sxs-lookup"><span data-stu-id="054d8-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="054d8-104">Teams에서 라이브 이벤트에 Windows PowerShell 정책 설정을 설정하고 할당하려면 다음 cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="054d8-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="054d8-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="054d8-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="054d8-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="054d8-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="054d8-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="054d8-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="054d8-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="054d8-109">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="054d8-109">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="054d8-110">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="054d8-111">이러한 cmdlet을 실행하려면 먼저 비즈니스용 Skype Online PowerShell에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="054d8-112">자세한 내용은 [Microsoft 365 또는 Office 365 PowerShell을](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)사용하여 비즈니스용 Skype Online 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="054d8-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="054d8-113">사용자가 라이브 이벤트를 예약할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="054d8-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="054d8-114">이러한 예제는 Teams에서 생성되는 이벤트에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="054d8-115">외부 앱 또는 디바이스로 생성되는 이벤트의 경우 추가 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="054d8-116">자세한 내용은 사용자가 외부 앱 또는 디바이스로 생성한 이벤트를 예약할 [수 있도록 합니다.](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)</span><span class="sxs-lookup"><span data-stu-id="054d8-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="054d8-117">**사용자가 라이브 이벤트를 예약할 수 있도록 허용**</span><span class="sxs-lookup"><span data-stu-id="054d8-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="054d8-118">사용자에게 전역 정책이 할당된 경우 *AllowBroadcastScheduling* 매개 변수가 True로 설정되어 있는지 실행하고 *확인해야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="054d8-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="054d8-119">그런 다음 전역 정책에 사용자를 할당하고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="054d8-120">사용자 시나리오</span><span class="sxs-lookup"><span data-stu-id="054d8-120">User scenarios</span></span>
<span data-ttu-id="054d8-121">**조직의 모든 사용자가 라이브 이벤트를 예약할 수 있도록 하려는 경우**</span><span class="sxs-lookup"><span data-stu-id="054d8-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="054d8-122">사용자에게 전역 정책이 할당된 경우 *AllowBroadcastScheduling* \*이 True로 설정되어 있는지 확인하고 *실행합니다.*</span><span class="sxs-lookup"><span data-stu-id="054d8-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="054d8-123">사용자에게 전역 정책이 다른 정책이 할당된 경우 *-AllowBroadcastScheduling이 True로* 설정되어 있는지 실행하고 *확인해야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="054d8-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="054d8-124">**조직 전체에서 라이브 이벤트 일정을 사용하지 않도록 설정하려는 경우**</span><span class="sxs-lookup"><span data-stu-id="054d8-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="054d8-125">라이브 이벤트 일정을 사용하지 않도록 설정하고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="054d8-126">조직의 모든 사용자를 전역 정책에 할당하고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="054d8-127">**많은 수의 사용자가 라이브 이벤트를 예약하고 사용자 집합이 이벤트를 예약하지 못하게 하려는 경우**</span><span class="sxs-lookup"><span data-stu-id="054d8-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="054d8-128">*AllowBroadcastScheduling이 True로* 설정되어 있는지 실행하고 *확인:*</span><span class="sxs-lookup"><span data-stu-id="054d8-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="054d8-129">그런 다음, 전역 정책에 사용자 또는 사용자를 할당하고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="054d8-130">라이브 이벤트 일정을 허용하지 않는 새 정책을 만들고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="054d8-131">라이브 이벤트 일정을 사용하지 않도록 설정하고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="054d8-132">그런 다음, 이 정책에 사용자를 할당하고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="054d8-133">**많은 수의 사용자에 대해 라이브 이벤트 예약을 사용하지 않도록 설정하고 사용자 집합이 일정을 예약하도록 허용하려는 경우**</span><span class="sxs-lookup"><span data-stu-id="054d8-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="054d8-134">라이브 이벤트 일정을 사용하지 않도록 설정하고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="054d8-135">그런 다음 해당 사용자를 전역 정책에 할당하고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="054d8-136">라이브 이벤트 일정을 허용하는 정책을 만들고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="054d8-137">라이브 이벤트 일정을 사용하도록 설정하고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="054d8-138">그런 다음, 이 정책에 사용자를 할당하고 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="054d8-139">라이브 이벤트에 참가할 수 있는 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="054d8-139">Set who can join live events</span></span>
 
<span data-ttu-id="054d8-140">사용자가 익명 사용자를 포함하여 모든 사용자가 참석하고 실행할 수 있는 이벤트를 만들 수 있도록 전역 정책을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="054d8-141">라이브 이벤트에 대한 기록 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="054d8-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="054d8-142">이 설정은 Teams에서 생성되는 이벤트에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="054d8-143">라이브 이벤트에 대한 기록을 사용하지 않도록 전역 정책을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="054d8-144">라이브 이벤트에서 라이브 캡션 및 자막 설정</span><span class="sxs-lookup"><span data-stu-id="054d8-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="054d8-145">이 설정은 Teams에서 생성되는 이벤트에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="054d8-146">이벤트 참석자에 대한 라이브 캡션 및 자막(전사)을 설정하는 전역 정책을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="054d8-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="054d8-147">관련 항목</span><span class="sxs-lookup"><span data-stu-id="054d8-147">Related topics</span></span>
- [<span data-ttu-id="054d8-148">Teams 라이브 이벤트 설정하기</span><span class="sxs-lookup"><span data-stu-id="054d8-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="054d8-149">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="054d8-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)

