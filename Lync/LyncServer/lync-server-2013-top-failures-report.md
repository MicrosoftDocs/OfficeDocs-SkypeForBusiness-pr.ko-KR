---
title: 'Lync Server 2013: 주요 오류 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 094f5034951e20d48b05c8772698ae2983492509
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a><span data-ttu-id="96ebd-102">Lync Server 2013의 상위 오류 보고서</span><span class="sxs-lookup"><span data-stu-id="96ebd-102">Top Failures Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96ebd-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="96ebd-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="96ebd-104">상위 오류 보고서에서는 가장 일반적으로 보고 되는 오류와 시간에 따른 추세를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-104">The Top Failures Report provides a look at the most-commonly reported failures and their trends over time.</span></span> <span data-ttu-id="96ebd-105">실패는 다음 두 메트릭의 조합에 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-105">Failures are based on a combination of the following two metrics:</span></span>

  - <span data-ttu-id="96ebd-106">**진단 ID**입니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-106">**Diagnostic ID**.</span></span> <span data-ttu-id="96ebd-107">SIP 메시지에 첨부 되는 고유 식별자 (ms-진단 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-107">Unique identifier (in the form of an ms-diagnostics header) that is attached to a SIP message.</span></span> <span data-ttu-id="96ebd-108">진단 Id는 통화 관련 문제를 해결 하는 데 유용한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-108">Diagnostic IDs provide information useful in troubleshooting call-related problems.</span></span>

  - <span data-ttu-id="96ebd-109">**응답 코드**.</span><span class="sxs-lookup"><span data-stu-id="96ebd-109">**Response code**.</span></span> <span data-ttu-id="96ebd-110">응답 코드는 sip 통신 세션에서 SIP 요청에 응답 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-110">Response codes are used in SIP communication sessions to respond to SIP requests.</span></span> <span data-ttu-id="96ebd-111">예를 들어: 진구에서 Pilar Ackerman로 초대 요청을 보내는 경우 (즉,: 진구 Myer 호출 Pilar Ackerman가 있다고 가정 합니다.)</span><span class="sxs-lookup"><span data-stu-id="96ebd-111">For example, suppose Ken sends the INVITE request to Pilar Ackerman (that is, suppose Ken Myer calls Pilar Ackerman).</span></span> <span data-ttu-id="96ebd-112">Pilar 경우 휴대폰에서 응답 코드 200 (OK)를 보내: 진구 님이 Pilar에 게 응답 했음을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-112">If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered.</span></span> <span data-ttu-id="96ebd-113">상위 오류 보고서에는 호출 실패에 대 한 응답으로 보낸 응답 코드만 포함 됩니다. Lync Server는 통화 도중에 발급 된 모든 응답 코드를 추적 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-113">The Top Failures Report only includes response codes that were sent in response to a call failure; Lync Server does not keep track of all the response codes issued during the course of a call.</span></span>

<span data-ttu-id="96ebd-114">이러한 정보는 오류가 발생 한 총 세션 수에 대해서는 보고 되지 않으며, 실패의 영향을 받은 총 사용자의 수에도 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-114">Information is reported not only for the total number of sessions where a failure occurred but also for the total number of users who were impacted by the failure.</span></span>

<div>

## <a name="accessing-the-top-failures-report"></a><span data-ttu-id="96ebd-115">상위 오류 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="96ebd-115">Accessing the Top Failures Report</span></span>

<span data-ttu-id="96ebd-116">상위 오류 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-116">The Top Failures Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="96ebd-117">보고 된 세션 메트릭을 클릭 하면 [Lync Server 2013의 실패 분포 보고서](lync-server-2013-failure-distribution-report.md)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-117">Clicking the Reported sessions metric will take you to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a><span data-ttu-id="96ebd-118">상위 오류 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="96ebd-118">Making the Best Use of the Top Failures Report</span></span>

<span data-ttu-id="96ebd-119">상위 오류 보고서는 매우 중요 한 것으로, 한 번에 최대 5 개의 진단 Id를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-119">The Top Failures Report is unusual in one regard: it allows you to filter on as many as 5 diagnostic IDs at once.</span></span> <span data-ttu-id="96ebd-120">(일반적으로 한 번에 하나의 사용자 SIP 주소와 같이 한 항목 에서만 필터링 할 수 있습니다.) 여러 진단 Id를 필터링 하려면 각 ID를 쉼표로 구분 하 여 진단 Id 상자에 입력 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-120">(Typically you can only filter on one item – such as one user SIP address – at a time.) To filter on multiple diagnostic IDs, simply enter each ID in the Diagnostic IDs box, separating the IDs by using commas.</span></span> <span data-ttu-id="96ebd-121">(원하는 경우 각 쉼표 뒤에 공백을 남길 수 있습니다.) 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="96ebd-121">(If you want to, you can leave a blank space after each comma.) For example:</span></span>

