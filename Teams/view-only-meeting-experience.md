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
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875058"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="a1caa-103">Teams 보기 전용 모임 환경</span><span class="sxs-lookup"><span data-stu-id="a1caa-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="a1caa-104">보기 전용 브로드캐스트는 Microsoft 365 E3/E5 및 Microsoft 365 A3/A5에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="a1caa-105">이 기능은 2021년 3월 1일을 기본값 해제로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="a1caa-106">Microsoft 365 정부 커뮤니티 클라우드(GCC)의 기능 배포는 2021년 3월 말에 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="a1caa-107">정부 커뮤니티 클라우드 높음(GCCH) 및 국방부(DoD)는 차후에 배포될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="a1caa-108">이 기능의 사용을 기본값으로 하려면 해당 날짜 이후에 기본 정책을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="a1caa-109">PowerShell을 통해 정책 설정을 사용 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span><span class="sxs-lookup"><span data-stu-id="a1caa-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="a1caa-110">모임 또는 웨비나가 최대 수용인원에 도달할 경우 10,000명 규모의 보기 전용 브로드캐스트 환경까지 수용할 수 있도록 Teams가 원활하게 규모를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="a1caa-111">또한 원격 작업 증가 기간 중, 올해 말까지는 이보다 더 많은 규모인 20,000명의 브로드캐스트를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="a1caa-112">Microsoft Teams에서 최대 10,000명 참석자가 Teams 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="a1caa-113">주 모임이 최대 허용 인원에 도달하면, 추가 참석자는 보기 전용 환경을 통해 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-113">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="a1caa-114">먼저 모임에 참가한 참석자 중 모임의 최대 허용 인원 까지는 모든 기능을 포함한 Teams 모임 환경이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-114">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="a1caa-115">즉, 음성 및 비디오 공유, 공유 비디오 시청, 모임의 채팅 참여가 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="a1caa-116">주 모임이 최대 허용 인원에 도달한 후 참가한 참석자에게는 보기 전용 환경이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="a1caa-117">참석자가 참가할 수 있도록 Android 및 iOS 모바일용 지원사항을 모두 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-117">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="a1caa-118">현재 모임에서 채팅 및 전화를 이용할 수 있는 최대 사용 인원은 WW에서는 300명, GCC, GCC High 및 DoD에서는 250명입니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-118">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="a1caa-119">E3/E5/A3/A5 SKU가 있는 모든 이끌이는 기본값으로 보기 전용 환경을 사용할 수 없도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-119">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="a1caa-120">추가 구성 또는 설정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-120">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="a1caa-121">Teams 보기 전용 환경 사용 불가로 설정</span><span class="sxs-lookup"><span data-stu-id="a1caa-121">Disable Teams view-only experience</span></span>

<span data-ttu-id="a1caa-122">관리자는 PowerShell을 통해 보기 전용 환경을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-122">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="a1caa-123">향후에는 관리자가 Teams 관리 센터에서 보기 전용 환경을 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-123">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="a1caa-124">사용자에게 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="a1caa-124">Impact to users</span></span>

<span data-ttu-id="a1caa-125">사용자의 환경은 여러 요인에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-125">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="a1caa-126">주 모임의 최대 허용 인원에 도달하면, 다음 중 해당 사항이 있는 참석자는 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-126">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="a1caa-127">관리자가 Teams 보기 전용 환경을 사용하지 않도록 설정.</span><span class="sxs-lookup"><span data-stu-id="a1caa-127">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="a1caa-128">참석자는 대기실을 지나칠 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-128">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="a1caa-129">주 모임의 최대 허용 인원에 도달하면, 모임 최대 허용 인원에 도달했고 새 참석자는 보기 전용으로 참여할 것이라는 배너가 모임 이끌이와 발표자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![이끌이 및 발표자에 대한 Teams 클라이언트 및 배너 메시지](media/chat-and-banner-message.png)

<span data-ttu-id="a1caa-131">주 모임의 최대 허용 인원에 도달하면, 모임 참석자는 사전 참가 화면에서 보기 전용 모드로 참가했다는 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams 사전 참가 화면과 참석자가 보기 전용 모드로 참가한다는 내용을 전하는 메시지](media/view-only-pre-join-screen.png)

<span data-ttu-id="a1caa-133">공석이 있는 경우 사용자는 항상 주 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="a1caa-134">주 모임이 최대 허용 인원에 도달하고 한명 이상의 참석자가 주 모임을 떠나는 경우 주 모임에 수용 가능 인원이 생깁니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="a1caa-135">모임이 다시 최대 허용 인원에 도달할 때까지 모임에 참가(또는 재참가)하는 참석자는 주 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="a1caa-136">보기 전용 환경을 사용 중인 참석자는 주 모임으로 자동으로 승격되지 못하며 현재 주 모임으로 수동으로 승격될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="a1caa-137">발표자/참석자 역할이 설정되지 않은 경우 주 모임의 공석은 선착순으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-137">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="a1caa-138">모임이 최대 허용 인원에 도달하면 다른 모든 사용자는 보기 전용 환경을 통해 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-138">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="a1caa-139">모임 발표자에게 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="a1caa-139">Impact to meeting presenters</span></span>

