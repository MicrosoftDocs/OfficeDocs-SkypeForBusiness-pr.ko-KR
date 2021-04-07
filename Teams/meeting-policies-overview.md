---
title: 모임 정책 관리
author: CarolynRowe
ms.author: crowe
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
- seo-marvel-apr2020
description: Teams에서 모임 정책 설정을 관리하고 이를 사용하여 사용자가 예약한 모임에 대해 모임 참가자가 사용할 수 있는 기능을 제어하는 방법을 배워야 합니다.
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598760"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="c084e-103">Teams에서의 모임 정책 관리</span><span class="sxs-lookup"><span data-stu-id="c084e-103">Manage meeting policies in Teams</span></span>

<span data-ttu-id="c084e-104"><a name="bkautomatically-admit-people"> </a></span><span class="sxs-lookup"><span data-stu-id="c084e-104"><a name="bkautomatically-admit-people"> </a></span></span>

<span data-ttu-id="c084e-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span><span class="sxs-lookup"><span data-stu-id="c084e-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span></span>

<span data-ttu-id="c084e-106"><a name="bkallow-transcription"> </a></span><span class="sxs-lookup"><span data-stu-id="c084e-106"><a name="bkallow-transcription"> </a></span></span>

<span data-ttu-id="c084e-107">모임 정책은 조직에서 사용자가 예약한 모임 참가자가 사용할 수 있는 기능을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-107">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="c084e-108">자동으로 생성되거나 사용자 지정 정책을 만들고 할당하는 전역(Org-wide default) 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-108">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="c084e-109">Microsoft Teams 관리 센터 또는 [PowerShell을](teams-powershell-overview.md)사용하여 모임 정책을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-109">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c084e-110">역할 사용에 대한 자세한 내용은 모임 발표자 및 참석자 권한 관리에 대한 자세한 내용은 Teams 모임의 [역할을 참조하세요.](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)</span><span class="sxs-lookup"><span data-stu-id="c084e-110">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="c084e-111">다음 방법으로 정책을 구현할 수 있습니다. 이 정책은 모임이 시작되기 전에, 모임 중에 또는 모임 후에 사용자에 대한 모임 경험에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-111">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="c084e-112">구현 유형</span><span class="sxs-lookup"><span data-stu-id="c084e-112">Implementation type</span></span>  |<span data-ttu-id="c084e-113">설명</span><span class="sxs-lookup"><span data-stu-id="c084e-113">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="c084e-114">구성자당</span><span class="sxs-lookup"><span data-stu-id="c084e-114">Per-organizer</span></span>    |<span data-ttu-id="c084e-115">이끌이당 정책을 구현할 때 모든 모임 참가자는 이끌이의 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-115">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="c084e-116">예를 들어 **사용자를** 자동으로 지정하는 것은 조직 내 정책으로, 사용자가 모임에 직접 참가할지 아니면 정책이 할당된 사용자가 예약한 모임을 위해 로비에서 대기할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-116">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="c084e-117">사용자당</span><span class="sxs-lookup"><span data-stu-id="c084e-117">Per-user</span></span>    |<span data-ttu-id="c084e-118">사용자당 정책을 구현할 때 사용자당 정책만 적용하여 이끌이 및/또는 모임 참가자에 대한 특정 기능을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-118">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="c084e-119">예를 들어 채널에서 **지금 만나기 허용은** 사용자당 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-119">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="c084e-120">이끌이 및 사용자당</span><span class="sxs-lookup"><span data-stu-id="c084e-120">Per-organizer and per-user</span></span>     |<span data-ttu-id="c084e-121">이끌이 및 사용자당 정책의 조합을 구현하는 경우 해당 정책 및 이끌이의 정책에 따라 모임 참가자에 대해 특정 기능이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-121">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="c084e-122">예를 들어 클라우드 기록 **허용은** 이끌이 및 사용자당 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-122">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="c084e-123">모임 이끌이 및 참가자가 녹음/녹화를 시작하고 중지할 수 있도록 이 설정을 켜 습니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-123">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="c084e-124">전역 정책에서 설정을 편집하거나 하나 이상의 사용자 지정 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-124">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="c084e-125">사용자 지정 정책을 만들고 할당하지 않는 한 사용자는 전역 정책을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-125">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="c084e-126">사용자가 오디오 회의 라이선스를 사용하도록 설정하거나 사용자가 오디오 회의를 허용하는 경우 모임 세부 정보 단추를 사용할 수 있습니다. 그렇지 않은 경우 모임 세부 정보를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-126">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="c084e-127">사용자 지정 모임 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="c084e-127">Create a custom meeting policy</span></span>

