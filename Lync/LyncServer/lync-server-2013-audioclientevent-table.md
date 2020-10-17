---
title: 'Lync Server 2013: 오디오 (c) Clientevent 테이블'
description: 'Lync Server 2013: 오디오 Clientevent 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2200cd9567bdd10ac4ad8f5c269062c2f5614dcb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568784"
---
# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="73fcd-103">Lync Server 2013의 오디오 Clientevent 테이블</span><span class="sxs-lookup"><span data-stu-id="73fcd-103">AudioClientEvent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73fcd-104">_**마지막으로 수정 된 항목:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="73fcd-104">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="73fcd-105">각 레코드에는 오디오 통화의 한 끝점에 대 한 클라이언트 이벤트가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-105">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="73fcd-106">일반적으로 한 통화에는 발신자 용 레코드와 수신자를 위한 레코드가 각각 하나씩 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-106">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73fcd-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="73fcd-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="73fcd-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="73fcd-110"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73fcd-111"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-112">datetime</span><span class="sxs-lookup"><span data-stu-id="73fcd-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="73fcd-113">Primary</span><span class="sxs-lookup"><span data-stu-id="73fcd-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="73fcd-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73fcd-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-116">int</span><span class="sxs-lookup"><span data-stu-id="73fcd-116">int</span></span></p></td>
<td><p><span data-ttu-id="73fcd-117">Primary</span><span class="sxs-lookup"><span data-stu-id="73fcd-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="73fcd-118"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73fcd-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="73fcd-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="73fcd-121">Primary</span><span class="sxs-lookup"><span data-stu-id="73fcd-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="73fcd-122"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73fcd-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-124">비트만</span><span class="sxs-lookup"><span data-stu-id="73fcd-124">bit</span></span></p></td>
<td><p><span data-ttu-id="73fcd-125">Primary</span><span class="sxs-lookup"><span data-stu-id="73fcd-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="73fcd-126">0: 수신자 데이터</span><span class="sxs-lookup"><span data-stu-id="73fcd-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="73fcd-127">1: 발신자 데이터</span><span class="sxs-lookup"><span data-stu-id="73fcd-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73fcd-128"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-128"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-129">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73fcd-129">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73fcd-130">세션 비율 NetworkSendQuality 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-130">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="73fcd-131">지터 또는 패킷 손실 측면의 네트워크 품질이 심각 하 고 전송 중인 오디오 품질에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-131">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73fcd-132"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-132"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-133">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73fcd-133">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73fcd-134">세션 백분율 상태로 receivesendquality 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-134">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="73fcd-135">지터 또는 패킷 손실 측면의 네트워크 품질이 심각 하 고 수신 중인 오디오 품질에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-135">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73fcd-136"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-136"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-137">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73fcd-137">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73fcd-138">세션 비율 지연 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-138">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="73fcd-139">네트워크 대기 시간이 심각 하며 대화형 통신을 방지 하 여 환경에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-139">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73fcd-140"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-140"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-141">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73fcd-141">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73fcd-142">세션 완료율 \ 대역폭 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-142">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="73fcd-143">사용 가능한 대역폭이 충분 하지 않은 음성 환경에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-143">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73fcd-144"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-144"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-145">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73fcd-145">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73fcd-146">세션 비율 ' 불량 ' 상태에 대해 CPU 부족 이벤트가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-146">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="73fcd-147">현재 사용 중인 형식 및 응용 프로그램을 처리 하는 데 필요한 CPU 사이클이 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-147">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="73fcd-148">이렇게 하면 오디오 채널에서 왜곡이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-148">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73fcd-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-149"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-150">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73fcd-150">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73fcd-151">세션 백분율 DeviceHalfDuplexAEC 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-151">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="73fcd-152">에코를 방지 하기 위해 시스템에서 반이중을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-152">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73fcd-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-153"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-154">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73fcd-154">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73fcd-155">세션 백분율 DeviceRenderNotFunctioning 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-155">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="73fcd-156">세션에 현재 사용 중인 렌더링 장치가 제대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-156">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="73fcd-157">이로 인해 단방향 오디오 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-157">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73fcd-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-158"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-159">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73fcd-159">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73fcd-160">세션 백분율 DeviceCaptureNotFunctioning 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-160">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="73fcd-161">세션에 현재 사용 중인 캡처 장치가 제대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-161">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="73fcd-162">이로 인해 단방향 오디오 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-162">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73fcd-163"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-163"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-164">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73fcd-164">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73fcd-165">세션 비율 DeviceGlitches 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-165">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="73fcd-166">오디오 렌더링 시 왜곡이 발생 하는 심각한 결함이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-166">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="73fcd-167">이러한 오류는 드라이버 문제, DPC (지연 된 프로시저 호출) 폭풍 (드라이버) 및 높은 CPU 사용량이 원인일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-167">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73fcd-168"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-168"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-169">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73fcd-169">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73fcd-170">세션 비율 DeviceLowSNR 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-170">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="73fcd-171">캡처 품질이 매우 나쁨, 매우 소음이 발생 하거나 사용자가 마이크를 너무 멀리 떨어진 곳에 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-171">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="73fcd-172">이렇게 하면 왜곡이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-172">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73fcd-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-173"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-174">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73fcd-174">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73fcd-175">세션 백분율 DeviceLowSpeechLevel 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-175">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="73fcd-176">사용자의 음성 수준이 너무 낮아 시스템에서 더 이상 늘릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-176">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="73fcd-177">이로 인해 왜곡이 발생 하거나 단방향 오디오로 인식 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-177">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73fcd-178"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-178"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-179">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73fcd-179">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73fcd-180">세션 백분율 상태로 deviceclipping 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-180">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="73fcd-181">근접 종료 음성이 마이크를 클립 하면 클리핑이 진행 되는 동안 끝점을 듣게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-181">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="73fcd-182">가까운 마이크 클리핑을 방지 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-182">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73fcd-183"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-183"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-184">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73fcd-184">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73fcd-185">세션 백분율 DeviceEchoEvent 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-185">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="73fcd-186">장치 또는 설정으로 인해 시스템에서 보정 하는 기능이 더 이상 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-186">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73fcd-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-187"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-188">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73fcd-188">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73fcd-189">세션 백분율 DeviceNearEndToEchoRatio 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-189">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="73fcd-190">사용자의 음성이 사용자에 게 방해가 되는 것을 제한 하므로 캡처 중인 에코에 비해 너무 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-190">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="73fcd-191">스피커 볼륨을 줄이고 마이크를 talker 가까이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-191">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73fcd-192"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-192"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-193">int</span><span class="sxs-lookup"><span data-stu-id="73fcd-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73fcd-194">세션 중 DeviceMultipleEndpoints 이벤트가 ' 잘못 됨 ' 상태에 대해 발생 한 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-194">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="73fcd-195">동일한 세션의 여러 오디오 끝점이 검색 되 고 시스템에서 렌더링 볼륨을 줄여 보정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-195">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73fcd-196"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-196"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-197">int</span><span class="sxs-lookup"><span data-stu-id="73fcd-197">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73fcd-198">세션 중 DeviceHowlingEvent 이벤트가 ' 잘못 됨 ' 상태에 대해 발생 한 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-198">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="73fcd-199">오디오 피드백 루프가 검색 되었습니다 (오디오 경로를 여러 번 공유 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="73fcd-199">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73fcd-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-200"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-201">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73fcd-201">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73fcd-202">세션 백분율 DeviceRenderZeroVolume 이벤트가 "잘못 됨 ' 상태에 있을 때 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-202">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="73fcd-203">렌더링 장치가 제로 볼륨으로 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-203">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="73fcd-204">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-204">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73fcd-205"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73fcd-205"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73fcd-206">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73fcd-206">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73fcd-207">세션 백분율 DeviceRenderMute 이벤트가 "잘못 됨 ' 상태에 있을 때 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-207">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="73fcd-208">렌더링 장치가 음소거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-208">The render device was muted.</span></span></p>
<p><span data-ttu-id="73fcd-209">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73fcd-209">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

