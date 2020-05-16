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
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: 팀에서 모임 정책 설정을 관리 하 고이를 사용 하 여 사용자가 예약한 모임의 모임 참가자가 사용할 수 있는 기능을 제어 하는 방법을 알아봅니다.
ms.openlocfilehash: a2c921da824bdbbcd6b0f6baf49887e55df08ca9
ms.sourcegitcommit: 296aeac481f901eb9d52b4f12a8c037afc49fa77
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "44256503"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="736ae-103">팀에서 모임 정책 관리</span><span class="sxs-lookup"><span data-stu-id="736ae-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="736ae-104">모임 정책은 조직에서 사용자가 예약한 모임 참가자가 사용할 수 있는 기능을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="736ae-105">정책을 만들고 변경한 후에 사용자를 정책에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-105">After you create a policy and make your changes, you can then assign users to the policy.</span></span> <span data-ttu-id="736ae-106">Microsoft 팀 관리 센터에서 또는 [PowerShell](teams-powershell-overview.md)을 사용 하 여 모임 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

<span data-ttu-id="736ae-107">모임 시작, 모임 중 또는 모임 이후 사용자의 모임 환경에 영향을 주는 다음과 같은 방법으로 정책을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-107">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="736ae-108">구현 형식</span><span class="sxs-lookup"><span data-stu-id="736ae-108">Implementation type</span></span>  |<span data-ttu-id="736ae-109">설명</span><span class="sxs-lookup"><span data-stu-id="736ae-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="736ae-110">이끌이 별</span><span class="sxs-lookup"><span data-stu-id="736ae-110">Per-organizer</span></span>    |<span data-ttu-id="736ae-111">이끌이 별 정책을 구현 하는 경우 모든 모임 참가자는 해당 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-111">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="736ae-112">예를 들어 사용자가 **자동으로** 허용 이끌이 정책 이며 사용자가 모임에 직접 참가 하는지 여부를 제어 하 고 정책에 할당 된 사용자가 예약한 모임에 대해 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-112">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="736ae-113">사용자별</span><span class="sxs-lookup"><span data-stu-id="736ae-113">Per-user</span></span>    |<span data-ttu-id="736ae-114">사용자별 정책을 구현할 때, 이끌이 및/또는 모임 참가자에 대 한 특정 기능을 제한 하는 사용자별 정책만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-114">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="736ae-115">예를 들어 **채널에서 모임** 시작을 허용 하는 것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-115">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="736ae-116">이끌이와 사용자 단위</span><span class="sxs-lookup"><span data-stu-id="736ae-116">Per-organizer and per-user</span></span>     |<span data-ttu-id="736ae-117">이끌이 및 사용자별 정책 조합을 구현 하는 경우 특정 기능은 해당 정책 및 이끌이의 정책에 따라 모임 참가자에 대해 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-117">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="736ae-118">예를 들어 **클라우드 기록은 허용** -이끌이 및 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-118">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="736ae-119">이 설정을 사용 하 여 모임 이끌이 및 참가자가 녹음/녹화를 시작 하 고 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-119">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="736ae-120">기본적으로 Global (조직 전체 기본값) 이라는 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-120">By default, a policy named Global (Org-wide default) is created.</span></span> <span data-ttu-id="736ae-121">조직의 모든 사용자는 기본적으로 전역 모임 정책에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-121">All users in your organization are assigned the Global meeting policy by default.</span></span> <span data-ttu-id="736ae-122">이를 변경 하거나 하나 이상의 사용자 지정 정책을 만들어 사용자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-122">You can either make changes to it or create one or more custom policies and assign users to them.</span></span> <span data-ttu-id="736ae-123">사용자 지정 정책을 만들고 할당 하지 않으면 사용자가 글로벌 정책을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-123">Users will get the Global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="736ae-124">사용자 지정 정책을 만들 때 사용자가 특정 기능을 사용할 수 있도록 허용 하거나 금지할 수 있으며 설정을 적용할 사용자 하나 이상에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-124">When you create a custom policy, you can allow or prevent certain features from being available to your users, and then assign it to one or more users who will have the settings applied to them.</span></span>

> [!NOTE]
> <span data-ttu-id="736ae-125">모임 세부 정보 단추는 사용자가 음성 회의 라이선스를 사용 하도록 설정 했거나 사용자가 오디오 회의를 허용 하는 경우 모임 세부 정보를 사용할 수 없는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-125">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="change-or-create-a-meeting-policy"></a><span data-ttu-id="736ae-126">모임 정책 변경 또는 만들기</span><span class="sxs-lookup"><span data-stu-id="736ae-126">Change or create a meeting policy</span></span>

<span data-ttu-id="736ae-127">모임 정책을 변경하거나 만들려면 Microsoft Teams 관리 센터 > **모임** > **모임 정책**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-127">To change or create a meeting policy, go to the Microsoft Teams admin center > **Meetings** > **Meeting policies**.</span></span> <span data-ttu-id="736ae-128">목록에서 정책을 선택하거나 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-128">Select a policy from the list or select **Add**.</span></span> <span data-ttu-id="736ae-129">새 정책을 만들려면 이름과 설명을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-129">If you're creating a new policy, add a name and description.</span></span> <span data-ttu-id="736ae-130">이름은 특수 문자가 포함될 수 없으며 64자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-130">The name can't contain special characters or be longer than 64 characters.</span></span> <span data-ttu-id="736ae-131">설정을 선택 하 고 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-131">Choose your settings, and then select **Save**.</span></span>

<span data-ttu-id="736ae-132">예를 들어, 사용자 수가 많은데 모임에 필요한 대역폭의 양을 제한하려고 한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-132">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="736ae-133">"제한된 대역폭"이라는 새 사용자 지정 정책을 만들고 다음 설정을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-133">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="736ae-134">**오디오 및 비디오**에서:</span><span class="sxs-lookup"><span data-stu-id="736ae-134">Under **Audio & video**:</span></span>
- <span data-ttu-id="736ae-135">클라우드 녹음/녹화 허용을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-135">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="736ae-136">IP 비디오 허용을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-136">Turn off Allow IP video.</span></span>

<span data-ttu-id="736ae-137">**콘텐츠 공유**에서:</span><span class="sxs-lookup"><span data-stu-id="736ae-137">Under **Content sharing**:</span></span>
- <span data-ttu-id="736ae-138">화면 공유 모드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-138">Disable screen sharing mode.</span></span>
- <span data-ttu-id="736ae-139">화이트보드 허용을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-139">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="736ae-140">공유 노트 허용을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-140">Turn off Allow shared notes.</span></span>

