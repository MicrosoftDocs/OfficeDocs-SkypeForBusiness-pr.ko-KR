---
title: 'Lync Server 2013: 실패 분포 보고서'
description: 'Lync Server 2013: 실패 분포 보고서입니다.'
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
ms.openlocfilehash: f5a87f779f87d6b7002fa108f1969c33739eed9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564734"
---
# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="b2037-103">Lync Server 2013의 실패 분포 보고서</span><span class="sxs-lookup"><span data-stu-id="b2037-103">Failure Distribution Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2037-104">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="b2037-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="b2037-105">실패 분포 보고서에서는 다음 범주의 실패한 세션 순위가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-105">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="b2037-106">상위 진단 이유</span><span class="sxs-lookup"><span data-stu-id="b2037-106">Top diagnostic reasons</span></span>

  - <span data-ttu-id="b2037-107">상위 형식</span><span class="sxs-lookup"><span data-stu-id="b2037-107">Top modalities</span></span>

  - <span data-ttu-id="b2037-108">상위 풀</span><span class="sxs-lookup"><span data-stu-id="b2037-108">Top pools</span></span>

  - <span data-ttu-id="b2037-109">상위 원본</span><span class="sxs-lookup"><span data-stu-id="b2037-109">Top sources</span></span>

  - <span data-ttu-id="b2037-110">상위 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b2037-110">Top components</span></span>

  - <span data-ttu-id="b2037-111">상위 출처 사용자</span><span class="sxs-lookup"><span data-stu-id="b2037-111">Top from users</span></span>

  - <span data-ttu-id="b2037-112">상위 대상 사용자</span><span class="sxs-lookup"><span data-stu-id="b2037-112">Top to users</span></span>

  - <span data-ttu-id="b2037-113">상위 출처 사용자 에이전트</span><span class="sxs-lookup"><span data-stu-id="b2037-113">Top from user agents</span></span>

<span data-ttu-id="b2037-p101">이러한 범주를 사용하여 문제가 발생하는 정확한 위치를 확인할 수 있으며 경우에 따라서는 문제 발생 이유도 파악할 수 있습니다. 예를 들어 지정된 날에 실패한 오디오/비디오 세션 242개가 기록되었다고 가정하겠습니다. 실패 분포 보고서에는 이와 같은 실패한 세션 중 237개가 Dublin 풀에서 진행되었다고 표시될 수 있습니다. 이 경우 실패의 원인을 어디서부터 추적 및 진단할지를 쉽게 파악할 수 있습니다. **상위 풀** 범주에서 Dublin 풀을 클릭하면 해당 풀과 관련된 정보만 표시되는 실패 분포 보고서를 볼 수 있습니다. 그러면 Dublin 풀에서 오류가 많이 발생하는 이유 분석을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="b2037-120">실패 분포 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="b2037-120">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="b2037-121">**예상 오류량** 또는 **예기치 않은 오류량** 메트릭을 클릭하여 다음 보고서 중 하나에서 실패 분포 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-121">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="b2037-122">Lync Server 2013의 상위 실패 보고서</span><span class="sxs-lookup"><span data-stu-id="b2037-122">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="b2037-123">Lync Server 2013의 전화 회의 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="b2037-123">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="b2037-124">Lync Server 2013의 피어 투 피어 활동 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="b2037-124">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="b2037-125">실패 분포 보고서에서 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013에서 실패 목록 보고서](lync-server-2013-failure-list-report.md)를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-125">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="b2037-126">상위 진단 이유(세션)</span><span class="sxs-lookup"><span data-stu-id="b2037-126">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="b2037-127">상위 형식(세션)</span><span class="sxs-lookup"><span data-stu-id="b2037-127">Top modalities (sessions)</span></span>

  - <span data-ttu-id="b2037-128">상위 풀(세션)</span><span class="sxs-lookup"><span data-stu-id="b2037-128">Top pools (sessions)</span></span>

  - <span data-ttu-id="b2037-129">상위 원본(세션)</span><span class="sxs-lookup"><span data-stu-id="b2037-129">Top sources (sessions)</span></span>

  - <span data-ttu-id="b2037-130">상위 구성 요소(세션)</span><span class="sxs-lookup"><span data-stu-id="b2037-130">Top components (sessions)</span></span>

  - <span data-ttu-id="b2037-131">상위 출처 사용자(세션)</span><span class="sxs-lookup"><span data-stu-id="b2037-131">Top from users (sessions)</span></span>

  - <span data-ttu-id="b2037-132">상위 대상 사용자(세션)</span><span class="sxs-lookup"><span data-stu-id="b2037-132">Top to users (sessions)</span></span>

  - <span data-ttu-id="b2037-133">상위 출처 사용자 에이전트(세션)</span><span class="sxs-lookup"><span data-stu-id="b2037-133">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="b2037-134">실패 분포 보고서 사용</span><span class="sxs-lookup"><span data-stu-id="b2037-134">Using the Failure Distribution Report</span></span>

