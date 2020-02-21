---
title: 'Lync Server 2013: 실패 분포 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1531b7b103e3df6f2d165a4fd6fcd3abf100132
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="d7a38-102">Lync Server 2013의 실패 분포 보고서</span><span class="sxs-lookup"><span data-stu-id="d7a38-102">Failure Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7a38-103">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="d7a38-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="d7a38-104">실패 분포 보고서에서는 다음 범주의 실패한 세션 순위가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-104">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="d7a38-105">상위 진단 이유</span><span class="sxs-lookup"><span data-stu-id="d7a38-105">Top diagnostic reasons</span></span>

  - <span data-ttu-id="d7a38-106">상위 형식</span><span class="sxs-lookup"><span data-stu-id="d7a38-106">Top modalities</span></span>

  - <span data-ttu-id="d7a38-107">상위 풀</span><span class="sxs-lookup"><span data-stu-id="d7a38-107">Top pools</span></span>

  - <span data-ttu-id="d7a38-108">상위 원본</span><span class="sxs-lookup"><span data-stu-id="d7a38-108">Top sources</span></span>

  - <span data-ttu-id="d7a38-109">상위 구성 요소</span><span class="sxs-lookup"><span data-stu-id="d7a38-109">Top components</span></span>

  - <span data-ttu-id="d7a38-110">상위 출처 사용자</span><span class="sxs-lookup"><span data-stu-id="d7a38-110">Top from users</span></span>

  - <span data-ttu-id="d7a38-111">상위 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="d7a38-111">Top to users</span></span>

  - <span data-ttu-id="d7a38-112">상위 출처 사용자 에이전트</span><span class="sxs-lookup"><span data-stu-id="d7a38-112">Top from user agents</span></span>

<span data-ttu-id="d7a38-p101">이러한 범주를 사용하여 문제가 발생하는 정확한 위치를 확인할 수 있으며 경우에 따라서는 문제 발생 이유도 파악할 수 있습니다. 예를 들어 지정된 날에 실패한 오디오/비디오 세션 242개가 기록되었다고 가정하겠습니다. 실패 분포 보고서에는 이와 같은 실패한 세션 중 237개가 Dublin 풀에서 진행되었다고 표시될 수 있습니다. 이 경우 실패의 원인을 어디서부터 추적 및 진단할지를 쉽게 파악할 수 있습니다. **상위 풀** 범주에서 Dublin 풀을 클릭하면 해당 풀과 관련된 정보만 표시되는 실패 분포 보고서를 볼 수 있습니다. 그러면 Dublin 풀에서 오류가 많이 발생하는 이유 분석을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="d7a38-119">실패 분포 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="d7a38-119">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="d7a38-120">**예상 오류량** 또는 **예기치 않은 오류량** 메트릭을 클릭하여 다음 보고서 중 하나에서 실패 분포 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-120">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="d7a38-121">Lync Server 2013의 상위 실패 보고서</span><span class="sxs-lookup"><span data-stu-id="d7a38-121">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="d7a38-122">Lync Server 2013의 전화 회의 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="d7a38-122">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="d7a38-123">Lync Server 2013의 피어 투 피어 활동 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="d7a38-123">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="d7a38-124">실패 분포 보고서에서 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013에서 실패 목록 보고서](lync-server-2013-failure-list-report.md)를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-124">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="d7a38-125">상위 진단 이유(세션)</span><span class="sxs-lookup"><span data-stu-id="d7a38-125">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="d7a38-126">상위 형식(세션)</span><span class="sxs-lookup"><span data-stu-id="d7a38-126">Top modalities (sessions)</span></span>

  - <span data-ttu-id="d7a38-127">상위 풀(세션)</span><span class="sxs-lookup"><span data-stu-id="d7a38-127">Top pools (sessions)</span></span>

  - <span data-ttu-id="d7a38-128">상위 원본(세션)</span><span class="sxs-lookup"><span data-stu-id="d7a38-128">Top sources (sessions)</span></span>

  - <span data-ttu-id="d7a38-129">상위 구성 요소(세션)</span><span class="sxs-lookup"><span data-stu-id="d7a38-129">Top components (sessions)</span></span>

  - <span data-ttu-id="d7a38-130">상위 출처 사용자(세션)</span><span class="sxs-lookup"><span data-stu-id="d7a38-130">Top from users (sessions)</span></span>

  - <span data-ttu-id="d7a38-131">상위 대상 사용자(세션)</span><span class="sxs-lookup"><span data-stu-id="d7a38-131">Top to users (sessions)</span></span>

  - <span data-ttu-id="d7a38-132">상위 출처 사용자 에이전트(세션)</span><span class="sxs-lookup"><span data-stu-id="d7a38-132">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="d7a38-133">실패 분포 보고서 사용</span><span class="sxs-lookup"><span data-stu-id="d7a38-133">Using the Failure Distribution Report</span></span>

