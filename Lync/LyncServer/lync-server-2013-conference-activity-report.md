---
title: 'Lync Server 2013: 컨퍼런스 활동 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f96ddc5dfda18fa1d96903eb5755481f76853c06
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="f6957-102">Lync Server 2013의 컨퍼런스 활동 보고서</span><span class="sxs-lookup"><span data-stu-id="f6957-102">Conference Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6957-103">_**마지막으로 수정한 주제:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="f6957-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="f6957-104">컨퍼런스 활동 보고서를 사용 하 여 매일 보유 하 고 있는 컨퍼런스 수와 이러한 회의가 어디에 있습니까?와 같은 질문에 쉽게 대답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-104">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="f6957-105">이와 같은 정보는 고유한 권한 뿐만 아니라 문제 해결 도구 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-105">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="f6957-106">예를 들어 사용자가 하루 중간에 특히 느린 네트워크를 complaining 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-106">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="f6957-107">회의 활동 보고서를 신속 하 게 살펴보기 할 수 있는 이유는 무엇 인가요? 오전 10:00, 2:00 PM 시간 사이에 더 많은 회의가 예정 되어 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-107">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="f6957-108">느린 네트워크로 인해 문제가 발생 하는 경우 사용자가 하루 보다 덜 trafficked 시간에 일부 회의를 다시 예약 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-108">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="f6957-109">컨퍼런스 활동 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="f6957-109">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="f6957-110">회의 활동 보고서에는 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 회의 요약 보고서](lync-server-2013-conference-summary-report.md) 에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-110">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="f6957-111">총 컨퍼런스</span><span class="sxs-lookup"><span data-stu-id="f6957-111">Total conferences</span></span>

  - <span data-ttu-id="f6957-112">총 참가자</span><span class="sxs-lookup"><span data-stu-id="f6957-112">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="f6957-113">컨퍼런스 활동 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="f6957-113">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="f6957-114">기본적으로 컨퍼런스 활동 보고서에는 지정 된 기간에 대 한 총 컨퍼런스 수 (예: 하루 총 회의 수 또는 일일 총 컨퍼런스 수)가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-114">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day).</span></span> <span data-ttu-id="f6957-115">그러나 해당 기간 또는 총 참가자 수 (분)에 대 한 총 참가자 수를 표시 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-115">However, you can also choose to display the total number of participants for that time period or the total number of participant minutes.</span></span> <span data-ttu-id="f6957-116">이렇게 하려면 매개 변수 표시/숨기기 단추를 클릭 하 여 필터링 옵션을 표시 하 고 보고서 드롭다운 목록에서 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-116">To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="f6957-117">참가자 수</span><span class="sxs-lookup"><span data-stu-id="f6957-117">Participant count</span></span>

  - <span data-ttu-id="f6957-118">참가자 통화 시간</span><span class="sxs-lookup"><span data-stu-id="f6957-118">Participant minutes</span></span>

  - <span data-ttu-id="f6957-119">컨퍼런스 수</span><span class="sxs-lookup"><span data-stu-id="f6957-119">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="f6957-120">필터가</span><span class="sxs-lookup"><span data-stu-id="f6957-120">Filters</span></span>

