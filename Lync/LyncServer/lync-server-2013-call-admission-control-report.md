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
ms.openlocfilehash: 60a51a27a4aa5c6d0df5970da669bc1c67f068c2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a><span data-ttu-id="2e941-102">Lync Server 2013의 통화 허용 제어 보고서</span><span class="sxs-lookup"><span data-stu-id="2e941-102">Call Admission Control Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e941-103">_**마지막으로 수정 된 항목:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="2e941-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="2e941-104">통화 허용 제어 보고서는 통화 허용 제어에서 설정한 제한에 따라 수행 된 피어-투-피어 및 회의 세션에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-104">The Call Admission Control Report provides information about peer-to-peer and conferencing sessions that were conducted under restrictions set in place by Call Admission Control.</span></span> <span data-ttu-id="2e941-105">Microsoft Lync Server 2010에서 도입 된 통화 허용 제어는 관리자가 대역폭 제약 조건에 따라 통신 세션을 허용 하거나 허용 하지 않는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-105">Call Admission Control, introduced in Microsoft Lync Server 2010, provides a way for administrators to allow (or not allow) communication sessions based on bandwidth constraints.</span></span> <span data-ttu-id="2e941-106">예를 들어 관리자는 음성 및 화상 통화에 사용할 수 있는 대역폭을 제한 하는 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-106">For example, administrators can create policies that impose a limit on the amount of bandwidth available for voice and video calls.</span></span> <span data-ttu-id="2e941-107">해당 대역폭 제한에 도달한 경우 현재 통화 중 하나가 종료 되어 필요한 네트워크 리소스를 사용할 수 있을 때까지 새로운 음성 또는 화상 통화를 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-107">If that bandwidth limit has been reached, then no new voice or video calls can be placed until one of the current calls has ended and freed up the required network resources.</span></span>

<div>

## <a name="accessing-the-call-admission-control-report"></a><span data-ttu-id="2e941-108">통화 허용 제어 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="2e941-108">Accessing the Call Admission Control Report</span></span>

<span data-ttu-id="2e941-109">통화 허용 제어 보고서는 모니터링 보고서 홈 페이지에서 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-109">The Call Admission Control Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="2e941-110">통화 허용 제어 보고서에서 다음 보고서 중 하나로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-110">From the Call Admission Control Report you can drill down to either of the following reports:</span></span>

  - <span data-ttu-id="2e941-111">전화 회의 정보 보고서 –이 보고서에 액세스 하려면 전화 회의 세션에서 세부 정보 메트릭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-111">Conference Detail Report – To access this report, click the Details metric from a conference session.</span></span>

  - <span data-ttu-id="2e941-112">피어 투 피어 세션 정보 보고서-이 보고서에 액세스 하려면 피어 투 피어 세션에 대 한 세부 정보 메트릭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-112">Peer-to-Peer Session Detail Report – To access this report, click the Details metric for a peer-to-peer session.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a><span data-ttu-id="2e941-113">통화 허용 제어 보고서를 가장 효율적으로 활용</span><span class="sxs-lookup"><span data-stu-id="2e941-113">Making the Best Use of the Call Admission Control Report</span></span>

<span data-ttu-id="2e941-114">대역폭 부족으로 인해 실패 한 통화 목록을 가져오려면 통화 범주 드롭다운 목록에서 통화 허용 제어로 인해 거부 된 통화를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-114">To get a list of calls that failed because of insufficient bandwidth, select Calls rejected because of call admission control from the Call category dropdown list.</span></span> <span data-ttu-id="2e941-115">반환 되는 호출의 대부분은 진단 ID가 5 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-115">Most of the returned calls will likely have a diagnostic ID of 5:</span></span>

<span data-ttu-id="2e941-116">대역폭 부족으로 세션을 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-116">Insufficient bandwidth to establish session.</span></span> <span data-ttu-id="2e941-117">PSTN 다시 라우트를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-117">Attempt PSTN re-route.</span></span>

<span data-ttu-id="2e941-118">이는 통화 허용 제어 제한으로 인해 VoIP 네트워크에서 통화가 수행 되지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-118">That indicates that Call Admission Control limitations were preventing the call from being made on the VoIP network.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2e941-119">필터</span><span class="sxs-lookup"><span data-stu-id="2e941-119">Filters</span></span>

<span data-ttu-id="2e941-120">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="2e941-121">예를 들어 통화 허용 제어 보고서를 사용 하면 전화를 건 사용자가 통화를 필터링 하거나, 통화를 시작한 사용자가 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-121">For example, the Call Admission Control Report enables you to filter calls by the user who initiated the call or by the user who was being called.</span></span> <span data-ttu-id="2e941-122">또한 데이터의 그룹 지정 방식도 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-122">You can also choose how data should be grouped.</span></span> <span data-ttu-id="2e941-123">이 경우 통화는 시간, 일, 주 및 월별로 그룹이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-123">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="2e941-124">다음 표에서는 통화 허용 제어 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-124">The following table lists the filters that you can use with the Call Admission Control Report.</span></span>

