---
title: 'Lync Server 2013: Top Failures 보고서'
description: 'Lync Server 2013: Top Failures 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 768c9a99916dece9eb76877b0cd65b057697ff95
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561274"
---
# <a name="top-failures-report-in-lync-server-2013"></a><span data-ttu-id="ef3b8-103">Lync Server 2013의 상위 실패 보고서</span><span class="sxs-lookup"><span data-stu-id="ef3b8-103">Top Failures Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef3b8-104">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ef3b8-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ef3b8-p101">Top Failures 보고서는 가장 일반적으로 보고되는 오류 및 해당 추세를 시간별로 조사합니다. 오류는 다음과 같은 두 가지 측정 단위의 조합을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-p101">The Top Failures Report provides a look at the most-commonly reported failures and their trends over time. Failures are based on a combination of the following two metrics:</span></span>

  - <span data-ttu-id="ef3b8-p102">**진단 ID**. SIP 메시지에 연결된 고유 식별자입니다(ms-diagnostics 헤더 형식). 진단 ID는 통화 관련 문제 해결에 유용한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-p102">**Diagnostic ID**. Unique identifier (in the form of an ms-diagnostics header) that is attached to a SIP message. Diagnostic IDs provide information useful in troubleshooting call-related problems.</span></span>

  - <span data-ttu-id="ef3b8-110">**응답 코드**.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-110">**Response code**.</span></span> <span data-ttu-id="ef3b8-111">응답 코드는 SIP 통신 세션에서 SIP 요청에 응답하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-111">Response codes are used in SIP communication sessions to respond to SIP requests.</span></span> <span data-ttu-id="ef3b8-112">예를 들어 Ken이 Pilar Ackerman에게 INVITE 요청을 보낸다고 가정해보십시오(즉, Ken Myer가 Pilar Ackerman을 호출한다고 가정).</span><span class="sxs-lookup"><span data-stu-id="ef3b8-112">For example, suppose Ken sends the INVITE request to Pilar Ackerman (that is, suppose Ken Myer calls Pilar Ackerman).</span></span> <span data-ttu-id="ef3b8-113">Pilar가 응답하면 해당 전화기가 응답 코드 200(OK)을 전송해서 Ken의 전화에서 Pilar가 응답했는지를 확인할 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-113">If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered.</span></span> <span data-ttu-id="ef3b8-114">Top Failures 보고서에는 통화 실패에 대 한 응답으로 전송 된 응답 코드만 포함 됩니다. Lync Server는 통화 중에 발생 한 모든 응답 코드를 추적 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-114">The Top Failures Report only includes response codes that were sent in response to a call failure; Lync Server does not keep track of all the response codes issued during the course of a call.</span></span>

<span data-ttu-id="ef3b8-115">정보는 오류가 발생한 총 세션 수뿐만 아니라 이 오류로 영향을 받는 총 사용자 수에 대해서도 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-115">Information is reported not only for the total number of sessions where a failure occurred but also for the total number of users who were impacted by the failure.</span></span>

<div>

## <a name="accessing-the-top-failures-report"></a><span data-ttu-id="ef3b8-116">Top Failures 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="ef3b8-116">Accessing the Top Failures Report</span></span>

<span data-ttu-id="ef3b8-117">Top Failures 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-117">The Top Failures Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="ef3b8-118">보고 된 세션 메트릭을 클릭 하면 [Lync Server 2013의 실패 분포 보고서](lync-server-2013-failure-distribution-report.md)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-118">Clicking the Reported sessions metric will take you to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a><span data-ttu-id="ef3b8-119">Top Failures 보고서의 모범 사례 만들기</span><span class="sxs-lookup"><span data-stu-id="ef3b8-119">Making the Best Use of the Top Failures Report</span></span>

<span data-ttu-id="ef3b8-p105">Top Failures 보고서는 한 가지 측면에서 일반적이지 않습니다. 이 보고서는 진단 ID를 한 번에 최대 5개까지 필터링할 수 있습니다. 일반적으로는 사용자 SIP 주소 하나와 같이 항목을 한 번에 하나만 필터링할 수 있습니다. 여러 진단 ID를 필터링하려면 진단 ID 상자에 각 ID를 입력하기만 하면 됩니다. ID는 쉼표로 구분합니다. 필요한 경우 각 쉼표 다음에 빈 칸을 남길 수 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-p105">The Top Failures Report is unusual in one regard: it allows you to filter on as many as 5 diagnostic IDs at once. (Typically you can only filter on one item – such as one user SIP address – at a time.) To filter on multiple diagnostic IDs, simply enter each ID in the Diagnostic IDs box, separating the IDs by using commas. (If you want to, you can leave a blank space after each comma.) For example:</span></span>

