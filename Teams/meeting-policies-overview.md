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
description: 모임에서 모임 정책 설정을 관리하고 Teams 모임 참가자가 예약한 모임에 사용할 수 있는 기능을 제어하는 방법을 학습합니다.
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598760"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="2c23d-103">Teams에서의 모임 정책 관리</span><span class="sxs-lookup"><span data-stu-id="2c23d-103">Manage meeting policies in Teams</span></span>

<span data-ttu-id="2c23d-104"><a name="bkautomatically-admit-people"> </a></span><span class="sxs-lookup"><span data-stu-id="2c23d-104"><a name="bkautomatically-admit-people"> </a></span></span>

<span data-ttu-id="2c23d-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span><span class="sxs-lookup"><span data-stu-id="2c23d-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span></span>

<span data-ttu-id="2c23d-106"><a name="bkallow-transcription"> </a></span><span class="sxs-lookup"><span data-stu-id="2c23d-106"><a name="bkallow-transcription"> </a></span></span>

<span data-ttu-id="2c23d-107">모임 정책은 조직에서 사용자가 예약한 모임 참가자가 사용할 수 있는 기능을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-107">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="2c23d-108">자동 생성된 전역(조직 전체의 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어서 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-108">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="2c23d-109">Microsoft Teams 관리 센터에서 아니면 [PowerShell](teams-powershell-overview.md)을 사용하여 모임 정책을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-109">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2c23d-110">역할을 사용하여 모임 발표자 및 참석자 권한 관리하기에 대한 자세한 내용은[ Teams 모임에서 역할](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c23d-110">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="2c23d-111">다음 방법으로 정책을 구현하면 이 정책은 모임이 시작되기 전이나, 모임 도중이나 모임 후에 사용자의 모임 환경에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-111">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="2c23d-112">구현 유형</span><span class="sxs-lookup"><span data-stu-id="2c23d-112">Implementation type</span></span>  |<span data-ttu-id="2c23d-113">설명</span><span class="sxs-lookup"><span data-stu-id="2c23d-113">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="2c23d-114">모임 이끌이별</span><span class="sxs-lookup"><span data-stu-id="2c23d-114">Per-organizer</span></span>    |<span data-ttu-id="2c23d-115">이끌이별 정책을 구현하면 모임의 모든 참가자가 이끌이의 정책을 이어 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-115">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="2c23d-116">예를 들어 **사용자를** 자동으로 지정하는 것은 조직 내 정책으로, 사용자가 모임에 직접 참가할지 아니면 정책이 할당된 사용자가 예약한 모임을 위해 로비에서 대기할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-116">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="2c23d-117">사용자별</span><span class="sxs-lookup"><span data-stu-id="2c23d-117">Per-user</span></span>    |<span data-ttu-id="2c23d-118">사용자별 정책을 구현하는 경우 사용자별 정책이 적용되어 이끌이 및/또는 모임 참가자의 특정 기능을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-118">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="2c23d-119">예를 들어 **지금 채널에서 모임 시작 허용** 은 사용자별 정책에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-119">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="2c23d-120">이끌이별 및 사용자별</span><span class="sxs-lookup"><span data-stu-id="2c23d-120">Per-organizer and per-user</span></span>     |<span data-ttu-id="2c23d-121">이끌이별 및 사용자별 정책 조합을 구현하는 경우 해당 정책 및 이끌이의 정책에 따라 모임 참가자의 특정 기능이 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-121">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="2c23d-122">예를 들어 **클라우드 녹음/녹화 허용** 은 이끌이별 및 사용자별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-122">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="2c23d-123">모임 이끌이 및 참가자가 녹음/녹화를 시작하고 중지할 수 있도록 이 설정을 켜 습니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-123">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="2c23d-124">전역 정책의 설정을 편집하거나 하나 이상의 사용자 지정 정책을 만들어 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-124">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="2c23d-125">사용자 지정 정책을 만들고 할당하지 않으면 사용자에게 전역 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-125">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="2c23d-126">사용자가 오디오 회의 라이선스를 사용하도록 설정하거나 사용자가 오디오 회의에 포함되어 있는 경우 모임 세부 정보 단추를 사용할 수 있습니다. 그렇지 않은 경우 모임 세부 정보를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-126">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="2c23d-127">사용자 지정 모임 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="2c23d-127">Create a custom meeting policy</span></span>

1. <span data-ttu-id="2c23d-128">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **모임** > **모임 정책** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-128">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="2c23d-129">**추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-129">Click **Add**.</span></span>
3. <span data-ttu-id="2c23d-130">정책의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-130">Enter a name and description for the policy.</span></span> <span data-ttu-id="2c23d-131">이름에 특수 문자가 들어가거나 64자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-131">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="2c23d-132">원하는 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-132">Choose the settings that you want.</span></span>
5. <span data-ttu-id="2c23d-133">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-133">Click **Save**.</span></span>

<span data-ttu-id="2c23d-134">예를 들어, 사용자 수가 많은데 모임에 필요한 대역폭의 양을 제한하려고 한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-134">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="2c23d-135">"제한된 대역폭"이라는 새 사용자 지정 정책을 만들고 다음 설정을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-135">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="2c23d-136">**오디오 및 비디오** 에서:</span><span class="sxs-lookup"><span data-stu-id="2c23d-136">Under **Audio & video**:</span></span>

- <span data-ttu-id="2c23d-137">클라우드 녹음/녹화 허용을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-137">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="2c23d-138">IP 비디오 허용을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-138">Turn off Allow IP video.</span></span>

<span data-ttu-id="2c23d-139">**콘텐츠 공유** 에서:</span><span class="sxs-lookup"><span data-stu-id="2c23d-139">Under **Content sharing**:</span></span>

- <span data-ttu-id="2c23d-140">화면 공유 모드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-140">Disable screen sharing mode.</span></span>
- <span data-ttu-id="2c23d-141">화이트보드 허용을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-141">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="2c23d-142">공유 노트 허용을 끕니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-142">Turn off Allow shared notes.</span></span>

<span data-ttu-id="2c23d-143">그 다음 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-143">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="2c23d-144">모임 정책 편집</span><span class="sxs-lookup"><span data-stu-id="2c23d-144">Edit a meeting policy</span></span>

<span data-ttu-id="2c23d-145">전역 정책 및 직접 만든 사용자 지정 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-145">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="2c23d-146">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **모임** > **모임 정책** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-146">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="2c23d-147">정책 이름 왼쪽을 클릭하여 정책을 선택한 다음 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-147">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="2c23d-148">여기서 원하는 내용을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-148">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="2c23d-149">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-149">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="2c23d-150">한 번에 한 개의 모임 정책만 사용자에게 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-150">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="2c23d-151">사용자에게 모임 정책 할당</span><span class="sxs-lookup"><span data-stu-id="2c23d-151">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="2c23d-152">사용자에게 할당된 정책을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-152">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="2c23d-153">먼저 영향을 받는 모든 사용자에게 다른 정책을 할당한 후에 처음의 정책을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-153">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="2c23d-154">모임 정책 설정</span><span class="sxs-lookup"><span data-stu-id="2c23d-154">Meeting policy settings</span></span>

<span data-ttu-id="2c23d-155">모임 정책 페이지에서 기존  정책을 선택하거나  추가를 선택하여 새 정책을 추가하면 다음에 대한 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c23d-155">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="2c23d-156">일반</span><span class="sxs-lookup"><span data-stu-id="2c23d-156">General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="2c23d-157">오디오 및 비디오</span><span class="sxs-lookup"><span data-stu-id="2c23d-157">Audio & video</span></span>](meeting-policies-audio-and-video.md)
- [<span data-ttu-id="2c23d-158">콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="2c23d-158">Content sharing</span></span>](meeting-policies-content-sharing.md)
- [<span data-ttu-id="2c23d-159">참가자 및 게스트</span><span class="sxs-lookup"><span data-stu-id="2c23d-159">Participants & guests</span></span>](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a><span data-ttu-id="2c23d-160">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2c23d-160">Related topics</span></span>

- [<span data-ttu-id="2c23d-161">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="2c23d-161">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="2c23d-162">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="2c23d-162">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="2c23d-163">사용자의 RestrictedAnonymousAccess Teams 모임 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="2c23d-163">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)