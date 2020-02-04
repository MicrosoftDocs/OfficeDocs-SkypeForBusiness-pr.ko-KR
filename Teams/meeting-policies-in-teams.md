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
f1.keywords:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: 팀에서 모임 정책 설정을 관리 하는 방법에 대해 알아보세요.
ms.openlocfilehash: 2223882020bf9ea045e18d42c6591eceba628999
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708844"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="dc259-103">팀에서 모임 정책 관리</span><span class="sxs-lookup"><span data-stu-id="dc259-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="dc259-104">모임 정책은 조직의 사용자가 예약한 모임에 대해 모임 참가자가 사용할 수 있는 기능을 제어 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="dc259-105">정책을 만들고 변경한 후 정책에 사용자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="dc259-106">Microsoft 팀 관리 센터에서 또는 [PowerShell](teams-powershell-overview.md)을 사용 하 여 모임 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="dc259-107">모임 시작, 모임 중 또는 모임 이후 사용자의 모임 환경에 영향을 주는 다음과 같은 방법으로 정책을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="dc259-108">구현 형식</span><span class="sxs-lookup"><span data-stu-id="dc259-108">Implementation type</span></span>  |<span data-ttu-id="dc259-109">설명</span><span class="sxs-lookup"><span data-stu-id="dc259-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="dc259-110">이끌이 별</span><span class="sxs-lookup"><span data-stu-id="dc259-110">Per-organizer</span></span>    |<span data-ttu-id="dc259-111">이끌이 별 정책을 구현 하는 경우 모든 모임 참가자는 해당 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="dc259-112">예를 들어 사용자가 **자동으로** 허용 이끌이 정책 이며 사용자가 모임에 직접 참가 하는지 여부를 제어 하 고 정책에 할당 된 사용자가 예약한 모임에 대해 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="dc259-113">사용자별</span><span class="sxs-lookup"><span data-stu-id="dc259-113">Per-user</span></span>    |<span data-ttu-id="dc259-114">사용자별 정책을 구현할 때, 이끌이 및/또는 모임 참가자에 대 한 특정 기능을 제한 하는 사용자별 정책만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="dc259-115">예를 들어 **채널에서 모임** 시작을 허용 하는 것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-115">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="dc259-116">이끌이와 사용자 단위</span><span class="sxs-lookup"><span data-stu-id="dc259-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="dc259-117">이끌이 및 사용자별 정책 조합을 구현 하는 경우 특정 기능은 해당 정책 및 이끌이의 정책에 따라 모임 참가자에 대해 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="dc259-118">예를 들어 **클라우드 기록은 허용** -이끌이 및 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="dc259-119">이 설정을 사용 하 여 모임 이끌이 및 참가자가 녹음/녹화를 시작 하 고 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="dc259-120">기본적으로 Global (조직 전체 기본값) 이라는 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-120">By default, a policy named Global (Org-wide default) is created.</span></span> <span data-ttu-id="dc259-121">조직의 모든 사용자는 기본적으로 전역 모임 정책에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-121">All users in your organization are assigned the Global meeting policy by default.</span></span> <span data-ttu-id="dc259-122">이를 변경 하거나 하나 이상의 사용자 지정 정책을 만들어 사용자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-122">You can either make changes to it or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="dc259-123">사용자 지정 정책을 만들고 할당 하지 않으면 사용자가 글로벌 정책을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-123">Users will get the Global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="dc259-124">사용자 지정 정책을 만들 때 사용자가 특정 기능을 사용할 수 있도록 허용 하거나 금지할 수 있으며 설정을 적용할 사용자 하나 이상에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-124">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span>

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="dc259-125">모임 정책 변경 또는 만들기</span><span class="sxs-lookup"><span data-stu-id="dc259-125">Change or create a meeting policy</span></span>

<span data-ttu-id="dc259-126">모임 정책을 변경 하거나 만들려면 Microsoft 팀 관리 센터 > **모임** > **모임 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-126">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="dc259-127">목록에서 정책을 선택 하거나 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-127">Select a policy from the list or select **Add**.</span></span> <span data-ttu-id="dc259-128">새 정책을 만드는 경우 이름 및 설명을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-128">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="dc259-129">이름은 특수 문자를 포함 하거나 64 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-129">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="dc259-130">설정을 선택 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-130">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="dc259-131">예를 들어 사용자가 여러 명 있고 모임에 필요한 대역폭의 양을 제한 하려고 한다고 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="dc259-131">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="dc259-132">"제한 된 대역폭" 이라는 새 사용자 지정 정책을 만들고 다음 설정을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-132">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="dc259-133">**오디오 & 비디오**:</span><span class="sxs-lookup"><span data-stu-id="dc259-133">Under **Audio & video**:</span></span>
- <span data-ttu-id="dc259-134">클라우드 기록 허용을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-134">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="dc259-135">IP 비디오 허용 설정을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-135">Turn off Allow IP video.</span></span>

<span data-ttu-id="dc259-136">**콘텐츠 공유**에서:</span><span class="sxs-lookup"><span data-stu-id="dc259-136">Under **Content sharing**:</span></span>
- <span data-ttu-id="dc259-137">화면 공유 모드를 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-137">Disable screen sharing mode.</span></span>
- <span data-ttu-id="dc259-138">화이트 보드 허용 기능을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-138">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="dc259-139">공유 메모 허용 기능을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-139">Turn off Allow shared notes.</span></span>

<span data-ttu-id="dc259-140">그런 다음 사용자에 게 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-140">Then assign the policy to the users.</span></span>

> [!NOTE]
> <span data-ttu-id="dc259-141">사용자는 한 번에 하나의 모임 정책만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-141">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="dc259-142">사용자에 게 모임 정책 할당</span><span class="sxs-lookup"><span data-stu-id="dc259-142">Assign a meeting policy to users</span></span>

