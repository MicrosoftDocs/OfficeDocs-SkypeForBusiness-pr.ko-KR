---
title: 'Lync Server 2013: 통화 목록 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d9d437b32907108d5666ef9e1b175c170030585
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526295"
---
# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="70377-102">Lync Server 2013의 통화 목록 보고서</span><span class="sxs-lookup"><span data-stu-id="70377-102">Call List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70377-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="70377-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="70377-104">통화 목록 보고서는 조직 내부에서 걸거나 받는 개별 통화에 대한 QoE(체감 품질) 메트릭을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="70377-104">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="70377-105">보고되는 실제 메트릭은 통화 목록 보고서에 액세스하는 방식에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="70377-105">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="70377-106">예를 들어 [Lync Server 2013의 장치 보고서](lync-server-2013-device-report.md)에서 보고서를 열면 다음과 같은 메트릭 (장치 보고서에도 보고 되는 메트릭)이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-106">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="70377-107">발신자의 마이크</span><span class="sxs-lookup"><span data-stu-id="70377-107">Caller's microphone</span></span>

  - <span data-ttu-id="70377-108">발신자의 스피커</span><span class="sxs-lookup"><span data-stu-id="70377-108">Caller's speaker</span></span>

  - <span data-ttu-id="70377-109">수신자의 마이크</span><span class="sxs-lookup"><span data-stu-id="70377-109">Callee's microphone</span></span>

  - <span data-ttu-id="70377-110">수신자의 스피커</span><span class="sxs-lookup"><span data-stu-id="70377-110">Callee's speaker</span></span>

  - <span data-ttu-id="70377-111">음성 스위치 시간 비율</span><span class="sxs-lookup"><span data-stu-id="70377-111">Ratio of voice switch time</span></span>

<span data-ttu-id="70377-112">그러나 [Lync Server 2013의 위치 보고서](lync-server-2013-location-report.md)에서 통화 목록 보고서를 여는 경우에는 이러한 메트릭이 표시 되지 않습니다. 대신 다음과 같은 메트릭을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70377-112">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="70377-113">왕복(밀리초)</span><span class="sxs-lookup"><span data-stu-id="70377-113">Round trip (ms)</span></span>

  - <span data-ttu-id="70377-114">저하(MOS)</span><span class="sxs-lookup"><span data-stu-id="70377-114">Degradation (MOS)</span></span>

  - <span data-ttu-id="70377-115">패킷 손실</span><span class="sxs-lookup"><span data-stu-id="70377-115">Packet loss</span></span>

  - <span data-ttu-id="70377-116">지터(밀리초)</span><span class="sxs-lookup"><span data-stu-id="70377-116">Jitter (ms)</span></span>

<span data-ttu-id="70377-p102">위치 보고서에서는 이러한 메트릭이 보고되지만, 통화 목록 보고서에서 세부 정보 메트릭을 클릭하면 모든 통화에 대한 완전한 QoE 정보가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-p102">Those are the metrics reported on the Location Report. However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="70377-119">통화 목록 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="70377-119">Accessing the Call List Report</span></span>

<span data-ttu-id="70377-120">통화 목록 보고서는 다음 보고서에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70377-120">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="70377-121">[Lync Server 2013의 위치 보고서](lync-server-2013-location-report.md) (통화 량 또는 불량 통화 율 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="70377-121">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="70377-122">[Lync Server 2013의 장치 보고서](lync-server-2013-device-report.md) (통화 량 또는 불량 통화 율 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="70377-122">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="70377-123">[Lync Server 2013의 미디어 품질 요약 보고서](lync-server-2013-media-quality-summary-report.md) (통화 량 또는 불량 통화 율 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="70377-123">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="70377-124">[Lync server 2013의 서버 성능 보고서](lync-server-2013-server-performance-report.md) (통화 량 또는 불량 통화 율 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="70377-124">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="70377-125">통화 목록 보고서 내에서 세부 정보 메트릭을 클릭 하 여 [Lync Server 2013의 통화 정보 보고서](lync-server-2013-call-detail-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70377-125">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="70377-126">통화 목록 보고서의 효과적인 활용</span><span class="sxs-lookup"><span data-stu-id="70377-126">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="70377-127">통화 목록 보고서의 일부 메트릭(예: 음성 스위치 시간 비율)이 실제로 무엇을 측정하는지 기억할 수 없는 경우 해당 메트릭 레이블 위에 마우스를 놓으면 도구 설명이 나타나 메트릭에 대한 간단한 설명을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70377-127">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="70377-128">필터</span><span class="sxs-lookup"><span data-stu-id="70377-128">Filters</span></span>

