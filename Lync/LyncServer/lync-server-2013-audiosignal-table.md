---
title: 'Lync Server 2013: 오디오 신호 테이블'
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
ms.openlocfilehash: 2d09842cb8b905798855cef7e015e4d9b32e72dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="8ab54-102">Lync Server 2013의 오디오 신호 테이블</span><span class="sxs-lookup"><span data-stu-id="8ab54-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ab54-103">_**마지막으로 수정 된 항목:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="8ab54-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="8ab54-104">각 레코드는 하나의 끝점에 대 한 오디오 신호 메트릭을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="8ab54-105">일반적으로 각 통화에는 두 개의 레코드가 있고, 하나는 발신자에 대 한 것이 고 하나는 수신자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ab54-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8ab54-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8ab54-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8ab54-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ab54-110"><strong>Conferencedatetime이 동일할</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-111">datetime</span><span class="sxs-lookup"><span data-stu-id="8ab54-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8ab54-112">Primary</span><span class="sxs-lookup"><span data-stu-id="8ab54-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="8ab54-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ab54-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-115">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-115">int</span></span></p></td>
<td><p><span data-ttu-id="8ab54-116">Primary</span><span class="sxs-lookup"><span data-stu-id="8ab54-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="8ab54-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ab54-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="8ab54-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="8ab54-120">Primary</span><span class="sxs-lookup"><span data-stu-id="8ab54-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="8ab54-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ab54-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-123">비트만</span><span class="sxs-lookup"><span data-stu-id="8ab54-123">bit</span></span></p></td>
<td><p><span data-ttu-id="8ab54-124">Primary</span><span class="sxs-lookup"><span data-stu-id="8ab54-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="8ab54-125">0: 수신자 데이터</span><span class="sxs-lookup"><span data-stu-id="8ab54-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="8ab54-126">1: 발신자 데이터</span><span class="sxs-lookup"><span data-stu-id="8ab54-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ab54-127"><strong>Sendsignallevel 참조</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-128">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-129">아날로그 후 게인 제어 오디오 신호 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="8ab54-130">이 메트릭의 단위는 dBmo입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="8ab54-131">적정 품질을 위해서는 최소 30 dBmo여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="8ab54-132">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ab54-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-134">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-135">Sendsignallevel 참조를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ab54-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ab54-136"><strong>Sendnoiselevel 참조</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-137">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-138">아날로그 향상 후 음성 노이즈 레벨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="8ab54-139">이 메트릭의 단위는 dBmo입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="8ab54-140">적정 품질을 위해서는 35 dBmo 미만이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="8ab54-141">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ab54-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-143">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-144">Sendnoiselevel 참조를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ab54-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ab54-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-146">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-147">반향 반환 손실 보정 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="8ab54-148">이 메트릭의 단위는 dB입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-148">The unit for this metric is dB.</span></span> <span data-ttu-id="8ab54-149">값이 낮으면 에코가 적습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-149">Lower values represent less echo.</span></span> <span data-ttu-id="8ab54-150">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ab54-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-152">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-153">확성기 렌더링에 대 한 5 분 당 평균 결함입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="8ab54-154">적정 품질을 위해서는 5분당 1 미만이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="8ab54-155">A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ab54-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-157">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-158">마이크 캡처에 대 한 5 분 당 평균 결함입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="8ab54-159">적정 품질을 위해서는 5분당 1 미만이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="8ab54-160">A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ab54-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-162">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8ab54-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-163">CPU 클럭에 비례하여 마이크 장치 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ab54-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-165">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8ab54-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-166">CPU 클럭에 비례하여 스피커 장치 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ab54-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-168">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8ab54-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-169">CPU 클럭에 비례하여 스피커 장치 클럭 드리프트 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="8ab54-170">통화의 최근 20초 동안 발생한 평균 마이크 캡처 스트림 타임스탬프 오류(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ab54-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-172">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="8ab54-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-173">통화의 최근 20 초 동안 발생 한 평균 스피커 렌더링 스트림 타임 스탬프 오류 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ab54-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-175">smallint</span><span class="sxs-lookup"><span data-stu-id="8ab54-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-176">음성 스위치는 중단 기능이 감소된 반이중 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="8ab54-177">음성 스위치 항목의 원인:</span><span class="sxs-lookup"><span data-stu-id="8ab54-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="8ab54-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="8ab54-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="8ab54-179">ENTER_VS_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="8ab54-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="8ab54-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="8ab54-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="8ab54-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="8ab54-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="8ab54-182">원인은 이러한 개별 원인의 조합이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="8ab54-183">ENTER_VS_FORCEORCONVERGENCE은 test 목적의 regkey 에서만 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="8ab54-184">Microsoft Lync Server 2013에서이 열에 대 한 데이터 형식이 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ab54-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="8ab54-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-187">에코 이벤트의 원인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="8ab54-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="8ab54-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="8ab54-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span><span class="sxs-lookup"><span data-stu-id="8ab54-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="8ab54-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="8ab54-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="8ab54-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="8ab54-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="8ab54-192">0x10 ECHO_EVENT_MIC_CLIPPING</span><span class="sxs-lookup"><span data-stu-id="8ab54-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="8ab54-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="8ab54-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="8ab54-194">원인은 이러한 개별 원인의 조합이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ab54-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-196">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8ab54-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-197">마이크 캡처 스트림에서 화면 표시가 감지 되는 시간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="8ab54-198">일반적으로 헤드셋 이나 송수화기에 대 한 값은 낮고, 스피커 전화 또는 독립 실행형 스피커의 경우에는 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="8ab54-199">온보드 음향 반향 취소를 지 원하는 장치의 경우 높은 값은 에코 누수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="8ab54-200">다른 장치의 경우에는이 메트릭을 사용 하 여 장치 품질을 평가 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ab54-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-202">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="8ab54-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ab54-203">전송 된 스트림에서 에코를 감지 하는 시간 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="8ab54-204">전송 스트림에서 에코 비율이 높으면 에코 누출을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ab54-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-206">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-207">게이트웨이에서 중재 서버에 대 한 신호 수준을 받았습니다. 이는 중재 서버에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="8ab54-208">이 메트릭의 단위는 dBoV입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="8ab54-209">좋은 품질을 위해 허용 되는 범위는 [-30 ~-18] dBoV 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ab54-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-211">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-212">게이트웨이에서 중재 서버에 대 한 신호 수준을 수신 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="8ab54-213">중재 서버에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="8ab54-214">이 메트릭의 단위는 dBoV입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="8ab54-215">적정 품질을 위해 허용되는 범위는 -50 dBoV 미만입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ab54-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-217">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-218">중재 서버 쪽의 AGC (자동 게인 컨트롤)입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ab54-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-220">식</span><span class="sxs-lookup"><span data-stu-id="8ab54-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8ab54-221">통화의 처음 30 초 동안 들어오는 신호의 RMS (root mean 제곱)입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ab54-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-223">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ab54-224">채널 1에서 수신 되는 신호 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="8ab54-225">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ab54-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-227">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ab54-228">채널 2에서 수신 되는 신호 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="8ab54-229">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ab54-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-231">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ab54-232">채널 1에서 수신 되는 노이즈 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="8ab54-233">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ab54-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-235">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ab54-236">채널 2에서 수신 되는 노이즈 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="8ab54-237">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ab54-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-239">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ab54-240">채널 1에서 송신 되는 신호 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="8ab54-241">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ab54-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-243">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ab54-244">채널 2에서 송신 되는 신호 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="8ab54-245">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ab54-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-247">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ab54-248">채널 1에서 전송 되는 노이즈 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="8ab54-249">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ab54-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="8ab54-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="8ab54-251">int</span><span class="sxs-lookup"><span data-stu-id="8ab54-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8ab54-252">채널 2에서 송신 되는 노이즈 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="8ab54-253">이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8ab54-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

