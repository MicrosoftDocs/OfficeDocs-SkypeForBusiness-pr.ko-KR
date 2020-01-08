---
title: 'Lync Server 2013: AudioStream 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9412001652f4f323bdd3fb5722d0d7222535fd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="cc047-102">Lync Server 2013의 AudioStream 테이블</span><span class="sxs-lookup"><span data-stu-id="cc047-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc047-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="cc047-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="cc047-104">각 레코드는 하나의 오디오 스트림을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-104">Each record represents one audio stream.</span></span> <span data-ttu-id="cc047-105">일반적으로 하나의 오디오 미디어 선에는 두 개의 오디오 스트림이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc047-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="cc047-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="cc047-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="cc047-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc047-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="cc047-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="cc047-112">주요한</span><span class="sxs-lookup"><span data-stu-id="cc047-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="cc047-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-115">int</span><span class="sxs-lookup"><span data-stu-id="cc047-115">int</span></span></p></td>
<td><p><span data-ttu-id="cc047-116">주요한</span><span class="sxs-lookup"><span data-stu-id="cc047-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="cc047-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="cc047-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="cc047-120">주요한</span><span class="sxs-lookup"><span data-stu-id="cc047-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="cc047-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-123">int</span><span class="sxs-lookup"><span data-stu-id="cc047-123">int</span></span></p></td>
<td><p><span data-ttu-id="cc047-124">주요한</span><span class="sxs-lookup"><span data-stu-id="cc047-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="cc047-125">미디어 라인 내의 고유 ID.</span><span class="sxs-lookup"><span data-stu-id="cc047-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-127">int</span><span class="sxs-lookup"><span data-stu-id="cc047-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-128">RTCP (실시간 제어 프로토콜) 통계의 평균 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-130">int</span><span class="sxs-lookup"><span data-stu-id="cc047-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-131">통화 중 최대 네트워크 지터.</span><span class="sxs-lookup"><span data-stu-id="cc047-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-133">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="cc047-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-134">통화 중의 평균 패킷 손실 율입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-136">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="cc047-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-137">통화 중에 최대 패킷 손실이 관찰 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-139">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="cc047-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-140">통화 중에 손실이 발생 한 경우 패킷 손실의 평균 밀도입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-142">int</span><span class="sxs-lookup"><span data-stu-id="cc047-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-143">통화 중에 손실 되는 패킷 손실의 평균 지속 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-145">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="cc047-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-146">패킷 손실의 버스트 간에 간격을 두는 경우 패킷 손실의 평균 밀도.</span><span class="sxs-lookup"><span data-stu-id="cc047-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-148">int</span><span class="sxs-lookup"><span data-stu-id="cc047-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-149">패킷 손실의 버스트 간 평균 간격 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-151">Int</span><span class="sxs-lookup"><span data-stu-id="cc047-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-152">오디오 스트림의 패킷 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-153"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-154">Int</span><span class="sxs-lookup"><span data-stu-id="cc047-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-155">오디오 스트림의 대역폭을 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-157">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="cc047-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-158">전체 통화에 대 한 네트워크 SPECIALIST 성능이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="cc047-159">범위는 0.0 ~ 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="cc047-160">이 메트릭은 지터 및 패킷 손실로 인해 네트워크 SPECIALIST 감소 된 양을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="cc047-161">허용 되는 품질은 0.5 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-163">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="cc047-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-164">통화 중에 최대 네트워크 SPECIALIST 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-166">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="cc047-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-167">지터로 인해 네트워크 SPECIALIST 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-169">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="cc047-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-170">패킷 손실로 인해 네트워크 SPECIALIST 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-172">int</span><span class="sxs-lookup"><span data-stu-id="cc047-172">int</span></span></p></td>
<td><p><span data-ttu-id="cc047-173">외부</span><span class="sxs-lookup"><span data-stu-id="cc047-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cc047-174">PayloadDescription 테이블에서 참조 되는 통화에 사용 되는 오디오 코덱입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-176">int</span><span class="sxs-lookup"><span data-stu-id="cc047-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-177">오디오 스트림의 샘플링 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-178"><strong>왕복이</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-179">int</span><span class="sxs-lookup"><span data-stu-id="cc047-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-180">RTCP 통계에서 왕복 시간을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="cc047-181">적절 한 품질을 위해서는 100ms 보다 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-183">int</span><span class="sxs-lookup"><span data-stu-id="cc047-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-184">오디오 스트림의 최대 라운드트립 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-186">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="cc047-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-187">통화에 대 한 평균 광대역 네트워크 SPECIALIST.</span><span class="sxs-lookup"><span data-stu-id="cc047-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="cc047-188">이 메트릭은 사용 되는 패킷 손실, 지터 및 코덱에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="cc047-189">범위는 [1.0에서 5.0]입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-191">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="cc047-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-192">통화에 대 한 최소 광대역 네트워크 SPECIALIST.</span><span class="sxs-lookup"><span data-stu-id="cc047-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-194">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="cc047-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-195">음성 수준, 노이즈 수준 및 캡처 장치 특성을 포함 하 여 발송 된 오디오에 대 한 평균 예측 광대역 SPECIALIST 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-197">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="cc047-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-198">통화에 대 한 최소 SendListenMOS입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-200">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="cc047-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-201">음성 수준, 소음 수준, 코덱, 네트워크 상태 및 캡처 장치 특성을 포함 하 여 네트워크에서 받은 오디오에 대 한 평균 예측 광대역 SPECIALIST 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-203">10 진수 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="cc047-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-204">통화에 대 한 최소 RecvListenMOS입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-205"><strong>오디오 및 사용</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-206">다소</span><span class="sxs-lookup"><span data-stu-id="cc047-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-207">오디오 FEC 통화에 사용 되었는지 여부를 나타내는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-209">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cc047-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-210">오디오 치유에서 생성 한 숨겨진 샘플의 평균 비율을 일반적인 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-212">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cc047-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-213">표준 샘플에 대 한 오디오 치유에서 생성 된 늘이기 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-215">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="cc047-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-216">오디오 치유에서 생성 한 압축 샘플의 평균 비율을 일반적인 샘플로 나타낸 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-217"><strong>Ipsec</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-218">다소</span><span class="sxs-lookup"><span data-stu-id="cc047-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-219">수신기 쪽에 있는 스트림 데이터를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-220"><strong>위한</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-221">다소</span><span class="sxs-lookup"><span data-stu-id="cc047-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-222">보낸 사람 측에 있는 스트림 데이터를 수신 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-224">다소</span><span class="sxs-lookup"><span data-stu-id="cc047-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cc047-225">1은 스트림 방향이 호출자에서 호출 수신자 까지의 것임을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="cc047-226">0은 스트림 방향이 피호출자부터 호출자에 게 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-228">o</span><span class="sxs-lookup"><span data-stu-id="cc047-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-229">지터 도착 시간에 대 한 표준 편차입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="cc047-230">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-232">o</span><span class="sxs-lookup"><span data-stu-id="cc047-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-233">Healer에서 숨겨진 패킷의 최대 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="cc047-234">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-236">o</span><span class="sxs-lookup"><span data-stu-id="cc047-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-237">Healer에서 숨겨진 패킷의 비율에 대 한 표준 편차입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="cc047-238">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-240">o</span><span class="sxs-lookup"><span data-stu-id="cc047-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-241">Healer에서 손실 된 패킷의 총 수를 수신 하 여 받은 패킷의 총량을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="cc047-242">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-244">o</span><span class="sxs-lookup"><span data-stu-id="cc047-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-245">받은 총 패킷 수와 비교 하 여 사용한 착신 전환 오류 수정 패킷의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="cc047-246">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-248">o</span><span class="sxs-lookup"><span data-stu-id="cc047-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-249">Healer에서 압축 한 최대 오디오 패킷 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="cc047-250">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-252">o</span><span class="sxs-lookup"><span data-stu-id="cc047-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-253">통화가 손실 혼잡 상태에 있는 시간의 백분율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="cc047-254">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-256">o</span><span class="sxs-lookup"><span data-stu-id="cc047-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-257">네트워크 패킷의 지연 도착으로 인해 혼잡이 있는 통화의 백분율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="cc047-258">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-260">o</span><span class="sxs-lookup"><span data-stu-id="cc047-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-261">통화가 네트워크 리소스에 대해 경쟁 하는 시간의 백분율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="cc047-262">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-264">int</span><span class="sxs-lookup"><span data-stu-id="cc047-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-265">통화 중 측정 되는 최소 대역폭 예상 양입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="cc047-266">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-268">int</span><span class="sxs-lookup"><span data-stu-id="cc047-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-269">통화 중에 측정 되는 최대 대역폭 예상 금액입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="cc047-270">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-272">int</span><span class="sxs-lookup"><span data-stu-id="cc047-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-273">통화 중에 측정 되는 대역폭 예상의 표준 편차입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="cc047-274">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-276">int</span><span class="sxs-lookup"><span data-stu-id="cc047-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-277">통화 중 측정 되는 평균 대역폭 예상 금액입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="cc047-278">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-280">o</span><span class="sxs-lookup"><span data-stu-id="cc047-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-281">단방향 총 대기 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-281">Total amount of one-way latency.</span></span> <span data-ttu-id="cc047-282">상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="cc047-283">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-285">o</span><span class="sxs-lookup"><span data-stu-id="cc047-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-286">평균 단방향 대기 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-286">Average amount of one-way latency.</span></span> <span data-ttu-id="cc047-287">상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="cc047-288">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-290">o</span><span class="sxs-lookup"><span data-stu-id="cc047-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-291">단방향 대기 시간의 최대 양입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="cc047-292">상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="cc047-293">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-295">int</span><span class="sxs-lookup"><span data-stu-id="cc047-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-296">전체 단방향 버스트 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="cc047-297">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="cc047-298">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="cc047-299">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-301">o</span><span class="sxs-lookup"><span data-stu-id="cc047-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-302">전체 단방향 버스트 밀도.</span><span class="sxs-lookup"><span data-stu-id="cc047-302">Total one-way burst density.</span></span> <span data-ttu-id="cc047-303">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="cc047-304">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="cc047-305">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-307">o</span><span class="sxs-lookup"><span data-stu-id="cc047-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-308">전체 단방향 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-308">Total one-way burst duration.</span></span> <span data-ttu-id="cc047-309">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="cc047-310">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="cc047-311">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-313">int</span><span class="sxs-lookup"><span data-stu-id="cc047-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-314">전체 단방향 간격이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="cc047-315">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="cc047-316">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="cc047-317">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-319">o</span><span class="sxs-lookup"><span data-stu-id="cc047-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-320">전체 단방향 간격 밀도.</span><span class="sxs-lookup"><span data-stu-id="cc047-320">Total one-way gap density.</span></span> <span data-ttu-id="cc047-321">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="cc047-322">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="cc047-323">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-325">o</span><span class="sxs-lookup"><span data-stu-id="cc047-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-326">전체 단방향 간격 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-326">Total one-way gap duration.</span></span> <span data-ttu-id="cc047-327">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="cc047-328">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="cc047-329">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-331">o</span><span class="sxs-lookup"><span data-stu-id="cc047-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-332">스테레오로 디코딩된 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="cc047-333">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-335">o</span><span class="sxs-lookup"><span data-stu-id="cc047-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-336">음향 반향 제거 기 스테레오로 렌더링 되는 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="cc047-337">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-338"><strong>오디오 및이 어//또는 r</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-339">o</span><span class="sxs-lookup"><span data-stu-id="cc047-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-340">전달 오류 수정 후 패킷 손실 율이 적용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="cc047-341">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc047-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-343">o</span><span class="sxs-lookup"><span data-stu-id="cc047-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-344">스테레오로 인코딩된 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="cc047-345">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc047-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="cc047-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="cc047-347">o</span><span class="sxs-lookup"><span data-stu-id="cc047-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="cc047-348">음향 반향 제거 기 스테레오로 캡처한 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="cc047-349">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cc047-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

