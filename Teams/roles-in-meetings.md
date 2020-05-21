---
title: Teams 모임의 발표자 및 참가자 기능
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams 모임의 발표자 및 참가자 기능에 대해 알아봅니다.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 11c5858532ade4fd4ed00f7c8f6d1d0c94baeb2d
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321737"
---
<a name="presenter-and-participant-capabilities-in-a-teams-meeting"></a><span data-ttu-id="bec32-103">Teams 모임의 발표자 및 참가자 기능</span><span class="sxs-lookup"><span data-stu-id="bec32-103">Presenter and participant capabilities in a Teams meeting</span></span>
======================================================

<span data-ttu-id="bec32-104">Microsoft Teams 모임은 다양한 참가자 유형을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-104">Microsoft Teams meetings support many participant types.</span></span> <span data-ttu-id="bec32-105">참가자는 조직 내부 또는 외부의 역할에 따라 다양한 모임 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-105">Participants can access various meeting features based on their roles inside or outside of an organization.</span></span>

<span data-ttu-id="bec32-106">사용 가능한 모임 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-106">The available meeting features are:</span></span>

- <span data-ttu-id="bec32-107">채팅(사진 및 스티커 포함)</span><span class="sxs-lookup"><span data-stu-id="bec32-107">Chat (includes photos and stickers)</span></span>
- <span data-ttu-id="bec32-108">회의 노트</span><span class="sxs-lookup"><span data-stu-id="bec32-108">Meeting Notes</span></span>
- <span data-ttu-id="bec32-109">화이트보드</span><span class="sxs-lookup"><span data-stu-id="bec32-109">Whiteboard</span></span>
- <span data-ttu-id="bec32-110">녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="bec32-110">Recording</span></span>
- <span data-ttu-id="bec32-111">파일</span><span class="sxs-lookup"><span data-stu-id="bec32-111">Files</span></span>
- <span data-ttu-id="bec32-112">모임 예약(모임에만 해당)</span><span class="sxs-lookup"><span data-stu-id="bec32-112">Schedule a meeting (for meetings only)</span></span>

<span data-ttu-id="bec32-113">해당 문서에서는 참가자 기능과 모임 기능에 대한 액세스 권한에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-113">This article describes those participant capabilities and what access they have to meeting features.</span></span>

## <a name="presenters-and-organizers"></a><span data-ttu-id="bec32-114">발표자 및 주최자</span><span class="sxs-lookup"><span data-stu-id="bec32-114">Presenters and organizers</span></span>

<span data-ttu-id="bec32-115">발표자와 주최자에게는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-115">Presenters and organizers include the following:</span></span>

- <span data-ttu-id="bec32-116">조직의 발표자</span><span class="sxs-lookup"><span data-stu-id="bec32-116">Presenters from my organization</span></span>
- <span data-ttu-id="bec32-117">다른 조직의 발표자 - 익명 및 외부 참가자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-117">Presenters from other organizations - this includes anonymous and external participants.</span></span> <span data-ttu-id="bec32-118">발표자는 주최자가 지정하며 주최자가 보낸 개인 초대가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-118">Presenters are designated by the organizer and require a personal invite from the organizer.</span></span>

<span data-ttu-id="bec32-119">발표자 및 주최자는 모임 또는 라이브 이벤트의 모든 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-119">Presenters and organizers have access to every feature in a meeting or live event.</span></span>

## <a name="participants"></a><span data-ttu-id="bec32-120">참가자</span><span class="sxs-lookup"><span data-stu-id="bec32-120">Participants</span></span>

<span data-ttu-id="bec32-121">다양한 유형의 모임 참가자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-121">There are several types of meeting participants:</span></span>

