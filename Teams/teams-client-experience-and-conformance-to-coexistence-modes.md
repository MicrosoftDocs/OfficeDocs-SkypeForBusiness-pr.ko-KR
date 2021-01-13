---
title: Teams 클라이언트 환경 및 공존 모드 준수
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Teams 클라이언트 환경 및 공존 모드(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)에 대한 준수에 대해 자세히 배워야 합니다.
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
ms.openlocfilehash: 20d1ff52fa59f31b796d2580a0e2819c80caaf42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821028"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="997d9-103">Teams 클라이언트 환경 및 공존 모드 준수</span><span class="sxs-lookup"><span data-stu-id="997d9-103">Teams client experience and conformance to coexistence modes</span></span>

<a name="about-upgrade-basic"></a>

<span data-ttu-id="997d9-104">비즈니스용 Skype 공존 모드(SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)의 목적은 조직이 비즈니스용 Skype에서 Teams로 전환할 때 최종 사용자에게 간단하고 예측 가능한 환경을 제공하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-104">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="997d9-105">Teams로 전환하는 조직의 경우 **Teams** 전용 모드는 각 사용자에 대한 최종 대상이지만, 모든 사용자에게 **Teams만(또는** 다른 모드)을 동시에 할당해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-105">For an organization moving to Teams, the **Teams Only** mode is the final destination for each user, though not all users need to be assigned **Teams Only** (or any other mode) at the same time.</span></span>  <span data-ttu-id="997d9-106">사용자가 TeamsOnly 모드에 도달하기 전에 조직은 비즈니스용 Skype 공존 모드를 사용하여 **Teams** 전용 사용자와 아직 그렇지 않은 사용자 간에 예측 가능한 통신을 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-106">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business coexistence modes to ensure predictable communication between users who are **Teams Only** and those who aren't yet.</span></span> 

<span data-ttu-id="997d9-107">사용자가 비즈니스용 Skype 모드에 있는 경우 들어오는 모든 채팅 및 통화가 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-107">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="997d9-108">최종 사용자 혼동을 방지하고 적절한 라우팅을 보장하기 위해 사용자가 비즈니스용 Skype 모드에 있는 경우 Teams 클라이언트의 통화 및 채팅 기능이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-108">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="997d9-109">마찬가지로 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있는 경우 Teams의 모임 예정이 명시적으로 비활성화되어 사용자가 SfBWithTeamsCollabAndMeetings 모드에 있는 경우 명시적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-109">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="997d9-110">현재 상태는 채팅 및 통화를 통한 연결 가능성의 표시이기 때문에 채팅 및 통화가 비활성화된 경우 Teams의 셀프 에디스(즉, 사용자의 사진에서 Teams 클라이언트에 자신의 현재 상태 표시)도 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-110">Because presence is an indication of reachability through chat and calling, when chat and calling are disabled, self-presence in Teams (that is, the display of one's own presence in the Teams client in the user's picture) is also hidden.</span></span> 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="997d9-111">Teams 클라이언트에서 사용 가능한 기능이 모드에 따라 변경하는 방식</span><span class="sxs-lookup"><span data-stu-id="997d9-111">How the available functionality in Teams client changes based on mode</span></span>

<span data-ttu-id="997d9-112">Teams에서 사용 가능한 기능은 TeamsUpgradePolicy에서 설정한 사용자의 공존 모드에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="997d9-113">다음 표에서는 동작을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-113">The following table summarizes the behavior:</span></span>

|<span data-ttu-id="997d9-114">사용자의 유효 모드</span><span class="sxs-lookup"><span data-stu-id="997d9-114">User's effective mode</span></span>|<span data-ttu-id="997d9-115">Teams 클라이언트의 환경</span><span class="sxs-lookup"><span data-stu-id="997d9-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="997d9-116">비즈니스용 Skype 모드</span><span class="sxs-lookup"><span data-stu-id="997d9-116">Any Skype for Business mode</span></span>|<span data-ttu-id="997d9-117">통화, 채팅 및 셀프 현재 상태는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-117">Calling, Chat, and self-presence are disabled.</span></span>|
|<span data-ttu-id="997d9-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="997d9-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="997d9-119">모임을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="997d9-120">SfBWithTeamsCollab 또는 SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="997d9-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="997d9-121">모임을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="997d9-122">다음 스크린샷은 Teams **전용** 모드  또는 제도 모드와 다른 모든 모드 간의 차이점을 보여 주는 스크린샷입니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-122">The following screenshots illustrate the difference between **Teams Only** or **Islands** mode and all other modes.</span></span> <span data-ttu-id="997d9-123">채팅 및 통화 아이콘은 **Teams 전용** 또는 제도  모드(왼쪽 스크린샷)에서 기본적으로 사용할 수 있지만 다른 모드(오른쪽 스크린샷)와는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-123">Note that the chat and calling icons are available by default with **Teams Only** or **Islands** mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![Teams 모드의 나란히 비교](media/teams-mode-comparison.png)

<span data-ttu-id="997d9-125">또한 다음과 같이 다른 모드에서는 셀프 존재를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-125">In addition, self presence is not available in the other modes, as shown here.</span></span>

![모임 우선의 셀프 에세이트 스크린샷](media/meetings-first-no-self-presence-general.png)
 
<span data-ttu-id="997d9-127">**참고:** 
 <sup>1</sup> 현재 SfBwithTeamsCollab 및 SfBOnly는 동일하게 사용되지만, SfBOnly 모드가 Teams에서 채널 및 파일 기능을 사용하지 않도록 설정하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-127">**Note:**
