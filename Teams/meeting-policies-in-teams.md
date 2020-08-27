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
ms.openlocfilehash: a075a432f57a6634a49e9442da0bdc215b1546d9
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255511"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="3b0e5-103">팀에서 모임 정책 관리</span><span class="sxs-lookup"><span data-stu-id="3b0e5-103">Manage meeting policies in Teams</span></span>

::: zone target="docs"
<span data-ttu-id="3b0e5-104">모임 정책은 조직에서 사용자가 예약한 모임 참가자가 사용할 수 있는 기능을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-104">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="3b0e5-105">자동으로 생성 되는 전역 (조직 차원의 기본) 정책을 사용 하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-105">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="3b0e5-106">Microsoft 팀 관리 센터에서 또는 [PowerShell](teams-powershell-overview.md)을 사용 하 여 모임 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-106">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3b0e5-107">역할을 사용 하 여 모임 발표자 및 참석자의 사용 권한을 관리 하는 방법에 대 한 자세한 내용은 [팀 모임에서 역할](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-107">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="3b0e5-108">모임 시작, 모임 중 또는 모임 이후 사용자의 모임 환경에 영향을 주는 다음과 같은 방법으로 정책을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-108">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="3b0e5-109">구현 형식</span><span class="sxs-lookup"><span data-stu-id="3b0e5-109">Implementation type</span></span>  |<span data-ttu-id="3b0e5-110">설명</span><span class="sxs-lookup"><span data-stu-id="3b0e5-110">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="3b0e5-111">이끌이 별</span><span class="sxs-lookup"><span data-stu-id="3b0e5-111">Per-organizer</span></span>    |<span data-ttu-id="3b0e5-112">이끌이 별 정책을 구현 하는 경우 모든 모임 참가자는 해당 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-112">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="3b0e5-113">예를 들어 사용자가 **자동으로** 허용 이끌이 정책 이며 사용자가 모임에 직접 참가 하는지 여부를 제어 하 고 정책에 할당 된 사용자가 예약한 모임에 대해 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-113">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="3b0e5-114">사용자별</span><span class="sxs-lookup"><span data-stu-id="3b0e5-114">Per-user</span></span>    |<span data-ttu-id="3b0e5-115">사용자별 정책을 구현할 때, 이끌이 및/또는 모임 참가자에 대 한 특정 기능을 제한 하는 사용자별 정책만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-115">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="3b0e5-116">예를 들어 **채널에서 모임** 시작을 허용 하는 것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-116">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="3b0e5-117">이끌이와 사용자 단위</span><span class="sxs-lookup"><span data-stu-id="3b0e5-117">Per-organizer and per-user</span></span>     |<span data-ttu-id="3b0e5-118">이끌이 및 사용자별 정책 조합을 구현 하는 경우 특정 기능은 해당 정책 및 이끌이의 정책에 따라 모임 참가자에 대해 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-118">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="3b0e5-119">예를 들어 **클라우드 기록은 허용** -이끌이 및 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-119">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="3b0e5-120">이 설정을 사용 하 여 모임 이끌이 및 참가자가 녹음/녹화를 시작 하 고 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-120">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="3b0e5-121">전역 정책에서 설정을 편집 하거나 하나 이상의 사용자 지정 정책을 만들어 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-121">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="3b0e5-122">사용자 지정 정책을 만들고 할당 하지 않으면 사용자가 글로벌 정책을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-122">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="3b0e5-123">모임 세부 정보 단추는 사용자가 음성 회의 라이선스를 사용 하도록 설정 했거나 사용자가 오디오 회의를 허용 하는 경우 모임 세부 정보를 사용할 수 없는 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-123">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="3b0e5-124">사용자 지정 모임 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="3b0e5-124">Create a custom meeting policy</span></span>

1. <span data-ttu-id="3b0e5-125">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **모임**  >  **모임 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-125">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="3b0e5-126">**추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-126">Click **Add**.</span></span>
3. <span data-ttu-id="3b0e5-127">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-127">Enter a name and description for the policy.</span></span> <span data-ttu-id="3b0e5-128">이름은 특수 문자가 포함될 수 없으며 64자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-128">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="3b0e5-129">원하는 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-129">Choose the settings that you want.</span></span>
5. <span data-ttu-id="3b0e5-130">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-130">Click **Save**.</span></span>

<span data-ttu-id="3b0e5-131">예를 들어, 사용자 수가 많은데 모임에 필요한 대역폭의 양을 제한하려고 한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-131">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="3b0e5-132">"제한된 대역폭"이라는 새 사용자 지정 정책을 만들고 다음 설정을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-132">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="3b0e5-133">**오디오 및 비디오**에서:</span><span class="sxs-lookup"><span data-stu-id="3b0e5-133">Under **Audio & video**:</span></span>

- <span data-ttu-id="3b0e5-134">클라우드 녹음/녹화 허용을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-134">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="3b0e5-135">IP 비디오 허용을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-135">Turn off Allow IP video.</span></span>

<span data-ttu-id="3b0e5-136">**콘텐츠 공유**에서:</span><span class="sxs-lookup"><span data-stu-id="3b0e5-136">Under **Content sharing**:</span></span>

- <span data-ttu-id="3b0e5-137">화면 공유 모드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-137">Disable screen sharing mode.</span></span>
- <span data-ttu-id="3b0e5-138">화이트보드 허용을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-138">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="3b0e5-139">공유 노트 허용을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-139">Turn off Allow shared notes.</span></span>

<span data-ttu-id="3b0e5-140">그 다음 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-140">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="3b0e5-141">모임 정책 편집</span><span class="sxs-lookup"><span data-stu-id="3b0e5-141">Edit a meeting policy</span></span>

<span data-ttu-id="3b0e5-142">만드는 모든 사용자 지정 정책에 대 한 전역 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-142">You can edit the global policy an any custom policies that you create.</span></span>

1. <span data-ttu-id="3b0e5-143">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **모임**  >  **모임 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-143">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="3b0e5-144">정책 이름 왼쪽을 클릭 하 여 정책을 선택한 다음 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-144">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="3b0e5-145">여기서 원하는 대로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-145">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="3b0e5-146">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-146">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="3b0e5-147">사용자는 한 번에 하나의 모임 정책만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-147">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="3b0e5-148">사용자에게 모임 정책 할당</span><span class="sxs-lookup"><span data-stu-id="3b0e5-148">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="3b0e5-149">사용자가 할당 된 정책은 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-149">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="3b0e5-150">먼저 영향을 받는 모든 사용자에 게 다른 정책을 할당 한 다음 원래 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-150">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="3b0e5-151">모임 정책 설정</span><span class="sxs-lookup"><span data-stu-id="3b0e5-151">Meeting policy settings</span></span>

<span data-ttu-id="3b0e5-152">**모임 정책** 페이지에서 기존 정책을 선택 하거나 **추가** 를 선택 하 여 새 정책을 추가 하면 다음에 대 한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-152">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="3b0e5-153">일반</span><span class="sxs-lookup"><span data-stu-id="3b0e5-153">General</span></span>](#meeting-policy-settings---general)
- [<span data-ttu-id="3b0e5-154">오디오 & 비디오</span><span class="sxs-lookup"><span data-stu-id="3b0e5-154">Audio & video</span></span>](#meeting-policy-settings---audio--video)
- [<span data-ttu-id="3b0e5-155">콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="3b0e5-155">Content sharing</span></span>](#meeting-policy-settings---content-sharing)
- [<span data-ttu-id="3b0e5-156">참가자가 게스트를 &</span><span class="sxs-lookup"><span data-stu-id="3b0e5-156">Participants & guests</span></span>](#meeting-policy-settings---participants--guests)

::: zone-end

<span data-ttu-id="3b0e5-157"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="3b0e5-157"><a name="bkgeneral"> </a></span></span>

## <a name="meeting-policy-settings---general"></a><span data-ttu-id="3b0e5-158">모임 정책 설정-일반</span><span class="sxs-lookup"><span data-stu-id="3b0e5-158">Meeting policy settings - General</span></span>

- [<span data-ttu-id="3b0e5-159">채널에서 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-159">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="3b0e5-160">Outlook 추가 기능 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-160">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="3b0e5-161">채널 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-161">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="3b0e5-162">개인 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-162">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="3b0e5-163">비공개 모임에서 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-163">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a><span data-ttu-id="3b0e5-164">채널에서 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-164">Allow Meet now in channels</span></span>

<span data-ttu-id="3b0e5-165">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-165">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="3b0e5-166">이 설정은 사용자가 팀 채널에서 임시 모임을 시작할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-166">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="3b0e5-167">이 기능을 설정 하면 사용자가 팀 채널에서 메시지를 게시할 때 작성 **상자 아래에 있는 모임 시작** 을 클릭 하 여 채널에서 특별 모임을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-167">If you turn this on, when a user posts a message in a Teams channel, the user can click **Meet now** under the compose box to start an ad hoc meeting in the channel.</span></span> <span data-ttu-id="3b0e5-168">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-168">The default value is True.</span></span>

![메시지 아래에 모임 시작 아이콘을 표시 하는 스크린샷](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a><span data-ttu-id="3b0e5-170">Outlook 추가 기능 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-170">Allow the Outlook add-in</span></span>

<span data-ttu-id="3b0e5-171">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-171">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="3b0e5-172">이 설정은 Outlook (Windows, Mac, 웹, 모바일)에서 팀 모임을 예약할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-172">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![새 모임 예약 기능을 보여 주는 스크린샷](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="3b0e5-174">이 기능을 해제 하면 사용자가 Outlook에서 새 모임을 만들 때 팀 회의를 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-174">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="3b0e5-175">예를 들어 Windows의 Outlook에서는 **새 팀 모임** 옵션이 리본 메뉴에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-175">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

### <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="3b0e5-176">채널 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-176">Allow channel meeting scheduling</span></span>

<span data-ttu-id="3b0e5-177">기존 AllowChannelMeetingScheduling 정책을 사용 하 여 팀 채널 일정에 만들 수 있는 이벤트 유형을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-177">Use the existing AllowChannelMeetingScheduling policy to control the types of events that can be created on the team channel calendars.</span></span> <span data-ttu-id="3b0e5-178">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-178">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="3b0e5-179">이 설정은 사용자가 팀 채널에서 모임을 예약할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-179">This setting controls whether users can schedule a meeting in a Teams channel.</span></span> <span data-ttu-id="3b0e5-180">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-180">The default value is True.</span></span>

<span data-ttu-id="3b0e5-181">이 정책을 끄면 사용자가 새 채널 모임을 만들 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-181">If this policy is OFF, users will not be able to create new channel meetings.</span></span> <span data-ttu-id="3b0e5-182">그러나 기존 채널 모임은 이벤트 구성 도우미를 통해 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-182">However, existing channel meetings can be edited by the organizer of the event.</span></span>

<span data-ttu-id="3b0e5-183">모임 예약을 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-183">Schedule a meeting will be disabled.</span></span>

![팀의 모임 예약 옵션을 보여 주는 스크린샷](media/schedule-meeting-option.png)

<span data-ttu-id="3b0e5-185">채널 선택을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-185">Channel selection is disabled.</span></span>

![모임 예약에 사용할 채널을 선택 하기 위한 일정 옵션을 보여 주는 스크린샷](media/meeting-policies-select-a-channel-to-meet-in.png)

<span data-ttu-id="3b0e5-187">채널 게시물 페이지에서 다음을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-187">In the channel posts page, the following will be disabled:</span></span>

- <span data-ttu-id="3b0e5-188">채널 회신 작성 상자에서 **모임 예약** 단추</span><span class="sxs-lookup"><span data-stu-id="3b0e5-188">**Schedule a meeting** button on the channel reply compose box.</span></span>
<span data-ttu-id="3b0e5-189">![모임 예약에 사용할 채널을 선택 하기 위한 일정 옵션을 보여 주는 스크린샷](media/schedule-meeting-disabled-in-chat2.png)</span><span class="sxs-lookup"><span data-stu-id="3b0e5-189">![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/schedule-meeting-disabled-in-chat2.png)</span></span>
- <span data-ttu-id="3b0e5-190">채널 헤더에서 **모임 예약** 단추</span><span class="sxs-lookup"><span data-stu-id="3b0e5-190">**Schedule a meeting** button on the channel header.</span></span>
<span data-ttu-id="3b0e5-191">![모임 예약에 사용할 채널을 선택 하기 위한 일정 옵션을 보여 주는 스크린샷](media/schedule-now-in-header.png)</span><span class="sxs-lookup"><span data-stu-id="3b0e5-191">![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/schedule-now-in-header.png)</span></span>

<span data-ttu-id="3b0e5-192">채널 일정에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-192">In the channel calendar:</span></span>

- <span data-ttu-id="3b0e5-193">채널 달력 머리글의 **새 이벤트 추가** 단추를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-193">**Add new event** button on channel calendar header will be disabled.</span></span>
<span data-ttu-id="3b0e5-194">![모임 예약에 사용할 채널을 선택 하기 위한 일정 옵션을 보여 주는 스크린샷](media/add-new-event-disabled.png)</span><span class="sxs-lookup"><span data-stu-id="3b0e5-194">![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/add-new-event-disabled.png)</span></span>
- <span data-ttu-id="3b0e5-195">사용자는 채널 일정에서 시간 블록을 끌어서 선택 하지 못하게 하 여 채널 모임을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-195">Users will not be able to drag and select a time block on the channel calendar to create a channel meeting.</span></span>
- <span data-ttu-id="3b0e5-196">사용자는 바로 가기 키를 사용 하 여 채널 일정에서 모임을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-196">Users cannot use Keyboard shortcuts to create a meeting on the channel calendar.</span></span>

<span data-ttu-id="3b0e5-197">관리 센터에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-197">In the Admin Center:</span></span>

<span data-ttu-id="3b0e5-198">채널 일정 앱은 권한 정책에 대 한 관리 패널의 **Microsoft apps** 섹션 아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-198">The channel calendar app will show up under the **Microsoft apps** section in the admin panel for permission policies.</span></span>

![팀 관리 콘솔의 Microsoft 앱 정책을 보여 주는 스크린샷](media/manage-microsoft-apps-policy.png)

### <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="3b0e5-200">개인 모임 예약 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-200">Allow scheduling private meetings</span></span>

<span data-ttu-id="3b0e5-201">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-201">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="3b0e5-202">이 설정은 사용자가 팀에서 비공개 모임을 예약할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-202">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="3b0e5-203">모임이 팀의 채널에 게시 되지 않은 경우 비공개 모임입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-203">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="3b0e5-204">**개인 모임 예약 허용** 을 해제 하 고 **채널 모임 예약을 허용**하는 경우 팀의 사용자는 **필수 참석자 추가** 및 **채널 추가** 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-204">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="3b0e5-205">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-205">The default value is True.</span></span>

### <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="3b0e5-206">비공개 모임에서 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-206">Allow Meet now in private meetings</span></span>

<span data-ttu-id="3b0e5-207">이것은 사용자별 정책으로, 모임이 시작 되기 전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-207">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="3b0e5-208">이 설정은 사용자가 임시 비공개 모임을 시작할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-208">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="3b0e5-209">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-209">The default value is True.</span></span>

<span data-ttu-id="3b0e5-210"><a name="bkaudioandvideo"> </a></span><span class="sxs-lookup"><span data-stu-id="3b0e5-210"><a name="bkaudioandvideo"> </a></span></span>

## <a name="meeting-policy-settings---audio--video"></a><span data-ttu-id="3b0e5-211">모임 정책 설정-오디오 & 비디오</span><span class="sxs-lookup"><span data-stu-id="3b0e5-211">Meeting policy settings - Audio & video</span></span>

- [<span data-ttu-id="3b0e5-212">내용 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-212">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="3b0e5-213">클라우드 기록 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-213">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="3b0e5-214">IP 비디오 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-214">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="3b0e5-215">미디어 비트 전송률 (Kbs)</span><span class="sxs-lookup"><span data-stu-id="3b0e5-215">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)

### <a name="allow-transcription"></a><span data-ttu-id="3b0e5-216">내용 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-216">Allow transcription</span></span>

<span data-ttu-id="3b0e5-217">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-217">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="3b0e5-218">이 설정은 모임 녹음/녹화를 재생 하는 동안 캡션과 기록 기능을 사용할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-218">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="3b0e5-219">이 기능을 해제 하면 모임 녹음/녹화를 재생 하는 동안 **검색** 및 **참조** 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-219">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="3b0e5-220">녹음/녹화를 시작한 사람에 게는 녹음/녹화가 포함 되도록이 설정이 켜져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-220">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span>

<span data-ttu-id="3b0e5-221">기록 된 모임에 대 한 정보는 현재 팀의 언어를 영어로 설정한 경우와 모임에서 영어를 사용 하 고 있는 사용자만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-221">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

![모임의 기록 옵션을 보여 주는 스크린샷](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a><span data-ttu-id="3b0e5-223">클라우드 기록 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-223">Allow cloud recording</span></span>

<span data-ttu-id="3b0e5-224">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-224">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="3b0e5-225">이 설정은 사용자의 모임을 녹화할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-225">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="3b0e5-226">참가자에 대해 정책 설정이 설정 된 경우와 다른 모임 참가자가 같은 조직의 인증 된 사용자 인 경우 기록을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-226">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="3b0e5-227">페더레이션 및 익명 사용자 등 조직 외부의 사용자가 녹음/녹화를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-227">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="3b0e5-228">게스트 사용자는 녹음/녹화를 시작 하거나 중지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-228">Guest users can't start or stop the recording.</span></span>

![기록 옵션을 보여 주는 스크린샷](media/meeting-policies-recording.png)

<span data-ttu-id="3b0e5-230">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-230">Let's look at the following example.</span></span>

|<span data-ttu-id="3b0e5-231">사용자</span><span class="sxs-lookup"><span data-stu-id="3b0e5-231">User</span></span> |<span data-ttu-id="3b0e5-232">모임 정책</span><span class="sxs-lookup"><span data-stu-id="3b0e5-232">Meeting policy</span></span>  |<span data-ttu-id="3b0e5-233">클라우드 기록 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-233">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3b0e5-234">Daniela</span><span class="sxs-lookup"><span data-stu-id="3b0e5-234">Daniela</span></span> | <span data-ttu-id="3b0e5-235">전역</span><span class="sxs-lookup"><span data-stu-id="3b0e5-235">Global</span></span>   | <span data-ttu-id="3b0e5-236">해제</span><span class="sxs-lookup"><span data-stu-id="3b0e5-236">False</span></span> |
|<span data-ttu-id="3b0e5-237">Amanda</span><span class="sxs-lookup"><span data-stu-id="3b0e5-237">Amanda</span></span> | <span data-ttu-id="3b0e5-238">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3b0e5-238">Location1MeetingPolicy</span></span> | <span data-ttu-id="3b0e5-239">False</span><span class="sxs-lookup"><span data-stu-id="3b0e5-239">True</span></span>|
|<span data-ttu-id="3b0e5-240">John (외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="3b0e5-240">John (external user)</span></span> | <span data-ttu-id="3b0e5-241">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="3b0e5-241">Not applicable</span></span> | <span data-ttu-id="3b0e5-242">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="3b0e5-242">Not applicable</span></span>|

<span data-ttu-id="3b0e5-243">Daniela에서 구성한 모임은 기록 하 고 Amanda 수 있으며, 정책 설정을 사용 하도록 설정한 경우 Daniela로 구성 된 모임을 녹화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-243">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="3b0e5-244">Amanda에서 구성한 모임은 녹화할 수 있지만, Daniela는 정책 설정을 사용 하지 않도록 설정 하 고 외부 사용자 인 John은 Amanda으로 구성 된 모임을 기록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-244">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="3b0e5-245">클라우드 모임 기록에 대해 자세히 알아보려면 [팀 클라우드 모임 기록을](cloud-recording.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-245">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="3b0e5-246">IP 비디오 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-246">Allow IP video</span></span>

<span data-ttu-id="3b0e5-247">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-247">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="3b0e5-248">비디오는 모임에 대 한 주요 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-248">Video is a key component to meetings.</span></span> <span data-ttu-id="3b0e5-249">일부 조직에서는 관리자가 어떤 사용자의 모임이 비디오를 보유 하 고 있는지 더 자세히 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-249">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="3b0e5-250">이 설정은 사용자가 호스트 하는 모임 및 사용자가 시작한 1:1 통화 및 그룹 통화에서 비디오를 켤 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-250">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 calls and group calls started by a user.</span></span> <span data-ttu-id="3b0e5-251">이 정책을 사용 하도록 설정한 사용자가 구성한 모임에는 모임 참가자가 정책을 사용 하도록 설정한 경우 모임 참가자가 모임에서 비디오 공유를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-251">Meetings organized by a user who has this policy enabled, allow video sharing in the meeting by the meeting participants, if the meeting participants also have the policy enabled.</span></span> <span data-ttu-id="3b0e5-252">배정 된 정책이 없는 모임 참가자 (예: 익명 및 페더레이션 참가자)는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-252">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

![오디오 및 비디오 설정을 사용 하 여 모임을 보여 주는 스크린샷](media/meeting-policies-audio-video-settings.png)

<span data-ttu-id="3b0e5-254">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-254">Let's look at the following example.</span></span>

|<span data-ttu-id="3b0e5-255">사용자</span><span class="sxs-lookup"><span data-stu-id="3b0e5-255">User</span></span> |<span data-ttu-id="3b0e5-256">모임 정책</span><span class="sxs-lookup"><span data-stu-id="3b0e5-256">Meeting policy</span></span>  |<span data-ttu-id="3b0e5-257">IP 영상 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-257">Allow IP Video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3b0e5-258">Daniela</span><span class="sxs-lookup"><span data-stu-id="3b0e5-258">Daniela</span></span>   | <span data-ttu-id="3b0e5-259">전역</span><span class="sxs-lookup"><span data-stu-id="3b0e5-259">Global</span></span>   | <span data-ttu-id="3b0e5-260">False</span><span class="sxs-lookup"><span data-stu-id="3b0e5-260">True</span></span>        |
|<span data-ttu-id="3b0e5-261">Amanda</span><span class="sxs-lookup"><span data-stu-id="3b0e5-261">Amanda</span></span>    | <span data-ttu-id="3b0e5-262">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3b0e5-262">Location1MeetingPolicy</span></span>        | <span data-ttu-id="3b0e5-263">해제</span><span class="sxs-lookup"><span data-stu-id="3b0e5-263">False</span></span>      |

<span data-ttu-id="3b0e5-264">Daniela에서 호스팅하는 모임은 영상 통화를 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-264">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="3b0e5-265">Daniela 모임에 참가 하 고 비디오를 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-265">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="3b0e5-266">Amanda의 정책이 비디오를 허용 하지 않도록 설정 되어 있기 때문에 Daniela 모임에서 비디오를 켤 수 없습니다 Amanda.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-266">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="3b0e5-267">Amanda는 모임의 다른 참가자가 공유 하는 비디오를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-267">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="3b0e5-268">Amanda에서 호스팅하는 모임에서 할당 된 비디오 정책에 관계 없이 비디오를 켤 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-268">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="3b0e5-269">이는 Daniela에서 Amanda의 모임에서 비디오를 켤 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-269">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="3b0e5-270">Daniela에서 비디오를 사용 하 여 Amanda를 호출 하는 경우 Amanda는 오디오 만으로 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-270">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="3b0e5-271">통화가 연결 되 면 Amanda에서 Daniela의 비디오를 볼 수 있지만 영상 통화는 켜지 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-271">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="3b0e5-272">Amanda에서 Daniela를 호출 하는 경우 Daniela는 비디오 및 오디오로 전화를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-272">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="3b0e5-273">통화가 연결 되 면 필요에 따라 Daniela에서 비디오를 켜거나 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-273">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="3b0e5-274">미디어 비트 전송률 (Kbs)</span><span class="sxs-lookup"><span data-stu-id="3b0e5-274">Media bit rate (Kbs)</span></span>

<span data-ttu-id="3b0e5-275">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-275">This is a per-user policy.</span></span> <span data-ttu-id="3b0e5-276">이 설정에 따라 사용자에 대 한 통화 및 모임에서 오디오, 비디오 및 비디오 기반 앱 공유 전송의 미디어 비트 전송률이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-276">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="3b0e5-277">통화 또는 모임에서 사용자의 업링크 및 다운 링크 미디어 트래버스 둘 다에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-277">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="3b0e5-278">이 설정을 사용 하면 조직의 대역폭을 관리 하는 방법을 세부적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-278">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="3b0e5-279">사용자에 게 필요한 모임 시나리오에 따라 좋은 품질 환경을 위해 적절 한 대역폭을 확보 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-279">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="3b0e5-280">최소값은 30kbps이 고 최대값은 모임 시나리오에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-280">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="3b0e5-281">팀에서 좋은 음질의 모임, 통화, 라이브 이벤트에 권장 되는 최소 대역폭에 대해 자세히 알아보려면 [대역폭 요구 사항을](prepare-network.md#bandwidth-requirements)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-281">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="3b0e5-282">모임에 대 한 대역폭이 충분 하지 않은 경우 참가자는 네트워크 품질이 좋지 않다는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-282">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="3b0e5-283">CEO 보드 모임 및 팀 라이브 이벤트와 같이 고품질의 비디오 환경을 필요로 하는 모임의 경우 대역폭을 10mbps로 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-283">For meetings that need the highest quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="3b0e5-284">최대 환경이 설정 된 경우에도 시나리오에 따라 특정 네트워크 조건이 감지 되는 경우 팀 미디어 스택이 낮은 대역폭 조건에 적응 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-284">Even when the maximum experience is set, the Teams media stack adapts to low bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span>

## <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="3b0e5-285">모임 정책 설정-콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="3b0e5-285">Meeting policy settings - Content sharing</span></span>

- [<span data-ttu-id="3b0e5-286">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="3b0e5-286">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="3b0e5-287">참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-287">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="3b0e5-288">외부 참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-288">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="3b0e5-289">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-289">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="3b0e5-290">화이트 보드 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-290">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="3b0e5-291">공유 메모 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-291">Allow shared notes</span></span>](#allow-shared-notes)

### <a name="screen-sharing-mode"></a><span data-ttu-id="3b0e5-292">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="3b0e5-292">Screen sharing mode</span></span>

<span data-ttu-id="3b0e5-293">이는 구성 단위 및 사용자별 정책 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-293">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="3b0e5-294">이 설정은 사용자의 모임에서 데스크톱 및/또는 창 공유를 허용할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-294">This setting controls whether desktop and/or window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="3b0e5-295">배정 된 정책이 없는 모임 참가자 (예: 익명, 게스트, B2B, 페더레이션 참가자)는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-295">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="3b0e5-296">값 설정</span><span class="sxs-lookup"><span data-stu-id="3b0e5-296">Setting value</span></span> |<span data-ttu-id="3b0e5-297">결과가</span><span class="sxs-lookup"><span data-stu-id="3b0e5-297">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="3b0e5-298">**전체 화면**</span><span class="sxs-lookup"><span data-stu-id="3b0e5-298">**Entire screen**</span></span>    | <span data-ttu-id="3b0e5-299">모임에서 전체 데스크톱 공유 및 응용 프로그램 공유를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-299">Full desktop sharing and application sharing is allowed in the meeting</span></span> |
|<span data-ttu-id="3b0e5-300">**단일 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="3b0e5-300">**Single application**</span></span>   | <span data-ttu-id="3b0e5-301">모임에서 응용 프로그램 공유가 허용 됨</span><span class="sxs-lookup"><span data-stu-id="3b0e5-301">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="3b0e5-302">**비활성화**</span><span class="sxs-lookup"><span data-stu-id="3b0e5-302">**Disabled**</span></span>     |<span data-ttu-id="3b0e5-303">모임에서 화면 공유 및 응용 프로그램 공유 기능을 해제 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-303">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="3b0e5-304">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-304">Let's look at the following example.</span></span>

|<span data-ttu-id="3b0e5-305">사용자</span><span class="sxs-lookup"><span data-stu-id="3b0e5-305">User</span></span> |<span data-ttu-id="3b0e5-306">모임 정책</span><span class="sxs-lookup"><span data-stu-id="3b0e5-306">Meeting policy</span></span> |<span data-ttu-id="3b0e5-307">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="3b0e5-307">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3b0e5-308">Daniela</span><span class="sxs-lookup"><span data-stu-id="3b0e5-308">Daniela</span></span>  | <span data-ttu-id="3b0e5-309">전역</span><span class="sxs-lookup"><span data-stu-id="3b0e5-309">Global</span></span>   | <span data-ttu-id="3b0e5-310">전체 화면</span><span class="sxs-lookup"><span data-stu-id="3b0e5-310">Entire screen</span></span> |
|<span data-ttu-id="3b0e5-311">Amanda</span><span class="sxs-lookup"><span data-stu-id="3b0e5-311">Amanda</span></span>   | <span data-ttu-id="3b0e5-312">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3b0e5-312">Location1MeetingPolicy</span></span>  | <span data-ttu-id="3b0e5-313">비활성화</span><span class="sxs-lookup"><span data-stu-id="3b0e5-313">Disabled</span></span> |

<span data-ttu-id="3b0e5-314">Daniela에서 호스팅하는 모임은 모임 참가자가 전체 화면 또는 특정 응용 프로그램을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-314">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="3b0e5-315">Amanda 참가 Daniela의 모임이 Amanda, 화면을 공유할 수 없거나, 정책 설정에 따라 특정 응용 프로그램을 사용 하지 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-315">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="3b0e5-316">Amanda에서 호스트 하는 모임에서는 자신에 게 할당 된 화면 공유 모드 정책에 관계 없이 화면 또는 단일 응용 프로그램을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-316">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span> <span data-ttu-id="3b0e5-317">즉, Daniela는 Amanda 모임의 화면 또는 단일 응용 프로그램을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-317">This means that Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="3b0e5-318">현재 사용자는 Google Chrome을 사용 하는 경우 팀 모임에서 비디오를 재생 하거나 화면을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-318">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

### <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="3b0e5-319">참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-319">Allow a participant to give or request control</span></span>

<span data-ttu-id="3b0e5-320">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-320">This is a per-user policy.</span></span> <span data-ttu-id="3b0e5-321">이 설정은 사용자가 공유 데스크톱 또는 창을 다른 모임 참가자에 게 제어권을 부여할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-321">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="3b0e5-322">컨트롤을 제공 하려면 화면 위쪽을 마우스로 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-322">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="3b0e5-323">사용자에 대해이 설정이 설정 된 경우 **제어권 제공** 옵션이 공유 세션의 위쪽 표시줄에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-323">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![제어권 제공 옵션을 보여 주는 스크린샷](media/meeting-policies-give-control.png)

<span data-ttu-id="3b0e5-325">사용자에 대해 설정이 꺼져 있으면 **제어권 제공** 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-325">If the settings is turned off for the user, the **Give Control** option isn't available.</span></span>

![제어권 부여 옵션을 사용할 수 없음을 보여 주는 스크린샷](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="3b0e5-327">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-327">Let's look at the following example.</span></span>

|<span data-ttu-id="3b0e5-328">사용자</span><span class="sxs-lookup"><span data-stu-id="3b0e5-328">User</span></span> |<span data-ttu-id="3b0e5-329">모임 정책</span><span class="sxs-lookup"><span data-stu-id="3b0e5-329">Meeting policy</span></span>  |<span data-ttu-id="3b0e5-330">참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-330">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3b0e5-331">Daniela</span><span class="sxs-lookup"><span data-stu-id="3b0e5-331">Daniela</span></span>   | <span data-ttu-id="3b0e5-332">전역</span><span class="sxs-lookup"><span data-stu-id="3b0e5-332">Global</span></span>   | <span data-ttu-id="3b0e5-333">False</span><span class="sxs-lookup"><span data-stu-id="3b0e5-333">True</span></span>       |
|<span data-ttu-id="3b0e5-334">Babek</span><span class="sxs-lookup"><span data-stu-id="3b0e5-334">Babek</span></span>    | <span data-ttu-id="3b0e5-335">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3b0e5-335">Location1MeetingPolicy</span></span>        | <span data-ttu-id="3b0e5-336">해제</span><span class="sxs-lookup"><span data-stu-id="3b0e5-336">False</span></span>   |

<span data-ttu-id="3b0e5-337">Daniela는 다른 참가자에 게 제어권을 부여할 수 없기 때문에 Babek에서 구성한 모임의 다른 참가자에 게 공유 데스크톱 또는 창을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-337">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek whereas Babek can't give control to other participants.</span></span>

<span data-ttu-id="3b0e5-338">PowerShell을 사용 하 여 제어권을 제공 하거나 제어권 요청을 받을 수 있는 사람을 제어 하려면 AllowParticipantGiveRequestControl cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-338">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="3b0e5-339">공유 중 공유 콘텐츠를 관리 하 고 제어 하려면 두 파티 모두 팀 데스크톱 클라이언트를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-339">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="3b0e5-340">컨트롤은 어느 쪽이든 브라우저에서 Teams를 실행 중인 경우 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-340">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="3b0e5-341">이것은 해결하려고 하는 기술적 제한 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-341">This is due to a technical limitation that we're planning to fix.</span></span>

### <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="3b0e5-342">외부 참가자가 제어권을 부여 하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-342">Allow an external participant to give or request control</span></span>

<span data-ttu-id="3b0e5-343">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-343">This is a per-user policy.</span></span> <span data-ttu-id="3b0e5-344">조직에서이 사용자에 대해이 집합을 보유 하 고 있는지 여부는 모임 이끌이가 설정한 내용에 관계 없이 외부 참가자가 수행할 수 있는 작업을 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-344">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="3b0e5-345">이 매개 변수는 해당 조직의 모임 정책 내에서 설정한 공유자에 따라 외부 참가자가 제어권을 부여 하거나 공유자 화면 제어권을 요청할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-345">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="3b0e5-346">팀 회의의 외부 참가자는 다음과 같이 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-346">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="3b0e5-347">익명 사용자</span><span class="sxs-lookup"><span data-stu-id="3b0e5-347">Anonymous user</span></span>
- <span data-ttu-id="3b0e5-348">게스트 사용자</span><span class="sxs-lookup"><span data-stu-id="3b0e5-348">Guest users</span></span>  
- <span data-ttu-id="3b0e5-349">B2B 사용자</span><span class="sxs-lookup"><span data-stu-id="3b0e5-349">B2B user</span></span>
- <span data-ttu-id="3b0e5-350">페더레이션 사용자</span><span class="sxs-lookup"><span data-stu-id="3b0e5-350">Federated user</span></span>  

<span data-ttu-id="3b0e5-351">공유 된 사용자가 외부 참가자가 조직에서 **제어권을 부여 하거나 요청할 수 있도록 허용을** 제어 하도록 설정 되어 있는 동안 페더레이션 사용자가 해당 사용자에 게 제어권을 부여할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="3b0e5-351">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="3b0e5-352">PowerShell을 사용 하 여 외부 참가자가 제어권을 제공 하거나 제어권 요청을 수락할 수 있는지 여부를 제어 하려면 AllowExternalParticipantGiveRequestControl cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-352">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="3b0e5-353">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-353">Allow PowerPoint sharing</span></span>

<span data-ttu-id="3b0e5-354">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-354">This is a per-user policy.</span></span> <span data-ttu-id="3b0e5-355">이 설정은 사용자가 모임에서 PowerPoint 슬라이드 데크를 공유할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-355">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="3b0e5-356">익명, 게스트, 페더레이션 사용자를 비롯 한 외부 사용자가 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-356">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="3b0e5-357">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-357">Let's look at the following example.</span></span>

|<span data-ttu-id="3b0e5-358">사용자</span><span class="sxs-lookup"><span data-stu-id="3b0e5-358">User</span></span> |<span data-ttu-id="3b0e5-359">모임 정책</span><span class="sxs-lookup"><span data-stu-id="3b0e5-359">Meeting policy</span></span>  |<span data-ttu-id="3b0e5-360">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-360">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3b0e5-361">Daniela</span><span class="sxs-lookup"><span data-stu-id="3b0e5-361">Daniela</span></span>   | <span data-ttu-id="3b0e5-362">전역</span><span class="sxs-lookup"><span data-stu-id="3b0e5-362">Global</span></span>   | <span data-ttu-id="3b0e5-363">False</span><span class="sxs-lookup"><span data-stu-id="3b0e5-363">True</span></span>       |
|<span data-ttu-id="3b0e5-364">Amanda</span><span class="sxs-lookup"><span data-stu-id="3b0e5-364">Amanda</span></span>   | <span data-ttu-id="3b0e5-365">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3b0e5-365">Location1MeetingPolicy</span></span>        | <span data-ttu-id="3b0e5-366">해제</span><span class="sxs-lookup"><span data-stu-id="3b0e5-366">False</span></span>   |

<span data-ttu-id="3b0e5-367">Amanda 모임 이끌이 인 경우에도 모임에서 PowerPoint 슬라이드 데크를 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-367">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="3b0e5-368">Daniela는 모임이 Amanda으로 구성 된 경우에도 PowerPoint 슬라이드 데크를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-368">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="3b0e5-369">Amanda는 PowerPoint 슬라이드 데크를 공유할 수는 없지만 모임에서 다른 사용자가 공유한 PowerPoint 슬라이드 데크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-369">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

### <a name="allow-whiteboard"></a><span data-ttu-id="3b0e5-370">화이트 보드 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-370">Allow whiteboard</span></span>

<span data-ttu-id="3b0e5-371">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-371">This is a per-user policy.</span></span> <span data-ttu-id="3b0e5-372">이 설정은 사용자가 모임에서 화이트 보드를 공유할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-372">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="3b0e5-373">익명, B2B, 페더레이션 사용자 등의 외부 사용자는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-373">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="3b0e5-374">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-374">Let's look at the following example.</span></span>

|<span data-ttu-id="3b0e5-375">사용자</span><span class="sxs-lookup"><span data-stu-id="3b0e5-375">User</span></span> |<span data-ttu-id="3b0e5-376">모임 정책</span><span class="sxs-lookup"><span data-stu-id="3b0e5-376">Meeting policy</span></span>  |<span data-ttu-id="3b0e5-377">화이트 보드 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-377">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="3b0e5-378">Daniela</span><span class="sxs-lookup"><span data-stu-id="3b0e5-378">Daniela</span></span>   | <span data-ttu-id="3b0e5-379">전역</span><span class="sxs-lookup"><span data-stu-id="3b0e5-379">Global</span></span>   | <span data-ttu-id="3b0e5-380">False</span><span class="sxs-lookup"><span data-stu-id="3b0e5-380">True</span></span>       |
|<span data-ttu-id="3b0e5-381">Amanda</span><span class="sxs-lookup"><span data-stu-id="3b0e5-381">Amanda</span></span>   | <span data-ttu-id="3b0e5-382">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3b0e5-382">Location1MeetingPolicy</span></span>        | <span data-ttu-id="3b0e5-383">해제</span><span class="sxs-lookup"><span data-stu-id="3b0e5-383">False</span></span>   |

<span data-ttu-id="3b0e5-384">Amanda 모임 이끌이 인 경우에도 모임에서 화이트 보드를 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-384">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="3b0e5-385">Daniela는 모임이 Amanda으로 구성 된 경우에도 화이트 보드를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-385">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

### <a name="allow-shared-notes"></a><span data-ttu-id="3b0e5-386">공유 메모 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-386">Allow shared notes</span></span>

<span data-ttu-id="3b0e5-387">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-387">This is a per-user policy.</span></span> <span data-ttu-id="3b0e5-388">이 설정은 사용자가 모임에서 노트를 만들고 공유할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-388">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="3b0e5-389">익명, B2B, 페더레이션 사용자 등의 외부 사용자는 모임 이끌이의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-389">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="3b0e5-390">**모임 메모** 탭은 현재 20 명 미만의 참가자가 있는 모임 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-390">The **Meeting Notes** tab is currently only supported in meetings that have less than 20 participants.</span></span>

<span data-ttu-id="3b0e5-391">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-391">Let's look at the following example.</span></span>

|<span data-ttu-id="3b0e5-392">사용자</span><span class="sxs-lookup"><span data-stu-id="3b0e5-392">User</span></span> |<span data-ttu-id="3b0e5-393">모임 정책</span><span class="sxs-lookup"><span data-stu-id="3b0e5-393">Meeting policy</span></span>  |<span data-ttu-id="3b0e5-394">공유 메모 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-394">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="3b0e5-395">Daniela</span><span class="sxs-lookup"><span data-stu-id="3b0e5-395">Daniela</span></span>   | <span data-ttu-id="3b0e5-396">전역</span><span class="sxs-lookup"><span data-stu-id="3b0e5-396">Global</span></span>   | <span data-ttu-id="3b0e5-397">False</span><span class="sxs-lookup"><span data-stu-id="3b0e5-397">True</span></span>       |
|<span data-ttu-id="3b0e5-398">Amanda</span><span class="sxs-lookup"><span data-stu-id="3b0e5-398">Amanda</span></span>   | <span data-ttu-id="3b0e5-399">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="3b0e5-399">Location1MeetingPolicy</span></span> | <span data-ttu-id="3b0e5-400">해제</span><span class="sxs-lookup"><span data-stu-id="3b0e5-400">False</span></span> |

<span data-ttu-id="3b0e5-401">Daniela는 Amanda의 모임에 메모를 기록 하 고 모든 모임에서 메모를 찍을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-401">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>

## <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="3b0e5-402">모임 정책 설정-게스트 & 참가자</span><span class="sxs-lookup"><span data-stu-id="3b0e5-402">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="3b0e5-403">이 설정은 모임에 참가 하기 전에 대기실에서 대기 하는 모임 참가자와 모임에서 허용 되는 참여 수준을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-403">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="3b0e5-404">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-404">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="3b0e5-405">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="3b0e5-405">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="3b0e5-406">전화 접속 사용자가 대기실를 우회할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-406">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="3b0e5-407">라이브 캡션 사용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-407">Enable live captions</span></span>](#enable-live-captions)
- [<span data-ttu-id="3b0e5-408">모임에서 채팅 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-408">Allow chat in meetings</span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="3b0e5-409">모임에 참가 하는 옵션은 각 팀 그룹의 설정 및 연결 방법에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-409">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="3b0e5-410">그룹에 오디오 회의가 있고이를 사용 하 여 연결 하는 경우 [오디오 회의](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-410">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="3b0e5-411">팀 그룹에 오디오 회의가 없는 경우 [팀에서 모임 참가](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-411">If your Teams group does not have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

### <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="3b0e5-412">익명 사용자가 모임을 시작 하도록 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-412">Let anonymous people start a meeting</span></span>

<span data-ttu-id="3b0e5-413">회의 모임에서 leaderless 전화 걸기를 허용 하는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-413">This is a per-organizer policy that allows for leaderless dial in conferencing meetings.</span></span> <span data-ttu-id="3b0e5-414">이 설정은 사용자가 전화 접속을 통해 조직에서 인증 된 사용자 없이 모임에 참가할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-414">This setting controls whether dial in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="3b0e5-415">기본값은 False 이며, 사용자의 전화 접속은 조직의 인증 된 사용자가 모임에 참가할 때까지 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-415">The default value is False which means dial in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span>

<span data-ttu-id="3b0e5-416">**참고** False 인 경우 전화 접속 사용자가 모임에 먼저 참가 하 고 대기실에 배치 된 경우 조직 사용자는 팀 클라이언트와 모임에 참가 하 여 사용자가 대기실에서 작업을 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-416">**Note** If False and a dial in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="3b0e5-417">사용자에 게 전화를 걸 수 있는 로비 컨트롤이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-417">There are no lobby controls available for dialed in users.</span></span>

### <a name="automatically-admit-people"></a><span data-ttu-id="3b0e5-418">자동으로 사람들의 입장</span><span class="sxs-lookup"><span data-stu-id="3b0e5-418">Automatically admit people</span></span>

<span data-ttu-id="3b0e5-419">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-419">This is a per-organizer policy.</span></span> <span data-ttu-id="3b0e5-420">이 설정은 사용자가 인증 된 사용자가 참여 하 게 될 때까지 자신이 모임에 직접 참가 하거나 대기실에서 대기할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-420">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="3b0e5-421">이 설정은 사용자의 전화 접속에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-421">This setting does not apply to dial in users.</span></span>

![대기실에 사용자가 있는 모임을 보여 주는 스크린샷](media/meeting-policies-lobby.png)

 <span data-ttu-id="3b0e5-423">모임 이끌이는 모임 초대에서 **모임 옵션** 을 클릭 하 여 자신이 예약한 각 모임에 대해이 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-423">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>

 <span data-ttu-id="3b0e5-424">**참고** 모임 옵션에 "대기실를 무시할 수 있는 사람" 이라고 표시 된 설정</span><span class="sxs-lookup"><span data-stu-id="3b0e5-424">**Note** In the meeting options the setting is labeled "Who can bypass the lobby"</span></span>
  
|<span data-ttu-id="3b0e5-425">값 설정</span><span class="sxs-lookup"><span data-stu-id="3b0e5-425">Setting value</span></span>  |<span data-ttu-id="3b0e5-426">조인 동작</span><span class="sxs-lookup"><span data-stu-id="3b0e5-426">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="3b0e5-427">**모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="3b0e5-427">**Everyone**</span></span>   |<span data-ttu-id="3b0e5-428">모든 모임 참가자는 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-428">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="3b0e5-429">여기에는 인증 된 사용자, 신뢰할 수 있는 조직 (페더레이션된)의 외부 사용자, 게스트 및 익명 사용자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-429">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="3b0e5-430">**조직 및 페더레이션된 조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="3b0e5-430">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="3b0e5-431">게스트 사용자와 신뢰할 수 있는 조직의 사용자를 포함 하 여 조직 내에서 인증 된 사용자가 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-431">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="3b0e5-432">익명 사용자가 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-432">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="3b0e5-433">**조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="3b0e5-433">**Everyone in your organization**</span></span>    |<span data-ttu-id="3b0e5-434">게스트 사용자를 포함 하 여 조직 내에서 인증 된 사용자가 대기실에서 대기 하지 않고 바로 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-434">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="3b0e5-435">신뢰할 수 있는 조직과 익명 사용자의 사용자가 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-435">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="3b0e5-436">기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-436">This is the default setting.</span></span>           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="3b0e5-437">전화 접속 사용자가 대기실를 우회할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-437">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="3b0e5-438">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-438">This is a per-organizer policy.</span></span> <span data-ttu-id="3b0e5-439">이 설정은 전화를 통해 전화를 거는 사용자가 모임에 직접 참가 하거나 **자동으로** 허용 되는 사용자 설정에 관계 없이 대기실에서 대기할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-439">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="3b0e5-440">기본값은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-440">The default value is False.</span></span> <span data-ttu-id="3b0e5-441">False 인 경우 전화 접속 사용자는 조직 사용자가 팀 클라이언트와 모임에 참가 하 고 입장할 때까지 대기실에서 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-441">When False, dial in users will wait in the lobby until a organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="3b0e5-442">True 인 경우 사용자의 전화 접속은 조직 사용자가 모임에 참가할 때 자동으로 모임에 참가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-442">When True, dial in users will automatically join the meeting when an organization user joins the meeting.</span></span>

<span data-ttu-id="3b0e5-443">**참고** 조직 사용자가 모임에 참가 하기 전에 전화 접속 사용자가 모임에 참가 하는 경우 조직 사용자가 팀 클라이언트를 사용 하 여 모임에 참가 하 고 입장할 때까지 로비에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-443">**Note** If a dial in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span>

### <a name="enable-live-captions"></a><span data-ttu-id="3b0e5-444">라이브 캡션 사용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-444">Enable live captions</span></span>

<span data-ttu-id="3b0e5-445">이것은 사용자별 정책으로 모임 중에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-445">This is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="3b0e5-446">이 설정은 사용자가 참석할는 모임에서 실시간 **캡션 켜기** 옵션을 사용 하 여 live 캡션을 켜고 끌 것인지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-446">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![라이브 캡션 켜기 옵션을 보여 주는 스크린샷](media/meeting-policies-live-captions.png)

|<span data-ttu-id="3b0e5-448">값 설정</span><span class="sxs-lookup"><span data-stu-id="3b0e5-448">Setting value</span></span> |<span data-ttu-id="3b0e5-449">결과가</span><span class="sxs-lookup"><span data-stu-id="3b0e5-449">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="3b0e5-450">**사용 하지 않도록 설정 되어 있지만 사용자가 무시할 수 있음**</span><span class="sxs-lookup"><span data-stu-id="3b0e5-450">**Disabled but the user can override**</span></span>     | <span data-ttu-id="3b0e5-451">Live 캡션은 모임 중에 사용자에 대해 자동으로 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-451">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="3b0e5-452">사용자는 오버플로 (**...**) 메뉴에서 **라이브 캡션 켜기** 옵션을 표시 하 여 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-452">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="3b0e5-453">기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-453">This is the default setting.</span></span> |
|<span data-ttu-id="3b0e5-454">**비활성화**</span><span class="sxs-lookup"><span data-stu-id="3b0e5-454">**Disabled**</span></span>     | <span data-ttu-id="3b0e5-455">모임 중에는 사용자가 실시간 캡션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-455">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="3b0e5-456">사용자는이 옵션을 켤 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-456">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="3b0e5-457"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="3b0e5-457"><a name="bkcontentsharing"> </a></span></span>

### <a name="allow-chat-in-meetings"></a><span data-ttu-id="3b0e5-458">모임에서 채팅 허용</span><span class="sxs-lookup"><span data-stu-id="3b0e5-458">Allow chat in meetings</span></span>

<span data-ttu-id="3b0e5-459">이는 이끌이 별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-459">This is a per-organizer policy.</span></span> <span data-ttu-id="3b0e5-460">이 설정은 사용자의 모임에서 모임 채팅을 허용할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-460">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="3b0e5-461"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="3b0e5-461"><a name="bkparticipantsandguests"> </a></span></span>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a><span data-ttu-id="3b0e5-462">모임 정책 설정-지정 된 발표자 역할 모드</span><span class="sxs-lookup"><span data-stu-id="3b0e5-462">Meeting policy settings - Designated presenter role mode</span></span>

<span data-ttu-id="3b0e5-463">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-463">This is a per-user policy.</span></span> <span data-ttu-id="3b0e5-464">이 설정을 사용 하면 팀 클라이언트의 **모임 옵션** 에서 설정할 **수 있는 사용자** 의 기본값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-464">This setting lets you change the default value of the **Who can present?** setting in **Meeting options** in the Teams client.</span></span> <span data-ttu-id="3b0e5-465">이 정책 설정은 모임 시작 모임을 포함 하 여 모든 모임에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-465">This policy setting affects all meetings, including Meet Now meetings.</span></span>

<span data-ttu-id="3b0e5-466">**누가 발표할 수 있나요?** 모임 이끌이가 모임에 발표자가 될 수 있는 사용자를 선택 하면이 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-466">The **Who can present?** setting lets meeting organizers choose who can be presenters in a meeting.</span></span> <span data-ttu-id="3b0e5-467">자세히 알아보려면 [팀 모임에서](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019) [팀 모임 및 역할에 대 한 참가자 설정 변경을](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-467">To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).</span></span>

<span data-ttu-id="3b0e5-468">현재는 PowerShell을 사용 하 여이 정책 설정을 구성할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-468">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="3b0e5-469">[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용 하 여 기존 팀 모임 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-469">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="3b0e5-470">또는 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용 하 여 새 팀 모임 정책을 만들고 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-470">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="3b0e5-471">**표시할 수 있는 사용자** 의 기본값을 지정 하려면 팀에서 **DesignatedPresenterRoleMode** 매개 변수를 다음 중 하나로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-471">To specify the default value of the **Who can present?** setting in Teams, set the **DesignatedPresenterRoleMode** parameter to one of the following:</span></span>

- <span data-ttu-id="3b0e5-472">**EveryoneUserOverride**: 모든 모임 참가자는 발표자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-472">**EveryoneUserOverride**:  All meeting participants can be presenters.</span></span> <span data-ttu-id="3b0e5-473">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-473">This is the default value.</span></span> <span data-ttu-id="3b0e5-474">이 매개 변수는 팀의 **모든 사용자** 설정에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-474">This parameter corresponds to the **Everyone** setting in Teams.</span></span>
- <span data-ttu-id="3b0e5-475">**EveryoneInCompanyUserOverride**: 게스트 사용자를 포함 하 여 조직에서 인증 된 사용자가 발표자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-475">**EveryoneInCompanyUserOverride**: Authenticated users in the organization, including guest users, can be presenters.</span></span> <span data-ttu-id="3b0e5-476">이 매개 변수는 팀의 **조직 내 사용자** 설정에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-476">This parameter corresponds to the **People in my organization** setting in Teams.</span></span>
- <span data-ttu-id="3b0e5-477">**OrganizerOnlyUserOverride**: 모임 이끌이만 발표자가 될 수 있으며 모든 모임 참가자가 참석자로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-477">**OrganizerOnlyUserOverride**: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees.</span></span> <span data-ttu-id="3b0e5-478">이 매개 **변수는 팀의 자신만 설정** 에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-478">This parameter corresponds to the **Only me** setting in Teams.</span></span>

<span data-ttu-id="3b0e5-479">기본값을 설정한 후에도 모임 이끌이는 팀에서이 설정을 변경 하 고 자신이 예약한 모임에 발표할 수 있는 사람을 선택할 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-479">Keep in mind that after you set the default value, meeting organizers can still change this setting in Teams and choose who can present in the meetings that they schedule.</span></span>

## <a name="meeting-policy-settings---meeting-attendance-report"></a><span data-ttu-id="3b0e5-480">모임 정책 설정-모임 참석 보고서</span><span class="sxs-lookup"><span data-stu-id="3b0e5-480">Meeting policy settings - Meeting attendance report</span></span>

<span data-ttu-id="3b0e5-481">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-481">This is a per-user policy.</span></span> <span data-ttu-id="3b0e5-482">이 설정은 모임 이끌이가 [모임 참석 보고서](teams-analytics-and-reports/meeting-attendance-report.md)를 다운로드할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-482">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="3b0e5-483">현재는 PowerShell을 사용 하 여이 정책 설정을 구성할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-483">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="3b0e5-484">[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용 하 여 기존 팀 모임 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-484">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="3b0e5-485">또는 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용 하 여 새 팀 모임 정책을 만들고 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-485">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="3b0e5-486">모임 이끌이가 모임 참석 보고서를 다운로드 하도록 설정 하려면 **AllowEngagementReport** 매개 변수를 **Enabled**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-486">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="3b0e5-487">이 설정을 사용 하면 **참가자** 창에 보고서를 다운로드 하는 옵션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-487">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="3b0e5-488">모임 이끌이가 보고서를 다운로드 하지 못하도록 하려면 매개 변수를 **Disabled**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-488">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="3b0e5-489">기본적으로이 설정은 비활성화 되어 있으며 보고서를 다운로드 하는 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-489">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a><span data-ttu-id="3b0e5-490">모임 정책 설정-제도 모드의 모임 공급자</span><span class="sxs-lookup"><span data-stu-id="3b0e5-490">Meeting policy settings - Meeting provider for Islands mode</span></span>

<span data-ttu-id="3b0e5-491">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-491">This is a per-user policy.</span></span> <span data-ttu-id="3b0e5-492">이 설정은 *아일랜드 모드에 있는 사용자*에 게 어떤 Outlook 모임 추가 기능을 사용 하는 지를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-492">This setting controls which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="3b0e5-493">사용자가 팀 모임 추가 기능을 사용할 수 있는지, 팀 모임이 나 비즈니스용 Skype 모임 추가 기능을 모두 사용 하 여 Outlook에서 모임을 예약할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-493">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="3b0e5-494">이 정책은 아일랜드 모드에 있는 사용자 에게만 적용할 수 있으며 팀 모임 정책에서 **AllowOutlookAddIn** 매개 변수를 **True** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-494">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span>

<span data-ttu-id="3b0e5-495">현재는 PowerShell을 사용 하 여이 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-495">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="3b0e5-496">[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용 하 여 기존 팀 모임 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-496">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="3b0e5-497">또는 [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용 하 여 새 팀 모임 정책을 만들고 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-497">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="3b0e5-498">사용자에 게 제공 하려는 모임 추가 기능을 지정 하려면 다음과 같이 **PreferredMeetingProviderForIslandsMode** 매개 변수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-498">To specify which meeting add-in you want to be available to users, set the **PreferredMeetingProviderForIslandsMode** parameter as follows:</span></span>

- <span data-ttu-id="3b0e5-499">Outlook에서 팀 모임 추가 기능 및 비즈니스용 Skype 추가 기능을 모두 사용 하도록 매개 변수를 **TeamsAndSfB** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-499">Set the parameter to **TeamsAndSfB** to enable both the Teams Meeting add-in and Skype for Business add-in in Outlook.</span></span> <span data-ttu-id="3b0e5-500">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-500">This is the default value.</span></span>
- <span data-ttu-id="3b0e5-501">Outlook에서 팀 모임 추가 기능만 사용할 수 있도록 하려면 해당 매개 변수를 **팀** 으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-501">Set the parameter to **Teams** to enable only the Teams Meeting add-in in Outlook.</span></span> <span data-ttu-id="3b0e5-502">이 정책 설정은 이후의 모든 모임에 팀 모임 참가 링크가 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-502">This policy setting ensures that all future meetings have a Teams meeting join link.</span></span> <span data-ttu-id="3b0e5-503">팀에 대 한 기존 비즈니스용 Skype 모임 참가 링크는 마이그레이션하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-503">It doesn't migrate existing Skype for Business meeting join links to Teams.</span></span> <span data-ttu-id="3b0e5-504">이 정책 설정은 현재 상태, 채팅, PSTN 통화 또는 비즈니스용 Skype의 기타 기능에는 영향을 주지 않으며,이는 사용자가 이러한 기능을 위해 계속 해 서 비즈니스용 Skype를 사용 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-504">This policy setting doesn't affect presence, chat, PSTN calling, or any other capabilities in Skype for Business, which means that users will continue to use Skype for Business for these capabilities.</span></span>

  <span data-ttu-id="3b0e5-505">매개 변수를 **팀**으로 설정한 다음 다시 **TeamsAndSfB**로 전환 하는 경우 두 모임 추가 기능이 모두 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-505">If you set the parameter to **Teams**, and then switch back to **TeamsAndSfB**, both meeting add-ins are enabled.</span></span> <span data-ttu-id="3b0e5-506">그러나 기존 팀 모임 참가 링크는 비즈니스용 Skype로 마이그레이션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-506">However, note that existing Teams meeting join links won't be migrated to Skype for Business.</span></span> <span data-ttu-id="3b0e5-507">변경 후에 예약 된 비즈니스용 Skype 모임에는 비즈니스용 Skype 모임 참가 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-507">Only Skype for Business meetings scheduled after the change will have a Skype for Business meeting join link.</span></span>

## <a name="meeting-policy-settings---video-filters-mode"></a><span data-ttu-id="3b0e5-508">모임 정책 설정-비디오 필터 모드</span><span class="sxs-lookup"><span data-stu-id="3b0e5-508">Meeting policy settings - Video filters mode</span></span>

<span data-ttu-id="3b0e5-509">이것은 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-509">This is a per-user policy.</span></span> <span data-ttu-id="3b0e5-510">이 설정은 사용자가 모임에서 비디오 배경을 사용자 지정할 수 있는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-510">This setting controls whether users can customize their video background in a meeting.</span></span>

<span data-ttu-id="3b0e5-511">현재는 PowerShell을 사용 하 여이 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-511">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="3b0e5-512">[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용 하 여 기존 팀 모임 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-512">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="3b0e5-513">또는 [새 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용 하 여 새 팀 모임 정책을 만든 다음 사용자에 게 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-513">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet, and then assign the policy to users.</span></span>

<span data-ttu-id="3b0e5-514">사용자가 모임에서 비디오 배경을 사용자 지정할 수 있는지 여부를 지정 하려면 다음과 같이 **VideoFiltersMode** 매개 변수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-514">To specify whether users can customize their video background in a meeting, set the **VideoFiltersMode** parameter as follows:</span></span>

|<span data-ttu-id="3b0e5-515">PowerShell에서 값 설정</span><span class="sxs-lookup"><span data-stu-id="3b0e5-515">Setting value in PowerShell</span></span> |<span data-ttu-id="3b0e5-516">결과가</span><span class="sxs-lookup"><span data-stu-id="3b0e5-516">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="3b0e5-517">**NoFilters**</span><span class="sxs-lookup"><span data-stu-id="3b0e5-517">**NoFilters**</span></span>     |<span data-ttu-id="3b0e5-518">사용자가 비디오 배경을 사용자 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-518">User can't customize their video background.</span></span>|
|<span data-ttu-id="3b0e5-519">**BlurOnly**</span><span class="sxs-lookup"><span data-stu-id="3b0e5-519">**BlurOnly**</span></span>     |<span data-ttu-id="3b0e5-520">사용자가 비디오 배경을 흐리게 하는 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-520">User has the option to blur their video background.</span></span> |
|<span data-ttu-id="3b0e5-521">**BlurandDefaultBackgrounds**</span><span class="sxs-lookup"><span data-stu-id="3b0e5-521">**BlurandDefaultBackgrounds**</span></span>     |<span data-ttu-id="3b0e5-522">사용자는 비디오 배경을 흐리게 하거나 기본 이미지 집합 중에서 선택 하 여 배경으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-522">User has the option to blur their video background or choose from the default set of images to use as their background.</span></span> |
|<span data-ttu-id="3b0e5-523">**AllFilters**</span><span class="sxs-lookup"><span data-stu-id="3b0e5-523">**AllFilters**</span></span>     |<span data-ttu-id="3b0e5-524">사용에는 비디오 배경을 흐리게 하거나 기본 이미지 집합에서 선택 하거나 배경으로 사용할 사용자 지정 이미지를 업로드 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-524">Use has the option to blur their video background, choose from the default set of images, or upload custom images to use as their background.</span></span> |

> [!NOTE]
> <span data-ttu-id="3b0e5-525">사용자가 업로드 한 이미지는 팀에 의해 차단 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-525">Images uploaded by users aren't screened by Teams.</span></span> <span data-ttu-id="3b0e5-526">**Allfilters** 설정을 사용 하는 경우 사용자가 공격적인 또는 부적절 한 이미지를 업로드 하거나 조직에 팀 모임 배경에 사용할 권한이 없는 이미지를 보호 하기 위한 내부 조직 정책이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b0e5-526">When you use the **AllFilters** setting, you should have internal organization policies to prevent users from uploading offensive or inappropriate images, or images your organization don't have rights to use for Teams meeting backgrounds.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3b0e5-527">관련 항목</span><span class="sxs-lookup"><span data-stu-id="3b0e5-527">Related topics</span></span>

- [<span data-ttu-id="3b0e5-528">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="3b0e5-528">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="3b0e5-529">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="3b0e5-529">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="3b0e5-530">사용자의 RestrictedAnonymousAccess 팀 모임 정책 제거</span><span class="sxs-lookup"><span data-stu-id="3b0e5-530">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
