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
ms.openlocfilehash: 81b97d6a7521add62817147ae87995508b841f2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="2385a-102">Lync Server 2013의 Session 테이블</span><span class="sxs-lookup"><span data-stu-id="2385a-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2385a-103">_**마지막으로 수정한 주제:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="2385a-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="2385a-104">각 레코드는 오디오 또는 오디오 및 비디오를 포함 하는 하나의 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="2385a-105">세션에 대 한 전반적인 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-105">It contains overall information about the session.</span></span> <span data-ttu-id="2385a-106">세션은 두 끝점 간에 오디오 또는 SIP (비디오 세션 초기화 프로토콜) 대화 상자로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2385a-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="2385a-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="2385a-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="2385a-110"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2385a-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-112">dmtf</span><span class="sxs-lookup"><span data-stu-id="2385a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="2385a-113">주요한</span><span class="sxs-lookup"><span data-stu-id="2385a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="2385a-114"><a href="lync-server-2013-dialog-table.md">Lync Server 2013의 대화 상자 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2385a-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-116">int</span><span class="sxs-lookup"><span data-stu-id="2385a-116">int</span></span></p></td>
<td><p><span data-ttu-id="2385a-117">주요한</span><span class="sxs-lookup"><span data-stu-id="2385a-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="2385a-118"><a href="lync-server-2013-dialog-table.md">Lync Server 2013의 대화 상자 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2385a-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-120">int</span><span class="sxs-lookup"><span data-stu-id="2385a-120">int</span></span></p></td>
<td><p><span data-ttu-id="2385a-121">외부</span><span class="sxs-lookup"><span data-stu-id="2385a-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2385a-122">회의 키입니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-122">Conference key.</span></span> <span data-ttu-id="2385a-123"><a href="lync-server-2013-conference-table.md">Lync Server 2013의 컨퍼런스 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2385a-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-125">int</span><span class="sxs-lookup"><span data-stu-id="2385a-125">int</span></span></p></td>
<td><p><span data-ttu-id="2385a-126">외부</span><span class="sxs-lookup"><span data-stu-id="2385a-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2385a-127">상관 관계 키입니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-127">Correlation key.</span></span> <span data-ttu-id="2385a-128"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013의 Sessioncorrelation 관계 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2385a-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-130">다소</span><span class="sxs-lookup"><span data-stu-id="2385a-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2385a-131">대화 상자 범주 0은 서버 레그 조정을 위한 Lync Server입니다. 1이 (가) PSTN 게이트웨이 레그로 서버를 중재 합니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2385a-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-133">다소</span><span class="sxs-lookup"><span data-stu-id="2385a-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2385a-134">통화가 바이패스 되었는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2385a-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-136">int</span><span class="sxs-lookup"><span data-stu-id="2385a-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2385a-137">이 필드에는 바이패스 Id가 일치 하는 경우에도 통화가 무시 되지 않은 이유가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="2385a-138">Lync Server의 경우 하나의 값만 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="2385a-139">0x0001-기본 네트워크 어댑터에 대 한 알 수 없는 바이패스 ID.</span><span class="sxs-lookup"><span data-stu-id="2385a-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2385a-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-141">dmtf</span><span class="sxs-lookup"><span data-stu-id="2385a-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2385a-142">통화 시작 시간.</span><span class="sxs-lookup"><span data-stu-id="2385a-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2385a-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-144">dmtf</span><span class="sxs-lookup"><span data-stu-id="2385a-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2385a-145">통화 종료 시간.</span><span class="sxs-lookup"><span data-stu-id="2385a-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2385a-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-147">int</span><span class="sxs-lookup"><span data-stu-id="2385a-147">int</span></span></p></td>
<td><p><span data-ttu-id="2385a-148">외부</span><span class="sxs-lookup"><span data-stu-id="2385a-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2385a-149">호출자의 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-149">The pool of the caller.</span></span> <span data-ttu-id="2385a-150"><a href="lync-server-2013-pool-table.md">Lync Server 2013의 풀 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2385a-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-152">int</span><span class="sxs-lookup"><span data-stu-id="2385a-152">int</span></span></p></td>
<td><p><span data-ttu-id="2385a-153">외부</span><span class="sxs-lookup"><span data-stu-id="2385a-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2385a-154">통화 수신기 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-154">The pool of the call receiver.</span></span> <span data-ttu-id="2385a-155"><a href="lync-server-2013-pool-table.md">Lync Server 2013의 풀 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2385a-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-157">int</span><span class="sxs-lookup"><span data-stu-id="2385a-157">int</span></span></p></td>
<td><p><span data-ttu-id="2385a-158">외부</span><span class="sxs-lookup"><span data-stu-id="2385a-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2385a-159">수신 끝점의 SIP p-어설션된 id (PAI)의 SIP URI입니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="2385a-160"><a href="lync-server-2013-user-table.md">Lync Server 2013의 사용자 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2385a-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-162">int</span><span class="sxs-lookup"><span data-stu-id="2385a-162">int</span></span></p></td>
<td><p><span data-ttu-id="2385a-163">외부</span><span class="sxs-lookup"><span data-stu-id="2385a-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2385a-164">호출자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-164">Caller’s URI.</span></span> <span data-ttu-id="2385a-165"><a href="lync-server-2013-user-table.md">Lync Server 2013의 사용자 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2385a-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-167">int</span><span class="sxs-lookup"><span data-stu-id="2385a-167">int</span></span></p></td>
<td><p><span data-ttu-id="2385a-168">외부</span><span class="sxs-lookup"><span data-stu-id="2385a-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2385a-169">호출자의 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-169">Caller’s endpoint.</span></span> <span data-ttu-id="2385a-170"><a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 끝점 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2385a-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-172">다소</span><span class="sxs-lookup"><span data-stu-id="2385a-172">bit</span></span></p></td>
<td><p><span data-ttu-id="2385a-173">외부</span><span class="sxs-lookup"><span data-stu-id="2385a-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2385a-174">발신자의 사용자 에이전트.</span><span class="sxs-lookup"><span data-stu-id="2385a-174">Caller’s user agent.</span></span> <span data-ttu-id="2385a-175"><a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2385a-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-177">smallint</span><span class="sxs-lookup"><span data-stu-id="2385a-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2385a-178">이 통화의 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2385a-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-180">다소</span><span class="sxs-lookup"><span data-stu-id="2385a-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2385a-181">이 열은 더 이상 사용 되지 않으며 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="2385a-182">대신이 정보는 미디어 단위 회선 기반에 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="2385a-183">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2385a-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2385a-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-185">int</span><span class="sxs-lookup"><span data-stu-id="2385a-185">int</span></span></p></td>
<td><p><span data-ttu-id="2385a-186">외부</span><span class="sxs-lookup"><span data-stu-id="2385a-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2385a-187">P-어설션 됨-통화를 놓은 사용자의 Id입니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="2385a-188">P-어설션된-Id (PAI)는 통화를 설정한 사용자의 실제 id를 전달 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2385a-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-190">int</span><span class="sxs-lookup"><span data-stu-id="2385a-190">int</span></span></p></td>
<td><p><span data-ttu-id="2385a-191">외부</span><span class="sxs-lookup"><span data-stu-id="2385a-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2385a-192">통화를 받은 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2385a-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-194">int</span><span class="sxs-lookup"><span data-stu-id="2385a-194">int</span></span></p></td>
<td><p><span data-ttu-id="2385a-195">외부</span><span class="sxs-lookup"><span data-stu-id="2385a-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2385a-196">통화를 받은 사용자가 사용 하는 사용자 에이전트입니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="2385a-197">사용자 에이전트는 클라이언트 끝점 장치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2385a-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="2385a-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2385a-199">int</span><span class="sxs-lookup"><span data-stu-id="2385a-199">int</span></span></p></td>
<td><p><span data-ttu-id="2385a-200">외부</span><span class="sxs-lookup"><span data-stu-id="2385a-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2385a-201">통화를 받은 사용자의 SIP URI입니다.</span><span class="sxs-lookup"><span data-stu-id="2385a-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