<span data-ttu-id="d7a38-p102">모니터 크기 및 화면 해상도에 따라 실패 분포 보고서를 화면에서 볼 때 보고서에 표시되는 일부 데이터가 잘릴 수 있습니다. 사용자 에이전트 등 레이블이 매우 긴 메트릭의 경우는 특히 데이터가 잘릴 가능성이 높습니다. 예를 들어 이름이 "UCCAPI/4.0.7400.0 OC/4.0.7400.0(Microsoft Lync 2013)"인 사용자 에이전트의 경우 화면에 다음과 같이 일부분만 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="d7a38-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0(Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="d7a38-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="d7a38-138">이 경우 잘린 값 위에 마우스를 놓기만 하면 전체 레이블을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-138">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="d7a38-p103">실패 분포 보고서를 사용하여 필터링할 수 있는 메트릭 중 주목할 만한 항목은 진단 ID입니다. 같은 진단 ID가 다른 보고서에도 나타나는 경우 실패 분포 보고서에서 해당 ID를 필터링하면 실패한 세션 중에 해당 ID가 보고된 정확한 위치 및 빈도를 매우 상세하게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d7a38-141">필터</span><span class="sxs-lookup"><span data-stu-id="d7a38-141">Filters</span></span>

<span data-ttu-id="d7a38-p104">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 오류 분포 보고서를 사용하면 활동 유형(피어 투 피어 세션 또는 회의 세션)과 같은 항목 또는 각 실패한 세션에 수반되는 진단 ID에 따라 필터링을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="d7a38-144">다음 표에서는 오류 분포 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-144">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="d7a38-145">오류 분포 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="d7a38-145">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7a38-146">이름</span><span class="sxs-lookup"><span data-stu-id="d7a38-146">Name</span></span></th>
<th><span data-ttu-id="d7a38-147">설명</span><span class="sxs-lookup"><span data-stu-id="d7a38-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-148"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-p105">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="d7a38-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d7a38-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d7a38-p106">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d7a38-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d7a38-154">7/7/2012</span></span></p>
<p><span data-ttu-id="d7a38-155">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d7a38-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d7a38-156">7/3/2012</span></span></p>
<p><span data-ttu-id="d7a38-157">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a38-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-p107">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="d7a38-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d7a38-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d7a38-p108">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d7a38-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d7a38-164">7/7/2012</span></span></p>
<p><span data-ttu-id="d7a38-165">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d7a38-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d7a38-166">7/3/2012</span></span></p>
<p><span data-ttu-id="d7a38-167">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-168"><strong>그룹</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-p109">등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a38-172"><strong>활동 유형</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-172"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-p110">필터링할 활동 유형입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d7a38-175">모든</span><span class="sxs-lookup"><span data-stu-id="d7a38-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="d7a38-176">피어-투-피어</span><span class="sxs-lookup"><span data-stu-id="d7a38-176">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="d7a38-177">전화</span><span class="sxs-lookup"><span data-stu-id="d7a38-177">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-178"><strong>세션 범주</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-178"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-p111">문제가 있는 활동이 성공 또는 실패했는지를 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d7a38-181">모든</span><span class="sxs-lookup"><span data-stu-id="d7a38-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="d7a38-182">Success</span><span class="sxs-lookup"><span data-stu-id="d7a38-182">Success</span></span></p></li>
<li><p><span data-ttu-id="d7a38-183">예상 오류</span><span class="sxs-lookup"><span data-stu-id="d7a38-183">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="d7a38-184">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="d7a38-184">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="d7a38-185">&quot;예상 되는&quot; 실패는 발생할 것으로 예상 되는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-185">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="d7a38-186">예를 들어 사용자가 자신의 상태를 방해 금지로 설정한 경우 해당 사용자에 대한 통화가 실패할 것으로 예상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-186">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="d7a38-187">&quot;예기치 않은 오류가&quot; 발생 하는 것은 정상적인 시스템이 아닌 것 처럼 보이는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-187">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="d7a38-188">예를 들어 발신자가 보류 상태일 때는 통화가 종료되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-188">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="d7a38-189">하지만 통화가 종료되면 바로 예기치 않은 오류로 플래그 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-189">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a38-190"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-190"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-p113">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다. 진단 헤더는 선택 사항이며(이러한 헤더를 포함하지 않는 SIP 세션도 가능함) 진단 ID는 일부 유형의 문제가 발생한 세션에 대해서만 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="d7a38-193">상위 진단 이유에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d7a38-193">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="d7a38-194">다음 표에서는 가장 자주 보고되는 진단 ID에 따라 오류 분포 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-194">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="d7a38-195">상위 진단 이유에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d7a38-195">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7a38-196">이름</span><span class="sxs-lookup"><span data-stu-id="d7a38-196">Name</span></span></th>
<th><span data-ttu-id="d7a38-197">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="d7a38-197">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d7a38-198">설명</span><span class="sxs-lookup"><span data-stu-id="d7a38-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-199"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-199"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-200">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-200">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-p114">진단 ID에 따른 실패한 세션의 상대적 순위입니다. 진단 ID는 오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a38-203"><strong>상위 진단 이유</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-203"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-204">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-204">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-205">세션에서 생성된 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-205">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-206"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-206"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-207">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-207">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-208">지정된 진단 ID가 생성된 실패한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-208">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="d7a38-209">상위 형식에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d7a38-209">Metrics for Top Modalities</span></span>

