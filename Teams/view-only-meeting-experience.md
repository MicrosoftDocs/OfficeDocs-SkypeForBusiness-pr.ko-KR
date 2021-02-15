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
description: 관리자, 발표자 및 참석자용 Teams 보기 전용 모임 경험에 대해 자세히 보기
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 54bbb3c00aae8a2785e867be9614f8509ca9344d
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237458"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="c9fdb-103">Teams 보기 전용 모임 환경</span><span class="sxs-lookup"><span data-stu-id="c9fdb-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="c9fdb-104">보기 전용 모임 환경은 2021년 3월 초에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-104">View-only meeting experience will be available in early March 2021.</span></span>

> [!Note]
> <span data-ttu-id="c9fdb-105">20,000명 참석자에 대한 보기 전용 환경이 일시적으로 증가했지만 2021년 6월 30일에는 10,000명으로 지원이 되감습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-105">We've temporarily increased view-only experience for 20,000 attendees, but we'll revert support to 10,000 attendees on June 30, 2021.</span></span>

<span data-ttu-id="c9fdb-106">Microsoft Teams를 사용하면 최대 10,000명까지 Teams 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-106">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="c9fdb-107">주 모임의 용량에 도달하면 추가 참석자는 보기 전용 환경으로 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-107">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="c9fdb-108">모임에 먼저 참가하는 참석자는 모임의 용량까지 전체 Teams 모임 환경을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-108">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="c9fdb-109">오디오 및 비디오를 공유하고, 공유 비디오를 보고, 모임 채팅에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-109">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="c9fdb-110">주 모임 용량에 도달한 후 참가하는 참석자는 보기 전용 환경을 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-110">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="c9fdb-111">참석자에 대한 전체 Android 및 iOS 모바일 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-111">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="c9fdb-112">모임에 채팅하고 전화를 걸 수 있는 사용자 수에 대한 현재 제한은 WW에서는 300, GCC, GCC High 및 DoD에서는 250개입니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-112">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="c9fdb-113">보기 전용 환경은 E3/E5/A3/A5 SKU가 있는 모든 이끌이에 대해 기본적으로 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-113">The view-only experience is enabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="c9fdb-114">추가 구성 또는 설정이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-114">No further configuration or setup is required.</span></span>

### <a name="disable-teams-view-only-experience"></a><span data-ttu-id="c9fdb-115">Teams 보기 전용 환경 사용 안</span><span class="sxs-lookup"><span data-stu-id="c9fdb-115">Disable Teams view-only experience</span></span>

<span data-ttu-id="c9fdb-116">관리자는 PowerShell을 사용하여 보기 전용 환경을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-116">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="c9fdb-117">관리자는 앞으로 Teams 관리 센터에서 보기 전용 환경을 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-117">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="c9fdb-118">사용자에게 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="c9fdb-118">Impact to users</span></span>

<span data-ttu-id="c9fdb-119">사용자의 환경은 여러 요인에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-119">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="c9fdb-120">주 모임의 용량에 도달하면 다음 중 한 가지가 참인 경우 참석자는 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-120">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="c9fdb-121">관리자가 Teams 보기 전용 환경을 사용하지 않도록 설정했습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-121">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="c9fdb-122">참석자에는 로비를 우회할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-122">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="c9fdb-123">주 모임의 용량에 도달하면 모임 이끌이와 발표자는 모임 용량에 도달하고 새 참석자가 보기 전용 참석자에 참가할 것임을 알리는 배너를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-123">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![이끌이 및 발표자용 Teams 클라이언트 및 배너](media/chat-and-banner-message.png)

<span data-ttu-id="c9fdb-125">주 모임의 용량에 도달하면 모임 참석자는 참가 전 화면에서 보기 전용 모드로 참가 중임에 대해 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-125">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams 사전 참가 화면 및 참가자에게 보기 전용 모드로 참가할 것 을 알려준 메시지](media/view-only-pre-join-screen.png)

<span data-ttu-id="c9fdb-127">공간이 있는 경우 사용자는 항상 주 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-127">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="c9fdb-128">주 모임이 용량에 도달하고 한명 이상의 참석자들이 주 모임을 나가는 경우 주 모임에는 사용 가능한 용량이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-128">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="c9fdb-129">모임에 참가(또는 다시 참가)하는 참석자는 용량에 다시 도달할 때까지 주 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-129">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="c9fdb-130">보기 전용 환경의 참석자도 자동으로 주 모임으로 승격되지는 못하며 현재는 주 모임으로 수동으로 승격될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-130">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="c9fdb-131">발표자/참석자 역할이 설정되지 않은 경우 주 모임의 공백은 선착오차로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-131">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="c9fdb-132">모임 용량에 도달하면 다른 모든 사용자가 보기 전용 환경으로 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-132">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="c9fdb-133">모임 발표자에 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="c9fdb-133">Impact to meeting presenters</span></span>

