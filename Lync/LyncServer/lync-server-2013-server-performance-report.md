---
title: 'Lync Server 2013: 서버 성능 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff400c0384d6b9e6b51da09666629d1bb6b725ee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="3c6a2-102">Lync Server 2013의 서버 성능 보고서</span><span class="sxs-lookup"><span data-stu-id="3c6a2-102">Server Performance Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c6a2-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="3c6a2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="3c6a2-104">서버 성능 보고서는 잘못 된 통화의 최고 비율을 경험한 Microsoft Lync Server 2013 서버 목록을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="3c6a2-105">보고서에서는 서버 유형별 서버를 분해 하 고 다음 유형에 대 한 별도의 통계를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="3c6a2-106">중재 서버</span><span class="sxs-lookup"><span data-stu-id="3c6a2-106">Mediation Server</span></span>

  - <span data-ttu-id="3c6a2-107">A/V 회의 서버</span><span class="sxs-lookup"><span data-stu-id="3c6a2-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="3c6a2-108">A/V 에지 서버</span><span class="sxs-lookup"><span data-stu-id="3c6a2-108">A/V Edge Server</span></span>

  - <span data-ttu-id="3c6a2-109">게이트웨이(중재 서버)</span><span class="sxs-lookup"><span data-stu-id="3c6a2-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="3c6a2-110">게이트웨이(중재 서버 바이패스)</span><span class="sxs-lookup"><span data-stu-id="3c6a2-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="3c6a2-111">비디오(A/V 회의 서버 및 A/V 에지 서버에 대한 비디오 메트릭 포함)</span><span class="sxs-lookup"><span data-stu-id="3c6a2-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="3c6a2-112">응용 프로그램 공유(A/V 회의 서버 및 A/V 에지 서버에 대한 응용 프로그램 공유 메트릭 포함)</span><span class="sxs-lookup"><span data-stu-id="3c6a2-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="3c6a2-p102">이 보고서에 나타나는 순위는 상대적인 순위입니다. 예를 들어 가장 성능이 낮은 서버에서 이루어진 통화 1,000건 중 불량 통화가 1건인 경우 불량 통화율이 0.1%이므로 허용되는 비율보다 높습니다. 그러나 다른 모든 서버의 불량 통화율이 0.1%보다도 더 낮아 이 서버의 성능이 가장 낮게 나온 경우 이 서버가 서버 성능 보고서에 여전히 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p102">It’s important to note that the ranking shown in this report as relative rankings. For example, suppose your worst-performing server had one poor call among its 1,000 placed calls. That's a more-than-acceptable percentage of .1%. However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="3c6a2-117">서버 성능 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="3c6a2-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="3c6a2-118">서버 성능 보고서는 모니터링 보고서 홈 페이지에서 액세스됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="3c6a2-119">[Lync Server 2013에서](lync-server-2013-call-list-report.md) 다음 메트릭 중 하나를 클릭 하 여 Call List Report로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="3c6a2-120">통화량</span><span class="sxs-lookup"><span data-stu-id="3c6a2-120">Call volume</span></span>

  - <span data-ttu-id="3c6a2-121">불량 통화율</span><span class="sxs-lookup"><span data-stu-id="3c6a2-121">Poor call percentage</span></span>

