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

# <a name="audioclientevent-table-in-lync-server-2013"></a>Lync Server 2013의 AudioClientEvent 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-17_

각 레코드에는 오디오 통화의 한 끝점에 대 한 클라이언트 이벤트가 포함 됩니다. 일반적으로 한 통화에는 두 개의 레코드 (호출자 용 1 개와 피호출자 용)가 있습니다.


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
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 NetworkSendQuality 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다.</p>
<p>지터 또는 패킷 손실로 인 한 네트워크 품질은 심각 하 고 전송 되는 오디오 품질에 영향을 미칩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 ReceiveSendQuality 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</p>
<p>지터 또는 패킷 손실 측면의 네트워크 품질은 심각 하며 수신 되는 오디오 품질에 영향을 미칩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 지연 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다. 네트워크 대기 시간이 심각 하 고 대화형 통신을 방지 하 여 환경에 영향을 미칩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 \ \ \ \에 대 한 \ \ \ n 대역폭 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다. 사용할 수 있는 대역폭이 불충분 한 음성 환경에 적합 하지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 CPU 이벤트 부족이 ' 잘못 된 ' 상태에 대해 발생 했습니다. 현재 사용 중인 형식을 및 응용 프로그램을 처리 하는 데 필요한 CPU 사이클이 부족 합니다. 오디오 채널에 왜곡이 발생 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 DeviceHalfDuplexAEC 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다. 화면을 방지 하기 위해 시스템에서 반이중을 입력 했습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 DeviceRenderNotFunctioning 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다. 현재 세션에 사용 중인 렌더 장치가 제대로 작동 하지 않습니다. 이로 인해 단방향 오디오 문제가 발생할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 DeviceCaptureNotFunctioning 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다. 세션에 현재 사용 중인 캡처 장치가 제대로 작동 하지 않습니다. 이로 인해 단방향 오디오 문제가 발생할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 DeviceGlitches 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다. 왜곡을 초래 하는 오디오 렌더링에는 심각한 결함이 있습니다. 이러한 결함은 드라이버 문제, DPC (지연 된 프로시저 호출) 스톰 (드라이버) 및 높은 CPU 사용으로 인해 발생할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 DeviceLowSNR 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다. 캡처 품질이 매우 나쁨, 매우 소음이 있거나 사용자가 마이크에서 멀리 떨어져 있는 것입니다. 이렇게 하면 왜곡이 발생할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 DeviceLowSpeechLevel 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다. 사용자의 음성 수준이 너무 낮기 때문에 시스템에서 더 이상 증가 시킬 수 없습니다. 이는 왜곡을 발생 시키거나 단방향 오디오로 인식 될 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 DeviceClipping 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</p>
<p>가까운 끝에 있는 음성이 마이크를 클리핑하여 클리핑으로 인 한 far의 왜곡을 듣습니다. 가까운 마이크 클리핑을 피하는 것이 중요 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 DeviceEchoEvent 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다. 장치 또는 설정으로 시스템에서 보정 하는 기능을 벗어나는 화면을 발생 시킵니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 DeviceNearEndToEchoRatio 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다. 사용자의 음성이 사용자에 게 영향을 줄 수 있는 것이 제한 되어 있으므로 캡처 중인 에코에 비해 너무 낮게 표시 됩니다. 스피커 볼륨을 낮추고 마이크를 발표자 가까이 놓습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>세션 중 ' 잘못 된 ' 상태에 대해 DeviceMultipleEndpoints 이벤트가 발생 한 횟수입니다. 동일한 세션의 여러 오디오 끝점을 감지 했 고 렌더링 볼륨을 줄임으로써 시스템을 보정 했습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>세션 중 ' 잘못 된 ' 상태에 대해 DeviceHowlingEvent 이벤트가 발생 한 횟수입니다. 오디오 피드백 루프가 여러 끝점 공유 오디오 경로에 의해 감지 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>세션 백분율 DeviceRenderZeroVolume 이벤트가 "잘못 된 ' 상태에 있을 때 발생 했습니다. 렌더 장치가 0 볼륨으로 설정 되었습니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>세션 백분율 DeviceRenderMute 이벤트가 "잘못 된 ' 상태에 있을 때 발생 했습니다. 렌더 장치가 음소거 되었습니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

