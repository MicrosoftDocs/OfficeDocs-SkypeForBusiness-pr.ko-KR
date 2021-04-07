---
title: 일반 모임 정책 관리
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
- ms.teamsadmincenter.meetingpolicies.general
- seo-marvel-apr2020
description: Teams에서 일반 모임 정책 설정을 관리하는 방법을 학습합니다.
ms.openlocfilehash: fb5f537e5cc96ba363fb4aa68bbfff2af513db6b
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598767"
---
# <a name="meeting-policy-settings---general"></a><span data-ttu-id="6c749-103">모임 정책 설정 - 일반</span><span class="sxs-lookup"><span data-stu-id="6c749-103">Meeting policy settings - General</span></span>

<span data-ttu-id="6c749-104"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="6c749-104"><a name="bkgeneral"> </a></span></span>

<span data-ttu-id="6c749-105">이 문서에서는 Teams 모임에 대한 다음 일반 정책 설정을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-105">This article describes the following general policy settings for Teams meetings:</span></span>

- [<span data-ttu-id="6c749-106">채널에서 지금 만나기 허용</span><span class="sxs-lookup"><span data-stu-id="6c749-106">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="6c749-107">Outlook 추가 기능 허용</span><span class="sxs-lookup"><span data-stu-id="6c749-107">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="6c749-108">채널 모임일정 허용</span><span class="sxs-lookup"><span data-stu-id="6c749-108">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="6c749-109">비공개 모임을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-109">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="6c749-110">비공개 모임에서 지금 모임 허용</span><span class="sxs-lookup"><span data-stu-id="6c749-110">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)
- [<span data-ttu-id="6c749-111">지정된 발표자 역할 모드</span><span class="sxs-lookup"><span data-stu-id="6c749-111">Designated presenter role mode</span></span>](#designated-presenter-role-mode)
- [<span data-ttu-id="6c749-112">모임 참석 보고서</span><span class="sxs-lookup"><span data-stu-id="6c749-112">Meeting attendance report</span></span>](#meeting-attendance-report)
- [<span data-ttu-id="6c749-113">제도 모드에 대한 모임 공급자</span><span class="sxs-lookup"><span data-stu-id="6c749-113">Meeting provider for Islands mode</span></span>](#meeting-provider-for-islands-mode)

## <a name="allow-meet-now-in-channels"></a><span data-ttu-id="6c749-114">채널에서 지금 만나기 허용</span><span class="sxs-lookup"><span data-stu-id="6c749-114">Allow Meet now in channels</span></span>

<span data-ttu-id="6c749-115">이는 사용자당 정책으로 모임이 시작되기 전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-115">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="6c749-116">이 설정은 사용자가 Teams 채널에서 모임을 시작할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-116">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="6c749-117">이 기능을 설정하면 사용자는 모임  단추를 클릭하여 모임을 시작하거나 채널에서 모임을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-117">If you turn this on, users can click the **Meet** button to start an ad hoc meeting or schedule a meeting in the channel.</span></span> <span data-ttu-id="6c749-118">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-118">The default value is True.</span></span>

<span data-ttu-id="6c749-119">[![메시지 아래에 지금 만나기 아이콘을 보여주는 스크린샷 ](media/meeting-policies-meet-now.png)](media/meeting-policies-meet-now.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="6c749-119">[ ![Screenshot showing the Meet now icon below a message](media/meeting-policies-meet-now.png) ](media/meeting-policies-meet-now.png#lightbox)</span></span>

## <a name="allow-the-outlook-add-in"></a><span data-ttu-id="6c749-120">Outlook 추가 기능 허용</span><span class="sxs-lookup"><span data-stu-id="6c749-120">Allow the Outlook add-in</span></span>

<span data-ttu-id="6c749-121">이는 사용자당 정책으로 모임이 시작되기 전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-121">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="6c749-122">이 설정은 Outlook(Windows, Mac, 웹 및 모바일) 내에서 Teams 모임을 예약할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-122">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![새 모임을 예약하는 기능을 보여주는 스크린샷](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="6c749-124">이 기능을 해제하면 사용자가 Outlook에서 새 모임을 만들 때 Teams 모임을 예약할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-124">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="6c749-125">예를 들어 Windows의 Outlook에서  새 팀 모임 옵션이 리본에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-125">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

## <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="6c749-126">채널 모임일정 허용</span><span class="sxs-lookup"><span data-stu-id="6c749-126">Allow channel meeting scheduling</span></span>

<span data-ttu-id="6c749-127">기존 AllowChannelMeetingScheduling 정책을 사용하여 팀 채널 일정에서 만들 수 있는 이벤트 유형을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-127">Use the existing AllowChannelMeetingScheduling policy to control the types of events that can be created on the team channel calendars.</span></span> <span data-ttu-id="6c749-128">이는 사용자당 정책으로 모임이 시작되기 전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-128">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="6c749-129">이 설정은 사용자가 Teams 채널에서 모임을 예약할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-129">This setting controls whether users can schedule a meeting in a Teams channel.</span></span> <span data-ttu-id="6c749-130">기본적으로 이 설정은 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-130">By default, this setting is turned on.</span></span> 

<span data-ttu-id="6c749-131">이 정책이 해제된 경우 사용자는 새 채널 모임을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-131">If this policy is turned off, users will not be able to create new channel meetings.</span></span> <span data-ttu-id="6c749-132">그러나 기존 채널 모임은 이벤트 이끌이가 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-132">However, existing channel meetings can be edited by the organizer of the event.</span></span>

<span data-ttu-id="6c749-133">모임 예약이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-133">Schedule a meeting will be disabled.</span></span>

![Teams에서 모임 예약 옵션을 보여주는 스크린샷](media/schedule-meeting-option.png)

<span data-ttu-id="6c749-135">채널 선택을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-135">Channel selection is disabled.</span></span>

<span data-ttu-id="6c749-136">[모임을 예약할 채널을 선택하는 일정 옵션을 보여주는 ![ 스크린샷입니다. ](media/meeting-policies-select-a-channel-to-meet-in.png)](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="6c749-136">[ ![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/meeting-policies-select-a-channel-to-meet-in.png) ](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)</span></span>

<span data-ttu-id="6c749-137">채널 게시물 페이지에서는 다음을 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-137">In the channel posts page, the following will be disabled:</span></span>

- <span data-ttu-id="6c749-138">**채널 회신** 작성 상자에서 모임 단추를 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-138">**Schedule a meeting** button on the channel reply compose box.</span></span>
  <span data-ttu-id="6c749-139">![모임을 예약할 채널을 선택하는 일정 옵션을 보여주는 스크린샷입니다.](media/schedule-meeting-disabled-in-chat2.png)</span><span class="sxs-lookup"><span data-stu-id="6c749-139">![Screenshot showing the calendar option for selecting a channel in which you want to schedule a meeting.](media/schedule-meeting-disabled-in-chat2.png)</span></span>
  
- <span data-ttu-id="6c749-140">**채널 헤더에서** 모임 단추를 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-140">**Schedule a meeting** button on the channel header.</span></span>
  <span data-ttu-id="6c749-141">![모임을 예약할 채널을 선택하는 일정 옵션을 보여주는 스크린샷입니다.](media/schedule-now-in-header.png)</span><span class="sxs-lookup"><span data-stu-id="6c749-141">![Screenshot showing the calendar option for selecting a channel through which you want to schedule a meeting.](media/schedule-now-in-header.png)</span></span>

<span data-ttu-id="6c749-142">채널 달력에서:</span><span class="sxs-lookup"><span data-stu-id="6c749-142">In the channel calendar:</span></span>

- <span data-ttu-id="6c749-143">**채널 일정 헤더에** 새 이벤트 단추를 추가하면 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-143">**Add new event** button on channel calendar header will be disabled.</span></span>
  <span data-ttu-id="6c749-144">![모임을 예약할 수 있는 채널을 선택하는 일정 옵션을 보여주는 스크린샷입니다.](media/add-new-event-disabled.png)</span><span class="sxs-lookup"><span data-stu-id="6c749-144">![Screenshot showing the calendar option for selecting a channel that will enable you to schedule a meeting.](media/add-new-event-disabled.png)</span></span>

- <span data-ttu-id="6c749-145">사용자는 채널 일정에서 시간 블록을 끌어 채널 모임을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-145">Users will not be able to drag and select a time block on the channel calendar to create a channel meeting.</span></span>

- <span data-ttu-id="6c749-146">사용자는 바로 가기 키를 사용하여 채널 일정에서 모임을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-146">Users cannot use Keyboard shortcuts to create a meeting on the channel calendar.</span></span>

<span data-ttu-id="6c749-147">관리 센터에서:</span><span class="sxs-lookup"><span data-stu-id="6c749-147">In the admin center:</span></span>

<span data-ttu-id="6c749-148">채널 일정 앱은 앱 권한 정책 페이지의 **Microsoft 앱** 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-148">The channel calendar app will show up in the **Microsoft apps** section on the app permission policies page.</span></span>

![Teams 관리 센터에서 앱 사용 권한 정책을 보여주는 스크린샷입니다.](media/manage-microsoft-apps-policy.png)

## <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="6c749-150">비공개 모임을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-150">Allow scheduling private meetings</span></span>

<span data-ttu-id="6c749-151">이는 사용자당 정책으로 모임이 시작되기 전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-151">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="6c749-152">이 설정은 사용자가 Teams에서 비공개 모임을 예약할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-152">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="6c749-153">모임은 팀의 채널에 게시되지 않은 경우 비공개입니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-153">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="6c749-154">비공개 모임 예약  허용을 해제하고 채널 모임 예약 허용을 해제하면 Teams의 사용자에 대해  필수 참석자 추가 및 채널 추가 옵션을 사용하지 않도록 설정됩니다. </span><span class="sxs-lookup"><span data-stu-id="6c749-154">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="6c749-155">기본적으로 이 설정은 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-155">By default, this setting is turned on.</span></span>

## <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="6c749-156">비공개 모임에서 지금 모임 허용</span><span class="sxs-lookup"><span data-stu-id="6c749-156">Allow Meet now in private meetings</span></span>

<span data-ttu-id="6c749-157">이는 사용자당 정책으로 모임이 시작되기 전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-157">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="6c749-158">이 설정은 사용자가 비공개 모임을 시작할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-158">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="6c749-159">기본적으로 이 설정은 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-159">By default, this setting is turned on.</span></span>

## <a name="designated-presenter-role-mode"></a><span data-ttu-id="6c749-160">지정된 발표자 역할 모드</span><span class="sxs-lookup"><span data-stu-id="6c749-160">Designated presenter role mode</span></span>

<span data-ttu-id="6c749-161">사용자당 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-161">This is a per-user policy.</span></span> <span data-ttu-id="6c749-162">이 설정을 사용하면 Teams 클라이언트의 모임 옵션에서  발표할 수 있는 **사람의** 기본값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-162">This setting lets you change the default value of the **Who can present?** setting in **Meeting options** in the Teams client.</span></span> <span data-ttu-id="6c749-163">이 정책 설정은 모임 지금 모임을 포함하여 모든 모임에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-163">This policy setting affects all meetings, including Meet Now meetings.</span></span>

<span data-ttu-id="6c749-164">발표할 **수 있는 사람?** 설정을 사용하면 모임 이끌이가 모임에서 발표자가 될 수 있는 인원을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-164">The **Who can present?** setting lets meeting organizers choose who can be presenters in a meeting.</span></span> <span data-ttu-id="6c749-165">자세한 내용은 Teams 모임의 [Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) 모임 및 역할에 대한 참가자 설정 [변경을 참조하세요.](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)</span><span class="sxs-lookup"><span data-stu-id="6c749-165">To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).</span></span>

<span data-ttu-id="6c749-166">현재 PowerShell을 사용하여 이 정책 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-166">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="6c749-167">[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용하여 기존 Teams 모임 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-167">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="6c749-168">또는 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용하여 새 Teams 모임 정책을 만들고 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-168">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="6c749-169">Teams에서 표시할 수 있는 **사람의** 기본값을 지정하기 위해 Teams에서 **DesignatedPresenterRoleMode** 매개 변수를 다음 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-169">To specify the default value of the **Who can present?** setting in Teams, set the **DesignatedPresenterRoleMode** parameter to one of the following:</span></span>

- <span data-ttu-id="6c749-170">**EveryoneUserOverride:** 모든 모임 참가자가 발표자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-170">**EveryoneUserOverride**:  All meeting participants can be presenters.</span></span> <span data-ttu-id="6c749-171">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-171">This is the default value.</span></span> <span data-ttu-id="6c749-172">이 매개 변수는 **Teams의 모든 사용자** 설정에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-172">This parameter corresponds to the **Everyone** setting in Teams.</span></span>
- <span data-ttu-id="6c749-173">**EveryoneInCompanyUserOverride:** 게스트 사용자를 포함하여 조직의 인증된 사용자가 발표자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-173">**EveryoneInCompanyUserOverride**: Authenticated users in the organization, including guest users, can be presenters.</span></span> <span data-ttu-id="6c749-174">이 매개 변수는 Teams의 내 조직 **설정의 사용자에** 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-174">This parameter corresponds to the **People in my organization** setting in Teams.</span></span>
- <span data-ttu-id="6c749-175">**OrganizerOnlyUserOverride:** 모임 이끌이만 발표자가 될 수 있으며 모든 모임 참가자는 참석자로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-175">**OrganizerOnlyUserOverride**: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees.</span></span> <span data-ttu-id="6c749-176">이 매개 변수는 **Teams의 나만** 설정에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-176">This parameter corresponds to the **Only me** setting in Teams.</span></span>

<span data-ttu-id="6c749-177">기본값을 설정한 후에도 모임 이끌이는 Teams에서 이 설정을 변경하고 예약한 모임에 참석할 수 있는 사용자도 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-177">Keep in mind that after you set the default value, meeting organizers can still change this setting in Teams and choose who can present in the meetings that they schedule.</span></span>

## <a name="meeting-attendance-report"></a><span data-ttu-id="6c749-178">모임 참석 보고서</span><span class="sxs-lookup"><span data-stu-id="6c749-178">Meeting attendance report</span></span>

<span data-ttu-id="6c749-179">사용자당 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-179">This is a per-user policy.</span></span> <span data-ttu-id="6c749-180">이 설정은 모임 이끌이가 모임 참석 보고서를 다운로드할 수 있는지 [여부를 제어합니다.](teams-analytics-and-reports/meeting-attendance-report.md)</span><span class="sxs-lookup"><span data-stu-id="6c749-180">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="6c749-181">현재 PowerShell을 사용하여 이 정책 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-181">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="6c749-182">[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용하여 기존 Teams 모임 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-182">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="6c749-183">또는 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용하여 새 Teams 모임 정책을 만들고 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-183">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="6c749-184">모임 이끌이가 모임 참석 보고서를 다운로드하도록 설정하려면 **AllowEngagementReport** 매개 변수를 사용 으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c749-184">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="6c749-185">이 옵션을 사용하도록 설정하면 보고서를 다운로드하는  옵션이 참가자 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-185">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="6c749-186">모임 이끌이가 보고서를 다운로드하지 못하게하려면 매개 변수를 사용 안 으로 **설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="6c749-186">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="6c749-187">기본적으로 이 설정은 비활성화되어 있으며 보고서를 다운로드하는 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-187">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="meeting-provider-for-islands-mode"></a><span data-ttu-id="6c749-188">제도 모드에 대한 모임 공급자</span><span class="sxs-lookup"><span data-stu-id="6c749-188">Meeting provider for Islands mode</span></span>

<span data-ttu-id="6c749-189">사용자당 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-189">This is a per-user policy.</span></span> <span data-ttu-id="6c749-190">이 설정은 아일랜드 모드인 사용자에게 사용되는 Outlook 모임 추가 기능을 *제어합니다.*</span><span class="sxs-lookup"><span data-stu-id="6c749-190">This setting controls which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="6c749-191">사용자가 Teams 모임 추가 기능만 사용할 수 있는지 또는 Teams 모임 및 비즈니스용 Skype 모임 추가 기능을 모두 사용하여 Outlook에서 회의를 예약할 수 있는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-191">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="6c749-192">이 정책은 아일랜드 모드이면서 Teams 모임 정책에서 **AllowOutlookAddIn** 매개 변수가 **True** 로 설정된 사용자에게만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-192">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span>

<span data-ttu-id="6c749-193">현재 PowerShell을 사용하여 이 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-193">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="6c749-194">[Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet을 사용하여 기존 Teams 모임 정책을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-194">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="6c749-195">또는 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet을 사용하여 새 Teams 모임 정책을 만들고 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-195">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="6c749-196">사용자가 사용할 수 있는 모임 추가 기능을 지정하기 위해 다음과 같이 **PreferredMeetingProviderForIslandsMode** 매개 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-196">To specify which meeting add-in you want to be available to users, set the **PreferredMeetingProviderForIslandsMode** parameter as follows:</span></span>

- <span data-ttu-id="6c749-197">**TeamsAndSfB로** 매개 변수를 설정하여 Outlook에서 Teams 모임 추가 기능 및 비즈니스용 Skype 추가 기능을 모두 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-197">Set the parameter to **TeamsAndSfB** to enable both the Teams Meeting add-in and Skype for Business add-in in Outlook.</span></span> <span data-ttu-id="6c749-198">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-198">This is the default value.</span></span>
- <span data-ttu-id="6c749-199">Outlook에서 **Teams** 모임 추가 기능만 사용하도록 설정하려면 매개 변수를 Teams로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-199">Set the parameter to **Teams** to enable only the Teams Meeting add-in in Outlook.</span></span> <span data-ttu-id="6c749-200">이 정책 설정은 향후 모든 모임에 Teams 모임 조인 링크가 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-200">This policy setting ensures that all future meetings have a Teams meeting join link.</span></span> <span data-ttu-id="6c749-201">기존 비즈니스용 Skype 모임 참가 링크를 Teams로 마이그레이션하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-201">It doesn't migrate existing Skype for Business meeting join links to Teams.</span></span> <span data-ttu-id="6c749-202">이 정책 설정은 비즈니스용 Skype의 현재 상태, 채팅, PSTN 통화 또는 기타 기능에 영향을 주지 않습니다. 즉, 사용자는 이러한 기능에 대해 비즈니스용 Skype를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-202">This policy setting doesn't affect presence, chat, PSTN calling, or any other capabilities in Skype for Business, which means that users will continue to use Skype for Business for these capabilities.</span></span>

  <span data-ttu-id="6c749-203">매개 변수를 **Teams로** 설정한 다음 **TeamsAndSfB로** 다시 전환하면 두 모임 추가 기능이 모두 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-203">If you set the parameter to **Teams**, and then switch back to **TeamsAndSfB**, both meeting add-ins are enabled.</span></span> <span data-ttu-id="6c749-204">그러나 기존 Teams 모임 조인 링크는 비즈니스용 Skype로 마이그레이션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-204">However, note that existing Teams meeting join links won't be migrated to Skype for Business.</span></span> <span data-ttu-id="6c749-205">변경 후 예약된 비즈니스용 Skype 모임만 비즈니스용 Skype 모임 참가 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-205">Only Skype for Business meetings scheduled after the change will have a Skype for Business meeting join link.</span></span>

## <a name="meeting-reactions"></a><span data-ttu-id="6c749-206">모임 반응</span><span class="sxs-lookup"><span data-stu-id="6c749-206">Meeting reactions</span></span>

<span data-ttu-id="6c749-207">AllowMeetingReactions 설정은 PowerShell을 사용하여만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-207">The AllowMeetingReactions setting can only be applied using PowerShell.</span></span> <span data-ttu-id="6c749-208">Teams 관리 센터에서 AllowMeetingReactions를 설정하거나 해제하는 옵션은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-208">There is no option to toggle AllowMeetingReactions on or off from the Teams admin center.</span></span>

<span data-ttu-id="6c749-209">모임 반응은 기본적으로 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-209">Meeting reactions are Off by default.</span></span> <span data-ttu-id="6c749-210">사용자에 대한 반응을 끄는 것은 사용자가 예약한 모임에서 반응을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-210">Turning off reactions for a user doesn't mean that a user can't use reactions in meetings they schedule.</span></span> <span data-ttu-id="6c749-211">모임 이끌이는 기본 설정에 관계없이 모임 옵션 페이지에서 여전히 반응을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c749-211">The meeting organizer can still turn on reactions from the meeting option page, regardless of the default setting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="6c749-212">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6c749-212">Related topics</span></span>

- [<span data-ttu-id="6c749-213">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="6c749-213">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="6c749-214">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6c749-214">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="6c749-215">사용자로부터 RestrictedAnonymousAccesss Teams 모임 정책 제거</span><span class="sxs-lookup"><span data-stu-id="6c749-215">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
