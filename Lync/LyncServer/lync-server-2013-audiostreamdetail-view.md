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
ms.openlocfilehash: b69cdbbe7a4635e60e5912e6f41d2f089612b30a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="c45fc-102">Lync Server 2013의 오디오 Streamdetail 보기</span><span class="sxs-lookup"><span data-stu-id="c45fc-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c45fc-103">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="c45fc-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="c45fc-104">AudioStreamDetail 보기에는 데이터베이스의 각 오디오 스트림에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="c45fc-105">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c45fc-106">열</span><span class="sxs-lookup"><span data-stu-id="c45fc-106">Column</span></span></th>
<th><span data-ttu-id="c45fc-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c45fc-107">Data Type</span></span></th>
<th><span data-ttu-id="c45fc-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="c45fc-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="c45fc-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="c45fc-110">datetime</span><span class="sxs-lookup"><span data-stu-id="c45fc-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="c45fc-111"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="c45fc-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="c45fc-113">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-113">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="c45fc-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="c45fc-116">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-116">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-117">미디어 회선 내의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="c45fc-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="c45fc-119">datetime</span><span class="sxs-lookup"><span data-stu-id="c45fc-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="c45fc-120">세션 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="c45fc-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="c45fc-122">datetime</span><span class="sxs-lookup"><span data-stu-id="c45fc-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="c45fc-123">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="c45fc-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="c45fc-125">비트만</span><span class="sxs-lookup"><span data-stu-id="c45fc-125">bit</span></span></p></td>
<td><p><span data-ttu-id="c45fc-126">대화 상자 범주: 0은 Lync server를 중재 서버 다리에 대 한 것입니다. 1은 PSTN 게이트웨이 레그에 대 한 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="c45fc-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="c45fc-128">비트만</span><span class="sxs-lookup"><span data-stu-id="c45fc-128">bit</span></span></p></td>
<td><p><span data-ttu-id="c45fc-129">통화가 바이패스되었는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="c45fc-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="c45fc-131">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-131">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p102">이 필드는(제공된 경우) 바이패스 ID가 일치한 경우에도 통화가 바이패스되지 않은 이유를 나타냅니다. 하나의 값만 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p102">If present, indicates why a call was not bypassed even if the bypass IDs matched. Only one value is defined:</span></span></p>
<p><span data-ttu-id="c45fc-134">0x0001 -  기본 네트워크 어댑터에 대한 알 수 없는 바이패스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="c45fc-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="c45fc-136">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-136">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-137">통화 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="c45fc-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="c45fc-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c45fc-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-140">발신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="c45fc-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="c45fc-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c45fc-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-143">수신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-144">최초</span><span class="sxs-lookup"><span data-stu-id="c45fc-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="c45fc-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c45fc-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-146">발신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-147">피호출자</span><span class="sxs-lookup"><span data-stu-id="c45fc-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="c45fc-148">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c45fc-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-149">수신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="c45fc-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="c45fc-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c45fc-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-152">발신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="c45fc-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="c45fc-154">smallint</span><span class="sxs-lookup"><span data-stu-id="c45fc-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="c45fc-155">발신자의 사용자 에이전트 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="c45fc-156">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c45fc-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="c45fc-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="c45fc-158">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c45fc-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-159">발신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="c45fc-160">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c45fc-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="c45fc-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="c45fc-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c45fc-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-163">수신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="c45fc-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="c45fc-165">smallint</span><span class="sxs-lookup"><span data-stu-id="c45fc-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="c45fc-166">수신자의 사용자 에이전트 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-166">Type of callee’s user agent.</span></span> <span data-ttu-id="c45fc-167">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c45fc-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="c45fc-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="c45fc-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="c45fc-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-170">수신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-170">Category of callee’s user agent.</span></span> <span data-ttu-id="c45fc-171">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c45fc-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="c45fc-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="c45fc-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c45fc-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-174">발신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="c45fc-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="c45fc-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="c45fc-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-177">수신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="c45fc-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="c45fc-179">name</span><span class="sxs-lookup"><span data-stu-id="c45fc-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-180">발신자의 끝점 OS(운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="c45fc-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="c45fc-182">name</span><span class="sxs-lookup"><span data-stu-id="c45fc-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-183">수신자의 끝점 OS(운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="c45fc-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="c45fc-185">name</span><span class="sxs-lookup"><span data-stu-id="c45fc-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-186">발신자의 끝점 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="c45fc-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="c45fc-188">name</span><span class="sxs-lookup"><span data-stu-id="c45fc-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-189">수신자의 끝점 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="c45fc-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="c45fc-191">smallint</span><span class="sxs-lookup"><span data-stu-id="c45fc-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="c45fc-192">발신자 끝점의 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="c45fc-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="c45fc-194">smallint</span><span class="sxs-lookup"><span data-stu-id="c45fc-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="c45fc-195">수신자 끝점의 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="c45fc-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="c45fc-197">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-197">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-198">발신자의 끝점 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="c45fc-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="c45fc-200">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-200">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-201">수신자의 끝점 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="c45fc-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="c45fc-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="c45fc-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c45fc-204">발신자의 시스템이 가상화된 환경에서 실행 중인 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="c45fc-205">자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 Endpoint table</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c45fc-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="c45fc-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="c45fc-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="c45fc-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c45fc-208">수신자의 시스템이 가상화된 환경에서 실행 중인 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="c45fc-209">자세한 내용은 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 Endpoint table</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c45fc-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="c45fc-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c45fc-211">상관 관계 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-211">Correlation key.</span></span> <span data-ttu-id="c45fc-212"><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013의 Sessioncorrelation 관계 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="c45fc-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="c45fc-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="c45fc-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c45fc-215">직접 또는 중계와 같은 미디어 경로에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="c45fc-216">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c45fc-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="c45fc-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="c45fc-218">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-218">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p111">비트 플래그로 설명된 발신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="c45fc-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="c45fc-222">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-222">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p112">비트 플래그로 설명된 수신자 측 ICE(Interactive Connectivity Establishment) 프로세스에 대한 대한 정보입니다. 자세한 내용은 체감 품질 모니터링 서버 프로토콜 사양을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-225">전송</span><span class="sxs-lookup"><span data-stu-id="c45fc-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="c45fc-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="c45fc-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c45fc-227">전송 종류: 0은 UDP, 1은 TCP입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="c45fc-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c45fc-229">var (50)</span><span class="sxs-lookup"><span data-stu-id="c45fc-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-230">발신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-230">IP address of the caller.</span></span> <span data-ttu-id="c45fc-231">이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="c45fc-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="c45fc-233">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-233">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-234">발신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="c45fc-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="c45fc-236">비트만</span><span class="sxs-lookup"><span data-stu-id="c45fc-236">bit</span></span></p></td>
<td><p><span data-ttu-id="c45fc-237">발신자가 내부 네트워크에 있는지 여부를 나타냅니다. 1은 발신자가 회사 네트워크 내에 있음을 의미하고 0은 발신자가 네트워크 외부에 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="c45fc-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c45fc-239">var (50)</span><span class="sxs-lookup"><span data-stu-id="c45fc-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-240">수신자의 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-240">IP address of the callee.</span></span> <span data-ttu-id="c45fc-241">이 주소는 IPv4 또는 IPv6 주소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="c45fc-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="c45fc-243">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-243">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-244">수신자가 사용하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="c45fc-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="c45fc-246">비트만</span><span class="sxs-lookup"><span data-stu-id="c45fc-246">bit</span></span></p></td>
<td><p><span data-ttu-id="c45fc-247">수신자가 내부 네트워크에 있는지 여부를 나타냅니다. 1은 수신자가 회사 네트워크 내에 있음을 의미하고 0은 수신자가 네트워크 외부에 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="c45fc-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="c45fc-249">name</span><span class="sxs-lookup"><span data-stu-id="c45fc-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-250">발신자 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="c45fc-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="c45fc-252">name</span><span class="sxs-lookup"><span data-stu-id="c45fc-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-253">발신자 사이트의 국가/지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="c45fc-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="c45fc-255">name</span><span class="sxs-lookup"><span data-stu-id="c45fc-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-256">수신자 사이트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="c45fc-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="c45fc-258">name</span><span class="sxs-lookup"><span data-stu-id="c45fc-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-259">수신자 사이트의 국가/지역 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="c45fc-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c45fc-261">var (50)</span><span class="sxs-lookup"><span data-stu-id="c45fc-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-262">A/V 에지 서비스에서 발신자가 사용하는 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="c45fc-263">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c45fc-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="c45fc-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="c45fc-265">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-265">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-266">발신자가 사용하는 A/V 에지 서비스에서 사용되는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="c45fc-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c45fc-268">var (50)</span><span class="sxs-lookup"><span data-stu-id="c45fc-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-269">A/V 에지 서비스에서 수신자가 사용하는 IP 주소 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="c45fc-270">자세한 내용은 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c45fc-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="c45fc-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="c45fc-272">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-272">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-273">수신자가 사용하는 A/V 에지 서비스에서 사용되는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="c45fc-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="c45fc-275">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c45fc-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-276">발신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="c45fc-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="c45fc-278">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c45fc-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-279">발신자의 렌더링 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="c45fc-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c45fc-281">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c45fc-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-282">발신자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="c45fc-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="c45fc-284">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c45fc-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-285">발신자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="c45fc-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="c45fc-287">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c45fc-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-288">수신자의 캡처 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="c45fc-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="c45fc-290">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c45fc-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-291">수신자의 렌더링 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="c45fc-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c45fc-293">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c45fc-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-294">수신자의 캡처 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="c45fc-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c45fc-296">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c45fc-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-297">수신자의 렌더링 장치 드라이버 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="c45fc-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="c45fc-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="c45fc-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c45fc-300">발신자의 네트워크 연결 형식입니다. 0은 유선, 1은 무선입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="c45fc-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="c45fc-302">비트만</span><span class="sxs-lookup"><span data-stu-id="c45fc-302">bit</span></span></p></td>
<td><p><span data-ttu-id="c45fc-303">발신자가 가상 사설망을 통해 연결되어 있는지 여부를 나타냅니다.1은 VPN(가상 사설망), 0은 VPN 외입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="c45fc-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="c45fc-305">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="c45fc-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-306">발신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="c45fc-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="c45fc-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="c45fc-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c45fc-309">수신자의 네트워크 연결 형식입니다. 0은 유선, 1은 무선입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="c45fc-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="c45fc-311">비트만</span><span class="sxs-lookup"><span data-stu-id="c45fc-311">bit</span></span></p></td>
<td><p><span data-ttu-id="c45fc-312">수신자가 가상 사설망을 통해 연결되어 있는지 여부를 나타냅니다.1은 VPN(가상 사설망), 0은 VPN 외입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="c45fc-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="c45fc-314">10 진수 (18, 0)</span><span class="sxs-lookup"><span data-stu-id="c45fc-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-315">수신자의 끝점에 대한 네트워크 연결 속도(bps)입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="c45fc-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="c45fc-317">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-318">오디오 세션의 협대역 대화 MOS입니다(두 오디오 스트림을 모두 기반으로 함).</span><span class="sxs-lookup"><span data-stu-id="c45fc-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="c45fc-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="c45fc-320">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-320">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p117">다양한 정책 설정(TURN, API, SDP, 정책 서버 등)이 제공된 지정된 송신측 스트림에 적용되는 실제 대역폭입니다. 이 대역폭은 대역폭 예상에 따라 유효 대역폭이 더 낮을 수 있으므로 유효 대역폭과 혼동해서는 안됩니다. 이 대역폭은 기본적으로 대역폭 예상치로 지정된 한도를 제외하고 송신 스트림이 사용할 수 있는 최대 대역폭입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p117">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="c45fc-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="c45fc-325">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-325">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-326">RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="c45fc-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="c45fc-328">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-328">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-329">통화 중 최대 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="c45fc-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="c45fc-331">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="c45fc-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-332">통화 중 평균 패킷 손실 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="c45fc-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="c45fc-334">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="c45fc-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-335">통화 중 관측된 최대 패킷 손실량입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-336">버스트 밀도</span><span class="sxs-lookup"><span data-stu-id="c45fc-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="c45fc-337">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="c45fc-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-338">통화 중 손실량이 많아지는 기간 동안의 평균 패킷 손실 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="c45fc-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="c45fc-340">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-340">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-341">통화 중 손실량이 많아지는 기간 동안의 평균 패킷 손실 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="c45fc-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="c45fc-343">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="c45fc-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-344">패킷 손실이 최고치인 기간 사이의 간격 중에 발생하는 평균 패킷 손실 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="c45fc-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="c45fc-346">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-346">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-347">패킷 손실이 최고치인 기간 사이의 간격에 대한 평균 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="c45fc-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="c45fc-349">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-349">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-350">오디오 스트림에 대한 패킷 수입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-351">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="c45fc-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="c45fc-352">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-352">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-353">오디오 스트림에 대한 대역폭 예상치입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="c45fc-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="c45fc-355">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p118">전체 통화에 대한 네트워크 MOS 저하입니다. 범위는 0.0에서 5.0까지입니다. 이 메트릭은 지터 및 패킷 손실로 인해 감소된 네트워크 MOS의 양을 보여 줍니다. 적정 품질을 위해서는 0.5 미만이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p118">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="c45fc-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="c45fc-361">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-362">통화 중 최대 네트워크 MOS 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="c45fc-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="c45fc-364">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-365">지터로 인해 발생한 네트워크 MOS 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="c45fc-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="c45fc-367">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-368">패킷 손실로 인해 발생한 네트워크 MOS 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="c45fc-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="c45fc-370">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-370">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-371"><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a>에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="c45fc-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="c45fc-373">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-373">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-374">오디오 스트림에 대한 샘플링 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="c45fc-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="c45fc-376">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-376">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p119">발신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p119">Post-Analog Gain Control audio signal level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="c45fc-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="c45fc-382">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-382">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p120">발신자가 수신한 오디오의 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p120">Audio signal level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="c45fc-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="c45fc-388">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-388">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p121">발신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p121">Post-Analog Gain Control audio noise level for the audio the caller sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="c45fc-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="c45fc-394">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-394">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p122">발신자가 수신한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p122">Post-Analog Gain Control audio noise level for the audio the caller received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="c45fc-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="c45fc-400">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-400">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p123">발신자의 에코 반환 손실 향상 메트릭입니다. 이 메트릭의 단위는 dB입니다. 값이 낮으면 에코가 적습니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p123">Echo Return Loss Enhancement for the caller. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="c45fc-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="c45fc-406">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-406">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p124">발신자의 스피커 렌더링에 대한 5분당 평균 결함 비율입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p124">Average glitches per five minutes for the caller’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="c45fc-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="c45fc-411">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-411">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p125">발신자의 마이크 캡처에 대한 5분당 평균 결함 비율입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p125">Average glitches per five minutes for the caller’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="c45fc-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="c45fc-416">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-417">CPU 클럭 대비 발신자 마이크 장치의 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="c45fc-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="c45fc-419">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-420">CPU 클럭 대비 발신자 스피커 장치의 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="c45fc-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="c45fc-422">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-423">통화의 최근 20초 동안 발생한 평균 마이크 캡처 스트림 타임스탬프 오류(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="c45fc-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="c45fc-425">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-426">통화의 최근 20초 동안 발생한 발신자의 평균 스피커 렌더링 스트림 타임스탬프 오류(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="c45fc-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="c45fc-428">smallint</span><span class="sxs-lookup"><span data-stu-id="c45fc-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="c45fc-429">음성 스위치는 중단 기능이 감소된 반이중 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="c45fc-430">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c45fc-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="c45fc-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="c45fc-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="c45fc-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c45fc-433">발신자의 에코 이벤트의 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="c45fc-434">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c45fc-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="c45fc-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="c45fc-436">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p128">발신자의 마이크 캡처 스트림에서 에코가 감지되는 시간의 비율입니다. 헤드셋을 사용할 경우 값이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p128">Percentage of time when echo is detected in the caller’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="c45fc-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="c45fc-440">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p129">발신자의 전송된 스트림에서 에코가 감지되는 시간의 비율입니다. 전송 스트림에서 에코 비율이 높으면 에코 누출을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p129">Percentage of time when echo is detected in the caller’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="c45fc-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="c45fc-444">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-444">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p130">중재 서버에서 발신자 오디오 게이트웨이로부터 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 [-30 ~ -18] dBoV입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p130">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="c45fc-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="c45fc-449">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-449">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p131">중재 서버에서 발신자 오디오 게이트웨이로부터 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 -50 dBoV 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p131">Received signal level on the Mediation Server from the Gateway for the caller’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="c45fc-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="c45fc-455">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-455">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-456">발신자 오디오에 적용되는 중재 서버 쪽의 AGC(자동 게인 컨트롤)입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="c45fc-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="c45fc-458">식</span><span class="sxs-lookup"><span data-stu-id="c45fc-458">float</span></span></p></td>
<td><p><span data-ttu-id="c45fc-459">통화 초반의 최대 30초 동안 발신자에게 수신되는 신호의 RMS(제곱 평균 오차)입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="c45fc-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="c45fc-461">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-461">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p132">수신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 신호 수준을 나타냅니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p132">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="c45fc-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="c45fc-467">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-467">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p133">수신자가 수신한 오디오의 오디오 신호 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p133">Audio signal level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be at least 30 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="c45fc-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="c45fc-473">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-473">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p134">수신자가 전송한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p134">Post-Analog Gain Control audio noise level for the audio the callee sent. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="c45fc-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="c45fc-479">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-479">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p135">수신자가 수신한 오디오의 포스트 아날로그 게인 컨트롤 오디오 소음 수준입니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p135">Post-Analog Gain Control audio noise level for the audio the callee received. The unit for this metric is dBmo. For acceptable quality, it should be less than 35 dBmo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="c45fc-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="c45fc-485">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-485">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p136">수신자의 에코 반환 손실 향상 메트릭입니다. 이 메트릭의 단위는 dB입니다. 값이 낮으면 에코가 적습니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p136">Echo Return Loss Enhancement for the callee. The unit for this metric is dB. Lower values represent less echo. This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="c45fc-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="c45fc-491">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-491">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p137">수신자의 스피커 렌더링에 대한 5분당 평균 결함 비율입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p137">Average glitches per five minutes for the callee’s loudspeaker rendering. For good quality, this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="c45fc-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="c45fc-496">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-496">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p138">수신자의 마이크 캡처에 대한 5분당 평균 결함 비율입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p138">Average glitches per five minutes for the callee’s microphone capture. For good quality this should be less than one per five minutes. Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="c45fc-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="c45fc-501">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-502">CPU 클럭 대비 수신자 마이크 장치의 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="c45fc-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="c45fc-504">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-505">CPU 클럭 대비 수신자 스피커 장치의 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="c45fc-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="c45fc-507">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-508">통화의 최근 20초 동안 발생한 평균 마이크 캡처 스트림 타임스탬프 오류(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="c45fc-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="c45fc-510">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-511">통화의 최근 20초 동안 발생한 수신자의 평균 스피커 렌더링 스트림 타임스탬프 오류(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="c45fc-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="c45fc-513">smallint</span><span class="sxs-lookup"><span data-stu-id="c45fc-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="c45fc-514">음성 스위치는 중단 기능이 감소된 반이중 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="c45fc-515">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c45fc-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="c45fc-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="c45fc-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="c45fc-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c45fc-518">수신자의 에코 이벤트의 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="c45fc-519">자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c45fc-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="c45fc-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="c45fc-521">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p141">수신자의 마이크 캡처 스트림에서 에코가 감지되는 시간의 비율입니다. 헤드셋을 사용할 경우 값이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p141">Percentage of time when echo is detected in the callee’s microphone capture stream. If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="c45fc-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="c45fc-525">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p142">수신자의 전송된 스트림에서 에코가 감지되는 시간의 비율입니다. 전송 스트림에서 에코 비율이 높으면 에코 누출을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p142">Percentage of time when echo is detected in the callee’s sent stream. High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="c45fc-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="c45fc-529">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-529">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p143">중재 서버에서 수신자 오디오 게이트웨이로부터 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 [-30 ~ -18] dBoV입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p143">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="c45fc-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="c45fc-534">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-534">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p144">중재 서버에서 수신자 오디오 게이트웨이로부터 수신된 신호 수준입니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 -50 dBoV 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p144">Received signal level on the Mediation Server from the Gateway for the callee’s audio. This applies only to the Mediation Server. The unit of this metric is dBoV. For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="c45fc-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="c45fc-540">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-540">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-541">수신자 오디오에 적용되는 중재 서버 쪽의 AGC(자동 게인 컨트롤)입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="c45fc-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="c45fc-543">식</span><span class="sxs-lookup"><span data-stu-id="c45fc-543">float</span></span></p></td>
<td><p><span data-ttu-id="c45fc-544">통화 초반의 최대 30초 동안 수신자에게 수신되는 신호의 RMS(제곱 평균 오차)입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="c45fc-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="c45fc-546">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-547">일반 샘플에 대한 오디오 힐링으로 생성된 숨겨진 평균 샘플 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="c45fc-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="c45fc-549">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-550">일반 샘플에 대한 오디오 힐링으로 생성된 평균 늘임 샘플 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="c45fc-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="c45fc-552">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-553">일반 샘플에 대한 오디오 힐링으로 생성된 숨겨진 압축 샘플 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-554">왕복</span><span class="sxs-lookup"><span data-stu-id="c45fc-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="c45fc-555">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-555">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-556">RTCP 통계로부터의 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="c45fc-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="c45fc-558">int</span><span class="sxs-lookup"><span data-stu-id="c45fc-558">int</span></span></p></td>
<td><p><span data-ttu-id="c45fc-559">오디오 스트림에 대한 최대 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="c45fc-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="c45fc-561">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-p145">통화에 대한 평균 광대역 네트워크 MOS입니다. 이 메트릭은 패킷 손실, 지터 및 사용된 코덱에 따라 달라집니다. 범위는 1.0 ~ 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-p145">Average wideband Network MOS for the call. This metric depends on the packet loss, jitter, and codec used. Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="c45fc-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="c45fc-566">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-567">통화에 대한 최소 광대역 네트워크 MOS입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="c45fc-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="c45fc-569">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-570">음성 수준, 잡음 수준 및 캡처 장치 특성을 포함하여 전송된 오디오에 대한 평균 예측 광대역 청취 MOS 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="c45fc-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="c45fc-572">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-573">통화에 대한 최소 SendListenMOS입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="c45fc-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="c45fc-575">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-576">음성 수준, 잡음 수준, 코덱, 네트워크 조건 및 캡처 장치 특성을 포함하여 수신된 오디오에 대한 평균 예측 광대역 청취 MOS 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="c45fc-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="c45fc-578">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="c45fc-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c45fc-579">통화에 대한 최소 RecvListenMOS입니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c45fc-580">오디오 \ Ecused</span><span class="sxs-lookup"><span data-stu-id="c45fc-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="c45fc-581">비트만</span><span class="sxs-lookup"><span data-stu-id="c45fc-581">bit</span></span></p></td>
<td><p><span data-ttu-id="c45fc-582">통화에 오디오 FEC가 사용되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c45fc-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="c45fc-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="c45fc-584">비트만</span><span class="sxs-lookup"><span data-stu-id="c45fc-584">bit</span></span></p></td>
<td><p><span data-ttu-id="c45fc-585">P-Asserted-Identity 정보의 방향을 나타냅니다. 1은 스트림 방향이 발신자에서 수신자의 방향임을 의미하고, 0은 스트림 방향이 수신자에서 발신자의 방향임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c45fc-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

