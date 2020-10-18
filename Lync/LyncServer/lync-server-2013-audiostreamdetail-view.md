---
title: 'Lync Server 2013: 오디오 Streamdetail 보기'
description: 'Lync Server 2013: 오디오 Streamdetail 보기입니다.'
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
ms.openlocfilehash: 92c4c9bbb4f126e242e28d835222f6ba2af89d8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573054"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="8f079-103">Lync Server 2013의 오디오 Streamdetail 보기</span><span class="sxs-lookup"><span data-stu-id="8f079-103">AudioStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f079-104">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="8f079-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="8f079-105">AudioStreamDetail 보기에는 데이터베이스의 각 오디오 스트림에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-105">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="8f079-106">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f079-107">열</span><span class="sxs-lookup"><span data-stu-id="8f079-107">Column</span></span></th>
<th><span data-ttu-id="8f079-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8f079-108">Data Type</span></span></th>
<th><span data-ttu-id="8f079-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="8f079-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f079-110">SessionTime</span><span class="sxs-lookup"><span data-stu-id="8f079-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="8f079-111">datetime</span><span class="sxs-lookup"><span data-stu-id="8f079-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8f079-112"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="8f079-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="8f079-114">int</span><span class="sxs-lookup"><span data-stu-id="8f079-114">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-115"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-116">StreamId</span><span class="sxs-lookup"><span data-stu-id="8f079-116">StreamId</span></span></p></td>
<td><p><span data-ttu-id="8f079-117">int</span><span class="sxs-lookup"><span data-stu-id="8f079-117">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-118">미디어 회선 내의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-118">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-119">StartTime</span><span class="sxs-lookup"><span data-stu-id="8f079-119">StartTime</span></span></p></td>
<td><p><span data-ttu-id="8f079-120">datetime</span><span class="sxs-lookup"><span data-stu-id="8f079-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="8f079-121">세션 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-121">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-122">EndTime</span><span class="sxs-lookup"><span data-stu-id="8f079-122">EndTime</span></span></p></td>
<td><p><span data-ttu-id="8f079-123">datetime</span><span class="sxs-lookup"><span data-stu-id="8f079-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="8f079-124">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-124">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-125">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="8f079-125">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="8f079-126">비트만</span><span class="sxs-lookup"><span data-stu-id="8f079-126">bit</span></span></p></td>
<td><p><span data-ttu-id="8f079-127">대화 상자 범주: 0은 Lync server를 중재 서버 다리에 대 한 것입니다. 1은 PSTN 게이트웨이 레그에 대 한 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-127">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-128">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="8f079-128">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="8f079-129">비트만</span><span class="sxs-lookup"><span data-stu-id="8f079-129">bit</span></span></p></td>
<td><p><span data-ttu-id="8f079-130">통화가 바이패스되었는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-130">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-131">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="8f079-131">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="8f079-132">int</span><span class="sxs-lookup"><span data-stu-id="8f079-132">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p102">이 필드는(제공된 경우) 바이패스 ID가 일치한 경우에도 통화가 바이패스되지 않은 이유를 나타냅니다. 하나의 값만 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="8f079-135">0x0001 -  기본 네트워크 어댑터에 대한 알 수 없는 바이패스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-135">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-136">CallPriority</span><span class="sxs-lookup"><span data-stu-id="8f079-136">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="8f079-137">int</span><span class="sxs-lookup"><span data-stu-id="8f079-137">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-138">통화 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-138">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-139">CallerPool</span><span class="sxs-lookup"><span data-stu-id="8f079-139">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="8f079-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8f079-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8f079-141">발신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-141">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-142">CalleePool</span><span class="sxs-lookup"><span data-stu-id="8f079-142">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="8f079-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8f079-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8f079-144">수신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-144">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-145">최초</span><span class="sxs-lookup"><span data-stu-id="8f079-145">Caller</span></span></p></td>
<td><p><span data-ttu-id="8f079-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8f079-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8f079-147">발신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-147">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-148">피호출자</span><span class="sxs-lookup"><span data-stu-id="8f079-148">Callee</span></span></p></td>
<td><p><span data-ttu-id="8f079-149">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8f079-149">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8f079-150">수신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-150">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-151">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="8f079-151">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="8f079-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8f079-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8f079-153">발신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-153">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-154">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="8f079-154">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="8f079-155">smallint</span><span class="sxs-lookup"><span data-stu-id="8f079-155">smallint</span></span></p></td>
<td><p><span data-ttu-id="8f079-156">발신자의 사용자 에이전트 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-156">Type of the caller’s user agent.</span></span> <span data-ttu-id="8f079-157">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f079-157">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-158">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="8f079-158">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="8f079-159">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="8f079-159">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="8f079-160">발신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-160">Category of the caller’s user agent.</span></span> <span data-ttu-id="8f079-161">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f079-161">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-162">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="8f079-162">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="8f079-163">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8f079-163">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8f079-164">수신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-164">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-165">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="8f079-165">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="8f079-166">smallint</span><span class="sxs-lookup"><span data-stu-id="8f079-166">smallint</span></span></p></td>
<td><p><span data-ttu-id="8f079-167">수신자의 사용자 에이전트 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-167">Type of callee’s user agent.</span></span> <span data-ttu-id="8f079-168">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f079-168">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-169">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="8f079-169">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="8f079-170">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="8f079-170">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="8f079-171">수신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-171">Category of callee’s user agent.</span></span> <span data-ttu-id="8f079-172">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f079-172">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-173">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="8f079-173">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="8f079-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8f079-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8f079-175">발신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-175">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-176">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="8f079-176">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="8f079-177">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8f079-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8f079-178">수신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-178">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-179">CallerOS</span><span class="sxs-lookup"><span data-stu-id="8f079-179">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="8f079-180">name</span><span class="sxs-lookup"><span data-stu-id="8f079-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8f079-181">발신자의 끝점 OS(운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-181">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-182">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="8f079-182">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="8f079-183">name</span><span class="sxs-lookup"><span data-stu-id="8f079-183">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8f079-184">수신자의 끝점 OS(운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-184">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-185">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="8f079-185">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="8f079-186">name</span><span class="sxs-lookup"><span data-stu-id="8f079-186">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8f079-187">발신자의 끝점 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-187">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-188">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="8f079-188">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="8f079-189">name</span><span class="sxs-lookup"><span data-stu-id="8f079-189">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8f079-190">수신자의 끝점 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-190">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-191">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="8f079-191">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="8f079-192">smallint</span><span class="sxs-lookup"><span data-stu-id="8f079-192">smallint</span></span></p></td>
<td><p><span data-ttu-id="8f079-193">발신자 끝점의 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-193">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-194">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="8f079-194">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="8f079-195">smallint</span><span class="sxs-lookup"><span data-stu-id="8f079-195">smallint</span></span></p></td>
<td><p><span data-ttu-id="8f079-196">수신자 끝점의 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-196">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-197">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="8f079-197">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="8f079-198">int</span><span class="sxs-lookup"><span data-stu-id="8f079-198">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-199">발신자의 끝점 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-199">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-200">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="8f079-200">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="8f079-201">int</span><span class="sxs-lookup"><span data-stu-id="8f079-201">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-202">수신자의 끝점 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-202">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-203">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="8f079-203">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="8f079-204">tinyint</span><span class="sxs-lookup"><span data-stu-id="8f079-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8f079-205">발신자의 시스템이 가상화된 환경에서 실행 중인 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-205">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="8f079-206">자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 Endpoint table</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f079-206">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-207">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="8f079-207">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="8f079-208">tinyint</span><span class="sxs-lookup"><span data-stu-id="8f079-208">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8f079-209">수신자의 시스템이 가상화된 환경에서 실행 중인 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-209">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="8f079-210">자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 Endpoint table</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f079-210">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-211">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="8f079-211">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8f079-212">상관 관계 키입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-212">Correlation key.</span></span> <span data-ttu-id="8f079-213"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013의 Sessioncorrelation 관계 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-213">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-214">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="8f079-214">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="8f079-215">tinyint</span><span class="sxs-lookup"><span data-stu-id="8f079-215">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8f079-216">직접 또는 중계와 같은 미디어 경로에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-216">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="8f079-217">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f079-217">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-218">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="8f079-218">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="8f079-219">int</span><span class="sxs-lookup"><span data-stu-id="8f079-219">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p111">비트 플래그로 설명된 발신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f079-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-222">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="8f079-222">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="8f079-223">int</span><span class="sxs-lookup"><span data-stu-id="8f079-223">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p112">비트 플래그로 설명된 수신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f079-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-226">전송</span><span class="sxs-lookup"><span data-stu-id="8f079-226">Transport</span></span></p></td>
<td><p><span data-ttu-id="8f079-227">tinyint</span><span class="sxs-lookup"><span data-stu-id="8f079-227">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8f079-228">전송 종류: 0은 UDP, 1은 TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-228">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-229">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="8f079-229">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8f079-230">var (50)</span><span class="sxs-lookup"><span data-stu-id="8f079-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8f079-231">발신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-231">IP address of the caller.</span></span> <span data-ttu-id="8f079-232">이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-233">CallerPort</span><span class="sxs-lookup"><span data-stu-id="8f079-233">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="8f079-234">int</span><span class="sxs-lookup"><span data-stu-id="8f079-234">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-235">발신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-235">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-236">CallerInside</span><span class="sxs-lookup"><span data-stu-id="8f079-236">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="8f079-237">비트만</span><span class="sxs-lookup"><span data-stu-id="8f079-237">bit</span></span></p></td>
<td><p><span data-ttu-id="8f079-238">발신자가 내부 네트워크에 있는지 여부를 나타냅니다. 1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-238">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-239">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="8f079-239">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8f079-240">var (50)</span><span class="sxs-lookup"><span data-stu-id="8f079-240">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8f079-241">수신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-241">IP address of the callee.</span></span> <span data-ttu-id="8f079-242">이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-242">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-243">CalleePort</span><span class="sxs-lookup"><span data-stu-id="8f079-243">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="8f079-244">int</span><span class="sxs-lookup"><span data-stu-id="8f079-244">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-245">수신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-245">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-246">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="8f079-246">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="8f079-247">비트만</span><span class="sxs-lookup"><span data-stu-id="8f079-247">bit</span></span></p></td>
<td><p><span data-ttu-id="8f079-248">수신자가 내부 네트워크에 있는지 여부를 나타냅니다. 1은 수신자가 회사 네트워크 내에 있음을 의미하고 0은 수신자가 네트워크 외부에 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-248">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-249">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="8f079-249">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="8f079-250">name</span><span class="sxs-lookup"><span data-stu-id="8f079-250">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8f079-251">발신자 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-251">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-252">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="8f079-252">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="8f079-253">name</span><span class="sxs-lookup"><span data-stu-id="8f079-253">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8f079-254">발신자 사이트의 국가/지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-254">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-255">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="8f079-255">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="8f079-256">name</span><span class="sxs-lookup"><span data-stu-id="8f079-256">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8f079-257">수신자 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-257">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-258">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="8f079-258">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="8f079-259">name</span><span class="sxs-lookup"><span data-stu-id="8f079-259">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="8f079-260">수신자 사이트의 국가/지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-260">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-261">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="8f079-261">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8f079-262">var (50)</span><span class="sxs-lookup"><span data-stu-id="8f079-262">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8f079-263">A/V 에지 서비스에서 발신자가 사용하는 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-263">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="8f079-264">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f079-264">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-265">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="8f079-265">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="8f079-266">int</span><span class="sxs-lookup"><span data-stu-id="8f079-266">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-267">발신자가 사용하는 A/V 에지 서비스에서 사용되는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-267">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-268">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="8f079-268">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="8f079-269">var (50)</span><span class="sxs-lookup"><span data-stu-id="8f079-269">var(50)</span></span></p></td>
<td><p><span data-ttu-id="8f079-270">A/V 에지 서비스에서 수신자가 사용하는 IP 주소 키입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-270">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="8f079-271">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f079-271">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-272">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="8f079-272">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="8f079-273">int</span><span class="sxs-lookup"><span data-stu-id="8f079-273">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-274">수신자가 사용하는 A/V 에지 서비스에서 사용되는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-274">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-275">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="8f079-275">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="8f079-276">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8f079-276">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8f079-277">발신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-277">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-278">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="8f079-278">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="8f079-279">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8f079-279">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8f079-280">발신자의 렌더링 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-280">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-281">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="8f079-281">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8f079-282">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8f079-282">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8f079-283">발신자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-283">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-284">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="8f079-284">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="8f079-285">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8f079-285">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8f079-286">발신자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-286">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-287">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="8f079-287">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="8f079-288">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8f079-288">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8f079-289">수신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-289">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-290">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="8f079-290">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="8f079-291">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8f079-291">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8f079-292">수신자의 렌더링 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-292">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-293">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="8f079-293">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8f079-294">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8f079-294">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8f079-295">수신자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-295">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-296">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="8f079-296">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="8f079-297">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="8f079-297">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8f079-298">수신자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-298">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-299">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="8f079-299">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="8f079-300">tinyint</span><span class="sxs-lookup"><span data-stu-id="8f079-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8f079-301">발신자의 네트워크 연결 형식입니다. 0은 유선, 1은 무선입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-301">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-302">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="8f079-302">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="8f079-303">비트만</span><span class="sxs-lookup"><span data-stu-id="8f079-303">bit</span></span></p></td>
<td><p><span data-ttu-id="8f079-304">발신자가 가상 사설망을 통해 연결되어 있는지 여부를 나타냅니다.1은 VPN(가상 사설망), 0은 VPN 외입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-304">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-305">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="8f079-305">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="8f079-306">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="8f079-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="8f079-307">발신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-307">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-308">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="8f079-308">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="8f079-309">tinyint</span><span class="sxs-lookup"><span data-stu-id="8f079-309">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8f079-310">수신자의 네트워크 연결 형식입니다. 0은 유선, 1은 무선입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-310">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-311">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="8f079-311">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="8f079-312">비트만</span><span class="sxs-lookup"><span data-stu-id="8f079-312">bit</span></span></p></td>
<td><p><span data-ttu-id="8f079-313">수신자가 가상 사설망을 통해 연결되어 있는지 여부를 나타냅니다.1은 VPN(가상 사설망), 0은 VPN 외입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-313">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-314">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="8f079-314">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="8f079-315">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="8f079-315">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="8f079-316">수신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-316">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-317">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="8f079-317">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="8f079-318">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-318">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-319">오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).</span><span class="sxs-lookup"><span data-stu-id="8f079-319">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-320">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="8f079-320">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="8f079-321">int</span><span class="sxs-lookup"><span data-stu-id="8f079-321">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p117">다양한 정책 설정(TURN, API, SDP, 정책 서버 등)이 제공된 지정된 송신측 스트림에 적용되는 실제 대역폭입니다. 이 대역폭은 대역폭 예상에 따라 유효 대역폭이 더 낮을 수 있으므로 유효 대역폭과 혼동해서는 안됩니다. 이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-325">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="8f079-325">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="8f079-326">int</span><span class="sxs-lookup"><span data-stu-id="8f079-326">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-327">RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-327">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-328">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="8f079-328">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="8f079-329">int</span><span class="sxs-lookup"><span data-stu-id="8f079-329">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-330">통화 중 최대 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-330">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-331">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="8f079-331">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="8f079-332">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="8f079-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="8f079-333">통화 중 평균 패킷 손실 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-333">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-334">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="8f079-334">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="8f079-335">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="8f079-335">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="8f079-336">통화 중 관측된 최대 패킷 손실량입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-336">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-337">버스트 밀도</span><span class="sxs-lookup"><span data-stu-id="8f079-337">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="8f079-338">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="8f079-338">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="8f079-339">통화 중 손실량이 많아지는 기간 동안의 평균 패킷 손실 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-339">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-340">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="8f079-340">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="8f079-341">int</span><span class="sxs-lookup"><span data-stu-id="8f079-341">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-342">통화 중 손실량이 많아지는 기간 동안의 평균 패킷 손실 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-342">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-343">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="8f079-343">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="8f079-344">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="8f079-344">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="8f079-345">패킷 손실이 최고치인 기간 사이의 간격 중에 발생하는 평균 패킷 손실 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-345">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-346">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="8f079-346">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="8f079-347">int</span><span class="sxs-lookup"><span data-stu-id="8f079-347">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-348">패킷 손실이 최고치인 기간 사이의 간격에 대한 평균 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-348">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-349">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="8f079-349">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="8f079-350">int</span><span class="sxs-lookup"><span data-stu-id="8f079-350">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-351">오디오 스트림에 대한 패킷 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-351">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-352">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="8f079-352">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="8f079-353">int</span><span class="sxs-lookup"><span data-stu-id="8f079-353">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-354">오디오 스트림에 대한 대역폭 예상치입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-354">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-355">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="8f079-355">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="8f079-356">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-356">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-p118">전체 통화에 대한 네트워크 MOS 저하입니다. 범위는 0.0에서 5.0까지입니다. 이 메트릭은 지터 및 패킷 손실로 인해 감소된 네트워크 MOS의 양을 보여 줍니다. 적정 품질을 위해서는 0.5 미만이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-361">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="8f079-361">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="8f079-362">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-362">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-363">통화 중 최대 네트워크 MOS 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-363">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-364">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="8f079-364">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="8f079-365">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-365">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-366">지터로 인해 발생한 네트워크 MOS 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-366">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-367">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="8f079-367">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="8f079-368">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-368">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-369">패킷 손실로 인해 발생한 네트워크 MOS 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-369">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-370">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="8f079-370">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="8f079-371">int</span><span class="sxs-lookup"><span data-stu-id="8f079-371">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-372"><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a>에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-372">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-373">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="8f079-373">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="8f079-374">int</span><span class="sxs-lookup"><span data-stu-id="8f079-374">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-375">오디오 스트림에 대한 샘플링 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-375">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-376">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="8f079-376">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="8f079-377">int</span><span class="sxs-lookup"><span data-stu-id="8f079-377">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p119">발신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-382">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="8f079-382">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="8f079-383">int</span><span class="sxs-lookup"><span data-stu-id="8f079-383">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p120">발신자가 수신한 오디오의 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-388">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="8f079-388">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="8f079-389">int</span><span class="sxs-lookup"><span data-stu-id="8f079-389">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p121">발신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-394">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="8f079-394">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="8f079-395">int</span><span class="sxs-lookup"><span data-stu-id="8f079-395">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p122">발신자가 수신한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-400">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="8f079-400">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="8f079-401">int</span><span class="sxs-lookup"><span data-stu-id="8f079-401">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p123">발신자의 에코 반환 손실 향상 메트릭입니다. 이 메트릭의 단위는 dB입니다. 값이 낮으면 에코가 적습니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-406">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="8f079-406">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="8f079-407">int</span><span class="sxs-lookup"><span data-stu-id="8f079-407">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p124">발신자의 스피커 렌더링에 대한 5분당 평균 결함 비율입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-411">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="8f079-411">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="8f079-412">int</span><span class="sxs-lookup"><span data-stu-id="8f079-412">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p125">발신자의 마이크 캡처에 대한 5분당 평균 결함 비율입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-416">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="8f079-416">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="8f079-417">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-417">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-418">CPU 클럭 대비 발신자 마이크 장치의 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-418">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-419">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="8f079-419">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="8f079-420">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-420">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-421">CPU 클럭 대비 발신자 스피커 장치의 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-421">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-422">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="8f079-422">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="8f079-423">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-423">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-424">통화의 최근 20초 동안 발생한 평균 마이크 캡처 스트림 타임스탬프 오류(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-424">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-425">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="8f079-425">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="8f079-426">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-426">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-427">통화의 최근 20초 동안 발생한 발신자의 평균 스피커 렌더링 스트림 타임스탬프 오류(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-427">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-428">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="8f079-428">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="8f079-429">smallint</span><span class="sxs-lookup"><span data-stu-id="8f079-429">smallint</span></span></p></td>
<td><p><span data-ttu-id="8f079-430">음성 스위치는 중단 기능이 감소된 반이중 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-430">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="8f079-431">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f079-431">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-432">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="8f079-432">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="8f079-433">tinyint</span><span class="sxs-lookup"><span data-stu-id="8f079-433">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8f079-434">발신자의 에코 이벤트의 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-434">Causes of an echo event for the caller.</span></span> <span data-ttu-id="8f079-435">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f079-435">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-436">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="8f079-436">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="8f079-437">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-437">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-p128">발신자의 마이크 캡처 스트림에서 에코가 감지되는 시간의 비율입니다. 헤드셋을 사용할 경우 값이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-440">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="8f079-440">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="8f079-441">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-441">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-p129">발신자의 전송된 스트림에서 에코가 감지되는 시간의 비율입니다. 전송 스트림에서 에코 비율이 높으면 에코 누출을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-444">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="8f079-444">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="8f079-445">int</span><span class="sxs-lookup"><span data-stu-id="8f079-445">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p130">중재 서버에서 발신자 오디오 게이트웨이로부터 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 [-30 ~ -18] dBoV입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-449">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="8f079-449">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="8f079-450">int</span><span class="sxs-lookup"><span data-stu-id="8f079-450">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p131">중재 서버에서 발신자 오디오 게이트웨이로부터 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 -50 dBoV 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-455">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="8f079-455">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="8f079-456">int</span><span class="sxs-lookup"><span data-stu-id="8f079-456">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-457">발신자 오디오에 적용되는 중재 서버 쪽의 AGC(자동 게인 컨트롤)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-457">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-458">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="8f079-458">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="8f079-459">식</span><span class="sxs-lookup"><span data-stu-id="8f079-459">float</span></span></p></td>
<td><p><span data-ttu-id="8f079-460">통화 초반의 최대 30초 동안 발신자에게 수신되는 신호의 RMS(제곱 평균 오차)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-460">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-461">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="8f079-461">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="8f079-462">int</span><span class="sxs-lookup"><span data-stu-id="8f079-462">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p132">수신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 신호 수준을 나타냅니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-467">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="8f079-467">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="8f079-468">int</span><span class="sxs-lookup"><span data-stu-id="8f079-468">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p133">수신자가 수신한 오디오의 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-473">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="8f079-473">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="8f079-474">int</span><span class="sxs-lookup"><span data-stu-id="8f079-474">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p134">수신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-479">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="8f079-479">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="8f079-480">int</span><span class="sxs-lookup"><span data-stu-id="8f079-480">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p135">수신자가 수신한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-485">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="8f079-485">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="8f079-486">int</span><span class="sxs-lookup"><span data-stu-id="8f079-486">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p136">수신자의 에코 반환 손실 향상 메트릭입니다. 이 메트릭의 단위는 dB입니다. 값이 낮으면 에코가 적습니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-491">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="8f079-491">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="8f079-492">int</span><span class="sxs-lookup"><span data-stu-id="8f079-492">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p137">수신자의 스피커 렌더링에 대한 5분당 평균 결함 비율입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-496">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="8f079-496">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="8f079-497">int</span><span class="sxs-lookup"><span data-stu-id="8f079-497">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p138">수신자의 마이크 캡처에 대한 5분당 평균 결함 비율입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-501">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="8f079-501">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="8f079-502">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-502">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-503">CPU 클럭 대비 수신자 마이크 장치의 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-503">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-504">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="8f079-504">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="8f079-505">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-505">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-506">CPU 클럭 대비 수신자 스피커 장치의 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-506">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-507">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="8f079-507">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="8f079-508">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-508">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-509">통화의 최근 20초 동안 발생한 평균 마이크 캡처 스트림 타임스탬프 오류(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-509">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-510">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="8f079-510">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="8f079-511">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-511">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-512">통화의 최근 20초 동안 발생한 수신자의 평균 스피커 렌더링 스트림 타임스탬프 오류(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-512">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-513">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="8f079-513">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="8f079-514">smallint</span><span class="sxs-lookup"><span data-stu-id="8f079-514">smallint</span></span></p></td>
<td><p><span data-ttu-id="8f079-515">음성 스위치는 중단 기능이 감소된 반이중 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-515">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="8f079-516">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f079-516">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-517">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="8f079-517">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="8f079-518">tinyint</span><span class="sxs-lookup"><span data-stu-id="8f079-518">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8f079-519">수신자의 에코 이벤트의 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-519">Causes of an echo event for the callee.</span></span> <span data-ttu-id="8f079-520">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8f079-520">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-521">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="8f079-521">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="8f079-522">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-522">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-p141">수신자의 마이크 캡처 스트림에서 에코가 감지되는 시간의 비율입니다. 헤드셋을 사용할 경우 값이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-525">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="8f079-525">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="8f079-526">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-526">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-p142">수신자의 전송된 스트림에서 에코가 감지되는 시간의 비율입니다. 전송 스트림에서 에코 비율이 높으면 에코 누출을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-529">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="8f079-529">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="8f079-530">int</span><span class="sxs-lookup"><span data-stu-id="8f079-530">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p143">중재 서버에서 수신자 오디오 게이트웨이로부터 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 [-30 ~ -18] dBoV입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-534">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="8f079-534">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="8f079-535">int</span><span class="sxs-lookup"><span data-stu-id="8f079-535">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-p144">중재 서버에서 수신자 오디오 게이트웨이로부터 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 -50 dBoV 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-540">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="8f079-540">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="8f079-541">int</span><span class="sxs-lookup"><span data-stu-id="8f079-541">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-542">수신자 오디오에 적용되는 중재 서버 쪽의 AGC(자동 게인 컨트롤)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-542">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-543">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="8f079-543">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="8f079-544">식</span><span class="sxs-lookup"><span data-stu-id="8f079-544">float</span></span></p></td>
<td><p><span data-ttu-id="8f079-545">통화 초반의 최대 30초 동안 수신자에게 수신되는 신호의 RMS(제곱 평균 오차)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-545">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-546">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="8f079-546">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="8f079-547">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-547">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-548">일반 샘플에 대한 오디오 힐링으로 생성된 숨겨진 평균 샘플 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-548">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-549">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="8f079-549">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="8f079-550">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-550">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-551">일반 샘플에 대한 오디오 힐링으로 생성된 평균 늘임 샘플 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-551">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-552">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="8f079-552">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="8f079-553">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-553">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-554">일반 샘플에 대한 오디오 힐링으로 생성된 숨겨진 압축 샘플 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-554">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-555">왕복</span><span class="sxs-lookup"><span data-stu-id="8f079-555">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="8f079-556">int</span><span class="sxs-lookup"><span data-stu-id="8f079-556">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-557">RTCP 통계로부터의 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-557">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-558">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="8f079-558">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="8f079-559">int</span><span class="sxs-lookup"><span data-stu-id="8f079-559">int</span></span></p></td>
<td><p><span data-ttu-id="8f079-560">오디오 스트림에 대한 최대 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-560">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-561">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="8f079-561">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="8f079-562">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-562">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-p145">통화에 대한 평균 광대역 네트워크 MOS입니다. 이 메트릭은 패킷 손실, 지터 및 사용된 코덱에 따라 달라집니다. 범위는 1.0 ~ 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-566">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="8f079-566">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="8f079-567">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-567">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-568">통화에 대한 최소 광대역 네트워크 MOS입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-568">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-569">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="8f079-569">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="8f079-570">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-570">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-571">음성 수준, 잡음 수준 및 캡처 장치 특성을 포함하여 전송된 오디오에 대한 평균 예측 광대역 청취 MOS 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-571">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-572">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="8f079-572">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="8f079-573">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-573">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-574">통화에 대한 최소 SendListenMOS입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-574">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-575">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="8f079-575">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="8f079-576">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-576">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-577">음성 수준, 잡음 수준, 코덱, 네트워크 조건 및 캡처 장치 특성을 포함하여 수신된 오디오에 대한 평균 예측 광대역 청취 MOS 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-577">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-578">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="8f079-578">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="8f079-579">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="8f079-579">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="8f079-580">통화에 대한 최소 RecvListenMOS입니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-580">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f079-581">오디오 \ Ecused</span><span class="sxs-lookup"><span data-stu-id="8f079-581">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="8f079-582">비트만</span><span class="sxs-lookup"><span data-stu-id="8f079-582">bit</span></span></p></td>
<td><p><span data-ttu-id="8f079-583">통화에 오디오 FEC가 사용되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-583">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f079-584">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="8f079-584">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="8f079-585">비트만</span><span class="sxs-lookup"><span data-stu-id="8f079-585">bit</span></span></p></td>
<td><p><span data-ttu-id="8f079-586">P-Asserted-Identity 정보의 방향을 나타냅니다. 1은 스트림 방향이 발신자에서 수신자의 방향임을 의미하고, 0은 스트림 방향이 수신자에서 발신자의 방향임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8f079-586">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

