---
title: 팀 클라이언트 환경 및 공존 모드 준수
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: 팀 클라이언트 환경 및 comformance 공존 모드
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9e5e637fc8be92f136d05a3e7f41628d61afce70
ms.sourcegitcommit: bb8577aca8c7e0673b37634a24bf793c86c0537b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/29/2019
ms.locfileid: "36675396"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="9f4e8-103">팀 클라이언트 환경 및 공존 모드 준수</span><span class="sxs-lookup"><span data-stu-id="9f4e8-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="9f4e8-104">이 페이지에서는 사용자가 비즈니스용 Skype 공존 모드 (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)에 있는 경우 팀 클라이언트의 동작에서 최근에 발표 된 중요 한 변경 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="9f4e8-105">비즈니스용 skype 공존 모드 (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)는 조직의 비즈니스용 Skype에서 팀으로 전환 하는 등 최종 사용자에 게 예측 가능한 간단한 환경을 제공 하는 데 목적이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-105">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="9f4e8-106">팀으로 이동 하는 조직의 경우 모든 사용자에 게 **팀 전용** (또는 다른 모드)을 동시에 배정할 필요가 없지만 **팀 전용** 모드는 각 사용자의 최종 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-106">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="9f4e8-107">사용자가 **팀** 의 유일한 모드에 도달 하기 전에, 조직에서 비즈니스용 Skype 공존 모드를 사용 하 여 다른 사용자와 현재 사용 하지 않는 사람 간의 예측 가능한 의사 소통을 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren’t yet.</span></span> 

<span data-ttu-id="9f4e8-108">사용자가 비즈니스용 Skype 모드에 있는 경우 모든 수신 채팅 및 통화는 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="9f4e8-109">사용자가 비즈니스용 Skype 모드에 있는 경우 최종 사용자의 혼란을 방지 하 고 팀 클라이언트의 통화 및 채팅 기능을 사용할 수 없도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="9f4e8-110">마찬가지로 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있고 사용자가 SfBWithTeamsCollabAndMeetings 모드일 때 명시적으로 사용 하도록 설정 되어 있는 경우 팀에서 모임 예약을 명시적으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="9f4e8-111">현재 상태는 채팅 및 통화를 통해 연결 가능성을 나타내는 것 이므로, 채팅 및 통화를 사용 하지 않도록 설정한 경우 팀의 자체 현재 상태 (즉, 사용자의 사진에 있는 팀 클라이언트에 게 표시 되는 항목)도 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-111">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one’s own presence in the Teams client in the user’s picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="9f4e8-112">팀 클라이언트에서 사용 가능한 기능이 모드에 따라 변경 되는 방식</span><span class="sxs-lookup"><span data-stu-id="9f4e8-112">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="9f4e8-113">팀에서 사용할 수 있는 기능은 TeamsUpgradePolicy에서 설정한 사용자의 공존 모드에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-113">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="9f4e8-114">다음 표에서는 이러한 동작에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-114">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="9f4e8-115">사용자의 유효 모드</span><span class="sxs-lookup"><span data-stu-id="9f4e8-115">User's effective mode</span></span>|<span data-ttu-id="9f4e8-116">팀 클라이언트의 환경</span><span class="sxs-lookup"><span data-stu-id="9f4e8-116">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="9f4e8-117">모든 비즈니스용 Skype 모드</span><span class="sxs-lookup"><span data-stu-id="9f4e8-117">Any Skype for Business mode</span></span>|<span data-ttu-id="9f4e8-118">통화, 채팅, 자체 현재 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-118">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="9f4e8-119">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="9f4e8-119">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="9f4e8-120">모임 예약을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-120">Meeting scheduling is available</span></span>|
|<span data-ttu-id="9f4e8-121">SfBWithTeamsCollab 또는 SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9f4e8-121">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="9f4e8-122">모임 예약을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-122">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="9f4e8-123">다음 스크린샷은 **팀 전용** 또는 **아일랜드** 모드와 다른 모드의 차이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-123">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="9f4e8-124">채팅 및 통화 아이콘은 기본적으로 **팀 전용** 또는 **아일랜드** 모드 (왼쪽 스크린샷)와 함께 사용할 수 있으며 다른 모드는 그렇지 않습니다 (오른쪽 스크린샷).</span><span class="sxs-lookup"><span data-stu-id="9f4e8-124">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![팀 모드의 병렬 비교](media/teams-mode-comparison.png)

<span data-ttu-id="9f4e8-126">또한 다음과 같이 다른 모드에서는 자체 현재 상태를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-126">In addition, self presence is not available in the other modes, as shown here.</span></span>

