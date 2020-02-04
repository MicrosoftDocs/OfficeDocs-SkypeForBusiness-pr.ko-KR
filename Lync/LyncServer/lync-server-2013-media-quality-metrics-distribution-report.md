---
title: 'Lync Server 2013: Media Quality 메트릭스 배포 보고서'
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
ms.openlocfilehash: 085525063d13c60dc1702ebf169fed92707675e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="e5a3f-102">Lync Server 2013의 Media Quality 메트릭스 배포 보고서</span><span class="sxs-lookup"><span data-stu-id="e5a3f-102">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5a3f-103">_**마지막으로 수정한 주제:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="e5a3f-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="e5a3f-104">미디어 품질 메트릭 배포 보고서를 사용 하면 지터 또는 패킷 손실과 같은 경험 치를 품질 메트릭의 분포 값을 보여 주는 그래프를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-104">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span> <span data-ttu-id="e5a3f-105">예를 들어 사용자가 총 10 개의 전화 통화를 하 게 되는 경우 이러한 10 개의 호출은 다음과 같은 왕복 횟수를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-105">For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5a3f-106">통화 번호</span><span class="sxs-lookup"><span data-stu-id="e5a3f-106">Call Number</span></span></th>
<th><span data-ttu-id="e5a3f-107">왕복 시간 (밀리초)</span><span class="sxs-lookup"><span data-stu-id="e5a3f-107">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5a3f-108">1</span><span class="sxs-lookup"><span data-stu-id="e5a3f-108">1</span></span></p></td>
<td><p><span data-ttu-id="e5a3f-109">50</span><span class="sxs-lookup"><span data-stu-id="e5a3f-109">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5a3f-110">2</span><span class="sxs-lookup"><span data-stu-id="e5a3f-110">2</span></span></p></td>
<td><p><span data-ttu-id="e5a3f-111">50</span><span class="sxs-lookup"><span data-stu-id="e5a3f-111">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5a3f-112">3</span><span class="sxs-lookup"><span data-stu-id="e5a3f-112">3</span></span></p></td>
<td><p><span data-ttu-id="e5a3f-113">50</span><span class="sxs-lookup"><span data-stu-id="e5a3f-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5a3f-114">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="e5a3f-114">4</span></span></p></td>
<td><p><span data-ttu-id="e5a3f-115">50</span><span class="sxs-lookup"><span data-stu-id="e5a3f-115">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5a3f-116">5mb</span><span class="sxs-lookup"><span data-stu-id="e5a3f-116">5</span></span></p></td>
<td><p><span data-ttu-id="e5a3f-117">50</span><span class="sxs-lookup"><span data-stu-id="e5a3f-117">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5a3f-118">26</span><span class="sxs-lookup"><span data-stu-id="e5a3f-118">6</span></span></p></td>
<td><p><span data-ttu-id="e5a3f-119">50</span><span class="sxs-lookup"><span data-stu-id="e5a3f-119">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5a3f-120">7</span><span class="sxs-lookup"><span data-stu-id="e5a3f-120">7</span></span></p></td>
<td><p><span data-ttu-id="e5a3f-121">50</span><span class="sxs-lookup"><span data-stu-id="e5a3f-121">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5a3f-122">20cm(8</span><span class="sxs-lookup"><span data-stu-id="e5a3f-122">8</span></span></p></td>
<td><p><span data-ttu-id="e5a3f-123">4550</span><span class="sxs-lookup"><span data-stu-id="e5a3f-123">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5a3f-124">되었는지</span><span class="sxs-lookup"><span data-stu-id="e5a3f-124">9</span></span></p></td>
<td><p><span data-ttu-id="e5a3f-125">50</span><span class="sxs-lookup"><span data-stu-id="e5a3f-125">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5a3f-126">1천만</span><span class="sxs-lookup"><span data-stu-id="e5a3f-126">10</span></span></p></td>
<td><p><span data-ttu-id="e5a3f-127">50</span><span class="sxs-lookup"><span data-stu-id="e5a3f-127">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e5a3f-128">이러한 왕복 시간에 대 한 평균은 500 밀리초 (5000을 10로 나눈 값)입니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-128">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="e5a3f-129">500 밀리초는 매우 큰 왕복 시간입니다. 결과적으로 네트워크 정체에 심각한 문제가 있다고 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-129">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="e5a3f-130">일반적으로 오버 로드 된 네트워크의 결과로 긴 왕복 시간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-130">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="e5a3f-131">물론 실제로는 통화의 90%가 탁월한 왕복 시간을가지고 있습니다. 전체 결과를 나타내는 잘못 된 통화가 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-131">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="e5a3f-132">평균 왕복 시간만 표시 하는 경우 매우 잘못 된 결론으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-132">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="e5a3f-133">미디어 품질 메트릭 배포 보고서를 사용 하면 특정 메트릭의 그래픽 분포 (예: 라운드트립 시간)를 표시 하 여 잘못 된 결론으로 점프할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-133">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time).</span></span> <span data-ttu-id="e5a3f-134">이러한 그래프는 매우 우수한 통화를 10 개, 매우 나쁜 통화를 하는 것을 명확 하 게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-134">These graphs can help make it clear that you had nine very good calls and one very bad call.</span></span> <span data-ttu-id="e5a3f-135">이 경우에도 해당 통화를 자세히 조사 하는 것이 좋습니다. 그러나 10 개의 통화 중 9 개를 사용 하는 것은 최소한이 시점에서 네트워크에 대 한 불필요 한 변경을 할 이유가 없다는 것을 제안 한다는 사실입니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-135">Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="e5a3f-136">필터가</span><span class="sxs-lookup"><span data-stu-id="e5a3f-136">Filters</span></span>

