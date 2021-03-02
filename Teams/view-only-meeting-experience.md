---
title: 보기 전용 모임 환경
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 관리자, 발표자 및 참석자에 대한 Teams 보기 전용 모임 경험에 대해 자세히 알아보기
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ed7221192fdc3588856755b8be651065fdbf15ab
ms.sourcegitcommit: 79b19b326ef40bf04af03021a7c6506fdd9417ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2021
ms.locfileid: "50397563"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="2b91a-103">Teams 보기 전용 모임 환경</span><span class="sxs-lookup"><span data-stu-id="2b91a-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="2b91a-104">보기 전용 모임 환경은 2021년 3월 초에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-104">View-only meeting experience will be available in early March 2021.</span></span> <span data-ttu-id="2b91a-105">이 기능은 2021년 3월 1일을 기본 OFF로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-105">This feature will be enabled on March 1,2021 as default OFF.</span></span> <span data-ttu-id="2b91a-106">이 기능을 기본값으로 설정하려면 해당 날짜 이후에 기본 정책을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-106">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="2b91a-107">PowerShell을 사용하여 정책을 사용하도록 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled` 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-107">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled`.</span></span>

> [!Note]
> <span data-ttu-id="2b91a-108">20,000명 참석자에 대한 보기 전용 환경이 일시적으로 증가했지만 2021년 6월 30일에는 10,000명으로 지원이 되감습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-108">We've temporarily increased view-only experience for 20,000 attendees, but we'll revert support to 10,000 attendees on June 30, 2021.</span></span>

<span data-ttu-id="2b91a-109">Microsoft Teams를 사용하면 최대 10,000명이 Teams 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-109">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="2b91a-110">주 모임의 용량에 도달하면 추가 참석자는 보기 전용 환경과 함께 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-110">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="2b91a-111">모임에 먼저 참가하는 참석자는 모임 용량까지 전체 Teams 모임 환경을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-111">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="2b91a-112">오디오 및 비디오를 공유하고, 공유 비디오를 보고, 모임 채팅에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-112">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="2b91a-113">주 모임 용량에 도달한 후에 참가하는 참석자는 보기 전용 환경을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-113">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="2b91a-114">참석자에 대한 전체 Android 및 iOS 모바일 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-114">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="2b91a-115">모임에 채팅하고 전화를 걸 수 있는 사용자 수에 대한 현재 제한은 WW에서 300, GCC, GCC High 및 DoD에서는 250입니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-115">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="2b91a-116">뷰 전용 환경은 기본적으로 E3/E5/A3/A5 SKU가 있는 모든 이끌이에 대해 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-116">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="2b91a-117">추가 구성 또는 설정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-117">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="2b91a-118">Teams 보기 전용 환경 사용 안 하세요</span><span class="sxs-lookup"><span data-stu-id="2b91a-118">Disable Teams view-only experience</span></span>

<span data-ttu-id="2b91a-119">관리자는 PowerShell을 사용하여 보기 전용 환경을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-119">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="2b91a-120">앞으로 관리자는 Teams 관리 센터에서 보기 전용 환경을 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-120">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="2b91a-121">사용자에게 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="2b91a-121">Impact to users</span></span>

<span data-ttu-id="2b91a-122">사용자의 환경은 여러 요인에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-122">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="2b91a-123">주 모임의 용량에 도달하면 다음 중 한 가지가 true인 경우 참석자는 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-123">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="2b91a-124">관리자가 Teams 보기 전용 환경을 사용하지 않도록 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-124">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="2b91a-125">참석자에 로비를 무시할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-125">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="2b91a-126">주 모임의 용량에 도달하면 모임 이끌이와 발표자가 모임 용량에 도달하고 새 참석자가 보기 전용 참석자에 참가할 것임이 알리는 배너가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-126">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![이끌이 및 발표자에 대한 Teams 클라이언트 및 배너 message](media/chat-and-banner-message.png)

<span data-ttu-id="2b91a-128">주 모임의 용량에 도달하면 모임 참석자는 참가 전 화면에서 보기 전용 모드로 참가하고 있는 것으로 알려 갑니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-128">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams 사전 참가 화면 및 참가자가 보기 전용 모드로 참가할 것 을 알려준 메시지](media/view-only-pre-join-screen.png)

<span data-ttu-id="2b91a-130">공백이 있는 경우 사용자는 항상 주 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-130">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="2b91a-131">주 모임이 용량에 도달하고 하나 이상의 참석자들이 주 모임을 나가면 주 모임에 사용 가능한 용량이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-131">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="2b91a-132">모임에 참가(또는 다시 참가)하는 참석자는 용량에 다시 도달할 때까지 주 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-132">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="2b91a-133">보기 전용 환경인 참석자들은 자동으로 주 모임으로 승격되지 않습니다. 현재는 주 모임으로 수동으로 승격할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-133">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="2b91a-134">발표자/참석자 역할이 설정되지 않은 경우 주 모임의 공백은 선착반으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-134">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="2b91a-135">모임 용량에 도달하면 다른 모든 사용자가 보기 전용 환경과 함께 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-135">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="2b91a-136">모임 발표자에 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="2b91a-136">Impact to meeting presenters</span></span>

