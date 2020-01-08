---
title: 'Lync Server 2013: 서버 성능 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5a08104f33fc07d6a0ec1c3241a7f14fa1227a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="8dec7-102">Lync Server 2013의 서버 성능 보고서</span><span class="sxs-lookup"><span data-stu-id="8dec7-102">Server Performance Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8dec7-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8dec7-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8dec7-104">서버 성능 보고서는 잘못 된 통화의 최고 비율을 경험 하는 Microsoft Lync Server 2013 서버 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="8dec7-105">다음 형식에 대 한 별도의 통계를 보고 하는 서버 유형별로 서버에서 하위 보고서를 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="8dec7-106">중재 서버</span><span class="sxs-lookup"><span data-stu-id="8dec7-106">Mediation Server</span></span>

  - <span data-ttu-id="8dec7-107">A/V 회의 서버</span><span class="sxs-lookup"><span data-stu-id="8dec7-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="8dec7-108">A/V에 지 서버</span><span class="sxs-lookup"><span data-stu-id="8dec7-108">A/V Edge Server</span></span>

  - <span data-ttu-id="8dec7-109">게이트웨이 (중재 서버)</span><span class="sxs-lookup"><span data-stu-id="8dec7-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="8dec7-110">게이트웨이 (중재 서버 무시)</span><span class="sxs-lookup"><span data-stu-id="8dec7-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="8dec7-111">비디오 (A/V 회의 서버용 비디오 메트릭과 A/V Edge 서버 포함)</span><span class="sxs-lookup"><span data-stu-id="8dec7-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="8dec7-112">응용 프로그램 공유 (A/V 회의 서버 및 A/V에 지 서버에 대 한 응용 프로그램 공유 메트릭 포함)</span><span class="sxs-lookup"><span data-stu-id="8dec7-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="8dec7-113">이 보고서에는 기준 순위 지정으로 표시 되는 등급이 있다는 점에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-113">It’s important to note that the ranking shown in this report as relative rankings.</span></span> <span data-ttu-id="8dec7-114">예를 들어, 최악의 서버의 1000 연결 된 통화에 대 한 한 가지 좋지 않은 호출이 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-114">For example, suppose your worst-performing server had one poor call among its 1,000 placed calls.</span></span> <span data-ttu-id="8dec7-115">이는 허용 되는 백분율이 며 1%입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-115">That's a more-than-acceptable percentage of .1%.</span></span> <span data-ttu-id="8dec7-116">그러나 사용 하는 최악의 서버 (즉, 다른 서버 모두의 통화 백분율이 0.1% 미만이 되 면 서버 성능 보고서에 계속 표시 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="8dec7-116">However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="8dec7-117">서버 성능 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="8dec7-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="8dec7-118">서버 성능 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="8dec7-119">다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 통화 목록 보고서](lync-server-2013-call-list-report.md) 로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="8dec7-120">통화 볼륨</span><span class="sxs-lookup"><span data-stu-id="8dec7-120">Call volume</span></span>

  - <span data-ttu-id="8dec7-121">통화 불량 백분율</span><span class="sxs-lookup"><span data-stu-id="8dec7-121">Poor call percentage</span></span>

