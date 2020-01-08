---
title: 'Lync Server 2013: 피어 투 피어 작업 진단 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f435a4b0ff0ec42e8898260c3ada528963bbebb1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="7688f-102">Lync Server 2013의 피어 투 피어 작업 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="7688f-102">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7688f-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7688f-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7688f-104">피어 투 피어 작업 진단 보고서는 피어 투 피어 통신 세션의 성공 및 실패에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-104">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="7688f-105">Microsoft Lync Server 2013는 서로 다른 종류의 오류를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-105">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="7688f-106">**오류가 발생**했습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-106">**Expected failure**.</span></span> <span data-ttu-id="7688f-107">일반적으로 예상 되는 오류는 대부분의 기술적인 측면 에서만 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="7688f-108">예를 들어 다른 사람에 게 전화를 걸 때, 사무실 밖에 서 전화를 받을 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="7688f-108">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="7688f-109">호출이 응답 되지 않았으므로 기술적으로는 오류로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-109">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="7688f-110">다른 한편으로는이 문제가 발생 했습니다. Microsoft Lync Server 2013는 휴대폰에 응답 하는 데 사용할 수 없는 경우 휴대폰에 응답 하지 않을 것으로 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-110">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="7688f-111">마찬가지로, 오프 라인 상태에 있는 사용자에 게 인스턴트 메시지를 보내거나 메신저를 지원 하지 않는 전화기로 로그온 한 경우에도 예상 되는 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-111">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="7688f-112">**예기치 않은 오류**.</span><span class="sxs-lookup"><span data-stu-id="7688f-112">**Unexpected failure**.</span></span> <span data-ttu-id="7688f-113">예기치 않은 오류는 상황에 따라 발생 하는 것으로 예상 되지 않는 오류를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="7688f-114">예를 들어 다른 사람에 게 전화를 걸고 해당 사용자가 전화를 받을 수 있습니다. 그러나 Lync Server 2013에서 음성 메일로 통화를 회람 하려고 하면 Exchange 통합 메시징의 연결이 끊어져서 호출에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-114">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="7688f-115">예기치 않은 오류가 발생 했습니다 .이 통화는 항상 보이스 메일로 라우팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-115">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="7688f-116">일반적으로 예기치 않은 오류가 발생 하는 경우에는 사용자 교육 이나 유사한 조치를 통해 해결할 수 없는 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-116">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="7688f-117">성공, 예상 실패, 예기치 않은 실패 메트릭이 총 세션 메트릭에 추가 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-117">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric.</span></span> <span data-ttu-id="7688f-118">예를 들어 앞의 그림에는 다음 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-118">For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7688f-119">회의</span><span class="sxs-lookup"><span data-stu-id="7688f-119">Successes</span></span></th>
<th><span data-ttu-id="7688f-120">예상 되는 오류</span><span class="sxs-lookup"><span data-stu-id="7688f-120">Expected failures</span></span></th>
<th><span data-ttu-id="7688f-121">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="7688f-121">Unexpected failures</span></span></th>
<th><span data-ttu-id="7688f-122">총 세션</span><span class="sxs-lookup"><span data-stu-id="7688f-122">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7688f-123">2024</span><span class="sxs-lookup"><span data-stu-id="7688f-123">2024</span></span></p></td>
<td><p><span data-ttu-id="7688f-124">469</span><span class="sxs-lookup"><span data-stu-id="7688f-124">469</span></span></p></td>
<td><p><span data-ttu-id="7688f-125">16</span><span class="sxs-lookup"><span data-stu-id="7688f-125">16</span></span></p></td>
<td><p><span data-ttu-id="7688f-126">2521</span><span class="sxs-lookup"><span data-stu-id="7688f-126">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7688f-127">2024 + 469 + 16을 추가 하는 경우 총 2509 세션을 받을 수 있지만 총 세션 열에는 총 2521 세션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-127">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="7688f-128">"누락 된" 12 개 세션은 시스템에서 성공 또는 실패로 분류할 수 없는 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-128">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="7688f-129">이는 타사 제품이 Lync Server에 익숙하지 않은 새로운 진단 코드를 도입 하는 경우에 해당 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-129">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="7688f-130">이 경우 해당 제품을 사용 하 여 호출 하 고 해당 진단 코드를 보고 하면 항상 성공, 실패 또는 예기치 않은 오류에 대 한 분류할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-130">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="7688f-131">피어 투 피어 작업 진단 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="7688f-131">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="7688f-132">피어 투 피어 진단 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-132">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="7688f-133">다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 실패 배포 보고서](lync-server-2013-failure-distribution-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-133">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="7688f-134">예기치 않은 오류 볼륨</span><span class="sxs-lookup"><span data-stu-id="7688f-134">Unexpected failure volume</span></span>

  - <span data-ttu-id="7688f-135">예상 고장 볼륨</span><span class="sxs-lookup"><span data-stu-id="7688f-135">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="7688f-136">피어 투 피어 작업 진단 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="7688f-136">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="7688f-137">피어 투 피어 작업 진단 보고서를 필터링 하는 방법에는 여러 가지가 있지만 기본적으로 이러한 필터링 옵션은 보기에서 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-137">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view.</span></span> <span data-ttu-id="7688f-138">사용할 수 있는 필터링 옵션을 보려면 보고서 창의 오른쪽 위 모서리에 있는 매개 변수 표시/숨기기 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-138">To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window.</span></span> <span data-ttu-id="7688f-139">이 작업을 수행 하면 필터링 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-139">Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7688f-140">필터가</span><span class="sxs-lookup"><span data-stu-id="7688f-140">Filters</span></span>

<span data-ttu-id="7688f-141">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-141">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="7688f-142">예를 들어 피어 투 피어 작업 진단 보고서를 사용 하 여 세션 형식 (예: 인스턴트 메시지, 파일 전송 또는 응용 프로그램 공유) 등의 항목을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-142">For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing).</span></span> <span data-ttu-id="7688f-143">데이터 그룹화 방법을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-143">You can also choose how data should be grouped.</span></span> <span data-ttu-id="7688f-144">이 경우 통화는 시, 일, 주 또는 월로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-144">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="7688f-145">다음 표에는 피어 투 피어 작업 진단 보고서에 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-145">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="7688f-146">피어 투 피어 작업 진단 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="7688f-146">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7688f-147">이름</span><span class="sxs-lookup"><span data-stu-id="7688f-147">Name</span></span></th>
<th><span data-ttu-id="7688f-148">설명</span><span class="sxs-lookup"><span data-stu-id="7688f-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7688f-149"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="7688f-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7688f-150">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-150">Start date/time for the time range.</span></span> <span data-ttu-id="7688f-151">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-151">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7688f-152">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="7688f-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7688f-153">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-153">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="7688f-154">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-154">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7688f-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7688f-155">7/7/2012</span></span></p>
<p><span data-ttu-id="7688f-156">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="7688f-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7688f-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7688f-157">7/3/2012</span></span></p>
<p><span data-ttu-id="7688f-158">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7688f-159"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="7688f-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7688f-160">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-160">End date/time for the time range.</span></span> <span data-ttu-id="7688f-161">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-161">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7688f-162">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="7688f-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7688f-163">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-163">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="7688f-164">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-164">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7688f-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7688f-165">7/7/2012</span></span></p>
<p><span data-ttu-id="7688f-166">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="7688f-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7688f-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7688f-167">7/3/2012</span></span></p>
<p><span data-ttu-id="7688f-168">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7688f-169"><strong>간격만</strong></span><span class="sxs-lookup"><span data-stu-id="7688f-169"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="7688f-170">시간 간격.</span><span class="sxs-lookup"><span data-stu-id="7688f-170">Time interval.</span></span> <span data-ttu-id="7688f-171">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-171">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7688f-172">매시간 (최대 25 시간 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="7688f-172">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7688f-173">매일 (최대 31 일이 표시 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="7688f-173">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7688f-174">주간 (최대 12 주를 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="7688f-174">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7688f-175">월간 (최대 12 개월을 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="7688f-175">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="7688f-176">시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-176">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="7688f-177">예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-177">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7688f-178"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="7688f-178"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="7688f-179">등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-179">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="7688f-180">개별 풀을 선택 하거나 <strong>[모두]</strong> 를 클릭 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-180">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="7688f-181">이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-181">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7688f-182"><strong>모달</strong></span><span class="sxs-lookup"><span data-stu-id="7688f-182"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="7688f-183">발생 한 통신 활동 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-183">Indicates the type of communication activity that took place.</span></span> <span data-ttu-id="7688f-184">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-184">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7688f-185">모든</span><span class="sxs-lookup"><span data-stu-id="7688f-185">[All]</span></span></p></li>
<li><p><span data-ttu-id="7688f-186">인스턴트 메시지</span><span class="sxs-lookup"><span data-stu-id="7688f-186">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="7688f-187">파일 전송</span><span class="sxs-lookup"><span data-stu-id="7688f-187">File transfer</span></span></p></li>
<li><p><span data-ttu-id="7688f-188">응용 프로그램 공유</span><span class="sxs-lookup"><span data-stu-id="7688f-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="7688f-189">오디오</span><span class="sxs-lookup"><span data-stu-id="7688f-189">Audio</span></span></p></li>
<li><p><span data-ttu-id="7688f-190">비디오만</span><span class="sxs-lookup"><span data-stu-id="7688f-190">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="7688f-191">메트릭 (각에 대 한 모달)</span><span class="sxs-lookup"><span data-stu-id="7688f-191">Metrics (per modality)</span></span>

<span data-ttu-id="7688f-192">다음 표에는 각 모달 피어 투 피어 작업 진단 보고서에 제공 된 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-192">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="7688f-193">메트릭 (각에 대 한 모달)</span><span class="sxs-lookup"><span data-stu-id="7688f-193">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7688f-194">이름</span><span class="sxs-lookup"><span data-stu-id="7688f-194">Name</span></span></th>
<th><span data-ttu-id="7688f-195">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7688f-195">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7688f-196">설명</span><span class="sxs-lookup"><span data-stu-id="7688f-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7688f-197"><strong>성공 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="7688f-197"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7688f-198">아니요</span><span class="sxs-lookup"><span data-stu-id="7688f-198">No</span></span></p></td>
<td><p><span data-ttu-id="7688f-199">성공한 피어 투 피어 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-199">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7688f-200"><strong>성공 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="7688f-200"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7688f-201">아니요</span><span class="sxs-lookup"><span data-stu-id="7688f-201">No</span></span></p></td>
<td><p><span data-ttu-id="7688f-202">중대 한 문제가 발생 하 여 완료 된 피어 투 피어 세션의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-202">Percentage of peer-to-peer sessions that completed with significant problems.</span></span> <span data-ttu-id="7688f-203">성공 볼륨을 총 세션으로 나누는 방법으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-203">Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7688f-204"><strong>예상 고장 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="7688f-204"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7688f-205">아니요</span><span class="sxs-lookup"><span data-stu-id="7688f-205">No</span></span></p></td>
<td><p><span data-ttu-id="7688f-206">예상 되는 오류가 &quot;&quot; 발생 한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-206">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="7688f-207">예상 되는 실패는 예상 되는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-207">An expected failure is a failure that is expected to happen.</span></span> <span data-ttu-id="7688f-208">예를 들어 사용자가 자신의 상태를 방해 금지로 설정 하면 해당 사용자에 게 전화를 거는 데 실패 하는 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-208">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7688f-209"><strong>예상 되는 실패 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="7688f-209"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7688f-210">아니요</span><span class="sxs-lookup"><span data-stu-id="7688f-210">No</span></span></p></td>
<td><p><span data-ttu-id="7688f-211">예상 되는 오류가 발생 한 피어 투 피어 세션의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-211">Percentage of peer-to-peer sessions that experienced an expected error.</span></span> <span data-ttu-id="7688f-212">예상 고장 볼륨을 총 세션으로 나누어 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-212">Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7688f-213"><strong>예기치 않은 오류 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="7688f-213"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="7688f-214">아니요</span><span class="sxs-lookup"><span data-stu-id="7688f-214">No</span></span></p></td>
<td><p><span data-ttu-id="7688f-215">예기치 않은 오류가 &quot;&quot; 발생 한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-215">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="7688f-216">예기치 않은 오류가 발생 하는 것은 정상적인 시스템 때문 이라고 표시 되는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-216">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="7688f-217">예를 들어 호출자가 대기 상태로 설정 된 경우에는 통화가 종료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-217">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="7688f-218">이 문제가 발생 하면 예기치 않은 오류로 플래그가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-218">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7688f-219"><strong>예기치 않은 오류 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="7688f-219"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="7688f-220">아니요</span><span class="sxs-lookup"><span data-stu-id="7688f-220">No</span></span></p></td>
<td><p><span data-ttu-id="7688f-221">예기치 않은 오류가 발생 한 피어 투 피어 세션의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-221">Percentage of peer-to-peer sessions that experienced an unexpected error.</span></span> <span data-ttu-id="7688f-222">예상 하지 못한 볼륨을 총 세션으로 나누면 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-222">Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7688f-223"><strong>총 세션</strong></span><span class="sxs-lookup"><span data-stu-id="7688f-223"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7688f-224">아니요</span><span class="sxs-lookup"><span data-stu-id="7688f-224">No</span></span></p></td>
<td><p><span data-ttu-id="7688f-225">성공한 세션, 실패 한 세션 (예상 되는 실패 및 예기치 못한 실패), 범주화 되지 않은 세션 등의 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7688f-225">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