<span data-ttu-id="3c6a2-122">또한 다음 메트릭을 클릭하여 서버 미디어 품질 추세 보고서로 드릴다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="3c6a2-123">보여줍니다</span><span class="sxs-lookup"><span data-stu-id="3c6a2-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="3c6a2-124">서버 성능 보고서의 효과적인 활용</span><span class="sxs-lookup"><span data-stu-id="3c6a2-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="3c6a2-p104">서버 성능 보고서에서는 여러 방식으로 데이터를 필터링할 수 있습니다. 예를 들어 네트워크 유형(유선 연결에서 수행된 통화와 무선 연결에서 수행된 통화) 및 액세스 유형(방화벽 내부에서 수행된 통화와 방화벽 외부에서 수행된 통화)을 기준으로 데이터를 필터링할 수 있습니다. 서버 성능 보고서를 확인할 때 이러한 필터를 활용하는 것이 좋습니다. 예를 들어 중재 서버의 불량 통화율이 3.24%일 경우 무선 통화만 확인해 보면 같은 서버의 불량 통화율이 20%에 육박할 수 있습니다. 이는 이 서버가 무선 통화에 문제가 있었음을 나타냅니다. 이 서버는 유선 통화에 문제가 없었기 때문에 필터를 활용하지 않았다면 이 문제가 있다는 것을 다소 파악하기 힘들었을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p104">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall). It's a good idea when viewing the server performance report to make use of these filters. For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%. If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%. That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="3c6a2-130">필터</span><span class="sxs-lookup"><span data-stu-id="3c6a2-130">Filters</span></span>

<span data-ttu-id="3c6a2-p105">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 서버 성능 보고서에서는 반환된 데이터를 서버 유형 또는 네트워크 유형(즉, 유선 또는 무선)별로 필터링하는 등의 작업을 수행할 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 데이터는 시간, 일, 주 또는 월별로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless). You can also choose how data should be grouped. In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="3c6a2-135">다음 표에서는 서버 성능 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="3c6a2-136">서버 성능 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="3c6a2-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c6a2-137">이름</span><span class="sxs-lookup"><span data-stu-id="3c6a2-137">Name</span></span></th>
<th><span data-ttu-id="3c6a2-138">설명</span><span class="sxs-lookup"><span data-stu-id="3c6a2-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-139"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p106">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="3c6a2-142">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="3c6a2-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3c6a2-p107">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3c6a2-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3c6a2-145">7/7/2012</span></span></p>
<p><span data-ttu-id="3c6a2-146">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3c6a2-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3c6a2-147">7/3/2012</span></span></p>
<p><span data-ttu-id="3c6a2-148">주는 항상 일요일부터 토요일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-149"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p108">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="3c6a2-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="3c6a2-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3c6a2-p109">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3c6a2-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3c6a2-155">7/7/2012</span></span></p>
<p><span data-ttu-id="3c6a2-156">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3c6a2-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3c6a2-157">7/3/2012</span></span></p>
<p><span data-ttu-id="3c6a2-158">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-159"><strong>서버 유형</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p110">성능을 보고할 서버 유형을 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p110">Indicates the type of server whose performance should be reported. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="3c6a2-162">모든</span><span class="sxs-lookup"><span data-stu-id="3c6a2-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-163">중재 서버</span><span class="sxs-lookup"><span data-stu-id="3c6a2-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-164">A/V 회의 서버</span><span class="sxs-lookup"><span data-stu-id="3c6a2-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-165">A/V 에지 서버</span><span class="sxs-lookup"><span data-stu-id="3c6a2-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-166"><strong>상위 N</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p111">각 범주에 표시할 서버 수(풀 통화 비율 기반)를 나타냅니다. 예를 들어 <strong>5</strong>를 선택하면 5개의 성능이 가장 낮은 서버가 표시됩니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p111">Indicates the number of servers (based on their poor call percentage) to be displayed in each category. For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="3c6a2-170">모든</span><span class="sxs-lookup"><span data-stu-id="3c6a2-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-171">2-5</span><span class="sxs-lookup"><span data-stu-id="3c6a2-171">5</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-172">10 </span><span class="sxs-lookup"><span data-stu-id="3c6a2-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-173"><strong>액세스 유형</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p112">통화가 시도되었을 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온되어 있는지를 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="3c6a2-176">모든</span><span class="sxs-lookup"><span data-stu-id="3c6a2-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-177">Internal</span><span class="sxs-lookup"><span data-stu-id="3c6a2-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-178">외부:</span><span class="sxs-lookup"><span data-stu-id="3c6a2-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-179"><strong>네트워크 유형</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p113">통화가 시도되었을 때 클라이언트가 연결된 네트워크의 유형을 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="3c6a2-182">모든</span><span class="sxs-lookup"><span data-stu-id="3c6a2-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-183">유선</span><span class="sxs-lookup"><span data-stu-id="3c6a2-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-184">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="3c6a2-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-185"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p114">통화가 시도되었을 때 외부 클라이언트가 VPN(가상 사설망) 연결을 사용 중이었는지를 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="3c6a2-188">모든</span><span class="sxs-lookup"><span data-stu-id="3c6a2-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-189">VPN</span><span class="sxs-lookup"><span data-stu-id="3c6a2-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-190">비 VPN</span><span class="sxs-lookup"><span data-stu-id="3c6a2-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="3c6a2-191">선별한</span><span class="sxs-lookup"><span data-stu-id="3c6a2-191">Metrics</span></span>

