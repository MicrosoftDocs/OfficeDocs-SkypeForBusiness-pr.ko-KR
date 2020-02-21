---
title: 'Lync Server 2013: 오디오 (c) Clientevent 테이블'
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
ms.openlocfilehash: d93a9cd9276ba2bdaacf892ca0ab3f4240458503
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="c1ecc-102">Lync Server 2013의 오디오 Clientevent 테이블</span><span class="sxs-lookup"><span data-stu-id="c1ecc-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1ecc-103">_**마지막으로 수정 된 항목:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="c1ecc-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="c1ecc-104">각 레코드에는 오디오 통화의 한 끝점에 대 한 클라이언트 이벤트가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="c1ecc-105">일반적으로 한 통화에는 발신자 용 레코드와 수신자를 위한 레코드가 각각 하나씩 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c1ecc-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c1ecc-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c1ecc-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c1ecc-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c1ecc-110"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-111">datetime</span><span class="sxs-lookup"><span data-stu-id="c1ecc-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="c1ecc-112">Primary</span><span class="sxs-lookup"><span data-stu-id="c1ecc-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c1ecc-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1ecc-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-115">int</span><span class="sxs-lookup"><span data-stu-id="c1ecc-115">int</span></span></p></td>
<td><p><span data-ttu-id="c1ecc-116">Primary</span><span class="sxs-lookup"><span data-stu-id="c1ecc-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="c1ecc-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1ecc-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="c1ecc-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c1ecc-120">Primary</span><span class="sxs-lookup"><span data-stu-id="c1ecc-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="c1ecc-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1ecc-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-123">비트만</span><span class="sxs-lookup"><span data-stu-id="c1ecc-123">bit</span></span></p></td>
<td><p><span data-ttu-id="c1ecc-124">Primary</span><span class="sxs-lookup"><span data-stu-id="c1ecc-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="c1ecc-125">0: 수신자 데이터</span><span class="sxs-lookup"><span data-stu-id="c1ecc-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="c1ecc-126">1: 발신자 데이터</span><span class="sxs-lookup"><span data-stu-id="c1ecc-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1ecc-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-128">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c1ecc-129">세션 비율 NetworkSendQuality 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="c1ecc-130">지터 또는 패킷 손실 측면의 네트워크 품질이 심각 하 고 전송 중인 오디오 품질에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1ecc-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-132">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c1ecc-133">세션 백분율 상태로 receivesendquality 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="c1ecc-134">지터 또는 패킷 손실 측면의 네트워크 품질이 심각 하 고 수신 중인 오디오 품질에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1ecc-135"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-136">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c1ecc-137">세션 비율 지연 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c1ecc-138">네트워크 대기 시간이 심각 하며 대화형 통신을 방지 하 여 환경에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1ecc-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-140">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c1ecc-141">세션 완료율 \ 대역폭 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c1ecc-142">사용 가능한 대역폭이 충분 하지 않은 음성 환경에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1ecc-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-144">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c1ecc-145">세션 비율 ' 불량 ' 상태에 대해 CPU 부족 이벤트가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c1ecc-146">현재 사용 중인 형식 및 응용 프로그램을 처리 하는 데 필요한 CPU 사이클이 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="c1ecc-147">이렇게 하면 오디오 채널에서 왜곡이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1ecc-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-149">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c1ecc-150">세션 백분율 DeviceHalfDuplexAEC 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c1ecc-151">에코를 방지 하기 위해 시스템에서 반이중을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1ecc-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-153">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c1ecc-154">세션 백분율 DeviceRenderNotFunctioning 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c1ecc-155">세션에 현재 사용 중인 렌더링 장치가 제대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="c1ecc-156">이로 인해 단방향 오디오 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1ecc-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-158">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c1ecc-159">세션 백분율 DeviceCaptureNotFunctioning 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c1ecc-160">세션에 현재 사용 중인 캡처 장치가 제대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="c1ecc-161">이로 인해 단방향 오디오 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1ecc-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-163">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c1ecc-164">세션 비율 DeviceGlitches 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c1ecc-165">오디오 렌더링 시 왜곡이 발생 하는 심각한 결함이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="c1ecc-166">이러한 오류는 드라이버 문제, DPC (지연 된 프로시저 호출) 폭풍 (드라이버) 및 높은 CPU 사용량이 원인일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1ecc-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-168">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c1ecc-169">세션 비율 DeviceLowSNR 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c1ecc-170">캡처 품질이 매우 나쁨, 매우 소음이 발생 하거나 사용자가 마이크를 너무 멀리 떨어진 곳에 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="c1ecc-171">이렇게 하면 왜곡이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1ecc-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-173">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c1ecc-174">세션 백분율 DeviceLowSpeechLevel 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c1ecc-175">사용자의 음성 수준이 너무 낮아 시스템에서 더 이상 늘릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="c1ecc-176">이로 인해 왜곡이 발생 하거나 단방향 오디오로 인식 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1ecc-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-178">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c1ecc-179">세션 백분율 상태로 deviceclipping 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="c1ecc-180">근접 종료 음성이 마이크를 클립 하면 클리핑이 진행 되는 동안 끝점을 듣게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="c1ecc-181">가까운 마이크 클리핑을 방지 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1ecc-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-183">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c1ecc-184">세션 백분율 DeviceEchoEvent 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c1ecc-185">장치 또는 설정으로 인해 시스템에서 보정 하는 기능이 더 이상 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1ecc-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-187">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c1ecc-188">세션 백분율 DeviceNearEndToEchoRatio 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c1ecc-189">사용자의 음성이 사용자에 게 방해가 되는 것을 제한 하므로 캡처 중인 에코에 비해 너무 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="c1ecc-190">스피커 볼륨을 줄이고 마이크를 talker 가까이 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1ecc-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-192">int</span><span class="sxs-lookup"><span data-stu-id="c1ecc-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c1ecc-193">세션 중 DeviceMultipleEndpoints 이벤트가 ' 잘못 됨 ' 상태에 대해 발생 한 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c1ecc-194">동일한 세션의 여러 오디오 끝점이 검색 되 고 시스템에서 렌더링 볼륨을 줄여 보정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1ecc-195"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-196">int</span><span class="sxs-lookup"><span data-stu-id="c1ecc-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c1ecc-197">세션 중 DeviceHowlingEvent 이벤트가 ' 잘못 됨 ' 상태에 대해 발생 한 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="c1ecc-198">오디오 피드백 루프가 검색 되었습니다 (오디오 경로를 여러 번 공유 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="c1ecc-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1ecc-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-200">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c1ecc-201">세션 백분율 DeviceRenderZeroVolume 이벤트가 "잘못 됨 ' 상태에 있을 때 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="c1ecc-202">렌더링 장치가 제로 볼륨으로 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="c1ecc-203">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1ecc-204"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c1ecc-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c1ecc-205">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="c1ecc-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c1ecc-206">세션 백분율 DeviceRenderMute 이벤트가 "잘못 됨 ' 상태에 있을 때 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="c1ecc-207">렌더링 장치가 음소거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="c1ecc-208">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c1ecc-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

