---
title: 보기 전용 모임 환경
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 관리자, 발표자 및 참석자를 위한 Teams 보기 전용 모임 환경에 대한 자세한 내용 알아보기
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76137c0ebfe73c6ba500a0dbcdc8ee1a01de85fc
ms.sourcegitcommit: 242561bfc12504614633539ca696b91dfc890b92
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52328560"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="e95ac-103">Teams 보기 전용 모임 환경</span><span class="sxs-lookup"><span data-stu-id="e95ac-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="e95ac-104">보기 전용 브로드캐스트는 Microsoft 365 E3/E5 및 Microsoft 365 A3/A5에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="e95ac-105">이 기능은 2021년 3월 1일을 기본값 해제로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="e95ac-106">Microsoft 365 정부 커뮤니티 클라우드(GCC)의 기능 배포는 2021년 3월 말에 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="e95ac-107">정부 커뮤니티 클라우드 높음(GCCH) 및 국방부(DoD)는 차후에 배포될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="e95ac-108">이 기능의 사용을 기본값으로 하려면 해당 날짜 이후에 기본 정책을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="e95ac-109">PowerShell을 통해 정책 설정을 사용 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span><span class="sxs-lookup"><span data-stu-id="e95ac-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="e95ac-110">모임 또는 웨비나가 최대 수용인원에 도달할 경우 10,000명 규모의 보기 전용 브로드캐스트 환경까지 수용할 수 있도록 Teams가 원활하게 규모를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="e95ac-111">또한 원격 작업 증가 기간 중, 올해 말까지는 이보다 더 많은 규모인 20,000명의 브로드캐스트를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="e95ac-112">Microsoft Teams에서 최대 10,000명 참석자가 Teams 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="e95ac-113">주 모임의 용량에 도달한 후(사용자가 1,000명이 모임에 참가하는 경우) 추가 참석자는 보기 전용 환경으로 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-113">After the capacity of the main meeting has been reached (which is when 1000 users enter a meeting), additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="e95ac-114">모임에 먼저 참가하는 참석자는 주 모임의 용량까지 모든 Teams 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-114">Attendees who join the meeting first, up to the capacity of the main meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="e95ac-115">즉, 음성 및 비디오 공유, 공유 비디오 시청, 모임의 채팅 참여가 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="e95ac-116">주 모임이 최대 허용 인원에 도달한 후 참가한 참석자에게는 보기 전용 환경이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="e95ac-117">참석자는 데스크톱, 웹 및 모바일(Android 및 iOS)을 통해 보기 전용 Teams 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-117">Attendees will be able to join the view-only experience through desktop, web, and Teams mobile (Android and iOS).</span></span>

> [!Note]
> <span data-ttu-id="e95ac-118">"주 모임"의 현재 제한 용량 또는 즉, 완전 대화형 사용자 수가 1000명으로, 이 제한은 GCC.</span><span class="sxs-lookup"><span data-stu-id="e95ac-118">The current limit capacity of the "main meeting", or in other words, the number of fully interactive users, is 1000 and includes GCC.</span></span>

## <a name="teams-view-only-experience-controls"></a><span data-ttu-id="e95ac-119">Teams 전용 환경 컨트롤</span><span class="sxs-lookup"><span data-stu-id="e95ac-119">Teams view-only experience controls</span></span>

<span data-ttu-id="e95ac-120">PowerShell을 사용하여 보기 전용 환경을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-120">You enable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

<span data-ttu-id="e95ac-121">보기 전용 환경을 사용하지 않도록 설정하기 위해 PowerShell을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-121">To disable the view-only experience, you can also use PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="e95ac-122">앞으로는 관리 센터에서 보기 전용 환경을 사용하도록 설정하거나 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-122">In the future, you'll be able to enable or disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="e95ac-123">사용자에게 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="e95ac-123">Impact to users</span></span>

