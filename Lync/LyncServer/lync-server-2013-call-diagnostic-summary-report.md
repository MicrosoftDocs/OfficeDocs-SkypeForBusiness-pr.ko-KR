---
title: 'Lync Server 2013: 호출 진단 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e747d257e7c88973790e8fd0c9ba828949248598
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="e5398-102">Lync Server 2013의 호출 진단 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="e5398-102">Call Diagnostic Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5398-103">_**마지막으로 수정한 주제:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="e5398-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="e5398-104">전화 진단 요약 보고서는 실패 한 피어 투 피어 및 회의 세션의 전반적인 모습을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-104">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions.</span></span> <span data-ttu-id="e5398-105">이 보고서는 두 유형의 세션에 대 한 전체 오류율을 표시 하 고 오류 정보를 세션 형식으로 아래로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-105">The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="e5398-106">인스턴트 메시지</span><span class="sxs-lookup"><span data-stu-id="e5398-106">Instant messaging</span></span>

  - <span data-ttu-id="e5398-107">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="e5398-107">Application sharing</span></span>

  - <span data-ttu-id="e5398-108">파일 전송</span><span class="sxs-lookup"><span data-stu-id="e5398-108">File transfer</span></span>

  - <span data-ttu-id="e5398-109">오디오</span><span class="sxs-lookup"><span data-stu-id="e5398-109">Audio</span></span>

  - <span data-ttu-id="e5398-110">비디오만</span><span class="sxs-lookup"><span data-stu-id="e5398-110">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="e5398-111">전화 진단 요약 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="e5398-111">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="e5398-112">모니터링 보고서 홈 페이지에서 전화 진단 요약 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-112">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="e5398-113">호출 진단 요약 보고서에서 보고서의 피어 투 피어 세션 요약 섹션에서 오류율을 클릭 하 여 [Lync Server 2013에서 피어 투 피어 작업 진단 보고서](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-113">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="e5398-114">다음 회의 메트릭 중 하나를 클릭 하 여 [Lync Server 2013에서 전화 회의 진단 보고서](lync-server-2013-conference-diagnostic-report.md) 에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-114">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="e5398-115">전체 세션 실패 율</span><span class="sxs-lookup"><span data-stu-id="e5398-115">Overall session failure rate</span></span>

  - <span data-ttu-id="e5398-116">초점 고장 속도</span><span class="sxs-lookup"><span data-stu-id="e5398-116">Focus failure rate</span></span>

  - <span data-ttu-id="e5398-117">MCU 실패 율</span><span class="sxs-lookup"><span data-stu-id="e5398-117">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="e5398-118">통화 진단 요약 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="e5398-118">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="e5398-119">전화 진단 요약 보고서에는 Microsoft Lync Server 2013에서 사용 되는 다양 한 형식을의 실패율을 비교 하는 그래프가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-119">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="e5398-120">이러한 그래프의 열은 실제로 hotlinks. 예를 들어 피어 투 피어 세션에 대해 인스턴트 메시지 열을 클릭 하면 [Lync Server 2013에서 피어 투 피어 작업 진단 보고서](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)의 인스턴스가 드릴 다운 되며,이는 전화 진단 요약 보고서에 포함 된 모든 인스턴트 메시징 세션에 대 한 추가 세부 정보를 제공 하는 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-120">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e5398-121">필터가</span><span class="sxs-lookup"><span data-stu-id="e5398-121">Filters</span></span>

