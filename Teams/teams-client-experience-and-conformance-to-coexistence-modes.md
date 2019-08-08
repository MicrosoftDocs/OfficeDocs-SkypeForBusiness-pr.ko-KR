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
ms.openlocfilehash: 85f74b63f465bd0004e8b9a2ef93c79b00196495
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243908"
---
<a name="about-upgrade-basic"></a>

# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a><span data-ttu-id="00b7e-103">팀 클라이언트 환경 및 공존 모드 준수</span><span class="sxs-lookup"><span data-stu-id="00b7e-103">Teams client experience and conformance to coexistence modes</span></span>

> [!NOTE]
> <span data-ttu-id="00b7e-104">이 페이지에서는 사용자가 비즈니스용 Skype 모드 (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)에 있는 경우 팀 클라이언트의 동작에서 최근에 발표 된 중요 한 변경 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-104">This page describes important, recently released changes in the behavior of Teams client when users are in any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).</span></span>


<span data-ttu-id="00b7e-105">공존 모드의 용도는 조직이 비즈니스용 Skype에서 팀으로 전환 하는 것 처럼 최종 사용자에 게 예측 가능한 간단한 환경을 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-105">The purpose of co-existence modes is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span>  <span data-ttu-id="00b7e-106">팀으로 이동 하는 조직의 경우 모든 사용자에 게 동시에 Teamonly (또는 기타 모드)를 할당 해야 하는 것은 아니지만 TeamsOnly 모드는 각 사용자의 최종 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-106">For an organization moving to Teams, the TeamsOnly mode is the final destination for each user, though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>  <span data-ttu-id="00b7e-107">사용자가 팀의 유일한 모드에 도달 하기 전에, 조직에서 비즈니스용 Skype 모드 (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)를 사용 하 여 팀이 자신을 대상으로 하 고 아직 받지 않은 사용자 간에 예측 가능한 의사 소통을 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-107">Prior to users reaching TeamsOnly mode, organizations can use any of the Skype for Business modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) to ensure predictable communication between users who are TeamsOnly and those who aren’t yet.</span></span> 

<span data-ttu-id="00b7e-108">사용자가 비즈니스용 Skype 모드에 있는 경우 모든 수신 채팅 및 통화는 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-108">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user’s Skype for Business client.</span></span> <span data-ttu-id="00b7e-109">사용자가 비즈니스용 Skype 모드에 있는 경우 최종 사용자의 혼란을 방지 하 고 팀 클라이언트의 통화 및 채팅 기능을 사용할 수 없도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-109">To avoid end user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="00b7e-110">마찬가지로 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있고 사용자가 SfBWithTeamsCollabAndMeetings 모드일 때 명시적으로 사용 하도록 설정 되어 있는 경우 팀에서 모임 예약을 명시적으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-110">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>   

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a><span data-ttu-id="00b7e-111">팀 클라이언트에서 사용 가능한 기능이 모드에 따라 변경 되는 방식</span><span class="sxs-lookup"><span data-stu-id="00b7e-111">How the available functionality in Teams client changes based on mode</span></span>
<span data-ttu-id="00b7e-112">팀에서 사용할 수 있는 기능은 TeamsUpgradePolicy에서 설정한 사용자의 공존 모드에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-112">The available functionality in Teams depends on the user's coexistence mode, as set by TeamsUpgradePolicy.</span></span> <span data-ttu-id="00b7e-113">다음 표에서는 동작을 요약 하 여 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-113">The table below summarizes the  behavior:</span></span>

|<span data-ttu-id="00b7e-114">사용자의 유효 모드</span><span class="sxs-lookup"><span data-stu-id="00b7e-114">User's effective mode</span></span>|<span data-ttu-id="00b7e-115">팀 클라이언트의 환경</span><span class="sxs-lookup"><span data-stu-id="00b7e-115">Experience in Teams client</span></span>|
|---|---|
|<span data-ttu-id="00b7e-116">모든 비즈니스용 Skype 모드</span><span class="sxs-lookup"><span data-stu-id="00b7e-116">Any Skype for Business mode</span></span>|<span data-ttu-id="00b7e-117">통화 및 채팅을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-117">Calling and Chat are disabled.</span></span>|
|<span data-ttu-id="00b7e-118">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="00b7e-118">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="00b7e-119">모임 예약을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-119">Meeting scheduling is available</span></span>|
|<span data-ttu-id="00b7e-120">SfBWithTeamsCollab 또는 SfBOnly<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="00b7e-120">SfBWithTeamsCollab or SfBOnly<sup>1</sup></span></span>|<span data-ttu-id="00b7e-121">모임 예약을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-121">Meeting scheduling is not available</span></span>|
|||

