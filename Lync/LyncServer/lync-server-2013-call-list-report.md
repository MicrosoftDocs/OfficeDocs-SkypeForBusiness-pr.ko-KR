---
title: 'Lync Server 2013: 통화 목록 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faf330a776f64534c02833a0472cfefea7f0998e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="7af48-102">Lync Server 2013의 통화 목록 보고서</span><span class="sxs-lookup"><span data-stu-id="7af48-102">Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7af48-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="7af48-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="7af48-104">통화 목록 보고서는 조직에서 생성 하 고 받은 개별 통화에 대 한 경력 (체감 품질) 메트릭을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-104">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="7af48-105">보고 되는 실제 메트릭은 통화 목록 보고서에 액세스 하는 방법에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-105">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="7af48-106">예를 들어 [Lync Server 2013에서 장치 보고서](lync-server-2013-device-report.md)의 보고서를 열면 장치 보고서에도 보고 되는 다음과 같은 메트릭이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-106">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="7af48-107">발신자의 마이크</span><span class="sxs-lookup"><span data-stu-id="7af48-107">Caller's microphone</span></span>

  - <span data-ttu-id="7af48-108">발신자의 강연자</span><span class="sxs-lookup"><span data-stu-id="7af48-108">Caller's speaker</span></span>

  - <span data-ttu-id="7af48-109">피호출자의 마이크</span><span class="sxs-lookup"><span data-stu-id="7af48-109">Callee's microphone</span></span>

  - <span data-ttu-id="7af48-110">피호출자의 강연자</span><span class="sxs-lookup"><span data-stu-id="7af48-110">Callee's speaker</span></span>

  - <span data-ttu-id="7af48-111">음성 전환 시간 비율</span><span class="sxs-lookup"><span data-stu-id="7af48-111">Ratio of voice switch time</span></span>

<span data-ttu-id="7af48-112">그러나 [Lync Server 2013의 위치 보고서](lync-server-2013-location-report.md)에서 통화 목록 보고서를 열면 이러한 메트릭이 표시 되지 않습니다. 대신 다음과 같은 메트릭이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-112">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="7af48-113">왕복 (ms)</span><span class="sxs-lookup"><span data-stu-id="7af48-113">Round trip (ms)</span></span>

  - <span data-ttu-id="7af48-114">성능 저하 (SPECIALIST)</span><span class="sxs-lookup"><span data-stu-id="7af48-114">Degradation (MOS)</span></span>

  - <span data-ttu-id="7af48-115">패킷 손실</span><span class="sxs-lookup"><span data-stu-id="7af48-115">Packet loss</span></span>

  - <span data-ttu-id="7af48-116">지터 (ms)</span><span class="sxs-lookup"><span data-stu-id="7af48-116">Jitter (ms)</span></span>

<span data-ttu-id="7af48-117">위치 보고서에 보고 되는 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-117">Those are the metrics reported on the Location Report.</span></span> <span data-ttu-id="7af48-118">그러나 통화 목록 보고서에서 언제 든 지 Detail metric을 클릭 하 여 모든 통화에 대 한 완전 한 체감 품질 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-118">However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="7af48-119">통화 목록 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="7af48-119">Accessing the Call List Report</span></span>

<span data-ttu-id="7af48-120">통화 목록 보고서는 다음 보고서에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-120">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="7af48-121">[Lync Server 2013의 위치 보고서](lync-server-2013-location-report.md) (통화 볼륨 또는 잘못 된 통화 백분율 메트릭을 클릭 하 여)</span><span class="sxs-lookup"><span data-stu-id="7af48-121">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="7af48-122">[Lync Server 2013의 장치 보고서](lync-server-2013-device-report.md) (통화 볼륨 또는 잘못 된 통화 백분율 메트릭을 클릭 하 여)</span><span class="sxs-lookup"><span data-stu-id="7af48-122">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="7af48-123">[Lync Server 2013의 미디어 품질 요약 보고서](lync-server-2013-media-quality-summary-report.md) (통화 볼륨 또는 잘못 된 통화 백분율 메트릭을 클릭 하 여)</span><span class="sxs-lookup"><span data-stu-id="7af48-123">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="7af48-124">[Lync server 2013의 서버 성능 보고서](lync-server-2013-server-performance-report.md) (통화 볼륨 또는 잘못 된 통화 백분율 메트릭을 클릭 하 여)</span><span class="sxs-lookup"><span data-stu-id="7af48-124">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="7af48-125">통화 목록 보고서 내에서 세부 정보 메트릭을 클릭 하 여 [Lync Server 2013의 통화 정보 보고서](lync-server-2013-call-detail-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-125">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="7af48-126">통화 목록 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="7af48-126">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="7af48-127">일부 통화 목록 보고서 메트릭 (예: 음성 전환 시간)이 실제로 측정 되는지 여부를 잊어버린 경우에는 미터법 레이블 위에 마우스를 놓습니다. 그런 다음 메트릭에 대 한 간략 한 설명을 제공 하는 도구 설명이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-127">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7af48-128">필터가</span><span class="sxs-lookup"><span data-stu-id="7af48-128">Filters</span></span>

