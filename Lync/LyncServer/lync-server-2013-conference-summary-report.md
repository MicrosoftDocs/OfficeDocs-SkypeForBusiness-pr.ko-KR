---
title: 'Lync Server 2013: 전화 회의 요약 보고서'
description: 'Lync Server 2013: 전화 회의 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d9c0b8ad7280d2c7336282c14f46e6b5d6a1aec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550714"
---
# <a name="conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="27b56-103">Lync Server 2013의 전화 회의 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="27b56-103">Conference Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27b56-104">_**마지막으로 수정 된 항목:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="27b56-104">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="27b56-105">회의 요약 보고서에서는 온라인 회의 세션에 대한 전반적인 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-105">The Conference Summary Report provides an overall view of your online conferencing sessions.</span></span> <span data-ttu-id="27b56-106">일반적으로 회의에는 사용자가 2 명 이상 포함 되며 Microsoft Lync Server 2013 회의 서비스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-106">A conference typically involves more than 2 users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="27b56-107">비교적 피어 투 피어 세션에서는 일반적으로 사용자가 2명만 포함되며 Lync Server의 회의 서비스를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-107">By comparison, a peer-to-peer session typically involves just 2 users and does not require the use of Lync Server's conferencing services.</span></span> <span data-ttu-id="27b56-108">피어 투 피어 활동은 [Lync Server 2013의 피어 투 피어 활동 요약 보고서](lync-server-2013-peer-to-peer-activity-summary-report.md)에 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-108">Peer-to-peer activities are reported on the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span></span>

<span data-ttu-id="27b56-109">전화 회의 요약 보고서에는 특정 기간 (매시간, 매일, 매주, 매월) 동안 개최 된 회의 수를 알려 주고 해당 회의에 참가 한 총 사용자 수 및 고유한 회의 이끌이 총 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-109">The Conference Summary Report not only tells you how many conferences were held during a given time period (hourly, daily, weekly, monthly) but also tells you the total number of people who took part in those conferences, and the total number of unique conference organizers.</span></span>

<span data-ttu-id="27b56-p102">"고유한" 이끌이란 적어도 하나 이상의 회의를 예약한 모든 사람을 의미합니다. 예를 들어 Pilar Ackerman이 하나의 회의를 예약했다면 한 명의 고유한 이끌이가 됩니다. Ken Myer가 148개의 회의를 예약했어도 한 명의 고유한 이끌이로 계산됩니다. 예를 들어, 아래 표에는 8개의 예약된 회의가 표시되지만 고유한 이끌이는 단 3명인 Ken Myer, Pilar Ackerman 및 David Ahs뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-p102">A "unique” organizer is anyone who schedules at least one conference. For example, if Pilar Ackerman schedules one conference she counts as one unique organizer. If Ken Myer schedules 148 conferences he, too counts as one unique organizer. For example, the table below shows 8 conferences scheduled, but just three unique organizers (Ken Myer, Pilar Ackerman, and David Ahs).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27b56-114">회의 이끌이</span><span class="sxs-lookup"><span data-stu-id="27b56-114">Conference Organizer</span></span></th>
<th><span data-ttu-id="27b56-115">회의 날짜</span><span class="sxs-lookup"><span data-stu-id="27b56-115">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27b56-116">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="27b56-116">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="27b56-117">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="27b56-117">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27b56-118">David Ahs</span><span class="sxs-lookup"><span data-stu-id="27b56-118">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="27b56-119">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="27b56-119">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27b56-120">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="27b56-120">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="27b56-121">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="27b56-121">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27b56-122">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="27b56-122">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="27b56-123">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="27b56-123">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27b56-124">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="27b56-124">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="27b56-125">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="27b56-125">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27b56-126">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="27b56-126">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="27b56-127">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="27b56-127">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27b56-128">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="27b56-128">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="27b56-129">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="27b56-129">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27b56-130">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="27b56-130">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="27b56-131">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="27b56-131">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="27b56-132">회의 요약 보고서에는 또한 오디오 및/또는 비디오가 포함된 회의 개수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-132">The Conference Summary Report also indicates how many conferences included audio and/or video.</span></span>

<div>

## <a name="accessing-the-conference-summary-report"></a><span data-ttu-id="27b56-133">회의 요약 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="27b56-133">Accessing the Conference Summary Report</span></span>

