---
title: 'Lync Server 2013: 전화 회의 진단 보고서'
description: 'Lync Server 2013: 전화 회의 진단 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d3ef3c78bc2145d907d5a40e1aed95a2f4cb4c4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577644"
---
# <a name="conference-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="e85f3-103">Lync Server 2013의 전화 회의 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="e85f3-103">Conference Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e85f3-104">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="e85f3-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="e85f3-105">전화 회의 진단 보고서는 모든 회의 세션의 성공 및 실패에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-105">The Conference Diagnostic Report provides information about the success and failure of all conferencing sessions.</span></span> <span data-ttu-id="e85f3-106">Microsoft Lync Server는 다음과 같은 다양 한 종류의 오류를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-106">Note that Microsoft Lync Server distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="e85f3-107">**예상 오류**입니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-107">**Expected failure**.</span></span> <span data-ttu-id="e85f3-108">일반적으로 예상 되는 오류는 가장 기술적으로 발생 하는 오류에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-108">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="e85f3-109">예를 들어 누군가 회의를 시작 하지만 누구나 참가할 수 있는 경우에는 전화를 끊기로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-109">For example, suppose someone starts a conference but hangs up before anyone can join.</span></span> <span data-ttu-id="e85f3-110">기술적으로, 회의가 시작 되었지만 완료 되지 않은 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-110">Technically that's a failure: the conference was initiated, but not completed.</span></span> <span data-ttu-id="e85f3-111">그러나 모든 사용자가 참석할 수 있을 때까지 이끌이가 회의를 취소 하면 회의가 완료 되지 않을 것으로 예상 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-111">However, that's a failure that you would expect to happen: if the organizer cancels the conference before anyone can join then you would not expect that conference to be completed.</span></span>

  - <span data-ttu-id="e85f3-112">**예기치 않은 오류**입니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-112">**Unexpected failure**.</span></span> <span data-ttu-id="e85f3-113">예기치 않은 오류는 해당 상황에 따라 발생할 것으로 예상 되는 오류를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="e85f3-114">예를 들어 이끌이의 모임 정책을 검색할 수 없어서 회의에 참가 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-114">For example, suppose a conference could not be held because the organizer's meeting policy could not be retrieved.</span></span> <span data-ttu-id="e85f3-115">예기치 않은 오류입니다. 모든 작업을 수행한 후에는 항상 사용자의 모임 정책을 검색할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-115">That's an unexpected error: after all, you should always be able to retrieve a user's meeting policy.</span></span>

<span data-ttu-id="e85f3-116">성공, 예상 오류 및 예기치 않은 오류 메트릭은 총 세션 메트릭에 추가되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-116">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric.</span></span> <span data-ttu-id="e85f3-117">예를 들어 보고서에 다음과 같은 값이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-117">For example, you might see the following values in the Report:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e85f3-118">성공</span><span class="sxs-lookup"><span data-stu-id="e85f3-118">Successes</span></span></th>
<th><span data-ttu-id="e85f3-119">예상 오류</span><span class="sxs-lookup"><span data-stu-id="e85f3-119">Expected failures</span></span></th>
<th><span data-ttu-id="e85f3-120">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="e85f3-120">Unexpected failures</span></span></th>
<th><span data-ttu-id="e85f3-121">총 세션</span><span class="sxs-lookup"><span data-stu-id="e85f3-121">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e85f3-122">2024</span><span class="sxs-lookup"><span data-stu-id="e85f3-122">2024</span></span></p></td>
<td><p><span data-ttu-id="e85f3-123">469</span><span class="sxs-lookup"><span data-stu-id="e85f3-123">469</span></span></p></td>
<td><p><span data-ttu-id="e85f3-124">16 </span><span class="sxs-lookup"><span data-stu-id="e85f3-124">16</span></span></p></td>
<td><p><span data-ttu-id="e85f3-125">2521</span><span class="sxs-lookup"><span data-stu-id="e85f3-125">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e85f3-126">2024 + 469 + 16을 추가 하면 총 2509 세션을 받게 되며 총 세션 열에 총 2521 세션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-126">If you add 2024 + 469 + 16 you get a total of 2,509 sessions and yet, the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="e85f3-127">"누락 된" 세션은 시스템에서 성공 또는 실패로 분류할 수 없는 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-127">The "missing" 12 sessions for are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="e85f3-128">예를 들어 타사 제품에서 모니터링 서버에 익숙하지 않은 새로운 진단 코드를 도입 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-128">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Monitoring Server.</span></span> <span data-ttu-id="e85f3-129">이와 같은 경우 해당 제품을 사용하여 전화를 걸고 해당 진단 코드를 보고하는 경우를 항상 성공, 예상 오류 또는 예기치 않은 오류로 분류할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-129">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-conference-diagnostic-report"></a><span data-ttu-id="e85f3-130">전화 회의 진단 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="e85f3-130">Accessing the Conference Diagnostic Report</span></span>

