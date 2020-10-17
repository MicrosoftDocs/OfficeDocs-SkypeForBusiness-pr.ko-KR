---
title: 'Lync Server 2013: 피어-투-피어 IM 보고서'
description: 'Lync Server 2013: 피어 투 피어 IM 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eac6291d0f099af8269ed15f7dc8c654ac944ed0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557294"
---
# <a name="peer-to-peer-im-report-in-lync-server-2013"></a><span data-ttu-id="63b54-103">Lync Server 2013의 피어 투 피어 IM 보고서</span><span class="sxs-lookup"><span data-stu-id="63b54-103">Peer-to-Peer IM Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63b54-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="63b54-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="63b54-p101">피어-투-피어 IM 보고서는 풀과 인증 유형별로 구분된 피어-투-피어 IM(인스턴트 메시징) 세션에 대한 추세 정보를 제공합니다. 이 보고서는 지정된 기간(예: 일별 또는 시간별) 동안 진행된 세션의 총 수를 표시할 수도 있고, 해당 기간 동안 발송된 인스턴트 메시지의 총 수를 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-p101">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type. The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="63b54-107">피어-투-피어 IM 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="63b54-107">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="63b54-108">[Lync Server 2013에서 피어 투 피어 활동 요약 보고서](lync-server-2013-peer-to-peer-activity-summary-report.md) 를 열고 다음 메트릭 중 하나를 클릭 하 여 피어 투 피어 IM 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-108">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>

  - <span data-ttu-id="63b54-109">총 피어 투 피어 IM 세션</span><span class="sxs-lookup"><span data-stu-id="63b54-109">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="63b54-110">총 피어 투 피어 IM 메시지</span><span class="sxs-lookup"><span data-stu-id="63b54-110">Total peer-to-peer IM messages</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="63b54-111">피어 투 피어 IM 보고서를 가장 효율적으로 활용</span><span class="sxs-lookup"><span data-stu-id="63b54-111">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="63b54-p102">기본적으로 피어 투 피어 IM 보고서에는 시간별(또는 설정에 따라 일별) 메시지 수가 표시됩니다. 그러나 특정일의 시간당 세션 수를 표시할 수도 있습니다. 이렇게 하려면 보고서 창 오른쪽 위에서 **매개 변수 표시/숨기기**를 클릭하고 **보고서 작성자** 목록에서 **세션 수**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-p102">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings). However, you can also choose to view the day by sessions per hour. To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="63b54-115">필터</span><span class="sxs-lookup"><span data-stu-id="63b54-115">Filters</span></span>

<span data-ttu-id="63b54-p103">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에서는 피어 투 피어 IM 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-p103">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>