<span data-ttu-id="3c6a2-192">다음 표에서는 서버 성능 보고서에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="3c6a2-193">서버 성능 보고서 메트릭: 오디오 통화 요약</span><span class="sxs-lookup"><span data-stu-id="3c6a2-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c6a2-194">이름</span><span class="sxs-lookup"><span data-stu-id="3c6a2-194">Name</span></span></th>
<th><span data-ttu-id="3c6a2-195">정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="3c6a2-195">Can Sort On</span></span></th>
<th><span data-ttu-id="3c6a2-196">설명</span><span class="sxs-lookup"><span data-stu-id="3c6a2-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-197"><strong>서버</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-198">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-198">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-199">서버의 이름/IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-200"><strong>통화량</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-201">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-201">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-202">수행된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-203"><strong>불량 통화율</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-204">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-204">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p115">불량으로 분류된 총 통화 수입니다. 불량 통화는 측정된 메트릭 중 적어도 하나 이상이 허용 값을 초과하는 모든 통화입니다(예: 지터가 과도하게 발생한 통화).</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p115">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-207"><strong>왕복(밀리초)</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-208">예</span><span class="sxs-lookup"><span data-stu-id="3c6a2-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p116">RTP(실시간 전송 프로토콜) 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 평균 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 100밀리초 미만 정도로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p116">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="3c6a2-p117">국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p117">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-213"><strong>저하(MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-214">예</span><span class="sxs-lookup"><span data-stu-id="3c6a2-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-215">통화 중 발생한 MOS(평균 평가점) 저하에 대한 평균값입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="3c6a2-216">저하 값의 범위는 0.0(낮음)에서 5.0(높음)까지입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="3c6a2-217">값이 0.5이하이면 허용 가능한 저하 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="3c6a2-218">현재까지 평균 평가점은 사용자가 1부터 5까지 통화 품질에 대한 점수를 스스로 매기게 하여 계산되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="3c6a2-219">Lync Server에서 모니터링 서버는 알고리즘 집합을 사용 하 여 사용자가 통화를 평가 하는 방법을 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="3c6a2-p119">정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버 또는 끝점의 과부하 등의 경우에는 저하 값이 높게 나타날 수 있습니다. 저하 값이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p119">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-222"><strong>패킷 손실</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-223">예</span><span class="sxs-lookup"><span data-stu-id="3c6a2-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p120">RTP(Real-time Transport Protocol) 패킷 손실의 평균 비율입니다. 패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다. 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p120">Average rate of real-time transport protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-227"><strong>지터(밀리초)</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-228">예</span><span class="sxs-lookup"><span data-stu-id="3c6a2-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-229">RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="3c6a2-230">(지터는 통화의 &quot;shakiness&quot; 을 측정 한 것입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-231"><strong>힐러 숨김 비율</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-232">예</span><span class="sxs-lookup"><span data-stu-id="3c6a2-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p122">총 오디오 샘플 수에 대한 숨겨진 평균 오디오 샘플 비율입니다. (숨겨진 오디오 샘플은 손실된 네트워크 패킷으로 인해 발생하는 갑작스러운 전환을 매끄럽게 조정하기 위해 사용되는 기술입니다.) 값이 높으면 패킷 손실이나 지터로 인해 적용된 손실 숨김 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p122">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-235"><strong>힐러 늘임 비율</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-236">예</span><span class="sxs-lookup"><span data-stu-id="3c6a2-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p123">총 오디오 샘플 수에 대한 늘어진 평균 오디오 샘플 비율입니다. (늘어진 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 연장되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 늘림 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p123">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-239"><strong>힐러 압축 비율</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-240">예</span><span class="sxs-lookup"><span data-stu-id="3c6a2-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p124">총 샘플 수에 대한 압축된 평균 오디오 샘플 비율입니다. (압축된 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 압축되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 압축 수준이 높음을 의미하며 이로 인해 오디오가 빠르게 들리거나 왜곡됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p124">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="3c6a2-243">서버 성능 보고서 메트릭: 비디오 통화 요약</span><span class="sxs-lookup"><span data-stu-id="3c6a2-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c6a2-244">이름</span><span class="sxs-lookup"><span data-stu-id="3c6a2-244">Name</span></span></th>
<th><span data-ttu-id="3c6a2-245">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="3c6a2-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3c6a2-246">설명</span><span class="sxs-lookup"><span data-stu-id="3c6a2-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-247"><strong>통화 유형/끝점 유형</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-248">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-248">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p125">이 항목을 클릭하면 보고서에 해당 유형에 따른 통화 세부 정보가 표시됩니다. 통화 유형에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p125">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="3c6a2-251">UC 피어 투 피어 통화</span><span class="sxs-lookup"><span data-stu-id="3c6a2-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-252">UC 회의 세션</span><span class="sxs-lookup"><span data-stu-id="3c6a2-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-253">PSTN 회의 세션</span><span class="sxs-lookup"><span data-stu-id="3c6a2-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-254">PSTN 통화: 미디어 바이패스</span><span class="sxs-lookup"><span data-stu-id="3c6a2-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-255">PSTN 통화(바이패스 없음): UC 레그</span><span class="sxs-lookup"><span data-stu-id="3c6a2-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-256">PSTN 통화(바이패스 없음): 게이트웨이 레그</span><span class="sxs-lookup"><span data-stu-id="3c6a2-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-257">기타 통화 유형</span><span class="sxs-lookup"><span data-stu-id="3c6a2-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-258"><strong>통화량</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-259">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-259">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-260">통화 유형별 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-261"><strong>불량 통화율</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-262">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-262">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p126">불량으로 분류된 총 통화 수입니다. 불량 통화는 측정된 메트릭 중 적어도 하나 이상이 허용 값을 초과하는 모든 통화입니다(예: 지터가 과도하게 발생한 통화).</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p126">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-265"><strong>통화량(무선 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-266">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-266">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-267">무선 연결이 사용된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-268"><strong>통화량(VPN 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-269">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-269">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-270">VPN 연결이 사용된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-271"><strong>통화량(외부 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-272">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-272">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-273">외부 연결이 사용된 통화 수입니다(예: 내부 네트워크 외부의 연결).</span><span class="sxs-lookup"><span data-stu-id="3c6a2-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-274"><strong>평균 비트 전송률(킬로비트/초)</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-275">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-275">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-276">비디오의 평균 비트 전송률(킬로비트/초)입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-277"><strong>낮은 비트 전송률 비율</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-278">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-278">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-279">비트 전송률이 낮은 통화의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-280"><strong>아웃바운드 패킷 손실</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-281">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-281">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p127">아웃바운드 패킷의 RTP(Real-time Transport Protocol) 패킷 손실입니다. 패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다. 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p127">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-285"><strong>정지된 프레임 비율</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-286">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-286">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p128">정지된 프레임의 비율입니다. 정지된 프레임에서는 통화의 오디오 부분이 계속되는 동안 비디오 진행이 멈춥니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p128">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-289"><strong>아웃바운드 평균 프레임 속도</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-290">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-290">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-291">통화 중 아웃바운드 전송의 평균 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-292"><strong>인바운드 평균 프레임 속도</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-293">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-293">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-294">통화 중 들어오는 전송의 평균 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-295"><strong>인바운드 낮은 프레임 속도 비율</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-296">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-296">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-297">수신 비디오의 비트 전송률이 낮은 통화의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-298"><strong>클라이언트 상태 비율</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3c6a2-299">통화 시 클라이언트 장치의 상대적인 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="3c6a2-300">서버 성능 보고서 메트릭: 응용 프로그램 공유 통화 요약</span><span class="sxs-lookup"><span data-stu-id="3c6a2-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c6a2-301">이름</span><span class="sxs-lookup"><span data-stu-id="3c6a2-301">Name</span></span></th>
<th><span data-ttu-id="3c6a2-302">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="3c6a2-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3c6a2-303">설명</span><span class="sxs-lookup"><span data-stu-id="3c6a2-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-304"><strong>통화 유형/끝점 유형</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-305">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-305">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p129">이 항목을 클릭하면 보고서에 해당 유형에 따른 통화 세부 정보가 표시됩니다. 통화 유형에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p129">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="3c6a2-308">UC 피어 투 피어 통화</span><span class="sxs-lookup"><span data-stu-id="3c6a2-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-309">UC 회의 세션</span><span class="sxs-lookup"><span data-stu-id="3c6a2-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-310">PSTN 회의 세션</span><span class="sxs-lookup"><span data-stu-id="3c6a2-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-311">PSTN 통화: 미디어 바이패스</span><span class="sxs-lookup"><span data-stu-id="3c6a2-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-312">PSTN 통화(바이패스 없음): UC 레그</span><span class="sxs-lookup"><span data-stu-id="3c6a2-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-313">PSTN 통화(바이패스 없음): 게이트웨이 레그</span><span class="sxs-lookup"><span data-stu-id="3c6a2-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="3c6a2-314">기타 통화 유형</span><span class="sxs-lookup"><span data-stu-id="3c6a2-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-315"><strong>통화량</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-316">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-316">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-317">통화 유형별 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-318"><strong>불량 통화율</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-319">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-319">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p130">불량으로 분류된 총 통화 수입니다. 불량 통화는 측정된 메트릭 중 적어도 하나 이상이 허용 값을 초과하는 모든 통화입니다(예: 지터가 과도하게 발생한 통화).</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p130">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-322"><strong>통화량(무선 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-323">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-323">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-324">무선 연결이 사용된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-325"><strong>통화량(VPN 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-326">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-326">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-327">VPN 연결이 사용된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-328"><strong>통화량(외부 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-329">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-329">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-330">외부 연결이 사용된 통화 수입니다(예: 내부 네트워크 외부의 연결).</span><span class="sxs-lookup"><span data-stu-id="3c6a2-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-331"><strong>지터(밀리초)</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-332">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-332">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-333">RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="3c6a2-334">(지터는 통화의 &quot;shakiness&quot; 을 측정 한 것입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-335"><strong>평균 상대 단방향</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-336">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-336">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p132">두 미디어 끝점 간의 평균 상대 단방향 지연입니다. 이는 단일 홉 대기 시간 측정값입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p132">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c6a2-339"><strong>평균 RDP 타일 처리 대기 시간</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-340">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-340">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-p133">보기 세션 동안 AS 회의 서버의 평균 RDP 타일 처리 대기 시간입니다. 이 메트릭에는 네트워크 대기 시간이 포함되지 않습니다. 평균이 높으면 보기 환경의 지연이 긴 것입니다. 과부하 회의 서버에서 평균 지연 값이 더욱 높게 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-p133">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session. This metric does not cover network latency. A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c6a2-345"><strong>총 손상 타일 비율</strong></span><span class="sxs-lookup"><span data-stu-id="3c6a2-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="3c6a2-346">아니요</span><span class="sxs-lookup"><span data-stu-id="3c6a2-346">No</span></span></p></td>
<td><p><span data-ttu-id="3c6a2-347">손상된 RDP 타일의 총 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="3c6a2-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

