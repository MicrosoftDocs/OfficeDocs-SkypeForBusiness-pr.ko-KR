---
title: 'Lync Server 2013: 미디어 품질 메트릭 배포 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48ee62d2eee4ab6e18b3c0c07b46f79b779bcce1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="1baac-102">Lync Server 2013의 미디어 품질 메트릭 배포 보고서</span><span class="sxs-lookup"><span data-stu-id="1baac-102">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1baac-103">_**마지막으로 수정 된 항목:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="1baac-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="1baac-p101">미디어 품질 메트릭 분포 보고서를 사용하면 지터, 패킷 손실 등 QoE(체감 품질)의 분포 값을 표시하는 그래프를 확인할 수 있습니다. 예를 들어 사용자가 총 10건의 전화 통화를 한 경우 해당 10건의 통화가 다음 왕복 시간을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-p101">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss. For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1baac-106">통화 횟수</span><span class="sxs-lookup"><span data-stu-id="1baac-106">Call Number</span></span></th>
<th><span data-ttu-id="1baac-107">왕복 시간(밀리초)</span><span class="sxs-lookup"><span data-stu-id="1baac-107">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1baac-108">개</span><span class="sxs-lookup"><span data-stu-id="1baac-108">1</span></span></p></td>
<td><p><span data-ttu-id="1baac-109">50</span><span class="sxs-lookup"><span data-stu-id="1baac-109">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1baac-110">2</span><span class="sxs-lookup"><span data-stu-id="1baac-110">2</span></span></p></td>
<td><p><span data-ttu-id="1baac-111">50</span><span class="sxs-lookup"><span data-stu-id="1baac-111">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1baac-112">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="1baac-112">3</span></span></p></td>
<td><p><span data-ttu-id="1baac-113">50</span><span class="sxs-lookup"><span data-stu-id="1baac-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1baac-114">1-4</span><span class="sxs-lookup"><span data-stu-id="1baac-114">4</span></span></p></td>
<td><p><span data-ttu-id="1baac-115">50</span><span class="sxs-lookup"><span data-stu-id="1baac-115">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1baac-116">2-5</span><span class="sxs-lookup"><span data-stu-id="1baac-116">5</span></span></p></td>
<td><p><span data-ttu-id="1baac-117">50</span><span class="sxs-lookup"><span data-stu-id="1baac-117">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1baac-118">6 </span><span class="sxs-lookup"><span data-stu-id="1baac-118">6</span></span></p></td>
<td><p><span data-ttu-id="1baac-119">50</span><span class="sxs-lookup"><span data-stu-id="1baac-119">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1baac-120">7 </span><span class="sxs-lookup"><span data-stu-id="1baac-120">7</span></span></p></td>
<td><p><span data-ttu-id="1baac-121">50</span><span class="sxs-lookup"><span data-stu-id="1baac-121">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1baac-122">8 </span><span class="sxs-lookup"><span data-stu-id="1baac-122">8</span></span></p></td>
<td><p><span data-ttu-id="1baac-123">4550</span><span class="sxs-lookup"><span data-stu-id="1baac-123">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1baac-124">9 </span><span class="sxs-lookup"><span data-stu-id="1baac-124">9</span></span></p></td>
<td><p><span data-ttu-id="1baac-125">50</span><span class="sxs-lookup"><span data-stu-id="1baac-125">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1baac-126">10 </span><span class="sxs-lookup"><span data-stu-id="1baac-126">10</span></span></p></td>
<td><p><span data-ttu-id="1baac-127">50</span><span class="sxs-lookup"><span data-stu-id="1baac-127">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1baac-p102">이러한 왕복 시간의 평균은 500밀리초(5000을 10으로 나눈 값)입니다. 500밀리초는 상당히 긴 왕복 시간이므로 심각한 네트워크 정체 문제가 있다고 생각할 것입니다. 왕복 시간이 길면 일번적으로 네트워크가 과부하 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-p102">The average for those roundtrip times is 500 milliseconds (5000 divided by 10). Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion. (Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="1baac-p103">물론, 실제로 통화의 90%에 대한 왕복 시간은 상당히 양호하며 단지 한 번의 불량 통화로 전체 결과가 왜곡되었습니다. 이처럼 평균 왕복 시간만 살펴본다면 아주 잘못된 결과에 도달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-p103">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results. If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="1baac-133">미디어 품질 메트릭 배포 보고서를 사용 하면 라운드트립 시간 등의 지정 된 메트릭의 그래픽 배포를 표시 하 여 틀린 결론으로 인해 발생 하는 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-133">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time).</span></span> <span data-ttu-id="1baac-134">이러한 그래프는 매우 우수한 통화를 9 개 가지 며 매우 불량 통화 한 개가 있음을 명확 하 게 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-134">These graphs can help make it clear that you had nine very good calls and one very bad call.</span></span> <span data-ttu-id="1baac-135">이 경우에도 해당 통화를 자세히 조사 해야 할 수도 있습니다. 그러나 10 개의 통화를 9 개까지 수행 하는 사실은 네트워크를 급격 하 게 변경할 필요가 없다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-135">Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="1baac-136">필터</span><span class="sxs-lookup"><span data-stu-id="1baac-136">Filters</span></span>

