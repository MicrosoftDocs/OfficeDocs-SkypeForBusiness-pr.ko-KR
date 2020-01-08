---
title: 'Lync Server 2013: 통화 허용 제어 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f31159742757b7ef8b6889b7961bad747b1f6d2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="dbbbe-102">Lync Server 2013의 통화 허용 제어 보고서</span><span class="sxs-lookup"><span data-stu-id="dbbbe-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbbbe-103">_**마지막으로 수정한 주제:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="dbbbe-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="dbbbe-104">통화 허용 제어 보고서는 통화 허용 제어에서 설정한 제한 하에서 수행한 피어 투 피어 및 회의 세션에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="dbbbe-105">Microsoft Lync Server 2010에서 도입 된 통화 허용 제어는 관리자가 대역폭 제약 조건을 기준으로 통신 세션을 허용 하거나 허용 하지 않는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="dbbbe-106">예를 들어, 관리자는 음성 및 영상 통화에 사용할 수 있는 대역폭의 양을 제한 하는 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="dbbbe-107">해당 대역폭 제한에 도달 하면 현재 통화 중 하나를 종료 하 고 필요한 네트워크 리소스를 해제할 때까지 새로운 음성 또는 영상 통화를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="dbbbe-108">통화 허용 컨트롤 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="dbbbe-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="dbbbe-109">모니터링 보고서 홈 페이지에서 통화 허용 제어 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-109">The Call Admission Control Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="dbbbe-110">통화 허용 제어 보고서에서 다음 보고서 중 하나로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-110">From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="dbbbe-111">회의 세부 정보 보고서 –이 보고서에 액세스 하려면 회의 세션에서 세부 정보 메트릭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="dbbbe-112">피어 투 피어 세션 세부 정보 보고서 –이 보고서에 액세스 하려면 피어 투 피어 세션에 대 한 세부 정보 메트릭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="dbbbe-113">통화 허용 제어 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="dbbbe-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="dbbbe-114">대역폭 부족으로 실패 한 통화 목록을 얻으려면 통화 범주 드롭다운 목록에서 통화 허용 제어로 인해 거부 된 통화를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-114">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list.</span></span> <span data-ttu-id="dbbbe-115">반환 되는 대부분의 통화는 진단 ID가 5 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-115">Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="dbbbe-116">대역폭이 부족 하 여 세션을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-116">Insufficient bandwidth to establish session.</span></span> <span data-ttu-id="dbbbe-117">PSTN re 경로를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-117">Attempt PSTN re-route.</span></span>

<span data-ttu-id="dbbbe-118">이것은 통화 허용 제어 제한 사항으로 인해 VoIP 네트워크에서 전화를 걸 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="dbbbe-119">필터가</span><span class="sxs-lookup"><span data-stu-id="dbbbe-119">Filters</span></span>

