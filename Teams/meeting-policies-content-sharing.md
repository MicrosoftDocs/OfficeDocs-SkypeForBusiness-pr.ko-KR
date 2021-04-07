---
title: 콘텐츠 공유를 위한 모임 정책 관리
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
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: 콘텐츠 공유를 위해 Teams에서 모임 정책 설정을 관리하는 방법을 알아보겠습니다.
ms.openlocfilehash: 7b318ad0025d6c68b041c65d8fbb78cbfbc87723
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598775"
---
# <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="1ca8a-103">모임 정책 설정 - 콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="1ca8a-103">Meeting policy settings - Content sharing</span></span>

<span data-ttu-id="1ca8a-104"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="1ca8a-104"><a name="bkcontentsharing"> </a></span></span>

<span data-ttu-id="1ca8a-105">이 문서에서는 콘텐츠 공유와 관련된 다음 모임 정책 설정을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-105">This article describes the following meeting policy settings related to content sharing:</span></span>

- [<span data-ttu-id="1ca8a-106">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="1ca8a-106">Screen sharing mode</span></span>](#screen-sharing-mode)
- [<span data-ttu-id="1ca8a-107">참가자가 제어를 제공하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="1ca8a-107">Allow a participant to give or request control</span></span>](#allow-a-participant-to-give-or-request-control)
- [<span data-ttu-id="1ca8a-108">외부 참가자가 제어를 제공하거나 요청하도록 허용</span><span class="sxs-lookup"><span data-stu-id="1ca8a-108">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="1ca8a-109">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="1ca8a-109">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="1ca8a-110">화이트보드 허용</span><span class="sxs-lookup"><span data-stu-id="1ca8a-110">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="1ca8a-111">공유 노트 허용</span><span class="sxs-lookup"><span data-stu-id="1ca8a-111">Allow shared notes</span></span>](#allow-shared-notes)

## <a name="screen-sharing-mode"></a><span data-ttu-id="1ca8a-112">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="1ca8a-112">Screen sharing mode</span></span>

<span data-ttu-id="1ca8a-113">이 설정은 이끌이 및 사용자당 정책의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-113">This setting is a combination of a per-organizer and per-user policies.</span></span> <span data-ttu-id="1ca8a-114">이 설정은 사용자의 모임에서 데스크톱 및 창 공유가 허용되는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-114">This setting controls whether desktop and window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="1ca8a-115">할당된 정책이 없는 모임 참가자(예: 익명, 게스트, B2B 및 페더리드 참가자)는 모임 이끌이의 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-115">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="1ca8a-116">값 설정</span><span class="sxs-lookup"><span data-stu-id="1ca8a-116">Setting value</span></span> |<span data-ttu-id="1ca8a-117">동작</span><span class="sxs-lookup"><span data-stu-id="1ca8a-117">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="1ca8a-118">**전체 화면**</span><span class="sxs-lookup"><span data-stu-id="1ca8a-118">**Entire screen**</span></span>    | <span data-ttu-id="1ca8a-119">모임에서 전체 데스크톱 공유 및 애플리케이션 공유가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-119">Full desktop sharing and application sharing are allowed in the meeting</span></span> |
|<span data-ttu-id="1ca8a-120">**단일 애플리케이션**</span><span class="sxs-lookup"><span data-stu-id="1ca8a-120">**Single application**</span></span>   | <span data-ttu-id="1ca8a-121">모임에서 애플리케이션 공유가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-121">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="1ca8a-122">**사용하지 않도록 설정**</span><span class="sxs-lookup"><span data-stu-id="1ca8a-122">**Disabled**</span></span>     |<span data-ttu-id="1ca8a-123">모임에서 화면 공유 및 애플리케이션 공유가 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-123">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="1ca8a-124">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-124">Let's look at the following example.</span></span>

|<span data-ttu-id="1ca8a-125">사용자</span><span class="sxs-lookup"><span data-stu-id="1ca8a-125">User</span></span> |<span data-ttu-id="1ca8a-126">모임 정책</span><span class="sxs-lookup"><span data-stu-id="1ca8a-126">Meeting policy</span></span> |<span data-ttu-id="1ca8a-127">화면 공유 모드</span><span class="sxs-lookup"><span data-stu-id="1ca8a-127">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1ca8a-128">Daniela</span><span class="sxs-lookup"><span data-stu-id="1ca8a-128">Daniela</span></span>  | <span data-ttu-id="1ca8a-129">전역</span><span class="sxs-lookup"><span data-stu-id="1ca8a-129">Global</span></span>   | <span data-ttu-id="1ca8a-130">전체 화면</span><span class="sxs-lookup"><span data-stu-id="1ca8a-130">Entire screen</span></span> |
|<span data-ttu-id="1ca8a-131">Amanda</span><span class="sxs-lookup"><span data-stu-id="1ca8a-131">Amanda</span></span>   | <span data-ttu-id="1ca8a-132">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1ca8a-132">Location1MeetingPolicy</span></span>  | <span data-ttu-id="1ca8a-133">사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="1ca8a-133">Disabled</span></span> |

<span data-ttu-id="1ca8a-134">Daniela에서 호스팅하는 모임을 사용하면 모임 참가자가 전체 화면 또는 특정 애플리케이션을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-134">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="1ca8a-135">Amanda가 Daniela의 모임에 참가하는 경우 Amanda는 자신의 정책 설정이 비활성화되어 화면 또는 특정 애플리케이션을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-135">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="1ca8a-136">Amanda가 호스팅하는 모임에서 할당된 화면 공유 모드 정책에 관계없이 누구도 자신의 화면 또는 단일 애플리케이션을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-136">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span>  <span data-ttu-id="1ca8a-137">따라서 Daniela는 Amanda의 모임에서 자신의 화면 또는 단일 애플리케이션을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-137">Consequently, Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="1ca8a-138">현재 사용자는 Google Chrome을 사용하는 경우 Teams 모임에서 비디오를 재생하거나 화면을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-138">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

## <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="1ca8a-139">참가자가 제어를 제공하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="1ca8a-139">Allow a participant to give or request control</span></span>

<span data-ttu-id="1ca8a-140">이 설정은 사용자당 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-140">This setting is a per-user policy.</span></span> <span data-ttu-id="1ca8a-141">이 설정은 사용자가 공유 데스크톱 또는 창을 다른 모임 참가자에게 제어할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-141">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="1ca8a-142">컨트롤을 제공하기 위해 화면 맨 위에 마우스를 다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-142">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="1ca8a-143">사용자에 대해 이 설정이 켜져 있는 경우 공유 세션의 맨 위에 컨트롤 제공 옵션이 표시됩니다. </span><span class="sxs-lookup"><span data-stu-id="1ca8a-143">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![제어권 제공 옵션을 보여 주는 스크린샷](media/meeting-policies-give-control.png)

<span data-ttu-id="1ca8a-145">사용자에 대한 설정이 꺼져  있는 경우 제어권 제공 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-145">If the setting is turned off for the user, the **Give Control** option isn't available.</span></span>

![제어권 제공 옵션을 사용할 수 없는 경우를 보여 주는 스크린샷](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="1ca8a-147">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-147">Let's look at the following example.</span></span>

|<span data-ttu-id="1ca8a-148">사용자</span><span class="sxs-lookup"><span data-stu-id="1ca8a-148">User</span></span> |<span data-ttu-id="1ca8a-149">모임 정책</span><span class="sxs-lookup"><span data-stu-id="1ca8a-149">Meeting policy</span></span>  |<span data-ttu-id="1ca8a-150">참가자가 제어를 제공하거나 요청할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="1ca8a-150">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1ca8a-151">Daniela</span><span class="sxs-lookup"><span data-stu-id="1ca8a-151">Daniela</span></span>   | <span data-ttu-id="1ca8a-152">전역</span><span class="sxs-lookup"><span data-stu-id="1ca8a-152">Global</span></span>   | <span data-ttu-id="1ca8a-153">에서</span><span class="sxs-lookup"><span data-stu-id="1ca8a-153">On</span></span>       |
|<span data-ttu-id="1ca8a-154">Babek</span><span class="sxs-lookup"><span data-stu-id="1ca8a-154">Babek</span></span>    | <span data-ttu-id="1ca8a-155">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1ca8a-155">Location1MeetingPolicy</span></span>        | <span data-ttu-id="1ca8a-156">끄기</span><span class="sxs-lookup"><span data-stu-id="1ca8a-156">Off</span></span>   |

<span data-ttu-id="1ca8a-157">Daniela는 Babek가 조직한 모임에서 다른 참가자에게 공유 데스크톱 또는 창을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-157">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek.</span></span> <span data-ttu-id="1ca8a-158">그러나 Babek는 다른 참가자에게 제어를 줄 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-158">However, Babek can't give control to other participants.</span></span>

<span data-ttu-id="1ca8a-159">PowerShell을 사용하여 제어 요청을 제어하거나 수락할 수 있는 사용자 제어를 위해 AllowParticipantGiveRequestControl cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-159">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="1ca8a-160">공유하는 동안 공유 콘텐츠를 주고 제어하려면 두 당사자가 Teams 데스크톱 클라이언트를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-160">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="1ca8a-161">컨트롤은 어느 쪽이든 브라우저에서 Teams를 실행 중인 경우 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-161">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="1ca8a-162">이것은 해결하려고 하는 기술적 제한 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-162">This is due to a technical limitation that we're planning to fix.</span></span>

## <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="1ca8a-163">외부 참가자가 제어를 제공하거나 요청하도록 허용</span><span class="sxs-lookup"><span data-stu-id="1ca8a-163">Allow an external participant to give or request control</span></span>

<span data-ttu-id="1ca8a-164">이 설정은 사용자당 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-164">This setting is a per-user policy.</span></span> <span data-ttu-id="1ca8a-165">조직이 사용자에 대해 이 정책을 설정한지 여부는 모임 이끌이가 설정한 대상에 관계없이 외부 참가자가 할 수 있는 작업을 제어하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-165">Whether an organization has set this policy for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="1ca8a-166">이 매개 변수는 외부 참가자가 조직의 모임 정책 내에서 설정한 공유자가 설정한 대상에 따라 공유자 화면의 제어 또는 요청 제어를 부여할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-166">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="1ca8a-167">Teams 모임의 외부 참가자는 다음과 같이 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-167">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="1ca8a-168">익명 사용자</span><span class="sxs-lookup"><span data-stu-id="1ca8a-168">Anonymous user</span></span>
- <span data-ttu-id="1ca8a-169">게스트 사용자</span><span class="sxs-lookup"><span data-stu-id="1ca8a-169">Guest users</span></span>  
- <span data-ttu-id="1ca8a-170">B2B 사용자</span><span class="sxs-lookup"><span data-stu-id="1ca8a-170">B2B user</span></span>
- <span data-ttu-id="1ca8a-171">페더리드 사용자</span><span class="sxs-lookup"><span data-stu-id="1ca8a-171">Federated user</span></span>  

<span data-ttu-id="1ca8a-172">페더링된 사용자가 공유하는 동안 외부 사용자에게 제어를  줄 수 있는지 여부는 외부 참가자가 조직에서 제어 설정을 제공하거나 요청할 수 있도록 허용에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-172">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="1ca8a-173">PowerShell을 사용하여 외부 참가자가 제어 요청을 제어하거나 수락할 수 있는지 여부를 제어하기 위해 AllowExternalParticipantGiveRequestControl cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-173">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="1ca8a-174">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="1ca8a-174">Allow PowerPoint sharing</span></span>

<span data-ttu-id="1ca8a-175">사용자당 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-175">This is a per-user policy.</span></span> <span data-ttu-id="1ca8a-176">이 설정은 사용자가 모임에서 PowerPoint 슬라이드 데크를 공유할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-176">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="1ca8a-177">익명, 게스트 및 페더리드 사용자를 포함한 외부 사용자는 모임 이끌이의 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-177">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="1ca8a-178">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-178">Let's look at the following example.</span></span>

|<span data-ttu-id="1ca8a-179">사용자</span><span class="sxs-lookup"><span data-stu-id="1ca8a-179">User</span></span> |<span data-ttu-id="1ca8a-180">모임 정책</span><span class="sxs-lookup"><span data-stu-id="1ca8a-180">Meeting policy</span></span>  |<span data-ttu-id="1ca8a-181">PowerPoint 공유 허용</span><span class="sxs-lookup"><span data-stu-id="1ca8a-181">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1ca8a-182">Daniela</span><span class="sxs-lookup"><span data-stu-id="1ca8a-182">Daniela</span></span>   | <span data-ttu-id="1ca8a-183">전역</span><span class="sxs-lookup"><span data-stu-id="1ca8a-183">Global</span></span>   | <span data-ttu-id="1ca8a-184">에서</span><span class="sxs-lookup"><span data-stu-id="1ca8a-184">On</span></span>       |
|<span data-ttu-id="1ca8a-185">Amanda</span><span class="sxs-lookup"><span data-stu-id="1ca8a-185">Amanda</span></span>   | <span data-ttu-id="1ca8a-186">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1ca8a-186">Location1MeetingPolicy</span></span>        | <span data-ttu-id="1ca8a-187">끄기</span><span class="sxs-lookup"><span data-stu-id="1ca8a-187">Off</span></span>   |

<span data-ttu-id="1ca8a-188">Amanda는 모임 이끌이인 경우에도 모임에서 PowerPoint 슬라이드 데크를 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-188">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="1ca8a-189">Daniela는 Amanda에서 모임을 구성하는 경우에도 PowerPoint 슬라이드 데크를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-189">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="1ca8a-190">Amanda는 PowerPoint 슬라이드 데크를 공유할 수 없는 경우에도 모임에서 다른 사람이 공유하는 PowerPoint 슬라이드 데크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-190">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

## <a name="allow-whiteboard"></a><span data-ttu-id="1ca8a-191">화이트보드 허용</span><span class="sxs-lookup"><span data-stu-id="1ca8a-191">Allow whiteboard</span></span>

<span data-ttu-id="1ca8a-192">이 설정은 사용자당 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-192">This setting is a per-user policy.</span></span> <span data-ttu-id="1ca8a-193">이 설정은 사용자가 모임에서 화이트보드를 공유할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-193">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="1ca8a-194">익명, B2B 및 페더리드 사용자를 포함한 외부 사용자는 모임 이끌이의 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-194">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="1ca8a-195">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-195">Let's look at the following example.</span></span>

|<span data-ttu-id="1ca8a-196">사용자</span><span class="sxs-lookup"><span data-stu-id="1ca8a-196">User</span></span> |<span data-ttu-id="1ca8a-197">모임 정책</span><span class="sxs-lookup"><span data-stu-id="1ca8a-197">Meeting policy</span></span>  |<span data-ttu-id="1ca8a-198">화이트보드 허용</span><span class="sxs-lookup"><span data-stu-id="1ca8a-198">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="1ca8a-199">Daniela</span><span class="sxs-lookup"><span data-stu-id="1ca8a-199">Daniela</span></span>   | <span data-ttu-id="1ca8a-200">전역</span><span class="sxs-lookup"><span data-stu-id="1ca8a-200">Global</span></span>   | <span data-ttu-id="1ca8a-201">에서</span><span class="sxs-lookup"><span data-stu-id="1ca8a-201">On</span></span>       |
|<span data-ttu-id="1ca8a-202">Amanda</span><span class="sxs-lookup"><span data-stu-id="1ca8a-202">Amanda</span></span>   | <span data-ttu-id="1ca8a-203">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1ca8a-203">Location1MeetingPolicy</span></span>        | <span data-ttu-id="1ca8a-204">끄기</span><span class="sxs-lookup"><span data-stu-id="1ca8a-204">Off</span></span>   |

<span data-ttu-id="1ca8a-205">Amanda는 모임 이끌이인 경우에도 모임에서 화이트보드를 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-205">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="1ca8a-206">Daniela는 모임이 Amanda에서 구성되어 있는 경우에도 화이트보드를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-206">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

## <a name="allow-shared-notes"></a><span data-ttu-id="1ca8a-207">공유 노트 허용</span><span class="sxs-lookup"><span data-stu-id="1ca8a-207">Allow shared notes</span></span>

<span data-ttu-id="1ca8a-208">이 설정은 사용자당 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-208">This setting is a per-user policy.</span></span> <span data-ttu-id="1ca8a-209">이 설정은 사용자가 모임에서 노트를 만들고 공유할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-209">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="1ca8a-210">익명, B2B 및 페더리드 사용자를 포함한 외부 사용자는 모임 이끌이의 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-210">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="1ca8a-211">모임 **노트** 탭은 현재 20명 미만의 참가자가 있는 모임에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-211">The **Meeting Notes** tab is currently only supported in meetings that have fewer than 20 participants.</span></span>

<span data-ttu-id="1ca8a-212">다음 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-212">Let's look at the following example.</span></span>

|<span data-ttu-id="1ca8a-213">사용자</span><span class="sxs-lookup"><span data-stu-id="1ca8a-213">User</span></span> |<span data-ttu-id="1ca8a-214">모임 정책</span><span class="sxs-lookup"><span data-stu-id="1ca8a-214">Meeting policy</span></span>  |<span data-ttu-id="1ca8a-215">공유 노트 허용</span><span class="sxs-lookup"><span data-stu-id="1ca8a-215">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1ca8a-216">Daniela</span><span class="sxs-lookup"><span data-stu-id="1ca8a-216">Daniela</span></span>   | <span data-ttu-id="1ca8a-217">전역</span><span class="sxs-lookup"><span data-stu-id="1ca8a-217">Global</span></span>   | <span data-ttu-id="1ca8a-218">에서</span><span class="sxs-lookup"><span data-stu-id="1ca8a-218">On</span></span>       |
|<span data-ttu-id="1ca8a-219">Amanda</span><span class="sxs-lookup"><span data-stu-id="1ca8a-219">Amanda</span></span>   | <span data-ttu-id="1ca8a-220">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="1ca8a-220">Location1MeetingPolicy</span></span> | <span data-ttu-id="1ca8a-221">끄기</span><span class="sxs-lookup"><span data-stu-id="1ca8a-221">Off</span></span> |

<span data-ttu-id="1ca8a-222">Daniela는 Amanda의 모임에서 메모를 작성할 수 있으며 Amanda는 모임에서 메모를 기록할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca8a-222">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>




## <a name="related-topics"></a><span data-ttu-id="1ca8a-223">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1ca8a-223">Related topics</span></span>

- [<span data-ttu-id="1ca8a-224">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="1ca8a-224">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="1ca8a-225">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="1ca8a-225">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="1ca8a-226">사용자로부터 RestrictedAnonymousAccesss Teams 모임 정책 제거</span><span class="sxs-lookup"><span data-stu-id="1ca8a-226">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
