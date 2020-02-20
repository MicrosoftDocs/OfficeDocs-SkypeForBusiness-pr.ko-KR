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
ms.openlocfilehash: 0f0d37de40340a66e6d87365ce40924f6c6d98f0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a>Lync Server 2013의 오디오 Clientevent 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-17_

각 레코드에는 오디오 통화의 한 끝점에 대 한 클라이언트 이벤트가 포함 되어 있습니다. 일반적으로 한 통화에는 발신자 용 레코드와 수신자를 위한 레코드가 각각 하나씩 있습니다.


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
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 비율 NetworkSendQuality 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</p>
<p>지터 또는 패킷 손실 측면의 네트워크 품질이 심각 하 고 전송 중인 오디오 품질에 영향을 미칩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 상태로 receivesendquality 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</p>
<p>지터 또는 패킷 손실 측면의 네트워크 품질이 심각 하 고 수신 중인 오디오 품질에 영향을 미칩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 비율 지연 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다. 네트워크 대기 시간이 심각 하며 대화형 통신을 방지 하 여 환경에 영향을 미칩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 완료율 \ 대역폭 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다. 사용 가능한 대역폭이 충분 하지 않은 음성 환경에 적합 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 비율 ' 불량 ' 상태에 대해 CPU 부족 이벤트가 발생 했습니다. 현재 사용 중인 형식 및 응용 프로그램을 처리 하는 데 필요한 CPU 사이클이 부족 합니다. 이렇게 하면 오디오 채널에서 왜곡이 발생 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 DeviceHalfDuplexAEC 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다. 에코를 방지 하기 위해 시스템에서 반이중을 시작 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 DeviceRenderNotFunctioning 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다. 세션에 현재 사용 중인 렌더링 장치가 제대로 작동 하지 않습니다. 이로 인해 단방향 오디오 문제가 발생할 수 있습니다.</p></td>
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
<td><p>세션 비율 DeviceGlitches 이벤트가 ' 불량 ' 상태에 대해 발생 했습니다. 오디오 렌더링 시 왜곡이 발생 하는 심각한 결함이 있습니다. 이러한 오류는 드라이버 문제, DPC (지연 된 프로시저 호출) 폭풍 (드라이버) 및 높은 CPU 사용량이 원인일 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 비율 DeviceLowSNR 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다. 캡처 품질이 매우 나쁨, 매우 소음이 발생 하거나 사용자가 마이크를 너무 멀리 떨어진 곳에 있는 것입니다. 이렇게 하면 왜곡이 발생 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 DeviceLowSpeechLevel 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다. 사용자의 음성 수준이 너무 낮아 시스템에서 더 이상 늘릴 수 없습니다. 이로 인해 왜곡이 발생 하거나 단방향 오디오로 인식 될 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 상태로 deviceclipping 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다.</p>
<p>근접 종료 음성이 마이크를 클립 하면 클리핑이 진행 되는 동안 끝점을 듣게 됩니다. 가까운 마이크 클리핑을 방지 하는 것이 중요 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 DeviceEchoEvent 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다. 장치 또는 설정으로 인해 시스템에서 보정 하는 기능이 더 이상 표시 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td><p> </p></td>
<td><p>세션 백분율 DeviceNearEndToEchoRatio 이벤트가 ' 잘못 된 ' 상태에 대해 발생 했습니다. 사용자의 음성이 사용자에 게 방해가 되는 것을 제한 하므로 캡처 중인 에코에 비해 너무 낮습니다. 스피커 볼륨을 줄이고 마이크를 talker 가까이 이동 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>세션 중 DeviceMultipleEndpoints 이벤트가 ' 잘못 됨 ' 상태에 대해 발생 한 횟수입니다. 동일한 세션의 여러 오디오 끝점이 검색 되 고 시스템에서 렌더링 볼륨을 줄여 보정 했습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>세션 중 DeviceHowlingEvent 이벤트가 ' 잘못 됨 ' 상태에 대해 발생 한 횟수입니다. 오디오 피드백 루프가 검색 되었습니다 (오디오 경로를 여러 번 공유 하는 경우).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>세션 백분율 DeviceRenderZeroVolume 이벤트가 "잘못 됨 ' 상태에 있을 때 발생 했습니다. 렌더링 장치가 제로 볼륨으로 설정 되었습니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>세션 백분율 DeviceRenderMute 이벤트가 "잘못 됨 ' 상태에 있을 때 발생 했습니다. 렌더링 장치가 음소거 되었습니다.</p>
<p>이 칼럼은 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

