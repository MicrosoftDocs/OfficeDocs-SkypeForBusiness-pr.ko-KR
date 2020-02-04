---
title: 'Lync Server 2013: 컨퍼런스 참가 시간 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cce80d3c61e94752423c70de9827d41243da7119
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="d9ffc-102">Lync Server 2013의 컨퍼런스 참가 시간 보고서</span><span class="sxs-lookup"><span data-stu-id="d9ffc-102">Conference Join Time Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9ffc-103">_**마지막으로 수정한 주제:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="d9ffc-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="d9ffc-104">컨퍼런스 참가 시간 요약을 통해 사용자가 회의에 참가 하는 데 걸리는 시간을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-104">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference.</span></span> <span data-ttu-id="d9ffc-105">이 보고서에는 평균 참가 시간 (밀리초)이 표시 되 고, 2 초 이내에 회의에 참가할 수 있는 사용자 수, 회의에 참가 하기 위해 2 ~ 5 초 사이에 필요한 사용자 수를 알 수 있는 분류도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-105">The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="d9ffc-106">컨퍼런스 참가 시간 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="d9ffc-106">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="d9ffc-107">회의 참가 시간 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-107">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d9ffc-108">필터가</span><span class="sxs-lookup"><span data-stu-id="d9ffc-108">Filters</span></span>