<span data-ttu-id="00b7e-122">다음 스크린샷은 팀 전용 또는 아일랜드 모드와 다른 모드의 차이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-122">The following screenshots illustrate the difference between TeamsOnly or Islands mode and all other modes.</span></span> <span data-ttu-id="00b7e-123">채팅 및 통화 아이콘은 팀 전용 또는 아일랜드 모드 (왼쪽 스크린샷)와 함께 사용할 수 있지만 다른 모드 (오른쪽 스크린샷)에는 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-123">Note that the chat and calling icons are available with TeamsOnly or Islands mode (left screenshot), but not with the other modes (right screenshot):</span></span>

![팀 모드의 병렬 비교](media/teams-mode-comparison.png)


 
<span data-ttu-id="00b7e-125">**참고:**
<sup>1</sup> 이제 SfBwithTeamsCollab 및 SfBOnly는 동일 하 게 작동 하지만 SfBOnly 모드에서 팀의 채널과 Files 기능을 사용 하지 않도록 설정할 수 있습니다. 그러나 현재 팀에서이 기능을 사용 하지 않도록 설정할 수 있는 설정은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-125">**Note:**
<sup>1</sup> For now, SfBwithTeamsCollab and SfBOnly behave the same, but the intent is for SfBOnly mode to also disable Channels and Files functionality in Teams; however, there is currently no setting that allows this functionality in Teams to be disabled.</span></span>


## <a name="impact-of-mode-on-other-policy-settings"></a><span data-ttu-id="00b7e-126">다른 정책 설정에 대 한 모드의 영향</span><span class="sxs-lookup"><span data-stu-id="00b7e-126">Impact of Mode on other policy settings</span></span>
<span data-ttu-id="00b7e-127">위에서 설명한 대로 사용자의 공존 모드 영향에 따라 사용자의 팀 클라이언트에서 사용할 수 있는 기능이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-127">As described above, a user's coexistence mode impact's what functionality is available in the user's Teams client.</span></span> <span data-ttu-id="00b7e-128">즉, mode에 따라 mode의 값이 다른 정책 설정의 값 보다 우선 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-128">This means that the value of mode can take precedence over the value of other policy settings, depending on the mode.</span></span> <span data-ttu-id="00b7e-129">특히 공존 모드는 다음 정책 설정이 허용 되는지 여부에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-129">Specifically,  coexistence mode impacts whether the following policy settings are honored:</span></span>

|<span data-ttu-id="00b7e-130">**모달 (앱)**</span><span class="sxs-lookup"><span data-stu-id="00b7e-130">**Modality (App)**</span></span>|<span data-ttu-id="00b7e-131">**정책. 설정**</span><span class="sxs-lookup"><span data-stu-id="00b7e-131">**Policy.Setting**</span></span>|
|---|---|
|<span data-ttu-id="00b7e-132">채트</span><span class="sxs-lookup"><span data-stu-id="00b7e-132">Chat</span></span>|<span data-ttu-id="00b7e-133">TeamsMessagingPolicy. AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="00b7e-133">TeamsMessagingPolicy.AllowUserChat</span></span>|
|<span data-ttu-id="00b7e-134">전화</span><span class="sxs-lookup"><span data-stu-id="00b7e-134">Calling</span></span>|<span data-ttu-id="00b7e-135">TeamsCallingPolicy. AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="00b7e-135">TeamsCallingPolicy.AllowPrivateCalling</span></span>|
|<span data-ttu-id="00b7e-136">모임 예약</span><span class="sxs-lookup"><span data-stu-id="00b7e-136">Meeting scheduling</span></span>|<span data-ttu-id="00b7e-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="00b7e-137">TeamsMeetingPolicy.AllowPrivateMeetingScheduling</span></span></br><span data-ttu-id="00b7e-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="00b7e-138">TeamsMeetingPolicy.AllowChannelMeetingScheduling</span></span>|
|||

<span data-ttu-id="00b7e-139">공동 존재 \*\* 모드를 사용 하는 경우 관리자는 이러한 정책 설정을 명시적으로 설정할 필요가 없지만, 이러한 설정은 지정 된 모드에서 다음과 같이 효과적으로 동작 한다는 것을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-139">Administrators need *not* explicitly set these policy settings when using co-existence mode, but it's important to understand that these settings effectively behave as follows for a given mode.</span></span> 

