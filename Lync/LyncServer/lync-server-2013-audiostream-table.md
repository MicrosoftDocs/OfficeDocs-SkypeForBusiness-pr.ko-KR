---
title: 'Lync Server 2013: 오디오 스트림 테이블'
description: 'Lync Server 2013: 오디오 스트림 테이블입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af2e622e14c54fa4f9a6313e1b0dae8f2483132
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552344"
---
# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="f9e12-103">Lync Server 2013의 오디오 스트림 테이블</span><span class="sxs-lookup"><span data-stu-id="f9e12-103">AudioStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9e12-104">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f9e12-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f9e12-105">각 레코드는 하나의 오디오 스트림을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-105">Each record represents one audio stream.</span></span> <span data-ttu-id="f9e12-106">일반적으로 하나의 오디오 미디어 회선에는 두 개의 오디오 스트림이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-106">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9e12-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f9e12-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f9e12-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f9e12-110"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-111"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f9e12-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f9e12-113">Primary</span><span class="sxs-lookup"><span data-stu-id="f9e12-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="f9e12-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-116">int</span><span class="sxs-lookup"><span data-stu-id="f9e12-116">int</span></span></p></td>
<td><p><span data-ttu-id="f9e12-117">Primary</span><span class="sxs-lookup"><span data-stu-id="f9e12-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="f9e12-118"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="f9e12-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f9e12-121">Primary</span><span class="sxs-lookup"><span data-stu-id="f9e12-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="f9e12-122"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-123"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-124">int</span><span class="sxs-lookup"><span data-stu-id="f9e12-124">int</span></span></p></td>
<td><p><span data-ttu-id="f9e12-125">Primary</span><span class="sxs-lookup"><span data-stu-id="f9e12-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="f9e12-126">미디어 회선 내의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-127"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-127"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-128">int</span><span class="sxs-lookup"><span data-stu-id="f9e12-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-129">RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-129">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-130"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-130"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-131">int</span><span class="sxs-lookup"><span data-stu-id="f9e12-131">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-132">통화 중 최대 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-132">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-133"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-133"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-134">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="f9e12-134">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-135">통화 중 평균 패킷 손실 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-135">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-136"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-136"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-137">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="f9e12-137">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-138">통화 중 관측된 최대 패킷 손실입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-138">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-139"><strong>버스트 밀도</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-139"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-140">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f9e12-140">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-141">통화 중 손실 버스트 동안의 평균 패킷 손실 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-141">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-142"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-142"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-143">int</span><span class="sxs-lookup"><span data-stu-id="f9e12-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-144">통화 중 손실량이 많아지는 기간 동안의 평균 패킷 손실 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-144">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-145"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-145"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-146">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f9e12-146">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-147">패킷 손실이 최고치인 기간 사이의 간격 중에 발생하는 평균 패킷 손실 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-147">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-148"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-148"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-149">int</span><span class="sxs-lookup"><span data-stu-id="f9e12-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-150">패킷 손실이 최고치인 기간 사이의 간격에 대한 평균 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-150">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-151"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-151"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-152">임계값</span><span class="sxs-lookup"><span data-stu-id="f9e12-152">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-153">오디오 스트림에 대한 패킷 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-153">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-154"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-154"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-155">임계값</span><span class="sxs-lookup"><span data-stu-id="f9e12-155">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-156">오디오 스트림에 대한 대역폭 예상치입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-156">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-157"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-157"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-158">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f9e12-158">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-p102">전체 통화에 대한 네트워크 MOS 저하입니다. 범위는 0.0에서 5.0까지입니다. 이 메트릭은 지터 및 패킷 손실로 인해 감소된 네트워크 MOS의 양을 보여 줍니다. 적정 품질을 위해서는 0.5 미만이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-163"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-163"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-164">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f9e12-164">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-165">통화 중 최대 네트워크 MOS 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-165">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-166"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-166"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-167">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f9e12-167">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-168">지터로 인해 발생한 네트워크 MOS 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-168">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-169"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-169"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-170">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f9e12-170">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-171">패킷 손실로 인해 발생한 네트워크 MOS 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-171">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-172"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-172"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-173">int</span><span class="sxs-lookup"><span data-stu-id="f9e12-173">int</span></span></p></td>
<td><p><span data-ttu-id="f9e12-174">외부</span><span class="sxs-lookup"><span data-stu-id="f9e12-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9e12-175">PayloadDescription Table에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-175">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-176"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-176"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-177">int</span><span class="sxs-lookup"><span data-stu-id="f9e12-177">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-178">오디오 스트림에 대한 샘플링 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-178">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-179"><strong>왕복</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-179"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-180">int</span><span class="sxs-lookup"><span data-stu-id="f9e12-180">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-181">RTCP 통계로부터의 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-181">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="f9e12-182">적절 한 품질을 위해 적고 100 밀리초 보다 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-182">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-183"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-183"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-184">int</span><span class="sxs-lookup"><span data-stu-id="f9e12-184">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-185">오디오 스트림에 대한 최대 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-185">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-186"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-186"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-187">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f9e12-187">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-188">통화에 대한 평균 광대역 네트워크 MOS입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-188">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="f9e12-189">이 메트릭은 패킷 손실, 지터 및 사용된 코덱에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-189">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="f9e12-190">범위는 [1.0 ~ 5.0]입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-190">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-191"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-191"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-192">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f9e12-192">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-193">통화에 대 한 최소 광대역 네트워크 MOS입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-193">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-194"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-194"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-195">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f9e12-195">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-196">음성 수준, 노이즈 수준 및 캡처 장치 특성을 포함 하 여 전송 된 오디오에 대 한 평균 예측 광대역 청취 MOS 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-196">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-197"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-197"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-198">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f9e12-198">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-199">통화에 대 한 최소 SendListenMOS입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-199">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-200"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-200"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-201">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f9e12-201">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-202">음성 수준, 노이즈 수준, 코덱, 네트워크 조건 및 캡처 장치 특성을 포함 하 여 네트워크에서 수신 된 오디오에 대 한 평균 예측 광대역 수신 MOS 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-202">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-203"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-203"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-204">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="f9e12-204">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-205">통화에 대 한 최소 RecvListenMOS입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-205">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-206"><strong>오디오 \ Ecused</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-206"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-207">비트만</span><span class="sxs-lookup"><span data-stu-id="f9e12-207">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-208">통화에 오디오 FEC가 사용 되었는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-208">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-209"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-209"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-210">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f9e12-210">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-211">일반 샘플에 대한 오디오 힐링으로 생성된 숨겨진 평균 샘플 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-211">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-212"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-212"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-213">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f9e12-213">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-214">일반 샘플에 대한 오디오 힐링으로 생성된 평균 늘임 샘플 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-214">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-215"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-215"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-216">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="f9e12-216">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-217">일반 샘플에 대한 오디오 힐링으로 생성된 숨겨진 압축 샘플 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-217">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-218"><strong>인바운드</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-218"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-219">비트만</span><span class="sxs-lookup"><span data-stu-id="f9e12-219">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-220">수신기 쪽의 Stream 데이터를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-220">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-221"><strong>아웃 바운드</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-221"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-222">비트만</span><span class="sxs-lookup"><span data-stu-id="f9e12-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-223">보낸 사람 쪽의 스트림 데이터가 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-223">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-224"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-224"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-225">비트만</span><span class="sxs-lookup"><span data-stu-id="f9e12-225">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9e12-226">1은 스트림 방향이 발신자에서 수신자에 게 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-226">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="f9e12-227">0은 스트림 방향이 수신자에서 발신자의 방향임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-227">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-228"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-228"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-229">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-229">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-230">지터 도착 시간에 대 한 표준 편차입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-230">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="f9e12-231">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-231">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-232"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-232"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-233">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-234">힐 러으로 숨겨진 최대 패킷 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-234">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="f9e12-235">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-235">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-236"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-236"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-237">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-238">힐 러의 숨겨진 패킷 비율에 대 한 표준 편차입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-238">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="f9e12-239">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-239">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-240"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-240"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-241">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-241">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-242">수신 된 총 패킷 수와 비교 하 여 힐 러에서 삭제 된 패킷의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-242">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="f9e12-243">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-243">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-244"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-244"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-245">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-246">수신 된 총 패킷 수에 비해 사용 된 정방향 오류 수정 패킷 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-246">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="f9e12-247">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-247">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-248"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-248"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-249">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-250">힐 러에서 압축 한 최대 오디오 패킷 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-250">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="f9e12-251">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-252"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-252"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-253">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-254">통화가 손실 혼잡 상태에 있는 시간의 백분율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-254">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="f9e12-255">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-256"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-256"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-257">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-258">네트워크 패킷의 지연 도착으로 인해 혼잡이 발생 한 통화 비율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-258">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="f9e12-259">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-259">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-260"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-260"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-261">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-261">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-262">호출이 네트워크 리소스를 경합 하는 시간 비율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-262">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="f9e12-263">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-263">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-264"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-264"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-265">int</span><span class="sxs-lookup"><span data-stu-id="f9e12-265">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-266">통화 중 측정 된 최소 대역폭 예상 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-266">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f9e12-267">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-268"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-268"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-269">int</span><span class="sxs-lookup"><span data-stu-id="f9e12-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-270">통화 중 측정 된 최대 대역폭 예상 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-270">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f9e12-271">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-271">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-272"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-272"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-273">int</span><span class="sxs-lookup"><span data-stu-id="f9e12-273">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-274">통화 중 측정 된 대역폭 예상 범위의 표준 편차입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-274">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f9e12-275">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-275">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-276"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-276"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-277">int</span><span class="sxs-lookup"><span data-stu-id="f9e12-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-278">통화 중 측정 된 평균 대역폭 양입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-278">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f9e12-279">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-280"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-280"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-281">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-281">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-p105">총 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f9e12-284">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-285"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-285"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-286">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-p106">평균 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f9e12-289">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-289">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-290"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-290"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-291">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-p107">최대 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f9e12-294">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-294">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-295"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-295"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-296">int</span><span class="sxs-lookup"><span data-stu-id="f9e12-296">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-p108">총 단방향 버스트 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f9e12-300">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-301"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-301"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-302">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-302">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-p109">총 단방향 버스트 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f9e12-306">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-306">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-307"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-307"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-308">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-308">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-p110">총 단방향 버스트 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f9e12-312">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-312">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-313"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-313"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-314">int</span><span class="sxs-lookup"><span data-stu-id="f9e12-314">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-p111">총 단방향 갭 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f9e12-318">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-319"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-319"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-320">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-p112">총 단방향 갭 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f9e12-324">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-325"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-325"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-326">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-326">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-p113">총 단방향 갭 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f9e12-330">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-331"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-331"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-332">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-332">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-333">스테레오로 디코딩된 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-333">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="f9e12-334">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-335"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-335"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-336">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-337">음향 반향 반향 스테레오으로 렌더링 된 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-337">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="f9e12-338">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-338">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-339"><strong>오디오 합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-339"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-340">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-341">전달 오류 정정이 적용 된 후의 패킷 손실 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-341">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="f9e12-342">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-342">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9e12-343"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-343"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-344">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-344">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-345">스테레오로 인코딩된 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-345">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="f9e12-346">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-346">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9e12-347"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f9e12-347"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f9e12-348">식</span><span class="sxs-lookup"><span data-stu-id="f9e12-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9e12-349">음향 반향 반향에 의해 스테레오로 캡처된 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-349">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="f9e12-350">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f9e12-350">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