<span data-ttu-id="f6957-121">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-121">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="f6957-122">다음 표에는 회의 활동 보고서에 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-122">The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="f6957-123">컨퍼런스 활동 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="f6957-123">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6957-124">이름</span><span class="sxs-lookup"><span data-stu-id="f6957-124">Name</span></span></th>
<th><span data-ttu-id="f6957-125">설명</span><span class="sxs-lookup"><span data-stu-id="f6957-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6957-126"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="f6957-126"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="f6957-127">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-127">Start date/time for the time range.</span></span> <span data-ttu-id="f6957-128">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-128">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="f6957-129">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="f6957-129">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f6957-130">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-130">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="f6957-131">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-131">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f6957-132">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f6957-132">7/7/2012</span></span></p>
<p><span data-ttu-id="f6957-133">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="f6957-133">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f6957-134">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f6957-134">7/3/2012</span></span></p>
<p><span data-ttu-id="f6957-135">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-135">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6957-136"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="f6957-136"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="f6957-137">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-137">End date/time for the time range.</span></span> <span data-ttu-id="f6957-138">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-138">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="f6957-139">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="f6957-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f6957-140">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-140">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="f6957-141">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-141">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f6957-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f6957-142">7/7/2012</span></span></p>
<p><span data-ttu-id="f6957-143">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="f6957-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f6957-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f6957-144">7/3/2012</span></span></p>
<p><span data-ttu-id="f6957-145">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6957-146"><strong>간격만</strong></span><span class="sxs-lookup"><span data-stu-id="f6957-146"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="f6957-147">시간 간격.</span><span class="sxs-lookup"><span data-stu-id="f6957-147">Time interval.</span></span> <span data-ttu-id="f6957-148">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-148">Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f6957-149">매시간 (최대 25 시간 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="f6957-149">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f6957-150">매일 (최대 31 일이 표시 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="f6957-150">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f6957-151">주간 (최대 12 주를 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="f6957-151">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f6957-152">월간 (최대 12 개월을 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="f6957-152">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="f6957-153">시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-153">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="f6957-154">예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-154">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6957-155"><strong>보고서 기준</strong></span><span class="sxs-lookup"><span data-stu-id="f6957-155"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="f6957-156">보고서에 사용할 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-156">Indicates the values to be used in the report.</span></span> <span data-ttu-id="f6957-157">다음 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-157">You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f6957-158">참가자 수</span><span class="sxs-lookup"><span data-stu-id="f6957-158">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="f6957-159">참가자 통화 시간</span><span class="sxs-lookup"><span data-stu-id="f6957-159">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="f6957-160">컨퍼런스 수</span><span class="sxs-lookup"><span data-stu-id="f6957-160">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="f6957-161">풀 별 컨퍼런스에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="f6957-161">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="f6957-162">다음 표에는 각 풀에 대 한 회의 활동 보고서의 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-162">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="f6957-163">풀 별 컨퍼런스에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="f6957-163">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6957-164">이름</span><span class="sxs-lookup"><span data-stu-id="f6957-164">Name</span></span></th>
<th><span data-ttu-id="f6957-165">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="f6957-165">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f6957-166">설명</span><span class="sxs-lookup"><span data-stu-id="f6957-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6957-167"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="f6957-167"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f6957-168">아니요</span><span class="sxs-lookup"><span data-stu-id="f6957-168">No</span></span></p></td>
<td><p><span data-ttu-id="f6957-169">회의에 사용 되는 등록자 풀 또는 Edge 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-169">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6957-170"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="f6957-170"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="f6957-171">아니요</span><span class="sxs-lookup"><span data-stu-id="f6957-171">No</span></span></p></td>
<td><p><span data-ttu-id="f6957-172">회의가 보류 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-172">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6957-173"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="f6957-173"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="f6957-174">아니요</span><span class="sxs-lookup"><span data-stu-id="f6957-174">No</span></span></p></td>
<td><p><span data-ttu-id="f6957-175">총 참가자 수, 총 참가자 시간 또는 총 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-175">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="f6957-176">서버 유형별 회의 메트릭</span><span class="sxs-lookup"><span data-stu-id="f6957-176">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="f6957-177">다음 표에는 각 유형의 서버에 대 한 회의 활동 보고서의 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-177">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="f6957-178">서버 유형별 회의 메트릭</span><span class="sxs-lookup"><span data-stu-id="f6957-178">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6957-179">이름</span><span class="sxs-lookup"><span data-stu-id="f6957-179">Name</span></span></th>
<th><span data-ttu-id="f6957-180">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="f6957-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f6957-181">설명</span><span class="sxs-lookup"><span data-stu-id="f6957-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6957-182"><strong>회의 서버 유형</strong></span><span class="sxs-lookup"><span data-stu-id="f6957-182"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="f6957-183">아니요</span><span class="sxs-lookup"><span data-stu-id="f6957-183">No</span></span></p></td>
<td><p><span data-ttu-id="f6957-184">회의에 사용 되는 서버 유형으로, 일반적으로 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-184">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f6957-185">웹 회의 서버</span><span class="sxs-lookup"><span data-stu-id="f6957-185">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="f6957-186">IM 회의 서버</span><span class="sxs-lookup"><span data-stu-id="f6957-186">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="f6957-187">전화 통신 회의 서버</span><span class="sxs-lookup"><span data-stu-id="f6957-187">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="f6957-188">AV 회의 서버</span><span class="sxs-lookup"><span data-stu-id="f6957-188">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="f6957-189">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="f6957-189">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6957-190"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="f6957-190"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="f6957-191">아니요</span><span class="sxs-lookup"><span data-stu-id="f6957-191">No</span></span></p></td>
<td><p><span data-ttu-id="f6957-192">회의가 보류 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-192">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6957-193"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="f6957-193"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="f6957-194">아니요</span><span class="sxs-lookup"><span data-stu-id="f6957-194">No</span></span></p></td>
<td><p><span data-ttu-id="f6957-195">총 참가자 수, 총 참가자 시간 또는 총 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f6957-195">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

