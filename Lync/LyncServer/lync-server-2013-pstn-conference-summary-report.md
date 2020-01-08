---
title: 'Lync Server 2013: PSTN 컨퍼런스 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b98628ea56fb36ec594e5ea4ff9915e9785b3cfa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="2d6d4-102">Lync Server 2013의 PSTN 회의 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="2d6d4-102">PSTN Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d6d4-103">_**마지막으로 수정한 주제:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="2d6d4-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="2d6d4-104">Microsoft Lync Server 2013에서 PSTN 컨퍼런스는 하나 이상의 참가자가 PSTN (공공 교환 전화 네트워크) 전화기를 사용 하 여 오디오 부분에 전화를 거는 모든 회의입니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-104">In Microsoft Lync Server 2013, a PSTN conference is any conference in which at least one participant dials in to the audio portion by a using a PSTN (public switched telephone network) phone.</span></span> <span data-ttu-id="2d6d4-105">PSTN 전화는 "유선전화", 휴대폰 또는 IP를 통해 음성을 사용 하지 않는 기타 전화기입니다. 이러한 회의는 모니터링 보고서의 PSTN 회의 라고 할 수 있지만, 일반적으로 전화 접속 회의로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-105">(A PSTN phone is a "landline," a cell phone, or any other phone which does not make use of Voice over IP.) Although referred to as PSTN conferences in the Monitoring Reports, these conferences are perhaps more-commonly known as dial-in conferences.</span></span>

<span data-ttu-id="2d6d4-106">PSTN 회의 요약 보고서는 조직에 있는 모든 PSTN 컨퍼런스 (즉, 하나 이상의 전화 접속 사용자가 있는 모든 회의)에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-106">The PSTN Conference Summary Report provides information about all the PSTN conferences held in your organization (that is, all the conferences that had at least one dial-in user).</span></span> <span data-ttu-id="2d6d4-107">이 보고서에는 총 PSTN 회의 수, 해당 회의에 참여 한 총 사용자 수, 그리고 가장 중요 한 총 전화 접속 사용자 수 (총 PSTN 참가자 메트릭)에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-107">The report includes information about the total number of PSTN conferences, the total number of people who participated in those conferences, and, perhaps, most important, the total number of dial-in users (the Total PSTN participants metric).</span></span>

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a><span data-ttu-id="2d6d4-108">PSTN 회의 요약 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="2d6d4-108">Accessing the PSTN Conference Summary Report</span></span>

<span data-ttu-id="2d6d4-109">PSTN 회의 요약 보고서는 모니터링 보고서 홈 페이지 에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-109">The PSTN Conference Summary Report can only be accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="2d6d4-110">이 보고서는 다른 보고서에 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-110">This report is not linked to any other reports.</span></span> <span data-ttu-id="2d6d4-111">각 끝점이이 정보를 제출 하는 데 책임이 있으므로 PSTN 회의에 대 한 자세한 호출 정보를 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-111">Note that you cannot retrieve detailed call information for a PSTN conference, in part because individual endpoints are responsible for submitting this information.</span></span> <span data-ttu-id="2d6d4-112">PSTN 전화는 통화 정보를 추적 하거나 제출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-112">PSTN phones are not capable of tracking or submitting call detail information.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a><span data-ttu-id="2d6d4-113">PSTN 회의 요약 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="2d6d4-113">Making the Best Use of the PSTN Conference Summary Report</span></span>

<span data-ttu-id="2d6d4-114">전화 접속 사용자를 포함 하는 모든 회의의 백분율을 확인 하려면 총 PSTN 회의 메트릭의 값을 [Lync Server 2013의 컨퍼런스 요약 보고서](lync-server-2013-conference-summary-report.md)에 있는 총 회의 메트릭으로 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-114">To determine the percentage of all your conferences that include dial-in users, compare the value of the Total PSTN conferences metric with the Total conferences metric found on the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span></span>

<span data-ttu-id="2d6d4-115">표시 해야 할 수 있는 것 처럼 많은 PSTN 회의가 표시 되지 않는 경우 전화 접속 사용자를 허용 하는 회의를 구성 하는 기능은 사용자에 게 할당 된 회의 정책에 따라 달라 집니다. 일부 사용자에 게 PS를 보류할 수 있는 권한이 있는 경우에 유의 하세요. TN-ZA&PLATFORM 회의는 매우 적은 PSTN 회의를 분명히 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-115">If you don't see as many PSTN conferences as you might have expected to see, keep in mind that the ability to organize a conference that allows dial-in users depends on the conferencing policy that has been assigned to a user: if very few of your users are allowed to hold PSTN conferences you would obviously see very few PSTN conferences.</span></span> <span data-ttu-id="2d6d4-116">Lync Server Management Shell 내에서 다음 명령을 실행 하 여 사용자가 PSTN 회의를 예약할 수 있도록 허용 하는 회의 정책 (있는 경우)을 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-116">You can quickly verify which of your conferencing policies (if any) allow users to schedule PSTN conferences by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