### <a name="call-admission-control-report-filters"></a><span data-ttu-id="2e941-125">통화 허용 제어 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="2e941-125">Call Admission Control Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e941-126">이름</span><span class="sxs-lookup"><span data-stu-id="2e941-126">Name</span></span></th>
<th><span data-ttu-id="2e941-127">설명</span><span class="sxs-lookup"><span data-stu-id="2e941-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e941-128"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-p106">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2e941-131">2012/7/17 오후 1:00</span><span class="sxs-lookup"><span data-stu-id="2e941-131">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="2e941-p107">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2e941-134">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="2e941-134">7/17/12012</span></span></p>
<p><span data-ttu-id="2e941-135">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2e941-136">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="2e941-136">7/13/2012</span></span></p>
<p><span data-ttu-id="2e941-137">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e941-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-p108">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2e941-141">2012/7/17 오후 1:00</span><span class="sxs-lookup"><span data-stu-id="2e941-141">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="2e941-p109">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2e941-144">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="2e941-144">7/17/12012</span></span></p>
<p><span data-ttu-id="2e941-145">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2e941-146">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="2e941-146">7/13/2012</span></span></p>
<p><span data-ttu-id="2e941-147">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e941-148"><strong>그룹</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-p110">등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-p110">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e941-152"><strong>활동 유형</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-152"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-153">활동 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-153">Type of activity.</span></span> <span data-ttu-id="2e941-154">다음 활동 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-154">Select one of the following activities:</span></span></p>
<ul>
<li><p><span data-ttu-id="2e941-155">모든</span><span class="sxs-lookup"><span data-stu-id="2e941-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="2e941-156">피어-투-피어</span><span class="sxs-lookup"><span data-stu-id="2e941-156">Peer-to-Peer</span></span></p></li>
<li><p><span data-ttu-id="2e941-157">전화</span><span class="sxs-lookup"><span data-stu-id="2e941-157">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e941-158"><strong>통화 범주</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-158"><strong>Call category</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-159">CAC가 통화에 사용 된 이유를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-159">Indicates the reason that CAC was used for the call.</span></span> <span data-ttu-id="2e941-160">다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-160">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2e941-161">모든</span><span class="sxs-lookup"><span data-stu-id="2e941-161">[All]</span></span></p></li>
<li><p><span data-ttu-id="2e941-162">통화 허용 제어로 인해 거부 된 통화</span><span class="sxs-lookup"><span data-stu-id="2e941-162">Call rejected because of call admission control</span></span></p></li>
<li><p><span data-ttu-id="2e941-163">통화 허용 제어로 인해 PSTN을 통해 착신 전환</span><span class="sxs-lookup"><span data-stu-id="2e941-163">Calls rerouted through PSTN because of call admission control</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="2e941-164">피어 투 피어 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="2e941-164">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="2e941-165">다음 표에서는 피어 투 피어 세션 (즉, 참가자가 두 개만 포함 된 세션)에 대해 통화 허용 제어 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-165">The following table lists the information provided in the Call Admission Control Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="2e941-166">피어 투 피어 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="2e941-166">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e941-167">이름</span><span class="sxs-lookup"><span data-stu-id="2e941-167">Name</span></span></th>
<th><span data-ttu-id="2e941-168">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="2e941-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2e941-169">설명</span><span class="sxs-lookup"><span data-stu-id="2e941-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e941-170"><strong>사항은</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-170"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-171">아니요</span><span class="sxs-lookup"><span data-stu-id="2e941-171">No</span></span></p></td>
<td><p><span data-ttu-id="2e941-172">이 항목을 클릭 하면 보고서에 지정 된 세션에 대 한 피어 투 피어 세션 세부 정보 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-172">When you click this item, the report shows you a Peer-to-Peer Session Detail Report for the specified session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e941-173"><strong>시작 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-173"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-174">예</span><span class="sxs-lookup"><span data-stu-id="2e941-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="2e941-175">세션을 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-175">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e941-176"><strong>대상 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-176"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-177">예</span><span class="sxs-lookup"><span data-stu-id="2e941-177">Yes</span></span></p></td>
<td><p><span data-ttu-id="2e941-178">세션에 참가 하도록 초대 된 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-178">SIP address of the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e941-179"><strong>형식</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-179"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-180">예</span><span class="sxs-lookup"><span data-stu-id="2e941-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="2e941-181">세션 중에 사용 된 통신 형식 (예: 오디오 및 비디오)입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-181">Communication modalities (such as audio and video) that were used during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e941-182"><strong>초대 시간</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-182"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-183">예</span><span class="sxs-lookup"><span data-stu-id="2e941-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="2e941-184">보낸 사람 사용자에 게 초기 세션 초대가 전송 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-184">Date and time the initial session invitation was sent to the From user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e941-185"><strong>응답 시간</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-185"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-186">예</span><span class="sxs-lookup"><span data-stu-id="2e941-186">Yes</span></span></p></td>
<td><p><span data-ttu-id="2e941-187">초대 수락이 수신 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-187">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e941-188"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-188"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-189">예</span><span class="sxs-lookup"><span data-stu-id="2e941-189">Yes</span></span></p></td>
<td><p><span data-ttu-id="2e941-190">세션이 종료 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-190">Date and time that the session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e941-191"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-192">예</span><span class="sxs-lookup"><span data-stu-id="2e941-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="2e941-p113">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다. 진단 헤더는 선택 사항이며(이러한 헤더를 포함하지 않는 SIP 세션도 가능함) 진단 ID는 일부 유형의 문제가 발생한 세션에 대해서만 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="2e941-195">회의 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="2e941-195">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="2e941-196">다음 표에서는 회의 세션 (즉, 참가자가 세 명 이상인 세션)에 대해 통화 허용 제어 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-196">The following table lists the information provided in the Call Admission Control Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="2e941-197">회의 세션에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="2e941-197">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e941-198">이름</span><span class="sxs-lookup"><span data-stu-id="2e941-198">Name</span></span></th>
<th><span data-ttu-id="2e941-199">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="2e941-199">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2e941-200">설명</span><span class="sxs-lookup"><span data-stu-id="2e941-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e941-201"><strong>전화 회의 URI</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-201"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-202">예</span><span class="sxs-lookup"><span data-stu-id="2e941-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="2e941-203">전화 회의에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-203">Unique identifier for the conference.</span></span> <span data-ttu-id="2e941-204">이 항목을 클릭 하면 보고서에 개별 회의 참가자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-204">When you click this item, the report shows the individual conference participants.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e941-205"><strong>구성 도우미</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-205"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-206">예</span><span class="sxs-lookup"><span data-stu-id="2e941-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="2e941-207">회의를 구성한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-207">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e941-208"><strong>그룹</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-208"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-209">예</span><span class="sxs-lookup"><span data-stu-id="2e941-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="2e941-210">전화 회의에서 사용 되는에 지 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-210">Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e941-211"><strong>시작 시간</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-211"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-212">예</span><span class="sxs-lookup"><span data-stu-id="2e941-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="2e941-213">전화 회의가 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-213">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e941-214"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-214"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-215">예</span><span class="sxs-lookup"><span data-stu-id="2e941-215">Yes</span></span></p></td>
<td><p><span data-ttu-id="2e941-216">회의가 종료된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-216">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="2e941-217">개별 회의 참가자에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="2e941-217">Metrics for Individual Conference Participants</span></span>

