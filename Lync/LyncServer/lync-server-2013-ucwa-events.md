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
ms.openlocfilehash: 4d42dbd967f90b6e2a905b92558c88fe52ef62d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="8ee6e-102">Lync Server 2013의 c/WA 이벤트</span><span class="sxs-lookup"><span data-stu-id="8ee6e-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ee6e-103">_**마지막으로 수정 된 항목:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="8ee6e-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="8ee6e-104">Lync Server 2013에서는 Microsoft Exchange에 액세스 하 여 모바일 클라이언트의 현재 상태를 업데이트 하는 데 필요한 다양 한 목적으로 통합 커뮤니케이션 웹 API (c)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="8ee6e-105">C u r c c r 12에서는 작업 동작 기록을 이벤트 유형 정보, 경고 및 오류로 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="8ee6e-106">다음 표에서는 c-WA 구성 요소에서 작성할 수 있는 이벤트에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ee6e-107">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="8ee6e-107">Event ID</span></span></th>
<th><span data-ttu-id="8ee6e-108">이벤트 유형</span><span class="sxs-lookup"><span data-stu-id="8ee6e-108">Event Type</span></span></th>
<th><span data-ttu-id="8ee6e-109">요약</span><span class="sxs-lookup"><span data-stu-id="8ee6e-109">Summary</span></span></th>
<th><span data-ttu-id="8ee6e-110">원인 및 해결 방법</span><span class="sxs-lookup"><span data-stu-id="8ee6e-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ee6e-111">20001</span><span class="sxs-lookup"><span data-stu-id="8ee6e-111">20001</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-112">알림</span><span class="sxs-lookup"><span data-stu-id="8ee6e-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-113">과 (와) 초기화 됨</span><span class="sxs-lookup"><span data-stu-id="8ee6e-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-114">해당 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-114">N/A</span></span></p>
<p><span data-ttu-id="8ee6e-115">해당 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee6e-116">20002</span><span class="sxs-lookup"><span data-stu-id="8ee6e-116">20002</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-117">오류</span><span class="sxs-lookup"><span data-stu-id="8ee6e-117">Error</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-118">초기화 하는 동안 c #에서 예기치 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-119">초기화 하는 동안 예기치 않은 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="8ee6e-120">관련 된 이벤트 로그 항목에서 예외 정보를 검사 하 여 가능한 원인을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee6e-121">20003</span><span class="sxs-lookup"><span data-stu-id="8ee6e-121">20003</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-122">오류</span><span class="sxs-lookup"><span data-stu-id="8ee6e-122">Error</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-123">(C)에서 처리 되지 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-124">처리 되지 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="8ee6e-125">서버를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-125">Restart the server.</span></span> <span data-ttu-id="8ee6e-126">문제가 계속 되 면 기술 지원 서비스에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee6e-127">20004</span><span class="sxs-lookup"><span data-stu-id="8ee6e-127">20004</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-128">오류</span><span class="sxs-lookup"><span data-stu-id="8ee6e-128">Error</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-129">HD photo에 대 한 Exchange에 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-130">Exchange에 대 한 연결을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="8ee6e-131">Exchange에 대 한 연결을 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="8ee6e-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee6e-132">20005</span><span class="sxs-lookup"><span data-stu-id="8ee6e-132">20005</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-133">알림</span><span class="sxs-lookup"><span data-stu-id="8ee6e-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-134">HD photo에 대 한 Exchange 액세스 실패에서 복구 됨</span><span class="sxs-lookup"><span data-stu-id="8ee6e-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-135">해당 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee6e-136">20006</span><span class="sxs-lookup"><span data-stu-id="8ee6e-136">20006</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-137">오류</span><span class="sxs-lookup"><span data-stu-id="8ee6e-137">Error</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-138">Exchange에 연락처 검색을 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-139">Exchange에 대 한 연결을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="8ee6e-140">Exchange에 대 한 연결을 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="8ee6e-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee6e-141">20007</span><span class="sxs-lookup"><span data-stu-id="8ee6e-141">20007</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-142">알림</span><span class="sxs-lookup"><span data-stu-id="8ee6e-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-143">Exchange에서 실패 한 대화 상대 로부터 복구 됨</span><span class="sxs-lookup"><span data-stu-id="8ee6e-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-144">해당 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee6e-145">20008</span><span class="sxs-lookup"><span data-stu-id="8ee6e-145">20008</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-146">경고</span><span class="sxs-lookup"><span data-stu-id="8ee6e-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-147">응용 프로그램당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-148">응용 프로그램당 허용 된 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="8ee6e-149">클라이언트에서 불필요 한 구독 확인</span><span class="sxs-lookup"><span data-stu-id="8ee6e-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee6e-150">20009</span><span class="sxs-lookup"><span data-stu-id="8ee6e-150">20009</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-151">경고</span><span class="sxs-lookup"><span data-stu-id="8ee6e-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-152">일괄 처리당 허용 되는 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-153">일괄 처리당 허용 되는 현재 상태 구독 보다 더 많은 구독을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="8ee6e-154">클라이언트에서 불필요 한 구독 확인</span><span class="sxs-lookup"><span data-stu-id="8ee6e-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee6e-155">20010</span><span class="sxs-lookup"><span data-stu-id="8ee6e-155">20010</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-156">오류</span><span class="sxs-lookup"><span data-stu-id="8ee6e-156">Error</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-157">인밴드 데이터를 검색할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-158">인밴드 데이터를 검색할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="8ee6e-159">문제가 계속 되 면 기술 지원 서비스에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee6e-160">20011</span><span class="sxs-lookup"><span data-stu-id="8ee6e-160">20011</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-161">오류</span><span class="sxs-lookup"><span data-stu-id="8ee6e-161">Error</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-162">현재 상태 구독 불가능</span><span class="sxs-lookup"><span data-stu-id="8ee6e-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-163">현재 상태 구독 불가능</span><span class="sxs-lookup"><span data-stu-id="8ee6e-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="8ee6e-164">문제가 계속 되 면 기술 지원 서비스에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee6e-165">20012</span><span class="sxs-lookup"><span data-stu-id="8ee6e-165">20012</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-166">오류</span><span class="sxs-lookup"><span data-stu-id="8ee6e-166">Error</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-167">끝점을 등록 하지 못함</span><span class="sxs-lookup"><span data-stu-id="8ee6e-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-168">끝점을 등록 하지 못함</span><span class="sxs-lookup"><span data-stu-id="8ee6e-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="8ee6e-169">문제가 계속 되 면 기술 지원 서비스에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee6e-170">20013</span><span class="sxs-lookup"><span data-stu-id="8ee6e-170">20013</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-171">오류</span><span class="sxs-lookup"><span data-stu-id="8ee6e-171">Error</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-172">IM MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-173">IM MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="8ee6e-174">IM MCU 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="8ee6e-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee6e-175">20014</span><span class="sxs-lookup"><span data-stu-id="8ee6e-175">20014</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-176">알림</span><span class="sxs-lookup"><span data-stu-id="8ee6e-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-177">메신저 대화에 연결 하지 못함 문제가 복구 됨</span><span class="sxs-lookup"><span data-stu-id="8ee6e-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-178">해당 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee6e-179">20015</span><span class="sxs-lookup"><span data-stu-id="8ee6e-179">20015</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-180">오류</span><span class="sxs-lookup"><span data-stu-id="8ee6e-180">Error</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-181">AV MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-182">AV MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="8ee6e-183">AV MCU가 실행 중인지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="8ee6e-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee6e-184">20016</span><span class="sxs-lookup"><span data-stu-id="8ee6e-184">20016</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-185">알림</span><span class="sxs-lookup"><span data-stu-id="8ee6e-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-186">장애 조치 (failover)에서 AV MCU 연결에 실패 하 여 복구 됨</span><span class="sxs-lookup"><span data-stu-id="8ee6e-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-187">해당 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee6e-188">20017</span><span class="sxs-lookup"><span data-stu-id="8ee6e-188">20017</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-189">오류</span><span class="sxs-lookup"><span data-stu-id="8ee6e-189">Error</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-190">MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-191">MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="8ee6e-192">MCU가 실행 되 고 있는지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="8ee6e-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee6e-193">20018</span><span class="sxs-lookup"><span data-stu-id="8ee6e-193">20018</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-194">알림</span><span class="sxs-lookup"><span data-stu-id="8ee6e-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-195">MCU로의 연결 실패 로부터 복구 됨</span><span class="sxs-lookup"><span data-stu-id="8ee6e-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-196">해당 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee6e-197">20019</span><span class="sxs-lookup"><span data-stu-id="8ee6e-197">20019</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-198">오류</span><span class="sxs-lookup"><span data-stu-id="8ee6e-198">Error</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-199">데이터 MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-200">데이터 MCU를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="8ee6e-201">데이터 MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="8ee6e-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee6e-202">20020</span><span class="sxs-lookup"><span data-stu-id="8ee6e-202">20020</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-203">알림</span><span class="sxs-lookup"><span data-stu-id="8ee6e-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-204">데이터 MCU 연결에 실패 하 여 복구 됨</span><span class="sxs-lookup"><span data-stu-id="8ee6e-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-205">해당 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee6e-206">20021</span><span class="sxs-lookup"><span data-stu-id="8ee6e-206">20021</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-207">오류</span><span class="sxs-lookup"><span data-stu-id="8ee6e-207">Error</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-208">IM MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-209">IM MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="8ee6e-210">IM MCU 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="8ee6e-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee6e-211">20022</span><span class="sxs-lookup"><span data-stu-id="8ee6e-211">20022</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-212">오류</span><span class="sxs-lookup"><span data-stu-id="8ee6e-212">Error</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-213">AV MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-214">AV MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="8ee6e-215">AV MCU가 실행 중인지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="8ee6e-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee6e-216">20023</span><span class="sxs-lookup"><span data-stu-id="8ee6e-216">20023</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-217">오류</span><span class="sxs-lookup"><span data-stu-id="8ee6e-217">Error</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-218">MCU로 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-219">MCU로 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="8ee6e-220">MCU가 실행 되 고 있는지 여부 확인</span><span class="sxs-lookup"><span data-stu-id="8ee6e-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee6e-221">20024</span><span class="sxs-lookup"><span data-stu-id="8ee6e-221">20024</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-222">오류</span><span class="sxs-lookup"><span data-stu-id="8ee6e-222">Error</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-223">데이터 MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-224">데이터 MCU에 참가할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="8ee6e-225">데이터 MCU가 실행 중인지 확인</span><span class="sxs-lookup"><span data-stu-id="8ee6e-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee6e-226">20025</span><span class="sxs-lookup"><span data-stu-id="8ee6e-226">20025</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-227">오류</span><span class="sxs-lookup"><span data-stu-id="8ee6e-227">Error</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-228">사진에 대 한 active directory에 액세스할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-229">Active directory에 대 한 연결을 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="8ee6e-230">Active directory에 대 한 연결을 사용할 수 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="8ee6e-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee6e-231">20026</span><span class="sxs-lookup"><span data-stu-id="8ee6e-231">20026</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-232">알림</span><span class="sxs-lookup"><span data-stu-id="8ee6e-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-233">사진에 대 한 active directory 액세스 실패에서 복구 됨</span><span class="sxs-lookup"><span data-stu-id="8ee6e-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-234">해당 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee6e-235">20027</span><span class="sxs-lookup"><span data-stu-id="8ee6e-235">20027</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-236">경고</span><span class="sxs-lookup"><span data-stu-id="8ee6e-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-237">역직렬화 할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="8ee6e-238">역직렬화 할 수 없음</span><span class="sxs-lookup"><span data-stu-id="8ee6e-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="8ee6e-239">문제가 계속 되 면 기술 지원 서비스에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ee6e-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