<span data-ttu-id="ef3b8-123">1011, 2412, 1033, 52116, 1008</span><span class="sxs-lookup"><span data-stu-id="ef3b8-123">1011, 2412, 1033, 52116, 1008</span></span>

<span data-ttu-id="ef3b8-124">이를 수행하면 이러한 5개의 진단 ID 중 하나 이상을 보고한 실패한 통화만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-124">Do that, and only failed calls that reported at least one of those five diagnostic IDs will be displayed.</span></span>

<span data-ttu-id="ef3b8-p106">응답 코드 위에 마우스를 두면 해당 응답 코드의 의미가 표시된 도구 상자가 나타납니다. 예를 들어 응답 코드 486 위에 마우스를 두면 다음 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-p106">If you hold your mouse over a Response code you'll see a tooltip that tells you what the Response code in question means. For example, if you hold the mouse over the Response code 486 you'll see this message:</span></span>

<span data-ttu-id="ef3b8-127">여기에서 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-127">Busy Here.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ef3b8-128">필터</span><span class="sxs-lookup"><span data-stu-id="ef3b8-128">Filters</span></span>

<span data-ttu-id="ef3b8-p107">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 상위 실패 보고서에서는 활동 유형(피어 투 피어 세션 또는 회의 세션)과 같은 항목이나 실패한 세션에 수반된 SIP 응답 코드별로 반환된 데이터를 필터링할 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 사용은 시간, 일, 주 및 월별로 그룹이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-p107">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Top Failures Report enables you to filter the returned data based on such things as the activity type (peer-to-peer session or conferencing session) or by the SIP response code that accompanied the failed session. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="ef3b8-133">다음 표에서는 상위 실패 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-133">The following table lists the filters that you can use with the Top Failures Report.</span></span>

### <a name="top-failures-report-filters"></a><span data-ttu-id="ef3b8-134">상위 실패 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="ef3b8-134">Top Failures Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef3b8-135">이름</span><span class="sxs-lookup"><span data-stu-id="ef3b8-135">Name</span></span></th>
<th><span data-ttu-id="ef3b8-136">설명</span><span class="sxs-lookup"><span data-stu-id="ef3b8-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef3b8-137"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="ef3b8-137"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="ef3b8-p108">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-p108">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="ef3b8-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ef3b8-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ef3b8-p109">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-p109">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ef3b8-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ef3b8-143">7/7/2012</span></span></p>
<p><span data-ttu-id="ef3b8-144">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ef3b8-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ef3b8-145">7/3/2012</span></span></p>
<p><span data-ttu-id="ef3b8-146">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef3b8-147"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="ef3b8-147"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="ef3b8-p110">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-p110">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="ef3b8-150">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ef3b8-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ef3b8-p111">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-p111">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ef3b8-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ef3b8-153">7/7/2012</span></span></p>
<p><span data-ttu-id="ef3b8-154">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ef3b8-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ef3b8-155">7/3/2012</span></span></p>
<p><span data-ttu-id="ef3b8-156">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef3b8-157"><strong>활동 유형</strong></span><span class="sxs-lookup"><span data-stu-id="ef3b8-157"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="ef3b8-p112">활동 유형입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-p112">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ef3b8-160">모든</span><span class="sxs-lookup"><span data-stu-id="ef3b8-160">[All]</span></span></p></li>
<li><p><span data-ttu-id="ef3b8-161">피어-투-피어</span><span class="sxs-lookup"><span data-stu-id="ef3b8-161">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="ef3b8-162">회의</span><span class="sxs-lookup"><span data-stu-id="ef3b8-162">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef3b8-163"><strong>형식</strong></span><span class="sxs-lookup"><span data-stu-id="ef3b8-163"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="ef3b8-164">현재까지 사용 가능한 유일한 옵션은 <strong>[모두]</strong>입니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-164">At this time the only option available is <strong>[All]</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef3b8-165"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="ef3b8-165"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ef3b8-p113">등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-p113">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef3b8-169"><strong>범주</strong></span><span class="sxs-lookup"><span data-stu-id="ef3b8-169"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="ef3b8-p114">발생한 오류 유형입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-p114">Type of failure experienced. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ef3b8-172">예상 오류 및 예기치 않은 오류 모두</span><span class="sxs-lookup"><span data-stu-id="ef3b8-172">Both expected and unexpected failure</span></span></p></li>
<li><p><span data-ttu-id="ef3b8-173">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="ef3b8-173">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="ef3b8-174">예상 되는 실패는 발생할 것으로 예상 되는 &quot; &quot; 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-174">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="ef3b8-175">예를 들어 사용자가 자신의 상태를 방해 금지로 설정한 경우 해당 사용자에 대한 통화가 실패할 것으로 예상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-175">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="ef3b8-176">예기치 않은 오류가 발생 하는 것 &quot; &quot; 은 정상적인 시스템이 아닌 것 처럼 보이는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-176">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="ef3b8-177">예를 들어 발신자가 보류 상태일 때는 통화가 종료되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-177">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="ef3b8-178">하지만 통화가 종료되면 바로 예기치 않은 오류로 플래그 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-178">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef3b8-179"><strong>응답 코드</strong></span><span class="sxs-lookup"><span data-stu-id="ef3b8-179"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="ef3b8-p116">회의가 실패했을 때 전송된 SIP 응답 코드입니다. 전체 응답 코드를 입력합니다. 예:</span><span class="sxs-lookup"><span data-stu-id="ef3b8-p116">SIP response code sent when the conference failed. Enter the entire response code For example:</span></span></p>
<p><span data-ttu-id="ef3b8-182">400</span><span class="sxs-lookup"><span data-stu-id="ef3b8-182">400</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef3b8-183"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="ef3b8-183"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="ef3b8-p117">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다. 진단 헤더는 선택 사항이며(이러한 헤더를 포함하지 않는 SIP 세션도 가능함) 진단 ID는 일부 유형의 문제가 발생한 세션에 대해서만 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-p117">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="ef3b8-186">메트릭</span><span class="sxs-lookup"><span data-stu-id="ef3b8-186">Metrics</span></span>

