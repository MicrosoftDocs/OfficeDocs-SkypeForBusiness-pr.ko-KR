---
title: 'Lync Server 2013: 미디어 품질 비교 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05b157be6cc94f0b01dbefadfd89041118b944e1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500665"
---
# <a name="media-quality-comparison-report-in-lync-server-2013"></a>Lync Server 2013의 미디어 품질 비교 보고서

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-04-22_

미디어 품질 비교 보고서를 사용하면 다양한 유형의 오디오 통화(예: 유선 연결에서 수행된 통화와 무선 연결에서 수행된 통화)의 통화 품질 값을 비교할 수 있습니다.

<div>

## <a name="accessing-the-media-quality-comparison-report"></a>미디어 품질 비교 보고서 액세스

미디어 품질 비교 보고서는 모니터링 보고서 홈 페이지에서 액세스됩니다.

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에서는 미디어 품질 비교 보고서에서 사용할 수 있는 필터를 보여 줍니다.

### <a name="media-quality-comparison-report-filters"></a>미디어 품질 비교 보고서 필터

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
<td><p><strong>시작</strong></p></td>
<td><p>시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</p>
<p>7/7/2012 1:00 PM</p>
<p>시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</p>
<p>7/7/2012</p>
<p>주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</p>
<p>7/3/2012</p>
<p>주는 항상 일요일부터 토요일까지로 실행됩니다.</p></td>
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
<td><p><strong>착신</strong></p></td>
<td><p>주 비교 항목으로 사용할 통화 유형입니다. 허용되는 값은 다음과 같습니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>외부</p></li>
<li><p>내부</p></li>
<li><p>VPN</p></li>
<li><p>비 VPN</p></li>
<li><p>유선</p></li>
<li><p>Wireless-n</p></li>
<li><p>외부 및 유선</p></li>
<li><p>외부 및 무선</p></li>
<li><p>외부 및 VPN</p></li>
<li><p>외부 및 VPN 외</p></li>
<li><p>내부 및 유선</p></li>
<li><p>내부 및 무선</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>비교 통화 항목</strong></p></td>
<td><p>보조 비교 항목으로 사용할 통화 유형입니다. 허용되는 값은 다음과 같습니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>외부</p></li>
<li><p>내부</p></li>
<li><p>VPN</p></li>
<li><p>비 VPN</p></li>
<li><p>유선</p></li>
<li><p>Wireless-n</p></li>
<li><p>외부 및 유선</p></li>
<li><p>외부 및 무선</p></li>
<li><p>외부 및 VPN</p></li>
<li><p>외부 및 VPN 외</p></li>
<li><p>내부 및 유선</p></li>
<li><p>내부 및 무선</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>간격당</strong></p></td>
<td><p>시간 간격입니다. 다음 중 하나를 선택합니다.</p>
<ul>
<li><p>시간별(최대 25시간 표시 가능)</p></li>
<li><p>일별(최대 31일 표시 가능)</p></li>
<li><p>주별(최대 12주 표시 가능)</p></li>
</ul>
<p>시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>메트릭

다음 표에서는 미디어 품질 비교 보고서에서 제공되는 정보를 보여 줍니다.

### <a name="media-quality-comparison-report-metrics"></a>미디어 품질 비교 보고서 메트릭

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
<td><p><strong>통화량</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 통화 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>저하(MOS)</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화 중에 발생 하는 평균 MOS (즉, 평균 평가 점수) 성능 저하입니다. 성능 저하 값의 범위는 0.0 개에서 높은 5.0 까지입니다. 값이 0.5 이하인 경우 허용 되는 저하를 나타냅니다. 이전에는 사용자가 1 ~ 5의 배율로 통화 품질을 평가 하 여 평균 성적 점수를 계산 했습니다. Lync Server에서는 사용자가 통화를 평가 하는 방법을 예측 하기 위한 알고리즘 집합을 사용 합니다.</p>
<p>정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버 또는 끝점의 과부하 등의 경우에는 저하 값이 높게 나타날 수 있습니다. 저하 값이 높으면 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>불량 통화율</strong></p></td>
<td><p>아니요</p></td>
<td><p>불량으로 분류된 총 통화 수입니다. 불량 통화는 측정된 메트릭 중 적어도 하나 이상이 허용 값을 초과하는 모든 통화입니다(예: 지터가 과도하게 발생한 통화).</p></td>
</tr>
<tr class="even">
<td><p><strong>왕복(밀리초)</strong></p></td>
<td><p>아니요</p></td>
<td><p>RTP(실시간 전송 프로토콜) 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 평균 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 200밀리초 미만 정도로 간주됩니다.</p>
<p>국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>패킷 손실</strong></p></td>
<td><p>아니요</p></td>
<td><p>RTP(Real-time Transport Protocol) 패킷 손실의 평균 비율입니다. (패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다.) 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>지터(밀리초)</strong></p></td>
<td><p>아니요</p></td>
<td><p>RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다. (지터는 통화의 shakiness을 측정 한 것 &quot; &quot; 입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>힐러 숨김 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 오디오 샘플 수에 대한 숨겨진 평균 오디오 샘플 비율입니다. (숨겨진 오디오 샘플은 손실된 네트워크 패킷으로 인해 발생하는 갑작스러운 전환을 매끄럽게 조정하기 위해 사용되는 기술입니다.) 값이 높으면 패킷 손실이나 지터로 인해 적용된 손실 숨김 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>힐러 늘임 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 오디오 샘플 수에 대한 늘어진 평균 오디오 샘플 비율입니다. (늘어진 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 연장되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 늘림 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>힐러 압축 비율</strong></p></td>
<td><p>아니요</p></td>
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