<span data-ttu-id="d7a38-210">다음 표에서는 대부분의 오류가 발생한 세션 형식에 따라 오류 분포 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-210">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="d7a38-211">상위 형식에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d7a38-211">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7a38-212">이름</span><span class="sxs-lookup"><span data-stu-id="d7a38-212">Name</span></span></th>
<th><span data-ttu-id="d7a38-213">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="d7a38-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d7a38-214">설명</span><span class="sxs-lookup"><span data-stu-id="d7a38-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-215"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-215"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-216">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-216">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-217">세션 유형을 기반으로 하는 실패한 세션의 상대적 순위입니다(예: 오디오/비디오 회의 또는 피어 투 피어 파일 전송 세션).</span><span class="sxs-lookup"><span data-stu-id="d7a38-217">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a38-218"><strong>상위 형식</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-218"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-219">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-219">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-220">세션 유형</span><span class="sxs-lookup"><span data-stu-id="d7a38-220">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-221"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-221"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-222">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-222">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-223">지정된 형식을 포함하는 실패한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-223">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="d7a38-224">상위 풀에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d7a38-224">Metrics for Top Pools</span></span>

<span data-ttu-id="d7a38-225">다음 표에서는 대부분의 오류가 발생한 풀에 따라 오류 분포 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-225">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="d7a38-226">상위 풀에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d7a38-226">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7a38-227">이름</span><span class="sxs-lookup"><span data-stu-id="d7a38-227">Name</span></span></th>
<th><span data-ttu-id="d7a38-228">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="d7a38-228">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d7a38-229">설명</span><span class="sxs-lookup"><span data-stu-id="d7a38-229">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-230"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-230"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-231">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-231">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-232">세션이 수행 된 등록자 풀 또는에 지 서버를 기반으로 하는 실패 한 세션의 상대적 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-232">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a38-233"><strong>상위 풀</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-233"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-234">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-234">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-235">등록자 풀 또는에 지 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-235">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-236"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-236"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-237">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-237">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-238">등록자 풀 또는에 지 서버 당 실패 한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-238">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="d7a38-239">상위 원본에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d7a38-239">Metrics for Top Sources</span></span>

<span data-ttu-id="d7a38-240">다음 표에서는 대부분의 오류가 발생한 컴퓨터에 따라 오류 분포 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-240">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="d7a38-241">상위 원본에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d7a38-241">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7a38-242">이름</span><span class="sxs-lookup"><span data-stu-id="d7a38-242">Name</span></span></th>
<th><span data-ttu-id="d7a38-243">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="d7a38-243">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d7a38-244">설명</span><span class="sxs-lookup"><span data-stu-id="d7a38-244">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-245"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-245"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-246">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-246">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-247">컴퓨터당 실패한 세션의 상대적 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-247">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a38-248"><strong>상위 원본</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-248"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-249">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-249">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-250">실패한 세션에 관련된 컴퓨터 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-250">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-251"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-251"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-252">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-252">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-253">컴퓨터당 실패한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-253">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="d7a38-254">상위 구성 요소에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d7a38-254">Metrics for Top Components</span></span>

