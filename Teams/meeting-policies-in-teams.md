---
title: 모임 정책 관리
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: 팀에서 모임 정책 설정을 관리 하는 방법에 대해 알아보세요.
ms.openlocfilehash: a3978b3615fabbff000a20d53408d4fbc1d98f12
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111712"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="af301-103">팀에서 모임 정책 관리</span><span class="sxs-lookup"><span data-stu-id="af301-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="af301-104">모임 정책은 조직의 사용자가 예약한 모임에 대해 모임 참가자가 사용할 수 있는 기능을 제어 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="af301-105">정책을 만들고 변경한 후 정책에 사용자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="af301-106">Microsoft 팀 관리 센터에서 또는 [PowerShell을 사용](teams-powershell-overview.md)하 여 모임 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-106">You manage meeting policies in the Microsoft Teams admin center or by [using PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="af301-107">모임 시작, 모임 중 또는 모임 이후 사용자의 모임 환경에 영향을 주는 다음과 같은 방법으로 정책을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="af301-108">구현 형식</span><span class="sxs-lookup"><span data-stu-id="af301-108">Implementation type</span></span>  |<span data-ttu-id="af301-109">설명</span><span class="sxs-lookup"><span data-stu-id="af301-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="af301-110">이끌이 별</span><span class="sxs-lookup"><span data-stu-id="af301-110">Per-organizer</span></span>    |<span data-ttu-id="af301-111">이끌이 별 정책을 구현 하는 경우 모든 모임 참가자는 해당 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="af301-112">예를 들어 사용자가 **자동으로** 허용 이끌이 정책 이며 사용자가 모임에 직접 참가 하는지 여부를 제어 하 고 정책에 할당 된 사용자가 예약한 모임에 대해 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="af301-113">사용자별</span><span class="sxs-lookup"><span data-stu-id="af301-113">Per-user</span></span>    |<span data-ttu-id="af301-114">사용자별 정책을 구현할 때, 이끌이 및/또는 모임 참가자에 대 한 특정 기능을 제한 하는 사용자별 정책만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="af301-115">예를 들어 **모임 시작 허용** 은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-115">For example, **Allow Meet now** is a per-user policy.</span></span>     |
|<span data-ttu-id="af301-116">이끌이와 사용자 단위</span><span class="sxs-lookup"><span data-stu-id="af301-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="af301-117">이끌이 및 사용자별 정책 조합을 구현 하는 경우 특정 기능은 해당 정책 및 이끌이의 정책에 따라 모임 참가자에 대해 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="af301-118">예를 들어 **클라우드 기록은 허용** -이끌이 및 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="af301-119">이 설정을 사용 하 여 모임 이끌이 및 참가자가 녹음/녹화를 시작 하 고 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span> 

<span data-ttu-id="af301-120">기본적으로 Global (조직 전체 기본값) 이라는 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="af301-120">By default, a policy named Global (org-wide default) is created.</span></span> <span data-ttu-id="af301-121">조직의 모든 사용자에 게이 모임 정책이 기본적으로 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-121">All users in your organization will be assigned this meeting policy by default.</span></span> <span data-ttu-id="af301-122">이 정책을 변경 하거나 하나 이상의 사용자 지정 정책을 만들어 사용자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-122">You can either make changes to this policy or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="af301-123">사용자 지정 정책을 만들 때 사용자가 특정 기능을 사용할 수 있도록 허용 하거나 금지할 수 있으며 설정을 적용할 사용자 하나 이상에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-123">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span> 

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="af301-124">모임 정책 변경 또는 만들기</span><span class="sxs-lookup"><span data-stu-id="af301-124">Change or create a meeting policy</span></span>

<span data-ttu-id="af301-125">모임 정책을 변경 하거나 만들려면 Microsoft 팀 관리 센터 > **모임** > **모임 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-125">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="af301-126">목록에서 정책을 선택 하거나 **새 정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-126">Select a policy from the list or select **New policy**.</span></span> <span data-ttu-id="af301-127">새 정책을 만드는 경우 이름 및 설명을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-127">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="af301-128">이름은 특수 문자를 포함 하거나 64 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-128">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="af301-129">설정을 선택 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-129">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="af301-130">예를 들어 사용자가 여러 명 있고 모임에 필요한 대역폭의 양을 제한 하려고 한다고 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="af301-130">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="af301-131">"제한 된 대역폭" 이라는 새 사용자 지정 정책을 만들고 다음 설정을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-131">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="af301-132">**오디오 & 비디오**:</span><span class="sxs-lookup"><span data-stu-id="af301-132">Under **Audio & video**:</span></span>
- <span data-ttu-id="af301-133">구름 기록 해제</span><span class="sxs-lookup"><span data-stu-id="af301-133">Turn off cloud recording</span></span>
- <span data-ttu-id="af301-134">IP 비디오 허용 해제</span><span class="sxs-lookup"><span data-stu-id="af301-134">Turn off Allow IP video</span></span>

<span data-ttu-id="af301-135">**콘텐츠 공유**에서:</span><span class="sxs-lookup"><span data-stu-id="af301-135">Under **Content sharing**:</span></span>
- <span data-ttu-id="af301-136">화면 공유 모드 해제</span><span class="sxs-lookup"><span data-stu-id="af301-136">Disable screen sharing mode</span></span>
- <span data-ttu-id="af301-137">화이트 보드 끄기</span><span class="sxs-lookup"><span data-stu-id="af301-137">Turn off whiteboard</span></span>
- <span data-ttu-id="af301-138">공유 메모 해제</span><span class="sxs-lookup"><span data-stu-id="af301-138">Turn off shared notes</span></span>

<span data-ttu-id="af301-139">그런 다음 사용자에 게 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-139">Then assign the policy to the users.</span></span>

> [!NOTE] 
> <span data-ttu-id="af301-140">사용자는 한 번에 하나의 모임 정책만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-140">A user can be assigned only one meeting policy at a time.</span></span> 

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="af301-141">사용자에 게 모임 정책 할당</span><span class="sxs-lookup"><span data-stu-id="af301-141">Assign a meeting policy to users</span></span>

