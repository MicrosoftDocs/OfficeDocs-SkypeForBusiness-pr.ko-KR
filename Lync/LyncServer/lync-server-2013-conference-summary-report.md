---
title: 'Lync Server 2013: 전화 회의 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772ece86803f9fc499b38299621ccd491221f84b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a>Lync Server 2013의 전화 회의 요약 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-09-03_

회의 요약 보고서에서는 온라인 회의 세션에 대한 전반적인 보기를 제공합니다. 일반적으로 회의에는 사용자가 2 명 이상 포함 되며 Microsoft Lync Server 2013 회의 서비스를 사용 해야 합니다. 비교적 피어 투 피어 세션에서는 일반적으로 사용자가 2명만 포함되며 Lync Server의 회의 서비스를 사용할 필요가 없습니다. 피어 투 피어 활동은 [Lync Server 2013의 피어 투 피어 활동 요약 보고서](lync-server-2013-peer-to-peer-activity-summary-report.md)에 보고 됩니다.

전화 회의 요약 보고서에는 특정 기간 (매시간, 매일, 매주, 매월) 동안 개최 된 회의 수를 알리는 것은 물론, 해당 회의에 참가 한 총 사용자 수 및 고유한 전화 회의 총 수를 알리는 정보도 표시 됩니다. 이끌이.

"고유한" 이끌이란 적어도 하나 이상의 회의를 예약한 모든 사람을 의미합니다. 예를 들어 Pilar Ackerman이 하나의 회의를 예약했다면 한 명의 고유한 이끌이가 됩니다. Ken Myer가 148개의 회의를 예약했어도 한 명의 고유한 이끌이로 계산됩니다. 예를 들어, 아래 표에는 8개의 예약된 회의가 표시되지만 고유한 이끌이는 단 3명인 Ken Myer, Pilar Ackerman 및 David Ahs뿐입니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>회의 이끌이</th>
<th>회의 날짜</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


회의 요약 보고서에는 또한 오디오 및/또는 비디오가 포함된 회의 개수가 표시됩니다.

<div>

## <a name="accessing-the-conference-summary-report"></a>회의 요약 보고서 액세스

회의 요약 보고서는 모니터링 보고서 홈 페이지에서 액세스됩니다. 다음 메트릭 중 하나를 클릭하여 회의 활동 보고서로 드릴다운할 수 있습니다.

  - 총 회의

  - 총 참가자

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a>회의 요약 보고서의 모범 사례 만들기

회의 요약 보고서에 사용된 대부분의 메트릭에 대한 총 값은 보고서 아래에서 찾을 수 있습니다. 지정된 기간 동안 수행된 총 회의 수 및 이러한 회의에 참가한 총 사용자 수와 같은 값을 보려면 아래로 스크롤합니다. 보고서 아래에 합계로 표시되지 않는 메트릭은 총 고유한 회의 이끌이입니다. 왜 그럴까요? 이유가 있습니다. 1개월 분량의 데이터를 조사한다고 가정해보십시오. 1일째에는 고유한 회의 이끌이 수가 34명이고, 2일째에는 고유한 회의 이끌이 수가 27명입니다. 그러면 이 이틀 동안의 고유한 회의 이끌이 수는 61명일까요? 반드시 그렇지는 않을 것입니다. 2일째에 회의를 주최한 27명이 모두 그 전날에 회의를 주최한 34명에 포함될 수도 있습니다. 예를 들어 여기에 표시된 간단한 보고서에서도 Ken Myer와 Pilar Ackerman은 7/7/2012 및 7/2/2012에 회의를 예약했습니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>회의 이끌이</th>
<th>회의 날짜</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


회의를 주최한 고유한 사용자의 총 수를 보다 쉽게 이해하기 위해 시간 간격을 바꿔보겠습니다. 예를 들어 하루가 아니라 한 달을 기준으로 데이터를 살펴 보겠습니다.

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 전화 회의 요약 보고서에서는 데이터의 그룹화 방법을 선택할 수 있습니다. 이 경우 전화 회의는 시간, 일, 주 또는 월별로 그룹화됩니다.

