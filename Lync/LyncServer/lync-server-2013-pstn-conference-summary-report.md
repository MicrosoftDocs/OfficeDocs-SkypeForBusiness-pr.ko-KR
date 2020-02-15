---
title: 'Lync Server 2013: PSTN 전화 회의 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa902b9e4d53bf0ebbedf835296a371437860095
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="b9ae4-102">Lync Server 2013의 PSTN 전화 회의 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="b9ae4-102">PSTN Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9ae4-103">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="b9ae4-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="b9ae4-104">Microsoft Lync Server 2013에서 PSTN 전화 회의는 하나 이상의 참가자가 PSTN (공중 전화망) 전화기를 사용 하 여 오디오 부분에 전화를 거는 모든 회의입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-104">In Microsoft Lync Server 2013, a PSTN conference is any conference in which at least one participant dials in to the audio portion by a using a PSTN (public switched telephone network) phone.</span></span> <span data-ttu-id="b9ae4-105">PSTN 전화는 "일반 전화선으로", 휴대폰 또는 다른 전화기를 사용 하 여 IP를 통해 음성을 사용할 수 없습니다. 모니터링 보고서에서 PSTN 회의 라고 하지만 이러한 회의는 일반적으로 전화 접속 회의 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-105">(A PSTN phone is a "landline," a cell phone, or any other phone which does not make use of Voice over IP.) Although referred to as PSTN conferences in the Monitoring Reports, these conferences are perhaps more-commonly known as dial-in conferences.</span></span>

<span data-ttu-id="b9ae4-p102">PSTN 전화 회의 요약 보고서에서는 조직에서 수행된 모든 PSTN 전화 회의에 대한 정보를 제공합니다(즉, 전화 접속 사용자가 한 명 이상 포함된 모든 회의). 보고서에는 총 PSTN 전화 회의 수, 이러한 회의에 참가한 총 사용자 수, 그리고 가장 중요한 총 전화 접속 사용자 수(총 PSTN 참가자 메트릭)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-p102">The PSTN Conference Summary Report provides information about all the PSTN conferences held in your organization (that is, all the conferences that had at least one dial-in user). The report includes information about the total number of PSTN conferences, the total number of people who participated in those conferences, and, perhaps, most important, the total number of dial-in users (the Total PSTN participants metric).</span></span>

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a><span data-ttu-id="b9ae4-108">PSTN 전화 회의 요약 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="b9ae4-108">Accessing the PSTN Conference Summary Report</span></span>

<span data-ttu-id="b9ae4-p103">PSTN 전화 회의 요약 보고서는 모니터링 보고서 홈 페이지에서만 액세스할 수 있습니다. 이 보고서는 다른 보고서에 연결되지 않습니다. PSTN 전화 회의에 대해서는 개별 끝점이 이 정보를 제출하기 때문에 자세한 통화 정보를 검색할 수 없습니다. PSTN 전화는 통화 세부 정보를 추적하거나 제출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-p103">The PSTN Conference Summary Report can only be accessed from the Monitoring Reports home page. This report is not linked to any other reports. Note that you cannot retrieve detailed call information for a PSTN conference, in part because individual endpoints are responsible for submitting this information. PSTN phones are not capable of tracking or submitting call detail information.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a><span data-ttu-id="b9ae4-113">PSTN 전화 회의 요약 보고서의 모범 사례 만들기</span><span class="sxs-lookup"><span data-stu-id="b9ae4-113">Making the Best Use of the PSTN Conference Summary Report</span></span>

<span data-ttu-id="b9ae4-114">전화 접속 사용자를 포함 하는 모든 회의의 비율을 확인 하려면 총 PSTN 전화 회의 메트릭의 값을 [Lync Server 2013의 전화 회의 요약 보고서](lync-server-2013-conference-summary-report.md)에 있는 총 회의 메트릭으로 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-114">To determine the percentage of all your conferences that include dial-in users, compare the value of the Total PSTN conferences metric with the Total conferences metric found on the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span></span>

