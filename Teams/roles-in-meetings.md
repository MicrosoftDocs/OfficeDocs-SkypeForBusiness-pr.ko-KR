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
ms.openlocfilehash: c8433d4caa0defbe83114ac4027c10b6bf61a725
ms.sourcegitcommit: 862ba1d2b3bd4622b1b0baa15096c29c591cc6c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2020
ms.locfileid: "44702693"
---
<a name="presenter-and-participant-capabilities-in-a-teams-meeting"></a><span data-ttu-id="51a38-103">Teams 모임의 발표자 및 참가자 기능</span><span class="sxs-lookup"><span data-stu-id="51a38-103">Presenter and participant capabilities in a Teams meeting</span></span>
======================================================

<span data-ttu-id="51a38-104">Microsoft Teams 모임은 다양한 참가자 유형을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-104">Microsoft Teams meetings support many participant types.</span></span> <span data-ttu-id="51a38-105">참가자는 조직 내부 또는 외부의 역할에 따라 다양한 모임 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-105">Participants can access various meeting features based on their roles inside or outside of an organization.</span></span>

<span data-ttu-id="51a38-106">사용 가능한 모임 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-106">The available meeting features are:</span></span>

- <span data-ttu-id="51a38-107">채팅(사진 및 스티커 포함)</span><span class="sxs-lookup"><span data-stu-id="51a38-107">Chat (includes photos and stickers)</span></span>
- <span data-ttu-id="51a38-108">회의 노트</span><span class="sxs-lookup"><span data-stu-id="51a38-108">Meeting Notes</span></span>
- <span data-ttu-id="51a38-109">화이트보드</span><span class="sxs-lookup"><span data-stu-id="51a38-109">Whiteboard</span></span>
- <span data-ttu-id="51a38-110">녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="51a38-110">Recording</span></span>
- <span data-ttu-id="51a38-111">파일</span><span class="sxs-lookup"><span data-stu-id="51a38-111">Files</span></span>
- <span data-ttu-id="51a38-112">모임 예약(모임에만 해당)</span><span class="sxs-lookup"><span data-stu-id="51a38-112">Schedule a meeting (for meetings only)</span></span>

<span data-ttu-id="51a38-113">해당 문서에서는 참가자 기능과 모임 기능에 대한 액세스 권한에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-113">This article describes those participant capabilities and what access they have to meeting features.</span></span>

## <a name="presenters-and-organizers"></a><span data-ttu-id="51a38-114">발표자 및 주최자</span><span class="sxs-lookup"><span data-stu-id="51a38-114">Presenters and organizers</span></span>

<span data-ttu-id="51a38-115">발표자와 주최자에게는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-115">Presenters and organizers include the following:</span></span>

- <span data-ttu-id="51a38-116">조직의 발표자</span><span class="sxs-lookup"><span data-stu-id="51a38-116">Presenters from my organization</span></span>
- <span data-ttu-id="51a38-117">다른 조직의 발표자 - 익명 및 외부 참가자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-117">Presenters from other organizations - this includes anonymous and external participants.</span></span> <span data-ttu-id="51a38-118">발표자는 주최자가 지정하며 주최자가 보낸 개인 초대가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-118">Presenters are designated by the organizer and require a personal invite from the organizer.</span></span>

<span data-ttu-id="51a38-119">발표자 및 주최자는 모임 또는 라이브 이벤트의 모든 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-119">Presenters and organizers have access to every feature in a meeting or live event.</span></span>

## <a name="participants"></a><span data-ttu-id="51a38-120">참가자</span><span class="sxs-lookup"><span data-stu-id="51a38-120">Participants</span></span>

<span data-ttu-id="51a38-121">다양한 유형의 모임 참가자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-121">There are several types of meeting participants:</span></span>

