---
title: 'Lync Server 2013: 통화 정보 보고서'
description: 'Lync Server 2013: 통화 정보 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d72ae6c1c1ec869041eee5b0dc35941c33609710
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561774"
---
# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="3da9b-103">Lync Server 2013의 통화 정보 보고서</span><span class="sxs-lookup"><span data-stu-id="3da9b-103">Call Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3da9b-104">_**마지막으로 수정 된 항목:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="3da9b-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="3da9b-105">통화 정보 보고서는 개별 통화에 대 한 자세한 정보를 제공 합니다. 이 보고서에는 다음과 같은 보고서 섹션으로 구분 된 Lync Server에서 수집한 거의 모든 품질 메트릭 및 통계가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-105">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="3da9b-106">통화 정보</span><span class="sxs-lookup"><span data-stu-id="3da9b-106">Call Information</span></span>

  - <span data-ttu-id="3da9b-107">발신자 장치 및 신호 품질 기준</span><span class="sxs-lookup"><span data-stu-id="3da9b-107">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="3da9b-108">수신자 장치 및 신호 품질 기준</span><span class="sxs-lookup"><span data-stu-id="3da9b-108">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="3da9b-109">발신자 클라이언트 이벤트</span><span class="sxs-lookup"><span data-stu-id="3da9b-109">Caller Client Event</span></span>

  - <span data-ttu-id="3da9b-110">수신자 클라이언트 이벤트</span><span class="sxs-lookup"><span data-stu-id="3da9b-110">Callee Client Event</span></span>

  - <span data-ttu-id="3da9b-111">오디오 스트림(발신자에게서 수신자 방향)</span><span class="sxs-lookup"><span data-stu-id="3da9b-111">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="3da9b-112">비디오 스트림(발신자에게서 수신자 방향)</span><span class="sxs-lookup"><span data-stu-id="3da9b-112">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="3da9b-113">오디오 스트림(수신자에게서 발신자 방향)</span><span class="sxs-lookup"><span data-stu-id="3da9b-113">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="3da9b-114">비디오 스트림(수신자에게서 발신자 방향)</span><span class="sxs-lookup"><span data-stu-id="3da9b-114">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="3da9b-p101">지정된 보고서에 표시되는 범주와 메트릭은 두 가지 항목, 즉 세션의 유형과 해당 세션에서 사용되는 끝점의 유형에 따라 달라집니다. 예를 들어 오디오 전용 통화의 경우 비디오 스트림이 없기 때문에 비디오 스트림에 대한 메트릭이 보고되지 않습니다. 마찬가지로 보고서에 발신자 통계만 표시되고 수신자 통계는 표시되지 않을 수도 있습니다. 이는 일반적으로 수신자가 SIP 호환 장치를 사용하지 않았기 때문입니다. 끝점은 통화 종료 시의 통계를 보고하지만 SIP 또는 SIP 통계를 인식하지 못하는 휴대폰은 이러한 종류의 정보를 보고할 수 없습니다. 전화를 걸어 수신자가 휴대폰에서 전화를 받는 경우에는 통화 종료 시 해당 휴대폰에서 보고서가 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="3da9b-121">통화 정보 보고서는 지정된 통화에서 미디어 품질 문제가 발생한 이유를 정확히 확인하려는 경우에 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-121">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="3da9b-122">통화 정보 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="3da9b-122">Accessing the Call Detail Report</span></span>

<span data-ttu-id="3da9b-123">다음 보고서에서 통화 정보 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-123">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="3da9b-124">[Lync Server 2013의 위치 보고서](lync-server-2013-location-report.md) (통화 량 또는 불량 통화 율 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="3da9b-124">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="3da9b-125">[Lync Server 2013의 미디어 품질 요약 보고서](lync-server-2013-media-quality-summary-report.md) (통화 량 또는 불량 통화 율 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="3da9b-125">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="3da9b-126">Lync server [2013에서 통화 목록 보고서](lync-server-2013-call-list-report.md) 를 클릭 하 고 세부 정보 메트릭을 클릭 하 여 온- [2013의 미디어 품질 비교 보고서](lync-server-2013-media-quality-comparison-report.md)</span><span class="sxs-lookup"><span data-stu-id="3da9b-126">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="3da9b-127">[Lync server 2013의 서버 성능 보고서](lync-server-2013-server-performance-report.md) (통화 량 또는 불량 통화 율 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="3da9b-127">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="3da9b-128">[Lync Server 2013의 통화 목록 보고서](lync-server-2013-call-list-report.md) (세부 정보 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="3da9b-128">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="3da9b-129">통화 정보 보고서 내에서 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 장치 보고서](lync-server-2013-device-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-129">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="3da9b-130">캡처 장치</span><span class="sxs-lookup"><span data-stu-id="3da9b-130">Capture device</span></span>

  - <span data-ttu-id="3da9b-131">렌더링 장치</span><span class="sxs-lookup"><span data-stu-id="3da9b-131">Render device</span></span>

