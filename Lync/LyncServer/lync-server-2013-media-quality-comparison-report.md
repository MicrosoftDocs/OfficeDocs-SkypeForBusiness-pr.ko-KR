---
title: 'Lync Server 2013: 미디어 품질 비교 보고서'
description: 'Lync Server 2013: 미디어 품질 비교 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2c4c5c948d167ce5210f9814c4e0625ffaa9152
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548234"
---
# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="0c180-103">Lync Server 2013의 미디어 품질 비교 보고서</span><span class="sxs-lookup"><span data-stu-id="0c180-103">Media Quality Comparison Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c180-104">_**마지막으로 수정 된 항목:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="0c180-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="0c180-105">미디어 품질 비교 보고서를 사용하면 다양한 유형의 오디오 통화(예: 유선 연결에서 수행된 통화와 무선 연결에서 수행된 통화)의 통화 품질 값을 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-105">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="0c180-106">미디어 품질 비교 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="0c180-106">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="0c180-107">미디어 품질 비교 보고서는 모니터링 보고서 홈 페이지에서 액세스됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-107">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0c180-108">필터</span><span class="sxs-lookup"><span data-stu-id="0c180-108">Filters</span></span>

<span data-ttu-id="0c180-p101">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에서는 미디어 품질 비교 보고서에서 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="0c180-111">미디어 품질 비교 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="0c180-111">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c180-112">이름</span><span class="sxs-lookup"><span data-stu-id="0c180-112">Name</span></span></th>
<th><span data-ttu-id="0c180-113">설명</span><span class="sxs-lookup"><span data-stu-id="0c180-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c180-114"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="0c180-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0c180-p102">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0c180-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0c180-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0c180-p103">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0c180-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0c180-120">7/7/2012</span></span></p>
<p><span data-ttu-id="0c180-121">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0c180-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0c180-122">7/3/2012</span></span></p>
<p><span data-ttu-id="0c180-123">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c180-124"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="0c180-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0c180-p104">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0c180-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0c180-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0c180-p105">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0c180-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0c180-130">7/7/2012</span></span></p>
<p><span data-ttu-id="0c180-131">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0c180-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0c180-132">7/3/2012</span></span></p>
<p><span data-ttu-id="0c180-133">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c180-134"><strong>착신</strong></span><span class="sxs-lookup"><span data-stu-id="0c180-134"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="0c180-p106">주 비교 항목으로 사용할 통화 유형입니다. 허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-p106">Type of call to be used as the main comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="0c180-137">모든</span><span class="sxs-lookup"><span data-stu-id="0c180-137">[All]</span></span></p></li>
<li><p><span data-ttu-id="0c180-138">외부</span><span class="sxs-lookup"><span data-stu-id="0c180-138">External</span></span></p></li>
<li><p><span data-ttu-id="0c180-139">내부</span><span class="sxs-lookup"><span data-stu-id="0c180-139">Internal</span></span></p></li>
<li><p><span data-ttu-id="0c180-140">VPN</span><span class="sxs-lookup"><span data-stu-id="0c180-140">VPN</span></span></p></li>
<li><p><span data-ttu-id="0c180-141">비 VPN</span><span class="sxs-lookup"><span data-stu-id="0c180-141">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="0c180-142">유선</span><span class="sxs-lookup"><span data-stu-id="0c180-142">Wired</span></span></p></li>
<li><p><span data-ttu-id="0c180-143">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="0c180-143">Wireless</span></span></p></li>
<li><p><span data-ttu-id="0c180-144">외부 및 유선</span><span class="sxs-lookup"><span data-stu-id="0c180-144">External and wired</span></span></p></li>
<li><p><span data-ttu-id="0c180-145">외부 및 무선</span><span class="sxs-lookup"><span data-stu-id="0c180-145">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="0c180-146">외부 및 VPN</span><span class="sxs-lookup"><span data-stu-id="0c180-146">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="0c180-147">외부 및 VPN 외</span><span class="sxs-lookup"><span data-stu-id="0c180-147">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="0c180-148">내부 및 유선</span><span class="sxs-lookup"><span data-stu-id="0c180-148">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="0c180-149">내부 및 무선</span><span class="sxs-lookup"><span data-stu-id="0c180-149">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c180-150"><strong>비교 통화 항목</strong></span><span class="sxs-lookup"><span data-stu-id="0c180-150"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="0c180-p107">보조 비교 항목으로 사용할 통화 유형입니다. 허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-p107">Type of call to be used as the secondary comparison item. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="0c180-153">모든</span><span class="sxs-lookup"><span data-stu-id="0c180-153">[All]</span></span></p></li>
<li><p><span data-ttu-id="0c180-154">외부</span><span class="sxs-lookup"><span data-stu-id="0c180-154">External</span></span></p></li>
<li><p><span data-ttu-id="0c180-155">내부</span><span class="sxs-lookup"><span data-stu-id="0c180-155">Internal</span></span></p></li>
<li><p><span data-ttu-id="0c180-156">VPN</span><span class="sxs-lookup"><span data-stu-id="0c180-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="0c180-157">비 VPN</span><span class="sxs-lookup"><span data-stu-id="0c180-157">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="0c180-158">유선</span><span class="sxs-lookup"><span data-stu-id="0c180-158">Wired</span></span></p></li>
<li><p><span data-ttu-id="0c180-159">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="0c180-159">Wireless</span></span></p></li>
<li><p><span data-ttu-id="0c180-160">외부 및 유선</span><span class="sxs-lookup"><span data-stu-id="0c180-160">External and wired</span></span></p></li>
<li><p><span data-ttu-id="0c180-161">외부 및 무선</span><span class="sxs-lookup"><span data-stu-id="0c180-161">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="0c180-162">외부 및 VPN</span><span class="sxs-lookup"><span data-stu-id="0c180-162">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="0c180-163">외부 및 VPN 외</span><span class="sxs-lookup"><span data-stu-id="0c180-163">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="0c180-164">내부 및 유선</span><span class="sxs-lookup"><span data-stu-id="0c180-164">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="0c180-165">내부 및 무선</span><span class="sxs-lookup"><span data-stu-id="0c180-165">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c180-166"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="0c180-166"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="0c180-p108">시간 간격입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0c180-169">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="0c180-169">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0c180-170">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="0c180-170">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0c180-171">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="0c180-171">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="0c180-p109">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="0c180-174">메트릭</span><span class="sxs-lookup"><span data-stu-id="0c180-174">Metrics</span></span>

