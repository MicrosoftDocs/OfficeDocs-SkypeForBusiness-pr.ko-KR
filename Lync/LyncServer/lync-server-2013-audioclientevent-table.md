---
title: 'Lync Server 2013: AudioClientEvent 테이블'
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
ms.openlocfilehash: 44d5146b334af83618ca2dd6261a18e72708f4f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a><span data-ttu-id="27be4-102">Lync Server 2013의 AudioClientEvent 테이블</span><span class="sxs-lookup"><span data-stu-id="27be4-102">AudioClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27be4-103">_**마지막으로 수정한 주제:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="27be4-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="27be4-104">각 레코드에는 오디오 통화의 한 끝점에 대 한 클라이언트 이벤트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-104">Each record contains a client event for one endpoint in an audio call.</span></span> <span data-ttu-id="27be4-105">일반적으로 한 통화에는 두 개의 레코드 (호출자 용 1 개와 피호출자 용)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27be4-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="27be4-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="27be4-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="27be4-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27be4-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="27be4-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="27be4-112">주요한</span><span class="sxs-lookup"><span data-stu-id="27be4-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="27be4-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27be4-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-115">int</span><span class="sxs-lookup"><span data-stu-id="27be4-115">int</span></span></p></td>
<td><p><span data-ttu-id="27be4-116">주요한</span><span class="sxs-lookup"><span data-stu-id="27be4-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="27be4-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27be4-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="27be4-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="27be4-120">주요한</span><span class="sxs-lookup"><span data-stu-id="27be4-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="27be4-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27be4-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-123">다소</span><span class="sxs-lookup"><span data-stu-id="27be4-123">bit</span></span></p></td>
<td><p><span data-ttu-id="27be4-124">주요한</span><span class="sxs-lookup"><span data-stu-id="27be4-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="27be4-125">0: 피호출자의 데이터</span><span class="sxs-lookup"><span data-stu-id="27be4-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="27be4-126">1: 발신자의 데이터</span><span class="sxs-lookup"><span data-stu-id="27be4-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27be4-127"><strong>NetworkSendQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-127"><strong>NetworkSendQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-128">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="27be4-128">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27be4-129">세션 백분율 NetworkSendQuality 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-129">Percentage of session the NetworkSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="27be4-130">지터 또는 패킷 손실로 인 한 네트워크 품질은 심각 하 고 전송 되는 오디오 품질에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-130">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27be4-131"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-131"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-132">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="27be4-132">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27be4-133">세션 백분율 ReceiveSendQuality 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-133">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="27be4-134">지터 또는 패킷 손실 측면의 네트워크 품질은 심각 하며 수신 되는 오디오 품질에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-134">Network quality in terms of jitter or packet loss is severe and impacting the quality of audio being received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27be4-135"><strong>NetworkDelayEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-135"><strong>NetworkDelayEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-136">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="27be4-136">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27be4-137">세션 백분율 지연 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-137">Percentage of session the Delay event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="27be4-138">네트워크 대기 시간이 심각 하 고 대화형 통신을 방지 하 여 환경에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-138">Network latency is severe and impacting the experience by preventing interactive communication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27be4-139"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-139"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-140">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="27be4-140">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27be4-141">세션 백분율 \ \ \ \에 대 한 \ \ \ n 대역폭 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-141">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="27be4-142">사용할 수 있는 대역폭이 불충분 한 음성 환경에 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-142">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27be4-143"><strong>CPUInsufficientEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-143"><strong>CPUInsufficientEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-144">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="27be4-144">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27be4-145">세션 백분율 CPU 이벤트 부족이 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-145">Percentage of session the insufficient CPU event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="27be4-146">현재 사용 중인 형식을 및 응용 프로그램을 처리 하는 데 필요한 CPU 사이클이 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-146">There are insufficient CPU cycles for processing with the current modalities and applications in use.</span></span> <span data-ttu-id="27be4-147">오디오 채널에 왜곡이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-147">This causes distortions with the audio channel.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27be4-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-148"><strong>DeviceHalfDuplexAECEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-149">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="27be4-149">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27be4-150">세션 백분율 DeviceHalfDuplexAEC 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-150">Percentage of session the DeviceHalfDuplexAEC event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="27be4-151">화면을 방지 하기 위해 시스템에서 반이중을 입력 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-151">In order to prevent echo, the system has enter half duplex.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27be4-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-152"><strong>DeviceRenderNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-153">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="27be4-153">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27be4-154">세션 백분율 DeviceRenderNotFunctioning 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-154">Percentage of session the DeviceRenderNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="27be4-155">현재 세션에 사용 중인 렌더 장치가 제대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-155">The render device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="27be4-156">이로 인해 단방향 오디오 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-156">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27be4-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-157"><strong>DeviceCaptureNotFunctioningEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-158">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="27be4-158">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27be4-159">세션 백분율 DeviceCaptureNotFunctioning 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-159">Percentage of session the DeviceCaptureNotFunctioning event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="27be4-160">세션에 현재 사용 중인 캡처 장치가 제대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-160">The capture device currently being used for the session is not functioning correctly.</span></span> <span data-ttu-id="27be4-161">이로 인해 단방향 오디오 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-161">This can cause one-way audio issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27be4-162"><strong>DeviceGlitchesEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-162"><strong>DeviceGlitchesEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-163">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="27be4-163">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27be4-164">세션 백분율 DeviceGlitches 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-164">Percentage of session the DeviceGlitches event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="27be4-165">왜곡을 초래 하는 오디오 렌더링에는 심각한 결함이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-165">There are severe glitches in the rendering of audio which is causing distortions.</span></span> <span data-ttu-id="27be4-166">이러한 결함은 드라이버 문제, DPC (지연 된 프로시저 호출) 스톰 (드라이버) 및 높은 CPU 사용으로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-166">These glitches can be caused by driver issues, deferred procedure calls (DPC) storm (drivers), and high CPU usage.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27be4-167"><strong>DeviceLowSNREventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-167"><strong>DeviceLowSNREventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-168">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="27be4-168">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27be4-169">세션 백분율 DeviceLowSNR 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-169">Percentage of session the DeviceLowSNR event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="27be4-170">캡처 품질이 매우 나쁨, 매우 소음이 있거나 사용자가 마이크에서 멀리 떨어져 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-170">The capture quality is very poor, either very noisy or user is talking too far away from the microphone.</span></span> <span data-ttu-id="27be4-171">이렇게 하면 왜곡이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-171">This will cause distortions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27be4-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-172"><strong>DeviceLowSpeechLevelEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-173">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="27be4-173">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27be4-174">세션 백분율 DeviceLowSpeechLevel 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-174">Percentage of session the DeviceLowSpeechLevel event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="27be4-175">사용자의 음성 수준이 너무 낮기 때문에 시스템에서 더 이상 증가 시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-175">User‘s speech level is too low and the system cannot increase it any further.</span></span> <span data-ttu-id="27be4-176">이는 왜곡을 발생 시키거나 단방향 오디오로 인식 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-176">This can either cause distortions or perceived as one-way audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27be4-177"><strong>DeviceClippingEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-177"><strong>DeviceClippingEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-178">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="27be4-178">Decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27be4-179">세션 백분율 DeviceClipping 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-179">Percentage of session the DeviceClipping event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="27be4-180">가까운 끝에 있는 음성이 마이크를 클리핑하여 클리핑으로 인 한 far의 왜곡을 듣습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-180">When near-end speech clips the microphone, far-end hears distortion due to clipping.</span></span> <span data-ttu-id="27be4-181">가까운 마이크 클리핑을 피하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-181">It is important to avoid near-end microphone clipping.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27be4-182"><strong>DeviceEchoEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-182"><strong>DeviceEchoEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-183">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="27be4-183">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27be4-184">세션 백분율 DeviceEchoEvent 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-184">Percentage of session the DeviceEchoEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="27be4-185">장치 또는 설정으로 시스템에서 보정 하는 기능을 벗어나는 화면을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-185">Device or setup is causing echo beyond the ability of the system to compensate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27be4-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-186"><strong>DeviceNearEndToEchoRatioEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-187">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="27be4-187">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27be4-188">세션 백분율 DeviceNearEndToEchoRatio 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-188">Percentage of session the DeviceNearEndToEchoRatio event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="27be4-189">사용자의 음성이 사용자에 게 영향을 줄 수 있는 것이 제한 되어 있으므로 캡처 중인 에코에 비해 너무 낮게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-189">The user’s speech is too low compared to the echo being captured which impacts the users experience because it limits how easy it is to interrupt a user.</span></span> <span data-ttu-id="27be4-190">스피커 볼륨을 낮추고 마이크를 발표자 가까이 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-190">Reduce speaker volume, move the microphone closer to the talker.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27be4-191"><strong>DeviceMultipleEndpointsEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-191"><strong>DeviceMultipleEndpointsEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-192">int</span><span class="sxs-lookup"><span data-stu-id="27be4-192">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27be4-193">세션 중 ' 잘못 된 ' 상태에 대해 DeviceMultipleEndpoints 이벤트가 발생 한 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-193">Number of times during session the DeviceMultipleEndpoints event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="27be4-194">동일한 세션의 여러 오디오 끝점을 감지 했 고 렌더링 볼륨을 줄임으로써 시스템을 보정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-194">Multiple audio endpoints in the same session detected and the system has compensated by reducing render volume.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27be4-195"><strong>DeviceHowlingEventCount</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-195"><strong>DeviceHowlingEventCount</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-196">int</span><span class="sxs-lookup"><span data-stu-id="27be4-196">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="27be4-197">세션 중 ' 잘못 된 ' 상태에 대해 DeviceHowlingEvent 이벤트가 발생 한 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-197">Number of times during session the DeviceHowlingEvent event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="27be4-198">오디오 피드백 루프가 여러 끝점 공유 오디오 경로에 의해 감지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-198">Audio feedback loop detected (caused by multiple endpoints sharing audio path).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27be4-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-199"><strong>DeviceRenderZeroVolumeEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-200">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="27be4-200">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27be4-201">세션 백분율 DeviceRenderZeroVolume 이벤트가 "잘못 된 ' 상태에 있을 때 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-201">Percentage of session the DeviceRenderZeroVolume event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="27be4-202">렌더 장치가 0 볼륨으로 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-202">The render device was set to zero volume.</span></span></p>
<p><span data-ttu-id="27be4-203">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-203">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27be4-204"><strong>DeviceRenderMuteEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="27be4-204"><strong>DeviceRenderMuteEventRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="27be4-205">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="27be4-205">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="27be4-206">세션 백분율 DeviceRenderMute 이벤트가 "잘못 된 ' 상태에 있을 때 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-206">Percentage of session the DeviceRenderMute event was fired for being in the “Bad’ state.</span></span> <span data-ttu-id="27be4-207">렌더 장치가 음소거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-207">The render device was muted.</span></span></p>
<p><span data-ttu-id="27be4-208">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="27be4-208">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

