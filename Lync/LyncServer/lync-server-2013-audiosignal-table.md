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

# <a name="audiosignal-table-in-lync-server-2013"></a>Lync Server 2013의 AudioSignal 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-11-12_

각 레코드는 한 끝점에 대 한 오디오 신호 메트릭을 나타냅니다. 일반적으로 각 통화에는 두 개의 레코드가 있으며, 하나는 호출자를 위한 것이 고 하나는 피호출자 용입니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>열</strong></th>
<th><strong>데이터 형식</strong></th>
<th><strong>키/인덱스</strong></th>
<th><strong>세부적인</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>주요한</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>주요한</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>다소</p></td>
<td><p>주요한</p></td>
<td><p>0: 피호출자의 데이터</p>
<p>1: 발신자의 데이터</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>아날로그 후 게인 제어 오디오 신호 수준을 나타냅니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 30 dBmo 이상 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>SendSignalLevel을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>아날로그 후 게인 제어 오디오 노이즈 수준을 나타냅니다. 이 메트릭의 단위는 dBmo입니다. 적절 한 품질을 위해서는 35 dBmo 미만 이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>SendNoiseLevel을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>반향 반환 손실 보정 메트릭입니다. 이 메트릭의 단위는 dB입니다. 값이 낮을수록 화면 표시 수준이 낮아집니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>스피커 렌더링에 대 한 5 분 당 평균 결함입니다. 좋은 품질을 위해서는 5 분에 1 보다 작아야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>마이크 캡처에 대 한 5 분 당 평균 결함. 좋은 품질을 위해서는 5 분에 1을 미만 이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화기에서 보고 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p> </p></td>
<td><p>CPU 클록을 기준으로 한 마이크 장치 시계 드리프트 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p> </p></td>
<td><p>CPU 클록을 기준으로 스피커 장치 시계 드리프트 속도입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p> </p></td>
<td><p>CPU 클록을 기준으로 스피커 장치 시계 드리프트 속도입니다.</p>
<p>평균 마이크 캡처 스트림 타임 스탬프 (밀리초) (통화의 마지막 20 초)</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p> </p></td>
<td><p>평균 스피커는 호출의 마지막 20 초 동안 스트림 타임 스탬프 오류를 밀리초 단위로 렌더링 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>음성 스위치는 인터럽트 감소 기능이 있는 반 양방향 모드입니다. 음성 전환 항목의 원인:</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>0x02 ENTER_VS_ECHO</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>원인은 이러한 개별적인 원인을 조합 했을 수 있습니다. ENTER_VS_FORCEORCONVERGENCE는 테스트 용도의 regkey 에서만 사용 하도록 설정할 수 있습니다.</p>
<p>Microsoft Lync Server 2013에서이 열의 데이터 형식이 변경 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>에코 이벤트의 원인:</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>0x02 ECHO_EVENT_POSTAEC_ECHO</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0x10</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>원인은 이러한 개별적인 원인을 조합 했을 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>마이크 캡처 스트림에 화면 표시가 감지 된 시간의 백분율입니다. 일반적으로 헤드셋 이나 송수화기의 경우 값은 낮고 스피커 전화 또는 독립 실행형 스피커는 더 높습니다. 화상 음향 반향 제거를 지 원하는 디바이스의 경우 높은 값은 에코 누수를 나타냅니다. 다른 디바이스의 경우이 메트릭은 장치 품질을 평가 하는 데 사용해 서는 안 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>전송 된 스트림에서 반향을 감지 하는 시간 백분율입니다. 송신 스트림의 화면 표시 백분율 에코 누수를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>게이트웨이에서 중재 서버의 신호 수준을 수신 했습니다. 이는 중재 서버에만 적용 됩니다. 이 메트릭의 단위는 dBoV입니다. 좋은 품질을 위해서는 허용 되는 범위는 [-30 ~-18] dBoV 이어야 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>게이트웨이에서 중재 서버의 신호 수준을 수신 했습니다. 이는 중재 서버에만 적용 됩니다. 이 메트릭의 단위는 dBoV입니다. 좋은 품질을 위해서는 허용 되는 범위가-50 dBoV 미만 이어야 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>중재 서버 쪽의 AGC (자동 게인 컨트롤)</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>o</p></td>
<td><p> </p></td>
<td><p>호출의 처음 30 초까지 들어오는 신호에 대 한 루트 평균 사각형 (RMS)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>채널 1에서 받은 신호 수준</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>채널 2에서 받은 신호 수준</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>채널 1에서 받은 소음 수준입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>채널 2에서 받은 소음 수준입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>채널 1에서 전송 되는 신호 수준</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>채널 2에서 전송 되는 신호 수준</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>채널 1에서 전송 되는 소음 수준입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>채널 2에서 전송 된 소음 수준입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

