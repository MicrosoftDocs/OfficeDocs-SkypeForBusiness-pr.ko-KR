---
title: 'Lync Server 2013: 실패 한 배포 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06481be824f6c51975431aeea2efe27e41eadabc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="7f1c5-102">Lync Server 2013의 실패 한 배포 보고서</span><span class="sxs-lookup"><span data-stu-id="7f1c5-102">Failure Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f1c5-103">_**마지막으로 수정한 주제:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="7f1c5-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="7f1c5-104">실패 한 배포 보고서는 실패 한 세션의 순위를 다음 범주로 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-104">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="7f1c5-105">주요 진단 이유</span><span class="sxs-lookup"><span data-stu-id="7f1c5-105">Top diagnostic reasons</span></span>

  - <span data-ttu-id="7f1c5-106">Top 형식을</span><span class="sxs-lookup"><span data-stu-id="7f1c5-106">Top modalities</span></span>

  - <span data-ttu-id="7f1c5-107">상위 풀</span><span class="sxs-lookup"><span data-stu-id="7f1c5-107">Top pools</span></span>

  - <span data-ttu-id="7f1c5-108">상위 원본</span><span class="sxs-lookup"><span data-stu-id="7f1c5-108">Top sources</span></span>

  - <span data-ttu-id="7f1c5-109">상위 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7f1c5-109">Top components</span></span>

  - <span data-ttu-id="7f1c5-110">사용자의 상위</span><span class="sxs-lookup"><span data-stu-id="7f1c5-110">Top from users</span></span>

  - <span data-ttu-id="7f1c5-111">상위 사용자</span><span class="sxs-lookup"><span data-stu-id="7f1c5-111">Top to users</span></span>

  - <span data-ttu-id="7f1c5-112">사용자 에이전트의 상위</span><span class="sxs-lookup"><span data-stu-id="7f1c5-112">Top from user agents</span></span>

<span data-ttu-id="7f1c5-113">이러한 범주를 사용 하 여 문제가 발생 하는 위치와 문제가 발생 하는 경우를 정확 하 게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-113">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring.</span></span> <span data-ttu-id="7f1c5-114">예를 들어 지정 된 날짜 동안 242 실패 한 오디오/비디오 세션을 기록 했다고 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-114">For example, suppose you recorded 242 failed audio/video sessions during a given day.</span></span> <span data-ttu-id="7f1c5-115">실패 한 배포 보고서에 대 한 자세한 내용은 실패 한 세션의 237가 더블린 풀에 발생 한 것으로 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-115">If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool.</span></span> <span data-ttu-id="7f1c5-116">이를 통해 추적 하 고 해당 오류에 대 한 원인을 진단할 때 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-116">That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures.</span></span> <span data-ttu-id="7f1c5-117">**상위 풀** 범주 아래에 있는 더블린 풀을 클릭 하면 해당 풀에 대 한 실패 분포 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-117">If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool.</span></span> <span data-ttu-id="7f1c5-118">그런 다음 더블린 풀이 많은 어려움을 겪고 있는 이유를 분석을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-118">You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="7f1c5-119">실패 한 배포 보고서 보기</span><span class="sxs-lookup"><span data-stu-id="7f1c5-119">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="7f1c5-120">**예상 고장 볼륨** 또는 **예기치 않은 오류 볼륨** 메트릭 중 하나를 클릭 하 여 다음 보고서에서 실패 배포 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-120">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="7f1c5-121">Lync Server 2013의 상위 오류 보고서</span><span class="sxs-lookup"><span data-stu-id="7f1c5-121">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="7f1c5-122">Lync Server 2013의 컨퍼런스 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="7f1c5-122">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="7f1c5-123">Lync Server 2013의 피어 투 피어 작업 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="7f1c5-123">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="7f1c5-124">실패 한 배포 보고서에서 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013에서 실패 목록 보고서](lync-server-2013-failure-list-report.md)를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-124">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="7f1c5-125">주요 진단 이유 (세션)</span><span class="sxs-lookup"><span data-stu-id="7f1c5-125">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="7f1c5-126">최상위 형식을 (세션)</span><span class="sxs-lookup"><span data-stu-id="7f1c5-126">Top modalities (sessions)</span></span>

  - <span data-ttu-id="7f1c5-127">상위 풀 (세션)</span><span class="sxs-lookup"><span data-stu-id="7f1c5-127">Top pools (sessions)</span></span>

  - <span data-ttu-id="7f1c5-128">상위 원본 (세션)</span><span class="sxs-lookup"><span data-stu-id="7f1c5-128">Top sources (sessions)</span></span>

  - <span data-ttu-id="7f1c5-129">상위 구성 요소 (세션)</span><span class="sxs-lookup"><span data-stu-id="7f1c5-129">Top components (sessions)</span></span>

  - <span data-ttu-id="7f1c5-130">사용자 (세션)의 상위</span><span class="sxs-lookup"><span data-stu-id="7f1c5-130">Top from users (sessions)</span></span>

  - <span data-ttu-id="7f1c5-131">상위 사용자 (세션)</span><span class="sxs-lookup"><span data-stu-id="7f1c5-131">Top to users (sessions)</span></span>

  - <span data-ttu-id="7f1c5-132">사용자 에이전트 (세션)에서 맨 위로</span><span class="sxs-lookup"><span data-stu-id="7f1c5-132">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="7f1c5-133">실패 한 배포 보고서 사용</span><span class="sxs-lookup"><span data-stu-id="7f1c5-133">Using the Failure Distribution Report</span></span>

