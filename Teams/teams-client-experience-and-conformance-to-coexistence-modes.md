---
title: Teams 클라이언트 환경 및 공존 모드 준수
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: 클라이언트 Teams 및 공존 모드(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)에 대한 준수에 대해 자세히 알아보습니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e07d33b8aa1b379823ffa3aaa605dc26c31604c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119257"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="eb624-103">Teams 클라이언트 환경 및 공존 모드 준수</span><span class="sxs-lookup"><span data-stu-id="eb624-103">Teams client experience and conformance to coexistence modes</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="eb624-104">공존 비즈니스용 Skype(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)은 조직이 조직에서 비즈니스용 Skype 예측 가능한 환경을 Teams.</span><span class="sxs-lookup"><span data-stu-id="eb624-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="eb624-105">조직으로 이동하는 Teams 유일한  Teams 모드는 각 사용자에 대한 최종 대상입니다. 그러나 모든 사용자에게는 Teams(또는 다른 **모드)를** 동시에 할당해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="eb624-106">TeamsOnly 모드에 도달하기 전에 조직은 모든 비즈니스용 Skype 공존 모드를 사용하여 사용자와 아직 Teams 사용자  간에 예측 가능한 통신을 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren't yet.</span></span> 

<span data-ttu-id="eb624-107">사용자가 모든 비즈니스용 Skype 있는 경우 들어오는 모든 채팅 및 호출이 사용자의 비즈니스용 Skype 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="eb624-108">최종 사용자 혼동을 방지하고 적절한 라우팅을 보장하기 위해 사용자가 Teams 모드 중 하나에 있는 경우 클라이언트의 호출 및 채팅 비즈니스용 Skype 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="eb624-109">마찬가지로 Teams, 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있는 경우 사용자가 SfBWithTeamsCollabAndMeetings 모드에 있는 경우 명시적으로 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="eb624-110">현재 상태는 채팅 및 통화를 통해 도달성을 표시하기 때문에 채팅 및 통화를 사용하지 않도록 설정하면 Teams(즉, 사용자의 사진에서 클라이언트에 자신의 Teams 표시)도 숨겨져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one's own presence in the Teams client in the user's picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="eb624-111">클라이언트에서 사용할 수 있는 Teams 모드에 따라 변경되는 방법</span><span class="sxs-lookup"><span data-stu-id="eb624-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="eb624-112">사용 가능한 Teams TeamsUpgradePolicy에서 설정한 사용자 공존 모드에 따라 달라 갑니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="eb624-113">다음 표에서는 동작을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="eb624-114">사용자의 유효 모드</span><span class="sxs-lookup"><span data-stu-id="eb624-114">User's effective mode</span></span>|<span data-ttu-id="eb624-115">클라이언트에서 Teams 경험</span><span class="sxs-lookup"><span data-stu-id="eb624-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="eb624-116">모든 비즈니스용 Skype 모드</span><span class="sxs-lookup"><span data-stu-id="eb624-116">Any Skype for Business mode</span></span>|<span data-ttu-id="eb624-117">통화, 채팅 및 자체 상태는 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="eb624-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="eb624-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="eb624-119">모임일정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="eb624-120">SfBWithTeamsCollab 또는 SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="eb624-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="eb624-121">모임일정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="eb624-122">다음 스크린샷은 Teams **또는** 섬 모드와 다른 모든 모드의 차이점을 보여 주는 스크린샷입니다. </span><span class="sxs-lookup"><span data-stu-id="eb624-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="eb624-123">채팅 및 통화 아이콘은 기본적으로 Teams 또는 섬 모드(왼쪽  스크린샷)와 함께 사용할 수 있지만 다른 모드(오른쪽 스크린샷)에서는 사용할 수 없습니다. </span><span class="sxs-lookup"><span data-stu-id="eb624-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![모드의 나란히 비교 Teams 비교](media/teams-mode-comparison.png)

