---
title: 'Lync Server 2013: Session 테이블'
description: 'Lync Server 2013: Session 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1a52813dfea808253cc934f71a9d4c846c2dbbd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576454"
---
# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="ed00d-103">Lync Server 2013의 Session 테이블</span><span class="sxs-lookup"><span data-stu-id="ed00d-103">Session table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed00d-104">_**마지막으로 수정 된 항목:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="ed00d-104">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="ed00d-105">각 레코드는 오디오 또는 오디오/비디오를 포함 하는 하나의 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-105">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="ed00d-106">세션에 대 한 전체 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-106">It contains overall information about the session.</span></span> <span data-ttu-id="ed00d-107">세션은 두 끝점 간에 오디오 또는 비디오 세션 시작 프로토콜 (SIP) 대화 상자로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-107">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed00d-108"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ed00d-109"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ed00d-110"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ed00d-111"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed00d-112"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-113">datetime</span><span class="sxs-lookup"><span data-stu-id="ed00d-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="ed00d-114">Primary</span><span class="sxs-lookup"><span data-stu-id="ed00d-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="ed00d-115"><a href="lync-server-2013-dialog-table.md">Lync Server 2013의 Dialog 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-115">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed00d-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-117">int</span><span class="sxs-lookup"><span data-stu-id="ed00d-117">int</span></span></p></td>
<td><p><span data-ttu-id="ed00d-118">Primary</span><span class="sxs-lookup"><span data-stu-id="ed00d-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="ed00d-119"><a href="lync-server-2013-dialog-table.md">Lync Server 2013의 Dialog 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-119">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed00d-120"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-120"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-121">int</span><span class="sxs-lookup"><span data-stu-id="ed00d-121">int</span></span></p></td>
<td><p><span data-ttu-id="ed00d-122">외부</span><span class="sxs-lookup"><span data-stu-id="ed00d-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed00d-123">전화 회의 키</span><span class="sxs-lookup"><span data-stu-id="ed00d-123">Conference key.</span></span> <span data-ttu-id="ed00d-124"><a href="lync-server-2013-conference-table.md">Lync Server 2013의 회의 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-124">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed00d-125"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-125"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-126">int</span><span class="sxs-lookup"><span data-stu-id="ed00d-126">int</span></span></p></td>
<td><p><span data-ttu-id="ed00d-127">외부</span><span class="sxs-lookup"><span data-stu-id="ed00d-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed00d-128">상관 관계 키입니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-128">Correlation key.</span></span> <span data-ttu-id="ed00d-129"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013의 Sessioncorrelation 관계 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-129">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed00d-130"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-130"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-131">비트만</span><span class="sxs-lookup"><span data-stu-id="ed00d-131">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed00d-132">대화 상자 범주 0은 중재 서버 레그에 대 한 Lync Server입니다. 1은 PSTN 게이트웨이 레그에 대 한 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-132">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed00d-133"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-133"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-134">비트만</span><span class="sxs-lookup"><span data-stu-id="ed00d-134">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed00d-135">통화가 바이패스되었는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-135">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed00d-136"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-136"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-137">int</span><span class="sxs-lookup"><span data-stu-id="ed00d-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed00d-138">이 필드(제공된 경우)는 우회 ID가 일치했어도 통화가 우회되지 않은 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-138">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="ed00d-139">Lync Server의 경우 한 가지 값만 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-139">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="ed00d-140">0x0001 -  기본 네트워크 어댑터에 대한 알 수 없는 바이패스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-140">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed00d-141"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-141"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-142">datetime</span><span class="sxs-lookup"><span data-stu-id="ed00d-142">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed00d-143">통화 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-143">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed00d-144"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-144"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-145">datetime</span><span class="sxs-lookup"><span data-stu-id="ed00d-145">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ed00d-146">통화 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-146">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed00d-147"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-147"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-148">int</span><span class="sxs-lookup"><span data-stu-id="ed00d-148">int</span></span></p></td>
<td><p><span data-ttu-id="ed00d-149">외부</span><span class="sxs-lookup"><span data-stu-id="ed00d-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed00d-150">발신자의 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-150">The pool of the caller.</span></span> <span data-ttu-id="ed00d-151"><a href="lync-server-2013-pool-table.md">Lync Server 2013의 Pool 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-151">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed00d-152"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-152"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-153">int</span><span class="sxs-lookup"><span data-stu-id="ed00d-153">int</span></span></p></td>
<td><p><span data-ttu-id="ed00d-154">외부</span><span class="sxs-lookup"><span data-stu-id="ed00d-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed00d-155">통화 수신기 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-155">The pool of the call receiver.</span></span> <span data-ttu-id="ed00d-156"><a href="lync-server-2013-pool-table.md">Lync Server 2013의 Pool 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-156">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed00d-157"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-157"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-158">int</span><span class="sxs-lookup"><span data-stu-id="ed00d-158">int</span></span></p></td>
<td><p><span data-ttu-id="ed00d-159">외부</span><span class="sxs-lookup"><span data-stu-id="ed00d-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed00d-160">수신 끝점의 SIP p-어설션된 id (PAI)에 있는 SIP URI입니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-160">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="ed00d-161"><a href="lync-server-2013-user-table.md">Lync Server 2013의 User 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-161">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed00d-162"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-162"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-163">int</span><span class="sxs-lookup"><span data-stu-id="ed00d-163">int</span></span></p></td>
<td><p><span data-ttu-id="ed00d-164">외부</span><span class="sxs-lookup"><span data-stu-id="ed00d-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed00d-165">발신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-165">Caller’s URI.</span></span> <span data-ttu-id="ed00d-166"><a href="lync-server-2013-user-table.md">Lync Server 2013의 User 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-166">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed00d-167"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-167"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-168">int</span><span class="sxs-lookup"><span data-stu-id="ed00d-168">int</span></span></p></td>
<td><p><span data-ttu-id="ed00d-169">외부</span><span class="sxs-lookup"><span data-stu-id="ed00d-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed00d-170">발신자의 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-170">Caller’s endpoint.</span></span> <span data-ttu-id="ed00d-171"><a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 끝점 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-171">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed00d-172"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-172"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-173">비트만</span><span class="sxs-lookup"><span data-stu-id="ed00d-173">bit</span></span></p></td>
<td><p><span data-ttu-id="ed00d-174">외부</span><span class="sxs-lookup"><span data-stu-id="ed00d-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed00d-175">발신자의 사용자 에이전트</span><span class="sxs-lookup"><span data-stu-id="ed00d-175">Caller’s user agent.</span></span> <span data-ttu-id="ed00d-176"><a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-176">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed00d-177"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-177"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-178">smallint</span><span class="sxs-lookup"><span data-stu-id="ed00d-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed00d-179">이 통화의 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-179">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed00d-180"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-180"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-181">비트만</span><span class="sxs-lookup"><span data-stu-id="ed00d-181">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ed00d-182">이 열은 더 이상 사용 되지 않으며 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-182">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="ed00d-183">대신이 정보는 미디어 단위 회선 기반에 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-183">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="ed00d-184">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ed00d-184">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed00d-185"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-185"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-186">int</span><span class="sxs-lookup"><span data-stu-id="ed00d-186">int</span></span></p></td>
<td><p><span data-ttu-id="ed00d-187">외부</span><span class="sxs-lookup"><span data-stu-id="ed00d-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed00d-188">P-어설션된-통화를 시작한 사용자의 Id입니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-188">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="ed00d-189">P-어설션된-Identity (PAI)는 통화를 시작한 사용자의 실제 id를 전달 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-189">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed00d-190"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-190"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-191">int</span><span class="sxs-lookup"><span data-stu-id="ed00d-191">int</span></span></p></td>
<td><p><span data-ttu-id="ed00d-192">외부</span><span class="sxs-lookup"><span data-stu-id="ed00d-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed00d-193">통화를 받은 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-193">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed00d-194"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-194"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-195">int</span><span class="sxs-lookup"><span data-stu-id="ed00d-195">int</span></span></p></td>
<td><p><span data-ttu-id="ed00d-196">외부</span><span class="sxs-lookup"><span data-stu-id="ed00d-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed00d-197">통화를 받은 사용자가 사용 하는 사용자 에이전트입니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-197">User agent employed by the user who received the call.</span></span> <span data-ttu-id="ed00d-198">사용자 에이전트는 클라이언트 끝점 장치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-198">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed00d-199"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="ed00d-199"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ed00d-200">int</span><span class="sxs-lookup"><span data-stu-id="ed00d-200">int</span></span></p></td>
<td><p><span data-ttu-id="ed00d-201">외부</span><span class="sxs-lookup"><span data-stu-id="ed00d-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ed00d-202">통화를 받은 사용자의 SIP URI입니다.</span><span class="sxs-lookup"><span data-stu-id="ed00d-202">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