<span data-ttu-id="7f1c5-134">모니터 크기와 화면 해상도에 따라 실패 배포 보고서에 표시 되는 일부 데이터가 화면에 표시 될 때 잘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-134">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen.</span></span> <span data-ttu-id="7f1c5-135">이는 매우 긴 레이블을 포함할 수 있는 사용자 에이전트와 같은 메트릭의 경우 특히 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-135">This is especially true for metrics such as user agents, which can have very long labels.</span></span> <span data-ttu-id="7f1c5-136">예를 들어 "e: CAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)"와 같은 이름이 있는 사용자 에이전트는 화면에 부분적 으로만 나타날 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-136">For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="7f1c5-137">S e u i CAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft와 ...</span><span class="sxs-lookup"><span data-stu-id="7f1c5-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="7f1c5-138">다행히 잘린 값을 마우스로 눌러 전체 레이블을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-138">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="7f1c5-139">실패 분포 보고서를 사용 하 여 필터링 할 수 있는 한 가지 흥미로운 메트릭은 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-139">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID.</span></span> <span data-ttu-id="7f1c5-140">다른 보고서에 동일한 진단 ID가 표시 되는 경우 실패 한 배포 보고서에서 해당 ID에 대해 필터링 할 수 있으며, 오류가 발생 한 세션 중에 해당 ID가 보고 되는 빈도에 대 한 자세한 내용을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-140">If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7f1c5-141">필터가</span><span class="sxs-lookup"><span data-stu-id="7f1c5-141">Filters</span></span>