<span data-ttu-id="d7a38-255">다음 표에서는 대부분의 오류가 발생 한 Microsoft Lync Server 2010 구성 요소를 기반으로 오류 분포 보고서에 제공 된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-255">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="d7a38-256">상위 구성 요소에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d7a38-256">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7a38-257">이름</span><span class="sxs-lookup"><span data-stu-id="d7a38-257">Name</span></span></th>
<th><span data-ttu-id="d7a38-258">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="d7a38-258">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d7a38-259">설명</span><span class="sxs-lookup"><span data-stu-id="d7a38-259">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-260"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-260"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-261">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-261">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-262">Lync Server 2010 구성 요소를 기반으로 하는 실패 한 세션의 상대적 순위입니다 (예: ExumRouting, GroupChat 또는 MediationServer).</span><span class="sxs-lookup"><span data-stu-id="d7a38-262">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a38-263"><strong>상위 구성 요소</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-263"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-264">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-264">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-265">실패한 세션에 관련된 구성 요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-265">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-266"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-266"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-267">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-267">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-268">구성 요소당 실패한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-268">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="d7a38-269">상위 출처 사용자에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d7a38-269">Metrics for Top From Users</span></span>

<span data-ttu-id="d7a38-270">다음 표에서는 다른 사용자에 대한 통화를 시도할 때 대부분의 오류가 발생한 사용자("시작" 사용자)를 기반으로 오류 분포 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-270">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="d7a38-271">상위 출처 사용자에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d7a38-271">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7a38-272">이름</span><span class="sxs-lookup"><span data-stu-id="d7a38-272">Name</span></span></th>
<th><span data-ttu-id="d7a38-273">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="d7a38-273">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d7a38-274">설명</span><span class="sxs-lookup"><span data-stu-id="d7a38-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-275"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-275"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-276">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-276">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-277">세션에 참가하도록 초대된 사용자를 기반으로 하는 실패한 세션의 상대적 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-277">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a38-278"><strong>상위 출처 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-278"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-279">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-279">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-280">세션에 참가하도록 초대된 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-280">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-281"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-281"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-282">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-282">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-283">사용자당 실패한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-283">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="d7a38-284">상위 대상 사용자에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d7a38-284">Metrics for Top To Users</span></span>

<span data-ttu-id="d7a38-285">다음 표에서는 다른 사용자의 통화 시도 시에 대부분의 오류가 발생한 사용자("대상" 사용자)를 기반으로 오류 분포 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-285">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7a38-286">이름</span><span class="sxs-lookup"><span data-stu-id="d7a38-286">Name</span></span></th>
<th><span data-ttu-id="d7a38-287">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="d7a38-287">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d7a38-288">설명</span><span class="sxs-lookup"><span data-stu-id="d7a38-288">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-289"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-289"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-290">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-290">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-291">세션을 시작한 사용자를 기반으로 하는 실패한 세션의 상대적 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-291">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a38-292"><strong>상위 대상 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-292"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-293">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-293">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-294">세션을 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-294">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-295"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-295"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-296">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-296">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-297">사용자당 실패한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-297">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="d7a38-298">최상위 사용자 에이전트에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d7a38-298">Metrics for Top User Agents</span></span>

<span data-ttu-id="d7a38-299">다음 표에서는 대부분의 오류가 발생한 끝점 소프트웨어에 따라 오류 분포 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-299">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="d7a38-300">최상위 사용자 에이전트에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="d7a38-300">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7a38-301">이름</span><span class="sxs-lookup"><span data-stu-id="d7a38-301">Name</span></span></th>
<th><span data-ttu-id="d7a38-302">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="d7a38-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d7a38-303">설명</span><span class="sxs-lookup"><span data-stu-id="d7a38-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-304"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-304"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-305">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-305">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-p115">세션에 관련된 사용자 에이전트(소프트웨어)를 기반으로 하는 실패한 세션의 상대적 순위입니다. 예: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="d7a38-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7a38-308"><strong>최상위 사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-308"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-309">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-309">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-310">실패한 세션에 관련된 사용자 에이전트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-310">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7a38-311"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="d7a38-311"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d7a38-312">아니요</span><span class="sxs-lookup"><span data-stu-id="d7a38-312">No</span></span></p></td>
<td><p><span data-ttu-id="d7a38-313">사용자 에이전트당 실패한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7a38-313">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

