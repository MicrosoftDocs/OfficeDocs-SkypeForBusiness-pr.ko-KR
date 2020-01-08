---
title: 'Lync Server 2013: AudioSignal 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6605a25191906660bbad11908f754a81360c893
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a><span data-ttu-id="a00ba-102">Lync Server 2013의 AudioSignal 테이블</span><span class="sxs-lookup"><span data-stu-id="a00ba-102">AudioSignal table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a00ba-103">_**마지막으로 수정한 주제:** 2013-11-12_</span><span class="sxs-lookup"><span data-stu-id="a00ba-103">_**Topic Last Modified:** 2013-11-12_</span></span>

<span data-ttu-id="a00ba-104">각 레코드는 한 끝점에 대 한 오디오 신호 메트릭을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-104">Each record represents audio signal metrics for one endpoint.</span></span> <span data-ttu-id="a00ba-105">일반적으로 각 통화에는 두 개의 레코드가 있으며, 하나는 호출자를 위한 것이 고 하나는 피호출자 용입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-105">Usually, each call has two records, one is for caller, and one is for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a00ba-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a00ba-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a00ba-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a00ba-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a00ba-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="a00ba-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a00ba-112">주요한</span><span class="sxs-lookup"><span data-stu-id="a00ba-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a00ba-113"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00ba-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-115">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-115">int</span></span></p></td>
<td><p><span data-ttu-id="a00ba-116">주요한</span><span class="sxs-lookup"><span data-stu-id="a00ba-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="a00ba-117"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00ba-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="a00ba-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a00ba-120">주요한</span><span class="sxs-lookup"><span data-stu-id="a00ba-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="a00ba-121"><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00ba-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-123">다소</span><span class="sxs-lookup"><span data-stu-id="a00ba-123">bit</span></span></p></td>
<td><p><span data-ttu-id="a00ba-124">주요한</span><span class="sxs-lookup"><span data-stu-id="a00ba-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="a00ba-125">0: 피호출자의 데이터</span><span class="sxs-lookup"><span data-stu-id="a00ba-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="a00ba-126">1: 발신자의 데이터</span><span class="sxs-lookup"><span data-stu-id="a00ba-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00ba-127"><strong>SendSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-127"><strong>SendSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-128">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-129">아날로그 후 게인 제어 오디오 신호 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-129">Represents the Post-Analog Gain Control audio signal level.</span></span> <span data-ttu-id="a00ba-130">이 메트릭의 단위는 dBmo입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-130">The unit for this metric is dBmo.</span></span> <span data-ttu-id="a00ba-131">적절 한 품질을 위해서는 30 dBmo 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-131">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="a00ba-132">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-132">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00ba-133"><strong>RecvSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-133"><strong>RecvSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-134">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-134">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-135">SendSignalLevel을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a00ba-135">See SendSignalLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00ba-136"><strong>SendNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-136"><strong>SendNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-137">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-137">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-138">아날로그 후 게인 제어 오디오 노이즈 수준을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-138">Represents the Post-Analog Gain Control audio noise level.</span></span> <span data-ttu-id="a00ba-139">이 메트릭의 단위는 dBmo입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-139">The unit for this metric is dBmo.</span></span> <span data-ttu-id="a00ba-140">적절 한 품질을 위해서는 35 dBmo 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-140">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="a00ba-141">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-141">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00ba-142"><strong>RecvNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-142"><strong>RecvNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-143">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-144">SendNoiseLevel을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a00ba-144">See SendNoiseLevel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00ba-145"><strong>EchoReturn</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-145"><strong>EchoReturn</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-146">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-147">반향 반환 손실 보정 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-147">Echo Return Loss Enhancement metric.</span></span> <span data-ttu-id="a00ba-148">이 메트릭의 단위는 dB입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-148">The unit for this metric is dB.</span></span> <span data-ttu-id="a00ba-149">값이 낮을수록 화면 표시 수준이 낮아집니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-149">Lower values represent less echo.</span></span> <span data-ttu-id="a00ba-150">이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-150">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00ba-151"><strong>AudioSpeakerGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-151"><strong>AudioSpeakerGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-152">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-152">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-153">스피커 렌더링에 대 한 5 분 당 평균 결함입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-153">Average glitches per five minutes for the loudspeaker rendering.</span></span> <span data-ttu-id="a00ba-154">좋은 품질을 위해서는 5 분에 1 보다 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-154">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="a00ba-155">A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-155">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00ba-156"><strong>AudioMicGlitchRate</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-156"><strong>AudioMicGlitchRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-157">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-157">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-158">마이크 캡처에 대 한 5 분 당 평균 결함.</span><span class="sxs-lookup"><span data-stu-id="a00ba-158">Average glitches per five minutes for the microphone capture.</span></span> <span data-ttu-id="a00ba-159">좋은 품질을 위해서는 5 분에 1을 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-159">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="a00ba-160">A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-160">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00ba-161"><strong>AudioTimestampDriftRateMic</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-161"><strong>AudioTimestampDriftRateMic</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-162">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="a00ba-162">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-163">CPU 클록을 기준으로 한 마이크 장치 시계 드리프트 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-163">Microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00ba-164"><strong>AudioTimestampDriftRateSpk</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-164"><strong>AudioTimestampDriftRateSpk</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-165">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="a00ba-165">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-166">CPU 클록을 기준으로 스피커 장치 시계 드리프트 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-166">Speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00ba-167"><strong>AudioTimestampErrorMicMs</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-167"><strong>AudioTimestampErrorMicMs</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-168">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="a00ba-168">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-169">CPU 클록을 기준으로 스피커 장치 시계 드리프트 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-169">Speaker device clock drift rate, relative to CPU clock.</span></span></p>
<p><span data-ttu-id="a00ba-170">평균 마이크 캡처 스트림 타임 스탬프 (밀리초) (통화의 마지막 20 초)</span><span class="sxs-lookup"><span data-stu-id="a00ba-170">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00ba-171"><strong>AudioTimestampErrorSpkMs</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-171"><strong>AudioTimestampErrorSpkMs</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-172">10 진수 (9, 2)</span><span class="sxs-lookup"><span data-stu-id="a00ba-172">decimal(9,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-173">평균 스피커는 호출의 마지막 20 초 동안 스트림 타임 스탬프 오류를 밀리초 단위로 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-173">Average speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00ba-174"><strong>VsEntryCauses</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-174"><strong>VsEntryCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-175">smallint</span><span class="sxs-lookup"><span data-stu-id="a00ba-175">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-176">음성 스위치는 인터럽트 감소 기능이 있는 반 양방향 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-176">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="a00ba-177">음성 전환 항목의 원인:</span><span class="sxs-lookup"><span data-stu-id="a00ba-177">Causes of voice switch entry:</span></span></p>
<p><span data-ttu-id="a00ba-178">ENTER_VS_BADTS 0x01</span><span class="sxs-lookup"><span data-stu-id="a00ba-178">ENTER_VS_BADTS 0x01</span></span></p>
<p><span data-ttu-id="a00ba-179">0x02 ENTER_VS_ECHO</span><span class="sxs-lookup"><span data-stu-id="a00ba-179">ENTER_VS_ECHO 0x02</span></span></p>
<p><span data-ttu-id="a00ba-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span><span class="sxs-lookup"><span data-stu-id="a00ba-180">ENTER_VS_FORCEORCONVERGENCE 0x04</span></span></p>
<p><span data-ttu-id="a00ba-181">ENTER_VS_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="a00ba-181">ENTER_VS_DNLP 0x08</span></span></p>
<p><span data-ttu-id="a00ba-182">원인은 이러한 개별적인 원인을 조합 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-182">The cause can be a combination of those individual causes.</span></span> <span data-ttu-id="a00ba-183">ENTER_VS_FORCEORCONVERGENCE는 테스트 용도의 regkey 에서만 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-183">ENTER_VS_FORCEORCONVERGENCE can only be enabled by regkey for test purpose.</span></span></p>
<p><span data-ttu-id="a00ba-184">Microsoft Lync Server 2013에서이 열의 데이터 형식이 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-184">The data type for this column was changed in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00ba-185"><strong>EchoEventCauses</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-185"><strong>EchoEventCauses</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-186">tinyint</span><span class="sxs-lookup"><span data-stu-id="a00ba-186">tinyint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-187">에코 이벤트의 원인:</span><span class="sxs-lookup"><span data-stu-id="a00ba-187">Causes of an echo event:</span></span></p>
<p><span data-ttu-id="a00ba-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span><span class="sxs-lookup"><span data-stu-id="a00ba-188">ECHO_EVENT_BAD_TIMESTAMP 0x01</span></span></p>
<p><span data-ttu-id="a00ba-189">0x02 ECHO_EVENT_POSTAEC_ECHO</span><span class="sxs-lookup"><span data-stu-id="a00ba-189">ECHO_EVENT_POSTAEC_ECHO 0x02</span></span></p>
<p><span data-ttu-id="a00ba-190">ECHO_EVENT_ANLP 0x04</span><span class="sxs-lookup"><span data-stu-id="a00ba-190">ECHO_EVENT_ANLP 0x04</span></span></p>
<p><span data-ttu-id="a00ba-191">ECHO_EVENT_DNLP 0x08</span><span class="sxs-lookup"><span data-stu-id="a00ba-191">ECHO_EVENT_DNLP 0x08</span></span></p>
<p><span data-ttu-id="a00ba-192">ECHO_EVENT_MIC_CLIPPING 0x10</span><span class="sxs-lookup"><span data-stu-id="a00ba-192">ECHO_EVENT_MIC_CLIPPING 0x10</span></span></p>
<p><span data-ttu-id="a00ba-193">ECHO_EVENT_BAD_STATE 0x20</span><span class="sxs-lookup"><span data-stu-id="a00ba-193">ECHO_EVENT_BAD_STATE 0x20</span></span></p>
<p><span data-ttu-id="a00ba-194">원인은 이러한 개별적인 원인을 조합 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-194">The cause can be a combination of those individual causes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00ba-195"><strong>EchoPercentMicIn</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-195"><strong>EchoPercentMicIn</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-196">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a00ba-196">decimal(5,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-197">마이크 캡처 스트림에 화면 표시가 감지 된 시간의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-197">Percentage of time when echo was detected in the microphone capture stream.</span></span> <span data-ttu-id="a00ba-198">일반적으로 헤드셋 이나 송수화기의 경우 값은 낮고 스피커 전화 또는 독립 실행형 스피커는 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-198">Typically, values are low for headsets or handsets, and higher for speaker phones or stand-alone speakers.</span></span> <span data-ttu-id="a00ba-199">화상 음향 반향 제거를 지 원하는 디바이스의 경우 높은 값은 에코 누수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-199">For devices that support on-board acoustic echo cancellation, high values indicate echo leak.</span></span> <span data-ttu-id="a00ba-200">다른 디바이스의 경우이 메트릭은 장치 품질을 평가 하는 데 사용해 서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-200">For other devices, this metric should not be used to evaluate device quality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00ba-201"><strong>EchoPercentSend</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-201"><strong>EchoPercentSend</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-202">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="a00ba-202">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a00ba-203">전송 된 스트림에서 반향을 감지 하는 시간 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-203">Percentage of time when echo is detected in sent stream.</span></span> <span data-ttu-id="a00ba-204">송신 스트림의 화면 표시 백분율 에코 누수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-204">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00ba-205"><strong>RxAGCSignalLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-205"><strong>RxAGCSignalLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-206">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-206">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-207">게이트웨이에서 중재 서버의 신호 수준을 수신 했습니다. 이는 중재 서버에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-207">Received signal level on the Mediation Server from the Gateway; this applies only to the Mediation Server.</span></span> <span data-ttu-id="a00ba-208">이 메트릭의 단위는 dBoV입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-208">The unit of this metric is dBoV.</span></span> <span data-ttu-id="a00ba-209">좋은 품질을 위해서는 허용 되는 범위는 [-30 ~-18] dBoV 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-209">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00ba-210"><strong>RxAGCNoiseLevel</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-210"><strong>RxAGCNoiseLevel</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-211">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-211">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-212">게이트웨이에서 중재 서버의 신호 수준을 수신 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-212">Received signal level on the Mediation Server from the Gateway.</span></span> <span data-ttu-id="a00ba-213">이는 중재 서버에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-213">This applies only to the Mediation Server.</span></span> <span data-ttu-id="a00ba-214">이 메트릭의 단위는 dBoV입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-214">The unit of this metric is dBoV.</span></span> <span data-ttu-id="a00ba-215">좋은 품질을 위해서는 허용 되는 범위가-50 dBoV 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-215">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00ba-216"><strong>RxAvgAGCGain</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-216"><strong>RxAvgAGCGain</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-217">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-217">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-218">중재 서버 쪽의 AGC (자동 게인 컨트롤)</span><span class="sxs-lookup"><span data-stu-id="a00ba-218">Automatic gain control (AGC) on the Mediation Server side.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00ba-219"><strong>InitialSignalLevelRMS</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-219"><strong>InitialSignalLevelRMS</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-220">o</span><span class="sxs-lookup"><span data-stu-id="a00ba-220">float</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a00ba-221">호출의 처음 30 초까지 들어오는 신호에 대 한 루트 평균 사각형 (RMS)입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-221">The root mean square (RMS) of the incoming signal of up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00ba-222"><strong>RecvSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-222"><strong>RecvSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-223">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-223">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a00ba-224">채널 1에서 받은 신호 수준</span><span class="sxs-lookup"><span data-stu-id="a00ba-224">Signal level as received on channel 1.</span></span></p>
<p><span data-ttu-id="a00ba-225">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00ba-226"><strong>RecvSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-226"><strong>RecvSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-227">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a00ba-228">채널 2에서 받은 신호 수준</span><span class="sxs-lookup"><span data-stu-id="a00ba-228">Signal level as received on channel 2.</span></span></p>
<p><span data-ttu-id="a00ba-229">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00ba-230"><strong>RecvNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-230"><strong>RecvNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-231">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a00ba-232">채널 1에서 받은 소음 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-232">Noise level as received on channel 1.</span></span></p>
<p><span data-ttu-id="a00ba-233">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00ba-234"><strong>RecvNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-234"><strong>RecvNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-235">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a00ba-236">채널 2에서 받은 소음 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-236">Noise level as received on channel 2.</span></span></p>
<p><span data-ttu-id="a00ba-237">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00ba-238"><strong>SendSignalLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-238"><strong>SendSignalLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-239">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a00ba-240">채널 1에서 전송 되는 신호 수준</span><span class="sxs-lookup"><span data-stu-id="a00ba-240">Signal level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="a00ba-241">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00ba-242"><strong>SendSignalLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-242"><strong>SendSignalLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-243">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-243">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a00ba-244">채널 2에서 전송 되는 신호 수준</span><span class="sxs-lookup"><span data-stu-id="a00ba-244">Signal level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="a00ba-245">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00ba-246"><strong>SendNoiseLevelCh1</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-246"><strong>SendNoiseLevelCh1</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-247">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-247">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a00ba-248">채널 1에서 전송 되는 소음 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-248">Noise level as sent on channel 1.</span></span></p>
<p><span data-ttu-id="a00ba-249">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-249">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00ba-250"><strong>SendNoiseLevelCh2</strong></span><span class="sxs-lookup"><span data-stu-id="a00ba-250"><strong>SendNoiseLevelCh2</strong></span></span></p></td>
<td><p><span data-ttu-id="a00ba-251">int</span><span class="sxs-lookup"><span data-stu-id="a00ba-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a00ba-252">채널 2에서 전송 된 소음 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-252">Noise level as sent on channel 2.</span></span></p>
<p><span data-ttu-id="a00ba-253">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a00ba-253">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

