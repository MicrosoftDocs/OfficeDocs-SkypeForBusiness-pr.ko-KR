---
title: 'Lync Server 2013: 피어 투 피어 활동 진단 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc7c6de27a4ccc9cd05777476ac4abc7d6fc9f58
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="93cad-102">Lync Server 2013의 피어 투 피어 활동 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="93cad-102">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93cad-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="93cad-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="93cad-104">피어 투 피어 활동 진단 보고서는 피어 투 피어 통신 세션의 성공 및 실패에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-104">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="93cad-105">Microsoft Lync Server 2013는 서로 다른 종류의 오류를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-105">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="93cad-106">**예상 오류**입니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-106">**Expected failure**.</span></span> <span data-ttu-id="93cad-107">일반적으로 예상 되는 오류는 가장 기술적으로 발생 하는 오류에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="93cad-108">예를 들어 상대방에 게 전화를 걸고 전화를 받을 수 없는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-108">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="93cad-109">통화가 응답 하지 않았으므로 기술적으로는 오류가 발생 하는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-109">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="93cad-110">반면에, Microsoft Lync Server 2013에서는 휴대폰에 응답할 수 없는 경우 휴대폰에 응답 하지 않을 것으로 예상 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-110">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="93cad-111">마찬가지로, 오프 라인 상태에 있는 사용자에 게 인스턴트 메시지를 보내거나 인스턴트 메시징을 지원 하지 않는 전화로 로그온 한 경우에도 예상 되는 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-111">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="93cad-112">**예기치 않은 오류**입니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-112">**Unexpected failure**.</span></span> <span data-ttu-id="93cad-113">예기치 않은 오류는 해당 상황에 따라 발생할 것으로 예상 되는 오류를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="93cad-114">예를 들어 다른 사람에 게 전화를 걸고 해당 사용자가 통화에 응답할 수 있다고 가정 합니다. 그러나 Lync Server 2013에서 음성 메일로 통화를 라우팅하 려는 경우 Exchange 통합 메시징에 대 한 연결이 끊어져서 호출이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-114">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="93cad-115">예기치 않은 오류입니다. 전화가 음성 메일로 라우팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-115">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="93cad-116">일반적으로 오류가 발생 하는 경우는 예기치 않은 오류 이며, 사용자 교육 이나 유사한 조치를 통해 해결할 수 없는 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-116">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="93cad-p104">성공, 예상 오류 및 예기치 않은 오류 메트릭은 총 세션 메트릭에 추가되지 않을 수 있습니다. 예를 들어 위 그림에는 다음과 같은 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93cad-119">성공</span><span class="sxs-lookup"><span data-stu-id="93cad-119">Successes</span></span></th>
<th><span data-ttu-id="93cad-120">예상 오류</span><span class="sxs-lookup"><span data-stu-id="93cad-120">Expected failures</span></span></th>
<th><span data-ttu-id="93cad-121">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="93cad-121">Unexpected failures</span></span></th>
<th><span data-ttu-id="93cad-122">총 세션</span><span class="sxs-lookup"><span data-stu-id="93cad-122">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93cad-123">2024</span><span class="sxs-lookup"><span data-stu-id="93cad-123">2024</span></span></p></td>
<td><p><span data-ttu-id="93cad-124">469</span><span class="sxs-lookup"><span data-stu-id="93cad-124">469</span></span></p></td>
<td><p><span data-ttu-id="93cad-125">16 </span><span class="sxs-lookup"><span data-stu-id="93cad-125">16</span></span></p></td>
<td><p><span data-ttu-id="93cad-126">2521</span><span class="sxs-lookup"><span data-stu-id="93cad-126">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="93cad-127">이 경우 2024+469+16=총 세션 수는 2,509개가 되지만 총 세션 열에는 총 세션 수가 2,521개로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-127">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="93cad-128">"누락된" 12개 세션은 시스템에서 성공 또는 실패로 분류하지 못한 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-128">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="93cad-129">타사 제품에서 Lync Server에 익숙하지 않은 새로운 진단 코드를 도입 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-129">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="93cad-130">이와 같은 경우 해당 제품을 사용하여 전화를 걸고 해당 진단 코드를 보고하는 경우를 항상 성공, 예상 오류 또는 예기치 않은 오류로 분류할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-130">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="93cad-131">피어 투 피어 활동 진단 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="93cad-131">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="93cad-132">피어 투 피어 진단 보고서는 모니터링 보고서 홈 페이지에서 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-132">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="93cad-133">다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 실패 분포 보고서](lync-server-2013-failure-distribution-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-133">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="93cad-134">예기치 않은 오류량</span><span class="sxs-lookup"><span data-stu-id="93cad-134">Unexpected failure volume</span></span>

  - <span data-ttu-id="93cad-135">예상 오류량</span><span class="sxs-lookup"><span data-stu-id="93cad-135">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="93cad-136">피어 투 피어 활동 진단 보고서를 가장 효율적으로 활용</span><span class="sxs-lookup"><span data-stu-id="93cad-136">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="93cad-p107">다양한 방법으로 피어 투 피어 활동 진단 보고서를 필터링할 수 있지만, 기본적으로 이러한 필터링 옵션은 보기에서 숨겨집니다. 사용 가능한 필터링 옵션을 보려면 보고서 창 오른쪽 위의 매개 변수 표시/숨기기 단추를 클릭합니다. 그러면 필터링 옵션을 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-p107">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view. To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window. Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="93cad-140">필터</span><span class="sxs-lookup"><span data-stu-id="93cad-140">Filters</span></span>

