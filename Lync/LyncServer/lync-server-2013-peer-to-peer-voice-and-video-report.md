---
title: 'Lync Server 2013: 피어-투-피어 음성 및 비디오 보고서'
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
ms.openlocfilehash: dc5d3905df971cf5ce09bfb026acc4838974ff18
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536805"
---
# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="04ead-102">Lync Server 2013의 피어 투 피어 음성 및 비디오 보고서</span><span class="sxs-lookup"><span data-stu-id="04ead-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04ead-103">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="04ead-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="04ead-p101">피어 투 피어 음성 및 비디오 보고서는 지정된 시간 동안의 음성 및 비디오 통화 배포 상황에 대한 자세한 정보(예를 들면, 시간당 통화 수 또는 일별 통화 수)를 제공합니다. 이 보고서는 발생된 모든 음성 및 비디오 통화를 보거나 성공 또는 실패한 통화만 볼 수 있는 옵션도 제공합니다. 이 보고서에는 다음 그룹으로 세분되는 통화 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-p101">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day). The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls. The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="04ead-107">풀별 통화 수</span><span class="sxs-lookup"><span data-stu-id="04ead-107">Calls per pool</span></span>

  - <span data-ttu-id="04ead-108">통화 유형별 통화 (예: Lync to Lync call 및 PSTN 네트워크의 사용자에 대 한 Lync 호출)</span><span class="sxs-lookup"><span data-stu-id="04ead-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="04ead-109">액세스 유형별 통화 수(내부 네트워크에 로그온한 사용자와 외부 네트워크에 로그온한 사용자)</span><span class="sxs-lookup"><span data-stu-id="04ead-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="04ead-110">중재 서버당 통화 수</span><span class="sxs-lookup"><span data-stu-id="04ead-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="04ead-111">피어 투 피어 음성 및 비디오 보고서에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="04ead-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="04ead-112">피어 투 피어 활동 요약 보고서를 열고 다음 메트릭 중 하나를 클릭해야 피어 투 피어 음성 및 비디오 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="04ead-113">총 피어 투 피어 오디오 세션</span><span class="sxs-lookup"><span data-stu-id="04ead-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="04ead-114">총 피어 투 피어 오디오 시간(분)</span><span class="sxs-lookup"><span data-stu-id="04ead-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="04ead-115">총 피어 투 피어 비디오 세션</span><span class="sxs-lookup"><span data-stu-id="04ead-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="04ead-116">총 피어 투 피어 비디오 시간(분)</span><span class="sxs-lookup"><span data-stu-id="04ead-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="04ead-117">피어 투 피어 음성 및 비디오 보고서를 최대한 활용하려면</span><span class="sxs-lookup"><span data-stu-id="04ead-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="04ead-p102">여러 방식으로 피어 투 피어 음성 및 비디오 보고서를 필터링할 수 있습니다. 하지만 이러한 필터링 옵션은 기본적으로 보기에서 숨겨져 있습니다. 사용할 수 있는 필터링 옵션을 보려면 보고서 창의 오른쪽 위에 있는 **매개 변수 표시/숨기기** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-p102">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report. However, those filtering options are hidden from view by default. To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="04ead-121">필터</span><span class="sxs-lookup"><span data-stu-id="04ead-121">Filters</span></span>

