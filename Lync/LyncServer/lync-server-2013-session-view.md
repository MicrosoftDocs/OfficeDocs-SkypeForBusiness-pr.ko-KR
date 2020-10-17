---
title: 'Lync Server 2013: 세션 보기'
description: 'Lync Server 2013: 세션 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff4bc4abbd55e073006693d28f092f077698ef75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545014"
---
# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="42f58-103">Lync Server 2013의 세션 보기</span><span class="sxs-lookup"><span data-stu-id="42f58-103">Session view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42f58-104">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="42f58-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="42f58-105">세션 보기에는 데이터베이스의 레코드가 포함된 세션에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-105">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="42f58-106">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42f58-107">열</span><span class="sxs-lookup"><span data-stu-id="42f58-107">Column</span></span></th>
<th><span data-ttu-id="42f58-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="42f58-108">Data Type</span></span></th>
<th><span data-ttu-id="42f58-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="42f58-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42f58-110">Conferencedatetime이 동일할</span><span class="sxs-lookup"><span data-stu-id="42f58-110">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="42f58-111">datetime</span><span class="sxs-lookup"><span data-stu-id="42f58-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="42f58-112">MediaLine 테이블에서 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-112">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42f58-113">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="42f58-113">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="42f58-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="42f58-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="42f58-115">항목이 회의인 경우 회의 URI이고 피어 투 피어 세션인 경우에는 DialogID입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-115">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42f58-116">Correlation</span><span class="sxs-lookup"><span data-stu-id="42f58-116">Correlation</span></span></p></td>
<td><p><span data-ttu-id="42f58-117">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="42f58-117">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="42f58-118">세션의 상관 관계 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-118">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42f58-119">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="42f58-119">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="42f58-120">비트만</span><span class="sxs-lookup"><span data-stu-id="42f58-120">bit</span></span></p></td>
<td><p><span data-ttu-id="42f58-121">대화 상자 범주 0은 중재 서버 레그에 대 한 Lync Server입니다. 1은 PSTN 게이트웨이 레그에 대 한 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-121">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42f58-122">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="42f58-122">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="42f58-123">비트만</span><span class="sxs-lookup"><span data-stu-id="42f58-123">bit</span></span></p></td>
<td><p><span data-ttu-id="42f58-124">통화가 우회되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-124">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42f58-125">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="42f58-125">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="42f58-126">int</span><span class="sxs-lookup"><span data-stu-id="42f58-126">int</span></span></p></td>
<td><p><span data-ttu-id="42f58-127">이 필드(제공된 경우)는 우회 ID가 일치했어도 통화가 우회되지 않은 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-127">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="42f58-128">Lync Server의 경우 한 가지 값만 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-128">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="42f58-129">0x0001 -  기본 네트워크 어댑터에 대한 알 수 없는 바이패스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-129">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42f58-130">StartTime</span><span class="sxs-lookup"><span data-stu-id="42f58-130">StartTime</span></span></p></td>
<td><p><span data-ttu-id="42f58-131">datetime</span><span class="sxs-lookup"><span data-stu-id="42f58-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="42f58-132">통화 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-132">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42f58-133">EndTime</span><span class="sxs-lookup"><span data-stu-id="42f58-133">EndTime</span></span></p></td>
<td><p><span data-ttu-id="42f58-134">datetime</span><span class="sxs-lookup"><span data-stu-id="42f58-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="42f58-135">통화 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-135">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42f58-136">CallerPool</span><span class="sxs-lookup"><span data-stu-id="42f58-136">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="42f58-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42f58-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="42f58-138">발신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-138">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42f58-139">CalleePool</span><span class="sxs-lookup"><span data-stu-id="42f58-139">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="42f58-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42f58-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="42f58-141">수신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-141">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42f58-142">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="42f58-142">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="42f58-143">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="42f58-143">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="42f58-144">발신자의 P-Asserted Identity URI입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-144">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42f58-145">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="42f58-145">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="42f58-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="42f58-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="42f58-147">발신자의 P-Asserted Identity URI입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-147">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42f58-148">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="42f58-148">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="42f58-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42f58-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="42f58-150">발신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-150">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42f58-151">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="42f58-151">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="42f58-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42f58-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="42f58-153">발신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-153">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42f58-154">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="42f58-154">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="42f58-155">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42f58-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="42f58-156">발신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-156">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42f58-157">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="42f58-157">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="42f58-158">smallint</span><span class="sxs-lookup"><span data-stu-id="42f58-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="42f58-159">발신자의 사용자 에이전트 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-159">Type of caller’s user agent.</span></span> <span data-ttu-id="42f58-160">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="42f58-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42f58-161">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="42f58-161">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="42f58-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="42f58-162">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="42f58-163">발신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-163">Category of caller’s user agent.</span></span> <span data-ttu-id="42f58-164">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="42f58-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42f58-165">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="42f58-165">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="42f58-166">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="42f58-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="42f58-167">수신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-167">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42f58-168">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="42f58-168">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="42f58-169">smallint</span><span class="sxs-lookup"><span data-stu-id="42f58-169">smallint</span></span></p></td>
<td><p><span data-ttu-id="42f58-170">수신자의 사용자 에이전트 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-170">Type of user agent for the callee.</span></span> <span data-ttu-id="42f58-171">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="42f58-171">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42f58-172">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="42f58-172">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="42f58-173">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="42f58-173">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="42f58-174">수신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-174">User agent category for the callee.</span></span> <span data-ttu-id="42f58-175">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="42f58-175">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42f58-176">CallerURI</span><span class="sxs-lookup"><span data-stu-id="42f58-176">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="42f58-177">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="42f58-177">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="42f58-178">발신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-178">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42f58-179">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="42f58-179">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="42f58-180">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="42f58-180">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="42f58-181">수신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-181">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42f58-182">Call Oirty</span><span class="sxs-lookup"><span data-stu-id="42f58-182">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="42f58-183">int</span><span class="sxs-lookup"><span data-stu-id="42f58-183">int</span></span></p></td>
<td><p><span data-ttu-id="42f58-184">통화 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="42f58-184">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

