---
title: 'Lync Server 2013: VideoStream 테이블'
description: 'Lync Server 2013: VideoStream 테이블'
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
ms.openlocfilehash: 0d741478e1f6290685181bff471f143e41ce9ca1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567994"
---
# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="a5d8b-103">Lync Server 2013의 VideoStream 테이블</span><span class="sxs-lookup"><span data-stu-id="a5d8b-103">VideoStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5d8b-104">_**마지막으로 수정 된 항목:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="a5d8b-104">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="a5d8b-105">각 레코드는 하나의 비디오 스트림을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-105">Each record represents one video stream.</span></span> <span data-ttu-id="a5d8b-106">일반적으로 하나의 비디오 미디어 회선에는 두 개의 비디오 스트림이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-106">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5d8b-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a5d8b-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a5d8b-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a5d8b-110"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-111"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="a5d8b-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="a5d8b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a5d8b-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a5d8b-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-116">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-116">int</span></span></p></td>
<td><p><span data-ttu-id="a5d8b-117">Primary</span><span class="sxs-lookup"><span data-stu-id="a5d8b-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="a5d8b-118"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 되는 R</span><span class="sxs-lookup"><span data-stu-id="a5d8b-118">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="a5d8b-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a5d8b-121">Primary</span><span class="sxs-lookup"><span data-stu-id="a5d8b-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="a5d8b-122"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-123"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-124">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-124">int</span></span></p></td>
<td><p><span data-ttu-id="a5d8b-125">Primary</span><span class="sxs-lookup"><span data-stu-id="a5d8b-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="a5d8b-126">미디어 회선 내의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-127"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-127"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-128">smallint</span><span class="sxs-lookup"><span data-stu-id="a5d8b-128">smallint</span></span></p></td>
<td><p><span data-ttu-id="a5d8b-129">외부, 기본</span><span class="sxs-lookup"><span data-stu-id="a5d8b-129">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="a5d8b-130">페이로드 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-130">Payload description.</span></span> <span data-ttu-id="a5d8b-131">자세한 내용은 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013의 PayloadDescription 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-131">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-133">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-134">RTCP(Real Time Control Protocol) 통계로부터 가져온 평균 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-134">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-136">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-136">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-137">비디오 세션 중의 최대 네트워크 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-137">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-138"><strong>왕복</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-138"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-139">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-139">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-140">RTCP 통계로부터의 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-140">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-141"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-141"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-142">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-143">비디오 스트림에 대 한 최대 왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-143">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-144"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-144"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-145">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="a5d8b-145">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-146">통화 중 평균 패킷 손실 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-146">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-147"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-147"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-148">10 진수 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="a5d8b-148">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-149">통화 중 관측된 최대 패킷 손실입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-149">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-151">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-151">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-152">비디오 스트림에 대한 패킷 수입니다(실시간 전송 프로토콜, RTP).</span><span class="sxs-lookup"><span data-stu-id="a5d8b-152">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-153"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-154">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-154">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-155">비디오 스트림에 대 한 대역폭 예상</span><span class="sxs-lookup"><span data-stu-id="a5d8b-155">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-156"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-156"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-157">char (9)</span><span class="sxs-lookup"><span data-stu-id="a5d8b-157">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-p103">픽셀 너비와 픽셀 높이를 곱한 수치의 비디오 해상도입니다. 문자열로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-160"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-160"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-161">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-161">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-162">비디오 스트림의 평균 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-162">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-163"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-163"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-164">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="a5d8b-164">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-165">수신 된 비디오 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-165">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-166"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-166"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-167">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="a5d8b-167">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-168">전송 된 비디오 프레임 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-168">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-169"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-169"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-170">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-171">비디오 세션 중의 최대 비디오 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-171">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-172"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-172"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-173">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="a5d8b-173">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-174">총 비디오 프레임 중 손실 된 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-174">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-175"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-175"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-176">비트만</span><span class="sxs-lookup"><span data-stu-id="a5d8b-176">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-177">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-177">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-179">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="a5d8b-179">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-180">총 비디오 프레임 중 손실 된 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-180">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-181"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-181"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-182">tinyint</span><span class="sxs-lookup"><span data-stu-id="a5d8b-182">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-183">CIF (Common 교환 형식) 해상도 인 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-183">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-184"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-184"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-185">tinyint</span><span class="sxs-lookup"><span data-stu-id="a5d8b-185">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-186">VGA 해상도 인 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-186">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-187"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-187"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-188">tinyint</span><span class="sxs-lookup"><span data-stu-id="a5d8b-188">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-189">HD720 resolution에 있던 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-189">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-190"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-190"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-191">tinyint</span><span class="sxs-lookup"><span data-stu-id="a5d8b-191">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-192">프레임 놓기가 없는 통화 기간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-192">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-193"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-193"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-194">tinyint</span><span class="sxs-lookup"><span data-stu-id="a5d8b-194">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-195">B 프레임 놓기가 있는 통화 기간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-195">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-196"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-196"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-197">tinyint</span><span class="sxs-lookup"><span data-stu-id="a5d8b-197">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-198">BP 프레임 낙하의 통화 시간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-198">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-199"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-199"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-200">tinyint</span><span class="sxs-lookup"><span data-stu-id="a5d8b-200">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-201">BPSP 프레임 하강 통화 지속 시간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-201">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-202"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-202"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="a5d8b-203">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-204">BPSPI 프레임 하강 통화 기간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-204">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-205"><strong>인바운드</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-205"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-206">비트만</span><span class="sxs-lookup"><span data-stu-id="a5d8b-206">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-207">수신기 쪽의 Stream 데이터를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-207">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-208"><strong>아웃 바운드</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-208"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-209">비트만</span><span class="sxs-lookup"><span data-stu-id="a5d8b-209">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-210">보낸 사람 쪽의 스트림 데이터가 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-210">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-211"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-211"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-212">비트만</span><span class="sxs-lookup"><span data-stu-id="a5d8b-212">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a5d8b-213">1은 스트림 방향이 발신자에서 수신자의 방향임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-213">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="a5d8b-214">0은 스트림 방향이 수신자에서 발신자의 방향임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-214">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-215"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-215"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-216">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-216">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-217">통화가 손실 혼잡 상태에 있는 시간의 백분율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-217">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="a5d8b-218">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-218">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-219"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-219"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-220">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-220">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-221">네트워크 패킷의 지연 도착으로 인해 혼잡이 발생 한 통화 비율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-221">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="a5d8b-222">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-222">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-223"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-223"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-224">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-224">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-225">호출이 네트워크 리소스를 경합 하는 시간 비율을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-225">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="a5d8b-226">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-227"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-227"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-228">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-229">통화 중 측정 된 최소 대역폭 예상 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-229">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="a5d8b-230">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-231"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-231"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-232">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-233">통화 중 측정 된 최대 대역폭 예상 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-233">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="a5d8b-234">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-235"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-235"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-236">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-237">통화 중 측정 된 대역폭 예상 범위의 표준 편차입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-237">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="a5d8b-238">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-239"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-239"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-240">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-241">통화 중 측정 된 평균 대역폭 양입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-241">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="a5d8b-242">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-243"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-243"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-244">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-245">끝점에서 네트워크 연결이 멀티뷰 video를 지원 하지 않는 것으로 확인 된 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-245">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="a5d8b-246">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-247"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-247"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-248">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-p104">총 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="a5d8b-251">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-252"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-252"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-253">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-p105">평균 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="a5d8b-256">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-256">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-257"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-257"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-258">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-p106">최대 단방향 대기 시간입니다. 상대 단방향 대기 시간이 클라이언트와 서버 간의 지연을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="a5d8b-261">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-261">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-262"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-262"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-263">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-263">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-p107">총 단방향 버스트 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a5d8b-267">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-268"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-268"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-269">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-p108">총 단방향 버스트 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a5d8b-273">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-273">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-274"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-274"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-275">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-275">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-p109">총 단방향 버스트 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a5d8b-279">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-280"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-280"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-281">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-281">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-p110">총 단방향 갭 발생 수입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a5d8b-285">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-285">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-286"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-286"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-287">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-287">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-p111">총 단방향 갭 밀도입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a5d8b-291">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-291">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-292"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-292"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-293">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-293">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-p112">총 단방향 갭 기간입니다. "버스트"가 발생한 전송은 데이터가 안정적 스트림이 아닌 예측 불가능한 버스트로 흐르는 전송입니다. 갭은 이러한 버스트 간의 지연을 나타냅니다. 이 메트릭은 클라이언트와 서버 간의 데이터 흐름을 측정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a5d8b-297">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-297">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-298"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-298"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-299">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="a5d8b-299">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-300">비디오 패킷이 손실된 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-300">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="a5d8b-301">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-301">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-302"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-302"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-303">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-303">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-304">비디오에 할당된 평균 대역폭 양입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-304">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="a5d8b-305">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-306"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-306"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-307">smallint</span><span class="sxs-lookup"><span data-stu-id="a5d8b-307">smallint</span></span></p></td>
<td><p><span data-ttu-id="a5d8b-308">외부</span><span class="sxs-lookup"><span data-stu-id="a5d8b-308">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a5d8b-309">보낸 사람이 사용 하는 비디오 코덱 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-309">Type of video codecs used by the sender.</span></span> <span data-ttu-id="a5d8b-310">자세한 내용은 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013의 CodecDescription 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-310">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="a5d8b-311">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-312"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-312"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-313">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-314">보낸 사람이 사용 하는 해상도 너비입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-314">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="a5d8b-315">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-315">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-316"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-316"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-317">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-317">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-318">보낸 사람이 사용한 해상도 높이입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-318">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="a5d8b-319">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-320"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-320"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-321">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-322">보낸 사람이 사용 하는 평균 비디오 프레임 속도 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-322">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="a5d8b-323">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-324"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-324"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-325">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-326">보낸 사람에 대 한 최대 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-326">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="a5d8b-327">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-327">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-328"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-328"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-329">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-329">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-330">보낸 사람에 대 한 평균 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-330">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-331"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-331"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-332">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-332">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-333">보낸 사람이 사용 하는 비디오 스트림의 최대 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-333">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="a5d8b-334">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-335"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-335"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-336">smallint</span><span class="sxs-lookup"><span data-stu-id="a5d8b-336">smallint</span></span></p></td>
<td><p><span data-ttu-id="a5d8b-337">외부</span><span class="sxs-lookup"><span data-stu-id="a5d8b-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a5d8b-338">수신자가 사용 하는 비디오 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-338">Video codes used by the receiver.</span></span> <span data-ttu-id="a5d8b-339">자세한 내용은 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013의 CodecDescription 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-339">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="a5d8b-340">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-341"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-341"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-342">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-343">수신자가 사용한 해상도 너비입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-343">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="a5d8b-344">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-344">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-345"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-345"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-346">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-346">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-347">수신자가 사용한 해상도 높이입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-347">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="a5d8b-348">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-348">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-349"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-349"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-350">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-350">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-351">수신자가 사용한 비디오 프레임 속도의 평균입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-351">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="a5d8b-352">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-352">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-353"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-353"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-354">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-354">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-355">수신자의 최대 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-355">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="a5d8b-356">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-356">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-357"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-357"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-358">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-358">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-359">수신자의 평균 비트 전송률입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-359">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="a5d8b-360">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-360">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-361"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-361"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-362">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-362">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-363">받는 사람에 대 한 최대 비디오 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-363">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="a5d8b-364">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-364">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-365"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-365"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-366">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-366">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-367">받는 사람에 대 한 최소 비디오 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-367">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="a5d8b-368">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-368">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-369"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-369"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-370">int</span><span class="sxs-lookup"><span data-stu-id="a5d8b-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-371">수신기의 비디오 모드 (예: 갤러리 또는 단일 스트림)입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-371">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="a5d8b-372">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-372">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-373"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-373"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-374">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-374">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-375">전달 오류 정정이 적용 된 후의 패킷 손실 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-375">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="a5d8b-376">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-376">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-377"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-377"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-378">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-378">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-379">동적 기능 플래그가 활성 상태인 시간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-379">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="a5d8b-380">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-380">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-381"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-381"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-382">char (9)</span><span class="sxs-lookup"><span data-stu-id="a5d8b-382">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-383">통화 중 측정 된 최소 해상도입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-383">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="a5d8b-384">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-384">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-385"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-385"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-386">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-386">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-387">낮은 비트 전송률 임계값에 해당 하는 통화 비율 (초당 70 킬로 비트)입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-387">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="a5d8b-388">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-388">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-389"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-389"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-390">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-391">낮은 프레임 속도 임계값 (초당 7.5 프레임, 인바운드) 아래의 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-391">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="a5d8b-392">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-392">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-393"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-393"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-394">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-395">최저 해상도에서 발생 한 통화 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-395">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="a5d8b-396">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="a5d8b-397">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-397">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5d8b-398"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-398"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-399">식</span><span class="sxs-lookup"><span data-stu-id="a5d8b-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-400">통화 길이 (초)입니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-400">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="a5d8b-401">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-401">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5d8b-402"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="a5d8b-402"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="a5d8b-403">비트만</span><span class="sxs-lookup"><span data-stu-id="a5d8b-403">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a5d8b-404">데이터가 여러 통화 로부터 집계 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-404">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="a5d8b-405">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d8b-405">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

