---
title: 'Lync Server 2013: 통화 허용 제어 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff036a27149db4360a938fe2ce9d63c2718f4d94
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="e540b-102">Lync Server 2013의 통화 허용 제어 보고서</span><span class="sxs-lookup"><span data-stu-id="e540b-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e540b-103">_**마지막으로 수정한 주제:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="e540b-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="e540b-104">통화 허용 제어 보고서는 통화 허용 제어에서 설정한 제한 하에서 수행한 피어 투 피어 및 회의 세션에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="e540b-105">Microsoft Lync Server 2010에서 도입 된 통화 허용 제어는 관리자가 대역폭 제약 조건을 기준으로 통신 세션을 허용 하거나 허용 하지 않는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="e540b-106">예를 들어, 관리자는 음성 및 영상 통화에 사용할 수 있는 대역폭의 양을 제한 하는 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="e540b-107">해당 대역폭 제한에 도달 하면 현재 통화 중 하나를 종료 하 고 필요한 네트워크 리소스를 해제할 때까지 새로운 음성 또는 영상 통화를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="e540b-108">통화 허용 컨트롤 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="e540b-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="e540b-109">모니터링 보고서 홈 페이지에서 통화 허용 제어 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-109">The Call Admission Control Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="e540b-110">통화 허용 제어 보고서에서 다음 보고서 중 하나로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-110">From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="e540b-111">회의 세부 정보 보고서 –이 보고서에 액세스 하려면 회의 세션에서 세부 정보 메트릭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="e540b-112">피어 투 피어 세션 세부 정보 보고서 –이 보고서에 액세스 하려면 피어 투 피어 세션에 대 한 세부 정보 메트릭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="e540b-113">통화 허용 제어 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="e540b-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="e540b-114">대역폭 부족으로 실패 한 통화 목록을 얻으려면 통화 범주 드롭다운 목록에서 통화 허용 제어로 인해 거부 된 통화를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-114">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list.</span></span> <span data-ttu-id="e540b-115">반환 되는 대부분의 통화는 진단 ID가 5 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-115">Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="e540b-116">대역폭이 부족 하 여 세션을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-116">Insufficient bandwidth to establish session.</span></span> <span data-ttu-id="e540b-117">PSTN re 경로를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-117">Attempt PSTN re-route.</span></span>

<span data-ttu-id="e540b-118">이것은 통화 허용 제어 제한 사항으로 인해 VoIP 네트워크에서 전화를 걸 수 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e540b-119">필터가</span><span class="sxs-lookup"><span data-stu-id="e540b-119">Filters</span></span>

