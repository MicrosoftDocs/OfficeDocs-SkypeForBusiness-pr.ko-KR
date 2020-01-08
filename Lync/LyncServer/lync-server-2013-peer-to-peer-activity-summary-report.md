---
title: 'Lync Server 2013: 피어 투 피어 작업 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62bdd1203db471de770ed56cf6377d7a3c651649
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="424d0-102">Lync Server 2013의 피어 투 피어 작업 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="424d0-102">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="424d0-103">_**마지막으로 수정한 주제:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="424d0-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="424d0-104">피어 투 피어 활동 요약 보고서는 피어 투 피어 통신 세션의 전체 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-104">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="424d0-105">피어 투 피어 세션에는 일반적으로 두 명의 사용자만 포함 되며 Lync Server 회의 서비스는 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-105">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="424d0-106">일반적으로 회의에는 두 명 이상의 사용자가 포함 되며 Microsoft Lync Server 2013 회의 서비스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-106">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="424d0-107">회의 활동이 회의 요약 보고서에 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-107">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="424d0-108">피어 투 피어 활동 요약 보고서를 통해 다음과 같은 질문에 대답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-108">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="424d0-109">사용자가 일반적인 날에 보내는 피어 투 피어 인스턴트 메시지의 수는 몇 개입니까?</span><span class="sxs-lookup"><span data-stu-id="424d0-109">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="424d0-110">사용자가 실제로 Lync Server 응용 프로그램 공유 및 파일 전송 기능을 활용 하 고 있나요?</span><span class="sxs-lookup"><span data-stu-id="424d0-110">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="424d0-111">사용자는 특정 시간에 네트워크가 느려지는 일을 complaining 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-111">Users have been complaining that the network seems slow at certain times of the day.</span></span> <span data-ttu-id="424d0-112">이러한 기간 동안 피어 투 피어 오디오 및 비디오 세션에 소요 되는 시간은 몇 분 정도 인가요?</span><span class="sxs-lookup"><span data-stu-id="424d0-112">How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="424d0-113">피어 투 피어 활동 요약 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="424d0-113">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="424d0-114">모니터링 보고서 홈 페이지에서 피어 투 피어 활동 요약 보고서에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-114">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="424d0-115">[Lync Server 2013에서](lync-server-2013-peer-to-peer-im-report.md) 다음 메트릭 중 하나를 클릭 하 여 피어 투 피어 IM 보고서를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-115">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="424d0-116">총 피어 투 피어 IM 세션</span><span class="sxs-lookup"><span data-stu-id="424d0-116">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="424d0-117">총 피어 투 피어 IM 메시지</span><span class="sxs-lookup"><span data-stu-id="424d0-117">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="424d0-118">마찬가지로 다음 메트릭 중 하나를 클릭 하 여 피어 투 피어 음성 및 비디오 보고서를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-118">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="424d0-119">총 피어 투 피어 오디오 세션</span><span class="sxs-lookup"><span data-stu-id="424d0-119">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="424d0-120">총 피어 투 피어 오디오 세션 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="424d0-120">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="424d0-121">총 피어 투 피어 오디오 세션</span><span class="sxs-lookup"><span data-stu-id="424d0-121">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="424d0-122">총 피어 투 피어 오디오 세션 시간 (분)</span><span class="sxs-lookup"><span data-stu-id="424d0-122">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="424d0-123">피어 투 피어 활동 요약 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="424d0-123">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="424d0-124">피어 투 피어 활동 요약 보고서 아래쪽에 총 피어 투 피어 IM 세션 및 총 피어 투 피어 IM 메시지 등의 메트릭에 대 한 합계를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-124">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages.</span></span> <span data-ttu-id="424d0-125">이렇게 하면 보고서 본문에서 찾은 상세 정보에 대 한 간략 한 요약이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-125">This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="424d0-126">필터가</span><span class="sxs-lookup"><span data-stu-id="424d0-126">Filters</span></span>