<span data-ttu-id="c9fdb-134">모임 옵션에서 발표자로 명시적으로 표시된 사용자를 위해 일반 모임의 공간을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-134">We'll reserve space in the normal meeting for users explicitly indicated as presenters in the meeting options.</span></span> <span data-ttu-id="c9fdb-135">발표자는 자리를 비우고 나중에 모임에 다시 참석하면 발표자는 모임에 참석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-135">If a presenter leaves and then later rejoins the meeting, they'll be let into the meeting as a presenter.</span></span>

<span data-ttu-id="c9fdb-136">모임 발표자에 대한 제한은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-136">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="c9fdb-137">보기 전용 참석자에 대한 정보는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-137">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="c9fdb-138">보기 전용 참석자에 대한 E-discovery는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-138">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="c9fdb-139">사용자는 보기 전용 참석자만 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-139">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="c9fdb-140">모임에서 보기 전용 참석자만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-140">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="c9fdb-141">참석자 수는 오버플로 회의실에 있는 사람이 아닌 모임에 있는 사람만 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-141">Attendee count will only reflect the people in the meeting and not the people in the overflow room.</span></span> <span data-ttu-id="c9fdb-142">따라서 발표자는 보기 전용 환경의 정확한 수를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-142">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="c9fdb-143">보기 전용 참석자 환경</span><span class="sxs-lookup"><span data-stu-id="c9fdb-143">Experience for view-only attendees</span></span>

<span data-ttu-id="c9fdb-144">Teams 보기 전용 환경을 통해 참석자도 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-144">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="c9fdb-145">주 Teams 모임의 참가자를 듣습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-145">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="c9fdb-146">활성 화자에 대한 비디오 피드를 참조하세요(활성 화자에서 비디오를 공유하는 경우).</span><span class="sxs-lookup"><span data-stu-id="c9fdb-146">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="c9fdb-147">공유 데스크톱 기능을 사용하여 공유되는 콘텐츠를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-147">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="c9fdb-148">보기 전용 참석자에서는 모임에서 다음 옵션을 경험할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-148">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="c9fdb-149">참석자에 대기실 정책 또는 옵션 설정에 따라 로비를 우회할 수 있는 권한이 없는 경우 모임에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-149">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="c9fdb-150">오디오 회의를 통해 오버플로 방에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-150">Join the Overflow Room via Audio Conferencing.</span></span>
- <span data-ttu-id="c9fdb-151">Microsoft Teams Room 시스템 또는 CVI(클라우드 비디오 Interop) 서비스를 통해 오버플로 방에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-151">Join the Overflow Room via Microsoft Teams Room system or via Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="c9fdb-152">Teams Android 모바일 앱을 통해 오버플로 방에 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-152">Join the Overflow Room via the Teams Android mobile app.</span></span>
- <span data-ttu-id="c9fdb-153">오디오 또는 비디오를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-153">Share their audio or video.</span></span>
- <span data-ttu-id="c9fdb-154">모임 채팅을 보거나 참가합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-154">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="c9fdb-155">참가자가 활성 발표자이지 않은 한 모임 참가자의 비디오 피드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-155">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="c9fdb-156">기본 공유 PowerPoint 기능 또는 개별 응용 프로그램 공유(데스크톱 공유 외)를 사용하여 공유되는 PowerPoint 파일을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-156">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="c9fdb-157">보기 전용 기능 제한 사항</span><span class="sxs-lookup"><span data-stu-id="c9fdb-157">View-only feature limitations</span></span>

- <span data-ttu-id="c9fdb-158">보기 전용 참석자는 해당 모임의 라이브 캡션 설정에 관계없이 항상 라이브 캡션을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-158">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="c9fdb-159">현재 영어 캡션만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-159">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="c9fdb-160">보기 전용 참석자는 스트리밍 기술로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-160">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="c9fdb-161">보기 전용 참석자는 참석자 보고서에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-161">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="c9fdb-162">보기 전용 참석자는 단일 비디오 환경을 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-162">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="c9fdb-163">활성 화자 또는 공유되는 콘텐츠를 볼 수 있지만 둘 다 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-163">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="c9fdb-164">현재는 보기 전용 참석자에 대한 **갤러리,** 큰 갤러리 또는 함께 모드 레이아웃을 지원하지 않습니다. </span><span class="sxs-lookup"><span data-stu-id="c9fdb-164">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="c9fdb-165">보기 전용 참석자에는 일반 참석자와 대기 시간이 동일하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-165">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="c9fdb-166"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c9fdb-166"><sup>1</sup></span></span>

  <span data-ttu-id="c9fdb-167"><sup>1회의</sup> 보기 전용 참석자는 모임의 30초 비디오 및 오디오 지연을 하게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c9fdb-167"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="c9fdb-168">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c9fdb-168">Related topics</span></span>

- [<span data-ttu-id="c9fdb-169">Teams용 고급 통신 추가 기능</span><span class="sxs-lookup"><span data-stu-id="c9fdb-169">Advanced communications add-on for Teams</span></span>](teams-add-on-licensing/advanced-communications.md)
- [<span data-ttu-id="c9fdb-170">Teams의 제한과 사양</span><span class="sxs-lookup"><span data-stu-id="c9fdb-170">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)
