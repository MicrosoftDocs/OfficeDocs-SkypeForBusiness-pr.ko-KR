---
title: 'Lync Server 2013: 위치 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0afe9de5220c81985ad4efc0f9c27d5ab87c325a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="8b9d2-102">Lync Server 2013의 위치 보고서</span><span class="sxs-lookup"><span data-stu-id="8b9d2-102">Location Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b9d2-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8b9d2-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8b9d2-p101">위치 보고서는 네트워크 위치(즉, 네트워크 서브넷)별로 그룹화된 통화 품질 메트릭에 대한 정보를 제공합니다. 사용자가 통화 품질에 문제를 겪는 경우 이 보고서를 통해 해당 문제가 전역적으로 나타나는지, 지정된 네트워크 세그먼트로만 크게 국한되는지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p101">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet). If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="8b9d2-106">위치 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="8b9d2-106">Accessing the Location Report</span></span>

<span data-ttu-id="8b9d2-p102">위치 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다. 또한 다음 메트릭 중 하나를 클릭하여 통화 목록 보고서까지 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p102">The Location Report is accessed from the Monitoring Reports home page. You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="8b9d2-109">통화량</span><span class="sxs-lookup"><span data-stu-id="8b9d2-109">Call volume</span></span>

  - <span data-ttu-id="8b9d2-110">불량 통화율</span><span class="sxs-lookup"><span data-stu-id="8b9d2-110">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8b9d2-111">필터</span><span class="sxs-lookup"><span data-stu-id="8b9d2-111">Filters</span></span>

<span data-ttu-id="8b9d2-p103">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 위치 보고서에서는 통화가 시작된 위치와 같은 항목 또는 무선 또는 유선 연결에서 통화가 수행되었는지 여부에 따라 필터링할 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 통화는 시간, 일, 주 및 월별로 그룹이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="8b9d2-116">다음 표에서는 위치 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-116">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="8b9d2-117">위치 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="8b9d2-117">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b9d2-118">이름</span><span class="sxs-lookup"><span data-stu-id="8b9d2-118">Name</span></span></th>
<th><span data-ttu-id="8b9d2-119">설명</span><span class="sxs-lookup"><span data-stu-id="8b9d2-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b9d2-120"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-p104">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8b9d2-123">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8b9d2-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8b9d2-p105">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8b9d2-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8b9d2-126">7/7/2012</span></span></p>
<p><span data-ttu-id="8b9d2-127">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-127">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8b9d2-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8b9d2-128">7/3/2012</span></span></p>
<p><span data-ttu-id="8b9d2-129">주는 항상 일요일부터 토요일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b9d2-130"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-p106">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8b9d2-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8b9d2-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8b9d2-p107">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8b9d2-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8b9d2-136">7/7/2012</span></span></p>
<p><span data-ttu-id="8b9d2-137">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8b9d2-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8b9d2-138">7/3/2012</span></span></p>
<p><span data-ttu-id="8b9d2-139">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b9d2-140"><strong>발신자 위치</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-140"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-p108">통화를 시작한 사용자의 IP 서브넷입니다. <strong>[모두]</strong>만 선택하면 모든 서브넷을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p108">IP subnet of the user who placed the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b9d2-143"><strong>수신자 위치</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-143"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-p109">통화를 받은 사용자의 IP 서브넷입니다. <strong>[모두]</strong>만 선택하면 모든 서브넷을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p109">IP subnet of the user who received the call. You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b9d2-146"><strong>네트워크 유형</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-146"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-p110">통화가 시도되었을 때 클라이언트가 연결된 네트워크의 유형을 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="8b9d2-149">모든</span><span class="sxs-lookup"><span data-stu-id="8b9d2-149">[All]</span></span></p></li>
<li><p><span data-ttu-id="8b9d2-150">유선</span><span class="sxs-lookup"><span data-stu-id="8b9d2-150">Wired</span></span></p></li>
<li><p><span data-ttu-id="8b9d2-151">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="8b9d2-151">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b9d2-152"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-152"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-p111">통화가 시도되었을 때 외부 클라이언트가 VPN(가상 사설망) 연결을 사용 중이었는지를 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="8b9d2-155">모든</span><span class="sxs-lookup"><span data-stu-id="8b9d2-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="8b9d2-156">VPN</span><span class="sxs-lookup"><span data-stu-id="8b9d2-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="8b9d2-157">비 VPN</span><span class="sxs-lookup"><span data-stu-id="8b9d2-157">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="8b9d2-158">선별한</span><span class="sxs-lookup"><span data-stu-id="8b9d2-158">Metrics</span></span>