<span data-ttu-id="7f1c5-142">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-142">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="7f1c5-143">예를 들어 실패 한 배포 보고서를 사용 하 여 활동 유형 (피어 투 피어 세션 또는 회의 세션) 또는 실패 한 각 세션과 함께 제공 되는 진단 ID를 기준으로 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-143">For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="7f1c5-144">다음 표에는 실패 분포 보고서에 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-144">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="7f1c5-145">실패 한 배포 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="7f1c5-145">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f1c5-146">이름</span><span class="sxs-lookup"><span data-stu-id="7f1c5-146">Name</span></span></th>
<th><span data-ttu-id="7f1c5-147">설명</span><span class="sxs-lookup"><span data-stu-id="7f1c5-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-148"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-149">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-149">Start date/time for the time range.</span></span> <span data-ttu-id="7f1c5-150">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-150">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7f1c5-151">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="7f1c5-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7f1c5-152">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-152">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="7f1c5-153">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-153">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7f1c5-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7f1c5-154">7/7/2012</span></span></p>
<p><span data-ttu-id="7f1c5-155">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="7f1c5-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7f1c5-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7f1c5-156">7/3/2012</span></span></p>
<p><span data-ttu-id="7f1c5-157">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f1c5-158"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-159">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-159">End date/time for the time range.</span></span> <span data-ttu-id="7f1c5-160">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-160">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7f1c5-161">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="7f1c5-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7f1c5-162">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-162">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="7f1c5-163">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-163">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7f1c5-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7f1c5-164">7/7/2012</span></span></p>
<p><span data-ttu-id="7f1c5-165">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="7f1c5-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7f1c5-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7f1c5-166">7/3/2012</span></span></p>
<p><span data-ttu-id="7f1c5-167">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-168"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-169">등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-169">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="7f1c5-170">개별 풀을 선택 하거나 <strong>[모두]</strong> 를 클릭 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-170">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="7f1c5-171">이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-171">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f1c5-172"><strong>활동 유형</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-172"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-173">필터링 할 활동의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-173">Type of activity to filter on.</span></span> <span data-ttu-id="7f1c5-174">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-174">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7f1c5-175">모든</span><span class="sxs-lookup"><span data-stu-id="7f1c5-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="7f1c5-176">피어 투 피어</span><span class="sxs-lookup"><span data-stu-id="7f1c5-176">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="7f1c5-177">회의</span><span class="sxs-lookup"><span data-stu-id="7f1c5-177">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-178"><strong>세션 범주</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-178"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-179">활동의 성공 또는 실패 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-179">Indicates whether the activity in question succeeded or failed.</span></span> <span data-ttu-id="7f1c5-180">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-180">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7f1c5-181">모든</span><span class="sxs-lookup"><span data-stu-id="7f1c5-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="7f1c5-182">시간당</span><span class="sxs-lookup"><span data-stu-id="7f1c5-182">Success</span></span></p></li>
<li><p><span data-ttu-id="7f1c5-183">예상 실패</span><span class="sxs-lookup"><span data-stu-id="7f1c5-183">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="7f1c5-184">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="7f1c5-184">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="7f1c5-185">&quot;예상 되는&quot; 실패는 예상 되는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-185">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="7f1c5-186">예를 들어 사용자가 자신의 상태를 방해 금지로 설정 하면 해당 사용자에 게 전화를 거는 데 실패 하는 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-186">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="7f1c5-187">&quot;예기치 않은 오류가&quot; 발생 하는 것은 정상적인 시스템 때문 이라고 표시 되는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-187">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="7f1c5-188">예를 들어 호출자가 대기 상태로 설정 된 경우에는 통화가 종료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-188">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="7f1c5-189">이 문제가 발생 하면 예기치 않은 오류로 플래그가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-189">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f1c5-190"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-190"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-191">오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-191">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="7f1c5-192">진단 헤더는 선택 사항으로,이 헤더를 포함 하지 않는 SIP 세션이 있을 수 있으며, 진단 Id는 일부 종류의 문제가 발생 하는 세션에 대해서만 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-192">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="7f1c5-193">주요 진단 이유에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="7f1c5-193">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="7f1c5-194">다음 표에는 가장 자주 보고 되는 진단 ID를 기준으로 실패 배포 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-194">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="7f1c5-195">주요 진단 이유에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="7f1c5-195">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f1c5-196">이름</span><span class="sxs-lookup"><span data-stu-id="7f1c5-196">Name</span></span></th>
<th><span data-ttu-id="7f1c5-197">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7f1c5-197">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7f1c5-198">설명</span><span class="sxs-lookup"><span data-stu-id="7f1c5-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-199"><strong>순위</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-199"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-200">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-200">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-201">진단 Id를 기준으로 실패 한 세션의 상대 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-201">Relative ranking of failed sessions based on diagnostic IDs.</span></span> <span data-ttu-id="7f1c5-202">진단 ID는 오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 연결 된 고유 식별자 (ms-진단 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-202">The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f1c5-203"><strong>주요 진단 이유</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-203"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-204">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-204">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-205">세션에서 생성 된 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-205">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-206"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-206"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-207">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-207">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-208">지정 된 진단 ID가 생성 된 총 실패 한 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-208">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="7f1c5-209">Top 형식을에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="7f1c5-209">Metrics for Top Modalities</span></span>