1. <span data-ttu-id="dc259-143">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 다음 사용자를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="dc259-144">사용자 이름 왼쪽의을 클릭 하 여 사용자를 선택 하 고 **설정 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-144">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="dc259-145">**모임 정책**에서 할당 하려는 정책을 선택한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-145">Under **Meeting policy**, select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="dc259-146">한 번에 여러 사용자에 게 정책을 할당 하려면 [팀 사용자 설정을 일괄적으로 편집](edit-user-settings-in-bulk.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc259-146">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="dc259-147">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-147">Or, you can also do the following:</span></span>

1. <span data-ttu-id="dc259-148">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **모임** > **모임 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-148">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="dc259-149">정책 이름 왼쪽에 있는을 클릭 하 여 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-149">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="dc259-150">**사용자 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-150">Select **Manage users**.</span></span>
4. <span data-ttu-id="dc259-151">**사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-151">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="dc259-152">추가 하려는 각 사용자에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-152">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="dc259-153">사용자 추가를 마쳤으면 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-153">After you finish adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="dc259-154">사용자가 할당 된 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-154">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="dc259-155">먼저 영향을 받는 모든 사용자에 게 다른 정책을 할당 한 다음 원래 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-155">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="dc259-156">모임 정책 설정</span><span class="sxs-lookup"><span data-stu-id="dc259-156">Meeting policy settings</span></span>

<span data-ttu-id="dc259-157">**모임 정책** 페이지에서 기존 정책을 선택 하거나 **추가** 를 선택 하 여 새 정책을 추가 하면 다음에 대 한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-157">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="dc259-158">일반</span><span class="sxs-lookup"><span data-stu-id="dc259-158">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="dc259-159">오디오 & 비디오</span><span class="sxs-lookup"><span data-stu-id="dc259-159">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="dc259-160">콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="dc259-160">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="dc259-161">참가자가 게스트를 &</span><span class="sxs-lookup"><span data-stu-id="dc259-161">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="dc259-162"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="dc259-162"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="dc259-163">모임 정책 설정-일반</span><span class="sxs-lookup"><span data-stu-id="dc259-163">Meeting policy settings - General</span></span>

- [<span data-ttu-id="dc259-164">채널에서 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-164">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="dc259-165">Outlook 추가 기능 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-165">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="dc259-166">채널 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-166">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="dc259-167">개인 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-167">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="dc259-168">채널에서 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-168">Allow Meet now in channels</span></span>

<span data-ttu-id="dc259-169">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-169">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="dc259-170">이 설정은 사용자가 팀 채널에서 임시 모임을 시작할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-170">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="dc259-171">이 기능을 설정 하면 사용자가 팀 채널에서 메시지를 게시할 때 작성 **상자 아래에 있는 모임 시작** 을 클릭 하 여 채널에서 특별 모임을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-171">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span>

![메시지 아래에 모임 시작 아이콘을 표시 하는 스크린샷](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="dc259-173">Outlook 추가 기능 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-173">Allow the Outlook add-in</span></span>

<span data-ttu-id="dc259-174">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-174">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="dc259-175">이 설정은 Outlook (Windows, Mac, 웹, 모바일)에서 팀 모임을 예약할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-175">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![새 모임 예약 기능을 보여 주는 스크린샷](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="dc259-177">이 기능을 해제 하면 사용자가 Outlook에서 새 모임을 만들 때 팀 회의를 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-177">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="dc259-178">예를 들어 Windows의 Outlook에서는 **새 팀 모임** 옵션이 리본 메뉴에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-178">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="dc259-179">채널 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-179">Allow channel meeting scheduling</span></span>

<span data-ttu-id="dc259-180">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-180">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="dc259-181">이 설정은 사용자가 팀 채널에서 모임을 예약할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-181">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="dc259-182">이 기능을 해제 하면 사용자가 팀 채널에서 모임을 시작할 때 **모임 예약** 옵션을 사용할 수 없으며, 팀의 사용자에 대해 **채널 추가** 옵션이 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-182">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add channel** option is disabled for users in Teams.</span></span>

![팀의 모임 예약 옵션을 보여 주는 스크린샷](media/meeting-policies-schedule-a-meeting.png)

![모임에 적용할 채널 선택 옵션을 보여 주는 스크린샷](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="dc259-185">개인 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-185">Allow scheduling private meetings</span></span>

<span data-ttu-id="dc259-186">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-186">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="dc259-187">이 설정은 사용자가 팀에서 비공개 모임을 예약할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-187">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="dc259-188">모임이 팀의 채널에 게시 되지 않은 경우 비공개 모임입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-188">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="dc259-189">**개인 모임 예약 허용** 을 해제 하 고 **채널 모임 예약을 허용**하는 경우 팀의 사용자는 **필수 참석자 추가** 및 **채널 추가** 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-189">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span>

<span data-ttu-id="dc259-190"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="dc259-190"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="dc259-191">모임 정책 설정-오디오 & 비디오</span><span class="sxs-lookup"><span data-stu-id="dc259-191">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="dc259-192">내용 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-192">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="dc259-193">클라우드 기록 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-193">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="dc259-194">IP 비디오 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-194">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="dc259-195">미디어 비트 전송률 (KBs)</span><span class="sxs-lookup"><span data-stu-id="dc259-195">Media bit rate (KBs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="dc259-196">내용 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-196">Allow transcription</span></span>

<span data-ttu-id="dc259-197">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-197">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="dc259-198">이 설정은 모임 녹음/녹화를 재생 하는 동안 캡션과 기록 기능을 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-198">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="dc259-199">이 기능을 해제 하면 모임 녹음/녹화를 재생 하는 동안 **검색** 및 **참조** 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-199">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="dc259-200">녹음/녹화를 시작한 사람에 게는 녹음/녹화가 포함 되도록이 설정이 켜져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-200">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="dc259-201">기록 된 모임에 대 한 정보는 현재 팀의 언어를 영어로 설정한 경우와 모임에서 영어를 사용 하 고 있는 사용자만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-201">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![모임의 기록 옵션을 보여 주는 스크린샷](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="dc259-203">클라우드 기록 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-203">Allow cloud recording</span></span>

<span data-ttu-id="dc259-204">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-204">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="dc259-205">이 설정은 사용자의 모임을 녹화할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-205">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="dc259-206">참가자에 대해 정책 설정이 설정 된 경우와 다른 모임 참가자가 같은 조직의 인증 된 사용자 인 경우 기록을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-206">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="dc259-207">페더레이션 및 익명 사용자 등 조직 외부의 사용자가 녹음/녹화를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-207">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="dc259-208">게스트 사용자는 녹음/녹화를 시작 하거나 중지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-208">Guest users can't start or stop the recording.</span></span> 

![기록 옵션을 보여 주는 스크린샷](media/meeting-policies-recording.png)

<span data-ttu-id="dc259-210">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-210">Let's look at the following example.</span></span>

|<span data-ttu-id="dc259-211">사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-211">User</span></span> |<span data-ttu-id="dc259-212">모임 정책</span><span class="sxs-lookup"><span data-stu-id="dc259-212">Meeting policy</span></span>  |<span data-ttu-id="dc259-213">클라우드 기록 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-213">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dc259-214">Daniela</span><span class="sxs-lookup"><span data-stu-id="dc259-214">Daniela</span></span> | <span data-ttu-id="dc259-215">전역</span><span class="sxs-lookup"><span data-stu-id="dc259-215">Global</span></span>   | <span data-ttu-id="dc259-216">해제</span><span class="sxs-lookup"><span data-stu-id="dc259-216">False</span></span> |
|<span data-ttu-id="dc259-217">Amanda</span><span class="sxs-lookup"><span data-stu-id="dc259-217">Amanda</span></span> | <span data-ttu-id="dc259-218">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dc259-218">Location1MeetingPolicy</span></span> | <span data-ttu-id="dc259-219">False</span><span class="sxs-lookup"><span data-stu-id="dc259-219">True</span></span>|
|<span data-ttu-id="dc259-220">John (외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="dc259-220">John (external user)</span></span> | <span data-ttu-id="dc259-221">해당 없음</span><span class="sxs-lookup"><span data-stu-id="dc259-221">Not applicable</span></span> | <span data-ttu-id="dc259-222">해당 없음</span><span class="sxs-lookup"><span data-stu-id="dc259-222">Not applicable</span></span>|

<span data-ttu-id="dc259-223">Daniela에서 구성한 모임은 기록 하 고 Amanda 수 있으며, 정책 설정을 사용 하도록 설정한 경우 Daniela로 구성 된 모임을 녹화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-223">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="dc259-224">Amanda에서 구성한 모임은 녹화할 수 있지만, Daniela는 정책 설정을 사용 하지 않도록 설정 하 고 외부 사용자 인 John은 Amanda으로 구성 된 모임을 기록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-224">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="dc259-225">클라우드 모임 기록에 대해 자세히 알아보려면 [팀 클라우드 모임 기록을](cloud-recording.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc259-225">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="dc259-226">IP 비디오 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-226">Allow IP video</span></span>

<span data-ttu-id="dc259-227">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-227">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="dc259-228">비디오는 모임에 대 한 주요 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-228">Video is a key component to meetings.</span></span> <span data-ttu-id="dc259-229">일부 조직에서는 관리자가 어떤 사용자의 모임이 비디오를 보유 하 고 있는지 더 자세히 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-229">In some organizations, admins might want more control over which users’ meetings have video.</span></span> <span data-ttu-id="dc259-230">이 설정은 사용자가 호스트 하는 모임 및 사용자가 시작한 1:1 통화 및 그룹 통화에서 비디오를 켤 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-230">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="dc259-231">이 정책을 사용 하도록 설정한 사용자가 구성한 모임에는 모임 참가자가 정책을 사용 하도록 설정한 경우 모임 참가자가 모임에서 비디오 공유를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-231">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="dc259-232">배정 된 정책이 없는 모임 참가자 (예: 익명 및 페더레이션 참가자)는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-232">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![오디오 및 비디오 설정을 사용 하 여 모임을 보여 주는 스크린샷](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="dc259-234">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-234">Let's look at the following example.</span></span>

|<span data-ttu-id="dc259-235">사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-235">User</span></span> |<span data-ttu-id="dc259-236">모임 정책</span><span class="sxs-lookup"><span data-stu-id="dc259-236">Meeting policy</span></span>  |<span data-ttu-id="dc259-237">IP 영상 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-237">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dc259-238">Daniela</span><span class="sxs-lookup"><span data-stu-id="dc259-238">Daniela</span></span>   | <span data-ttu-id="dc259-239">전역</span><span class="sxs-lookup"><span data-stu-id="dc259-239">Global</span></span>   | <span data-ttu-id="dc259-240">False</span><span class="sxs-lookup"><span data-stu-id="dc259-240">True</span></span>        |
|<span data-ttu-id="dc259-241">Amanda</span><span class="sxs-lookup"><span data-stu-id="dc259-241">Amanda</span></span>    | <span data-ttu-id="dc259-242">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dc259-242">Location1MeetingPolicy</span></span>        | <span data-ttu-id="dc259-243">해제</span><span class="sxs-lookup"><span data-stu-id="dc259-243">False</span></span>      |

<span data-ttu-id="dc259-244">Daniela에서 호스팅하는 모임은 영상 통화를 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-244">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="dc259-245">Daniela 모임에 참가 하 고 비디오를 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-245">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="dc259-246">Amanda의 정책이 비디오를 허용 하지 않도록 설정 되어 있기 때문에 Daniela 모임에서 비디오를 켤 수 없습니다 Amanda.</span><span class="sxs-lookup"><span data-stu-id="dc259-246">Amanda can't turn on video in Daniela's meeting because Amanda’s policy is set to not allow video.</span></span> <span data-ttu-id="dc259-247">Amanda는 모임의 다른 참가자가 공유 하는 비디오를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-247">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="dc259-248">Amanda에서 호스팅하는 모임에서 할당 된 비디오 정책에 관계 없이 비디오를 켤 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-248">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="dc259-249">이는 Daniela에서 Amanda의 모임에서 비디오를 켤 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-249">This means Daniela can't turn on video in Amanda’s meetings.</span></span>  

<span data-ttu-id="dc259-250">Daniela에서 비디오를 사용 하 여 Amanda를 호출 하는 경우 Amanda는 오디오 만으로 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-250">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="dc259-251">통화가 연결 되 면 Amanda에서 Daniela의 비디오를 볼 수 있지만 영상 통화는 켜지 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-251">When the call is connected, Amanda can see Daniela’s video, but can't turn on video.</span></span> <span data-ttu-id="dc259-252">Amanda에서 Daniela를 호출 하는 경우 Daniela는 비디오 및 오디오로 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-252">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="dc259-253">통화가 연결 되 면 필요에 따라 Daniela에서 비디오를 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-253">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="dc259-254">미디어 비트 전송률 (KBs)</span><span class="sxs-lookup"><span data-stu-id="dc259-254">Media bit rate (KBs)</span></span>

<span data-ttu-id="dc259-255">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-255">This is a per-user policy.</span></span> <span data-ttu-id="dc259-256">이 설정에 따라 사용자에 대 한 통화 및 모임에서 오디오, 비디오 및 비디오 기반 앱 공유 전송의 미디어 비트 전송률이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-256">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="dc259-257">통화 또는 모임에서 사용자의 업링크 및 다운 링크 미디어 트래버스 둘 다에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-257">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="dc259-258">이 설정을 사용 하면 조직의 대역폭을 관리 하는 방법을 세부적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-258">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="dc259-259">사용자에 게 필요한 모임 시나리오에 따라 좋은 품질 환경을 위해 적절 한 대역폭을 확보 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-259">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="dc259-260">최소값은 30kbps이 고 최대값은 모임 시나리오에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-260">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="dc259-261">팀에서 좋은 음질의 모임, 통화, 라이브 이벤트에 권장 되는 최소 대역폭에 대해 자세히 알아보려면 [대역폭 요구 사항을](prepare-network.md#bandwidth-requirements)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc259-261">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="dc259-262">모임에 대 한 대역폭이 충분 하지 않은 경우 참가자는 네트워크 품질이 좋지 않다는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-262">If there isn’t enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="dc259-263">CEO 보드 모임 및 팀 라이브 이벤트와 같이 고품질의 비디오 환경을 필요로 하는 모임의 경우 대역폭을 10mbps로 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-263">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="dc259-264">최대 환경이 설정 된 경우에도 시나리오에 따라 특정 네트워크 조건이 감지 되는 경우 팀 미디어 스택이 낮은 대역폭 조건에 적응 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-264">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="dc259-265">모임 정책 설정-콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="dc259-265">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="dc259-266">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="dc259-266">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="dc259-267">참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-267">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="dc259-268">외부 참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-268">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="dc259-269">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-269">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="dc259-270">화이트 보드 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-270">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="dc259-271">공유 메모 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-271">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="dc259-272">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="dc259-272">Screen sharing mode</span></span>

<span data-ttu-id="dc259-273">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-273">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="dc259-274">이 설정은 사용자의 모임에서 데스크톱 및/또는 창 공유를 허용할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-274">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="dc259-275">배정 된 정책이 없는 모임 참가자 (예: 익명, 게스트, B2B, 페더레이션 참가자)는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-275">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="dc259-276">값 설정</span><span class="sxs-lookup"><span data-stu-id="dc259-276">Setting value</span></span> |<span data-ttu-id="dc259-277">결과가</span><span class="sxs-lookup"><span data-stu-id="dc259-277">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="dc259-278">**전체 화면**</span><span class="sxs-lookup"><span data-stu-id="dc259-278">**Entire screen**</span></span>    | <span data-ttu-id="dc259-279">모임에서 전체 데스크톱 공유 및 응용 프로그램 공유를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-279">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="dc259-280">**단일 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="dc259-280">**Single application**</span></span>   | <span data-ttu-id="dc259-281">모임에서 응용 프로그램 공유가 허용 됨</span><span class="sxs-lookup"><span data-stu-id="dc259-281">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="dc259-282">**비활성화**</span><span class="sxs-lookup"><span data-stu-id="dc259-282">**Disabled**</span></span>     |<span data-ttu-id="dc259-283">모임에서 화면 공유 및 응용 프로그램 공유 기능을 해제 했습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-283">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="dc259-284">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-284">Let's look at the following example.</span></span>

|<span data-ttu-id="dc259-285">사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-285">User</span></span> |<span data-ttu-id="dc259-286">모임 정책</span><span class="sxs-lookup"><span data-stu-id="dc259-286">Meeting policy</span></span> |<span data-ttu-id="dc259-287">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="dc259-287">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dc259-288">Daniela</span><span class="sxs-lookup"><span data-stu-id="dc259-288">Daniela</span></span>  | <span data-ttu-id="dc259-289">전역</span><span class="sxs-lookup"><span data-stu-id="dc259-289">Global</span></span>   | <span data-ttu-id="dc259-290">전체 화면</span><span class="sxs-lookup"><span data-stu-id="dc259-290">Entire screen</span></span> |
|<span data-ttu-id="dc259-291">Amanda</span><span class="sxs-lookup"><span data-stu-id="dc259-291">Amanda</span></span>   | <span data-ttu-id="dc259-292">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dc259-292">Location1MeetingPolicy</span></span>  | <span data-ttu-id="dc259-293">비활성화</span><span class="sxs-lookup"><span data-stu-id="dc259-293">Disabled</span></span> |

<span data-ttu-id="dc259-294">Daniela에서 호스팅하는 모임은 모임 참가자가 전체 화면 또는 특정 응용 프로그램을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-294">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="dc259-295">Amanda 참가 Daniela의 모임이 Amanda, 화면을 공유할 수 없거나, 정책 설정에 따라 특정 응용 프로그램을 사용 하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-295">If Amanda joins Daniela’s meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="dc259-296">Amanda에서 호스트 하는 모임에서는 자신에 게 할당 된 화면 공유 모드 정책에 관계 없이 화면 또는 단일 응용 프로그램을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-296">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="dc259-297">즉, Daniela는 Amanda 모임의 화면 또는 단일 응용 프로그램을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-297">This means that Daniela can't share her screen or a single application in Amanda’s meetings.</span></span>  

<span data-ttu-id="dc259-298">현재 사용자는 Google Chrome을 사용 하는 경우 팀 모임에서 비디오를 재생 하거나 화면을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-298">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="dc259-299">참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-299">Allow a participant to give or request control</span></span>

<span data-ttu-id="dc259-300">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-300">This is a per-user policy.</span></span> <span data-ttu-id="dc259-301">이 설정은 사용자가 공유 데스크톱 또는 창을 다른 모임 참가자에 게 제어권을 부여할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-301">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="dc259-302">컨트롤을 제공 하려면 화면 위쪽을 마우스로 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-302">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="dc259-303">사용자에 대해이 설정이 설정 된 경우 **제어권 제공** 옵션이 공유 세션의 위쪽 표시줄에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-303">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![제어권 제공 옵션을 보여 주는 스크린샷](media/meeting-policies-give-control.png)

<span data-ttu-id="dc259-305">사용자에 대해 설정이 꺼져 있으면 **제어권 제공** 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-305">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![제어권 부여 옵션을 사용할 수 없음을 보여 주는 스크린샷](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="dc259-307">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-307">Let's look at the following example.</span></span>

|<span data-ttu-id="dc259-308">사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-308">User</span></span> |<span data-ttu-id="dc259-309">모임 정책</span><span class="sxs-lookup"><span data-stu-id="dc259-309">Meeting policy</span></span>  |<span data-ttu-id="dc259-310">참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-310">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dc259-311">Daniela</span><span class="sxs-lookup"><span data-stu-id="dc259-311">Daniela</span></span>   | <span data-ttu-id="dc259-312">전역</span><span class="sxs-lookup"><span data-stu-id="dc259-312">Global</span></span>   | <span data-ttu-id="dc259-313">False</span><span class="sxs-lookup"><span data-stu-id="dc259-313">True</span></span>       |
|<span data-ttu-id="dc259-314">Babek</span><span class="sxs-lookup"><span data-stu-id="dc259-314">Babek</span></span>    | <span data-ttu-id="dc259-315">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dc259-315">Location1MeetingPolicy</span></span>        | <span data-ttu-id="dc259-316">해제</span><span class="sxs-lookup"><span data-stu-id="dc259-316">False</span></span>   |

<span data-ttu-id="dc259-317">Daniela는 다른 참가자에 게 제어권을 부여할 수 없기 때문에 Babek에서 구성한 모임의 다른 참가자에 게 공유 데스크톱 또는 창을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-317">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="dc259-318">PowerShell을 사용 하 여 제어권을 제공 하거나 제어권 요청을 받을 수 있는 사람을 제어 하려면 AllowParticipantGiveRequestControl cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-318">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="dc259-319">공유 중 공유 콘텐츠를 관리 하 고 제어 하려면 두 파티 모두 팀 데스크톱 클라이언트를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-319">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="dc259-320">컨트롤은 어느 쪽이든 브라우저에서 Teams를 실행 중인 경우 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-320">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="dc259-321">이것은 해결하려고 하는 기술적 제한 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-321">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="dc259-322">외부 참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-322">Allow an external participant to give or request control</span></span>

<span data-ttu-id="dc259-323">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-323">This is a per-user policy.</span></span> <span data-ttu-id="dc259-324">이 설정은 모임의 외부 참가자가 모임의 다른 참가자에 게 공유 데스크톱 또는 창을 제어할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-324">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="dc259-325">팀 회의의 외부 참가자는 다음과 같이 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-325">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="dc259-326">익명 사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-326">Anonymous user</span></span>
- <span data-ttu-id="dc259-327">게스트 사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-327">Guest users</span></span>  
- <span data-ttu-id="dc259-328">B2B 사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-328">B2B user</span></span>
- <span data-ttu-id="dc259-329">페더레이션 사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-329">Federated user</span></span>  

<span data-ttu-id="dc259-330">공유 된 사용자가 외부 참가자가 조직에서 **제어권을 부여 하거나 요청할 수 있도록 허용을** 제어 하도록 설정 되어 있는 동안 페더레이션 사용자가 해당 사용자에 게 제어권을 부여할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="dc259-330">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="dc259-331">PowerShell을 사용 하 여 외부 참가자가 제어권을 제공 하거나 제어권 요청을 수락할 수 있는지 여부를 제어 하려면 AllowExternalParticipantGiveRequestControl cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-331">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="dc259-332">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-332">Allow PowerPoint sharing</span></span>

<span data-ttu-id="dc259-333">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-333">This is a per-user policy.</span></span> <span data-ttu-id="dc259-334">이 설정은 사용자가 모임에서 PowerPoint 슬라이드 데크를 공유할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-334">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="dc259-335">익명, 게스트, 페더레이션 사용자를 비롯 한 외부 사용자가 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-335">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="dc259-336">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-336">Let's look at the following example.</span></span>

|<span data-ttu-id="dc259-337">사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-337">User</span></span> |<span data-ttu-id="dc259-338">모임 정책</span><span class="sxs-lookup"><span data-stu-id="dc259-338">Meeting policy</span></span>  |<span data-ttu-id="dc259-339">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-339">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dc259-340">Daniela</span><span class="sxs-lookup"><span data-stu-id="dc259-340">Daniela</span></span>   | <span data-ttu-id="dc259-341">전역</span><span class="sxs-lookup"><span data-stu-id="dc259-341">Global</span></span>   | <span data-ttu-id="dc259-342">False</span><span class="sxs-lookup"><span data-stu-id="dc259-342">True</span></span>       |
|<span data-ttu-id="dc259-343">Amanda</span><span class="sxs-lookup"><span data-stu-id="dc259-343">Amanda</span></span>   | <span data-ttu-id="dc259-344">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dc259-344">Location1MeetingPolicy</span></span>        | <span data-ttu-id="dc259-345">해제</span><span class="sxs-lookup"><span data-stu-id="dc259-345">False</span></span>   |

<span data-ttu-id="dc259-346">Amanda 모임 이끌이 인 경우에도 모임에서 PowerPoint 슬라이드 데크를 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-346">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="dc259-347">Daniela는 모임이 Amanda으로 구성 된 경우에도 PowerPoint 슬라이드 데크를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-347">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="dc259-348">Amanda는 PowerPoint 슬라이드 데크를 공유할 수는 없지만 모임에서 다른 사용자가 공유한 PowerPoint 슬라이드 데크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-348">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="dc259-349">화이트 보드 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-349">Allow whiteboard</span></span>

<span data-ttu-id="dc259-350">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-350">This is a per-user policy.</span></span> <span data-ttu-id="dc259-351">이 설정은 사용자가 모임에서 화이트 보드를 공유할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-351">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="dc259-352">익명, B2B, 페더레이션 사용자 등의 외부 사용자는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-352">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="dc259-353">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-353">Let's look at the following example.</span></span>

|<span data-ttu-id="dc259-354">사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-354">User</span></span> |<span data-ttu-id="dc259-355">모임 정책</span><span class="sxs-lookup"><span data-stu-id="dc259-355">Meeting policy</span></span>  |<span data-ttu-id="dc259-356">화이트 보드 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-356">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="dc259-357">Daniela</span><span class="sxs-lookup"><span data-stu-id="dc259-357">Daniela</span></span>   | <span data-ttu-id="dc259-358">전역</span><span class="sxs-lookup"><span data-stu-id="dc259-358">Global</span></span>   | <span data-ttu-id="dc259-359">False</span><span class="sxs-lookup"><span data-stu-id="dc259-359">True</span></span>       |
|<span data-ttu-id="dc259-360">Amanda</span><span class="sxs-lookup"><span data-stu-id="dc259-360">Amanda</span></span>   | <span data-ttu-id="dc259-361">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dc259-361">Location1MeetingPolicy</span></span>        | <span data-ttu-id="dc259-362">해제</span><span class="sxs-lookup"><span data-stu-id="dc259-362">False</span></span>   |

<span data-ttu-id="dc259-363">Amanda 모임 이끌이 인 경우에도 모임에서 화이트 보드를 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-363">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="dc259-364">Daniela는 모임이 Amanda으로 구성 된 경우에도 화이트 보드를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-364">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="dc259-365">공유 메모 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-365">Allow shared notes</span></span>

<span data-ttu-id="dc259-366">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-366">This is a per-user policy.</span></span> <span data-ttu-id="dc259-367">이 설정은 사용자가 모임에서 노트를 만들고 공유할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-367">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="dc259-368">익명, B2B, 페더레이션 사용자 등의 외부 사용자는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-368">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="dc259-369">**모임 메모** 탭은 현재 20 명 미만의 참가자가 있는 모임 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-369">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="dc259-370">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-370">Let's look at the following example.</span></span>

|<span data-ttu-id="dc259-371">사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-371">User</span></span> |<span data-ttu-id="dc259-372">모임 정책</span><span class="sxs-lookup"><span data-stu-id="dc259-372">Meeting policy</span></span>  |<span data-ttu-id="dc259-373">공유 메모 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-373">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dc259-374">Daniela</span><span class="sxs-lookup"><span data-stu-id="dc259-374">Daniela</span></span>   | <span data-ttu-id="dc259-375">전역</span><span class="sxs-lookup"><span data-stu-id="dc259-375">Global</span></span>   | <span data-ttu-id="dc259-376">False</span><span class="sxs-lookup"><span data-stu-id="dc259-376">True</span></span>       |
|<span data-ttu-id="dc259-377">Amanda</span><span class="sxs-lookup"><span data-stu-id="dc259-377">Amanda</span></span>   | <span data-ttu-id="dc259-378">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="dc259-378">Location1MeetingPolicy</span></span> | <span data-ttu-id="dc259-379">해제</span><span class="sxs-lookup"><span data-stu-id="dc259-379">False</span></span> |

<span data-ttu-id="dc259-380">Daniela는 Amanda의 모임에 메모를 기록 하 고 모든 모임에서 메모를 찍을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-380">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="dc259-381">모임 정책 설정-게스트 & 참가자</span><span class="sxs-lookup"><span data-stu-id="dc259-381">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="dc259-382">이 설정은 모임에 참가 하기 전에 대기실에서 대기 하는 모임 참가자와 모임에서 허용 되는 참여 수준을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-382">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="dc259-383">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-383">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="dc259-384">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="dc259-384">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="dc259-385">전화 접속 사용자가 대기실를 우회할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-385">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="dc259-386">비공개 모임에서 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-386">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)
- [<span data-ttu-id="dc259-387">라이브 캡션 사용</span><span class="sxs-lookup"><span data-stu-id="dc259-387">Enable live captions </span></span>](#enable-live-captions)
- [<span data-ttu-id="dc259-388">모임에서 채팅 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-388">Allow chat in meetings </span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="dc259-389">모임에 참가 하는 옵션은 각 팀 그룹의 설정 및 연결 방법에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-389">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="dc259-390">그룹에 오디오 회의가 있고이를 사용 하 여 연결 하는 경우 [Office 365의 오디오 회의](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc259-390">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="dc259-391">팀 그룹에 오디오 회의가 없는 경우 [팀에서 모임 참가](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc259-391">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="dc259-392">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-392">Let anonymous people start a meeting</span></span>

<span data-ttu-id="dc259-393">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-393">This is a per-organizer policy.</span></span> <span data-ttu-id="dc259-394">이 설정은 B2B, 페더레이션 사용자 등의 익명 사용자가 조직에서 인증 된 사용자가 아닌 사용자의 모임에 참석할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-394">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> 

![대기 중인 사용자에 게 메시지를 표시 하는 스크린샷](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="dc259-396">인증 된 사용자가 모임에 참석 하는 경우 익명 사용자의 참가 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-396">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="dc259-397">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-397">Let anonymous people start a meeting</span></span>  |<span data-ttu-id="dc259-398">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="dc259-398">Automatically admit people</span></span> |<span data-ttu-id="dc259-399">익명 사용자의 참가 동작</span><span class="sxs-lookup"><span data-stu-id="dc259-399">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dc259-400">False</span><span class="sxs-lookup"><span data-stu-id="dc259-400">True</span></span>    | <span data-ttu-id="dc259-401">가</span><span class="sxs-lookup"><span data-stu-id="dc259-401">Everyone</span></span>      | <span data-ttu-id="dc259-402">직접 참가</span><span class="sxs-lookup"><span data-stu-id="dc259-402">Join directly</span></span>         |
|   | <span data-ttu-id="dc259-403">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-403">Everyone in your organization</span></span>       | <span data-ttu-id="dc259-404">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="dc259-404">Wait in lobby</span></span>        |
|   | <span data-ttu-id="dc259-405">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-405">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="dc259-406">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="dc259-406">Wait in lobby</span></span>         |
|<span data-ttu-id="dc259-407">해제</span><span class="sxs-lookup"><span data-stu-id="dc259-407">False</span></span>    | <span data-ttu-id="dc259-408">가</span><span class="sxs-lookup"><span data-stu-id="dc259-408">Everyone</span></span>        | <span data-ttu-id="dc259-409">직접 참가</span><span class="sxs-lookup"><span data-stu-id="dc259-409">Join directly</span></span>        |
|   | <span data-ttu-id="dc259-410">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-410">Everyone in your organization</span></span>     | <span data-ttu-id="dc259-411">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="dc259-411">Wait in lobby</span></span>        |
|   | <span data-ttu-id="dc259-412">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-412">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="dc259-413">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="dc259-413">Wait in lobby</span></span>         |

<span data-ttu-id="dc259-414">다음은 인증 된 사용자가 모임에 없는 경우의 익명 사용자의 참가 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-414">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="dc259-415">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-415">Let anonymous people start a meeting</span></span> |<span data-ttu-id="dc259-416">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="dc259-416">Automatically admit people</span></span>  |<span data-ttu-id="dc259-417">익명 사용자의 참가 동작</span><span class="sxs-lookup"><span data-stu-id="dc259-417">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dc259-418">False</span><span class="sxs-lookup"><span data-stu-id="dc259-418">True</span></span>    | <span data-ttu-id="dc259-419">가</span><span class="sxs-lookup"><span data-stu-id="dc259-419">Everyone</span></span>      | <span data-ttu-id="dc259-420">직접 참가</span><span class="sxs-lookup"><span data-stu-id="dc259-420">Join directly</span></span>         |
|   | <span data-ttu-id="dc259-421">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-421">Everyone in your organization</span></span>       | <span data-ttu-id="dc259-422">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="dc259-422">Wait in lobby</span></span>        |
|   | <span data-ttu-id="dc259-423">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-423">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="dc259-424">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="dc259-424">Wait in lobby</span></span>         |
|<span data-ttu-id="dc259-425">해제</span><span class="sxs-lookup"><span data-stu-id="dc259-425">False</span></span>    | <span data-ttu-id="dc259-426">가</span><span class="sxs-lookup"><span data-stu-id="dc259-426">Everyone</span></span>        | <span data-ttu-id="dc259-427">대기실에서 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-427">Wait in lobby.</span></span> <span data-ttu-id="dc259-428">인증 된 첫 번째 사용자가 모임에 참가 하면 사용자가 자동으로 허가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-428">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="dc259-429">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-429">Everyone in your organization</span></span>     |<span data-ttu-id="dc259-430">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="dc259-430">Wait in lobby</span></span>         |
|   | <span data-ttu-id="dc259-431">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-431">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="dc259-432">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="dc259-432">Wait in lobby</span></span>         |

### <a name="automatically-admit-people"></a><span data-ttu-id="dc259-433">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="dc259-433">Automatically admit people</span></span>

<span data-ttu-id="dc259-434">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-434">This is a per-organizer policy.</span></span> <span data-ttu-id="dc259-435">이 설정은 사용자가 인증 된 사용자가 참여 하 게 될 때까지 자신이 모임에 직접 참가 하거나 대기실에서 대기할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-435">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![대기실에 사용자가 있는 모임을 보여 주는 스크린샷](media/meeting-policies-lobby.png)

 <span data-ttu-id="dc259-437">모임 이끌이는 모임 초대에서 **모임 옵션** 을 클릭 하 여 자신이 예약한 각 모임에 대해이 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-437">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span> <span data-ttu-id="dc259-438">**(출시 예정)**</span><span class="sxs-lookup"><span data-stu-id="dc259-438">**(coming soon)**</span></span>
  
|<span data-ttu-id="dc259-439">값 설정</span><span class="sxs-lookup"><span data-stu-id="dc259-439">Setting value</span></span>  |<span data-ttu-id="dc259-440">조인 동작</span><span class="sxs-lookup"><span data-stu-id="dc259-440">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="dc259-441">**가**</span><span class="sxs-lookup"><span data-stu-id="dc259-441">**Everyone**</span></span>   |<span data-ttu-id="dc259-442">모든 모임 참가자는 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-442">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="dc259-443">여기에는 인증 된 사용자, 페더레이션 사용자, 게스트, 익명 사용자, 휴대폰으로 전화 접속 하는 사용자 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-443">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="dc259-444">**조직 및 페더레이션된 조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="dc259-444">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="dc259-445">게스트 사용자 및 페더레이션된 조직의 사용자를 포함 하 여 조직 내에서 인증 된 사용자가 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-445">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="dc259-446">익명 사용자 및 전화를 통해 전화를 거는 사용자는 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-446">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="dc259-447">**조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="dc259-447">**Everyone in your organization**</span></span>    |<span data-ttu-id="dc259-448">게스트 사용자를 포함 하 여 조직 내에서 인증 된 사용자가 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-448">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="dc259-449">연결 된 사용자, 익명 사용자, 휴대폰으로 전화를 걸고 있는 사용자는 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-449">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="dc259-450">전화 접속 사용자가 대기실를 우회할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-450">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="dc259-451">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-451">This is a per-organizer policy.</span></span> <span data-ttu-id="dc259-452">이 설정은 전화를 통해 전화를 거는 사용자가 모임에 직접 참가 하거나 **자동으로** 허용 되는 사용자 설정에 관계 없이 대기실에서 대기할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-452">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span>

<span data-ttu-id="dc259-453">휴대폰에서 전화를 거는 사용자의 참가 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-453">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="dc259-454">전화 접속 사용자가 대기실를 우회할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-454">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="dc259-455">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="dc259-455">Automatically admit people</span></span>  |<span data-ttu-id="dc259-456">전화 접속 사용자의 참가 동작</span><span class="sxs-lookup"><span data-stu-id="dc259-456">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="dc259-457">False</span><span class="sxs-lookup"><span data-stu-id="dc259-457">True</span></span>    | <span data-ttu-id="dc259-458">가</span><span class="sxs-lookup"><span data-stu-id="dc259-458">Everyone</span></span>      | <span data-ttu-id="dc259-459">직접 참가</span><span class="sxs-lookup"><span data-stu-id="dc259-459">Join directly</span></span>         |
|   | <span data-ttu-id="dc259-460">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-460">Everyone in your organization</span></span>       | <span data-ttu-id="dc259-461">직접 참가</span><span class="sxs-lookup"><span data-stu-id="dc259-461">Join directly</span></span>        |
|   | <span data-ttu-id="dc259-462">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-462">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="dc259-463">직접 참가</span><span class="sxs-lookup"><span data-stu-id="dc259-463">Join directly</span></span>         |
|<span data-ttu-id="dc259-464">해제</span><span class="sxs-lookup"><span data-stu-id="dc259-464">False</span></span>    | <span data-ttu-id="dc259-465">가</span><span class="sxs-lookup"><span data-stu-id="dc259-465">Everyone</span></span>        | <span data-ttu-id="dc259-466">직접 참가</span><span class="sxs-lookup"><span data-stu-id="dc259-466">Join directly</span></span>        |
|   | <span data-ttu-id="dc259-467">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-467">Everyone in your organization</span></span>     |<span data-ttu-id="dc259-468">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="dc259-468">Wait in lobby</span></span>         |
|   | <span data-ttu-id="dc259-469">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="dc259-469">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="dc259-470">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="dc259-470">Wait in lobby</span></span>         |

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="dc259-471">비공개 모임에서 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-471">Allow Meet now in private meetings</span></span>

<span data-ttu-id="dc259-472">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-472">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="dc259-473">이 설정은 사용자가 임시 비공개 모임을 시작할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-473">This setting controls whether a user can start an ad hoc private meeting.</span></span> 

### <a name="enable-live-captions"></a><span data-ttu-id="dc259-474">라이브 캡션 사용</span><span class="sxs-lookup"><span data-stu-id="dc259-474">Enable live captions</span></span>

<span data-ttu-id="dc259-475">이것은 사용자별 정책으로 모임 중에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-475">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="dc259-476">이 설정은 사용자가 참석할는 모임에서 실시간 **캡션 켜기** 옵션을 사용 하 여 live 캡션을 켜고 끌 것인지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-476">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![라이브 캡션 켜기 옵션을 보여 주는 스크린샷](media/meeting-policies-live-captions.png)

|<span data-ttu-id="dc259-478">값 설정</span><span class="sxs-lookup"><span data-stu-id="dc259-478">Setting value</span></span> |<span data-ttu-id="dc259-479">결과가</span><span class="sxs-lookup"><span data-stu-id="dc259-479">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="dc259-480">**사용 하지 않도록 설정 되어 있으며 이끌이는 무시할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="dc259-480">**Disabled but the organizer can override**</span></span>     | <span data-ttu-id="dc259-481">Live 캡션은 모임 중에 사용자에 대해 자동으로 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-481">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="dc259-482">사용자는 오버플로 (**...**) 메뉴에서 **라이브 캡션 켜기** 옵션을 표시 하 여 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-482">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="dc259-483">이는 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-483">This is the default setting.</span></span> |
|<span data-ttu-id="dc259-484">**비활성화**</span><span class="sxs-lookup"><span data-stu-id="dc259-484">**Disabled**</span></span>     | <span data-ttu-id="dc259-485">모임 중에는 사용자가 실시간 캡션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-485">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="dc259-486">사용자는이 옵션을 켤 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-486">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="dc259-487"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="dc259-487"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="dc259-488">모임에서 채팅 허용</span><span class="sxs-lookup"><span data-stu-id="dc259-488">Allow chat in meetings</span></span>

<span data-ttu-id="dc259-489">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-489">This is a per-organizer policy.</span></span> <span data-ttu-id="dc259-490">이 설정은 사용자의 모임에서 모임 채팅을 허용할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc259-490">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="dc259-491"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="dc259-491"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="related-topics"></a><span data-ttu-id="dc259-492">관련 주제</span><span class="sxs-lookup"><span data-stu-id="dc259-492">Related topics</span></span>

[<span data-ttu-id="dc259-493">팀의 메시징 정책</span><span class="sxs-lookup"><span data-stu-id="dc259-493">Messaging policies in Teams</span></span>](messaging-policies-in-teams.md)
