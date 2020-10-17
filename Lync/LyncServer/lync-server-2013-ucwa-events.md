---
title: 'Lync Server 2013: c (WA) 이벤트'
description: 'Lync Server 2013: c-WA 이벤트'
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
ms.openlocfilehash: 8104ce9c7533350f40ce194e1cde205bc3692792
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548854"
---
# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="d5a0a-103">Lync Server 2013의 c/WA 이벤트</span><span class="sxs-lookup"><span data-stu-id="d5a0a-103">UCWA events in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5a0a-104">_**마지막으로 수정 된 항목:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="d5a0a-104">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="d5a0a-105">Lync Server 2013에서는 Microsoft Exchange에 액세스 하 여 모바일 클라이언트의 현재 상태를 업데이트 하는 데 필요한 다양 한 목적으로 통합 커뮤니케이션 웹 API (c)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-105">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="d5a0a-106">C u r c c r 12에서는 작업 동작 기록을 이벤트 유형 정보, 경고 및 오류로 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-106">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="d5a0a-107">다음 표에서는 c-WA 구성 요소에서 작성할 수 있는 이벤트에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-107">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5a0a-108">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="d5a0a-108">Event ID</span></span></th>
<th><span data-ttu-id="d5a0a-109">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="d5a0a-109">Event Type</span></span></th>
<th><span data-ttu-id="d5a0a-110">요약</span><span class="sxs-lookup"><span data-stu-id="d5a0a-110">Summary</span></span></th>
<th><span data-ttu-id="d5a0a-111">원인 및 해결 방법</span><span class="sxs-lookup"><span data-stu-id="d5a0a-111">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5a0a-112">20001</span><span class="sxs-lookup"><span data-stu-id="d5a0a-112">20001</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-113">알림</span><span class="sxs-lookup"><span data-stu-id="d5a0a-113">Informational</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-114">과 (와) 초기화 됨</span><span class="sxs-lookup"><span data-stu-id="d5a0a-114">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-115">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-115">N/A</span></span></p>
<p><span data-ttu-id="d5a0a-116">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-116">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5a0a-117">20002</span><span class="sxs-lookup"><span data-stu-id="d5a0a-117">20002</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-118">오류</span><span class="sxs-lookup"><span data-stu-id="d5a0a-118">Error</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-119">초기화 하는 동안 c #에서 예기치 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-119">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-120">초기화 하는 동안 예기치 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-120">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="d5a0a-121">관련 된 이벤트 로그 항목에서 예외 정보를 검사 하 여 가능한 원인을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-121">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5a0a-122">20003</span><span class="sxs-lookup"><span data-stu-id="d5a0a-122">20003</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-123">오류</span><span class="sxs-lookup"><span data-stu-id="d5a0a-123">Error</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-124">(C)에서 처리 되지 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-124">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-125">처리 되지 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-125">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="d5a0a-126">서버를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-126">Restart the server.</span></span> <span data-ttu-id="d5a0a-127">문제가 계속 되 면 기술 지원 서비스에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-127">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5a0a-128">20004</span><span class="sxs-lookup"><span data-stu-id="d5a0a-128">20004</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-129">오류</span><span class="sxs-lookup"><span data-stu-id="d5a0a-129">Error</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-130">HD photo에 대 한 Exchange에 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-130">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-131">Exchange에 대 한 연결을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-131">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="d5a0a-132">Exchange에 대 한 연결을 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="d5a0a-132">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5a0a-133">20005</span><span class="sxs-lookup"><span data-stu-id="d5a0a-133">20005</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-134">알림</span><span class="sxs-lookup"><span data-stu-id="d5a0a-134">Informational</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-135">HD photo에 대 한 Exchange 액세스 실패에서 복구 됨</span><span class="sxs-lookup"><span data-stu-id="d5a0a-135">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-136">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-136">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5a0a-137">20006</span><span class="sxs-lookup"><span data-stu-id="d5a0a-137">20006</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-138">오류</span><span class="sxs-lookup"><span data-stu-id="d5a0a-138">Error</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-139">Exchange에 연락처 검색을 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-139">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-140">Exchange에 대 한 연결을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-140">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="d5a0a-141">Exchange에 대 한 연결을 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="d5a0a-141">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5a0a-142">20007</span><span class="sxs-lookup"><span data-stu-id="d5a0a-142">20007</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-143">알림</span><span class="sxs-lookup"><span data-stu-id="d5a0a-143">Informational</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-144">Exchange에서 실패 한 대화 상대 로부터 복구 됨</span><span class="sxs-lookup"><span data-stu-id="d5a0a-144">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-145">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-145">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5a0a-146">20008</span><span class="sxs-lookup"><span data-stu-id="d5a0a-146">20008</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-147">경고</span><span class="sxs-lookup"><span data-stu-id="d5a0a-147">Warning</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-148">응용 프로그램당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-149">응용 프로그램당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-149">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="d5a0a-150">클라이언트에서 불필요 한 구독 확인</span><span class="sxs-lookup"><span data-stu-id="d5a0a-150">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5a0a-151">20009</span><span class="sxs-lookup"><span data-stu-id="d5a0a-151">20009</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-152">경고</span><span class="sxs-lookup"><span data-stu-id="d5a0a-152">Warning</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-153">일괄 처리당 허용 되는 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-154">일괄 처리당 허용 되는 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-154">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="d5a0a-155">클라이언트에서 불필요 한 구독 확인</span><span class="sxs-lookup"><span data-stu-id="d5a0a-155">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5a0a-156">20010</span><span class="sxs-lookup"><span data-stu-id="d5a0a-156">20010</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-157">오류</span><span class="sxs-lookup"><span data-stu-id="d5a0a-157">Error</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-158">인밴드 데이터를 검색할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-158">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-159">인밴드 데이터를 검색할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-159">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="d5a0a-160">문제가 계속 되 면 기술 지원 서비스에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-160">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5a0a-161">20011</span><span class="sxs-lookup"><span data-stu-id="d5a0a-161">20011</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-162">오류</span><span class="sxs-lookup"><span data-stu-id="d5a0a-162">Error</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-163">현재 상태 구독 불가능</span><span class="sxs-lookup"><span data-stu-id="d5a0a-163">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-164">현재 상태 구독 불가능</span><span class="sxs-lookup"><span data-stu-id="d5a0a-164">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="d5a0a-165">문제가 계속 되 면 기술 지원 서비스에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-165">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5a0a-166">20012</span><span class="sxs-lookup"><span data-stu-id="d5a0a-166">20012</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-167">오류</span><span class="sxs-lookup"><span data-stu-id="d5a0a-167">Error</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-168">끝점을 등록 하지 못함</span><span class="sxs-lookup"><span data-stu-id="d5a0a-168">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-169">끝점을 등록 하지 못함</span><span class="sxs-lookup"><span data-stu-id="d5a0a-169">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="d5a0a-170">문제가 계속 되 면 기술 지원 서비스에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-170">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5a0a-171">20013</span><span class="sxs-lookup"><span data-stu-id="d5a0a-171">20013</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-172">오류</span><span class="sxs-lookup"><span data-stu-id="d5a0a-172">Error</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-173">IM MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-173">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-174">IM MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-174">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="d5a0a-175">IM MCU 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="d5a0a-175">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5a0a-176">20014</span><span class="sxs-lookup"><span data-stu-id="d5a0a-176">20014</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-177">알림</span><span class="sxs-lookup"><span data-stu-id="d5a0a-177">Informational</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-178">메신저 대화에 연결 하지 못함 문제가 복구 됨</span><span class="sxs-lookup"><span data-stu-id="d5a0a-178">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-179">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-179">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5a0a-180">20015</span><span class="sxs-lookup"><span data-stu-id="d5a0a-180">20015</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-181">오류</span><span class="sxs-lookup"><span data-stu-id="d5a0a-181">Error</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-182">AV MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-182">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-183">AV MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-183">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="d5a0a-184">AV MCU가 실행 중인지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="d5a0a-184">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5a0a-185">20016</span><span class="sxs-lookup"><span data-stu-id="d5a0a-185">20016</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-186">알림</span><span class="sxs-lookup"><span data-stu-id="d5a0a-186">Informational</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-187">장애 조치 (failover)에서 AV MCU 연결에 실패 하 여 복구 됨</span><span class="sxs-lookup"><span data-stu-id="d5a0a-187">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-188">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-188">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5a0a-189">20017</span><span class="sxs-lookup"><span data-stu-id="d5a0a-189">20017</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-190">오류</span><span class="sxs-lookup"><span data-stu-id="d5a0a-190">Error</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-191">MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-191">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-192">MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-192">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="d5a0a-193">MCU가 실행 되 고 있는지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="d5a0a-193">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5a0a-194">20018</span><span class="sxs-lookup"><span data-stu-id="d5a0a-194">20018</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-195">알림</span><span class="sxs-lookup"><span data-stu-id="d5a0a-195">Informational</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-196">MCU로의 연결 실패 로부터 복구 됨</span><span class="sxs-lookup"><span data-stu-id="d5a0a-196">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-197">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-197">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5a0a-198">20019</span><span class="sxs-lookup"><span data-stu-id="d5a0a-198">20019</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-199">오류</span><span class="sxs-lookup"><span data-stu-id="d5a0a-199">Error</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-200">데이터 MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-200">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-201">데이터 MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-201">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="d5a0a-202">데이터 MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="d5a0a-202">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5a0a-203">20020</span><span class="sxs-lookup"><span data-stu-id="d5a0a-203">20020</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-204">알림</span><span class="sxs-lookup"><span data-stu-id="d5a0a-204">Informational</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-205">데이터 MCU 연결에 실패 하 여 복구 됨</span><span class="sxs-lookup"><span data-stu-id="d5a0a-205">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-206">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-206">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5a0a-207">20021</span><span class="sxs-lookup"><span data-stu-id="d5a0a-207">20021</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-208">오류</span><span class="sxs-lookup"><span data-stu-id="d5a0a-208">Error</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-209">IM MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-209">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-210">IM MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-210">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="d5a0a-211">IM MCU 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="d5a0a-211">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5a0a-212">20022</span><span class="sxs-lookup"><span data-stu-id="d5a0a-212">20022</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-213">오류</span><span class="sxs-lookup"><span data-stu-id="d5a0a-213">Error</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-214">AV MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-214">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-215">AV MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-215">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="d5a0a-216">AV MCU가 실행 중인지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="d5a0a-216">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5a0a-217">20023</span><span class="sxs-lookup"><span data-stu-id="d5a0a-217">20023</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-218">오류</span><span class="sxs-lookup"><span data-stu-id="d5a0a-218">Error</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-219">MCU로 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-219">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-220">MCU로 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-220">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="d5a0a-221">MCU가 실행 되 고 있는지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="d5a0a-221">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5a0a-222">20024</span><span class="sxs-lookup"><span data-stu-id="d5a0a-222">20024</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-223">오류</span><span class="sxs-lookup"><span data-stu-id="d5a0a-223">Error</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-224">데이터 MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-224">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-225">데이터 MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-225">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="d5a0a-226">데이터 MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="d5a0a-226">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5a0a-227">20025</span><span class="sxs-lookup"><span data-stu-id="d5a0a-227">20025</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-228">오류</span><span class="sxs-lookup"><span data-stu-id="d5a0a-228">Error</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-229">사진에 대 한 active directory에 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-229">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-230">Active directory에 대 한 연결을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-230">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="d5a0a-231">Active directory에 대 한 연결을 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="d5a0a-231">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5a0a-232">20026</span><span class="sxs-lookup"><span data-stu-id="d5a0a-232">20026</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-233">알림</span><span class="sxs-lookup"><span data-stu-id="d5a0a-233">Informational</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-234">사진에 대 한 active directory 액세스 실패에서 복구 됨</span><span class="sxs-lookup"><span data-stu-id="d5a0a-234">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-235">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-235">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5a0a-236">20027</span><span class="sxs-lookup"><span data-stu-id="d5a0a-236">20027</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-237">경고</span><span class="sxs-lookup"><span data-stu-id="d5a0a-237">Warning</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-238">역직렬화 할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-238">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="d5a0a-239">역직렬화 할 수 없음</span><span class="sxs-lookup"><span data-stu-id="d5a0a-239">Cannot deserialize</span></span></p>
<p><span data-ttu-id="d5a0a-240">문제가 계속 되 면 기술 지원 서비스에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d5a0a-240">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

