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
ms.openlocfilehash: 11279857e7bf217d311f4f2eb0a54a5d5f628084
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="d8be5-102">Lync Server 2013의 오디오 Streamdetail 보기</span><span class="sxs-lookup"><span data-stu-id="d8be5-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8be5-103">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d8be5-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d8be5-104">AudioStreamDetail 보기에는 데이터베이스의 각 오디오 스트림에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="d8be5-105">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8be5-106">열</span><span class="sxs-lookup"><span data-stu-id="d8be5-106">Column</span></span></th>
<th><span data-ttu-id="d8be5-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d8be5-107">Data Type</span></span></th>
<th><span data-ttu-id="d8be5-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d8be5-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="d8be5-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="d8be5-110">datetime</span><span class="sxs-lookup"><span data-stu-id="d8be5-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="d8be5-111"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="d8be5-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="d8be5-113">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-113">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="d8be5-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="d8be5-116">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-116">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-117">미디어 회선 내의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="d8be5-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="d8be5-119">datetime</span><span class="sxs-lookup"><span data-stu-id="d8be5-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="d8be5-120">세션 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="d8be5-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="d8be5-122">datetime</span><span class="sxs-lookup"><span data-stu-id="d8be5-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="d8be5-123">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="d8be5-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="d8be5-125">비트만</span><span class="sxs-lookup"><span data-stu-id="d8be5-125">bit</span></span></p></td>
<td><p><span data-ttu-id="d8be5-126">대화 상자 범주: 0은 Lync server를 중재 서버 다리에 대 한 것입니다. 1은 PSTN 게이트웨이 레그에 대 한 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="d8be5-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="d8be5-128">비트만</span><span class="sxs-lookup"><span data-stu-id="d8be5-128">bit</span></span></p></td>
<td><p><span data-ttu-id="d8be5-129">통화가 바이패스되었는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="d8be5-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="d8be5-131">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-131">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p102">이 필드는(제공된 경우) 바이패스 ID가 일치한 경우에도 통화가 바이패스되지 않은 이유를 나타냅니다. 하나의 값만 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="d8be5-134">0x0001 -  기본 네트워크 어댑터에 대한 알 수 없는 바이패스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="d8be5-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="d8be5-136">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-136">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-137">통화 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="d8be5-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="d8be5-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d8be5-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-140">발신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="d8be5-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="d8be5-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d8be5-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-143">수신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-144">최초</span><span class="sxs-lookup"><span data-stu-id="d8be5-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="d8be5-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d8be5-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-146">발신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-147">피호출자</span><span class="sxs-lookup"><span data-stu-id="d8be5-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="d8be5-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d8be5-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-149">수신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="d8be5-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="d8be5-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d8be5-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-152">발신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="d8be5-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="d8be5-154">smallint</span><span class="sxs-lookup"><span data-stu-id="d8be5-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="d8be5-155">발신자의 사용자 에이전트 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="d8be5-156">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8be5-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="d8be5-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="d8be5-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d8be5-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-159">발신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="d8be5-160">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8be5-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="d8be5-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="d8be5-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d8be5-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-163">수신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="d8be5-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="d8be5-165">smallint</span><span class="sxs-lookup"><span data-stu-id="d8be5-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="d8be5-166">수신자의 사용자 에이전트 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-166">Type of callee’s user agent.</span></span> <span data-ttu-id="d8be5-167">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8be5-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="d8be5-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="d8be5-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d8be5-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-170">수신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-170">Category of callee’s user agent.</span></span> <span data-ttu-id="d8be5-171">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8be5-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="d8be5-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="d8be5-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d8be5-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-174">발신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="d8be5-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="d8be5-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d8be5-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-177">수신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="d8be5-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="d8be5-179">name</span><span class="sxs-lookup"><span data-stu-id="d8be5-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-180">발신자의 끝점 OS(운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="d8be5-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="d8be5-182">name</span><span class="sxs-lookup"><span data-stu-id="d8be5-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-183">수신자의 끝점 OS(운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="d8be5-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="d8be5-185">name</span><span class="sxs-lookup"><span data-stu-id="d8be5-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-186">발신자의 끝점 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="d8be5-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="d8be5-188">name</span><span class="sxs-lookup"><span data-stu-id="d8be5-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-189">수신자의 끝점 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="d8be5-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="d8be5-191">smallint</span><span class="sxs-lookup"><span data-stu-id="d8be5-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="d8be5-192">발신자 끝점의 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="d8be5-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="d8be5-194">smallint</span><span class="sxs-lookup"><span data-stu-id="d8be5-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="d8be5-195">수신자 끝점의 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="d8be5-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="d8be5-197">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-197">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-198">발신자의 끝점 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="d8be5-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="d8be5-200">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-200">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-201">수신자의 끝점 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="d8be5-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="d8be5-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="d8be5-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d8be5-204">발신자의 시스템이 가상화된 환경에서 실행 중인 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="d8be5-205">자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 Endpoint table</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8be5-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="d8be5-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="d8be5-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="d8be5-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d8be5-208">수신자의 시스템이 가상화된 환경에서 실행 중인 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="d8be5-209">자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 Endpoint table</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8be5-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="d8be5-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d8be5-211">상관 관계 키입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-211">Correlation key.</span></span> <span data-ttu-id="d8be5-212"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013의 Sessioncorrelation 관계 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="d8be5-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="d8be5-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="d8be5-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d8be5-215">직접 또는 중계와 같은 미디어 경로에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="d8be5-216">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8be5-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="d8be5-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="d8be5-218">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-218">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p111">비트 플래그로 설명된 발신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="d8be5-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="d8be5-222">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-222">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p112">비트 플래그로 설명된 수신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-225">전송</span><span class="sxs-lookup"><span data-stu-id="d8be5-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="d8be5-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="d8be5-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d8be5-227">전송 종류: 0은 UDP, 1은 TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="d8be5-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d8be5-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="d8be5-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-230">발신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-230">IP address of the caller.</span></span> <span data-ttu-id="d8be5-231">이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="d8be5-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="d8be5-233">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-233">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-234">발신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="d8be5-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="d8be5-236">비트만</span><span class="sxs-lookup"><span data-stu-id="d8be5-236">bit</span></span></p></td>
<td><p><span data-ttu-id="d8be5-237">발신자가 내부 네트워크에 있는지 여부를 나타냅니다. 1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="d8be5-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d8be5-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="d8be5-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-240">수신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-240">IP address of the callee.</span></span> <span data-ttu-id="d8be5-241">이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="d8be5-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="d8be5-243">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-243">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-244">수신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="d8be5-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="d8be5-246">비트만</span><span class="sxs-lookup"><span data-stu-id="d8be5-246">bit</span></span></p></td>
<td><p><span data-ttu-id="d8be5-247">수신자가 내부 네트워크에 있는지 여부를 나타냅니다. 1은 수신자가 회사 네트워크 내에 있음을 의미하고 0은 수신자가 네트워크 외부에 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="d8be5-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="d8be5-249">name</span><span class="sxs-lookup"><span data-stu-id="d8be5-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-250">발신자 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="d8be5-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="d8be5-252">name</span><span class="sxs-lookup"><span data-stu-id="d8be5-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-253">발신자 사이트의 국가/지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="d8be5-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="d8be5-255">name</span><span class="sxs-lookup"><span data-stu-id="d8be5-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-256">수신자 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="d8be5-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="d8be5-258">name</span><span class="sxs-lookup"><span data-stu-id="d8be5-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-259">수신자 사이트의 국가/지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="d8be5-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d8be5-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="d8be5-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-262">A/V 에지 서비스에서 발신자가 사용하는 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="d8be5-263">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8be5-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="d8be5-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="d8be5-265">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-265">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-266">발신자가 사용하는 A/V 에지 서비스에서 사용되는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="d8be5-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="d8be5-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="d8be5-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-269">A/V 에지 서비스에서 수신자가 사용하는 IP 주소 키입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="d8be5-270">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8be5-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="d8be5-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="d8be5-272">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-272">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-273">수신자가 사용하는 A/V 에지 서비스에서 사용되는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="d8be5-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="d8be5-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d8be5-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-276">발신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="d8be5-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="d8be5-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d8be5-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-279">발신자의 렌더링 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="d8be5-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d8be5-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d8be5-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-282">발신자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="d8be5-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="d8be5-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d8be5-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-285">발신자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="d8be5-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="d8be5-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d8be5-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-288">수신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="d8be5-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="d8be5-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d8be5-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-291">수신자의 렌더링 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="d8be5-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d8be5-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d8be5-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-294">수신자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="d8be5-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="d8be5-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="d8be5-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-297">수신자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="d8be5-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="d8be5-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="d8be5-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d8be5-300">발신자의 네트워크 연결 형식입니다. 0은 유선, 1은 무선입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="d8be5-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="d8be5-302">비트만</span><span class="sxs-lookup"><span data-stu-id="d8be5-302">bit</span></span></p></td>
<td><p><span data-ttu-id="d8be5-303">발신자가 가상 사설망을 통해 연결되어 있는지 여부를 나타냅니다.1은 VPN(가상 사설망), 0은 VPN 외입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="d8be5-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="d8be5-305">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="d8be5-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-306">발신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="d8be5-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="d8be5-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="d8be5-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d8be5-309">수신자의 네트워크 연결 형식입니다. 0은 유선, 1은 무선입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="d8be5-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="d8be5-311">비트만</span><span class="sxs-lookup"><span data-stu-id="d8be5-311">bit</span></span></p></td>
<td><p><span data-ttu-id="d8be5-312">수신자가 가상 사설망을 통해 연결되어 있는지 여부를 나타냅니다.1은 VPN(가상 사설망), 0은 VPN 외입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="d8be5-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="d8be5-314">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="d8be5-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-315">수신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="d8be5-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="d8be5-317">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-318">오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).</span><span class="sxs-lookup"><span data-stu-id="d8be5-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="d8be5-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="d8be5-320">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-320">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p117">다양한 정책 설정(TURN, API, SDP, 정책 서버 등)이 제공된 지정된 송신측 스트림에 적용되는 실제 대역폭입니다. 이 대역폭은 대역폭 예상에 따라 유효 대역폭이 더 낮을 수 있으므로 유효 대역폭과 혼동해서는 안됩니다. 이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="d8be5-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="d8be5-325">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-325">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-326">RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="d8be5-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="d8be5-328">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-328">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-329">통화 중 최대 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="d8be5-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="d8be5-331">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="d8be5-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-332">통화 중 평균 패킷 손실 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="d8be5-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="d8be5-334">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="d8be5-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-335">통화 중 관측된 최대 패킷 손실량입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-336">버스트 밀도</span><span class="sxs-lookup"><span data-stu-id="d8be5-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="d8be5-337">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="d8be5-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-338">통화 중 손실량이 많아지는 기간 동안의 평균 패킷 손실 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="d8be5-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="d8be5-340">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-340">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-341">통화 중 손실량이 많아지는 기간 동안의 평균 패킷 손실 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="d8be5-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="d8be5-343">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="d8be5-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-344">패킷 손실이 최고치인 기간 사이의 간격 중에 발생하는 평균 패킷 손실 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="d8be5-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="d8be5-346">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-346">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-347">패킷 손실이 최고치인 기간 사이의 간격에 대한 평균 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="d8be5-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="d8be5-349">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-349">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-350">오디오 스트림에 대한 패킷 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-351">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="d8be5-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="d8be5-352">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-352">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-353">오디오 스트림에 대한 대역폭 예상치입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="d8be5-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="d8be5-355">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p118">전체 통화에 대한 네트워크 MOS 저하입니다. 범위는 0.0에서 5.0까지입니다. 이 메트릭은 지터 및 패킷 손실로 인해 감소된 네트워크 MOS의 양을 보여 줍니다. 적정 품질을 위해서는 0.5 미만이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="d8be5-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="d8be5-361">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-362">통화 중 최대 네트워크 MOS 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="d8be5-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="d8be5-364">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-365">지터로 인해 발생한 네트워크 MOS 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="d8be5-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="d8be5-367">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-368">패킷 손실로 인해 발생한 네트워크 MOS 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="d8be5-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="d8be5-370">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-370">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-371"><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a>에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="d8be5-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="d8be5-373">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-373">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-374">오디오 스트림에 대한 샘플링 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="d8be5-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="d8be5-376">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-376">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p119">발신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="d8be5-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="d8be5-382">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-382">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p120">발신자가 수신한 오디오의 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="d8be5-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="d8be5-388">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-388">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p121">발신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="d8be5-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="d8be5-394">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-394">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p122">발신자가 수신한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="d8be5-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="d8be5-400">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-400">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p123">발신자의 에코 반환 손실 향상 메트릭입니다. 이 메트릭의 단위는 dB입니다. 값이 낮으면 에코가 적습니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="d8be5-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="d8be5-406">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-406">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p124">발신자의 스피커 렌더링에 대한 5분당 평균 결함 비율입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="d8be5-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="d8be5-411">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-411">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p125">발신자의 마이크 캡처에 대한 5분당 평균 결함 비율입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="d8be5-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="d8be5-416">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-417">CPU 클럭 대비 발신자 마이크 장치의 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="d8be5-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="d8be5-419">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-420">CPU 클럭 대비 발신자 스피커 장치의 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="d8be5-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="d8be5-422">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-423">통화의 최근 20초 동안 발생한 평균 마이크 캡처 스트림 타임스탬프 오류(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="d8be5-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="d8be5-425">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-426">통화의 최근 20초 동안 발생한 발신자의 평균 스피커 렌더링 스트림 타임스탬프 오류(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="d8be5-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="d8be5-428">smallint</span><span class="sxs-lookup"><span data-stu-id="d8be5-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="d8be5-429">음성 스위치는 중단 기능이 감소된 반이중 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="d8be5-430">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8be5-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="d8be5-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="d8be5-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="d8be5-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d8be5-433">발신자의 에코 이벤트의 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="d8be5-434">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8be5-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="d8be5-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="d8be5-436">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p128">발신자의 마이크 캡처 스트림에서 에코가 감지되는 시간의 비율입니다. 헤드셋을 사용할 경우 값이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="d8be5-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="d8be5-440">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p129">발신자의 전송된 스트림에서 에코가 감지되는 시간의 비율입니다. 전송 스트림에서 에코 비율이 높으면 에코 누출을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="d8be5-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="d8be5-444">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-444">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p130">중재 서버에서 발신자 오디오 게이트웨이로부터 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 [-30 ~ -18] dBoV입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="d8be5-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="d8be5-449">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-449">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p131">중재 서버에서 발신자 오디오 게이트웨이로부터 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 -50 dBoV 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="d8be5-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="d8be5-455">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-455">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-456">발신자 오디오에 적용되는 중재 서버 쪽의 AGC(자동 게인 컨트롤)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="d8be5-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="d8be5-458">식</span><span class="sxs-lookup"><span data-stu-id="d8be5-458">float</span></span></p></td>
<td><p><span data-ttu-id="d8be5-459">통화 초반의 최대 30초 동안 발신자에게 수신되는 신호의 RMS(제곱 평균 오차)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="d8be5-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="d8be5-461">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-461">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p132">수신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 신호 수준을 나타냅니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="d8be5-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="d8be5-467">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-467">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p133">수신자가 수신한 오디오의 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="d8be5-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="d8be5-473">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-473">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p134">수신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="d8be5-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="d8be5-479">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-479">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p135">수신자가 수신한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="d8be5-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="d8be5-485">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-485">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p136">수신자의 에코 반환 손실 향상 메트릭입니다. 이 메트릭의 단위는 dB입니다. 값이 낮으면 에코가 적습니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="d8be5-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="d8be5-491">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-491">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p137">수신자의 스피커 렌더링에 대한 5분당 평균 결함 비율입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="d8be5-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="d8be5-496">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-496">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p138">수신자의 마이크 캡처에 대한 5분당 평균 결함 비율입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="d8be5-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="d8be5-501">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-502">CPU 클럭 대비 수신자 마이크 장치의 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="d8be5-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="d8be5-504">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-505">CPU 클럭 대비 수신자 스피커 장치의 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="d8be5-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="d8be5-507">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-508">통화의 최근 20초 동안 발생한 평균 마이크 캡처 스트림 타임스탬프 오류(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="d8be5-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="d8be5-510">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-511">통화의 최근 20초 동안 발생한 수신자의 평균 스피커 렌더링 스트림 타임스탬프 오류(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="d8be5-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="d8be5-513">smallint</span><span class="sxs-lookup"><span data-stu-id="d8be5-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="d8be5-514">음성 스위치는 중단 기능이 감소된 반이중 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="d8be5-515">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8be5-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="d8be5-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="d8be5-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="d8be5-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d8be5-518">수신자의 에코 이벤트의 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="d8be5-519">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8be5-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="d8be5-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="d8be5-521">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p141">수신자의 마이크 캡처 스트림에서 에코가 감지되는 시간의 비율입니다. 헤드셋을 사용할 경우 값이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="d8be5-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="d8be5-525">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p142">수신자의 전송된 스트림에서 에코가 감지되는 시간의 비율입니다. 전송 스트림에서 에코 비율이 높으면 에코 누출을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="d8be5-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="d8be5-529">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-529">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p143">중재 서버에서 수신자 오디오 게이트웨이로부터 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 [-30 ~ -18] dBoV입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="d8be5-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="d8be5-534">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-534">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p144">중재 서버에서 수신자 오디오 게이트웨이로부터 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 -50 dBoV 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="d8be5-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="d8be5-540">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-540">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-541">수신자 오디오에 적용되는 중재 서버 쪽의 AGC(자동 게인 컨트롤)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="d8be5-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="d8be5-543">식</span><span class="sxs-lookup"><span data-stu-id="d8be5-543">float</span></span></p></td>
<td><p><span data-ttu-id="d8be5-544">통화 초반의 최대 30초 동안 수신자에게 수신되는 신호의 RMS(제곱 평균 오차)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="d8be5-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="d8be5-546">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-547">일반 샘플에 대한 오디오 힐링으로 생성된 숨겨진 평균 샘플 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="d8be5-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="d8be5-549">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-550">일반 샘플에 대한 오디오 힐링으로 생성된 평균 늘임 샘플 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="d8be5-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="d8be5-552">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-553">일반 샘플에 대한 오디오 힐링으로 생성된 숨겨진 압축 샘플 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-554">왕복</span><span class="sxs-lookup"><span data-stu-id="d8be5-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="d8be5-555">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-555">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-556">RTCP 통계로부터의 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="d8be5-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="d8be5-558">int</span><span class="sxs-lookup"><span data-stu-id="d8be5-558">int</span></span></p></td>
<td><p><span data-ttu-id="d8be5-559">오디오 스트림에 대한 최대 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="d8be5-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="d8be5-561">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-p145">통화에 대한 평균 광대역 네트워크 MOS입니다. 이 메트릭은 패킷 손실, 지터 및 사용된 코덱에 따라 달라집니다. 범위는 1.0 ~ 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="d8be5-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="d8be5-566">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-567">통화에 대한 최소 광대역 네트워크 MOS입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="d8be5-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="d8be5-569">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-570">음성 수준, 잡음 수준 및 캡처 장치 특성을 포함하여 전송된 오디오에 대한 평균 예측 광대역 청취 MOS 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="d8be5-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="d8be5-572">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-573">통화에 대한 최소 SendListenMOS입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="d8be5-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="d8be5-575">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-576">음성 수준, 잡음 수준, 코덱, 네트워크 조건 및 캡처 장치 특성을 포함하여 수신된 오디오에 대한 평균 예측 광대역 청취 MOS 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="d8be5-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="d8be5-578">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="d8be5-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="d8be5-579">통화에 대한 최소 RecvListenMOS입니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8be5-580">오디오 \ Ecused</span><span class="sxs-lookup"><span data-stu-id="d8be5-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="d8be5-581">비트만</span><span class="sxs-lookup"><span data-stu-id="d8be5-581">bit</span></span></p></td>
<td><p><span data-ttu-id="d8be5-582">통화에 오디오 FEC가 사용되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8be5-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="d8be5-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="d8be5-584">비트만</span><span class="sxs-lookup"><span data-stu-id="d8be5-584">bit</span></span></p></td>
<td><p><span data-ttu-id="d8be5-585">P-Asserted-Identity 정보의 방향을 나타냅니다. 1은 스트림 방향이 발신자에서 수신자의 방향임을 의미하고, 0은 스트림 방향이 수신자에서 발신자의 방향임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d8be5-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