<span data-ttu-id="70377-p103">없음. 통화 목록 보고서는 필터링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70377-p103">None. You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="70377-131">메트릭</span><span class="sxs-lookup"><span data-stu-id="70377-131">Metrics</span></span>

<span data-ttu-id="70377-132">다음 표에서는 각 통화에 대해 통화 목록 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="70377-132">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="70377-133">통화 목록 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="70377-133">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="70377-134">이름</span><span class="sxs-lookup"><span data-stu-id="70377-134">Name</span></span></th>
<th><span data-ttu-id="70377-135">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="70377-135">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="70377-136">설명</span><span class="sxs-lookup"><span data-stu-id="70377-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="70377-137"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="70377-137"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="70377-138">아니요</span><span class="sxs-lookup"><span data-stu-id="70377-138">No</span></span></p></td>
<td><p><span data-ttu-id="70377-139">이 항목을 클릭하면 보고서에 통화에 대한 추가 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-139">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70377-140"><strong>최초</strong></span><span class="sxs-lookup"><span data-stu-id="70377-140"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="70377-141">예</span><span class="sxs-lookup"><span data-stu-id="70377-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="70377-142">통화를 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="70377-142">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70377-143"><strong>피호출자</strong></span><span class="sxs-lookup"><span data-stu-id="70377-143"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="70377-144">예</span><span class="sxs-lookup"><span data-stu-id="70377-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="70377-145">통화를 받은 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="70377-145">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70377-146"><strong>시작 시간</strong></span><span class="sxs-lookup"><span data-stu-id="70377-146"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="70377-147">예</span><span class="sxs-lookup"><span data-stu-id="70377-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="70377-148">통화가 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="70377-148">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70377-149"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="70377-149"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="70377-150">예</span><span class="sxs-lookup"><span data-stu-id="70377-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="70377-151">통화가 종료된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="70377-151">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70377-152"><strong>발신자 사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="70377-152"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="70377-153">예</span><span class="sxs-lookup"><span data-stu-id="70377-153">Yes</span></span></p></td>
<td><p><span data-ttu-id="70377-154">통화를 시작한 사용자의 끝점에 사용된 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="70377-154">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70377-155"><strong>수신자 사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="70377-155"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="70377-156">예</span><span class="sxs-lookup"><span data-stu-id="70377-156">Yes</span></span></p></td>
<td><p><span data-ttu-id="70377-157">통화를 받은 사용자의 끝점에 사용된 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="70377-157">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70377-158"><strong>왕복(밀리초)</strong></span><span class="sxs-lookup"><span data-stu-id="70377-158"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="70377-159">예</span><span class="sxs-lookup"><span data-stu-id="70377-159">Yes</span></span></p></td>
<td><p><span data-ttu-id="70377-p104">RTP(실시간 전송 프로토콜) 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 평균 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 100밀리초 미만 정도로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-p104">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back. Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="70377-p105">국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="70377-p105">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70377-164"><strong>저하(MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="70377-164"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="70377-165">예</span><span class="sxs-lookup"><span data-stu-id="70377-165">Yes</span></span></p></td>
<td><p><span data-ttu-id="70377-166">통화 중 발생한 MOS(평균 평가점) 저하에 대한 평균값입니다.</span><span class="sxs-lookup"><span data-stu-id="70377-166">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="70377-167">저하 값의 범위는 0.0(낮음)에서 5.0(높음)까지입니다.</span><span class="sxs-lookup"><span data-stu-id="70377-167">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="70377-168">값이 0.5이하이면 허용 가능한 저하 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70377-168">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="70377-169">현재까지 평균 평가점은 사용자가 1부터 5까지 통화 품질에 대한 점수를 스스로 매기게 하여 계산되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70377-169">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="70377-170">Lync Server에서 Lync Server는 알고리즘 집합을 사용 하 여 사용자가 통화를 평가 하는 방법을 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="70377-170">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="70377-p107">정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버 또는 끝점의 과부하 등의 경우에는 저하 값이 높게 나타날 수 있습니다. 저하 값이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="70377-p107">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70377-173"><strong>패킷 손실</strong></span><span class="sxs-lookup"><span data-stu-id="70377-173"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="70377-174">예</span><span class="sxs-lookup"><span data-stu-id="70377-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="70377-p108">RTP 패킷에 대한 평균 손실률입니다. (패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다.) 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="70377-p108">Average rate of RTP packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70377-178"><strong>지터</strong></span><span class="sxs-lookup"><span data-stu-id="70377-178"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="70377-179">예</span><span class="sxs-lookup"><span data-stu-id="70377-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="70377-180">RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="70377-180">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="70377-181">(지터는 통화의 shakiness을 측정 한 것 &quot; &quot; 입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70377-181">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70377-182"><strong>힐러 숨김 비율</strong></span><span class="sxs-lookup"><span data-stu-id="70377-182"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="70377-183">예</span><span class="sxs-lookup"><span data-stu-id="70377-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="70377-p110">총 오디오 샘플 수에 대한 숨겨진 평균 오디오 샘플 비율입니다. (숨겨진 오디오 샘플은 손실된 네트워크 패킷으로 인해 발생하는 갑작스러운 전환을 매끄럽게 조정하기 위해 사용되는 기술입니다.) 값이 높으면 패킷 손실이나 지터로 인해 적용된 손실 숨김 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="70377-p110">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70377-186"><strong>힐러 늘임 비율</strong></span><span class="sxs-lookup"><span data-stu-id="70377-186"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="70377-187">예</span><span class="sxs-lookup"><span data-stu-id="70377-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="70377-p111">총 오디오 샘플 수에 대한 늘어진 평균 오디오 샘플 비율입니다. (늘어진 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 연장되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 늘림 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="70377-p111">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="70377-190"><strong>힐러 압축 비율</strong></span><span class="sxs-lookup"><span data-stu-id="70377-190"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="70377-191">예</span><span class="sxs-lookup"><span data-stu-id="70377-191">Yes</span></span></p></td>
<td><p><span data-ttu-id="70377-p112">총 샘플 수에 대한 압축된 평균 오디오 샘플 비율입니다. (압축된 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 압축되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 압축 수준이 높음을 의미하며 이로 인해 오디오가 빠르게 들리거나 왜곡됩니다.</span><span class="sxs-lookup"><span data-stu-id="70377-p112">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="70377-194"><strong>연결</strong></span><span class="sxs-lookup"><span data-stu-id="70377-194"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="70377-195">예</span><span class="sxs-lookup"><span data-stu-id="70377-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="70377-p113">무선 통신 링크의 유형입니다. 일반적으로 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="70377-p113">Type of wireless communication link. Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="70377-198">릴레이</span><span class="sxs-lookup"><span data-stu-id="70377-198">Relay</span></span></p></li>
<li><p><span data-ttu-id="70377-199">연결할</span><span class="sxs-lookup"><span data-stu-id="70377-199">Direct</span></span></p></li>
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

