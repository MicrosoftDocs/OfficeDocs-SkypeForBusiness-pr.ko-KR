---
title: 'Lync Server 2013: 회의 참가 시간 보고서'
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
ms.openlocfilehash: e11932d1f63e6d756b0a3a5ba1eb7b33498dac61
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="62321-102">Lync Server 2013의 회의 참가 시간 보고서</span><span class="sxs-lookup"><span data-stu-id="62321-102">Conference Join Time Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62321-103">_**마지막으로 수정 된 항목:** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="62321-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="62321-104">회의 참가 시간 요약을 사용 하면 사용자가 회의에 참가 하는 데 걸리는 시간을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62321-104">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference.</span></span> <span data-ttu-id="62321-105">이 보고서에는 평균 참가 시간 (밀리초)이 표시 되 고, 2 초 이내에 회의에 참가할 수 있었던 사용자 수, 회의에 참가 하는 데 2 ~ 5 초 사이에 필요한 사용자 수를 알 수 있는 분류도 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62321-105">The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="62321-106">회의 참가 시간 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="62321-106">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="62321-107">회의 참가 시간 보고서는 모니터링 보고서 홈 페이지에서 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="62321-107">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="62321-108">필터</span><span class="sxs-lookup"><span data-stu-id="62321-108">Filters</span></span>

