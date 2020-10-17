---
title: 'Lync Server 2013: 피어-투-피어 활동 요약 보고서'
description: 'Lync Server 2013: 피어 투 피어 활동 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f081f542a5063ed83be470d3e991c58e458b487
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557304"
---
# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="7d8e3-103">Lync Server 2013의 피어 투 피어 활동 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="7d8e3-103">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d8e3-104">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="7d8e3-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="7d8e3-105">피어 투 피어 활동 요약 보고서는 피어 투 피어 통신 세션에 대 한 전체 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-105">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="7d8e3-106">피어 투 피어 세션에는 일반적으로 두 명의 사용자만 포함 되며 Lync Server 회의 서비스는 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-106">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="7d8e3-107">일반적으로 회의에는 두 명 이상의 사용자가 포함 되므로 Microsoft Lync Server 2013 회의 서비스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-107">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="7d8e3-108">전화 회의 활동이 전화 회의 요약 보고서에 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-108">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="7d8e3-109">피어 투 피어 활동 요약 보고서는 다음과 같은 질문에 답할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-109">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="7d8e3-110">사용자가 일반적인 날에 얼마나 많은 피어 투 피어 인스턴트 메시지를 보낼 것인가?</span><span class="sxs-lookup"><span data-stu-id="7d8e3-110">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="7d8e3-111">실제로 Lync Server 응용 프로그램 공유 및 파일 전송 기능을 활용 하는 사용자가 있나요?</span><span class="sxs-lookup"><span data-stu-id="7d8e3-111">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="7d8e3-112">사용자가 하루 중 특정 시간에 느린 속도로 네트워크를 불만 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-112">Users have been complaining that the network seems slow at certain times of the day.</span></span> <span data-ttu-id="7d8e3-113">이러한 기간 동안 피어 투 피어 오디오 및 비디오 세션에 소요 되는 시간은 몇 분 입니까?</span><span class="sxs-lookup"><span data-stu-id="7d8e3-113">How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="7d8e3-114">피어 투 피어 활동 요약 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="7d8e3-114">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="7d8e3-115">모니터링 보고서 홈 페이지에서 피어 투 피어 활동 요약 보고서에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-115">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="7d8e3-116">[Lync Server 2013에서](lync-server-2013-peer-to-peer-im-report.md) 다음 메트릭 중 하나를 클릭 하 여 피어 투 피어 IM 보고서를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-116">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="7d8e3-117">총 피어 투 피어 IM 세션</span><span class="sxs-lookup"><span data-stu-id="7d8e3-117">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="7d8e3-118">총 피어 투 피어 IM 메시지</span><span class="sxs-lookup"><span data-stu-id="7d8e3-118">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="7d8e3-119">마찬가지로 다음 메트릭 중 하나를 클릭 하 여 피어 투 피어 음성 및 비디오 보고서를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-119">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="7d8e3-120">총 피어 투 피어 오디오 세션</span><span class="sxs-lookup"><span data-stu-id="7d8e3-120">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="7d8e3-121">총 피어 투 피어 오디오 세션 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="7d8e3-121">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="7d8e3-122">총 피어 투 피어 오디오 세션</span><span class="sxs-lookup"><span data-stu-id="7d8e3-122">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="7d8e3-123">총 피어 투 피어 오디오 세션 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="7d8e3-123">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="7d8e3-124">피어 투 피어 활동 요약 보고서의 모범 사례 만들기</span><span class="sxs-lookup"><span data-stu-id="7d8e3-124">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="7d8e3-125">피어 투 피어 활동 요약 보고서 아래쪽에서 총 피어 투 피어 IM 세션 및 총 피어 투 피어 IM 메시지와 같은 메트릭에 대 한 합계를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-125">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages.</span></span> <span data-ttu-id="7d8e3-126">보고서 본문에서 찾은 자세한 정보를 요약 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-126">This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7d8e3-127">필터</span><span class="sxs-lookup"><span data-stu-id="7d8e3-127">Filters</span></span>