<span data-ttu-id="424d0-127">필터는 더욱 세밀 하 게 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-127">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="424d0-128">예를 들어 피어 투 피어 활동 요약 보고서를 사용 하 여 데이터를 그룹화 하는 방법을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-128">For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="424d0-129">이 경우 작업 시간은 시, 일, 주 또는 월로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-129">In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="424d0-130">다음 표에는 피어 투 피어 활동 요약 보고서에 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-130">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="424d0-131">피어 투 피어 작업 요약 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="424d0-131">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="424d0-132">이름</span><span class="sxs-lookup"><span data-stu-id="424d0-132">Name</span></span></th>
<th><span data-ttu-id="424d0-133">설명</span><span class="sxs-lookup"><span data-stu-id="424d0-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="424d0-134"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-134"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="424d0-135">시간 범위에 대 한 시작 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-135">Start date and time for the time range.</span></span> <span data-ttu-id="424d0-136">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-136">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="424d0-137">오후 7/17/12012 1:00</span><span class="sxs-lookup"><span data-stu-id="424d0-137">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="424d0-138">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-138">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="424d0-139">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-139">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="424d0-140">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="424d0-140">7/17/12012</span></span></p>
<p><span data-ttu-id="424d0-141">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="424d0-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="424d0-142">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="424d0-142">7/13/2012</span></span></p>
<p><span data-ttu-id="424d0-143">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="424d0-144"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-144"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="424d0-145">시간 범위의 종료 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-145">End date and time for the time range.</span></span> <span data-ttu-id="424d0-146">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-146">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="424d0-147">오후 7/17/12012 1:00</span><span class="sxs-lookup"><span data-stu-id="424d0-147">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="424d0-148">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-148">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="424d0-149">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-149">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="424d0-150">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="424d0-150">7/17/12012</span></span></p>
<p><span data-ttu-id="424d0-151">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="424d0-151">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="424d0-152">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="424d0-152">7/13/2012</span></span></p>
<p><span data-ttu-id="424d0-153">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-153">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="424d0-154"><strong>간격만</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-154"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="424d0-155">시간 간격.</span><span class="sxs-lookup"><span data-stu-id="424d0-155">Time interval.</span></span> <span data-ttu-id="424d0-156">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-156">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="424d0-157">매시간 (최대 25 시간 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="424d0-157">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="424d0-158">매일 (최대 31 일이 표시 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="424d0-158">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="424d0-159">주간 (최대 12 주를 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="424d0-159">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="424d0-160">월간 (최대 12 개월을 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="424d0-160">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="424d0-161">시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-161">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="424d0-162">예를 들어 시작 날짜가 7/17/12012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/12012 12:00 AM ~ 9/7/12012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-162">For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="424d0-163">매트릭스</span><span class="sxs-lookup"><span data-stu-id="424d0-163">Metrics</span></span>