<span data-ttu-id="1baac-137">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-137">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="1baac-138">다음 표에서는 미디어 품질 메트릭 분포 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-138">The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="1baac-139">미디어 품질 메트릭 분포 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="1baac-139">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1baac-140">이름</span><span class="sxs-lookup"><span data-stu-id="1baac-140">Name</span></span></th>
<th><span data-ttu-id="1baac-141">설명</span><span class="sxs-lookup"><span data-stu-id="1baac-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1baac-142"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="1baac-142"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1baac-p106">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1baac-145">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1baac-145">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1baac-p107">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1baac-148">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1baac-148">7/7/2012</span></span></p>
<p><span data-ttu-id="1baac-149">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-149">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1baac-150">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1baac-150">7/3/2012</span></span></p>
<p><span data-ttu-id="1baac-151">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-151">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1baac-152"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="1baac-152"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1baac-p108">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1baac-155">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1baac-155">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1baac-p109">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1baac-158">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1baac-158">7/7/2012</span></span></p>
<p><span data-ttu-id="1baac-159">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-159">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1baac-160">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1baac-160">7/3/2012</span></span></p>
<p><span data-ttu-id="1baac-161">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-161">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1baac-162"><strong>X 축 최소값</strong></span><span class="sxs-lookup"><span data-stu-id="1baac-162"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="1baac-163">그래프의 X 축에 표시할 최소값입니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-163">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1baac-164"><strong>X 축 최대값</strong></span><span class="sxs-lookup"><span data-stu-id="1baac-164"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="1baac-165">그래프의 X 축에 표시할 가장 높은 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-165">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1baac-166"><strong>액세스 유형</strong></span><span class="sxs-lookup"><span data-stu-id="1baac-166"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="1baac-p110">통화가 시도되었을 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온되어 있는지를 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1baac-169">모든</span><span class="sxs-lookup"><span data-stu-id="1baac-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="1baac-170">Internal</span><span class="sxs-lookup"><span data-stu-id="1baac-170">Internal</span></span></p></li>
<li><p><span data-ttu-id="1baac-171">외부:</span><span class="sxs-lookup"><span data-stu-id="1baac-171">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1baac-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="1baac-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="1baac-p111">통화가 시도되었을 때 외부 클라이언트가 VPN(가상 사설망) 연결을 사용 중이었는지를 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1baac-175">모든</span><span class="sxs-lookup"><span data-stu-id="1baac-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="1baac-176">VPN</span><span class="sxs-lookup"><span data-stu-id="1baac-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="1baac-177">비 VPN</span><span class="sxs-lookup"><span data-stu-id="1baac-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1baac-178"><strong>네트워크 유형</strong></span><span class="sxs-lookup"><span data-stu-id="1baac-178"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="1baac-p112">통화가 시도되었을 때 클라이언트가 연결된 네트워크의 유형을 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1baac-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1baac-181">모든</span><span class="sxs-lookup"><span data-stu-id="1baac-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="1baac-182">유선</span><span class="sxs-lookup"><span data-stu-id="1baac-182">Wired</span></span></p></li>
<li><p><span data-ttu-id="1baac-183">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="1baac-183">Wireless</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