<span data-ttu-id="0c180-175">다음 표에서는 미디어 품질 비교 보고서에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-175">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="0c180-176">미디어 품질 비교 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="0c180-176">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c180-177">이름</span><span class="sxs-lookup"><span data-stu-id="0c180-177">Name</span></span></th>
<th><span data-ttu-id="0c180-178">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="0c180-178">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0c180-179">설명</span><span class="sxs-lookup"><span data-stu-id="0c180-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c180-180"><strong>통화량</strong></span><span class="sxs-lookup"><span data-stu-id="0c180-180"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0c180-181">아니요</span><span class="sxs-lookup"><span data-stu-id="0c180-181">No</span></span></p></td>
<td><p><span data-ttu-id="0c180-182">총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-182">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c180-183"><strong>저하(MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="0c180-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="0c180-184">아니요</span><span class="sxs-lookup"><span data-stu-id="0c180-184">No</span></span></p></td>
<td><p><span data-ttu-id="0c180-185">통화 중에 발생 하는 평균 MOS (즉, 평균 평가 점수) 성능 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-185">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="0c180-186">성능 저하 값의 범위는 0.0 개에서 높은 5.0 까지입니다. 값이 0.5 이하인 경우 허용 되는 저하를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-186">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="0c180-187">이전에는 사용자가 1 ~ 5의 배율로 통화 품질을 평가 하 여 평균 성적 점수를 계산 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-187">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="0c180-188">Lync Server에서는 사용자가 통화를 평가 하는 방법을 예측 하기 위한 알고리즘 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-188">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="0c180-p111">정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버 또는 끝점의 과부하 등의 경우에는 저하 값이 높게 나타날 수 있습니다. 저하 값이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-p111">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c180-191"><strong>불량 통화율</strong></span><span class="sxs-lookup"><span data-stu-id="0c180-191"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0c180-192">아니요</span><span class="sxs-lookup"><span data-stu-id="0c180-192">No</span></span></p></td>
<td><p><span data-ttu-id="0c180-p112">불량으로 분류된 총 통화 수입니다. 불량 통화는 측정된 메트릭 중 적어도 하나 이상이 허용 값을 초과하는 모든 통화입니다(예: 지터가 과도하게 발생한 통화).</span><span class="sxs-lookup"><span data-stu-id="0c180-p112">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c180-195"><strong>왕복(밀리초)</strong></span><span class="sxs-lookup"><span data-stu-id="0c180-195"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="0c180-196">아니요</span><span class="sxs-lookup"><span data-stu-id="0c180-196">No</span></span></p></td>
<td><p><span data-ttu-id="0c180-p113">RTP(실시간 전송 프로토콜) 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 평균 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 200밀리초 미만 정도로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-p113">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="0c180-p114">국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-p114">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c180-201"><strong>패킷 손실</strong></span><span class="sxs-lookup"><span data-stu-id="0c180-201"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="0c180-202">아니요</span><span class="sxs-lookup"><span data-stu-id="0c180-202">No</span></span></p></td>
<td><p><span data-ttu-id="0c180-p115">RTP(Real-time Transport Protocol) 패킷 손실의 평균 비율입니다. (패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다.) 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-p115">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c180-206"><strong>지터(밀리초)</strong></span><span class="sxs-lookup"><span data-stu-id="0c180-206"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="0c180-207">아니요</span><span class="sxs-lookup"><span data-stu-id="0c180-207">No</span></span></p></td>
<td><p><span data-ttu-id="0c180-208">RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-208">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="0c180-209">(지터는 통화의 shakiness을 측정 한 것 &quot; &quot; 입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-209">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c180-210"><strong>힐러 숨김 비율</strong></span><span class="sxs-lookup"><span data-stu-id="0c180-210"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="0c180-211">아니요</span><span class="sxs-lookup"><span data-stu-id="0c180-211">No</span></span></p></td>
<td><p><span data-ttu-id="0c180-p117">총 오디오 샘플 수에 대한 숨겨진 평균 오디오 샘플 비율입니다. (숨겨진 오디오 샘플은 손실된 네트워크 패킷으로 인해 발생하는 갑작스러운 전환을 매끄럽게 조정하기 위해 사용되는 기술입니다.) 값이 높으면 패킷 손실이나 지터로 인해 적용된 손실 숨김 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-p117">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c180-214"><strong>힐러 늘임 비율</strong></span><span class="sxs-lookup"><span data-stu-id="0c180-214"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="0c180-215">아니요</span><span class="sxs-lookup"><span data-stu-id="0c180-215">No</span></span></p></td>
<td><p><span data-ttu-id="0c180-p118">총 오디오 샘플 수에 대한 늘어진 평균 오디오 샘플 비율입니다. (늘어진 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 연장되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 늘림 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-p118">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c180-218"><strong>힐러 압축 비율</strong></span><span class="sxs-lookup"><span data-stu-id="0c180-218"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="0c180-219">아니요</span><span class="sxs-lookup"><span data-stu-id="0c180-219">No</span></span></p></td>
<td><p><span data-ttu-id="0c180-p119">총 샘플 수에 대한 압축된 평균 오디오 샘플 비율입니다. (압축된 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 압축되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 압축 수준이 높음을 의미하며 이로 인해 오디오가 빠르게 들리거나 왜곡됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c180-p119">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

