---
title: 'Lync Server 2013: 미디어 품질 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89a5046ba15534d40c81e1e3b8a4f310873a9e1b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="2b49c-102">Lync Server 2013의 미디어 품질 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="2b49c-102">Media Quality Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b49c-103">_**마지막으로 수정 된 항목:** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="2b49c-103">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="2b49c-104">미디어 품질 요약 보고서는 조직에서 통화 품질을 분석하는 데 가장 많이 사용됩니다. 이 보고서는 다음 범주로 세분화된 자세한 QoE(체감 품질) 통화 메트릭을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-104">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="2b49c-105">UC 피어 투 피어 통화 (예: Microsoft Lync 2013 to Microsoft Lync 2013 call)</span><span class="sxs-lookup"><span data-stu-id="2b49c-105">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="2b49c-106">UC 회의 세션</span><span class="sxs-lookup"><span data-stu-id="2b49c-106">UC Conference Sessions</span></span>

  - <span data-ttu-id="2b49c-107">PSTN 회의 세션</span><span class="sxs-lookup"><span data-stu-id="2b49c-107">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="2b49c-108">PSTN 통화: 미디어 바이패스</span><span class="sxs-lookup"><span data-stu-id="2b49c-108">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="2b49c-109">PSTN 통화(바이패스 없음): UC 레그</span><span class="sxs-lookup"><span data-stu-id="2b49c-109">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="2b49c-110">PSTN 통화(바이패스 없음): 게이트웨이 레그</span><span class="sxs-lookup"><span data-stu-id="2b49c-110">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="2b49c-111">기타 통화 유형</span><span class="sxs-lookup"><span data-stu-id="2b49c-111">Other Call Types</span></span>

<span data-ttu-id="2b49c-112">보고서를 처음 열면 각 범주에 대한 요약 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-112">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="2b49c-113">보고서를 떠나지 않고 각 범주를 확장 하 여 Office Communicator 2007 R2에서 Lync 2013로 수행한 통화와 같은 하위 범주를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-113">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="2b49c-114">그런 다음 이러한 하위 범주로 드릴다운해서 해당 하위 범주 내에서 수행된 각 통화에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-114">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="2b49c-115">Microsoft Lync Server 2013에서는 미디어 품질 요약 보고서에서 데이터를 오디오 통화, 비디오 통화 및 응용 프로그램 공유 통화의 세 가지 통화 유형으로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-115">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="2b49c-116">각 통화 유형은 보고서에서 고유 섹션으로 표시되며 고유한 사용자 지정 통화 메트릭 집합을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-116">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="2b49c-117">미디어 품질 요약 보고서에서는 또한 유선 통화와 무선 통화, 내부 통화와 외부 통화, VPN 통화와 비 VPN 통화의 통화 품질 비교를 수행할 수 있도록 필터를 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-117">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="2b49c-118">미디어 품질 요약 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="2b49c-118">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="2b49c-119">미디어 품질 요약 보고서는 모니터링 보고서 홈 페이지에서 액세스됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-119">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="2b49c-120">[Lync Server 2013에서](lync-server-2013-call-list-report.md) 다음 메트릭 중 하나를 클릭 하 여 Call List Report로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="2b49c-121">통화량</span><span class="sxs-lookup"><span data-stu-id="2b49c-121">Call volume</span></span>

  - <span data-ttu-id="2b49c-122">불량 통화율</span><span class="sxs-lookup"><span data-stu-id="2b49c-122">Poor call percentage</span></span>

<span data-ttu-id="2b49c-123">또한 다음 오디오 통화 메트릭 중 하나를 클릭하여 미디어 품질 메트릭 분포 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-123">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="2b49c-124">왕복(밀리초)</span><span class="sxs-lookup"><span data-stu-id="2b49c-124">Round trip (ms)</span></span>

  - <span data-ttu-id="2b49c-125">저하(MOS)</span><span class="sxs-lookup"><span data-stu-id="2b49c-125">Degradation (MOS)</span></span>

  - <span data-ttu-id="2b49c-126">패킷 손실</span><span class="sxs-lookup"><span data-stu-id="2b49c-126">Packet loss</span></span>

  - <span data-ttu-id="2b49c-127">지터(밀리초)</span><span class="sxs-lookup"><span data-stu-id="2b49c-127">Jitter (ms)</span></span>

  - <span data-ttu-id="2b49c-128">힐러 숨김 비율</span><span class="sxs-lookup"><span data-stu-id="2b49c-128">Healer concealed ratio</span></span>

  - <span data-ttu-id="2b49c-129">힐러 늘임 비율</span><span class="sxs-lookup"><span data-stu-id="2b49c-129">Healer stretched ratio</span></span>

  - <span data-ttu-id="2b49c-130">힐러 압축 비율</span><span class="sxs-lookup"><span data-stu-id="2b49c-130">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2b49c-131">필터</span><span class="sxs-lookup"><span data-stu-id="2b49c-131">Filters</span></span>