<span data-ttu-id="b9ae4-p104">PSTN 전화 회의 수가 예상한 것보다 적은 경우, 전화 접속 사용자를 허용하는 회의를 구성하는 기능이 사용자에게 지정된 회의 정책에 따라 달라진다는 것에 유의하십시오. PSTN 전화 회의를 주최하도록 허용된 사용자 수가 적을수록 PSTN 전화 회의 수가 줄어듭니다. Lync Server 관리 셸 내에서 다음 명령을 실행하면 사용자가 PSTN 전화 회의를 예약하도록 허용하는 회의 정책(있는 경우)을 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-p104">If you don't see as many PSTN conferences as you might have expected to see, keep in mind that the ability to organize a conference that allows dial-in users depends on the conferencing policy that has been assigned to a user: if very few of your users are allowed to hold PSTN conferences you would obviously see very few PSTN conferences. You can quickly verify which of your conferencing policies (if any) allow users to schedule PSTN conferences by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

<span data-ttu-id="b9ae4-117">이 명령을 실행하면 다음과 같은 데이터가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-117">That will return data similar to this:</span></span>

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

<span data-ttu-id="b9ae4-118">그러면 다음과 비슷한 데이터가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-118">That will return data similar to this:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b9ae4-119">필터</span><span class="sxs-lookup"><span data-stu-id="b9ae4-119">Filters</span></span>

