---
title: 'Lync Server 2013: VideoStreamDetail 보기'
description: 'Lync Server 2013: VideoStreamDetail 보기입니다.'
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
ms.openlocfilehash: a3f420c292627d15fd0d54f2eba01c565a49a72d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567974"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="7e43a-103">Lync Server 2013의 VideoStreamDetail 보기</span><span class="sxs-lookup"><span data-stu-id="7e43a-103">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e43a-104">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="7e43a-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="7e43a-105">VideoStreamDetail 보기는 데이터베이스에 각 비디오 스트림에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-105">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="7e43a-106">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e43a-107">열</span><span class="sxs-lookup"><span data-stu-id="7e43a-107">Column</span></span></th>
<th><span data-ttu-id="7e43a-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7e43a-108">Data Type</span></span></th>
<th><span data-ttu-id="7e43a-109">설명</span><span class="sxs-lookup"><span data-stu-id="7e43a-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-110">SessionTime</span><span class="sxs-lookup"><span data-stu-id="7e43a-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="7e43a-111">datetime</span><span class="sxs-lookup"><span data-stu-id="7e43a-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7e43a-112"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="7e43a-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="7e43a-114">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-114">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-115"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-116">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="7e43a-116">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="7e43a-117">tinyint</span><span class="sxs-lookup"><span data-stu-id="7e43a-117">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7e43a-118"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-119">StreamId</span><span class="sxs-lookup"><span data-stu-id="7e43a-119">StreamId</span></span></p></td>
<td><p><span data-ttu-id="7e43a-120">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-120">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-121">미디어 회선 내의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-121">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="7e43a-122">StartTime</span></span></p></td>
<td><p><span data-ttu-id="7e43a-123">datetime</span><span class="sxs-lookup"><span data-stu-id="7e43a-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="7e43a-124">세션 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-124">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-125">EndTime</span><span class="sxs-lookup"><span data-stu-id="7e43a-125">EndTime</span></span></p></td>
<td><p><span data-ttu-id="7e43a-126">datetime</span><span class="sxs-lookup"><span data-stu-id="7e43a-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="7e43a-127">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-127">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-128">CallPriority</span><span class="sxs-lookup"><span data-stu-id="7e43a-128">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="7e43a-129">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-129">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-130">통화 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-130">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-131">CallerPool</span><span class="sxs-lookup"><span data-stu-id="7e43a-131">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="7e43a-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7e43a-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-133">발신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-133">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-134">CalleePool</span><span class="sxs-lookup"><span data-stu-id="7e43a-134">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="7e43a-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7e43a-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-136">수신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-136">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-137">최초</span><span class="sxs-lookup"><span data-stu-id="7e43a-137">Caller</span></span></p></td>
<td><p><span data-ttu-id="7e43a-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7e43a-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-139">발신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-139">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-140">피호출자</span><span class="sxs-lookup"><span data-stu-id="7e43a-140">Callee</span></span></p></td>
<td><p><span data-ttu-id="7e43a-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7e43a-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-142">수신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-142">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-143">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="7e43a-143">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="7e43a-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7e43a-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-145">발신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-145">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-146">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="7e43a-146">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="7e43a-147">smallint</span><span class="sxs-lookup"><span data-stu-id="7e43a-147">smallint</span></span></p></td>
<td><p><span data-ttu-id="7e43a-148">발신자의 사용자 에이전트 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-148">Type of caller’s user agent.</span></span> <span data-ttu-id="7e43a-149">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e43a-149">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-150">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="7e43a-150">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="7e43a-151">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="7e43a-151">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-152">발신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-152">Category of caller’s user agent.</span></span> <span data-ttu-id="7e43a-153">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e43a-153">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-154">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="7e43a-154">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="7e43a-155">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7e43a-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-156">수신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-156">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-157">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="7e43a-157">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="7e43a-158">smallint</span><span class="sxs-lookup"><span data-stu-id="7e43a-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="7e43a-159">수신자의 사용자 에이전트 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-159">Type of callee’s user agent.</span></span> <span data-ttu-id="7e43a-160">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e43a-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-161">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="7e43a-161">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="7e43a-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="7e43a-162">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-163">수신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-163">Category of callee’s user agent.</span></span> <span data-ttu-id="7e43a-164">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e43a-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-165">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="7e43a-165">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="7e43a-166">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7e43a-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-167">발신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-167">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-168">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="7e43a-168">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="7e43a-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="7e43a-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-170">수신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-170">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-171">CallerOS</span><span class="sxs-lookup"><span data-stu-id="7e43a-171">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="7e43a-172">name</span><span class="sxs-lookup"><span data-stu-id="7e43a-172">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-173">발신자의 끝점 OS(운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-173">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-174">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="7e43a-174">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="7e43a-175">name</span><span class="sxs-lookup"><span data-stu-id="7e43a-175">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-176">수신자의 끝점 OS(운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-176">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-177">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="7e43a-177">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="7e43a-178">name</span><span class="sxs-lookup"><span data-stu-id="7e43a-178">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-179">발신자의 끝점 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-179">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-180">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="7e43a-180">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="7e43a-181">name</span><span class="sxs-lookup"><span data-stu-id="7e43a-181">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-182">수신자의 끝점 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-182">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-183">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="7e43a-183">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="7e43a-184">smallint</span><span class="sxs-lookup"><span data-stu-id="7e43a-184">smallint</span></span></p></td>
<td><p><span data-ttu-id="7e43a-185">발신자의 끝점 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-185">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-186">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="7e43a-186">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="7e43a-187">smallint</span><span class="sxs-lookup"><span data-stu-id="7e43a-187">smallint</span></span></p></td>
<td><p><span data-ttu-id="7e43a-188">수신자의 끝점 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-188">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-189">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="7e43a-189">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="7e43a-190">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-190">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-191">발신자의 끝점 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-191">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-192">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="7e43a-192">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="7e43a-193">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-193">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-194">수신자의 끝점 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-194">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-195">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="7e43a-195">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="7e43a-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="7e43a-196">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7e43a-197">발신자의 시스템이 가상화된 환경에서 실행 중인 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-197">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="7e43a-198">자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 Endpoint table</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e43a-198">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-199">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="7e43a-199">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="7e43a-200">tinyint</span><span class="sxs-lookup"><span data-stu-id="7e43a-200">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7e43a-201">수신자의 시스템이 가상화된 환경에서 실행 중인 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-201">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="7e43a-202">자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 Endpoint table</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e43a-202">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-203">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="7e43a-203">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="7e43a-204">tinyint</span><span class="sxs-lookup"><span data-stu-id="7e43a-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7e43a-205">직접 또는 중계와 같은 미디어 경로에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-205">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="7e43a-206">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e43a-206">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-207">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="7e43a-207">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="7e43a-208">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-208">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-p109">비트 플래그로 설명된 발신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e43a-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-211">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="7e43a-211">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="7e43a-212">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-212">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-p110">비트 플래그로 설명된 수신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e43a-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-215">전송</span><span class="sxs-lookup"><span data-stu-id="7e43a-215">Transport</span></span></p></td>
<td><p><span data-ttu-id="7e43a-216">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-216">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-217">전송 종류: 0은 UDP, 1은 TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-217">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-218">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="7e43a-218">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="7e43a-219">var (50)</span><span class="sxs-lookup"><span data-stu-id="7e43a-219">var(50)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-220">발신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-220">IP address of the caller.</span></span> <span data-ttu-id="7e43a-221">이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-221">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-222">CallerPort</span><span class="sxs-lookup"><span data-stu-id="7e43a-222">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="7e43a-223">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-223">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-224">발신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-224">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-225">CallerInside</span><span class="sxs-lookup"><span data-stu-id="7e43a-225">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="7e43a-226">비트만</span><span class="sxs-lookup"><span data-stu-id="7e43a-226">bit</span></span></p></td>
<td><p><span data-ttu-id="7e43a-p112">발신자가 조직 네트워크 내부에 있는지 여부를 나타냅니다. 1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-229">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="7e43a-229">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="7e43a-230">var (50)</span><span class="sxs-lookup"><span data-stu-id="7e43a-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-231">수신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-231">IP address of the callee.</span></span> <span data-ttu-id="7e43a-232">이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-233">CalleePort</span><span class="sxs-lookup"><span data-stu-id="7e43a-233">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="7e43a-234">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-234">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-235">수신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-235">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-236">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="7e43a-236">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="7e43a-237">비트만</span><span class="sxs-lookup"><span data-stu-id="7e43a-237">bit</span></span></p></td>
<td><p><span data-ttu-id="7e43a-238">수신자가 조직 네트워크 내부에 있는지 여부를 나타냅니다. 1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-238">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-239">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="7e43a-239">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="7e43a-240">name</span><span class="sxs-lookup"><span data-stu-id="7e43a-240">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-241">발신자 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-241">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-242">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="7e43a-242">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="7e43a-243">name</span><span class="sxs-lookup"><span data-stu-id="7e43a-243">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-244">발신자 사이트의 국가/지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-244">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-245">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="7e43a-245">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="7e43a-246">name</span><span class="sxs-lookup"><span data-stu-id="7e43a-246">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-247">수신자 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-247">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-248">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="7e43a-248">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="7e43a-249">name</span><span class="sxs-lookup"><span data-stu-id="7e43a-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-250">수신자 사이트의 국가/지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-250">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-251">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="7e43a-251">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="7e43a-252">var (50)</span><span class="sxs-lookup"><span data-stu-id="7e43a-252">var(50)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-253">A/V 에지 서비스에서 발신자가 사용하는 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-253">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="7e43a-254">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e43a-254">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-255">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="7e43a-255">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="7e43a-256">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-256">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-257">A/V 에지 서비스에서 발신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-257">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-258">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="7e43a-258">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="7e43a-259">var (50)</span><span class="sxs-lookup"><span data-stu-id="7e43a-259">var(50)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-260">A/V 에지 서비스에서 수신자가 사용하는 IP 주소 키입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-260">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="7e43a-261">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e43a-261">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-262">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="7e43a-262">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="7e43a-263">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-263">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-264">A/V 에지 서비스에서 수신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-264">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-265">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="7e43a-265">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="7e43a-266">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7e43a-266">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-267">발신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-267">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-268">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="7e43a-268">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="7e43a-269">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7e43a-269">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-270">발신자의 렌더링 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-270">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-271">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="7e43a-271">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="7e43a-272">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7e43a-272">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-273">발신자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-273">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-274">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="7e43a-274">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="7e43a-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7e43a-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-276">발신자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-276">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-277">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="7e43a-277">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="7e43a-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7e43a-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-279">수신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-279">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-280">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="7e43a-280">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="7e43a-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7e43a-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-282">수신자의 렌더링 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-282">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-283">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="7e43a-283">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="7e43a-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7e43a-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-285">수신자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-285">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-286">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="7e43a-286">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="7e43a-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="7e43a-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-288">수신자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-288">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-289">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="7e43a-289">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="7e43a-290">tinyint</span><span class="sxs-lookup"><span data-stu-id="7e43a-290">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7e43a-291">발신자의 네트워크 연결 형식입니다. 0은 유선, 1은 무선입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-291">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-292">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="7e43a-292">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="7e43a-293">비트만</span><span class="sxs-lookup"><span data-stu-id="7e43a-293">bit</span></span></p></td>
<td><p><span data-ttu-id="7e43a-p116">발신자가 VPN(가상 사설망)을 통해 연결되었는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-296">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="7e43a-296">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="7e43a-297">10 진수 (18,)</span><span class="sxs-lookup"><span data-stu-id="7e43a-297">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-298">발신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-298">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-299">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="7e43a-299">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="7e43a-300">tinyint</span><span class="sxs-lookup"><span data-stu-id="7e43a-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7e43a-301">수신자의 네트워크 연결 형식입니다. 0은 유선, 1은 무선입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-301">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-302">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="7e43a-302">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="7e43a-303">비트만</span><span class="sxs-lookup"><span data-stu-id="7e43a-303">bit</span></span></p></td>
<td><p><span data-ttu-id="7e43a-p117">수신자가 VPN(가상 사설망)을 통해 연결되었는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-306">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="7e43a-306">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="7e43a-307">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="7e43a-307">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-308">수신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-308">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-309">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="7e43a-309">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="7e43a-310">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="7e43a-310">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-311">오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).</span><span class="sxs-lookup"><span data-stu-id="7e43a-311">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-312">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="7e43a-312">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="7e43a-313">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-313">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-p118">다양한 정책 설정(TURN, API, SDP, 정책 서버 등)이 제공된 지정된 송신측 스트림에 적용되는 실제 대역폭입니다. 이 대역폭은 대역폭 예상에 따라 유효 대역폭이 더 낮을 수 있으므로 유효 대역폭과 혼동해서는 안됩니다. 이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-317">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="7e43a-317">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="7e43a-318">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-318">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-319">RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-319">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-320">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="7e43a-320">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="7e43a-321">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-321">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-322">통화 중 최대 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-322">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-323">왕복</span><span class="sxs-lookup"><span data-stu-id="7e43a-323">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="7e43a-324">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-324">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-325">RTCP 통계로부터의 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-325">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-326">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="7e43a-326">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="7e43a-327">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-327">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-328">오디오 스트림에 대한 최대 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-328">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-329">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="7e43a-329">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="7e43a-330">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="7e43a-330">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-331">통화 중 평균 패킷 손실 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-331">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-332">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="7e43a-332">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="7e43a-333">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="7e43a-333">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-334">통화 중 관측된 최대 패킷 손실입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-334">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-335">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="7e43a-335">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="7e43a-336">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-336">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-337">비디오 스트림에 대한 패킷 수입니다(실시간 전송 프로토콜, RTP).</span><span class="sxs-lookup"><span data-stu-id="7e43a-337">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-338">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="7e43a-338">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="7e43a-339">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-339">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-340">오디오 스트림에 대한 대역폭 예상치입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-340">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-341">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="7e43a-341">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="7e43a-342">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-342">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-343"><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a>에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-343">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-344">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="7e43a-344">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="7e43a-345">char (9)</span><span class="sxs-lookup"><span data-stu-id="7e43a-345">char(9)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-p119">픽셀 너비와 픽셀 높이를 곱한 수치의 비디오 해상도입니다. 문자열로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-348">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="7e43a-348">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="7e43a-349">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-349">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-350">비디오 스트림의 평균 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-350">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-351">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="7e43a-351">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="7e43a-352">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7e43a-352">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-353">수신된 비디오의 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-353">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-354">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="7e43a-354">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="7e43a-355">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7e43a-355">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-356">전송된 비디오의 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-356">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-357">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="7e43a-357">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="7e43a-358">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-358">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-359">비디오 세션 중의 최대 비디오 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-359">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-360">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="7e43a-360">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="7e43a-361">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7e43a-361">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-362">비디오 패킷이 손실된 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-362">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-363">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="7e43a-363">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="7e43a-364">소수 (9.4)</span><span class="sxs-lookup"><span data-stu-id="7e43a-364">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-365">총 비디오 프레임 중 손실된 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-365">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-366">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="7e43a-366">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="7e43a-367">비트만</span><span class="sxs-lookup"><span data-stu-id="7e43a-367">bit</span></span></p></td>
<td><p><span data-ttu-id="7e43a-368">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-368">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-369">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="7e43a-369">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="7e43a-370">int</span><span class="sxs-lookup"><span data-stu-id="7e43a-370">int</span></span></p></td>
<td><p><span data-ttu-id="7e43a-371">비디오에 할당된 평균 대역폭 양입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-371">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e43a-372">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="7e43a-372">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="7e43a-373">소수 (9.4)</span><span class="sxs-lookup"><span data-stu-id="7e43a-373">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="7e43a-374">총 비디오 프레임 중 손실된 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-374">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e43a-375">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="7e43a-375">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="7e43a-376">비트만</span><span class="sxs-lookup"><span data-stu-id="7e43a-376">bit</span></span></p></td>
<td><p><span data-ttu-id="7e43a-p120">p-어설션된 ID 정보에 대한 스트림 방향입니다. 1은 발신자에서 수신자로 방향이며, 0은 수신자에서 발신자로 방향입니다.</span><span class="sxs-lookup"><span data-stu-id="7e43a-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