<span data-ttu-id="7af48-129">없음.</span><span class="sxs-lookup"><span data-stu-id="7af48-129">None.</span></span> <span data-ttu-id="7af48-130">통화 목록 보고서는 필터링 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-130">You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7af48-131">매트릭스</span><span class="sxs-lookup"><span data-stu-id="7af48-131">Metrics</span></span>

<span data-ttu-id="7af48-132">다음 표에는 각 통화에 대 한 통화 목록 보고서에서 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-132">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="7af48-133">통화 목록 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="7af48-133">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7af48-134">이름</span><span class="sxs-lookup"><span data-stu-id="7af48-134">Name</span></span></th>
<th><span data-ttu-id="7af48-135">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="7af48-135">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7af48-136">설명</span><span class="sxs-lookup"><span data-stu-id="7af48-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7af48-137"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="7af48-137"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="7af48-138">아니요</span><span class="sxs-lookup"><span data-stu-id="7af48-138">No</span></span></p></td>
<td><p><span data-ttu-id="7af48-139">이 항목을 클릭 하면 보고서에 통화에 대 한 추가 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-139">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7af48-140"><strong>호출인</strong></span><span class="sxs-lookup"><span data-stu-id="7af48-140"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="7af48-141">예</span><span class="sxs-lookup"><span data-stu-id="7af48-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="7af48-142">통화를 시작한 사람의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-142">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7af48-143"><strong>피호출자</strong></span><span class="sxs-lookup"><span data-stu-id="7af48-143"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="7af48-144">예</span><span class="sxs-lookup"><span data-stu-id="7af48-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="7af48-145">호출 된 사람의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-145">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7af48-146"><strong>시작 시간</strong></span><span class="sxs-lookup"><span data-stu-id="7af48-146"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="7af48-147">예</span><span class="sxs-lookup"><span data-stu-id="7af48-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="7af48-148">통화가 시작 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-148">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7af48-149"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="7af48-149"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="7af48-150">예</span><span class="sxs-lookup"><span data-stu-id="7af48-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="7af48-151">통화가 종료 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-151">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7af48-152"><strong>발신자 사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="7af48-152"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="7af48-153">예</span><span class="sxs-lookup"><span data-stu-id="7af48-153">Yes</span></span></p></td>
<td><p><span data-ttu-id="7af48-154">통화를 시작한 사람의 끝점에서 사용 하는 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-154">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7af48-155"><strong>호출 수신자 사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="7af48-155"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="7af48-156">예</span><span class="sxs-lookup"><span data-stu-id="7af48-156">Yes</span></span></p></td>
<td><p><span data-ttu-id="7af48-157">호출 된 사람의 끝점에 사용 되는 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-157">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7af48-158"><strong>왕복 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="7af48-158"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="7af48-159">예</span><span class="sxs-lookup"><span data-stu-id="7af48-159">Yes</span></span></p></td>
<td><p><span data-ttu-id="7af48-160">다른 끝점으로 이동 하 고 나 서 다시 사용할 수 있는 RTP (실시간 전송 프로토콜) 패킷에 필요한 평균 양 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-160">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="7af48-161">100 밀리초 이하의 왕복 시간은 허용 되는 품질로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-161">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="7af48-162">많은 라운드트립 값은 국제 통화 라우팅, 라우팅 잘못 구성 또는 오버 로드 된 미디어 서버에 의해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-162">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server.</span></span> <span data-ttu-id="7af48-163">왕복 시간이 높으면 양방향 실시간 음성 대화에서 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-163">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7af48-164"><strong>성능 저하 (SPECIALIST)</strong></span><span class="sxs-lookup"><span data-stu-id="7af48-164"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="7af48-165">예</span><span class="sxs-lookup"><span data-stu-id="7af48-165">Yes</span></span></p></td>
<td><p><span data-ttu-id="7af48-166">통화 중에 발생 한 평균 SPECIALIST (의미 있는 평가 점수) 감소 금액입니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-166">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="7af48-167">성능 저하 값의 범위는 0.0 ~ 5.0의 최대값까지입니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-167">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="7af48-168">0.5 이하의 값은 허용 되는 저하를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-168">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="7af48-169">지금까지 평균 옵션 점수는 사용자가 1 ~ 5의 배율로 통화 품질을 평가할 수 있도록 하 여 계산 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-169">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="7af48-170">Lync server에서 Lync Server는 사용자가 전화를 평가한 방법을 예측 하는 알고리즘 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-170">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="7af48-171">높은 성능 저하 값은 정체, 대역폭 부족, 무선 정체 또는 간섭 또는 오버 로드 된 미디어 서버 또는 끝점으로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-171">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="7af48-172">품질이 높으면 오디오가 왜곡 되거나 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-172">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7af48-173"><strong>패킷 손실</strong></span><span class="sxs-lookup"><span data-stu-id="7af48-173"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="7af48-174">예</span><span class="sxs-lookup"><span data-stu-id="7af48-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="7af48-175">RTP 패킷 손실의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-175">Average rate of RTP packet loss.</span></span> <span data-ttu-id="7af48-176">(패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 높은 손실률은 일반적으로 혼잡, 대역폭 부족, 무선 정체 또는 간섭 또는 오버 로드 된 미디어 서버 중에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-176">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="7af48-177">패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-177">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7af48-178"><strong>지터</strong></span><span class="sxs-lookup"><span data-stu-id="7af48-178"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="7af48-179">예</span><span class="sxs-lookup"><span data-stu-id="7af48-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="7af48-180">RTP 패킷 도착 간에 감지 된 평균 지터.</span><span class="sxs-lookup"><span data-stu-id="7af48-180">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="7af48-181">(지터는 통화의 &quot;shakiness&quot; 을 측정 하는 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-181">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7af48-182"><strong>Healer 숨겨진 비율</strong></span><span class="sxs-lookup"><span data-stu-id="7af48-182"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="7af48-183">예</span><span class="sxs-lookup"><span data-stu-id="7af48-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="7af48-184">총 샘플 수에 대 한 총 숨겨진 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-184">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="7af48-185">(숨겨진 오디오 샘플은 일반적으로 손실 된 네트워크 패킷으로 인해 발생 하는 갑작스런 전환을 매끄럽게 하는 데 사용 되는 기술입니다.) 값이 높으면 패킷 손실률 또는 지터로 인해 적용 되는 손실 concealment의 상당 부분이 왜곡 되거나 손실 되는 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-185">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7af48-186"><strong>Healer 늘이기 비율</strong></span><span class="sxs-lookup"><span data-stu-id="7af48-186"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="7af48-187">예</span><span class="sxs-lookup"><span data-stu-id="7af48-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="7af48-188">총 샘플 수에 대 한 총 스트레치 된 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-188">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="7af48-189">(늘인 오디오는 손실 된 네트워크 패킷이 감지 될 때 통화 품질을 유지 하기 위해 확장 되어 있는 오디오입니다.) 값이 높으면 지터로 인해 발생 하는 샘플 스트레치의 상당 수준을 나타내고, 오디오는 로보틱 또는 왜곡 될 때 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-189">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7af48-190"><strong>Healer 압축 비율</strong></span><span class="sxs-lookup"><span data-stu-id="7af48-190"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="7af48-191">예</span><span class="sxs-lookup"><span data-stu-id="7af48-191">Yes</span></span></p></td>
<td><p><span data-ttu-id="7af48-192">총 샘플 수에 대 한 압축 된 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-192">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="7af48-193">(압축 오디오는 손실 된 네트워크 패킷이 감지 되었을 때 통화 품질을 유지 하기 위해 압축 된 오디오입니다.) 값이 높으면 지터로 인해 발생 하는 샘플 압축의 상당 부분이 표시 되 고 오디오의 가속 또는 왜곡이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-193">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7af48-194"><strong>연결성</strong></span><span class="sxs-lookup"><span data-stu-id="7af48-194"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="7af48-195">예</span><span class="sxs-lookup"><span data-stu-id="7af48-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="7af48-196">무선 통신 링크의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-196">Type of wireless communication link.</span></span> <span data-ttu-id="7af48-197">일반적으로 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7af48-197">Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7af48-198">오픈</span><span class="sxs-lookup"><span data-stu-id="7af48-198">Relay</span></span></p></li>
<li><p><span data-ttu-id="7af48-199">Dm</span><span class="sxs-lookup"><span data-stu-id="7af48-199">Direct</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