<span data-ttu-id="424d0-164">다음 표에서는 피어 투 피어 활동 요약 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-164">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="424d0-165">피어 투 피어 작업 요약 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="424d0-165">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="424d0-166">이름</span><span class="sxs-lookup"><span data-stu-id="424d0-166">Name</span></span></th>
<th><span data-ttu-id="424d0-167">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="424d0-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="424d0-168">설명</span><span class="sxs-lookup"><span data-stu-id="424d0-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="424d0-169"><strong>마다</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-169"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="424d0-170"><strong>Daily</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-170"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="424d0-171"><strong>매주</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-171"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="424d0-172"><strong>월간</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-172"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="424d0-173">아니요</span><span class="sxs-lookup"><span data-stu-id="424d0-173">No</span></span></p></td>
<td><p><span data-ttu-id="424d0-174">필터 도구 모음에서 선택한 시간 간격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-174">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="424d0-175">해당 되는 경우 지정 된 시간 간격을 클릭 하 여 해당 간격에 대 한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-175">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="424d0-176">예를 들어 일일 기간을 사용 하는 경우 7/17/12012을 클릭 하면 해당 날짜에 대 한 사용자 등록 작업을 시간별로 분류 하 여 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-176">For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="424d0-177"><strong>총 피어 투 피어 세션</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-177"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="424d0-178">아니요</span><span class="sxs-lookup"><span data-stu-id="424d0-178">No</span></span></p></td>
<td><p><span data-ttu-id="424d0-179">세션 유형에 관계 없이 수행 된 총 피어 투 피어 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-179">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="424d0-180"><strong>총 피어 투 피어 IM 세션</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-180"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="424d0-181">아니요</span><span class="sxs-lookup"><span data-stu-id="424d0-181">No</span></span></p></td>
<td><p><span data-ttu-id="424d0-182">피어 투 피어 인스턴트 메시지 (IM) 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-182">Total number of peer-to-peer instant messaging (IM) sessions.</span></span> <span data-ttu-id="424d0-183">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 IM 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-183">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="424d0-184"><strong>총 피어 투 피어 IM 메시지</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-184"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="424d0-185">아니요</span><span class="sxs-lookup"><span data-stu-id="424d0-185">No</span></span></p></td>
<td><p><span data-ttu-id="424d0-186">피어 투 피어 세션에서 전송 된 총 인스턴트 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-186">Total number of instant messages sent in peer-to-peer sessions.</span></span> <span data-ttu-id="424d0-187">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 IM 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-187">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="424d0-188"><strong>총 피어 투 피어 오디오 세션</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-188"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="424d0-189">아니요</span><span class="sxs-lookup"><span data-stu-id="424d0-189">No</span></span></p></td>
<td><p><span data-ttu-id="424d0-190">총 피어 투 피어 오디오 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-190">Total number of peer-to-peer audio calls.</span></span> <span data-ttu-id="424d0-191">이 필드를 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 음성 및 비디오 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-191">When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="424d0-192"><strong>총 피어 투 피어 오디오 세션 시간 (분)</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-192"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="424d0-193">아니요</span><span class="sxs-lookup"><span data-stu-id="424d0-193">No</span></span></p></td>
<td><p><span data-ttu-id="424d0-194">피어 투 피어 오디오 세션에 소요 된 총 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-194">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="424d0-195">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 음성 및 비디오 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-195">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="424d0-196"><strong>평균 피어 투 피어 오디오 세션 시간 (분)</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-196"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="424d0-197">아니요</span><span class="sxs-lookup"><span data-stu-id="424d0-197">No</span></span></p></td>
<td><p><span data-ttu-id="424d0-198">피어 투 피어 오디오 세션에 소요 된 평균 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-198">Average amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="424d0-199">총 오디오 세션 시간을 총 오디오 세션 수로 나누는 방법으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-199">Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="424d0-200"><strong>총 피어 투 피어 비디오 세션</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-200"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="424d0-201">아니요</span><span class="sxs-lookup"><span data-stu-id="424d0-201">No</span></span></p></td>
<td><p><span data-ttu-id="424d0-202">총 피어 투 피어 영상 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-202">Total number of peer-to-peer video calls.</span></span> <span data-ttu-id="424d0-203">비디오 세션도 오디오 세션으로 계산 되며, 각 비디오 세션은 하나의 비디오 세션 및 하나의 오디오 세션으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-203">Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session.</span></span> <span data-ttu-id="424d0-204">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 음성 및 비디오 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-204">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="424d0-205"><strong>총 피어 투 피어 비디오 세션 시간 (분)</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-205"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="424d0-206">아니요</span><span class="sxs-lookup"><span data-stu-id="424d0-206">No</span></span></p></td>
<td><p><span data-ttu-id="424d0-207">피어 투 피어 비디오 세션에 소요 된 총 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-207">Total amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="424d0-208">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 음성 및 비디오 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-208">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="424d0-209"><strong>평균 피어 투 피어 비디오 세션 시간 (분)</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-209"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="424d0-210">아니요</span><span class="sxs-lookup"><span data-stu-id="424d0-210">No</span></span></p></td>
<td><p><span data-ttu-id="424d0-211">피어 투 피어 비디오 세션에서 소요 된 평균 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-211">Average amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="424d0-212">총 비디오 세션 시간을 총 비디오 세션 수로 나누는 방법으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-212">Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="424d0-213"><strong>총 피어 투 피어 파일 전송 세션</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-213"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="424d0-214">아니요</span><span class="sxs-lookup"><span data-stu-id="424d0-214">No</span></span></p></td>
<td><p><span data-ttu-id="424d0-215">파일 전송이 포함 된 총 피어 투 피어 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-215">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="424d0-216"><strong>총 피어 투 피어 응용 프로그램 공유 세션</strong></span><span class="sxs-lookup"><span data-stu-id="424d0-216"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="424d0-217">아니요</span><span class="sxs-lookup"><span data-stu-id="424d0-217">No</span></span></p></td>
<td><p><span data-ttu-id="424d0-218">응용 프로그램 공유가 포함 된 총 피어 투 피어 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="424d0-218">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

