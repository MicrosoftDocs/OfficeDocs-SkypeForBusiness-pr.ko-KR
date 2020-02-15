---
title: 'Lync Server 2013: 전화 회의 요약 보고서'
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
ms.openlocfilehash: f3ad7208095473529204fd69db631718d8bd774e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="07c4a-102">Lync Server 2013의 전화 회의 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="07c4a-102">Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07c4a-103">_**마지막으로 수정 된 항목:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="07c4a-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="07c4a-104">회의 요약 보고서에서는 온라인 회의 세션에 대한 전반적인 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-104">The Conference Summary Report provides an overall view of your online conferencing sessions.</span></span> <span data-ttu-id="07c4a-105">일반적으로 회의에는 사용자가 2 명 이상 포함 되며 Microsoft Lync Server 2013 회의 서비스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-105">A conference typically involves more than 2 users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="07c4a-106">비교적 피어 투 피어 세션에서는 일반적으로 사용자가 2명만 포함되며 Lync Server의 회의 서비스를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-106">By comparison, a peer-to-peer session typically involves just 2 users and does not require the use of Lync Server's conferencing services.</span></span> <span data-ttu-id="07c4a-107">피어 투 피어 활동은 [Lync Server 2013의 피어 투 피어 활동 요약 보고서](lync-server-2013-peer-to-peer-activity-summary-report.md)에 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-107">Peer-to-peer activities are reported on the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span></span>

<span data-ttu-id="07c4a-108">전화 회의 요약 보고서에는 특정 기간 (매시간, 매일, 매주, 매월) 동안 개최 된 회의 수를 알리는 것은 물론, 해당 회의에 참가 한 총 사용자 수 및 고유한 전화 회의 총 수를 알리는 정보도 표시 됩니다. 이끌이.</span><span class="sxs-lookup"><span data-stu-id="07c4a-108">The Conference Summary Report not only tells you how many conferences were held during a given time period (hourly, daily, weekly, monthly) but also tells you the total number of people who took part in those conferences, and the total number of unique conference organizers.</span></span>

<span data-ttu-id="07c4a-p102">"고유한" 이끌이란 적어도 하나 이상의 회의를 예약한 모든 사람을 의미합니다. 예를 들어 Pilar Ackerman이 하나의 회의를 예약했다면 한 명의 고유한 이끌이가 됩니다. Ken Myer가 148개의 회의를 예약했어도 한 명의 고유한 이끌이로 계산됩니다. 예를 들어, 아래 표에는 8개의 예약된 회의가 표시되지만 고유한 이끌이는 단 3명인 Ken Myer, Pilar Ackerman 및 David Ahs뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-p102">A "unique” organizer is anyone who schedules at least one conference. For example, if Pilar Ackerman schedules one conference she counts as one unique organizer. If Ken Myer schedules 148 conferences he, too counts as one unique organizer. For example, the table below shows 8 conferences scheduled, but just three unique organizers (Ken Myer, Pilar Ackerman, and David Ahs).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07c4a-113">회의 이끌이</span><span class="sxs-lookup"><span data-stu-id="07c4a-113">Conference Organizer</span></span></th>
<th><span data-ttu-id="07c4a-114">회의 날짜</span><span class="sxs-lookup"><span data-stu-id="07c4a-114">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07c4a-115">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="07c4a-115">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="07c4a-116">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="07c4a-116">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4a-117">David Ahs</span><span class="sxs-lookup"><span data-stu-id="07c4a-117">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="07c4a-118">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="07c4a-118">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4a-119">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="07c4a-119">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="07c4a-120">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="07c4a-120">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4a-121">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="07c4a-121">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="07c4a-122">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="07c4a-122">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4a-123">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="07c4a-123">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="07c4a-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="07c4a-124">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4a-125">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="07c4a-125">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="07c4a-126">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="07c4a-126">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4a-127">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="07c4a-127">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="07c4a-128">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="07c4a-128">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4a-129">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="07c4a-129">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="07c4a-130">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="07c4a-130">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="07c4a-131">회의 요약 보고서에는 또한 오디오 및/또는 비디오가 포함된 회의 개수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-131">The Conference Summary Report also indicates how many conferences included audio and/or video.</span></span>

<div>

## <a name="accessing-the-conference-summary-report"></a><span data-ttu-id="07c4a-132">회의 요약 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="07c4a-132">Accessing the Conference Summary Report</span></span>

