---
title: 'Lync Server 2013: 회의 참가 시간 보고서'
description: 'Lync Server 2013: 회의 참가 시간 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd4aa5d21a8109a323bb953c7196f43715d51413
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542794"
---
# <a name="conference-join-time-report-in-lync-server-2013"></a>Lync Server 2013의 회의 참가 시간 보고서

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-04-23_

회의 참가 시간 요약을 사용 하면 사용자가 회의에 참가 하는 데 걸리는 시간을 확인할 수 있습니다. 이 보고서에는 평균 참가 시간 (밀리초)이 표시 되 고, 2 초 이내에 회의에 참가할 수 있었던 사용자 수, 회의에 참가 하는 데 2 ~ 5 초 사이에 필요한 사용자 수를 알 수 있는 분류도 제공 됩니다.

<div>

## <a name="accessing-the-conference-join-time-report"></a>회의 참가 시간 보고서 액세스

회의 참가 시간 보고서는 모니터링 보고서 홈 페이지에서 액세스 합니다.

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에서는 회의 참가 시간 보고서에 사용할 수 있는 필터를 보여 줍니다.

### <a name="conference-join-time-report-filters"></a>회의 참가 시간 보고서 필터

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
<tr class="even">
<td><p><strong>풀</strong></p></td>
<td><p>등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>회의 세션</strong></p></td>
<td><p>세션 유형입니다. 허용되는 값은 다음과 같습니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>포커스 세션 (온라인 모임에 대 한 중앙 정책 및 상태 관리자, 그리고 회의의 모든 측면을 조정 하는 포커스)</p></li>
<li><p>응용 프로그램 공유</p></li>
<li><p>A/V 회의</p></li>
</ul>
<p>[모두]를 선택 하면 총 회의 참가 시간이 보고서 위쪽에 표시 됩니다. 이러한 합계는 Microsoft Exchange 또는 Microsoft Outlook을 사용 하 여 예약 된 회의에만 해당 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>메트릭

다음 표에서는 회의 참가 시간 보고서에 제공 된 정보를 보여 줍니다.

### <a name="conference-join-time-report-metrics"></a>회의 참가 시간 보고서 메트릭

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
<td><p><strong>날짜</strong></p>
<p>이 메트릭에 대 한 실제 제목은 선택 된 간격에 따라 달라 집니다.</p></td>
<td><p>아니요</p></td>
<td><p>회의가 발생 한 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>성공한 세션, 실패한 세션(예상 오류 및 예기치 않은 오류 모두) 및 분류되지 않은 세션을 포함한 총 세션 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>평균 (밀리초)</strong></p></td>
<td><p>아니요</p></td>
<td><p>참가자가 회의에 참가 하는 데 걸린 평균 시간 (밀리초)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>세션 &lt; 2 초, 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>2 초 이내에 회의에 참가할 수 있었던 참가자 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션 &lt; 2 초, 백분율</strong></p></td>
<td><p>아니요</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>세션 2-5 초, 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의에 참가 하는 데 2 ~ 5 초가 소요 된 참가자 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션 2-5 초, 백분율</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의에 참가 하는 데 2 ~ 5 초가 소요 된 총 통화 참가자 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>세션 5-10 초, 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의에 참가 하는 데 5 ~ 10 초가 소요 된 참가자 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션 5-10 초, 백분율</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의에 참가 하는 데 5 ~ 10 초가 소요 된 총 통화 참가자 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>세션 &gt; 10 초, 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의에 참가 하는 데 10 초 이상이 소요 된 참가자 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션 &gt; 10 초, 백분율</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의에 참가 하는 데 10 초 이상이 소요 된 총 통화 참가자 비율입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