<span data-ttu-id="b2037-p102">모니터 크기 및 화면 해상도에 따라 실패 분포 보고서를 화면에서 볼 때 보고서에 표시되는 일부 데이터가 잘릴 수 있습니다. 사용자 에이전트 등 레이블이 매우 긴 메트릭의 경우는 특히 데이터가 잘릴 가능성이 높습니다. 예를 들어 이름이 "UCCAPI/4.0.7400.0 OC/4.0.7400.0(Microsoft Lync 2013)"인 사용자 에이전트의 경우 화면에 다음과 같이 일부분만 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="b2037-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0(Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="b2037-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="b2037-139">이 경우 잘린 값 위에 마우스를 놓기만 하면 전체 레이블을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-139">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="b2037-p103">실패 분포 보고서를 사용하여 필터링할 수 있는 메트릭 중 주목할 만한 항목은 진단 ID입니다. 같은 진단 ID가 다른 보고서에도 나타나는 경우 실패 분포 보고서에서 해당 ID를 필터링하면 실패한 세션 중에 해당 ID가 보고된 정확한 위치 및 빈도를 매우 상세하게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b2037-142">필터</span><span class="sxs-lookup"><span data-stu-id="b2037-142">Filters</span></span>

<span data-ttu-id="b2037-p104">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 오류 분포 보고서를 사용하면 활동 유형(피어 투 피어 세션 또는 회의 세션)과 같은 항목 또는 각 실패한 세션에 수반되는 진단 ID에 따라 필터링을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="b2037-145">다음 표에서는 오류 분포 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-145">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="b2037-146">오류 분포 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="b2037-146">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2037-147">이름</span><span class="sxs-lookup"><span data-stu-id="b2037-147">Name</span></span></th>
<th><span data-ttu-id="b2037-148">설명</span><span class="sxs-lookup"><span data-stu-id="b2037-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2037-149"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-p105">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b2037-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b2037-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b2037-p106">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b2037-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b2037-155">7/7/2012</span></span></p>
<p><span data-ttu-id="b2037-156">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b2037-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b2037-157">7/3/2012</span></span></p>
<p><span data-ttu-id="b2037-158">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2037-159"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-p107">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b2037-162">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b2037-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b2037-p108">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b2037-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b2037-165">7/7/2012</span></span></p>
<p><span data-ttu-id="b2037-166">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b2037-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b2037-167">7/3/2012</span></span></p>
<p><span data-ttu-id="b2037-168">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2037-169"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-169"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-p109">등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2037-173"><strong>활동 유형</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-173"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-p110">필터링할 활동 유형입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b2037-176">모든</span><span class="sxs-lookup"><span data-stu-id="b2037-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="b2037-177">피어-투-피어</span><span class="sxs-lookup"><span data-stu-id="b2037-177">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="b2037-178">회의</span><span class="sxs-lookup"><span data-stu-id="b2037-178">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2037-179"><strong>세션 범주</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-179"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-p111">문제가 있는 활동이 성공 또는 실패했는지를 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b2037-182">모든</span><span class="sxs-lookup"><span data-stu-id="b2037-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="b2037-183">Success</span><span class="sxs-lookup"><span data-stu-id="b2037-183">Success</span></span></p></li>
<li><p><span data-ttu-id="b2037-184">예상 오류</span><span class="sxs-lookup"><span data-stu-id="b2037-184">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="b2037-185">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="b2037-185">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="b2037-186">예상 되는 실패는 발생할 것으로 예상 되는 &quot; &quot; 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-186">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="b2037-187">예를 들어 사용자가 자신의 상태를 방해 금지로 설정한 경우 해당 사용자에 대한 통화가 실패할 것으로 예상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-187">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="b2037-188">예기치 않은 오류가 발생 하는 것 &quot; &quot; 은 정상적인 시스템이 아닌 것 처럼 보이는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-188">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="b2037-189">예를 들어 발신자가 보류 상태일 때는 통화가 종료되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-189">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="b2037-190">하지만 통화가 종료되면 바로 예기치 않은 오류로 플래그 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-190">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2037-191"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-p113">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다. 진단 헤더는 선택 사항이며(이러한 헤더를 포함하지 않는 SIP 세션도 가능함) 진단 ID는 일부 유형의 문제가 발생한 세션에 대해서만 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="b2037-194">상위 진단 이유에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="b2037-194">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="b2037-195">다음 표에서는 가장 자주 보고되는 진단 ID에 따라 오류 분포 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-195">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="b2037-196">상위 진단 이유에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="b2037-196">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2037-197">이름</span><span class="sxs-lookup"><span data-stu-id="b2037-197">Name</span></span></th>
<th><span data-ttu-id="b2037-198">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="b2037-198">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b2037-199">설명</span><span class="sxs-lookup"><span data-stu-id="b2037-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2037-200"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-200"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-201">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-201">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-p114">진단 ID에 따른 실패한 세션의 상대적 순위입니다. 진단 ID는 오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2037-204"><strong>상위 진단 이유</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-204"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-205">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-205">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-206">세션에서 생성된 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-206">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2037-207"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-207"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-208">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-208">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-209">지정된 진단 ID가 생성된 실패한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-209">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="b2037-210">상위 형식에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="b2037-210">Metrics for Top Modalities</span></span>