<span data-ttu-id="27b56-p103">회의 요약 보고서는 모니터링 보고서 홈 페이지에서 액세스됩니다. 다음 메트릭 중 하나를 클릭하여 회의 활동 보고서로 드릴다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-p103">The Conference Summary Report is accessed from the Monitoring Reports home page. You can drill down to the Conference Activity report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="27b56-136">총 회의</span><span class="sxs-lookup"><span data-stu-id="27b56-136">Total conferences</span></span>

  - <span data-ttu-id="27b56-137">총 참가자</span><span class="sxs-lookup"><span data-stu-id="27b56-137">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a><span data-ttu-id="27b56-138">회의 요약 보고서의 모범 사례 만들기</span><span class="sxs-lookup"><span data-stu-id="27b56-138">Making the Best Use of the Conference Summary Report</span></span>

<span data-ttu-id="27b56-p104">회의 요약 보고서에 사용된 대부분의 메트릭에 대한 총 값은 보고서 아래에서 찾을 수 있습니다. 지정된 기간 동안 수행된 총 회의 수 및 이러한 회의에 참가한 총 사용자 수와 같은 값을 보려면 아래로 스크롤합니다. 보고서 아래에 합계로 표시되지 않는 메트릭은 총 고유한 회의 이끌이입니다. 왜 그럴까요? 이유가 있습니다. 1개월 분량의 데이터를 조사한다고 가정해보십시오. 1일째에는 고유한 회의 이끌이 수가 34명이고, 2일째에는 고유한 회의 이끌이 수가 27명입니다. 그러면 이 이틀 동안의 고유한 회의 이끌이 수는 61명일까요? 반드시 그렇지는 않을 것입니다. 2일째에 회의를 주최한 27명이 모두 그 전날에 회의를 주최한 34명에 포함될 수도 있습니다. 예를 들어 여기에 표시된 간단한 보고서에서도 Ken Myer와 Pilar Ackerman은 7/7/2012 및 7/2/2012에 회의를 예약했습니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-p104">Total values for most of the metrics used on the Conference Summary Report can be found at the bottom of the report; scroll down to see values such as the total number of conferences held during the specified time period, and the total number of people who participated in those conferences. One metric that is not totaled at the bottom of the report is Total unique conference organizers. Why not? Here’s one reason. Suppose you are looking at a month's worth of data. On day 1 you had 34 unique conference organizers; on day 2 you had 27 unique conference organizers. Does that mean you had 61 unique conference organizers for those two days? Not necessarily. After all, all 27 people who organized conferences on day 2 might be among the 34 people who organized conferences on day 1. For example, in this simple report, note that Ken Myer and Pilar Ackerman scheduled conferences both on 7/7/2012 and on 7/2/2012:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27b56-149">회의 이끌이</span><span class="sxs-lookup"><span data-stu-id="27b56-149">Conference Organizer</span></span></th>
<th><span data-ttu-id="27b56-150">회의 날짜</span><span class="sxs-lookup"><span data-stu-id="27b56-150">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27b56-151">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="27b56-151">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="27b56-152">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="27b56-152">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27b56-153">David Ahs</span><span class="sxs-lookup"><span data-stu-id="27b56-153">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="27b56-154">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="27b56-154">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27b56-155">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="27b56-155">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="27b56-156">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="27b56-156">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27b56-157">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="27b56-157">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="27b56-158">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="27b56-158">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27b56-159">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="27b56-159">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="27b56-160">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="27b56-160">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27b56-161">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="27b56-161">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="27b56-162">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="27b56-162">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27b56-163">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="27b56-163">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="27b56-164">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="27b56-164">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27b56-165">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="27b56-165">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="27b56-166">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="27b56-166">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="27b56-167">회의를 주최한 고유한 사용자의 총 수를 보다 쉽게 이해하기 위해 시간 간격을 바꿔보겠습니다. 예를 들어 하루가 아니라 한 달을 기준으로 데이터를 살펴 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-167">To get a better idea of the total number of unique users who organized conferences, change your time interval; for example, look at the data by month instead of by day.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="27b56-168">필터</span><span class="sxs-lookup"><span data-stu-id="27b56-168">Filters</span></span>

<span data-ttu-id="27b56-p105">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 전화 회의 요약 보고서에서는 데이터의 그룹화 방법을 선택할 수 있습니다. 이 경우 전화 회의는 시간, 일, 주 또는 월별로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Summary Report enables you to choose how data should be grouped. In this case, conferences grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="27b56-172">다음 표에서는 전화 회의 요약 보고서에서 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-172">The following table lists the filters that you can use with the Conference Summary Report.</span></span>