<span data-ttu-id="eb624-125">또한 여기에서와 같이 다른 모드에서는 셀프 존재를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![모임 첫 번째에서 자체 존재의 스크린샷](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="eb624-127">**참고:** 
 <sup>1</sup> 현재 SfBwithTeamsCollab과 SfBOnly는 동일하게 사용되지만 SfBOnly 모드는 SfBOnly 모드에서 채널 및 파일 기능을 사용하지 않도록 설정하기 위한 Teams.</span><span class="sxs-lookup"><span data-stu-id="eb624-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="eb624-128">중간에 앱 사용 권한 정책을 사용하여 채널을 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="eb624-129">모드가 다른 정책 설정에 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="eb624-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="eb624-130">위에서 설명한 대로 사용자의 공존 모드 영향은 사용자의 클라이언트에서 사용할 수 있는 Teams 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="eb624-131">즉, 모드 값이 모드에 따라 다른 정책 설정 값보다 우선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="eb624-132">특히 공존 모드는 다음 정책 설정을 적용하는지 여부에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="eb624-133">**모달리티(앱)**</span><span class="sxs-lookup"><span data-stu-id="eb624-133">**Modality (App)**</span></span>|<span data-ttu-id="eb624-134">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="eb624-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="eb624-135">채팅</span><span class="sxs-lookup"><span data-stu-id="eb624-135">Chat</span></span>|<span data-ttu-id="eb624-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="eb624-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="eb624-137">통화</span><span class="sxs-lookup"><span data-stu-id="eb624-137">Calling</span></span>|<span data-ttu-id="eb624-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="eb624-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="eb624-139">모임일정</span><span class="sxs-lookup"><span data-stu-id="eb624-139">Meeting scheduling</span></span>|<span data-ttu-id="eb624-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="eb624-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="eb624-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="eb624-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="eb624-142">관리자는 공생 모드를 사용할 때 이러한 정책 설정을 명시적으로 설정할 필요는 없지만, 이러한 설정이 주어진 모드에 대해 다음과 같이 효과적으로 행동한다는 것을 이해하는 것이 중요합니다. </span><span class="sxs-lookup"><span data-stu-id="eb624-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="eb624-143">모드</span><span class="sxs-lookup"><span data-stu-id="eb624-143">Mode</span></span>|<span data-ttu-id="eb624-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="eb624-144">AllowUserChat</span></span>|<span data-ttu-id="eb624-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="eb624-145">AllowPrivateCalling</span></span>|<span data-ttu-id="eb624-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="eb624-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="eb624-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="eb624-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="eb624-148">TeamsOnly 또는 Islands</span><span class="sxs-lookup"><span data-stu-id="eb624-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="eb624-149">사용 가능</span><span class="sxs-lookup"><span data-stu-id="eb624-149">Enabled</span></span>|<span data-ttu-id="eb624-150">사용 가능</span><span class="sxs-lookup"><span data-stu-id="eb624-150">Enabled</span></span>|<span data-ttu-id="eb624-151">사용 가능</span><span class="sxs-lookup"><span data-stu-id="eb624-151">Enabled</span></span>|<span data-ttu-id="eb624-152">사용 가능</span><span class="sxs-lookup"><span data-stu-id="eb624-152">Enabled</span></span>|
|<span data-ttu-id="eb624-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="eb624-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="eb624-154">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="eb624-154">Disabled</span></span>|<span data-ttu-id="eb624-155">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="eb624-155">Disabled</span></span>|<span data-ttu-id="eb624-156">사용 가능</span><span class="sxs-lookup"><span data-stu-id="eb624-156">Enabled</span></span>|<span data-ttu-id="eb624-157">사용 가능</span><span class="sxs-lookup"><span data-stu-id="eb624-157">Enabled</span></span>|
|<span data-ttu-id="eb624-158">SfBWithTeamsCollab 또는 SfBOnly</span><span class="sxs-lookup"><span data-stu-id="eb624-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="eb624-159">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="eb624-159">Disabled</span></span>|<span data-ttu-id="eb624-160">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="eb624-160">Disabled</span></span>|<span data-ttu-id="eb624-161">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="eb624-161">Disabled</span></span>|<span data-ttu-id="eb624-162">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="eb624-162">Disabled</span></span>|
||||||

<span data-ttu-id="eb624-163">PowerShell을 사용하는 경우 `Grant-CsTeamsUpgradePolicy` cmdlet은 TeamsMessagingPolicy, TeamsCallingPolicy 및 TeamsMeetingPolicy의 해당 설정의 구성을 검사하여 TeamsUpgradePolicy에서 해당 설정을 대신할지 여부를 확인하고 이 경우 PowerShell에 정보 메시지가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="eb624-164">위에서 설명한 대로 이러한 다른 정책 설정을 설정하는 데 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="eb624-165">다음은 PowerShell 경고의 모양을 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb624-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a><span data-ttu-id="eb624-166">관련 항목</span><span class="sxs-lookup"><span data-stu-id="eb624-166">Related topics</span></span>

[<span data-ttu-id="eb624-167">조직과 함께 Teams 조직에 대한 마이그레이션 및 상호 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="eb624-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)