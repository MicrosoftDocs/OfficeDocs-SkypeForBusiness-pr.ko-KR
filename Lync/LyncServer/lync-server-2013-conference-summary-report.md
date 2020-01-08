---
title: 'Lync Server 2013: 컨퍼런스 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dde91a25d33bac5af8b1759b1fbfc90cfb9bc0ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="89d88-102">Lync Server 2013의 컨퍼런스 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="89d88-102">Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89d88-103">_**마지막으로 수정한 주제:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="89d88-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="89d88-104">회의 요약 보고서는 온라인 회의 세션의 전체 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-104">The Conference Summary Report provides an overall view of your online conferencing sessions.</span></span> <span data-ttu-id="89d88-105">일반적으로 컨퍼런스에는 2 명 이상의 사용자가 포함 되며 Microsoft Lync Server 2013 회의 서비스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-105">A conference typically involves more than 2 users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="89d88-106">일반적으로 피어 투 피어 세션에는 두 명의 사용자만 포함 되며 Lync Server의 회의 서비스를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-106">By comparison, a peer-to-peer session typically involves just 2 users and does not require the use of Lync Server's conferencing services.</span></span> <span data-ttu-id="89d88-107">피어 투 피어 작업은 [Lync Server 2013의 피어 투 피어 작업 요약 보고서](lync-server-2013-peer-to-peer-activity-summary-report.md)에 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-107">Peer-to-peer activities are reported on the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span></span>

<span data-ttu-id="89d88-108">회의 요약 보고서는 특정 기간 (매시간, 매일, 매주, 매월) 동안 얼마나 많은 회의가 진행 되었는지 알려 주고 해당 회의에 참여 한 총 사용자 수와 고유한 컨퍼런스 총 수를 알려 주는 것도 아닙니다. 이끌이가.</span><span class="sxs-lookup"><span data-stu-id="89d88-108">The Conference Summary Report not only tells you how many conferences were held during a given time period (hourly, daily, weekly, monthly) but also tells you the total number of people who took part in those conferences, and the total number of unique conference organizers.</span></span>

<span data-ttu-id="89d88-109">"고유" 이끌이는 하나 이상의 회의를 예약 하는 사람입니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-109">A "unique” organizer is anyone who schedules at least one conference.</span></span> <span data-ttu-id="89d88-110">예를 들어 Pilar Ackerman은 한 회의를 한 명의 고유한 이끌이만으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-110">For example, if Pilar Ackerman schedules one conference she counts as one unique organizer.</span></span> <span data-ttu-id="89d88-111">: 진구 Myer에서 148 회의를 하는 경우 1 개의 고유 이끌이로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-111">If Ken Myer schedules 148 conferences he, too counts as one unique organizer.</span></span> <span data-ttu-id="89d88-112">예를 들어 아래 표에는 예약 된 8 개의 회의가 표시 되지만,: 진구 Myer, Pilar Ackerman, David Ahs)와 같은 세 가지 고유한 조직자만 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-112">For example, the table below shows 8 conferences scheduled, but just three unique organizers (Ken Myer, Pilar Ackerman, and David Ahs).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89d88-113">컨퍼런스 이끌이</span><span class="sxs-lookup"><span data-stu-id="89d88-113">Conference Organizer</span></span></th>
<th><span data-ttu-id="89d88-114">컨퍼런스 날짜</span><span class="sxs-lookup"><span data-stu-id="89d88-114">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89d88-115">: 진구 Myer</span><span class="sxs-lookup"><span data-stu-id="89d88-115">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="89d88-116">오전 7/7/2012 10:00</span><span class="sxs-lookup"><span data-stu-id="89d88-116">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d88-117">David Ahs</span><span class="sxs-lookup"><span data-stu-id="89d88-117">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="89d88-118">오전 7/7/2012 10:00</span><span class="sxs-lookup"><span data-stu-id="89d88-118">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d88-119">: 진구 Myer</span><span class="sxs-lookup"><span data-stu-id="89d88-119">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="89d88-120">오전 7/7/2012 11:00</span><span class="sxs-lookup"><span data-stu-id="89d88-120">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d88-121">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="89d88-121">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="89d88-122">오전 7/7/2012 11:00</span><span class="sxs-lookup"><span data-stu-id="89d88-122">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d88-123">: 진구 Myer</span><span class="sxs-lookup"><span data-stu-id="89d88-123">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="89d88-124">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="89d88-124">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d88-125">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="89d88-125">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="89d88-126">오후 7/7/2012 2:00</span><span class="sxs-lookup"><span data-stu-id="89d88-126">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d88-127">: 진구 Myer</span><span class="sxs-lookup"><span data-stu-id="89d88-127">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="89d88-128">오전 7/2/2012 10:00</span><span class="sxs-lookup"><span data-stu-id="89d88-128">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d88-129">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="89d88-129">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="89d88-130">오전 7/2/2012 10:00</span><span class="sxs-lookup"><span data-stu-id="89d88-130">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="89d88-131">회의 요약 보고서에는 오디오 및/또는 비디오가 포함 된 회의 수도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-131">The Conference Summary Report also indicates how many conferences included audio and/or video.</span></span>

