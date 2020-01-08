---
title: 'Lync Server 2013: 미디어 품질 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Summary Report
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615012(v=OCS.15)
ms:contentKeyID: 48184776
ms.date: 06/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c967c6d6b120c73cb933281d4edb17be1868900
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-summary-report-in-lync-server-2013"></a><span data-ttu-id="3a01d-102">Lync Server 2013의 미디어 품질 요약 보고서</span><span class="sxs-lookup"><span data-stu-id="3a01d-102">Media Quality Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a01d-103">_**마지막으로 수정한 주제:** 2016-06-29_</span><span class="sxs-lookup"><span data-stu-id="3a01d-103">_**Topic Last Modified:** 2016-06-29_</span></span>

<span data-ttu-id="3a01d-104">미디어 품질 요약 보고서는 조직의 통화 품질을 분석할 때 가장 좋은 방법일 수 있습니다 .이 보고서는 다음 범주로 분류 된 자세한 체감 품질 (환경 품질) 통화 메트릭을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-104">The Media Quality Summary Report is perhaps your best bet for analyzing call quality in your organization: this report provides detailed Quality of Experience (QoE) call metrics broken down into the following categories:</span></span>

  - <span data-ttu-id="3a01d-105">UC 피어 투 피어 통화 (예: Microsoft Lync 2013에서 Microsoft Lync 2013 통화)</span><span class="sxs-lookup"><span data-stu-id="3a01d-105">UC Peer to Peer Calls (such as a Microsoft Lync 2013 to Microsoft Lync 2013 call)</span></span>

  - <span data-ttu-id="3a01d-106">UC 회의 세션</span><span class="sxs-lookup"><span data-stu-id="3a01d-106">UC Conference Sessions</span></span>

  - <span data-ttu-id="3a01d-107">PSTN 회의 세션</span><span class="sxs-lookup"><span data-stu-id="3a01d-107">PSTN Conference Sessions</span></span>

  - <span data-ttu-id="3a01d-108">PSTN 통화: 미디어 바이패스</span><span class="sxs-lookup"><span data-stu-id="3a01d-108">PSTN Calls: Media Bypass</span></span>

  - <span data-ttu-id="3a01d-109">PSTN 통화 (비 바이패스): UC 레그</span><span class="sxs-lookup"><span data-stu-id="3a01d-109">PSTN Calls (Non-Bypass): UC Leg</span></span>

  - <span data-ttu-id="3a01d-110">PSTN 통화 (비 바이패스): 게이트웨이 다리</span><span class="sxs-lookup"><span data-stu-id="3a01d-110">PSTN Calls (Non-Bypass): Gateway Leg</span></span>

  - <span data-ttu-id="3a01d-111">기타 통화 형식</span><span class="sxs-lookup"><span data-stu-id="3a01d-111">Other Call Types</span></span>

<span data-ttu-id="3a01d-112">보고서를 처음 열면 이러한 각 범주에 대 한 요약 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-112">When you first open the report, you see summary information for each of these categories.</span></span> <span data-ttu-id="3a01d-113">보고서를 종료 하지 않고 각 범주를 확장 하 여 Office Communicator 2007 R2에서 Lync 2013로 만든 호출과 같은 하위 범주를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-113">Without leaving the report, you can expand each category to look at subcategories such as calls made from Office Communicator 2007 R2 to Lync 2013.</span></span> <span data-ttu-id="3a01d-114">그런 다음 하위 범주를 드릴 다운 하 여 해당 범주 내에서 발생 하는 각 통화에 대 한 세부 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-114">In turn, you can then drill down into these subcategories to see details about each call made within that subcategory.</span></span>

<span data-ttu-id="3a01d-115">Microsoft Lync Server 2013에서 미디어 품질 요약 보고서는 데이터를 음성 통화, 영상 통화, 응용 프로그램 공유 통화 등의 세 가지 통화 유형으로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-115">In Microsoft Lync Server 2013 the Media Quality Summary Report further breaks the data down into three call types: audio calls, video calls, and application sharing calls.</span></span> <span data-ttu-id="3a01d-116">각 통화 유형에는 보고서에 고유한 섹션, 그리고 자체 사용자 지정 호출 메트릭 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-116">Each call type has its own section in the report, and its own custom set of call metrics.</span></span>