- [<span data-ttu-id="bec32-122">테넌트 내 참가자</span><span class="sxs-lookup"><span data-stu-id="bec32-122">In-tenant participant</span></span>](#in-tenant-participant)
- [<span data-ttu-id="bec32-123">게스트 참가자</span><span class="sxs-lookup"><span data-stu-id="bec32-123">Guest participant</span></span>](#guest-participant)
- [<span data-ttu-id="bec32-124">외부(페더레이션) 참가자</span><span class="sxs-lookup"><span data-stu-id="bec32-124">External (federated) participant</span></span>](#external-federated-participant)
- [<span data-ttu-id="bec32-125">익명 참가자</span><span class="sxs-lookup"><span data-stu-id="bec32-125">Anonymous participant</span></span>](#anonymous-participant)

### <a name="in-tenant-participant"></a><span data-ttu-id="bec32-126">테넌트 내 참가자</span><span class="sxs-lookup"><span data-stu-id="bec32-126">In-tenant participant</span></span>

<span data-ttu-id="bec32-127">테넌트 내 참가자는 조직에 속하고 테넌트에 대한 자격 증명을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-127">The in-tenant participant belongs to the organization and has credentials for the tenant.</span></span> <span data-ttu-id="bec32-128">[보안 및 Microsoft Teams](teams-security-guide.md#participant-types)에서 해당 참가자에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-128">Learn more about this participant in [Security and Microsoft Teams](teams-security-guide.md#participant-types).</span></span>

|<span data-ttu-id="bec32-129">모임</span><span class="sxs-lookup"><span data-stu-id="bec32-129">Meeting</span></span>  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| <span data-ttu-id="bec32-130">**기능**</span><span class="sxs-lookup"><span data-stu-id="bec32-130">**Feature**</span></span>        | <span data-ttu-id="bec32-131">사전 모임</span><span class="sxs-lookup"><span data-stu-id="bec32-131">Pre-meeting</span></span> | <span data-ttu-id="bec32-132">모임 중</span><span class="sxs-lookup"><span data-stu-id="bec32-132">In-meeting</span></span> | <span data-ttu-id="bec32-133">모임 후</span><span class="sxs-lookup"><span data-stu-id="bec32-133">Post-meeting</span></span> |
| <span data-ttu-id="bec32-134">채팅</span><span class="sxs-lookup"><span data-stu-id="bec32-134">Chat</span></span> | <span data-ttu-id="bec32-135">예</span><span class="sxs-lookup"><span data-stu-id="bec32-135">Yes</span></span> | <span data-ttu-id="bec32-136">예</span><span class="sxs-lookup"><span data-stu-id="bec32-136">Yes</span></span> | <span data-ttu-id="bec32-137">예</span><span class="sxs-lookup"><span data-stu-id="bec32-137">Yes</span></span> |
| <span data-ttu-id="bec32-138">회의 노트</span><span class="sxs-lookup"><span data-stu-id="bec32-138">Meeting Notes</span></span> | <span data-ttu-id="bec32-139">예</span><span class="sxs-lookup"><span data-stu-id="bec32-139">Yes</span></span> | <span data-ttu-id="bec32-140">예</span><span class="sxs-lookup"><span data-stu-id="bec32-140">Yes</span></span> |<span data-ttu-id="bec32-141">예</span><span class="sxs-lookup"><span data-stu-id="bec32-141">Yes</span></span> |
| <span data-ttu-id="bec32-142">화이트보드</span><span class="sxs-lookup"><span data-stu-id="bec32-142">Whiteboard</span></span> | <span data-ttu-id="bec32-143">예</span><span class="sxs-lookup"><span data-stu-id="bec32-143">Yes</span></span> | <span data-ttu-id="bec32-144">예</span><span class="sxs-lookup"><span data-stu-id="bec32-144">Yes</span></span> |<span data-ttu-id="bec32-145">예</span><span class="sxs-lookup"><span data-stu-id="bec32-145">Yes</span></span> |
| <span data-ttu-id="bec32-146">녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="bec32-146">Recording</span></span> | <span data-ttu-id="bec32-147">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-147">N/A</span></span> |<span data-ttu-id="bec32-148">예</span><span class="sxs-lookup"><span data-stu-id="bec32-148">Yes</span></span> | <span data-ttu-id="bec32-149">예</span><span class="sxs-lookup"><span data-stu-id="bec32-149">Yes</span></span> |
| <span data-ttu-id="bec32-150">파일</span><span class="sxs-lookup"><span data-stu-id="bec32-150">Files</span></span> | <span data-ttu-id="bec32-151">예</span><span class="sxs-lookup"><span data-stu-id="bec32-151">Yes</span></span> | <span data-ttu-id="bec32-152">예</span><span class="sxs-lookup"><span data-stu-id="bec32-152">Yes</span></span> | <span data-ttu-id="bec32-153">예</span><span class="sxs-lookup"><span data-stu-id="bec32-153">Yes</span></span> |
| <span data-ttu-id="bec32-154">모임 예약</span><span class="sxs-lookup"><span data-stu-id="bec32-154">Schedule a meeting</span></span> | <span data-ttu-id="bec32-155">예</span><span class="sxs-lookup"><span data-stu-id="bec32-155">Yes</span></span> | <span data-ttu-id="bec32-156">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-156">N/A</span></span> | <span data-ttu-id="bec32-157">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-157">N/A</span></span> |
|||||||

### <a name="guest-participant"></a><span data-ttu-id="bec32-158">게스트 참가자</span><span class="sxs-lookup"><span data-stu-id="bec32-158">Guest participant</span></span>

<span data-ttu-id="bec32-159">게스트 참가자는 Azure Active Directory B2B 플랫폼을 기반으로 조직의 테넌트에 있는 Teams 또는 기타 리소스에 액세스하도록 초대 받은 다른 조직의 참가자입니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-159">A guest participant is someone from another organization who has been invited to access Teams or other resources in your organization's tenant, based on the Azure Active Directory B2B platform.</span></span> <span data-ttu-id="bec32-160">게스트 사용자를 정기 모임 및 채널 모임에 참가하도록 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-160">Guest users can be invited to join regular meetings and channel meetings.</span></span> <span data-ttu-id="bec32-161">[What the guest experience is like(게스트 환경의 특징)](guest-experience.md#comparison-of-team-member-and-guest-capabilities)에서 게스트 참가자에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-161">Read more about a guest participant in [What the guest experience is like](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span></span>

| <span data-ttu-id="bec32-162">모임</span><span class="sxs-lookup"><span data-stu-id="bec32-162">Meeting</span></span> |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| <span data-ttu-id="bec32-163">**기능**</span><span class="sxs-lookup"><span data-stu-id="bec32-163">**Feature**</span></span>        | <span data-ttu-id="bec32-164">사전 모임</span><span class="sxs-lookup"><span data-stu-id="bec32-164">Pre-meeting</span></span> | <span data-ttu-id="bec32-165">모임 중</span><span class="sxs-lookup"><span data-stu-id="bec32-165">In-meeting</span></span> | <span data-ttu-id="bec32-166">모임 후</span><span class="sxs-lookup"><span data-stu-id="bec32-166">Post-meeting</span></span> |
| <span data-ttu-id="bec32-167">채팅</span><span class="sxs-lookup"><span data-stu-id="bec32-167">Chat</span></span> | <span data-ttu-id="bec32-168">예</span><span class="sxs-lookup"><span data-stu-id="bec32-168">Yes</span></span> | <span data-ttu-id="bec32-169">예</span><span class="sxs-lookup"><span data-stu-id="bec32-169">Yes</span></span> | <span data-ttu-id="bec32-170">예</span><span class="sxs-lookup"><span data-stu-id="bec32-170">Yes</span></span> |
| <span data-ttu-id="bec32-171">회의 노트</span><span class="sxs-lookup"><span data-stu-id="bec32-171">Meeting Notes</span></span> | <span data-ttu-id="bec32-172">예</span><span class="sxs-lookup"><span data-stu-id="bec32-172">Yes</span></span> | <span data-ttu-id="bec32-173">예</span><span class="sxs-lookup"><span data-stu-id="bec32-173">Yes</span></span> | <span data-ttu-id="bec32-174">예</span><span class="sxs-lookup"><span data-stu-id="bec32-174">Yes</span></span> |
| <span data-ttu-id="bec32-175">화이트보드</span><span class="sxs-lookup"><span data-stu-id="bec32-175">Whiteboard</span></span> | <span data-ttu-id="bec32-176">아니요</span><span class="sxs-lookup"><span data-stu-id="bec32-176">No</span></span> | <span data-ttu-id="bec32-177">아니요</span><span class="sxs-lookup"><span data-stu-id="bec32-177">No</span></span> |<span data-ttu-id="bec32-178">아니요</span><span class="sxs-lookup"><span data-stu-id="bec32-178">No</span></span> |
| <span data-ttu-id="bec32-179">녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="bec32-179">Recording</span></span> | <span data-ttu-id="bec32-180">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-180">N/A</span></span> |<span data-ttu-id="bec32-181">아니요</span><span class="sxs-lookup"><span data-stu-id="bec32-181">No</span></span> | <span data-ttu-id="bec32-182">아니요</span><span class="sxs-lookup"><span data-stu-id="bec32-182">No</span></span> |
| <span data-ttu-id="bec32-183">파일</span><span class="sxs-lookup"><span data-stu-id="bec32-183">Files</span></span> | <span data-ttu-id="bec32-184">예</span><span class="sxs-lookup"><span data-stu-id="bec32-184">Yes</span></span> | <span data-ttu-id="bec32-185">예</span><span class="sxs-lookup"><span data-stu-id="bec32-185">Yes</span></span> | <span data-ttu-id="bec32-186">예</span><span class="sxs-lookup"><span data-stu-id="bec32-186">Yes</span></span> |
| <span data-ttu-id="bec32-187">모임 예약</span><span class="sxs-lookup"><span data-stu-id="bec32-187">Schedule a meeting</span></span> | <span data-ttu-id="bec32-188">아니요</span><span class="sxs-lookup"><span data-stu-id="bec32-188">No</span></span> | <span data-ttu-id="bec32-189">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-189">N/A</span></span> | <span data-ttu-id="bec32-190">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-190">N/A</span></span> |
|||||||

### <a name="external-federated-participant"></a><span data-ttu-id="bec32-191">외부(페더레이션) 참가자</span><span class="sxs-lookup"><span data-stu-id="bec32-191">External (federated) participant</span></span>

<span data-ttu-id="bec32-192">외부 참가자는 Teams를 사용하며 모임에 참가하도록 초대되었지만 사용자 조직의 다른 공유 리소스에 대한 액세스 권한이 없는 다른 조직의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-192">An external participant is someone using Teams in another organization who has been invited to join a meeting, but does not otherwise have access to other shared resources from your organization.</span></span> <span data-ttu-id="bec32-193">외부 사용자 참가자는 자신의 조직에서 사용하는 것과 동일한 ID 이름으로 모임 명단에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-193">External user participants appear in the meeting roster with the same identity name as they have in their own organization.</span></span> <span data-ttu-id="bec32-194">[Communicate with users from other organizations(다른 조직의 사용자와 커뮤니케이션)](communicate-with-users-from-other-organizations.md#external-access)에서 외부 참가자에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-194">Read more about an external participant in [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md#external-access).</span></span>

| <span data-ttu-id="bec32-195">모임 (게스트로만 팀에 추가할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="bec32-195">Meeting (Can be added to a team as a guest only)</span></span> ||
|-|-|-|
| <span data-ttu-id="bec32-196">**기능**</span><span class="sxs-lookup"><span data-stu-id="bec32-196">**Feature**</span></span> |||
| <span data-ttu-id="bec32-197">채팅</span><span class="sxs-lookup"><span data-stu-id="bec32-197">Chat</span></span> | <span data-ttu-id="bec32-198">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-198">N/A</span></span> |
| <span data-ttu-id="bec32-199">회의 노트</span><span class="sxs-lookup"><span data-stu-id="bec32-199">Meeting Notes</span></span> | <span data-ttu-id="bec32-200">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-200">N/A</span></span> |  
| <span data-ttu-id="bec32-201">화이트보드</span><span class="sxs-lookup"><span data-stu-id="bec32-201">Whiteboard</span></span> | <span data-ttu-id="bec32-202">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-202">N/A</span></span> |
| <span data-ttu-id="bec32-203">녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="bec32-203">Recording</span></span> | <span data-ttu-id="bec32-204">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-204">N/A</span></span> |  
| <span data-ttu-id="bec32-205">파일</span><span class="sxs-lookup"><span data-stu-id="bec32-205">Files</span></span> | <span data-ttu-id="bec32-206">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-206">N/A</span></span> |
| <span data-ttu-id="bec32-207">모임 예약</span><span class="sxs-lookup"><span data-stu-id="bec32-207">Schedule a meeting</span></span> | <span data-ttu-id="bec32-208">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-208">N/A</span></span> |
|||

### <a name="anonymous-participant"></a><span data-ttu-id="bec32-209">익명 참가자</span><span class="sxs-lookup"><span data-stu-id="bec32-209">Anonymous participant</span></span>

<span data-ttu-id="bec32-210">익명 참가자는 외부 사용자와 유사하지만 ID가 모임에 프로젝션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-210">The anonymous participant is like an external user, but their identity is not projected into the meeting.</span></span> <span data-ttu-id="bec32-211">참가 시 별칭을 직접 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-211">At join time, they manually enter a nickname.</span></span> <span data-ttu-id="bec32-212">[보안 및 Microsoft Teams](teams-security-guide.md#participant-types)에서 익명 참가자에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bec32-212">Learn more about an anonymous participant in [Security and Microsoft Teams](teams-security-guide.md#participant-types).</span></span>

| <span data-ttu-id="bec32-213">모임</span><span class="sxs-lookup"><span data-stu-id="bec32-213">Meeting</span></span>  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| <span data-ttu-id="bec32-214">**기능**</span><span class="sxs-lookup"><span data-stu-id="bec32-214">**Feature**</span></span>        | <span data-ttu-id="bec32-215">사전 모임</span><span class="sxs-lookup"><span data-stu-id="bec32-215">Pre-meeting</span></span> | <span data-ttu-id="bec32-216">모임 중</span><span class="sxs-lookup"><span data-stu-id="bec32-216">In-meeting</span></span> | <span data-ttu-id="bec32-217">모임 후</span><span class="sxs-lookup"><span data-stu-id="bec32-217">Post-meeting</span></span> |
| <span data-ttu-id="bec32-218">채팅</span><span class="sxs-lookup"><span data-stu-id="bec32-218">Chat</span></span> | <span data-ttu-id="bec32-219">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-219">N/A</span></span> | <span data-ttu-id="bec32-220">아니요</span><span class="sxs-lookup"><span data-stu-id="bec32-220">No</span></span> | <span data-ttu-id="bec32-221">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-221">N/A</span></span> |
| <span data-ttu-id="bec32-222">회의 노트</span><span class="sxs-lookup"><span data-stu-id="bec32-222">Meeting Notes</span></span> | <span data-ttu-id="bec32-223">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-223">N/A</span></span> | <span data-ttu-id="bec32-224">아니요</span><span class="sxs-lookup"><span data-stu-id="bec32-224">No</span></span> | <span data-ttu-id="bec32-225">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-225">N/A</span></span> |
| <span data-ttu-id="bec32-226">화이트보드</span><span class="sxs-lookup"><span data-stu-id="bec32-226">Whiteboard</span></span> | <span data-ttu-id="bec32-227">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-227">N/A</span></span> | <span data-ttu-id="bec32-228">아니요</span><span class="sxs-lookup"><span data-stu-id="bec32-228">No</span></span> | <span data-ttu-id="bec32-229">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-229">N/A</span></span> |
| <span data-ttu-id="bec32-230">녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="bec32-230">Recording</span></span> | <span data-ttu-id="bec32-231">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-231">N/A</span></span> | <span data-ttu-id="bec32-232">아니요</span><span class="sxs-lookup"><span data-stu-id="bec32-232">No</span></span> | <span data-ttu-id="bec32-233">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-233">N/A</span></span> |
| <span data-ttu-id="bec32-234">파일</span><span class="sxs-lookup"><span data-stu-id="bec32-234">Files</span></span> | <span data-ttu-id="bec32-235">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-235">N/A</span></span> | <span data-ttu-id="bec32-236">아니요</span><span class="sxs-lookup"><span data-stu-id="bec32-236">No</span></span> | <span data-ttu-id="bec32-237">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-237">N/A</span></span> |
| <span data-ttu-id="bec32-238">모임 예약</span><span class="sxs-lookup"><span data-stu-id="bec32-238">Schedule a meeting</span></span> | <span data-ttu-id="bec32-239">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-239">N/A</span></span> | <span data-ttu-id="bec32-240">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-240">N/A</span></span> | <span data-ttu-id="bec32-241">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bec32-241">N/A</span></span> |
|||||||

## <a name="related-topics"></a><span data-ttu-id="bec32-242">관련 항목</span><span class="sxs-lookup"><span data-stu-id="bec32-242">Related topics</span></span>

[<span data-ttu-id="bec32-243">보안 및 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bec32-243">Security and Microsoft Teams</span></span>](teams-security-guide.md)

[<span data-ttu-id="bec32-244">Teams의 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="bec32-244">Guest access in Teams</span></span>](guest-access.md)
