---
title: 'Lync Server 2013: 위치 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2035d66d9b690a351a9b286eeff378ec0a36c1f9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a>Lync Server 2013의 위치 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

위치 보고서는 네트워크 위치(즉, 네트워크 서브넷)별로 그룹화된 통화 품질 메트릭에 대한 정보를 제공합니다. 사용자가 통화 품질에 문제를 겪는 경우 이 보고서를 통해 해당 문제가 전역적으로 나타나는지, 지정된 네트워크 세그먼트로만 크게 국한되는지를 확인할 수 있습니다.

<div>

## <a name="accessing-the-location-report"></a>위치 보고서 액세스

위치 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다. 또한 다음 메트릭 중 하나를 클릭하여 통화 목록 보고서까지 드릴 다운할 수 있습니다.

  - 통화량

  - 불량 통화율

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 위치 보고서에서는 통화가 시작된 위치와 같은 항목 또는 무선 또는 유선 연결에서 통화가 수행되었는지 여부에 따라 필터링할 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 통화는 시간, 일, 주 및 월별로 그룹이 지정됩니다.

다음 표에서는 위치 보고서에 사용할 수 있는 필터를 보여 줍니다.

### <a name="location-report-filters"></a>위치 보고서 필터

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>이름</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</p>
<p>7/7/2012 1:00 PM</p>
<p>시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</p>
<p>7/7/2012</p>
<p>주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</p>
<p>7/3/2012</p>
<p>주는 항상 일요일부터 토요일까지입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</p>
<p>7/7/2012 1:00 PM</p>
<p>종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</p>
<p>7/7/2012</p>
<p>주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</p>
<p>7/3/2012</p>
<p>주는 항상 일요일부터 토요일까지로 실행됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>발신자 위치</strong></p></td>
<td><p>통화를 시작한 사용자의 IP 서브넷입니다. <strong>[모두]</strong>만 선택하면 모든 서브넷을 나타낼 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>수신자 위치</strong></p></td>
<td><p>통화를 받은 사용자의 IP 서브넷입니다. <strong>[모두]</strong>만 선택하면 모든 서브넷을 나타낼 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>네트워크 유형</strong></p></td>
<td><p>통화가 시도되었을 때 클라이언트가 연결된 네트워크의 유형을 나타냅니다. 다음 중 하나를 선택합니다.</p>
<ol>
<li><p>모든</p></li>
<li><p>유선</p></li>
<li><p>Wireless-n</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>통화가 시도되었을 때 외부 클라이언트가 VPN(가상 사설망) 연결을 사용 중이었는지를 나타냅니다. 다음 중 하나를 선택합니다.</p>
<ol>
<li><p>모든</p></li>
<li><p>VPN</p></li>
<li><p>비 VPN</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>선별한

다음 표에서는 위치 보고서에서 제공되는 정보를 보여 줍니다.

### <a name="location-report-metrics"></a>위치 보고서 메트릭

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
<td><p><strong>발신자 서브넷</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화를 시작한 사용자의 IP 서브넷입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>수신자 서브넷</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화를 받은 사용자의 IP 서브넷입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>통화량</strong></p></td>
<td><p>예</p></td>
<td><p>수행된 총 통화 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>불량 통화율</strong></p></td>
<td><p>예</p></td>
<td><p>불량 통화로 분류된 통화 비율입니다. 불량 통화는 측정된 메트릭 중 적어도 하나 이상이 허용 값을 초과하는 모든 통화입니다(예: 지터가 과도하게 발생한 통화).</p></td>
</tr>
<tr class="odd">
<td><p><strong>왕복(밀리초)</strong></p></td>
<td><p>예</p></td>
<td><p>RTP(실시간 전송 프로토콜) 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 평균 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 100밀리초 미만 정도로 간주됩니다.</p>
<p>국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>저하(MOS)</strong></p></td>
<td><p>예</p></td>
<td><p>통화 중 발생한 MOS(평균 평가점) 저하에 대한 평균값입니다. 저하 값의 범위는 0.0(낮음)에서 5.0(높음)까지입니다. 값이 0.5이하이면 허용 가능한 저하 수준을 나타냅니다. 현재까지 평균 평가점은 사용자가 1부터 5까지 통화 품질에 대한 점수를 스스로 매기게 하여 계산되었습니다. Lync Server에서 Lync Server는 알고리즘 집합을 사용 하 여 사용자가 통화를 평가 하는 방법을 예측 합니다.</p>
<p>정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버 또는 끝점의 과부하 등의 경우에는 저하 값이 높게 나타날 수 있습니다. 저하 값이 높으면 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>패킷 손실</strong></p></td>
<td><p>예</p></td>
<td><p>RTP 패킷에 대한 평균 손실률입니다. (패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다.) 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>지터</strong></p></td>
<td><p>예</p></td>
<td><p>RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다. (지터는 통화의 &quot;shakiness&quot; 을 측정 한 것입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>힐러 숨김 비율</strong></p></td>
<td><p>예</p></td>
<td><p>총 오디오 샘플 수에 대한 숨겨진 평균 오디오 샘플 비율입니다. (숨겨진 오디오 샘플은 손실된 네트워크 패킷으로 인해 발생하는 갑작스러운 전환을 매끄럽게 조정하기 위해 사용되는 기술입니다.) 값이 높으면 패킷 손실이나 지터로 인해 적용된 손실 숨김 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>힐러 늘임 비율</strong></p></td>
<td><p>예</p></td>
<td><p>총 오디오 샘플 수에 대한 늘어진 평균 오디오 샘플 비율입니다. (늘어진 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 연장되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 늘림 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>힐러 압축 비율</strong></p></td>
<td><p>예</p></td>
<td><p>총 샘플 수에 대한 압축된 평균 오디오 샘플 비율입니다. (압축된 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 압축되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 압축 수준이 높음을 의미하며 이로 인해 오디오가 빠르게 들리거나 왜곡됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

