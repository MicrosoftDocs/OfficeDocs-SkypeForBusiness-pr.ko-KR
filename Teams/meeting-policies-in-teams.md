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
ms.openlocfilehash: ba44188d978c9109d1ba3d038c5b1f48d0670746
ms.sourcegitcommit: 43cab5f0fc8692174db09badf3d448e8ff6a50d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40744872"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="595a6-103">팀에서 모임 정책 관리</span><span class="sxs-lookup"><span data-stu-id="595a6-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="595a6-104">모임 정책은 조직의 사용자가 예약한 모임에 대해 모임 참가자가 사용할 수 있는 기능을 제어 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="595a6-105">정책을 만들고 변경한 후 정책에 사용자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="595a6-106">Microsoft 팀 관리 센터에서 또는 [PowerShell을 사용](teams-powershell-overview.md)하 여 모임 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-106">You manage meeting policies in the Microsoft Teams admin center or by [using PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="595a6-107">모임 시작, 모임 중 또는 모임 이후 사용자의 모임 환경에 영향을 주는 다음과 같은 방법으로 정책을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="595a6-108">구현 형식</span><span class="sxs-lookup"><span data-stu-id="595a6-108">Implementation type</span></span>  |<span data-ttu-id="595a6-109">설명</span><span class="sxs-lookup"><span data-stu-id="595a6-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="595a6-110">이끌이 별</span><span class="sxs-lookup"><span data-stu-id="595a6-110">Per-organizer</span></span>    |<span data-ttu-id="595a6-111">이끌이 별 정책을 구현 하는 경우 모든 모임 참가자는 해당 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="595a6-112">예를 들어 사용자가 **자동으로** 허용 이끌이 정책 이며 사용자가 모임에 직접 참가 하는지 여부를 제어 하 고 정책에 할당 된 사용자가 예약한 모임에 대해 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="595a6-113">사용자별</span><span class="sxs-lookup"><span data-stu-id="595a6-113">Per-user</span></span>    |<span data-ttu-id="595a6-114">사용자별 정책을 구현할 때, 이끌이 및/또는 모임 참가자에 대 한 특정 기능을 제한 하는 사용자별 정책만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="595a6-115">예를 들어 **모임 시작 허용** 은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-115">For example, **Allow Meet now** is a per-user policy.</span></span>     |
|<span data-ttu-id="595a6-116">이끌이와 사용자 단위</span><span class="sxs-lookup"><span data-stu-id="595a6-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="595a6-117">이끌이 및 사용자별 정책 조합을 구현 하는 경우 특정 기능은 해당 정책 및 이끌이의 정책에 따라 모임 참가자에 대해 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="595a6-118">예를 들어 **클라우드 기록은 허용** -이끌이 및 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="595a6-119">이 설정을 사용 하 여 모임 이끌이 및 참가자가 녹음/녹화를 시작 하 고 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span> 

<span data-ttu-id="595a6-120">기본적으로 Global (조직 전체 기본값) 이라는 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-120">By default, a policy named Global (org-wide default) is created.</span></span> <span data-ttu-id="595a6-121">조직의 모든 사용자에 게이 모임 정책이 기본적으로 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-121">All users in your organization will be assigned this meeting policy by default.</span></span> <span data-ttu-id="595a6-122">이 정책을 변경 하거나 하나 이상의 사용자 지정 정책을 만들어 사용자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-122">You can either make changes to this policy or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="595a6-123">사용자 지정 정책을 만들 때 사용자가 특정 기능을 사용할 수 있도록 허용 하거나 금지할 수 있으며 설정을 적용할 사용자 하나 이상에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-123">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span> 

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="595a6-124">모임 정책 변경 또는 만들기</span><span class="sxs-lookup"><span data-stu-id="595a6-124">Change or create a meeting policy</span></span>

<span data-ttu-id="595a6-125">모임 정책을 변경 하거나 만들려면 Microsoft 팀 관리 센터 > **모임** > **모임 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-125">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="595a6-126">목록에서 정책을 선택 하거나 **새 정책을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-126">Select a policy from the list or select **New policy**.</span></span> <span data-ttu-id="595a6-127">새 정책을 만드는 경우 이름 및 설명을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-127">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="595a6-128">이름은 특수 문자를 포함 하거나 64 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-128">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="595a6-129">설정을 선택 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-129">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="595a6-130">예를 들어 사용자가 여러 명 있고 모임에 필요한 대역폭의 양을 제한 하려고 한다고 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="595a6-130">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="595a6-131">"제한 된 대역폭" 이라는 새 사용자 지정 정책을 만들고 다음 설정을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-131">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="595a6-132">**오디오 & 비디오**:</span><span class="sxs-lookup"><span data-stu-id="595a6-132">Under **Audio & video**:</span></span>
- <span data-ttu-id="595a6-133">구름 기록 해제</span><span class="sxs-lookup"><span data-stu-id="595a6-133">Turn off cloud recording</span></span>
- <span data-ttu-id="595a6-134">IP 비디오 허용 해제</span><span class="sxs-lookup"><span data-stu-id="595a6-134">Turn off Allow IP video</span></span>

<span data-ttu-id="595a6-135">**콘텐츠 공유**에서:</span><span class="sxs-lookup"><span data-stu-id="595a6-135">Under **Content sharing**:</span></span>
- <span data-ttu-id="595a6-136">화면 공유 모드 해제</span><span class="sxs-lookup"><span data-stu-id="595a6-136">Disable screen sharing mode</span></span>
- <span data-ttu-id="595a6-137">화이트 보드 끄기</span><span class="sxs-lookup"><span data-stu-id="595a6-137">Turn off whiteboard</span></span>
- <span data-ttu-id="595a6-138">공유 메모 해제</span><span class="sxs-lookup"><span data-stu-id="595a6-138">Turn off shared notes</span></span>

<span data-ttu-id="595a6-139">그런 다음 사용자에 게 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-139">Then assign the policy to the users.</span></span>

> [!NOTE] 
> <span data-ttu-id="595a6-140">사용자는 한 번에 하나의 모임 정책만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-140">A user can be assigned only one meeting policy at a time.</span></span> 

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="595a6-141">사용자에 게 모임 정책 할당</span><span class="sxs-lookup"><span data-stu-id="595a6-141">Assign a meeting policy to users</span></span>

