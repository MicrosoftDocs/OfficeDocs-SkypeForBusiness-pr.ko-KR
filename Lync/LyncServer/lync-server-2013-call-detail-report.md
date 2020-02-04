---
title: 'Lync Server 2013: 통화 세부 정보 보고서'
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
ms.openlocfilehash: ffbfa8c3553b33f75b0f014265f93cccf46e7de6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="ed9f5-102">Lync Server 2013의 통화 세부 정보 보고서</span><span class="sxs-lookup"><span data-stu-id="ed9f5-102">Call Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed9f5-103">_**마지막으로 수정한 주제:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="ed9f5-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="ed9f5-104">통화 정보 보고서는 개별 통화에 대 한 자세한 정보를 제공 합니다. 이 보고서에는 Lync Server에서 수집한 경험 메트릭과 통계의 거의 모든 품질이 포함 되어 있으며, 다음과 같은 보고서 섹션으로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-104">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="ed9f5-105">통화 정보</span><span class="sxs-lookup"><span data-stu-id="ed9f5-105">Call Information</span></span>

  - <span data-ttu-id="ed9f5-106">발신자 장치 및 신호 메트릭</span><span class="sxs-lookup"><span data-stu-id="ed9f5-106">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="ed9f5-107">호출 수신자 장치 및 신호 메트릭</span><span class="sxs-lookup"><span data-stu-id="ed9f5-107">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="ed9f5-108">발신자 클라이언트 이벤트</span><span class="sxs-lookup"><span data-stu-id="ed9f5-108">Caller Client Event</span></span>

  - <span data-ttu-id="ed9f5-109">호출 수신자 클라이언트 이벤트</span><span class="sxs-lookup"><span data-stu-id="ed9f5-109">Callee Client Event</span></span>

  - <span data-ttu-id="ed9f5-110">오디오 스트림 (호출자 to 피호출자)</span><span class="sxs-lookup"><span data-stu-id="ed9f5-110">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="ed9f5-111">비디오 스트림 (호출자 to 피호출자)</span><span class="sxs-lookup"><span data-stu-id="ed9f5-111">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="ed9f5-112">오디오 스트림 (피호출자를 호출자로)</span><span class="sxs-lookup"><span data-stu-id="ed9f5-112">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="ed9f5-113">비디오 스트림 (호출자에 게 피호출자)</span><span class="sxs-lookup"><span data-stu-id="ed9f5-113">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="ed9f5-114">지정 된 보고서에 표시 되는 범주와 메트릭은 세션의 종류와 세션에 사용 되는 끝점의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-114">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session.</span></span> <span data-ttu-id="ed9f5-115">예를 들어 오디오 전용 통화는 비디오 스트림에 대 한 메트릭을 보고 하지 않습니다. 이는 통화에 비디오 스트림이 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-115">For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream.</span></span> <span data-ttu-id="ed9f5-116">마찬가지로 호출자 통계는 포함 되지만 호출 수신자 통계는 나열 되지 않는 보고서가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-116">Likewise, you might have a report that lists caller statistics but not callee statistics.</span></span> <span data-ttu-id="ed9f5-117">이는 일반적으로 호출 수신자가 SIP 호환 장치를 사용 하지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-117">That's typically because the callee was not using a SIP-compliant device.</span></span> <span data-ttu-id="ed9f5-118">끝점은 통화 종료 시 통계 보고를 담당 합니다. 그러나 휴대폰 (SIP 또는 SIP 통계에 대 한 자세한 내용은 없음)은 해당 정보를 보고할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-118">Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information.</span></span> <span data-ttu-id="ed9f5-119">다른 사람에 게 전화를 걸어 휴대폰으로 전화를 받은 경우 통화가 종료 되 면 해당 휴대폰에서 보고서를 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-119">If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="ed9f5-120">통화 정보 보고서는 특정 통화에 미디어 품질 문제가 발생 한 이유를 정확히 확인 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-120">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="ed9f5-121">통화 정보 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="ed9f5-121">Accessing the Call Detail Report</span></span>

