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
ms.openlocfilehash: 3d419800842fed080efe4005e7282a25c91f29df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518525"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="ec06d-102">Lync Server 2013의 VideoStreamDetail 보기</span><span class="sxs-lookup"><span data-stu-id="ec06d-102">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec06d-103">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="ec06d-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="ec06d-104">VideoStreamDetail 보기는 데이터베이스에 각 비디오 스트림에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="ec06d-105">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec06d-106">열</span><span class="sxs-lookup"><span data-stu-id="ec06d-106">Column</span></span></th>
<th><span data-ttu-id="ec06d-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ec06d-107">Data Type</span></span></th>
<th><span data-ttu-id="ec06d-108">설명</span><span class="sxs-lookup"><span data-stu-id="ec06d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="ec06d-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="ec06d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ec06d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ec06d-111"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="ec06d-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="ec06d-113">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-113">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="ec06d-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="ec06d-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="ec06d-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ec06d-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="ec06d-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="ec06d-119">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-119">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-120">미디어 회선 내의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="ec06d-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="ec06d-122">datetime</span><span class="sxs-lookup"><span data-stu-id="ec06d-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="ec06d-123">세션 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="ec06d-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="ec06d-125">datetime</span><span class="sxs-lookup"><span data-stu-id="ec06d-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="ec06d-126">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="ec06d-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="ec06d-128">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-128">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-129">통화 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="ec06d-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="ec06d-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ec06d-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-132">발신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="ec06d-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="ec06d-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ec06d-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-135">수신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-136">최초</span><span class="sxs-lookup"><span data-stu-id="ec06d-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="ec06d-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ec06d-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-138">발신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-139">피호출자</span><span class="sxs-lookup"><span data-stu-id="ec06d-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="ec06d-140">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ec06d-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-141">수신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="ec06d-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="ec06d-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ec06d-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-144">발신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="ec06d-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="ec06d-146">smallint</span><span class="sxs-lookup"><span data-stu-id="ec06d-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="ec06d-147">발신자의 사용자 에이전트 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-147">Type of caller’s user agent.</span></span> <span data-ttu-id="ec06d-148">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec06d-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="ec06d-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="ec06d-150">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ec06d-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-151">발신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-151">Category of caller’s user agent.</span></span> <span data-ttu-id="ec06d-152">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec06d-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="ec06d-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="ec06d-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ec06d-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-155">수신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="ec06d-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="ec06d-157">smallint</span><span class="sxs-lookup"><span data-stu-id="ec06d-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="ec06d-158">수신자의 사용자 에이전트 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-158">Type of callee’s user agent.</span></span> <span data-ttu-id="ec06d-159">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec06d-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="ec06d-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="ec06d-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ec06d-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-162">수신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-162">Category of callee’s user agent.</span></span> <span data-ttu-id="ec06d-163">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec06d-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="ec06d-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="ec06d-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ec06d-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-166">발신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="ec06d-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="ec06d-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ec06d-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-169">수신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="ec06d-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="ec06d-171">name</span><span class="sxs-lookup"><span data-stu-id="ec06d-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-172">발신자의 끝점 OS(운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="ec06d-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="ec06d-174">name</span><span class="sxs-lookup"><span data-stu-id="ec06d-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-175">수신자의 끝점 OS(운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="ec06d-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="ec06d-177">name</span><span class="sxs-lookup"><span data-stu-id="ec06d-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-178">발신자의 끝점 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="ec06d-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="ec06d-180">name</span><span class="sxs-lookup"><span data-stu-id="ec06d-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-181">수신자의 끝점 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="ec06d-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="ec06d-183">smallint</span><span class="sxs-lookup"><span data-stu-id="ec06d-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="ec06d-184">발신자의 끝점 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="ec06d-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="ec06d-186">smallint</span><span class="sxs-lookup"><span data-stu-id="ec06d-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="ec06d-187">수신자의 끝점 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="ec06d-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="ec06d-189">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-189">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-190">발신자의 끝점 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="ec06d-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="ec06d-192">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-192">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-193">수신자의 끝점 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="ec06d-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="ec06d-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="ec06d-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ec06d-196">발신자의 시스템이 가상화된 환경에서 실행 중인 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="ec06d-197">자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 Endpoint table</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec06d-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="ec06d-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="ec06d-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="ec06d-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ec06d-200">수신자의 시스템이 가상화된 환경에서 실행 중인 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="ec06d-201">자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 Endpoint table</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec06d-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="ec06d-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="ec06d-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="ec06d-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ec06d-204">직접 또는 중계와 같은 미디어 경로에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="ec06d-205">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec06d-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="ec06d-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="ec06d-207">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-207">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-p109">비트 플래그로 설명된 발신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec06d-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="ec06d-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="ec06d-211">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-211">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-p110">비트 플래그로 설명된 수신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec06d-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-214">전송</span><span class="sxs-lookup"><span data-stu-id="ec06d-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="ec06d-215">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-215">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-216">전송 종류: 0은 UDP, 1은 TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="ec06d-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ec06d-218">var (50)</span><span class="sxs-lookup"><span data-stu-id="ec06d-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-219">발신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-219">IP address of the caller.</span></span> <span data-ttu-id="ec06d-220">이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="ec06d-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="ec06d-222">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-222">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-223">발신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="ec06d-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="ec06d-225">비트만</span><span class="sxs-lookup"><span data-stu-id="ec06d-225">bit</span></span></p></td>
<td><p><span data-ttu-id="ec06d-p112">발신자가 조직 네트워크 내부에 있는지 여부를 나타냅니다. 1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="ec06d-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ec06d-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="ec06d-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-230">수신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-230">IP address of the callee.</span></span> <span data-ttu-id="ec06d-231">이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="ec06d-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="ec06d-233">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-233">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-234">수신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="ec06d-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="ec06d-236">비트만</span><span class="sxs-lookup"><span data-stu-id="ec06d-236">bit</span></span></p></td>
<td><p><span data-ttu-id="ec06d-237">수신자가 조직 네트워크 내부에 있는지 여부를 나타냅니다. 1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="ec06d-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="ec06d-239">name</span><span class="sxs-lookup"><span data-stu-id="ec06d-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-240">발신자 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="ec06d-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="ec06d-242">name</span><span class="sxs-lookup"><span data-stu-id="ec06d-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-243">발신자 사이트의 국가/지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="ec06d-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="ec06d-245">name</span><span class="sxs-lookup"><span data-stu-id="ec06d-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-246">수신자 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="ec06d-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="ec06d-248">name</span><span class="sxs-lookup"><span data-stu-id="ec06d-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-249">수신자 사이트의 국가/지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="ec06d-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ec06d-251">var (50)</span><span class="sxs-lookup"><span data-stu-id="ec06d-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-252">A/V 에지 서비스에서 발신자가 사용하는 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="ec06d-253">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ec06d-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="ec06d-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="ec06d-255">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-255">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-256">A/V 에지 서비스에서 발신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="ec06d-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="ec06d-258">var (50)</span><span class="sxs-lookup"><span data-stu-id="ec06d-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-259">A/V 에지 서비스에서 수신자가 사용하는 IP 주소 키입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="ec06d-260">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ec06d-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="ec06d-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="ec06d-262">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-262">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-263">A/V 에지 서비스에서 수신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="ec06d-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="ec06d-265">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ec06d-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-266">발신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="ec06d-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="ec06d-268">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ec06d-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-269">발신자의 렌더링 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="ec06d-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ec06d-271">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ec06d-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-272">발신자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="ec06d-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ec06d-274">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ec06d-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-275">발신자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="ec06d-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="ec06d-277">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ec06d-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-278">수신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="ec06d-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="ec06d-280">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ec06d-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-281">수신자의 렌더링 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="ec06d-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ec06d-283">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ec06d-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-284">수신자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="ec06d-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="ec06d-286">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ec06d-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-287">수신자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="ec06d-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="ec06d-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="ec06d-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ec06d-290">발신자의 네트워크 연결 형식입니다. 0은 유선, 1은 무선입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="ec06d-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="ec06d-292">비트만</span><span class="sxs-lookup"><span data-stu-id="ec06d-292">bit</span></span></p></td>
<td><p><span data-ttu-id="ec06d-p116">발신자가 VPN(가상 사설망)을 통해 연결되었는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="ec06d-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="ec06d-296">10 진수 (18,)</span><span class="sxs-lookup"><span data-stu-id="ec06d-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-297">발신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="ec06d-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="ec06d-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="ec06d-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ec06d-300">수신자의 네트워크 연결 형식입니다. 0은 유선, 1은 무선입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="ec06d-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="ec06d-302">비트만</span><span class="sxs-lookup"><span data-stu-id="ec06d-302">bit</span></span></p></td>
<td><p><span data-ttu-id="ec06d-p117">수신자가 VPN(가상 사설망)을 통해 연결되었는지 여부를 나타냅니다. 1은 VPN(가상 사설망), 0은 비VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="ec06d-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="ec06d-306">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="ec06d-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-307">수신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="ec06d-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="ec06d-309">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="ec06d-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-310">오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).</span><span class="sxs-lookup"><span data-stu-id="ec06d-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="ec06d-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="ec06d-312">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-312">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-p118">다양한 정책 설정(TURN, API, SDP, 정책 서버 등)이 제공된 지정된 송신측 스트림에 적용되는 실제 대역폭입니다. 이 대역폭은 대역폭 예상에 따라 유효 대역폭이 더 낮을 수 있으므로 유효 대역폭과 혼동해서는 안됩니다. 이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="ec06d-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="ec06d-317">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-317">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-318">RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="ec06d-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="ec06d-320">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-320">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-321">통화 중 최대 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-322">왕복</span><span class="sxs-lookup"><span data-stu-id="ec06d-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="ec06d-323">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-323">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-324">RTCP 통계로부터의 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="ec06d-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="ec06d-326">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-326">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-327">오디오 스트림에 대한 최대 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="ec06d-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="ec06d-329">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ec06d-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-330">통화 중 평균 패킷 손실 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="ec06d-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="ec06d-332">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="ec06d-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-333">통화 중 관측된 최대 패킷 손실입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="ec06d-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="ec06d-335">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-335">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-336">비디오 스트림에 대한 패킷 수입니다(실시간 전송 프로토콜, RTP).</span><span class="sxs-lookup"><span data-stu-id="ec06d-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-337">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="ec06d-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="ec06d-338">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-338">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-339">오디오 스트림에 대한 대역폭 예상치입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="ec06d-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="ec06d-341">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-341">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-342"><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a>에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="ec06d-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="ec06d-344">char (9)</span><span class="sxs-lookup"><span data-stu-id="ec06d-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-p119">픽셀 너비와 픽셀 높이를 곱한 수치의 비디오 해상도입니다. 문자열로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="ec06d-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="ec06d-348">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-348">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-349">비디오 스트림의 평균 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="ec06d-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="ec06d-351">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ec06d-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-352">수신된 비디오의 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="ec06d-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="ec06d-354">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ec06d-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-355">전송된 비디오의 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="ec06d-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="ec06d-357">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-357">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-358">비디오 세션 중의 최대 비디오 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="ec06d-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="ec06d-360">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="ec06d-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-361">비디오 패킷이 손실된 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="ec06d-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="ec06d-363">소수 (9.4)</span><span class="sxs-lookup"><span data-stu-id="ec06d-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-364">총 비디오 프레임 중 손실된 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="ec06d-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="ec06d-366">비트만</span><span class="sxs-lookup"><span data-stu-id="ec06d-366">bit</span></span></p></td>
<td><p><span data-ttu-id="ec06d-367">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="ec06d-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="ec06d-369">int</span><span class="sxs-lookup"><span data-stu-id="ec06d-369">int</span></span></p></td>
<td><p><span data-ttu-id="ec06d-370">비디오에 할당된 평균 대역폭 양입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec06d-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="ec06d-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="ec06d-372">소수 (9.4)</span><span class="sxs-lookup"><span data-stu-id="ec06d-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="ec06d-373">총 비디오 프레임 중 손실된 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec06d-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="ec06d-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="ec06d-375">비트만</span><span class="sxs-lookup"><span data-stu-id="ec06d-375">bit</span></span></p></td>
<td><p><span data-ttu-id="ec06d-p120">p-어설션된 ID 정보에 대한 스트림 방향입니다. 1은 발신자에서 수신자로 방향이며, 0은 수신자에서 발신자로 방향입니다.</span><span class="sxs-lookup"><span data-stu-id="ec06d-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