<span data-ttu-id="2e941-218">다음 표에서는 개별 회의 참가자에 대해 통화 허용 제어 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-218">The following table lists the information provided in the Call Admission Control Report for individual conference participants.</span></span>

### <a name="metrics-for-individual-conference-participants"></a><span data-ttu-id="2e941-219">개별 회의 참가자에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="2e941-219">Metrics for Individual Conference Participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2e941-220">이름</span><span class="sxs-lookup"><span data-stu-id="2e941-220">Name</span></span></th>
<th><span data-ttu-id="2e941-221">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="2e941-221">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2e941-222">설명</span><span class="sxs-lookup"><span data-stu-id="2e941-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e941-223"><strong>역할</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-223"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-224">아니요</span><span class="sxs-lookup"><span data-stu-id="2e941-224">No</span></span></p></td>
<td><p><span data-ttu-id="2e941-225">전화 회의 참가자가 수행하는 역할(예: 발표자)입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-225">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e941-226"><strong>조직</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-226"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-227">아니요</span><span class="sxs-lookup"><span data-stu-id="2e941-227">No</span></span></p></td>
<td><p><span data-ttu-id="2e941-228">회의 참가자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-228">SIP address of the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e941-229"><strong>연결</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-229"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-230">아니요</span><span class="sxs-lookup"><span data-stu-id="2e941-230">No</span></span></p></td>
<td><p><span data-ttu-id="2e941-231">참가자의 네트워크 연결(일반적으로 내부 발신 또는 외부 발신)입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-231">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e941-232"><strong>형식</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-232"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-233">아니요</span><span class="sxs-lookup"><span data-stu-id="2e941-233">No</span></span></p></td>
<td><p><span data-ttu-id="2e941-234">회의 유형 (예: A/V 회의)입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-234">Conference type (for example, A/V conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e941-235"><strong>참가 시간</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-235"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-236">아니요</span><span class="sxs-lookup"><span data-stu-id="2e941-236">No</span></span></p></td>
<td><p><span data-ttu-id="2e941-237">참가자가 전화 회의에 참가한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-237">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e941-238"><strong>나간 시간</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-238"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-239">아니요</span><span class="sxs-lookup"><span data-stu-id="2e941-239">No</span></span></p></td>
<td><p><span data-ttu-id="2e941-240">참가자가 전화 회의에서 나간 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-240">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e941-241"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="2e941-241"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="2e941-242">아니요</span><span class="sxs-lookup"><span data-stu-id="2e941-242">No</span></span></p></td>
<td><p><span data-ttu-id="2e941-p115">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다. 진단 헤더는 선택 사항이며(이러한 헤더를 포함하지 않는 SIP 세션도 가능함) 진단 ID는 일부 유형의 문제가 발생한 세션에 대해서만 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e941-p115">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

