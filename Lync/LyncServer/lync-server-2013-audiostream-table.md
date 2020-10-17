---
title: 'Lync Server 2013: 오디오 스트림 테이블'
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
ms.openlocfilehash: 331b2afbfa4b6c4147ffab3765af4e9e5031c190
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502875"
---
# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="0e96f-102">Lync Server 2013의 오디오 스트림 테이블</span><span class="sxs-lookup"><span data-stu-id="0e96f-102">AudioStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e96f-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="0e96f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="0e96f-104">각 레코드는 하나의 오디오 스트림을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-104">Each record represents one audio stream.</span></span> <span data-ttu-id="0e96f-105">일반적으로 하나의 오디오 미디어 회선에는 두 개의 오디오 스트림이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e96f-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="0e96f-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="0e96f-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="0e96f-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-110"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-111">datetime</span><span class="sxs-lookup"><span data-stu-id="0e96f-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="0e96f-112">Primary</span><span class="sxs-lookup"><span data-stu-id="0e96f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="0e96f-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-115">int</span><span class="sxs-lookup"><span data-stu-id="0e96f-115">int</span></span></p></td>
<td><p><span data-ttu-id="0e96f-116">Primary</span><span class="sxs-lookup"><span data-stu-id="0e96f-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="0e96f-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="0e96f-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0e96f-120">Primary</span><span class="sxs-lookup"><span data-stu-id="0e96f-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="0e96f-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-123">int</span><span class="sxs-lookup"><span data-stu-id="0e96f-123">int</span></span></p></td>
<td><p><span data-ttu-id="0e96f-124">Primary</span><span class="sxs-lookup"><span data-stu-id="0e96f-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="0e96f-125">미디어 회선 내의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-127">int</span><span class="sxs-lookup"><span data-stu-id="0e96f-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-128">RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-130">int</span><span class="sxs-lookup"><span data-stu-id="0e96f-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-131">통화 중 최대 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-133">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="0e96f-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-134">통화 중 평균 패킷 손실 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-136">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="0e96f-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-137">통화 중 관측된 최대 패킷 손실입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-138"><strong>버스트 밀도</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-139">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="0e96f-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-140">통화 중 손실 버스트 동안의 평균 패킷 손실 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-142">int</span><span class="sxs-lookup"><span data-stu-id="0e96f-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-143">통화 중 손실량이 많아지는 기간 동안의 평균 패킷 손실 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-145">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="0e96f-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-146">패킷 손실이 최고치인 기간 사이의 간격 중에 발생하는 평균 패킷 손실 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-148">int</span><span class="sxs-lookup"><span data-stu-id="0e96f-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-149">패킷 손실이 최고치인 기간 사이의 간격에 대한 평균 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-151">임계값</span><span class="sxs-lookup"><span data-stu-id="0e96f-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-152">오디오 스트림에 대한 패킷 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-153"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-154">임계값</span><span class="sxs-lookup"><span data-stu-id="0e96f-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-155">오디오 스트림에 대한 대역폭 예상치입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-157">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e96f-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-p102">전체 통화에 대한 네트워크 MOS 저하입니다. 범위는 0.0에서 5.0까지입니다. 이 메트릭은 지터 및 패킷 손실로 인해 감소된 네트워크 MOS의 양을 보여 줍니다. 적정 품질을 위해서는 0.5 미만이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-p102">Network MOS Degradation for the whole call. Range is 0.0 to 5.0. This metric shows the amount the Network MOS was reduced because of jitter and packet loss. For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-163">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e96f-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-164">통화 중 최대 네트워크 MOS 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-166">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e96f-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-167">지터로 인해 발생한 네트워크 MOS 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-169">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e96f-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-170">패킷 손실로 인해 발생한 네트워크 MOS 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-172">int</span><span class="sxs-lookup"><span data-stu-id="0e96f-172">int</span></span></p></td>
<td><p><span data-ttu-id="0e96f-173">외부</span><span class="sxs-lookup"><span data-stu-id="0e96f-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0e96f-174">PayloadDescription Table에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-176">int</span><span class="sxs-lookup"><span data-stu-id="0e96f-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-177">오디오 스트림에 대한 샘플링 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-178"><strong>왕복</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-179">int</span><span class="sxs-lookup"><span data-stu-id="0e96f-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-180">RTCP 통계로부터의 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="0e96f-181">적절 한 품질을 위해 적고 100 밀리초 보다 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-183">int</span><span class="sxs-lookup"><span data-stu-id="0e96f-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-184">오디오 스트림에 대한 최대 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-186">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e96f-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-187">통화에 대한 평균 광대역 네트워크 MOS입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="0e96f-188">이 메트릭은 패킷 손실, 지터 및 사용된 코덱에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="0e96f-189">범위는 [1.0 ~ 5.0]입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-191">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e96f-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-192">통화에 대 한 최소 광대역 네트워크 MOS입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-194">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e96f-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-195">음성 수준, 노이즈 수준 및 캡처 장치 특성을 포함 하 여 전송 된 오디오에 대 한 평균 예측 광대역 청취 MOS 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-197">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e96f-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-198">통화에 대 한 최소 SendListenMOS입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-200">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e96f-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-201">음성 수준, 노이즈 수준, 코덱, 네트워크 조건 및 캡처 장치 특성을 포함 하 여 네트워크에서 수신 된 오디오에 대 한 평균 예측 광대역 수신 MOS 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-203">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="0e96f-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-204">통화에 대 한 최소 RecvListenMOS입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-205"><strong>오디오 \ Ecused</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-206">비트만</span><span class="sxs-lookup"><span data-stu-id="0e96f-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-207">통화에 오디오 FEC가 사용 되었는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-209">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0e96f-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-210">일반 샘플에 대한 오디오 힐링으로 생성된 숨겨진 평균 샘플 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-212">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0e96f-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-213">일반 샘플에 대한 오디오 힐링으로 생성된 평균 늘임 샘플 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-215">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="0e96f-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-216">일반 샘플에 대한 오디오 힐링으로 생성된 숨겨진 압축 샘플 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-217"><strong>인바운드</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-218">비트만</span><span class="sxs-lookup"><span data-stu-id="0e96f-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-219">수신기 쪽의 Stream 데이터를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-220"><strong>아웃 바운드</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-221">비트만</span><span class="sxs-lookup"><span data-stu-id="0e96f-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-222">보낸 사람 쪽의 스트림 데이터가 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-224">비트만</span><span class="sxs-lookup"><span data-stu-id="0e96f-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0e96f-225">1은 스트림 방향이 발신자에서 수신자에 게 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="0e96f-226">0은 스트림 방향이 수신자에서 발신자의 방향임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-228">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-229">지터 도착 시간에 대 한 표준 편차입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="0e96f-230">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-232">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-233">힐 러으로 숨겨진 최대 패킷 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="0e96f-234">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-236">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-237">힐 러의 숨겨진 패킷 비율에 대 한 표준 편차입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="0e96f-238">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-240">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-241">수신 된 총 패킷 수와 비교 하 여 힐 러에서 삭제 된 패킷의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="0e96f-242">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-244">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-245">수신 된 총 패킷 수에 비해 사용 된 정방향 오류 수정 패킷 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="0e96f-246">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-248">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-249">힐 러에서 압축 한 최대 오디오 패킷 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="0e96f-250">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-252">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-253">통화가 손실 혼잡 상태에 있는 시간의 백분율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="0e96f-254">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-256">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-257">네트워크 패킷의 지연 도착으로 인해 혼잡이 발생 한 통화 비율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="0e96f-258">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-260">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-261">호출이 네트워크 리소스를 경합 하는 시간 비율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="0e96f-262">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-264">int</span><span class="sxs-lookup"><span data-stu-id="0e96f-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-265">통화 중 측정 된 최소 대역폭 예상 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="0e96f-266">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-268">int</span><span class="sxs-lookup"><span data-stu-id="0e96f-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-269">통화 중 측정 된 최대 대역폭 예상 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="0e96f-270">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-272">int</span><span class="sxs-lookup"><span data-stu-id="0e96f-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-273">통화 중 측정 된 대역폭 예상 범위의 표준 편차입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="0e96f-274">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-276">int</span><span class="sxs-lookup"><span data-stu-id="0e96f-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-277">통화 중 측정 된 평균 대역폭 양입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="0e96f-278">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-280">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-p105">총 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="0e96f-283">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-285">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-p106">평균 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="0e96f-288">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-290">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-p107">최대 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="0e96f-293">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-295">int</span><span class="sxs-lookup"><span data-stu-id="0e96f-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-p108">총 단방향 버스트 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0e96f-299">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-301">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-p109">총 단방향 버스트 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0e96f-305">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-307">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-p110">총 단방향 버스트 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0e96f-311">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-313">int</span><span class="sxs-lookup"><span data-stu-id="0e96f-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-p111">총 단방향 갭 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0e96f-317">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-319">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-p112">총 단방향 갭 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0e96f-323">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-325">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-p113">총 단방향 갭 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0e96f-329">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-331">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-332">스테레오로 디코딩된 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="0e96f-333">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-335">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-336">음향 반향 반향 스테레오으로 렌더링 된 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="0e96f-337">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-338"><strong>오디오 합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-339">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-340">전달 오류 정정이 적용 된 후의 패킷 손실 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="0e96f-341">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e96f-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-343">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-344">스테레오로 인코딩된 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="0e96f-345">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e96f-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0e96f-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0e96f-347">식</span><span class="sxs-lookup"><span data-stu-id="0e96f-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0e96f-348">음향 반향 반향에 의해 스테레오로 캡처된 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="0e96f-349">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e96f-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