<span data-ttu-id="3a01d-117">미디어 품질 요약 보고서를 사용 하면 유선 통화와 무선 통화, 내부 통화, 외부 통화 및 VPN 통화와 비 VPN 통화 간의 통화 음질을 비교할 수 있는 필터를 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-117">The Media Quality Summary Report also allows you to apply filters that enable you to compare the call quality of wired calls vs. wireless calls, internal calls vs. external calls, and VPN calls vs. non-VPN calls.</span></span>

<div>

## <a name="accessing-the-media-quality-summary-report"></a><span data-ttu-id="3a01d-118">미디어 품질 요약 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="3a01d-118">Accessing the Media Quality Summary Report</span></span>

<span data-ttu-id="3a01d-119">모니터링 보고서 홈 페이지에서 미디어 품질 요약 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-119">The Media Quality Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="3a01d-120">다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 통화 목록 보고서](lync-server-2013-call-list-report.md) 로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-120">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="3a01d-121">통화 볼륨</span><span class="sxs-lookup"><span data-stu-id="3a01d-121">Call volume</span></span>

  - <span data-ttu-id="3a01d-122">통화 불량 백분율</span><span class="sxs-lookup"><span data-stu-id="3a01d-122">Poor call percentage</span></span>

<span data-ttu-id="3a01d-123">또한 다음 오디오 통화 메트릭 중 하나를 클릭 하 여 미디어 품질 메트릭 배포 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-123">In addition, you can access the Media Quality Metrics Distribution Report by clicking any of the following audio call metrics:</span></span>

  - <span data-ttu-id="3a01d-124">왕복 (ms)</span><span class="sxs-lookup"><span data-stu-id="3a01d-124">Round trip (ms)</span></span>

  - <span data-ttu-id="3a01d-125">성능 저하 (SPECIALIST)</span><span class="sxs-lookup"><span data-stu-id="3a01d-125">Degradation (MOS)</span></span>

  - <span data-ttu-id="3a01d-126">패킷 손실</span><span class="sxs-lookup"><span data-stu-id="3a01d-126">Packet loss</span></span>

  - <span data-ttu-id="3a01d-127">지터 (ms)</span><span class="sxs-lookup"><span data-stu-id="3a01d-127">Jitter (ms)</span></span>

  - <span data-ttu-id="3a01d-128">Healer 숨겨진 비율</span><span class="sxs-lookup"><span data-stu-id="3a01d-128">Healer concealed ratio</span></span>

  - <span data-ttu-id="3a01d-129">Healer 늘이기 비율</span><span class="sxs-lookup"><span data-stu-id="3a01d-129">Healer stretched ratio</span></span>

  - <span data-ttu-id="3a01d-130">Healer 압축 비율</span><span class="sxs-lookup"><span data-stu-id="3a01d-130">Healer compressed ratio</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="3a01d-131">필터가</span><span class="sxs-lookup"><span data-stu-id="3a01d-131">Filters</span></span>

