---
title: 'Lync Server 2013: 통화 진단 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ebd3da761fe9923f05c2ddd5dfced852b4b27e6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="d67b4-102">Lync Server 2013의 통화 진단 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="d67b4-102">Call Diagnostic Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d67b4-103">_**마지막으로 수정 된 항목:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="d67b4-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="d67b4-104">통화 진단 요약 보고서는 실패 한 피어-투-피어 및 회의 세션에 대 한 전체 확인을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-104">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions.</span></span> <span data-ttu-id="d67b4-105">이 보고서에는 두 세션 유형의 전체 오류율이 표시 되 고, 오류 정보는 세션 모달 형식에 따라 아래로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-105">The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="d67b4-106">인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="d67b4-106">Instant messaging</span></span>

  - <span data-ttu-id="d67b4-107">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="d67b4-107">Application sharing</span></span>

  - <span data-ttu-id="d67b4-108">파일 전송</span><span class="sxs-lookup"><span data-stu-id="d67b4-108">File transfer</span></span>

  - <span data-ttu-id="d67b4-109">오디오만</span><span class="sxs-lookup"><span data-stu-id="d67b4-109">Audio</span></span>

  - <span data-ttu-id="d67b4-110">비디오</span><span class="sxs-lookup"><span data-stu-id="d67b4-110">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="d67b4-111">통화 진단 요약 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="d67b4-111">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="d67b4-112">통화 진단 요약 보고서는 모니터링 보고서 홈 페이지에서 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-112">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="d67b4-113">통화 진단 요약 보고서에서 보고서의 피어 투 피어 세션 요약 섹션에서 오류율을 클릭 하 여 [Lync Server 2013의 피어 투 피어 활동 진단 보고서](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-113">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="d67b4-114">다음 회의 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 전화 회의 진단 보고서](lync-server-2013-conference-diagnostic-report.md) 에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-114">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="d67b4-115">전체 세션 실패율</span><span class="sxs-lookup"><span data-stu-id="d67b4-115">Overall session failure rate</span></span>

  - <span data-ttu-id="d67b4-116">회의 센터 실패율</span><span class="sxs-lookup"><span data-stu-id="d67b4-116">Focus failure rate</span></span>

  - <span data-ttu-id="d67b4-117">MCU 실패율</span><span class="sxs-lookup"><span data-stu-id="d67b4-117">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="d67b4-118">통화 진단 요약 보고서의 효과적인 활용</span><span class="sxs-lookup"><span data-stu-id="d67b4-118">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="d67b4-119">통화 진단 요약 보고서에는 Microsoft Lync Server 2013에서 사용 되는 다양 한 형식의 실패율을 비교 하는 그래프가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-119">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="d67b4-120">이러한 그래프의 열은 실제로 hotlinks 예를 들어 피어 투 피어 세션에 대 한 인스턴트 메시징 열을 클릭 하면 호출 진단 요약 보고서에 포함 된 모든 인스턴트 메시징 세션에 대 한 추가 정보를 제공 하는 보고서 인 [Lync Server 2013의 피어 투 피어 활동 진단 보고서](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)인스턴스로 드릴 다운 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-120">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d67b4-121">필터</span><span class="sxs-lookup"><span data-stu-id="d67b4-121">Filters</span></span>