다음 표에서는 전화 회의 요약 보고서에서 사용할 수 있는 필터를 보여 줍니다.

### <a name="conference-summary-report-filters"></a>전화 회의 요약 보고서 필터

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
<p>2012/7/7 오후 1:00</p>
<p>종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</p>
<p>7/7/2012</p>
<p>주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</p>
<p>7/3/2012</p>
<p>주는 항상 일요일부터 토요일까지로 실행됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>간격당</strong></p></td>
<td><p>시간 간격입니다. 다음 중 하나를 선택합니다.</p>
<ul>
<li><p>시간별(최대 25시간 표시 가능)</p></li>
<li><p>일별(최대 31일 표시 가능)</p></li>
<li><p>주별(최대 12주 표시 가능)</p></li>
<li><p>월별(최대 12개월 표시 가능)</p></li>
</ul>
<p>시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>선별한

다음 표에서는 전화 회의 요약 보고서에서 제공되는 정보를 보여 줍니다.

### <a name="conference-summary-report-metrics"></a>전화 회의 요약 보고서 메트릭

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
<td><p><strong>매시간</strong></p>
<p><strong>매일</strong></p>
<p><strong>매주</strong></p>
<p><strong>월간</strong></p></td>
<td><p>아니요</p></td>
<td><p>필터 도구 모음에서 선택한 시간 간격을 나타냅니다. 적용 가능한 경우 제공된 시간 간격을 클릭하여 해당 간격에 대한 자세한 정보를 볼 수 있습니다. 예를 들어 일별 간격을 사용 중이고 7/7/2012을 클릭하면 해당 날짜에 사용자 등록 활동에 대한 시간별 세부 내역을 볼 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 전화 회의</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 회의 유형에 관계없이 보류된 총 전화 회의 수입니다. 이 항목을 클릭하면 보고서에 선택한 기간에 대한 전화 회의 활동 보고서가 표시됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 참가자</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 회의에 참가한 총 사용자 수입니다. 이 항목을 클릭하면 보고서에 선택한 기간에 대한 전화 회의 활동 보고서가 표시됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>회의당 평균 참가자 수</strong></p></td>
<td><p>아니요</p></td>
<td><p>특정 전화 회의에 참가한 평균 사용자 수입니다. 총 회의를 총 참가자로 나눠서 확인됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 A/V 회의</strong></p></td>
<td><p>아니요</p></td>
<td><p>오디오 또는 비디오를 포함하는 총 회의 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 A/V 회의 시간(분)</strong></p></td>
<td><p>아니요</p></td>
<td><p>오디오/비디오 회의에 할당된 총 시간(분)입니다.</p>
<p>총 A/V 회의 시간 메트릭은 A/V 회의를 포함 한 모든 오디오/시각적 회의 유형을 요약 하 여 보여 줍니다. IM 회의; 앱 공유 회의 데이터 회의 및 PSTN 회의</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 A/V 회의 참가 시간(분)</strong></p></td>
<td><p>아니요</p></td>
<td><p>오디오/비디오 회의에 할당된 총 참가 시간(분)입니다. 예를 들어 한 명의 사용자가 오디오/비디오 회의에서 5분을 소비하고 두 번째 사용자가 동일한 회의에서 3분을 소비했다고 가정하면 회의 참가 시간은 5분과 3분을 더한 총 8분이 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>평균 A/V 회의 시간(분)</strong></p></td>
<td><p>아니요</p></td>
<td><p>오디오/비디오 회의당 평균 시간(분)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>회의의 고유한 총 이끌이 수</strong></p></td>
<td><p>아니요</p></td>
<td><p>적어도 하나 이상의 회의를 구성한 총 사용자 수입니다. 회의를 하나 이상 구성한 사용자는 단일 회의만 구성한 사용자와 같이 한 명의 고유한 이끌이로 계산됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 회의 메시지</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의 중 전송된 총 인스턴스 메시지 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