<span data-ttu-id="93cad-p108">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 피어 투 피어 활동 진단 보고서를 통해 세션 형식(예: 인스턴트 메시징, 파일 전송 또는 응용 프로그램 공유)과 같은 항목으로 필터링할 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 통화는 시간, 일, 주 및 월별로 그룹이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing). You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="93cad-145">다음 표에서는 피어 투 피어 활동 진단 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-145">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="93cad-146">피어 투 피어 활동 진단 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="93cad-146">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93cad-147">이름</span><span class="sxs-lookup"><span data-stu-id="93cad-147">Name</span></span></th>
<th><span data-ttu-id="93cad-148">설명</span><span class="sxs-lookup"><span data-stu-id="93cad-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93cad-149"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="93cad-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="93cad-p109">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="93cad-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="93cad-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="93cad-p110">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="93cad-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="93cad-155">7/7/2012</span></span></p>
<p><span data-ttu-id="93cad-156">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="93cad-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="93cad-157">7/3/2012</span></span></p>
<p><span data-ttu-id="93cad-158">주는 항상 일요일부터 토요일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93cad-159"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="93cad-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="93cad-p111">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="93cad-162">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="93cad-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="93cad-p112">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="93cad-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="93cad-165">7/7/2012</span></span></p>
<p><span data-ttu-id="93cad-166">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="93cad-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="93cad-167">7/3/2012</span></span></p>
<p><span data-ttu-id="93cad-168">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93cad-169"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="93cad-169"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="93cad-p113">시간 간격입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="93cad-172">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="93cad-172">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="93cad-173">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="93cad-173">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="93cad-174">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="93cad-174">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="93cad-175">월별(최대 12개월 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="93cad-175">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="93cad-p114">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93cad-178"><strong>그룹</strong></span><span class="sxs-lookup"><span data-stu-id="93cad-178"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="93cad-p115">등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93cad-182"><strong>형식</strong></span><span class="sxs-lookup"><span data-stu-id="93cad-182"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="93cad-p116">발생한 통신 활동의 유형을 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-p116">Indicates the type of communication activity that took place. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="93cad-185">모든</span><span class="sxs-lookup"><span data-stu-id="93cad-185">[All]</span></span></p></li>
<li><p><span data-ttu-id="93cad-186">인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="93cad-186">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="93cad-187">파일 전송</span><span class="sxs-lookup"><span data-stu-id="93cad-187">File transfer</span></span></p></li>
<li><p><span data-ttu-id="93cad-188">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="93cad-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="93cad-189">오디오만</span><span class="sxs-lookup"><span data-stu-id="93cad-189">Audio</span></span></p></li>
<li><p><span data-ttu-id="93cad-190">비디오</span><span class="sxs-lookup"><span data-stu-id="93cad-190">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="93cad-191">메트릭(형식별)</span><span class="sxs-lookup"><span data-stu-id="93cad-191">Metrics (per modality)</span></span>