<span data-ttu-id="3da9b-132">A/V 에지 서버 메트릭을 클릭하면 서버 미디어 품질 추세 보고서에도 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-132">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="3da9b-133">통화 정보 보고서를 가장 효율적으로 활용</span><span class="sxs-lookup"><span data-stu-id="3da9b-133">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="3da9b-p102">통화 정보 보고서에는 보통 서로 다른 250개의 메트릭이 포함되며, 여기에는 마이크 타임스탬프 드리프트, 낮은 SNR 시간, 수화자 에코 시간 등의 항목이 있습니다. 이러한 모든 메트릭이 실제로 측정하는 항목을 기억하기가 어려우면 메트릭 레이블 위에 마우스를 놓아 보십시오. 그러면 대부분의 경우 해당 메트릭을 설명하는 도구 설명이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="3da9b-p103">메트릭을 찾기가 어려우면 검색 상자에 메트릭 레이블의 일부분을 입력하고 찾기를 클릭합니다. 예를 들어 낮은 SNR 시간 메트릭을 찾을 수 없는 경우 검색 상자에 SNR을 입력하고 찾기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-p103">If you have problems locating a metric, type part of the metric label in the search box and then click Find. For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="3da9b-138">보고서는 통화에 대 한 정보를 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-138">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="3da9b-139">통화 자체가 기록 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-139">The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="3da9b-140">필터</span><span class="sxs-lookup"><span data-stu-id="3da9b-140">Filters</span></span>

<span data-ttu-id="3da9b-p105">없음. 통화 정보 보고서는 필터링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-p105">None. You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="3da9b-143">메트릭</span><span class="sxs-lookup"><span data-stu-id="3da9b-143">Metrics</span></span>

<span data-ttu-id="3da9b-144">다음 표에서는 각 통화에 대해 통화 정보 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-144">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="3da9b-145">통화 정보 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="3da9b-145">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3da9b-146">이름</span><span class="sxs-lookup"><span data-stu-id="3da9b-146">Name</span></span></th>
<th><span data-ttu-id="3da9b-147">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="3da9b-147">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3da9b-148">설명</span><span class="sxs-lookup"><span data-stu-id="3da9b-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3da9b-149"><strong>발신자 PAI</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-149"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-150">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-150">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-p106">통화를 시작한 사용자의 P-Asserted-Identity입니다. P-Asserted-Identity는 트러스트된 네트워크 내에서 사용자의 입증된 ID를 전달하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3da9b-153"><strong>발신자 URI</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-153"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-154">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-154">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-155">통화를 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-155">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3da9b-156"><strong>발신자 끝점</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-156"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-157">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-157">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-158">통화에 사용된 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-158">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3da9b-159"><strong>발신자 사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-159"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-160">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-160">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-161">통화 장치에 사용된 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-161">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3da9b-162"><strong>통화 시작</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-162"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-163">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-163">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-164">통화가 처음 발생한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-164">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3da9b-165"><strong>중재 서버 바이패스 통화</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-165"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-166">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-166">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-167">통화가 중재 서버를 거치지 않고 PSTN 음성 게이트웨이 또는 적격한 IP-PBX에 연결되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-167">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3da9b-168"><strong>발신자 OS</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-168"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-169">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-169">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-170">발신자 컴퓨터의 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-170">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3da9b-171"><strong>발신자 CPU</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-171"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-172">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-172">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-173">통화를 시작한 사용자 컴퓨터에 설치된 CPU입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-173">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3da9b-174"><strong>발신자 CPU 코어 수</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-174"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-175">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-175">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-176">통화를 시작한 사용자가 사용한 컴퓨터의 프로세서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-176">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3da9b-177"><strong>발신자 CPU 속도</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-177"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-178">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-178">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-179">통화를 시작한 사용자가 사용한 컴퓨터의 CPU 클럭 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-179">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3da9b-180"><strong>발신자 CPU 가상화</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-180"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-181">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-181">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-182">통화를 시작한 사용자가 사용한 컴퓨터에 사용된 가상화(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-182">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3da9b-183"><strong>수신자 PAI</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-183"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-184">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-184">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-p107">통화에 참가하도록 초대된 사용자의 P-Asserted-Identity입니다. P-Asserted-Identity는 트러스트된 네트워크 내에서 사용자의 입증된 ID를 전달하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3da9b-187"><strong>수신자 URI</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-187"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-188">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-188">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-189">통화를 받은 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-189">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3da9b-190"><strong>수신자 끝점</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-190"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-191">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-191">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-192">통화를 받기 위해 사용된 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-192">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3da9b-193"><strong>수신자 사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-193"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-194">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-194">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-195">통화를 받은 장치에 사용된 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-195">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3da9b-196"><strong>기간</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-196"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-197">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-197">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-198">통화 시간 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-198">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3da9b-199"><strong>미디어 바이패스 경고 플래그</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-199"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-200">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-200">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-201">중재 서버를 바이패스할 때 발생한 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-201">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3da9b-202"><strong>수신자 OS</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-202"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-203">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-203">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-204">통화를 받은 사용자 컴퓨터의 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-204">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3da9b-205"><strong>수신자 CPU</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-205"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-206">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-206">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-207">통화를 받은 사용자 컴퓨터에 설치된 CPU입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-207">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3da9b-208"><strong>수신자 코어 수</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-208"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-209">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-209">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-210">통화를 받은 사용자가 사용한 컴퓨터의 프로세서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-210">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3da9b-211"><strong>수신자 CPU 속도</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-211"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-212">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-212">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-213">통화를 받은 사용자가 사용한 컴퓨터의 CPU 클럭 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-213">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3da9b-214"><strong>수신자 CPU 가상화</strong></span><span class="sxs-lookup"><span data-stu-id="3da9b-214"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="3da9b-215">아니요</span><span class="sxs-lookup"><span data-stu-id="3da9b-215">No</span></span></p></td>
<td><p><span data-ttu-id="3da9b-216">통화를 받은 사용자가 사용한 컴퓨터에 사용된 가상화(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="3da9b-216">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

