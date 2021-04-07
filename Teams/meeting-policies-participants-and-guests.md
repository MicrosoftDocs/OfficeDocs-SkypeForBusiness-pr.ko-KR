---
title: 참가자 및 게스트에 대한 모임 정책 관리
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
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: 참가자 및 게스트에 대한 Teams에서 모임 정책 설정을 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: 51d121ab9c537e6ba304045e47b6e875cd98afd6
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598754"
---
# <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="ca77e-103">모임 정책 설정 - 참가자 & 게스트</span><span class="sxs-lookup"><span data-stu-id="ca77e-103">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="ca77e-104"><a name="bkmeetingparticipants"> </a></span><span class="sxs-lookup"><span data-stu-id="ca77e-104"><a name="bkmeetingparticipants"> </a></span></span>

<span data-ttu-id="ca77e-105">이러한 설정은 모임에 참가하기 전에 로비에서 대기하는 모임 참가자와 모임에서 허용되는 참여 수준을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-105">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="ca77e-106">익명의 사용자가 모임을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-106">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="ca77e-107">자동으로 인원을 인정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-107">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="ca77e-108">전화 접속 사용자가 로비를 우회할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="ca77e-108">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="ca77e-109">라이브 캡션 사용</span><span class="sxs-lookup"><span data-stu-id="ca77e-109">Enable live captions</span></span>](#enable-live-captions)
- [<span data-ttu-id="ca77e-110">모임에서 채팅 허용</span><span class="sxs-lookup"><span data-stu-id="ca77e-110">Allow chat in meetings</span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="ca77e-111">모임에 참가하는 옵션은 각 Teams 그룹의 설정 및 연결 방법에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-111">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="ca77e-112">그룹에 오디오 회의가 있으며 연결에 사용하는 경우 오디오 회의 [를 참조합니다.](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="ca77e-112">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="ca77e-113">Teams 그룹에 오디오 회의가 없는 경우 Teams에서 모임 [참가를 참조합니다.](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)</span><span class="sxs-lookup"><span data-stu-id="ca77e-113">If your Teams group doesn't have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

## <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="ca77e-114">익명의 사용자가 모임을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-114">Let anonymous people start a meeting</span></span>

<span data-ttu-id="ca77e-115">이 설정은 지시자가 없는 전화 접속 회의 모임을 허용하는 조직자당 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-115">This setting is a per-organizer policy that allows for leaderless dial-in conferencing meetings.</span></span> <span data-ttu-id="ca77e-116">이 설정은 전화 접속 사용자가 조직의 인증된 사용자가 참석하지 않고 모임에 참가할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-116">This setting controls whether dial-in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="ca77e-117">기본적으로 이 설정은 해제되어 전화 접속 사용자가 조직의 인증된 사용자가 모임에 참가할 때까지 로비에서 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-117">By default, this setting is turned off, which means dial-in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="ca77e-118">이 설정을 해제하고 전화 접속 사용자가 모임에 먼저 참가하고 로비에 배치되는 경우 조직 사용자는 Teams 클라이언트와 모임에 참가하여 로비에서 사용자를 인정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-118">If this setting is turned off and a dial-in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="ca77e-119">사용자가 전화를 걸 때 사용할 수 있는 로비 컨트롤은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-119">There are no lobby controls available for dialed in users.</span></span>

## <a name="automatically-admit-people"></a><span data-ttu-id="ca77e-120">자동으로 인원을 인정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-120">Automatically admit people</span></span>

<span data-ttu-id="ca77e-121">구성자당 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-121">This is a per-organizer policy.</span></span> <span data-ttu-id="ca77e-122">이 설정은 인증된 사용자가 모임에 직접 참가할지 아니면 로비에서 대기할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-122">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="ca77e-123">이 설정은 전화 접속 사용자에게는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-123">This setting does not apply to dial-in users.</span></span>

![로비에서 사용자와의 모임을 보여주는 스크린샷](media/meeting-policies-lobby.png)

 <span data-ttu-id="ca77e-125">모임 이끌이는  모임 초대에서 모임 옵션을 클릭하여 예약한 각 모임에 대해 이 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-125">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="ca77e-126">모임 옵션에서 설정에는 "로비를 무시할 수 있는 사용자"가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-126">In the meeting options the setting is labeled "Who can bypass the lobby".</span></span> <span data-ttu-id="ca77e-127">모든 사용자에 대한 기본 설정을 변경하면 해당 사용자가 구성한 모든 새 모임 및 사용자가 모임 옵션을 수정하지 않은 이전 모임에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-127">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>
  
|<span data-ttu-id="ca77e-128">값 설정</span><span class="sxs-lookup"><span data-stu-id="ca77e-128">Setting value</span></span>  |<span data-ttu-id="ca77e-129">조인 동작</span><span class="sxs-lookup"><span data-stu-id="ca77e-129">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="ca77e-130">**모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="ca77e-130">**Everyone**</span></span>   |<span data-ttu-id="ca77e-131">모든 모임 참가자는 로비에서 대기하지 않고 직접 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-131">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="ca77e-132">여기에는 인증된 사용자, 신뢰할 수 있는 조직의 외부 사용자(페더리화), 게스트 및 익명 사용자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-132">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="ca77e-133">**조직 및 페더리드 조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="ca77e-133">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="ca77e-134">게스트 사용자 및 신뢰할 수 있는 조직의 사용자를 포함하여 조직 내의 인증된 사용자는 로비에서 대기하지 않고 직접 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-134">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="ca77e-135">익명 사용자는 로비에서 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-135">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="ca77e-136">**조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="ca77e-136">**Everyone in your organization**</span></span>    |<span data-ttu-id="ca77e-137">게스트 사용자를 포함하여 조직 내에서 인증된 사용자가 로비에서 대기하지 않고 직접 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-137">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="ca77e-138">신뢰할 수 있는 조직의 사용자 및 익명 사용자들이 로비에서 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-138">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="ca77e-139">기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-139">This is the default setting.</span></span>           |
|<span data-ttu-id="ca77e-140">**이끌이만 해당**</span><span class="sxs-lookup"><span data-stu-id="ca77e-140">**Organizer only**</span></span>    |<span data-ttu-id="ca77e-141">로비에서 대기하지 않고 모임 이끌이만 모임에 직접 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-141">Only meeting organizers can join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="ca77e-142">조직 내의 인증된 사용자, 게스트 사용자, 신뢰할 수 있는 조직의 사용자 및 익명 사용자를 비롯한 다른 모든 사용자는 로비에서 대기해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-142">Everyone else, including authenticated users within the organization, guest users, users from trusted organizations and anonymous users must wait in the lobby.</span></span>           |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="ca77e-143">전화 접속 사용자가 로비를 우회할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="ca77e-143">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="ca77e-144">구성자당 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-144">This is a per-organizer policy.</span></span> <span data-ttu-id="ca77e-145">이 설정은 전화로 전화로 전화 접속하는 사람이 모임에 직접 참가할지 아니면 자동으로 사용자 설정에 관계 없이 로비에서 대기하는지 여부를 **제어합니다.**</span><span class="sxs-lookup"><span data-stu-id="ca77e-145">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="ca77e-146">기본적으로 이 설정은 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-146">By default, this setting is turned off.</span></span> <span data-ttu-id="ca77e-147">이 설정을 해제하면 조직 사용자가 Teams 클라이언트로 모임에 참가하고 이를 인정할 때까지 전화 접속 사용자는 로비에서 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-147">When this setting is turned off, dial-in users will wait in the lobby until an organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="ca77e-148">이 설정이 설정되어 있는 경우 전화 접속 사용자는 조직 사용자가 모임에 참가할 때 자동으로 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-148">When this setting is turned on, dial-in users will automatically join the meeting when an organization user joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="ca77e-149">조직 사용자가 모임에 참가하기 전에 모임에 참가하는 경우 조직 사용자가 Teams 클라이언트를 사용하여 모임에 참가하고 해당 모임을 인정할 때까지 로비에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-149">If a dial-in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span> <span data-ttu-id="ca77e-150">모든 사용자에 대한 기본 설정을 변경하면 해당 사용자가 구성한 모든 새 모임 및 사용자가 모임 옵션을 수정하지 않은 이전 모임에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-150">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>

## <a name="enable-live-captions"></a><span data-ttu-id="ca77e-151">라이브 캡션 사용</span><span class="sxs-lookup"><span data-stu-id="ca77e-151">Enable live captions</span></span>

<span data-ttu-id="ca77e-152">이 설정은 사용자당 정책으로 모임 중에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-152">This setting is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="ca77e-153">이 설정은 사용자가  참석하는 모임에서 라이브 캡션을 켜고 끄는 데 사용할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-153">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![라이브 캡션 켜기 옵션을 보여주는 스크린샷](media/meeting-policies-live-captions.png)

|<span data-ttu-id="ca77e-155">값 설정</span><span class="sxs-lookup"><span data-stu-id="ca77e-155">Setting value</span></span> |<span data-ttu-id="ca77e-156">동작</span><span class="sxs-lookup"><span data-stu-id="ca77e-156">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="ca77e-157">**사용 안 했지만 사용자가 을재지할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="ca77e-157">**Disabled but the user can override**</span></span>     | <span data-ttu-id="ca77e-158">모임 중에 사용자에 대해 라이브 캡션이 자동으로 켜져 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-158">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="ca77e-159">사용자는 오버플로(...**)** 메뉴에서 라이브 캡션 켜기 옵션을 보고 해당 캡션을 켜는 옵션을 볼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="ca77e-159">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="ca77e-160">기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-160">This is the default setting.</span></span> |
|<span data-ttu-id="ca77e-161">**사용하지 않도록 설정**</span><span class="sxs-lookup"><span data-stu-id="ca77e-161">**Disabled**</span></span>     | <span data-ttu-id="ca77e-162">모임 중에 사용자에 대해 라이브 캡션을 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-162">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="ca77e-163">사용자에게 설정하는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-163">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="ca77e-164"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="ca77e-164"><a name="bkcontentsharing"> </a></span></span>

## <a name="allow-chat-in-meetings"></a><span data-ttu-id="ca77e-165">모임에서 채팅 허용</span><span class="sxs-lookup"><span data-stu-id="ca77e-165">Allow chat in meetings</span></span>

<span data-ttu-id="ca77e-166">이 설정은 참가자당 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-166">This setting is a per-participant setting.</span></span> <span data-ttu-id="ca77e-167">이 설정은 사용자의 모임에서 모임 채팅이 허용되는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77e-167">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="ca77e-168"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="ca77e-168"><a name="bkparticipantsandguests"> </a></span></span>






## <a name="related-topics"></a><span data-ttu-id="ca77e-169">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ca77e-169">Related topics</span></span>

- [<span data-ttu-id="ca77e-170">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="ca77e-170">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="ca77e-171">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="ca77e-171">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="ca77e-172">사용자로부터 RestrictedAnonymousAccesss Teams 모임 정책 제거</span><span class="sxs-lookup"><span data-stu-id="ca77e-172">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