<span data-ttu-id="d9ffc-109">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-109">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="d9ffc-110">다음 표에는 컨퍼런스 참가 시간 보고서와 함께 사용할 수 있는 필터가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-110">The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="d9ffc-111">컨퍼런스 참가 시간 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="d9ffc-111">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9ffc-112">이름</span><span class="sxs-lookup"><span data-stu-id="d9ffc-112">Name</span></span></th>
<th><span data-ttu-id="d9ffc-113">설명</span><span class="sxs-lookup"><span data-stu-id="d9ffc-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9ffc-114"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="d9ffc-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="d9ffc-115">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-115">Start date/time for the time range.</span></span> <span data-ttu-id="d9ffc-116">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-116">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="d9ffc-117">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="d9ffc-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d9ffc-118">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-118">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="d9ffc-119">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-119">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d9ffc-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d9ffc-120">7/7/2012</span></span></p>
<p><span data-ttu-id="d9ffc-121">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="d9ffc-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d9ffc-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d9ffc-122">7/3/2012</span></span></p>
<p><span data-ttu-id="d9ffc-123">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9ffc-124"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="d9ffc-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="d9ffc-125">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-125">End date/time for the time range.</span></span> <span data-ttu-id="d9ffc-126">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-126">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="d9ffc-127">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="d9ffc-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d9ffc-128">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-128">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="d9ffc-129">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-129">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d9ffc-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d9ffc-130">7/7/2012</span></span></p>
<p><span data-ttu-id="d9ffc-131">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="d9ffc-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d9ffc-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d9ffc-132">7/3/2012</span></span></p>
<p><span data-ttu-id="d9ffc-133">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9ffc-134"><strong>간격만</strong></span><span class="sxs-lookup"><span data-stu-id="d9ffc-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="d9ffc-135">시간 간격.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-135">Time interval.</span></span> <span data-ttu-id="d9ffc-136">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-136">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d9ffc-137">매시간 (최대 25 시간 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d9ffc-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d9ffc-138">매일 (최대 31 일이 표시 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d9ffc-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d9ffc-139">주간 (최대 12 주를 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d9ffc-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d9ffc-140">월간 (최대 12 개월을 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d9ffc-140">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="d9ffc-141">시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-141">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="d9ffc-142">예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-142">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9ffc-143"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="d9ffc-143"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="d9ffc-144">등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-144">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="d9ffc-145">개별 풀을 선택 하거나 <strong>[모두]</strong> 를 클릭 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-145">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="d9ffc-146">이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-146">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9ffc-147"><strong>회의 세션</strong></span><span class="sxs-lookup"><span data-stu-id="d9ffc-147"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d9ffc-148">세션의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-148">Type of session.</span></span> <span data-ttu-id="d9ffc-149">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-149">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="d9ffc-150">모든</span><span class="sxs-lookup"><span data-stu-id="d9ffc-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="d9ffc-151">포커스 세션 (포커스는 온라인 모임에 대 한 중앙 정책 및 상태 관리자 이며, 회의의 모든 측면을 조정 합니다.)</span><span class="sxs-lookup"><span data-stu-id="d9ffc-151">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="d9ffc-152">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="d9ffc-152">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="d9ffc-153">A/V 회의</span><span class="sxs-lookup"><span data-stu-id="d9ffc-153">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="d9ffc-154">[모두]를 선택 하면 총 컨퍼런스 참가 시간이 보고서의 맨 위에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-154">If you select [All], the total conference join time will be displayed at the top of the report.</span></span> <span data-ttu-id="d9ffc-155">이러한 합계는 Microsoft Exchange 또는 Microsoft Outlook을 사용 하 여 예약한 회의에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-155">Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="d9ffc-156">매트릭스</span><span class="sxs-lookup"><span data-stu-id="d9ffc-156">Metrics</span></span>

<span data-ttu-id="d9ffc-157">다음 표에는 컨퍼런스 참가 시간 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-157">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="d9ffc-158">컨퍼런스 참가 시간 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="d9ffc-158">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9ffc-159">이름</span><span class="sxs-lookup"><span data-stu-id="d9ffc-159">Name</span></span></th>
<th><span data-ttu-id="d9ffc-160">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="d9ffc-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d9ffc-161">설명</span><span class="sxs-lookup"><span data-stu-id="d9ffc-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9ffc-162"><strong>시작일</strong></span><span class="sxs-lookup"><span data-stu-id="d9ffc-162"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="d9ffc-163">이 메트릭의 실제 제목은 선택한 간격에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-163">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="d9ffc-164">아니요</span><span class="sxs-lookup"><span data-stu-id="d9ffc-164">No</span></span></p></td>
<td><p><span data-ttu-id="d9ffc-165">회의가 발생 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-165">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9ffc-166"><strong>총 세션</strong></span><span class="sxs-lookup"><span data-stu-id="d9ffc-166"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d9ffc-167">아니요</span><span class="sxs-lookup"><span data-stu-id="d9ffc-167">No</span></span></p></td>
<td><p><span data-ttu-id="d9ffc-168">성공한 세션, 실패 한 세션 (예상 되는 실패 및 예기치 못한 실패), 범주화 되지 않은 세션 등의 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-168">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9ffc-169"><strong>평균 (밀리초)</strong></span><span class="sxs-lookup"><span data-stu-id="d9ffc-169"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="d9ffc-170">아니요</span><span class="sxs-lookup"><span data-stu-id="d9ffc-170">No</span></span></p></td>
<td><p><span data-ttu-id="d9ffc-171">참가자가 회의에 참가 하는 데 걸린 평균 시간 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-171">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9ffc-172"><strong>세션 &lt; 2 초, 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="d9ffc-172"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="d9ffc-173">아니요</span><span class="sxs-lookup"><span data-stu-id="d9ffc-173">No</span></span></p></td>
<td><p><span data-ttu-id="d9ffc-174">2 초 이내로 회의에 참가할 수 있는 참가자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-174">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9ffc-175"><strong>세션 &lt; 2 초, 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="d9ffc-175"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="d9ffc-176">아니요</span><span class="sxs-lookup"><span data-stu-id="d9ffc-176">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9ffc-177"><strong>세션 2-5 초, 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="d9ffc-177"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="d9ffc-178">아니요</span><span class="sxs-lookup"><span data-stu-id="d9ffc-178">No</span></span></p></td>
<td><p><span data-ttu-id="d9ffc-179">회의에 참가 하는 데 2 초와 5 초 사이에 걸린 참가자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-179">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9ffc-180"><strong>세션 2-5 초, 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="d9ffc-180"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="d9ffc-181">아니요</span><span class="sxs-lookup"><span data-stu-id="d9ffc-181">No</span></span></p></td>
<td><p><span data-ttu-id="d9ffc-182">회의에 참가 하기 위해 2 초와 5 초 사이에 걸린 총 통화 참가자의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-182">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9ffc-183"><strong>세션 5-10 초, 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="d9ffc-183"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="d9ffc-184">아니요</span><span class="sxs-lookup"><span data-stu-id="d9ffc-184">No</span></span></p></td>
<td><p><span data-ttu-id="d9ffc-185">회의에 참가 하는 데 5 초에서 10 초가 소요 되는 참가자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-185">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9ffc-186"><strong>세션 5-10 초, 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="d9ffc-186"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="d9ffc-187">아니요</span><span class="sxs-lookup"><span data-stu-id="d9ffc-187">No</span></span></p></td>
<td><p><span data-ttu-id="d9ffc-188">회의에 참가 하는 데 5 초에서 10 초가 소요 되는 총 통화 참가자의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-188">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9ffc-189"><strong>세션 &gt; 10 초, 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="d9ffc-189"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="d9ffc-190">아니요</span><span class="sxs-lookup"><span data-stu-id="d9ffc-190">No</span></span></p></td>
<td><p><span data-ttu-id="d9ffc-191">회의에 참가 하는 데 10 초가 소요 되는 참가자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-191">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9ffc-192"><strong>세션 &gt; 10 초, 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="d9ffc-192"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="d9ffc-193">아니요</span><span class="sxs-lookup"><span data-stu-id="d9ffc-193">No</span></span></p></td>
<td><p><span data-ttu-id="d9ffc-194">전화 회의에 참가 하는 데 10 초가 소요 되는 총 통화 참가자의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="d9ffc-194">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

