---
title: 'Lync Server 2013: Session 테이블'
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
ms.openlocfilehash: c252ef5cd96511875fa299f44ca2a707f766f59a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="b4bac-102">Lync Server 2013의 Session 테이블</span><span class="sxs-lookup"><span data-stu-id="b4bac-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4bac-103">_**마지막으로 수정 된 항목:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="b4bac-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="b4bac-104">각 레코드는 오디오 또는 오디오/비디오를 포함 하는 하나의 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="b4bac-105">세션에 대 한 전체 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-105">It contains overall information about the session.</span></span> <span data-ttu-id="b4bac-106">세션은 두 끝점 간에 오디오 또는 비디오 세션 시작 프로토콜 (SIP) 대화 상자로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4bac-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b4bac-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b4bac-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b4bac-110"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4bac-111"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-112">datetime</span><span class="sxs-lookup"><span data-stu-id="b4bac-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="b4bac-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b4bac-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="b4bac-114"><a href="lync-server-2013-dialog-table.md">Lync Server 2013의 Dialog 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4bac-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-116">int</span><span class="sxs-lookup"><span data-stu-id="b4bac-116">int</span></span></p></td>
<td><p><span data-ttu-id="b4bac-117">Primary</span><span class="sxs-lookup"><span data-stu-id="b4bac-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="b4bac-118"><a href="lync-server-2013-dialog-table.md">Lync Server 2013의 Dialog 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4bac-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-120">int</span><span class="sxs-lookup"><span data-stu-id="b4bac-120">int</span></span></p></td>
<td><p><span data-ttu-id="b4bac-121">외부</span><span class="sxs-lookup"><span data-stu-id="b4bac-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4bac-122">전화 회의 키</span><span class="sxs-lookup"><span data-stu-id="b4bac-122">Conference key.</span></span> <span data-ttu-id="b4bac-123"><a href="lync-server-2013-conference-table.md">Lync Server 2013의 회의 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4bac-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-125">int</span><span class="sxs-lookup"><span data-stu-id="b4bac-125">int</span></span></p></td>
<td><p><span data-ttu-id="b4bac-126">외부</span><span class="sxs-lookup"><span data-stu-id="b4bac-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4bac-127">상관 관계 키입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-127">Correlation key.</span></span> <span data-ttu-id="b4bac-128"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013의 Sessioncorrelation 관계 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4bac-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-130">비트만</span><span class="sxs-lookup"><span data-stu-id="b4bac-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b4bac-131">대화 상자 범주 0은 중재 서버 레그에 대 한 Lync Server입니다. 1은 PSTN 게이트웨이 레그에 대 한 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4bac-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-133">비트만</span><span class="sxs-lookup"><span data-stu-id="b4bac-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b4bac-134">통화가 바이패스되었는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4bac-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-136">int</span><span class="sxs-lookup"><span data-stu-id="b4bac-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b4bac-137">이 필드(제공된 경우)는 우회 ID가 일치했어도 통화가 우회되지 않은 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="b4bac-138">Lync Server의 경우 한 가지 값만 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="b4bac-139">0x0001 -  기본 네트워크 어댑터에 대한 알 수 없는 바이패스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4bac-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-141">datetime</span><span class="sxs-lookup"><span data-stu-id="b4bac-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b4bac-142">통화 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4bac-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-144">datetime</span><span class="sxs-lookup"><span data-stu-id="b4bac-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b4bac-145">통화 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4bac-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-147">int</span><span class="sxs-lookup"><span data-stu-id="b4bac-147">int</span></span></p></td>
<td><p><span data-ttu-id="b4bac-148">외부</span><span class="sxs-lookup"><span data-stu-id="b4bac-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4bac-149">발신자의 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-149">The pool of the caller.</span></span> <span data-ttu-id="b4bac-150"><a href="lync-server-2013-pool-table.md">Lync Server 2013의 Pool 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4bac-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-152">int</span><span class="sxs-lookup"><span data-stu-id="b4bac-152">int</span></span></p></td>
<td><p><span data-ttu-id="b4bac-153">외부</span><span class="sxs-lookup"><span data-stu-id="b4bac-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4bac-154">통화 수신기 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-154">The pool of the call receiver.</span></span> <span data-ttu-id="b4bac-155"><a href="lync-server-2013-pool-table.md">Lync Server 2013의 Pool 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4bac-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-157">int</span><span class="sxs-lookup"><span data-stu-id="b4bac-157">int</span></span></p></td>
<td><p><span data-ttu-id="b4bac-158">외부</span><span class="sxs-lookup"><span data-stu-id="b4bac-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4bac-159">수신 끝점의 SIP p-어설션된 id (PAI)에 있는 SIP URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="b4bac-160"><a href="lync-server-2013-user-table.md">Lync Server 2013의 User 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4bac-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-162">int</span><span class="sxs-lookup"><span data-stu-id="b4bac-162">int</span></span></p></td>
<td><p><span data-ttu-id="b4bac-163">외부</span><span class="sxs-lookup"><span data-stu-id="b4bac-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4bac-164">발신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-164">Caller’s URI.</span></span> <span data-ttu-id="b4bac-165"><a href="lync-server-2013-user-table.md">Lync Server 2013의 User 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4bac-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-167">int</span><span class="sxs-lookup"><span data-stu-id="b4bac-167">int</span></span></p></td>
<td><p><span data-ttu-id="b4bac-168">외부</span><span class="sxs-lookup"><span data-stu-id="b4bac-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4bac-169">발신자의 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-169">Caller’s endpoint.</span></span> <span data-ttu-id="b4bac-170"><a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 끝점 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4bac-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-172">비트만</span><span class="sxs-lookup"><span data-stu-id="b4bac-172">bit</span></span></p></td>
<td><p><span data-ttu-id="b4bac-173">외부</span><span class="sxs-lookup"><span data-stu-id="b4bac-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4bac-174">발신자의 사용자 에이전트</span><span class="sxs-lookup"><span data-stu-id="b4bac-174">Caller’s user agent.</span></span> <span data-ttu-id="b4bac-175"><a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4bac-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-177">smallint</span><span class="sxs-lookup"><span data-stu-id="b4bac-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b4bac-178">이 통화의 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4bac-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-180">비트만</span><span class="sxs-lookup"><span data-stu-id="b4bac-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b4bac-181">이 열은 더 이상 사용 되지 않으며 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="b4bac-182">대신이 정보는 미디어 단위 회선 기반에 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="b4bac-183">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b4bac-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4bac-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-185">int</span><span class="sxs-lookup"><span data-stu-id="b4bac-185">int</span></span></p></td>
<td><p><span data-ttu-id="b4bac-186">외부</span><span class="sxs-lookup"><span data-stu-id="b4bac-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4bac-187">P-어설션된-통화를 시작한 사용자의 Id입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="b4bac-188">P-어설션된-Identity (PAI)는 통화를 시작한 사용자의 실제 id를 전달 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4bac-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-190">int</span><span class="sxs-lookup"><span data-stu-id="b4bac-190">int</span></span></p></td>
<td><p><span data-ttu-id="b4bac-191">외부</span><span class="sxs-lookup"><span data-stu-id="b4bac-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4bac-192">통화를 받은 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4bac-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-194">int</span><span class="sxs-lookup"><span data-stu-id="b4bac-194">int</span></span></p></td>
<td><p><span data-ttu-id="b4bac-195">외부</span><span class="sxs-lookup"><span data-stu-id="b4bac-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4bac-196">통화를 받은 사용자가 사용 하는 사용자 에이전트입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="b4bac-197">사용자 에이전트는 클라이언트 끝점 장치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4bac-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="b4bac-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b4bac-199">int</span><span class="sxs-lookup"><span data-stu-id="b4bac-199">int</span></span></p></td>
<td><p><span data-ttu-id="b4bac-200">외부</span><span class="sxs-lookup"><span data-stu-id="b4bac-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b4bac-201">통화를 받은 사용자의 SIP URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b4bac-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