<span data-ttu-id="dbbbe-120">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="dbbbe-121">예를 들어, 통화 허용 제어 보고서를 사용 하면 호출을 시작한 사용자 또는 호출 하는 사용자에의 한 통화를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-121">For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called.</span></span> <span data-ttu-id="dbbbe-122">데이터 그룹화 방법을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-122">You can also choose how data should be grouped.</span></span> <span data-ttu-id="dbbbe-123">이 경우 통화는 시, 일, 주 또는 월로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-123">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="dbbbe-124">다음 표에는 통화 허용 컨트롤 보고서와 함께 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="dbbbe-125">통화 허용 제어 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="dbbbe-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbbbe-126">이름</span><span class="sxs-lookup"><span data-stu-id="dbbbe-126">Name</span></span></th>
<th><span data-ttu-id="dbbbe-127">설명</span><span class="sxs-lookup"><span data-stu-id="dbbbe-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbbbe-128"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-129">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-129">Start date/time for the time range.</span></span> <span data-ttu-id="dbbbe-130">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-130">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="dbbbe-131">오후 7/17/12012 1:00</span><span class="sxs-lookup"><span data-stu-id="dbbbe-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="dbbbe-132">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-132">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="dbbbe-133">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-133">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dbbbe-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="dbbbe-134">7/17/12012</span></span></p>
<p><span data-ttu-id="dbbbe-135">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="dbbbe-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dbbbe-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="dbbbe-136">7/13/2012</span></span></p>
<p><span data-ttu-id="dbbbe-137">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbbbe-138"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-139">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-139">End date/time for the time range.</span></span> <span data-ttu-id="dbbbe-140">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-140">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="dbbbe-141">오후 7/17/12012 1:00</span><span class="sxs-lookup"><span data-stu-id="dbbbe-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="dbbbe-142">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-142">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="dbbbe-143">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-143">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dbbbe-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="dbbbe-144">7/17/12012</span></span></p>
<p><span data-ttu-id="dbbbe-145">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="dbbbe-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dbbbe-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="dbbbe-146">7/13/2012</span></span></p>
<p><span data-ttu-id="dbbbe-147">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbbbe-148"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-149">등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-149">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="dbbbe-150">개별 풀을 선택 하거나 <strong>[모두]</strong> 를 클릭 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-150">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="dbbbe-151">이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-151">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbbbe-152"><strong>활동 유형</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-153">활동의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-153">Type of activity.</span></span> <span data-ttu-id="dbbbe-154">다음 활동 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-154">Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbbbe-155">모든</span><span class="sxs-lookup"><span data-stu-id="dbbbe-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="dbbbe-156">피어 투 피어</span><span class="sxs-lookup"><span data-stu-id="dbbbe-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="dbbbe-157">회의</span><span class="sxs-lookup"><span data-stu-id="dbbbe-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbbbe-158"><strong>통화 범주</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-159">CAC가 통화에 사용 된 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-159">Indicates the reason that CAC was used for the call.</span></span> <span data-ttu-id="dbbbe-160">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-160">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbbbe-161">모든</span><span class="sxs-lookup"><span data-stu-id="dbbbe-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="dbbbe-162">통화 허용 제어로 인해 통화가 거부 됨</span><span class="sxs-lookup"><span data-stu-id="dbbbe-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="dbbbe-163">통화 허용 제어로 인해 PSTN을 통해 통화가 전환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="dbbbe-164">피어 투 피어 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="dbbbe-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="dbbbe-165">다음 표에는 피어 투 피어 세션 (즉, 두 명의 참가자만 참여 하는 세션)에 대 한 호출 허용 제어 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="dbbbe-166">피어 투 피어 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="dbbbe-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbbbe-167">이름</span><span class="sxs-lookup"><span data-stu-id="dbbbe-167">Name</span></span></th>
<th><span data-ttu-id="dbbbe-168">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="dbbbe-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dbbbe-169">설명</span><span class="sxs-lookup"><span data-stu-id="dbbbe-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbbbe-170"><strong>도</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-171">아니요</span><span class="sxs-lookup"><span data-stu-id="dbbbe-171">No</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-172">이 항목을 클릭 하면 보고서에는 지정 된 세션에 대 한 피어 투 피어 세션 세부 정보 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbbbe-173"><strong>사용자의</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-174">예</span><span class="sxs-lookup"><span data-stu-id="dbbbe-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-175">세션을 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbbbe-176"><strong>사용자에 게</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-177">예</span><span class="sxs-lookup"><span data-stu-id="dbbbe-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-178">세션에 참가 하도록 초대 받은 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbbbe-179"><strong>형식을</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-180">예</span><span class="sxs-lookup"><span data-stu-id="dbbbe-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-181">세션 중 사용 된 통신 형식을 (오디오 및 비디오 등)</span><span class="sxs-lookup"><span data-stu-id="dbbbe-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbbbe-182"><strong>초대 시간</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-183">예</span><span class="sxs-lookup"><span data-stu-id="dbbbe-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-184">초기 세션 초대를 보낸 사람 사용자에 게 보낸 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbbbe-185"><strong>응답 시간</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-186">예</span><span class="sxs-lookup"><span data-stu-id="dbbbe-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-187">초대 수락을 받은 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbbbe-188"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-189">예</span><span class="sxs-lookup"><span data-stu-id="dbbbe-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-190">세션이 종료 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbbbe-191"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-192">예</span><span class="sxs-lookup"><span data-stu-id="dbbbe-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-193">오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-193">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="dbbbe-194">진단 헤더는 선택 사항으로,이 헤더를 포함 하지 않는 SIP 세션이 있을 수 있으며, 진단 Id는 일부 종류의 문제가 발생 하는 세션에 대해서만 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-194">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="dbbbe-195">회의 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="dbbbe-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="dbbbe-196">다음 표에서는 회의 세션 (즉, 세 명 이상의 참가자와 관련 된 세션)의 호출 허용 제어 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="dbbbe-197">회의 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="dbbbe-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbbbe-198">이름</span><span class="sxs-lookup"><span data-stu-id="dbbbe-198">Name</span></span></th>
<th><span data-ttu-id="dbbbe-199">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="dbbbe-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dbbbe-200">설명</span><span class="sxs-lookup"><span data-stu-id="dbbbe-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbbbe-201"><strong>컨퍼런스 URI</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-202">예</span><span class="sxs-lookup"><span data-stu-id="dbbbe-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-203">회의의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-203">Unique identifier for the conference.</span></span> <span data-ttu-id="dbbbe-204">이 항목을 클릭 하면 보고서에 개별 회의 참가자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-204">When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbbbe-205"><strong>구성 도우미</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-206">예</span><span class="sxs-lookup"><span data-stu-id="dbbbe-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-207">회의를 구성한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbbbe-208"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-209">예</span><span class="sxs-lookup"><span data-stu-id="dbbbe-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-210">에 지 서버를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbbbe-211"><strong>시작 시간</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-212">예</span><span class="sxs-lookup"><span data-stu-id="dbbbe-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-213">회의가 시작 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbbbe-214"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-215">예</span><span class="sxs-lookup"><span data-stu-id="dbbbe-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-216">회의가 종료 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="dbbbe-217">개별 회의 참가자에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="dbbbe-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="dbbbe-218">다음 표에는 개별 회의 참가자를 위해 통화 허용 제어 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="dbbbe-219">개별 회의 참가자에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="dbbbe-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbbbe-220">이름</span><span class="sxs-lookup"><span data-stu-id="dbbbe-220">Name</span></span></th>
<th><span data-ttu-id="dbbbe-221">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="dbbbe-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="dbbbe-222">설명</span><span class="sxs-lookup"><span data-stu-id="dbbbe-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbbbe-223"><strong>역할인</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-224">아니요</span><span class="sxs-lookup"><span data-stu-id="dbbbe-224">No</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-225">회의 참가자가 재생 한 역할 (예: 발표자)입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbbbe-226"><strong>참여자</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-227">아니요</span><span class="sxs-lookup"><span data-stu-id="dbbbe-227">No</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-228">회의 참가자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbbbe-229"><strong>연결성</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-230">아니요</span><span class="sxs-lookup"><span data-stu-id="dbbbe-230">No</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-231">참가자의 네트워크 연결 (일반적으로 내부 또는 외부에서)</span><span class="sxs-lookup"><span data-stu-id="dbbbe-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbbbe-232"><strong>모달</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-233">아니요</span><span class="sxs-lookup"><span data-stu-id="dbbbe-233">No</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-234">회의 유형 (예: A/V 회의).</span><span class="sxs-lookup"><span data-stu-id="dbbbe-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbbbe-235"><strong>참가 시간</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-236">아니요</span><span class="sxs-lookup"><span data-stu-id="dbbbe-236">No</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-237">참가자가 회의에 참가 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbbbe-238"><strong>휴가 시간</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-239">아니요</span><span class="sxs-lookup"><span data-stu-id="dbbbe-239">No</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-240">참가자가 회의를 남겨진 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbbbe-241"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="dbbbe-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="dbbbe-242">아니요</span><span class="sxs-lookup"><span data-stu-id="dbbbe-242">No</span></span></p></td>
<td><p><span data-ttu-id="dbbbe-243">오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-243">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="dbbbe-244">진단 헤더는 선택 사항으로,이 헤더를 포함 하지 않는 SIP 세션이 있을 수 있으며, 진단 Id는 일부 종류의 문제가 발생 하는 세션에 대해서만 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbbbe-244">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

