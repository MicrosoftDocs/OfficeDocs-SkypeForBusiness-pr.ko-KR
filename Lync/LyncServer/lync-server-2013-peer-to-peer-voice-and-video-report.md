---
title: 'Lync Server 2013: 피어-투-피어 음성 및 비디오 보고서'
description: 'Lync Server 2013: 피어 투 피어 음성 및 비디오 보고서'
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
ms.openlocfilehash: 43041926b3d6b57508b6ee4c53ca9cb055bcb348
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557274"
---
# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="d4130-103">Lync Server 2013의 피어 투 피어 음성 및 비디오 보고서</span><span class="sxs-lookup"><span data-stu-id="d4130-103">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4130-104">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="d4130-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="d4130-p101">피어 투 피어 음성 및 비디오 보고서는 지정된 시간 동안의 음성 및 비디오 통화 배포 상황에 대한 자세한 정보(예를 들면, 시간당 통화 수 또는 일별 통화 수)를 제공합니다. 이 보고서는 발생된 모든 음성 및 비디오 통화를 보거나 성공 또는 실패한 통화만 볼 수 있는 옵션도 제공합니다. 이 보고서에는 다음 그룹으로 세분되는 통화 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-p101">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day). The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls. The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="d4130-108">풀별 통화 수</span><span class="sxs-lookup"><span data-stu-id="d4130-108">Calls per pool</span></span>

  - <span data-ttu-id="d4130-109">통화 유형별 통화 (예: Lync to Lync call 및 PSTN 네트워크의 사용자에 대 한 Lync 호출)</span><span class="sxs-lookup"><span data-stu-id="d4130-109">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="d4130-110">액세스 유형별 통화 수(내부 네트워크에 로그온한 사용자와 외부 네트워크에 로그온한 사용자)</span><span class="sxs-lookup"><span data-stu-id="d4130-110">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="d4130-111">중재 서버당 통화 수</span><span class="sxs-lookup"><span data-stu-id="d4130-111">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="d4130-112">피어 투 피어 음성 및 비디오 보고서에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="d4130-112">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="d4130-113">피어 투 피어 활동 요약 보고서를 열고 다음 메트릭 중 하나를 클릭해야 피어 투 피어 음성 및 비디오 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-113">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="d4130-114">총 피어 투 피어 오디오 세션</span><span class="sxs-lookup"><span data-stu-id="d4130-114">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="d4130-115">총 피어 투 피어 오디오 시간(분)</span><span class="sxs-lookup"><span data-stu-id="d4130-115">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="d4130-116">총 피어 투 피어 비디오 세션</span><span class="sxs-lookup"><span data-stu-id="d4130-116">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="d4130-117">총 피어 투 피어 비디오 시간(분)</span><span class="sxs-lookup"><span data-stu-id="d4130-117">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="d4130-118">피어 투 피어 음성 및 비디오 보고서를 최대한 활용하려면</span><span class="sxs-lookup"><span data-stu-id="d4130-118">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="d4130-p102">여러 방식으로 피어 투 피어 음성 및 비디오 보고서를 필터링할 수 있습니다. 하지만 이러한 필터링 옵션은 기본적으로 보기에서 숨겨져 있습니다. 사용할 수 있는 필터링 옵션을 보려면 보고서 창의 오른쪽 위에 있는 **매개 변수 표시/숨기기** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-p102">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report. However, those filtering options are hidden from view by default. To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d4130-122">필터</span><span class="sxs-lookup"><span data-stu-id="d4130-122">Filters</span></span>