<span data-ttu-id="7d8e3-128">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-128">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="7d8e3-129">예를 들어 피어 투 피어 활동 요약 보고서를 사용 하 여 데이터를 그룹화 하는 방법을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-129">For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="7d8e3-130">이 경우 작업은 시, 일, 주 또는 월별로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-130">In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="7d8e3-131">다음 표에서는 피어 투 피어 활동 요약 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-131">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="7d8e3-132">피어-투-피어 활동 요약 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="7d8e3-132">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d8e3-133">이름</span><span class="sxs-lookup"><span data-stu-id="7d8e3-133">Name</span></span></th>
<th><span data-ttu-id="7d8e3-134">설명</span><span class="sxs-lookup"><span data-stu-id="7d8e3-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d8e3-135"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-135"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7d8e3-p106">시간 범위의 시작 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜와 시간을 모두 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7d8e3-138">2012/7/17 오후 1:00</span><span class="sxs-lookup"><span data-stu-id="7d8e3-138">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="7d8e3-p107">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7d8e3-141">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="7d8e3-141">7/17/12012</span></span></p>
<p><span data-ttu-id="7d8e3-142">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-142">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7d8e3-143">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="7d8e3-143">7/13/2012</span></span></p>
<p><span data-ttu-id="7d8e3-144">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-144">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d8e3-145"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-145"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7d8e3-p108">시간 범위의 종료 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7d8e3-148">2012/7/17 오후 1:00</span><span class="sxs-lookup"><span data-stu-id="7d8e3-148">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="7d8e3-p109">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7d8e3-151">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="7d8e3-151">7/17/12012</span></span></p>
<p><span data-ttu-id="7d8e3-152">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-152">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7d8e3-153">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="7d8e3-153">7/13/2012</span></span></p>
<p><span data-ttu-id="7d8e3-154">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-154">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d8e3-155"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-155"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="7d8e3-p110">시간 간격입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7d8e3-158">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="7d8e3-158">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7d8e3-159">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="7d8e3-159">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7d8e3-160">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="7d8e3-160">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7d8e3-161">월별(최대 12개월 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="7d8e3-161">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="7d8e3-162">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-162">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="7d8e3-163">예를 들어 시작 날짜가 7/17/12012이 고 종료 날짜가 2/28/2012 인 일별 간격을 선택 하는 경우 데이터는 8/7/12012 12:00 오전에서 9/7/12012 12:00까지, 즉 총 31 일 분량의 데이터에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-163">For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7d8e3-164">메트릭</span><span class="sxs-lookup"><span data-stu-id="7d8e3-164">Metrics</span></span>