<span data-ttu-id="2d6d4-117">이는 다음과 같은 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-117">That will return data similar to this:</span></span>

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

<span data-ttu-id="2d6d4-118">이는 다음과 같은 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-118">That will return data similar to this:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2d6d4-119">필터가</span><span class="sxs-lookup"><span data-stu-id="2d6d4-119">Filters</span></span>

<span data-ttu-id="2d6d4-120">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="2d6d4-121">예를 들어 PSTN 회의 요약 보고서를 사용 하 여 데이터를 그룹화 하는 방법을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-121">For example, the PSTN Conference Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="2d6d4-122">이 경우 회의는 시간, 일, 주 또는 월로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-122">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="2d6d4-123">다음 표에는 PSTN 회의 요약 보고서에 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-123">The following table lists the filters that you can use with the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-filters"></a><span data-ttu-id="2d6d4-124">PSTN 회의 요약 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="2d6d4-124">PSTN Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d6d4-125">이름</span><span class="sxs-lookup"><span data-stu-id="2d6d4-125">Name</span></span></th>
<th><span data-ttu-id="2d6d4-126">설명</span><span class="sxs-lookup"><span data-stu-id="2d6d4-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d6d4-127"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="2d6d4-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2d6d4-128">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-128">Start date/time for the time range.</span></span> <span data-ttu-id="2d6d4-129">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-129">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2d6d4-130">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="2d6d4-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2d6d4-131">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-131">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="2d6d4-132">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-132">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2d6d4-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2d6d4-133">7/7/2012</span></span></p>
<p><span data-ttu-id="2d6d4-134">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="2d6d4-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2d6d4-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2d6d4-135">7/3/2012</span></span></p>
<p><span data-ttu-id="2d6d4-136">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d6d4-137"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="2d6d4-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2d6d4-138">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-138">End date/time for the time range.</span></span> <span data-ttu-id="2d6d4-139">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-139">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2d6d4-140">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="2d6d4-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2d6d4-141">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-141">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="2d6d4-142">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-142">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2d6d4-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2d6d4-143">7/7/2012</span></span></p>
<p><span data-ttu-id="2d6d4-144">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="2d6d4-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2d6d4-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2d6d4-145">7/3/2012</span></span></p>
<p><span data-ttu-id="2d6d4-146">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d6d4-147"><strong>간격만</strong></span><span class="sxs-lookup"><span data-stu-id="2d6d4-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="2d6d4-148">시간 간격.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-148">Time interval.</span></span> <span data-ttu-id="2d6d4-149">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-149">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2d6d4-150">매시간 (최대 25 시간 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="2d6d4-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2d6d4-151">매일 (최대 31 일이 표시 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="2d6d4-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2d6d4-152">주간 (최대 12 주를 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="2d6d4-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2d6d4-153">월간 (최대 12 개월을 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="2d6d4-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="2d6d4-154">시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-154">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="2d6d4-155">예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-155">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="2d6d4-156">매트릭스</span><span class="sxs-lookup"><span data-stu-id="2d6d4-156">Metrics</span></span>