<span data-ttu-id="e5a3f-137">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-137">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="e5a3f-138">다음 표에는 미디어 품질 메트릭 배포 보고서와 함께 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-138">The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="e5a3f-139">미디어 품질 메트릭 배포 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="e5a3f-139">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5a3f-140">이름</span><span class="sxs-lookup"><span data-stu-id="e5a3f-140">Name</span></span></th>
<th><span data-ttu-id="e5a3f-141">설명</span><span class="sxs-lookup"><span data-stu-id="e5a3f-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5a3f-142"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="e5a3f-142"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e5a3f-143">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-143">Start date/time for the time range.</span></span> <span data-ttu-id="e5a3f-144">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-144">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e5a3f-145">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="e5a3f-145">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e5a3f-146">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-146">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="e5a3f-147">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-147">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e5a3f-148">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e5a3f-148">7/7/2012</span></span></p>
<p><span data-ttu-id="e5a3f-149">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="e5a3f-149">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e5a3f-150">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e5a3f-150">7/3/2012</span></span></p>
<p><span data-ttu-id="e5a3f-151">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-151">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5a3f-152"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="e5a3f-152"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e5a3f-153">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-153">End date/time for the time range.</span></span> <span data-ttu-id="e5a3f-154">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-154">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e5a3f-155">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="e5a3f-155">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e5a3f-156">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-156">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="e5a3f-157">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-157">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e5a3f-158">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e5a3f-158">7/7/2012</span></span></p>
<p><span data-ttu-id="e5a3f-159">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="e5a3f-159">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e5a3f-160">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e5a3f-160">7/3/2012</span></span></p>
<p><span data-ttu-id="e5a3f-161">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-161">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5a3f-162"><strong>최소 x 축 기준</strong></span><span class="sxs-lookup"><span data-stu-id="e5a3f-162"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="e5a3f-163">그래프의 X 축에 표시할 최소값입니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-163">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5a3f-164"><strong>최대 x 축</strong></span><span class="sxs-lookup"><span data-stu-id="e5a3f-164"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="e5a3f-165">그래프의 X 축에 표시할 가장 높은 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-165">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5a3f-166"><strong>Access 형식</strong></span><span class="sxs-lookup"><span data-stu-id="e5a3f-166"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="e5a3f-167">전화를 걸 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-167">Indicates whether the client was logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="e5a3f-168">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-168">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e5a3f-169">모든</span><span class="sxs-lookup"><span data-stu-id="e5a3f-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="e5a3f-170">내부용</span><span class="sxs-lookup"><span data-stu-id="e5a3f-170">Internal</span></span></p></li>
<li><p><span data-ttu-id="e5a3f-171">내부</span><span class="sxs-lookup"><span data-stu-id="e5a3f-171">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5a3f-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="e5a3f-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="e5a3f-173">통화를 했을 때 외부 클라이언트가 VPN (가상 사설망) 연결을 사용 중인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-173">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="e5a3f-174">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-174">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e5a3f-175">모든</span><span class="sxs-lookup"><span data-stu-id="e5a3f-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="e5a3f-176">VPN</span><span class="sxs-lookup"><span data-stu-id="e5a3f-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="e5a3f-177">비 VPN</span><span class="sxs-lookup"><span data-stu-id="e5a3f-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5a3f-178"><strong>네트워크 유형</strong></span><span class="sxs-lookup"><span data-stu-id="e5a3f-178"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="e5a3f-179">전화를 걸 때 클라이언트가 연결 된 네트워크의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-179">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="e5a3f-180">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a3f-180">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e5a3f-181">모든</span><span class="sxs-lookup"><span data-stu-id="e5a3f-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="e5a3f-182">유</span><span class="sxs-lookup"><span data-stu-id="e5a3f-182">Wired</span></span></p></li>
<li><p><span data-ttu-id="e5a3f-183">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="e5a3f-183">Wireless</span></span></p></li>
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