<span data-ttu-id="7d8e3-165">다음 표에서는 피어 투 피어 활동 요약 보고서에서 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-165">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="7d8e3-166">피어 투 피어 활동 요약 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="7d8e3-166">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d8e3-167">이름</span><span class="sxs-lookup"><span data-stu-id="7d8e3-167">Name</span></span></th>
<th><span data-ttu-id="7d8e3-168">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="7d8e3-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7d8e3-169">설명</span><span class="sxs-lookup"><span data-stu-id="7d8e3-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d8e3-170"><strong>매시간</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-170"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="7d8e3-171"><strong>매일</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-171"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="7d8e3-172"><strong>매주</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-172"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="7d8e3-173"><strong>월간</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-173"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="7d8e3-174">아니요</span><span class="sxs-lookup"><span data-stu-id="7d8e3-174">No</span></span></p></td>
<td><p><span data-ttu-id="7d8e3-175">필터 도구 모음에서 선택한 시간 간격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-175">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="7d8e3-176">적용 가능한 경우 제공된 시간 간격을 클릭하여 해당 간격에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-176">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="7d8e3-177">예를 들어 일별 간격을 사용 하는 상태에서 7/17/12012를 클릭 하면 해당 날짜에 대 한 사용자 등록 작업을 시간별로 분석 하 여 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-177">For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d8e3-178"><strong>총 피어 투 피어 세션</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-178"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7d8e3-179">아니요</span><span class="sxs-lookup"><span data-stu-id="7d8e3-179">No</span></span></p></td>
<td><p><span data-ttu-id="7d8e3-180">세션 유형에 관계 없이 수행 된 총 피어 투 피어 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-180">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d8e3-181"><strong>총 피어 투 피어 IM 세션</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-181"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7d8e3-182">아니요</span><span class="sxs-lookup"><span data-stu-id="7d8e3-182">No</span></span></p></td>
<td><p><span data-ttu-id="7d8e3-183">피어 투 피어 IM (인스턴트 메시징) 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-183">Total number of peer-to-peer instant messaging (IM) sessions.</span></span> <span data-ttu-id="7d8e3-184">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 IM 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-184">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d8e3-185"><strong>총 피어 투 피어 IM 메시지</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-185"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="7d8e3-186">아니요</span><span class="sxs-lookup"><span data-stu-id="7d8e3-186">No</span></span></p></td>
<td><p><span data-ttu-id="7d8e3-187">피어 투 피어 세션에서 전송 된 총 인스턴트 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-187">Total number of instant messages sent in peer-to-peer sessions.</span></span> <span data-ttu-id="7d8e3-188">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 IM 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-188">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d8e3-189"><strong>총 피어 투 피어 오디오 세션</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-189"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7d8e3-190">아니요</span><span class="sxs-lookup"><span data-stu-id="7d8e3-190">No</span></span></p></td>
<td><p><span data-ttu-id="7d8e3-191">총 피어 투 피어 오디오 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-191">Total number of peer-to-peer audio calls.</span></span> <span data-ttu-id="7d8e3-192">이 필드를 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 음성 및 비디오 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-192">When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d8e3-193"><strong>총 피어 투 피어 오디오 세션 시간 (분)</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-193"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="7d8e3-194">아니요</span><span class="sxs-lookup"><span data-stu-id="7d8e3-194">No</span></span></p></td>
<td><p><span data-ttu-id="7d8e3-195">피어 투 피어 오디오 세션에 소요 된 총 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-195">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="7d8e3-196">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 음성 및 비디오 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-196">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d8e3-197"><strong>평균 피어 투 피어 오디오 세션 시간 (분)</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-197"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="7d8e3-198">아니요</span><span class="sxs-lookup"><span data-stu-id="7d8e3-198">No</span></span></p></td>
<td><p><span data-ttu-id="7d8e3-199">피어 투 피어 오디오 세션에 소요 된 평균 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-199">Average amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="7d8e3-200">총 오디오 세션 시간을 총 오디오 세션 수로 나누어서 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-200">Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d8e3-201"><strong>총 피어 투 피어 비디오 세션</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-201"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7d8e3-202">아니요</span><span class="sxs-lookup"><span data-stu-id="7d8e3-202">No</span></span></p></td>
<td><p><span data-ttu-id="7d8e3-203">총 피어 투 피어 비디오 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-203">Total number of peer-to-peer video calls.</span></span> <span data-ttu-id="7d8e3-204">비디오 세션은 오디오 세션으로도 계산 되며, 각 비디오 세션은 하나의 비디오 세션 및 하나의 오디오 세션으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-204">Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session.</span></span> <span data-ttu-id="7d8e3-205">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 음성 및 비디오 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-205">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d8e3-206"><strong>총 피어 투 피어 비디오 세션 시간 (분)</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-206"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="7d8e3-207">아니요</span><span class="sxs-lookup"><span data-stu-id="7d8e3-207">No</span></span></p></td>
<td><p><span data-ttu-id="7d8e3-208">피어 투 피어 비디오 세션에서 소요 된 총 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-208">Total amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="7d8e3-209">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 음성 및 비디오 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-209">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d8e3-210"><strong>평균 피어 투 피어 비디오 세션 시간 (분)</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-210"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="7d8e3-211">아니요</span><span class="sxs-lookup"><span data-stu-id="7d8e3-211">No</span></span></p></td>
<td><p><span data-ttu-id="7d8e3-212">피어 투 피어 비디오 세션에 소요 된 평균 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-212">Average amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="7d8e3-213">총 비디오 세션 시간을 총 비디오 세션 수로 나누면 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-213">Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d8e3-214"><strong>총 피어 투 피어 파일 전송 세션</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-214"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7d8e3-215">아니요</span><span class="sxs-lookup"><span data-stu-id="7d8e3-215">No</span></span></p></td>
<td><p><span data-ttu-id="7d8e3-216">파일 전송이 포함 된 총 피어 투 피어 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-216">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d8e3-217"><strong>총 피어 투 피어 응용 프로그램 공유 세션</strong></span><span class="sxs-lookup"><span data-stu-id="7d8e3-217"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="7d8e3-218">아니요</span><span class="sxs-lookup"><span data-stu-id="7d8e3-218">No</span></span></p></td>
<td><p><span data-ttu-id="7d8e3-219">응용 프로그램 공유가 포함 된 총 피어 투 피어 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7d8e3-219">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