<span data-ttu-id="e85f3-131">전화 회의 진단 보고서는 모니터링 보고서 홈 페이지에서 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-131">The Conference Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="e85f3-132">다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 실패 분포 보고서](lync-server-2013-failure-distribution-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-132">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="e85f3-133">예기치 않은 오류량</span><span class="sxs-lookup"><span data-stu-id="e85f3-133">Unexpected failure volume</span></span>

  - <span data-ttu-id="e85f3-134">예상 오류량</span><span class="sxs-lookup"><span data-stu-id="e85f3-134">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a><span data-ttu-id="e85f3-135">전화 회의 진단 보고서의 모범 사례 만들기</span><span class="sxs-lookup"><span data-stu-id="e85f3-135">Making the Best Use of the Conference Diagnostic Report</span></span>

<span data-ttu-id="e85f3-136">전화 회의 진단 보고서에는 일련의 그래프가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-136">The Conference Diagnostic Report includes a series of graphs.</span></span> <span data-ttu-id="e85f3-137">그래프에 표시 되는 각 열은 실제로 하이퍼링크입니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-137">Each of the columns shown in the graph is actually a hyperlink.</span></span> <span data-ttu-id="e85f3-138">열을 클릭 하면 해당 기간 및 해당 회의 유형에 대해 [Lync Server 2013의 실패 분포 보고서](lync-server-2013-failure-distribution-report.md) 가 드릴 다운 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-138">If you click a column, you'll drill down to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) for that time period and that conference type.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e85f3-139">필터</span><span class="sxs-lookup"><span data-stu-id="e85f3-139">Filters</span></span>

<span data-ttu-id="e85f3-140">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-140">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="e85f3-141">예를 들어 회의 진단 보고서를 사용 하 여 수행 되는 회의 유형 (예: 포커스 기반 전화 회의) 또는 회의에 사용 되는에 지 서버에 해당 하는 항목을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-141">For example, the Conference Diagnostic Report enables you to filter on such things as the type of conference being conducted (for example, a Focus-based conference) or by the Edge Server used in the conference.</span></span> <span data-ttu-id="e85f3-142">또한 데이터의 그룹 지정 방식도 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-142">You can also choose how data should be grouped.</span></span> <span data-ttu-id="e85f3-143">이 경우 전화 회의는 시간, 일, 주 또는 월별로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-143">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="e85f3-144">다음 표에서는 전화 회의 진단 보고서에서 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-144">The following table lists the filters that you can use with the Conference Diagnostic Report.</span></span>

### <a name="conference-diagnostic-report-filters"></a><span data-ttu-id="e85f3-145">전화 회의 진단 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="e85f3-145">Conference Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e85f3-146">이름</span><span class="sxs-lookup"><span data-stu-id="e85f3-146">Name</span></span></th>
<th><span data-ttu-id="e85f3-147">설명</span><span class="sxs-lookup"><span data-stu-id="e85f3-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e85f3-148"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="e85f3-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e85f3-p109">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e85f3-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e85f3-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e85f3-p110">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e85f3-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e85f3-154">7/7/2012</span></span></p>
<p><span data-ttu-id="e85f3-155">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e85f3-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e85f3-156">7/3/2012</span></span></p>
<p><span data-ttu-id="e85f3-157">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e85f3-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e85f3-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e85f3-p111">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e85f3-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e85f3-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e85f3-p112">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e85f3-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e85f3-164">7/7/2012</span></span></p>
<p><span data-ttu-id="e85f3-165">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e85f3-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e85f3-166">7/3/2012</span></span></p>
<p><span data-ttu-id="e85f3-167">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e85f3-168"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="e85f3-168"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="e85f3-p113">시간 간격입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e85f3-171">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="e85f3-171">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e85f3-172">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="e85f3-172">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e85f3-173">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="e85f3-173">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e85f3-174">월별(최대 12개월 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="e85f3-174">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="e85f3-p114">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e85f3-177"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="e85f3-177"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e85f3-p115">등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e85f3-181"><strong>회의 세션</strong></span><span class="sxs-lookup"><span data-stu-id="e85f3-181"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e85f3-182">회의 세션의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-182">Indicates the type of conferencing session.</span></span> <span data-ttu-id="e85f3-183">다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-183">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e85f3-184">모든</span><span class="sxs-lookup"><span data-stu-id="e85f3-184">[All]</span></span></p></li>
<li><p><span data-ttu-id="e85f3-185">회의 센터 세션</span><span class="sxs-lookup"><span data-stu-id="e85f3-185">Focus sessions</span></span></p></li>
<li><p><span data-ttu-id="e85f3-186">모든 MCU 세션</span><span class="sxs-lookup"><span data-stu-id="e85f3-186">All MCU sessions</span></span></p></li>
<li><p><span data-ttu-id="e85f3-187">IM 회의</span><span class="sxs-lookup"><span data-stu-id="e85f3-187">IM conferencing</span></span></p></li>
<li><p><span data-ttu-id="e85f3-188">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="e85f3-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="e85f3-189">A/V 회의</span><span class="sxs-lookup"><span data-stu-id="e85f3-189">A/V conferencing</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e85f3-190">메트릭</span><span class="sxs-lookup"><span data-stu-id="e85f3-190">Metrics</span></span>