<span data-ttu-id="96ebd-122">1011, 2412, 1033, 52116, 1008</span><span class="sxs-lookup"><span data-stu-id="96ebd-122">1011, 2412, 1033, 52116, 1008</span></span>

<span data-ttu-id="96ebd-123">이 작업을 수행 하면 해당 다섯 가지 진단 Id 중 하나 이상을 보고 한 실패 한 호출만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-123">Do that, and only failed calls that reported at least one of those five diagnostic IDs will be displayed.</span></span>

<span data-ttu-id="96ebd-124">마우스를 응답 코드 위에 두면 질문에 대 한 응답 코드의 의미를 알려 주는 도구 설명이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-124">If you hold your mouse over a Response code you'll see a tooltip that tells you what the Response code in question means.</span></span> <span data-ttu-id="96ebd-125">예를 들어 응답 코드 486 위에 마우스를 놓으면 다음 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-125">For example, if you hold the mouse over the Response code 486 you'll see this message:</span></span>

<span data-ttu-id="96ebd-126">여기에서 통화 중입니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-126">Busy Here.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="96ebd-127">필터가</span><span class="sxs-lookup"><span data-stu-id="96ebd-127">Filters</span></span>

<span data-ttu-id="96ebd-128">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-128">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="96ebd-129">예를 들어 상위 오류 보고서를 사용 하 여 반환 된 데이터를 활동 유형 (피어 투 피어 세션 또는 회의 세션) 또는 실패 한 세션과 함께 제공 되는 SIP 응답 코드에 따라 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-129">For example, the Top Failures Report enables you to filter the returned data based on such things as the activity type (peer-to-peer session or conferencing session) or by the SIP response code that accompanied the failed session.</span></span> <span data-ttu-id="96ebd-130">데이터 그룹화 방법을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-130">You can also choose how data should be grouped.</span></span> <span data-ttu-id="96ebd-131">이 경우 사용량은 시간, 일, 주 또는 월로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-131">In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="96ebd-132">다음 표에는 상위 오류 보고서에 사용할 수 있는 필터가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-132">The following table lists the filters that you can use with the Top Failures Report.</span></span>

### <a name="top-failures-report-filters"></a><span data-ttu-id="96ebd-133">상위 오류 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="96ebd-133">Top Failures Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96ebd-134">이름</span><span class="sxs-lookup"><span data-stu-id="96ebd-134">Name</span></span></th>
<th><span data-ttu-id="96ebd-135">설명</span><span class="sxs-lookup"><span data-stu-id="96ebd-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96ebd-136"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="96ebd-136"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="96ebd-137">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-137">Start date/time for the time range.</span></span> <span data-ttu-id="96ebd-138">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-138">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="96ebd-139">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="96ebd-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="96ebd-140">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-140">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="96ebd-141">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-141">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="96ebd-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="96ebd-142">7/7/2012</span></span></p>
<p><span data-ttu-id="96ebd-143">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="96ebd-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="96ebd-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="96ebd-144">7/3/2012</span></span></p>
<p><span data-ttu-id="96ebd-145">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96ebd-146"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="96ebd-146"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="96ebd-147">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-147">End date/time for the time range.</span></span> <span data-ttu-id="96ebd-148">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-148">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="96ebd-149">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="96ebd-149">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="96ebd-150">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-150">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="96ebd-151">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-151">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="96ebd-152">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="96ebd-152">7/7/2012</span></span></p>
<p><span data-ttu-id="96ebd-153">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="96ebd-153">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="96ebd-154">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="96ebd-154">7/3/2012</span></span></p>
<p><span data-ttu-id="96ebd-155">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-155">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96ebd-156"><strong>활동 유형</strong></span><span class="sxs-lookup"><span data-stu-id="96ebd-156"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="96ebd-157">활동의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-157">Type of activity.</span></span> <span data-ttu-id="96ebd-158">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-158">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="96ebd-159">모든</span><span class="sxs-lookup"><span data-stu-id="96ebd-159">[All]</span></span></p></li>
<li><p><span data-ttu-id="96ebd-160">피어 투 피어</span><span class="sxs-lookup"><span data-stu-id="96ebd-160">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="96ebd-161">회의</span><span class="sxs-lookup"><span data-stu-id="96ebd-161">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96ebd-162"><strong>모달</strong></span><span class="sxs-lookup"><span data-stu-id="96ebd-162"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="96ebd-163">이번에는 <strong>[All]</strong>옵션만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-163">At this time the only option available is <strong>[All]</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96ebd-164"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="96ebd-164"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="96ebd-165">등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-165">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="96ebd-166">개별 풀을 선택 하거나 <strong>[모두]</strong> 를 클릭 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-166">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="96ebd-167">이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-167">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96ebd-168"><strong>범주만</strong></span><span class="sxs-lookup"><span data-stu-id="96ebd-168"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="96ebd-169">발생 한 오류 유형.</span><span class="sxs-lookup"><span data-stu-id="96ebd-169">Type of failure experienced.</span></span> <span data-ttu-id="96ebd-170">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-170">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="96ebd-171">예상 및 예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="96ebd-171">Both expected and unexpected failure</span></span></p></li>
<li><p><span data-ttu-id="96ebd-172">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="96ebd-172">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="96ebd-173">&quot;예상 되는&quot; 실패는 예상 되는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-173">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="96ebd-174">예를 들어 사용자가 자신의 상태를 방해 금지로 설정 하면 해당 사용자에 게 전화를 거는 데 실패 하는 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-174">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="96ebd-175">&quot;예기치 않은 오류가&quot; 발생 하는 것은 정상적인 시스템 때문 이라고 표시 되는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-175">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="96ebd-176">예를 들어 호출자가 대기 상태로 설정 된 경우에는 통화가 종료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-176">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="96ebd-177">이 문제가 발생 하면 예기치 않은 오류로 플래그가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-177">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96ebd-178"><strong>응답 코드</strong></span><span class="sxs-lookup"><span data-stu-id="96ebd-178"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="96ebd-179">회의에 실패 한 경우 SIP 응답 코드가 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-179">SIP response code sent when the conference failed.</span></span> <span data-ttu-id="96ebd-180">전체 응답 코드를 입력 합니다 (예:).</span><span class="sxs-lookup"><span data-stu-id="96ebd-180">Enter the entire response code For example:</span></span></p>
<p><span data-ttu-id="96ebd-181">400</span><span class="sxs-lookup"><span data-stu-id="96ebd-181">400</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96ebd-182"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="96ebd-182"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="96ebd-183">오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-183">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="96ebd-184">진단 헤더는 선택 사항으로,이 헤더를 포함 하지 않는 SIP 세션이 있을 수 있으며, 진단 Id는 일부 종류의 문제가 발생 하는 세션에 대해서만 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-184">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="96ebd-185">매트릭스</span><span class="sxs-lookup"><span data-stu-id="96ebd-185">Metrics</span></span>