<span data-ttu-id="2b49c-p104">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 미디어 품질 요약 보고서에서는 액세스 유형(즉, 내부 액세스와 외부 액세스) 또는 유선/무선 네트워크 연결 등의 조건에 따라 반환되는 데이터를 필터링할 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 통화는 시간, 일, 주 및 월별로 그룹이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="2b49c-136">다음 표에서는 미디어 품질 요약 보고서에서 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-136">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="2b49c-137">미디어 품질 요약 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="2b49c-137">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b49c-138">이름</span><span class="sxs-lookup"><span data-stu-id="2b49c-138">Name</span></span></th>
<th><span data-ttu-id="2b49c-139">설명</span><span class="sxs-lookup"><span data-stu-id="2b49c-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-140"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-p105">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2b49c-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2b49c-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2b49c-p106">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2b49c-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2b49c-146">7/7/2012</span></span></p>
<p><span data-ttu-id="2b49c-147">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2b49c-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2b49c-148">7/3/2012</span></span></p>
<p><span data-ttu-id="2b49c-149">주는 항상 일요일부터 토요일까지입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-150"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-p107">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2b49c-153">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2b49c-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2b49c-p108">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2b49c-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2b49c-156">7/7/2012</span></span></p>
<p><span data-ttu-id="2b49c-157">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2b49c-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2b49c-158">7/3/2012</span></span></p>
<p><span data-ttu-id="2b49c-159">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-160"><strong>액세스 유형</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-160"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-p109">통화가 시도되었을 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온되어 있는지를 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p109">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b49c-163">모든</span><span class="sxs-lookup"><span data-stu-id="2b49c-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="2b49c-164">Internal</span><span class="sxs-lookup"><span data-stu-id="2b49c-164">Internal</span></span></p></li>
<li><p><span data-ttu-id="2b49c-165">외부:</span><span class="sxs-lookup"><span data-stu-id="2b49c-165">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-166"><strong>네트워크 유형</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-166"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-p110">통화가 시도되었을 때 클라이언트가 연결된 네트워크의 유형을 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b49c-169">모든</span><span class="sxs-lookup"><span data-stu-id="2b49c-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="2b49c-170">유선</span><span class="sxs-lookup"><span data-stu-id="2b49c-170">Wired</span></span></p></li>
<li><p><span data-ttu-id="2b49c-171">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="2b49c-171">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-p111">통화가 시도되었을 때 외부 클라이언트가 VPN(가상 사설망) 연결을 사용 중이었는지를 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b49c-175">모든</span><span class="sxs-lookup"><span data-stu-id="2b49c-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="2b49c-176">VPN</span><span class="sxs-lookup"><span data-stu-id="2b49c-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="2b49c-177">비 VPN</span><span class="sxs-lookup"><span data-stu-id="2b49c-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="2b49c-178">선별한</span><span class="sxs-lookup"><span data-stu-id="2b49c-178">Metrics</span></span>