### <a name="peer-to-peer-im-report-filters"></a><span data-ttu-id="63b54-118">피어 투 피어 IM 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="63b54-118">Peer-to-Peer IM Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63b54-119">이름</span><span class="sxs-lookup"><span data-stu-id="63b54-119">Name</span></span></th>
<th><span data-ttu-id="63b54-120">설명</span><span class="sxs-lookup"><span data-stu-id="63b54-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63b54-121"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="63b54-121"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="63b54-p104">시간 범위의 시작 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜와 시간을 모두 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="63b54-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="63b54-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="63b54-p105">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="63b54-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="63b54-127">7/7/2012</span></span></p>
<p><span data-ttu-id="63b54-128">주 또는 월별로 보려면 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-128">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="63b54-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="63b54-129">7/3/2012</span></span></p>
<p><span data-ttu-id="63b54-130">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b54-131"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="63b54-131"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="63b54-p106">시간 범위의 종료 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-p106">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="63b54-134">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="63b54-134">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="63b54-p107">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="63b54-137">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="63b54-137">7/7/2012</span></span></p>
<p><span data-ttu-id="63b54-138">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-138">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="63b54-139">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="63b54-139">7/3/2012</span></span></p>
<p><span data-ttu-id="63b54-140">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-140">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b54-141"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="63b54-141"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="63b54-p108">시간 간격입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="63b54-144">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="63b54-144">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="63b54-145">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="63b54-145">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="63b54-146">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="63b54-146">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="63b54-147">월별(최대 12개월 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="63b54-147">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="63b54-p109">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b54-150"><strong>보고서 작성자</strong></span><span class="sxs-lookup"><span data-stu-id="63b54-150"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="63b54-p110">보고서에 사용할 값을 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-p110">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="63b54-153">세션 수</span><span class="sxs-lookup"><span data-stu-id="63b54-153">Session count</span></span></p></li>
<li><p><span data-ttu-id="63b54-154">메시지 수</span><span class="sxs-lookup"><span data-stu-id="63b54-154">Message count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="63b54-155">풀별 피어 투 피어 IM 세션 메트릭</span><span class="sxs-lookup"><span data-stu-id="63b54-155">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="63b54-156">다음 표에서는 피어 투 피어 IM 보고서에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-156">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="63b54-157">풀별 피어 투 피어 IM 세션 메트릭</span><span class="sxs-lookup"><span data-stu-id="63b54-157">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63b54-158">이름</span><span class="sxs-lookup"><span data-stu-id="63b54-158">Name</span></span></th>
<th><span data-ttu-id="63b54-159">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="63b54-159">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="63b54-160">설명</span><span class="sxs-lookup"><span data-stu-id="63b54-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63b54-161"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="63b54-161"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="63b54-162">아니요</span><span class="sxs-lookup"><span data-stu-id="63b54-162">No</span></span></p></td>
<td><p><span data-ttu-id="63b54-163">등록자 풀 또는에 지 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-163">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b54-164"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="63b54-164"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="63b54-165">아니요</span><span class="sxs-lookup"><span data-stu-id="63b54-165">No</span></span></p></td>
<td><p><span data-ttu-id="63b54-166">세션이 발생한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-166">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b54-167"><strong>합계</strong></span><span class="sxs-lookup"><span data-stu-id="63b54-167"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="63b54-168">아니요</span><span class="sxs-lookup"><span data-stu-id="63b54-168">No</span></span></p></td>
<td><p><span data-ttu-id="63b54-169">총 세션 수 또는 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-169">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="63b54-170">인증 유형별 피어 투 피어 IM 세션 메트릭</span><span class="sxs-lookup"><span data-stu-id="63b54-170">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="63b54-171">다음 표에서는 피어 투 피어 세션의 참가자가 사용하는 각 인증 유형에 대해 피어 투 피어 IM 보고서에 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-171">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="63b54-172">인증 유형별 피어 투 피어 IM 세션 메트릭</span><span class="sxs-lookup"><span data-stu-id="63b54-172">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63b54-173">이름</span><span class="sxs-lookup"><span data-stu-id="63b54-173">Name</span></span></th>
<th><span data-ttu-id="63b54-174">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="63b54-174">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="63b54-175">설명</span><span class="sxs-lookup"><span data-stu-id="63b54-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63b54-176"><strong>인증 유형</strong></span><span class="sxs-lookup"><span data-stu-id="63b54-176"><strong>Authentication type</strong></span></span></p></td>
<td><p><span data-ttu-id="63b54-177">아니요</span><span class="sxs-lookup"><span data-stu-id="63b54-177">No</span></span></p></td>
<td><p><span data-ttu-id="63b54-p111">세션 참가자가 사용하는 인증 유형입니다. 값은 일반적으로 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-p111">Type of authentication used by the session participants. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="63b54-180">Enterprise</span><span class="sxs-lookup"><span data-stu-id="63b54-180">Enterprise</span></span></p></li>
<li><p><span data-ttu-id="63b54-181">페더레이션된</span><span class="sxs-lookup"><span data-stu-id="63b54-181">Federated</span></span></p></li>
<li><p><span data-ttu-id="63b54-182">C</span><span class="sxs-lookup"><span data-stu-id="63b54-182">PIC</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63b54-183"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="63b54-183"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="63b54-184">아니요</span><span class="sxs-lookup"><span data-stu-id="63b54-184">No</span></span></p></td>
<td><p><span data-ttu-id="63b54-185">세션이 발생한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-185">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63b54-186"><strong>합계</strong></span><span class="sxs-lookup"><span data-stu-id="63b54-186"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="63b54-187">아니요</span><span class="sxs-lookup"><span data-stu-id="63b54-187">No</span></span></p></td>
<td><p><span data-ttu-id="63b54-188">총 세션 수 또는 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="63b54-188">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