- [<span data-ttu-id="51a38-122">테넌트 내 참가자</span><span class="sxs-lookup"><span data-stu-id="51a38-122">In-tenant participant</span></span>](#in-tenant-participant)
- [<span data-ttu-id="51a38-123">게스트 참가자</span><span class="sxs-lookup"><span data-stu-id="51a38-123">Guest participant</span></span>](#guest-participant)
- [<span data-ttu-id="51a38-124">외부(페더레이션) 참가자</span><span class="sxs-lookup"><span data-stu-id="51a38-124">External (federated) participant</span></span>](#external-federated-participant)
- [<span data-ttu-id="51a38-125">익명 참가자</span><span class="sxs-lookup"><span data-stu-id="51a38-125">Anonymous participant</span></span>](#anonymous-participant)

### <a name="in-tenant-participant"></a><span data-ttu-id="51a38-126">테넌트 내 참가자</span><span class="sxs-lookup"><span data-stu-id="51a38-126">In-tenant participant</span></span>

<span data-ttu-id="51a38-127">테넌트 내 참가자는 조직에 속하고 테넌트에 대한 자격 증명을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-127">The in-tenant participant belongs to the organization and has credentials for the tenant.</span></span> <span data-ttu-id="51a38-128">[보안 및 Microsoft Teams](teams-security-guide.md#participant-types)에서 해당 참가자에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-128">Learn more about this participant in [Security and Microsoft Teams](teams-security-guide.md#participant-types).</span></span>

|<span data-ttu-id="51a38-129">모임</span><span class="sxs-lookup"><span data-stu-id="51a38-129">Meeting</span></span>  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| <span data-ttu-id="51a38-130">**기능**</span><span class="sxs-lookup"><span data-stu-id="51a38-130">**Feature**</span></span>        | <span data-ttu-id="51a38-131">사전 모임</span><span class="sxs-lookup"><span data-stu-id="51a38-131">Pre-meeting</span></span> | <span data-ttu-id="51a38-132">모임 중</span><span class="sxs-lookup"><span data-stu-id="51a38-132">In-meeting</span></span> | <span data-ttu-id="51a38-133">모임 후</span><span class="sxs-lookup"><span data-stu-id="51a38-133">Post-meeting</span></span> |
| <span data-ttu-id="51a38-134">채팅</span><span class="sxs-lookup"><span data-stu-id="51a38-134">Chat</span></span> | <span data-ttu-id="51a38-135">예</span><span class="sxs-lookup"><span data-stu-id="51a38-135">Yes</span></span> | <span data-ttu-id="51a38-136">예</span><span class="sxs-lookup"><span data-stu-id="51a38-136">Yes</span></span> | <span data-ttu-id="51a38-137">예</span><span class="sxs-lookup"><span data-stu-id="51a38-137">Yes</span></span> |
| <span data-ttu-id="51a38-138">회의 노트</span><span class="sxs-lookup"><span data-stu-id="51a38-138">Meeting Notes</span></span> | <span data-ttu-id="51a38-139">예</span><span class="sxs-lookup"><span data-stu-id="51a38-139">Yes</span></span> | <span data-ttu-id="51a38-140">예</span><span class="sxs-lookup"><span data-stu-id="51a38-140">Yes</span></span> |<span data-ttu-id="51a38-141">예</span><span class="sxs-lookup"><span data-stu-id="51a38-141">Yes</span></span> |
| <span data-ttu-id="51a38-142">화이트보드</span><span class="sxs-lookup"><span data-stu-id="51a38-142">Whiteboard</span></span> | <span data-ttu-id="51a38-143">예</span><span class="sxs-lookup"><span data-stu-id="51a38-143">Yes</span></span> | <span data-ttu-id="51a38-144">예</span><span class="sxs-lookup"><span data-stu-id="51a38-144">Yes</span></span> |<span data-ttu-id="51a38-145">예</span><span class="sxs-lookup"><span data-stu-id="51a38-145">Yes</span></span> |
| <span data-ttu-id="51a38-146">녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="51a38-146">Recording</span></span> | <span data-ttu-id="51a38-147">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-147">N/A</span></span> |<span data-ttu-id="51a38-148">예</span><span class="sxs-lookup"><span data-stu-id="51a38-148">Yes</span></span> | <span data-ttu-id="51a38-149">예</span><span class="sxs-lookup"><span data-stu-id="51a38-149">Yes</span></span> |
| <span data-ttu-id="51a38-150">파일</span><span class="sxs-lookup"><span data-stu-id="51a38-150">Files</span></span> | <span data-ttu-id="51a38-151">예</span><span class="sxs-lookup"><span data-stu-id="51a38-151">Yes</span></span> | <span data-ttu-id="51a38-152">예</span><span class="sxs-lookup"><span data-stu-id="51a38-152">Yes</span></span> | <span data-ttu-id="51a38-153">예</span><span class="sxs-lookup"><span data-stu-id="51a38-153">Yes</span></span> |
| <span data-ttu-id="51a38-154">모임 예약</span><span class="sxs-lookup"><span data-stu-id="51a38-154">Schedule a meeting</span></span> | <span data-ttu-id="51a38-155">예</span><span class="sxs-lookup"><span data-stu-id="51a38-155">Yes</span></span> | <span data-ttu-id="51a38-156">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-156">N/A</span></span> | <span data-ttu-id="51a38-157">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-157">N/A</span></span> |
|||||||

### <a name="guest-participant"></a><span data-ttu-id="51a38-158">게스트 참가자</span><span class="sxs-lookup"><span data-stu-id="51a38-158">Guest participant</span></span>

<span data-ttu-id="51a38-159">게스트 참가자는 Azure Active Directory B2B 플랫폼을 기반으로 조직의 테넌트에 있는 Teams 또는 기타 리소스에 액세스하도록 초대 받은 다른 조직의 참가자입니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-159">A guest participant is someone from another organization who has been invited to access Teams or other resources in your organization's tenant, based on the Azure Active Directory B2B platform.</span></span> <span data-ttu-id="51a38-160">게스트 사용자를 정기 모임 및 채널 모임에 참가하도록 초대할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-160">Guest users can be invited to join regular meetings and channel meetings.</span></span> <span data-ttu-id="51a38-161">[What the guest experience is like(게스트 환경의 특징)](guest-experience.md#comparison-of-team-member-and-guest-capabilities)에서 게스트 참가자에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-161">Read more about a guest participant in [What the guest experience is like](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span></span>

| <span data-ttu-id="51a38-162">모임</span><span class="sxs-lookup"><span data-stu-id="51a38-162">Meeting</span></span> |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| <span data-ttu-id="51a38-163">**기능**</span><span class="sxs-lookup"><span data-stu-id="51a38-163">**Feature**</span></span>        | <span data-ttu-id="51a38-164">사전 모임</span><span class="sxs-lookup"><span data-stu-id="51a38-164">Pre-meeting</span></span> | <span data-ttu-id="51a38-165">모임 중</span><span class="sxs-lookup"><span data-stu-id="51a38-165">In-meeting</span></span> | <span data-ttu-id="51a38-166">모임 후</span><span class="sxs-lookup"><span data-stu-id="51a38-166">Post-meeting</span></span> |
| <span data-ttu-id="51a38-167">채팅</span><span class="sxs-lookup"><span data-stu-id="51a38-167">Chat</span></span> | <span data-ttu-id="51a38-168">예</span><span class="sxs-lookup"><span data-stu-id="51a38-168">Yes</span></span> | <span data-ttu-id="51a38-169">예</span><span class="sxs-lookup"><span data-stu-id="51a38-169">Yes</span></span> | <span data-ttu-id="51a38-170">예</span><span class="sxs-lookup"><span data-stu-id="51a38-170">Yes</span></span> |
| <span data-ttu-id="51a38-171">회의 노트</span><span class="sxs-lookup"><span data-stu-id="51a38-171">Meeting Notes</span></span> | <span data-ttu-id="51a38-172">예</span><span class="sxs-lookup"><span data-stu-id="51a38-172">Yes</span></span> | <span data-ttu-id="51a38-173">예</span><span class="sxs-lookup"><span data-stu-id="51a38-173">Yes</span></span> | <span data-ttu-id="51a38-174">예</span><span class="sxs-lookup"><span data-stu-id="51a38-174">Yes</span></span> |
| <span data-ttu-id="51a38-175">화이트보드</span><span class="sxs-lookup"><span data-stu-id="51a38-175">Whiteboard</span></span> | <span data-ttu-id="51a38-176">아니요</span><span class="sxs-lookup"><span data-stu-id="51a38-176">No</span></span> | <span data-ttu-id="51a38-177">아니요</span><span class="sxs-lookup"><span data-stu-id="51a38-177">No</span></span> |<span data-ttu-id="51a38-178">아니요</span><span class="sxs-lookup"><span data-stu-id="51a38-178">No</span></span> |
| <span data-ttu-id="51a38-179">녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="51a38-179">Recording</span></span> | <span data-ttu-id="51a38-180">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-180">N/A</span></span> |<span data-ttu-id="51a38-181">아니요</span><span class="sxs-lookup"><span data-stu-id="51a38-181">No</span></span> | <span data-ttu-id="51a38-182">아니요</span><span class="sxs-lookup"><span data-stu-id="51a38-182">No</span></span> |
| <span data-ttu-id="51a38-183">파일</span><span class="sxs-lookup"><span data-stu-id="51a38-183">Files</span></span> | <span data-ttu-id="51a38-184">예</span><span class="sxs-lookup"><span data-stu-id="51a38-184">Yes</span></span> | <span data-ttu-id="51a38-185">예</span><span class="sxs-lookup"><span data-stu-id="51a38-185">Yes</span></span> | <span data-ttu-id="51a38-186">예</span><span class="sxs-lookup"><span data-stu-id="51a38-186">Yes</span></span> |
| <span data-ttu-id="51a38-187">모임 예약</span><span class="sxs-lookup"><span data-stu-id="51a38-187">Schedule a meeting</span></span> | <span data-ttu-id="51a38-188">아니요</span><span class="sxs-lookup"><span data-stu-id="51a38-188">No</span></span> | <span data-ttu-id="51a38-189">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-189">N/A</span></span> | <span data-ttu-id="51a38-190">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-190">N/A</span></span> |
|||||||

### <a name="external-federated-participant"></a><span data-ttu-id="51a38-191">외부(페더레이션) 참가자</span><span class="sxs-lookup"><span data-stu-id="51a38-191">External (federated) participant</span></span>

<span data-ttu-id="51a38-192">외부 참가자는 Teams를 사용하며 모임에 참가하도록 초대되었지만 사용자 조직의 다른 공유 리소스에 대한 액세스 권한이 없는 다른 조직의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-192">An external participant is someone using Teams in another organization who has been invited to join a meeting, but does not otherwise have access to other shared resources from your organization.</span></span> <span data-ttu-id="51a38-193">외부 사용자 참가자는 자신의 조직에서 사용하는 것과 동일한 ID 이름으로 모임 명단에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-193">External user participants appear in the meeting roster with the same identity name as they have in their own organization.</span></span> <span data-ttu-id="51a38-194">[Communicate with users from other organizations(다른 조직의 사용자와 커뮤니케이션)](communicate-with-users-from-other-organizations.md#external-access)에서 외부 참가자에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-194">Read more about an external participant in [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md#external-access).</span></span>

| <span data-ttu-id="51a38-195">모임</span><span class="sxs-lookup"><span data-stu-id="51a38-195">Meeting</span></span> ||
|-|-|-|
| <span data-ttu-id="51a38-196">**기능**</span><span class="sxs-lookup"><span data-stu-id="51a38-196">**Feature**</span></span> |||
| <span data-ttu-id="51a38-197">채팅</span><span class="sxs-lookup"><span data-stu-id="51a38-197">Chat</span></span> | <span data-ttu-id="51a38-198">예</span><span class="sxs-lookup"><span data-stu-id="51a38-198">Yes</span></span> |
| <span data-ttu-id="51a38-199">회의 노트</span><span class="sxs-lookup"><span data-stu-id="51a38-199">Meeting Notes</span></span> | <span data-ttu-id="51a38-200">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-200">N/A</span></span> |  
| <span data-ttu-id="51a38-201">화이트보드</span><span class="sxs-lookup"><span data-stu-id="51a38-201">Whiteboard</span></span> | <span data-ttu-id="51a38-202">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-202">N/A</span></span> |
| <span data-ttu-id="51a38-203">녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="51a38-203">Recording</span></span> | <span data-ttu-id="51a38-204">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-204">N/A</span></span> |  
| <span data-ttu-id="51a38-205">파일</span><span class="sxs-lookup"><span data-stu-id="51a38-205">Files</span></span> | <span data-ttu-id="51a38-206">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-206">N/A</span></span> |
| <span data-ttu-id="51a38-207">모임 예약</span><span class="sxs-lookup"><span data-stu-id="51a38-207">Schedule a meeting</span></span> | <span data-ttu-id="51a38-208">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-208">N/A</span></span> |
|||

### <a name="anonymous-participant"></a><span data-ttu-id="51a38-209">익명 참가자</span><span class="sxs-lookup"><span data-stu-id="51a38-209">Anonymous participant</span></span>

<span data-ttu-id="51a38-210">익명 참가자는 외부 사용자와 유사하지만 ID가 모임에 프로젝션되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-210">The anonymous participant is like an external user, but their identity is not projected into the meeting.</span></span> <span data-ttu-id="51a38-211">참가 시 별칭을 직접 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-211">At join time, they manually enter a nickname.</span></span> <span data-ttu-id="51a38-212">[보안 및 Microsoft Teams](teams-security-guide.md#participant-types)에서 익명 참가자에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="51a38-212">Learn more about an anonymous participant in [Security and Microsoft Teams](teams-security-guide.md#participant-types).</span></span>

| <span data-ttu-id="51a38-213">모임</span><span class="sxs-lookup"><span data-stu-id="51a38-213">Meeting</span></span>  | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| <span data-ttu-id="51a38-214">**기능**</span><span class="sxs-lookup"><span data-stu-id="51a38-214">**Feature**</span></span>        | <span data-ttu-id="51a38-215">사전 모임</span><span class="sxs-lookup"><span data-stu-id="51a38-215">Pre-meeting</span></span> | <span data-ttu-id="51a38-216">모임 중</span><span class="sxs-lookup"><span data-stu-id="51a38-216">In-meeting</span></span> | <span data-ttu-id="51a38-217">모임 후</span><span class="sxs-lookup"><span data-stu-id="51a38-217">Post-meeting</span></span> |
| <span data-ttu-id="51a38-218">채팅</span><span class="sxs-lookup"><span data-stu-id="51a38-218">Chat</span></span> | <span data-ttu-id="51a38-219">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-219">N/A</span></span> | <span data-ttu-id="51a38-220">예</span><span class="sxs-lookup"><span data-stu-id="51a38-220">Yes</span></span> | <span data-ttu-id="51a38-221">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-221">N/A</span></span> |
| <span data-ttu-id="51a38-222">회의 노트</span><span class="sxs-lookup"><span data-stu-id="51a38-222">Meeting Notes</span></span> | <span data-ttu-id="51a38-223">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-223">N/A</span></span> | <span data-ttu-id="51a38-224">아니요</span><span class="sxs-lookup"><span data-stu-id="51a38-224">No</span></span> | <span data-ttu-id="51a38-225">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-225">N/A</span></span> |
| <span data-ttu-id="51a38-226">화이트보드</span><span class="sxs-lookup"><span data-stu-id="51a38-226">Whiteboard</span></span> | <span data-ttu-id="51a38-227">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-227">N/A</span></span> | <span data-ttu-id="51a38-228">아니요</span><span class="sxs-lookup"><span data-stu-id="51a38-228">No</span></span> | <span data-ttu-id="51a38-229">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-229">N/A</span></span> |
| <span data-ttu-id="51a38-230">녹음/녹화</span><span class="sxs-lookup"><span data-stu-id="51a38-230">Recording</span></span> | <span data-ttu-id="51a38-231">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-231">N/A</span></span> | <span data-ttu-id="51a38-232">아니요</span><span class="sxs-lookup"><span data-stu-id="51a38-232">No</span></span> | <span data-ttu-id="51a38-233">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-233">N/A</span></span> |
| <span data-ttu-id="51a38-234">파일</span><span class="sxs-lookup"><span data-stu-id="51a38-234">Files</span></span> | <span data-ttu-id="51a38-235">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-235">N/A</span></span> | <span data-ttu-id="51a38-236">아니요</span><span class="sxs-lookup"><span data-stu-id="51a38-236">No</span></span> | <span data-ttu-id="51a38-237">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-237">N/A</span></span> |
| <span data-ttu-id="51a38-238">모임 예약</span><span class="sxs-lookup"><span data-stu-id="51a38-238">Schedule a meeting</span></span> | <span data-ttu-id="51a38-239">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-239">N/A</span></span> | <span data-ttu-id="51a38-240">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-240">N/A</span></span> | <span data-ttu-id="51a38-241">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51a38-241">N/A</span></span> |
|||||||

## <a name="related-topics"></a><span data-ttu-id="51a38-242">관련 항목</span><span class="sxs-lookup"><span data-stu-id="51a38-242">Related topics</span></span>

[<span data-ttu-id="51a38-243">보안 및 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="51a38-243">Security and Microsoft Teams</span></span>](teams-security-guide.md)

[<span data-ttu-id="51a38-244">Teams의 게스트 액세스</span><span class="sxs-lookup"><span data-stu-id="51a38-244">Guest access in Teams</span></span>](guest-access.md)
