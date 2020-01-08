---
title: 'Lync Server 2013: 피어 투 피어 IM 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f44d25ec36788e6964ea81bde71e82f3746c5aee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a><span data-ttu-id="67121-102">Lync Server 2013의 피어 투 피어 IM 보고서</span><span class="sxs-lookup"><span data-stu-id="67121-102">Peer-to-Peer IM Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67121-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="67121-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="67121-104">피어 투 피어 IM 보고서는 피어 투 피어 인스턴트 메시징 (IM) 세션에 대 한 추세 정보를 풀 및 인증 유형별로 분류 하 여 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="67121-104">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type.</span></span> <span data-ttu-id="67121-105">보고서에는 지정 된 기간 동안에 보유 한 총 세션 수 (예: 일일 또는 시간별) 또는 해당 기간 동안 보낸 총 인스턴트 메시지 수를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67121-105">The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="67121-106">피어 투 피어 IM 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="67121-106">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="67121-107">[Lync Server 2013에서 피어 투 피어 활동 요약 보고서](lync-server-2013-peer-to-peer-activity-summary-report.md) 를 열고 다음 메트릭 중 하나를 클릭 하 여 피어 투 피어 IM 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67121-107">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>

  - <span data-ttu-id="67121-108">총 피어 투 피어 IM 세션</span><span class="sxs-lookup"><span data-stu-id="67121-108">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="67121-109">총 피어 투 피어 IM 메시지</span><span class="sxs-lookup"><span data-stu-id="67121-109">Total peer-to-peer IM messages</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="67121-110">피어 투 피어 IM 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="67121-110">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="67121-111">기본적으로 피어 투 피어 IM 보고서에는 사용자가 시간 당 메시지 수 (또는 설정에 따라 일)가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67121-111">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings).</span></span> <span data-ttu-id="67121-112">그러나 일일 세션당 일별 세션만 표시 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67121-112">However, you can also choose to view the day by sessions per hour.</span></span> <span data-ttu-id="67121-113">이렇게 하려면 보고서 창의 오른쪽 위 모서리에서 **매개 변수 숨기기/표시** 를 클릭 한 다음 **보고서** 목록에서 **세션 개수** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="67121-113">To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="67121-114">필터가</span><span class="sxs-lookup"><span data-stu-id="67121-114">Filters</span></span>

<span data-ttu-id="67121-115">필터는 더욱 세밀 하 게 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="67121-115">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="67121-116">다음 표에는 피어 투 피어 IM 보고서에 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67121-116">The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>