### <a name="conference-summary-report-filters"></a><span data-ttu-id="27b56-173">전화 회의 요약 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="27b56-173">Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27b56-174">이름</span><span class="sxs-lookup"><span data-stu-id="27b56-174">Name</span></span></th>
<th><span data-ttu-id="27b56-175">설명</span><span class="sxs-lookup"><span data-stu-id="27b56-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27b56-176"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="27b56-176"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="27b56-p106">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="27b56-179">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="27b56-179">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="27b56-p107">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="27b56-182">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="27b56-182">7/7/2012</span></span></p>
<p><span data-ttu-id="27b56-183">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-183">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="27b56-184">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="27b56-184">7/3/2012</span></span></p>
<p><span data-ttu-id="27b56-185">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-185">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27b56-186"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="27b56-186"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="27b56-p108">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="27b56-189">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="27b56-189">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="27b56-p109">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="27b56-192">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="27b56-192">7/7/2012</span></span></p>
<p><span data-ttu-id="27b56-193">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-193">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="27b56-194">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="27b56-194">7/3/2012</span></span></p>
<p><span data-ttu-id="27b56-195">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-195">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27b56-196"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="27b56-196"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="27b56-p110">시간 간격입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="27b56-199">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="27b56-199">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="27b56-200">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="27b56-200">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="27b56-201">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="27b56-201">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="27b56-202">월별(최대 12개월 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="27b56-202">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="27b56-p111">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="27b56-205">메트릭</span><span class="sxs-lookup"><span data-stu-id="27b56-205">Metrics</span></span>

<span data-ttu-id="27b56-206">다음 표에서는 전화 회의 요약 보고서에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-206">The following table the information provided by the Conferences Summary Report.</span></span>

### <a name="conference-summary-report-metrics"></a><span data-ttu-id="27b56-207">전화 회의 요약 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="27b56-207">Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27b56-208">이름</span><span class="sxs-lookup"><span data-stu-id="27b56-208">Name</span></span></th>
<th><span data-ttu-id="27b56-209">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="27b56-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="27b56-210">설명</span><span class="sxs-lookup"><span data-stu-id="27b56-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27b56-211"><strong>매시간</strong></span><span class="sxs-lookup"><span data-stu-id="27b56-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="27b56-212"><strong>매일</strong></span><span class="sxs-lookup"><span data-stu-id="27b56-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="27b56-213"><strong>매주</strong></span><span class="sxs-lookup"><span data-stu-id="27b56-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="27b56-214"><strong>월간</strong></span><span class="sxs-lookup"><span data-stu-id="27b56-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="27b56-215">아니요</span><span class="sxs-lookup"><span data-stu-id="27b56-215">No</span></span></p></td>
<td><p><span data-ttu-id="27b56-p112">필터 도구 모음에서 선택한 시간 간격을 나타냅니다. 적용 가능한 경우 제공된 시간 간격을 클릭하여 해당 간격에 대한 자세한 정보를 볼 수 있습니다. 예를 들어 일별 간격을 사용 중이고 7/7/2012을 클릭하면 해당 날짜에 사용자 등록 활동에 대한 시간별 세부 내역을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-p112">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27b56-219"><strong>총 전화 회의</strong></span><span class="sxs-lookup"><span data-stu-id="27b56-219"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="27b56-220">아니요</span><span class="sxs-lookup"><span data-stu-id="27b56-220">No</span></span></p></td>
<td><p><span data-ttu-id="27b56-p113">전화 회의 유형에 관계없이 보류된 총 전화 회의 수입니다. 이 항목을 클릭하면 보고서에 선택한 기간에 대한 전화 회의 활동 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-p113">Total number of conferences (regardless of conference type) that were held. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27b56-223"><strong>총 참가자</strong></span><span class="sxs-lookup"><span data-stu-id="27b56-223"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="27b56-224">아니요</span><span class="sxs-lookup"><span data-stu-id="27b56-224">No</span></span></p></td>
<td><p><span data-ttu-id="27b56-p114">전화 회의에 참가한 총 사용자 수입니다. 이 항목을 클릭하면 보고서에 선택한 기간에 대한 전화 회의 활동 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-p114">Total number of people who took part in the conferences. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27b56-227"><strong>회의당 평균 참가자 수</strong></span><span class="sxs-lookup"><span data-stu-id="27b56-227"><strong>Average participants per conference</strong></span></span></p></td>
<td><p><span data-ttu-id="27b56-228">아니요</span><span class="sxs-lookup"><span data-stu-id="27b56-228">No</span></span></p></td>
<td><p><span data-ttu-id="27b56-p115">특정 전화 회의에 참가한 평균 사용자 수입니다. 총 회의를 총 참가자로 나눠서 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-p115">Average number of people who took part in a given conference. Determined by dividing the total conferences by the total participants.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27b56-231"><strong>총 A/V 회의</strong></span><span class="sxs-lookup"><span data-stu-id="27b56-231"><strong>Total A/V conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="27b56-232">아니요</span><span class="sxs-lookup"><span data-stu-id="27b56-232">No</span></span></p></td>
<td><p><span data-ttu-id="27b56-233">오디오 또는 비디오를 포함하는 총 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-233">Total number of conferences that included audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27b56-234"><strong>총 A/V 회의 시간(분)</strong></span><span class="sxs-lookup"><span data-stu-id="27b56-234"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="27b56-235">아니요</span><span class="sxs-lookup"><span data-stu-id="27b56-235">No</span></span></p></td>
<td><p><span data-ttu-id="27b56-236">오디오/비디오 회의에 할당된 총 시간(분)입니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-236">Total number of minutes devoted to audio/video conferencing.</span></span></p>
<p><span data-ttu-id="27b56-237">총 A/V 회의 시간 메트릭은 A/V 회의를 포함 한 모든 오디오/시각적 회의 유형을 요약 하 여 보여 줍니다. IM 회의; 앱 공유 회의 데이터 회의 및 PSTN 회의</span><span class="sxs-lookup"><span data-stu-id="27b56-237">The Total A/V conference minutes metric summarizes all the audio/visual conference types, including: A/V conferences; IM conferences; app sharing conferences; data conferences; and PSTN conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27b56-238"><strong>총 A/V 회의 참가 시간(분)</strong></span><span class="sxs-lookup"><span data-stu-id="27b56-238"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="27b56-239">아니요</span><span class="sxs-lookup"><span data-stu-id="27b56-239">No</span></span></p></td>
<td><p><span data-ttu-id="27b56-p116">오디오/비디오 회의에 할당된 총 참가 시간(분)입니다. 예를 들어 한 명의 사용자가 오디오/비디오 회의에서 5분을 소비하고 두 번째 사용자가 동일한 회의에서 3분을 소비했다고 가정하면 회의 참가 시간은 5분과 3분을 더한 총 8분이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-p116">Total number of participant minutes devoted to audio/video conferencing. For example, suppose one user spends 5 minutes in an audio/video conference and a second user spends 3 minutes in that same conference. That makes a total of 8 participant minutes: 5 minutes plus 3 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27b56-243"><strong>평균 A/V 회의 시간(분)</strong></span><span class="sxs-lookup"><span data-stu-id="27b56-243"><strong>Average A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="27b56-244">아니요</span><span class="sxs-lookup"><span data-stu-id="27b56-244">No</span></span></p></td>
<td><p><span data-ttu-id="27b56-245">오디오/비디오 회의당 평균 시간(분)입니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-245">Average number of minutes per audio/video conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27b56-246"><strong>회의의 고유한 총 이끌이 수</strong></span><span class="sxs-lookup"><span data-stu-id="27b56-246"><strong>Total number of unique organizers of conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="27b56-247">아니요</span><span class="sxs-lookup"><span data-stu-id="27b56-247">No</span></span></p></td>
<td><p><span data-ttu-id="27b56-p117">적어도 하나 이상의 회의를 구성한 총 사용자 수입니다. 회의를 하나 이상 구성한 사용자는 단일 회의만 구성한 사용자와 같이 한 명의 고유한 이끌이로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-p117">Total number of users who organized at least one conference. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27b56-250"><strong>총 회의 메시지</strong></span><span class="sxs-lookup"><span data-stu-id="27b56-250"><strong>Total conference messages</strong></span></span></p></td>
<td><p><span data-ttu-id="27b56-251">아니요</span><span class="sxs-lookup"><span data-stu-id="27b56-251">No</span></span></p></td>
<td><p><span data-ttu-id="27b56-252">회의 중 전송된 총 인스턴스 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="27b56-252">Total number of instant messages sent during the conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

