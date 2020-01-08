---
title: 'Lync Server 2013: 위치 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac5ab1d077acb8f96849b4ac44911a4c90786fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="515dd-102">Lync Server 2013의 위치 보고서</span><span class="sxs-lookup"><span data-stu-id="515dd-102">Location Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="515dd-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="515dd-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="515dd-104">위치 보고서는 네트워크 위치 (즉, 네트워크 서브넷) 별로 그룹화 된 통화 품질 메트릭에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-104">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet).</span></span> <span data-ttu-id="515dd-105">사용자에 게 전화를 거는 데 문제가 있는 경우,이 보고서를 통해 해당 문제가 광범위 하 게 표시 되는지 또는 주어진 네트워크 세그먼트에 국한 되어 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-105">If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="515dd-106">위치 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="515dd-106">Accessing the Location Report</span></span>

<span data-ttu-id="515dd-107">위치 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-107">The Location Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="515dd-108">다음 메트릭 중 하나를 클릭 하 여 통화 목록 보고서로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-108">You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="515dd-109">통화 볼륨</span><span class="sxs-lookup"><span data-stu-id="515dd-109">Call volume</span></span>

  - <span data-ttu-id="515dd-110">통화 불량 백분율</span><span class="sxs-lookup"><span data-stu-id="515dd-110">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="515dd-111">필터가</span><span class="sxs-lookup"><span data-stu-id="515dd-111">Filters</span></span>

<span data-ttu-id="515dd-112">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-112">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="515dd-113">예를 들어 위치 보고서를 사용 하 여 호출이 시작 된 위치 또는 무선 또는 유선 연결을 통해 통화가 발생 했는지 여부 등을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-113">For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection.</span></span> <span data-ttu-id="515dd-114">데이터 그룹화 방법을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-114">You can also choose how data should be grouped.</span></span> <span data-ttu-id="515dd-115">이 경우 통화는 시, 일, 주 또는 월로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-115">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="515dd-116">다음 표에는 위치 보고서에 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-116">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="515dd-117">위치 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="515dd-117">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="515dd-118">이름</span><span class="sxs-lookup"><span data-stu-id="515dd-118">Name</span></span></th>
<th><span data-ttu-id="515dd-119">설명</span><span class="sxs-lookup"><span data-stu-id="515dd-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="515dd-120"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-121">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-121">Start date/time for the time range.</span></span> <span data-ttu-id="515dd-122">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-122">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="515dd-123">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="515dd-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="515dd-124">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-124">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="515dd-125">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-125">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="515dd-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="515dd-126">7/7/2012</span></span></p>
<p><span data-ttu-id="515dd-127">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="515dd-127">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="515dd-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="515dd-128">7/3/2012</span></span></p>
<p><span data-ttu-id="515dd-129">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="515dd-130"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-131">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-131">End date/time for the time range.</span></span> <span data-ttu-id="515dd-132">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-132">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="515dd-133">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="515dd-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="515dd-134">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-134">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="515dd-135">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-135">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="515dd-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="515dd-136">7/7/2012</span></span></p>
<p><span data-ttu-id="515dd-137">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="515dd-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="515dd-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="515dd-138">7/3/2012</span></span></p>
<p><span data-ttu-id="515dd-139">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="515dd-140"><strong>발신자 위치</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-140"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-141">통화를 설정한 사용자의 IP 서브넷입니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-141">IP subnet of the user who placed the call.</span></span> <span data-ttu-id="515dd-142"><strong>[모두]</strong> 를 선택 하 여 모든 서브넷을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-142">You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="515dd-143"><strong>호출 수신자 위치</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-143"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-144">통화를 받은 사용자의 IP 서브넷입니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-144">IP subnet of the user who received the call.</span></span> <span data-ttu-id="515dd-145"><strong>[모두]</strong> 를 선택 하 여 모든 서브넷을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-145">You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="515dd-146"><strong>네트워크 유형</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-146"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-147">전화를 걸 때 클라이언트가 연결 된 네트워크의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-147">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="515dd-148">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-148">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="515dd-149">모든</span><span class="sxs-lookup"><span data-stu-id="515dd-149">[All]</span></span></p></li>
<li><p><span data-ttu-id="515dd-150">유</span><span class="sxs-lookup"><span data-stu-id="515dd-150">Wired</span></span></p></li>
<li><p><span data-ttu-id="515dd-151">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="515dd-151">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="515dd-152"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-152"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-153">통화를 했을 때 외부 클라이언트가 VPN (가상 사설망) 연결을 사용 중인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-153">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="515dd-154">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-154">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="515dd-155">모든</span><span class="sxs-lookup"><span data-stu-id="515dd-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="515dd-156">VPN</span><span class="sxs-lookup"><span data-stu-id="515dd-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="515dd-157">비 VPN</span><span class="sxs-lookup"><span data-stu-id="515dd-157">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="515dd-158">매트릭스</span><span class="sxs-lookup"><span data-stu-id="515dd-158">Metrics</span></span>