<div>

## <a name="accessing-the-conference-summary-report"></a><span data-ttu-id="89d88-132">회의 요약 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="89d88-132">Accessing the Conference Summary Report</span></span>

<span data-ttu-id="89d88-133">회의 요약 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-133">The Conference Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="89d88-134">다음 메트릭 중 하나를 클릭 하 여 컨퍼런스 활동 보고서를 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-134">You can drill down to the Conference Activity report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="89d88-135">총 컨퍼런스</span><span class="sxs-lookup"><span data-stu-id="89d88-135">Total conferences</span></span>

  - <span data-ttu-id="89d88-136">총 참가자</span><span class="sxs-lookup"><span data-stu-id="89d88-136">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a><span data-ttu-id="89d88-137">회의 요약 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="89d88-137">Making the Best Use of the Conference Summary Report</span></span>

<span data-ttu-id="89d88-138">회의 요약 보고서에 사용 되는 대부분의 메트릭 값 합계는 보고서의 맨 아래에서 찾을 수 있습니다. 아래로 스크롤하여 지정 된 기간 동안 보유 한 총 회의 수 및 해당 회의에 참가 한 총 컨퍼런스 수 등의 값을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-138">Total values for most of the metrics used on the Conference Summary Report can be found at the bottom of the report; scroll down to see values such as the total number of conferences held during the specified time period, and the total number of people who participated in those conferences.</span></span> <span data-ttu-id="89d88-139">보고서의 맨 아래에서 합산 되지 않는 하나의 메트릭은 총 고유한 회의 이끌이입니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-139">One metric that is not totaled at the bottom of the report is Total unique conference organizers.</span></span> <span data-ttu-id="89d88-140">왜 안 돼요?</span><span class="sxs-lookup"><span data-stu-id="89d88-140">Why not?</span></span> <span data-ttu-id="89d88-141">한 가지 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-141">Here’s one reason.</span></span> <span data-ttu-id="89d88-142">월의 데이터를 보고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-142">Suppose you are looking at a month's worth of data.</span></span> <span data-ttu-id="89d88-143">1 일에 34 고유한 회의 이끌이를가지고 있습니다. 일 2에 27 개의 고유한 컨퍼런스 이끌이를가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-143">On day 1 you had 34 unique conference organizers; on day 2 you had 27 unique conference organizers.</span></span> <span data-ttu-id="89d88-144">2 일 동안 61 고유한 회의 이끌이가 있다는 의미 입니까?</span><span class="sxs-lookup"><span data-stu-id="89d88-144">Does that mean you had 61 unique conference organizers for those two days?</span></span> <span data-ttu-id="89d88-145">필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-145">Not necessarily.</span></span> <span data-ttu-id="89d88-146">매일 2 일에 회의를 이끄는 모든 27 명의 사용자가 일 1에 회의를 이끄는 34 사람 중에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-146">After all, all 27 people who organized conferences on day 2 might be among the 34 people who organized conferences on day 1.</span></span> <span data-ttu-id="89d88-147">예를 들어이 간단한 보고서에서는: 진구 Myer 및 Pilar Ackerman이 7/7/2012 및 7/2/2012에서 모두 예약한 회의를 수행 하는 것을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="89d88-147">For example, in this simple report, note that Ken Myer and Pilar Ackerman scheduled conferences both on 7/7/2012 and on 7/2/2012:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89d88-148">컨퍼런스 이끌이</span><span class="sxs-lookup"><span data-stu-id="89d88-148">Conference Organizer</span></span></th>
<th><span data-ttu-id="89d88-149">컨퍼런스 날짜</span><span class="sxs-lookup"><span data-stu-id="89d88-149">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89d88-150">: 진구 Myer</span><span class="sxs-lookup"><span data-stu-id="89d88-150">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="89d88-151">오전 7/7/2012 10:00</span><span class="sxs-lookup"><span data-stu-id="89d88-151">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d88-152">David Ahs</span><span class="sxs-lookup"><span data-stu-id="89d88-152">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="89d88-153">오전 7/7/2012 10:00</span><span class="sxs-lookup"><span data-stu-id="89d88-153">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d88-154">: 진구 Myer</span><span class="sxs-lookup"><span data-stu-id="89d88-154">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="89d88-155">오전 7/7/2012 11:00</span><span class="sxs-lookup"><span data-stu-id="89d88-155">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d88-156">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="89d88-156">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="89d88-157">오전 7/7/2012 11:00</span><span class="sxs-lookup"><span data-stu-id="89d88-157">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d88-158">: 진구 Myer</span><span class="sxs-lookup"><span data-stu-id="89d88-158">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="89d88-159">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="89d88-159">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d88-160">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="89d88-160">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="89d88-161">오후 7/7/2012 2:00</span><span class="sxs-lookup"><span data-stu-id="89d88-161">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d88-162">: 진구 Myer</span><span class="sxs-lookup"><span data-stu-id="89d88-162">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="89d88-163">오전 7/2/2012 10:00</span><span class="sxs-lookup"><span data-stu-id="89d88-163">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d88-164">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="89d88-164">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="89d88-165">오전 7/2/2012 10:00</span><span class="sxs-lookup"><span data-stu-id="89d88-165">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="89d88-166">회의를 구성한 고유 사용자의 총 수를 더 잘 이해 하려면 시간 간격을 변경 하세요. 예를 들어 일이 아닌 월별로 데이터를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-166">To get a better idea of the total number of unique users who organized conferences, change your time interval; for example, look at the data by month instead of by day.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="89d88-167">필터가</span><span class="sxs-lookup"><span data-stu-id="89d88-167">Filters</span></span>

