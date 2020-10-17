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
ms.openlocfilehash: ef5c417ff391bb3ec5954cf12d00f6de3d2e6d9b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518565"
---
# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="86413-102">Lync Server 2013의 VideoStream 테이블</span><span class="sxs-lookup"><span data-stu-id="86413-102">VideoStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86413-103">_**마지막으로 수정 된 항목:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="86413-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="86413-104">각 레코드는 하나의 비디오 스트림을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="86413-104">Each record represents one video stream.</span></span> <span data-ttu-id="86413-105">일반적으로 하나의 비디오 미디어 회선에는 두 개의 비디오 스트림이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86413-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="86413-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="86413-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="86413-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="86413-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="86413-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="86413-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="86413-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86413-110"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="86413-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-111">datetime</span><span class="sxs-lookup"><span data-stu-id="86413-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="86413-112">Primary</span><span class="sxs-lookup"><span data-stu-id="86413-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="86413-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86413-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="86413-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-115">int</span><span class="sxs-lookup"><span data-stu-id="86413-115">int</span></span></p></td>
<td><p><span data-ttu-id="86413-116">Primary</span><span class="sxs-lookup"><span data-stu-id="86413-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="86413-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 되는 R</span><span class="sxs-lookup"><span data-stu-id="86413-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="86413-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="86413-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="86413-120">Primary</span><span class="sxs-lookup"><span data-stu-id="86413-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="86413-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86413-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="86413-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-123">int</span><span class="sxs-lookup"><span data-stu-id="86413-123">int</span></span></p></td>
<td><p><span data-ttu-id="86413-124">Primary</span><span class="sxs-lookup"><span data-stu-id="86413-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="86413-125">미디어 회선 내의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="86413-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-127">smallint</span><span class="sxs-lookup"><span data-stu-id="86413-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="86413-128">외부, 기본</span><span class="sxs-lookup"><span data-stu-id="86413-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="86413-129">페이로드 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-129">Payload description.</span></span> <span data-ttu-id="86413-130">자세한 내용은 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="86413-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="86413-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-132">int</span><span class="sxs-lookup"><span data-stu-id="86413-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-133">RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="86413-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-135">int</span><span class="sxs-lookup"><span data-stu-id="86413-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-136">비디오 세션 중의 최대 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-137"><strong>왕복</strong></span><span class="sxs-lookup"><span data-stu-id="86413-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-138">int</span><span class="sxs-lookup"><span data-stu-id="86413-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-139">RTCP 통계로부터의 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="86413-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-141">int</span><span class="sxs-lookup"><span data-stu-id="86413-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-142">비디오 스트림에 대 한 최대 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="86413-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-144">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="86413-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-145">통화 중 평균 패킷 손실 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="86413-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-147">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="86413-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-148">통화 중 관측된 최대 패킷 손실입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="86413-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-150">int</span><span class="sxs-lookup"><span data-stu-id="86413-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-151">비디오 스트림에 대한 패킷 수입니다(실시간 전송 프로토콜, RTP).</span><span class="sxs-lookup"><span data-stu-id="86413-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-152"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="86413-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-153">int</span><span class="sxs-lookup"><span data-stu-id="86413-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-154">비디오 스트림에 대 한 대역폭 예상</span><span class="sxs-lookup"><span data-stu-id="86413-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="86413-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-156">char (9)</span><span class="sxs-lookup"><span data-stu-id="86413-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-p103">픽셀 너비와 픽셀 높이를 곱한 수치의 비디오 해상도입니다. 문자열로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="86413-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="86413-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-160">int</span><span class="sxs-lookup"><span data-stu-id="86413-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-161">비디오 스트림의 평균 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="86413-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-163">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="86413-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-164">수신 된 비디오 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="86413-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-166">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="86413-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-167">전송 된 비디오 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="86413-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-169">int</span><span class="sxs-lookup"><span data-stu-id="86413-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-170">비디오 세션 중의 최대 비디오 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="86413-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-172">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="86413-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-173">총 비디오 프레임 중 손실 된 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="86413-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-175">비트만</span><span class="sxs-lookup"><span data-stu-id="86413-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-176">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="86413-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-178">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="86413-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-179">총 비디오 프레임 중 손실 된 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="86413-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="86413-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-182">CIF (Common 교환 형식) 해상도 인 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="86413-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="86413-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-185">VGA 해상도 인 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="86413-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="86413-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-188">HD720 resolution에 있던 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="86413-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="86413-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-191">프레임 놓기가 없는 통화 기간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="86413-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="86413-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-194">B 프레임 놓기가 있는 통화 기간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="86413-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="86413-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-197">BP 프레임 낙하의 통화 시간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="86413-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="86413-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-200">BPSP 프레임 하강 통화 지속 시간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="86413-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="86413-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-203">BPSPI 프레임 하강 통화 기간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-204"><strong>인바운드</strong></span><span class="sxs-lookup"><span data-stu-id="86413-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-205">비트만</span><span class="sxs-lookup"><span data-stu-id="86413-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-206">수신기 쪽의 Stream 데이터를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="86413-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-207"><strong>아웃 바운드</strong></span><span class="sxs-lookup"><span data-stu-id="86413-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-208">비트만</span><span class="sxs-lookup"><span data-stu-id="86413-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-209">보낸 사람 쪽의 스트림 데이터가 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86413-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="86413-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-211">비트만</span><span class="sxs-lookup"><span data-stu-id="86413-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="86413-212">1은 스트림 방향이 발신자에서 수신자의 방향임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="86413-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="86413-213">0은 스트림 방향이 수신자에서 발신자의 방향임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="86413-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="86413-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-215">식</span><span class="sxs-lookup"><span data-stu-id="86413-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-216">통화가 손실 혼잡 상태에 있는 시간의 백분율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="86413-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="86413-217">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="86413-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-219">식</span><span class="sxs-lookup"><span data-stu-id="86413-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-220">네트워크 패킷의 지연 도착으로 인해 혼잡이 발생 한 통화 비율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="86413-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="86413-221">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="86413-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-223">식</span><span class="sxs-lookup"><span data-stu-id="86413-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-224">호출이 네트워크 리소스를 경합 하는 시간 비율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="86413-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="86413-225">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="86413-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-227">int</span><span class="sxs-lookup"><span data-stu-id="86413-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-228">통화 중 측정 된 최소 대역폭 예상 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="86413-229">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="86413-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-231">int</span><span class="sxs-lookup"><span data-stu-id="86413-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-232">통화 중 측정 된 최대 대역폭 예상 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="86413-233">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="86413-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-235">int</span><span class="sxs-lookup"><span data-stu-id="86413-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-236">통화 중 측정 된 대역폭 예상 범위의 표준 편차입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="86413-237">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="86413-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-239">int</span><span class="sxs-lookup"><span data-stu-id="86413-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-240">통화 중 측정 된 평균 대역폭 양입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="86413-241">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="86413-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-243">식</span><span class="sxs-lookup"><span data-stu-id="86413-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-244">끝점에서 네트워크 연결이 멀티뷰 video를 지원 하지 않는 것으로 확인 된 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="86413-245">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="86413-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-247">식</span><span class="sxs-lookup"><span data-stu-id="86413-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-p104">총 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="86413-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="86413-250">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="86413-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-252">식</span><span class="sxs-lookup"><span data-stu-id="86413-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-p105">평균 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="86413-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="86413-255">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="86413-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-257">식</span><span class="sxs-lookup"><span data-stu-id="86413-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-p106">최대 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="86413-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="86413-260">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86413-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-262">int</span><span class="sxs-lookup"><span data-stu-id="86413-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-p107">총 단방향 버스트 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="86413-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="86413-266">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86413-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-268">int</span><span class="sxs-lookup"><span data-stu-id="86413-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-p108">총 단방향 버스트 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="86413-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="86413-272">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86413-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-274">식</span><span class="sxs-lookup"><span data-stu-id="86413-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-p109">총 단방향 버스트 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="86413-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="86413-278">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="86413-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-280">int</span><span class="sxs-lookup"><span data-stu-id="86413-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-p110">총 단방향 갭 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="86413-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="86413-284">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="86413-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-286">식</span><span class="sxs-lookup"><span data-stu-id="86413-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-p111">총 단방향 갭 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="86413-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="86413-290">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="86413-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-292">식</span><span class="sxs-lookup"><span data-stu-id="86413-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-p112">총 단방향 갭 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="86413-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="86413-296">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="86413-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-298">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="86413-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-299">비디오 패킷이 손실된 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="86413-300">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="86413-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-302">int</span><span class="sxs-lookup"><span data-stu-id="86413-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-303">비디오에 할당된 평균 대역폭 양입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="86413-304">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="86413-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-306">smallint</span><span class="sxs-lookup"><span data-stu-id="86413-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="86413-307">외부</span><span class="sxs-lookup"><span data-stu-id="86413-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86413-308">보낸 사람이 사용 하는 비디오 코덱 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="86413-309">자세한 내용은 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013의 CodecDescription 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="86413-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="86413-310">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="86413-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-312">int</span><span class="sxs-lookup"><span data-stu-id="86413-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-313">보낸 사람이 사용 하는 해상도 너비입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="86413-314">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="86413-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-316">int</span><span class="sxs-lookup"><span data-stu-id="86413-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-317">보낸 사람이 사용한 해상도 높이입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="86413-318">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="86413-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-320">식</span><span class="sxs-lookup"><span data-stu-id="86413-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-321">보낸 사람이 사용 하는 평균 비디오 프레임 속도 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="86413-322">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="86413-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-324">int</span><span class="sxs-lookup"><span data-stu-id="86413-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-325">보낸 사람에 대 한 최대 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="86413-326">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="86413-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-328">int</span><span class="sxs-lookup"><span data-stu-id="86413-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-329">보낸 사람에 대 한 평균 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="86413-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-331">int</span><span class="sxs-lookup"><span data-stu-id="86413-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-332">보낸 사람이 사용 하는 비디오 스트림의 최대 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="86413-333">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="86413-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-335">smallint</span><span class="sxs-lookup"><span data-stu-id="86413-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="86413-336">외부</span><span class="sxs-lookup"><span data-stu-id="86413-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="86413-337">수신자가 사용 하는 비디오 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-337">Video codes used by the receiver.</span></span> <span data-ttu-id="86413-338">자세한 내용은 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013의 CodecDescription 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="86413-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="86413-339">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="86413-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-341">int</span><span class="sxs-lookup"><span data-stu-id="86413-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-342">수신자가 사용한 해상도 너비입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="86413-343">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="86413-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-345">int</span><span class="sxs-lookup"><span data-stu-id="86413-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-346">수신자가 사용한 해상도 높이입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="86413-347">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="86413-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-349">식</span><span class="sxs-lookup"><span data-stu-id="86413-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-350">수신자가 사용한 비디오 프레임 속도의 평균입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="86413-351">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="86413-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-353">int</span><span class="sxs-lookup"><span data-stu-id="86413-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-354">수신자의 최대 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="86413-355">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="86413-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-357">int</span><span class="sxs-lookup"><span data-stu-id="86413-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-358">수신자의 평균 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="86413-359">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="86413-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-361">int</span><span class="sxs-lookup"><span data-stu-id="86413-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-362">받는 사람에 대 한 최대 비디오 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="86413-363">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="86413-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-365">int</span><span class="sxs-lookup"><span data-stu-id="86413-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-366">받는 사람에 대 한 최소 비디오 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="86413-367">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="86413-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-369">int</span><span class="sxs-lookup"><span data-stu-id="86413-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-370">수신기의 비디오 모드 (예: 갤러리 또는 단일 스트림)입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="86413-371">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="86413-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-373">식</span><span class="sxs-lookup"><span data-stu-id="86413-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-374">전달 오류 정정이 적용 된 후의 패킷 손실 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="86413-375">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="86413-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-377">식</span><span class="sxs-lookup"><span data-stu-id="86413-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-378">동적 기능 플래그가 활성 상태인 시간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="86413-379">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="86413-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-381">char (9)</span><span class="sxs-lookup"><span data-stu-id="86413-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-382">통화 중 측정 된 최소 해상도입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="86413-383">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="86413-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-385">식</span><span class="sxs-lookup"><span data-stu-id="86413-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-386">낮은 비트 전송률 임계값에 해당 하는 통화 비율 (초당 70 킬로 비트)입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="86413-387">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="86413-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-389">식</span><span class="sxs-lookup"><span data-stu-id="86413-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-390">낮은 프레임 속도 임계값 (초당 7.5 프레임, 인바운드) 아래의 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="86413-391">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="86413-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-393">식</span><span class="sxs-lookup"><span data-stu-id="86413-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-394">최저 해상도에서 발생 한 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="86413-395">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="86413-396">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86413-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="86413-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-398">식</span><span class="sxs-lookup"><span data-stu-id="86413-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-399">통화 길이 (초)입니다.</span><span class="sxs-lookup"><span data-stu-id="86413-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="86413-400">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86413-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="86413-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="86413-402">비트만</span><span class="sxs-lookup"><span data-stu-id="86413-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="86413-403">데이터가 여러 통화 로부터 집계 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="86413-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="86413-404">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86413-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

