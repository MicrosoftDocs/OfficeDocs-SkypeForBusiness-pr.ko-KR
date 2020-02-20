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
ms.openlocfilehash: b27721923e265bbb687b5df42b32e0fb6f25e92e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="dc1b0-102">Lync Server 2013의 SessionDetails 테이블</span><span class="sxs-lookup"><span data-stu-id="dc1b0-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc1b0-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="dc1b0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="dc1b0-104">각 레코드는 VoIP-VoIP 전화 통화, 두 사용자 간 IM 세션 또는 기타 유형의 세션일 수 있는 하나의 피어 투 피어 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="dc1b0-105">[Lync Server 2013의 미디어 테이블과](lync-server-2013-media-table.md) 함께 테이블 join을 수행 하 여이 세션과 관련 된 각 미디어에 대 한 세부 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="dc1b0-106">IsUser1IntegratedWithDeskPhone 및 IsUser2IntegratedWithDeskPhone 필드는 Microsoft Lync Server 2013에 사용 된 SessionDetails 테이블에서 삭제 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc1b0-107">열</span><span class="sxs-lookup"><span data-stu-id="dc1b0-107">Column</span></span></th>
<th><span data-ttu-id="dc1b0-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="dc1b0-108">Data Type</span></span></th>
<th><span data-ttu-id="dc1b0-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="dc1b0-109">Key/Index</span></span></th>
<th><span data-ttu-id="dc1b0-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="dc1b0-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-112">datetime</span><span class="sxs-lookup"><span data-stu-id="dc1b0-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-113">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="dc1b0-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-114">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-114">Time of session request.</span></span> <span data-ttu-id="dc1b0-115"><strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="dc1b0-116">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-118">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-118">int</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-119">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="dc1b0-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-120">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-120">ID number to identify the session.</span></span> <span data-ttu-id="dc1b0-121">세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다. \* 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-122"><strong>관계</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-123">고유</span><span class="sxs-lookup"><span data-stu-id="dc1b0-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-124">여러 세션의 관계를 지정하기 위한 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-126">datetime</span><span class="sxs-lookup"><span data-stu-id="dc1b0-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-127">외부</span><span class="sxs-lookup"><span data-stu-id="dc1b0-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-128">현재 세션으로 교체된 대화를 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="dc1b0-129">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-131">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-131">int</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-132">외부</span><span class="sxs-lookup"><span data-stu-id="dc1b0-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-133">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-133">ID number to identify the session.</span></span> <span data-ttu-id="dc1b0-134"><strong>ReplacesDialogIdTime</strong>과 함께 이 세션으로 교체된 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="dc1b0-135">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-137">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-137">int</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-138">외부</span><span class="sxs-lookup"><span data-stu-id="dc1b0-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-139">세션에 포함된 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-139">ID of one user in the session.</span></span> <span data-ttu-id="dc1b0-140">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-142">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-142">int</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-143">외부</span><span class="sxs-lookup"><span data-stu-id="dc1b0-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-144">세션에 포함된 다른 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-144">ID of the other user in the session.</span></span> <span data-ttu-id="dc1b0-145">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-147">고유</span><span class="sxs-lookup"><span data-stu-id="dc1b0-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-148">세션의 첫 번째 사용자가 사용한 끝점을 식별하는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="dc1b0-149">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-151">고유</span><span class="sxs-lookup"><span data-stu-id="dc1b0-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-152">세션의 두 번째 사용자가 사용한 끝점을 식별하는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="dc1b0-153">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-155">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-155">int</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-156">외부</span><span class="sxs-lookup"><span data-stu-id="dc1b0-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-157">SIP 요청에서 원래의 대상 사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="dc1b0-158">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-160">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-160">int</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-161">외부</span><span class="sxs-lookup"><span data-stu-id="dc1b0-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-162">세션을 시작한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-162">ID of the user who started the session.</span></span> <span data-ttu-id="dc1b0-163">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-165">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-165">int</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-166">외부</span><span class="sxs-lookup"><span data-stu-id="dc1b0-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-167">발신자가 역할을 대신 수행하고 있는 원래 사용자의 ID를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="dc1b0-168">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-170">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-170">int</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-171">외부</span><span class="sxs-lookup"><span data-stu-id="dc1b0-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-172">통화를 참조한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="dc1b0-173">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-175">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-175">int</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-176">외부</span><span class="sxs-lookup"><span data-stu-id="dc1b0-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-177">이 세션에 사용된 프런트 엔드 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="dc1b0-178">자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-180">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-180">int</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-181">외부</span><span class="sxs-lookup"><span data-stu-id="dc1b0-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-182">세션이 캡처된 풀의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="dc1b0-183">자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-185">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-185">int</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-186">외부</span><span class="sxs-lookup"><span data-stu-id="dc1b0-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-187">세션에 사용된 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-187">Content type used in the session.</span></span> <span data-ttu-id="dc1b0-188">자세한 내용은 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013의 Contenttypes 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-190">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-190">int</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-191">외부</span><span class="sxs-lookup"><span data-stu-id="dc1b0-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-192">User1이 사용한 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-192">Client version used by User1.</span></span> <span data-ttu-id="dc1b0-193">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-195">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-195">int</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-196">외부</span><span class="sxs-lookup"><span data-stu-id="dc1b0-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-197">User2가 사용한 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-197">Client version used by User2.</span></span> <span data-ttu-id="dc1b0-198">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-200">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-200">int</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-201">외부</span><span class="sxs-lookup"><span data-stu-id="dc1b0-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-202">User1이 사용한 에지 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-202">Edge Server used by User1.</span></span> <span data-ttu-id="dc1b0-203">자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-205">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-205">int</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-206">외부</span><span class="sxs-lookup"><span data-stu-id="dc1b0-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-207">User2가 사용한 에지 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-207">Edge Server used by User2.</span></span> <span data-ttu-id="dc1b0-208">자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-210">비트만</span><span class="sxs-lookup"><span data-stu-id="dc1b0-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-211">User1이 내부로부터 로그온되었는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-213">비트만</span><span class="sxs-lookup"><span data-stu-id="dc1b0-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-214">User2가 내부로부터 로그온되었는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-216">datetime</span><span class="sxs-lookup"><span data-stu-id="dc1b0-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-217">첫 번째 INVITE 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-217">The time of the first INVITE request.</span></span> <span data-ttu-id="dc1b0-218">이 필드는 대개 세션의 초기 INVITE 메시지에서 생성된 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="dc1b0-219">INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="dc1b0-220">이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="dc1b0-221">INVITE 메시지가 없으면 이 필드가 첫 번째 해당 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜와 시간으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-223">datetime</span><span class="sxs-lookup"><span data-stu-id="dc1b0-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-224">첫 번째 INVITE 메시지에 대한 응답 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="dc1b0-225">이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="dc1b0-226">INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-228">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-p121">세션 초대에 대한 SIP 응답 코드입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-233">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-234">SIP 헤더에서 캡처된 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-236">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-236">int</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-237">외부</span><span class="sxs-lookup"><span data-stu-id="dc1b0-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-238">통화 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-238">Call priority.</span></span> <span data-ttu-id="dc1b0-239">자세한 내용은 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013의 Callpriorities 순위 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-241">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-242">세션 중 User1이 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-244">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-245">세션 중 User2가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-247">datetime</span><span class="sxs-lookup"><span data-stu-id="dc1b0-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-248">세션 종료 시 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-250">int</span><span class="sxs-lookup"><span data-stu-id="dc1b0-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-p123">이 세션의 미디어 유형을 나타내는 비트 집합입니다. 다음 유형의 정의가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-253">메시징을</span><span class="sxs-lookup"><span data-stu-id="dc1b0-253">IM</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-254">개</span><span class="sxs-lookup"><span data-stu-id="dc1b0-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="dc1b0-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-256">2</span><span class="sxs-lookup"><span data-stu-id="dc1b0-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="dc1b0-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-258">1-4</span><span class="sxs-lookup"><span data-stu-id="dc1b0-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="dc1b0-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-260">8 </span><span class="sxs-lookup"><span data-stu-id="dc1b0-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-261">오디오만</span><span class="sxs-lookup"><span data-stu-id="dc1b0-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-262">16 </span><span class="sxs-lookup"><span data-stu-id="dc1b0-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-263">비디오</span><span class="sxs-lookup"><span data-stu-id="dc1b0-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-264">32</span><span class="sxs-lookup"><span data-stu-id="dc1b0-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="dc1b0-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="dc1b0-266">64</span><span class="sxs-lookup"><span data-stu-id="dc1b0-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-268">smallint</span><span class="sxs-lookup"><span data-stu-id="dc1b0-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-p124">User1 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc1b0-271">0x01 - 데스크톱 전화와 통합됨</span><span class="sxs-lookup"><span data-stu-id="dc1b0-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-273">smallint</span><span class="sxs-lookup"><span data-stu-id="dc1b0-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-p125">User2 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc1b0-276">0x01 - 데스크톱 전화와 통합됨</span><span class="sxs-lookup"><span data-stu-id="dc1b0-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc1b0-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-278">smallint</span><span class="sxs-lookup"><span data-stu-id="dc1b0-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-p126">통화 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="dc1b0-281">0x01 - 다시 시도된 세션</span><span class="sxs-lookup"><span data-stu-id="dc1b0-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="dc1b0-282">0x02 - 응답 그룹을 대신하여 에이전트가 시작한 통화</span><span class="sxs-lookup"><span data-stu-id="dc1b0-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc1b0-283"><strong>전처리</strong></span><span class="sxs-lookup"><span data-stu-id="dc1b0-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="dc1b0-284">비트만</span><span class="sxs-lookup"><span data-stu-id="dc1b0-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dc1b0-285">모니터링 서비스의 내부 사용 용도</span><span class="sxs-lookup"><span data-stu-id="dc1b0-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="dc1b0-286">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dc1b0-287">\*대부분의 세션에서 SessionIdSeq는 값 1을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="dc1b0-288">여러 세션이 정확히 동시에 시작될 경우 한 세션에 대한 SessionIdSeq가 1이 되고 다른 세션에 대해서는 2, 3, 4의 순서로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc1b0-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