<span data-ttu-id="3a01d-132">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-132">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="3a01d-133">예를 들어 미디어 품질 요약 보고서를 사용 하면 액세스 형식 (즉, 간격 액세스와 외부 액세스) 또는 유선/무선 네트워크 연결을 통해 반환 된 데이터를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-133">For example, the Media Quality Summary Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection.</span></span> <span data-ttu-id="3a01d-134">데이터 그룹화 방법을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-134">You can also choose how data should be grouped.</span></span> <span data-ttu-id="3a01d-135">이 경우 통화는 시, 일, 주 또는 월로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-135">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="3a01d-136">다음 표에는 미디어 품질 요약 보고서에 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-136">The following table lists the filters that you can use with the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-filters"></a><span data-ttu-id="3a01d-137">미디어 품질 요약 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="3a01d-137">Media Quality Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a01d-138">이름</span><span class="sxs-lookup"><span data-stu-id="3a01d-138">Name</span></span></th>
<th><span data-ttu-id="3a01d-139">설명</span><span class="sxs-lookup"><span data-stu-id="3a01d-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-140"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-140"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-141">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-141">Start date/time for the time range.</span></span> <span data-ttu-id="3a01d-142">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-142">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="3a01d-143">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="3a01d-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3a01d-144">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-144">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="3a01d-145">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-145">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3a01d-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3a01d-146">7/7/2012</span></span></p>
<p><span data-ttu-id="3a01d-147">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="3a01d-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3a01d-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3a01d-148">7/3/2012</span></span></p>
<p><span data-ttu-id="3a01d-149">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-150"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-150"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-151">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-151">End date/time for the time range.</span></span> <span data-ttu-id="3a01d-152">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-152">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="3a01d-153">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="3a01d-153">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3a01d-154">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-154">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="3a01d-155">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-155">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3a01d-156">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3a01d-156">7/7/2012</span></span></p>
<p><span data-ttu-id="3a01d-157">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="3a01d-157">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3a01d-158">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3a01d-158">7/3/2012</span></span></p>
<p><span data-ttu-id="3a01d-159">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-159">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-160"><strong>Access 형식</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-160"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-161">전화를 걸 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-161">Indicates whether the client was logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="3a01d-162">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-162">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3a01d-163">모든</span><span class="sxs-lookup"><span data-stu-id="3a01d-163">[All]</span></span></p></li>
<li><p><span data-ttu-id="3a01d-164">내부용</span><span class="sxs-lookup"><span data-stu-id="3a01d-164">Internal</span></span></p></li>
<li><p><span data-ttu-id="3a01d-165">내부</span><span class="sxs-lookup"><span data-stu-id="3a01d-165">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-166"><strong>네트워크 유형</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-166"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-167">전화를 걸 때 클라이언트가 연결 된 네트워크의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-167">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="3a01d-168">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-168">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3a01d-169">모든</span><span class="sxs-lookup"><span data-stu-id="3a01d-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="3a01d-170">유</span><span class="sxs-lookup"><span data-stu-id="3a01d-170">Wired</span></span></p></li>
<li><p><span data-ttu-id="3a01d-171">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="3a01d-171">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-173">통화를 했을 때 외부 클라이언트가 VPN (가상 사설망) 연결을 사용 중인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-173">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="3a01d-174">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-174">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3a01d-175">모든</span><span class="sxs-lookup"><span data-stu-id="3a01d-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="3a01d-176">VPN</span><span class="sxs-lookup"><span data-stu-id="3a01d-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="3a01d-177">비 VPN</span><span class="sxs-lookup"><span data-stu-id="3a01d-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="3a01d-178">매트릭스</span><span class="sxs-lookup"><span data-stu-id="3a01d-178">Metrics</span></span>

<span data-ttu-id="3a01d-179">다음 표에는 미디어 품질 요약 보고서에서 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-179">The following table lists the information provided in the Media Quality Summary Report.</span></span>

