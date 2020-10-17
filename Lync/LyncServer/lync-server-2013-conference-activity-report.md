---
title: 'Lync Server 2013: 회의 활동 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe99c67faa5cc9d0fadd2bdabd260c9d40091303
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526045"
---
# <a name="conference-activity-report-in-lync-server-2013"></a>Lync Server 2013의 전화 회의 활동 보고서

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-22_

전화 회의 활동 보고서를 사용 하면 매일 몇 회의를 개최 하 고 언제 어떤 회의가 진행 되 고 있습니까? 이와 같은 정보는 자체 권한 뿐만 아니라 문제 해결 도구 이기도 합니다. 예를 들어 사용자가 특히 하루 중에 네트워크가 느리게 불만 가정 합니다. 전화 회의 활동 보고서에 대 한 간략 한 설명을 통해 가능한 이유는 다음 중 하나입니다. 1 시간 10:00 시, 2:00 오후 10 시 사이에 회의가 더 많이 진행 되 고 있습니다.

느린 네트워크로 인해 문제가 발생 하는 경우 사용자가 하루 덜 트래픽이 더 적은 시간에 일부 전화 회의를 다시 예약 하도록 할 수 있습니다.

<div>

## <a name="accessing-the-conference-activity-report"></a>전화 회의 활동 보고서 액세스

전화 회의 활동 보고서는 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 전화 회의 요약 보고서](lync-server-2013-conference-summary-report.md) 에서 액세스 합니다.

  - 총 회의

  - 총 참가자

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a>전화 회의 활동 보고서를 가장 효율적으로 활용

기본적으로 전화 회의 활동 보고서에는 지정 된 기간에 대 한 총 회의 수 (예: 하루 총 회의 수 또는 하루 중 시간당 총 회의 수)가 표시 됩니다. 그러나 해당 기간에 대 한 총 참석자 수 또는 총 참가자 수 (분)를 표시 하도록 선택할 수도 있습니다. 이렇게 하려면 매개 변수 표시/숨기기 단추를 클릭 하 여 필터링 옵션을 표시 한 다음 보고서 기준 드롭다운 목록에서 다음 중 하나를 선택 합니다.

  - 참가자 수

  - 참가자 시간 (분)

  - 전화 회의 수

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에서는 전화 회의 활동 보고서에서 사용할 수 있는 필터를 보여 줍니다.

### <a name="conference-activity-report-filters"></a>전화 회의 활동 보고서 필터

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
<td><p>시간 간격입니다. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>시간별(최대 25시간 표시 가능)</p></li>
<li><p>일별(최대 31일 표시 가능)</p></li>
<li><p>주별(최대 12주 표시 가능)</p></li>
<li><p>월별(최대 12개월 표시 가능)</p></li>
</ul>
<p>시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>보고서 작성자</strong></p></td>
<td><p>보고서에 사용할 값을 나타냅니다. 다음 중 하나를 선택할 수 있습니다.</p>
<ul>
<li><p>참가자 수</p></li>
<li><p>참가자 시간 (분)</p></li>
<li><p>전화 회의 수</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a>풀 별 전화 회의 메트릭

다음 표에서는 각 풀에 대 한 전화 회의 활동 보고서의 정보를 보여 줍니다.

### <a name="metrics-for-conferences-by-pool"></a>풀 별 전화 회의 메트릭

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
<td><p><strong>풀</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 회의에서 사용 되는 등록자 풀 또는에 지 서버의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>날짜/시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 회의가 보류 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>합계</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 참가자 수, 총 참가 시간 (분) 또는 총 전화 회의 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a>서버 유형별 전화 회의 메트릭

다음 표에서는 각 서버 유형에 대 한 전화 회의 활동 보고서의 정보를 보여 줍니다.

### <a name="metrics-for-conferences-by-server-type"></a>서버 유형별 전화 회의 메트릭

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
<td><p><strong>회의 서버 유형</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 회의에서 사용 되는 서버의 유형으로, 일반적으로 다음 중 하나입니다.</p>
<ul>
<li><p>웹 회의 서버</p></li>
<li><p>IM 회의 서버</p></li>
<li><p>전화 회의 서버</p></li>
<li><p>AV 회의 서버</p></li>
<li><p>응용 프로그램 공유</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>날짜/시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 회의가 보류 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>합계</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 참가자 수, 총 참가 시간 (분) 또는 총 전화 회의 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