<span data-ttu-id="96ebd-186">다음 표에는 상위 오류 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-186">The following table lists the information provided in the Top Failures Report.</span></span>

### <a name="top-failures-report-metrics"></a><span data-ttu-id="96ebd-187">상위 오류 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="96ebd-187">Top Failures Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96ebd-188">이름</span><span class="sxs-lookup"><span data-stu-id="96ebd-188">Name</span></span></th>
<th><span data-ttu-id="96ebd-189">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="96ebd-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="96ebd-190">설명</span><span class="sxs-lookup"><span data-stu-id="96ebd-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96ebd-191"><strong>순위</strong></span><span class="sxs-lookup"><span data-stu-id="96ebd-191"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="96ebd-192">예</span><span class="sxs-lookup"><span data-stu-id="96ebd-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="96ebd-193">보고 된 세션의 수를 기준으로 상대 순위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-193">Relative rank based on the number of reported sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96ebd-194"><strong>보고 된 세션</strong></span><span class="sxs-lookup"><span data-stu-id="96ebd-194"><strong>Reported sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="96ebd-195">예</span><span class="sxs-lookup"><span data-stu-id="96ebd-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="96ebd-196">진단 ID 및 SIP 응답 코드에 따라 실패 한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-196">Total number of failed sessions based on diagnostic ID and SIP response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96ebd-197"><strong>사용자에 게 영향을 받음</strong></span><span class="sxs-lookup"><span data-stu-id="96ebd-197"><strong>Users impacted</strong></span></span></p></td>
<td><p><span data-ttu-id="96ebd-198">예</span><span class="sxs-lookup"><span data-stu-id="96ebd-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="96ebd-199">실패 한 세션의 영향을 받는 총 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-199">Total number of users affected by the failed session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96ebd-200"><strong>오류 정보</strong></span><span class="sxs-lookup"><span data-stu-id="96ebd-200"><strong>Failure information</strong></span></span></p></td>
<td><p><span data-ttu-id="96ebd-201">아니요</span><span class="sxs-lookup"><span data-stu-id="96ebd-201">No</span></span></p></td>
<td><p><span data-ttu-id="96ebd-202">진단 ID, SIP 응답 코드, 세션이 실패 한 이유에 대 한 설명 등 오류에 대 한 자세한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-202">Detailed information about the failure, including diagnostic ID, SIP response code, and description of why the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96ebd-203"><strong>과거 추세</strong></span><span class="sxs-lookup"><span data-stu-id="96ebd-203"><strong>Trend in the past</strong></span></span></p></td>
<td><p><span data-ttu-id="96ebd-204">아니요</span><span class="sxs-lookup"><span data-stu-id="96ebd-204">No</span></span></p></td>
<td><p><span data-ttu-id="96ebd-205">시간이 지남에 따라 실패 한 세션을 그래프로 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="96ebd-205">Graphs failed sessions over time.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

