---
title: 'Lync Server 2013: SessionDetails 테이블'
description: 'Lync Server 2013: SessionDetails 테이블'
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
ms.openlocfilehash: fd927f784fb0f2a835c896824105fe8bb112c7a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569934"
---
# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="3c5d4-103">Lync Server 2013의 SessionDetails 테이블</span><span class="sxs-lookup"><span data-stu-id="3c5d4-103">SessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c5d4-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3c5d4-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3c5d4-105">각 레코드는 VoIP-VoIP 전화 통화, 두 사용자 간 IM 세션 또는 기타 유형의 세션일 수 있는 하나의 피어 투 피어 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-105">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="3c5d4-106">[Lync Server 2013의 미디어 테이블과](lync-server-2013-media-table.md) 함께 테이블 join을 수행 하 여이 세션과 관련 된 각 미디어에 대 한 세부 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-106">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="3c5d4-107">IsUser1IntegratedWithDeskPhone 및 IsUser2IntegratedWithDeskPhone 필드는 Microsoft Lync Server 2013에 사용 된 SessionDetails 테이블에서 삭제 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-107">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c5d4-108">열</span><span class="sxs-lookup"><span data-stu-id="3c5d4-108">Column</span></span></th>
<th><span data-ttu-id="3c5d4-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3c5d4-109">Data Type</span></span></th>
<th><span data-ttu-id="3c5d4-110">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="3c5d4-110">Key/Index</span></span></th>
<th><span data-ttu-id="3c5d4-111">세부 정보</span><span class="sxs-lookup"><span data-stu-id="3c5d4-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-112"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-112"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-113">datetime</span><span class="sxs-lookup"><span data-stu-id="3c5d4-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-114">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="3c5d4-114">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-115">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-115">Time of session request.</span></span> <span data-ttu-id="3c5d4-116"><strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-116">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="3c5d4-117">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-117">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-118"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-118"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-119">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-119">int</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-120">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="3c5d4-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-121">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-121">ID number to identify the session.</span></span> <span data-ttu-id="3c5d4-122">세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다. \* 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-122">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-123"><strong>관계</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-123"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-124">고유</span><span class="sxs-lookup"><span data-stu-id="3c5d4-124">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-125">여러 세션의 관계를 지정하기 위한 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-125">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-126"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-126"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-127">datetime</span><span class="sxs-lookup"><span data-stu-id="3c5d4-127">datetime</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-128">외부</span><span class="sxs-lookup"><span data-stu-id="3c5d4-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-129">현재 세션으로 교체된 대화를 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-129">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="3c5d4-130">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-130">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-131"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-131"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-132">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-132">int</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-133">외부</span><span class="sxs-lookup"><span data-stu-id="3c5d4-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-134">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-134">ID number to identify the session.</span></span> <span data-ttu-id="3c5d4-135"><strong>ReplacesDialogIdTime</strong>과 함께 이 세션으로 교체된 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-135">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="3c5d4-136">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-136">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-137"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-137"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-138">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-138">int</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-139">외부</span><span class="sxs-lookup"><span data-stu-id="3c5d4-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-140">세션에 포함된 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-140">ID of one user in the session.</span></span> <span data-ttu-id="3c5d4-141">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-141">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-142"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-142"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-143">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-143">int</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-144">외부</span><span class="sxs-lookup"><span data-stu-id="3c5d4-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-145">세션에 포함된 다른 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-145">ID of the other user in the session.</span></span> <span data-ttu-id="3c5d4-146">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-146">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-147"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-147"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-148">고유</span><span class="sxs-lookup"><span data-stu-id="3c5d4-148">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-149">세션의 첫 번째 사용자가 사용한 끝점을 식별하는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-149">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="3c5d4-150">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-150">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-151"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-151"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-152">고유</span><span class="sxs-lookup"><span data-stu-id="3c5d4-152">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-153">세션의 두 번째 사용자가 사용한 끝점을 식별하는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-153">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="3c5d4-154">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-155"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-155"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-156">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-156">int</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-157">외부</span><span class="sxs-lookup"><span data-stu-id="3c5d4-157">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-158">SIP 요청에서 원래의 대상 사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-158">The original To user URI in the SIP request.</span></span> <span data-ttu-id="3c5d4-159">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-159">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-160"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-160"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-161">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-161">int</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-162">외부</span><span class="sxs-lookup"><span data-stu-id="3c5d4-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-163">세션을 시작한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-163">ID of the user who started the session.</span></span> <span data-ttu-id="3c5d4-164">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-164">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-165"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-165"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-166">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-166">int</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-167">외부</span><span class="sxs-lookup"><span data-stu-id="3c5d4-167">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-168">발신자가 역할을 대신 수행하고 있는 원래 사용자의 ID를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-168">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="3c5d4-169">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-169">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-170"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-170"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-171">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-171">int</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-172">외부</span><span class="sxs-lookup"><span data-stu-id="3c5d4-172">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-173">통화를 참조한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-173">ID of the user by who the call is referred.</span></span> <span data-ttu-id="3c5d4-174">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-174">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-175"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-175"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-176">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-176">int</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-177">외부</span><span class="sxs-lookup"><span data-stu-id="3c5d4-177">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-178">이 세션에 사용된 프런트 엔드 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-178">ID of the front-end server used for this session.</span></span> <span data-ttu-id="3c5d4-179">자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-179">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-180"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-180"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-181">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-181">int</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-182">외부</span><span class="sxs-lookup"><span data-stu-id="3c5d4-182">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-183">세션이 캡처된 풀의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-183">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="3c5d4-184">자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-184">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-185"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-185"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-186">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-186">int</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-187">외부</span><span class="sxs-lookup"><span data-stu-id="3c5d4-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-188">세션에 사용된 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-188">Content type used in the session.</span></span> <span data-ttu-id="3c5d4-189">자세한 내용은 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013의 Contenttypes 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-189">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-190"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-190"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-191">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-191">int</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-192">외부</span><span class="sxs-lookup"><span data-stu-id="3c5d4-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-193">User1이 사용한 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-193">Client version used by User1.</span></span> <span data-ttu-id="3c5d4-194">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-194">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-195"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-195"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-196">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-196">int</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-197">외부</span><span class="sxs-lookup"><span data-stu-id="3c5d4-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-198">User2가 사용한 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-198">Client version used by User2.</span></span> <span data-ttu-id="3c5d4-199">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-199">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-200"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-200"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-201">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-201">int</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-202">외부</span><span class="sxs-lookup"><span data-stu-id="3c5d4-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-203">User1이 사용한 에지 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-203">Edge Server used by User1.</span></span> <span data-ttu-id="3c5d4-204">자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-204">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-205"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-205"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-206">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-206">int</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-207">외부</span><span class="sxs-lookup"><span data-stu-id="3c5d4-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-208">User2가 사용한 에지 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-208">Edge Server used by User2.</span></span> <span data-ttu-id="3c5d4-209">자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-209">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-210"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-210"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-211">비트만</span><span class="sxs-lookup"><span data-stu-id="3c5d4-211">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-212">User1이 내부로부터 로그온되었는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-212">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-213"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-213"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-214">비트만</span><span class="sxs-lookup"><span data-stu-id="3c5d4-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-215">User2가 내부로부터 로그온되었는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-215">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-216"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-216"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-217">datetime</span><span class="sxs-lookup"><span data-stu-id="3c5d4-217">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-218">첫 번째 INVITE 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-218">The time of the first INVITE request.</span></span> <span data-ttu-id="3c5d4-219">이 필드는 대개 세션의 초기 INVITE 메시지에서 생성된 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-219">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="3c5d4-220">INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-220">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="3c5d4-221">이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-221">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="3c5d4-222">INVITE 메시지가 없으면 이 필드가 첫 번째 해당 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜와 시간으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-222">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-223"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-223"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-224">datetime</span><span class="sxs-lookup"><span data-stu-id="3c5d4-224">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-225">첫 번째 INVITE 메시지에 대한 응답 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-225">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="3c5d4-226">이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-226">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="3c5d4-227">INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-227">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-228"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-228"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-229">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-p121">세션 초대에 대한 SIP 응답 코드입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-233"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-233"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-234">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-234">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-235">SIP 헤더에서 캡처된 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-235">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-236"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-236"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-237">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-237">int</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-238">외부</span><span class="sxs-lookup"><span data-stu-id="3c5d4-238">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-239">통화 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-239">Call priority.</span></span> <span data-ttu-id="3c5d4-240">자세한 내용은 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013의 Callpriorities 순위 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-240">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-241"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-241"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-242">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-243">세션 중 User1이 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-243">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-244"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-244"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-245">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-245">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-246">세션 중 User2가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-246">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-247"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-247"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-248">datetime</span><span class="sxs-lookup"><span data-stu-id="3c5d4-248">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-249">세션 종료 시 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-249">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-250"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-250"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-251">int</span><span class="sxs-lookup"><span data-stu-id="3c5d4-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-p123">이 세션의 미디어 유형을 나타내는 비트 집합입니다. 다음 유형의 정의가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-254">메시징을</span><span class="sxs-lookup"><span data-stu-id="3c5d4-254">IM</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-255">1 </span><span class="sxs-lookup"><span data-stu-id="3c5d4-255">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-256">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="3c5d4-256">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-257">2</span><span class="sxs-lookup"><span data-stu-id="3c5d4-257">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-258">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="3c5d4-258">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-259">4 </span><span class="sxs-lookup"><span data-stu-id="3c5d4-259">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-260">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="3c5d4-260">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-261">8 </span><span class="sxs-lookup"><span data-stu-id="3c5d4-261">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-262">오디오만</span><span class="sxs-lookup"><span data-stu-id="3c5d4-262">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-263">16 </span><span class="sxs-lookup"><span data-stu-id="3c5d4-263">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-264">비디오</span><span class="sxs-lookup"><span data-stu-id="3c5d4-264">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-265">32</span><span class="sxs-lookup"><span data-stu-id="3c5d4-265">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-266">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="3c5d4-266">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="3c5d4-267">64</span><span class="sxs-lookup"><span data-stu-id="3c5d4-267">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-268"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-268"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-269">smallint</span><span class="sxs-lookup"><span data-stu-id="3c5d4-269">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-p124">User1 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="3c5d4-272">0x01 - 데스크톱 전화와 통합됨</span><span class="sxs-lookup"><span data-stu-id="3c5d4-272">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-273"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-273"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-274">smallint</span><span class="sxs-lookup"><span data-stu-id="3c5d4-274">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-p125">User2 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="3c5d4-277">0x01 - 데스크톱 전화와 통합됨</span><span class="sxs-lookup"><span data-stu-id="3c5d4-277">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c5d4-278"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-278"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-279">smallint</span><span class="sxs-lookup"><span data-stu-id="3c5d4-279">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-p126">통화 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="3c5d4-282">0x01 - 다시 시도된 세션</span><span class="sxs-lookup"><span data-stu-id="3c5d4-282">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="3c5d4-283">0x02 - 응답 그룹을 대신하여 에이전트가 시작한 통화</span><span class="sxs-lookup"><span data-stu-id="3c5d4-283">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c5d4-284"><strong>전처리</strong></span><span class="sxs-lookup"><span data-stu-id="3c5d4-284"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="3c5d4-285">비트만</span><span class="sxs-lookup"><span data-stu-id="3c5d4-285">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c5d4-286">모니터링 서비스의 내부 사용 용도</span><span class="sxs-lookup"><span data-stu-id="3c5d4-286">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="3c5d4-287">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-287">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3c5d4-288">\* 대부분의 세션에서 SessionIdSeq는 값 1을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-288">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="3c5d4-289">여러 세션이 정확히 동시에 시작될 경우 한 세션에 대한 SessionIdSeq가 1이 되고 다른 세션에 대해서는 2, 3, 4의 순서로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c5d4-289">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