<span data-ttu-id="af301-142">한 사용자에 게 정책을 적용 하는 경우 왼쪽 탐색 창에서 **사용자** 를 선택한 다음 사용자의 표시 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-142">If you're applying the policy to one user, select **Users** on the left navigation pane, and then click the user's display name.</span></span> <span data-ttu-id="af301-143">사용자의 페이지에서 **할당 된 정책**옆에 있는 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-143">On the user's page, next to **Assigned policies**, select **Edit**.</span></span> <span data-ttu-id="af301-144">그런 다음 **사용자 정책 편집** 창의 **모임 정책**아래에 있는 드롭다운 목록에서 모임 정책을 선택한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-144">Then, in the **Edit user policies** pane, under **Meeting policy**, select the meeting policy from the drop-down list, and then select **Save**.</span></span> <span data-ttu-id="af301-145">사용자 목록에서 정책을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-145">You can also assign policies from the list of users.</span></span> <span data-ttu-id="af301-146">이렇게 하려면 사용자의 표시 이름 왼쪽을 클릭 하 여 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-146">To do this, select the user by clicking to the left of the user's display name.</span></span> <span data-ttu-id="af301-147">**설정 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-147">Select **Edit settings**.</span></span> <span data-ttu-id="af301-148">그런 다음 **설정 편집** 창의 **모임 정책**아래에 있는 드롭다운 목록에서 정책을 선택한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-148">Then, on the **Edit settings** pane, under **Meeting policy**, select the policy from the drop-down list, and then select **Save**.</span></span> 
 
<span data-ttu-id="af301-149">정책을 두 명 이상의 사용자에 게 적용 하는 경우 왼쪽 탐색 창에서 **사용자** 를 선택한 다음 사용자 이름 왼쪽을 클릭 하 여 각 사용자를 선택 하 고 **설정 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-149">If you're applying a policy to more than one user, select **Users** on the left navigation pane, and then select each user by clicking to the left of the user name, and then click **Edit settings**.</span></span> <span data-ttu-id="af301-150">**설정 편집** 창의 **모임 정책**아래에 있는 드롭다운 목록에서 정책을 선택한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-150">On the **Edit Settings** pane, under **Meeting policy**, select the policy from the drop-down list, and then select **Save**.</span></span>
 
<span data-ttu-id="af301-151">다음과 같이 한 명 이상의 사용자에 게 모임 정책을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-151">You can also assign a meeting policy to one or more users as follows:</span></span>

1. <span data-ttu-id="af301-152">**Microsoft 팀 관리 센터** > **모임** > **정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-152">Go to **Microsoft Teams admin center** > **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="af301-153">정책 이름 왼쪽에 있는을 클릭 하 여 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-153">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="af301-154">**사용자 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-154">Select **Manage users**.</span></span>
4. <span data-ttu-id="af301-155">**사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-155">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="af301-156">추가 하려는 각 사용자에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-156">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="af301-157">사용자 추가를 마쳤으면 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-157">When you're finished adding users, select **Save**.</span></span>
 
> [!NOTE] 
> <span data-ttu-id="af301-158">사용자가 할당 된 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-158">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="af301-159">먼저 영향을 받는 모든 사용자에 게 다른 정책을 할당 한 다음 원래 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-159">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>
 
## <a name="meeting-policy-settings"></a><span data-ttu-id="af301-160">모임 정책 설정</span><span class="sxs-lookup"><span data-stu-id="af301-160">Meeting policy settings</span></span>

<span data-ttu-id="af301-161">**모임 정책** 페이지의 기존 정책을 선택 하거나 새 **정책을 선택 하 여 새** 정책을 추가 하면 다음에 대 한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-161">When you select an existing policy on the **Meeting policies** page or select **New policy** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="af301-162">일반</span><span class="sxs-lookup"><span data-stu-id="af301-162">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="af301-163">오디오 & 비디오</span><span class="sxs-lookup"><span data-stu-id="af301-163">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="af301-164">콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="af301-164">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="af301-165">참가자가 게스트를 &</span><span class="sxs-lookup"><span data-stu-id="af301-165">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="af301-166"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="af301-166"></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="af301-167">모임 정책 설정-일반</span><span class="sxs-lookup"><span data-stu-id="af301-167">Meeting policy settings - General</span></span>