<span data-ttu-id="07c4a-p103">회의 요약 보고서는 모니터링 보고서 홈 페이지에서 액세스됩니다. 다음 메트릭 중 하나를 클릭하여 회의 활동 보고서로 드릴다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-p103">The Conference Summary Report is accessed from the Monitoring Reports home page. You can drill down to the Conference Activity report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="07c4a-135">총 회의</span><span class="sxs-lookup"><span data-stu-id="07c4a-135">Total conferences</span></span>

  - <span data-ttu-id="07c4a-136">총 참가자</span><span class="sxs-lookup"><span data-stu-id="07c4a-136">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a><span data-ttu-id="07c4a-137">회의 요약 보고서의 모범 사례 만들기</span><span class="sxs-lookup"><span data-stu-id="07c4a-137">Making the Best Use of the Conference Summary Report</span></span>

<span data-ttu-id="07c4a-p104">회의 요약 보고서에 사용된 대부분의 메트릭에 대한 총 값은 보고서 아래에서 찾을 수 있습니다. 지정된 기간 동안 수행된 총 회의 수 및 이러한 회의에 참가한 총 사용자 수와 같은 값을 보려면 아래로 스크롤합니다. 보고서 아래에 합계로 표시되지 않는 메트릭은 총 고유한 회의 이끌이입니다. 왜 그럴까요? 이유가 있습니다. 1개월 분량의 데이터를 조사한다고 가정해보십시오. 1일째에는 고유한 회의 이끌이 수가 34명이고, 2일째에는 고유한 회의 이끌이 수가 27명입니다. 그러면 이 이틀 동안의 고유한 회의 이끌이 수는 61명일까요? 반드시 그렇지는 않을 것입니다. 2일째에 회의를 주최한 27명이 모두 그 전날에 회의를 주최한 34명에 포함될 수도 있습니다. 예를 들어 여기에 표시된 간단한 보고서에서도 Ken Myer와 Pilar Ackerman은 7/7/2012 및 7/2/2012에 회의를 예약했습니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-p104">Total values for most of the metrics used on the Conference Summary Report can be found at the bottom of the report; scroll down to see values such as the total number of conferences held during the specified time period, and the total number of people who participated in those conferences. One metric that is not totaled at the bottom of the report is Total unique conference organizers. Why not? Here’s one reason. Suppose you are looking at a month's worth of data. On day 1 you had 34 unique conference organizers; on day 2 you had 27 unique conference organizers. Does that mean you had 61 unique conference organizers for those two days? Not necessarily. After all, all 27 people who organized conferences on day 2 might be among the 34 people who organized conferences on day 1. For example, in this simple report, note that Ken Myer and Pilar Ackerman scheduled conferences both on 7/7/2012 and on 7/2/2012:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07c4a-148">회의 이끌이</span><span class="sxs-lookup"><span data-stu-id="07c4a-148">Conference Organizer</span></span></th>
<th><span data-ttu-id="07c4a-149">회의 날짜</span><span class="sxs-lookup"><span data-stu-id="07c4a-149">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07c4a-150">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="07c4a-150">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="07c4a-151">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="07c4a-151">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4a-152">David Ahs</span><span class="sxs-lookup"><span data-stu-id="07c4a-152">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="07c4a-153">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="07c4a-153">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4a-154">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="07c4a-154">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="07c4a-155">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="07c4a-155">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4a-156">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="07c4a-156">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="07c4a-157">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="07c4a-157">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4a-158">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="07c4a-158">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="07c4a-159">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="07c4a-159">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4a-160">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="07c4a-160">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="07c4a-161">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="07c4a-161">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4a-162">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="07c4a-162">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="07c4a-163">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="07c4a-163">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4a-164">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="07c4a-164">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="07c4a-165">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="07c4a-165">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="07c4a-166">회의를 주최한 고유한 사용자의 총 수를 보다 쉽게 이해하기 위해 시간 간격을 바꿔보겠습니다. 예를 들어 하루가 아니라 한 달을 기준으로 데이터를 살펴 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-166">To get a better idea of the total number of unique users who organized conferences, change your time interval; for example, look at the data by month instead of by day.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="07c4a-167">필터</span><span class="sxs-lookup"><span data-stu-id="07c4a-167">Filters</span></span>

<span data-ttu-id="07c4a-p105">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 전화 회의 요약 보고서에서는 데이터의 그룹화 방법을 선택할 수 있습니다. 이 경우 전화 회의는 시간, 일, 주 또는 월별로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Summary Report enables you to choose how data should be grouped. In this case, conferences grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="07c4a-171">다음 표에서는 전화 회의 요약 보고서에서 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-171">The following table lists the filters that you can use with the Conference Summary Report.</span></span>