<span data-ttu-id="736ae-141">그 다음 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-141">Then assign the policy to the users.</span></span>

> [!NOTE]
> <span data-ttu-id="736ae-142">사용자는 한 번에 하나의 모임 정책만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-142">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="736ae-143">사용자에게 모임 정책 할당</span><span class="sxs-lookup"><span data-stu-id="736ae-143">Assign a meeting policy to users</span></span>

1. <span data-ttu-id="736ae-144">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="736ae-145">사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-145">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="736ae-146">**모임 정책**에서 할당하려는 정책을 선택한 후 **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-146">Under **Meeting policy**, select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="736ae-147">한 번에 여러 사용자에게 정책을 할당하려면 [Teams 사용자 설정을 일괄 편집](edit-user-settings-in-bulk.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="736ae-147">To assign a policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="736ae-148">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-148">Or, you can also do the following:</span></span>

1. <span data-ttu-id="736ae-149">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **모임**  >  **모임 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-149">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="736ae-150">정책 이름의 왼쪽을 클릭하여 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-150">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="736ae-151">**사용자 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-151">Select **Manage users**.</span></span>
4. <span data-ttu-id="736ae-152">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가**를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="736ae-152">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="736ae-153">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-153">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="736ae-154">사용자 추가를 마쳤으면 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-154">After you finish adding users, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="736ae-155">사용자가 할당 된 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-155">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="736ae-156">먼저 영향을 받는 모든 사용자에 게 다른 정책을 할당 한 다음 원래 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-156">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="736ae-157">모임 정책 설정</span><span class="sxs-lookup"><span data-stu-id="736ae-157">Meeting policy settings</span></span>

<span data-ttu-id="736ae-158">**모임 정책** 페이지에서 기존 정책을 선택 하거나 **추가** 를 선택 하 여 새 정책을 추가 하면 다음에 대 한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-158">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="736ae-159">일반</span><span class="sxs-lookup"><span data-stu-id="736ae-159">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="736ae-160">오디오 & 비디오</span><span class="sxs-lookup"><span data-stu-id="736ae-160">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="736ae-161">콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="736ae-161">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="736ae-162">참가자가 게스트를 &</span><span class="sxs-lookup"><span data-stu-id="736ae-162">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end 

<span data-ttu-id="736ae-163"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="736ae-163"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="736ae-164">모임 정책 설정-일반</span><span class="sxs-lookup"><span data-stu-id="736ae-164">Meeting policy settings - General</span></span>

- [<span data-ttu-id="736ae-165">채널에서 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-165">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="736ae-166">Outlook 추가 기능 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-166">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="736ae-167">채널 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-167">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="736ae-168">개인 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-168">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="736ae-169">비공개 모임에서 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-169">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="736ae-170">채널에서 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-170">Allow Meet now in channels</span></span>

<span data-ttu-id="736ae-171">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-171">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="736ae-172">이 설정은 사용자가 팀 채널에서 임시 모임을 시작할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-172">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="736ae-173">이 기능을 설정 하면 사용자가 팀 채널에서 메시지를 게시할 때 작성 **상자 아래에 있는 모임 시작** 을 클릭 하 여 채널에서 특별 모임을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-173">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span> <span data-ttu-id="736ae-174">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-174">The default value is True.</span></span>

![메시지 아래에 모임 시작 아이콘을 표시 하는 스크린샷](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="736ae-176">Outlook 추가 기능 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-176">Allow the Outlook add-in</span></span>

<span data-ttu-id="736ae-177">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-177">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="736ae-178">이 설정은 Outlook (Windows, Mac, 웹, 모바일)에서 팀 모임을 예약할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-178">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![새 모임 예약 기능을 보여 주는 스크린샷](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="736ae-180">이 기능을 해제 하면 사용자가 Outlook에서 새 모임을 만들 때 팀 회의를 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-180">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="736ae-181">예를 들어 Windows의 Outlook에서는 **새 팀 모임** 옵션이 리본 메뉴에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-181">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="736ae-182">채널 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-182">Allow channel meeting scheduling</span></span>

<span data-ttu-id="736ae-183">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-183">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="736ae-184">이 설정은 사용자가 팀 채널에서 모임을 예약할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-184">This setting controls whether users can schedule a meeting in a Teams channel.</span></span>  <span data-ttu-id="736ae-185">이 기능을 해제 하면 사용자가 팀 채널에서 모임을 시작할 때 **모임 예약** 옵션을 사용할 수 없으며, 팀의 사용자에 대해 **채널 추가** 옵션이 비활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-185">If you turn this off, the **Schedule a meeting** option won't be available to the user when they start a meeting in a Teams channel and the **Add channel** option is disabled for users in Teams.</span></span> <span data-ttu-id="736ae-186">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-186">The default value is True.</span></span>

![팀의 모임 예약 옵션을 보여 주는 스크린샷](media/meeting-policies-schedule-a-meeting.png)

![모임에 적용할 채널 선택 옵션을 보여 주는 스크린샷](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="736ae-189">개인 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-189">Allow scheduling private meetings</span></span>

<span data-ttu-id="736ae-190">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-190">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="736ae-191">이 설정은 사용자가 팀에서 비공개 모임을 예약할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-191">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="736ae-192">모임이 팀의 채널에 게시 되지 않은 경우 비공개 모임입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-192">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="736ae-193">**개인 모임 예약 허용** 을 해제 하 고 **채널 모임 예약을 허용**하는 경우 팀의 사용자는 **필수 참석자 추가** 및 **채널 추가** 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-193">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="736ae-194">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-194">The default value is True.</span></span>

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="736ae-195">비공개 모임에서 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-195">Allow Meet now in private meetings</span></span>

<span data-ttu-id="736ae-196">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-196">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="736ae-197">이 설정은 사용자가 임시 비공개 모임을 시작할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-197">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="736ae-198">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-198">The default value is True.</span></span>

<span data-ttu-id="736ae-199"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="736ae-199"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="736ae-200">모임 정책 설정-오디오 & 비디오</span><span class="sxs-lookup"><span data-stu-id="736ae-200">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="736ae-201">내용 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-201">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="736ae-202">클라우드 기록 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-202">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="736ae-203">IP 비디오 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-203">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="736ae-204">미디어 비트 전송률 (Kbs)</span><span class="sxs-lookup"><span data-stu-id="736ae-204">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="736ae-205">내용 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-205">Allow transcription</span></span>

<span data-ttu-id="736ae-206">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-206">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="736ae-207">이 설정은 모임 녹음/녹화를 재생 하는 동안 캡션과 기록 기능을 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-207">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="736ae-208">이 기능을 해제 하면 모임 녹음/녹화를 재생 하는 동안 **검색** 및 **참조** 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-208">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="736ae-209">녹음/녹화를 시작한 사람에 게는 녹음/녹화가 포함 되도록이 설정이 켜져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-209">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span> 

<span data-ttu-id="736ae-210">기록 된 모임에 대 한 정보는 현재 팀의 언어를 영어로 설정한 경우와 모임에서 영어를 사용 하 고 있는 사용자만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-210">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![모임의 기록 옵션을 보여 주는 스크린샷](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="736ae-212">클라우드 기록 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-212">Allow cloud recording</span></span>

<span data-ttu-id="736ae-213">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-213">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="736ae-214">이 설정은 사용자의 모임을 녹화할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-214">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="736ae-215">참가자에 대해 정책 설정이 설정 된 경우와 다른 모임 참가자가 같은 조직의 인증 된 사용자 인 경우 기록을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-215">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="736ae-216">페더레이션 및 익명 사용자 등 조직 외부의 사용자가 녹음/녹화를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-216">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="736ae-217">게스트 사용자는 녹음/녹화를 시작 하거나 중지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-217">Guest users can't start or stop the recording.</span></span> 

![기록 옵션을 보여 주는 스크린샷](media/meeting-policies-recording.png)

<span data-ttu-id="736ae-219">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-219">Let's look at the following example.</span></span>

|<span data-ttu-id="736ae-220">사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-220">User</span></span> |<span data-ttu-id="736ae-221">모임 정책</span><span class="sxs-lookup"><span data-stu-id="736ae-221">Meeting policy</span></span>  |<span data-ttu-id="736ae-222">클라우드 기록 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-222">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="736ae-223">Daniela</span><span class="sxs-lookup"><span data-stu-id="736ae-223">Daniela</span></span> | <span data-ttu-id="736ae-224">전역</span><span class="sxs-lookup"><span data-stu-id="736ae-224">Global</span></span>   | <span data-ttu-id="736ae-225">해제</span><span class="sxs-lookup"><span data-stu-id="736ae-225">False</span></span> |
|<span data-ttu-id="736ae-226">Amanda</span><span class="sxs-lookup"><span data-stu-id="736ae-226">Amanda</span></span> | <span data-ttu-id="736ae-227">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="736ae-227">Location1MeetingPolicy</span></span> | <span data-ttu-id="736ae-228">False</span><span class="sxs-lookup"><span data-stu-id="736ae-228">True</span></span>|
|<span data-ttu-id="736ae-229">John (외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="736ae-229">John (external user)</span></span> | <span data-ttu-id="736ae-230">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="736ae-230">Not applicable</span></span> | <span data-ttu-id="736ae-231">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="736ae-231">Not applicable</span></span>|

<span data-ttu-id="736ae-232">Daniela에서 구성한 모임은 기록 하 고 Amanda 수 있으며, 정책 설정을 사용 하도록 설정한 경우 Daniela로 구성 된 모임을 녹화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-232">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="736ae-233">Amanda에서 구성한 모임은 녹화할 수 있지만, Daniela는 정책 설정을 사용 하지 않도록 설정 하 고 외부 사용자 인 John은 Amanda으로 구성 된 모임을 기록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-233">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="736ae-234">클라우드 모임 기록에 대해 자세히 알아보려면 [팀 클라우드 모임 기록을](cloud-recording.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="736ae-234">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="736ae-235">IP 비디오 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-235">Allow IP video</span></span>

<span data-ttu-id="736ae-236">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-236">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="736ae-237">비디오는 모임에 대 한 주요 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-237">Video is a key component to meetings.</span></span> <span data-ttu-id="736ae-238">일부 조직에서는 관리자가 어떤 사용자의 모임이 비디오를 보유 하 고 있는지 더 자세히 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-238">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="736ae-239">이 설정은 사용자가 호스트 하는 모임 및 사용자가 시작한 1:1 통화 및 그룹 통화에서 비디오를 켤 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-239">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="736ae-240">이 정책을 사용 하도록 설정한 사용자가 구성한 모임에는 모임 참가자가 정책을 사용 하도록 설정한 경우 모임 참가자가 모임에서 비디오 공유를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-240">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="736ae-241">배정 된 정책이 없는 모임 참가자 (예: 익명 및 페더레이션 참가자)는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-241">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![오디오 및 비디오 설정을 사용 하 여 모임을 보여 주는 스크린샷](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="736ae-243">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-243">Let's look at the following example.</span></span>

|<span data-ttu-id="736ae-244">사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-244">User</span></span> |<span data-ttu-id="736ae-245">모임 정책</span><span class="sxs-lookup"><span data-stu-id="736ae-245">Meeting policy</span></span>  |<span data-ttu-id="736ae-246">IP 영상 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-246">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="736ae-247">Daniela</span><span class="sxs-lookup"><span data-stu-id="736ae-247">Daniela</span></span>   | <span data-ttu-id="736ae-248">전역</span><span class="sxs-lookup"><span data-stu-id="736ae-248">Global</span></span>   | <span data-ttu-id="736ae-249">False</span><span class="sxs-lookup"><span data-stu-id="736ae-249">True</span></span>        |
|<span data-ttu-id="736ae-250">Amanda</span><span class="sxs-lookup"><span data-stu-id="736ae-250">Amanda</span></span>    | <span data-ttu-id="736ae-251">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="736ae-251">Location1MeetingPolicy</span></span>        | <span data-ttu-id="736ae-252">해제</span><span class="sxs-lookup"><span data-stu-id="736ae-252">False</span></span>      |

<span data-ttu-id="736ae-253">Daniela에서 호스팅하는 모임은 영상 통화를 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-253">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="736ae-254">Daniela 모임에 참가 하 고 비디오를 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-254">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="736ae-255">Amanda의 정책이 비디오를 허용 하지 않도록 설정 되어 있기 때문에 Daniela 모임에서 비디오를 켤 수 없습니다 Amanda.</span><span class="sxs-lookup"><span data-stu-id="736ae-255">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="736ae-256">Amanda는 모임의 다른 참가자가 공유 하는 비디오를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-256">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="736ae-257">Amanda에서 호스팅하는 모임에서 할당 된 비디오 정책에 관계 없이 비디오를 켤 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-257">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="736ae-258">이는 Daniela에서 Amanda의 모임에서 비디오를 켤 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-258">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="736ae-259">Daniela에서 비디오를 사용 하 여 Amanda를 호출 하는 경우 Amanda는 오디오 만으로 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-259">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="736ae-260">통화가 연결 되 면 Amanda에서 Daniela의 비디오를 볼 수 있지만 영상 통화는 켜지 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-260">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="736ae-261">Amanda에서 Daniela를 호출 하는 경우 Daniela는 비디오 및 오디오로 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-261">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="736ae-262">통화가 연결 되 면 필요에 따라 Daniela에서 비디오를 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-262">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="736ae-263">미디어 비트 전송률 (Kbs)</span><span class="sxs-lookup"><span data-stu-id="736ae-263">Media bit rate (Kbs)</span></span>

<span data-ttu-id="736ae-264">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-264">This is a per-user policy.</span></span> <span data-ttu-id="736ae-265">이 설정에 따라 사용자에 대 한 통화 및 모임에서 오디오, 비디오 및 비디오 기반 앱 공유 전송의 미디어 비트 전송률이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-265">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="736ae-266">통화 또는 모임에서 사용자의 업링크 및 다운 링크 미디어 트래버스 둘 다에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-266">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="736ae-267">이 설정을 사용 하면 조직의 대역폭을 관리 하는 방법을 세부적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-267">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="736ae-268">사용자에 게 필요한 모임 시나리오에 따라 좋은 품질 환경을 위해 적절 한 대역폭을 확보 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-268">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="736ae-269">최소값은 30kbps이 고 최대값은 모임 시나리오에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-269">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="736ae-270">팀에서 좋은 음질의 모임, 통화, 라이브 이벤트에 권장 되는 최소 대역폭에 대해 자세히 알아보려면 [대역폭 요구 사항을](prepare-network.md#bandwidth-requirements)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="736ae-270">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="736ae-271">모임에 대 한 대역폭이 충분 하지 않은 경우 참가자는 네트워크 품질이 좋지 않다는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-271">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="736ae-272">CEO 보드 모임 및 팀 라이브 이벤트와 같이 고품질의 비디오 환경을 필요로 하는 모임의 경우 대역폭을 10mbps로 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-272">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="736ae-273">최대 환경이 설정 된 경우에도 시나리오에 따라 특정 네트워크 조건이 감지 되는 경우 팀 미디어 스택이 낮은 대역폭 조건에 적응 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-273">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span> 

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="736ae-274">모임 정책 설정-콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="736ae-274">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="736ae-275">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="736ae-275">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="736ae-276">참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-276">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="736ae-277">외부 참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-277">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="736ae-278">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-278">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="736ae-279">화이트 보드 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-279">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="736ae-280">공유 메모 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-280">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="736ae-281">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="736ae-281">Screen sharing mode</span></span>

<span data-ttu-id="736ae-282">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-282">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="736ae-283">이 설정은 사용자의 모임에서 데스크톱 및/또는 창 공유를 허용할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-283">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="736ae-284">배정 된 정책이 없는 모임 참가자 (예: 익명, 게스트, B2B, 페더레이션 참가자)는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-284">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="736ae-285">값 설정</span><span class="sxs-lookup"><span data-stu-id="736ae-285">Setting value</span></span> |<span data-ttu-id="736ae-286">결과가</span><span class="sxs-lookup"><span data-stu-id="736ae-286">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="736ae-287">**전체 화면**</span><span class="sxs-lookup"><span data-stu-id="736ae-287">**Entire screen**</span></span>    | <span data-ttu-id="736ae-288">모임에서 전체 데스크톱 공유 및 응용 프로그램 공유를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-288">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="736ae-289">**단일 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="736ae-289">**Single application**</span></span>   | <span data-ttu-id="736ae-290">모임에서 응용 프로그램 공유가 허용 됨</span><span class="sxs-lookup"><span data-stu-id="736ae-290">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="736ae-291">**비활성화**</span><span class="sxs-lookup"><span data-stu-id="736ae-291">**Disabled**</span></span>     |<span data-ttu-id="736ae-292">모임에서 화면 공유 및 응용 프로그램 공유 기능을 해제 했습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-292">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="736ae-293">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-293">Let's look at the following example.</span></span>

|<span data-ttu-id="736ae-294">사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-294">User</span></span> |<span data-ttu-id="736ae-295">모임 정책</span><span class="sxs-lookup"><span data-stu-id="736ae-295">Meeting policy</span></span> |<span data-ttu-id="736ae-296">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="736ae-296">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="736ae-297">Daniela</span><span class="sxs-lookup"><span data-stu-id="736ae-297">Daniela</span></span>  | <span data-ttu-id="736ae-298">전역</span><span class="sxs-lookup"><span data-stu-id="736ae-298">Global</span></span>   | <span data-ttu-id="736ae-299">전체 화면</span><span class="sxs-lookup"><span data-stu-id="736ae-299">Entire screen</span></span> |
|<span data-ttu-id="736ae-300">Amanda</span><span class="sxs-lookup"><span data-stu-id="736ae-300">Amanda</span></span>   | <span data-ttu-id="736ae-301">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="736ae-301">Location1MeetingPolicy</span></span>  | <span data-ttu-id="736ae-302">비활성화</span><span class="sxs-lookup"><span data-stu-id="736ae-302">Disabled</span></span> |

<span data-ttu-id="736ae-303">Daniela에서 호스팅하는 모임은 모임 참가자가 전체 화면 또는 특정 응용 프로그램을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-303">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="736ae-304">Amanda 참가 Daniela의 모임이 Amanda, 화면을 공유할 수 없거나, 정책 설정에 따라 특정 응용 프로그램을 사용 하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-304">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="736ae-305">Amanda에서 호스트 하는 모임에서는 자신에 게 할당 된 화면 공유 모드 정책에 관계 없이 화면 또는 단일 응용 프로그램을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-305">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="736ae-306">즉, Daniela는 Amanda 모임의 화면 또는 단일 응용 프로그램을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-306">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="736ae-307">현재 사용자는 Google Chrome을 사용 하는 경우 팀 모임에서 비디오를 재생 하거나 화면을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-307">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="736ae-308">참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-308">Allow a participant to give or request control</span></span>

<span data-ttu-id="736ae-309">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-309">This is a per-user policy.</span></span> <span data-ttu-id="736ae-310">이 설정은 사용자가 공유 데스크톱 또는 창을 다른 모임 참가자에 게 제어권을 부여할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-310">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="736ae-311">컨트롤을 제공 하려면 화면 위쪽을 마우스로 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-311">To give control, hover over the top of the screen.</span></span> 

<span data-ttu-id="736ae-312">사용자에 대해이 설정이 설정 된 경우 **제어권 제공** 옵션이 공유 세션의 위쪽 표시줄에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-312">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span> 

![제어권 제공 옵션을 보여 주는 스크린샷](media/meeting-policies-give-control.png)

<span data-ttu-id="736ae-314">사용자에 대해 설정이 꺼져 있으면 **제어권 제공** 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-314">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![제어권 부여 옵션을 사용할 수 없음을 보여 주는 스크린샷](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="736ae-316">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-316">Let's look at the following example.</span></span>

|<span data-ttu-id="736ae-317">사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-317">User</span></span> |<span data-ttu-id="736ae-318">모임 정책</span><span class="sxs-lookup"><span data-stu-id="736ae-318">Meeting policy</span></span>  |<span data-ttu-id="736ae-319">참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-319">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="736ae-320">Daniela</span><span class="sxs-lookup"><span data-stu-id="736ae-320">Daniela</span></span>   | <span data-ttu-id="736ae-321">전역</span><span class="sxs-lookup"><span data-stu-id="736ae-321">Global</span></span>   | <span data-ttu-id="736ae-322">False</span><span class="sxs-lookup"><span data-stu-id="736ae-322">True</span></span>       |
|<span data-ttu-id="736ae-323">Babek</span><span class="sxs-lookup"><span data-stu-id="736ae-323">Babek</span></span>    | <span data-ttu-id="736ae-324">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="736ae-324">Location1MeetingPolicy</span></span>        | <span data-ttu-id="736ae-325">해제</span><span class="sxs-lookup"><span data-stu-id="736ae-325">False</span></span>   |

<span data-ttu-id="736ae-326">Daniela는 다른 참가자에 게 제어권을 부여할 수 없기 때문에 Babek에서 구성한 모임의 다른 참가자에 게 공유 데스크톱 또는 창을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-326">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="736ae-327">PowerShell을 사용 하 여 제어권을 제공 하거나 제어권 요청을 받을 수 있는 사람을 제어 하려면 AllowParticipantGiveRequestControl cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-327">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="736ae-328">공유 중 공유 콘텐츠를 관리 하 고 제어 하려면 두 파티 모두 팀 데스크톱 클라이언트를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-328">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="736ae-329">컨트롤은 어느 쪽이든 브라우저에서 Teams를 실행 중인 경우 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-329">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="736ae-330">이것은 해결하려고 하는 기술적 제한 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-330">This is due to a technical limitation that we're planning to fix.</span></span> 

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="736ae-331">외부 참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-331">Allow an external participant to give or request control</span></span>

<span data-ttu-id="736ae-332">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-332">This is a per-user policy.</span></span> <span data-ttu-id="736ae-333">이 설정은 모임의 외부 참가자가 모임의 다른 참가자에 게 공유 데스크톱 또는 창을 제어할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-333">This setting controls whether external participants in a meeting can give control of their shared desktop or window to other participants in the meeting.</span></span> <span data-ttu-id="736ae-334">팀 회의의 외부 참가자는 다음과 같이 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-334">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="736ae-335">익명 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-335">Anonymous user</span></span>
- <span data-ttu-id="736ae-336">게스트 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-336">Guest users</span></span>  
- <span data-ttu-id="736ae-337">B2B 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-337">B2B user</span></span>
- <span data-ttu-id="736ae-338">페더레이션 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-338">Federated user</span></span>  

<span data-ttu-id="736ae-339">공유 된 사용자가 외부 참가자가 조직에서 **제어권을 부여 하거나 요청할 수 있도록 허용을** 제어 하도록 설정 되어 있는 동안 페더레이션 사용자가 해당 사용자에 게 제어권을 부여할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="736ae-339">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="736ae-340">PowerShell을 사용 하 여 외부 참가자가 제어권을 제공 하거나 제어권 요청을 수락할 수 있는지 여부를 제어 하려면 AllowExternalParticipantGiveRequestControl cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-340">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="736ae-341">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-341">Allow PowerPoint sharing</span></span>

<span data-ttu-id="736ae-342">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-342">This is a per-user policy.</span></span> <span data-ttu-id="736ae-343">이 설정은 사용자가 모임에서 PowerPoint 슬라이드 데크를 공유할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-343">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="736ae-344">익명, 게스트, 페더레이션 사용자를 비롯 한 외부 사용자가 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-344">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="736ae-345">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-345">Let's look at the following example.</span></span>

|<span data-ttu-id="736ae-346">사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-346">User</span></span> |<span data-ttu-id="736ae-347">모임 정책</span><span class="sxs-lookup"><span data-stu-id="736ae-347">Meeting policy</span></span>  |<span data-ttu-id="736ae-348">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-348">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="736ae-349">Daniela</span><span class="sxs-lookup"><span data-stu-id="736ae-349">Daniela</span></span>   | <span data-ttu-id="736ae-350">전역</span><span class="sxs-lookup"><span data-stu-id="736ae-350">Global</span></span>   | <span data-ttu-id="736ae-351">False</span><span class="sxs-lookup"><span data-stu-id="736ae-351">True</span></span>       |
|<span data-ttu-id="736ae-352">Amanda</span><span class="sxs-lookup"><span data-stu-id="736ae-352">Amanda</span></span>   | <span data-ttu-id="736ae-353">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="736ae-353">Location1MeetingPolicy</span></span>        | <span data-ttu-id="736ae-354">해제</span><span class="sxs-lookup"><span data-stu-id="736ae-354">False</span></span>   |

<span data-ttu-id="736ae-355">Amanda 모임 이끌이 인 경우에도 모임에서 PowerPoint 슬라이드 데크를 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-355">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="736ae-356">Daniela는 모임이 Amanda으로 구성 된 경우에도 PowerPoint 슬라이드 데크를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-356">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="736ae-357">Amanda는 PowerPoint 슬라이드 데크를 공유할 수는 없지만 모임에서 다른 사용자가 공유한 PowerPoint 슬라이드 데크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-357">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="736ae-358">화이트 보드 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-358">Allow whiteboard</span></span>

<span data-ttu-id="736ae-359">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-359">This is a per-user policy.</span></span> <span data-ttu-id="736ae-360">이 설정은 사용자가 모임에서 화이트 보드를 공유할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-360">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="736ae-361">익명, B2B, 페더레이션 사용자 등의 외부 사용자는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-361">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> 

<span data-ttu-id="736ae-362">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-362">Let's look at the following example.</span></span>

|<span data-ttu-id="736ae-363">사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-363">User</span></span> |<span data-ttu-id="736ae-364">모임 정책</span><span class="sxs-lookup"><span data-stu-id="736ae-364">Meeting policy</span></span>  |<span data-ttu-id="736ae-365">화이트 보드 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-365">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="736ae-366">Daniela</span><span class="sxs-lookup"><span data-stu-id="736ae-366">Daniela</span></span>   | <span data-ttu-id="736ae-367">전역</span><span class="sxs-lookup"><span data-stu-id="736ae-367">Global</span></span>   | <span data-ttu-id="736ae-368">False</span><span class="sxs-lookup"><span data-stu-id="736ae-368">True</span></span>       |
|<span data-ttu-id="736ae-369">Amanda</span><span class="sxs-lookup"><span data-stu-id="736ae-369">Amanda</span></span>   | <span data-ttu-id="736ae-370">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="736ae-370">Location1MeetingPolicy</span></span>        | <span data-ttu-id="736ae-371">해제</span><span class="sxs-lookup"><span data-stu-id="736ae-371">False</span></span>   |

<span data-ttu-id="736ae-372">Amanda 모임 이끌이 인 경우에도 모임에서 화이트 보드를 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-372">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="736ae-373">Daniela는 모임이 Amanda으로 구성 된 경우에도 화이트 보드를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-373">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="736ae-374">공유 메모 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-374">Allow shared notes</span></span>

<span data-ttu-id="736ae-375">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-375">This is a per-user policy.</span></span> <span data-ttu-id="736ae-376">이 설정은 사용자가 모임에서 노트를 만들고 공유할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-376">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="736ae-377">익명, B2B, 페더레이션 사용자 등의 외부 사용자는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-377">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="736ae-378">**모임 메모** 탭은 현재 20 명 미만의 참가자가 있는 모임 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-378">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="736ae-379">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-379">Let's look at the following example.</span></span>

|<span data-ttu-id="736ae-380">사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-380">User</span></span> |<span data-ttu-id="736ae-381">모임 정책</span><span class="sxs-lookup"><span data-stu-id="736ae-381">Meeting policy</span></span>  |<span data-ttu-id="736ae-382">공유 메모 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-382">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="736ae-383">Daniela</span><span class="sxs-lookup"><span data-stu-id="736ae-383">Daniela</span></span>   | <span data-ttu-id="736ae-384">전역</span><span class="sxs-lookup"><span data-stu-id="736ae-384">Global</span></span>   | <span data-ttu-id="736ae-385">False</span><span class="sxs-lookup"><span data-stu-id="736ae-385">True</span></span>       |
|<span data-ttu-id="736ae-386">Amanda</span><span class="sxs-lookup"><span data-stu-id="736ae-386">Amanda</span></span>   | <span data-ttu-id="736ae-387">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="736ae-387">Location1MeetingPolicy</span></span> | <span data-ttu-id="736ae-388">해제</span><span class="sxs-lookup"><span data-stu-id="736ae-388">False</span></span> |

<span data-ttu-id="736ae-389">Daniela는 Amanda의 모임에 메모를 기록 하 고 모든 모임에서 메모를 찍을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-389">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="736ae-390">모임 정책 설정-게스트 & 참가자</span><span class="sxs-lookup"><span data-stu-id="736ae-390">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="736ae-391">이 설정은 모임에 참가 하기 전에 대기실에서 대기 하는 모임 참가자와 모임에서 허용 되는 참여 수준을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-391">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="736ae-392">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-392">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="736ae-393">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="736ae-393">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="736ae-394">전화 접속 사용자가 대기실를 우회할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-394">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="736ae-395">라이브 캡션 사용</span><span class="sxs-lookup"><span data-stu-id="736ae-395">Enable live captions </span></span>](#enable-live-captions)
- [<span data-ttu-id="736ae-396">모임에서 채팅 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-396">Allow chat in meetings </span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="736ae-397">모임에 참가 하는 옵션은 각 팀 그룹의 설정 및 연결 방법에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-397">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="736ae-398">그룹에 오디오 회의가 있고이를 사용 하 여 연결 하는 경우 [Office 365의 오디오 회의](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="736ae-398">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing in Office 365](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="736ae-399">팀 그룹에 오디오 회의가 없는 경우 [팀에서 모임 참가](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="736ae-399">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="736ae-400">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-400">Let anonymous people start a meeting</span></span>

<span data-ttu-id="736ae-401">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-401">This is a per-organizer policy.</span></span> <span data-ttu-id="736ae-402">이 설정은 B2B, 페더레이션 사용자 등의 익명 사용자가 조직에서 인증 된 사용자가 아닌 사용자의 모임에 참석할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-402">This setting controls whether anonymous people, including B2B, and federated users, can join the user's meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="736ae-403">기본값은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-403">The default value is False.</span></span>

![대기 중인 사용자에 게 메시지를 표시 하는 스크린샷](media/meeting-policies-anonymous-user-lobby.png)

<span data-ttu-id="736ae-405">인증 된 사용자가 모임에 참석 하는 경우 익명 사용자의 참가 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-405">Here's the join behavior of anonymous people when authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="736ae-406">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-406">Let anonymous people start a meeting</span></span>  |<span data-ttu-id="736ae-407">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="736ae-407">Automatically admit people</span></span> |<span data-ttu-id="736ae-408">익명 사용자의 참가 동작</span><span class="sxs-lookup"><span data-stu-id="736ae-408">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="736ae-409">False</span><span class="sxs-lookup"><span data-stu-id="736ae-409">True</span></span>    | <span data-ttu-id="736ae-410">모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-410">Everyone</span></span>      | <span data-ttu-id="736ae-411">직접 참가</span><span class="sxs-lookup"><span data-stu-id="736ae-411">Join directly</span></span>         |
|   | <span data-ttu-id="736ae-412">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-412">Everyone in your organization</span></span>       | <span data-ttu-id="736ae-413">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="736ae-413">Wait in lobby</span></span>        |
|   | <span data-ttu-id="736ae-414">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-414">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="736ae-415">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="736ae-415">Wait in lobby</span></span>         |
|<span data-ttu-id="736ae-416">해제</span><span class="sxs-lookup"><span data-stu-id="736ae-416">False</span></span>    | <span data-ttu-id="736ae-417">모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-417">Everyone</span></span>        | <span data-ttu-id="736ae-418">직접 참가</span><span class="sxs-lookup"><span data-stu-id="736ae-418">Join directly</span></span>        |
|   | <span data-ttu-id="736ae-419">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-419">Everyone in your organization</span></span>     | <span data-ttu-id="736ae-420">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="736ae-420">Wait in lobby</span></span>        |
|   | <span data-ttu-id="736ae-421">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-421">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="736ae-422">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="736ae-422">Wait in lobby</span></span>         |

<span data-ttu-id="736ae-423">다음은 인증 된 사용자가 모임에 없는 경우의 익명 사용자의 참가 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-423">Here's the join behavior of anonymous people when no authenticated users are present in the meeting.</span></span>

|<span data-ttu-id="736ae-424">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-424">Let anonymous people start a meeting</span></span> |<span data-ttu-id="736ae-425">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="736ae-425">Automatically admit people</span></span>  |<span data-ttu-id="736ae-426">익명 사용자의 참가 동작</span><span class="sxs-lookup"><span data-stu-id="736ae-426">Join behavior of anonymous people</span></span> |
|---------|---------|---------|
|<span data-ttu-id="736ae-427">False</span><span class="sxs-lookup"><span data-stu-id="736ae-427">True</span></span>    | <span data-ttu-id="736ae-428">모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-428">Everyone</span></span>      | <span data-ttu-id="736ae-429">직접 참가</span><span class="sxs-lookup"><span data-stu-id="736ae-429">Join directly</span></span>         |
|   | <span data-ttu-id="736ae-430">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-430">Everyone in your organization</span></span>       | <span data-ttu-id="736ae-431">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="736ae-431">Wait in lobby</span></span>        |
|   | <span data-ttu-id="736ae-432">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-432">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="736ae-433">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="736ae-433">Wait in lobby</span></span>         |
|<span data-ttu-id="736ae-434">해제</span><span class="sxs-lookup"><span data-stu-id="736ae-434">False</span></span>    | <span data-ttu-id="736ae-435">모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-435">Everyone</span></span>        | <span data-ttu-id="736ae-436">대기실에서 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-436">Wait in lobby.</span></span> <span data-ttu-id="736ae-437">인증 된 첫 번째 사용자가 모임에 참가 하면 사용자가 자동으로 허가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-437">Users are automatically admitted when the first authenticated user joins the meeting.</span></span>        |
|   | <span data-ttu-id="736ae-438">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-438">Everyone in your organization</span></span>     |<span data-ttu-id="736ae-439">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="736ae-439">Wait in lobby</span></span>         |
|   | <span data-ttu-id="736ae-440">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-440">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="736ae-441">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="736ae-441">Wait in lobby</span></span>         |

### <a name="automatically-admit-people"></a><span data-ttu-id="736ae-442">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="736ae-442">Automatically admit people</span></span>

<span data-ttu-id="736ae-443">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-443">This is a per-organizer policy.</span></span> <span data-ttu-id="736ae-444">이 설정은 사용자가 인증 된 사용자가 참여 하 게 될 때까지 자신이 모임에 직접 참가 하거나 대기실에서 대기할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-444">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span>

![대기실에 사용자가 있는 모임을 보여 주는 스크린샷](media/meeting-policies-lobby.png)

 <span data-ttu-id="736ae-446">모임 이끌이는 모임 초대에서 **모임 옵션** 을 클릭 하 여 자신이 예약한 각 모임에 대해이 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-446">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>
  
|<span data-ttu-id="736ae-447">값 설정</span><span class="sxs-lookup"><span data-stu-id="736ae-447">Setting value</span></span>  |<span data-ttu-id="736ae-448">조인 동작</span><span class="sxs-lookup"><span data-stu-id="736ae-448">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="736ae-449">**모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="736ae-449">**Everyone**</span></span>   |<span data-ttu-id="736ae-450">모든 모임 참가자는 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-450">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="736ae-451">여기에는 인증 된 사용자, 페더레이션 사용자, 게스트, 익명 사용자, 휴대폰으로 전화 접속 하는 사용자 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-451">This includes authenticated users, federated users, guests, anonymous users, and people who dial in by phone.</span></span>       |
|<span data-ttu-id="736ae-452">**조직 및 페더레이션된 조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="736ae-452">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="736ae-453">게스트 사용자 및 페더레이션된 조직의 사용자를 포함 하 여 조직 내에서 인증 된 사용자가 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-453">Authenticated users within the organization, including guest users and the users from federated organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="736ae-454">익명 사용자 및 전화를 통해 전화를 거는 사용자는 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-454">Anonymous users and users who dial in by phone wait in the lobby.</span></span>   |
|<span data-ttu-id="736ae-455">**조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="736ae-455">**Everyone in your organization**</span></span>    |<span data-ttu-id="736ae-456">게스트 사용자를 포함 하 여 조직 내에서 인증 된 사용자가 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-456">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="736ae-457">연결 된 사용자, 익명 사용자, 휴대폰으로 전화를 걸고 있는 사용자는 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-457">Federated users, anonymous users, and users who dial in by phone wait in the lobby.</span></span> <span data-ttu-id="736ae-458">기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-458">This is the default setting.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="736ae-459">전화 접속 사용자가 대기실를 우회할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-459">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="736ae-460">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-460">This is a per-organizer policy.</span></span> <span data-ttu-id="736ae-461">이 설정은 전화를 통해 전화를 거는 사용자가 모임에 직접 참가 하거나 **자동으로** 허용 되는 사용자 설정에 관계 없이 대기실에서 대기할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-461">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="736ae-462">기본값은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-462">The default value is False.</span></span>

<span data-ttu-id="736ae-463">휴대폰에서 전화를 거는 사용자의 참가 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-463">Here's the join behavior of people who dial in by phone.</span></span>

|<span data-ttu-id="736ae-464">전화 접속 사용자가 대기실를 우회할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-464">Allow dial-in users to bypass the lobby</span></span>  |<span data-ttu-id="736ae-465">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="736ae-465">Automatically admit people</span></span>  |<span data-ttu-id="736ae-466">전화 접속 사용자의 참가 동작</span><span class="sxs-lookup"><span data-stu-id="736ae-466">Join behavior of people who dial in</span></span> |
|---------|---------|---------|
|<span data-ttu-id="736ae-467">False</span><span class="sxs-lookup"><span data-stu-id="736ae-467">True</span></span>    | <span data-ttu-id="736ae-468">모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-468">Everyone</span></span>      | <span data-ttu-id="736ae-469">직접 참가</span><span class="sxs-lookup"><span data-stu-id="736ae-469">Join directly</span></span>         |
|   | <span data-ttu-id="736ae-470">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-470">Everyone in your organization</span></span>       | <span data-ttu-id="736ae-471">직접 참가</span><span class="sxs-lookup"><span data-stu-id="736ae-471">Join directly</span></span>        |
|   | <span data-ttu-id="736ae-472">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-472">Everyone in your organization and federated organizations</span></span>       | <span data-ttu-id="736ae-473">직접 참가</span><span class="sxs-lookup"><span data-stu-id="736ae-473">Join directly</span></span>         |
|<span data-ttu-id="736ae-474">해제</span><span class="sxs-lookup"><span data-stu-id="736ae-474">False</span></span>    | <span data-ttu-id="736ae-475">모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-475">Everyone</span></span>        | <span data-ttu-id="736ae-476">직접 참가</span><span class="sxs-lookup"><span data-stu-id="736ae-476">Join directly</span></span>        |
|   | <span data-ttu-id="736ae-477">조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-477">Everyone in your organization</span></span>     |<span data-ttu-id="736ae-478">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="736ae-478">Wait in lobby</span></span>         |
|   | <span data-ttu-id="736ae-479">조직 및 페더레이션된 조직의 모든 사용자</span><span class="sxs-lookup"><span data-stu-id="736ae-479">Everyone in your organization and federated organizations</span></span>      | <span data-ttu-id="736ae-480">대기실에서 대기</span><span class="sxs-lookup"><span data-stu-id="736ae-480">Wait in lobby</span></span>         |


### <a name="enable-live-captions"></a><span data-ttu-id="736ae-481">라이브 캡션 사용</span><span class="sxs-lookup"><span data-stu-id="736ae-481">Enable live captions</span></span>

<span data-ttu-id="736ae-482">이것은 사용자별 정책으로 모임 중에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-482">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="736ae-483">이 설정은 사용자가 참석할는 모임에서 실시간 **캡션 켜기** 옵션을 사용 하 여 live 캡션을 켜고 끌 것인지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-483">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![라이브 캡션 켜기 옵션을 보여 주는 스크린샷](media/meeting-policies-live-captions.png)

|<span data-ttu-id="736ae-485">값 설정</span><span class="sxs-lookup"><span data-stu-id="736ae-485">Setting value</span></span> |<span data-ttu-id="736ae-486">결과가</span><span class="sxs-lookup"><span data-stu-id="736ae-486">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="736ae-487">**사용 하지 않도록 설정 되어 있으며 이끌이는 무시할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="736ae-487">**Disabled but the organizer can override**</span></span>     | <span data-ttu-id="736ae-488">Live 캡션은 모임 중에 사용자에 대해 자동으로 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-488">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="736ae-489">사용자는 오버플로 (**...**) 메뉴에서 **라이브 캡션 켜기** 옵션을 표시 하 여 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-489">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="736ae-490">기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-490">This is the default setting.</span></span> |
|<span data-ttu-id="736ae-491">**비활성화**</span><span class="sxs-lookup"><span data-stu-id="736ae-491">**Disabled**</span></span>     | <span data-ttu-id="736ae-492">모임 중에는 사용자가 실시간 캡션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-492">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="736ae-493">사용자는이 옵션을 켤 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-493">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="736ae-494"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="736ae-494"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="736ae-495">모임에서 채팅 허용</span><span class="sxs-lookup"><span data-stu-id="736ae-495">Allow chat in meetings</span></span>

<span data-ttu-id="736ae-496">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-496">This is a per-organizer policy.</span></span> <span data-ttu-id="736ae-497">이 설정은 사용자의 모임에서 모임 채팅을 허용할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-497">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="736ae-498"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="736ae-498"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="meeting-policy-settings---meeting-attendance-report"></a><span data-ttu-id="736ae-499">모임 정책 설정-모임 참석 보고서</span><span class="sxs-lookup"><span data-stu-id="736ae-499">Meeting policy settings - Meeting attendance report</span></span>

<span data-ttu-id="736ae-500">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-500">This is a per-user policy.</span></span> <span data-ttu-id="736ae-501">이 설정은 모임 이끌이가 [모임 참석 보고서](teams-analytics-and-reports/meeting-attendance-report.md)를 다운로드할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-501">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="736ae-502">현재는 PowerShell을 사용 하 여이 정책 설정을 구성할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-502">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="736ae-503">[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용 하 여 기존 팀 모임 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-503">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="736ae-504">또는 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용 하 여 새 팀 모임 정책을 만들고 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-504">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="736ae-505">모임 이끌이가 모임 참석 보고서를 다운로드 하도록 설정 하려면 **AllowEngagementReport** 매개 변수를 **Enabled**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-505">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="736ae-506">이 설정을 사용 하면 **참가자** 창에 보고서를 다운로드 하는 옵션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-506">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="736ae-507">모임 이끌이가 보고서를 다운로드 하지 못하도록 하려면 매개 변수를 **Disabled**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-507">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="736ae-508">기본적으로이 설정은 비활성화 되어 있으며 보고서를 다운로드 하는 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="736ae-508">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="736ae-509">관련 항목</span><span class="sxs-lookup"><span data-stu-id="736ae-509">Related topics</span></span>

- [<span data-ttu-id="736ae-510">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="736ae-510">Teams PowerShell overview</span></span>](teams-powershell-overview.md)