<span data-ttu-id="7f1c5-210">다음 표에서는 실패 배포 보고서에 제공 되는 정보를 가장 많이 발생 하는 세션 형식을에 따라 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-210">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="7f1c5-211">Top 형식을에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="7f1c5-211">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f1c5-212">이름</span><span class="sxs-lookup"><span data-stu-id="7f1c5-212">Name</span></span></th>
<th><span data-ttu-id="7f1c5-213">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7f1c5-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7f1c5-214">설명</span><span class="sxs-lookup"><span data-stu-id="7f1c5-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-215"><strong>순위</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-215"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-216">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-216">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-217">세션 유형에 따라 실패 한 세션 (예: 오디오/비디오 컨퍼런스 또는 피어 투 피어 파일 전송 세션)을 기준으로 상대 순위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-217">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f1c5-218"><strong>Top 형식을</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-218"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-219">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-219">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-220">세션 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-220">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-221"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-221"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-222">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-222">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-223">지정 된 모달을 포함 하는 실패 한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-223">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="7f1c5-224">최상위 풀에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="7f1c5-224">Metrics for Top Pools</span></span>

<span data-ttu-id="7f1c5-225">다음 표에서는 오류가 발생 한 배포 보고서에 제공 되는 정보를 가장 많이 발생 한 풀에 기반 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-225">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="7f1c5-226">최상위 풀에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="7f1c5-226">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f1c5-227">이름</span><span class="sxs-lookup"><span data-stu-id="7f1c5-227">Name</span></span></th>
<th><span data-ttu-id="7f1c5-228">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7f1c5-228">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7f1c5-229">설명</span><span class="sxs-lookup"><span data-stu-id="7f1c5-229">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-230"><strong>순위</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-230"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-231">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-231">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-232">세션이 수행 된 등록자 풀이나 Edge 서버를 기반으로 하는 실패 한 세션의 상대 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-232">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f1c5-233"><strong>상위 풀</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-233"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-234">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-234">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-235">등록자 풀 또는 Edge 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-235">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-236"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-236"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-237">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-237">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-238">등록자 풀 또는 Edge 서버 당 실패 한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-238">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="7f1c5-239">상위 원본에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="7f1c5-239">Metrics for Top Sources</span></span>

<span data-ttu-id="7f1c5-240">다음 표에서는 실패 한 배포 보고서에서 발생 하는 대부분의 오류가 발생 한 컴퓨터를 기준으로 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-240">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="7f1c5-241">상위 원본에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="7f1c5-241">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f1c5-242">이름</span><span class="sxs-lookup"><span data-stu-id="7f1c5-242">Name</span></span></th>
<th><span data-ttu-id="7f1c5-243">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7f1c5-243">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7f1c5-244">설명</span><span class="sxs-lookup"><span data-stu-id="7f1c5-244">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-245"><strong>순위</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-245"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-246">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-246">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-247">컴퓨터당 상대적인 순위 지정 실패 한 세션</span><span class="sxs-lookup"><span data-stu-id="7f1c5-247">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f1c5-248"><strong>상위 원본</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-248"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-249">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-249">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-250">실패 한 세션과 관련 된 컴퓨터의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-250">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-251"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-251"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-252">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-252">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-253">컴퓨터당 총 failed sessions 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-253">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="7f1c5-254">최상위 구성 요소에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="7f1c5-254">Metrics for Top Components</span></span>

