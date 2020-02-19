---
title: 'Lync Server 2013: 회의 활동 보고서'
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
ms.openlocfilehash: 93113f3167cf16733f5c7ab51247dcb57f1a118c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="2cbe2-102">Lync Server 2013의 전화 회의 활동 보고서</span><span class="sxs-lookup"><span data-stu-id="2cbe2-102">Conference Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2cbe2-103">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="2cbe2-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="2cbe2-104">전화 회의 활동 보고서를 사용 하면 매일 몇 회의를 개최 하 고 언제 어떤 회의가 진행 되 고 있습니까?</span><span class="sxs-lookup"><span data-stu-id="2cbe2-104">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="2cbe2-105">이와 같은 정보는 자체 권한 뿐만 아니라 문제 해결 도구 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-105">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="2cbe2-106">예를 들어 사용자가 특히 하루 중에 네트워크가 느리게 불만 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-106">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="2cbe2-107">전화 회의 활동 보고서에 대 한 간략 한 설명을 통해 가능한 이유는 다음 중 하나입니다. 1 시간 10:00 시, 2:00 오후 10 시 사이에 회의가 더 많이 진행 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-107">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="2cbe2-108">느린 네트워크로 인해 문제가 발생 하는 경우 사용자가 하루 덜 트래픽이 더 적은 시간에 일부 전화 회의를 다시 예약 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-108">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="2cbe2-109">전화 회의 활동 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="2cbe2-109">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="2cbe2-110">전화 회의 활동 보고서는 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 전화 회의 요약 보고서](lync-server-2013-conference-summary-report.md) 에서 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-110">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="2cbe2-111">총 회의</span><span class="sxs-lookup"><span data-stu-id="2cbe2-111">Total conferences</span></span>

  - <span data-ttu-id="2cbe2-112">총 참가자</span><span class="sxs-lookup"><span data-stu-id="2cbe2-112">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="2cbe2-113">전화 회의 활동 보고서를 가장 효율적으로 활용</span><span class="sxs-lookup"><span data-stu-id="2cbe2-113">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="2cbe2-114">기본적으로 전화 회의 활동 보고서에는 지정 된 기간에 대 한 총 회의 수 (예: 하루 총 회의 수 또는 하루 중 시간당 총 회의 수)가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-114">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day).</span></span> <span data-ttu-id="2cbe2-115">그러나 해당 기간에 대 한 총 참석자 수 또는 총 참가자 수 (분)를 표시 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-115">However, you can also choose to display the total number of participants for that time period or the total number of participant minutes.</span></span> <span data-ttu-id="2cbe2-116">이렇게 하려면 매개 변수 표시/숨기기 단추를 클릭 하 여 필터링 옵션을 표시 한 다음 보고서 기준 드롭다운 목록에서 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-116">To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="2cbe2-117">참가자 수</span><span class="sxs-lookup"><span data-stu-id="2cbe2-117">Participant count</span></span>

  - <span data-ttu-id="2cbe2-118">참가자 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="2cbe2-118">Participant minutes</span></span>

  - <span data-ttu-id="2cbe2-119">전화 회의 수</span><span class="sxs-lookup"><span data-stu-id="2cbe2-119">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2cbe2-120">필터</span><span class="sxs-lookup"><span data-stu-id="2cbe2-120">Filters</span></span>

