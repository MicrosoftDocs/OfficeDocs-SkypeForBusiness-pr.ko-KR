---
title: 'Lync Server 2013: 세션 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a90d6a3f066caccb20b141daa485cabea29e2352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="b0c47-102">Lync Server 2013의 세션 보기</span><span class="sxs-lookup"><span data-stu-id="b0c47-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0c47-103">_**마지막으로 수정한 주제:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="b0c47-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="b0c47-104">세션 보기는 데이터베이스에 레코드가 있는 세션에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="b0c47-105">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0c47-106">열</span><span class="sxs-lookup"><span data-stu-id="b0c47-106">Column</span></span></th>
<th><span data-ttu-id="b0c47-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b0c47-107">Data Type</span></span></th>
<th><span data-ttu-id="b0c47-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="b0c47-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0c47-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="b0c47-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="b0c47-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="b0c47-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b0c47-111">MediaLine 테이블에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0c47-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="b0c47-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="b0c47-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b0c47-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b0c47-114">회의가 면 회의 URI이 고 피어 투 피어 세션 인 경우 DialogID입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0c47-115">상관이</span><span class="sxs-lookup"><span data-stu-id="b0c47-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="b0c47-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="b0c47-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="b0c47-117">세션의 상관 관계 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0c47-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="b0c47-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="b0c47-119">다소</span><span class="sxs-lookup"><span data-stu-id="b0c47-119">bit</span></span></p></td>
<td><p><span data-ttu-id="b0c47-120">대화 상자 범주 0은 서버 레그 조정을 위한 Lync Server입니다. 1이 (가) PSTN 게이트웨이 레그로 서버를 중재 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0c47-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="b0c47-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="b0c47-122">다소</span><span class="sxs-lookup"><span data-stu-id="b0c47-122">bit</span></span></p></td>
<td><p><span data-ttu-id="b0c47-123">통화가 생략 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0c47-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="b0c47-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="b0c47-125">int</span><span class="sxs-lookup"><span data-stu-id="b0c47-125">int</span></span></p></td>
<td><p><span data-ttu-id="b0c47-126">이 필드에는 바이패스 Id가 일치 하는 경우에도 통화가 무시 되지 않은 이유가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="b0c47-127">Lync Server의 경우 하나의 값만 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="b0c47-128">0x0001-기본 네트워크 어댑터에 대 한 알 수 없는 바이패스 ID</span><span class="sxs-lookup"><span data-stu-id="b0c47-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0c47-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="b0c47-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="b0c47-130">dmtf</span><span class="sxs-lookup"><span data-stu-id="b0c47-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="b0c47-131">통화 시작 시간.</span><span class="sxs-lookup"><span data-stu-id="b0c47-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0c47-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="b0c47-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="b0c47-133">dmtf</span><span class="sxs-lookup"><span data-stu-id="b0c47-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="b0c47-134">통화 종료 시간.</span><span class="sxs-lookup"><span data-stu-id="b0c47-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0c47-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="b0c47-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="b0c47-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b0c47-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b0c47-137">발신자 풀 FQDN.</span><span class="sxs-lookup"><span data-stu-id="b0c47-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0c47-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="b0c47-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="b0c47-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b0c47-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b0c47-140">호출 수신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0c47-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="b0c47-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="b0c47-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b0c47-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b0c47-143">호출자의 p-어설션된 id URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0c47-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="b0c47-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="b0c47-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b0c47-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b0c47-146">피호출자의 p-어설션된 id URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0c47-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="b0c47-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="b0c47-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b0c47-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b0c47-149">호출자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0c47-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="b0c47-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="b0c47-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b0c47-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b0c47-152">호출자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0c47-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="b0c47-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="b0c47-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b0c47-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b0c47-155">호출자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0c47-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="b0c47-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="b0c47-157">smallint</span><span class="sxs-lookup"><span data-stu-id="b0c47-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="b0c47-158">호출자의 사용자 에이전트 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-158">Type of caller’s user agent.</span></span> <span data-ttu-id="b0c47-159">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b0c47-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0c47-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="b0c47-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="b0c47-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b0c47-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="b0c47-162">호출자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-162">Category of caller’s user agent.</span></span> <span data-ttu-id="b0c47-163">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (체감 품질)</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b0c47-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0c47-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="b0c47-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="b0c47-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b0c47-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b0c47-166">호출 수신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0c47-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="b0c47-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="b0c47-168">smallint</span><span class="sxs-lookup"><span data-stu-id="b0c47-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="b0c47-169">호출 수신자의 사용자 에이전트 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-169">Type of user agent for the callee.</span></span> <span data-ttu-id="b0c47-170">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b0c47-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0c47-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="b0c47-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="b0c47-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b0c47-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="b0c47-173">호출 수신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-173">User agent category for the callee.</span></span> <span data-ttu-id="b0c47-174">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (체감 품질)</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b0c47-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0c47-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="b0c47-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="b0c47-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b0c47-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b0c47-177">호출자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0c47-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="b0c47-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="b0c47-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b0c47-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b0c47-180">호출 수신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0c47-181">Callto Oirty</span><span class="sxs-lookup"><span data-stu-id="b0c47-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="b0c47-182">int</span><span class="sxs-lookup"><span data-stu-id="b0c47-182">int</span></span></p></td>
<td><p><span data-ttu-id="b0c47-183">통화의 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="b0c47-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

