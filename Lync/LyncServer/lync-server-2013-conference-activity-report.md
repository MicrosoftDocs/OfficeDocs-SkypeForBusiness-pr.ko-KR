---
title: 'Lync Server 2013: 회의 활동 보고서'
description: 'Lync Server 2013: 회의 활동 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7a2b23a08970defaec62b98d075ad1167527fd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577654"
---
# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="3eb67-103">Lync Server 2013의 전화 회의 활동 보고서</span><span class="sxs-lookup"><span data-stu-id="3eb67-103">Conference Activity Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3eb67-104">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="3eb67-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="3eb67-105">전화 회의 활동 보고서를 사용 하면 매일 몇 회의를 개최 하 고 언제 어떤 회의가 진행 되 고 있습니까?</span><span class="sxs-lookup"><span data-stu-id="3eb67-105">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="3eb67-106">이와 같은 정보는 자체 권한 뿐만 아니라 문제 해결 도구 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-106">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="3eb67-107">예를 들어 사용자가 특히 하루 중에 네트워크가 느리게 불만 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-107">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="3eb67-108">전화 회의 활동 보고서에 대 한 간략 한 설명을 통해 가능한 이유는 다음 중 하나입니다. 1 시간 10:00 시, 2:00 오후 10 시 사이에 회의가 더 많이 진행 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-108">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="3eb67-109">느린 네트워크로 인해 문제가 발생 하는 경우 사용자가 하루 덜 트래픽이 더 적은 시간에 일부 전화 회의를 다시 예약 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-109">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="3eb67-110">전화 회의 활동 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="3eb67-110">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="3eb67-111">전화 회의 활동 보고서는 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 전화 회의 요약 보고서](lync-server-2013-conference-summary-report.md) 에서 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-111">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="3eb67-112">총 회의</span><span class="sxs-lookup"><span data-stu-id="3eb67-112">Total conferences</span></span>

  - <span data-ttu-id="3eb67-113">총 참가자</span><span class="sxs-lookup"><span data-stu-id="3eb67-113">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="3eb67-114">전화 회의 활동 보고서를 가장 효율적으로 활용</span><span class="sxs-lookup"><span data-stu-id="3eb67-114">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="3eb67-115">기본적으로 전화 회의 활동 보고서에는 지정 된 기간에 대 한 총 회의 수 (예: 하루 총 회의 수 또는 하루 중 시간당 총 회의 수)가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-115">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day).</span></span> <span data-ttu-id="3eb67-116">그러나 해당 기간에 대 한 총 참석자 수 또는 총 참가자 수 (분)를 표시 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-116">However, you can also choose to display the total number of participants for that time period or the total number of participant minutes.</span></span> <span data-ttu-id="3eb67-117">이렇게 하려면 매개 변수 표시/숨기기 단추를 클릭 하 여 필터링 옵션을 표시 한 다음 보고서 기준 드롭다운 목록에서 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-117">To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="3eb67-118">참가자 수</span><span class="sxs-lookup"><span data-stu-id="3eb67-118">Participant count</span></span>

  - <span data-ttu-id="3eb67-119">참가자 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="3eb67-119">Participant minutes</span></span>

  - <span data-ttu-id="3eb67-120">전화 회의 수</span><span class="sxs-lookup"><span data-stu-id="3eb67-120">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="3eb67-121">필터</span><span class="sxs-lookup"><span data-stu-id="3eb67-121">Filters</span></span>