<span data-ttu-id="7f1c5-255">다음 표에는 대부분의 오류가 발생 한 Microsoft Lync Server 2010 구성 요소를 기반으로 실패 배포 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-255">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="7f1c5-256">최상위 구성 요소에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="7f1c5-256">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f1c5-257">이름</span><span class="sxs-lookup"><span data-stu-id="7f1c5-257">Name</span></span></th>
<th><span data-ttu-id="7f1c5-258">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7f1c5-258">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7f1c5-259">설명</span><span class="sxs-lookup"><span data-stu-id="7f1c5-259">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-260"><strong>순위</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-260"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-261">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-261">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-262">Lync Server 2010 구성 요소 (예: ExumRouting, GroupChat 또는 MediationServer)를 기반으로 하는 실패 한 세션의 상대 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-262">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f1c5-263"><strong>상위 구성 요소</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-263"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-264">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-264">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-265">실패 한 세션과 관련 된 구성 요소의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-265">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-266"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-266"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-267">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-267">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-268">구성 요소 당 실패 한 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-268">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="7f1c5-269">사용자의 상위에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="7f1c5-269">Metrics for Top From Users</span></span>

<span data-ttu-id="7f1c5-270">다음 표에는 다른 사용자에 게 전화를 거는 경우 ("보낸 사람" 사용자)를 사용 하 여 발생 하는 대부분의 경우 오류 배포 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-270">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="7f1c5-271">사용자의 상위에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="7f1c5-271">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f1c5-272">이름</span><span class="sxs-lookup"><span data-stu-id="7f1c5-272">Name</span></span></th>
<th><span data-ttu-id="7f1c5-273">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7f1c5-273">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7f1c5-274">설명</span><span class="sxs-lookup"><span data-stu-id="7f1c5-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-275"><strong>순위</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-275"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-276">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-276">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-277">세션에 참가 하도록 초대 된 사용자에 따라 실패 한 세션의 상대 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-277">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f1c5-278"><strong>사용자의 상위</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-278"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-279">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-279">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-280">세션에 참가 하도록 초대 받은 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-280">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-281"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-281"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-282">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-282">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-283">사용자 당 실패 한 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-283">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="7f1c5-284">상위 사용자에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="7f1c5-284">Metrics for Top To Users</span></span>

<span data-ttu-id="7f1c5-285">다음 표에는 다른 사용자가 전화를 거는 경우 ("받는 사람" 사용자)를 사용 하 여 오류가 발생 한 사용자를 기준으로 실패 배포 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-285">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f1c5-286">이름</span><span class="sxs-lookup"><span data-stu-id="7f1c5-286">Name</span></span></th>
<th><span data-ttu-id="7f1c5-287">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7f1c5-287">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7f1c5-288">설명</span><span class="sxs-lookup"><span data-stu-id="7f1c5-288">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-289"><strong>순위</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-289"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-290">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-290">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-291">세션을 시작한 사용자에 따라 실패 한 세션의 상대 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-291">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f1c5-292"><strong>상위 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-292"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-293">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-293">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-294">세션을 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-294">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-295"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-295"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-296">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-296">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-297">사용자 당 실패 한 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-297">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="7f1c5-298">상위 사용자 에이전트에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="7f1c5-298">Metrics for Top User Agents</span></span>

<span data-ttu-id="7f1c5-299">다음 표에는 오류가 발생 한 끝점 소프트웨어에 따라 실패 배포 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-299">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="7f1c5-300">상위 사용자 에이전트에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="7f1c5-300">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7f1c5-301">이름</span><span class="sxs-lookup"><span data-stu-id="7f1c5-301">Name</span></span></th>
<th><span data-ttu-id="7f1c5-302">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7f1c5-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7f1c5-303">설명</span><span class="sxs-lookup"><span data-stu-id="7f1c5-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-304"><strong>순위</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-304"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-305">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-305">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-306">세션과 관련 된 사용자 에이전트 (소프트웨어)를 기반으로 하는 실패 한 세션의 상대 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-306">Relative ranking of failed sessions based on the user agent (software) involved in the session.</span></span> <span data-ttu-id="7f1c5-307">예: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-307">For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f1c5-308"><strong>상위 사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-308"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-309">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-309">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-310">실패 한 세션과 관련 된 사용자 에이전트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-310">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f1c5-311"><strong>세션</strong></span><span class="sxs-lookup"><span data-stu-id="7f1c5-311"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7f1c5-312">아니요</span><span class="sxs-lookup"><span data-stu-id="7f1c5-312">No</span></span></p></td>
<td><p><span data-ttu-id="7f1c5-313">사용자 에이전트 당 실패 한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7f1c5-313">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