<span data-ttu-id="8b9d2-159">다음 표에서는 위치 보고서에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-159">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="8b9d2-160">위치 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="8b9d2-160">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b9d2-161">이름</span><span class="sxs-lookup"><span data-stu-id="8b9d2-161">Name</span></span></th>
<th><span data-ttu-id="8b9d2-162">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="8b9d2-162">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8b9d2-163">설명</span><span class="sxs-lookup"><span data-stu-id="8b9d2-163">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b9d2-164"><strong>발신자 서브넷</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-164"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-165">아니요</span><span class="sxs-lookup"><span data-stu-id="8b9d2-165">No</span></span></p></td>
<td><p><span data-ttu-id="8b9d2-166">통화를 시작한 사용자의 IP 서브넷입니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-166">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b9d2-167"><strong>수신자 서브넷</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-167"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-168">아니요</span><span class="sxs-lookup"><span data-stu-id="8b9d2-168">No</span></span></p></td>
<td><p><span data-ttu-id="8b9d2-169">통화를 받은 사용자의 IP 서브넷입니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-169">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b9d2-170"><strong>통화량</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-170"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-171">예</span><span class="sxs-lookup"><span data-stu-id="8b9d2-171">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b9d2-172">수행된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-172">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b9d2-173"><strong>불량 통화율</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-173"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-174">예</span><span class="sxs-lookup"><span data-stu-id="8b9d2-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b9d2-p112">불량 통화로 분류된 통화 비율입니다. 불량 통화는 측정된 메트릭 중 적어도 하나 이상이 허용 값을 초과하는 모든 통화입니다(예: 지터가 과도하게 발생한 통화).</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p112">Percentage of calls classified as poor calls. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b9d2-177"><strong>왕복(밀리초)</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-177"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-178">예</span><span class="sxs-lookup"><span data-stu-id="8b9d2-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b9d2-p113">RTP(실시간 전송 프로토콜) 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 평균 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 100밀리초 미만 정도로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p113">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="8b9d2-p114">국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p114">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b9d2-183"><strong>저하(MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-184">예</span><span class="sxs-lookup"><span data-stu-id="8b9d2-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b9d2-185">통화 중 발생한 MOS(평균 평가점) 저하에 대한 평균값입니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-185">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="8b9d2-186">저하 값의 범위는 0.0(낮음)에서 5.0(높음)까지입니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-186">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="8b9d2-187">값이 0.5이하이면 허용 가능한 저하 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-187">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="8b9d2-188">현재까지 평균 평가점은 사용자가 1부터 5까지 통화 품질에 대한 점수를 스스로 매기게 하여 계산되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-188">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="8b9d2-189">Lync Server에서 Lync Server는 알고리즘 집합을 사용 하 여 사용자가 통화를 평가 하는 방법을 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-189">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="8b9d2-p116">정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버 또는 끝점의 과부하 등의 경우에는 저하 값이 높게 나타날 수 있습니다. 저하 값이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p116">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b9d2-192"><strong>패킷 손실</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-192"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-193">예</span><span class="sxs-lookup"><span data-stu-id="8b9d2-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b9d2-p117">RTP 패킷에 대한 평균 손실률입니다. (패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다.) 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p117">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b9d2-197"><strong>지터</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-197"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-198">예</span><span class="sxs-lookup"><span data-stu-id="8b9d2-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b9d2-199">RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-199">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="8b9d2-200">(지터는 통화의 &quot;shakiness&quot; 을 측정 한 것입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-200">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b9d2-201"><strong>힐러 숨김 비율</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-201"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-202">예</span><span class="sxs-lookup"><span data-stu-id="8b9d2-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b9d2-p119">총 오디오 샘플 수에 대한 숨겨진 평균 오디오 샘플 비율입니다. (숨겨진 오디오 샘플은 손실된 네트워크 패킷으로 인해 발생하는 갑작스러운 전환을 매끄럽게 조정하기 위해 사용되는 기술입니다.) 값이 높으면 패킷 손실이나 지터로 인해 적용된 손실 숨김 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p119">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b9d2-205"><strong>힐러 늘임 비율</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-205"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-206">예</span><span class="sxs-lookup"><span data-stu-id="8b9d2-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b9d2-p120">총 오디오 샘플 수에 대한 늘어진 평균 오디오 샘플 비율입니다. (늘어진 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 연장되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 늘림 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p120">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b9d2-209"><strong>힐러 압축 비율</strong></span><span class="sxs-lookup"><span data-stu-id="8b9d2-209"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="8b9d2-210">예</span><span class="sxs-lookup"><span data-stu-id="8b9d2-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="8b9d2-p121">총 샘플 수에 대한 압축된 평균 오디오 샘플 비율입니다. (압축된 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 압축되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 압축 수준이 높음을 의미하며 이로 인해 오디오가 빠르게 들리거나 왜곡됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b9d2-p121">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