<span data-ttu-id="a1caa-140">모임 발표자에 대한 제한 사항:</span><span class="sxs-lookup"><span data-stu-id="a1caa-140">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="a1caa-141">보기 전용 참석자에 대한 정보는 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-141">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="a1caa-142">보기 전용 참석자에 대해 E-discovery를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-142">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="a1caa-143">사용자는 보기 전용 참석자를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-143">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="a1caa-144">모임에서 보기 전용 참석자를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-144">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="a1caa-145">참석자 수는 보기 전용 방의 인원을 제외하고 모임에 있는 사람만 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-145">Attendee count will only reflect the people in the meeting and not the people in the view-only room.</span></span> <span data-ttu-id="a1caa-146">따라서 발표자는 보기 전용 환경의 참석 인원을 정확히 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-146">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="a1caa-147">보기 전용 참석자 환경</span><span class="sxs-lookup"><span data-stu-id="a1caa-147">Experience for view-only attendees</span></span>

<span data-ttu-id="a1caa-148">Teams 보기 전용 환경 참석자들은 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-148">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="a1caa-149">주 Teams 모임의 참가자 듣기</span><span class="sxs-lookup"><span data-stu-id="a1caa-149">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="a1caa-150">현재 발표자에 대한 비디오 피드 보기(현재 발표자가 비디오를 공유하고 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="a1caa-150">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="a1caa-151">공유 데스크톱 기능을 사용하여 공유되고 있는 콘텐츠 보기</span><span class="sxs-lookup"><span data-stu-id="a1caa-151">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="a1caa-152">보기 전용 참석자는 모임에서 다음과 같은 옵션을 경험할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-152">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="a1caa-153">참석자가 설정된 로비 정책 또는 옵션에 따라 대기실을 지나칠 수 있는 권한이 없는 경우 모임에 참가</span><span class="sxs-lookup"><span data-stu-id="a1caa-153">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="a1caa-154">오디오 회의를 사용하여 보기 전용 공간에 참가</span><span class="sxs-lookup"><span data-stu-id="a1caa-154">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="a1caa-155">Microsoft Teams Room System 또는 CVI(Cloud Video Interop) 서비스를 사용하여 보기 전용 공간에 참가</span><span class="sxs-lookup"><span data-stu-id="a1caa-155">Join the view-only room using Microsoft Teams Room system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="a1caa-156">오디오 또는 비디오 공유</span><span class="sxs-lookup"><span data-stu-id="a1caa-156">Share their audio or video.</span></span>
- <span data-ttu-id="a1caa-157">모임 채팅을 보거나 참여하기</span><span class="sxs-lookup"><span data-stu-id="a1caa-157">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="a1caa-158">참가자가 현재 발표자가 아닌 경우 모임 참가자의 비디오 피드 보기</span><span class="sxs-lookup"><span data-stu-id="a1caa-158">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="a1caa-159">기본 공유 PowerPoint 기능 또는 개별 응용 프로그램 공유(데스크톱 공유 외)를 사용하여 공유된 PowerPoint 파일 보기</span><span class="sxs-lookup"><span data-stu-id="a1caa-159">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="a1caa-160">보기 전용 기능 제한 사항</span><span class="sxs-lookup"><span data-stu-id="a1caa-160">View-only feature limitations</span></span>

- <span data-ttu-id="a1caa-161">보기 전용 참석자는 해당 모임의 라이브 캡션 설정에 관계없이 항상 라이브 캡션을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-161">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="a1caa-162">현재 영어 캡션만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-162">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="a1caa-163">보기 전용 참석자에게 스트리밍 기술이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-163">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="a1caa-164">보기 전용 참석자는 참석자 보고서에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-164">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="a1caa-165">보기 전용 참석자는 단일 비디오 환경을 이용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-165">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="a1caa-166">현재 발표자 또는 공유되고 있는 콘텐츠 중 하나는 볼 수 있지만 두가지를 동시에 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-166">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="a1caa-167">현재는 보기 전용 참석자를 위한 **갤러리**, **대형 갤러리**, 또는 **함께 모드** 레이아웃을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-167">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="a1caa-168">보기 전용 참석자의 대기 시간은 일반 참석자와 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-168">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="a1caa-169"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a1caa-169"><sup>1</sup></span></span>

  <span data-ttu-id="a1caa-170"><sup>1</sup> 보기 전용 참석자는 회의에서 비디오 및 오디오가 30초 지연되어 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1caa-170"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