<span data-ttu-id="89d88-168">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-168">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="89d88-169">예를 들어 회의 요약 보고서를 사용 하 여 데이터를 그룹화 하는 방법을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-169">For example, the Conference Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="89d88-170">이 경우 시간, 일, 주 또는 월로 그룹화 된 컨퍼런스.</span><span class="sxs-lookup"><span data-stu-id="89d88-170">In this case, conferences grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="89d88-171">다음 표에는 회의 요약 보고서에 사용할 수 있는 필터가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-171">The following table lists the filters that you can use with the Conference Summary Report.</span></span>

### <a name="conference-summary-report-filters"></a><span data-ttu-id="89d88-172">회의 요약 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="89d88-172">Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89d88-173">이름</span><span class="sxs-lookup"><span data-stu-id="89d88-173">Name</span></span></th>
<th><span data-ttu-id="89d88-174">설명</span><span class="sxs-lookup"><span data-stu-id="89d88-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89d88-175"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="89d88-175"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="89d88-176">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-176">Start date/time for the time range.</span></span> <span data-ttu-id="89d88-177">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-177">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="89d88-178">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="89d88-178">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="89d88-179">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-179">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="89d88-180">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-180">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="89d88-181">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="89d88-181">7/7/2012</span></span></p>
<p><span data-ttu-id="89d88-182">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="89d88-182">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="89d88-183">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="89d88-183">7/3/2012</span></span></p>
<p><span data-ttu-id="89d88-184">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-184">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d88-185"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="89d88-185"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="89d88-186">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-186">End date/time for the time range.</span></span> <span data-ttu-id="89d88-187">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-187">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="89d88-188">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="89d88-188">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="89d88-189">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-189">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="89d88-190">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-190">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="89d88-191">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="89d88-191">7/7/2012</span></span></p>
<p><span data-ttu-id="89d88-192">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="89d88-192">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="89d88-193">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="89d88-193">7/3/2012</span></span></p>
<p><span data-ttu-id="89d88-194">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-194">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d88-195"><strong>간격만</strong></span><span class="sxs-lookup"><span data-stu-id="89d88-195"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="89d88-196">시간 간격.</span><span class="sxs-lookup"><span data-stu-id="89d88-196">Time interval.</span></span> <span data-ttu-id="89d88-197">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-197">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="89d88-198">매시간 (최대 25 시간 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="89d88-198">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="89d88-199">매일 (최대 31 일이 표시 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="89d88-199">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="89d88-200">주간 (최대 12 주를 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="89d88-200">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="89d88-201">월간 (최대 12 개월을 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="89d88-201">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="89d88-202">시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값의 수만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-202">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="89d88-203">예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-203">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="89d88-204">매트릭스</span><span class="sxs-lookup"><span data-stu-id="89d88-204">Metrics</span></span>