1. <span data-ttu-id="c084e-128">Microsoft Teams 관리 센터의 왼쪽 탐색에서 모임 모임 정책  >  **으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="c084e-128">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="c084e-129">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-129">Click **Add**.</span></span>
3. <span data-ttu-id="c084e-130">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-130">Enter a name and description for the policy.</span></span> <span data-ttu-id="c084e-131">이름은 특수 문자가 포함될 수 없으며 64자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-131">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="c084e-132">원하는 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-132">Choose the settings that you want.</span></span>
5. <span data-ttu-id="c084e-133">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-133">Click **Save**.</span></span>

<span data-ttu-id="c084e-134">예를 들어, 사용자 수가 많은데 모임에 필요한 대역폭의 양을 제한하려고 한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-134">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="c084e-135">"제한된 대역폭"이라는 새 사용자 지정 정책을 만들고 다음 설정을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-135">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="c084e-136">**오디오 및 비디오** 에서:</span><span class="sxs-lookup"><span data-stu-id="c084e-136">Under **Audio & video**:</span></span>

- <span data-ttu-id="c084e-137">클라우드 녹음/녹화 허용을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-137">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="c084e-138">IP 비디오 허용을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-138">Turn off Allow IP video.</span></span>

<span data-ttu-id="c084e-139">**콘텐츠 공유** 에서:</span><span class="sxs-lookup"><span data-stu-id="c084e-139">Under **Content sharing**:</span></span>

- <span data-ttu-id="c084e-140">화면 공유 모드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-140">Disable screen sharing mode.</span></span>
- <span data-ttu-id="c084e-141">화이트보드 허용을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-141">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="c084e-142">공유 노트 허용을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-142">Turn off Allow shared notes.</span></span>

<span data-ttu-id="c084e-143">그 다음 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-143">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="c084e-144">모임 정책 편집</span><span class="sxs-lookup"><span data-stu-id="c084e-144">Edit a meeting policy</span></span>

<span data-ttu-id="c084e-145">전역 정책 및 만든 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-145">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="c084e-146">Microsoft Teams 관리 센터의 왼쪽 탐색에서 모임 모임 정책  >  **으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="c084e-146">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="c084e-147">정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-147">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="c084e-148">여기서 원하는 내용을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-148">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="c084e-149">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-149">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="c084e-150">사용자는 한 번씩 하나의 모임 정책만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-150">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="c084e-151">사용자에게 모임 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c084e-151">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="c084e-152">사용자가 할당된 경우 정책을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-152">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="c084e-153">먼저 영향을 받는 모든 사용자에게 다른 정책을 할당한 다음 원래 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-153">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="c084e-154">모임 정책 설정</span><span class="sxs-lookup"><span data-stu-id="c084e-154">Meeting policy settings</span></span>

<span data-ttu-id="c084e-155">모임 정책 페이지에서 기존  정책을 선택하거나  추가를 선택하여 새 정책을 추가하면 다음에 대한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c084e-155">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="c084e-156">일반</span><span class="sxs-lookup"><span data-stu-id="c084e-156">General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="c084e-157">오디오 & 비디오</span><span class="sxs-lookup"><span data-stu-id="c084e-157">Audio & video</span></span>](meeting-policies-audio-and-video.md)
- [<span data-ttu-id="c084e-158">콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="c084e-158">Content sharing</span></span>](meeting-policies-content-sharing.md)
- [<span data-ttu-id="c084e-159">참가자 & 게스트</span><span class="sxs-lookup"><span data-stu-id="c084e-159">Participants & guests</span></span>](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a><span data-ttu-id="c084e-160">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c084e-160">Related topics</span></span>

- [<span data-ttu-id="c084e-161">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="c084e-161">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="c084e-162">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c084e-162">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="c084e-163">사용자로부터 RestrictedAnonymousAccesss Teams 모임 정책 제거</span><span class="sxs-lookup"><span data-stu-id="c084e-163">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)