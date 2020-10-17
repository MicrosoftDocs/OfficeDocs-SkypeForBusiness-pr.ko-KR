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
# <a name="audiosignal-table-in-lync-server-2013"></a>Lync Server 2013의 오디오 신호 테이블

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-11-12_

각 레코드는 하나의 끝점에 대 한 오디오 신호 메트릭을 나타냅니다. 일반적으로 각 통화에는 두 개의 레코드가 있고, 하나는 발신자에 대 한 것이 고 하나는 수신자를 위한 것입니다.


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
<th><strong>세부 정보</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Conferencedatetime이 동일할</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>비트만</p></td>
<td><p>Primary</p></td>
<td><p>0: 수신자 데이터</p>
<p>1: 발신자 데이터</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sendsignallevel 참조</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>아날로그 후 게인 제어 오디오 신호 수준을 나타냅니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 최소 30 dBmo여야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Sendsignallevel 참조를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sendnoiselevel 참조</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>아날로그 향상 후 음성 노이즈 레벨을 나타냅니다. 이 메트릭의 단위는 dBmo입니다. 적정 품질을 위해서는 35 dBmo 미만이어야 합니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Sendnoiselevel 참조를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>반향 반환 손실 보정 메트릭입니다. 이 메트릭의 단위는 dB입니다. 값이 낮으면 에코가 적습니다. 이 메트릭은 A/V 회의 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>확성기 렌더링에 대 한 5 분 당 평균 결함입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>마이크 캡처에 대 한 5 분 당 평균 결함입니다. 적정 품질을 위해서는 5분당 1 미만이어야 합니다. A/V 회의 서버, 중재 서버 또는 IP 전화에서 보고되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p> </p></td>
<td><p>CPU 클럭에 비례하여 마이크 장치 클럭 드리프트 비율입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p> </p></td>
<td><p>CPU 클럭에 비례하여 스피커 장치 클럭 드리프트 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p> </p></td>
<td><p>CPU 클럭에 비례하여 스피커 장치 클럭 드리프트 비율입니다.</p>
<p>통화의 최근 20초 동안 발생한 평균 마이크 캡처 스트림 타임스탬프 오류(밀리초)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>10 진수 (9, 2)</p></td>
<td><p> </p></td>
<td><p>통화의 최근 20 초 동안 발생 한 평균 스피커 렌더링 스트림 타임 스탬프 오류 (밀리초)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>음성 스위치는 중단 기능이 감소된 반이중 모드입니다. 음성 스위치 항목의 원인:</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>원인은 이러한 개별 원인의 조합이 될 수 있습니다. ENTER_VS_FORCEORCONVERGENCE은 test 목적의 regkey 에서만 사용 하도록 설정할 수 있습니다.</p>
<p>Microsoft Lync Server 2013에서이 열에 대 한 데이터 형식이 변경 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>에코 이벤트의 원인은 다음과 같습니다.</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0x02</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>0x10 ECHO_EVENT_MIC_CLIPPING</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>원인은 이러한 개별 원인의 조합이 될 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>마이크 캡처 스트림에서 화면 표시가 감지 되는 시간 비율입니다. 일반적으로 헤드셋 이나 송수화기에 대 한 값은 낮고, 스피커 전화 또는 독립 실행형 스피커의 경우에는 더 높습니다. 온보드 음향 반향 취소를 지 원하는 장치의 경우 높은 값은 에코 누수를 나타냅니다. 다른 장치의 경우에는이 메트릭을 사용 하 여 장치 품질을 평가 해서는 안 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>전송 된 스트림에서 에코를 감지 하는 시간 비율입니다. 전송 스트림에서 에코 비율이 높으면 에코 누출을 나타낼 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>게이트웨이에서 중재 서버에 대 한 신호 수준을 받았습니다. 이는 중재 서버에만 적용 됩니다. 이 메트릭의 단위는 dBoV입니다. 좋은 품질을 위해 허용 되는 범위는 [-30 ~-18] dBoV 이어야 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>게이트웨이에서 중재 서버에 대 한 신호 수준을 수신 했습니다. 중재 서버에만 적용됩니다. 이 메트릭의 단위는 dBoV입니다. 적정 품질을 위해 허용되는 범위는 -50 dBoV 미만입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>중재 서버 쪽의 AGC (자동 게인 컨트롤)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>식</p></td>
<td><p> </p></td>
<td><p>통화의 처음 30 초 동안 들어오는 신호의 RMS (root mean 제곱)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>채널 1에서 수신 되는 신호 수준입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>채널 2에서 수신 되는 신호 수준입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>채널 1에서 수신 되는 노이즈 수준입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>채널 2에서 수신 되는 노이즈 수준입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>채널 1에서 송신 되는 신호 수준입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>채널 2에서 송신 되는 신호 수준입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>채널 1에서 전송 되는 노이즈 수준입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>채널 2에서 송신 되는 노이즈 수준입니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

