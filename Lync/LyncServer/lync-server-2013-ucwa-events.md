---
title: Lync Server 2013:로 이벤트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5063aca74fe3454569a2b2309be584a4ca11d13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="d77ca-102">Lync Server 2013의 일부 이벤트</span><span class="sxs-lookup"><span data-stu-id="d77ca-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d77ca-103">_**마지막으로 수정한 주제:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="d77ca-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="d77ca-104">Lync Server 2013는 연락처 검색을 위해 Microsoft Exchange에 액세스 하 여 모바일 클라이언트에 대 한 현재 상태를 업데이트 하는 데 이르기까지 다양 한 용도로 통합 커뮤니케이션 웹 API (c)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="d77ca-105">작업 동작의 레코드를 이벤트 형식 정보, 경고 및 오류로 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="d77ca-106">다음 표에서는 함께 사용할 수 있는 이벤트에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d77ca-107">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d77ca-107">Event ID</span></span></th>
<th><span data-ttu-id="d77ca-108">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="d77ca-108">Event Type</span></span></th>
<th><span data-ttu-id="d77ca-109">요약</span><span class="sxs-lookup"><span data-stu-id="d77ca-109">Summary</span></span></th>
<th><span data-ttu-id="d77ca-110">원인 및 해결 방법</span><span class="sxs-lookup"><span data-stu-id="d77ca-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d77ca-111">20001</span><span class="sxs-lookup"><span data-stu-id="d77ca-111">20001</span></span></p></td>
<td><p><span data-ttu-id="d77ca-112">나타낼</span><span class="sxs-lookup"><span data-stu-id="d77ca-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="d77ca-113">초기화</span><span class="sxs-lookup"><span data-stu-id="d77ca-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="d77ca-114">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-114">N/A</span></span></p>
<p><span data-ttu-id="d77ca-115">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d77ca-116">20002</span><span class="sxs-lookup"><span data-stu-id="d77ca-116">20002</span></span></p></td>
<td><p><span data-ttu-id="d77ca-117">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-117">Error</span></span></p></td>
<td><p><span data-ttu-id="d77ca-118">초기화 중에 예기치 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="d77ca-119">초기화 하는 동안 예기치 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="d77ca-120">연결 된 이벤트 로그 항목에서 예외 정보를 검사 하 여 가능한 원인을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d77ca-121">20003</span><span class="sxs-lookup"><span data-stu-id="d77ca-121">20003</span></span></p></td>
<td><p><span data-ttu-id="d77ca-122">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-122">Error</span></span></p></td>
<td><p><span data-ttu-id="d77ca-123">A;/WA에서 처리 되지 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="d77ca-124">처리 되지 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="d77ca-125">서버를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-125">Restart the server.</span></span> <span data-ttu-id="d77ca-126">문제가 지속 되 면 기술 지원팀에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d77ca-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d77ca-127">20004</span><span class="sxs-lookup"><span data-stu-id="d77ca-127">20004</span></span></p></td>
<td><p><span data-ttu-id="d77ca-128">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-128">Error</span></span></p></td>
<td><p><span data-ttu-id="d77ca-129">HD photo에 대 한 Exchange에 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="d77ca-130">Exchange에 대 한 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="d77ca-131">Exchange에 대 한 연결을 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="d77ca-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d77ca-132">20005</span><span class="sxs-lookup"><span data-stu-id="d77ca-132">20005</span></span></p></td>
<td><p><span data-ttu-id="d77ca-133">나타낼</span><span class="sxs-lookup"><span data-stu-id="d77ca-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="d77ca-134">HD photo에 대 한 Exchange 액세스 실패 복구</span><span class="sxs-lookup"><span data-stu-id="d77ca-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="d77ca-135">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d77ca-136">20006</span><span class="sxs-lookup"><span data-stu-id="d77ca-136">20006</span></span></p></td>
<td><p><span data-ttu-id="d77ca-137">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-137">Error</span></span></p></td>
<td><p><span data-ttu-id="d77ca-138">연락처 검색을 위해 Exchange에 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="d77ca-139">Exchange에 대 한 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="d77ca-140">Exchange에 대 한 연결을 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="d77ca-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d77ca-141">20007</span><span class="sxs-lookup"><span data-stu-id="d77ca-141">20007</span></span></p></td>
<td><p><span data-ttu-id="d77ca-142">나타낼</span><span class="sxs-lookup"><span data-stu-id="d77ca-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="d77ca-143">Exchange에서 연락처 검색 실패에서 복구 됨</span><span class="sxs-lookup"><span data-stu-id="d77ca-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="d77ca-144">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d77ca-145">20008</span><span class="sxs-lookup"><span data-stu-id="d77ca-145">20008</span></span></p></td>
<td><p><span data-ttu-id="d77ca-146">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="d77ca-147">앱 당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="d77ca-148">앱 당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="d77ca-149">클라이언트에 불필요 한 구독이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="d77ca-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d77ca-150">20009</span><span class="sxs-lookup"><span data-stu-id="d77ca-150">20009</span></span></p></td>
<td><p><span data-ttu-id="d77ca-151">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="d77ca-152">일괄 처리당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="d77ca-153">일괄 처리당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="d77ca-154">클라이언트에 불필요 한 구독이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="d77ca-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d77ca-155">20010</span><span class="sxs-lookup"><span data-stu-id="d77ca-155">20010</span></span></p></td>
<td><p><span data-ttu-id="d77ca-156">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-156">Error</span></span></p></td>
<td><p><span data-ttu-id="d77ca-157">Inband 데이터를 검색할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="d77ca-158">Inband 데이터를 검색할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="d77ca-159">문제가 지속 되 면 기술 지원팀에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d77ca-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d77ca-160">20011</span><span class="sxs-lookup"><span data-stu-id="d77ca-160">20011</span></span></p></td>
<td><p><span data-ttu-id="d77ca-161">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-161">Error</span></span></p></td>
<td><p><span data-ttu-id="d77ca-162">현재 상태를 구독할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="d77ca-163">현재 상태를 구독할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="d77ca-164">문제가 지속 되 면 기술 지원팀에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d77ca-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d77ca-165">20012</span><span class="sxs-lookup"><span data-stu-id="d77ca-165">20012</span></span></p></td>
<td><p><span data-ttu-id="d77ca-166">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-166">Error</span></span></p></td>
<td><p><span data-ttu-id="d77ca-167">끝점을 등록 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="d77ca-168">끝점을 등록 하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="d77ca-169">문제가 지속 되 면 기술 지원팀에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d77ca-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d77ca-170">20013</span><span class="sxs-lookup"><span data-stu-id="d77ca-170">20013</span></span></p></td>
<td><p><span data-ttu-id="d77ca-171">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-171">Error</span></span></p></td>
<td><p><span data-ttu-id="d77ca-172">메신저 대화 MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d77ca-173">메신저 대화 MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="d77ca-174">메신저 대화 MCU 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="d77ca-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d77ca-175">20014</span><span class="sxs-lookup"><span data-stu-id="d77ca-175">20014</span></span></p></td>
<td><p><span data-ttu-id="d77ca-176">나타낼</span><span class="sxs-lookup"><span data-stu-id="d77ca-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="d77ca-177">실패에서 메신저 대화에 연결 되지 않도록 복구 됨</span><span class="sxs-lookup"><span data-stu-id="d77ca-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="d77ca-178">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d77ca-179">20015</span><span class="sxs-lookup"><span data-stu-id="d77ca-179">20015</span></span></p></td>
<td><p><span data-ttu-id="d77ca-180">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-180">Error</span></span></p></td>
<td><p><span data-ttu-id="d77ca-181">AV MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d77ca-182">AV MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="d77ca-183">AV MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="d77ca-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d77ca-184">20016</span><span class="sxs-lookup"><span data-stu-id="d77ca-184">20016</span></span></p></td>
<td><p><span data-ttu-id="d77ca-185">나타낼</span><span class="sxs-lookup"><span data-stu-id="d77ca-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="d77ca-186">이 (가) AV MCU 연결 실패에서 복구 됨</span><span class="sxs-lookup"><span data-stu-id="d77ca-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="d77ca-187">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d77ca-188">20017</span><span class="sxs-lookup"><span data-stu-id="d77ca-188">20017</span></span></p></td>
<td><p><span data-ttu-id="d77ca-189">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-189">Error</span></span></p></td>
<td><p><span data-ttu-id="d77ca-190">MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d77ca-191">MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="d77ca-192">MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="d77ca-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d77ca-193">20018</span><span class="sxs-lookup"><span data-stu-id="d77ca-193">20018</span></span></p></td>
<td><p><span data-ttu-id="d77ca-194">나타낼</span><span class="sxs-lookup"><span data-stu-id="d77ca-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="d77ca-195">이 (가) MCU에 연결 하지 못한 경우 복구 됨</span><span class="sxs-lookup"><span data-stu-id="d77ca-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="d77ca-196">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d77ca-197">20019</span><span class="sxs-lookup"><span data-stu-id="d77ca-197">20019</span></span></p></td>
<td><p><span data-ttu-id="d77ca-198">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-198">Error</span></span></p></td>
<td><p><span data-ttu-id="d77ca-199">데이터 MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d77ca-200">데이터 MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="d77ca-201">데이터 MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="d77ca-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d77ca-202">20020</span><span class="sxs-lookup"><span data-stu-id="d77ca-202">20020</span></span></p></td>
<td><p><span data-ttu-id="d77ca-203">나타낼</span><span class="sxs-lookup"><span data-stu-id="d77ca-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="d77ca-204">데이터 MCU 연결에 실패 하 여 복구 되지 않음</span><span class="sxs-lookup"><span data-stu-id="d77ca-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="d77ca-205">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d77ca-206">20021</span><span class="sxs-lookup"><span data-stu-id="d77ca-206">20021</span></span></p></td>
<td><p><span data-ttu-id="d77ca-207">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-207">Error</span></span></p></td>
<td><p><span data-ttu-id="d77ca-208">메신저 대화 MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="d77ca-209">메신저 대화 MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="d77ca-210">메신저 대화 MCU 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="d77ca-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d77ca-211">20022</span><span class="sxs-lookup"><span data-stu-id="d77ca-211">20022</span></span></p></td>
<td><p><span data-ttu-id="d77ca-212">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-212">Error</span></span></p></td>
<td><p><span data-ttu-id="d77ca-213">AV MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="d77ca-214">AV MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="d77ca-215">AV MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="d77ca-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d77ca-216">20023</span><span class="sxs-lookup"><span data-stu-id="d77ca-216">20023</span></span></p></td>
<td><p><span data-ttu-id="d77ca-217">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-217">Error</span></span></p></td>
<td><p><span data-ttu-id="d77ca-218">MCU로 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="d77ca-219">MCU로 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="d77ca-220">MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="d77ca-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d77ca-221">20024</span><span class="sxs-lookup"><span data-stu-id="d77ca-221">20024</span></span></p></td>
<td><p><span data-ttu-id="d77ca-222">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-222">Error</span></span></p></td>
<td><p><span data-ttu-id="d77ca-223">데이터 MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="d77ca-224">데이터 MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="d77ca-225">데이터 MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="d77ca-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d77ca-226">20025</span><span class="sxs-lookup"><span data-stu-id="d77ca-226">20025</span></span></p></td>
<td><p><span data-ttu-id="d77ca-227">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-227">Error</span></span></p></td>
<td><p><span data-ttu-id="d77ca-228">사진에 대 한 active directory에 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="d77ca-229">Active directory에 대 한 연결을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d77ca-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="d77ca-230">Active directory에 대 한 연결을 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="d77ca-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d77ca-231">20026</span><span class="sxs-lookup"><span data-stu-id="d77ca-231">20026</span></span></p></td>
<td><p><span data-ttu-id="d77ca-232">나타낼</span><span class="sxs-lookup"><span data-stu-id="d77ca-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="d77ca-233">사진에 대 한 active directory 액세스가 실패 함에 복구 됨</span><span class="sxs-lookup"><span data-stu-id="d77ca-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="d77ca-234">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d77ca-235">20027</span><span class="sxs-lookup"><span data-stu-id="d77ca-235">20027</span></span></p></td>
<td><p><span data-ttu-id="d77ca-236">오류</span><span class="sxs-lookup"><span data-stu-id="d77ca-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="d77ca-237">Deserialize 할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="d77ca-238">Deserialize 할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d77ca-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="d77ca-239">문제가 지속 되 면 기술 지원팀에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d77ca-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