<span data-ttu-id="b2037-211">다음 표에서는 대부분의 오류가 발생한 세션 형식에 따라 오류 분포 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-211">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="b2037-212">상위 형식에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="b2037-212">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2037-213">이름</span><span class="sxs-lookup"><span data-stu-id="b2037-213">Name</span></span></th>
<th><span data-ttu-id="b2037-214">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="b2037-214">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b2037-215">설명</span><span class="sxs-lookup"><span data-stu-id="b2037-215">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2037-216"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-216"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-217">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-217">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-218">세션 유형을 기반으로 하는 실패한 세션의 상대적 순위입니다(예: 오디오/비디오 회의 또는 피어 투 피어 파일 전송 세션).</span><span class="sxs-lookup"><span data-stu-id="b2037-218">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2037-219"><strong>상위 형식</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-219"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-220">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-220">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-221">세션 유형</span><span class="sxs-lookup"><span data-stu-id="b2037-221">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2037-222"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-222"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-223">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-223">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-224">지정된 형식을 포함하는 실패한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-224">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="b2037-225">상위 풀에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="b2037-225">Metrics for Top Pools</span></span>

<span data-ttu-id="b2037-226">다음 표에서는 대부분의 오류가 발생한 풀에 따라 오류 분포 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-226">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="b2037-227">상위 풀에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="b2037-227">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2037-228">이름</span><span class="sxs-lookup"><span data-stu-id="b2037-228">Name</span></span></th>
<th><span data-ttu-id="b2037-229">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="b2037-229">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b2037-230">설명</span><span class="sxs-lookup"><span data-stu-id="b2037-230">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2037-231"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-231"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-232">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-232">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-233">세션이 수행 된 등록자 풀 또는에 지 서버를 기반으로 하는 실패 한 세션의 상대적 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-233">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2037-234"><strong>상위 풀</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-234"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-235">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-235">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-236">등록자 풀 또는에 지 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-236">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2037-237"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-237"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-238">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-238">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-239">등록자 풀 또는에 지 서버 당 실패 한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-239">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="b2037-240">상위 원본에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="b2037-240">Metrics for Top Sources</span></span>

<span data-ttu-id="b2037-241">다음 표에서는 대부분의 오류가 발생한 컴퓨터에 따라 오류 분포 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-241">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="b2037-242">상위 원본에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="b2037-242">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2037-243">이름</span><span class="sxs-lookup"><span data-stu-id="b2037-243">Name</span></span></th>
<th><span data-ttu-id="b2037-244">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="b2037-244">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b2037-245">설명</span><span class="sxs-lookup"><span data-stu-id="b2037-245">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2037-246"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-246"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-247">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-247">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-248">컴퓨터당 실패한 세션의 상대적 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-248">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2037-249"><strong>상위 원본</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-249"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-250">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-250">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-251">실패한 세션에 관련된 컴퓨터 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-251">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2037-252"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-252"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-253">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-253">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-254">컴퓨터당 실패한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-254">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="b2037-255">상위 구성 요소에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="b2037-255">Metrics for Top Components</span></span>

