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
ms.openlocfilehash: 46d61e01574945fe090d3fd9425133f9569bd111
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="a45ce-102">Lync Server 2013의 통화 허용 제어 보고서</span><span class="sxs-lookup"><span data-stu-id="a45ce-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a45ce-103">_**마지막으로 수정 된 항목:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="a45ce-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="a45ce-104">통화 허용 제어 보고서는 통화 허용 제어에서 설정한 제한에 따라 수행 된 피어-투-피어 및 회의 세션에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="a45ce-105">Microsoft Lync Server 2010에서 도입 된 통화 허용 제어는 관리자가 대역폭 제약 조건에 따라 통신 세션을 허용 하거나 허용 하지 않는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="a45ce-106">예를 들어 관리자는 음성 및 화상 통화에 사용할 수 있는 대역폭을 제한 하는 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="a45ce-107">해당 대역폭 제한에 도달한 경우 현재 통화 중 하나가 종료 되어 필요한 네트워크 리소스를 사용할 수 있을 때까지 새로운 음성 또는 화상 통화를 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="a45ce-108">통화 허용 제어 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="a45ce-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="a45ce-109">통화 허용 제어 보고서는 모니터링 보고서 홈 페이지에서 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-109">The Call Admission Control Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="a45ce-110">통화 허용 제어 보고서에서 다음 보고서 중 하나로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-110">From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="a45ce-111">전화 회의 정보 보고서 –이 보고서에 액세스 하려면 전화 회의 세션에서 세부 정보 메트릭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="a45ce-112">피어 투 피어 세션 정보 보고서-이 보고서에 액세스 하려면 피어 투 피어 세션에 대 한 세부 정보 메트릭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="a45ce-113">통화 허용 제어 보고서를 가장 효율적으로 활용</span><span class="sxs-lookup"><span data-stu-id="a45ce-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="a45ce-114">대역폭 부족으로 인해 실패 한 통화 목록을 가져오려면 통화 범주 드롭다운 목록에서 통화 허용 제어로 인해 거부 된 통화를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-114">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list.</span></span> <span data-ttu-id="a45ce-115">반환 되는 호출의 대부분은 진단 ID가 5 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-115">Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="a45ce-116">대역폭 부족으로 세션을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-116">Insufficient bandwidth to establish session.</span></span> <span data-ttu-id="a45ce-117">PSTN 다시 라우트를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-117">Attempt PSTN re-route.</span></span>

<span data-ttu-id="a45ce-118">이는 통화 허용 제어 제한으로 인해 VoIP 네트워크에서 통화가 수행 되지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="a45ce-119">필터</span><span class="sxs-lookup"><span data-stu-id="a45ce-119">Filters</span></span>