### <a name="media-quality-summary-report-metrics-audio-call-summary"></a><span data-ttu-id="3a01d-180">미디어 품질 요약 보고서 메트릭: 오디오 통화 요약</span><span class="sxs-lookup"><span data-stu-id="3a01d-180">Media Quality Summary Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a01d-181">이름</span><span class="sxs-lookup"><span data-stu-id="3a01d-181">Name</span></span></th>
<th><span data-ttu-id="3a01d-182">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="3a01d-182">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3a01d-183">설명</span><span class="sxs-lookup"><span data-stu-id="3a01d-183">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-184"><strong>통화 형식/끝점 형식</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-184"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-185">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-185">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-186">이 항목을 클릭 하면 보고서에 해당 형식에 따른 호출에 대 한 자세한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-186">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="3a01d-187">통화 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-187">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="3a01d-188">UC 피어 투 피어 통화</span><span class="sxs-lookup"><span data-stu-id="3a01d-188">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="3a01d-189">UC 회의 세션</span><span class="sxs-lookup"><span data-stu-id="3a01d-189">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="3a01d-190">PSTN 회의 세션</span><span class="sxs-lookup"><span data-stu-id="3a01d-190">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="3a01d-191">PSTN 통화: 미디어 바이패스</span><span class="sxs-lookup"><span data-stu-id="3a01d-191">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="3a01d-192">PSTN 통화 (비 바이패스): UC 레그</span><span class="sxs-lookup"><span data-stu-id="3a01d-192">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="3a01d-193">PSTN 통화 (비 바이패스): 게이트웨이 다리</span><span class="sxs-lookup"><span data-stu-id="3a01d-193">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="3a01d-194">기타 통화 형식</span><span class="sxs-lookup"><span data-stu-id="3a01d-194">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-195"><strong>통화 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-195"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-196">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-196">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-197">통화 유형별 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-197">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-198"><strong>통화 불량 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-198"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-199">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-199">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-200">불량으로 분류 된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-200">Total number of calls classified as poor.</span></span> <span data-ttu-id="3a01d-201">잘못 된 통화는 측정 된 메트릭 중 적어도 하나가 허용 된 값 (예: 과도 한 지터)을 초과한 모든 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-201">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-202"><strong>통화 볼륨 (무선 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-202"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-203">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-203">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-204">무선 연결을 사용한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-204">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-205"><strong>통화 볼륨 (VPN 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-205"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-206">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-206">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-207">VPN 연결을 사용한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-207">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-208"><strong>통화 볼륨 (외부 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-208"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-209">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-209">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-210">외부 연결 (즉, 내부 네트워크 외부의 연결)을 사용한 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-210">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-211"><strong>왕복 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-211"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-212">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-212">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-213">다른 끝점으로 이동 하 고 나 서 다시 사용할 수 있는 RTP (실시간 전송 프로토콜) 패킷에 필요한 평균 양 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-213">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="3a01d-214">100 밀리초 이하의 왕복 시간은 허용 되는 품질로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-214">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="3a01d-215">많은 라운드트립 값은 국제 통화 라우팅, 라우팅 잘못 구성 또는 오버 로드 된 미디어 서버에 의해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-215">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server.</span></span> <span data-ttu-id="3a01d-216">왕복 시간이 높으면 양방향 실시간 음성 대화에서 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-216">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-217"><strong>성능 저하 (SPECIALIST)</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-217"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-218">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-218">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-219">통화 중에 발생 한 평균 SPECIALIST (의미 있는 평가 점수) 감소 금액입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-219">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="3a01d-220">성능 저하 값의 범위는 0.0 ~ 5.0의 최대값까지입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-220">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="3a01d-221">0.5 이하의 값은 허용 되는 저하를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-221">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="3a01d-222">지금까지 평균 옵션 점수는 사용자가 1 ~ 5의 배율로 통화 품질을 평가할 수 있도록 하 여 계산 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-222">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="3a01d-223">Lync server에서 Lync Server는 사용자가 전화를 평가한 방법을 예측 하는 알고리즘 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-223">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="3a01d-224">높은 성능 저하 값은 정체, 대역폭 부족, 무선 정체 또는 간섭 또는 오버 로드 된 미디어 서버 또는 끝점으로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-224">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="3a01d-225">품질이 높으면 오디오가 왜곡 되거나 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-225">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-226"><strong>패킷 손실</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-226"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-227">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-227">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-228">RTP 패킷 손실의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-228">Average rate of RTP packet loss.</span></span> <span data-ttu-id="3a01d-229">(패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 높은 손실률은 일반적으로 혼잡, 대역폭 부족, 무선 정체 또는 간섭 또는 오버 로드 된 미디어 서버 중에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-229">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="3a01d-230">패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-230">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-231"><strong>지터 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-231"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-232">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-232">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-233">RTP 패킷 도착 간에 감지 된 평균 지터.</span><span class="sxs-lookup"><span data-stu-id="3a01d-233">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="3a01d-234">(지터는 통화의 &quot;shakiness&quot; 을 측정 하는 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-234">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-235"><strong>Healer 숨겨진 비율</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-235"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-236">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-236">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-237">총 샘플 수에 대 한 총 숨겨진 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-237">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="3a01d-238">(숨겨진 오디오 샘플은 일반적으로 손실 된 네트워크 패킷으로 인해 발생 하는 갑작스런 전환을 매끄럽게 하는 데 사용 되는 기술입니다.) 값이 높으면 패킷 손실률 또는 지터로 인해 적용 되는 손실 concealment의 상당 부분이 왜곡 되거나 손실 되는 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-238">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-239"><strong>Healer 늘이기 비율</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-239"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-240">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-240">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-241">총 샘플 수에 대 한 총 스트레치 된 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-241">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="3a01d-242">(늘인 오디오는 손실 된 네트워크 패킷이 감지 될 때 통화 품질을 유지 하기 위해 확장 되어 있는 오디오입니다.) 값이 높으면 지터로 인해 발생 하는 샘플 스트레치의 상당 수준을 나타내고, 오디오는 로보틱 또는 왜곡 될 때 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-242">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-243"><strong>Healer 압축 비율</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-243"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-244">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-244">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-245">총 샘플 수에 대 한 압축 된 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-245">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="3a01d-246">(압축 오디오는 손실 된 네트워크 패킷이 감지 되었을 때 통화 품질을 유지 하기 위해 압축 된 오디오입니다.) 값이 높으면 지터로 인해 발생 하는 샘플 압축의 상당 부분이 표시 되 고 오디오의 가속 또는 왜곡이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-246">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-video-call-summary"></a><span data-ttu-id="3a01d-247">미디어 품질 요약 보고서 메트릭: 영상 통화 요약</span><span class="sxs-lookup"><span data-stu-id="3a01d-247">Media Quality Summary Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a01d-248">이름</span><span class="sxs-lookup"><span data-stu-id="3a01d-248">Name</span></span></th>
<th><span data-ttu-id="3a01d-249">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="3a01d-249">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3a01d-250">설명</span><span class="sxs-lookup"><span data-stu-id="3a01d-250">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-251"><strong>통화 형식/끝점 형식</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-251"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-252">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-252">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-253">이 항목을 클릭 하면 보고서에 해당 형식에 따른 호출에 대 한 자세한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-253">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="3a01d-254">통화 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-254">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="3a01d-255">UC 피어 투 피어 통화</span><span class="sxs-lookup"><span data-stu-id="3a01d-255">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="3a01d-256">UC 회의 세션</span><span class="sxs-lookup"><span data-stu-id="3a01d-256">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="3a01d-257">PSTN 회의 세션</span><span class="sxs-lookup"><span data-stu-id="3a01d-257">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="3a01d-258">PSTN 통화: 미디어 바이패스</span><span class="sxs-lookup"><span data-stu-id="3a01d-258">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="3a01d-259">PSTN 통화 (비 바이패스): UC 레그</span><span class="sxs-lookup"><span data-stu-id="3a01d-259">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="3a01d-260">PSTN 통화 (비 바이패스): 게이트웨이 다리</span><span class="sxs-lookup"><span data-stu-id="3a01d-260">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="3a01d-261">기타 통화 형식</span><span class="sxs-lookup"><span data-stu-id="3a01d-261">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-262"><strong>통화 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-262"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-263">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-263">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-264">통화 유형별 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-264">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-265"><strong>통화 불량 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-265"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-266">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-266">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-267">불량으로 분류 된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-267">Total number of calls classified as poor.</span></span> <span data-ttu-id="3a01d-268">잘못 된 통화는 측정 된 메트릭 중 적어도 하나가 허용 된 값 (예: 과도 한 지터)을 초과한 모든 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-268">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-269"><strong>통화 볼륨 (무선 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-269"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-270">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-270">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-271">무선 연결을 사용한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-271">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-272"><strong>통화 볼륨 (VPN 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-272"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-273">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-273">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-274">VPN 연결을 사용한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-274">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-275"><strong>통화 볼륨 (외부 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-275"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-276">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-276">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-277">외부 연결 (즉, 내부 네트워크 외부의 연결)을 사용한 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-277">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-278"><strong>평균 비트 전송률 (킬/초)</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-278"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-279">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-279">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-280">평균 비디오 비트 전송률 (초당 k b/초)입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-280">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-281"><strong>낮은 비트/속도 비율 (%)</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-281"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-282">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-282">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-283">비트 전송률이 낮은 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-283">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-284"><strong>아웃 바운드 패킷 손실</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-284"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-285">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-285">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-286">아웃 바운드 패킷에 대 한 RTP (리얼 표준시 Transport Protocol) 패킷 손실</span><span class="sxs-lookup"><span data-stu-id="3a01d-286">Real-Time Transport Protocol (RTP) packet loss for outbound packets.</span></span> <span data-ttu-id="3a01d-287">(패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 높은 손실률은 일반적으로 혼잡, 대역폭 부족, 무선 정체 또는 간섭 또는 오버 로드 된 미디어 서버 중에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-287">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="3a01d-288">패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-288">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-289"><strong>고정 프레임%</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-289"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-290">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-290">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-291">"고정 된" 프레임의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-291">Percentage of “frozen” frames.</span></span> <span data-ttu-id="3a01d-292">고정 프레임에서는 통화의 오디오 부분이 계속 진행 되는 동안 비디오가 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-292">In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-293"><strong>아웃 바운드 평균 프레임 속도</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-293"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-294">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-294">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-295">통화 중의 아웃 바운드 전송에 대 한 평균 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-295">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-296"><strong>인바운드 평균 프레임 속도</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-296"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-297">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-297">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-298">통화 중 들어오는 전송에 대 한 평균 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-298">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-299"><strong>인바운드 낮은 프레임 속도%</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-299"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-300">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-300">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-301">들어오는 비디오의 비트 전송률이 낮은 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-301">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-302"><strong>클라이언트 상태%</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-302"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a01d-303">통화 중에 클라이언트 장치에 대 한 상대 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-303">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="media-quality-summary-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="3a01d-304">미디어 품질 요약 보고서 메트릭: 응용 프로그램 공유 통화 요약</span><span class="sxs-lookup"><span data-stu-id="3a01d-304">Media Quality Summary Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a01d-305">이름</span><span class="sxs-lookup"><span data-stu-id="3a01d-305">Name</span></span></th>
<th><span data-ttu-id="3a01d-306">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="3a01d-306">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3a01d-307">설명</span><span class="sxs-lookup"><span data-stu-id="3a01d-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-308"><strong>통화 형식/끝점 형식</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-308"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-309">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-309">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-310">이 항목을 클릭 하면 보고서에 해당 형식에 따른 호출에 대 한 자세한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-310">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="3a01d-311">통화 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-311">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="3a01d-312">UC 피어 투 피어 통화</span><span class="sxs-lookup"><span data-stu-id="3a01d-312">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="3a01d-313">UC 회의 세션</span><span class="sxs-lookup"><span data-stu-id="3a01d-313">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="3a01d-314">PSTN 회의 세션</span><span class="sxs-lookup"><span data-stu-id="3a01d-314">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="3a01d-315">PSTN 통화: 미디어 바이패스</span><span class="sxs-lookup"><span data-stu-id="3a01d-315">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="3a01d-316">PSTN 통화 (비 바이패스): UC 레그</span><span class="sxs-lookup"><span data-stu-id="3a01d-316">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="3a01d-317">PSTN 통화 (비 바이패스): 게이트웨이 다리</span><span class="sxs-lookup"><span data-stu-id="3a01d-317">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="3a01d-318">기타 통화 형식</span><span class="sxs-lookup"><span data-stu-id="3a01d-318">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-319"><strong>통화 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-319"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-320">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-320">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-321">통화 유형별 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-321">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-322"><strong>통화 불량 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-322"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-323">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-323">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-324">불량으로 분류 된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-324">Total number of calls classified as poor.</span></span> <span data-ttu-id="3a01d-325">잘못 된 통화는 측정 된 메트릭 중 적어도 하나가 허용 된 값 (예: 과도 한 지터)을 초과한 모든 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-325">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-326"><strong>통화 볼륨 (무선 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-326"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-327">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-327">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-328">무선 연결을 사용한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-328">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-329"><strong>통화 볼륨 (VPN 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-329"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-330">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-330">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-331">VPN 연결을 사용한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-331">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-332"><strong>통화 볼륨 (외부 통화)</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-332"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-333">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-333">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-334">외부 연결 (즉, 내부 네트워크 외부의 연결)을 사용한 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-334">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-335"><strong>지터 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-335"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-336">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-336">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-337">RTP 패킷 도착 간에 감지 된 평균 지터.</span><span class="sxs-lookup"><span data-stu-id="3a01d-337">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="3a01d-338">(지터는 통화의 &quot;shakiness&quot; 을 측정 하는 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-338">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-339"><strong>평균 기준 단방향</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-339"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-340">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-340">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-341">두 미디어 끝점 사이의 단방향 지연과 평균을 비교한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-341">Average relative one-way delay between two media endpoints.</span></span> <span data-ttu-id="3a01d-342">이것은 단일 홉 대기 시간 측정입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-342">This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a01d-343"><strong>평균 .RDP 타일 처리 대기 시간</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-343"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-344">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-344">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-345">보기 세션 중에 회의 서버의 평균 RDP 타일 처리 대기 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-345">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="3a01d-346">평균 높음은 보기 환경의 지연 시간을 반영 하 고 네트워크 대기 시간을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-346">A high average reflects a longer delay in the viewing experience, and includes network latency.</span></span> <span data-ttu-id="3a01d-347">오버 로드 된 회의 서버는 평균 지연 시간을 겪을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-347">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a01d-348"><strong>총 spoiled 타일 비율 (%)</strong></span><span class="sxs-lookup"><span data-stu-id="3a01d-348"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="3a01d-349">아니요</span><span class="sxs-lookup"><span data-stu-id="3a01d-349">No</span></span></p></td>
<td><p><span data-ttu-id="3a01d-350">Spoiled RDP 타일의 총 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="3a01d-350">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