<span data-ttu-id="515dd-159">다음 표에는 위치 보고서에서 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-159">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="515dd-160">위치 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="515dd-160">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="515dd-161">이름</span><span class="sxs-lookup"><span data-stu-id="515dd-161">Name</span></span></th>
<th><span data-ttu-id="515dd-162">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="515dd-162">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="515dd-163">설명</span><span class="sxs-lookup"><span data-stu-id="515dd-163">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="515dd-164"><strong>발신자 서브넷</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-164"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-165">아니요</span><span class="sxs-lookup"><span data-stu-id="515dd-165">No</span></span></p></td>
<td><p><span data-ttu-id="515dd-166">통화를 설정한 사용자의 IP 서브넷입니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-166">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="515dd-167"><strong>호출 수신자 서브넷</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-167"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-168">아니요</span><span class="sxs-lookup"><span data-stu-id="515dd-168">No</span></span></p></td>
<td><p><span data-ttu-id="515dd-169">통화를 받은 사용자의 IP 서브넷입니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-169">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="515dd-170"><strong>통화 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-170"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-171">예</span><span class="sxs-lookup"><span data-stu-id="515dd-171">Yes</span></span></p></td>
<td><p><span data-ttu-id="515dd-172">총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-172">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="515dd-173"><strong>통화 불량 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-173"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-174">예</span><span class="sxs-lookup"><span data-stu-id="515dd-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="515dd-175">불량 통화로 분류 된 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-175">Percentage of calls classified as poor calls.</span></span> <span data-ttu-id="515dd-176">잘못 된 통화는 측정 된 메트릭 중 적어도 하나가 허용 된 값 (예: 과도 한 지터)을 초과한 모든 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-176">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="515dd-177"><strong>왕복 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-177"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-178">예</span><span class="sxs-lookup"><span data-stu-id="515dd-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="515dd-179">다른 끝점으로 이동 하 고 나 서 다시 사용할 수 있는 RTP (실시간 전송 프로토콜) 패킷에 필요한 평균 양 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-179">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="515dd-180">100 밀리초 이하의 왕복 시간은 허용 되는 품질로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-180">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="515dd-181">많은 라운드트립 값은 국제 통화 라우팅, 라우팅 잘못 구성 또는 오버 로드 된 미디어 서버에 의해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-181">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server.</span></span> <span data-ttu-id="515dd-182">왕복 시간이 높으면 양방향 실시간 음성 대화에서 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-182">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="515dd-183"><strong>성능 저하 (SPECIALIST)</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-184">예</span><span class="sxs-lookup"><span data-stu-id="515dd-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="515dd-185">통화 중에 발생 한 평균 SPECIALIST (의미 있는 평가 점수) 감소 금액입니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-185">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="515dd-186">성능 저하 값의 범위는 0.0 ~ 5.0의 최대값까지입니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-186">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="515dd-187">0.5 이하의 값은 허용 되는 저하를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-187">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="515dd-188">지금까지 평균 옵션 점수는 사용자가 1 ~ 5의 배율로 통화 품질을 평가할 수 있도록 하 여 계산 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-188">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="515dd-189">Lync server에서 Lync Server는 사용자가 전화를 평가한 방법을 예측 하는 알고리즘 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-189">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="515dd-190">높은 성능 저하 값은 정체, 대역폭 부족, 무선 정체 또는 간섭 또는 오버 로드 된 미디어 서버 또는 끝점으로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-190">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="515dd-191">품질이 높으면 오디오가 왜곡 되거나 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-191">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="515dd-192"><strong>패킷 손실</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-192"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-193">예</span><span class="sxs-lookup"><span data-stu-id="515dd-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="515dd-194">RTP 패킷 손실의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-194">Average rate of RTP packet loss.</span></span> <span data-ttu-id="515dd-195">(패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 높은 손실률은 일반적으로 혼잡, 대역폭 부족, 무선 정체 또는 간섭 또는 오버 로드 된 미디어 서버 중에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-195">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="515dd-196">패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-196">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="515dd-197"><strong>지터</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-197"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-198">예</span><span class="sxs-lookup"><span data-stu-id="515dd-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="515dd-199">RTP 패킷 도착 간에 감지 된 평균 지터.</span><span class="sxs-lookup"><span data-stu-id="515dd-199">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="515dd-200">(지터는 통화의 &quot;shakiness&quot; 을 측정 하는 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-200">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="515dd-201"><strong>Healer 숨겨진 비율</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-201"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-202">예</span><span class="sxs-lookup"><span data-stu-id="515dd-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="515dd-203">총 샘플 수에 대 한 총 숨겨진 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-203">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="515dd-204">(숨겨진 오디오 샘플은 일반적으로 손실 된 네트워크 패킷으로 인해 발생 하는 갑작스런 전환을 매끄럽게 하는 데 사용 되는 기술입니다.) 값이 높으면 패킷 손실률 또는 지터로 인해 적용 되는 손실 concealment의 상당 부분이 왜곡 되거나 손실 되는 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-204">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="515dd-205"><strong>Healer 늘이기 비율</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-205"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-206">예</span><span class="sxs-lookup"><span data-stu-id="515dd-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="515dd-207">총 샘플 수에 대 한 총 스트레치 된 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-207">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="515dd-208">(늘인 오디오는 손실 된 네트워크 패킷이 감지 될 때 통화 품질을 유지 하기 위해 확장 되어 있는 오디오입니다.) 값이 높으면 지터로 인해 발생 하는 샘플 스트레치의 상당 수준을 나타내고, 오디오는 로보틱 또는 왜곡 될 때 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-208">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="515dd-209"><strong>Healer 압축 비율</strong></span><span class="sxs-lookup"><span data-stu-id="515dd-209"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="515dd-210">예</span><span class="sxs-lookup"><span data-stu-id="515dd-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="515dd-211">총 샘플 수에 대 한 압축 된 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-211">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="515dd-212">(압축 오디오는 손실 된 네트워크 패킷이 감지 되었을 때 통화 품질을 유지 하기 위해 압축 된 오디오입니다.) 값이 높으면 지터로 인해 발생 하는 샘플 압축의 상당 부분이 표시 되 고 오디오의 가속 또는 왜곡이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="515dd-212">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

