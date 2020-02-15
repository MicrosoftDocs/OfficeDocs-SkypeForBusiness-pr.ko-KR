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
ms.openlocfilehash: 311fb8fcd750261dbb5ef2e579fb092781526a19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="e043b-102">Lync Server 2013의 VideoStreamDetail 보기</span><span class="sxs-lookup"><span data-stu-id="e043b-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e043b-103">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e043b-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e043b-104">VideoStreamDetail 보기는 데이터베이스에 각 비디오 스트림에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="e043b-105">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e043b-106">열</span><span class="sxs-lookup"><span data-stu-id="e043b-106">Column</span></span></th>
<th><span data-ttu-id="e043b-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e043b-107">Data Type</span></span></th>
<th><span data-ttu-id="e043b-108">설명</span><span class="sxs-lookup"><span data-stu-id="e043b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e043b-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="e043b-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="e043b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="e043b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e043b-111"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="e043b-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="e043b-113">int</span><span class="sxs-lookup"><span data-stu-id="e043b-113">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="e043b-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="e043b-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="e043b-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e043b-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="e043b-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="e043b-119">int</span><span class="sxs-lookup"><span data-stu-id="e043b-119">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-120">미디어 회선 내의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="e043b-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="e043b-122">datetime</span><span class="sxs-lookup"><span data-stu-id="e043b-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="e043b-123">세션 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="e043b-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="e043b-125">datetime</span><span class="sxs-lookup"><span data-stu-id="e043b-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="e043b-126">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="e043b-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="e043b-128">int</span><span class="sxs-lookup"><span data-stu-id="e043b-128">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-129">통화 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="e043b-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="e043b-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e043b-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e043b-132">발신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="e043b-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="e043b-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e043b-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e043b-135">수신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-136">최초</span><span class="sxs-lookup"><span data-stu-id="e043b-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="e043b-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e043b-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e043b-138">발신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-139">피호출자</span><span class="sxs-lookup"><span data-stu-id="e043b-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="e043b-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e043b-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e043b-141">수신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="e043b-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e043b-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e043b-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e043b-144">발신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="e043b-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e043b-146">smallint</span><span class="sxs-lookup"><span data-stu-id="e043b-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="e043b-147">발신자의 사용자 에이전트 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-147">Type of caller’s user agent.</span></span> <span data-ttu-id="e043b-148">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e043b-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="e043b-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e043b-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e043b-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e043b-151">발신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-151">Category of caller’s user agent.</span></span> <span data-ttu-id="e043b-152">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e043b-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="e043b-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e043b-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e043b-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e043b-155">수신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="e043b-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e043b-157">smallint</span><span class="sxs-lookup"><span data-stu-id="e043b-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="e043b-158">수신자의 사용자 에이전트 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-158">Type of callee’s user agent.</span></span> <span data-ttu-id="e043b-159">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e043b-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="e043b-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e043b-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e043b-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e043b-162">수신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-162">Category of callee’s user agent.</span></span> <span data-ttu-id="e043b-163">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e043b-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="e043b-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e043b-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e043b-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e043b-166">발신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="e043b-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e043b-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e043b-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e043b-169">수신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="e043b-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="e043b-171">name</span><span class="sxs-lookup"><span data-stu-id="e043b-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e043b-172">발신자의 끝점 OS(운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="e043b-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="e043b-174">name</span><span class="sxs-lookup"><span data-stu-id="e043b-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e043b-175">수신자의 끝점 OS(운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="e043b-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="e043b-177">name</span><span class="sxs-lookup"><span data-stu-id="e043b-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e043b-178">발신자의 끝점 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="e043b-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="e043b-180">name</span><span class="sxs-lookup"><span data-stu-id="e043b-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e043b-181">수신자의 끝점 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="e043b-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="e043b-183">smallint</span><span class="sxs-lookup"><span data-stu-id="e043b-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="e043b-184">발신자의 끝점 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="e043b-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="e043b-186">smallint</span><span class="sxs-lookup"><span data-stu-id="e043b-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="e043b-187">수신자의 끝점 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="e043b-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="e043b-189">int</span><span class="sxs-lookup"><span data-stu-id="e043b-189">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-190">발신자의 끝점 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="e043b-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="e043b-192">int</span><span class="sxs-lookup"><span data-stu-id="e043b-192">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-193">수신자의 끝점 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="e043b-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="e043b-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="e043b-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e043b-196">발신자의 시스템이 가상화된 환경에서 실행 중인 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="e043b-197">자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 Endpoint table</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e043b-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="e043b-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="e043b-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="e043b-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e043b-200">수신자의 시스템이 가상화된 환경에서 실행 중인 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="e043b-201">자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 Endpoint table</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e043b-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="e043b-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="e043b-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="e043b-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e043b-204">직접 또는 중계와 같은 미디어 경로에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="e043b-205">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e043b-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e043b-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e043b-207">int</span><span class="sxs-lookup"><span data-stu-id="e043b-207">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-p109">비트 플래그로 설명된 발신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e043b-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e043b-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e043b-211">int</span><span class="sxs-lookup"><span data-stu-id="e043b-211">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-p110">비트 플래그로 설명된 수신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e043b-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-214">전송</span><span class="sxs-lookup"><span data-stu-id="e043b-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="e043b-215">int</span><span class="sxs-lookup"><span data-stu-id="e043b-215">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-216">전송 종류: 0은 UDP, 1은 TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="e043b-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e043b-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="e043b-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e043b-219">발신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-219">IP address of the caller.</span></span> <span data-ttu-id="e043b-220">이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="e043b-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="e043b-222">int</span><span class="sxs-lookup"><span data-stu-id="e043b-222">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-223">발신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="e043b-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="e043b-225">비트만</span><span class="sxs-lookup"><span data-stu-id="e043b-225">bit</span></span></p></td>
<td><p><span data-ttu-id="e043b-p112">발신자가 조직 네트워크 내부에 있는지 여부를 나타냅니다. 1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="e043b-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e043b-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="e043b-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e043b-230">수신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-230">IP address of the callee.</span></span> <span data-ttu-id="e043b-231">이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="e043b-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="e043b-233">int</span><span class="sxs-lookup"><span data-stu-id="e043b-233">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-234">수신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="e043b-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="e043b-236">비트만</span><span class="sxs-lookup"><span data-stu-id="e043b-236">bit</span></span></p></td>
<td><p><span data-ttu-id="e043b-237">수신자가 조직 네트워크 내부에 있는지 여부를 나타냅니다. 1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="e043b-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="e043b-239">name</span><span class="sxs-lookup"><span data-stu-id="e043b-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e043b-240">발신자 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="e043b-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="e043b-242">name</span><span class="sxs-lookup"><span data-stu-id="e043b-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e043b-243">발신자 사이트의 국가/지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="e043b-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="e043b-245">name</span><span class="sxs-lookup"><span data-stu-id="e043b-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e043b-246">수신자 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="e043b-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="e043b-248">name</span><span class="sxs-lookup"><span data-stu-id="e043b-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e043b-249">수신자 사이트의 국가/지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e043b-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e043b-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="e043b-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e043b-252">A/V 에지 서비스에서 발신자가 사용하는 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="e043b-253">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e043b-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="e043b-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e043b-255">int</span><span class="sxs-lookup"><span data-stu-id="e043b-255">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-256">A/V 에지 서비스에서 발신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e043b-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e043b-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="e043b-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e043b-259">A/V 에지 서비스에서 수신자가 사용하는 IP 주소 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="e043b-260">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e043b-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="e043b-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e043b-262">int</span><span class="sxs-lookup"><span data-stu-id="e043b-262">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-263">A/V 에지 서비스에서 수신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="e043b-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e043b-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e043b-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e043b-266">발신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="e043b-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e043b-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e043b-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e043b-269">발신자의 렌더링 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="e043b-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e043b-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e043b-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e043b-272">발신자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="e043b-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e043b-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e043b-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e043b-275">발신자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="e043b-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e043b-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e043b-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e043b-278">수신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="e043b-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e043b-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e043b-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e043b-281">수신자의 렌더링 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="e043b-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e043b-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e043b-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e043b-284">수신자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="e043b-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e043b-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e043b-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e043b-287">수신자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="e043b-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="e043b-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="e043b-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e043b-290">발신자의 네트워크 연결 형식입니다. 0은 유선, 1은 무선입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="e043b-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="e043b-292">비트만</span><span class="sxs-lookup"><span data-stu-id="e043b-292">bit</span></span></p></td>
<td><p><span data-ttu-id="e043b-p116">발신자가 VPN(가상 사설망)을 통해 연결되었는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="e043b-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="e043b-296">10 진수 (18,)</span><span class="sxs-lookup"><span data-stu-id="e043b-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="e043b-297">발신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="e043b-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="e043b-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="e043b-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e043b-300">수신자의 네트워크 연결 형식입니다. 0은 유선, 1은 무선입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="e043b-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="e043b-302">비트만</span><span class="sxs-lookup"><span data-stu-id="e043b-302">bit</span></span></p></td>
<td><p><span data-ttu-id="e043b-p117">수신자가 VPN(가상 사설망)을 통해 연결되었는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="e043b-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="e043b-306">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="e043b-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="e043b-307">수신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="e043b-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="e043b-309">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="e043b-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e043b-310">오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).</span><span class="sxs-lookup"><span data-stu-id="e043b-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="e043b-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="e043b-312">int</span><span class="sxs-lookup"><span data-stu-id="e043b-312">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-p118">다양한 정책 설정(TURN, API, SDP, 정책 서버 등)이 제공된 지정된 송신측 스트림에 적용되는 실제 대역폭입니다. 이 대역폭은 대역폭 예상에 따라 유효 대역폭이 더 낮을 수 있으므로 유효 대역폭과 혼동해서는 안됩니다. 이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="e043b-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="e043b-317">int</span><span class="sxs-lookup"><span data-stu-id="e043b-317">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-318">RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="e043b-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="e043b-320">int</span><span class="sxs-lookup"><span data-stu-id="e043b-320">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-321">통화 중 최대 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-322">왕복</span><span class="sxs-lookup"><span data-stu-id="e043b-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="e043b-323">int</span><span class="sxs-lookup"><span data-stu-id="e043b-323">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-324">RTCP 통계로부터의 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="e043b-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="e043b-326">int</span><span class="sxs-lookup"><span data-stu-id="e043b-326">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-327">오디오 스트림에 대한 최대 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="e043b-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="e043b-329">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="e043b-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="e043b-330">통화 중 평균 패킷 손실 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="e043b-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="e043b-332">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="e043b-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="e043b-333">통화 중 관측된 최대 패킷 손실입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="e043b-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="e043b-335">int</span><span class="sxs-lookup"><span data-stu-id="e043b-335">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-336">비디오 스트림에 대한 패킷 수입니다(실시간 전송 프로토콜, RTP).</span><span class="sxs-lookup"><span data-stu-id="e043b-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-337">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="e043b-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="e043b-338">int</span><span class="sxs-lookup"><span data-stu-id="e043b-338">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-339">오디오 스트림에 대한 대역폭 예상치입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="e043b-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="e043b-341">int</span><span class="sxs-lookup"><span data-stu-id="e043b-341">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-342"><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a>에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="e043b-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="e043b-344">char (9)</span><span class="sxs-lookup"><span data-stu-id="e043b-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="e043b-p119">픽셀 너비와 픽셀 높이를 곱한 수치의 비디오 해상도입니다. 문자열로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="e043b-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="e043b-348">int</span><span class="sxs-lookup"><span data-stu-id="e043b-348">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-349">비디오 스트림의 평균 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="e043b-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="e043b-351">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e043b-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e043b-352">수신된 비디오의 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="e043b-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="e043b-354">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e043b-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e043b-355">전송된 비디오의 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="e043b-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="e043b-357">int</span><span class="sxs-lookup"><span data-stu-id="e043b-357">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-358">비디오 세션 중의 최대 비디오 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="e043b-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="e043b-360">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e043b-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e043b-361">비디오 패킷이 손실된 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="e043b-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="e043b-363">소수 (9.4)</span><span class="sxs-lookup"><span data-stu-id="e043b-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="e043b-364">총 비디오 프레임 중 손실된 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="e043b-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="e043b-366">비트만</span><span class="sxs-lookup"><span data-stu-id="e043b-366">bit</span></span></p></td>
<td><p><span data-ttu-id="e043b-367">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="e043b-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="e043b-369">int</span><span class="sxs-lookup"><span data-stu-id="e043b-369">int</span></span></p></td>
<td><p><span data-ttu-id="e043b-370">비디오에 할당된 평균 대역폭 양입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e043b-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="e043b-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="e043b-372">소수 (9.4)</span><span class="sxs-lookup"><span data-stu-id="e043b-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="e043b-373">총 비디오 프레임 중 손실된 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e043b-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="e043b-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="e043b-375">비트만</span><span class="sxs-lookup"><span data-stu-id="e043b-375">bit</span></span></p></td>
<td><p><span data-ttu-id="e043b-p120">p-어설션된 ID 정보에 대한 스트림 방향입니다. 1은 발신자에서 수신자로 방향이며, 0은 수신자에서 발신자로 방향입니다.</span><span class="sxs-lookup"><span data-stu-id="e043b-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