<span data-ttu-id="8dec7-122">또한 다음 메트릭을 클릭 하 여 서버 미디어 품질 추세 보고서로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="8dec7-123">추세가</span><span class="sxs-lookup"><span data-stu-id="8dec7-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="8dec7-124">서버 성능 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="8dec7-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="8dec7-125">서버 성능 보고서는 데이터를 필터링 하는 여러 가지 방법을 제공 합니다. 예를 들어 네트워크 종류 (유선 연결에서 발생 하는 통화와 무선 연결에서 발생 하는 전화) 및 액세스 형식 (방화벽 외부에서 생성 된 호출 및 방화벽 내부에서 발생 한 호출)에 대해 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-125">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall).</span></span> <span data-ttu-id="8dec7-126">이러한 필터를 사용 하려면 서버 성능 보고서를 보는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-126">It's a good idea when viewing the server performance report to make use of these filters.</span></span> <span data-ttu-id="8dec7-127">예를 들어 잘못 된 통화 백분율이 3.24% 인 중재 서버가 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-127">For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%.</span></span> <span data-ttu-id="8dec7-128">무선 전화를 사용 하 고 있는 경우 같은 서버의 통화 백분율이 20%에 도달 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-128">If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%.</span></span> <span data-ttu-id="8dec7-129">즉, 서버에서 무선 통화에 문제가 발생 하 여 서버가 유선 호출에 문제가 있지 않기 때문에 부분적으로 가려진 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-129">That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8dec7-130">필터가</span><span class="sxs-lookup"><span data-stu-id="8dec7-130">Filters</span></span>

<span data-ttu-id="8dec7-131">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-131">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="8dec7-132">예를 들어 서버 성능 보고서를 사용 하면 반환 된 데이터를 서버 유형 또는 네트워크 형식 (유선 또는 무선)으로 필터링 하는 등의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-132">For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless).</span></span> <span data-ttu-id="8dec7-133">데이터 그룹화 방법을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-133">You can also choose how data should be grouped.</span></span> <span data-ttu-id="8dec7-134">이 경우 데이터는 시간, 일, 주 또는 월로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-134">In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="8dec7-135">다음 표에는 서버 성능 보고서에 사용할 수 있는 필터가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="8dec7-136">서버 성능 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="8dec7-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dec7-137">이름</span><span class="sxs-lookup"><span data-stu-id="8dec7-137">Name</span></span></th>
<th><span data-ttu-id="8dec7-138">설명</span><span class="sxs-lookup"><span data-stu-id="8dec7-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-139"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-140">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-140">Start date/time for the time range.</span></span> <span data-ttu-id="8dec7-141">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-141">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8dec7-142">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="8dec7-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8dec7-143">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-143">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="8dec7-144">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-144">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8dec7-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8dec7-145">7/7/2012</span></span></p>
<p><span data-ttu-id="8dec7-146">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="8dec7-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8dec7-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8dec7-147">7/3/2012</span></span></p>
<p><span data-ttu-id="8dec7-148">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-149"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-150">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-150">End date/time for the time range.</span></span> <span data-ttu-id="8dec7-151">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-151">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8dec7-152">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="8dec7-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8dec7-153">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-153">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="8dec7-154">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-154">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8dec7-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8dec7-155">7/7/2012</span></span></p>
<p><span data-ttu-id="8dec7-156">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="8dec7-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8dec7-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8dec7-157">7/3/2012</span></span></p>
<p><span data-ttu-id="8dec7-158">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-159"><strong>서버 유형</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-160">성능이 보고 되어야 하는 서버의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-160">Indicates the type of server whose performance should be reported.</span></span> <span data-ttu-id="8dec7-161">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-161">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="8dec7-162">모든</span><span class="sxs-lookup"><span data-stu-id="8dec7-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="8dec7-163">중재 서버</span><span class="sxs-lookup"><span data-stu-id="8dec7-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="8dec7-164">A/V 회의 서버</span><span class="sxs-lookup"><span data-stu-id="8dec7-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="8dec7-165">A/V에 지 서버</span><span class="sxs-lookup"><span data-stu-id="8dec7-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-166"><strong>상위 N 개</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-167">각 범주에 표시할 서버 수 (불량 통화 백분율 기준)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-167">Indicates the number of servers (based on their poor call percentage) to be displayed in each category.</span></span> <span data-ttu-id="8dec7-168">예를 들어 <strong>5</strong> 를 선택한 경우 5 개의 poorest 수행 하는 서버가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-168">For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed.</span></span> <span data-ttu-id="8dec7-169">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-169">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="8dec7-170">모든</span><span class="sxs-lookup"><span data-stu-id="8dec7-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="8dec7-171">5mb</span><span class="sxs-lookup"><span data-stu-id="8dec7-171">5</span></span></p></li>
<li><p><span data-ttu-id="8dec7-172">1천만</span><span class="sxs-lookup"><span data-stu-id="8dec7-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-173"><strong>Access 형식</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-174">전화를 걸 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-174">Indicates whether the client was logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="8dec7-175">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-175">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="8dec7-176">모든</span><span class="sxs-lookup"><span data-stu-id="8dec7-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="8dec7-177">내부용</span><span class="sxs-lookup"><span data-stu-id="8dec7-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="8dec7-178">내부</span><span class="sxs-lookup"><span data-stu-id="8dec7-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-179"><strong>네트워크 유형</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-180">전화를 걸 때 클라이언트가 연결 된 네트워크의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-180">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="8dec7-181">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-181">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="8dec7-182">모든</span><span class="sxs-lookup"><span data-stu-id="8dec7-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="8dec7-183">유</span><span class="sxs-lookup"><span data-stu-id="8dec7-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="8dec7-184">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="8dec7-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-185"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-186">통화를 했을 때 외부 클라이언트가 VPN (가상 사설망) 연결을 사용 중인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-186">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="8dec7-187">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-187">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="8dec7-188">모든</span><span class="sxs-lookup"><span data-stu-id="8dec7-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="8dec7-189">VPN</span><span class="sxs-lookup"><span data-stu-id="8dec7-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="8dec7-190">비 VPN</span><span class="sxs-lookup"><span data-stu-id="8dec7-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="8dec7-191">매트릭스</span><span class="sxs-lookup"><span data-stu-id="8dec7-191">Metrics</span></span>

