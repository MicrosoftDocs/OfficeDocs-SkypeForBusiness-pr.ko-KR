---
title: 'Lync Server 2013: VideoStream 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 674d013faca3b43db04d2c5b4802103def83dbd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="0d70a-102">Lync Server 2013의 VideoStream 테이블</span><span class="sxs-lookup"><span data-stu-id="0d70a-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d70a-103">_**마지막으로 수정한 주제:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="0d70a-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="0d70a-104">각 레코드는 하나의 비디오 스트림을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-104">Each record represents one video stream.</span></span> <span data-ttu-id="0d70a-105">하나의 비디오 미디어 라인에는 일반적으로 두 개의 비디오 스트림이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d70a-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="0d70a-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="0d70a-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="0d70a-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="0d70a-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="0d70a-112">주요한</span><span class="sxs-lookup"><span data-stu-id="0d70a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="0d70a-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-115">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-115">int</span></span></p></td>
<td><p><span data-ttu-id="0d70a-116">주요한</span><span class="sxs-lookup"><span data-stu-id="0d70a-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="0d70a-117">R <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="0d70a-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0d70a-120">주요한</span><span class="sxs-lookup"><span data-stu-id="0d70a-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="0d70a-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-123">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-123">int</span></span></p></td>
<td><p><span data-ttu-id="0d70a-124">주요한</span><span class="sxs-lookup"><span data-stu-id="0d70a-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="0d70a-125">미디어 라인 내의 고유 ID.</span><span class="sxs-lookup"><span data-stu-id="0d70a-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-127">smallint</span><span class="sxs-lookup"><span data-stu-id="0d70a-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="0d70a-128">외국, 기본</span><span class="sxs-lookup"><span data-stu-id="0d70a-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="0d70a-129">페이로드 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-129">Payload description.</span></span> <span data-ttu-id="0d70a-130">자세한 내용은 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d70a-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-132">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-133">RTCP (실시간 제어 프로토콜) 통계의 평균 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-135">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-136">비디오 세션 중에 최대 네트워크 지터.</span><span class="sxs-lookup"><span data-stu-id="0d70a-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-137"><strong>왕복이</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-138">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-139">RTCP 통계에서 왕복 시간을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-141">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-142">비디오 스트림의 최대 라운드 트립 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-144">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="0d70a-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-145">통화 중의 평균 패킷 손실 율입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-147">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="0d70a-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-148">통화 중에 최대 패킷 손실이 관찰 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-150">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-151">비디오 스트림의 패킷 개수 (리얼 시간 전송 프로토콜, RTP).</span><span class="sxs-lookup"><span data-stu-id="0d70a-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-152"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-153">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-154">비디오 스트림의 대역폭을 예측 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-156">char (9)</span><span class="sxs-lookup"><span data-stu-id="0d70a-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-157">픽셀 너비를 픽셀 높이로 곱한 비디오 해상도입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="0d70a-158">문자열로 보고 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-160">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-161">비디오 스트림의 평균 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-163">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="0d70a-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-164">수신 된 비디오 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-166">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="0d70a-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-167">전송 된 비디오 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-169">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-170">비디오 세션 중의 최대 비디오 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-172">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="0d70a-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-173">손실 된 총 비디오 프레임의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-175">다소</span><span class="sxs-lookup"><span data-stu-id="0d70a-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-176">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-178">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="0d70a-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-179">손실 된 총 비디오 프레임의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="0d70a-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-182">CIF (Common 인터체인지 Format) 해상도에 있던 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="0d70a-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-185">VGA 해상도의 통화에 대 한 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="0d70a-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-188">HD720 해상도에 있던 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="0d70a-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-191">프레임 놓기가 없는 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="0d70a-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-194">B 프레임 놓기가 있는 통화 시간의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="0d70a-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-197">BP 프레임 낙하의 통화 시간 백분율.</span><span class="sxs-lookup"><span data-stu-id="0d70a-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="0d70a-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-200">BPSP 프레임 놓기를 사용 하는 통화 시간의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="0d70a-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-203">BPSPI 프레임 낙하에 대 한 통화 시간의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-204"><strong>Ipsec</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-205">다소</span><span class="sxs-lookup"><span data-stu-id="0d70a-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-206">수신기 쪽에 있는 스트림 데이터를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-207"><strong>위한</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-208">다소</span><span class="sxs-lookup"><span data-stu-id="0d70a-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-209">보낸 사람 측에 있는 스트림 데이터를 수신 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-211">다소</span><span class="sxs-lookup"><span data-stu-id="0d70a-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0d70a-212">1은 스트림 방향이 호출자에서 피호출자로 되었음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="0d70a-213">0은 스트림 방향이 피호출자부터 호출자에 게 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-215">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-216">통화가 손실 혼잡 상태에 있는 시간의 백분율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="0d70a-217">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-219">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-220">네트워크 패킷의 지연 도착으로 인해 혼잡이 있는 통화의 백분율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="0d70a-221">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-223">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-224">통화가 네트워크 리소스에 대해 경쟁 하는 시간의 백분율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="0d70a-225">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-227">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-228">통화 중 측정 되는 최소 대역폭 예상 양입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="0d70a-229">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-231">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-232">통화 중에 측정 되는 최대 대역폭 예상 금액입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="0d70a-233">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-235">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-236">통화 중에 측정 되는 대역폭 예상의 표준 편차입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="0d70a-237">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-239">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-240">통화 중 측정 되는 평균 대역폭 예상 금액입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="0d70a-241">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-243">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-244">끝점에서 네트워크 연결이 multiview video를 지원 하지 않는 것으로 결정 한 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="0d70a-245">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-247">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-248">단방향 총 대기 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-248">Total amount of one-way latency.</span></span> <span data-ttu-id="0d70a-249">상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="0d70a-250">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-252">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-253">평균 단방향 대기 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-253">Average amount of one-way latency.</span></span> <span data-ttu-id="0d70a-254">상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="0d70a-255">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-257">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-258">단방향 대기 시간의 최대 양입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="0d70a-259">상대적 단방향 대기 시간은 클라이언트와 서버 간의 지연을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="0d70a-260">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-262">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-263">전체 단방향 버스트 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="0d70a-264">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="0d70a-265">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0d70a-266">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-268">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-269">전체 단방향 버스트 밀도.</span><span class="sxs-lookup"><span data-stu-id="0d70a-269">Total one-way burst density.</span></span> <span data-ttu-id="0d70a-270">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="0d70a-271">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0d70a-272">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-274">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-275">전체 단방향 버스트 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-275">Total one-way burst duration.</span></span> <span data-ttu-id="0d70a-276">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="0d70a-277">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0d70a-278">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-280">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-281">전체 단방향 간격이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="0d70a-282">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="0d70a-283">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0d70a-284">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-286">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-287">전체 단방향 간격 밀도.</span><span class="sxs-lookup"><span data-stu-id="0d70a-287">Total one-way gap density.</span></span> <span data-ttu-id="0d70a-288">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="0d70a-289">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0d70a-290">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-292">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-293">전체 단방향 간격 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-293">Total one-way gap duration.</span></span> <span data-ttu-id="0d70a-294">"Bursty" 전송은 안정적 스트림이 아닌 버스트로 데이터가 흐르는 전송입니다. 간격은 이러한 버스트 간의 지연을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="0d70a-295">이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0d70a-296">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-298">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="0d70a-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-299">비디오 패킷이 손실 된 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="0d70a-300">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-302">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-303">비디오에 대해 할당 된 평균 대역폭 양입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="0d70a-304">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-306">smallint</span><span class="sxs-lookup"><span data-stu-id="0d70a-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="0d70a-307">외부</span><span class="sxs-lookup"><span data-stu-id="0d70a-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0d70a-308">보낸 사람이 사용 하는 비디오 코덱 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="0d70a-309">자세한 내용은 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013의 CodecDescription 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d70a-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="0d70a-310">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-312">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-313">보낸 사람이 사용 하는 해상도 너비입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="0d70a-314">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-316">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-317">보낸 사람이 사용 하는 해상도 높이입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="0d70a-318">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-320">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-321">보낸 사람이 사용한 평균 비디오 프레임 속도 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="0d70a-322">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-324">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-325">보낸 사람의 최대 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="0d70a-326">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-328">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-329">보낸 사람의 평균 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-331">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-332">보낸 사람이 사용 하는 비디오 스트림의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="0d70a-333">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-335">smallint</span><span class="sxs-lookup"><span data-stu-id="0d70a-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="0d70a-336">외부</span><span class="sxs-lookup"><span data-stu-id="0d70a-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0d70a-337">수신자가 사용 하는 영상 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-337">Video codes used by the receiver.</span></span> <span data-ttu-id="0d70a-338">자세한 내용은 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013의 CodecDescription 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d70a-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="0d70a-339">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-341">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-342">수신자가 사용 하는 해상도 너비입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="0d70a-343">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-345">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-346">수신기에서 사용 하는 해상도 높이입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="0d70a-347">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-349">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-350">수신기에서 사용 하는 평균 비디오 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="0d70a-351">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-353">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-354">받는 사람에 대 한 최대 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="0d70a-355">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-357">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-358">수신기의 평균 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="0d70a-359">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-361">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-362">수신기에 대 한 최대 비디오 스트림.</span><span class="sxs-lookup"><span data-stu-id="0d70a-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="0d70a-363">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-365">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-366">수신기의 최소 비디오 스트림</span><span class="sxs-lookup"><span data-stu-id="0d70a-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="0d70a-367">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-369">int</span><span class="sxs-lookup"><span data-stu-id="0d70a-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-370">수신기에 대 한 비디오 모드 (예: 갤러리 또는 단일 스트림)입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="0d70a-371">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-373">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-374">전달 오류 수정 후 패킷 손실 율이 적용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="0d70a-375">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-377">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-378">동적 접근 권한 플래그가 활성 상태인 시간의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="0d70a-379">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-381">char (9)</span><span class="sxs-lookup"><span data-stu-id="0d70a-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-382">통화 중에 측정 되는 최소 해상도.</span><span class="sxs-lookup"><span data-stu-id="0d70a-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="0d70a-383">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-385">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-386">낮은 비트 전송률 임계값 이하의 통화 백분율 (초당 70 킬로 비트)입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="0d70a-387">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-389">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-390">낮은 프레임 속도 임계값 미만의 통화 백분율 (7.5 프레임/초)</span><span class="sxs-lookup"><span data-stu-id="0d70a-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="0d70a-391">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-393">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-394">최저 해상도에서 발생 한 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="0d70a-395">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="0d70a-396">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-398">o</span><span class="sxs-lookup"><span data-stu-id="0d70a-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-399">통화의 길이 (초)입니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="0d70a-400">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-402">다소</span><span class="sxs-lookup"><span data-stu-id="0d70a-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0d70a-403">데이터가 여러 호출에서 집계 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="0d70a-404">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d70a-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

