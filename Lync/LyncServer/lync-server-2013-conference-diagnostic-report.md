---
title: 'Lync Server 2013: 컨퍼런스 진단 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279d844a4c67d3b09b35fff92f6868cae8971059
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="4155e-102">Lync Server 2013의 컨퍼런스 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="4155e-102">Conference Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4155e-103">_**마지막으로 수정한 주제:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="4155e-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="4155e-104">컨퍼런스 진단 보고서는 모든 회의 세션의 성공 및 실패에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-104">The Conference Diagnostic Report provides information about the success and failure of all conferencing sessions.</span></span> <span data-ttu-id="4155e-105">Microsoft Lync Server는 서로 다른 종류의 오류를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-105">Note that Microsoft Lync Server distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="4155e-106">**오류가 발생**했습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-106">**Expected failure**.</span></span> <span data-ttu-id="4155e-107">일반적으로 예상 되는 오류는 대부분의 기술적인 측면 에서만 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="4155e-108">예를 들어 누군가 회의를 시작 하 고 누구나 참가할 수 있도록 하기 위해 연결이 중단 되었다고 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="4155e-108">For example, suppose someone starts a conference but hangs up before anyone can join.</span></span> <span data-ttu-id="4155e-109">기술적으로 실패 하는 문제: 회의가 시작 되었지만 완료 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-109">Technically that's a failure: the conference was initiated, but not completed.</span></span> <span data-ttu-id="4155e-110">그러나 모든 사용자가 참가 하기 전에 회의가 취소 되 면 해당 회의가 완료 되지 않을 것으로 예상 하는 것이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-110">However, that's a failure that you would expect to happen: if the organizer cancels the conference before anyone can join then you would not expect that conference to be completed.</span></span>

  - <span data-ttu-id="4155e-111">**예기치 않은 오류**.</span><span class="sxs-lookup"><span data-stu-id="4155e-111">**Unexpected failure**.</span></span> <span data-ttu-id="4155e-112">예기치 않은 오류는 상황에 따라 발생 하는 것으로 예상 되지 않는 오류를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-112">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="4155e-113">예를 들어 이끌이 모임 정책을 검색할 수 없기 때문에 회의를 받을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-113">For example, suppose a conference could not be held because the organizer's meeting policy could not be retrieved.</span></span> <span data-ttu-id="4155e-114">예기치 않은 오류: 이제 항상 사용자의 모임 정책을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-114">That's an unexpected error: after all, you should always be able to retrieve a user's meeting policy.</span></span>

<span data-ttu-id="4155e-115">성공, 예상 실패, 예기치 않은 실패 메트릭이 총 세션 메트릭에 추가 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-115">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric.</span></span> <span data-ttu-id="4155e-116">예를 들어 보고서에 다음 값이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-116">For example, you might see the following values in the Report:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4155e-117">회의</span><span class="sxs-lookup"><span data-stu-id="4155e-117">Successes</span></span></th>
<th><span data-ttu-id="4155e-118">예상 되는 오류</span><span class="sxs-lookup"><span data-stu-id="4155e-118">Expected failures</span></span></th>
<th><span data-ttu-id="4155e-119">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="4155e-119">Unexpected failures</span></span></th>
<th><span data-ttu-id="4155e-120">총 세션</span><span class="sxs-lookup"><span data-stu-id="4155e-120">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4155e-121">2024</span><span class="sxs-lookup"><span data-stu-id="4155e-121">2024</span></span></p></td>
<td><p><span data-ttu-id="4155e-122">469</span><span class="sxs-lookup"><span data-stu-id="4155e-122">469</span></span></p></td>
<td><p><span data-ttu-id="4155e-123">16</span><span class="sxs-lookup"><span data-stu-id="4155e-123">16</span></span></p></td>
<td><p><span data-ttu-id="4155e-124">2521</span><span class="sxs-lookup"><span data-stu-id="4155e-124">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4155e-125">2024 + 469 + 16을 추가 하는 경우 총 2509 세션을 받을 수 있지만 총 세션 열에는 총 2521 세션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-125">If you add 2024 + 469 + 16 you get a total of 2,509 sessions and yet, the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="4155e-126">"누락 된" 12 개의 세션은 시스템에서 성공 또는 실패로 분류할 수 없는 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-126">The "missing" 12 sessions for are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="4155e-127">이는 타사 제품에 모니터링 서버에 익숙하지 않은 새로운 진단 코드가 도입 된 경우에 해당 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-127">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Monitoring Server.</span></span> <span data-ttu-id="4155e-128">이 경우 해당 제품을 사용 하 여 호출 하 고 해당 진단 코드를 보고 하면 항상 성공, 실패 또는 예기치 않은 오류에 대 한 분류할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-128">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-conference-diagnostic-report"></a><span data-ttu-id="4155e-129">컨퍼런스 진단 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="4155e-129">Accessing the Conference Diagnostic Report</span></span>

