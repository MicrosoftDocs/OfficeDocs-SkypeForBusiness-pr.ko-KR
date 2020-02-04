---
title: 'Lync Server 2013: 피어 투 피어 음성 및 비디오 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68cddb8296a94ff5d5b084895024d7379a42022c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="4c5a8-102">Lync Server 2013의 피어 투 피어 음성 및 비디오 보고서</span><span class="sxs-lookup"><span data-stu-id="4c5a8-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c5a8-103">_**마지막으로 수정한 주제:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="4c5a8-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="4c5a8-104">피어 투 피어 음성 및 비디오 보고서는 지정 된 기간의 음성 및 영상 통화 분포에 대 한 자세한 정보 (예: 시간당 통화 또는 하루에 한 번)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-104">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day).</span></span> <span data-ttu-id="4c5a8-105">또한 보고서는 모든 음성 및 영상 통화를 보거나 성공 또는 실패 한 통화를 보는 옵션도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-105">The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls.</span></span> <span data-ttu-id="4c5a8-106">이 보고서에는 다음과 같은 그룹으로 구분 된 통화 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-106">The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="4c5a8-107">풀 당 통화</span><span class="sxs-lookup"><span data-stu-id="4c5a8-107">Calls per pool</span></span>

  - <span data-ttu-id="4c5a8-108">통화 유형별 통화 (예: Lync to Lync 통화 및 PSTN 네트워크의 사용자에 대 한 Lync 통화)</span><span class="sxs-lookup"><span data-stu-id="4c5a8-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="4c5a8-109">액세스 유형별 통화 (내부 네트워크에 로그온 한 사용자와 외부 네트워크에 로그온 한 사용자)</span><span class="sxs-lookup"><span data-stu-id="4c5a8-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="4c5a8-110">중재 서버 당 통화</span><span class="sxs-lookup"><span data-stu-id="4c5a8-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="4c5a8-111">피어 투 피어 음성 및 비디오 보고서에 액세스 하려면</span><span class="sxs-lookup"><span data-stu-id="4c5a8-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="4c5a8-112">피어 투 피어 음성 및 비디오 보고서에 액세스 하려면 동위 투 피어 활동 요약 보고서를 열고 다음 메트릭 중 하나를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="4c5a8-113">총 피어 투 피어 오디오 세션</span><span class="sxs-lookup"><span data-stu-id="4c5a8-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="4c5a8-114">총 피어 투 피어 오디오 시간</span><span class="sxs-lookup"><span data-stu-id="4c5a8-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="4c5a8-115">총 피어 투 피어 비디오 세션</span><span class="sxs-lookup"><span data-stu-id="4c5a8-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="4c5a8-116">총 피어 투 피어 비디오 통화</span><span class="sxs-lookup"><span data-stu-id="4c5a8-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="4c5a8-117">피어 투 피어 음성 및 비디오 보고서의 용도를 최대한 활용 하려면</span><span class="sxs-lookup"><span data-stu-id="4c5a8-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="4c5a8-118">피어 투 피어 음성 및 비디오 보고서를 필터링 하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-118">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report.</span></span> <span data-ttu-id="4c5a8-119">그러나 이러한 필터링 옵션은 기본적으로 보기에서 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-119">However, those filtering options are hidden from view by default.</span></span> <span data-ttu-id="4c5a8-120">사용할 수 있는 필터링 옵션을 보려면 보고서 창의 오른쪽 위 모서리에 있는 **매개 변수 표시/숨기기** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-120">To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4c5a8-121">필터가</span><span class="sxs-lookup"><span data-stu-id="4c5a8-121">Filters</span></span>