<span data-ttu-id="b2037-256">다음 표에서는 대부분의 오류가 발생 한 Microsoft Lync Server 2010 구성 요소를 기반으로 오류 분포 보고서에 제공 된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-256">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="b2037-257">상위 구성 요소에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="b2037-257">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2037-258">이름</span><span class="sxs-lookup"><span data-stu-id="b2037-258">Name</span></span></th>
<th><span data-ttu-id="b2037-259">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="b2037-259">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b2037-260">설명</span><span class="sxs-lookup"><span data-stu-id="b2037-260">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2037-261"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-261"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-262">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-262">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-263">Lync Server 2010 구성 요소를 기반으로 하는 실패 한 세션의 상대적 순위입니다 (예: ExumRouting, GroupChat 또는 MediationServer).</span><span class="sxs-lookup"><span data-stu-id="b2037-263">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2037-264"><strong>상위 구성 요소</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-264"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-265">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-265">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-266">실패한 세션에 관련된 구성 요소 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-266">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2037-267"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-267"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-268">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-268">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-269">구성 요소당 실패한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-269">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="b2037-270">상위 출처 사용자에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="b2037-270">Metrics for Top From Users</span></span>

<span data-ttu-id="b2037-271">다음 표에서는 다른 사용자에 대한 통화를 시도할 때 대부분의 오류가 발생한 사용자("시작" 사용자)를 기반으로 오류 분포 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-271">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="b2037-272">상위 출처 사용자에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="b2037-272">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2037-273">이름</span><span class="sxs-lookup"><span data-stu-id="b2037-273">Name</span></span></th>
<th><span data-ttu-id="b2037-274">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="b2037-274">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b2037-275">설명</span><span class="sxs-lookup"><span data-stu-id="b2037-275">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2037-276"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-276"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-277">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-277">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-278">세션에 참가하도록 초대된 사용자를 기반으로 하는 실패한 세션의 상대적 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-278">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2037-279"><strong>상위 출처 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-279"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-280">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-280">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-281">세션에 참가하도록 초대된 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-281">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2037-282"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-282"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-283">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-283">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-284">사용자당 실패한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-284">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="b2037-285">상위 대상 사용자에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="b2037-285">Metrics for Top To Users</span></span>

<span data-ttu-id="b2037-286">다음 표에서는 다른 사용자의 통화 시도 시에 대부분의 오류가 발생한 사용자("대상" 사용자)를 기반으로 오류 분포 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-286">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2037-287">이름</span><span class="sxs-lookup"><span data-stu-id="b2037-287">Name</span></span></th>
<th><span data-ttu-id="b2037-288">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="b2037-288">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b2037-289">설명</span><span class="sxs-lookup"><span data-stu-id="b2037-289">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2037-290"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-290"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-291">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-291">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-292">세션을 시작한 사용자를 기반으로 하는 실패한 세션의 상대적 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-292">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2037-293"><strong>상위 대상 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-293"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-294">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-294">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-295">세션을 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-295">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2037-296"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-296"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-297">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-297">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-298">사용자당 실패한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-298">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="b2037-299">최상위 사용자 에이전트에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="b2037-299">Metrics for Top User Agents</span></span>

<span data-ttu-id="b2037-300">다음 표에서는 대부분의 오류가 발생한 끝점 소프트웨어에 따라 오류 분포 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-300">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="b2037-301">최상위 사용자 에이전트에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="b2037-301">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2037-302">이름</span><span class="sxs-lookup"><span data-stu-id="b2037-302">Name</span></span></th>
<th><span data-ttu-id="b2037-303">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="b2037-303">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b2037-304">설명</span><span class="sxs-lookup"><span data-stu-id="b2037-304">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2037-305"><strong>오름차순</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-305"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-306">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-306">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-p115">세션에 관련된 사용자 에이전트(소프트웨어)를 기반으로 하는 실패한 세션의 상대적 순위입니다. 예: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="b2037-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2037-309"><strong>최상위 사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-309"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-310">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-310">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-311">실패한 세션에 관련된 사용자 에이전트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-311">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2037-312"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="b2037-312"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="b2037-313">아니요</span><span class="sxs-lookup"><span data-stu-id="b2037-313">No</span></span></p></td>
<td><p><span data-ttu-id="b2037-314">사용자 에이전트당 실패한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b2037-314">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