<span data-ttu-id="4155e-130">모니터링 보고서 홈 페이지에서 전화 회의 진단 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-130">The Conference Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="4155e-131">다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 실패 배포 보고서](lync-server-2013-failure-distribution-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-131">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="4155e-132">예기치 않은 오류 볼륨</span><span class="sxs-lookup"><span data-stu-id="4155e-132">Unexpected failure volume</span></span>

  - <span data-ttu-id="4155e-133">예상 고장 볼륨</span><span class="sxs-lookup"><span data-stu-id="4155e-133">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a><span data-ttu-id="4155e-134">컨퍼런스 진단 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="4155e-134">Making the Best Use of the Conference Diagnostic Report</span></span>

<span data-ttu-id="4155e-135">회의 진단 보고서에 일련의 그래프가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-135">The Conference Diagnostic Report includes a series of graphs.</span></span> <span data-ttu-id="4155e-136">그래프에 표시 되는 각 열은 실제로 하이퍼링크입니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-136">Each of the columns shown in the graph is actually a hyperlink.</span></span> <span data-ttu-id="4155e-137">열을 클릭 하면 [Lync Server 2013에서](lync-server-2013-failure-distribution-report.md) 해당 기간 및 해당 전화 형식의 실패 배포 보고서로 드릴 다운 합니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-137">If you click a column, you'll drill down to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) for that time period and that conference type.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4155e-138">필터가</span><span class="sxs-lookup"><span data-stu-id="4155e-138">Filters</span></span>

<span data-ttu-id="4155e-139">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-139">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="4155e-140">예를 들어 회의 진단 보고서를 사용 하면 수행 중인 회의 유형 (예: 포커스 기반 컨퍼런스) 또는 회의에 사용 되는 Edge 서버를 기준으로 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-140">For example, the Conference Diagnostic Report enables you to filter on such things as the type of conference being conducted (for example, a Focus-based conference) or by the Edge Server used in the conference.</span></span> <span data-ttu-id="4155e-141">데이터 그룹화 방법을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-141">You can also choose how data should be grouped.</span></span> <span data-ttu-id="4155e-142">이 경우 회의는 시간, 일, 주 또는 월로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-142">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="4155e-143">다음 표에는 컨퍼런스 진단 보고서에 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-143">The following table lists the filters that you can use with the Conference Diagnostic Report.</span></span>