### <a name="conference-summary-report-filters"></a><span data-ttu-id="07c4a-172">전화 회의 요약 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="07c4a-172">Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07c4a-173">이름</span><span class="sxs-lookup"><span data-stu-id="07c4a-173">Name</span></span></th>
<th><span data-ttu-id="07c4a-174">설명</span><span class="sxs-lookup"><span data-stu-id="07c4a-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07c4a-175"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="07c4a-175"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="07c4a-p106">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="07c4a-178">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="07c4a-178">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="07c4a-p107">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="07c4a-181">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="07c4a-181">7/7/2012</span></span></p>
<p><span data-ttu-id="07c4a-182">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-182">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="07c4a-183">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="07c4a-183">7/3/2012</span></span></p>
<p><span data-ttu-id="07c4a-184">주는 항상 일요일부터 토요일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-184">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4a-185"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="07c4a-185"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="07c4a-p108">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="07c4a-188">2012/7/7 오후 1:00</span><span class="sxs-lookup"><span data-stu-id="07c4a-188">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="07c4a-p109">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="07c4a-191">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="07c4a-191">7/7/2012</span></span></p>
<p><span data-ttu-id="07c4a-192">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-192">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="07c4a-193">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="07c4a-193">7/3/2012</span></span></p>
<p><span data-ttu-id="07c4a-194">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-194">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4a-195"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="07c4a-195"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="07c4a-p110">시간 간격입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="07c4a-198">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="07c4a-198">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="07c4a-199">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="07c4a-199">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="07c4a-200">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="07c4a-200">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="07c4a-201">월별(최대 12개월 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="07c4a-201">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="07c4a-p111">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="07c4a-204">선별한</span><span class="sxs-lookup"><span data-stu-id="07c4a-204">Metrics</span></span>

<span data-ttu-id="07c4a-205">다음 표에서는 전화 회의 요약 보고서에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-205">The following table the information provided by the Conferences Summary Report.</span></span>

### <a name="conference-summary-report-metrics"></a><span data-ttu-id="07c4a-206">전화 회의 요약 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="07c4a-206">Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07c4a-207">이름</span><span class="sxs-lookup"><span data-stu-id="07c4a-207">Name</span></span></th>
<th><span data-ttu-id="07c4a-208">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="07c4a-208">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="07c4a-209">설명</span><span class="sxs-lookup"><span data-stu-id="07c4a-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07c4a-210"><strong>매시간</strong></span><span class="sxs-lookup"><span data-stu-id="07c4a-210"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="07c4a-211"><strong>매일</strong></span><span class="sxs-lookup"><span data-stu-id="07c4a-211"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="07c4a-212"><strong>매주</strong></span><span class="sxs-lookup"><span data-stu-id="07c4a-212"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="07c4a-213"><strong>월간</strong></span><span class="sxs-lookup"><span data-stu-id="07c4a-213"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="07c4a-214">아니요</span><span class="sxs-lookup"><span data-stu-id="07c4a-214">No</span></span></p></td>
<td><p><span data-ttu-id="07c4a-p112">필터 도구 모음에서 선택한 시간 간격을 나타냅니다. 적용 가능한 경우 제공된 시간 간격을 클릭하여 해당 간격에 대한 자세한 정보를 볼 수 있습니다. 예를 들어 일별 간격을 사용 중이고 7/7/2012을 클릭하면 해당 날짜에 사용자 등록 활동에 대한 시간별 세부 내역을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-p112">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4a-218"><strong>총 전화 회의</strong></span><span class="sxs-lookup"><span data-stu-id="07c4a-218"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="07c4a-219">아니요</span><span class="sxs-lookup"><span data-stu-id="07c4a-219">No</span></span></p></td>
<td><p><span data-ttu-id="07c4a-p113">전화 회의 유형에 관계없이 보류된 총 전화 회의 수입니다. 이 항목을 클릭하면 보고서에 선택한 기간에 대한 전화 회의 활동 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-p113">Total number of conferences (regardless of conference type) that were held. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4a-222"><strong>총 참가자</strong></span><span class="sxs-lookup"><span data-stu-id="07c4a-222"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="07c4a-223">아니요</span><span class="sxs-lookup"><span data-stu-id="07c4a-223">No</span></span></p></td>
<td><p><span data-ttu-id="07c4a-p114">전화 회의에 참가한 총 사용자 수입니다. 이 항목을 클릭하면 보고서에 선택한 기간에 대한 전화 회의 활동 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-p114">Total number of people who took part in the conferences. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4a-226"><strong>회의당 평균 참가자 수</strong></span><span class="sxs-lookup"><span data-stu-id="07c4a-226"><strong>Average participants per conference</strong></span></span></p></td>
<td><p><span data-ttu-id="07c4a-227">아니요</span><span class="sxs-lookup"><span data-stu-id="07c4a-227">No</span></span></p></td>
<td><p><span data-ttu-id="07c4a-p115">특정 전화 회의에 참가한 평균 사용자 수입니다. 총 회의를 총 참가자로 나눠서 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-p115">Average number of people who took part in a given conference. Determined by dividing the total conferences by the total participants.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4a-230"><strong>총 A/V 회의</strong></span><span class="sxs-lookup"><span data-stu-id="07c4a-230"><strong>Total A/V conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="07c4a-231">아니요</span><span class="sxs-lookup"><span data-stu-id="07c4a-231">No</span></span></p></td>
<td><p><span data-ttu-id="07c4a-232">오디오 또는 비디오를 포함하는 총 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-232">Total number of conferences that included audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4a-233"><strong>총 A/V 회의 시간(분)</strong></span><span class="sxs-lookup"><span data-stu-id="07c4a-233"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="07c4a-234">아니요</span><span class="sxs-lookup"><span data-stu-id="07c4a-234">No</span></span></p></td>
<td><p><span data-ttu-id="07c4a-235">오디오/비디오 회의에 할당된 총 시간(분)입니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-235">Total number of minutes devoted to audio/video conferencing.</span></span></p>
<p><span data-ttu-id="07c4a-236">총 A/V 회의 시간 메트릭은 A/V 회의를 포함 한 모든 오디오/시각적 회의 유형을 요약 하 여 보여 줍니다. IM 회의; 앱 공유 회의 데이터 회의 및 PSTN 회의</span><span class="sxs-lookup"><span data-stu-id="07c4a-236">The Total A/V conference minutes metric summarizes all the audio/visual conference types, including: A/V conferences; IM conferences; app sharing conferences; data conferences; and PSTN conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4a-237"><strong>총 A/V 회의 참가 시간(분)</strong></span><span class="sxs-lookup"><span data-stu-id="07c4a-237"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="07c4a-238">아니요</span><span class="sxs-lookup"><span data-stu-id="07c4a-238">No</span></span></p></td>
<td><p><span data-ttu-id="07c4a-p116">오디오/비디오 회의에 할당된 총 참가 시간(분)입니다. 예를 들어 한 명의 사용자가 오디오/비디오 회의에서 5분을 소비하고 두 번째 사용자가 동일한 회의에서 3분을 소비했다고 가정하면 회의 참가 시간은 5분과 3분을 더한 총 8분이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-p116">Total number of participant minutes devoted to audio/video conferencing. For example, suppose one user spends 5 minutes in an audio/video conference and a second user spends 3 minutes in that same conference. That makes a total of 8 participant minutes: 5 minutes plus 3 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4a-242"><strong>평균 A/V 회의 시간(분)</strong></span><span class="sxs-lookup"><span data-stu-id="07c4a-242"><strong>Average A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="07c4a-243">아니요</span><span class="sxs-lookup"><span data-stu-id="07c4a-243">No</span></span></p></td>
<td><p><span data-ttu-id="07c4a-244">오디오/비디오 회의당 평균 시간(분)입니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-244">Average number of minutes per audio/video conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07c4a-245"><strong>회의의 고유한 총 이끌이 수</strong></span><span class="sxs-lookup"><span data-stu-id="07c4a-245"><strong>Total number of unique organizers of conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="07c4a-246">아니요</span><span class="sxs-lookup"><span data-stu-id="07c4a-246">No</span></span></p></td>
<td><p><span data-ttu-id="07c4a-p117">적어도 하나 이상의 회의를 구성한 총 사용자 수입니다. 회의를 하나 이상 구성한 사용자는 단일 회의만 구성한 사용자와 같이 한 명의 고유한 이끌이로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-p117">Total number of users who organized at least one conference. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07c4a-249"><strong>총 회의 메시지</strong></span><span class="sxs-lookup"><span data-stu-id="07c4a-249"><strong>Total conference messages</strong></span></span></p></td>
<td><p><span data-ttu-id="07c4a-250">아니요</span><span class="sxs-lookup"><span data-stu-id="07c4a-250">No</span></span></p></td>
<td><p><span data-ttu-id="07c4a-251">회의 중 전송된 총 인스턴스 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="07c4a-251">Total number of instant messages sent during the conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

