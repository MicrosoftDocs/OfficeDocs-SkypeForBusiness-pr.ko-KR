---
title: 'Lync Server 2013: c (WA) 이벤트'
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
ms.openlocfilehash: 1ae71fa6e91c0bc212bc019b1afa85ebcacb4d0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527795"
---
# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="51c80-102">Lync Server 2013의 c/WA 이벤트</span><span class="sxs-lookup"><span data-stu-id="51c80-102">UCWA events in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51c80-103">_**마지막으로 수정 된 항목:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="51c80-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="51c80-104">Lync Server 2013에서는 Microsoft Exchange에 액세스 하 여 모바일 클라이언트의 현재 상태를 업데이트 하는 데 필요한 다양 한 목적으로 통합 커뮤니케이션 웹 API (c)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c80-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="51c80-105">C u r c c r 12에서는 작업 동작 기록을 이벤트 유형 정보, 경고 및 오류로 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c80-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="51c80-106">다음 표에서는 c-WA 구성 요소에서 작성할 수 있는 이벤트에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c80-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51c80-107">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="51c80-107">Event ID</span></span></th>
<th><span data-ttu-id="51c80-108">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="51c80-108">Event Type</span></span></th>
<th><span data-ttu-id="51c80-109">요약</span><span class="sxs-lookup"><span data-stu-id="51c80-109">Summary</span></span></th>
<th><span data-ttu-id="51c80-110">원인 및 해결 방법</span><span class="sxs-lookup"><span data-stu-id="51c80-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51c80-111">20001</span><span class="sxs-lookup"><span data-stu-id="51c80-111">20001</span></span></p></td>
<td><p><span data-ttu-id="51c80-112">알림</span><span class="sxs-lookup"><span data-stu-id="51c80-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="51c80-113">과 (와) 초기화 됨</span><span class="sxs-lookup"><span data-stu-id="51c80-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="51c80-114">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-114">N/A</span></span></p>
<p><span data-ttu-id="51c80-115">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c80-116">20002</span><span class="sxs-lookup"><span data-stu-id="51c80-116">20002</span></span></p></td>
<td><p><span data-ttu-id="51c80-117">오류</span><span class="sxs-lookup"><span data-stu-id="51c80-117">Error</span></span></p></td>
<td><p><span data-ttu-id="51c80-118">초기화 하는 동안 c #에서 예기치 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="51c80-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="51c80-119">초기화 하는 동안 예기치 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="51c80-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="51c80-120">관련 된 이벤트 로그 항목에서 예외 정보를 검사 하 여 가능한 원인을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c80-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51c80-121">20003</span><span class="sxs-lookup"><span data-stu-id="51c80-121">20003</span></span></p></td>
<td><p><span data-ttu-id="51c80-122">오류</span><span class="sxs-lookup"><span data-stu-id="51c80-122">Error</span></span></p></td>
<td><p><span data-ttu-id="51c80-123">(C)에서 처리 되지 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="51c80-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="51c80-124">처리 되지 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="51c80-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="51c80-125">서버를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="51c80-125">Restart the server.</span></span> <span data-ttu-id="51c80-126">문제가 계속 되 면 기술 지원 서비스에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="51c80-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c80-127">20004</span><span class="sxs-lookup"><span data-stu-id="51c80-127">20004</span></span></p></td>
<td><p><span data-ttu-id="51c80-128">오류</span><span class="sxs-lookup"><span data-stu-id="51c80-128">Error</span></span></p></td>
<td><p><span data-ttu-id="51c80-129">HD photo에 대 한 Exchange에 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="51c80-130">Exchange에 대 한 연결을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="51c80-131">Exchange에 대 한 연결을 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="51c80-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51c80-132">20005</span><span class="sxs-lookup"><span data-stu-id="51c80-132">20005</span></span></p></td>
<td><p><span data-ttu-id="51c80-133">알림</span><span class="sxs-lookup"><span data-stu-id="51c80-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="51c80-134">HD photo에 대 한 Exchange 액세스 실패에서 복구 됨</span><span class="sxs-lookup"><span data-stu-id="51c80-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="51c80-135">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c80-136">20006</span><span class="sxs-lookup"><span data-stu-id="51c80-136">20006</span></span></p></td>
<td><p><span data-ttu-id="51c80-137">오류</span><span class="sxs-lookup"><span data-stu-id="51c80-137">Error</span></span></p></td>
<td><p><span data-ttu-id="51c80-138">Exchange에 연락처 검색을 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="51c80-139">Exchange에 대 한 연결을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="51c80-140">Exchange에 대 한 연결을 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="51c80-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51c80-141">20007</span><span class="sxs-lookup"><span data-stu-id="51c80-141">20007</span></span></p></td>
<td><p><span data-ttu-id="51c80-142">알림</span><span class="sxs-lookup"><span data-stu-id="51c80-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="51c80-143">Exchange에서 실패 한 대화 상대 로부터 복구 됨</span><span class="sxs-lookup"><span data-stu-id="51c80-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="51c80-144">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c80-145">20008</span><span class="sxs-lookup"><span data-stu-id="51c80-145">20008</span></span></p></td>
<td><p><span data-ttu-id="51c80-146">경고</span><span class="sxs-lookup"><span data-stu-id="51c80-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="51c80-147">응용 프로그램당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c80-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="51c80-148">응용 프로그램당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c80-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="51c80-149">클라이언트에서 불필요 한 구독 확인</span><span class="sxs-lookup"><span data-stu-id="51c80-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51c80-150">20009</span><span class="sxs-lookup"><span data-stu-id="51c80-150">20009</span></span></p></td>
<td><p><span data-ttu-id="51c80-151">경고</span><span class="sxs-lookup"><span data-stu-id="51c80-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="51c80-152">일괄 처리당 허용 되는 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c80-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="51c80-153">일괄 처리당 허용 되는 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c80-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="51c80-154">클라이언트에서 불필요 한 구독 확인</span><span class="sxs-lookup"><span data-stu-id="51c80-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c80-155">20010</span><span class="sxs-lookup"><span data-stu-id="51c80-155">20010</span></span></p></td>
<td><p><span data-ttu-id="51c80-156">오류</span><span class="sxs-lookup"><span data-stu-id="51c80-156">Error</span></span></p></td>
<td><p><span data-ttu-id="51c80-157">인밴드 데이터를 검색할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="51c80-158">인밴드 데이터를 검색할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="51c80-159">문제가 계속 되 면 기술 지원 서비스에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="51c80-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51c80-160">20011</span><span class="sxs-lookup"><span data-stu-id="51c80-160">20011</span></span></p></td>
<td><p><span data-ttu-id="51c80-161">오류</span><span class="sxs-lookup"><span data-stu-id="51c80-161">Error</span></span></p></td>
<td><p><span data-ttu-id="51c80-162">현재 상태 구독 불가능</span><span class="sxs-lookup"><span data-stu-id="51c80-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="51c80-163">현재 상태 구독 불가능</span><span class="sxs-lookup"><span data-stu-id="51c80-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="51c80-164">문제가 계속 되 면 기술 지원 서비스에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="51c80-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c80-165">20012</span><span class="sxs-lookup"><span data-stu-id="51c80-165">20012</span></span></p></td>
<td><p><span data-ttu-id="51c80-166">오류</span><span class="sxs-lookup"><span data-stu-id="51c80-166">Error</span></span></p></td>
<td><p><span data-ttu-id="51c80-167">끝점을 등록 하지 못함</span><span class="sxs-lookup"><span data-stu-id="51c80-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="51c80-168">끝점을 등록 하지 못함</span><span class="sxs-lookup"><span data-stu-id="51c80-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="51c80-169">문제가 계속 되 면 기술 지원 서비스에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="51c80-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51c80-170">20013</span><span class="sxs-lookup"><span data-stu-id="51c80-170">20013</span></span></p></td>
<td><p><span data-ttu-id="51c80-171">오류</span><span class="sxs-lookup"><span data-stu-id="51c80-171">Error</span></span></p></td>
<td><p><span data-ttu-id="51c80-172">IM MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="51c80-173">IM MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="51c80-174">IM MCU 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="51c80-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c80-175">20014</span><span class="sxs-lookup"><span data-stu-id="51c80-175">20014</span></span></p></td>
<td><p><span data-ttu-id="51c80-176">알림</span><span class="sxs-lookup"><span data-stu-id="51c80-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="51c80-177">메신저 대화에 연결 하지 못함 문제가 복구 됨</span><span class="sxs-lookup"><span data-stu-id="51c80-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="51c80-178">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51c80-179">20015</span><span class="sxs-lookup"><span data-stu-id="51c80-179">20015</span></span></p></td>
<td><p><span data-ttu-id="51c80-180">오류</span><span class="sxs-lookup"><span data-stu-id="51c80-180">Error</span></span></p></td>
<td><p><span data-ttu-id="51c80-181">AV MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="51c80-182">AV MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="51c80-183">AV MCU가 실행 중인지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="51c80-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c80-184">20016</span><span class="sxs-lookup"><span data-stu-id="51c80-184">20016</span></span></p></td>
<td><p><span data-ttu-id="51c80-185">알림</span><span class="sxs-lookup"><span data-stu-id="51c80-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="51c80-186">장애 조치 (failover)에서 AV MCU 연결에 실패 하 여 복구 됨</span><span class="sxs-lookup"><span data-stu-id="51c80-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="51c80-187">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51c80-188">20017</span><span class="sxs-lookup"><span data-stu-id="51c80-188">20017</span></span></p></td>
<td><p><span data-ttu-id="51c80-189">오류</span><span class="sxs-lookup"><span data-stu-id="51c80-189">Error</span></span></p></td>
<td><p><span data-ttu-id="51c80-190">MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="51c80-191">MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="51c80-192">MCU가 실행 되 고 있는지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="51c80-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c80-193">20018</span><span class="sxs-lookup"><span data-stu-id="51c80-193">20018</span></span></p></td>
<td><p><span data-ttu-id="51c80-194">알림</span><span class="sxs-lookup"><span data-stu-id="51c80-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="51c80-195">MCU로의 연결 실패 로부터 복구 됨</span><span class="sxs-lookup"><span data-stu-id="51c80-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="51c80-196">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51c80-197">20019</span><span class="sxs-lookup"><span data-stu-id="51c80-197">20019</span></span></p></td>
<td><p><span data-ttu-id="51c80-198">오류</span><span class="sxs-lookup"><span data-stu-id="51c80-198">Error</span></span></p></td>
<td><p><span data-ttu-id="51c80-199">데이터 MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="51c80-200">데이터 MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="51c80-201">데이터 MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="51c80-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c80-202">20020</span><span class="sxs-lookup"><span data-stu-id="51c80-202">20020</span></span></p></td>
<td><p><span data-ttu-id="51c80-203">알림</span><span class="sxs-lookup"><span data-stu-id="51c80-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="51c80-204">데이터 MCU 연결에 실패 하 여 복구 됨</span><span class="sxs-lookup"><span data-stu-id="51c80-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="51c80-205">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51c80-206">20021</span><span class="sxs-lookup"><span data-stu-id="51c80-206">20021</span></span></p></td>
<td><p><span data-ttu-id="51c80-207">오류</span><span class="sxs-lookup"><span data-stu-id="51c80-207">Error</span></span></p></td>
<td><p><span data-ttu-id="51c80-208">IM MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="51c80-209">IM MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="51c80-210">IM MCU 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="51c80-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c80-211">20022</span><span class="sxs-lookup"><span data-stu-id="51c80-211">20022</span></span></p></td>
<td><p><span data-ttu-id="51c80-212">오류</span><span class="sxs-lookup"><span data-stu-id="51c80-212">Error</span></span></p></td>
<td><p><span data-ttu-id="51c80-213">AV MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="51c80-214">AV MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="51c80-215">AV MCU가 실행 중인지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="51c80-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51c80-216">20023</span><span class="sxs-lookup"><span data-stu-id="51c80-216">20023</span></span></p></td>
<td><p><span data-ttu-id="51c80-217">오류</span><span class="sxs-lookup"><span data-stu-id="51c80-217">Error</span></span></p></td>
<td><p><span data-ttu-id="51c80-218">MCU로 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="51c80-219">MCU로 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="51c80-220">MCU가 실행 되 고 있는지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="51c80-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c80-221">20024</span><span class="sxs-lookup"><span data-stu-id="51c80-221">20024</span></span></p></td>
<td><p><span data-ttu-id="51c80-222">오류</span><span class="sxs-lookup"><span data-stu-id="51c80-222">Error</span></span></p></td>
<td><p><span data-ttu-id="51c80-223">데이터 MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="51c80-224">데이터 MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="51c80-225">데이터 MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="51c80-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51c80-226">20025</span><span class="sxs-lookup"><span data-stu-id="51c80-226">20025</span></span></p></td>
<td><p><span data-ttu-id="51c80-227">오류</span><span class="sxs-lookup"><span data-stu-id="51c80-227">Error</span></span></p></td>
<td><p><span data-ttu-id="51c80-228">사진에 대 한 active directory에 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="51c80-229">Active directory에 대 한 연결을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="51c80-230">Active directory에 대 한 연결을 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="51c80-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51c80-231">20026</span><span class="sxs-lookup"><span data-stu-id="51c80-231">20026</span></span></p></td>
<td><p><span data-ttu-id="51c80-232">알림</span><span class="sxs-lookup"><span data-stu-id="51c80-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="51c80-233">사진에 대 한 active directory 액세스 실패에서 복구 됨</span><span class="sxs-lookup"><span data-stu-id="51c80-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="51c80-234">해당 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51c80-235">20027</span><span class="sxs-lookup"><span data-stu-id="51c80-235">20027</span></span></p></td>
<td><p><span data-ttu-id="51c80-236">경고</span><span class="sxs-lookup"><span data-stu-id="51c80-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="51c80-237">역직렬화 할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="51c80-238">역직렬화 할 수 없음</span><span class="sxs-lookup"><span data-stu-id="51c80-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="51c80-239">문제가 계속 되 면 기술 지원 서비스에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="51c80-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