![모임에서의 자체 현재 상태에 대 한 스크린샷 먼저](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="9f4e8-128">**참고:**
<sup></sup> 이번에는 SfBwithTeamsCollab 및 SfBOnly가 동일 하 게 작동 하지만 팀에서 채널 및 파일 기능을 사용 하지 않도록 설정 하는 것도 SfBOnly 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-128">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="9f4e8-129">중간에는 앱 사용 권한 정책을 사용 하 여 채널을 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-129">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="9f4e8-130">다른 정책 설정에 대 한 모드의 영향</span><span class="sxs-lookup"><span data-stu-id="9f4e8-130">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="9f4e8-131">위에서 설명한 대로 사용자의 공존 모드 영향에 따라 사용자의 팀 클라이언트에서 사용할 수 있는 기능이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-131">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="9f4e8-132">즉, mode에 따라 mode의 값이 다른 정책 설정의 값 보다 우선 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-132">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="9f4e8-133">특히 공존 모드는 다음 정책 설정이 허용 되는지 여부에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-133">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="9f4e8-134">**모달 (앱)**</span><span class="sxs-lookup"><span data-stu-id="9f4e8-134">**Modality (App)**</span></span>|<span data-ttu-id="9f4e8-135">**정책. 설정**</span><span class="sxs-lookup"><span data-stu-id="9f4e8-135">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="9f4e8-136">채트</span><span class="sxs-lookup"><span data-stu-id="9f4e8-136">Chat</span></span>|<span data-ttu-id="9f4e8-137">TeamsMessagingPolicy. AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="9f4e8-137">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="9f4e8-138">전화</span><span class="sxs-lookup"><span data-stu-id="9f4e8-138">Calling</span></span>|<span data-ttu-id="9f4e8-139">TeamsCallingPolicy. AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="9f4e8-139">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="9f4e8-140">모임 예약</span><span class="sxs-lookup"><span data-stu-id="9f4e8-140">Meeting scheduling</span></span>|<span data-ttu-id="9f4e8-141">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="9f4e8-141">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="9f4e8-142">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="9f4e8-142">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="9f4e8-143">공동 존재 \*\* 모드를 사용 하는 경우 관리자는 이러한 정책 설정을 명시적으로 설정할 필요가 없지만, 이러한 설정은 지정 된 모드에서 다음과 같이 효과적으로 동작 한다는 것을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-143">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="9f4e8-144">모드</span><span class="sxs-lookup"><span data-stu-id="9f4e8-144">Mode</span></span>|<span data-ttu-id="9f4e8-145">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="9f4e8-145">AllowUserChat</span></span>|<span data-ttu-id="9f4e8-146">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="9f4e8-146">AllowPrivateCalling</span></span>|<span data-ttu-id="9f4e8-147">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="9f4e8-147">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="9f4e8-148">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="9f4e8-148">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="9f4e8-149">TeamsOnly 또는 군도</span><span class="sxs-lookup"><span data-stu-id="9f4e8-149">TeamsOnly or Islands</span></span>|<span data-ttu-id="9f4e8-150">수</span><span class="sxs-lookup"><span data-stu-id="9f4e8-150">Enabled</span></span>|<span data-ttu-id="9f4e8-151">수</span><span class="sxs-lookup"><span data-stu-id="9f4e8-151">Enabled</span></span>|<span data-ttu-id="9f4e8-152">수</span><span class="sxs-lookup"><span data-stu-id="9f4e8-152">Enabled</span></span>|<span data-ttu-id="9f4e8-153">수</span><span class="sxs-lookup"><span data-stu-id="9f4e8-153">Enabled</span></span>|
|<span data-ttu-id="9f4e8-154">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="9f4e8-154">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="9f4e8-155">비활성화</span><span class="sxs-lookup"><span data-stu-id="9f4e8-155">Disabled</span></span>|<span data-ttu-id="9f4e8-156">비활성화</span><span class="sxs-lookup"><span data-stu-id="9f4e8-156">Disabled</span></span>|<span data-ttu-id="9f4e8-157">수</span><span class="sxs-lookup"><span data-stu-id="9f4e8-157">Enabled</span></span>|<span data-ttu-id="9f4e8-158">수</span><span class="sxs-lookup"><span data-stu-id="9f4e8-158">Enabled</span></span>|
|<span data-ttu-id="9f4e8-159">SfBWithTeamsCollab 또는 SfBOnly</span><span class="sxs-lookup"><span data-stu-id="9f4e8-159">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="9f4e8-160">비활성화</span><span class="sxs-lookup"><span data-stu-id="9f4e8-160">Disabled</span></span>|<span data-ttu-id="9f4e8-161">비활성화</span><span class="sxs-lookup"><span data-stu-id="9f4e8-161">Disabled</span></span>|<span data-ttu-id="9f4e8-162">비활성화</span><span class="sxs-lookup"><span data-stu-id="9f4e8-162">Disabled</span></span>|<span data-ttu-id="9f4e8-163">비활성화</span><span class="sxs-lookup"><span data-stu-id="9f4e8-163">Disabled</span></span>|
||||||

<span data-ttu-id="9f4e8-164">PowerShell을 사용 하는 `Grant-CsTeamsUpgradePolicy` 경우 Cmdlet은 TeamsMessagingPolicy, Teamsmessagingpolicy 및 TeamsMeetingPolicy에서 해당 설정의 구성을 확인 하 여 해당 설정이 TeamsUpgradePolicy로 대체 되는지 여부를 결정 합니다. 알림 메시지는 PowerShell에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-164">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="9f4e8-165">위에서 설명한 것 처럼 더 이상 다른 정책 설정을 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-165">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="9f4e8-166">다음은 PowerShell 경고의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="9f4e8-166">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="9f4e8-167">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9f4e8-167">Related topics</span></span>

[<span data-ttu-id="9f4e8-168">비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침</span><span class="sxs-lookup"><span data-stu-id="9f4e8-168">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