<span data-ttu-id="595a6-142">한 사용자에 게 정책을 적용 하는 경우 왼쪽 탐색 창에서 **사용자** 를 선택한 다음 사용자의 표시 이름을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-142">If you're applying the policy to one user, select **Users** on the left navigation pane, and then click the user's display name.</span></span> <span data-ttu-id="595a6-143">사용자의 페이지에서 **할당 된 정책**옆에 있는 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-143">On the user's page, next to **Assigned policies**, select **Edit**.</span></span> <span data-ttu-id="595a6-144">그런 다음 **사용자 정책 편집** 창의 **모임 정책**아래에 있는 드롭다운 목록에서 모임 정책을 선택한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-144">Then, in the **Edit user policies** pane, under **Meeting policy**, select the meeting policy from the drop-down list, and then select **Save**.</span></span> <span data-ttu-id="595a6-145">사용자 목록에서 정책을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-145">You can also assign policies from the list of users.</span></span> <span data-ttu-id="595a6-146">이렇게 하려면 사용자의 표시 이름 왼쪽을 클릭 하 여 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-146">To do this, select the user by clicking to the left of the user's display name.</span></span> <span data-ttu-id="595a6-147">**설정 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-147">Select **Edit settings**.</span></span> <span data-ttu-id="595a6-148">그런 다음 **설정 편집** 창의 **모임 정책**아래에 있는 드롭다운 목록에서 정책을 선택한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-148">Then, on the **Edit settings** pane, under **Meeting policy**, select the policy from the drop-down list, and then select **Save**.</span></span> 
 
<span data-ttu-id="595a6-149">정책을 두 명 이상의 사용자에 게 적용 하는 경우 왼쪽 탐색 창에서 **사용자** 를 선택한 다음 사용자 이름 왼쪽을 클릭 하 여 각 사용자를 선택 하 고 **설정 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-149">If you're applying a policy to more than one user, select **Users** on the left navigation pane, and then select each user by clicking to the left of the user name, and then click **Edit settings**.</span></span> <span data-ttu-id="595a6-150">**설정 편집** 창의 **모임 정책**아래에 있는 드롭다운 목록에서 정책을 선택한 다음 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-150">On the **Edit Settings** pane, under **Meeting policy**, select the policy from the drop-down list, and then select **Save**.</span></span>
 
<span data-ttu-id="595a6-151">다음과 같이 한 명 이상의 사용자에 게 모임 정책을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-151">You can also assign a meeting policy to one or more users as follows:</span></span>

1. <span data-ttu-id="595a6-152">**Microsoft 팀 관리 센터** > **모임** > **정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-152">Go to **Microsoft Teams admin center** > **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="595a6-153">정책 이름 왼쪽에 있는을 클릭 하 여 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-153">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="595a6-154">**사용자 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-154">Select **Manage users**.</span></span>
4. <span data-ttu-id="595a6-155">**사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-155">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="595a6-156">추가 하려는 각 사용자에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-156">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="595a6-157">사용자 추가를 마쳤으면 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-157">When you're finished adding users, select **Save**.</span></span>
 
> [!NOTE] 
> <span data-ttu-id="595a6-158">사용자가 할당 된 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-158">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="595a6-159">먼저 영향을 받는 모든 사용자에 게 다른 정책을 할당 한 다음 원래 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-159">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>
 
## <a name="meeting-policy-settings"></a><span data-ttu-id="595a6-160">모임 정책 설정</span><span class="sxs-lookup"><span data-stu-id="595a6-160">Meeting policy settings</span></span>

<span data-ttu-id="595a6-161">**모임 정책** 페이지의 기존 정책을 선택 하거나 새 **정책을 선택 하 여 새** 정책을 추가 하면 다음에 대 한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-161">When you select an existing policy on the **Meeting policies** page or select **New policy** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="595a6-162">일반</span><span class="sxs-lookup"><span data-stu-id="595a6-162">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="595a6-163">오디오 & 비디오</span><span class="sxs-lookup"><span data-stu-id="595a6-163">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="595a6-164">콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="595a6-164">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="595a6-165">참가자가 게스트를 &</span><span class="sxs-lookup"><span data-stu-id="595a6-165">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="595a6-166"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="595a6-166"></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="595a6-167">모임 정책 설정-일반</span><span class="sxs-lookup"><span data-stu-id="595a6-167">Meeting policy settings - General</span></span>