<span data-ttu-id="4c5a8-122">필터를 통해 보다 세부적으로 대상 지정 된 데이터 집합을 반환 하거나 다양 한 방법으로 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-122">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways.</span></span> <span data-ttu-id="4c5a8-123">다음 표에는 피어 투 피어 음성 및 비디오 보고서에 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-123">The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="4c5a8-124">피어 투 피어 음성 및 비디오 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="4c5a8-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c5a8-125">이름</span><span class="sxs-lookup"><span data-stu-id="4c5a8-125">Name</span></span></th>
<th><span data-ttu-id="4c5a8-126">설명</span><span class="sxs-lookup"><span data-stu-id="4c5a8-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c5a8-127"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-128">시간 범위에 대 한 시작 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-128">Start date and time for the time range.</span></span> <span data-ttu-id="4c5a8-129">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-129">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4c5a8-130">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="4c5a8-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4c5a8-131">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-131">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="4c5a8-132">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-132">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4c5a8-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4c5a8-133">7/7/2012</span></span></p>
<p><span data-ttu-id="4c5a8-134">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="4c5a8-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4c5a8-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4c5a8-135">7/3/2012</span></span></p>
<p><span data-ttu-id="4c5a8-136">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5a8-137"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-138">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-138">End date/time for the time range.</span></span> <span data-ttu-id="4c5a8-139">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-139">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4c5a8-140">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="4c5a8-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4c5a8-141">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-141">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="4c5a8-142">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-142">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4c5a8-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4c5a8-143">7/7/2012</span></span></p>
<p><span data-ttu-id="4c5a8-144">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="4c5a8-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4c5a8-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4c5a8-145">7/3/2012</span></span></p>
<p><span data-ttu-id="4c5a8-146">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5a8-147"><strong>간격만</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-148">시간 간격.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-148">Time interval.</span></span> <span data-ttu-id="4c5a8-149">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-149">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c5a8-150">매시간 (최대 25 시간 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="4c5a8-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4c5a8-151">매일 (최대 31 일이 표시 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="4c5a8-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4c5a8-152">주간 (최대 12 주를 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="4c5a8-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4c5a8-153">월간 (최대 12 개월을 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="4c5a8-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="4c5a8-154">시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-154">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="4c5a8-155">예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-155">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5a8-156"><strong>미디어 유형</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-157">세션에 사용 되는 미디어 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-157">Indicates the type of media used in the session.</span></span> <span data-ttu-id="4c5a8-158">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-158">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c5a8-159">양방향</span><span class="sxs-lookup"><span data-stu-id="4c5a8-159">Both</span></span></p></li>
<li><p><span data-ttu-id="4c5a8-160">오디오</span><span class="sxs-lookup"><span data-stu-id="4c5a8-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="4c5a8-161">비디오만</span><span class="sxs-lookup"><span data-stu-id="4c5a8-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5a8-162"><strong>통화 처리</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-163">세션의 성공 또는 실패를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-163">Indicates the success or failure of the session.</span></span> <span data-ttu-id="4c5a8-164">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-164">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c5a8-165">모든</span><span class="sxs-lookup"><span data-stu-id="4c5a8-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="4c5a8-166">성공 통화</span><span class="sxs-lookup"><span data-stu-id="4c5a8-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="4c5a8-167">통화 실패</span><span class="sxs-lookup"><span data-stu-id="4c5a8-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5a8-168"><strong>보고서 기준</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-169">보고서에 사용할 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-169">Indicates the values to be used in the report.</span></span> <span data-ttu-id="4c5a8-170">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-170">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c5a8-171">세션 수</span><span class="sxs-lookup"><span data-stu-id="4c5a8-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="4c5a8-172">통화 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="4c5a8-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="4c5a8-173">피어 투 피어 음성 및 풀 별 비디오 활동에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="4c5a8-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="4c5a8-174">다음 표에는 각 풀에 대 한 피어 투 피어 음성 및 비디오 보고서에서 제공 하는 정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="4c5a8-175">피어 투 피어 음성 및 풀 별 비디오 활동에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="4c5a8-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c5a8-176">이름</span><span class="sxs-lookup"><span data-stu-id="4c5a8-176">Name</span></span></th>
<th><span data-ttu-id="4c5a8-177">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="4c5a8-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4c5a8-178">설명</span><span class="sxs-lookup"><span data-stu-id="4c5a8-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c5a8-179"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-180">아니요</span><span class="sxs-lookup"><span data-stu-id="4c5a8-180">No</span></span></p></td>
<td><p><span data-ttu-id="4c5a8-181">통화에 사용 되는 등록자 풀 또는 Edge 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5a8-182"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-183">아니요</span><span class="sxs-lookup"><span data-stu-id="4c5a8-183">No</span></span></p></td>
<td><p><span data-ttu-id="4c5a8-184">통화가 발생 한 날짜 및 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5a8-185"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-186">아니요</span><span class="sxs-lookup"><span data-stu-id="4c5a8-186">No</span></span></p></td>
<td><p><span data-ttu-id="4c5a8-187">총 세션 수 또는 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="4c5a8-188">피어 투 피어 음성 및 통화 유형별 비디오 활동에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="4c5a8-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="4c5a8-189">다음 표에서는 각 통화 유형에 대 한 피어 투 피어 음성 및 비디오 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="4c5a8-190">피어 투 피어 음성 및 통화 유형별 비디오 활동에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="4c5a8-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c5a8-191">이름</span><span class="sxs-lookup"><span data-stu-id="4c5a8-191">Name</span></span></th>
<th><span data-ttu-id="4c5a8-192">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="4c5a8-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4c5a8-193">설명</span><span class="sxs-lookup"><span data-stu-id="4c5a8-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c5a8-194"><strong>통화 종류</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-195">아니요</span><span class="sxs-lookup"><span data-stu-id="4c5a8-195">No</span></span></p></td>
<td><p><span data-ttu-id="4c5a8-196">발생 한 통화 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-196">Indicates the type of call that was made.</span></span> <span data-ttu-id="4c5a8-197">값은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-197">Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c5a8-198">UC-UC</span><span class="sxs-lookup"><span data-stu-id="4c5a8-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="4c5a8-199">UC 대 PSTN</span><span class="sxs-lookup"><span data-stu-id="4c5a8-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="4c5a8-200">PSTN에서 UC로</span><span class="sxs-lookup"><span data-stu-id="4c5a8-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="4c5a8-201">PSTN에서 PSTN으로</span><span class="sxs-lookup"><span data-stu-id="4c5a8-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5a8-202"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-203">아니요</span><span class="sxs-lookup"><span data-stu-id="4c5a8-203">No</span></span></p></td>
<td><p><span data-ttu-id="4c5a8-204">통화가 발생 한 날짜 및 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5a8-205"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-206">아니요</span><span class="sxs-lookup"><span data-stu-id="4c5a8-206">No</span></span></p></td>
<td><p><span data-ttu-id="4c5a8-207">총 세션 수 또는 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="4c5a8-208">피어 투 피어 음성 및 access 유형별 비디오 활동에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="4c5a8-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="4c5a8-209">다음 표에는 각 네트워크 액세스 형식에 대 한 피어 투 피어 음성 및 비디오 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="4c5a8-210">피어 투 피어 음성 및 access 유형별 비디오 활동에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="4c5a8-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c5a8-211">이름</span><span class="sxs-lookup"><span data-stu-id="4c5a8-211">Name</span></span></th>
<th><span data-ttu-id="4c5a8-212">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="4c5a8-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4c5a8-213">설명</span><span class="sxs-lookup"><span data-stu-id="4c5a8-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c5a8-214"><strong>활동 유형</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-215">아니요</span><span class="sxs-lookup"><span data-stu-id="4c5a8-215">No</span></span></p></td>
<td><p><span data-ttu-id="4c5a8-216">전화를 걸 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-216">Indicates whether the clients were logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="4c5a8-217">값은 일반적으로 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-217">Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4c5a8-218">내부용</span><span class="sxs-lookup"><span data-stu-id="4c5a8-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="4c5a8-219">내부</span><span class="sxs-lookup"><span data-stu-id="4c5a8-219">External</span></span></p></li>
<li><p><span data-ttu-id="4c5a8-220">섞여</span><span class="sxs-lookup"><span data-stu-id="4c5a8-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5a8-221"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-222">아니요</span><span class="sxs-lookup"><span data-stu-id="4c5a8-222">No</span></span></p></td>
<td><p><span data-ttu-id="4c5a8-223">통화가 발생 한 날짜 및 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5a8-224"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-225">아니요</span><span class="sxs-lookup"><span data-stu-id="4c5a8-225">No</span></span></p></td>
<td><p><span data-ttu-id="4c5a8-226">총 세션 수 또는 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="4c5a8-227">중재 서버용 피어 투 피어 음성 및 비디오 활동에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="4c5a8-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="4c5a8-228">다음 표에는 각 중재 서버의 피어 투 피어 음성 및 비디오 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="4c5a8-229">중재 서버용 피어 투 피어 음성 및 비디오 활동에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="4c5a8-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c5a8-230">이름</span><span class="sxs-lookup"><span data-stu-id="4c5a8-230">Name</span></span></th>
<th><span data-ttu-id="4c5a8-231">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="4c5a8-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4c5a8-232">설명</span><span class="sxs-lookup"><span data-stu-id="4c5a8-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c5a8-233"><strong>중재 서버</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-234">아니요</span><span class="sxs-lookup"><span data-stu-id="4c5a8-234">No</span></span></p></td>
<td><p><span data-ttu-id="4c5a8-235">중재 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c5a8-236"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-237">아니요</span><span class="sxs-lookup"><span data-stu-id="4c5a8-237">No</span></span></p></td>
<td><p><span data-ttu-id="4c5a8-238">통화가 발생 한 날짜 및 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c5a8-239"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="4c5a8-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="4c5a8-240">아니요</span><span class="sxs-lookup"><span data-stu-id="4c5a8-240">No</span></span></p></td>
<td><p><span data-ttu-id="4c5a8-241">총 세션 수 또는 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5a8-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