<span data-ttu-id="e540b-120">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="e540b-121">예를 들어, 통화 허용 제어 보고서를 사용 하면 호출을 시작한 사용자 또는 호출 하는 사용자에의 한 통화를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-121">For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called.</span></span> <span data-ttu-id="e540b-122">데이터 그룹화 방법을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-122">You can also choose how data should be grouped.</span></span> <span data-ttu-id="e540b-123">이 경우 통화는 시, 일, 주 또는 월로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-123">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="e540b-124">다음 표에는 통화 허용 컨트롤 보고서와 함께 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="e540b-125">통화 허용 제어 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="e540b-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e540b-126">이름</span><span class="sxs-lookup"><span data-stu-id="e540b-126">Name</span></span></th>
<th><span data-ttu-id="e540b-127">설명</span><span class="sxs-lookup"><span data-stu-id="e540b-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e540b-128"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-129">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-129">Start date/time for the time range.</span></span> <span data-ttu-id="e540b-130">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-130">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e540b-131">오후 7/17/12012 1:00</span><span class="sxs-lookup"><span data-stu-id="e540b-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="e540b-132">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-132">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="e540b-133">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-133">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e540b-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="e540b-134">7/17/12012</span></span></p>
<p><span data-ttu-id="e540b-135">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="e540b-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e540b-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="e540b-136">7/13/2012</span></span></p>
<p><span data-ttu-id="e540b-137">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e540b-138"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-139">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-139">End date/time for the time range.</span></span> <span data-ttu-id="e540b-140">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-140">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e540b-141">오후 7/17/12012 1:00</span><span class="sxs-lookup"><span data-stu-id="e540b-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="e540b-142">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-142">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="e540b-143">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-143">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e540b-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="e540b-144">7/17/12012</span></span></p>
<p><span data-ttu-id="e540b-145">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="e540b-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e540b-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="e540b-146">7/13/2012</span></span></p>
<p><span data-ttu-id="e540b-147">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e540b-148"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-149">등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-149">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="e540b-150">개별 풀을 선택 하거나 <strong>[모두]</strong> 를 클릭 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-150">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="e540b-151">이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-151">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e540b-152"><strong>활동 유형</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-153">활동의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-153">Type of activity.</span></span> <span data-ttu-id="e540b-154">다음 활동 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-154">Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="e540b-155">모든</span><span class="sxs-lookup"><span data-stu-id="e540b-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="e540b-156">피어 투 피어</span><span class="sxs-lookup"><span data-stu-id="e540b-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="e540b-157">회의</span><span class="sxs-lookup"><span data-stu-id="e540b-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e540b-158"><strong>통화 범주</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-159">CAC가 통화에 사용 된 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-159">Indicates the reason that CAC was used for the call.</span></span> <span data-ttu-id="e540b-160">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-160">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e540b-161">모든</span><span class="sxs-lookup"><span data-stu-id="e540b-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="e540b-162">통화 허용 제어로 인해 통화가 거부 됨</span><span class="sxs-lookup"><span data-stu-id="e540b-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="e540b-163">통화 허용 제어로 인해 PSTN을 통해 통화가 전환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="e540b-164">피어 투 피어 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="e540b-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="e540b-165">다음 표에는 피어 투 피어 세션 (즉, 두 명의 참가자만 참여 하는 세션)에 대 한 호출 허용 제어 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="e540b-166">피어 투 피어 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="e540b-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e540b-167">이름</span><span class="sxs-lookup"><span data-stu-id="e540b-167">Name</span></span></th>
<th><span data-ttu-id="e540b-168">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e540b-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e540b-169">설명</span><span class="sxs-lookup"><span data-stu-id="e540b-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e540b-170"><strong>도</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-171">아니요</span><span class="sxs-lookup"><span data-stu-id="e540b-171">No</span></span></p></td>
<td><p><span data-ttu-id="e540b-172">이 항목을 클릭 하면 보고서에는 지정 된 세션에 대 한 피어 투 피어 세션 세부 정보 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e540b-173"><strong>사용자의</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-174">예</span><span class="sxs-lookup"><span data-stu-id="e540b-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="e540b-175">세션을 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e540b-176"><strong>사용자에 게</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-177">예</span><span class="sxs-lookup"><span data-stu-id="e540b-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="e540b-178">세션에 참가 하도록 초대 받은 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e540b-179"><strong>형식을</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-180">예</span><span class="sxs-lookup"><span data-stu-id="e540b-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="e540b-181">세션 중 사용 된 통신 형식을 (오디오 및 비디오 등)</span><span class="sxs-lookup"><span data-stu-id="e540b-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e540b-182"><strong>초대 시간</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-183">예</span><span class="sxs-lookup"><span data-stu-id="e540b-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="e540b-184">초기 세션 초대를 보낸 사람 사용자에 게 보낸 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e540b-185"><strong>응답 시간</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-186">예</span><span class="sxs-lookup"><span data-stu-id="e540b-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="e540b-187">초대 수락을 받은 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e540b-188"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-189">예</span><span class="sxs-lookup"><span data-stu-id="e540b-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="e540b-190">세션이 종료 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e540b-191"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-192">예</span><span class="sxs-lookup"><span data-stu-id="e540b-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="e540b-193">오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-193">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="e540b-194">진단 헤더는 선택 사항으로,이 헤더를 포함 하지 않는 SIP 세션이 있을 수 있으며, 진단 Id는 일부 종류의 문제가 발생 하는 세션에 대해서만 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-194">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="e540b-195">회의 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="e540b-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="e540b-196">다음 표에서는 회의 세션 (즉, 세 명 이상의 참가자와 관련 된 세션)의 호출 허용 제어 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="e540b-197">회의 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="e540b-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e540b-198">이름</span><span class="sxs-lookup"><span data-stu-id="e540b-198">Name</span></span></th>
<th><span data-ttu-id="e540b-199">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e540b-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e540b-200">설명</span><span class="sxs-lookup"><span data-stu-id="e540b-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e540b-201"><strong>컨퍼런스 URI</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-202">예</span><span class="sxs-lookup"><span data-stu-id="e540b-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="e540b-203">회의의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-203">Unique identifier for the conference.</span></span> <span data-ttu-id="e540b-204">이 항목을 클릭 하면 보고서에 개별 회의 참가자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-204">When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e540b-205"><strong>구성 도우미</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-206">예</span><span class="sxs-lookup"><span data-stu-id="e540b-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="e540b-207">회의를 구성한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e540b-208"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-209">예</span><span class="sxs-lookup"><span data-stu-id="e540b-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="e540b-210">에 지 서버를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e540b-211"><strong>시작 시간</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-212">예</span><span class="sxs-lookup"><span data-stu-id="e540b-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="e540b-213">회의가 시작 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e540b-214"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-215">예</span><span class="sxs-lookup"><span data-stu-id="e540b-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="e540b-216">회의가 종료 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="e540b-217">개별 회의 참가자에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="e540b-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="e540b-218">다음 표에는 개별 회의 참가자를 위해 통화 허용 제어 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="e540b-219">개별 회의 참가자에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="e540b-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e540b-220">이름</span><span class="sxs-lookup"><span data-stu-id="e540b-220">Name</span></span></th>
<th><span data-ttu-id="e540b-221">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e540b-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e540b-222">설명</span><span class="sxs-lookup"><span data-stu-id="e540b-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e540b-223"><strong>역할인</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-224">아니요</span><span class="sxs-lookup"><span data-stu-id="e540b-224">No</span></span></p></td>
<td><p><span data-ttu-id="e540b-225">회의 참가자가 재생 한 역할 (예: 발표자)입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e540b-226"><strong>참여자</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-227">아니요</span><span class="sxs-lookup"><span data-stu-id="e540b-227">No</span></span></p></td>
<td><p><span data-ttu-id="e540b-228">회의 참가자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e540b-229"><strong>연결성</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-230">아니요</span><span class="sxs-lookup"><span data-stu-id="e540b-230">No</span></span></p></td>
<td><p><span data-ttu-id="e540b-231">참가자의 네트워크 연결 (일반적으로 내부 또는 외부에서)</span><span class="sxs-lookup"><span data-stu-id="e540b-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e540b-232"><strong>모달</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-233">아니요</span><span class="sxs-lookup"><span data-stu-id="e540b-233">No</span></span></p></td>
<td><p><span data-ttu-id="e540b-234">회의 유형 (예: A/V 회의).</span><span class="sxs-lookup"><span data-stu-id="e540b-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e540b-235"><strong>참가 시간</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-236">아니요</span><span class="sxs-lookup"><span data-stu-id="e540b-236">No</span></span></p></td>
<td><p><span data-ttu-id="e540b-237">참가자가 회의에 참가 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e540b-238"><strong>휴가 시간</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-239">아니요</span><span class="sxs-lookup"><span data-stu-id="e540b-239">No</span></span></p></td>
<td><p><span data-ttu-id="e540b-240">참가자가 회의를 남겨진 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e540b-241"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="e540b-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="e540b-242">아니요</span><span class="sxs-lookup"><span data-stu-id="e540b-242">No</span></span></p></td>
<td><p><span data-ttu-id="e540b-243">오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-243">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="e540b-244">진단 헤더는 선택 사항으로,이 헤더를 포함 하지 않는 SIP 세션이 있을 수 있으며, 진단 Id는 일부 종류의 문제가 발생 하는 세션에 대해서만 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e540b-244">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