<span data-ttu-id="2d6d4-157">다음 표에는 PSTN 회의 요약 보고서의 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-157">The following table lists the information in the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-metrics"></a><span data-ttu-id="2d6d4-158">PSTN 회의 요약 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="2d6d4-158">PSTN Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d6d4-159">이름</span><span class="sxs-lookup"><span data-stu-id="2d6d4-159">Name</span></span></th>
<th><span data-ttu-id="2d6d4-160">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="2d6d4-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2d6d4-161">설명</span><span class="sxs-lookup"><span data-stu-id="2d6d4-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d6d4-162"><strong>마다</strong></span><span class="sxs-lookup"><span data-stu-id="2d6d4-162"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="2d6d4-163"><strong>Daily</strong></span><span class="sxs-lookup"><span data-stu-id="2d6d4-163"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="2d6d4-164"><strong>매주</strong></span><span class="sxs-lookup"><span data-stu-id="2d6d4-164"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="2d6d4-165"><strong>월간</strong></span><span class="sxs-lookup"><span data-stu-id="2d6d4-165"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="2d6d4-166">아니요</span><span class="sxs-lookup"><span data-stu-id="2d6d4-166">No</span></span></p></td>
<td><p><span data-ttu-id="2d6d4-167">선택한 시간 간격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-167">Indicates the selected time interval.</span></span> <span data-ttu-id="2d6d4-168">해당 되는 경우 지정 된 시간 간격을 클릭 하 여 해당 간격에 대 한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-168">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="2d6d4-169">예를 들어 일일 기간을 사용 하는 경우 7/7/2012을 클릭 하면 해당 날짜에 대 한 사용자 등록 작업을 시간별로 분류 하 여 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-169">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d6d4-170"><strong>총 PSTN 컨퍼런스</strong></span><span class="sxs-lookup"><span data-stu-id="2d6d4-170"><strong>Total PSTN conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="2d6d4-171">아니요</span><span class="sxs-lookup"><span data-stu-id="2d6d4-171">No</span></span></p></td>
<td><p><span data-ttu-id="2d6d4-172">전화 접속 액세스를 허용 하는 총 컨퍼런스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-172">Total number conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d6d4-173"><strong>총 참가자</strong></span><span class="sxs-lookup"><span data-stu-id="2d6d4-173"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="2d6d4-174">아니요</span><span class="sxs-lookup"><span data-stu-id="2d6d4-174">No</span></span></p></td>
<td><p><span data-ttu-id="2d6d4-175">전화 접속 액세스를 허용 하는 회의에 참가 한 총 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-175">Total number of people who participated in conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d6d4-176"><strong>총 A/V 회의 시간 (분)</strong></span><span class="sxs-lookup"><span data-stu-id="2d6d4-176"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="2d6d4-177">아니요</span><span class="sxs-lookup"><span data-stu-id="2d6d4-177">No</span></span></p></td>
<td><p><span data-ttu-id="2d6d4-178">오디오/시각 컨퍼런스 총 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-178">Total amount of audio/visual conference time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d6d4-179"><strong>총 A/V 회의 참가자 통화 시간</strong></span><span class="sxs-lookup"><span data-stu-id="2d6d4-179"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="2d6d4-180">아니요</span><span class="sxs-lookup"><span data-stu-id="2d6d4-180">No</span></span></p></td>
<td><p><span data-ttu-id="2d6d4-181">총 오디오/시각적 참가자 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-181">Total amount of audio/visual participant time.</span></span> <span data-ttu-id="2d6d4-182">예를 들어 한 참가자가 A/V 회의에 5 분을 소요 하 고 다른 참가자가 같은 회의에서 3 분이 소요 되는 경우 총 A/V 회의 참가자 시간은 8 분입니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-182">For example, if one participant spent five minutes in an A/V conference and another participant spent three minutes in the same conference, the total A/V conference participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d6d4-183"><strong>총 PSTN 참가자</strong></span><span class="sxs-lookup"><span data-stu-id="2d6d4-183"><strong>Total PSTN participants</strong></span></span></p></td>
<td><p><span data-ttu-id="2d6d4-184">아니요</span><span class="sxs-lookup"><span data-stu-id="2d6d4-184">No</span></span></p></td>
<td><p><span data-ttu-id="2d6d4-185">전화 접속 액세스를 허용 하는 회의에 전화를 건 총 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-185">Total number of users who dialed in to conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d6d4-186"><strong>총 PSTN 참가 시간 (분)</strong></span><span class="sxs-lookup"><span data-stu-id="2d6d4-186"><strong>Total PSTN participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="2d6d4-187">아니요</span><span class="sxs-lookup"><span data-stu-id="2d6d4-187">No</span></span></p></td>
<td><p><span data-ttu-id="2d6d4-188">전화 접속 사용자가 소비한 총 컨퍼런스 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-188">Total amount of conference time spent by dial-in users.</span></span> <span data-ttu-id="2d6d4-189">예를 들어 전화 접속 참가 참석자 한 명에 5 분이 소요 되 고 다른 참가자가 같은 회의에서 3 분이 소요 되는 경우 총 PSTN 참가자 시간은 8 분입니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-189">For example, if one dial-in participant spent five minutes in a conference and another participant spent three minutes in the same conference, the total PSTN participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d6d4-190"><strong>고유한 회의 이끌이</strong></span><span class="sxs-lookup"><span data-stu-id="2d6d4-190"><strong>Unique conference organizers</strong></span></span></p></td>
<td><p><span data-ttu-id="2d6d4-191">아니요</span><span class="sxs-lookup"><span data-stu-id="2d6d4-191">No</span></span></p></td>
<td><p><span data-ttu-id="2d6d4-192">전화 접속 액세스를 허용 하는 하나 이상의 회의를 구성한 총 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-192">Total number of users who organized at least one conference that allowed dial-in access.</span></span> <span data-ttu-id="2d6d4-193">두 개 이상의 회의를 구성한 사용자는 단일 컨퍼런스만 구성한 사용자와 같이 하나의 고유 이끌이로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d6d4-193">Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