<span data-ttu-id="e95ac-124">사용자의 환경은 여러 요인에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-124">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="e95ac-125">주 모임의 최대 허용 인원에 도달하면, 다음 중 해당 사항이 있는 참석자는 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-125">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="e95ac-126">관리자는 이끌이 또는 Teams 보기 전용 환경을 사용하지 않도록 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-126">An administrator has disabled the Teams view-only experience for either the organizer or for the entire tenant.</span></span>
- <span data-ttu-id="e95ac-127">보기 전용 참석자만 로비를 무시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-127">The view-only attendee can't bypass the lobby.</span></span> <span data-ttu-id="e95ac-128">예를 들어 모임 이끌이가 내 조직의 사용자만  로비를 무시하고 조직 외부의 참석자가 보기 전용 참석자로 참가하려고 하는 경우 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-128">As an example, if an organizer of a meeting chooses to have only **People in my organization** bypass the lobby, and an attendee who is outside of the organization attempts to join as a view-only attendee, they won't be able to join.</span></span>

<span data-ttu-id="e95ac-129">주 모임의 용량에 도달하면 모임 이끌이와 발표자가 새 참석자가 보기 전용 참석자로 참가할 것임이 알리는 배너가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that new attendees will join as view-only attendees.</span></span>

  ![이끌이 및 발표자에 대한 Teams 클라이언트 및 배너 메시지](media/chat-and-banner-message.png)

<span data-ttu-id="e95ac-131">주 모임의 최대 허용 인원에 도달하면, 모임 참석자는 사전 참가 화면에서 보기 전용 모드로 참가했다는 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams 사전 참가 화면과 참석자가 보기 전용 모드로 참가한다는 내용을 전하는 메시지](media/view-only-pre-join-screen.png)

<span data-ttu-id="e95ac-133">공석이 있는 경우 사용자는 항상 주 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="e95ac-134">주 모임이 최대 허용 인원에 도달하고 한명 이상의 참석자가 주 모임을 떠나는 경우 주 모임에 수용 가능 인원이 생깁니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="e95ac-135">모임이 다시 최대 허용 인원에 도달할 때까지 모임에 참가(또는 재참가)하는 참석자는 주 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="e95ac-136">보기 전용 환경인 참석자들은 자동으로 주 모임으로 승격되지 않습니다. 주 모임으로 수동으로 승격할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't be manually promoted to the main meeting.</span></span>

<span data-ttu-id="e95ac-137">발표자 및 참석자 역할이 설정되고 발표자는 주 모임이 용량에 도달한 후 모임에 참가하려고 하는 경우 보기 전용 참석자로 참가하고 다른 보기 전용 참석자와 동일한 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-137">If presenter and attendee roles have been set, and a presenter attempts to join a meeting after the main meeting has reached capacity, they'll join as a view-only attendee and have the same limitations as other view-only attendees.</span></span> <span data-ttu-id="e95ac-138">모든 발표자들이 주 모임에 참가할 수 있도록 지원이 나중에 롤아웃됩니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-138">Support to ensure all presenters join the main meeting will roll out at a later date.</span></span> <span data-ttu-id="e95ac-139">이끌이는 항상 주 모임의 공간을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-139">The organizer will always be guaranteed space in the main meeting.</span></span>

## <a name="impact-to-meeting-presenters-and-organizers"></a><span data-ttu-id="e95ac-140">모임 발표자 및 이끌이에게 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="e95ac-140">Impact to meeting presenters and organizers</span></span>

<span data-ttu-id="e95ac-141">모임 발표자 및 이끌이에 대한 제한은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-141">Limitations for meeting presenters and organizers include:</span></span>

- <span data-ttu-id="e95ac-142">보기 전용 참석자에 대한 정보는 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-142">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="e95ac-143">보기 전용 참석자에 대해 E-discovery를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-143">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="e95ac-144">주 모임의 사용자는 보기 전용 참석자만 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-144">Users in the main meeting can't see the view-only attendees.</span></span>
- <span data-ttu-id="e95ac-145">모임에서 보기 전용 참석자를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-145">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="e95ac-146">참석자 수는 보기 전용 회의실에 있는 사람이 아니라 주 모임의 사람만 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-146">Attendee count will only reflect the people in the main meeting and not the people in the view-only room.</span></span> <span data-ttu-id="e95ac-147">따라서 발표자는 보기 전용 환경의 참석 인원을 정확히 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-147">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="e95ac-148">보기 전용 참석자 환경</span><span class="sxs-lookup"><span data-stu-id="e95ac-148">Experience for view-only attendees</span></span>