<span data-ttu-id="e85f3-191">다음 표에서는 각 회의 세션 유형에 대해 회의 진단 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-191">The following table lists the information provided in the Conference Diagnostic Report for each type of conferencing session.</span></span>

### <a name="conference-diagnostic-report-metrics"></a><span data-ttu-id="e85f3-192">전화 회의 진단 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="e85f3-192">Conference Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e85f3-193">이름</span><span class="sxs-lookup"><span data-stu-id="e85f3-193">Name</span></span></th>
<th><span data-ttu-id="e85f3-194">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="e85f3-194">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e85f3-195">설명</span><span class="sxs-lookup"><span data-stu-id="e85f3-195">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e85f3-196"><strong>성공량</strong></span><span class="sxs-lookup"><span data-stu-id="e85f3-196"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e85f3-197">아니요</span><span class="sxs-lookup"><span data-stu-id="e85f3-197">No</span></span></p></td>
<td><p><span data-ttu-id="e85f3-198">성공한 총 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-198">Total number of successful conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e85f3-199"><strong>성공 비율</strong></span><span class="sxs-lookup"><span data-stu-id="e85f3-199"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e85f3-200">아니요</span><span class="sxs-lookup"><span data-stu-id="e85f3-200">No</span></span></p></td>
<td><p><span data-ttu-id="e85f3-201">중요 한 문제로 인해 완료 된 회의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-201">Percentage of conferences that completed with significant problems.</span></span> <span data-ttu-id="e85f3-202">성공량을 총 세션으로 나눠서 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-202">Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e85f3-203"><strong>예상 오류량</strong></span><span class="sxs-lookup"><span data-stu-id="e85f3-203"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e85f3-204">아니요</span><span class="sxs-lookup"><span data-stu-id="e85f3-204">No</span></span></p></td>
<td><p><span data-ttu-id="e85f3-205">예상 되는 오류가 발생 한 총 회의 수 &quot; &quot; 입니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-205">Total number of conferences where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="e85f3-p118">예상 오류는 발생할 것으로 예상된 오류입니다. 예를 들어 사용자가 자신의 상태를 방해 금지로 설정한 경우 해당 사용자에 대한 통화가 실패할 것으로 예상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e85f3-208"><strong>예상 오류 비율</strong></span><span class="sxs-lookup"><span data-stu-id="e85f3-208"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e85f3-209">아니요</span><span class="sxs-lookup"><span data-stu-id="e85f3-209">No</span></span></p></td>
<td><p><span data-ttu-id="e85f3-210">예상 되는 오류가 발생 한 전화 회의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-210">Percentage of conferences that experienced an expected error.</span></span> <span data-ttu-id="e85f3-211">예상 오류량을 총 세션으로 나눠서 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-211">Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e85f3-212"><strong>예기치 않은 오류량</strong></span><span class="sxs-lookup"><span data-stu-id="e85f3-212"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e85f3-213">아니요</span><span class="sxs-lookup"><span data-stu-id="e85f3-213">No</span></span></p></td>
<td><p><span data-ttu-id="e85f3-214">예기치 않은 오류가 발생 한 총 전화 회의 수 &quot; &quot; 입니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-214">Total number of conferences where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="e85f3-p120">예기치 않은 오류는 일반적으로 정상 상태의 시스템으로 보이지만 예기치 않게 발생한 오류입니다. 예를 들어 발신자가 보류 상태일 때는 통화가 종료되지 않아야 합니다. 하지만 통화가 종료되면 바로 예기치 않은 오류로 플래그 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e85f3-218"><strong>예기치 않은 오류 비율</strong></span><span class="sxs-lookup"><span data-stu-id="e85f3-218"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e85f3-219">아니요</span><span class="sxs-lookup"><span data-stu-id="e85f3-219">No</span></span></p></td>
<td><p><span data-ttu-id="e85f3-220">예기치 않은 오류가 발생 한 전화 회의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-220">Percentage of conferences that experienced an unexpected error.</span></span> <span data-ttu-id="e85f3-221">예기치 않은 오류량을 총 세션으로 나눠서 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-221">Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e85f3-222"><strong>총 세션</strong></span><span class="sxs-lookup"><span data-stu-id="e85f3-222"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e85f3-223">아니요</span><span class="sxs-lookup"><span data-stu-id="e85f3-223">No</span></span></p></td>
<td><p><span data-ttu-id="e85f3-224">성공적인 회의, 실패 한 회의 (예상 오류 및 예기치 않은 오류 모두) 및 분류 되지 않은 회의를 포함 한 총 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-224">Total number of conferences, including successful conferences, failed conferences (both expected failures and unexpected failures), and uncategorized conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