<span data-ttu-id="b9ae4-p105">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 PSTN 전화 회의 요약 보고서에서는 데이터의 그룹화 방법을 선택할 수 있습니다. 이 경우 전화 회의는 시간, 일, 주 또는 월별로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the PSTN Conference Summary Report enables you to choose how data should be grouped. In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="b9ae4-123">다음 표에서는 PSTN 전화 회의 요약 보고서에서 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-123">The following table lists the filters that you can use with the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-filters"></a><span data-ttu-id="b9ae4-124">PSTN 전화 회의 요약 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="b9ae4-124">PSTN Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9ae4-125">이름</span><span class="sxs-lookup"><span data-stu-id="b9ae4-125">Name</span></span></th>
<th><span data-ttu-id="b9ae4-126">설명</span><span class="sxs-lookup"><span data-stu-id="b9ae4-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9ae4-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="b9ae4-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ae4-p106">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b9ae4-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b9ae4-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b9ae4-p107">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b9ae4-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b9ae4-133">7/7/2012</span></span></p>
<p><span data-ttu-id="b9ae4-134">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b9ae4-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b9ae4-135">7/3/2012</span></span></p>
<p><span data-ttu-id="b9ae4-136">주는 항상 일요일부터 토요일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9ae4-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="b9ae4-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ae4-p108">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b9ae4-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b9ae4-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b9ae4-p109">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b9ae4-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b9ae4-143">7/7/2012</span></span></p>
<p><span data-ttu-id="b9ae4-144">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b9ae4-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b9ae4-145">7/3/2012</span></span></p>
<p><span data-ttu-id="b9ae4-146">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9ae4-147"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="b9ae4-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ae4-p110">시간 간격입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b9ae4-150">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="b9ae4-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b9ae4-151">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="b9ae4-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b9ae4-152">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="b9ae4-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b9ae4-153">월별(최대 12개월 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="b9ae4-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="b9ae4-p111">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b9ae4-156">선별한</span><span class="sxs-lookup"><span data-stu-id="b9ae4-156">Metrics</span></span>

<span data-ttu-id="b9ae4-157">다음 표에서는 PSTN 전화 회의 요약 보고서의 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-157">The following table lists the information in the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-metrics"></a><span data-ttu-id="b9ae4-158">PSTN 전화 회의 요약 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="b9ae4-158">PSTN Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9ae4-159">이름</span><span class="sxs-lookup"><span data-stu-id="b9ae4-159">Name</span></span></th>
<th><span data-ttu-id="b9ae4-160">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="b9ae4-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b9ae4-161">설명</span><span class="sxs-lookup"><span data-stu-id="b9ae4-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9ae4-162"><strong>매시간</strong></span><span class="sxs-lookup"><span data-stu-id="b9ae4-162"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="b9ae4-163"><strong>매일</strong></span><span class="sxs-lookup"><span data-stu-id="b9ae4-163"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="b9ae4-164"><strong>매주</strong></span><span class="sxs-lookup"><span data-stu-id="b9ae4-164"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="b9ae4-165"><strong>월간</strong></span><span class="sxs-lookup"><span data-stu-id="b9ae4-165"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ae4-166">아니요</span><span class="sxs-lookup"><span data-stu-id="b9ae4-166">No</span></span></p></td>
<td><p><span data-ttu-id="b9ae4-p112">선택한 시간 간격을 나타냅니다. 적용 가능한 경우 제공된 시간 간격을 클릭하여 해당 간격에 대한 자세한 정보를 볼 수 있습니다. 예를 들어 일별 간격을 사용 중이고 7/7/2012를 클릭하면 해당 날짜에 사용자 등록 활동에 대한 시간별 세부 내역을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-p112">Indicates the selected time interval. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9ae4-170"><strong>총 PSTN 전화 회의</strong></span><span class="sxs-lookup"><span data-stu-id="b9ae4-170"><strong>Total PSTN conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ae4-171">아니요</span><span class="sxs-lookup"><span data-stu-id="b9ae4-171">No</span></span></p></td>
<td><p><span data-ttu-id="b9ae4-172">전화 접속 액세스가 허용된 총 전화 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-172">Total number conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9ae4-173"><strong>총 참가자</strong></span><span class="sxs-lookup"><span data-stu-id="b9ae4-173"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ae4-174">아니요</span><span class="sxs-lookup"><span data-stu-id="b9ae4-174">No</span></span></p></td>
<td><p><span data-ttu-id="b9ae4-175">전화 접속 액세스가 허용된 전화 회의에 참가한 총 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-175">Total number of people who participated in conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9ae4-176"><strong>총 A/V 회의 시간(분)</strong></span><span class="sxs-lookup"><span data-stu-id="b9ae4-176"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ae4-177">아니요</span><span class="sxs-lookup"><span data-stu-id="b9ae4-177">No</span></span></p></td>
<td><p><span data-ttu-id="b9ae4-178">오디오/비디오 회의의 총 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-178">Total amount of audio/visual conference time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9ae4-179"><strong>총 A/V 회의 참가 시간(분)</strong></span><span class="sxs-lookup"><span data-stu-id="b9ae4-179"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ae4-180">아니요</span><span class="sxs-lookup"><span data-stu-id="b9ae4-180">No</span></span></p></td>
<td><p><span data-ttu-id="b9ae4-p113">오디오/비디오 참가자의 총 시간입니다. 예를 들어 한 사용자가 A/V 회의에서 5분을 소비하고 다른 참가자 같은 회의에서 3분을 소비한 경우 총 A/V 회의 참가자 시간은 8분입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-p113">Total amount of audio/visual participant time. For example, if one participant spent five minutes in an A/V conference and another participant spent three minutes in the same conference, the total A/V conference participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9ae4-183"><strong>총 PSTN 참가자</strong></span><span class="sxs-lookup"><span data-stu-id="b9ae4-183"><strong>Total PSTN participants</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ae4-184">아니요</span><span class="sxs-lookup"><span data-stu-id="b9ae4-184">No</span></span></p></td>
<td><p><span data-ttu-id="b9ae4-185">전화 접속 액세스가 허용된 전화 회의에 전화 접속한 총 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-185">Total number of users who dialed in to conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9ae4-186"><strong>총 PSTN 참가자 시간(분)</strong></span><span class="sxs-lookup"><span data-stu-id="b9ae4-186"><strong>Total PSTN participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ae4-187">아니요</span><span class="sxs-lookup"><span data-stu-id="b9ae4-187">No</span></span></p></td>
<td><p><span data-ttu-id="b9ae4-p114">전화 접속 사용자가 소비한 총 전화 회의 시간입니다. 예를 들어 한 전화 접속 사용자가 한 회의에서 5분을 소비하고 다른 참가자 같은 회의에서 3분을 소비한 경우 총 PSTN 참가자 시간은 8분입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-p114">Total amount of conference time spent by dial-in users. For example, if one dial-in participant spent five minutes in a conference and another participant spent three minutes in the same conference, the total PSTN participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9ae4-190"><strong>고유한 전화 회의 이끌이</strong></span><span class="sxs-lookup"><span data-stu-id="b9ae4-190"><strong>Unique conference organizers</strong></span></span></p></td>
<td><p><span data-ttu-id="b9ae4-191">아니요</span><span class="sxs-lookup"><span data-stu-id="b9ae4-191">No</span></span></p></td>
<td><p><span data-ttu-id="b9ae4-p115">전화 접속 액세스가 허용된 전화 회의를 하나 이상 구성한 총 사용자 수입니다. 회의를 하나 이상 구성한 사용자는 단일 회의만 구성한 사용자와 같이 한 명의 고유한 이끌이로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ae4-p115">Total number of users who organized at least one conference that allowed dial-in access. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