- [<span data-ttu-id="595a6-168">채널에서 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-168">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="595a6-169">지금 비공개 모임 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-169">Allow private Meet now</span></span>](#allow-private-meet-now)
- [<span data-ttu-id="595a6-170">Outlook 추가 기능 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-170">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="595a6-171">채널 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-171">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="595a6-172">개인 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-172">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="595a6-173">채널에서 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-173">Allow Meet now in channels</span></span>

<span data-ttu-id="595a6-174">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-174">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="595a6-175">이 설정은 사용자가 팀 채널에서 임시 모임을 시작할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-175">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="595a6-176">이 기능을 설정 하면 사용자가 팀 채널에서 메시지를 게시할 때 작성 **상자 아래에 있는 모임 시작** 을 클릭 하 여 채널의 임시 모임을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-176">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** beneath the compose box to start an ad hoc meeting in the channel.</span></span>

![메시지 아래에 모임 시작 아이콘을 표시 하는 스크린샷](media/meeting-policies-meet-now.png)

### <a name="allow-private-meet-now"></a><span data-ttu-id="595a6-178">지금 비공개 모임 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-178">Allow private Meet now</span></span>

<span data-ttu-id="595a6-179">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-179">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="595a6-180">이 설정은 사용자가 임시 비공개 모임을 시작할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-180">This setting controls whether a user can start an ad hoc private meeting.</span></span>  

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="595a6-181">Outlook 추가 기능 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-181">Allow the Outlook add-in</span></span>

<span data-ttu-id="595a6-182">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-182">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="595a6-183">이 설정은 Outlook (Windows, Mac, 웹, 모바일)에서 팀 모임을 예약할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-183">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![새 모임 예약 기능을 보여 주는 스크린샷](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="595a6-185">이 기능을 해제 하면 사용자가 Outlook에서 새 모임을 만들 때 팀 회의를 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-185">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="595a6-186">예를 들어 Windows의 Outlook에서는 **새 팀 모임** 옵션이 리본 메뉴에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-186">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="595a6-187">채널 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-187">Allow channel meeting scheduling</span></span>

<span data-ttu-id="595a6-188">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-188">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="595a6-189">이 설정은 사용자가 팀 채널에서 모임을 예약할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-189">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="595a6-190">이 기능을 해제 한 경우 팀 채널에서 모임을 시작할 때 사용자가 **모임 예약** 옵션을 사용할 수 없으며 팀의 모임에서 모임을 예약 하는 경우 사용자가 모임 **에 대 한 채널 선택** 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-190">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Select a channel to meet** option won't be available to the user when they schedule a meeting from Meetings in Teams.</span></span>

![팀의 모임 예약 옵션을 보여 주는 스크린샷](media/meeting-policies-schedule-a-meeting.png)

![모임에 적용할 채널 선택 옵션을 보여 주는 스크린샷](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="595a6-193">개인 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-193">Allow scheduling private meetings</span></span>

<span data-ttu-id="595a6-194">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-194">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="595a6-195">이 설정은 사용자가 팀에서 비공개 모임을 예약할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-195">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="595a6-196">모임이 팀의 채널에 게시 되지 않은 경우 비공개 모임입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-196">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="595a6-197">**비공개 모임 예약 허용** 을 해제 하 고 **채널 모임 예약을 허용**하면 **모임 예약** 옵션을 사용할 수 없으며 사용자가 팀에서 모임을 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-197">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Schedule a meeting** option won't be available and users will be unable to schedule meetings in Teams.</span></span>

<span data-ttu-id="595a6-198"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="595a6-198"></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="595a6-199">모임 정책 설정-오디오 & 비디오</span><span class="sxs-lookup"><span data-stu-id="595a6-199">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="595a6-200">내용 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-200">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="595a6-201">클라우드 기록 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-201">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="595a6-202">IP 비디오 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-202">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="595a6-203">미디어 비트 전송률 (KBs)</span><span class="sxs-lookup"><span data-stu-id="595a6-203">Media bit rate (KBs)</span></span>](#media-bit-rate-kbs)
- [<span data-ttu-id="595a6-204">실시간 캡션 사용 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="595a6-204">Enable live captions (preview)</span></span>](#enable-live-captions-preview)

### <a name="allow-transcription"></a><span data-ttu-id="595a6-205">내용 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-205">Allow transcription</span></span>

<span data-ttu-id="595a6-206">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-206">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="595a6-207">이 설정은 모임 녹음/녹화를 재생 하는 동안 캡션과 기록 기능을 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-207">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="595a6-208">이 기능을 해제 하면 모임 녹음/녹화를 재생 하는 동안 **검색** 및 **참조** 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-208">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="595a6-209">녹음/녹화를 시작한 사람에 게는 녹음/녹화가 포함 되도록이 설정이 켜져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-209">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="595a6-210">기록 된 모임에 대 한 정보는 현재 팀의 언어를 영어로 설정한 경우와 모임에서 영어를 사용 하 고 있는 사용자만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-210">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![모임의 기록 옵션을 보여 주는 스크린샷](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="595a6-212">클라우드 기록 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-212">Allow cloud recording</span></span>

<span data-ttu-id="595a6-213">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-213">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="595a6-214">이 설정은 사용자의 모임을 녹화할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-214">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="595a6-215">참가자에 대해 정책 설정이 설정 된 경우와 다른 모임 참가자가 같은 조직의 인증 된 사용자 인 경우 기록을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-215">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="595a6-216">페더레이션 및 익명 사용자 등 조직 외부의 사용자가 녹음/녹화를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-216">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="595a6-217">게스트 사용자는 녹음/녹화를 시작 하거나 중지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-217">Guest users can't start or stop the recording.</span></span> 

![기록 옵션을 보여 주는 스크린샷](media/meeting-policies-recording.png)

<span data-ttu-id="595a6-219">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-219">Let's look at the following example.</span></span>

|<span data-ttu-id="595a6-220">사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-220">User</span></span> |<span data-ttu-id="595a6-221">모임 정책</span><span class="sxs-lookup"><span data-stu-id="595a6-221">Meeting policy</span></span>  |<span data-ttu-id="595a6-222">클라우드 기록 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-222">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="595a6-223">Daniela</span><span class="sxs-lookup"><span data-stu-id="595a6-223">Daniela</span></span> | <span data-ttu-id="595a6-224">전역</span><span class="sxs-lookup"><span data-stu-id="595a6-224">Global</span></span>   | <span data-ttu-id="595a6-225">해제</span><span class="sxs-lookup"><span data-stu-id="595a6-225">False</span></span> |
|<span data-ttu-id="595a6-226">Amanda</span><span class="sxs-lookup"><span data-stu-id="595a6-226">Amanda</span></span> | <span data-ttu-id="595a6-227">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="595a6-227">Location1MeetingPolicy</span></span> | <span data-ttu-id="595a6-228">False</span><span class="sxs-lookup"><span data-stu-id="595a6-228">True</span></span>|
|<span data-ttu-id="595a6-229">John (외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="595a6-229">John (external user)</span></span> | <span data-ttu-id="595a6-230">해당 없음</span><span class="sxs-lookup"><span data-stu-id="595a6-230">Not applicable</span></span> | <span data-ttu-id="595a6-231">해당 없음</span><span class="sxs-lookup"><span data-stu-id="595a6-231">Not applicable</span></span>|

<span data-ttu-id="595a6-232">Daniela에서 구성한 모임은 기록 하 고 Amanda 수 있으며, 정책 설정을 사용 하도록 설정한 경우 Daniela로 구성 된 모임을 녹화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-232">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="595a6-233">Amanda에서 구성한 모임은 녹화할 수 있지만, Daniela는 정책 설정을 사용 하지 않도록 설정 하 고 외부 사용자 인 John은 Amanda으로 구성 된 모임을 기록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-233">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="595a6-234">클라우드 모임 기록에 대해 자세히 알아보려면 [팀 클라우드 모임 기록을](cloud-recording.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="595a6-234">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="595a6-235">IP 비디오 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-235">Allow IP video</span></span>

<span data-ttu-id="595a6-236">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-236">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="595a6-237">비디오는 모임에 대 한 주요 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-237">Video is a key component to meetings.</span></span> <span data-ttu-id="595a6-238">일부 조직에서는 관리자가 어떤 사용자의 모임이 비디오를 보유 하 고 있는지 더 자세히 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-238">In some organizations, admins might want more control over which users’ meetings have video.</span></span> <span data-ttu-id="595a6-239">이 설정은 사용자가 호스트 하는 모임 및 사용자가 시작한 1:1 통화 및 그룹 통화에서 비디오를 켤 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-239">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="595a6-240">이 정책을 사용 하도록 설정한 사용자가 구성한 모임에는 모임 참가자가 정책을 사용 하도록 설정한 경우 모임 참가자가 모임에서 비디오 공유를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-240">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="595a6-241">배정 된 정책이 없는 모임 참가자 (예: 익명 및 페더레이션 참가자)는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-241">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![오디오 및 비디오 설정을 사용 하 여 모임을 보여 주는 스크린샷](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="595a6-243">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-243">Let's look at the following example.</span></span>

|<span data-ttu-id="595a6-244">사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-244">User</span></span> |<span data-ttu-id="595a6-245">모임 정책</span><span class="sxs-lookup"><span data-stu-id="595a6-245">Meeting policy</span></span>  |<span data-ttu-id="595a6-246">IP 영상 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-246">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="595a6-247">Daniela</span><span class="sxs-lookup"><span data-stu-id="595a6-247">Daniela</span></span>   | <span data-ttu-id="595a6-248">전역</span><span class="sxs-lookup"><span data-stu-id="595a6-248">Global</span></span>   | <span data-ttu-id="595a6-249">False</span><span class="sxs-lookup"><span data-stu-id="595a6-249">True</span></span>        |
|<span data-ttu-id="595a6-250">Amanda</span><span class="sxs-lookup"><span data-stu-id="595a6-250">Amanda</span></span>    | <span data-ttu-id="595a6-251">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="595a6-251">Location1MeetingPolicy</span></span>        | <span data-ttu-id="595a6-252">해제</span><span class="sxs-lookup"><span data-stu-id="595a6-252">False</span></span>      |

<span data-ttu-id="595a6-253">Daniela에서 호스팅하는 모임은 영상 통화를 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-253">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="595a6-254">Daniela 모임에 참가 하 고 비디오를 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-254">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="595a6-255">Amanda의 정책이 비디오를 허용 하지 않도록 설정 되어 있기 때문에 Daniela 모임에서 비디오를 켤 수 없습니다 Amanda.</span><span class="sxs-lookup"><span data-stu-id="595a6-255">Amanda can't turn on video in Daniela's meeting because Amanda’s policy is set to not allow video.</span></span> <span data-ttu-id="595a6-256">Amanda는 모임의 다른 참가자가 공유 하는 비디오를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-256">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="595a6-257">Amanda에서 호스팅하는 모임에서 할당 된 비디오 정책에 관계 없이 비디오를 켤 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-257">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="595a6-258">이는 Daniela에서 Amanda의 모임에서 비디오를 켤 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-258">This means Daniela can't turn on video in Amanda’s meetings.</span></span>  

<span data-ttu-id="595a6-259">Daniela에서 비디오를 사용 하 여 Amanda를 호출 하는 경우 Amanda는 오디오 만으로 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-259">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="595a6-260">통화가 연결 되 면 Amanda에서 Daniela의 비디오를 볼 수 있지만 영상 통화는 켜지 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-260">When the call is connected, Amanda can see Daniela’s video, but can't turn on video.</span></span> <span data-ttu-id="595a6-261">Amanda에서 Daniela를 호출 하는 경우 Daniela는 비디오 및 오디오로 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-261">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="595a6-262">통화가 연결 되 면 필요에 따라 Daniela에서 비디오를 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-262">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="595a6-263">미디어 비트 전송률 (KBs)</span><span class="sxs-lookup"><span data-stu-id="595a6-263">Media bit rate (KBs)</span></span>

<span data-ttu-id="595a6-264">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-264">This is a per-user policy.</span></span> <span data-ttu-id="595a6-265">이 설정에 따라 사용자에 대 한 통화 및 모임에서 오디오, 비디오 및 비디오 기반 앱 공유 전송의 미디어 비트 전송률이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-265">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="595a6-266">통화 또는 모임에서 사용자의 업링크 및 다운 링크 미디어 트래버스 둘 다에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-266">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="595a6-267">이 설정을 사용 하면 조직의 대역폭을 관리 하는 방법을 세부적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-267">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="595a6-268">사용자에 게 필요한 모임 시나리오에 따라 좋은 품질 환경을 위해 적절 한 대역폭을 확보 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-268">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="595a6-269">최소값은 30kbps이 고 최대값은 모임 시나리오에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-269">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="595a6-270">팀에서 좋은 음질의 모임, 통화, 라이브 이벤트에 권장 되는 최소 대역폭에 대해 자세히 알아보려면 [대역폭 요구 사항을](prepare-network.md#bandwidth-requirements)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="595a6-270">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="595a6-271">모임에 대 한 대역폭이 충분 하지 않은 경우 참가자는 네트워크 품질이 좋지 않다는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-271">If there isn’t enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="595a6-272">CEO 보드 모임 및 팀 라이브 이벤트와 같이 고품질의 비디오 환경을 필요로 하는 모임의 경우 대역폭을 10mbps로 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-272">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="595a6-273">최대 환경이 설정 된 경우에도 시나리오에 따라 특정 네트워크 조건이 감지 되는 경우 팀 미디어 스택이 낮은 대역폭 조건에 적응 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-273">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

### <a name="enable-live-captions-preview"></a><span data-ttu-id="595a6-274">실시간 캡션 사용 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="595a6-274">Enable live captions (preview)</span></span>

<span data-ttu-id="595a6-275">이것은 사용자별 정책으로 모임 중에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-275">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="595a6-276">이 설정은 사용자가 참석할는 모임에서 실시간 **캡션 켜기** 옵션을 사용 하 여 live 캡션을 켜고 끌 것인지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-276">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![라이브 캡션 켜기 옵션을 보여 주는 스크린샷](media/meeting-policies-live-captions.png)

|<span data-ttu-id="595a6-278">값 설정</span><span class="sxs-lookup"><span data-stu-id="595a6-278">Setting value</span></span> |<span data-ttu-id="595a6-279">결과가</span><span class="sxs-lookup"><span data-stu-id="595a6-279">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="595a6-280">**사용 하지 않도록 설정 하 고 사용자가 무시할 수 있음**</span><span class="sxs-lookup"><span data-stu-id="595a6-280">**Disabled and the user can override**</span></span>     | <span data-ttu-id="595a6-281">Live 캡션은 모임 중에 사용자에 대해 자동으로 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-281">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="595a6-282">사용자는 오버플로 (**...**) 메뉴에서 **라이브 캡션 켜기** 옵션을 표시 하 여 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-282">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="595a6-283">이는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-283">This is the default setting.</span></span> |
|<span data-ttu-id="595a6-284">**비활성화**</span><span class="sxs-lookup"><span data-stu-id="595a6-284">**Disabled**</span></span>     | <span data-ttu-id="595a6-285">모임 중에는 사용자가 실시간 캡션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-285">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="595a6-286">사용자는이 옵션을 켤 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-286">The user doesn't have the option to turn them on.</span></span>          |


<span data-ttu-id="595a6-287"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="595a6-287"></span></span>

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="595a6-288">모임 정책 설정-콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="595a6-288">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="595a6-289">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="595a6-289">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="595a6-290">참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-290">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="595a6-291">외부 참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-291">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="595a6-292">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-292">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="595a6-293">화이트 보드 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-293">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="595a6-294">공유 메모 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-294">Allow shared notes</span></span>](#allow-shared-notes)
- [<span data-ttu-id="595a6-295">모임에서 채팅 허용 (예정 대로)</span><span class="sxs-lookup"><span data-stu-id="595a6-295">Allow chat in meetings (coming soon)</span></span>](#allow-chat-in-meetings-coming-soon)

### <a name="screen-sharing-mode"></a><span data-ttu-id="595a6-296">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="595a6-296">Screen sharing mode</span></span>

<span data-ttu-id="595a6-297">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-297">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="595a6-298">이 설정은 사용자의 모임에서 데스크톱 및/또는 창 공유를 허용할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-298">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="595a6-299">배정 된 정책이 없는 모임 참가자 (예: 익명, 게스트, B2B, 페더레이션 참가자)는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-299">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="595a6-300">값 설정</span><span class="sxs-lookup"><span data-stu-id="595a6-300">Setting value</span></span> |<span data-ttu-id="595a6-301">결과가</span><span class="sxs-lookup"><span data-stu-id="595a6-301">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="595a6-302">**전체 화면**</span><span class="sxs-lookup"><span data-stu-id="595a6-302">**Entire screen**</span></span>    | <span data-ttu-id="595a6-303">모임에서 전체 데스크톱 공유 및 응용 프로그램 공유를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-303">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="595a6-304">**단일 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="595a6-304">**Single application**</span></span>   | <span data-ttu-id="595a6-305">모임에서 응용 프로그램 공유가 허용 됨</span><span class="sxs-lookup"><span data-stu-id="595a6-305">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="595a6-306">**비활성화**</span><span class="sxs-lookup"><span data-stu-id="595a6-306">**Disabled**</span></span>     |<span data-ttu-id="595a6-307">모임에서 화면 공유 및 응용 프로그램 공유 기능을 해제 했습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-307">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="595a6-308">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-308">Let's look at the following example.</span></span>

|<span data-ttu-id="595a6-309">사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-309">User</span></span> |<span data-ttu-id="595a6-310">모임 정책</span><span class="sxs-lookup"><span data-stu-id="595a6-310">Meeting policy</span></span> |<span data-ttu-id="595a6-311">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="595a6-311">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="595a6-312">Daniela</span><span class="sxs-lookup"><span data-stu-id="595a6-312">Daniela</span></span>  | <span data-ttu-id="595a6-313">전역</span><span class="sxs-lookup"><span data-stu-id="595a6-313">Global</span></span>   | <span data-ttu-id="595a6-314">전체 화면</span><span class="sxs-lookup"><span data-stu-id="595a6-314">Entire screen</span></span> |
|<span data-ttu-id="595a6-315">Amanda</span><span class="sxs-lookup"><span data-stu-id="595a6-315">Amanda</span></span>   | <span data-ttu-id="595a6-316">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="595a6-316">Location1MeetingPolicy</span></span>  | <span data-ttu-id="595a6-317">비활성화</span><span class="sxs-lookup"><span data-stu-id="595a6-317">Disabled</span></span> |

<span data-ttu-id="595a6-318">Daniela에서 호스팅하는 모임은 모임 참가자가 전체 화면 또는 특정 응용 프로그램을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-318">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="595a6-319">Amanda 참가 Daniela의 모임이 Amanda, 화면을 공유할 수 없거나, 정책 설정에 따라 특정 응용 프로그램을 사용 하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-319">If Amanda joins Daniela’s meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="595a6-320">Amanda에서 호스트 하는 모임에서는 자신에 게 할당 된 화면 공유 모드 정책에 관계 없이 화면 또는 단일 응용 프로그램을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-320">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="595a6-321">즉, Daniela는 Amanda 모임의 화면 또는 단일 응용 프로그램을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-321">This means that Daniela can't share her screen or a single application in Amanda’s meetings.</span></span>  

<span data-ttu-id="595a6-322">현재 사용자는 Google Chrome을 사용 하는 경우 팀 모임에서 비디오를 재생 하거나 화면을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-322">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="595a6-323">참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-323">Allow a participant to give or request control</span></span>

<span data-ttu-id="595a6-324">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-324">This is a per-user policy.</span></span> <span data-ttu-id="595a6-325">이 설정은 사용자가 공유 데스크톱 또는 창을 다른 모임 참가자에 게 제어권을 부여할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-325">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="595a6-326">컨트롤을 제공 하려면 화면 위쪽을 마우스로 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-326">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="595a6-327">사용자에 대해이 설정이 설정 된 경우 **제어권 제공** 옵션이 공유 세션의 위쪽 표시줄에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-327">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![제어권 제공 옵션을 보여 주는 스크린샷](media/meeting-policies-give-control.png)

<span data-ttu-id="595a6-329">사용자에 대해 설정이 꺼져 있으면 **제어권 제공** 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-329">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![제어권 부여 옵션을 사용할 수 없음을 보여 주는 스크린샷](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="595a6-331">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-331">Let's look at the following example.</span></span>

|<span data-ttu-id="595a6-332">사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-332">User</span></span> |<span data-ttu-id="595a6-333">모임 정책</span><span class="sxs-lookup"><span data-stu-id="595a6-333">Meeting policy</span></span>  |<span data-ttu-id="595a6-334">참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-334">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="595a6-335">Daniela</span><span class="sxs-lookup"><span data-stu-id="595a6-335">Daniela</span></span>   | <span data-ttu-id="595a6-336">전역</span><span class="sxs-lookup"><span data-stu-id="595a6-336">Global</span></span>   | <span data-ttu-id="595a6-337">False</span><span class="sxs-lookup"><span data-stu-id="595a6-337">True</span></span>       |
|<span data-ttu-id="595a6-338">Babek</span><span class="sxs-lookup"><span data-stu-id="595a6-338">Babek</span></span>    | <span data-ttu-id="595a6-339">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="595a6-339">Location1MeetingPolicy</span></span>        | <span data-ttu-id="595a6-340">해제</span><span class="sxs-lookup"><span data-stu-id="595a6-340">False</span></span>   |

<span data-ttu-id="595a6-341">Daniela는 다른 참가자에 게 제어권을 부여할 수 없기 때문에 Babek에서 구성한 모임의 다른 참가자에 게 공유 데스크톱 또는 창을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-341">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="595a6-342">외부 참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-342">Allow an external participant to give or request control</span></span>

<span data-ttu-id="595a6-343">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-343">This is a per-user policy.</span></span> <span data-ttu-id="595a6-344">이 설정은 모임의 외부 참가자가 모임의 다른 참가자에 게 공유 데스크톱 또는 창을 제어할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-344">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="595a6-345">팀 회의의 외부 참가자는 다음과 같이 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-345">External participants in Teams meetings can be categorized as follows:</span></span>  

   - <span data-ttu-id="595a6-346">익명 사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-346">Anonymous user</span></span>
   - <span data-ttu-id="595a6-347">게스트 사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-347">Guest users</span></span>  
   - <span data-ttu-id="595a6-348">B2B 사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-348">B2B user</span></span>
   - <span data-ttu-id="595a6-349">페더레이션 사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-349">Federated user</span></span>  

<span data-ttu-id="595a6-350">공유 된 사용자가 외부 참가자가 조직에서 **제어권을 부여 하거나 요청할 수 있도록 허용을** 제어 하도록 설정 되어 있는 동안 페더레이션 사용자가 해당 사용자에 게 제어권을 부여할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="595a6-350">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="595a6-351">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-351">Allow PowerPoint sharing</span></span>

<span data-ttu-id="595a6-352">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-352">This is a per-user policy.</span></span> <span data-ttu-id="595a6-353">이 설정은 사용자가 모임에서 PowerPoint 슬라이드 데크를 공유할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-353">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="595a6-354">익명, 게스트, 페더레이션 사용자를 비롯 한 외부 사용자가 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-354">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="595a6-355">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-355">Let's look at the following example.</span></span>

|<span data-ttu-id="595a6-356">사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-356">User</span></span> |<span data-ttu-id="595a6-357">모임 정책</span><span class="sxs-lookup"><span data-stu-id="595a6-357">Meeting policy</span></span>  |<span data-ttu-id="595a6-358">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-358">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="595a6-359">Daniela</span><span class="sxs-lookup"><span data-stu-id="595a6-359">Daniela</span></span>   | <span data-ttu-id="595a6-360">전역</span><span class="sxs-lookup"><span data-stu-id="595a6-360">Global</span></span>   | <span data-ttu-id="595a6-361">False</span><span class="sxs-lookup"><span data-stu-id="595a6-361">True</span></span>       |
|<span data-ttu-id="595a6-362">Amanda</span><span class="sxs-lookup"><span data-stu-id="595a6-362">Amanda</span></span>   | <span data-ttu-id="595a6-363">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="595a6-363">Location1MeetingPolicy</span></span>        | <span data-ttu-id="595a6-364">해제</span><span class="sxs-lookup"><span data-stu-id="595a6-364">False</span></span>   |

<span data-ttu-id="595a6-365">Amanda 모임 이끌이 인 경우에도 모임에서 PowerPoint 슬라이드 데크를 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-365">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="595a6-366">Daniela는 모임이 Amanda으로 구성 된 경우에도 PowerPoint 슬라이드 데크를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-366">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="595a6-367">Amanda는 PowerPoint 슬라이드 데크를 공유할 수는 없지만 모임에서 다른 사용자가 공유한 PowerPoint 슬라이드 데크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-367">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="595a6-368">화이트 보드 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-368">Allow whiteboard</span></span>

<span data-ttu-id="595a6-369">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-369">This is a per-user policy.</span></span> <span data-ttu-id="595a6-370">이 설정은 사용자가 모임에서 화이트 보드를 공유할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-370">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="595a6-371">익명, B2B, 페더레이션 사용자 등의 외부 사용자는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-371">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="595a6-372">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-372">Let's look at the following example.</span></span>

|<span data-ttu-id="595a6-373">사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-373">User</span></span> |<span data-ttu-id="595a6-374">모임 정책</span><span class="sxs-lookup"><span data-stu-id="595a6-374">Meeting policy</span></span>  |<span data-ttu-id="595a6-375">화이트 보드 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-375">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="595a6-376">Daniela</span><span class="sxs-lookup"><span data-stu-id="595a6-376">Daniela</span></span>   | <span data-ttu-id="595a6-377">전역</span><span class="sxs-lookup"><span data-stu-id="595a6-377">Global</span></span>   | <span data-ttu-id="595a6-378">False</span><span class="sxs-lookup"><span data-stu-id="595a6-378">True</span></span>       |
|<span data-ttu-id="595a6-379">Amanda</span><span class="sxs-lookup"><span data-stu-id="595a6-379">Amanda</span></span>   | <span data-ttu-id="595a6-380">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="595a6-380">Location1MeetingPolicy</span></span>        | <span data-ttu-id="595a6-381">해제</span><span class="sxs-lookup"><span data-stu-id="595a6-381">False</span></span>   |

<span data-ttu-id="595a6-382">Amanda 모임 이끌이 인 경우에도 모임에서 화이트 보드를 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-382">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="595a6-383">Daniela는 모임이 Amanda으로 구성 된 경우에도 화이트 보드를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-383">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="595a6-384">공유 메모 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-384">Allow shared notes</span></span>

<span data-ttu-id="595a6-385">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-385">This is a per-user policy.</span></span> <span data-ttu-id="595a6-386">이 설정은 사용자가 모임에서 노트를 만들고 공유할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-386">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="595a6-387">익명, B2B, 페더레이션 사용자 등의 외부 사용자는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-387">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="595a6-388">**모임 메모** 탭은 현재 20 명 미만의 참가자가 있는 모임 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-388">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span> 

<span data-ttu-id="595a6-389">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-389">Let's look at the following example.</span></span>

|<span data-ttu-id="595a6-390">사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-390">User</span></span> |<span data-ttu-id="595a6-391">모임 정책</span><span class="sxs-lookup"><span data-stu-id="595a6-391">Meeting policy</span></span>  |<span data-ttu-id="595a6-392">공유 메모 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-392">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="595a6-393">Daniela</span><span class="sxs-lookup"><span data-stu-id="595a6-393">Daniela</span></span>   | <span data-ttu-id="595a6-394">전역</span><span class="sxs-lookup"><span data-stu-id="595a6-394">Global</span></span>   | <span data-ttu-id="595a6-395">False</span><span class="sxs-lookup"><span data-stu-id="595a6-395">True</span></span>       |
|<span data-ttu-id="595a6-396">Amanda</span><span class="sxs-lookup"><span data-stu-id="595a6-396">Amanda</span></span>   | <span data-ttu-id="595a6-397">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="595a6-397">Location1MeetingPolicy</span></span> | <span data-ttu-id="595a6-398">해제</span><span class="sxs-lookup"><span data-stu-id="595a6-398">False</span></span> |

<span data-ttu-id="595a6-399">Daniela는 Amanda의 모임에 메모를 기록 하 고 모든 모임에서 메모를 찍을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-399">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

### <a name="allow-chat-in-meetings-coming-soon"></a><span data-ttu-id="595a6-400">모임에서 채팅 허용 (예정 대로)</span><span class="sxs-lookup"><span data-stu-id="595a6-400">Allow chat in meetings (coming soon)</span></span>

<span data-ttu-id="595a6-401">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-401">This is a per-organizer policy.</span></span> <span data-ttu-id="595a6-402">이 설정은 사용자의 모임에서 모임 채팅을 허용할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-402">This setting controls whether meeting chat is allowed in the user's meeting.</span></span> 

<span data-ttu-id="595a6-403"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="595a6-403"></span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="595a6-404">모임 정책 설정-게스트 & 참가자</span><span class="sxs-lookup"><span data-stu-id="595a6-404">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="595a6-405">이 설정은 모임에 참가 하기 전에 대기실에서 대기 하는 모임 참가자와 모임에서 허용 되는 참여 수준을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-405">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="595a6-406">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="595a6-406">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="595a6-407">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-407">Allow anonymous people to start a meeting</span></span>](#allow-anonymous-people-to-start-a-meeting)
- [<span data-ttu-id="595a6-408">전화 접속 사용자가 대기실를 우회할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-408">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby-coming-soon)

> [!NOTE]
><span data-ttu-id="595a6-409">모임에 참가 하는 옵션은 각 팀 그룹의 설정 및 연결 방법에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-409">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="595a6-410">그룹에 오디오 회의가 있고이를 사용 하 여 연결 하는 경우 [Office 365의 오디오 회의](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="595a6-410">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="595a6-411">팀 그룹에 오디오 회의가 없는 경우 [팀에서 모임 참가](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="595a6-411">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="automatically-admit-people"></a><span data-ttu-id="595a6-412">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="595a6-412">Automatically admit people</span></span>

<span data-ttu-id="595a6-413">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-413">This is a per-organizer policy.</span></span> <span data-ttu-id="595a6-414">이 설정은 사용자가 인증 된 사용자가 참여 하 게 될 때까지 자신이 모임에 직접 참가 하거나 대기실에서 대기할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-414">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![대기실에 사용자가 있는 모임을 보여 주는 스크린샷](media/meeting-policies-lobby.png)

 <span data-ttu-id="595a6-416">모임 이끌이는 모임 초대에서 **모임 옵션** 을 클릭 하 여 자신이 예약한 각 모임에 대해이 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-416">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span> <span data-ttu-id="595a6-417">**(출시 예정)**</span><span class="sxs-lookup"><span data-stu-id="595a6-417">**(coming soon)**</span></span>
  
|<span data-ttu-id="595a6-418">값 설정</span><span class="sxs-lookup"><span data-stu-id="595a6-418">Setting value</span></span>  |<span data-ttu-id="595a6-419">조인 동작</span><span class="sxs-lookup"><span data-stu-id="595a6-419">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="595a6-420">**가**</span><span class="sxs-lookup"><span data-stu-id="595a6-420">**Everyone**</span></span>   |<span data-ttu-id="595a6-421">모든 모임 참가자는 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-421">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="595a6-422">여기에는 인증 된 사용자, 페더레이션 사용자, 게스트, 익명 사용자, 휴대폰으로 전화 접속 하는 사용자 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-422">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="595a6-423">**조직 및 페더레이션된 조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="595a6-423">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="595a6-424">게스트 사용자 및 페더레이션된 조직의 사용자를 포함 하 여 조직 내에서 인증 된 사용자가 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-424">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="595a6-425">익명 사용자 및 전화를 통해 전화를 거는 사용자는 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-425">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="595a6-426">**조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="595a6-426">**Everyone in your organization**</span></span>    |<span data-ttu-id="595a6-427">게스트 사용자를 포함 하 여 조직 내에서 인증 된 사용자가 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-427">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="595a6-428">연결 된 사용자, 익명 사용자, 휴대폰으로 전화를 걸고 있는 사용자는 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-428">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span>           |

### <a name="allow-anonymous-people-to-start-a-meeting"></a><span data-ttu-id="595a6-429">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-429">Allow anonymous people to start a meeting</span></span>

<span data-ttu-id="595a6-430">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-430">This is a per-organizer policy.</span></span> <span data-ttu-id="595a6-431">이 설정은 B2B, 페더레이션 사용자 등의 익명 사용자가 조직에서 인증 된 사용자가 아닌 사용자의 모임에 참석할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-431">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> 

![대기 중인 사용자에 게 메시지를 표시 하는 스크린샷](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="595a6-433">인증 된 사용자가 모임에 참석 하는 경우 익명 사용자의 참가 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-433">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="595a6-434">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-434">Allow anonymous people to start a meeting</span></span>  |<span data-ttu-id="595a6-435">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="595a6-435">Automatically admit people</span></span> |<span data-ttu-id="595a6-436">익명 사용자의 참가 동작</span><span class="sxs-lookup"><span data-stu-id="595a6-436">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="595a6-437">False</span><span class="sxs-lookup"><span data-stu-id="595a6-437">True</span></span>    | <span data-ttu-id="595a6-438">가</span><span class="sxs-lookup"><span data-stu-id="595a6-438">Everyone</span></span>      | <span data-ttu-id="595a6-439">직접 참가</span><span class="sxs-lookup"><span data-stu-id="595a6-439">Join directly</span></span>         |
|   | <span data-ttu-id="595a6-440">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-440">Everyone in your organization</span></span>       | <span data-ttu-id="595a6-441">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="595a6-441">Wait in lobby</span></span>        |
|   | <span data-ttu-id="595a6-442">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-442">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="595a6-443">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="595a6-443">Wait in lobby</span></span>         |
|<span data-ttu-id="595a6-444">해제</span><span class="sxs-lookup"><span data-stu-id="595a6-444">False</span></span>    | <span data-ttu-id="595a6-445">가</span><span class="sxs-lookup"><span data-stu-id="595a6-445">Everyone</span></span>        | <span data-ttu-id="595a6-446">직접 참가</span><span class="sxs-lookup"><span data-stu-id="595a6-446">Join directly</span></span>        |
|   | <span data-ttu-id="595a6-447">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-447">Everyone in your organization</span></span>     | <span data-ttu-id="595a6-448">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="595a6-448">Wait in lobby</span></span>        |
|   | <span data-ttu-id="595a6-449">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-449">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="595a6-450">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="595a6-450">Wait in lobby</span></span>         |

<span data-ttu-id="595a6-451">다음은 인증 된 사용자가 모임에 없는 경우의 익명 사용자의 참가 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-451">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="595a6-452">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-452">Allow anonymous people to start a meeting</span></span> |<span data-ttu-id="595a6-453">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="595a6-453">Automatically admit people</span></span>  |<span data-ttu-id="595a6-454">익명 사용자의 참가 동작</span><span class="sxs-lookup"><span data-stu-id="595a6-454">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="595a6-455">False</span><span class="sxs-lookup"><span data-stu-id="595a6-455">True</span></span>    | <span data-ttu-id="595a6-456">가</span><span class="sxs-lookup"><span data-stu-id="595a6-456">Everyone</span></span>      | <span data-ttu-id="595a6-457">직접 참가</span><span class="sxs-lookup"><span data-stu-id="595a6-457">Join directly</span></span>         |
|   | <span data-ttu-id="595a6-458">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-458">Everyone in your organization</span></span>       | <span data-ttu-id="595a6-459">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="595a6-459">Wait in lobby</span></span>        |
|   | <span data-ttu-id="595a6-460">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-460">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="595a6-461">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="595a6-461">Wait in lobby</span></span>         |
|<span data-ttu-id="595a6-462">해제</span><span class="sxs-lookup"><span data-stu-id="595a6-462">False</span></span>    | <span data-ttu-id="595a6-463">가</span><span class="sxs-lookup"><span data-stu-id="595a6-463">Everyone</span></span>        | <span data-ttu-id="595a6-464">대기실에서 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-464">Wait in lobby.</span></span> <span data-ttu-id="595a6-465">인증 된 첫 번째 사용자가 모임에 참가 하면 사용자가 자동으로 허가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-465">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="595a6-466">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-466">Everyone in your organization</span></span>     |<span data-ttu-id="595a6-467">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="595a6-467">Wait in lobby</span></span>         |
|   | <span data-ttu-id="595a6-468">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-468">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="595a6-469">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="595a6-469">Wait in lobby</span></span>         |

### <a name="allow-dial-in-users-to-bypass-the-lobby-coming-soon"></a><span data-ttu-id="595a6-470">전화 접속 사용자가 대기실를 우회할 수 있도록 허용 (예정 대로)</span><span class="sxs-lookup"><span data-stu-id="595a6-470">Allow dial-in users to bypass the lobby (coming soon)</span></span>

<span data-ttu-id="595a6-471">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-471">This is a per-organizer policy.</span></span> <span data-ttu-id="595a6-472">이 설정은 전화를 통해 전화를 거는 사용자가 모임에 직접 참가 하거나 **자동으로** 허용 되는 사용자 설정에 관계 없이 대기실에서 대기할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-472">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span>

<span data-ttu-id="595a6-473">휴대폰에서 전화를 거는 사용자의 참가 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-473">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="595a6-474">전화 접속 사용자가 대기실를 우회할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="595a6-474">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="595a6-475">자동으로 사용자를 인정 합니다.</span><span class="sxs-lookup"><span data-stu-id="595a6-475">Automatically admit users</span></span>  |<span data-ttu-id="595a6-476">전화 접속 사용자의 참가 동작</span><span class="sxs-lookup"><span data-stu-id="595a6-476">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="595a6-477">False</span><span class="sxs-lookup"><span data-stu-id="595a6-477">True</span></span>    | <span data-ttu-id="595a6-478">가</span><span class="sxs-lookup"><span data-stu-id="595a6-478">Everyone</span></span>      | <span data-ttu-id="595a6-479">직접 참가</span><span class="sxs-lookup"><span data-stu-id="595a6-479">Join directly</span></span>         |
|   | <span data-ttu-id="595a6-480">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-480">Everyone in your organization</span></span>       | <span data-ttu-id="595a6-481">직접 참가</span><span class="sxs-lookup"><span data-stu-id="595a6-481">Join directly</span></span>        |
|   | <span data-ttu-id="595a6-482">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-482">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="595a6-483">직접 참가</span><span class="sxs-lookup"><span data-stu-id="595a6-483">Join directly</span></span>         |
|<span data-ttu-id="595a6-484">해제</span><span class="sxs-lookup"><span data-stu-id="595a6-484">False</span></span>    | <span data-ttu-id="595a6-485">가</span><span class="sxs-lookup"><span data-stu-id="595a6-485">Everyone</span></span>        | <span data-ttu-id="595a6-486">직접 참가</span><span class="sxs-lookup"><span data-stu-id="595a6-486">Join directly</span></span>        |
|   | <span data-ttu-id="595a6-487">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-487">Everyone in your organization</span></span>     |<span data-ttu-id="595a6-488">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="595a6-488">Wait in lobby</span></span>         |
|   | <span data-ttu-id="595a6-489">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="595a6-489">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="595a6-490">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="595a6-490">Wait in lobby</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="595a6-491">관련 항목</span><span class="sxs-lookup"><span data-stu-id="595a6-491">Related topics</span></span>
[<span data-ttu-id="595a6-492">팀의 메시징 정책</span><span class="sxs-lookup"><span data-stu-id="595a6-492">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