<sup>1</sup> At this time, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams.</span></span> <span data-ttu-id="997d9-128">중간에 앱 사용 권한 정책을 사용하여 채널을 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-128">In the interim, Channels can be hidden using the App Permissions policy.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="997d9-129">모드가 다른 정책 설정에 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="997d9-129">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="997d9-130">위에서 설명한 대로 사용자의 공존 모드는 사용자의 Teams 클라이언트에서 사용할 수 있는 기능에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-130">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="997d9-131">즉 모드 값이 모드에 따라 다른 정책 설정 값보다 우선적으로 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-131">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="997d9-132">특히 공존 모드는 다음 정책 설정을 적용하는지 여부에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-132">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="997d9-133">**Modality(앱)**</span><span class="sxs-lookup"><span data-stu-id="997d9-133">**Modality (App)**</span></span>|<span data-ttu-id="997d9-134">**Policy.Setting**</span><span class="sxs-lookup"><span data-stu-id="997d9-134">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="997d9-135">채팅</span><span class="sxs-lookup"><span data-stu-id="997d9-135">Chat</span></span>|<span data-ttu-id="997d9-136">TeamsMessagingPolicy.AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="997d9-136">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="997d9-137">통화</span><span class="sxs-lookup"><span data-stu-id="997d9-137">Calling</span></span>|<span data-ttu-id="997d9-138">TeamsCallingPolicy.AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="997d9-138">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="997d9-139">모임일정</span><span class="sxs-lookup"><span data-stu-id="997d9-139">Meeting scheduling</span></span>|<span data-ttu-id="997d9-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="997d9-140">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="997d9-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="997d9-141">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="997d9-142">관리자는 공생 모드를 사용할 때 이러한 정책 설정을 명시적으로 설정할 필요가 없지만, 이러한 설정이 주어진 모드에 대해 다음과 같이 효과적으로 행동한다는 것을 이해하는 것이 중요합니다. </span><span class="sxs-lookup"><span data-stu-id="997d9-142">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="997d9-143">모드</span><span class="sxs-lookup"><span data-stu-id="997d9-143">Mode</span></span>|<span data-ttu-id="997d9-144">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="997d9-144">AllowUserChat</span></span>|<span data-ttu-id="997d9-145">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="997d9-145">AllowPrivateCalling</span></span>|<span data-ttu-id="997d9-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="997d9-146">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="997d9-147">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="997d9-147">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="997d9-148">TeamsOnly 또는 Islands</span><span class="sxs-lookup"><span data-stu-id="997d9-148">TeamsOnly or Islands</span></span>|<span data-ttu-id="997d9-149">사용</span><span class="sxs-lookup"><span data-stu-id="997d9-149">Enabled</span></span>|<span data-ttu-id="997d9-150">사용</span><span class="sxs-lookup"><span data-stu-id="997d9-150">Enabled</span></span>|<span data-ttu-id="997d9-151">사용</span><span class="sxs-lookup"><span data-stu-id="997d9-151">Enabled</span></span>|<span data-ttu-id="997d9-152">사용</span><span class="sxs-lookup"><span data-stu-id="997d9-152">Enabled</span></span>|
|<span data-ttu-id="997d9-153">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="997d9-153">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="997d9-154">사용 안</span><span class="sxs-lookup"><span data-stu-id="997d9-154">Disabled</span></span>|<span data-ttu-id="997d9-155">사용 안</span><span class="sxs-lookup"><span data-stu-id="997d9-155">Disabled</span></span>|<span data-ttu-id="997d9-156">사용</span><span class="sxs-lookup"><span data-stu-id="997d9-156">Enabled</span></span>|<span data-ttu-id="997d9-157">사용</span><span class="sxs-lookup"><span data-stu-id="997d9-157">Enabled</span></span>|
|<span data-ttu-id="997d9-158">SfBWithTeamsCollab 또는 SfBOnly</span><span class="sxs-lookup"><span data-stu-id="997d9-158">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="997d9-159">사용 안</span><span class="sxs-lookup"><span data-stu-id="997d9-159">Disabled</span></span>|<span data-ttu-id="997d9-160">사용 안</span><span class="sxs-lookup"><span data-stu-id="997d9-160">Disabled</span></span>|<span data-ttu-id="997d9-161">사용 안</span><span class="sxs-lookup"><span data-stu-id="997d9-161">Disabled</span></span>|<span data-ttu-id="997d9-162">사용 안</span><span class="sxs-lookup"><span data-stu-id="997d9-162">Disabled</span></span>|
||||||

<span data-ttu-id="997d9-163">PowerShell을 사용하는 경우 `Grant-CsTeamsUpgradePolicy` cmdlet은 TeamsMessagingPolicy, TeamsCallingPolicy 및 TeamsMeetingPolicy에서 해당 설정의 구성을 확인하여 해당 설정을 TeamsUpgradePolicy로 대신할지 여부를 확인하고, 이 경우 PowerShell에서 정보 메시지가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-163">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superseded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="997d9-164">위에서 설명한 대로 이러한 다른 정책 설정을 더 이상 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-164">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="997d9-165">다음은 PowerShell 경고의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="997d9-165">The following is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a><span data-ttu-id="997d9-166">관련 항목</span><span class="sxs-lookup"><span data-stu-id="997d9-166">Related topics</span></span>

[<span data-ttu-id="997d9-167">비즈니스용 Skype와 함께 Teams를 사용하는 조직을 위한 마이그레이션 및 상호 연동성 지침</span><span class="sxs-lookup"><span data-stu-id="997d9-167">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