<span data-ttu-id="62321-109">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62321-109">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="62321-110">다음 표에서는 회의 참가 시간 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="62321-110">The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="62321-111">회의 참가 시간 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="62321-111">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62321-112">이름</span><span class="sxs-lookup"><span data-stu-id="62321-112">Name</span></span></th>
<th><span data-ttu-id="62321-113">설명</span><span class="sxs-lookup"><span data-stu-id="62321-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62321-114"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="62321-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="62321-p103">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="62321-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="62321-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="62321-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="62321-p104">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="62321-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="62321-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="62321-120">7/7/2012</span></span></p>
<p><span data-ttu-id="62321-121">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62321-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="62321-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="62321-122">7/3/2012</span></span></p>
<p><span data-ttu-id="62321-123">주는 항상 일요일부터 토요일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="62321-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62321-124"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="62321-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="62321-p105">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="62321-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="62321-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="62321-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="62321-p106">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="62321-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="62321-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="62321-130">7/7/2012</span></span></p>
<p><span data-ttu-id="62321-131">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62321-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="62321-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="62321-132">7/3/2012</span></span></p>
<p><span data-ttu-id="62321-133">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="62321-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62321-134"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="62321-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="62321-p107">시간 간격입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="62321-p107">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="62321-137">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="62321-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="62321-138">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="62321-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="62321-139">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="62321-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="62321-140">월별(최대 12개월 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="62321-140">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="62321-p108">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="62321-p108">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62321-143"><strong>그룹</strong></span><span class="sxs-lookup"><span data-stu-id="62321-143"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="62321-p109">등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="62321-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62321-147"><strong>회의 세션</strong></span><span class="sxs-lookup"><span data-stu-id="62321-147"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="62321-148">세션 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="62321-148">Type of session.</span></span> <span data-ttu-id="62321-149">허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="62321-149">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="62321-150">모든</span><span class="sxs-lookup"><span data-stu-id="62321-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="62321-151">포커스 세션 (온라인 모임에 대 한 중앙 정책 및 상태 관리자, 그리고 회의의 모든 측면을 조정 하는 포커스)</span><span class="sxs-lookup"><span data-stu-id="62321-151">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="62321-152">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="62321-152">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="62321-153">A/V 회의</span><span class="sxs-lookup"><span data-stu-id="62321-153">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="62321-154">[모두]를 선택 하면 총 회의 참가 시간이 보고서 위쪽에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62321-154">If you select [All], the total conference join time will be displayed at the top of the report.</span></span> <span data-ttu-id="62321-155">이러한 합계는 Microsoft Exchange 또는 Microsoft Outlook을 사용 하 여 예약 된 회의에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62321-155">Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="62321-156">선별한</span><span class="sxs-lookup"><span data-stu-id="62321-156">Metrics</span></span>

<span data-ttu-id="62321-157">다음 표에서는 회의 참가 시간 보고서에 제공 된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="62321-157">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="62321-158">회의 참가 시간 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="62321-158">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="62321-159">이름</span><span class="sxs-lookup"><span data-stu-id="62321-159">Name</span></span></th>
<th><span data-ttu-id="62321-160">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="62321-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="62321-161">설명</span><span class="sxs-lookup"><span data-stu-id="62321-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="62321-162"><strong>날짜</strong></span><span class="sxs-lookup"><span data-stu-id="62321-162"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="62321-163">이 메트릭에 대 한 실제 제목은 선택 된 간격에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="62321-163">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="62321-164">아니요</span><span class="sxs-lookup"><span data-stu-id="62321-164">No</span></span></p></td>
<td><p><span data-ttu-id="62321-165">회의가 발생 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="62321-165">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62321-166"><strong>총 세션</strong></span><span class="sxs-lookup"><span data-stu-id="62321-166"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="62321-167">아니요</span><span class="sxs-lookup"><span data-stu-id="62321-167">No</span></span></p></td>
<td><p><span data-ttu-id="62321-168">성공한 세션, 실패한 세션(예상 오류 및 예기치 않은 오류 모두) 및 분류되지 않은 세션을 포함한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="62321-168">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62321-169"><strong>평균 (밀리초)</strong></span><span class="sxs-lookup"><span data-stu-id="62321-169"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="62321-170">아니요</span><span class="sxs-lookup"><span data-stu-id="62321-170">No</span></span></p></td>
<td><p><span data-ttu-id="62321-171">참가자가 회의에 참가 하는 데 걸린 평균 시간 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="62321-171">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62321-172"><strong>세션 &lt; 2 초, 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="62321-172"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="62321-173">아니요</span><span class="sxs-lookup"><span data-stu-id="62321-173">No</span></span></p></td>
<td><p><span data-ttu-id="62321-174">2 초 이내에 회의에 참가할 수 있었던 참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="62321-174">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62321-175"><strong>세션 &lt; 2 초, 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="62321-175"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="62321-176">아니요</span><span class="sxs-lookup"><span data-stu-id="62321-176">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62321-177"><strong>세션 2-5 초, 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="62321-177"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="62321-178">아니요</span><span class="sxs-lookup"><span data-stu-id="62321-178">No</span></span></p></td>
<td><p><span data-ttu-id="62321-179">회의에 참가 하는 데 2 ~ 5 초가 소요 된 참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="62321-179">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62321-180"><strong>세션 2-5 초, 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="62321-180"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="62321-181">아니요</span><span class="sxs-lookup"><span data-stu-id="62321-181">No</span></span></p></td>
<td><p><span data-ttu-id="62321-182">회의에 참가 하는 데 2 ~ 5 초가 소요 된 총 통화 참가자 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="62321-182">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62321-183"><strong>세션 5-10 초, 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="62321-183"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="62321-184">아니요</span><span class="sxs-lookup"><span data-stu-id="62321-184">No</span></span></p></td>
<td><p><span data-ttu-id="62321-185">회의에 참가 하는 데 5 ~ 10 초가 소요 된 참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="62321-185">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62321-186"><strong>세션 5-10 초, 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="62321-186"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="62321-187">아니요</span><span class="sxs-lookup"><span data-stu-id="62321-187">No</span></span></p></td>
<td><p><span data-ttu-id="62321-188">회의에 참가 하는 데 5 ~ 10 초가 소요 된 총 통화 참가자 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="62321-188">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="62321-189"><strong>세션 &gt; 10 초, 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="62321-189"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="62321-190">아니요</span><span class="sxs-lookup"><span data-stu-id="62321-190">No</span></span></p></td>
<td><p><span data-ttu-id="62321-191">회의에 참가 하는 데 10 초 이상이 소요 된 참가자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="62321-191">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="62321-192"><strong>세션 &gt; 10 초, 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="62321-192"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="62321-193">아니요</span><span class="sxs-lookup"><span data-stu-id="62321-193">No</span></span></p></td>
<td><p><span data-ttu-id="62321-194">회의에 참가 하는 데 10 초 이상이 소요 된 총 통화 참가자 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="62321-194">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

