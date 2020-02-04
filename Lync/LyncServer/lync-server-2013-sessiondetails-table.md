---
title: 'Lync Server 2013: SessionDetails 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b68c50fc17199c68a69c5a7c6dd6abc8a5bd1dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="49865-102">Lync Server 2013의 SessionDetails 테이블</span><span class="sxs-lookup"><span data-stu-id="49865-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49865-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="49865-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="49865-104">각 레코드는 하나의 피어 투 피어 세션을 나타내며,이는 VoIP 전화 통화, 2-파티 IM 세션 또는 기타 세션 유형이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49865-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="49865-105">[Lync Server 2013의 미디어 테이블](lync-server-2013-media-table.md) 을 사용 하 여 테이블 조인을 수행 하 여이 세션과 관련 된 각 미디어의 세부 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49865-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="49865-106">Microsoft Lync Server 2013에서 사용 되는 SessionDetails 테이블에서 IsUser1IntegratedWithDeskPhone 및 IsUser2IntegratedWithDeskPhone 필드가 삭제 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49865-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49865-107">열</span><span class="sxs-lookup"><span data-stu-id="49865-107">Column</span></span></th>
<th><span data-ttu-id="49865-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="49865-108">Data Type</span></span></th>
<th><span data-ttu-id="49865-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="49865-109">Key/Index</span></span></th>
<th><span data-ttu-id="49865-110">세부적인</span><span class="sxs-lookup"><span data-stu-id="49865-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49865-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="49865-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-112">dmtf</span><span class="sxs-lookup"><span data-stu-id="49865-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="49865-113">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="49865-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-114">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-114">Time of session request.</span></span> <span data-ttu-id="49865-115">세션을 고유 하 게 식별 하는 <strong>Sessionidseq</strong> 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49865-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="49865-116">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="49865-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-118">int</span><span class="sxs-lookup"><span data-stu-id="49865-118">int</span></span></p></td>
<td><p><span data-ttu-id="49865-119">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="49865-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-120">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-120">ID number to identify the session.</span></span> <span data-ttu-id="49865-121">세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다. \* 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-122"><strong>Legredir</strong></span><span class="sxs-lookup"><span data-stu-id="49865-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-123">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="49865-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-124">여러 세션을 연관 시킬 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="49865-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-126">dmtf</span><span class="sxs-lookup"><span data-stu-id="49865-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="49865-127">외부</span><span class="sxs-lookup"><span data-stu-id="49865-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-128">현재 세션으로 대체 된 대화 상자를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="49865-129">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="49865-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-131">int</span><span class="sxs-lookup"><span data-stu-id="49865-131">int</span></span></p></td>
<td><p><span data-ttu-id="49865-132">외부</span><span class="sxs-lookup"><span data-stu-id="49865-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-133">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-133">ID number to identify the session.</span></span> <span data-ttu-id="49865-134"><strong>ReplacesDialogIdTime</strong> 와 함께 사용 하 여이 세션으로 대체 되는 세션을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="49865-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="49865-135">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="49865-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-137">int</span><span class="sxs-lookup"><span data-stu-id="49865-137">int</span></span></p></td>
<td><p><span data-ttu-id="49865-138">외부</span><span class="sxs-lookup"><span data-stu-id="49865-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-139">세션의 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-139">ID of one user in the session.</span></span> <span data-ttu-id="49865-140">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="49865-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-142">int</span><span class="sxs-lookup"><span data-stu-id="49865-142">int</span></span></p></td>
<td><p><span data-ttu-id="49865-143">외부</span><span class="sxs-lookup"><span data-stu-id="49865-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-144">세션의 다른 사용자에 대 한 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-144">ID of the other user in the session.</span></span> <span data-ttu-id="49865-145">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="49865-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-147">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="49865-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-148">세션에서 첫 번째 사용자가 사용 하는 끝점을 식별 하는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="49865-149">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49865-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="49865-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="49865-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-152">세션에서 두 번째 사용자가 사용 하는 끝점을 식별 하는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="49865-153">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49865-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="49865-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-155">int</span><span class="sxs-lookup"><span data-stu-id="49865-155">int</span></span></p></td>
<td><p><span data-ttu-id="49865-156">외부</span><span class="sxs-lookup"><span data-stu-id="49865-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-157">SIP 요청의 원본에서 사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="49865-158">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="49865-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-160">int</span><span class="sxs-lookup"><span data-stu-id="49865-160">int</span></span></p></td>
<td><p><span data-ttu-id="49865-161">외부</span><span class="sxs-lookup"><span data-stu-id="49865-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-162">세션을 시작한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-162">ID of the user who started the session.</span></span> <span data-ttu-id="49865-163">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="49865-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-165">int</span><span class="sxs-lookup"><span data-stu-id="49865-165">int</span></span></p></td>
<td><p><span data-ttu-id="49865-166">외부</span><span class="sxs-lookup"><span data-stu-id="49865-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-167">호출자가 대신 하는 사용자의 ID를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="49865-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="49865-168">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="49865-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-170">int</span><span class="sxs-lookup"><span data-stu-id="49865-170">int</span></span></p></td>
<td><p><span data-ttu-id="49865-171">외부</span><span class="sxs-lookup"><span data-stu-id="49865-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-172">통화를 참조 하는 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="49865-173">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="49865-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-175">int</span><span class="sxs-lookup"><span data-stu-id="49865-175">int</span></span></p></td>
<td><p><span data-ttu-id="49865-176">외부</span><span class="sxs-lookup"><span data-stu-id="49865-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-177">이 세션에 사용 되는 프런트 엔드 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="49865-178">자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 서버 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="49865-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-180">int</span><span class="sxs-lookup"><span data-stu-id="49865-180">int</span></span></p></td>
<td><p><span data-ttu-id="49865-181">외부</span><span class="sxs-lookup"><span data-stu-id="49865-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-182">세션이 캡처된 풀의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="49865-183">자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="49865-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-185">int</span><span class="sxs-lookup"><span data-stu-id="49865-185">int</span></span></p></td>
<td><p><span data-ttu-id="49865-186">외부</span><span class="sxs-lookup"><span data-stu-id="49865-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-187">세션에 사용 되는 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-187">Content type used in the session.</span></span> <span data-ttu-id="49865-188">자세한 내용은 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013의 Contenttypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="49865-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-190">int</span><span class="sxs-lookup"><span data-stu-id="49865-190">int</span></span></p></td>
<td><p><span data-ttu-id="49865-191">외부</span><span class="sxs-lookup"><span data-stu-id="49865-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-192">User1이 사용 하는 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-192">Client version used by User1.</span></span> <span data-ttu-id="49865-193">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 Clientversions 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="49865-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-195">int</span><span class="sxs-lookup"><span data-stu-id="49865-195">int</span></span></p></td>
<td><p><span data-ttu-id="49865-196">외부</span><span class="sxs-lookup"><span data-stu-id="49865-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-197">%2에서 사용 하는 클라이언트 버전.</span><span class="sxs-lookup"><span data-stu-id="49865-197">Client version used by User2.</span></span> <span data-ttu-id="49865-198">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 Clientversions 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="49865-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-200">int</span><span class="sxs-lookup"><span data-stu-id="49865-200">int</span></span></p></td>
<td><p><span data-ttu-id="49865-201">외부</span><span class="sxs-lookup"><span data-stu-id="49865-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-202">User1이 사용 하는 Edge 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-202">Edge Server used by User1.</span></span> <span data-ttu-id="49865-203">자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="49865-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-205">int</span><span class="sxs-lookup"><span data-stu-id="49865-205">int</span></span></p></td>
<td><p><span data-ttu-id="49865-206">외부</span><span class="sxs-lookup"><span data-stu-id="49865-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-207">%2에서 사용 하는 Edge 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-207">Edge Server used by User2.</span></span> <span data-ttu-id="49865-208">자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="49865-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-210">다소</span><span class="sxs-lookup"><span data-stu-id="49865-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-211">User1이 내부에서 로그온 되었는지 여부</span><span class="sxs-lookup"><span data-stu-id="49865-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="49865-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-213">다소</span><span class="sxs-lookup"><span data-stu-id="49865-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-214">%2이 (가) 내부에서 로그온 되었는지 여부</span><span class="sxs-lookup"><span data-stu-id="49865-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="49865-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-216">dmtf</span><span class="sxs-lookup"><span data-stu-id="49865-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-217">첫 번째 초대 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-217">The time of the first INVITE request.</span></span> <span data-ttu-id="49865-218">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="49865-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="49865-219">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="49865-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="49865-220">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="49865-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="49865-221">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="49865-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="49865-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-223">dmtf</span><span class="sxs-lookup"><span data-stu-id="49865-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-224">첫 번째 초대 메시지에 대 한 응답 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="49865-225">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="49865-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="49865-226">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="49865-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="49865-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-228">int</span><span class="sxs-lookup"><span data-stu-id="49865-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-229">세션 초대에 대 한 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-229">SIP response code to the session invitation.</span></span> <span data-ttu-id="49865-230">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="49865-230">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="49865-231">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="49865-231">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="49865-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-233">int</span><span class="sxs-lookup"><span data-stu-id="49865-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-234">SIP 헤더에서 진단 ID를 캡처 했습니다.</span><span class="sxs-lookup"><span data-stu-id="49865-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="49865-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-236">int</span><span class="sxs-lookup"><span data-stu-id="49865-236">int</span></span></p></td>
<td><p><span data-ttu-id="49865-237">외부</span><span class="sxs-lookup"><span data-stu-id="49865-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="49865-238">통화 우선 순위.</span><span class="sxs-lookup"><span data-stu-id="49865-238">Call priority.</span></span> <span data-ttu-id="49865-239">자세한 내용은 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013의 Callpriorities 순위 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49865-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="49865-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-241">int</span><span class="sxs-lookup"><span data-stu-id="49865-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-242">세션 중에 User1이 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="49865-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-244">int</span><span class="sxs-lookup"><span data-stu-id="49865-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-245">세션 중에 %2이 (가) 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="49865-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-247">dmtf</span><span class="sxs-lookup"><span data-stu-id="49865-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-248">세션이 종료 되는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="49865-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-250">int</span><span class="sxs-lookup"><span data-stu-id="49865-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-251">이 세션의 미디어 유형을 나타내는 비트 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-251">A bit set that indicates the media type of this session.</span></span> <span data-ttu-id="49865-252">다음은 형식에 대 한 정의입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-252">Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49865-253">메신저</span><span class="sxs-lookup"><span data-stu-id="49865-253">IM</span></span></p></td>
<td><p><span data-ttu-id="49865-254">1</span><span class="sxs-lookup"><span data-stu-id="49865-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="49865-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="49865-256">2</span><span class="sxs-lookup"><span data-stu-id="49865-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="49865-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="49865-258">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="49865-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="49865-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="49865-260">20cm(8</span><span class="sxs-lookup"><span data-stu-id="49865-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-261">오디오</span><span class="sxs-lookup"><span data-stu-id="49865-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="49865-262">16</span><span class="sxs-lookup"><span data-stu-id="49865-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-263">비디오만</span><span class="sxs-lookup"><span data-stu-id="49865-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="49865-264">32</span><span class="sxs-lookup"><span data-stu-id="49865-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="49865-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="49865-266">64</span><span class="sxs-lookup"><span data-stu-id="49865-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="49865-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-268">smallint</span><span class="sxs-lookup"><span data-stu-id="49865-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-269">User1 특성을 나타내는 비트 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-269">A bit set that indicates the User1 attributes.</span></span> <span data-ttu-id="49865-270">다음과 같은 특성 정의가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49865-270">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="49865-271">0x01-데스크톱 전화와 통합</span><span class="sxs-lookup"><span data-stu-id="49865-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="49865-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-273">smallint</span><span class="sxs-lookup"><span data-stu-id="49865-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-274">지 속성 특성을 나타내는 비트 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-274">A bit set that indicates the User2 attributes.</span></span> <span data-ttu-id="49865-275">다음과 같은 특성 정의가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49865-275">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="49865-276">0x01-데스크톱 전화와 통합</span><span class="sxs-lookup"><span data-stu-id="49865-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49865-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="49865-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-278">smallint</span><span class="sxs-lookup"><span data-stu-id="49865-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-279">통화 특성을 나타내는 비트 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="49865-279">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="49865-280">다음과 같은 특성 정의가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49865-280">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="49865-281">0x01-재시도 하는 세션</span><span class="sxs-lookup"><span data-stu-id="49865-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="49865-282">0x02-응답 그룹을 대신 하 여 상담원이 수행한 A 통화</span><span class="sxs-lookup"><span data-stu-id="49865-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49865-283"><strong>처리</strong></span><span class="sxs-lookup"><span data-stu-id="49865-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="49865-284">다소</span><span class="sxs-lookup"><span data-stu-id="49865-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="49865-285">모니터링 서비스에 내부적으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="49865-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="49865-286">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="49865-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="49865-287">\*대부분의 세션에서 SessionIdSeq에는 값 1이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49865-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="49865-288">정확히 동시에 여러 세션을 시작 하는 경우 1에 대 한 SessionIdSeq는 1이 되 고 다른 하나는 2가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49865-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

