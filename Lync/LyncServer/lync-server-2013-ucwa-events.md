---
title: Lync Server 2013:로 이벤트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0671b51e5fbd4b5f072676855d9e8f5201b3e04
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="217db-102">Lync Server 2013의 일부 이벤트</span><span class="sxs-lookup"><span data-stu-id="217db-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="217db-103">_**마지막으로 수정한 주제:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="217db-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="217db-104">Lync Server 2013는 연락처 검색을 위해 Microsoft Exchange에 액세스 하 여 모바일 클라이언트에 대 한 현재 상태를 업데이트 하는 데 이르기까지 다양 한 용도로 통합 커뮤니케이션 웹 API (c)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="217db-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="217db-105">작업 동작의 레코드를 이벤트 형식 정보, 경고 및 오류로 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="217db-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="217db-106">다음 표에서는 함께 사용할 수 있는 이벤트에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="217db-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="217db-107">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="217db-107">Event ID</span></span></th>
<th><span data-ttu-id="217db-108">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="217db-108">Event Type</span></span></th>
<th><span data-ttu-id="217db-109">요약</span><span class="sxs-lookup"><span data-stu-id="217db-109">Summary</span></span></th>
<th><span data-ttu-id="217db-110">원인 및 해결 방법</span><span class="sxs-lookup"><span data-stu-id="217db-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="217db-111">20001</span><span class="sxs-lookup"><span data-stu-id="217db-111">20001</span></span></p></td>
<td><p><span data-ttu-id="217db-112">나타낼</span><span class="sxs-lookup"><span data-stu-id="217db-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="217db-113">초기화</span><span class="sxs-lookup"><span data-stu-id="217db-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="217db-114">해당 없음</span><span class="sxs-lookup"><span data-stu-id="217db-114">N/A</span></span></p>
<p><span data-ttu-id="217db-115">해당 없음</span><span class="sxs-lookup"><span data-stu-id="217db-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="217db-116">20002</span><span class="sxs-lookup"><span data-stu-id="217db-116">20002</span></span></p></td>
<td><p><span data-ttu-id="217db-117">오류</span><span class="sxs-lookup"><span data-stu-id="217db-117">Error</span></span></p></td>
<td><p><span data-ttu-id="217db-118">초기화 중에 예기치 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="217db-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="217db-119">초기화 하는 동안 예기치 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="217db-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="217db-120">연결 된 이벤트 로그 항목에서 예외 정보를 검사 하 여 가능한 원인을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="217db-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="217db-121">20003</span><span class="sxs-lookup"><span data-stu-id="217db-121">20003</span></span></p></td>
<td><p><span data-ttu-id="217db-122">오류</span><span class="sxs-lookup"><span data-stu-id="217db-122">Error</span></span></p></td>
<td><p><span data-ttu-id="217db-123">A;/WA에서 처리 되지 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="217db-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="217db-124">처리 되지 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="217db-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="217db-125">서버를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="217db-125">Restart the server.</span></span> <span data-ttu-id="217db-126">문제가 지속 되 면 기술 지원팀에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="217db-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="217db-127">20004</span><span class="sxs-lookup"><span data-stu-id="217db-127">20004</span></span></p></td>
<td><p><span data-ttu-id="217db-128">오류</span><span class="sxs-lookup"><span data-stu-id="217db-128">Error</span></span></p></td>
<td><p><span data-ttu-id="217db-129">HD photo에 대 한 Exchange에 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="217db-130">Exchange에 대 한 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="217db-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="217db-131">Exchange에 대 한 연결을 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="217db-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="217db-132">20005</span><span class="sxs-lookup"><span data-stu-id="217db-132">20005</span></span></p></td>
<td><p><span data-ttu-id="217db-133">나타낼</span><span class="sxs-lookup"><span data-stu-id="217db-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="217db-134">HD photo에 대 한 Exchange 액세스 실패 복구</span><span class="sxs-lookup"><span data-stu-id="217db-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="217db-135">해당 없음</span><span class="sxs-lookup"><span data-stu-id="217db-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="217db-136">20006</span><span class="sxs-lookup"><span data-stu-id="217db-136">20006</span></span></p></td>
<td><p><span data-ttu-id="217db-137">오류</span><span class="sxs-lookup"><span data-stu-id="217db-137">Error</span></span></p></td>
<td><p><span data-ttu-id="217db-138">연락처 검색을 위해 Exchange에 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="217db-139">Exchange에 대 한 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="217db-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="217db-140">Exchange에 대 한 연결을 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="217db-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="217db-141">20007</span><span class="sxs-lookup"><span data-stu-id="217db-141">20007</span></span></p></td>
<td><p><span data-ttu-id="217db-142">나타낼</span><span class="sxs-lookup"><span data-stu-id="217db-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="217db-143">Exchange에서 연락처 검색 실패에서 복구 됨</span><span class="sxs-lookup"><span data-stu-id="217db-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="217db-144">해당 없음</span><span class="sxs-lookup"><span data-stu-id="217db-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="217db-145">20008</span><span class="sxs-lookup"><span data-stu-id="217db-145">20008</span></span></p></td>
<td><p><span data-ttu-id="217db-146">오류</span><span class="sxs-lookup"><span data-stu-id="217db-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="217db-147">앱 당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="217db-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="217db-148">앱 당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="217db-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="217db-149">클라이언트에 불필요 한 구독이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="217db-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="217db-150">20009</span><span class="sxs-lookup"><span data-stu-id="217db-150">20009</span></span></p></td>
<td><p><span data-ttu-id="217db-151">오류</span><span class="sxs-lookup"><span data-stu-id="217db-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="217db-152">일괄 처리당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="217db-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="217db-153">일괄 처리당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="217db-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="217db-154">클라이언트에 불필요 한 구독이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="217db-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="217db-155">20010</span><span class="sxs-lookup"><span data-stu-id="217db-155">20010</span></span></p></td>
<td><p><span data-ttu-id="217db-156">오류</span><span class="sxs-lookup"><span data-stu-id="217db-156">Error</span></span></p></td>
<td><p><span data-ttu-id="217db-157">Inband 데이터를 검색할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="217db-158">Inband 데이터를 검색할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="217db-159">문제가 지속 되 면 기술 지원팀에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="217db-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="217db-160">20011</span><span class="sxs-lookup"><span data-stu-id="217db-160">20011</span></span></p></td>
<td><p><span data-ttu-id="217db-161">오류</span><span class="sxs-lookup"><span data-stu-id="217db-161">Error</span></span></p></td>
<td><p><span data-ttu-id="217db-162">현재 상태를 구독할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="217db-163">현재 상태를 구독할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="217db-164">문제가 지속 되 면 기술 지원팀에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="217db-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="217db-165">20012</span><span class="sxs-lookup"><span data-stu-id="217db-165">20012</span></span></p></td>
<td><p><span data-ttu-id="217db-166">오류</span><span class="sxs-lookup"><span data-stu-id="217db-166">Error</span></span></p></td>
<td><p><span data-ttu-id="217db-167">끝점을 등록 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="217db-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="217db-168">끝점을 등록 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="217db-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="217db-169">문제가 지속 되 면 기술 지원팀에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="217db-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="217db-170">20013</span><span class="sxs-lookup"><span data-stu-id="217db-170">20013</span></span></p></td>
<td><p><span data-ttu-id="217db-171">오류</span><span class="sxs-lookup"><span data-stu-id="217db-171">Error</span></span></p></td>
<td><p><span data-ttu-id="217db-172">메신저 대화 MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="217db-173">메신저 대화 MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="217db-174">메신저 대화 MCU 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="217db-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="217db-175">20014</span><span class="sxs-lookup"><span data-stu-id="217db-175">20014</span></span></p></td>
<td><p><span data-ttu-id="217db-176">나타낼</span><span class="sxs-lookup"><span data-stu-id="217db-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="217db-177">실패에서 메신저 대화에 연결 되지 않도록 복구 됨</span><span class="sxs-lookup"><span data-stu-id="217db-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="217db-178">해당 없음</span><span class="sxs-lookup"><span data-stu-id="217db-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="217db-179">20015</span><span class="sxs-lookup"><span data-stu-id="217db-179">20015</span></span></p></td>
<td><p><span data-ttu-id="217db-180">오류</span><span class="sxs-lookup"><span data-stu-id="217db-180">Error</span></span></p></td>
<td><p><span data-ttu-id="217db-181">AV MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="217db-182">AV MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="217db-183">AV MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="217db-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="217db-184">20016</span><span class="sxs-lookup"><span data-stu-id="217db-184">20016</span></span></p></td>
<td><p><span data-ttu-id="217db-185">나타낼</span><span class="sxs-lookup"><span data-stu-id="217db-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="217db-186">이 (가) AV MCU 연결 실패에서 복구 됨</span><span class="sxs-lookup"><span data-stu-id="217db-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="217db-187">해당 없음</span><span class="sxs-lookup"><span data-stu-id="217db-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="217db-188">20017</span><span class="sxs-lookup"><span data-stu-id="217db-188">20017</span></span></p></td>
<td><p><span data-ttu-id="217db-189">오류</span><span class="sxs-lookup"><span data-stu-id="217db-189">Error</span></span></p></td>
<td><p><span data-ttu-id="217db-190">MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="217db-191">MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="217db-192">MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="217db-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="217db-193">20018</span><span class="sxs-lookup"><span data-stu-id="217db-193">20018</span></span></p></td>
<td><p><span data-ttu-id="217db-194">나타낼</span><span class="sxs-lookup"><span data-stu-id="217db-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="217db-195">이 (가) MCU에 연결 하지 못한 경우 복구 됨</span><span class="sxs-lookup"><span data-stu-id="217db-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="217db-196">해당 없음</span><span class="sxs-lookup"><span data-stu-id="217db-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="217db-197">20019</span><span class="sxs-lookup"><span data-stu-id="217db-197">20019</span></span></p></td>
<td><p><span data-ttu-id="217db-198">오류</span><span class="sxs-lookup"><span data-stu-id="217db-198">Error</span></span></p></td>
<td><p><span data-ttu-id="217db-199">데이터 MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="217db-200">데이터 MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="217db-201">데이터 MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="217db-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="217db-202">20020</span><span class="sxs-lookup"><span data-stu-id="217db-202">20020</span></span></p></td>
<td><p><span data-ttu-id="217db-203">나타낼</span><span class="sxs-lookup"><span data-stu-id="217db-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="217db-204">데이터 MCU 연결에 실패 하 여 복구 되지 않음</span><span class="sxs-lookup"><span data-stu-id="217db-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="217db-205">해당 없음</span><span class="sxs-lookup"><span data-stu-id="217db-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="217db-206">20021</span><span class="sxs-lookup"><span data-stu-id="217db-206">20021</span></span></p></td>
<td><p><span data-ttu-id="217db-207">오류</span><span class="sxs-lookup"><span data-stu-id="217db-207">Error</span></span></p></td>
<td><p><span data-ttu-id="217db-208">메신저 대화 MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="217db-209">메신저 대화 MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="217db-210">메신저 대화 MCU 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="217db-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="217db-211">20022</span><span class="sxs-lookup"><span data-stu-id="217db-211">20022</span></span></p></td>
<td><p><span data-ttu-id="217db-212">오류</span><span class="sxs-lookup"><span data-stu-id="217db-212">Error</span></span></p></td>
<td><p><span data-ttu-id="217db-213">AV MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="217db-214">AV MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="217db-215">AV MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="217db-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="217db-216">20023</span><span class="sxs-lookup"><span data-stu-id="217db-216">20023</span></span></p></td>
<td><p><span data-ttu-id="217db-217">오류</span><span class="sxs-lookup"><span data-stu-id="217db-217">Error</span></span></p></td>
<td><p><span data-ttu-id="217db-218">MCU로 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="217db-219">MCU로 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="217db-220">MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="217db-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="217db-221">20024</span><span class="sxs-lookup"><span data-stu-id="217db-221">20024</span></span></p></td>
<td><p><span data-ttu-id="217db-222">오류</span><span class="sxs-lookup"><span data-stu-id="217db-222">Error</span></span></p></td>
<td><p><span data-ttu-id="217db-223">데이터 MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="217db-224">데이터 MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="217db-225">데이터 MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="217db-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="217db-226">20025</span><span class="sxs-lookup"><span data-stu-id="217db-226">20025</span></span></p></td>
<td><p><span data-ttu-id="217db-227">오류</span><span class="sxs-lookup"><span data-stu-id="217db-227">Error</span></span></p></td>
<td><p><span data-ttu-id="217db-228">사진에 대 한 active directory에 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="217db-229">Active directory에 대 한 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="217db-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="217db-230">Active directory에 대 한 연결을 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="217db-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="217db-231">20026</span><span class="sxs-lookup"><span data-stu-id="217db-231">20026</span></span></p></td>
<td><p><span data-ttu-id="217db-232">나타낼</span><span class="sxs-lookup"><span data-stu-id="217db-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="217db-233">사진에 대 한 active directory 액세스가 실패 함에 복구 됨</span><span class="sxs-lookup"><span data-stu-id="217db-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="217db-234">해당 없음</span><span class="sxs-lookup"><span data-stu-id="217db-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="217db-235">20027</span><span class="sxs-lookup"><span data-stu-id="217db-235">20027</span></span></p></td>
<td><p><span data-ttu-id="217db-236">오류</span><span class="sxs-lookup"><span data-stu-id="217db-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="217db-237">Deserialize 할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="217db-238">Deserialize 할 수 없음</span><span class="sxs-lookup"><span data-stu-id="217db-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="217db-239">문제가 지속 되 면 기술 지원팀에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="217db-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

