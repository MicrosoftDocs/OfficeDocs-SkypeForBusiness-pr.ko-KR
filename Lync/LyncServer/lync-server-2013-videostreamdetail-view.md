---
title: 'Lync Server 2013: VideoStreamDetail 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfa754fbcc24377b07bab3b13473adb1c5e953ea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="93e07-102">Lync Server 2013의 VideoStreamDetail 보기</span><span class="sxs-lookup"><span data-stu-id="93e07-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93e07-103">_**마지막으로 수정한 주제:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="93e07-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="93e07-104">VideoStreamDetail 보기에는 데이터베이스의 각 비디오 스트림에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="93e07-105">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93e07-106">열</span><span class="sxs-lookup"><span data-stu-id="93e07-106">Column</span></span></th>
<th><span data-ttu-id="93e07-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="93e07-107">Data Type</span></span></th>
<th><span data-ttu-id="93e07-108">설명</span><span class="sxs-lookup"><span data-stu-id="93e07-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93e07-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="93e07-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="93e07-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="93e07-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="93e07-111"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="93e07-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="93e07-113">int</span><span class="sxs-lookup"><span data-stu-id="93e07-113">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="93e07-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="93e07-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="93e07-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="93e07-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="93e07-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="93e07-119">int</span><span class="sxs-lookup"><span data-stu-id="93e07-119">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-120">미디어 라인 내의 고유 ID.</span><span class="sxs-lookup"><span data-stu-id="93e07-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="93e07-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="93e07-122">dmtf</span><span class="sxs-lookup"><span data-stu-id="93e07-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="93e07-123">세션 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="93e07-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="93e07-125">dmtf</span><span class="sxs-lookup"><span data-stu-id="93e07-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="93e07-126">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="93e07-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="93e07-128">int</span><span class="sxs-lookup"><span data-stu-id="93e07-128">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-129">통화의 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="93e07-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="93e07-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="93e07-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="93e07-132">발신자 풀 FQDN.</span><span class="sxs-lookup"><span data-stu-id="93e07-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="93e07-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="93e07-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="93e07-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="93e07-135">호출 수신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-136">호출인</span><span class="sxs-lookup"><span data-stu-id="93e07-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="93e07-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="93e07-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="93e07-138">호출자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-139">피호출자</span><span class="sxs-lookup"><span data-stu-id="93e07-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="93e07-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="93e07-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="93e07-141">호출 수신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="93e07-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="93e07-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="93e07-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="93e07-144">호출자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="93e07-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="93e07-146">smallint</span><span class="sxs-lookup"><span data-stu-id="93e07-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="93e07-147">호출자의 사용자 에이전트 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-147">Type of caller’s user agent.</span></span> <span data-ttu-id="93e07-148">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="93e07-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="93e07-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="93e07-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="93e07-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="93e07-151">호출자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-151">Category of caller’s user agent.</span></span> <span data-ttu-id="93e07-152">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (체감 품질)</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="93e07-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="93e07-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="93e07-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="93e07-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="93e07-155">호출 수신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="93e07-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="93e07-157">smallint</span><span class="sxs-lookup"><span data-stu-id="93e07-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="93e07-158">호출 수신자의 사용자 에이전트 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-158">Type of callee’s user agent.</span></span> <span data-ttu-id="93e07-159">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="93e07-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="93e07-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="93e07-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="93e07-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="93e07-162">호출 수신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-162">Category of callee’s user agent.</span></span> <span data-ttu-id="93e07-163">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (체감 품질)</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="93e07-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="93e07-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="93e07-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="93e07-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="93e07-166">호출자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="93e07-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="93e07-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="93e07-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="93e07-169">호출 수신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="93e07-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="93e07-171">name</span><span class="sxs-lookup"><span data-stu-id="93e07-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="93e07-172">호출자 끝점의 OS (운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="93e07-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="93e07-174">name</span><span class="sxs-lookup"><span data-stu-id="93e07-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="93e07-175">호출 수신자의 끝점에 대 한 OS (운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="93e07-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="93e07-177">name</span><span class="sxs-lookup"><span data-stu-id="93e07-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="93e07-178">호출자 끝점의 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="93e07-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="93e07-180">name</span><span class="sxs-lookup"><span data-stu-id="93e07-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="93e07-181">호출 수신자의 끝점에 대 한 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-182">Callercpunum<c13> Of코어</span><span class="sxs-lookup"><span data-stu-id="93e07-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="93e07-183">smallint</span><span class="sxs-lookup"><span data-stu-id="93e07-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="93e07-184">호출자 끝점의 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="93e07-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="93e07-186">smallint</span><span class="sxs-lookup"><span data-stu-id="93e07-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="93e07-187">호출 수신자의 끝점에 대 한 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="93e07-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="93e07-189">int</span><span class="sxs-lookup"><span data-stu-id="93e07-189">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-190">호출자 끝점의 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="93e07-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="93e07-192">int</span><span class="sxs-lookup"><span data-stu-id="93e07-192">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-193">호출 수신자의 끝점에 대 한 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="93e07-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="93e07-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="93e07-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="93e07-196">호출자의 시스템이 가상화 된 환경에서 실행 중인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="93e07-197">자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 끝점 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="93e07-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="93e07-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="93e07-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="93e07-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="93e07-200">호출 수신자의 시스템이 가상화 된 환경에서 실행 중인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="93e07-201">자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 끝점 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="93e07-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="93e07-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="93e07-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="93e07-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="93e07-204">미디어 경로에 대 한 정보 (예: 직접 또는 릴레이)입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="93e07-205">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="93e07-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="93e07-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="93e07-207">int</span><span class="sxs-lookup"><span data-stu-id="93e07-207">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-208">호출자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-208">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="93e07-209">자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="93e07-209">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="93e07-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="93e07-211">int</span><span class="sxs-lookup"><span data-stu-id="93e07-211">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-212">호출 수신자의 bits 플래그에 설명 된 ICE (대화형 연결 설정) 프로세스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-212">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="93e07-213">자세한 내용은 경험의 품질 모니터링 서버 프로토콜 사양을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="93e07-213">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-214">운송</span><span class="sxs-lookup"><span data-stu-id="93e07-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="93e07-215">int</span><span class="sxs-lookup"><span data-stu-id="93e07-215">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-216">전송 종류: 0은 UDP이 고, 1은 TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="93e07-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="93e07-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="93e07-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="93e07-219">발신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-219">IP address of the caller.</span></span> <span data-ttu-id="93e07-220">IPv4 또는 IPv6 주소 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="93e07-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="93e07-222">int</span><span class="sxs-lookup"><span data-stu-id="93e07-222">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-223">호출자가 사용 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="93e07-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="93e07-225">다소</span><span class="sxs-lookup"><span data-stu-id="93e07-225">bit</span></span></p></td>
<td><p><span data-ttu-id="93e07-226">호출자가 조직 네트워크 내에 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="93e07-227">1은 발신자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고, 0 이면 발신자가 네트워크 외부에 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="93e07-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="93e07-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="93e07-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="93e07-230">호출 수신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-230">IP address of the callee.</span></span> <span data-ttu-id="93e07-231">IPv4 또는 IPv6 주소 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="93e07-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="93e07-233">int</span><span class="sxs-lookup"><span data-stu-id="93e07-233">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-234">호출 수신자가 사용 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="93e07-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="93e07-236">다소</span><span class="sxs-lookup"><span data-stu-id="93e07-236">bit</span></span></p></td>
<td><p><span data-ttu-id="93e07-237">호출자가 조직 네트워크 내에 있는지 여부를 나타냅니다. 1은 호출 수신자가 엔터프라이즈 네트워크 내에 있음을 의미 하 고 0은 호출 수신자가 네트워크 외부에 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="93e07-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="93e07-239">name</span><span class="sxs-lookup"><span data-stu-id="93e07-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="93e07-240">호출자 사이트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="93e07-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="93e07-242">name</span><span class="sxs-lookup"><span data-stu-id="93e07-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="93e07-243">발신자 사이트의 국가/지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="93e07-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="93e07-245">name</span><span class="sxs-lookup"><span data-stu-id="93e07-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="93e07-246">피호출자 사이트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="93e07-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="93e07-248">name</span><span class="sxs-lookup"><span data-stu-id="93e07-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="93e07-249">피호출자 사이트의 국가/지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="93e07-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="93e07-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="93e07-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="93e07-252">발신자가 사용 하는 A/V Edge 서비스의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="93e07-253">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="93e07-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="93e07-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="93e07-255">int</span><span class="sxs-lookup"><span data-stu-id="93e07-255">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-256">호출자가 사용 하는 A/V에 지 서비스의 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="93e07-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="93e07-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="93e07-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="93e07-259">호출 수신자가 사용 하는 A/V Edge 서비스의 IP 주소 키입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="93e07-260">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="93e07-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="93e07-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="93e07-262">int</span><span class="sxs-lookup"><span data-stu-id="93e07-262">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-263">호출 수신자가 사용 하는 A/V에 지 서비스의 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="93e07-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="93e07-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="93e07-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="93e07-266">발신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="93e07-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="93e07-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="93e07-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="93e07-269">발신자의 렌더링 장치 이름.</span><span class="sxs-lookup"><span data-stu-id="93e07-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="93e07-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="93e07-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="93e07-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="93e07-272">발신자의 캡처 장치 드라이버 이름.</span><span class="sxs-lookup"><span data-stu-id="93e07-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="93e07-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="93e07-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="93e07-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="93e07-275">호출자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="93e07-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="93e07-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="93e07-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="93e07-278">호출 수신자의 캡처 디바이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="93e07-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="93e07-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="93e07-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="93e07-281">피호출자의 렌더링 디바이스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="93e07-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="93e07-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="93e07-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="93e07-284">피호출자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="93e07-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="93e07-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="93e07-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="93e07-287">피호출자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="93e07-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="93e07-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="93e07-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="93e07-290">발신자의 네트워크 연결 유형: 0이 유선 인 경우 1은 무선입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="93e07-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="93e07-292">다소</span><span class="sxs-lookup"><span data-stu-id="93e07-292">bit</span></span></p></td>
<td><p><span data-ttu-id="93e07-293">호출자가 가상 개인 네트워크를 통해 연결 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="93e07-294">1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="93e07-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="93e07-296">10 진수 (18,)</span><span class="sxs-lookup"><span data-stu-id="93e07-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="93e07-297">Bps의 호출자 끝점에 대 한 네트워크 링크 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="93e07-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="93e07-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="93e07-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="93e07-300">피호출자의 네트워크 연결 형식: 0이 유선 인 경우 1은 무선입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="93e07-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="93e07-302">다소</span><span class="sxs-lookup"><span data-stu-id="93e07-302">bit</span></span></p></td>
<td><p><span data-ttu-id="93e07-303">호출 수신자가 가상 개인 네트워크를 통해 연결 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="93e07-304">1은 VPN (가상 사설망)이 고 0은 VPN이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="93e07-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="93e07-306">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="93e07-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="93e07-307">호출 수신자의 끝점에 대 한 네트워크 링크 속도 (bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="93e07-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="93e07-309">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="93e07-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="93e07-310">오디오 세션의 Narrowband 대화 SPECIALIST (두 오디오 스트림 모두 기준).</span><span class="sxs-lookup"><span data-stu-id="93e07-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="93e07-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="93e07-312">int</span><span class="sxs-lookup"><span data-stu-id="93e07-312">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-313">다양 한 정책 설정 (TURN, API, SDP, 정책 서버 등)을 지정 하 여 지정 된 보내기 쪽 스트림에 실제 대역폭을 적용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="93e07-314">대역폭 예측을 기준으로 낮은 유효 대역폭을 사용할 수 있기 때문에 효과적인 대역폭과 혼동 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="93e07-315">이 값이 기본적으로 최대 대역폭입니다. 송신 스트림은 대역폭 추정치에 의해 부과 된 제한을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="93e07-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="93e07-317">int</span><span class="sxs-lookup"><span data-stu-id="93e07-317">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-318">RTCP (실시간 제어 프로토콜) 통계의 평균 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="93e07-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="93e07-320">int</span><span class="sxs-lookup"><span data-stu-id="93e07-320">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-321">통화 중 최대 네트워크 지터.</span><span class="sxs-lookup"><span data-stu-id="93e07-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-322">왕복이</span><span class="sxs-lookup"><span data-stu-id="93e07-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="93e07-323">int</span><span class="sxs-lookup"><span data-stu-id="93e07-323">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-324">RTCP 통계에서 왕복 시간을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="93e07-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="93e07-326">int</span><span class="sxs-lookup"><span data-stu-id="93e07-326">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-327">오디오 스트림의 최대 라운드트립 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="93e07-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="93e07-329">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="93e07-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="93e07-330">통화 중의 평균 패킷 손실 율입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="93e07-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="93e07-332">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="93e07-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="93e07-333">통화 중에 최대 패킷 손실이 관찰 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="93e07-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="93e07-335">int</span><span class="sxs-lookup"><span data-stu-id="93e07-335">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-336">비디오 스트림의 패킷 개수 (리얼 시간 전송 프로토콜, RTP).</span><span class="sxs-lookup"><span data-stu-id="93e07-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-337">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="93e07-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="93e07-338">int</span><span class="sxs-lookup"><span data-stu-id="93e07-338">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-339">오디오 스트림의 대역폭을 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="93e07-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="93e07-341">int</span><span class="sxs-lookup"><span data-stu-id="93e07-341">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-342"><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a>에서 참조 하는 통화에 사용 되는 오디오 코덱입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="93e07-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="93e07-344">char (9)</span><span class="sxs-lookup"><span data-stu-id="93e07-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="93e07-345">픽셀 너비를 픽셀 높이로 곱한 비디오 해상도입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="93e07-346">문자열로 보고 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="93e07-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="93e07-348">int</span><span class="sxs-lookup"><span data-stu-id="93e07-348">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-349">비디오 스트림의 평균 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="93e07-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="93e07-351">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="93e07-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="93e07-352">수신 된 비디오의 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="93e07-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="93e07-354">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="93e07-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="93e07-355">전송 된 비디오의 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="93e07-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="93e07-357">int</span><span class="sxs-lookup"><span data-stu-id="93e07-357">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-358">비디오 세션 중에 최대 비디오 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="93e07-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="93e07-360">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="93e07-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="93e07-361">비디오 패킷이 손실 된 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="93e07-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="93e07-363">10 진수 (9.4)</span><span class="sxs-lookup"><span data-stu-id="93e07-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="93e07-364">손실 된 총 비디오 프레임의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="93e07-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="93e07-366">다소</span><span class="sxs-lookup"><span data-stu-id="93e07-366">bit</span></span></p></td>
<td><p><span data-ttu-id="93e07-367">사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="93e07-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="93e07-369">int</span><span class="sxs-lookup"><span data-stu-id="93e07-369">int</span></span></p></td>
<td><p><span data-ttu-id="93e07-370">비디오에 대해 할당 된 평균 대역폭 양입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93e07-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="93e07-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="93e07-372">10 진수 (9.4)</span><span class="sxs-lookup"><span data-stu-id="93e07-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="93e07-373">손실 된 총 비디오 프레임의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93e07-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="93e07-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="93e07-375">다소</span><span class="sxs-lookup"><span data-stu-id="93e07-375">bit</span></span></p></td>
<td><p><span data-ttu-id="93e07-376">P-어설션된 id 정보에 대 한 스트림 방향입니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="93e07-377">1은 스트림 방향이 호출자에서 호출 수신자 까지의 것임을 의미 합니다. 0은 스트림 방향이 피호출자부터 호출자에 게 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="93e07-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

