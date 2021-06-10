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
description: 참가자 및 게스트의 모임 정책 설정을 Teams 자세히 알아보고
ms.openlocfilehash: bec3f82c66984147f109dc68cc97376c502dd9a6
ms.sourcegitcommit: f5b6a0fe055e42e06eee21ce311813b5127474ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52741057"
---
# <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="09d94-103">모임 정책 설정 - 참가자 및 게스트</span><span class="sxs-lookup"><span data-stu-id="09d94-103">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="09d94-104"><a name="bkmeetingparticipants"> </a></span><span class="sxs-lookup"><span data-stu-id="09d94-104"><a name="bkmeetingparticipants"> </a></span></span>

<span data-ttu-id="09d94-105">이러한 설정은 참가자가 대기실에서 대기한 후에 모임 입장이 허락되는 모임과 모임에서 참가자에게 허용되는 참여 수준을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-105">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="09d94-106">익명 사용자의 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="09d94-106">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="09d94-107">자동으로 사용자 입장</span><span class="sxs-lookup"><span data-stu-id="09d94-107">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="09d94-108">전화 접속 사용자의 대기실 우회 허용</span><span class="sxs-lookup"><span data-stu-id="09d94-108">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="09d94-109">라이브 캡션 사용</span><span class="sxs-lookup"><span data-stu-id="09d94-109">Enable live captions</span></span>](#enable-live-captions)
- [<span data-ttu-id="09d94-110">모임에서 채팅 허용</span><span class="sxs-lookup"><span data-stu-id="09d94-110">Allow chat in meetings</span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="09d94-111">모임 참가 옵션은 각 Teams 그룹의 설정 및 연결 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-111">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="09d94-112">그룹에 오디오 회의 옵션이 있고 해당 옵션을 사용하여 연결하는 경우 [오디오 회의](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09d94-112">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="09d94-113">Teams 그룹에 오디오 회의 옵션이 없는 경우 [Teams에서 모임 참가](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09d94-113">If your Teams group doesn't have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

## <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="09d94-114">익명 사용자의 모임 시작 허용</span><span class="sxs-lookup"><span data-stu-id="09d94-114">Let anonymous people start a meeting</span></span>

<span data-ttu-id="09d94-115">이 설정은 지시자가 없는 전화 접속 회의 모임을 허용하는 조직자당 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-115">This setting is a per-organizer policy that allows for leaderless dial-in conferencing meetings.</span></span> <span data-ttu-id="09d94-116">이 설정은 전화 접속 사용자가 조직의 인증된 사용자가 참석하지 않고 모임에 참가할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-116">This setting controls whether dial-in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="09d94-117">기본적으로 이 설정은 해제되어 전화 접속 사용자가 조직의 인증된 사용자가 모임에 참가할 때까지 로비에서 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-117">By default, this setting is turned off, which means dial-in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="09d94-118">이 설정을 해제하고 전화 접속 사용자가 모임에 먼저 참가하고 로비에 배치되는 경우 조직 사용자는 로비에서 사용자를 Teams 클라이언트와 모임에 참가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-118">If this setting is turned off and a dial-in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="09d94-119">전화 접속 사용자는 대기실 컨트롤을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-119">There are no lobby controls available for dialed in users.</span></span>

## <a name="automatically-admit-people"></a><span data-ttu-id="09d94-120">자동으로 사용자 입장</span><span class="sxs-lookup"><span data-stu-id="09d94-120">Automatically admit people</span></span>

<span data-ttu-id="09d94-121">이 설정은 이끌이별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-121">This is a per-organizer policy.</span></span> <span data-ttu-id="09d94-122">이 설정으로 사용자가 바로 모임에 참가할지 아니면 인증된 사용자의 인정을 받을 때까지 대기실에서 대기하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-122">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="09d94-123">이 설정은 전화 접속 사용자에게는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-123">This setting does not apply to dial-in users.</span></span>

![사용자가 대기실에 있는 모임을 보여주는 스크린샷](media/meeting-policies-lobby.png)

 <span data-ttu-id="09d94-125">모임 이끌이는  모임 초대에서 모임 옵션을 클릭하여 예약한 각 모임에 대해 이 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-125">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="09d94-p105">모임 옵션에서 설정에는 "대기실을 무시할 수 있는 사용자"라는 레이블이 지정됩니다. 아무 사용자에 대해서든 기본 설정을 변경하는 경우 해당 사용자가 이끄는 모든 새 모임 및 사용자가 모임 옵션을 수정하지 않은 이전 모임에 변경된 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-p105">In the meeting options the setting is labeled "Who can bypass the lobby". If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>
  
|<span data-ttu-id="09d94-128">설정값</span><span class="sxs-lookup"><span data-stu-id="09d94-128">Setting value</span></span>  |<span data-ttu-id="09d94-129">참가 동작</span><span class="sxs-lookup"><span data-stu-id="09d94-129">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="09d94-130">**모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="09d94-130">**Everyone**</span></span>   |<span data-ttu-id="09d94-131">모든 모임 참가자가 대기실에서 기다리지 않고 바로 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-131">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="09d94-132">여기에는 인증된 사용자, 신뢰할 수 있는 조직의 외부 사용자(페더레이션), 게스트 및 익명 사용자도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-132">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="09d94-133">**내 조직의 사용자 및 게스트**</span><span class="sxs-lookup"><span data-stu-id="09d94-133">**People in my organization and guests**</span></span>     |<span data-ttu-id="09d94-134">게스트 사용자를 포함하여 조직 내에서 인증된 사용자는 로비에서 대기하지 않고 직접 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-134">Authenticated users within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="09d94-135">익명 사용자는 대기실에서 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-135">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="09d94-136">**내 조직의 사용자, 신뢰할 수 있는 조직 및 게스트**</span><span class="sxs-lookup"><span data-stu-id="09d94-136">**People in my organization, trusted organizations, and guests**</span></span>     |<span data-ttu-id="09d94-137">게스트 사용자 및 신뢰할 수 있는 조직의 사용자를 포함하여 조직 내 인증된 사용자는 대기실에서 기다리지 않고 바로 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-137">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="09d94-138">익명 사용자는 대기실에서 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-138">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="09d94-139">**내 조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="09d94-139">**Everyone in my organization**</span></span>    |<span data-ttu-id="09d94-140">게스트 사용자를 포함하여 조직 내의 인증된 사용자는 대기실에서 기다리지 않고 바로 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-140">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="09d94-141">신뢰할 수 있는 조직의 사용자와 익명 사용자는 대기실에서 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-141">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="09d94-142">기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-142">This is the default setting.</span></span>           |
|<span data-ttu-id="09d94-143">**모임 이끌이만**</span><span class="sxs-lookup"><span data-stu-id="09d94-143">**Organizer only**</span></span>    |<span data-ttu-id="09d94-144">모임 이끌이만 대기실에서 기다리지 않고 바로 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-144">Only meeting organizers can join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="09d94-145">조직 내의 인증된 사용자, 게스트 사용자, 신뢰할 수 있는 조직의 사용자 및 익명 사용자를 포함하여 다른 모든 사용자는 로비에서 대기해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-145">Everyone else, including authenticated users within the organization, guest users, users from trusted organizations, and anonymous users must wait in the lobby.</span></span>           |
|<span data-ttu-id="09d94-146">**초대된 사용자만**</span><span class="sxs-lookup"><span data-stu-id="09d94-146">**Invited users only**</span></span>    |<span data-ttu-id="09d94-147">초대된 사용자 및 모임 이끌이만 로비에서 대기하지 않고 직접 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-147">Only invited users and meeting organizers can join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="09d94-148">조직 내의 인증된 사용자, 게스트 사용자, 신뢰할 수 있는 조직의 사용자 및 익명 사용자를 포함하여 다른 모든 사용자는 로비에서 대기해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-148">Everyone else, including authenticated users within the organization, guest users, users from trusted organizations, and anonymous users must wait in the lobby.</span></span>           |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="09d94-149">전화 접속 사용자의 대기실 우회 허용</span><span class="sxs-lookup"><span data-stu-id="09d94-149">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="09d94-150">이 설정은 이끌이별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-150">This is a per-organizer policy.</span></span> <span data-ttu-id="09d94-151">이 설정으로 전화 접속한 참가자가 **자동으로 사용자 입장** 설정과 관계없이 바로 모임에 참가할지 아니면 대기실에서 기다릴지를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-151">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="09d94-152">기본적으로 이 설정은 꺼져 잇습니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-152">By default, this setting is turned off.</span></span> <span data-ttu-id="09d94-153">이 설정을 끄면 전화 접속 사용자는 조직 사용자가 Teams 클라이언트에서 모임에 참가하여 입장을 허락할 때까지 대기실에서 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-153">When this setting is turned off, dial-in users will wait in the lobby until an organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="09d94-154">이 설정이 켜져 있는 경우 전화 접속 사용자는 조직 사용자가 모임에 참가할 때 자동으로 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-154">When this setting is turned on, dial-in users will automatically join the meeting when an organization user joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="09d94-155">조직 사용자가 모임에 참가하기 전에 전화 접속 사용자가 모임에 참가하는 경우 조직 사용자가 Teams 클라이언트를 사용하여 모임에 참가한 다음 해당 전화 접속 사용자를 인정할 때까지 대기실에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-155">If a dial-in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span> <span data-ttu-id="09d94-156">아무 사용자에 대해서든 기본 설정을 변경하는 경우 해당 사용자가 이끄는 모든 새 모임 및 사용자가 모임 옵션을 수정하지 않은 이전 모임에 변경된 설정이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-156">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>

## <a name="enable-live-captions"></a><span data-ttu-id="09d94-157">라이브 캡션 사용</span><span class="sxs-lookup"><span data-stu-id="09d94-157">Enable live captions</span></span>

<span data-ttu-id="09d94-158">이 설정은 사용자당 정책으로 모임 중에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-158">This setting is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="09d94-159">이 설정으로 사용자가 참석하는 모임에서 사용자가 라이브 캡션을 설정 및 해제하는 데 **라이브 캡션 켜기** 옵션을 사용할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-159">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![라이브 캡션 켜기 옵션을 보여주는 스크린샷](media/meeting-policies-live-captions.png)

|<span data-ttu-id="09d94-161">설정값</span><span class="sxs-lookup"><span data-stu-id="09d94-161">Setting value</span></span> |<span data-ttu-id="09d94-162">동작</span><span class="sxs-lookup"><span data-stu-id="09d94-162">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="09d94-163">**사용하지 않도록 설정되었지만 사용자 재정의 가능**</span><span class="sxs-lookup"><span data-stu-id="09d94-163">**Disabled but the user can override**</span></span>     | <span data-ttu-id="09d94-164">라이브 캡션 기능은 모임 중인 사용자에 대해 자동으로 설정되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-164">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="09d94-165">사용자가 기능을 켜도록 넘침 단추(**...**) 메뉴에서 **라이브 캡션 켜기** 옵션이 보입니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-165">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="09d94-166">기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-166">This is the default setting.</span></span> |
|<span data-ttu-id="09d94-167">**사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="09d94-167">**Disabled**</span></span>     | <span data-ttu-id="09d94-168">라이브 캡션 기능이 모임 중인 사용자에 대해 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-168">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="09d94-169">사용자에게 이 기능을 켜는 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-169">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="09d94-170"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="09d94-170"><a name="bkcontentsharing"> </a></span></span>

## <a name="allow-chat-in-meetings"></a><span data-ttu-id="09d94-171">모임에서 채팅 허용</span><span class="sxs-lookup"><span data-stu-id="09d94-171">Allow chat in meetings</span></span>

<span data-ttu-id="09d94-172">이 설정은 참가자당 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-172">This setting is a per-participant setting.</span></span> <span data-ttu-id="09d94-173">이 설정으로 사용자 모임에서 모임 채팅을 허용할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="09d94-173">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="09d94-174"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="09d94-174"><a name="bkparticipantsandguests"> </a></span></span>






## <a name="related-topics"></a><span data-ttu-id="09d94-175">관련 항목</span><span class="sxs-lookup"><span data-stu-id="09d94-175">Related topics</span></span>

- [<span data-ttu-id="09d94-176">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="09d94-176">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="09d94-177">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="09d94-177">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="09d94-178">사용자의 RestrictedAnonymousAccess Teams 모임 정책 삭제</span><span class="sxs-lookup"><span data-stu-id="09d94-178">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
