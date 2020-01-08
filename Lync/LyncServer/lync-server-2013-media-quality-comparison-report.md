---
title: 'Lync Server 2013: 미디어 품질 비교 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6697e02d7b821ebd3dc3cabc3a95c8d00960a08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="08eae-102">Lync Server 2013의 미디어 품질 비교 보고서</span><span class="sxs-lookup"><span data-stu-id="08eae-102">Media Quality Comparison Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08eae-103">_**마지막으로 수정한 주제:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="08eae-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="08eae-104">미디어 품질 비교 보고서를 사용 하면 다양 한 종류의 오디오 통화 (예: 무선 네트워크 또는 유선 연결을 통해 생성 된 통화)에 대 한 통화 품질 값을 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-104">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="08eae-105">미디어 품질 비교 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="08eae-105">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="08eae-106">미디어 품질 비교 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-106">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="08eae-107">필터가</span><span class="sxs-lookup"><span data-stu-id="08eae-107">Filters</span></span>

<span data-ttu-id="08eae-108">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="08eae-109">다음 표에는 미디어 품질 비교 보고서에 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-109">The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="08eae-110">미디어 품질 비교 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="08eae-110">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08eae-111">이름</span><span class="sxs-lookup"><span data-stu-id="08eae-111">Name</span></span></th>
<th><span data-ttu-id="08eae-112">설명</span><span class="sxs-lookup"><span data-stu-id="08eae-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08eae-113"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="08eae-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="08eae-114">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-114">Start date/time for the time range.</span></span> <span data-ttu-id="08eae-115">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-115">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="08eae-116">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="08eae-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="08eae-117">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-117">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="08eae-118">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-118">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="08eae-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="08eae-119">7/7/2012</span></span></p>
<p><span data-ttu-id="08eae-120">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="08eae-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="08eae-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="08eae-121">7/3/2012</span></span></p>
<p><span data-ttu-id="08eae-122">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08eae-123"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="08eae-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="08eae-124">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-124">End date/time for the time range.</span></span> <span data-ttu-id="08eae-125">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-125">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="08eae-126">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="08eae-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="08eae-127">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-127">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="08eae-128">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-128">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="08eae-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="08eae-129">7/7/2012</span></span></p>
<p><span data-ttu-id="08eae-130">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="08eae-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="08eae-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="08eae-131">7/3/2012</span></span></p>
<p><span data-ttu-id="08eae-132">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08eae-133"><strong>전화가</strong></span><span class="sxs-lookup"><span data-stu-id="08eae-133"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="08eae-134">주 비교 항목으로 사용할 통화 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-134">Type of call to be used as the main comparison item.</span></span> <span data-ttu-id="08eae-135">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-135">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="08eae-136">모든</span><span class="sxs-lookup"><span data-stu-id="08eae-136">[All]</span></span></p></li>
<li><p><span data-ttu-id="08eae-137">내부</span><span class="sxs-lookup"><span data-stu-id="08eae-137">External</span></span></p></li>
<li><p><span data-ttu-id="08eae-138">내부용</span><span class="sxs-lookup"><span data-stu-id="08eae-138">Internal</span></span></p></li>
<li><p><span data-ttu-id="08eae-139">VPN</span><span class="sxs-lookup"><span data-stu-id="08eae-139">VPN</span></span></p></li>
<li><p><span data-ttu-id="08eae-140">비 VPN</span><span class="sxs-lookup"><span data-stu-id="08eae-140">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="08eae-141">유</span><span class="sxs-lookup"><span data-stu-id="08eae-141">Wired</span></span></p></li>
<li><p><span data-ttu-id="08eae-142">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="08eae-142">Wireless</span></span></p></li>
<li><p><span data-ttu-id="08eae-143">외장 및 유선</span><span class="sxs-lookup"><span data-stu-id="08eae-143">External and wired</span></span></p></li>
<li><p><span data-ttu-id="08eae-144">외부 및 무선</span><span class="sxs-lookup"><span data-stu-id="08eae-144">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="08eae-145">외부 및 VPN</span><span class="sxs-lookup"><span data-stu-id="08eae-145">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="08eae-146">외부 및 비 VPN</span><span class="sxs-lookup"><span data-stu-id="08eae-146">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="08eae-147">내부 및 유선</span><span class="sxs-lookup"><span data-stu-id="08eae-147">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="08eae-148">내부 및 무선</span><span class="sxs-lookup"><span data-stu-id="08eae-148">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08eae-149"><strong>통화와 비교</strong></span><span class="sxs-lookup"><span data-stu-id="08eae-149"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="08eae-150">보조 비교 항목으로 사용할 통화 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-150">Type of call to be used as the secondary comparison item.</span></span> <span data-ttu-id="08eae-151">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-151">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="08eae-152">모든</span><span class="sxs-lookup"><span data-stu-id="08eae-152">[All]</span></span></p></li>
<li><p><span data-ttu-id="08eae-153">내부</span><span class="sxs-lookup"><span data-stu-id="08eae-153">External</span></span></p></li>
<li><p><span data-ttu-id="08eae-154">내부용</span><span class="sxs-lookup"><span data-stu-id="08eae-154">Internal</span></span></p></li>
<li><p><span data-ttu-id="08eae-155">VPN</span><span class="sxs-lookup"><span data-stu-id="08eae-155">VPN</span></span></p></li>
<li><p><span data-ttu-id="08eae-156">비 VPN</span><span class="sxs-lookup"><span data-stu-id="08eae-156">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="08eae-157">유</span><span class="sxs-lookup"><span data-stu-id="08eae-157">Wired</span></span></p></li>
<li><p><span data-ttu-id="08eae-158">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="08eae-158">Wireless</span></span></p></li>
<li><p><span data-ttu-id="08eae-159">외장 및 유선</span><span class="sxs-lookup"><span data-stu-id="08eae-159">External and wired</span></span></p></li>
<li><p><span data-ttu-id="08eae-160">외부 및 무선</span><span class="sxs-lookup"><span data-stu-id="08eae-160">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="08eae-161">외부 및 VPN</span><span class="sxs-lookup"><span data-stu-id="08eae-161">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="08eae-162">외부 및 비 VPN</span><span class="sxs-lookup"><span data-stu-id="08eae-162">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="08eae-163">내부 및 유선</span><span class="sxs-lookup"><span data-stu-id="08eae-163">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="08eae-164">내부 및 무선</span><span class="sxs-lookup"><span data-stu-id="08eae-164">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08eae-165"><strong>간격만</strong></span><span class="sxs-lookup"><span data-stu-id="08eae-165"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="08eae-166">시간 간격.</span><span class="sxs-lookup"><span data-stu-id="08eae-166">Time interval.</span></span> <span data-ttu-id="08eae-167">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-167">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="08eae-168">매시간 (최대 25 시간 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="08eae-168">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="08eae-169">매일 (최대 31 일이 표시 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="08eae-169">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="08eae-170">주간 (최대 12 주를 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="08eae-170">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="08eae-171">시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-171">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="08eae-172">예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-172">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="08eae-173">매트릭스</span><span class="sxs-lookup"><span data-stu-id="08eae-173">Metrics</span></span>

<span data-ttu-id="08eae-174">다음 표에는 미디어 품질 비교 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-174">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="08eae-175">미디어 품질 비교 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="08eae-175">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08eae-176">이름</span><span class="sxs-lookup"><span data-stu-id="08eae-176">Name</span></span></th>
<th><span data-ttu-id="08eae-177">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="08eae-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="08eae-178">설명</span><span class="sxs-lookup"><span data-stu-id="08eae-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08eae-179"><strong>통화 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="08eae-179"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="08eae-180">아니요</span><span class="sxs-lookup"><span data-stu-id="08eae-180">No</span></span></p></td>
<td><p><span data-ttu-id="08eae-181">총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-181">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08eae-182"><strong>성능 저하 (SPECIALIST)</strong></span><span class="sxs-lookup"><span data-stu-id="08eae-182"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="08eae-183">아니요</span><span class="sxs-lookup"><span data-stu-id="08eae-183">No</span></span></p></td>
<td><p><span data-ttu-id="08eae-184">통화 중에 발생 한 평균 SPECIALIST (평균 의견 성과)의 감소 금액입니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-184">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="08eae-185">성능 저하 값의 범위는 0.0 ~ 5.0 ~ 높음이 하입니다. 0.5 이하의 값은 허용 되는 저하를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-185">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="08eae-186">지금까지 사용자가 1 ~ 5의 배율로 통화 품질을 평가할 수 있도록 하 여 평균 성적 점수가 계산 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-186">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="08eae-187">Lync Server는 사용자가 통화를 평가 하는 방법을 예측 하는 알고리즘 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-187">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="08eae-188">높은 성능 저하 값은 정체로 인해 발생할 수 있습니다. 대역폭 부족, 무선 혼잡 또는 간섭 또는 오버 로드 된 미디어 서버 또는 끝점.</span><span class="sxs-lookup"><span data-stu-id="08eae-188">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="08eae-189">품질이 높으면 오디오가 왜곡 되거나 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-189">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08eae-190"><strong>통화 불량 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="08eae-190"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="08eae-191">아니요</span><span class="sxs-lookup"><span data-stu-id="08eae-191">No</span></span></p></td>
<td><p><span data-ttu-id="08eae-192">불량으로 분류 된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-192">The total number of calls classified as poor.</span></span> <span data-ttu-id="08eae-193">잘못 된 통화는 측정 된 메트릭 중 적어도 하나가 허용 된 값 (예: 과도 한 지터)을 초과한 모든 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-193">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08eae-194"><strong>왕복 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="08eae-194"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="08eae-195">아니요</span><span class="sxs-lookup"><span data-stu-id="08eae-195">No</span></span></p></td>
<td><p><span data-ttu-id="08eae-196">실시간 전송 프로토콜 패킷이 다른 끝점으로 이동한 다음 다시 이동 하는 데 필요한 평균 시간 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-196">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="08eae-197">200 밀리초 이하의 왕복 시간은 허용 되는 품질로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-197">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="08eae-198">높은 라운드트립 값은 국제 통화 라우팅으로 인해 발생할 수 있습니다. 라우팅 구성이 잘못 되었습니다. 또는 오버 로드 된 미디어 서버.</span><span class="sxs-lookup"><span data-stu-id="08eae-198">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="08eae-199">왕복 시간이 높으면 양방향 실시간 음성 대화에서 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-199">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08eae-200"><strong>패킷 손실</strong></span><span class="sxs-lookup"><span data-stu-id="08eae-200"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="08eae-201">아니요</span><span class="sxs-lookup"><span data-stu-id="08eae-201">No</span></span></p></td>
<td><p><span data-ttu-id="08eae-202">RTP (실시간 전송 프로토콜) 패킷 손실의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-202">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="08eae-203">(패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 일반적으로 정체 때문에 손실률이 높습니다. 대역폭 부족, 무선 정체 또는 간섭. 또는 오버 로드 된 미디어 서버.</span><span class="sxs-lookup"><span data-stu-id="08eae-203">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="08eae-204">패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-204">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08eae-205"><strong>지터 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="08eae-205"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="08eae-206">아니요</span><span class="sxs-lookup"><span data-stu-id="08eae-206">No</span></span></p></td>
<td><p><span data-ttu-id="08eae-207">RTP 패킷 도착 간에 감지 된 평균 지터.</span><span class="sxs-lookup"><span data-stu-id="08eae-207">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="08eae-208">(지터는 통화의 &quot;shakiness&quot; 을 측정 하는 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-208">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08eae-209"><strong>Healer 숨겨진 비율</strong></span><span class="sxs-lookup"><span data-stu-id="08eae-209"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="08eae-210">아니요</span><span class="sxs-lookup"><span data-stu-id="08eae-210">No</span></span></p></td>
<td><p><span data-ttu-id="08eae-211">총 샘플 수에 대 한 총 숨겨진 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-211">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="08eae-212">(숨겨진 오디오 샘플은 일반적으로 손실 된 네트워크 패킷으로 인해 발생 하는 갑작스런 전환을 매끄럽게 하는 데 사용 되는 기술입니다.) 값이 높으면 패킷 손실률 또는 지터로 인해 적용 되는 손실 concealment의 상당 부분이 왜곡 되거나 손실 되는 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-212">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08eae-213"><strong>Healer 늘이기 비율</strong></span><span class="sxs-lookup"><span data-stu-id="08eae-213"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="08eae-214">아니요</span><span class="sxs-lookup"><span data-stu-id="08eae-214">No</span></span></p></td>
<td><p><span data-ttu-id="08eae-215">총 샘플 수에 대 한 총 스트레치 된 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-215">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="08eae-216">(늘인 오디오는 손실 된 네트워크 패킷이 감지 될 때 통화 품질을 유지 하기 위해 확장 되어 있는 오디오입니다.) 값이 높으면 지터로 인해 발생 하는 샘플 스트레치의 상당 수준을 나타내고, 오디오는 로보틱 또는 왜곡 될 때 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-216">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08eae-217"><strong>Healer 압축 비율</strong></span><span class="sxs-lookup"><span data-stu-id="08eae-217"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="08eae-218">아니요</span><span class="sxs-lookup"><span data-stu-id="08eae-218">No</span></span></p></td>
<td><p><span data-ttu-id="08eae-219">총 샘플 수에 대 한 압축 된 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-219">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="08eae-220">(압축 오디오는 손실 된 네트워크 패킷이 감지 되었을 때 통화 품질을 유지 하기 위해 압축 된 오디오입니다.) 값이 높으면 지터로 인해 발생 하는 샘플 압축의 상당 부분이 표시 되 고 오디오의 가속 또는 왜곡이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="08eae-220">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