<span data-ttu-id="d4130-p103">필터를 사용하면 여러 방식으로 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에서는 피어 투 피어 음성 및 비디오 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-p103">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways. The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="d4130-125">피어 투 피어 음성 및 비디오 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="d4130-125">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4130-126">이름</span><span class="sxs-lookup"><span data-stu-id="d4130-126">Name</span></span></th>
<th><span data-ttu-id="d4130-127">설명</span><span class="sxs-lookup"><span data-stu-id="d4130-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4130-128"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-p104">시간 범위의 시작 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜와 시간을 모두 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="d4130-131">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d4130-131">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d4130-p105">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d4130-134">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d4130-134">7/7/2012</span></span></p>
<p><span data-ttu-id="d4130-135">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d4130-136">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d4130-136">7/3/2012</span></span></p>
<p><span data-ttu-id="d4130-137">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4130-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-p106">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="d4130-141">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d4130-141">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d4130-p107">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d4130-144">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d4130-144">7/7/2012</span></span></p>
<p><span data-ttu-id="d4130-145">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d4130-146">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d4130-146">7/3/2012</span></span></p>
<p><span data-ttu-id="d4130-147">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4130-148"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-148"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-p108">시간 간격입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d4130-151">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="d4130-151">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d4130-152">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="d4130-152">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d4130-153">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="d4130-153">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d4130-154">월별(최대 12개월 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="d4130-154">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="d4130-p109">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4130-157"><strong>미디어 유형</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-157"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-p110">세션에 사용된 미디어 유형을 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-p110">Indicates the type of media used in the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d4130-160">모두</span><span class="sxs-lookup"><span data-stu-id="d4130-160">Both</span></span></p></li>
<li><p><span data-ttu-id="d4130-161">오디오만</span><span class="sxs-lookup"><span data-stu-id="d4130-161">Audio</span></span></p></li>
<li><p><span data-ttu-id="d4130-162">비디오</span><span class="sxs-lookup"><span data-stu-id="d4130-162">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4130-163"><strong>통화 처리</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-163"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-p111">세션의 성공 또는 실패를 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-p111">Indicates the success or failure of the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d4130-166">모든</span><span class="sxs-lookup"><span data-stu-id="d4130-166">[All]</span></span></p></li>
<li><p><span data-ttu-id="d4130-167">성공한 통화</span><span class="sxs-lookup"><span data-stu-id="d4130-167">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="d4130-168">실패한 통화</span><span class="sxs-lookup"><span data-stu-id="d4130-168">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4130-169"><strong>보고서 작성자</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-169"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-p112">보고서에 사용할 값을 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d4130-172">세션 수</span><span class="sxs-lookup"><span data-stu-id="d4130-172">Session count</span></span></p></li>
<li><p><span data-ttu-id="d4130-173">통화 시간(분)</span><span class="sxs-lookup"><span data-stu-id="d4130-173">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="d4130-174">풀별 피어 투 피어 음성 및 비디오 활동 메트릭</span><span class="sxs-lookup"><span data-stu-id="d4130-174">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="d4130-175">다음 표에서는 각 풀에 대해 피어 투 피어 음성 및 비디오 보고서에 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-175">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="d4130-176">풀별 피어 투 피어 음성 및 비디오 활동 메트릭</span><span class="sxs-lookup"><span data-stu-id="d4130-176">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4130-177">이름</span><span class="sxs-lookup"><span data-stu-id="d4130-177">Name</span></span></th>
<th><span data-ttu-id="d4130-178">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="d4130-178">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d4130-179">설명</span><span class="sxs-lookup"><span data-stu-id="d4130-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4130-180"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-180"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-181">아니요</span><span class="sxs-lookup"><span data-stu-id="d4130-181">No</span></span></p></td>
<td><p><span data-ttu-id="d4130-182">통화에 사용 되는 등록자 풀 또는에 지 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-182">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4130-183"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-183"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-184">아니요</span><span class="sxs-lookup"><span data-stu-id="d4130-184">No</span></span></p></td>
<td><p><span data-ttu-id="d4130-185">통화가 발생한 날짜 및 시간 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-185">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4130-186"><strong>합계</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-186"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-187">아니요</span><span class="sxs-lookup"><span data-stu-id="d4130-187">No</span></span></p></td>
<td><p><span data-ttu-id="d4130-188">총 세션 수 또는 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-188">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="d4130-189">통화 유형별 피어 투 피어 음성 및 비디오 활동 메트릭</span><span class="sxs-lookup"><span data-stu-id="d4130-189">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="d4130-190">다음 표에서는 수행된 통화의 각 유형에 대해 피어 투 피어 음성 및 비디오 보고서에 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-190">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="d4130-191">통화 유형별 피어 투 피어 음성 및 비디오 활동 메트릭</span><span class="sxs-lookup"><span data-stu-id="d4130-191">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4130-192">이름</span><span class="sxs-lookup"><span data-stu-id="d4130-192">Name</span></span></th>
<th><span data-ttu-id="d4130-193">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="d4130-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d4130-194">설명</span><span class="sxs-lookup"><span data-stu-id="d4130-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4130-195"><strong>통화 유형</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-195"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-196">아니요</span><span class="sxs-lookup"><span data-stu-id="d4130-196">No</span></span></p></td>
<td><p><span data-ttu-id="d4130-p113">수행된 통화의 유형을 나타냅니다. 값은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-p113">Indicates the type of call that was made. Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d4130-199">UC-UC</span><span class="sxs-lookup"><span data-stu-id="d4130-199">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="d4130-200">UC-PSTN</span><span class="sxs-lookup"><span data-stu-id="d4130-200">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="d4130-201">PSTN-UC</span><span class="sxs-lookup"><span data-stu-id="d4130-201">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="d4130-202">PSTN-PSTN</span><span class="sxs-lookup"><span data-stu-id="d4130-202">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4130-203"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-203"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-204">아니요</span><span class="sxs-lookup"><span data-stu-id="d4130-204">No</span></span></p></td>
<td><p><span data-ttu-id="d4130-205">통화가 발생한 날짜 및 시간 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-205">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4130-206"><strong>합계</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-206"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-207">아니요</span><span class="sxs-lookup"><span data-stu-id="d4130-207">No</span></span></p></td>
<td><p><span data-ttu-id="d4130-208">총 세션 수 또는 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-208">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="d4130-209">액세스 유형별 피어 투 피어 음성 및 비디오 활동 메트릭</span><span class="sxs-lookup"><span data-stu-id="d4130-209">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="d4130-210">다음 표에서는 각 네트워크 액세스 유형에 대해 피어 투 피어 음성 및 비디오 보고서에 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-210">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="d4130-211">액세스 유형별 피어 투 피어 음성 및 비디오 활동 메트릭</span><span class="sxs-lookup"><span data-stu-id="d4130-211">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4130-212">이름</span><span class="sxs-lookup"><span data-stu-id="d4130-212">Name</span></span></th>
<th><span data-ttu-id="d4130-213">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="d4130-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d4130-214">설명</span><span class="sxs-lookup"><span data-stu-id="d4130-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4130-215"><strong>활동 유형</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-215"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-216">아니요</span><span class="sxs-lookup"><span data-stu-id="d4130-216">No</span></span></p></td>
<td><p><span data-ttu-id="d4130-p114">통화가 시도되었을 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온되어 있는지를 나타냅니다. 값은 일반적으로 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-p114">Indicates whether the clients were logged on to the internal network or the external network when the call was placed. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d4130-219">내부</span><span class="sxs-lookup"><span data-stu-id="d4130-219">Internal</span></span></p></li>
<li><p><span data-ttu-id="d4130-220">외부</span><span class="sxs-lookup"><span data-stu-id="d4130-220">External</span></span></p></li>
<li><p><span data-ttu-id="d4130-221">여러</span><span class="sxs-lookup"><span data-stu-id="d4130-221">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4130-222"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-222"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-223">아니요</span><span class="sxs-lookup"><span data-stu-id="d4130-223">No</span></span></p></td>
<td><p><span data-ttu-id="d4130-224">통화가 발생한 날짜 및 시간 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-224">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4130-225"><strong>합계</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-225"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-226">아니요</span><span class="sxs-lookup"><span data-stu-id="d4130-226">No</span></span></p></td>
<td><p><span data-ttu-id="d4130-227">총 세션 수 또는 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-227">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="d4130-228">중재 서버별 피어 투 피어 음성 및 비디오 활동 메트릭</span><span class="sxs-lookup"><span data-stu-id="d4130-228">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="d4130-229">다음 표에서는 각 중재 서버에 대해 피어 투 피어 음성 및 비디오 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-229">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="d4130-230">중재 서버별 피어 투 피어 음성 및 비디오 활동 메트릭</span><span class="sxs-lookup"><span data-stu-id="d4130-230">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d4130-231">이름</span><span class="sxs-lookup"><span data-stu-id="d4130-231">Name</span></span></th>
<th><span data-ttu-id="d4130-232">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="d4130-232">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d4130-233">설명</span><span class="sxs-lookup"><span data-stu-id="d4130-233">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4130-234"><strong>중재 서버</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-234"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-235">아니요</span><span class="sxs-lookup"><span data-stu-id="d4130-235">No</span></span></p></td>
<td><p><span data-ttu-id="d4130-236">중재 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-236">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4130-237"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-237"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-238">아니요</span><span class="sxs-lookup"><span data-stu-id="d4130-238">No</span></span></p></td>
<td><p><span data-ttu-id="d4130-239">통화가 발생한 날짜 및 시간 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-239">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4130-240"><strong>합계</strong></span><span class="sxs-lookup"><span data-stu-id="d4130-240"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="d4130-241">아니요</span><span class="sxs-lookup"><span data-stu-id="d4130-241">No</span></span></p></td>
<td><p><span data-ttu-id="d4130-242">총 세션 수 또는 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d4130-242">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