<span data-ttu-id="04ead-p103">필터를 사용하면 여러 방식으로 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에서는 피어 투 피어 음성 및 비디오 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-p103">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways. The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="04ead-124">피어 투 피어 음성 및 비디오 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="04ead-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04ead-125">이름</span><span class="sxs-lookup"><span data-stu-id="04ead-125">Name</span></span></th>
<th><span data-ttu-id="04ead-126">설명</span><span class="sxs-lookup"><span data-stu-id="04ead-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04ead-127"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-p104">시간 범위의 시작 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜와 시간을 모두 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="04ead-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="04ead-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="04ead-p105">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="04ead-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="04ead-133">7/7/2012</span></span></p>
<p><span data-ttu-id="04ead-134">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="04ead-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="04ead-135">7/3/2012</span></span></p>
<p><span data-ttu-id="04ead-136">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04ead-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-p106">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="04ead-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="04ead-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="04ead-p107">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="04ead-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="04ead-143">7/7/2012</span></span></p>
<p><span data-ttu-id="04ead-144">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="04ead-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="04ead-145">7/3/2012</span></span></p>
<p><span data-ttu-id="04ead-146">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04ead-147"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-p108">시간 간격입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="04ead-150">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="04ead-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="04ead-151">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="04ead-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="04ead-152">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="04ead-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="04ead-153">월별(최대 12개월 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="04ead-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="04ead-p109">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04ead-156"><strong>미디어 유형</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-p110">세션에 사용된 미디어 유형을 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-p110">Indicates the type of media used in the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="04ead-159">모두</span><span class="sxs-lookup"><span data-stu-id="04ead-159">Both</span></span></p></li>
<li><p><span data-ttu-id="04ead-160">오디오만</span><span class="sxs-lookup"><span data-stu-id="04ead-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="04ead-161">비디오</span><span class="sxs-lookup"><span data-stu-id="04ead-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04ead-162"><strong>통화 처리</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-p111">세션의 성공 또는 실패를 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-p111">Indicates the success or failure of the session. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="04ead-165">모든</span><span class="sxs-lookup"><span data-stu-id="04ead-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="04ead-166">성공한 통화</span><span class="sxs-lookup"><span data-stu-id="04ead-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="04ead-167">실패한 통화</span><span class="sxs-lookup"><span data-stu-id="04ead-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04ead-168"><strong>보고서 작성자</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-p112">보고서에 사용할 값을 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="04ead-171">세션 수</span><span class="sxs-lookup"><span data-stu-id="04ead-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="04ead-172">통화 시간(분)</span><span class="sxs-lookup"><span data-stu-id="04ead-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="04ead-173">풀별 피어 투 피어 음성 및 비디오 활동 메트릭</span><span class="sxs-lookup"><span data-stu-id="04ead-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="04ead-174">다음 표에서는 각 풀에 대해 피어 투 피어 음성 및 비디오 보고서에 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="04ead-175">풀별 피어 투 피어 음성 및 비디오 활동 메트릭</span><span class="sxs-lookup"><span data-stu-id="04ead-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04ead-176">이름</span><span class="sxs-lookup"><span data-stu-id="04ead-176">Name</span></span></th>
<th><span data-ttu-id="04ead-177">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="04ead-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="04ead-178">설명</span><span class="sxs-lookup"><span data-stu-id="04ead-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04ead-179"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-180">아니요</span><span class="sxs-lookup"><span data-stu-id="04ead-180">No</span></span></p></td>
<td><p><span data-ttu-id="04ead-181">통화에 사용 되는 등록자 풀 또는에 지 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04ead-182"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-183">아니요</span><span class="sxs-lookup"><span data-stu-id="04ead-183">No</span></span></p></td>
<td><p><span data-ttu-id="04ead-184">통화가 발생한 날짜 및 시간 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04ead-185"><strong>합계</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-186">아니요</span><span class="sxs-lookup"><span data-stu-id="04ead-186">No</span></span></p></td>
<td><p><span data-ttu-id="04ead-187">총 세션 수 또는 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="04ead-188">통화 유형별 피어 투 피어 음성 및 비디오 활동 메트릭</span><span class="sxs-lookup"><span data-stu-id="04ead-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="04ead-189">다음 표에서는 수행된 통화의 각 유형에 대해 피어 투 피어 음성 및 비디오 보고서에 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="04ead-190">통화 유형별 피어 투 피어 음성 및 비디오 활동 메트릭</span><span class="sxs-lookup"><span data-stu-id="04ead-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04ead-191">이름</span><span class="sxs-lookup"><span data-stu-id="04ead-191">Name</span></span></th>
<th><span data-ttu-id="04ead-192">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="04ead-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="04ead-193">설명</span><span class="sxs-lookup"><span data-stu-id="04ead-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04ead-194"><strong>통화 유형</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-195">아니요</span><span class="sxs-lookup"><span data-stu-id="04ead-195">No</span></span></p></td>
<td><p><span data-ttu-id="04ead-p113">수행된 통화의 유형을 나타냅니다. 값은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-p113">Indicates the type of call that was made. Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="04ead-198">UC-UC</span><span class="sxs-lookup"><span data-stu-id="04ead-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="04ead-199">UC-PSTN</span><span class="sxs-lookup"><span data-stu-id="04ead-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="04ead-200">PSTN-UC</span><span class="sxs-lookup"><span data-stu-id="04ead-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="04ead-201">PSTN-PSTN</span><span class="sxs-lookup"><span data-stu-id="04ead-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04ead-202"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-203">아니요</span><span class="sxs-lookup"><span data-stu-id="04ead-203">No</span></span></p></td>
<td><p><span data-ttu-id="04ead-204">통화가 발생한 날짜 및 시간 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04ead-205"><strong>합계</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-206">아니요</span><span class="sxs-lookup"><span data-stu-id="04ead-206">No</span></span></p></td>
<td><p><span data-ttu-id="04ead-207">총 세션 수 또는 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="04ead-208">액세스 유형별 피어 투 피어 음성 및 비디오 활동 메트릭</span><span class="sxs-lookup"><span data-stu-id="04ead-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="04ead-209">다음 표에서는 각 네트워크 액세스 유형에 대해 피어 투 피어 음성 및 비디오 보고서에 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="04ead-210">액세스 유형별 피어 투 피어 음성 및 비디오 활동 메트릭</span><span class="sxs-lookup"><span data-stu-id="04ead-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04ead-211">이름</span><span class="sxs-lookup"><span data-stu-id="04ead-211">Name</span></span></th>
<th><span data-ttu-id="04ead-212">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="04ead-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="04ead-213">설명</span><span class="sxs-lookup"><span data-stu-id="04ead-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04ead-214"><strong>활동 유형</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-215">아니요</span><span class="sxs-lookup"><span data-stu-id="04ead-215">No</span></span></p></td>
<td><p><span data-ttu-id="04ead-p114">통화가 시도되었을 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온되어 있는지를 나타냅니다. 값은 일반적으로 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-p114">Indicates whether the clients were logged on to the internal network or the external network when the call was placed. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="04ead-218">내부</span><span class="sxs-lookup"><span data-stu-id="04ead-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="04ead-219">외부</span><span class="sxs-lookup"><span data-stu-id="04ead-219">External</span></span></p></li>
<li><p><span data-ttu-id="04ead-220">여러</span><span class="sxs-lookup"><span data-stu-id="04ead-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04ead-221"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-222">아니요</span><span class="sxs-lookup"><span data-stu-id="04ead-222">No</span></span></p></td>
<td><p><span data-ttu-id="04ead-223">통화가 발생한 날짜 및 시간 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04ead-224"><strong>합계</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-225">아니요</span><span class="sxs-lookup"><span data-stu-id="04ead-225">No</span></span></p></td>
<td><p><span data-ttu-id="04ead-226">총 세션 수 또는 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="04ead-227">중재 서버별 피어 투 피어 음성 및 비디오 활동 메트릭</span><span class="sxs-lookup"><span data-stu-id="04ead-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="04ead-228">다음 표에서는 각 중재 서버에 대해 피어 투 피어 음성 및 비디오 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="04ead-229">중재 서버별 피어 투 피어 음성 및 비디오 활동 메트릭</span><span class="sxs-lookup"><span data-stu-id="04ead-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04ead-230">이름</span><span class="sxs-lookup"><span data-stu-id="04ead-230">Name</span></span></th>
<th><span data-ttu-id="04ead-231">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="04ead-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="04ead-232">설명</span><span class="sxs-lookup"><span data-stu-id="04ead-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04ead-233"><strong>중재 서버</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-234">아니요</span><span class="sxs-lookup"><span data-stu-id="04ead-234">No</span></span></p></td>
<td><p><span data-ttu-id="04ead-235">중재 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04ead-236"><strong>날짜/시간</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-237">아니요</span><span class="sxs-lookup"><span data-stu-id="04ead-237">No</span></span></p></td>
<td><p><span data-ttu-id="04ead-238">통화가 발생한 날짜 및 시간 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04ead-239"><strong>합계</strong></span><span class="sxs-lookup"><span data-stu-id="04ead-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="04ead-240">아니요</span><span class="sxs-lookup"><span data-stu-id="04ead-240">No</span></span></p></td>
<td><p><span data-ttu-id="04ead-241">총 세션 수 또는 총 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="04ead-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

