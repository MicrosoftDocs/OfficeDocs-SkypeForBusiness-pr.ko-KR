---
title: 'Lync Server 2013: 오디오 Streamdetail 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cebcd47d735f1779396c0272877c0ec64a6189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="c2609-102">Lync Server 2013의 오디오 Streamdetail 보기</span><span class="sxs-lookup"><span data-stu-id="c2609-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2609-103">_**마지막으로 수정한 주제:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="c2609-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="c2609-104">오디오 Streamdetail 보기에는 데이터베이스의 각 오디오 스트림에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="c2609-105">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2609-106">열</span><span class="sxs-lookup"><span data-stu-id="c2609-106">Column</span></span></th>
<th><span data-ttu-id="c2609-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c2609-107">Data Type</span></span></th>
<th><span data-ttu-id="c2609-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="c2609-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2609-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="c2609-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="c2609-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="c2609-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="c2609-111"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="c2609-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="c2609-113">int</span><span class="sxs-lookup"><span data-stu-id="c2609-113">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="c2609-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="c2609-116">int</span><span class="sxs-lookup"><span data-stu-id="c2609-116">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-117">미디어 라인 내의 고유 ID.</span><span class="sxs-lookup"><span data-stu-id="c2609-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="c2609-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="c2609-119">dmtf</span><span class="sxs-lookup"><span data-stu-id="c2609-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="c2609-120">세션 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="c2609-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="c2609-122">dmtf</span><span class="sxs-lookup"><span data-stu-id="c2609-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="c2609-123">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="c2609-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="c2609-125">다소</span><span class="sxs-lookup"><span data-stu-id="c2609-125">bit</span></span></p></td>
<td><p><span data-ttu-id="c2609-126">대화 상자 범주: 0은 서버 레그를 중재 하는 Lync 서버입니다. 1은 PSTN 게이트웨이 레그에 대 한 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="c2609-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="c2609-128">다소</span><span class="sxs-lookup"><span data-stu-id="c2609-128">bit</span></span></p></td>
<td><p><span data-ttu-id="c2609-129">통화가 바이패스 되었는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="c2609-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="c2609-131">int</span><span class="sxs-lookup"><span data-stu-id="c2609-131">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-132">바이패스 Id가 일치 하는 경우에도 통화가 무시 되지 않은 이유를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-132">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="c2609-133">하나의 값만 정의 된 경우:</span><span class="sxs-lookup"><span data-stu-id="c2609-133">Only one value is defined:</span></span></p>
<p><span data-ttu-id="c2609-134">0x0001-기본 네트워크 어댑터에 대 한 알 수 없는 바이패스 ID.</span><span class="sxs-lookup"><span data-stu-id="c2609-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="c2609-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="c2609-136">int</span><span class="sxs-lookup"><span data-stu-id="c2609-136">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-137">통화의 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="c2609-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="c2609-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2609-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2609-140">발신자 풀 FQDN.</span><span class="sxs-lookup"><span data-stu-id="c2609-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="c2609-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="c2609-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2609-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2609-143">호출 수신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-144">호출인</span><span class="sxs-lookup"><span data-stu-id="c2609-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="c2609-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c2609-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c2609-146">호출자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-147">피호출자</span><span class="sxs-lookup"><span data-stu-id="c2609-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="c2609-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c2609-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c2609-149">호출 수신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="c2609-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="c2609-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2609-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2609-152">호출자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="c2609-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="c2609-154">smallint</span><span class="sxs-lookup"><span data-stu-id="c2609-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="c2609-155">호출자의 사용자 에이전트 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="c2609-156">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2609-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="c2609-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="c2609-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c2609-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c2609-159">호출자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="c2609-160">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (체감 품질)</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2609-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="c2609-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="c2609-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2609-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2609-163">호출 수신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="c2609-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="c2609-165">smallint</span><span class="sxs-lookup"><span data-stu-id="c2609-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="c2609-166">호출 수신자의 사용자 에이전트 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-166">Type of callee’s user agent.</span></span> <span data-ttu-id="c2609-167">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2609-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="c2609-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="c2609-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c2609-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c2609-170">호출 수신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-170">Category of callee’s user agent.</span></span> <span data-ttu-id="c2609-171">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (체감 품질)</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2609-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="c2609-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="c2609-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2609-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2609-174">호출자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="c2609-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="c2609-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2609-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2609-177">호출 수신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="c2609-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="c2609-179">name</span><span class="sxs-lookup"><span data-stu-id="c2609-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c2609-180">호출자 끝점의 OS (운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="c2609-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="c2609-182">name</span><span class="sxs-lookup"><span data-stu-id="c2609-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c2609-183">호출 수신자의 끝점에 대 한 OS (운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="c2609-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="c2609-185">name</span><span class="sxs-lookup"><span data-stu-id="c2609-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c2609-186">호출자 끝점의 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="c2609-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="c2609-188">name</span><span class="sxs-lookup"><span data-stu-id="c2609-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c2609-189">호출 수신자의 끝점에 대 한 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-190">Callercpunum<c13> Of코어</span><span class="sxs-lookup"><span data-stu-id="c2609-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="c2609-191">smallint</span><span class="sxs-lookup"><span data-stu-id="c2609-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="c2609-192">호출자 끝점의 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="c2609-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="c2609-194">smallint</span><span class="sxs-lookup"><span data-stu-id="c2609-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="c2609-195">호출 수신자의 끝점에 있는 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="c2609-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="c2609-197">int</span><span class="sxs-lookup"><span data-stu-id="c2609-197">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-198">호출자 끝점의 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="c2609-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="c2609-200">int</span><span class="sxs-lookup"><span data-stu-id="c2609-200">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-201">호출 수신자의 끝점에 대 한 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="c2609-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="c2609-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="c2609-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c2609-204">호출자의 시스템이 가상화 된 환경에서 실행 중인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="c2609-205">자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 끝점 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2609-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="c2609-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="c2609-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="c2609-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c2609-208">호출 수신자의 시스템이 가상화 된 환경에서 실행 중인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="c2609-209">자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 끝점 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2609-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="c2609-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c2609-211">상관 관계 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-211">Correlation key.</span></span> <span data-ttu-id="c2609-212"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013의 Sessioncorrelation 관계 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="c2609-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="c2609-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="c2609-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c2609-215">미디어 경로에 대 한 정보 (예: 직접 또는 릴레이)입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="c2609-216">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2609-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="c2609-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="c2609-218">int</span><span class="sxs-lookup"><span data-stu-id="c2609-218">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-219">호출자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-219">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="c2609-220">자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2609-220">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="c2609-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="c2609-222">int</span><span class="sxs-lookup"><span data-stu-id="c2609-222">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-223">호출 수신자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-223">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="c2609-224">자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2609-224">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-225">운송</span><span class="sxs-lookup"><span data-stu-id="c2609-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="c2609-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="c2609-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c2609-227">전송 종류: 0은 UDP이 고, 1은 TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="c2609-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c2609-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="c2609-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c2609-230">발신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-230">IP address of the caller.</span></span> <span data-ttu-id="c2609-231">IPv4 또는 IPv6 주소 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="c2609-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="c2609-233">int</span><span class="sxs-lookup"><span data-stu-id="c2609-233">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-234">호출자가 사용 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="c2609-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="c2609-236">다소</span><span class="sxs-lookup"><span data-stu-id="c2609-236">bit</span></span></p></td>
<td><p><span data-ttu-id="c2609-237">호출자가 간격 네트워크 내에 있는지 여부를 나타냅니다. 1은 호출자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고 0 이면 호출자가 네트워크 외부에 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="c2609-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c2609-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="c2609-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c2609-240">호출 수신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-240">IP address of the callee.</span></span> <span data-ttu-id="c2609-241">IPv4 또는 IPv6 주소 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="c2609-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="c2609-243">int</span><span class="sxs-lookup"><span data-stu-id="c2609-243">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-244">호출 수신자가 사용 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="c2609-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="c2609-246">다소</span><span class="sxs-lookup"><span data-stu-id="c2609-246">bit</span></span></p></td>
<td><p><span data-ttu-id="c2609-247">호출 수신자가 간격 네트워크 내에 있는지 여부를 나타냅니다. 1은 호출 수신자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고 0은 호출 수신자가 네트워크 외부에 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="c2609-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="c2609-249">name</span><span class="sxs-lookup"><span data-stu-id="c2609-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c2609-250">호출자 사이트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="c2609-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="c2609-252">name</span><span class="sxs-lookup"><span data-stu-id="c2609-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c2609-253">발신자 사이트의 국가/지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="c2609-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="c2609-255">name</span><span class="sxs-lookup"><span data-stu-id="c2609-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c2609-256">피호출자 사이트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="c2609-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="c2609-258">name</span><span class="sxs-lookup"><span data-stu-id="c2609-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c2609-259">피호출자 사이트의 국가/지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="c2609-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c2609-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="c2609-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c2609-262">발신자가 사용 하는 A/V Edge 서비스의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="c2609-263">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2609-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="c2609-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="c2609-265">int</span><span class="sxs-lookup"><span data-stu-id="c2609-265">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-266">호출자가 사용 하는 A/V Edge 서비스에 사용 되는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="c2609-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c2609-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="c2609-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c2609-269">호출 수신자가 사용 하는 A/V Edge 서비스의 IP 주소 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="c2609-270">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2609-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="c2609-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="c2609-272">int</span><span class="sxs-lookup"><span data-stu-id="c2609-272">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-273">호출 수신자가 사용 하는 A/V Edge 서비스에 사용 되는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="c2609-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="c2609-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2609-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2609-276">발신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="c2609-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="c2609-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2609-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2609-279">발신자의 렌더링 장치 이름.</span><span class="sxs-lookup"><span data-stu-id="c2609-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="c2609-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c2609-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2609-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2609-282">발신자의 캡처 장치 드라이버 이름.</span><span class="sxs-lookup"><span data-stu-id="c2609-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="c2609-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="c2609-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2609-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2609-285">호출자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="c2609-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="c2609-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2609-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2609-288">호출 수신자의 캡처 디바이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="c2609-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="c2609-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2609-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2609-291">피호출자의 렌더링 디바이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="c2609-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c2609-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2609-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2609-294">피호출자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="c2609-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c2609-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c2609-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2609-297">피호출자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="c2609-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="c2609-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="c2609-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c2609-300">발신자의 네트워크 연결 유형: 0이 유선 인 경우 1은 무선입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="c2609-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="c2609-302">다소</span><span class="sxs-lookup"><span data-stu-id="c2609-302">bit</span></span></p></td>
<td><p><span data-ttu-id="c2609-303">가상 개인 네트워크를 통해 연결 된 호출자가 VPN (가상 사설망) 인 경우 0이 고 VPN이 아닌 경우를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="c2609-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="c2609-305">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="c2609-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="c2609-306">Bps의 호출자 끝점에 대 한 네트워크 링크 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="c2609-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="c2609-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="c2609-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c2609-309">피호출자의 네트워크 연결 형식: 0이 유선 인 경우 1은 무선입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="c2609-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="c2609-311">다소</span><span class="sxs-lookup"><span data-stu-id="c2609-311">bit</span></span></p></td>
<td><p><span data-ttu-id="c2609-312">가상 개인 네트워크를 통해 연결 된 호출자가 VPN (가상 사설망) 인 경우 0이 고 VPN이 아닌 경우를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="c2609-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="c2609-314">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="c2609-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="c2609-315">Bps의 호출 수신자 끝점에 대 한 네트워크 링크 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="c2609-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="c2609-317">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-318">오디오 세션의 Narrowband 대화 SPECIALIST (두 오디오 스트림 모두 기준).</span><span class="sxs-lookup"><span data-stu-id="c2609-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="c2609-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="c2609-320">int</span><span class="sxs-lookup"><span data-stu-id="c2609-320">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-321">다양 한 정책 설정 (TURN, API, SDP, 정책 서버 등)을 지정 하 여 지정 된 보내기 쪽 스트림에 실제 대역폭을 적용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-321">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="c2609-322">대역폭 예측을 기준으로 낮은 유효 대역폭을 사용할 수 있기 때문에 효과적인 대역폭과 혼동 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-322">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="c2609-323">이 값은 기본적으로 전송 스트림에 의해 대역폭 예상에 의해 적용 되는 최대 대역폭을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-323">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="c2609-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="c2609-325">int</span><span class="sxs-lookup"><span data-stu-id="c2609-325">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-326">RTCP (실시간 제어 프로토콜) 통계의 평균 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="c2609-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="c2609-328">int</span><span class="sxs-lookup"><span data-stu-id="c2609-328">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-329">통화 중 최대 네트워크 지터.</span><span class="sxs-lookup"><span data-stu-id="c2609-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="c2609-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="c2609-331">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="c2609-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="c2609-332">통화 중의 평균 패킷 손실 율입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="c2609-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="c2609-334">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="c2609-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="c2609-335">통화 중에 최대 패킷 손실이 관찰 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="c2609-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="c2609-337">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="c2609-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="c2609-338">통화 중에 손실이 발생 한 경우 패킷 손실의 평균 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="c2609-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="c2609-340">int</span><span class="sxs-lookup"><span data-stu-id="c2609-340">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-341">통화 중에 손실 되는 패킷 손실의 평균 지속 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="c2609-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="c2609-343">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="c2609-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="c2609-344">패킷 손실의 버스트 간에 간격을 두는 경우 패킷 손실의 평균 밀도.</span><span class="sxs-lookup"><span data-stu-id="c2609-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="c2609-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="c2609-346">int</span><span class="sxs-lookup"><span data-stu-id="c2609-346">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-347">패킷 손실의 버스트 간 평균 간격 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="c2609-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="c2609-349">int</span><span class="sxs-lookup"><span data-stu-id="c2609-349">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-350">오디오 스트림의 패킷 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-351">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="c2609-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="c2609-352">int</span><span class="sxs-lookup"><span data-stu-id="c2609-352">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-353">오디오 스트림의 대역폭을 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="c2609-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="c2609-355">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-356">전체 통화에 대 한 네트워크 SPECIALIST 성능이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-356">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="c2609-357">범위는 0.0 ~ 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-357">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="c2609-358">이 메트릭은 지터 및 패킷 손실로 인해 네트워크 SPECIALIST 감소 된 양을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-358">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="c2609-359">허용 되는 품질은 0.5 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-359">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="c2609-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="c2609-361">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-362">통화 중에 최대 네트워크 SPECIALIST 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="c2609-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="c2609-364">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-365">지터로 인해 네트워크 SPECIALIST 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="c2609-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="c2609-367">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-368">패킷 손실로 인해 네트워크 SPECIALIST 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="c2609-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="c2609-370">int</span><span class="sxs-lookup"><span data-stu-id="c2609-370">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-371"><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a>에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="c2609-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="c2609-373">int</span><span class="sxs-lookup"><span data-stu-id="c2609-373">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-374">오디오 스트림의 샘플링 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="c2609-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="c2609-376">int</span><span class="sxs-lookup"><span data-stu-id="c2609-376">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-377">발신자가 보낸 오디오에 대 한 아날로그 게인 포스트 컨트롤 오디오 신호 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-377">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="c2609-378">이 메트릭의 단위는 dBmo입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-378">The unit for this metric is dBmo.</span></span> <span data-ttu-id="c2609-379">적절 한 품질을 위해서는 30 dBmo 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-379">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="c2609-380">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-380">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="c2609-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="c2609-382">int</span><span class="sxs-lookup"><span data-stu-id="c2609-382">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-383">발신자가 받은 오디오에 대 한 오디오 신호 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-383">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="c2609-384">이 메트릭의 단위는 dBmo입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-384">The unit for this metric is dBmo.</span></span> <span data-ttu-id="c2609-385">적절 한 품질을 위해서는 30 dBmo 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-385">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="c2609-386">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-386">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="c2609-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="c2609-388">int</span><span class="sxs-lookup"><span data-stu-id="c2609-388">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-389">발신자가 보낸 오디오에 대 한 아날로그 게인 사후 제어 오디오 노이즈 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-389">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="c2609-390">이 메트릭의 단위는 dBmo입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-390">The unit for this metric is dBmo.</span></span> <span data-ttu-id="c2609-391">적절 한 품질을 위해서는 35 dBmo 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-391">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="c2609-392">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-392">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="c2609-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="c2609-394">int</span><span class="sxs-lookup"><span data-stu-id="c2609-394">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-395">발신자가 받은 오디오에 대 한 아날로그 게인 포스트 컨트롤 오디오 잡음 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-395">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="c2609-396">이 메트릭의 단위는 dBmo입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-396">The unit for this metric is dBmo.</span></span> <span data-ttu-id="c2609-397">적절 한 품질을 위해서는 35 dBmo 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-397">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="c2609-398">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-398">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="c2609-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="c2609-400">int</span><span class="sxs-lookup"><span data-stu-id="c2609-400">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-401">호출자에 대 한 에코 반환 손실 보정.</span><span class="sxs-lookup"><span data-stu-id="c2609-401">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="c2609-402">이 메트릭의 단위는 dB입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-402">The unit for this metric is dB.</span></span> <span data-ttu-id="c2609-403">값이 낮을수록 화면 표시 수준이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-403">Lower values represent less echo.</span></span> <span data-ttu-id="c2609-404">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-404">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="c2609-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="c2609-406">int</span><span class="sxs-lookup"><span data-stu-id="c2609-406">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-407">호출자의 스피커 렌더링에 대 한 5 분 당 평균 결함입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-407">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="c2609-408">좋은 품질을 위해서는 5 분에 1 보다 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-408">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="c2609-409">A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-409">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="c2609-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="c2609-411">int</span><span class="sxs-lookup"><span data-stu-id="c2609-411">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-412">발신자의 마이크 캡처에 대 한 5 분 당 평균 결함.</span><span class="sxs-lookup"><span data-stu-id="c2609-412">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="c2609-413">좋은 품질을 위해서는 5 분에 1을 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-413">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="c2609-414">A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-414">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="c2609-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="c2609-416">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-417">발신자의 마이크 장치 시계 드리프트 속도 (CPU 클록 기준).</span><span class="sxs-lookup"><span data-stu-id="c2609-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="c2609-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="c2609-419">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-420">호출자의 스피커 장치 시계 드리프트 속도 (CPU 클록 기준)입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="c2609-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="c2609-422">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-423">평균 마이크 캡처 스트림 타임 스탬프 (밀리초) (통화의 마지막 20 초)</span><span class="sxs-lookup"><span data-stu-id="c2609-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="c2609-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="c2609-425">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-426">호출자의 스피커 평균 마지막 20 초 동안 스트림 타임 스탬프 오류를 밀리초 단위로 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="c2609-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="c2609-428">smallint</span><span class="sxs-lookup"><span data-stu-id="c2609-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="c2609-429">음성 스위치는 인터럽트 감소 기능이 있는 반 양방향 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="c2609-430">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2609-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="c2609-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="c2609-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="c2609-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c2609-433">호출자에 대 한 에코 이벤트의 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="c2609-434">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2609-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="c2609-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="c2609-436">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-437">발신자의 마이크 캡처 스트림에서 반향을 감지 하는 시간의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-437">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="c2609-438">헤드셋을 사용 하는 경우 값이 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-438">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="c2609-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="c2609-440">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-441">발신자의 전송 된 스트림에서 반향을 감지 하는 시간의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-441">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="c2609-442">송신 스트림의 화면 표시 백분율 에코 누수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-442">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="c2609-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="c2609-444">int</span><span class="sxs-lookup"><span data-stu-id="c2609-444">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-445">게이트웨이에서 호출자 오디오에 대 한 중재 서버의 신호 수준을 수신 했습니다. 이는 중재 서버에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-445">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="c2609-446">이 메트릭의 단위는 dBoV입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-446">The unit of this metric is dBoV.</span></span> <span data-ttu-id="c2609-447">좋은 품질을 위해서는 허용 되는 범위는-30 ~-18 dBoV 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-447">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="c2609-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="c2609-449">int</span><span class="sxs-lookup"><span data-stu-id="c2609-449">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-450">발신자의 오디오에 대 한 게이트웨이에서 중재 서버에 대 한 신호 수준을 수신 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-450">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="c2609-451">이는 중재 서버에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-451">This applies only to the Mediation Server.</span></span> <span data-ttu-id="c2609-452">이 메트릭의 단위는 dBoV입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-452">The unit of this metric is dBoV.</span></span> <span data-ttu-id="c2609-453">좋은 품질을 위해서는 허용 되는 범위가-50 dBoV 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-453">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="c2609-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="c2609-455">int</span><span class="sxs-lookup"><span data-stu-id="c2609-455">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-456">조정 서버 쪽의 자동 게인 제어 (AGC)를 호출자의 오디오에 적용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="c2609-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="c2609-458">o</span><span class="sxs-lookup"><span data-stu-id="c2609-458">float</span></span></p></td>
<td><p><span data-ttu-id="c2609-459">통화의 처음 30 초까지 호출자에 게 들어오는 신호에 대 한 루트 평균 제곱근 (RMS).</span><span class="sxs-lookup"><span data-stu-id="c2609-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="c2609-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="c2609-461">int</span><span class="sxs-lookup"><span data-stu-id="c2609-461">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-462">호출 수신자가 보낸 오디오에 대 한 아날로그 게인 포스트 컨트롤 오디오 신호 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-462">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="c2609-463">이 메트릭의 단위는 dBmo입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-463">The unit for this metric is dBmo.</span></span> <span data-ttu-id="c2609-464">적절 한 품질을 위해서는 30 dBmo 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-464">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="c2609-465">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-465">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="c2609-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="c2609-467">int</span><span class="sxs-lookup"><span data-stu-id="c2609-467">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-468">호출 수신자가 받은 오디오에 대 한 오디오 신호 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-468">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="c2609-469">이 메트릭의 단위는 dBmo입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-469">The unit for this metric is dBmo.</span></span> <span data-ttu-id="c2609-470">적절 한 품질을 위해서는 30 dBmo 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-470">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="c2609-471">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-471">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="c2609-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="c2609-473">int</span><span class="sxs-lookup"><span data-stu-id="c2609-473">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-474">호출 수신자가 보낸 오디오에 대 한 아날로그 게인 사후 제어 오디오 노이즈 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-474">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="c2609-475">이 메트릭의 단위는 dBmo입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-475">The unit for this metric is dBmo.</span></span> <span data-ttu-id="c2609-476">적절 한 품질을 위해서는 35 dBmo 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-476">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="c2609-477">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-477">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="c2609-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="c2609-479">int</span><span class="sxs-lookup"><span data-stu-id="c2609-479">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-480">호출 수신자가 받은 오디오에 대 한 아날로그 게인 사후 제어 오디오 노이즈 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-480">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="c2609-481">이 메트릭의 단위는 dBmo입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-481">The unit for this metric is dBmo.</span></span> <span data-ttu-id="c2609-482">적절 한 품질을 위해서는 35 dBmo 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-482">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="c2609-483">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-483">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="c2609-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="c2609-485">int</span><span class="sxs-lookup"><span data-stu-id="c2609-485">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-486">호출 수신자에 대 한 에코 반환 손실 보정.</span><span class="sxs-lookup"><span data-stu-id="c2609-486">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="c2609-487">이 메트릭의 단위는 dB입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-487">The unit for this metric is dB.</span></span> <span data-ttu-id="c2609-488">값이 낮을수록 화면 표시 수준이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-488">Lower values represent less echo.</span></span> <span data-ttu-id="c2609-489">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-489">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="c2609-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="c2609-491">int</span><span class="sxs-lookup"><span data-stu-id="c2609-491">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-492">호출 수신자의 스피커 렌더링에 대 한 5 분 당 평균 결함입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-492">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="c2609-493">좋은 품질을 위해서는 5 분에 1 보다 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-493">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="c2609-494">A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-494">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="c2609-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="c2609-496">int</span><span class="sxs-lookup"><span data-stu-id="c2609-496">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-497">호출 수신자의 마이크 캡처에 대 한 5 분 당 평균 결함입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-497">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="c2609-498">좋은 품질을 위해서는 5 분에 1을 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-498">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="c2609-499">A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-499">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="c2609-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="c2609-501">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-502">CPU 클록을 기준으로 피호출자의 마이크 장치 시계 드리프트 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="c2609-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="c2609-504">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-505">CPU 클록을 기준으로 호출 수신자의 스피커 장치 시계 드리프트 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="c2609-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="c2609-507">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-508">평균 마이크 캡처 스트림 타임 스탬프 (밀리초) (통화의 마지막 20 초)</span><span class="sxs-lookup"><span data-stu-id="c2609-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="c2609-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="c2609-510">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-511">호출 수신자의 스피커 평균 마지막 20 초 동안 밀리초 단위의 렌더링 스트림 타임 스탬프 오류</span><span class="sxs-lookup"><span data-stu-id="c2609-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="c2609-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="c2609-513">smallint</span><span class="sxs-lookup"><span data-stu-id="c2609-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="c2609-514">음성 스위치는 인터럽트 감소 기능이 있는 반 양방향 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="c2609-515">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2609-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="c2609-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="c2609-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="c2609-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c2609-518">호출 수신자에 대 한 에코 이벤트의 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="c2609-519">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c2609-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="c2609-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="c2609-521">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-522">호출 수신자의 마이크 캡처 스트림에서 화면 표시를 감지 하는 시간의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-522">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="c2609-523">헤드셋을 사용 하는 경우 값이 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-523">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="c2609-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="c2609-525">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-526">호출 수신자의 전송 된 스트림에서 반향을 감지 하는 시간의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-526">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="c2609-527">송신 스트림의 화면 표시 백분율 에코 누수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-527">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="c2609-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="c2609-529">int</span><span class="sxs-lookup"><span data-stu-id="c2609-529">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-530">게이트웨이에서 호출 수신자의 오디오에 대 한 중재 서버의 신호 수준을 수신 했습니다. 이는 중재 서버에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-530">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="c2609-531">이 메트릭의 단위는 dBoV입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-531">The unit of this metric is dBoV.</span></span> <span data-ttu-id="c2609-532">좋은 품질을 위해서는 허용 되는 범위는 [-30 ~-18] dBoV 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-532">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="c2609-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="c2609-534">int</span><span class="sxs-lookup"><span data-stu-id="c2609-534">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-535">게이트웨이에서 호출 수신자의 오디오에 대 한 조정 서버의 신호 수준을 수신 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-535">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="c2609-536">이는 중재 서버에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-536">This applies only to the Mediation Server.</span></span> <span data-ttu-id="c2609-537">이 메트릭의 단위는 dBoV입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-537">The unit of this metric is dBoV.</span></span> <span data-ttu-id="c2609-538">좋은 품질을 위해서는 허용 되는 범위가-50 dBoV 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-538">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="c2609-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="c2609-540">int</span><span class="sxs-lookup"><span data-stu-id="c2609-540">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-541">조정 서버 쪽의 자동 게인 제어 (AGC)를 호출 수신자의 오디오에 적용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="c2609-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="c2609-543">o</span><span class="sxs-lookup"><span data-stu-id="c2609-543">float</span></span></p></td>
<td><p><span data-ttu-id="c2609-544">호출의 처음 30 초까지 수신자에 대 한 수신 신호에 대 한 루트 평균 제곱근 (RMS)입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="c2609-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="c2609-546">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-547">오디오 치유에서 생성 한 숨겨진 샘플의 평균 비율을 일반적인 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="c2609-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="c2609-549">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-550">표준 샘플에 대 한 오디오 치유에서 생성 된 늘이기 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="c2609-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="c2609-552">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-553">오디오 치유에서 생성 한 압축 샘플의 평균 비율을 일반적인 샘플로 나타낸 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-554">왕복이</span><span class="sxs-lookup"><span data-stu-id="c2609-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="c2609-555">int</span><span class="sxs-lookup"><span data-stu-id="c2609-555">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-556">RTCP 통계에서 왕복 시간을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="c2609-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="c2609-558">int</span><span class="sxs-lookup"><span data-stu-id="c2609-558">int</span></span></p></td>
<td><p><span data-ttu-id="c2609-559">오디오 스트림의 최대 라운드트립 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="c2609-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="c2609-561">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-562">통화에 대 한 평균 광대역 네트워크 SPECIALIST.</span><span class="sxs-lookup"><span data-stu-id="c2609-562">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="c2609-563">이 메트릭은 사용 되는 패킷 손실, 지터 및 코덱에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-563">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="c2609-564">범위는 1.0 ~ 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-564">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="c2609-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="c2609-566">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-567">통화에 대 한 최소 광대역 네트워크 SPECIALIST.</span><span class="sxs-lookup"><span data-stu-id="c2609-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="c2609-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="c2609-569">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-570">음성 수준, 노이즈 수준 및 캡처 장치 특성을 포함 하 여 전송 되는 오디오에 대 한 평균 예측 광대역 SPECIALIST 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="c2609-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="c2609-572">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-573">통화에 대 한 최소 SendListenMOS.</span><span class="sxs-lookup"><span data-stu-id="c2609-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="c2609-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="c2609-575">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-576">음성 수준, 소음 수준, 코덱, 네트워크 상태 및 캡처 장치 특성을 포함 하 여 네트워크에서 받은 오디오에 대 한 평균 예측 광대역 SPECIALIST 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="c2609-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="c2609-578">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c2609-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c2609-579">통화에 대 한 최소 RecvListenMOS.</span><span class="sxs-lookup"><span data-stu-id="c2609-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2609-580">오디오 및 사용</span><span class="sxs-lookup"><span data-stu-id="c2609-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="c2609-581">다소</span><span class="sxs-lookup"><span data-stu-id="c2609-581">bit</span></span></p></td>
<td><p><span data-ttu-id="c2609-582">오디오 FEC 통화에 사용 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2609-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="c2609-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="c2609-584">다소</span><span class="sxs-lookup"><span data-stu-id="c2609-584">bit</span></span></p></td>
<td><p><span data-ttu-id="c2609-585">P-어설션된 식별 정보의 방향을 나타냅니다. 1은 스트림 방향이 호출자에서 호출 수신자 까지의 것임을 의미 합니다. 0은 스트림 방향이 피호출자부터 호출자에 게 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2609-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