<span data-ttu-id="2b91a-137">모임 발표자에 대한 제한은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-137">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="2b91a-138">보기 전용 참석자에 대한 정보가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-138">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="2b91a-139">보기 전용 참석자에 대한 E-discovery는 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-139">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="2b91a-140">보기 전용 참석자만 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-140">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="2b91a-141">모임에서 보기 전용 참석자만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-141">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="2b91a-142">참석자 수는 오버플로 룸의 사람이 아니라 모임에 있는 사람만 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-142">Attendee count will only reflect the people in the meeting and not the people in the overflow room.</span></span> <span data-ttu-id="2b91a-143">따라서 발표자는 보기 전용 환경의 정확한 수를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-143">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="2b91a-144">보기 전용 참석자 환경</span><span class="sxs-lookup"><span data-stu-id="2b91a-144">Experience for view-only attendees</span></span>

<span data-ttu-id="2b91a-145">Teams 보기 전용 환경을 통해 참석자들은 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-145">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="2b91a-146">주 Teams 모임의 참가자를 들어 듣습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-146">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="2b91a-147">활성 화자에 대한 비디오 피드를 참조하세요(활성 스피커가 비디오를 공유하는 경우).</span><span class="sxs-lookup"><span data-stu-id="2b91a-147">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="2b91a-148">공유 데스크톱 기능을 사용하여 공유되는 콘텐츠를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b91a-148">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="2b91a-149">보기 전용 참석자들은 모임에서 다음 옵션을 경험할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-149">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="2b91a-150">참석자 설정 로비 정책 또는 옵션에 따라 로비를 우회할 수 있는 권한이 없는 경우 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-150">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="2b91a-151">오디오 회의를 통해 오버플로 룸에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-151">Join the Overflow Room via Audio Conferencing.</span></span>
- <span data-ttu-id="2b91a-152">Microsoft Teams Room 시스템 또는 CVI(Cloud Video Interop) 서비스를 통해 오버플로 룸에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-152">Join the Overflow Room via Microsoft Teams Room system or via Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="2b91a-153">오디오 또는 비디오를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-153">Share their audio or video.</span></span>
- <span data-ttu-id="2b91a-154">모임 채팅을 보거나 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-154">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="2b91a-155">참가자가 활성 발표자인 경우를 위해 모임 참가자의 비디오 피드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b91a-155">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="2b91a-156">기본 공유 PowerPoint 기능 또는 개별 애플리케이션 공유(데스크톱 공유 외)를 사용하여 공유되는 PowerPoint 파일을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-156">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="2b91a-157">보기 전용 기능 제한 사항</span><span class="sxs-lookup"><span data-stu-id="2b91a-157">View-only feature limitations</span></span>

- <span data-ttu-id="2b91a-158">보기 전용 참석자는 해당 모임에 대한 라이브 캡션 설정에 관계없이 항상 라이브 캡션을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-158">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="2b91a-159">현재 영어 캡션만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-159">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="2b91a-160">보기 전용 참석자는 스트리밍 기술을 통해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-160">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="2b91a-161">보기 전용 참석자는 참석 보고서에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-161">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="2b91a-162">보기 전용 참석자는 단일 비디오 환경을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-162">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="2b91a-163">활성 스피커 또는 공유되는 콘텐츠를 볼 수 있지만 둘 다 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-163">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="2b91a-164">현재는 보기 전용 참석자에 대한 **갤러리,** 큰 갤러리 **또는** 함께 모드 레이아웃을 지원하지 않습니다. </span><span class="sxs-lookup"><span data-stu-id="2b91a-164">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="2b91a-165">보기 전용 참석자에는 일반 참석자와 동일한 대기 시간이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-165">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="2b91a-166"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2b91a-166"><sup>1</sup></span></span>

  <span data-ttu-id="2b91a-167"><sup>1</sup> 보기 전용 참석자는 모임의 30초 비디오 및 오디오 지연에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b91a-167"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="2b91a-168">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2b91a-168">Related topics</span></span>

- [<span data-ttu-id="2b91a-169">Teams용 고급 통신 추가 기능</span><span class="sxs-lookup"><span data-stu-id="2b91a-169">Advanced communications add-on for Teams</span></span>](teams-add-on-licensing/advanced-communications.md)
- [<span data-ttu-id="2b91a-170">Teams의 제한과 사양</span><span class="sxs-lookup"><span data-stu-id="2b91a-170">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)