<span data-ttu-id="ed9f5-122">다음 보고서에서 통화 정보 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-122">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="ed9f5-123">[Lync Server 2013의 위치 보고서](lync-server-2013-location-report.md) (통화 볼륨 또는 불량 통화 백분율 메트릭 중 하나를 클릭 하 여)</span><span class="sxs-lookup"><span data-stu-id="ed9f5-123">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="ed9f5-124">[Lync Server 2013의 미디어 품질 요약 보고서](lync-server-2013-media-quality-summary-report.md) (통화 볼륨 또는 잘못 된 통화 백분율 메트릭을 클릭 하 여)</span><span class="sxs-lookup"><span data-stu-id="ed9f5-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="ed9f5-125">[Lync server 2013의 미디어 품질 비교 보고서](lync-server-2013-media-quality-comparison-report.md) ( [lync Server 2013에서 통화 목록 보고서](lync-server-2013-call-list-report.md) 를 클릭 한 다음 세부 정보 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="ed9f5-125">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="ed9f5-126">Lync Server 2013 (통화 볼륨 또는 잘못 된 통화 백분율 메트릭 중 하나를 클릭 하 여) [의 서버 성능 보고서](lync-server-2013-server-performance-report.md)</span><span class="sxs-lookup"><span data-stu-id="ed9f5-126">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="ed9f5-127">[Lync Server 2013의 통화 목록 보고서](lync-server-2013-call-list-report.md) (세부 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="ed9f5-127">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="ed9f5-128">통화 정보 보고서 내에서 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013에서 장치 보고서](lync-server-2013-device-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-128">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="ed9f5-129">캡처 장치</span><span class="sxs-lookup"><span data-stu-id="ed9f5-129">Capture device</span></span>

  - <span data-ttu-id="ed9f5-130">렌더링 장치</span><span class="sxs-lookup"><span data-stu-id="ed9f5-130">Render device</span></span>

<span data-ttu-id="ed9f5-131">A/V edge 서버 메트릭을 클릭 하 여 서버 미디어 품질 추세 보고서에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-131">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="ed9f5-132">통화 정보 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="ed9f5-132">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="ed9f5-133">일반적으로 통화 세부 정보 보고서에는 마이크 타임 스탬프 드리프트, 낮은 우선 r 시간, 가까운 끝, 에코 시간 등의 항목을 포함 하 여 250의 다른 메트릭이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-133">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time.</span></span> <span data-ttu-id="ed9f5-134">이러한 모든 메트릭이 실제로 측정 하는 것을 잊어버린 경우에는 미터법 레이블 위에 마우스를 누른 채 보세요. 종종 해당 메트릭에 대해 설명 하는 도구 설명이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-134">If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="ed9f5-135">메트릭을 찾는 데 문제가 있는 경우 검색 상자에 메트릭 레이블의 일부를 입력 한 다음 찾기를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-135">If you have problems locating a metric, type part of the metric label in the search box and then click Find.</span></span> <span data-ttu-id="ed9f5-136">예를 들어 낮은 SNR 시간 메트릭을 찾을 수 없는 경우 검색 상자에 SNR을 입력 한 다음 찾기를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-136">For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="ed9f5-137">보고서는 통화에 대 한 정보만 추적 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-137">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="ed9f5-138">통화 자체는 기록 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-138">The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ed9f5-139">필터가</span><span class="sxs-lookup"><span data-stu-id="ed9f5-139">Filters</span></span>

<span data-ttu-id="ed9f5-140">없음.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-140">None.</span></span> <span data-ttu-id="ed9f5-141">통화 정보 보고서는 필터링 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-141">You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="ed9f5-142">매트릭스</span><span class="sxs-lookup"><span data-stu-id="ed9f5-142">Metrics</span></span>

<span data-ttu-id="ed9f5-143">다음 표에는 각 통화에 대 한 통화 정보 보고서에서 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-143">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="ed9f5-144">통화 세부 정보 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="ed9f5-144">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed9f5-145">이름</span><span class="sxs-lookup"><span data-stu-id="ed9f5-145">Name</span></span></th>
<th><span data-ttu-id="ed9f5-146">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ed9f5-146">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ed9f5-147">설명</span><span class="sxs-lookup"><span data-stu-id="ed9f5-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed9f5-148"><strong>발신자 PAI</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-148"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-149">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-149">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-150">P-어설션 됨-통화를 시작한 사용자의 Id입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-150">P-Asserted-Identity of the user who initiated the call.</span></span> <span data-ttu-id="ed9f5-151">P-어설션된-Id는 신뢰할 수 있는 네트워크 내에서 사용자의 증명 된 id를 전달 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-151">The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed9f5-152"><strong>발신자 URI</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-152"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-153">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-153">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-154">통화를 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-154">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed9f5-155"><strong>발신자 끝점</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-155"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-156">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-156">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-157">전화를 걸 때 사용 하는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-157">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed9f5-158"><strong>발신자 사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-158"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-159">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-159">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-160">통화를 한 장치에서 사용 하는 소프트웨어</span><span class="sxs-lookup"><span data-stu-id="ed9f5-160">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed9f5-161"><strong>통화 시작</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-161"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-162">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-162">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-163">통화가 처음에 배치 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-163">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed9f5-164"><strong>중재 서버 바이패스 통화</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-164"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-165">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-165">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-166">호출이 중재 서버를 통과 하지 않고 PSTN 음성 게이트웨이 또는 정식 IP PBX에 연결 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-166">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed9f5-167"><strong>발신자 OS</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-167"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-168">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-168">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-169">전화 걸기 컴퓨터의 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-169">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed9f5-170"><strong>호출자 CPU</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-170"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-171">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-171">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-172">통화를 시작한 사용자의 컴퓨터에 설치 된 CPU입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-172">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed9f5-173"><strong>발신자 CPU 코어 번호</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-173"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-174">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-174">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-175">통화를 시작한 사람이 사용 하는 컴퓨터의 프로세서 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-175">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed9f5-176"><strong>발신자 CPU 속도</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-176"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-177">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-177">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-178">통화를 시작한 사람이 사용 하는 컴퓨터의 CPU 클록 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-178">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed9f5-179"><strong>발신자 CPU 가상화</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-179"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-180">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-180">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-181">통화를 시작한 사람이 사용 하는 컴퓨터에서 사용 되는 가상화 (있는 경우)</span><span class="sxs-lookup"><span data-stu-id="ed9f5-181">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed9f5-182"><strong>호출 수신자 PAI</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-182"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-183">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-183">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-184">P-어설션 됨-통화에 참가 하도록 초대 받은 사용자의 Id입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-184">P-Asserted-Identity of the user who was invited to join the call.</span></span> <span data-ttu-id="ed9f5-185">P-어설션된-Id는 신뢰할 수 있는 네트워크 내에서 사용자의 증명 된 id를 전달 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-185">The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed9f5-186"><strong>호출 수신자 URI</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-186"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-187">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-187">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-188">호출 된 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-188">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed9f5-189"><strong>호출 수신자 끝점</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-189"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-190">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-190">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-191">통화를 수신 하는 데 사용 되는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-191">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed9f5-192"><strong>호출 수신자 사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-192"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-193">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-193">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-194">통화를 받은 장치에 사용 되는 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-194">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed9f5-195"><strong>시간이</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-195"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-196">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-196">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-197">통화 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-197">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed9f5-198"><strong>미디어 바이패스 경고 플래그</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-198"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-199">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-199">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-200">중재 서버를 우회 했을 때 발급 되는 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-200">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed9f5-201"><strong>호출 수신자 OS</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-201"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-202">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-202">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-203">호출 된 사용자에 대 한 컴퓨터의 운영 체제입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-203">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed9f5-204"><strong>호출 수신자 CPU</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-204"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-205">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-205">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-206">호출한 사용자의 컴퓨터에 설치 된 CPU입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-206">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed9f5-207"><strong>호출 수신자 핵심 번호</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-207"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-208">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-208">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-209">호출 된 사용자가 사용 하는 컴퓨터의 프로세서 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-209">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed9f5-210"><strong>호출 수신자 CPU 속도</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-210"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-211">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-211">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-212">호출 된 사용자가 사용 하는 컴퓨터의 CPU 클록 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-212">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed9f5-213"><strong>호출 수신자 CPU 가상화</strong></span><span class="sxs-lookup"><span data-stu-id="ed9f5-213"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="ed9f5-214">아니요</span><span class="sxs-lookup"><span data-stu-id="ed9f5-214">No</span></span></p></td>
<td><p><span data-ttu-id="ed9f5-215">호출 된 사용자가 사용 하는 컴퓨터에서 가상화 (있는 경우)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed9f5-215">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