<span data-ttu-id="ef3b8-187">다음 표에서는 상위 실패 보고서에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-187">The following table lists the information provided in the Top Failures Report.</span></span>

### <a name="top-failures-report-metrics"></a><span data-ttu-id="ef3b8-188">상위 실패 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="ef3b8-188">Top Failures Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef3b8-189">이름</span><span class="sxs-lookup"><span data-stu-id="ef3b8-189">Name</span></span></th>
<th><span data-ttu-id="ef3b8-190">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="ef3b8-190">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ef3b8-191">설명</span><span class="sxs-lookup"><span data-stu-id="ef3b8-191">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef3b8-192"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="ef3b8-192"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="ef3b8-193">예</span><span class="sxs-lookup"><span data-stu-id="ef3b8-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="ef3b8-194">보고된 세션 수에 따른 상대적 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-194">Relative rank based on the number of reported sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef3b8-195"><strong>보고된 세션</strong></span><span class="sxs-lookup"><span data-stu-id="ef3b8-195"><strong>Reported sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ef3b8-196">예</span><span class="sxs-lookup"><span data-stu-id="ef3b8-196">Yes</span></span></p></td>
<td><p><span data-ttu-id="ef3b8-197">진단 ID 및 SIP 응답 코드에 따른 실패한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-197">Total number of failed sessions based on diagnostic ID and SIP response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef3b8-198"><strong>영향 받은 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="ef3b8-198"><strong>Users impacted</strong></span></span></p></td>
<td><p><span data-ttu-id="ef3b8-199">예</span><span class="sxs-lookup"><span data-stu-id="ef3b8-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="ef3b8-200">실패한 세션의 영향을 받은 총 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-200">Total number of users affected by the failed session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef3b8-201"><strong>실패 정보</strong></span><span class="sxs-lookup"><span data-stu-id="ef3b8-201"><strong>Failure information</strong></span></span></p></td>
<td><p><span data-ttu-id="ef3b8-202">아니요</span><span class="sxs-lookup"><span data-stu-id="ef3b8-202">No</span></span></p></td>
<td><p><span data-ttu-id="ef3b8-203">진단 ID, SIP 응답 코드, 세션이 실패한 이유에 대한 설명을 비롯한 실패에 대한 자세한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-203">Detailed information about the failure, including diagnostic ID, SIP response code, and description of why the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef3b8-204"><strong>지난 추세</strong></span><span class="sxs-lookup"><span data-stu-id="ef3b8-204"><strong>Trend in the past</strong></span></span></p></td>
<td><p><span data-ttu-id="ef3b8-205">아니요</span><span class="sxs-lookup"><span data-stu-id="ef3b8-205">No</span></span></p></td>
<td><p><span data-ttu-id="ef3b8-206">시간별로 실패한 세션의 그래프입니다.</span><span class="sxs-lookup"><span data-stu-id="ef3b8-206">Graphs failed sessions over time.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