<span data-ttu-id="2b49c-179">다음 표에서는 미디어 품질 요약 보고서에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-179">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="2b49c-180">미디어 품질 요약 보고서 메트릭: 오디오 통화 요약</span><span class="sxs-lookup"><span data-stu-id="2b49c-180">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b49c-181">이름</span><span class="sxs-lookup"><span data-stu-id="2b49c-181">Name</span></span></th>
<th><span data-ttu-id="2b49c-182">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="2b49c-182">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2b49c-183">설명</span><span class="sxs-lookup"><span data-stu-id="2b49c-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-184"><strong>통화 유형/끝점 유형</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-184"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-185">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-185">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-p112">이 항목을 클릭하면 보고서에 해당 유형에 따른 통화 세부 정보가 표시됩니다. 통화 유형에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p112">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b49c-188">UC 피어 투 피어 통화</span><span class="sxs-lookup"><span data-stu-id="2b49c-188">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="2b49c-189">UC 회의 세션</span><span class="sxs-lookup"><span data-stu-id="2b49c-189">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2b49c-190">PSTN 회의 세션</span><span class="sxs-lookup"><span data-stu-id="2b49c-190">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2b49c-191">PSTN 통화: 미디어 바이패스</span><span class="sxs-lookup"><span data-stu-id="2b49c-191">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="2b49c-192">PSTN 통화(바이패스 없음): UC 레그</span><span class="sxs-lookup"><span data-stu-id="2b49c-192">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="2b49c-193">PSTN 통화(바이패스 없음): 게이트웨이 레그</span><span class="sxs-lookup"><span data-stu-id="2b49c-193">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="2b49c-194">기타 통화 유형</span><span class="sxs-lookup"><span data-stu-id="2b49c-194">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-195"><strong>통화량</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-195"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-196">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-196">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-197">통화 유형별 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-197">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-198"><strong>불량 통화율</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-198"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-199">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-199">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-p113">불량으로 분류된 총 통화 수입니다. 불량 통화는 측정된 메트릭 중 적어도 하나 이상이 허용 값을 초과하는 모든 통화입니다(예: 지터가 과도하게 발생한 통화).</span><span class="sxs-lookup"><span data-stu-id="2b49c-p113">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-202"><strong>통화량(무선 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-202"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-203">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-203">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-204">무선 연결이 사용된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-204">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-205"><strong>통화량(VPN 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-205"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-206">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-206">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-207">VPN 연결이 사용된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-207">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-208"><strong>통화량(외부 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-208"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-209">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-209">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-210">외부 연결이 사용된 통화 수입니다(예: 내부 네트워크 외부의 연결).</span><span class="sxs-lookup"><span data-stu-id="2b49c-210">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-211"><strong>왕복(밀리초)</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-211"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-212">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-212">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-p114">RTP(실시간 전송 프로토콜) 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 평균 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 100밀리초 미만 정도로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p114">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="2b49c-p115">국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p115">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-217"><strong>저하(MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-217"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-218">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-218">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-219">통화 중 발생한 MOS(평균 평가점) 저하의 평균 양입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-219">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="2b49c-220">저하 값의 범위는 0.0(낮음)에서 5.0(높음)까지입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-220">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="2b49c-221">값이 0.5이하이면 허용 가능한 저하 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-221">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="2b49c-222">현재까지 평균 평가점은 사용자가 1부터 5까지 통화 품질에 대한 점수를 스스로 매기게 하여 계산되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-222">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="2b49c-223">Lync Server에서 Lync Server는 알고리즘 집합을 사용 하 여 사용자가 통화를 평가 하는 방법을 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-223">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="2b49c-p117">정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버 또는 끝점의 과부하 등의 경우에는 저하 값이 높게 나타날 수 있습니다. 저하 값이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p117">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-226"><strong>패킷 손실</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-226"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-227">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-227">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-p118">RTP 패킷에 대한 평균 손실률입니다. (패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다.) 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p118">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-231"><strong>Jitter (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-231"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-232">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-232">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-233">RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-233">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="2b49c-234">(지터는 통화의 &quot;shakiness&quot; 을 측정 한 것입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-234">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-235"><strong>힐러 숨김 비율</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-235"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-236">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-236">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-p120">총 오디오 샘플 수에 대한 숨겨진 평균 오디오 샘플 비율입니다. (숨겨진 오디오 샘플은 손실된 네트워크 패킷으로 인해 발생하는 갑작스러운 전환을 매끄럽게 조정하기 위해 사용되는 기술입니다.) 값이 높으면 패킷 손실이나 지터로 인해 적용된 손실 숨김 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p120">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-239"><strong>힐러 늘임 비율</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-239"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-240">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-240">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-p121">총 오디오 샘플 수에 대한 늘어진 평균 오디오 샘플 비율입니다. (늘어진 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 연장되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 늘림 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p121">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-243"><strong>힐러 압축 비율</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-243"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-244">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-244">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-p122">총 샘플 수에 대한 압축된 평균 오디오 샘플 비율입니다. (압축된 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 압축되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 압축 수준이 높음을 의미하며 이로 인해 오디오가 빠르게 들리거나 왜곡됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p122">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="2b49c-247">미디어 품질 요약 보고서 메트릭: 비디오 통화 요약</span><span class="sxs-lookup"><span data-stu-id="2b49c-247">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b49c-248">이름</span><span class="sxs-lookup"><span data-stu-id="2b49c-248">Name</span></span></th>
<th><span data-ttu-id="2b49c-249">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="2b49c-249">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2b49c-250">설명</span><span class="sxs-lookup"><span data-stu-id="2b49c-250">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-251"><strong>통화 유형/끝점 유형</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-251"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-252">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-252">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-p123">이 항목을 클릭하면 보고서에 해당 유형에 따른 통화 세부 정보가 표시됩니다. 통화 유형에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p123">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b49c-255">UC 피어 투 피어 통화</span><span class="sxs-lookup"><span data-stu-id="2b49c-255">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="2b49c-256">UC 회의 세션</span><span class="sxs-lookup"><span data-stu-id="2b49c-256">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2b49c-257">PSTN 회의 세션</span><span class="sxs-lookup"><span data-stu-id="2b49c-257">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2b49c-258">PSTN 통화: 미디어 바이패스</span><span class="sxs-lookup"><span data-stu-id="2b49c-258">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="2b49c-259">PSTN 통화(바이패스 없음): UC 레그</span><span class="sxs-lookup"><span data-stu-id="2b49c-259">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="2b49c-260">PSTN 통화(바이패스 없음): 게이트웨이 레그</span><span class="sxs-lookup"><span data-stu-id="2b49c-260">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="2b49c-261">기타 통화 유형</span><span class="sxs-lookup"><span data-stu-id="2b49c-261">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-262"><strong>통화량</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-262"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-263">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-263">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-264">통화 유형별 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-264">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-265"><strong>불량 통화율</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-265"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-266">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-266">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-p124">불량으로 분류된 총 통화 수입니다. 불량 통화는 측정된 메트릭 중 적어도 하나 이상이 허용 값을 초과하는 모든 통화입니다(예: 지터가 과도하게 발생한 통화).</span><span class="sxs-lookup"><span data-stu-id="2b49c-p124">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-269"><strong>통화량(무선 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-269"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-270">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-270">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-271">무선 연결이 사용된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-271">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-272"><strong>통화량(VPN 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-272"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-273">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-273">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-274">VPN 연결이 사용된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-274">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-275"><strong>통화량(외부 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-275"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-276">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-276">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-277">외부 연결이 사용된 통화 수입니다(예: 내부 네트워크 외부의 연결).</span><span class="sxs-lookup"><span data-stu-id="2b49c-277">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-278"><strong>평균 비트 전송률(킬로비트/초)</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-278"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-279">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-279">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-280">비디오의 평균 비트 전송률(킬로비트/초)입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-280">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-281"><strong>낮은 비트 전송률 비율</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-281"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-282">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-282">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-283">비트 전송률이 낮은 통화의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-283">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-284"><strong>아웃바운드 패킷 손실</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-284"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-285">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-285">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-p125">아웃바운드 패킷에 대한 RTP(실시간 전송 프로토콜) 패킷 손실입니다. (패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다.) 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p125">Real-Time Transport Protocol (RTP) packet loss for outbound packets. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-289"><strong>고정 프레임 비율 %</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-289"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-290">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-290">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-p126">정지된 프레임의 비율입니다. 정지된 프레임에서는 통화의 오디오 부분이 계속되는 동안 비디오 진행이 멈춥니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p126">Percentage of “frozen” frames. In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-293"><strong>아웃바운드 평균 프레임 속도</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-293"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-294">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-294">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-295">통화 중 아웃바운드 전송의 평균 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-295">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-296"><strong>인바운드 평균 프레임 속도</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-296"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-297">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-297">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-298">통화 중 들어오는 전송의 평균 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-298">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-299"><strong>인바운드 낮은 프레임 속도 비율</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-299"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-300">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-300">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-301">수신 비디오의 비트 전송률이 낮은 통화의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-301">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-302"><strong>클라이언트 상태 비율</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-302"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2b49c-303">통화 중 클라이언트 장치의 상대적 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-303">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="2b49c-304">미디어 품질 요약 보고서 메트릭: 응용 프로그램 공유 통화 요약</span><span class="sxs-lookup"><span data-stu-id="2b49c-304">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b49c-305">이름</span><span class="sxs-lookup"><span data-stu-id="2b49c-305">Name</span></span></th>
<th><span data-ttu-id="2b49c-306">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="2b49c-306">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2b49c-307">설명</span><span class="sxs-lookup"><span data-stu-id="2b49c-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-308"><strong>통화 유형/끝점 유형</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-308"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-309">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-309">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-p127">이 항목을 클릭하면 보고서에 해당 유형에 따른 통화 세부 정보가 표시됩니다. 통화 유형에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p127">When you click this item, the report shows detailed information about calls based on that type. Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b49c-312">UC 피어 투 피어 통화</span><span class="sxs-lookup"><span data-stu-id="2b49c-312">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="2b49c-313">UC 회의 세션</span><span class="sxs-lookup"><span data-stu-id="2b49c-313">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2b49c-314">PSTN 회의 세션</span><span class="sxs-lookup"><span data-stu-id="2b49c-314">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="2b49c-315">PSTN 통화: 미디어 바이패스</span><span class="sxs-lookup"><span data-stu-id="2b49c-315">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="2b49c-316">PSTN 통화(바이패스 없음): UC 레그</span><span class="sxs-lookup"><span data-stu-id="2b49c-316">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="2b49c-317">PSTN 통화(바이패스 없음): 게이트웨이 레그</span><span class="sxs-lookup"><span data-stu-id="2b49c-317">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="2b49c-318">기타 통화 유형</span><span class="sxs-lookup"><span data-stu-id="2b49c-318">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-319"><strong>통화량</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-319"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-320">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-320">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-321">통화 유형별 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-321">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-322"><strong>불량 통화율</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-322"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-323">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-323">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-p128">불량으로 분류된 총 통화 수입니다. 불량 통화는 측정된 메트릭 중 적어도 하나 이상이 허용 값을 초과하는 모든 통화입니다(예: 지터가 과도하게 발생한 통화).</span><span class="sxs-lookup"><span data-stu-id="2b49c-p128">Total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-326"><strong>통화량(무선 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-326"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-327">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-327">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-328">무선 연결이 사용된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-328">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-329"><strong>통화량(VPN 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-329"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-330">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-330">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-331">VPN 연결이 사용된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-331">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-332"><strong>통화량(외부 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-332"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-333">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-333">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-334">외부 연결이 사용된 통화 수입니다(예: 내부 네트워크 외부의 연결).</span><span class="sxs-lookup"><span data-stu-id="2b49c-334">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-335"><strong>지터(밀리초)</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-335"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-336">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-336">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-337">RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-337">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="2b49c-338">(지터는 통화의 &quot;shakiness&quot; 을 측정 한 것입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-338">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-339"><strong>평균 상대 단방향</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-339"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-340">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-340">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-p130">두 미디어 끝점 간의 평균 상대 단방향 지연입니다. 이는 단일 홉 대기 시간 측정값입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-p130">Average relative one-way delay between two media endpoints. This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b49c-343"><strong>평균 RDP 타일 처리 대기 시간</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-343"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-344">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-344">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-345">보기 세션 동안 AS 회의 서버의 평균 RDP 타일 처리 대기 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-345">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="2b49c-346">평균이 높으면 보기 환경의 지연 시간이 길어지고 네트워크 대기 시간이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-346">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="2b49c-347">과부하 회의 서버에서 평균 지연 값이 더욱 높게 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-347">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b49c-348"><strong>총 손상 타일 비율</strong></span><span class="sxs-lookup"><span data-stu-id="2b49c-348"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="2b49c-349">아니요</span><span class="sxs-lookup"><span data-stu-id="2b49c-349">No</span></span></p></td>
<td><p><span data-ttu-id="2b49c-350">손상된 RDP 타일의 총 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="2b49c-350">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

