---
title: 'Lync Server 2013: 오디오 신호 테이블'
description: 'Lync Server 2013: 오디오 신호 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82f3b3119eaccfe56c4706cff07469bc3434461f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568764"
---
# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="e8cd7-103">Lync Server 2013의 오디오 신호 테이블</span><span class="sxs-lookup"><span data-stu-id="e8cd7-103">AudioSignal table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8cd7-104">_**마지막으로 수정 된 항목:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="e8cd7-104">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="e8cd7-105">각 레코드는 하나의 끝점에 대 한 오디오 신호 메트릭을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-105">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="e8cd7-106">일반적으로 각 통화에는 두 개의 레코드가 있고, 하나는 발신자에 대 한 것이 고 하나는 수신자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-106">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8cd7-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e8cd7-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e8cd7-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e8cd7-110"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8cd7-111"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e8cd7-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e8cd7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e8cd7-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="e8cd7-114"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cd7-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-116">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-116">int</span></span></p></td>
<td><p><span data-ttu-id="e8cd7-117">Primary</span><span class="sxs-lookup"><span data-stu-id="e8cd7-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="e8cd7-118"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cd7-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="e8cd7-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e8cd7-121">Primary</span><span class="sxs-lookup"><span data-stu-id="e8cd7-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="e8cd7-122"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cd7-123"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-123"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-124">비트만</span><span class="sxs-lookup"><span data-stu-id="e8cd7-124">bit</span></span></p></td>
<td><p><span data-ttu-id="e8cd7-125">Primary</span><span class="sxs-lookup"><span data-stu-id="e8cd7-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="e8cd7-126">0: 수신자 데이터</span><span class="sxs-lookup"><span data-stu-id="e8cd7-126">0: Callee’s data</span></span></p>
<p><span data-ttu-id="e8cd7-127">1: 발신자 데이터</span><span class="sxs-lookup"><span data-stu-id="e8cd7-127">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cd7-128"><strong>Sendsignallevel 참조</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-128"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-129">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-129">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-130">아날로그 후 게인 제어 오디오 신호 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-130">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="e8cd7-131">이 메트릭의 단위는 dBmo입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-131">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e8cd7-132">적정 품질을 위해서는 최소 30 dBmo여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-132">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="e8cd7-133">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-133">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cd7-134"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-134"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-135">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-136">Sendsignallevel 참조를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-136">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cd7-137"><strong>Sendnoiselevel 참조</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-137"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-138">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-139">아날로그 향상 후 음성 노이즈 레벨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-139">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="e8cd7-140">이 메트릭의 단위는 dBmo입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-140">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e8cd7-141">적정 품질을 위해서는 35 dBmo 미만이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-141">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="e8cd7-142">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-142">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cd7-143"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-143"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-144">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-144">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-145">Sendnoiselevel 참조를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-145">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cd7-146"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-146"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-147">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-147">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-148">반향 반환 손실 보정 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-148">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="e8cd7-149">이 메트릭의 단위는 dB입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-149">The unit for this metric is dB.</span></span> <span data-ttu-id="e8cd7-150">값이 낮으면 에코가 적습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-150">Lower values represent less echo.</span></span> <span data-ttu-id="e8cd7-151">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-151">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cd7-152"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-152"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-153">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-154">확성기 렌더링에 대 한 5 분 당 평균 결함입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-154">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="e8cd7-155">적정 품질을 위해서는 5분당 1 미만이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-155">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="e8cd7-156">A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-156">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cd7-157"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-157"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-158">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-158">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-159">마이크 캡처에 대 한 5 분 당 평균 결함입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-159">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="e8cd7-160">적정 품질을 위해서는 5분당 1 미만이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-160">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="e8cd7-161">A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-161">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cd7-162"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-162"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-163">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="e8cd7-163">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-164">CPU 클럭에 비례하여 마이크 장치 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-164">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cd7-165"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-165"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-166">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="e8cd7-166">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-167">CPU 클럭에 비례하여 스피커 장치 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-167">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cd7-168"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-168"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-169">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="e8cd7-169">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-170">CPU 클럭에 비례하여 스피커 장치 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-170">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="e8cd7-171">통화의 최근 20초 동안 발생한 평균 마이크 캡처 스트림 타임스탬프 오류(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-171">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cd7-172"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-172"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-173">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="e8cd7-173">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-174">통화의 최근 20 초 동안 발생 한 평균 스피커 렌더링 스트림 타임 스탬프 오류 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-174">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cd7-175"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-175"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-176">smallint</span><span class="sxs-lookup"><span data-stu-id="e8cd7-176">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-177">음성 스위치는 중단 기능이 감소된 반이중 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-177">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="e8cd7-178">음성 스위치 항목의 원인:</span><span class="sxs-lookup"><span data-stu-id="e8cd7-178">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="e8cd7-179">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="e8cd7-179">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="e8cd7-180">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="e8cd7-180">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="e8cd7-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="e8cd7-181">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="e8cd7-182">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="e8cd7-182">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="e8cd7-183">원인은 이러한 개별 원인의 조합이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-183">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="e8cd7-184">ENTER_VS_FORCEORCONVERGENCE은 test 목적의 regkey 에서만 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-184">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="e8cd7-185">Microsoft Lync Server 2013에서이 열에 대 한 데이터 형식이 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-185">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cd7-186"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-186"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="e8cd7-187">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-188">에코 이벤트의 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-188">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="e8cd7-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="e8cd7-189">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="e8cd7-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="e8cd7-190">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="e8cd7-191">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="e8cd7-191">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="e8cd7-192">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="e8cd7-192">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="e8cd7-193">0x10 ECHO_EVENT_MIC_CLIPPING</span><span class="sxs-lookup"><span data-stu-id="e8cd7-193">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="e8cd7-194">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="e8cd7-194">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="e8cd7-195">원인은 이러한 개별 원인의 조합이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-195">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cd7-196"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-196"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-197">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e8cd7-197">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-198">마이크 캡처 스트림에서 화면 표시가 감지 되는 시간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-198">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="e8cd7-199">일반적으로 헤드셋 이나 송수화기에 대 한 값은 낮고, 스피커 전화 또는 독립 실행형 스피커의 경우에는 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-199">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="e8cd7-200">온보드 음향 반향 취소를 지 원하는 장치의 경우 높은 값은 에코 누수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-200">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="e8cd7-201">다른 장치의 경우에는이 메트릭을 사용 하 여 장치 품질을 평가 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-201">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cd7-202"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-202"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-203">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e8cd7-203">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8cd7-204">전송 된 스트림에서 에코를 감지 하는 시간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-204">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="e8cd7-205">전송 스트림에서 에코 비율이 높으면 에코 누출을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-205">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cd7-206"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-206"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-207">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-207">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-208">게이트웨이에서 중재 서버에 대 한 신호 수준을 받았습니다. 이는 중재 서버에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-208">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="e8cd7-209">이 메트릭의 단위는 dBoV입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-209">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e8cd7-210">좋은 품질을 위해 허용 되는 범위는 [-30 ~-18] dBoV 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-210">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cd7-211"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-211"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-212">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-212">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-213">게이트웨이에서 중재 서버에 대 한 신호 수준을 수신 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-213">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="e8cd7-214">중재 서버에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-214">This applies only to the Mediation Server.</span></span> <span data-ttu-id="e8cd7-215">이 메트릭의 단위는 dBoV입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-215">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e8cd7-216">적정 품질을 위해 허용되는 범위는 -50 dBoV 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-216">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cd7-217"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-217"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-218">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-218">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-219">중재 서버 쪽의 AGC (자동 게인 컨트롤)입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-219">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cd7-220"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-220"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-221">식</span><span class="sxs-lookup"><span data-stu-id="e8cd7-221">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e8cd7-222">통화의 처음 30 초 동안 들어오는 신호의 RMS (root mean 제곱)입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-222">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cd7-223"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-223"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-224">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-224">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8cd7-225">채널 1에서 수신 되는 신호 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-225">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="e8cd7-226">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cd7-227"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-227"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-228">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8cd7-229">채널 2에서 수신 되는 신호 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-229">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="e8cd7-230">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cd7-231"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-231"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-232">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8cd7-233">채널 1에서 수신 되는 노이즈 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-233">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="e8cd7-234">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cd7-235"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-235"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-236">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8cd7-237">채널 2에서 수신 되는 노이즈 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-237">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="e8cd7-238">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cd7-239"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-239"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-240">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8cd7-241">채널 1에서 송신 되는 신호 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-241">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="e8cd7-242">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cd7-243"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-243"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-244">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8cd7-245">채널 2에서 송신 되는 신호 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-245">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="e8cd7-246">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8cd7-247"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-247"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-248">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-248">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8cd7-249">채널 1에서 전송 되는 노이즈 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-249">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="e8cd7-250">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8cd7-251"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="e8cd7-251"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="e8cd7-252">int</span><span class="sxs-lookup"><span data-stu-id="e8cd7-252">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e8cd7-253">채널 2에서 송신 되는 노이즈 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-253">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="e8cd7-254">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cd7-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