<span data-ttu-id="d67b4-122">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-122">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="d67b4-123">예를 들어 통화 진단 요약 보고서를 사용 하면 세션에서 사용 되는 등록자 풀 또는에 지 서버와 같은 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-123">For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session.</span></span> <span data-ttu-id="d67b4-124">또한 데이터의 그룹 지정 방식도 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-124">You can also choose how data should be grouped.</span></span> <span data-ttu-id="d67b4-125">이 경우 통화는 시간, 일, 주 및 월별로 그룹이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-125">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="d67b4-126">다음 표에서는 통화 진단 요약 보고서에서 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-126">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="d67b4-127">통화 진단 요약 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="d67b4-127">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d67b4-128">이름</span><span class="sxs-lookup"><span data-stu-id="d67b4-128">Name</span></span></th>
<th><span data-ttu-id="d67b4-129">설명</span><span class="sxs-lookup"><span data-stu-id="d67b4-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d67b4-130"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="d67b4-130"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="d67b4-p105">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="d67b4-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d67b4-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d67b4-p106">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d67b4-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d67b4-136">7/7/2012</span></span></p>
<p><span data-ttu-id="d67b4-137">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d67b4-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d67b4-138">7/3/2012</span></span></p>
<p><span data-ttu-id="d67b4-139">주는 항상 일요일부터 토요일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d67b4-140"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="d67b4-140"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="d67b4-p107">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="d67b4-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d67b4-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d67b4-p108">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d67b4-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d67b4-146">7/7/2012</span></span></p>
<p><span data-ttu-id="d67b4-147">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d67b4-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d67b4-148">7/3/2012</span></span></p>
<p><span data-ttu-id="d67b4-149">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d67b4-150"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="d67b4-150"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="d67b4-p109">시간 간격입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d67b4-153">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="d67b4-153">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d67b4-154">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="d67b4-154">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d67b4-155">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="d67b4-155">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d67b4-156">월별(최대 12개월 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="d67b4-156">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="d67b4-p110">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d67b4-159"><strong>그룹</strong></span><span class="sxs-lookup"><span data-stu-id="d67b4-159"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="d67b4-p111">등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-p111">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="d67b4-163">피어 투 피어 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d67b4-163">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="d67b4-164">다음 표에서는 피어 투 피어 세션 (즉, 참가자가 두 개만 포함 되는 세션)에 대해 통화 진단 요약 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-164">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="d67b4-165">피어 투 피어 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d67b4-165">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d67b4-166">이름</span><span class="sxs-lookup"><span data-stu-id="d67b4-166">Name</span></span></th>
<th><span data-ttu-id="d67b4-167">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="d67b4-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d67b4-168">설명</span><span class="sxs-lookup"><span data-stu-id="d67b4-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d67b4-169"><strong>총 세션</strong></span><span class="sxs-lookup"><span data-stu-id="d67b4-169"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d67b4-170">아니요</span><span class="sxs-lookup"><span data-stu-id="d67b4-170">No</span></span></p></td>
<td><p><span data-ttu-id="d67b4-171">수행 된 총 피어 투 피어 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-171">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d67b4-172"><strong>실패율</strong></span><span class="sxs-lookup"><span data-stu-id="d67b4-172"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="d67b4-173">아니요</span><span class="sxs-lookup"><span data-stu-id="d67b4-173">No</span></span></p></td>
<td><p><span data-ttu-id="d67b4-174">실패한 피어 투 피어 세션의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-174">Percentage of peer-to-peer sessions that failed.</span></span> <span data-ttu-id="d67b4-175">이 항목을 클릭 하면 보고서에 실패 한 피어 투 피어 세션에 대 한 자세한 정보가 표시 되는 피어 투 피어 활동 진단 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-175">When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="d67b4-176">회의 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d67b4-176">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="d67b4-177">다음 표에서는 회의 세션 (즉, 참가자가 세 명 이상인 세션)에 대해 통화 진단 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-177">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="d67b4-178">회의 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d67b4-178">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d67b4-179">이름</span><span class="sxs-lookup"><span data-stu-id="d67b4-179">Name</span></span></th>
<th><span data-ttu-id="d67b4-180">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="d67b4-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d67b4-181">설명</span><span class="sxs-lookup"><span data-stu-id="d67b4-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d67b4-182"><strong>총 전화 회의</strong></span><span class="sxs-lookup"><span data-stu-id="d67b4-182"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="d67b4-183">아니요</span><span class="sxs-lookup"><span data-stu-id="d67b4-183">No</span></span></p></td>
<td><p><span data-ttu-id="d67b4-184">수행 된 총 전화 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-184">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d67b4-185"><strong>총 전화 회의 세션</strong></span><span class="sxs-lookup"><span data-stu-id="d67b4-185"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d67b4-186">아니요</span><span class="sxs-lookup"><span data-stu-id="d67b4-186">No</span></span></p></td>
<td><p><span data-ttu-id="d67b4-187">수행 된 총 회의 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-187">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d67b4-188"><strong>전체 세션 실패율</strong></span><span class="sxs-lookup"><span data-stu-id="d67b4-188"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="d67b4-189">아니요</span><span class="sxs-lookup"><span data-stu-id="d67b4-189">No</span></span></p></td>
<td><p><span data-ttu-id="d67b4-190">실패 한 총 회의 세션의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-190">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d67b4-191"><strong>회의 센터 세션</strong></span><span class="sxs-lookup"><span data-stu-id="d67b4-191"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d67b4-192">아니요</span><span class="sxs-lookup"><span data-stu-id="d67b4-192">No</span></span></p></td>
<td><p><span data-ttu-id="d67b4-193">실패 한 총 포커스 기반 전화 회의 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-193">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d67b4-194"><strong>회의 센터 실패율</strong></span><span class="sxs-lookup"><span data-stu-id="d67b4-194"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="d67b4-195">아니요</span><span class="sxs-lookup"><span data-stu-id="d67b4-195">No</span></span></p></td>
<td><p><span data-ttu-id="d67b4-196">실패 한 집중 (Focus) 기반 회의 세션의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-196">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d67b4-197"><strong>MCU 세션</strong></span><span class="sxs-lookup"><span data-stu-id="d67b4-197"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d67b4-198">아니요</span><span class="sxs-lookup"><span data-stu-id="d67b4-198">No</span></span></p></td>
<td><p><span data-ttu-id="d67b4-199">실패 한 총 회의 서버 기반 (이전의 Multipoint 컨트롤 단위 또는 MCU) 전화 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-199">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d67b4-200"><strong>MCU 실패율</strong></span><span class="sxs-lookup"><span data-stu-id="d67b4-200"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="d67b4-201">아니요</span><span class="sxs-lookup"><span data-stu-id="d67b4-201">No</span></span></p></td>
<td><p><span data-ttu-id="d67b4-202">실패 한 회의 서버 기반 (이전의 Multipoint Control Unit 또는 MCU) 회의의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="d67b4-202">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