<span data-ttu-id="3eb67-122">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-122">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="3eb67-123">다음 표에서는 전화 회의 활동 보고서에서 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-123">The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="3eb67-124">전화 회의 활동 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="3eb67-124">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3eb67-125">이름</span><span class="sxs-lookup"><span data-stu-id="3eb67-125">Name</span></span></th>
<th><span data-ttu-id="3eb67-126">설명</span><span class="sxs-lookup"><span data-stu-id="3eb67-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3eb67-127"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="3eb67-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="3eb67-p104">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="3eb67-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="3eb67-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3eb67-p105">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3eb67-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3eb67-133">7/7/2012</span></span></p>
<p><span data-ttu-id="3eb67-134">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3eb67-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3eb67-135">7/3/2012</span></span></p>
<p><span data-ttu-id="3eb67-136">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3eb67-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="3eb67-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="3eb67-p106">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="3eb67-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="3eb67-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3eb67-p107">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3eb67-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3eb67-143">7/7/2012</span></span></p>
<p><span data-ttu-id="3eb67-144">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3eb67-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3eb67-145">7/3/2012</span></span></p>
<p><span data-ttu-id="3eb67-146">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3eb67-147"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="3eb67-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="3eb67-148">시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-148">Time interval.</span></span> <span data-ttu-id="3eb67-149">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-149">Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3eb67-150">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="3eb67-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="3eb67-151">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="3eb67-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="3eb67-152">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="3eb67-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="3eb67-153">월별(최대 12개월 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="3eb67-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="3eb67-p109">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3eb67-156"><strong>보고서 작성자</strong></span><span class="sxs-lookup"><span data-stu-id="3eb67-156"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="3eb67-157">보고서에 사용할 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-157">Indicates the values to be used in the report.</span></span> <span data-ttu-id="3eb67-158">다음 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-158">You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3eb67-159">참가자 수</span><span class="sxs-lookup"><span data-stu-id="3eb67-159">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="3eb67-160">참가자 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="3eb67-160">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="3eb67-161">전화 회의 수</span><span class="sxs-lookup"><span data-stu-id="3eb67-161">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="3eb67-162">풀 별 전화 회의 메트릭</span><span class="sxs-lookup"><span data-stu-id="3eb67-162">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="3eb67-163">다음 표에서는 각 풀에 대 한 전화 회의 활동 보고서의 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-163">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="3eb67-164">풀 별 전화 회의 메트릭</span><span class="sxs-lookup"><span data-stu-id="3eb67-164">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3eb67-165">이름</span><span class="sxs-lookup"><span data-stu-id="3eb67-165">Name</span></span></th>
<th><span data-ttu-id="3eb67-166">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="3eb67-166">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3eb67-167">설명</span><span class="sxs-lookup"><span data-stu-id="3eb67-167">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3eb67-168"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="3eb67-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="3eb67-169">아니요</span><span class="sxs-lookup"><span data-stu-id="3eb67-169">No</span></span></p></td>
<td><p><span data-ttu-id="3eb67-170">전화 회의에서 사용 되는 등록자 풀 또는에 지 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-170">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3eb67-171"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="3eb67-171"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="3eb67-172">아니요</span><span class="sxs-lookup"><span data-stu-id="3eb67-172">No</span></span></p></td>
<td><p><span data-ttu-id="3eb67-173">전화 회의가 보류 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-173">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3eb67-174"><strong>합계</strong></span><span class="sxs-lookup"><span data-stu-id="3eb67-174"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="3eb67-175">아니요</span><span class="sxs-lookup"><span data-stu-id="3eb67-175">No</span></span></p></td>
<td><p><span data-ttu-id="3eb67-176">총 참가자 수, 총 참가 시간 (분) 또는 총 전화 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-176">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="3eb67-177">서버 유형별 전화 회의 메트릭</span><span class="sxs-lookup"><span data-stu-id="3eb67-177">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="3eb67-178">다음 표에서는 각 서버 유형에 대 한 전화 회의 활동 보고서의 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-178">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="3eb67-179">서버 유형별 전화 회의 메트릭</span><span class="sxs-lookup"><span data-stu-id="3eb67-179">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3eb67-180">이름</span><span class="sxs-lookup"><span data-stu-id="3eb67-180">Name</span></span></th>
<th><span data-ttu-id="3eb67-181">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="3eb67-181">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3eb67-182">설명</span><span class="sxs-lookup"><span data-stu-id="3eb67-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3eb67-183"><strong>회의 서버 유형</strong></span><span class="sxs-lookup"><span data-stu-id="3eb67-183"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="3eb67-184">아니요</span><span class="sxs-lookup"><span data-stu-id="3eb67-184">No</span></span></p></td>
<td><p><span data-ttu-id="3eb67-185">전화 회의에서 사용 되는 서버의 유형으로, 일반적으로 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-185">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3eb67-186">웹 회의 서버</span><span class="sxs-lookup"><span data-stu-id="3eb67-186">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="3eb67-187">IM 회의 서버</span><span class="sxs-lookup"><span data-stu-id="3eb67-187">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="3eb67-188">전화 회의 서버</span><span class="sxs-lookup"><span data-stu-id="3eb67-188">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="3eb67-189">AV 회의 서버</span><span class="sxs-lookup"><span data-stu-id="3eb67-189">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="3eb67-190">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="3eb67-190">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3eb67-191"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="3eb67-191"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="3eb67-192">아니요</span><span class="sxs-lookup"><span data-stu-id="3eb67-192">No</span></span></p></td>
<td><p><span data-ttu-id="3eb67-193">전화 회의가 보류 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-193">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3eb67-194"><strong>합계</strong></span><span class="sxs-lookup"><span data-stu-id="3eb67-194"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="3eb67-195">아니요</span><span class="sxs-lookup"><span data-stu-id="3eb67-195">No</span></span></p></td>
<td><p><span data-ttu-id="3eb67-196">총 참가자 수, 총 참가 시간 (분) 또는 총 전화 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3eb67-196">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

