---
title: 'Lync Server 2013: 세션 보기'
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
ms.openlocfilehash: 80b9c7c9b54deb28b70c8ee2386359bec37d5a69
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="9bf63-102">Lync Server 2013의 세션 보기</span><span class="sxs-lookup"><span data-stu-id="9bf63-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bf63-103">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9bf63-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9bf63-104">세션 보기에는 데이터베이스의 레코드가 포함된 세션에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="9bf63-105">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9bf63-106">열</span><span class="sxs-lookup"><span data-stu-id="9bf63-106">Column</span></span></th>
<th><span data-ttu-id="9bf63-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9bf63-107">Data Type</span></span></th>
<th><span data-ttu-id="9bf63-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="9bf63-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9bf63-109">Conferencedatetime이 동일할</span><span class="sxs-lookup"><span data-stu-id="9bf63-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="9bf63-110">datetime</span><span class="sxs-lookup"><span data-stu-id="9bf63-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="9bf63-111">MediaLine 테이블에서 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bf63-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="9bf63-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="9bf63-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9bf63-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9bf63-114">항목이 회의인 경우 회의 URI이고 피어 투 피어 세션인 경우에는 DialogID입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bf63-115">Correlation</span><span class="sxs-lookup"><span data-stu-id="9bf63-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="9bf63-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="9bf63-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="9bf63-117">세션의 상관 관계 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bf63-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="9bf63-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="9bf63-119">비트만</span><span class="sxs-lookup"><span data-stu-id="9bf63-119">bit</span></span></p></td>
<td><p><span data-ttu-id="9bf63-120">대화 상자 범주 0은 중재 서버 레그에 대 한 Lync Server입니다. 1은 PSTN 게이트웨이 레그에 대 한 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bf63-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="9bf63-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="9bf63-122">비트만</span><span class="sxs-lookup"><span data-stu-id="9bf63-122">bit</span></span></p></td>
<td><p><span data-ttu-id="9bf63-123">통화가 우회되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bf63-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="9bf63-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="9bf63-125">int</span><span class="sxs-lookup"><span data-stu-id="9bf63-125">int</span></span></p></td>
<td><p><span data-ttu-id="9bf63-126">이 필드(제공된 경우)는 우회 ID가 일치했어도 통화가 우회되지 않은 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="9bf63-127">Lync Server의 경우 한 가지 값만 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="9bf63-128">0x0001 -  기본 네트워크 어댑터에 대한 알 수 없는 바이패스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bf63-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="9bf63-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="9bf63-130">datetime</span><span class="sxs-lookup"><span data-stu-id="9bf63-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="9bf63-131">통화 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bf63-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="9bf63-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="9bf63-133">datetime</span><span class="sxs-lookup"><span data-stu-id="9bf63-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="9bf63-134">통화 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bf63-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="9bf63-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="9bf63-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9bf63-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9bf63-137">발신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bf63-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="9bf63-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="9bf63-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9bf63-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9bf63-140">수신자 풀 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bf63-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="9bf63-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="9bf63-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9bf63-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9bf63-143">발신자의 P-Asserted Identity URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bf63-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="9bf63-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="9bf63-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9bf63-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9bf63-146">발신자의 P-Asserted Identity URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bf63-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="9bf63-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="9bf63-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9bf63-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9bf63-149">발신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bf63-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="9bf63-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="9bf63-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9bf63-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9bf63-152">발신자의 끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bf63-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="9bf63-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="9bf63-154">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9bf63-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9bf63-155">발신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bf63-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="9bf63-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="9bf63-157">smallint</span><span class="sxs-lookup"><span data-stu-id="9bf63-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="9bf63-158">발신자의 사용자 에이전트 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-158">Type of caller’s user agent.</span></span> <span data-ttu-id="9bf63-159">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bf63-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bf63-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="9bf63-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="9bf63-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9bf63-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="9bf63-162">발신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-162">Category of caller’s user agent.</span></span> <span data-ttu-id="9bf63-163">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bf63-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bf63-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="9bf63-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="9bf63-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9bf63-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9bf63-166">수신자의 사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bf63-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="9bf63-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="9bf63-168">smallint</span><span class="sxs-lookup"><span data-stu-id="9bf63-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="9bf63-169">수신자의 사용자 에이전트 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-169">Type of user agent for the callee.</span></span> <span data-ttu-id="9bf63-170">자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bf63-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bf63-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="9bf63-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="9bf63-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9bf63-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="9bf63-173">수신자의 사용자 에이전트 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-173">User agent category for the callee.</span></span> <span data-ttu-id="9bf63-174">자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9bf63-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bf63-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="9bf63-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="9bf63-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9bf63-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9bf63-177">발신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bf63-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="9bf63-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="9bf63-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9bf63-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9bf63-180">수신자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bf63-181">Call Oirty</span><span class="sxs-lookup"><span data-stu-id="9bf63-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="9bf63-182">int</span><span class="sxs-lookup"><span data-stu-id="9bf63-182">int</span></span></p></td>
<td><p><span data-ttu-id="9bf63-183">통화 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="9bf63-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