<span data-ttu-id="93cad-192">다음 표에서는 각 형식에 대해 피어 투 피어 활동 진단 보고서에 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-192">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="93cad-193">메트릭(형식별)</span><span class="sxs-lookup"><span data-stu-id="93cad-193">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93cad-194">이름</span><span class="sxs-lookup"><span data-stu-id="93cad-194">Name</span></span></th>
<th><span data-ttu-id="93cad-195">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="93cad-195">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="93cad-196">설명</span><span class="sxs-lookup"><span data-stu-id="93cad-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93cad-197"><strong>성공량</strong></span><span class="sxs-lookup"><span data-stu-id="93cad-197"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="93cad-198">아니요</span><span class="sxs-lookup"><span data-stu-id="93cad-198">No</span></span></p></td>
<td><p><span data-ttu-id="93cad-199">성공한 총 피어 투 피어 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-199">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93cad-200"><strong>성공 비율</strong></span><span class="sxs-lookup"><span data-stu-id="93cad-200"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="93cad-201">아니요</span><span class="sxs-lookup"><span data-stu-id="93cad-201">No</span></span></p></td>
<td><p><span data-ttu-id="93cad-p117">중요 문제와 함께 완료된 피어 투 피어 세션의 비율입니다. 성공량을 총 세션으로 나눠서 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-p117">Percentage of peer-to-peer sessions that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93cad-204"><strong>예상 오류량</strong></span><span class="sxs-lookup"><span data-stu-id="93cad-204"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="93cad-205">아니요</span><span class="sxs-lookup"><span data-stu-id="93cad-205">No</span></span></p></td>
<td><p><span data-ttu-id="93cad-206">예상 오류가 &quot;&quot; 발생 한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-206">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="93cad-p118">예상 오류는 발생할 것으로 예상된 오류입니다. 예를 들어 사용자가 자신의 상태를 방해 금지로 설정한 경우 해당 사용자에 대한 통화가 실패할 것으로 예상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93cad-209"><strong>예상 오류 비율</strong></span><span class="sxs-lookup"><span data-stu-id="93cad-209"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="93cad-210">아니요</span><span class="sxs-lookup"><span data-stu-id="93cad-210">No</span></span></p></td>
<td><p><span data-ttu-id="93cad-p119">예상 오류가 발생한 피어 투 피어 세션의 비율입니다. 예상 오류량을 총 세션으로 나눠서 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-p119">Percentage of peer-to-peer sessions that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93cad-213"><strong>예기치 않은 오류량</strong></span><span class="sxs-lookup"><span data-stu-id="93cad-213"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="93cad-214">아니요</span><span class="sxs-lookup"><span data-stu-id="93cad-214">No</span></span></p></td>
<td><p><span data-ttu-id="93cad-215">예기치 않은 오류가 &quot;&quot; 발생 한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-215">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="93cad-p120">예기치 않은 오류는 일반적으로 정상 상태의 시스템으로 보이지만 예기치 않게 발생한 오류입니다. 예를 들어 발신자가 보류 상태일 때는 통화가 종료되지 않아야 합니다. 하지만 통화가 종료되면 바로 예기치 않은 오류로 플래그 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93cad-219"><strong>예기치 않은 오류 비율</strong></span><span class="sxs-lookup"><span data-stu-id="93cad-219"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="93cad-220">아니요</span><span class="sxs-lookup"><span data-stu-id="93cad-220">No</span></span></p></td>
<td><p><span data-ttu-id="93cad-p121">예기치 않은 오류가 발생한 피어 투 피어 세션의 비율입니다. 예기치 않은 오류량을 총 세션으로 나눠서 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-p121">Percentage of peer-to-peer sessions that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="93cad-223"><strong>총 세션</strong></span><span class="sxs-lookup"><span data-stu-id="93cad-223"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="93cad-224">아니요</span><span class="sxs-lookup"><span data-stu-id="93cad-224">No</span></span></p></td>
<td><p><span data-ttu-id="93cad-225">성공한 세션, 실패한 세션(예상 오류 및 예기치 않은 오류 모두) 및 분류되지 않은 세션을 포함한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="93cad-225">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