|<span data-ttu-id="00b7e-140">모드</span><span class="sxs-lookup"><span data-stu-id="00b7e-140">Mode</span></span>|<span data-ttu-id="00b7e-141">AllowUserChat</span><span class="sxs-lookup"><span data-stu-id="00b7e-141">AllowUserChat</span></span>|<span data-ttu-id="00b7e-142">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="00b7e-142">AllowPrivateCalling</span></span>|<span data-ttu-id="00b7e-143">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="00b7e-143">AllowPrivateMeetingScheduling</span></span>|<span data-ttu-id="00b7e-144">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="00b7e-144">AllowChannelMeetingScheduling</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="00b7e-145">TeamsOnly 또는 군도</span><span class="sxs-lookup"><span data-stu-id="00b7e-145">TeamsOnly or Islands</span></span>|<span data-ttu-id="00b7e-146">수</span><span class="sxs-lookup"><span data-stu-id="00b7e-146">Enabled</span></span>|<span data-ttu-id="00b7e-147">수</span><span class="sxs-lookup"><span data-stu-id="00b7e-147">Enabled</span></span>|<span data-ttu-id="00b7e-148">수</span><span class="sxs-lookup"><span data-stu-id="00b7e-148">Enabled</span></span>|<span data-ttu-id="00b7e-149">수</span><span class="sxs-lookup"><span data-stu-id="00b7e-149">Enabled</span></span>|
|<span data-ttu-id="00b7e-150">SfBWithTeamsCollabAndMeetings</span><span class="sxs-lookup"><span data-stu-id="00b7e-150">SfBWithTeamsCollabAndMeetings</span></span>|<span data-ttu-id="00b7e-151">비활성화</span><span class="sxs-lookup"><span data-stu-id="00b7e-151">Disabled</span></span>|<span data-ttu-id="00b7e-152">비활성화</span><span class="sxs-lookup"><span data-stu-id="00b7e-152">Disabled</span></span>|<span data-ttu-id="00b7e-153">수</span><span class="sxs-lookup"><span data-stu-id="00b7e-153">Enabled</span></span>|<span data-ttu-id="00b7e-154">수</span><span class="sxs-lookup"><span data-stu-id="00b7e-154">Enabled</span></span>|
|<span data-ttu-id="00b7e-155">SfBWithTeamsCollab 또는 SfBOnly</span><span class="sxs-lookup"><span data-stu-id="00b7e-155">SfBWithTeamsCollab or SfBOnly</span></span>|<span data-ttu-id="00b7e-156">비활성화</span><span class="sxs-lookup"><span data-stu-id="00b7e-156">Disabled</span></span>|<span data-ttu-id="00b7e-157">비활성화</span><span class="sxs-lookup"><span data-stu-id="00b7e-157">Disabled</span></span>|<span data-ttu-id="00b7e-158">비활성화</span><span class="sxs-lookup"><span data-stu-id="00b7e-158">Disabled</span></span>|<span data-ttu-id="00b7e-159">비활성화</span><span class="sxs-lookup"><span data-stu-id="00b7e-159">Disabled</span></span>|
||||||

<span data-ttu-id="00b7e-160">PowerShell을 사용 하는 `Grant-CsTeamsUpgradePolicy` 경우 Cmdlet은 TeamsMessagingPolicy, Teamsmessagingpolicy 및 TeamsMeetingPolicy에서 해당 설정의 구성을 확인 하 여 해당 설정이 TeamsUpgradePolicy로 대체 되는지 여부를 결정 합니다. 알림 메시지는 PowerShell에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-160">When using PowerShell, the `Grant-CsTeamsUpgradePolicy` cmdlet checks the configuration of the corresponding settings in TeamsMessagingPolicy, TeamsCallingPolicy, and TeamsMeetingPolicy to determine if those settings would be superceded by TeamsUpgradePolicy and if so, an informational message is provided in PowerShell.</span></span>  <span data-ttu-id="00b7e-161">위에서 설명한 것 처럼 더 이상 다른 정책 설정을 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-161">As noted above,  is no longer necessary to set these other policy settings.</span></span> <span data-ttu-id="00b7e-162">다음은 PowerShell 경고가 다음과 같이 표시 되는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="00b7e-162">Below is an example of what the PowerShell warning looks like:</span></span>

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



# <a name="related-topics"></a><span data-ttu-id="00b7e-163">관련 항목</span><span class="sxs-lookup"><span data-stu-id="00b7e-163">Related topics</span></span>

[<span data-ttu-id="00b7e-164">비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침</span><span class="sxs-lookup"><span data-stu-id="00b7e-164">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/en-us/microsoftteams/migration-interop-guidance-for-teams-with-skype)




