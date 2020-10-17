---
title: 'Lync Server 2013: 통화 목록 보고서'
description: 'Lync Server 2013: 통화 목록 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b08d4c5f3011facc9cd8d4f6b2800638f3cc896
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561694"
---
# <a name="call-list-report-in-lync-server-2013"></a>Lync Server 2013의 통화 목록 보고서

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

통화 목록 보고서는 조직 내부에서 걸거나 받는 개별 통화에 대한 QoE(체감 품질) 메트릭을 제공합니다. 보고되는 실제 메트릭은 통화 목록 보고서에 액세스하는 방식에 따라 다릅니다. 예를 들어 [Lync Server 2013의 장치 보고서](lync-server-2013-device-report.md)에서 보고서를 열면 다음과 같은 메트릭 (장치 보고서에도 보고 되는 메트릭)이 표시 됩니다.

  - 발신자의 마이크

  - 발신자의 스피커

  - 수신자의 마이크

  - 수신자의 스피커

  - 음성 스위치 시간 비율

그러나 [Lync Server 2013의 위치 보고서](lync-server-2013-location-report.md)에서 통화 목록 보고서를 여는 경우에는 이러한 메트릭이 표시 되지 않습니다. 대신 다음과 같은 메트릭을 볼 수 있습니다.

  - 왕복(밀리초)

  - 저하(MOS)

  - 패킷 손실

  - 지터(밀리초)

위치 보고서에서는 이러한 메트릭이 보고되지만, 통화 목록 보고서에서 세부 정보 메트릭을 클릭하면 모든 통화에 대한 완전한 QoE 정보가 제공됩니다.

<div>

## <a name="accessing-the-call-list-report"></a>통화 목록 보고서 액세스

통화 목록 보고서는 다음 보고서에서 액세스할 수 있습니다.

  - [Lync Server 2013의 위치 보고서](lync-server-2013-location-report.md) (통화 량 또는 불량 통화 율 메트릭 클릭)

  - [Lync Server 2013의 장치 보고서](lync-server-2013-device-report.md) (통화 량 또는 불량 통화 율 메트릭 클릭)

  - [Lync Server 2013의 미디어 품질 요약 보고서](lync-server-2013-media-quality-summary-report.md) (통화 량 또는 불량 통화 율 메트릭 클릭)

  - [Lync server 2013의 서버 성능 보고서](lync-server-2013-server-performance-report.md) (통화 량 또는 불량 통화 율 메트릭 클릭)

통화 목록 보고서 내에서 세부 정보 메트릭을 클릭 하 여 [Lync Server 2013의 통화 정보 보고서](lync-server-2013-call-detail-report.md) 에 액세스할 수 있습니다.

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a>통화 목록 보고서의 효과적인 활용

통화 목록 보고서의 일부 메트릭(예: 음성 스위치 시간 비율)이 실제로 무엇을 측정하는지 기억할 수 없는 경우 해당 메트릭 레이블 위에 마우스를 놓으면 도구 설명이 나타나 메트릭에 대한 간단한 설명을 볼 수 있습니다.

</div>

<div>

## <a name="filters"></a>필터

없음. 통화 목록 보고서는 필터링할 수 없습니다.

</div>

<div>

## <a name="metrics"></a>메트릭

다음 표에서는 각 통화에 대해 통화 목록 보고서에 제공된 정보를 보여 줍니다.

### <a name="call-list-report-metrics"></a>통화 목록 보고서 메트릭

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>이름</th>
<th>이 항목에 대한 정렬 가능 여부</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>세부 정보</strong></p></td>
<td><p>아니요</p></td>
<td><p>이 항목을 클릭하면 보고서에 통화에 대한 추가 정보가 표시됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>최초</strong></p></td>
<td><p>예</p></td>
<td><p>통화를 시작한 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>피호출자</strong></p></td>
<td><p>예</p></td>
<td><p>통화를 받은 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>시작 시간</strong></p></td>
<td><p>예</p></td>
<td><p>통화가 시작된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>종료 시간</strong></p></td>
<td><p>예</p></td>
<td><p>통화가 종료된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>발신자 사용자 에이전트</strong></p></td>
<td><p>예</p></td>
<td><p>통화를 시작한 사용자의 끝점에 사용된 소프트웨어입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>수신자 사용자 에이전트</strong></p></td>
<td><p>예</p></td>
<td><p>통화를 받은 사용자의 끝점에 사용된 소프트웨어입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>왕복(밀리초)</strong></p></td>
<td><p>예</p></td>
<td><p>RTP(실시간 전송 프로토콜) 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 평균 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 100밀리초 미만 정도로 간주됩니다.</p>
<p>국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>저하(MOS)</strong></p></td>
<td><p>예</p></td>
<td><p>통화 중 발생한 MOS(평균 평가점) 저하에 대한 평균값입니다. 저하 값의 범위는 0.0(낮음)에서 5.0(높음)까지입니다. 값이 0.5이하이면 허용 가능한 저하 수준을 나타냅니다. 현재까지 평균 평가점은 사용자가 1부터 5까지 통화 품질에 대한 점수를 스스로 매기게 하여 계산되었습니다. Lync Server에서 Lync Server는 알고리즘 집합을 사용 하 여 사용자가 통화를 평가 하는 방법을 예측 합니다.</p>
<p>정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버 또는 끝점의 과부하 등의 경우에는 저하 값이 높게 나타날 수 있습니다. 저하 값이 높으면 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>패킷 손실</strong></p></td>
<td><p>예</p></td>
<td><p>RTP 패킷에 대한 평균 손실률입니다. (패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다.) 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>지터</strong></p></td>
<td><p>예</p></td>
<td><p>RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다. (지터는 통화의 shakiness을 측정 한 것 &quot; &quot; 입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>힐러 숨김 비율</strong></p></td>
<td><p>예</p></td>
<td><p>총 오디오 샘플 수에 대한 숨겨진 평균 오디오 샘플 비율입니다. (숨겨진 오디오 샘플은 손실된 네트워크 패킷으로 인해 발생하는 갑작스러운 전환을 매끄럽게 조정하기 위해 사용되는 기술입니다.) 값이 높으면 패킷 손실이나 지터로 인해 적용된 손실 숨김 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>힐러 늘임 비율</strong></p></td>
<td><p>예</p></td>
<td><p>총 오디오 샘플 수에 대한 늘어진 평균 오디오 샘플 비율입니다. (늘어진 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 연장되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 늘림 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>힐러 압축 비율</strong></p></td>
<td><p>예</p></td>
<td><p>총 샘플 수에 대한 압축된 평균 오디오 샘플 비율입니다. (압축된 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 압축되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 압축 수준이 높음을 의미하며 이로 인해 오디오가 빠르게 들리거나 왜곡됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>연결</strong></p></td>
<td><p>예</p></td>
<td><p>무선 통신 링크의 유형입니다. 일반적으로 다음 중 하나입니다.</p>
<ul>
<li><p>릴레이</p></li>
<li><p>연결할</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