<span data-ttu-id="89d88-205">다음 표에는 회의 요약 보고서에서 제공 하는 정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-205">The following table the information provided by the Conferences Summary Report.</span></span>

### <a name="conference-summary-report-metrics"></a><span data-ttu-id="89d88-206">회의 요약 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="89d88-206">Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89d88-207">이름</span><span class="sxs-lookup"><span data-stu-id="89d88-207">Name</span></span></th>
<th><span data-ttu-id="89d88-208">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="89d88-208">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="89d88-209">설명</span><span class="sxs-lookup"><span data-stu-id="89d88-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89d88-210"><strong>마다</strong></span><span class="sxs-lookup"><span data-stu-id="89d88-210"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="89d88-211"><strong>Daily</strong></span><span class="sxs-lookup"><span data-stu-id="89d88-211"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="89d88-212"><strong>매주</strong></span><span class="sxs-lookup"><span data-stu-id="89d88-212"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="89d88-213"><strong>월간</strong></span><span class="sxs-lookup"><span data-stu-id="89d88-213"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="89d88-214">아니요</span><span class="sxs-lookup"><span data-stu-id="89d88-214">No</span></span></p></td>
<td><p><span data-ttu-id="89d88-215">필터 도구 모음에서 선택한 시간 간격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-215">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="89d88-216">해당 되는 경우 지정 된 시간 간격을 클릭 하 여 해당 간격에 대 한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-216">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="89d88-217">예를 들어 일일 기간을 사용 하는 경우 7/7/2012을 클릭 하면 해당 날짜에 대 한 사용자 등록 작업을 시간별로 분류 하 여 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-217">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d88-218"><strong>총 컨퍼런스</strong></span><span class="sxs-lookup"><span data-stu-id="89d88-218"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="89d88-219">아니요</span><span class="sxs-lookup"><span data-stu-id="89d88-219">No</span></span></p></td>
<td><p><span data-ttu-id="89d88-220">전화 회의 유형에 관계 없이 보유 한 총 컨퍼런스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-220">Total number of conferences (regardless of conference type) that were held.</span></span> <span data-ttu-id="89d88-221">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 컨퍼런스 활동 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-221">When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d88-222"><strong>총 참가자</strong></span><span class="sxs-lookup"><span data-stu-id="89d88-222"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="89d88-223">아니요</span><span class="sxs-lookup"><span data-stu-id="89d88-223">No</span></span></p></td>
<td><p><span data-ttu-id="89d88-224">회의에 참가 한 총 사용자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-224">Total number of people who took part in the conferences.</span></span> <span data-ttu-id="89d88-225">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 컨퍼런스 활동 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-225">When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d88-226"><strong>회의 당 평균 참가자 수</strong></span><span class="sxs-lookup"><span data-stu-id="89d88-226"><strong>Average participants per conference</strong></span></span></p></td>
<td><p><span data-ttu-id="89d88-227">아니요</span><span class="sxs-lookup"><span data-stu-id="89d88-227">No</span></span></p></td>
<td><p><span data-ttu-id="89d88-228">지정 된 회의에 참여 한 평균 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-228">Average number of people who took part in a given conference.</span></span> <span data-ttu-id="89d88-229">총 회의를 총 참가자로 나누어 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-229">Determined by dividing the total conferences by the total participants.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d88-230"><strong>총 A/V 회의</strong></span><span class="sxs-lookup"><span data-stu-id="89d88-230"><strong>Total A/V conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="89d88-231">아니요</span><span class="sxs-lookup"><span data-stu-id="89d88-231">No</span></span></p></td>
<td><p><span data-ttu-id="89d88-232">오디오 또는 비디오를 포함 한 총 컨퍼런스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-232">Total number of conferences that included audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d88-233"><strong>총 A/V 회의 시간 (분)</strong></span><span class="sxs-lookup"><span data-stu-id="89d88-233"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="89d88-234">아니요</span><span class="sxs-lookup"><span data-stu-id="89d88-234">No</span></span></p></td>
<td><p><span data-ttu-id="89d88-235">오디오/비디오 회의에 소요 된 총 시간 (분)입니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-235">Total number of minutes devoted to audio/video conferencing.</span></span></p>
<p><span data-ttu-id="89d88-236">총 A/V 회의 시간 메트릭은 A/V 회의를 포함 하 여 모든 오디오/시각적 회의 유형을 요약 합니다. 메신저 대화 회의 앱 공유 회의 데이터 회의 및 PSTN 회의.</span><span class="sxs-lookup"><span data-stu-id="89d88-236">The Total A/V conference minutes metric summarizes all the audio/visual conference types, including: A/V conferences; IM conferences; app sharing conferences; data conferences; and PSTN conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d88-237"><strong>총 A/V 회의 참가자 통화 시간</strong></span><span class="sxs-lookup"><span data-stu-id="89d88-237"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="89d88-238">아니요</span><span class="sxs-lookup"><span data-stu-id="89d88-238">No</span></span></p></td>
<td><p><span data-ttu-id="89d88-239">오디오/비디오 회의에 소요 된 총 참가자 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-239">Total number of participant minutes devoted to audio/video conferencing.</span></span> <span data-ttu-id="89d88-240">예를 들어 한 명의 사용자가 오디오/비디오 회의에서 5 분 정도 소요 되는 경우 두 번째 사용자는 같은 회의에서 3 분이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-240">For example, suppose one user spends 5 minutes in an audio/video conference and a second user spends 3 minutes in that same conference.</span></span> <span data-ttu-id="89d88-241">이를 통해 총 8 분의 참가자가 5 분 + 3 분이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-241">That makes a total of 8 participant minutes: 5 minutes plus 3 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d88-242"><strong>평균 A/V 회의 시간 (분)</strong></span><span class="sxs-lookup"><span data-stu-id="89d88-242"><strong>Average A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="89d88-243">아니요</span><span class="sxs-lookup"><span data-stu-id="89d88-243">No</span></span></p></td>
<td><p><span data-ttu-id="89d88-244">오디오/비디오 회의 당 평균 분 수입니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-244">Average number of minutes per audio/video conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89d88-245"><strong>고유한 회의 이끌이의 총 수입니다.</strong></span><span class="sxs-lookup"><span data-stu-id="89d88-245"><strong>Total number of unique organizers of conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="89d88-246">아니요</span><span class="sxs-lookup"><span data-stu-id="89d88-246">No</span></span></p></td>
<td><p><span data-ttu-id="89d88-247">하나 이상의 회의를 구성한 총 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-247">Total number of users who organized at least one conference.</span></span> <span data-ttu-id="89d88-248">두 개 이상의 회의를 구성한 사용자는 단일 컨퍼런스만 구성한 사용자와 같이 하나의 고유 이끌이로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-248">Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89d88-249"><strong>총 컨퍼런스 메시지</strong></span><span class="sxs-lookup"><span data-stu-id="89d88-249"><strong>Total conference messages</strong></span></span></p></td>
<td><p><span data-ttu-id="89d88-250">아니요</span><span class="sxs-lookup"><span data-stu-id="89d88-250">No</span></span></p></td>
<td><p><span data-ttu-id="89d88-251">회의 중에 전송 된 총 인스턴트 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="89d88-251">Total number of instant messages sent during the conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