### <a name="conference-diagnostic-report-filters"></a><span data-ttu-id="4155e-144">컨퍼런스 진단 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="4155e-144">Conference Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4155e-145">이름</span><span class="sxs-lookup"><span data-stu-id="4155e-145">Name</span></span></th>
<th><span data-ttu-id="4155e-146">설명</span><span class="sxs-lookup"><span data-stu-id="4155e-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4155e-147"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="4155e-147"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4155e-148">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-148">Start date/time for the time range.</span></span> <span data-ttu-id="4155e-149">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-149">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4155e-150">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="4155e-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4155e-151">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-151">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="4155e-152">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-152">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4155e-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4155e-153">7/7/2012</span></span></p>
<p><span data-ttu-id="4155e-154">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="4155e-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4155e-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4155e-155">7/3/2012</span></span></p>
<p><span data-ttu-id="4155e-156">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4155e-157"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="4155e-157"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4155e-158">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-158">End date/time for the time range.</span></span> <span data-ttu-id="4155e-159">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-159">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4155e-160">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="4155e-160">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4155e-161">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-161">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="4155e-162">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-162">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4155e-163">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4155e-163">7/7/2012</span></span></p>
<p><span data-ttu-id="4155e-164">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="4155e-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4155e-165">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4155e-165">7/3/2012</span></span></p>
<p><span data-ttu-id="4155e-166">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4155e-167"><strong>간격만</strong></span><span class="sxs-lookup"><span data-stu-id="4155e-167"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="4155e-168">시간 간격.</span><span class="sxs-lookup"><span data-stu-id="4155e-168">Time interval.</span></span> <span data-ttu-id="4155e-169">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-169">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4155e-170">매시간 (최대 25 시간 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="4155e-170">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4155e-171">매일 (최대 31 일이 표시 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="4155e-171">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4155e-172">주간 (최대 12 주를 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="4155e-172">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4155e-173">월간 (최대 12 개월을 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="4155e-173">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="4155e-174">시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-174">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="4155e-175">예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-175">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4155e-176"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="4155e-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="4155e-177">등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-177">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="4155e-178">개별 풀을 선택 하거나 <strong>[모두]</strong> 를 클릭 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-178">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="4155e-179">이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-179">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4155e-180"><strong>회의 세션</strong></span><span class="sxs-lookup"><span data-stu-id="4155e-180"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="4155e-181">회의 세션의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-181">Indicates the type of conferencing session.</span></span> <span data-ttu-id="4155e-182">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-182">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4155e-183">모든</span><span class="sxs-lookup"><span data-stu-id="4155e-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="4155e-184">포커스 세션</span><span class="sxs-lookup"><span data-stu-id="4155e-184">Focus sessions</span></span></p></li>
<li><p><span data-ttu-id="4155e-185">모든 MCU 세션</span><span class="sxs-lookup"><span data-stu-id="4155e-185">All MCU sessions</span></span></p></li>
<li><p><span data-ttu-id="4155e-186">메신저 대화 회의</span><span class="sxs-lookup"><span data-stu-id="4155e-186">IM conferencing</span></span></p></li>
<li><p><span data-ttu-id="4155e-187">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="4155e-187">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="4155e-188">A/V 회의</span><span class="sxs-lookup"><span data-stu-id="4155e-188">A/V conferencing</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="4155e-189">매트릭스</span><span class="sxs-lookup"><span data-stu-id="4155e-189">Metrics</span></span>

<span data-ttu-id="4155e-190">다음 표에는 각 회의 세션 유형에 대해 회의 진단 보고서에서 제공 하는 정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-190">The following table lists the information provided in the Conference Diagnostic Report for each type of conferencing session.</span></span>

### <a name="conference-diagnostic-report-metrics"></a><span data-ttu-id="4155e-191">컨퍼런스 진단 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="4155e-191">Conference Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4155e-192">이름</span><span class="sxs-lookup"><span data-stu-id="4155e-192">Name</span></span></th>
<th><span data-ttu-id="4155e-193">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="4155e-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4155e-194">설명</span><span class="sxs-lookup"><span data-stu-id="4155e-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4155e-195"><strong>성공 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="4155e-195"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4155e-196">아니요</span><span class="sxs-lookup"><span data-stu-id="4155e-196">No</span></span></p></td>
<td><p><span data-ttu-id="4155e-197">성공한 총 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-197">Total number of successful conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4155e-198"><strong>성공 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="4155e-198"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4155e-199">아니요</span><span class="sxs-lookup"><span data-stu-id="4155e-199">No</span></span></p></td>
<td><p><span data-ttu-id="4155e-200">중대 한 문제에 대해 완료 된 회의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-200">Percentage of conferences that completed with significant problems.</span></span> <span data-ttu-id="4155e-201">성공 볼륨을 총 세션으로 나누는 방법으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-201">Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4155e-202"><strong>예상 고장 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="4155e-202"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4155e-203">아니요</span><span class="sxs-lookup"><span data-stu-id="4155e-203">No</span></span></p></td>
<td><p><span data-ttu-id="4155e-204">예상 되는 오류가 &quot;&quot; 발생 한 총 컨퍼런스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-204">Total number of conferences where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="4155e-205">예상 되는 실패는 예상 되는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-205">An expected failure is a failure that is expected to happen.</span></span> <span data-ttu-id="4155e-206">예를 들어 사용자가 자신의 상태를 방해 금지로 설정 하면 해당 사용자에 게 전화를 거는 데 실패 하는 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-206">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4155e-207"><strong>예상 되는 실패 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="4155e-207"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4155e-208">아니요</span><span class="sxs-lookup"><span data-stu-id="4155e-208">No</span></span></p></td>
<td><p><span data-ttu-id="4155e-209">예상 되는 오류가 발생 한 회의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-209">Percentage of conferences that experienced an expected error.</span></span> <span data-ttu-id="4155e-210">예상 고장 볼륨을 총 세션으로 나누어 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-210">Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4155e-211"><strong>예기치 않은 오류 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="4155e-211"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="4155e-212">아니요</span><span class="sxs-lookup"><span data-stu-id="4155e-212">No</span></span></p></td>
<td><p><span data-ttu-id="4155e-213">예기치 않은 오류가 &quot;&quot; 발생 한 총 컨퍼런스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-213">Total number of conferences where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="4155e-214">예기치 않은 오류가 발생 하는 것은 정상적인 시스템 때문 이라고 표시 되는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-214">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="4155e-215">예를 들어 호출자가 대기 상태로 설정 된 경우에는 통화가 종료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-215">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="4155e-216">이 문제가 발생 하면 예기치 않은 오류로 플래그가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-216">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4155e-217"><strong>예기치 않은 오류 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="4155e-217"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="4155e-218">아니요</span><span class="sxs-lookup"><span data-stu-id="4155e-218">No</span></span></p></td>
<td><p><span data-ttu-id="4155e-219">예기치 않은 오류가 발생 한 회의의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-219">Percentage of conferences that experienced an unexpected error.</span></span> <span data-ttu-id="4155e-220">예상 하지 못한 볼륨을 총 세션으로 나누면 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-220">Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4155e-221"><strong>총 세션</strong></span><span class="sxs-lookup"><span data-stu-id="4155e-221"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="4155e-222">아니요</span><span class="sxs-lookup"><span data-stu-id="4155e-222">No</span></span></p></td>
<td><p><span data-ttu-id="4155e-223">성공적인 컨퍼런스, 실패 한 컨퍼런스 (예상 오류 및 예기치 못한 오류 모두 포함), 범주화 되지 않은 회의 등의 총 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4155e-223">Total number of conferences, including successful conferences, failed conferences (both expected failures and unexpected failures), and uncategorized conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