<span data-ttu-id="8dec7-192">다음 표에는 서버 성능 보고서에서 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="8dec7-193">서버 성능 보고서 메트릭: 오디오 통화 요약</span><span class="sxs-lookup"><span data-stu-id="8dec7-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dec7-194">이름</span><span class="sxs-lookup"><span data-stu-id="8dec7-194">Name</span></span></th>
<th><span data-ttu-id="8dec7-195">정렬 가능</span><span class="sxs-lookup"><span data-stu-id="8dec7-195">Can Sort On</span></span></th>
<th><span data-ttu-id="8dec7-196">설명</span><span class="sxs-lookup"><span data-stu-id="8dec7-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-197"><strong>서버</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-198">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-198">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-199">서버의 이름/i p 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-200"><strong>통화 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-201">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-201">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-202">생성 된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-203"><strong>통화 불량 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-204">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-204">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-205">불량으로 분류 된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-205">Total number of calls classified as poor.</span></span> <span data-ttu-id="8dec7-206">잘못 된 통화는 측정 된 메트릭 중 적어도 하나가 허용 된 값 (예: 과도 한 지터)을 초과한 모든 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-206">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-207"><strong>왕복 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-208">예</span><span class="sxs-lookup"><span data-stu-id="8dec7-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="8dec7-209">다른 끝점으로 이동 하 고 나 서 다시 사용할 수 있는 RTP (실시간 전송 프로토콜) 패킷에 필요한 평균 양 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-209">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="8dec7-210">100 밀리초 이하의 왕복 시간은 허용 되는 품질로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-210">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="8dec7-211">높은 라운드트립 값은 국제 통화 라우팅으로 인해 발생할 수 있습니다. 라우팅 구성이 잘못 되었습니다. 또는 오버 로드 된 미디어 서버.</span><span class="sxs-lookup"><span data-stu-id="8dec7-211">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="8dec7-212">왕복 시간이 높으면 양방향 실시간 음성 대화에서 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-212">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-213"><strong>성능 저하 (SPECIALIST)</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-214">예</span><span class="sxs-lookup"><span data-stu-id="8dec7-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="8dec7-215">통화 중에 발생 한 평균 SPECIALIST (의미 있는 평가 점수) 감소 금액입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="8dec7-216">성능 저하 값의 범위는 0.0 ~ 5.0의 최대값까지입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="8dec7-217">0.5 이하의 값은 허용 되는 저하를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="8dec7-218">지금까지 평균 옵션 점수는 사용자가 1 ~ 5의 배율로 통화 품질을 평가할 수 있도록 하 여 계산 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="8dec7-219">Lync Server에서 모니터링 서버는 알고리즘 집합을 사용 하 여 사용자가 전화를 평가한 방법을 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="8dec7-220">높은 성능 저하 값은 정체, 대역폭 부족, 무선 정체 또는 간섭 또는 오버 로드 된 미디어 서버 또는 끝점으로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-220">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="8dec7-221">품질이 높으면 오디오가 왜곡 되거나 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-221">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-222"><strong>패킷 손실</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-223">예</span><span class="sxs-lookup"><span data-stu-id="8dec7-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="8dec7-224">RTP (실시간 전송 프로토콜) 패킷 손실의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-224">Average rate of real-time transport protocol (RTP) packet loss.</span></span> <span data-ttu-id="8dec7-225">(패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 높은 손실률은 일반적으로 혼잡, 대역폭 부족, 무선 정체 또는 간섭 또는 오버 로드 된 미디어 서버 중에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-225">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="8dec7-226">패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-226">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-227"><strong>지터 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-228">예</span><span class="sxs-lookup"><span data-stu-id="8dec7-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="8dec7-229">RTP 패킷 도착 간에 감지 된 평균 지터.</span><span class="sxs-lookup"><span data-stu-id="8dec7-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="8dec7-230">(지터는 통화의 &quot;shakiness&quot; 을 측정 하는 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-231"><strong>Healer 숨겨진 비율</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-232">예</span><span class="sxs-lookup"><span data-stu-id="8dec7-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="8dec7-233">총 샘플 수에 대 한 총 숨겨진 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-233">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="8dec7-234">(숨겨진 오디오 샘플은 일반적으로 손실 된 네트워크 패킷으로 인해 발생 하는 갑작스런 전환을 매끄럽게 하는 데 사용 되는 기술입니다.) 값이 높으면 패킷 손실률 또는 지터로 인해 적용 되는 손실 concealment의 상당 부분이 왜곡 되거나 손실 되는 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-234">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-235"><strong>Healer 늘이기 비율</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-236">예</span><span class="sxs-lookup"><span data-stu-id="8dec7-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="8dec7-237">총 샘플 수에 대 한 총 스트레치 된 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-237">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="8dec7-238">(늘인 오디오는 손실 된 네트워크 패킷이 감지 될 때 통화 품질을 유지 하기 위해 확장 되어 있는 오디오입니다.) 값이 높으면 지터로 인해 발생 하는 샘플 스트레치의 상당 수준을 나타내고, 오디오는 로보틱 또는 왜곡 될 때 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-238">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-239"><strong>Healer 압축 비율</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-240">예</span><span class="sxs-lookup"><span data-stu-id="8dec7-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="8dec7-241">총 샘플 수에 대 한 압축 된 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-241">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="8dec7-242">(압축 오디오는 손실 된 네트워크 패킷이 감지 되었을 때 통화 품질을 유지 하기 위해 압축 된 오디오입니다.) 값이 높으면 지터로 인해 발생 하는 샘플 압축의 상당 부분이 표시 되 고 오디오의 가속 또는 왜곡이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-242">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="8dec7-243">서버 성능 보고서 메트릭: 영상 통화 요약</span><span class="sxs-lookup"><span data-stu-id="8dec7-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dec7-244">이름</span><span class="sxs-lookup"><span data-stu-id="8dec7-244">Name</span></span></th>
<th><span data-ttu-id="8dec7-245">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="8dec7-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8dec7-246">설명</span><span class="sxs-lookup"><span data-stu-id="8dec7-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-247"><strong>통화 형식/끝점 형식</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-248">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-248">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-249">이 항목을 클릭 하면 보고서에 해당 형식에 따른 호출에 대 한 자세한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-249">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="8dec7-250">통화 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-250">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="8dec7-251">UC 피어 투 피어 통화</span><span class="sxs-lookup"><span data-stu-id="8dec7-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="8dec7-252">UC 회의 세션</span><span class="sxs-lookup"><span data-stu-id="8dec7-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="8dec7-253">PSTN 회의 세션</span><span class="sxs-lookup"><span data-stu-id="8dec7-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="8dec7-254">PSTN 통화: 미디어 바이패스</span><span class="sxs-lookup"><span data-stu-id="8dec7-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="8dec7-255">PSTN 통화 (비 바이패스): UC 레그</span><span class="sxs-lookup"><span data-stu-id="8dec7-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="8dec7-256">PSTN 통화 (비 바이패스): 게이트웨이 다리</span><span class="sxs-lookup"><span data-stu-id="8dec7-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="8dec7-257">기타 통화 형식</span><span class="sxs-lookup"><span data-stu-id="8dec7-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-258"><strong>통화 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-259">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-259">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-260">통화 유형별 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-261"><strong>통화 불량 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-262">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-262">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-263">불량으로 분류 된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-263">Total number of calls classified as poor.</span></span> <span data-ttu-id="8dec7-264">잘못 된 통화는 측정 된 메트릭 중 적어도 하나가 허용 된 값 (예: 과도 한 지터)을 초과한 모든 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-264">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-265"><strong>통화 볼륨 (무선 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-266">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-266">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-267">무선 연결을 사용한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-268"><strong>통화 볼륨 (VPN 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-269">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-269">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-270">VPN 연결을 사용한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-271"><strong>통화 볼륨 (외부 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-272">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-272">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-273">외부 연결 (즉, 내부 네트워크 외부의 연결)을 사용한 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-274"><strong>평균 비트 전송률 (킬/초)</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-275">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-275">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-276">평균 비디오 비트 전송률 (초당 k b/초)입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-277"><strong>낮은 비트/속도 비율 (%)</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-278">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-278">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-279">비트 전송률이 낮은 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-280"><strong>아웃 바운드 패킷 손실</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-281">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-281">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-282">아웃 바운드 패킷에 대 한 RTP (리얼 표준시 Transport Protocol) 패킷 손실</span><span class="sxs-lookup"><span data-stu-id="8dec7-282">Real-Time Transport Protocol (RTP) packet loss for outbound packets.</span></span> <span data-ttu-id="8dec7-283">(패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 일반적으로 정체 때문에 손실률이 높습니다. 대역폭 부족, 무선 정체 또는 간섭. 또는 오버 로드 된 미디어 서버.</span><span class="sxs-lookup"><span data-stu-id="8dec7-283">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="8dec7-284">패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-284">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-285"><strong>고정 프레임%</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-286">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-286">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-287">"고정 된" 프레임의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-287">Percentage of “frozen” frames.</span></span> <span data-ttu-id="8dec7-288">고정 프레임에서는 통화의 오디오 부분이 계속 진행 되는 동안 비디오가 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-288">In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-289"><strong>아웃 바운드 평균 프레임 속도</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-290">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-290">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-291">통화 중의 아웃 바운드 전송에 대 한 평균 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-292"><strong>인바운드 평균 프레임 속도</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-293">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-293">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-294">통화 중 들어오는 전송에 대 한 평균 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-295"><strong>인바운드 낮은 프레임 속도%</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-296">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-296">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-297">들어오는 비디오의 비트 전송률이 낮은 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-298"><strong>클라이언트 상태%</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8dec7-299">통화 중에 클라이언트 장치에 대 한 상대 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="8dec7-300">서버 성능 보고서 메트릭: 응용 프로그램 공유 통화 요약</span><span class="sxs-lookup"><span data-stu-id="8dec7-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8dec7-301">이름</span><span class="sxs-lookup"><span data-stu-id="8dec7-301">Name</span></span></th>
<th><span data-ttu-id="8dec7-302">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="8dec7-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8dec7-303">설명</span><span class="sxs-lookup"><span data-stu-id="8dec7-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-304"><strong>통화 형식/끝점 형식</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-305">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-305">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-306">이 항목을 클릭 하면 보고서에 해당 형식에 따른 호출에 대 한 자세한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-306">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="8dec7-307">통화 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-307">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="8dec7-308">UC 피어 투 피어 통화</span><span class="sxs-lookup"><span data-stu-id="8dec7-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="8dec7-309">UC 회의 세션</span><span class="sxs-lookup"><span data-stu-id="8dec7-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="8dec7-310">PSTN 회의 세션</span><span class="sxs-lookup"><span data-stu-id="8dec7-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="8dec7-311">PSTN 통화: 미디어 바이패스</span><span class="sxs-lookup"><span data-stu-id="8dec7-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="8dec7-312">PSTN 통화 (비 바이패스): UC 레그</span><span class="sxs-lookup"><span data-stu-id="8dec7-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="8dec7-313">PSTN 통화 (비 바이패스): 게이트웨이 다리</span><span class="sxs-lookup"><span data-stu-id="8dec7-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="8dec7-314">기타 통화 형식</span><span class="sxs-lookup"><span data-stu-id="8dec7-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-315"><strong>통화 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-316">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-316">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-317">통화 유형별 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-318"><strong>통화 불량 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-319">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-319">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-320">불량으로 분류 된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-320">Total number of calls classified as poor.</span></span> <span data-ttu-id="8dec7-321">잘못 된 통화는 측정 된 메트릭 중 적어도 하나가 허용 된 값 (예: 과도 한 지터)을 초과한 모든 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-321">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-322"><strong>통화 볼륨 (무선 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-323">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-323">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-324">무선 연결을 사용한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-325"><strong>통화 볼륨 (VPN 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-326">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-326">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-327">VPN 연결을 사용한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-328"><strong>통화 볼륨 (외부 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-329">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-329">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-330">외부 연결 (즉, 내부 네트워크 외부의 연결)을 사용한 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-331"><strong>지터 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-332">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-332">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-333">RTP 패킷 도착 간에 감지 된 평균 지터.</span><span class="sxs-lookup"><span data-stu-id="8dec7-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="8dec7-334">(지터는 통화의 &quot;shakiness&quot; 을 측정 하는 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-335"><strong>평균 기준 단방향</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-336">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-336">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-337">두 미디어 끝점 사이의 단방향 지연과 평균을 비교한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-337">Average relative one-way delay between two media endpoints.</span></span> <span data-ttu-id="8dec7-338">이것은 단일 홉 대기 시간 측정입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-338">This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8dec7-339"><strong>평균 .RDP 타일 처리 대기 시간</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-340">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-340">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-341">보기 세션 중에 회의 서버의 평균 RDP 타일 처리 대기 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-341">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="8dec7-342">이 메트릭은 네트워크 대기 시간을 차지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-342">This metric does not cover network latency.</span></span> <span data-ttu-id="8dec7-343">평균 높음은 보기 환경에서 더 오래 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-343">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="8dec7-344">오버 로드 된 회의 서버는 평균 지연 시간을 겪을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-344">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8dec7-345"><strong>총 spoiled 타일 비율 (%)</strong></span><span class="sxs-lookup"><span data-stu-id="8dec7-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="8dec7-346">아니요</span><span class="sxs-lookup"><span data-stu-id="8dec7-346">No</span></span></p></td>
<td><p><span data-ttu-id="8dec7-347">Spoiled RDP 타일의 총 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="8dec7-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