<span data-ttu-id="2cbe2-121">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-121">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="2cbe2-122">다음 표에서는 전화 회의 활동 보고서에서 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-122">The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="2cbe2-123">전화 회의 활동 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="2cbe2-123">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cbe2-124">이름</span><span class="sxs-lookup"><span data-stu-id="2cbe2-124">Name</span></span></th>
<th><span data-ttu-id="2cbe2-125">설명</span><span class="sxs-lookup"><span data-stu-id="2cbe2-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cbe2-126"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="2cbe2-126"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2cbe2-p104">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2cbe2-129">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2cbe2-129">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2cbe2-p105">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2cbe2-132">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2cbe2-132">7/7/2012</span></span></p>
<p><span data-ttu-id="2cbe2-133">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-133">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2cbe2-134">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2cbe2-134">7/3/2012</span></span></p>
<p><span data-ttu-id="2cbe2-135">주는 항상 일요일부터 토요일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-135">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cbe2-136"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="2cbe2-136"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2cbe2-p106">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2cbe2-139">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2cbe2-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2cbe2-p107">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2cbe2-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2cbe2-142">7/7/2012</span></span></p>
<p><span data-ttu-id="2cbe2-143">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2cbe2-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2cbe2-144">7/3/2012</span></span></p>
<p><span data-ttu-id="2cbe2-145">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cbe2-146"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="2cbe2-146"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="2cbe2-147">시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-147">Time interval.</span></span> <span data-ttu-id="2cbe2-148">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-148">Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cbe2-149">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="2cbe2-149">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2cbe2-150">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="2cbe2-150">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2cbe2-151">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="2cbe2-151">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2cbe2-152">월별(최대 12개월 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="2cbe2-152">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="2cbe2-p109">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cbe2-155"><strong>보고서 작성자</strong></span><span class="sxs-lookup"><span data-stu-id="2cbe2-155"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="2cbe2-156">보고서에 사용할 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-156">Indicates the values to be used in the report.</span></span> <span data-ttu-id="2cbe2-157">다음 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-157">You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cbe2-158">참가자 수</span><span class="sxs-lookup"><span data-stu-id="2cbe2-158">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="2cbe2-159">참가자 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="2cbe2-159">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="2cbe2-160">전화 회의 수</span><span class="sxs-lookup"><span data-stu-id="2cbe2-160">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="2cbe2-161">풀 별 전화 회의 메트릭</span><span class="sxs-lookup"><span data-stu-id="2cbe2-161">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="2cbe2-162">다음 표에서는 각 풀에 대 한 전화 회의 활동 보고서의 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-162">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="2cbe2-163">풀 별 전화 회의 메트릭</span><span class="sxs-lookup"><span data-stu-id="2cbe2-163">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cbe2-164">이름</span><span class="sxs-lookup"><span data-stu-id="2cbe2-164">Name</span></span></th>
<th><span data-ttu-id="2cbe2-165">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="2cbe2-165">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2cbe2-166">설명</span><span class="sxs-lookup"><span data-stu-id="2cbe2-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cbe2-167"><strong>그룹</strong></span><span class="sxs-lookup"><span data-stu-id="2cbe2-167"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="2cbe2-168">아니요</span><span class="sxs-lookup"><span data-stu-id="2cbe2-168">No</span></span></p></td>
<td><p><span data-ttu-id="2cbe2-169">전화 회의에서 사용 되는 등록자 풀 또는에 지 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-169">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cbe2-170"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="2cbe2-170"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="2cbe2-171">아니요</span><span class="sxs-lookup"><span data-stu-id="2cbe2-171">No</span></span></p></td>
<td><p><span data-ttu-id="2cbe2-172">전화 회의가 보류 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-172">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cbe2-173"><strong>합계</strong></span><span class="sxs-lookup"><span data-stu-id="2cbe2-173"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="2cbe2-174">아니요</span><span class="sxs-lookup"><span data-stu-id="2cbe2-174">No</span></span></p></td>
<td><p><span data-ttu-id="2cbe2-175">총 참가자 수, 총 참가 시간 (분) 또는 총 전화 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-175">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="2cbe2-176">서버 유형별 전화 회의 메트릭</span><span class="sxs-lookup"><span data-stu-id="2cbe2-176">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="2cbe2-177">다음 표에서는 각 서버 유형에 대 한 전화 회의 활동 보고서의 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-177">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="2cbe2-178">서버 유형별 전화 회의 메트릭</span><span class="sxs-lookup"><span data-stu-id="2cbe2-178">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2cbe2-179">이름</span><span class="sxs-lookup"><span data-stu-id="2cbe2-179">Name</span></span></th>
<th><span data-ttu-id="2cbe2-180">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="2cbe2-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2cbe2-181">설명</span><span class="sxs-lookup"><span data-stu-id="2cbe2-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2cbe2-182"><strong>회의 서버 유형</strong></span><span class="sxs-lookup"><span data-stu-id="2cbe2-182"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="2cbe2-183">아니요</span><span class="sxs-lookup"><span data-stu-id="2cbe2-183">No</span></span></p></td>
<td><p><span data-ttu-id="2cbe2-184">전화 회의에서 사용 되는 서버의 유형으로, 일반적으로 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-184">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2cbe2-185">웹 회의 서버</span><span class="sxs-lookup"><span data-stu-id="2cbe2-185">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="2cbe2-186">IM 회의 서버</span><span class="sxs-lookup"><span data-stu-id="2cbe2-186">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="2cbe2-187">전화 회의 서버</span><span class="sxs-lookup"><span data-stu-id="2cbe2-187">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="2cbe2-188">AV 회의 서버</span><span class="sxs-lookup"><span data-stu-id="2cbe2-188">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="2cbe2-189">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="2cbe2-189">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2cbe2-190"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="2cbe2-190"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="2cbe2-191">아니요</span><span class="sxs-lookup"><span data-stu-id="2cbe2-191">No</span></span></p></td>
<td><p><span data-ttu-id="2cbe2-192">전화 회의가 보류 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-192">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2cbe2-193"><strong>합계</strong></span><span class="sxs-lookup"><span data-stu-id="2cbe2-193"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="2cbe2-194">아니요</span><span class="sxs-lookup"><span data-stu-id="2cbe2-194">No</span></span></p></td>
<td><p><span data-ttu-id="2cbe2-195">총 참가자 수, 총 참가 시간 (분) 또는 총 전화 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbe2-195">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