### <a name="peer-to-peer-im-report-filters"></a><span data-ttu-id="67121-117">피어 투 피어 IM 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="67121-117">Peer-to-Peer IM Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67121-118">이름</span><span class="sxs-lookup"><span data-stu-id="67121-118">Name</span></span></th>
<th><span data-ttu-id="67121-119">설명</span><span class="sxs-lookup"><span data-stu-id="67121-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67121-120"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="67121-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="67121-121">시간 범위에 대 한 시작 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="67121-121">Start date and time for the time range.</span></span> <span data-ttu-id="67121-122">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="67121-122">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="67121-123">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="67121-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="67121-124">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67121-124">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="67121-125">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="67121-125">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="67121-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="67121-126">7/7/2012</span></span></p>
<p><span data-ttu-id="67121-127">주별 또는 월별로 보려면 주 또는 월에 속하는 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="67121-127">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="67121-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="67121-128">7/3/2012</span></span></p>
<p><span data-ttu-id="67121-129">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="67121-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67121-130"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="67121-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="67121-131">시간 범위의 종료 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="67121-131">End date and time for the time range.</span></span> <span data-ttu-id="67121-132">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="67121-132">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="67121-133">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="67121-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="67121-134">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67121-134">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="67121-135">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="67121-135">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="67121-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="67121-136">7/7/2012</span></span></p>
<p><span data-ttu-id="67121-137">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="67121-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="67121-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="67121-138">7/3/2012</span></span></p>
<p><span data-ttu-id="67121-139">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="67121-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67121-140"><strong>간격만</strong></span><span class="sxs-lookup"><span data-stu-id="67121-140"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="67121-141">시간 간격.</span><span class="sxs-lookup"><span data-stu-id="67121-141">Time interval.</span></span> <span data-ttu-id="67121-142">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67121-142">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="67121-143">매시간 (최대 25 시간 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="67121-143">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="67121-144">매일 (최대 31 일이 표시 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="67121-144">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="67121-145">주간 (최대 12 주를 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="67121-145">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="67121-146">월간 (최대 12 개월을 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="67121-146">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="67121-147">시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하면 시작 날짜부터 시작 하 여 최대 값만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67121-147">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="67121-148">예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67121-148">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67121-149"><strong>보고서 기준</strong></span><span class="sxs-lookup"><span data-stu-id="67121-149"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="67121-150">보고서에 사용할 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="67121-150">Indicates the values to be used in the report.</span></span> <span data-ttu-id="67121-151">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="67121-151">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="67121-152">세션 수</span><span class="sxs-lookup"><span data-stu-id="67121-152">Session count</span></span></p></li>
<li><p><span data-ttu-id="67121-153">메시지 수</span><span class="sxs-lookup"><span data-stu-id="67121-153">Message count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="67121-154">풀에의 한 피어 투 피어 IM 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="67121-154">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="67121-155">다음 표에는 피어 투 피어 IM 보고서에 제공 되는 정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67121-155">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="67121-156">풀에의 한 피어 투 피어 IM 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="67121-156">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67121-157">이름</span><span class="sxs-lookup"><span data-stu-id="67121-157">Name</span></span></th>
<th><span data-ttu-id="67121-158">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="67121-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="67121-159">설명</span><span class="sxs-lookup"><span data-stu-id="67121-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67121-160"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="67121-160"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="67121-161">아니요</span><span class="sxs-lookup"><span data-stu-id="67121-161">No</span></span></p></td>
<td><p><span data-ttu-id="67121-162">등록자 풀 또는 Edge 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="67121-162">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67121-163"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="67121-163"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="67121-164">아니요</span><span class="sxs-lookup"><span data-stu-id="67121-164">No</span></span></p></td>
<td><p><span data-ttu-id="67121-165">세션이 발생 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="67121-165">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67121-166"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="67121-166"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="67121-167">아니요</span><span class="sxs-lookup"><span data-stu-id="67121-167">No</span></span></p></td>
<td><p><span data-ttu-id="67121-168">총 세션 수 또는 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="67121-168">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="67121-169">인증 유형별 피어 투 피어 IM 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="67121-169">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="67121-170">다음 표에는 피어 투 피어 세션에서 참가자가 사용 하는 각 유형의 인증에 대해 피어 투 피어 IM 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67121-170">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="67121-171">인증 유형별 피어 투 피어 IM 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="67121-171">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67121-172">이름</span><span class="sxs-lookup"><span data-stu-id="67121-172">Name</span></span></th>
<th><span data-ttu-id="67121-173">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="67121-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="67121-174">설명</span><span class="sxs-lookup"><span data-stu-id="67121-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67121-175"><strong>인증 유형</strong></span><span class="sxs-lookup"><span data-stu-id="67121-175"><strong>Authentication type</strong></span></span></p></td>
<td><p><span data-ttu-id="67121-176">아니요</span><span class="sxs-lookup"><span data-stu-id="67121-176">No</span></span></p></td>
<td><p><span data-ttu-id="67121-177">세션 참가자가 사용 하는 인증 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="67121-177">Type of authentication used by the session participants.</span></span> <span data-ttu-id="67121-178">값은 일반적으로 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="67121-178">Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="67121-179">Enterprise</span><span class="sxs-lookup"><span data-stu-id="67121-179">Enterprise</span></span></p></li>
<li><p><span data-ttu-id="67121-180">제휴</span><span class="sxs-lookup"><span data-stu-id="67121-180">Federated</span></span></p></li>
<li><p><span data-ttu-id="67121-181">PIC</span><span class="sxs-lookup"><span data-stu-id="67121-181">PIC</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67121-182"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="67121-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="67121-183">아니요</span><span class="sxs-lookup"><span data-stu-id="67121-183">No</span></span></p></td>
<td><p><span data-ttu-id="67121-184">세션이 발생 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="67121-184">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67121-185"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="67121-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="67121-186">아니요</span><span class="sxs-lookup"><span data-stu-id="67121-186">No</span></span></p></td>
<td><p><span data-ttu-id="67121-187">총 세션 수 또는 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="67121-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

