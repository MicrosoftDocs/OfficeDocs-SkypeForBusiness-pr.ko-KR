---
title: 'Lync Server 2013: Media Quality 메트릭스 배포 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 085525063d13c60dc1702ebf169fed92707675e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a>Lync Server 2013의 Media Quality 메트릭스 배포 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-06_

미디어 품질 메트릭 배포 보고서를 사용 하면 지터 또는 패킷 손실과 같은 경험 치를 품질 메트릭의 분포 값을 보여 주는 그래프를 볼 수 있습니다. 예를 들어 사용자가 총 10 개의 전화 통화를 하 게 되는 경우 이러한 10 개의 호출은 다음과 같은 왕복 횟수를 보고 합니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>통화 번호</th>
<th>왕복 시간 (밀리초)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>4(tcp/ipv4)</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>5mb</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>26</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>20cm(8</p></td>
<td><p>4550</p></td>
</tr>
<tr class="odd">
<td><p>되었는지</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>1천만</p></td>
<td><p>50</p></td>
</tr>
</tbody>
</table>


이러한 왕복 시간에 대 한 평균은 500 밀리초 (5000을 10로 나눈 값)입니다. 500 밀리초는 매우 큰 왕복 시간입니다. 결과적으로 네트워크 정체에 심각한 문제가 있다고 생각할 수 있습니다. 일반적으로 오버 로드 된 네트워크의 결과로 긴 왕복 시간이 있습니다.

물론 실제로는 통화의 90%가 탁월한 왕복 시간을가지고 있습니다. 전체 결과를 나타내는 잘못 된 통화가 하나 있습니다. 평균 왕복 시간만 표시 하는 경우 매우 잘못 된 결론으로 이동할 수 있습니다.

미디어 품질 메트릭 배포 보고서를 사용 하면 특정 메트릭의 그래픽 분포 (예: 라운드트립 시간)를 표시 하 여 잘못 된 결론으로 점프할 필요가 없습니다. 이러한 그래프는 매우 우수한 통화를 10 개, 매우 나쁜 통화를 하는 것을 명확 하 게 만들 수 있습니다. 이 경우에도 해당 통화를 자세히 조사 하는 것이 좋습니다. 그러나 10 개의 통화 중 9 개를 사용 하는 것은 최소한이 시점에서 네트워크에 대 한 불필요 한 변경을 할 이유가 없다는 것을 제안 한다는 사실입니다.

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 다음 표에는 미디어 품질 메트릭 배포 보고서와 함께 사용할 수 있는 필터가 나와 있습니다.

### <a name="media-quality-metrics-distribution-report-filters"></a>미디어 품질 메트릭 배포 보고서 필터

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
<td><p><strong>보낸 사람</strong></p></td>
<td><p>시간 범위의 시작 날짜/시간입니다. 시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</p>
<p>오후 7/7/2012 1:00</p>
<p>시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다. 날짜별로 데이터를 보려면 날짜만 입력 합니다.</p>
<p>7/7/2012</p>
<p>주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</p>
<p>7/3/2012</p>
<p>주는 항상 일요일 ~ 토요일을 실행 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>받는 사람</strong></p></td>
<td><p>시간 범위의 종료 날짜/시간입니다. 시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</p>
<p>오후 7/7/2012 1:00</p>
<p>종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다. 날짜별로 데이터를 보려면 날짜만 입력 합니다.</p>
<p>7/7/2012</p>
<p>주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</p>
<p>7/3/2012</p>
<p>주는 항상 일요일 ~ 토요일을 실행 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>최소 x 축 기준</strong></p></td>
<td><p>그래프의 X 축에 표시할 최소값입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>최대 x 축</strong></p></td>
<td><p>그래프의 X 축에 표시할 가장 높은 값입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Access 형식</strong></p></td>
<td><p>전화를 걸 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온 되었는지 여부를 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>내부용</p></li>
<li><p>내부</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>통화를 했을 때 외부 클라이언트가 VPN (가상 사설망) 연결을 사용 중인지 여부를 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>VPN</p></li>
<li><p>비 VPN</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>네트워크 유형</strong></p></td>
<td><p>전화를 걸 때 클라이언트가 연결 된 네트워크의 유형을 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>유</p></li>
<li><p>Wireless-n</p></li>
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