<span data-ttu-id="e5398-122">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-122">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="e5398-123">예를 들어 통화 진단 요약 보고서를 사용 하 여 세션에 사용 되는 등록자 풀이나 Edge 서버와 같은 작업을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-123">For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session.</span></span> <span data-ttu-id="e5398-124">데이터 그룹화 방법을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-124">You can also choose how data should be grouped.</span></span> <span data-ttu-id="e5398-125">이 경우 통화는 시, 일, 주 또는 월로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-125">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="e5398-126">다음 표에는 호출 진단 요약 보고서와 함께 사용할 수 있는 필터가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-126">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="e5398-127">전화 진단 요약 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="e5398-127">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5398-128">이름</span><span class="sxs-lookup"><span data-stu-id="e5398-128">Name</span></span></th>
<th><span data-ttu-id="e5398-129">설명</span><span class="sxs-lookup"><span data-stu-id="e5398-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5398-130"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="e5398-130"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e5398-131">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-131">Start date/time for the time range.</span></span> <span data-ttu-id="e5398-132">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-132">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e5398-133">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="e5398-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e5398-134">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-134">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="e5398-135">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-135">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e5398-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e5398-136">7/7/2012</span></span></p>
<p><span data-ttu-id="e5398-137">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="e5398-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e5398-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e5398-138">7/3/2012</span></span></p>
<p><span data-ttu-id="e5398-139">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5398-140"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="e5398-140"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e5398-141">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-141">End date/time for the time range.</span></span> <span data-ttu-id="e5398-142">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-142">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e5398-143">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="e5398-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e5398-144">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-144">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="e5398-145">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-145">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e5398-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e5398-146">7/7/2012</span></span></p>
<p><span data-ttu-id="e5398-147">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="e5398-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e5398-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e5398-148">7/3/2012</span></span></p>
<p><span data-ttu-id="e5398-149">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5398-150"><strong>간격만</strong></span><span class="sxs-lookup"><span data-stu-id="e5398-150"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="e5398-151">시간 간격.</span><span class="sxs-lookup"><span data-stu-id="e5398-151">Time interval.</span></span> <span data-ttu-id="e5398-152">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-152">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e5398-153">매시간 (최대 25 시간 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="e5398-153">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e5398-154">매일 (최대 31 일이 표시 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="e5398-154">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e5398-155">주간 (최대 12 주를 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="e5398-155">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e5398-156">월간 (최대 12 개월을 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="e5398-156">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="e5398-157">시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-157">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="e5398-158">예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-158">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5398-159"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="e5398-159"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e5398-160">등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-160">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="e5398-161">개별 풀을 선택 하거나 <strong>[모두]</strong> 를 클릭 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-161">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="e5398-162">이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-162">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="e5398-163">피어 투 피어 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="e5398-163">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="e5398-164">다음 표에는 피어 투 피어 세션 (즉, 두 명의 참가자만 참여 하는 세션)에 대 한 호출 진단 요약 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-164">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="e5398-165">피어 투 피어 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="e5398-165">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5398-166">이름</span><span class="sxs-lookup"><span data-stu-id="e5398-166">Name</span></span></th>
<th><span data-ttu-id="e5398-167">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e5398-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e5398-168">설명</span><span class="sxs-lookup"><span data-stu-id="e5398-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5398-169"><strong>총 세션</strong></span><span class="sxs-lookup"><span data-stu-id="e5398-169"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e5398-170">아니요</span><span class="sxs-lookup"><span data-stu-id="e5398-170">No</span></span></p></td>
<td><p><span data-ttu-id="e5398-171">수행 된 피어 투 피어 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-171">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5398-172"><strong>실패 율</strong></span><span class="sxs-lookup"><span data-stu-id="e5398-172"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="e5398-173">아니요</span><span class="sxs-lookup"><span data-stu-id="e5398-173">No</span></span></p></td>
<td><p><span data-ttu-id="e5398-174">실패 한 피어 투 피어 세션의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-174">Percentage of peer-to-peer sessions that failed.</span></span> <span data-ttu-id="e5398-175">이 항목을 클릭 하면 실패 한 피어 투 피어 세션에 대 한 자세한 정보를 표시 하는 피어 투 피어 작업 진단 보고서가 보고서에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-175">When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="e5398-176">회의 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="e5398-176">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="e5398-177">다음 표에는 회의 세션 (즉, 세 명 이상의 참가자와 관련 된 세션)에 대 한 호출 진단 보고서에서 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-177">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="e5398-178">회의 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="e5398-178">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5398-179">이름</span><span class="sxs-lookup"><span data-stu-id="e5398-179">Name</span></span></th>
<th><span data-ttu-id="e5398-180">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e5398-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e5398-181">설명</span><span class="sxs-lookup"><span data-stu-id="e5398-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5398-182"><strong>총 컨퍼런스</strong></span><span class="sxs-lookup"><span data-stu-id="e5398-182"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="e5398-183">아니요</span><span class="sxs-lookup"><span data-stu-id="e5398-183">No</span></span></p></td>
<td><p><span data-ttu-id="e5398-184">수행 된 총 컨퍼런스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-184">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5398-185"><strong>총 회의 세션</strong></span><span class="sxs-lookup"><span data-stu-id="e5398-185"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e5398-186">아니요</span><span class="sxs-lookup"><span data-stu-id="e5398-186">No</span></span></p></td>
<td><p><span data-ttu-id="e5398-187">수행 된 총 회의 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-187">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5398-188"><strong>전체 세션 실패 율</strong></span><span class="sxs-lookup"><span data-stu-id="e5398-188"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="e5398-189">아니요</span><span class="sxs-lookup"><span data-stu-id="e5398-189">No</span></span></p></td>
<td><p><span data-ttu-id="e5398-190">실패 한 총 회의 세션의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-190">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5398-191"><strong>포커스 세션</strong></span><span class="sxs-lookup"><span data-stu-id="e5398-191"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e5398-192">아니요</span><span class="sxs-lookup"><span data-stu-id="e5398-192">No</span></span></p></td>
<td><p><span data-ttu-id="e5398-193">실패 한 포커스 기반 회의 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-193">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5398-194"><strong>초점 고장 속도</strong></span><span class="sxs-lookup"><span data-stu-id="e5398-194"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="e5398-195">아니요</span><span class="sxs-lookup"><span data-stu-id="e5398-195">No</span></span></p></td>
<td><p><span data-ttu-id="e5398-196">실패 한 포커스 기반 회의 세션의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-196">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5398-197"><strong>MCU 세션</strong></span><span class="sxs-lookup"><span data-stu-id="e5398-197"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e5398-198">아니요</span><span class="sxs-lookup"><span data-stu-id="e5398-198">No</span></span></p></td>
<td><p><span data-ttu-id="e5398-199">실패 한 총 회의 서버 기반 (이전의 Multipoint 컨트롤 단위 또는 MCU) 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-199">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5398-200"><strong>MCU 실패 율</strong></span><span class="sxs-lookup"><span data-stu-id="e5398-200"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="e5398-201">아니요</span><span class="sxs-lookup"><span data-stu-id="e5398-201">No</span></span></p></td>
<td><p><span data-ttu-id="e5398-202">장애가 있는 회의 서버 기반 (이전의 Multipoint 컨트롤 단위 또는 MCU) 회의의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="e5398-202">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