- [<span data-ttu-id="af301-168">채널에서 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="af301-168">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="af301-169">지금 비공개 모임 허용</span><span class="sxs-lookup"><span data-stu-id="af301-169">Allow private Meet now</span></span>](#allow-private-meet-now)
- [<span data-ttu-id="af301-170">Outlook 추가 기능 허용</span><span class="sxs-lookup"><span data-stu-id="af301-170">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="af301-171">채널 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="af301-171">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="af301-172">개인 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="af301-172">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="af301-173">채널에서 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="af301-173">Allow Meet now in channels</span></span>

<span data-ttu-id="af301-174">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-174">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="af301-175">이 설정은 사용자가 팀 채널에서 임시 모임을 시작할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-175">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="af301-176">이 기능을 설정 하면 사용자가 팀 채널에서 메시지를 게시할 때 작성 **상자 아래에 있는 모임 시작** 을 클릭 하 여 채널의 임시 모임을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-176">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** beneath the compose box to start an ad hoc meeting in the channel.</span></span>

![메시지 아래에 모임 시작 아이콘을 표시 하는 스크린샷](media/meeting-policies-meet-now.png)

### <a name="allow-private-meet-now"></a><span data-ttu-id="af301-178">지금 비공개 모임 허용</span><span class="sxs-lookup"><span data-stu-id="af301-178">Allow private Meet now</span></span>

<span data-ttu-id="af301-179">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-179">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="af301-180">이 설정은 사용자가 임시 비공개 모임을 시작할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-180">This setting controls whether a user can start an ad hoc private meeting.</span></span>  

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="af301-181">Outlook 추가 기능 허용</span><span class="sxs-lookup"><span data-stu-id="af301-181">Allow the Outlook add-in</span></span>

<span data-ttu-id="af301-182">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-182">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="af301-183">이 설정은 Outlook (Windows, Mac, 웹, 모바일)에서 팀 모임을 예약할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-183">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![새 모임 예약 기능을 보여 주는 스크린샷](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="af301-185">이 기능을 해제 하면 사용자가 Outlook에서 새 모임을 만들 때 팀 회의를 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-185">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="af301-186">예를 들어 Windows의 Outlook에서는 **새 팀 모임** 옵션이 리본 메뉴에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-186">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="af301-187">채널 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="af301-187">Allow channel meeting scheduling</span></span>

<span data-ttu-id="af301-188">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-188">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="af301-189">이 설정은 사용자가 팀 채널에서 모임을 예약할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-189">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="af301-190">이 기능을 해제 한 경우 팀 채널에서 모임을 시작할 때 사용자가 **모임 예약** 옵션을 사용할 수 없으며 팀의 모임에서 모임을 예약 하는 경우 사용자가 모임 **에 대 한 채널 선택** 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-190">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Select a channel to meet** option won't be available to the user when they schedule a meeting from Meetings in Teams.</span></span>

![팀의 모임 예약 옵션을 보여 주는 스크린샷](media/meeting-policies-schedule-a-meeting.png)

![모임에 적용할 채널 선택 옵션을 보여 주는 스크린샷](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="af301-193">개인 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="af301-193">Allow scheduling private meetings</span></span>

<span data-ttu-id="af301-194">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-194">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="af301-195">이 설정은 사용자가 팀에서 비공개 모임을 예약할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-195">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="af301-196">모임이 팀의 채널에 게시 되지 않은 경우 비공개 모임입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-196">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="af301-197">**비공개 모임 예약 허용** 을 해제 하 고 **채널 모임 예약을 허용**하면 **모임 예약** 옵션을 사용할 수 없으며 사용자가 팀에서 모임을 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-197">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Schedule a meeting** option won't be available and users will be unable to schedule meetings in Teams.</span></span>

<span data-ttu-id="af301-198"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="af301-198"></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="af301-199">모임 정책 설정-오디오 & 비디오</span><span class="sxs-lookup"><span data-stu-id="af301-199">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="af301-200">내용 허용</span><span class="sxs-lookup"><span data-stu-id="af301-200">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="af301-201">클라우드 기록 허용</span><span class="sxs-lookup"><span data-stu-id="af301-201">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="af301-202">IP 비디오 허용</span><span class="sxs-lookup"><span data-stu-id="af301-202">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="af301-203">미디어 비트 전송률 (KBs)</span><span class="sxs-lookup"><span data-stu-id="af301-203">Media bit rate (KBs)</span></span>](#media-bit-rate-kbs)
- [<span data-ttu-id="af301-204">실시간 캡션 사용 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="af301-204">Enable live captions (preview)</span></span>](#enable-live-captions-preview)

### <a name="allow-transcription"></a><span data-ttu-id="af301-205">내용 허용</span><span class="sxs-lookup"><span data-stu-id="af301-205">Allow transcription</span></span>

<span data-ttu-id="af301-206">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-206">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="af301-207">이 설정은 모임 녹음/녹화를 재생 하는 동안 캡션과 기록 기능을 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-207">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="af301-208">이 기능을 해제 하면 모임 녹음/녹화를 재생 하는 동안 **검색** 및 **참조** 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-208">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="af301-209">녹음/녹화를 시작한 사람에 게는 녹음/녹화가 포함 되도록이 설정이 켜져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-209">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="af301-210">기록 된 모임에 대 한 정보는 현재 팀의 언어를 영어로 설정한 경우와 모임에서 영어를 사용 하 고 있는 사용자만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-210">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![모임의 기록 옵션을 보여 주는 스크린샷](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="af301-212">클라우드 기록 허용</span><span class="sxs-lookup"><span data-stu-id="af301-212">Allow cloud recording</span></span>

<span data-ttu-id="af301-213">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-213">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="af301-214">이 설정은 사용자의 모임을 녹화할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-214">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="af301-215">참가자에 대해 정책 설정이 설정 된 경우와 다른 모임 참가자가 같은 조직의 인증 된 사용자 인 경우 기록을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-215">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="af301-216">페더레이션 및 익명 사용자 등 조직 외부의 사용자가 녹음/녹화를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-216">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="af301-217">게스트 사용자는 녹음/녹화를 시작 하거나 중지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-217">Guest users can't start or stop the recording.</span></span> 

![기록 옵션을 보여 주는 스크린샷](media/meeting-policies-recording.png)

<span data-ttu-id="af301-219">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-219">Let's look at the following example.</span></span>

|<span data-ttu-id="af301-220">사용자</span><span class="sxs-lookup"><span data-stu-id="af301-220">User</span></span> |<span data-ttu-id="af301-221">모임 정책</span><span class="sxs-lookup"><span data-stu-id="af301-221">Meeting policy</span></span>  |<span data-ttu-id="af301-222">클라우드 기록 허용</span><span class="sxs-lookup"><span data-stu-id="af301-222">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="af301-223">Daniela</span><span class="sxs-lookup"><span data-stu-id="af301-223">Daniela</span></span> | <span data-ttu-id="af301-224">전역</span><span class="sxs-lookup"><span data-stu-id="af301-224">Global</span></span>   | <span data-ttu-id="af301-225">해제</span><span class="sxs-lookup"><span data-stu-id="af301-225">False</span></span> |
|<span data-ttu-id="af301-226">Amanda</span><span class="sxs-lookup"><span data-stu-id="af301-226">Amanda</span></span> | <span data-ttu-id="af301-227">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="af301-227">Location1MeetingPolicy</span></span> | <span data-ttu-id="af301-228">False</span><span class="sxs-lookup"><span data-stu-id="af301-228">True</span></span>|
|<span data-ttu-id="af301-229">John (외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="af301-229">John (external user)</span></span> | <span data-ttu-id="af301-230">해당 없음</span><span class="sxs-lookup"><span data-stu-id="af301-230">Not applicable</span></span> | <span data-ttu-id="af301-231">해당 없음</span><span class="sxs-lookup"><span data-stu-id="af301-231">Not applicable</span></span>|

<span data-ttu-id="af301-232">Daniela에서 구성한 모임은 기록 하 고 Amanda 수 있으며, 정책 설정을 사용 하도록 설정한 경우 Daniela로 구성 된 모임을 녹화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-232">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="af301-233">Amanda에서 구성한 모임은 녹화할 수 있지만, Daniela는 정책 설정을 사용 하지 않도록 설정 하 고 외부 사용자 인 John은 Amanda으로 구성 된 모임을 기록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-233">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="af301-234">클라우드 모임 기록에 대해 자세히 알아보려면 [팀 클라우드 모임 기록을](cloud-recording.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af301-234">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="af301-235">IP 비디오 허용</span><span class="sxs-lookup"><span data-stu-id="af301-235">Allow IP video</span></span>

<span data-ttu-id="af301-236">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-236">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="af301-237">비디오는 모임에 대 한 주요 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-237">Video is a key component to meetings.</span></span> <span data-ttu-id="af301-238">일부 조직에서는 관리자가 어떤 사용자의 모임이 비디오를 보유 하 고 있는지 더 자세히 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-238">In some organizations, admins might want more control over which users’ meetings have video.</span></span> <span data-ttu-id="af301-239">이 설정은 사용자가 호스트 하는 모임 및 사용자가 시작한 1:1 통화 및 그룹 통화에서 비디오를 켤 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-239">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="af301-240">이 정책을 사용 하도록 설정한 사용자가 구성한 모임에는 모임 참가자가 정책을 사용 하도록 설정한 경우 모임 참가자가 모임에서 비디오 공유를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-240">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="af301-241">배정 된 정책이 없는 모임 참가자 (예: 익명 및 페더레이션 참가자)는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-241">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![오디오 및 비디오 설정을 사용 하 여 모임을 보여 주는 스크린샷](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="af301-243">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-243">Let's look at the following example.</span></span>

|<span data-ttu-id="af301-244">사용자</span><span class="sxs-lookup"><span data-stu-id="af301-244">User</span></span> |<span data-ttu-id="af301-245">모임 정책</span><span class="sxs-lookup"><span data-stu-id="af301-245">Meeting policy</span></span>  |<span data-ttu-id="af301-246">IP 영상 허용</span><span class="sxs-lookup"><span data-stu-id="af301-246">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="af301-247">Daniela</span><span class="sxs-lookup"><span data-stu-id="af301-247">Daniela</span></span>   | <span data-ttu-id="af301-248">전역</span><span class="sxs-lookup"><span data-stu-id="af301-248">Global</span></span>   | <span data-ttu-id="af301-249">False</span><span class="sxs-lookup"><span data-stu-id="af301-249">True</span></span>        |
|<span data-ttu-id="af301-250">Amanda</span><span class="sxs-lookup"><span data-stu-id="af301-250">Amanda</span></span>    | <span data-ttu-id="af301-251">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="af301-251">Location1MeetingPolicy</span></span>        | <span data-ttu-id="af301-252">해제</span><span class="sxs-lookup"><span data-stu-id="af301-252">False</span></span>      |

<span data-ttu-id="af301-253">Daniela에서 호스팅하는 모임은 영상 통화를 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-253">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="af301-254">Daniela 모임에 참가 하 고 비디오를 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-254">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="af301-255">Amanda의 정책이 비디오를 허용 하지 않도록 설정 되어 있기 때문에 Daniela 모임에서 비디오를 켤 수 없습니다 Amanda.</span><span class="sxs-lookup"><span data-stu-id="af301-255">Amanda can't turn on video in Daniela's meeting because Amanda’s policy is set to not allow video.</span></span> <span data-ttu-id="af301-256">Amanda는 모임의 다른 참가자가 공유 하는 비디오를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-256">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="af301-257">Amanda에서 호스팅하는 모임에서 할당 된 비디오 정책에 관계 없이 비디오를 켤 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-257">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="af301-258">이는 Daniela에서 Amanda의 모임에서 비디오를 켤 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-258">This means Daniela can't turn on video in Amanda’s meetings.</span></span>  

<span data-ttu-id="af301-259">Daniela에서 비디오를 사용 하 여 Amanda를 호출 하는 경우 Amanda는 오디오 만으로 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-259">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="af301-260">통화가 연결 되 면 Amanda에서 Daniela의 비디오를 볼 수 있지만 영상 통화는 켜지 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-260">When the call is connected, Amanda can see Daniela’s video, but can't turn on video.</span></span> <span data-ttu-id="af301-261">Amanda에서 Daniela를 호출 하는 경우 Daniela는 비디오 및 오디오로 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-261">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="af301-262">통화가 연결 되 면 필요에 따라 Daniela에서 비디오를 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-262">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="af301-263">미디어 비트 전송률 (KBs)</span><span class="sxs-lookup"><span data-stu-id="af301-263">Media bit rate (KBs)</span></span>

<span data-ttu-id="af301-264">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-264">This is a per-user policy.</span></span> <span data-ttu-id="af301-265">이 설정에 따라 사용자에 대 한 통화 및 모임에서 오디오, 비디오 및 비디오 기반 앱 공유 전송의 미디어 비트 전송률이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-265">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="af301-266">통화 또는 모임에서 사용자의 업링크 및 다운 링크 미디어 트래버스 둘 다에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-266">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="af301-267">이 설정을 사용 하면 조직의 대역폭을 관리 하는 방법을 세부적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-267">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="af301-268">사용자에 게 필요한 모임 시나리오에 따라 좋은 품질 환경을 위해 적절 한 대역폭을 확보 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-268">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="af301-269">최소값은 30kbps이 고 최대값은 모임 시나리오에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="af301-269">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="af301-270">팀에서 좋은 음질의 모임, 통화, 라이브 이벤트에 권장 되는 최소 대역폭에 대해 자세히 알아보려면 [대역폭 요구 사항을](prepare-network.md#bandwidth-requirements)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af301-270">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="af301-271">모임에 대 한 대역폭이 충분 하지 않은 경우 참가자는 네트워크 품질이 좋지 않다는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-271">If there isn’t enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="af301-272">CEO 보드 모임 및 팀 라이브 이벤트와 같이 고품질의 비디오 환경을 필요로 하는 모임의 경우 대역폭을 10mbps로 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-272">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="af301-273">최대 환경이 설정 된 경우에도 시나리오에 따라 특정 네트워크 조건이 감지 되는 경우 팀 미디어 스택이 낮은 대역폭 조건에 적응 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-273">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

### <a name="enable-live-captions-preview"></a><span data-ttu-id="af301-274">실시간 캡션 사용 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="af301-274">Enable live captions (preview)</span></span>

<span data-ttu-id="af301-275">이것은 사용자별 정책으로 모임 중에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-275">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="af301-276">이 설정은 사용자가 참석할는 모임에서 실시간 **캡션 켜기** 옵션을 사용 하 여 live 캡션을 켜고 끌 것인지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-276">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![라이브 캡션 켜기 옵션을 보여 주는 스크린샷](media/meeting-policies-live-captions.png)

|<span data-ttu-id="af301-278">값 설정</span><span class="sxs-lookup"><span data-stu-id="af301-278">Setting value</span></span> |<span data-ttu-id="af301-279">결과가</span><span class="sxs-lookup"><span data-stu-id="af301-279">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="af301-280">**사용 하지 않도록 설정 하 고 사용자가 무시할 수 있음**</span><span class="sxs-lookup"><span data-stu-id="af301-280">**Disabled and the user can override**</span></span>     | <span data-ttu-id="af301-281">Live 캡션은 모임 중에 사용자에 대해 자동으로 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-281">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="af301-282">사용자는 오버플로 (**...**) 메뉴에서 **라이브 캡션 켜기** 옵션을 표시 하 여 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-282">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="af301-283">이는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-283">This is the default setting.</span></span> |
|<span data-ttu-id="af301-284">**비활성화**</span><span class="sxs-lookup"><span data-stu-id="af301-284">**Disabled**</span></span>     | <span data-ttu-id="af301-285">모임 중에는 사용자가 실시간 캡션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-285">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="af301-286">사용자는이 옵션을 켤 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-286">The user doesn't have the option to turn them on.</span></span>          |


<span data-ttu-id="af301-287"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="af301-287"></span></span>

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="af301-288">모임 정책 설정-콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="af301-288">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="af301-289">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="af301-289">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="af301-290">참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="af301-290">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="af301-291">외부 참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="af301-291">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="af301-292">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="af301-292">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="af301-293">화이트 보드 허용</span><span class="sxs-lookup"><span data-stu-id="af301-293">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="af301-294">공유 메모 허용</span><span class="sxs-lookup"><span data-stu-id="af301-294">Allow shared notes</span></span>](#allow-shared-notes)
- [<span data-ttu-id="af301-295">모임에서 채팅 허용 (예정 대로)</span><span class="sxs-lookup"><span data-stu-id="af301-295">Allow chat in meetings (coming soon)</span></span>](#allow-chat-in-meetings-coming-soon)

### <a name="screen-sharing-mode"></a><span data-ttu-id="af301-296">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="af301-296">Screen sharing mode</span></span>

<span data-ttu-id="af301-297">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-297">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="af301-298">이 설정은 사용자의 모임에서 데스크톱 및/또는 창 공유를 허용할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-298">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="af301-299">배정 된 정책이 없는 모임 참가자 (예: 익명, 게스트, B2B, 페더레이션 참가자)는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-299">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="af301-300">값 설정</span><span class="sxs-lookup"><span data-stu-id="af301-300">Setting value</span></span> |<span data-ttu-id="af301-301">결과가</span><span class="sxs-lookup"><span data-stu-id="af301-301">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="af301-302">**전체 화면**</span><span class="sxs-lookup"><span data-stu-id="af301-302">**Entire screen**</span></span>    | <span data-ttu-id="af301-303">모임에서 전체 데스크톱 공유 및 응용 프로그램 공유를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-303">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="af301-304">**단일 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="af301-304">**Single application**</span></span>   | <span data-ttu-id="af301-305">모임에서 응용 프로그램 공유가 허용 됨</span><span class="sxs-lookup"><span data-stu-id="af301-305">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="af301-306">**비활성화**</span><span class="sxs-lookup"><span data-stu-id="af301-306">**Disabled**</span></span>     |<span data-ttu-id="af301-307">모임에서 화면 공유 및 응용 프로그램 공유 기능을 해제 했습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-307">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="af301-308">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-308">Let's look at the following example.</span></span>

|<span data-ttu-id="af301-309">사용자</span><span class="sxs-lookup"><span data-stu-id="af301-309">User</span></span> |<span data-ttu-id="af301-310">모임 정책</span><span class="sxs-lookup"><span data-stu-id="af301-310">Meeting policy</span></span> |<span data-ttu-id="af301-311">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="af301-311">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="af301-312">Daniela</span><span class="sxs-lookup"><span data-stu-id="af301-312">Daniela</span></span>  | <span data-ttu-id="af301-313">전역</span><span class="sxs-lookup"><span data-stu-id="af301-313">Global</span></span>   | <span data-ttu-id="af301-314">전체 화면</span><span class="sxs-lookup"><span data-stu-id="af301-314">Entire screen</span></span> |
|<span data-ttu-id="af301-315">Amanda</span><span class="sxs-lookup"><span data-stu-id="af301-315">Amanda</span></span>   | <span data-ttu-id="af301-316">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="af301-316">Location1MeetingPolicy</span></span>  | <span data-ttu-id="af301-317">비활성화</span><span class="sxs-lookup"><span data-stu-id="af301-317">Disabled</span></span> |

<span data-ttu-id="af301-318">Daniela에서 호스팅하는 모임은 모임 참가자가 전체 화면 또는 특정 응용 프로그램을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-318">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="af301-319">Amanda 참가 Daniela의 모임이 Amanda, 화면을 공유할 수 없거나, 정책 설정에 따라 특정 응용 프로그램을 사용 하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-319">If Amanda joins Daniela’s meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="af301-320">Amanda에서 호스트 하는 모임에서는 자신에 게 할당 된 화면 공유 모드 정책에 관계 없이 화면 또는 단일 응용 프로그램을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-320">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="af301-321">즉, Daniela는 Amanda 모임의 화면 또는 단일 응용 프로그램을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-321">This means that Daniela can't share her screen or a single application in Amanda’s meetings.</span></span>  

<span data-ttu-id="af301-322">현재 사용자는 Google Chrome을 사용 하는 경우 팀 모임에서 비디오를 재생 하거나 화면을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-322">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="af301-323">참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="af301-323">Allow a participant to give or request control</span></span>

<span data-ttu-id="af301-324">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-324">This is a per-user policy.</span></span> <span data-ttu-id="af301-325">이 설정은 사용자가 공유 데스크톱 또는 창을 다른 모임 참가자에 게 제어권을 부여할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-325">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="af301-326">컨트롤을 제공 하려면 화면 위쪽을 마우스로 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="af301-326">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="af301-327">사용자에 대해이 설정이 설정 된 경우 **제어권 제공** 옵션이 공유 세션의 위쪽 표시줄에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-327">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![제어권 제공 옵션을 보여 주는 스크린샷](media/meeting-policies-give-control.png)

<span data-ttu-id="af301-329">사용자에 대해 설정이 꺼져 있으면 **제어권 제공** 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-329">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![제어권 부여 옵션을 사용할 수 없음을 보여 주는 스크린샷](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="af301-331">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-331">Let's look at the following example.</span></span>

|<span data-ttu-id="af301-332">사용자</span><span class="sxs-lookup"><span data-stu-id="af301-332">User</span></span> |<span data-ttu-id="af301-333">모임 정책</span><span class="sxs-lookup"><span data-stu-id="af301-333">Meeting policy</span></span>  |<span data-ttu-id="af301-334">참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="af301-334">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="af301-335">Daniela</span><span class="sxs-lookup"><span data-stu-id="af301-335">Daniela</span></span>   | <span data-ttu-id="af301-336">전역</span><span class="sxs-lookup"><span data-stu-id="af301-336">Global</span></span>   | <span data-ttu-id="af301-337">False</span><span class="sxs-lookup"><span data-stu-id="af301-337">True</span></span>       |
|<span data-ttu-id="af301-338">Babek</span><span class="sxs-lookup"><span data-stu-id="af301-338">Babek</span></span>    | <span data-ttu-id="af301-339">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="af301-339">Location1MeetingPolicy</span></span>        | <span data-ttu-id="af301-340">해제</span><span class="sxs-lookup"><span data-stu-id="af301-340">False</span></span>   |

<span data-ttu-id="af301-341">Daniela는 다른 참가자에 게 제어권을 부여할 수 없기 때문에 Babek에서 구성한 모임의 다른 참가자에 게 공유 데스크톱 또는 창을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-341">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

> [!NOTE]
> <span data-ttu-id="af301-342">공유 중 공유 콘텐츠를 관리 하 고 제어 하려면 두 파티 모두 팀 데스크톱 클라이언트를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-342">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="af301-343">파티 중 하나가 브라우저에서 팀을 실행 중인 경우 컨트롤은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-343">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="af301-344">이 문제는 해결 하려는 기술 제한 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-344">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="af301-345">외부 참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="af301-345">Allow an external participant to give or request control</span></span>

<span data-ttu-id="af301-346">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-346">This is a per-user policy.</span></span> <span data-ttu-id="af301-347">이 설정은 모임의 외부 참가자가 모임의 다른 참가자에 게 공유 데스크톱 또는 창을 제어할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-347">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="af301-348">팀 회의의 외부 참가자는 다음과 같이 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-348">External participants in Teams meetings can be categorized as follows:</span></span>  

   - <span data-ttu-id="af301-349">익명 사용자</span><span class="sxs-lookup"><span data-stu-id="af301-349">Anonymous user</span></span>
   - <span data-ttu-id="af301-350">게스트 사용자</span><span class="sxs-lookup"><span data-stu-id="af301-350">Guest users</span></span>  
   - <span data-ttu-id="af301-351">B2B 사용자</span><span class="sxs-lookup"><span data-stu-id="af301-351">B2B user</span></span>
   - <span data-ttu-id="af301-352">페더레이션 사용자</span><span class="sxs-lookup"><span data-stu-id="af301-352">Federated user</span></span>  

<span data-ttu-id="af301-353">공유 된 사용자가 외부 참가자가 조직에서 **제어권을 부여 하거나 요청할 수 있도록 허용을** 제어 하도록 설정 되어 있는 동안 페더레이션 사용자가 해당 사용자에 게 제어권을 부여할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="af301-353">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="af301-354">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="af301-354">Allow PowerPoint sharing</span></span>

<span data-ttu-id="af301-355">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-355">This is a per-user policy.</span></span> <span data-ttu-id="af301-356">이 설정은 사용자가 모임에서 PowerPoint 슬라이드 데크를 공유할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-356">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="af301-357">익명, 게스트, 페더레이션 사용자를 비롯 한 외부 사용자가 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-357">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="af301-358">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-358">Let's look at the following example.</span></span>

|<span data-ttu-id="af301-359">사용자</span><span class="sxs-lookup"><span data-stu-id="af301-359">User</span></span> |<span data-ttu-id="af301-360">모임 정책</span><span class="sxs-lookup"><span data-stu-id="af301-360">Meeting policy</span></span>  |<span data-ttu-id="af301-361">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="af301-361">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="af301-362">Daniela</span><span class="sxs-lookup"><span data-stu-id="af301-362">Daniela</span></span>   | <span data-ttu-id="af301-363">전역</span><span class="sxs-lookup"><span data-stu-id="af301-363">Global</span></span>   | <span data-ttu-id="af301-364">False</span><span class="sxs-lookup"><span data-stu-id="af301-364">True</span></span>       |
|<span data-ttu-id="af301-365">Amanda</span><span class="sxs-lookup"><span data-stu-id="af301-365">Amanda</span></span>   | <span data-ttu-id="af301-366">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="af301-366">Location1MeetingPolicy</span></span>        | <span data-ttu-id="af301-367">해제</span><span class="sxs-lookup"><span data-stu-id="af301-367">False</span></span>   |

<span data-ttu-id="af301-368">Amanda 모임 이끌이 인 경우에도 모임에서 PowerPoint 슬라이드 데크를 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-368">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="af301-369">Daniela는 모임이 Amanda으로 구성 된 경우에도 PowerPoint 슬라이드 데크를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-369">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="af301-370">Amanda는 PowerPoint 슬라이드 데크를 공유할 수는 없지만 모임에서 다른 사용자가 공유한 PowerPoint 슬라이드 데크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-370">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="af301-371">화이트 보드 허용</span><span class="sxs-lookup"><span data-stu-id="af301-371">Allow whiteboard</span></span>

<span data-ttu-id="af301-372">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-372">This is a per-user policy.</span></span> <span data-ttu-id="af301-373">이 설정은 사용자가 모임에서 화이트 보드를 공유할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-373">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="af301-374">익명, B2B, 페더레이션 사용자 등의 외부 사용자는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-374">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="af301-375">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-375">Let's look at the following example.</span></span>

|<span data-ttu-id="af301-376">사용자</span><span class="sxs-lookup"><span data-stu-id="af301-376">User</span></span> |<span data-ttu-id="af301-377">모임 정책</span><span class="sxs-lookup"><span data-stu-id="af301-377">Meeting policy</span></span>  |<span data-ttu-id="af301-378">화이트 보드 허용</span><span class="sxs-lookup"><span data-stu-id="af301-378">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="af301-379">Daniela</span><span class="sxs-lookup"><span data-stu-id="af301-379">Daniela</span></span>   | <span data-ttu-id="af301-380">전역</span><span class="sxs-lookup"><span data-stu-id="af301-380">Global</span></span>   | <span data-ttu-id="af301-381">False</span><span class="sxs-lookup"><span data-stu-id="af301-381">True</span></span>       |
|<span data-ttu-id="af301-382">Amanda</span><span class="sxs-lookup"><span data-stu-id="af301-382">Amanda</span></span>   | <span data-ttu-id="af301-383">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="af301-383">Location1MeetingPolicy</span></span>        | <span data-ttu-id="af301-384">해제</span><span class="sxs-lookup"><span data-stu-id="af301-384">False</span></span>   |

<span data-ttu-id="af301-385">Amanda 모임 이끌이 인 경우에도 모임에서 화이트 보드를 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-385">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="af301-386">Daniela는 모임이 Amanda으로 구성 된 경우에도 화이트 보드를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-386">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="af301-387">공유 메모 허용</span><span class="sxs-lookup"><span data-stu-id="af301-387">Allow shared notes</span></span>

<span data-ttu-id="af301-388">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-388">This is a per-user policy.</span></span> <span data-ttu-id="af301-389">이 설정은 사용자가 모임에서 노트를 만들고 공유할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-389">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="af301-390">익명, B2B, 페더레이션 사용자 등의 외부 사용자는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-390">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="af301-391">**모임 메모** 탭은 현재 20 명 미만의 참가자가 있는 모임 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-391">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span> 

<span data-ttu-id="af301-392">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-392">Let's look at the following example.</span></span>

|<span data-ttu-id="af301-393">사용자</span><span class="sxs-lookup"><span data-stu-id="af301-393">User</span></span> |<span data-ttu-id="af301-394">모임 정책</span><span class="sxs-lookup"><span data-stu-id="af301-394">Meeting policy</span></span>  |<span data-ttu-id="af301-395">공유 메모 허용</span><span class="sxs-lookup"><span data-stu-id="af301-395">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="af301-396">Daniela</span><span class="sxs-lookup"><span data-stu-id="af301-396">Daniela</span></span>   | <span data-ttu-id="af301-397">전역</span><span class="sxs-lookup"><span data-stu-id="af301-397">Global</span></span>   | <span data-ttu-id="af301-398">False</span><span class="sxs-lookup"><span data-stu-id="af301-398">True</span></span>       |
|<span data-ttu-id="af301-399">Amanda</span><span class="sxs-lookup"><span data-stu-id="af301-399">Amanda</span></span>   | <span data-ttu-id="af301-400">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="af301-400">Location1MeetingPolicy</span></span> | <span data-ttu-id="af301-401">해제</span><span class="sxs-lookup"><span data-stu-id="af301-401">False</span></span> |

<span data-ttu-id="af301-402">Daniela는 Amanda의 모임에 메모를 기록 하 고 모든 모임에서 메모를 찍을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-402">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

### <a name="allow-chat-in-meetings-coming-soon"></a><span data-ttu-id="af301-403">모임에서 채팅 허용 (예정 대로)</span><span class="sxs-lookup"><span data-stu-id="af301-403">Allow chat in meetings (coming soon)</span></span>

<span data-ttu-id="af301-404">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-404">This is a per-organizer policy.</span></span> <span data-ttu-id="af301-405">이 설정은 사용자의 모임에서 모임 채팅을 허용할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-405">This setting controls whether meeting chat is allowed in the user's meeting.</span></span> 

<span data-ttu-id="af301-406"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="af301-406"></span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="af301-407">모임 정책 설정-게스트 & 참가자</span><span class="sxs-lookup"><span data-stu-id="af301-407">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="af301-408">이 설정은 모임에 참가 하기 전에 대기실에서 대기 하는 모임 참가자와 모임에서 허용 되는 참여 수준을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-408">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="af301-409">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="af301-409">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="af301-410">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="af301-410">Allow anonymous people to start a meeting</span></span>](#allow-anonymous-people-to-start-a-meeting)
- [<span data-ttu-id="af301-411">전화 접속 사용자가 대기실를 우회할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="af301-411">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby-coming-soon)

> [!NOTE]
><span data-ttu-id="af301-412">모임에 참가 하는 옵션은 각 팀 그룹의 설정 및 연결 방법에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="af301-412">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="af301-413">그룹에 오디오 회의가 있고이를 사용 하 여 연결 하는 경우 [Office 365의 오디오 회의](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af301-413">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="af301-414">팀 그룹에 오디오 회의가 없는 경우 [팀에서 모임 참가](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="af301-414">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="automatically-admit-people"></a><span data-ttu-id="af301-415">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="af301-415">Automatically admit people</span></span>

<span data-ttu-id="af301-416">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-416">This is a per-organizer policy.</span></span> <span data-ttu-id="af301-417">이 설정은 사용자가 인증 된 사용자가 참여 하 게 될 때까지 자신이 모임에 직접 참가 하거나 대기실에서 대기할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-417">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![대기실에 사용자가 있는 모임을 보여 주는 스크린샷](media/meeting-policies-lobby.png)

 <span data-ttu-id="af301-419">모임 이끌이는 모임 초대에서 **모임 옵션** 을 클릭 하 여 자신이 예약한 각 모임에 대해이 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af301-419">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span> <span data-ttu-id="af301-420">**(출시 예정)**</span><span class="sxs-lookup"><span data-stu-id="af301-420">**(coming soon)**</span></span>
  
|<span data-ttu-id="af301-421">값 설정</span><span class="sxs-lookup"><span data-stu-id="af301-421">Setting value</span></span>  |<span data-ttu-id="af301-422">조인 동작</span><span class="sxs-lookup"><span data-stu-id="af301-422">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="af301-423">**가**</span><span class="sxs-lookup"><span data-stu-id="af301-423">**Everyone**</span></span>   |<span data-ttu-id="af301-424">모든 모임 참가자는 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-424">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="af301-425">여기에는 인증 된 사용자, 페더레이션 사용자, 게스트, 익명 사용자, 휴대폰으로 전화 접속 하는 사용자 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-425">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="af301-426">**조직 및 페더레이션된 조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="af301-426">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="af301-427">게스트 사용자 및 페더레이션된 조직의 사용자를 포함 하 여 조직 내에서 인증 된 사용자가 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-427">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="af301-428">익명 사용자 및 전화를 통해 전화를 거는 사용자는 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-428">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="af301-429">**조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="af301-429">**Everyone in your organization**</span></span>    |<span data-ttu-id="af301-430">게스트 사용자를 포함 하 여 조직 내에서 인증 된 사용자가 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-430">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="af301-431">연결 된 사용자, 익명 사용자, 휴대폰으로 전화를 걸고 있는 사용자는 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-431">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span>           |

### <a name="allow-anonymous-people-to-start-a-meeting"></a><span data-ttu-id="af301-432">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="af301-432">Allow anonymous people to start a meeting</span></span>

<span data-ttu-id="af301-433">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-433">This is a per-organizer policy.</span></span> <span data-ttu-id="af301-434">이 설정은 B2B, 페더레이션 사용자 등의 익명 사용자가 조직에서 인증 된 사용자가 아닌 사용자의 모임에 참석할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-434">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> 

![대기 중인 사용자에 게 메시지를 표시 하는 스크린샷](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="af301-436">인증 된 사용자가 모임에 참석 하는 경우 익명 사용자의 참가 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-436">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="af301-437">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="af301-437">Allow anonymous people to start a meeting</span></span>  |<span data-ttu-id="af301-438">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="af301-438">Automatically admit people</span></span> |<span data-ttu-id="af301-439">익명 사용자의 참가 동작</span><span class="sxs-lookup"><span data-stu-id="af301-439">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="af301-440">False</span><span class="sxs-lookup"><span data-stu-id="af301-440">True</span></span>    | <span data-ttu-id="af301-441">가</span><span class="sxs-lookup"><span data-stu-id="af301-441">Everyone</span></span>      | <span data-ttu-id="af301-442">직접 참가</span><span class="sxs-lookup"><span data-stu-id="af301-442">Join directly</span></span>         |
|   | <span data-ttu-id="af301-443">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="af301-443">Everyone in your organization</span></span>       | <span data-ttu-id="af301-444">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="af301-444">Wait in lobby</span></span>        |
|   | <span data-ttu-id="af301-445">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="af301-445">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="af301-446">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="af301-446">Wait in lobby</span></span>         |
|<span data-ttu-id="af301-447">해제</span><span class="sxs-lookup"><span data-stu-id="af301-447">False</span></span>    | <span data-ttu-id="af301-448">가</span><span class="sxs-lookup"><span data-stu-id="af301-448">Everyone</span></span>        | <span data-ttu-id="af301-449">직접 참가</span><span class="sxs-lookup"><span data-stu-id="af301-449">Join directly</span></span>        |
|   | <span data-ttu-id="af301-450">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="af301-450">Everyone in your organization</span></span>     | <span data-ttu-id="af301-451">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="af301-451">Wait in lobby</span></span>        |
|   | <span data-ttu-id="af301-452">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="af301-452">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="af301-453">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="af301-453">Wait in lobby</span></span>         |

<span data-ttu-id="af301-454">다음은 인증 된 사용자가 모임에 없는 경우의 익명 사용자의 참가 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-454">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="af301-455">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="af301-455">Allow anonymous people to start a meeting</span></span> |<span data-ttu-id="af301-456">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="af301-456">Automatically admit people</span></span>  |<span data-ttu-id="af301-457">익명 사용자의 참가 동작</span><span class="sxs-lookup"><span data-stu-id="af301-457">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="af301-458">False</span><span class="sxs-lookup"><span data-stu-id="af301-458">True</span></span>    | <span data-ttu-id="af301-459">가</span><span class="sxs-lookup"><span data-stu-id="af301-459">Everyone</span></span>      | <span data-ttu-id="af301-460">직접 참가</span><span class="sxs-lookup"><span data-stu-id="af301-460">Join directly</span></span>         |
|   | <span data-ttu-id="af301-461">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="af301-461">Everyone in your organization</span></span>       | <span data-ttu-id="af301-462">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="af301-462">Wait in lobby</span></span>        |
|   | <span data-ttu-id="af301-463">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="af301-463">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="af301-464">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="af301-464">Wait in lobby</span></span>         |
|<span data-ttu-id="af301-465">해제</span><span class="sxs-lookup"><span data-stu-id="af301-465">False</span></span>    | <span data-ttu-id="af301-466">가</span><span class="sxs-lookup"><span data-stu-id="af301-466">Everyone</span></span>        | <span data-ttu-id="af301-467">대기실에서 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="af301-467">Wait in lobby.</span></span> <span data-ttu-id="af301-468">인증 된 첫 번째 사용자가 모임에 참가 하면 사용자가 자동으로 허가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af301-468">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="af301-469">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="af301-469">Everyone in your organization</span></span>     |<span data-ttu-id="af301-470">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="af301-470">Wait in lobby</span></span>         |
|   | <span data-ttu-id="af301-471">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="af301-471">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="af301-472">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="af301-472">Wait in lobby</span></span>         |

### <a name="allow-dial-in-users-to-bypass-the-lobby-coming-soon"></a><span data-ttu-id="af301-473">전화 접속 사용자가 대기실를 우회할 수 있도록 허용 (예정 대로)</span><span class="sxs-lookup"><span data-stu-id="af301-473">Allow dial-in users to bypass the lobby (coming soon)</span></span>

<span data-ttu-id="af301-474">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-474">This is a per-organizer policy.</span></span> <span data-ttu-id="af301-475">이 설정은 전화를 통해 전화를 거는 사용자가 모임에 직접 참가 하거나 **자동으로** 허용 되는 사용자 설정에 관계 없이 대기실에서 대기할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-475">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span>

<span data-ttu-id="af301-476">휴대폰에서 전화를 거는 사용자의 참가 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="af301-476">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="af301-477">전화 접속 사용자가 대기실를 우회할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="af301-477">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="af301-478">자동으로 사용자를 인정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af301-478">Automatically admit users</span></span>  |<span data-ttu-id="af301-479">전화 접속 사용자의 참가 동작</span><span class="sxs-lookup"><span data-stu-id="af301-479">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="af301-480">False</span><span class="sxs-lookup"><span data-stu-id="af301-480">True</span></span>    | <span data-ttu-id="af301-481">가</span><span class="sxs-lookup"><span data-stu-id="af301-481">Everyone</span></span>      | <span data-ttu-id="af301-482">직접 참가</span><span class="sxs-lookup"><span data-stu-id="af301-482">Join directly</span></span>         |
|   | <span data-ttu-id="af301-483">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="af301-483">Everyone in your organization</span></span>       | <span data-ttu-id="af301-484">직접 참가</span><span class="sxs-lookup"><span data-stu-id="af301-484">Join directly</span></span>        |
|   | <span data-ttu-id="af301-485">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="af301-485">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="af301-486">직접 참가</span><span class="sxs-lookup"><span data-stu-id="af301-486">Join directly</span></span>         |
|<span data-ttu-id="af301-487">해제</span><span class="sxs-lookup"><span data-stu-id="af301-487">False</span></span>    | <span data-ttu-id="af301-488">가</span><span class="sxs-lookup"><span data-stu-id="af301-488">Everyone</span></span>        | <span data-ttu-id="af301-489">직접 참가</span><span class="sxs-lookup"><span data-stu-id="af301-489">Join directly</span></span>        |
|   | <span data-ttu-id="af301-490">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="af301-490">Everyone in your organization</span></span>     |<span data-ttu-id="af301-491">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="af301-491">Wait in lobby</span></span>         |
|   | <span data-ttu-id="af301-492">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="af301-492">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="af301-493">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="af301-493">Wait in lobby</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="af301-494">관련 항목</span><span class="sxs-lookup"><span data-stu-id="af301-494">Related topics</span></span>
[<span data-ttu-id="af301-495">팀의 메시징 정책</span><span class="sxs-lookup"><span data-stu-id="af301-495">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