<span data-ttu-id="e95ac-149">Teams 보기 전용 환경 참석자들은 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-149">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="e95ac-150">주 Teams 모임의 참가자 듣기</span><span class="sxs-lookup"><span data-stu-id="e95ac-150">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="e95ac-151">현재 발표자에 대한 비디오 피드 보기(현재 발표자가 비디오를 공유하고 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="e95ac-151">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="e95ac-152">공유 데스크톱 또는 화면 기능을 사용하여 공유되는 콘텐츠를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e95ac-152">See content being shared using the share desktop or screen functionality.</span></span>

<span data-ttu-id="e95ac-153">보기 전용 참석자는 모임에서 다음과 같은 옵션을 경험할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-153">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="e95ac-154">참석자가 설정된 로비 정책 또는 옵션에 따라 대기실을 지나칠 수 있는 권한이 없는 경우 모임에 참가</span><span class="sxs-lookup"><span data-stu-id="e95ac-154">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="e95ac-155">오디오 회의를 사용하여 보기 전용 공간에 참가</span><span class="sxs-lookup"><span data-stu-id="e95ac-155">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="e95ac-156">CVI(Cloud Video Interop) 서비스를 사용하여 Microsoft Teams 룸 보기 전용 룸에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-156">Join the view-only room using Microsoft Teams Rooms system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="e95ac-157">오디오 또는 비디오 공유</span><span class="sxs-lookup"><span data-stu-id="e95ac-157">Share their audio or video.</span></span>
- <span data-ttu-id="e95ac-158">모임 채팅을 보거나 참여하기</span><span class="sxs-lookup"><span data-stu-id="e95ac-158">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="e95ac-159">참가자가 현재 발표자가 아닌 경우 모임 참가자의 비디오 피드 보기</span><span class="sxs-lookup"><span data-stu-id="e95ac-159">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="e95ac-160">라이브 PowerPoint 또는 개별 PowerPoint 공유(데스크톱 또는 화면 공유 외)를 사용하여 공유되는 PowerPoint 파일을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-160">See PowerPoint files that are shared using the PowerPoint Live functionality or individual application shares (other than desktop or screen sharing).</span></span>
- <span data-ttu-id="e95ac-161">모임에서 손을 다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-161">Raise their hand in the meeting.</span></span>
- <span data-ttu-id="e95ac-162">반응을 보내거나 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-162">Send or see reactions.</span></span>
- <span data-ttu-id="e95ac-163">설문 조사를 포함하여 Teams 통합된 모든 3P 앱과 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-163">Interact with any 3P App integrating into the Teams Meeting, including Polls.</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="e95ac-164">보기 전용 기능 제한 사항</span><span class="sxs-lookup"><span data-stu-id="e95ac-164">View-only feature limitations</span></span>

- <span data-ttu-id="e95ac-165">보기 전용 참석자는 데스크톱 및 웹에서 라이브 캡션만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-165">View-only attendees will only be able to see Live Captions on Desktop and Web.</span></span> <span data-ttu-id="e95ac-166">현재 영어 캡션만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-166">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="e95ac-167">보기 전용 참석자에게 스트리밍 기술이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-167">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="e95ac-168">보기 전용 참석자는 참석자 보고서에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-168">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="e95ac-169">보기 전용 참석자는 단일 비디오 환경을 이용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-169">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="e95ac-170">현재 발표자 또는 공유되고 있는 콘텐츠 중 하나는 볼 수 있지만 두가지를 동시에 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-170">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="e95ac-171">현재는 보기 전용 참석자를 위한 **갤러리**, **대형 갤러리**, 또는 **함께 모드** 레이아웃을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-171">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="e95ac-172">보기 전용 참석자의 대기 시간은 일반 참석자와 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-172">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="e95ac-173"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e95ac-173"><sup>1</sup></span></span>

  <span data-ttu-id="e95ac-174"><sup>1</sup> 보기 전용 참석자는 회의에서 비디오 및 오디오가 30초 지연되어 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="e95ac-174"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