<span data-ttu-id="a45ce-120">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="a45ce-121">예를 들어 통화 허용 제어 보고서를 사용 하면 전화를 건 사용자가 통화를 필터링 하거나, 통화를 시작한 사용자가 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-121">For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called.</span></span> <span data-ttu-id="a45ce-122">또한 데이터의 그룹 지정 방식도 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-122">You can also choose how data should be grouped.</span></span> <span data-ttu-id="a45ce-123">이 경우 통화는 시간, 일, 주 및 월별로 그룹이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-123">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="a45ce-124">다음 표에서는 통화 허용 제어 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="a45ce-125">통화 허용 제어 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="a45ce-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a45ce-126">이름</span><span class="sxs-lookup"><span data-stu-id="a45ce-126">Name</span></span></th>
<th><span data-ttu-id="a45ce-127">설명</span><span class="sxs-lookup"><span data-stu-id="a45ce-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a45ce-128"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-p106">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a45ce-131">2012/7/17 오후 1:00</span><span class="sxs-lookup"><span data-stu-id="a45ce-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="a45ce-p107">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a45ce-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="a45ce-134">7/17/12012</span></span></p>
<p><span data-ttu-id="a45ce-135">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a45ce-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="a45ce-136">7/13/2012</span></span></p>
<p><span data-ttu-id="a45ce-137">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a45ce-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-p108">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a45ce-141">2012/7/17 오후 1:00</span><span class="sxs-lookup"><span data-stu-id="a45ce-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="a45ce-p109">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a45ce-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="a45ce-144">7/17/12012</span></span></p>
<p><span data-ttu-id="a45ce-145">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a45ce-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="a45ce-146">7/13/2012</span></span></p>
<p><span data-ttu-id="a45ce-147">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a45ce-148"><strong>그룹</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-p110">등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a45ce-152"><strong>활동 유형</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-153">활동 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-153">Type of activity.</span></span> <span data-ttu-id="a45ce-154">다음 활동 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-154">Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="a45ce-155">모든</span><span class="sxs-lookup"><span data-stu-id="a45ce-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="a45ce-156">피어-투-피어</span><span class="sxs-lookup"><span data-stu-id="a45ce-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="a45ce-157">전화</span><span class="sxs-lookup"><span data-stu-id="a45ce-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a45ce-158"><strong>통화 범주</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-159">CAC가 통화에 사용 된 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-159">Indicates the reason that CAC was used for the call.</span></span> <span data-ttu-id="a45ce-160">다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-160">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a45ce-161">모든</span><span class="sxs-lookup"><span data-stu-id="a45ce-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="a45ce-162">통화 허용 제어로 인해 거부 된 통화</span><span class="sxs-lookup"><span data-stu-id="a45ce-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="a45ce-163">통화 허용 제어로 인해 PSTN을 통해 착신 전환</span><span class="sxs-lookup"><span data-stu-id="a45ce-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="a45ce-164">피어 투 피어 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="a45ce-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="a45ce-165">다음 표에서는 피어 투 피어 세션 (즉, 참가자가 두 개만 포함 된 세션)에 대해 통화 허용 제어 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="a45ce-166">피어 투 피어 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="a45ce-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a45ce-167">이름</span><span class="sxs-lookup"><span data-stu-id="a45ce-167">Name</span></span></th>
<th><span data-ttu-id="a45ce-168">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="a45ce-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a45ce-169">설명</span><span class="sxs-lookup"><span data-stu-id="a45ce-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a45ce-170"><strong>사항은</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-171">아니요</span><span class="sxs-lookup"><span data-stu-id="a45ce-171">No</span></span></p></td>
<td><p><span data-ttu-id="a45ce-172">이 항목을 클릭 하면 보고서에 지정 된 세션에 대 한 피어 투 피어 세션 세부 정보 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a45ce-173"><strong>시작 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-174">예</span><span class="sxs-lookup"><span data-stu-id="a45ce-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="a45ce-175">세션을 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a45ce-176"><strong>대상 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-177">예</span><span class="sxs-lookup"><span data-stu-id="a45ce-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="a45ce-178">세션에 참가 하도록 초대 된 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a45ce-179"><strong>형식</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-180">예</span><span class="sxs-lookup"><span data-stu-id="a45ce-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="a45ce-181">세션 중에 사용 된 통신 형식 (예: 오디오 및 비디오)입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a45ce-182"><strong>초대 시간</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-183">예</span><span class="sxs-lookup"><span data-stu-id="a45ce-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="a45ce-184">보낸 사람 사용자에 게 초기 세션 초대가 전송 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a45ce-185"><strong>응답 시간</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-186">예</span><span class="sxs-lookup"><span data-stu-id="a45ce-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="a45ce-187">초대 수락이 수신 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a45ce-188"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-189">예</span><span class="sxs-lookup"><span data-stu-id="a45ce-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="a45ce-190">세션이 종료 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a45ce-191"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-192">예</span><span class="sxs-lookup"><span data-stu-id="a45ce-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="a45ce-p113">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다. 진단 헤더는 선택 사항이며(이러한 헤더를 포함하지 않는 SIP 세션도 가능함) 진단 ID는 일부 유형의 문제가 발생한 세션에 대해서만 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="a45ce-195">회의 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="a45ce-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="a45ce-196">다음 표에서는 회의 세션 (즉, 참가자가 세 명 이상인 세션)에 대해 통화 허용 제어 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="a45ce-197">회의 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="a45ce-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a45ce-198">이름</span><span class="sxs-lookup"><span data-stu-id="a45ce-198">Name</span></span></th>
<th><span data-ttu-id="a45ce-199">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="a45ce-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a45ce-200">설명</span><span class="sxs-lookup"><span data-stu-id="a45ce-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a45ce-201"><strong>전화 회의 URI</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-202">예</span><span class="sxs-lookup"><span data-stu-id="a45ce-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="a45ce-203">전화 회의에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-203">Unique identifier for the conference.</span></span> <span data-ttu-id="a45ce-204">이 항목을 클릭 하면 보고서에 개별 회의 참가자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-204">When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a45ce-205"><strong>구성 도우미</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-206">예</span><span class="sxs-lookup"><span data-stu-id="a45ce-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="a45ce-207">회의를 구성한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a45ce-208"><strong>그룹</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-209">예</span><span class="sxs-lookup"><span data-stu-id="a45ce-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="a45ce-210">전화 회의에서 사용 되는에 지 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a45ce-211"><strong>시작 시간</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-212">예</span><span class="sxs-lookup"><span data-stu-id="a45ce-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="a45ce-213">전화 회의가 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a45ce-214"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-215">예</span><span class="sxs-lookup"><span data-stu-id="a45ce-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="a45ce-216">회의가 종료된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="a45ce-217">개별 회의 참가자에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="a45ce-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="a45ce-218">다음 표에서는 개별 회의 참가자에 대해 통화 허용 제어 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="a45ce-219">개별 회의 참가자에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="a45ce-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a45ce-220">이름</span><span class="sxs-lookup"><span data-stu-id="a45ce-220">Name</span></span></th>
<th><span data-ttu-id="a45ce-221">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="a45ce-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a45ce-222">설명</span><span class="sxs-lookup"><span data-stu-id="a45ce-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a45ce-223"><strong>역할</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-224">아니요</span><span class="sxs-lookup"><span data-stu-id="a45ce-224">No</span></span></p></td>
<td><p><span data-ttu-id="a45ce-225">전화 회의 참가자가 수행하는 역할(예: 발표자)입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a45ce-226"><strong>조직</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-227">아니요</span><span class="sxs-lookup"><span data-stu-id="a45ce-227">No</span></span></p></td>
<td><p><span data-ttu-id="a45ce-228">회의 참가자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a45ce-229"><strong>연결</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-230">아니요</span><span class="sxs-lookup"><span data-stu-id="a45ce-230">No</span></span></p></td>
<td><p><span data-ttu-id="a45ce-231">참가자의 네트워크 연결(일반적으로 내부 발신 또는 외부 발신)입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a45ce-232"><strong>형식</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-233">아니요</span><span class="sxs-lookup"><span data-stu-id="a45ce-233">No</span></span></p></td>
<td><p><span data-ttu-id="a45ce-234">회의 유형 (예: A/V 회의)입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a45ce-235"><strong>참가 시간</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-236">아니요</span><span class="sxs-lookup"><span data-stu-id="a45ce-236">No</span></span></p></td>
<td><p><span data-ttu-id="a45ce-237">참가자가 전화 회의에 참가한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a45ce-238"><strong>나간 시간</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-239">아니요</span><span class="sxs-lookup"><span data-stu-id="a45ce-239">No</span></span></p></td>
<td><p><span data-ttu-id="a45ce-240">참가자가 전화 회의에서 나간 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a45ce-241"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="a45ce-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="a45ce-242">아니요</span><span class="sxs-lookup"><span data-stu-id="a45ce-242">No</span></span></p></td>
<td><p><span data-ttu-id="a45ce-p115">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다. 진단 헤더는 선택 사항이며(이러한 헤더를 포함하지 않는 SIP 세션도 가능함) 진단 ID는 일부 유형의 문제가 발생한 세션에 대해서만 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="a45ce-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

