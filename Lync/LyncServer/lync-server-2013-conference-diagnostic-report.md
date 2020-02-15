---
title: 'Lync Server 2013: 전화 회의 진단 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6061f04875d15f163bfb91d8803c488467cadb6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007877"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a>Lync Server 2013의 전화 회의 진단 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-22_

전화 회의 진단 보고서는 모든 회의 세션의 성공 및 실패에 대 한 정보를 제공 합니다. Microsoft Lync Server는 다음과 같은 다양 한 종류의 오류를 구분 합니다.

  - **예상 오류**입니다. 일반적으로 예상 되는 오류는 가장 기술적으로 발생 하는 오류에 불과합니다. 예를 들어 누군가 회의를 시작 하지만 누구나 참가할 수 있는 경우에는 전화를 끊기로 가정 합니다. 기술적으로, 회의가 시작 되었지만 완료 되지 않은 오류입니다. 그러나 모든 사용자가 참석할 수 있을 때까지 이끌이가 회의를 취소 하면 회의가 완료 되지 않을 것으로 예상 하는 것이 좋습니다.

  - **예기치 않은 오류**입니다. 예기치 않은 오류는 해당 상황에 따라 발생할 것으로 예상 되는 오류를 의미 합니다. 예를 들어 이끌이의 모임 정책을 검색할 수 없어서 회의에 참가 하지 못할 수 있습니다. 예기치 않은 오류입니다. 모든 작업을 수행한 후에는 항상 사용자의 모임 정책을 검색할 수 있게 됩니다.

성공, 예상 오류 및 예기치 않은 오류 메트릭은 총 세션 메트릭에 추가되지 않을 수 있습니다. 예를 들어 보고서에 다음과 같은 값이 표시 될 수 있습니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>성공</th>
<th>예상 오류</th>
<th>예기치 않은 오류</th>
<th>총 세션</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2024</p></td>
<td><p>469</p></td>
<td><p>16 </p></td>
<td><p>2521</p></td>
</tr>
</tbody>
</table>


2024 + 469 + 16을 추가 하면 총 2509 세션을 받게 되며 총 세션 열에 총 2521 세션이 표시 됩니다. "누락 된" 세션은 시스템에서 성공 또는 실패로 분류할 수 없는 세션입니다. 예를 들어 타사 제품에서 모니터링 서버에 익숙하지 않은 새로운 진단 코드를 도입 하는 경우가 있습니다. 이와 같은 경우 해당 제품을 사용하여 전화를 걸고 해당 진단 코드를 보고하는 경우를 항상 성공, 예상 오류 또는 예기치 않은 오류로 분류할 수 있는 것은 아닙니다.

<div>

## <a name="accessing-the-conference-diagnostic-report"></a>전화 회의 진단 보고서 액세스

전화 회의 진단 보고서는 모니터링 보고서 홈 페이지에서 액세스 합니다. 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 실패 분포 보고서](lync-server-2013-failure-distribution-report.md) 에 액세스할 수 있습니다.

  - 예기치 않은 오류량

  - 예상 오류량

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a>전화 회의 진단 보고서의 모범 사례 만들기

전화 회의 진단 보고서에는 일련의 그래프가 포함 되어 있습니다. 그래프에 표시 되는 각 열은 실제로 하이퍼링크입니다. 열을 클릭 하면 해당 기간 및 해당 회의 유형에 대해 [Lync Server 2013의 실패 분포 보고서](lync-server-2013-failure-distribution-report.md) 가 드릴 다운 됩니다.

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 회의 진단 보고서를 사용 하 여 수행 되는 회의 유형 (예: 포커스 기반 전화 회의) 또는 회의에 사용 되는에 지 서버에 해당 하는 항목을 필터링 할 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 전화 회의는 시간, 일, 주 또는 월별로 그룹화됩니다.

다음 표에서는 전화 회의 진단 보고서에서 사용할 수 있는 필터를 보여 줍니다.

### <a name="conference-diagnostic-report-filters"></a>전화 회의 진단 보고서 필터

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
<td><p><strong>그룹</strong></p></td>
<td><p>등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>회의 세션</strong></p></td>
<td><p>회의 세션의 유형을 나타냅니다. 다음 중 하나를 선택합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>회의 센터 세션</p></li>
<li><p>모든 MCU 세션</p></li>
<li><p>IM 회의</p></li>
<li><p>응용 프로그램 공유</p></li>
<li><p>A/V 회의</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>선별한

다음 표에서는 각 회의 세션 유형에 대해 회의 진단 보고서에 제공 되는 정보를 보여 줍니다.

### <a name="conference-diagnostic-report-metrics"></a>전화 회의 진단 보고서 메트릭

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
<td><p><strong>성공량</strong></p></td>
<td><p>아니요</p></td>
<td><p>성공한 총 회의 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>성공 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>중요 한 문제로 인해 완료 된 회의 비율입니다. 성공량을 총 세션으로 나눠서 계산됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>예상 오류량</strong></p></td>
<td><p>아니요</p></td>
<td><p>예상 되는 오류가 &quot;&quot; 발생 한 총 회의 수입니다.</p>
<p>예상 오류는 발생할 것으로 예상된 오류입니다. 예를 들어 사용자가 자신의 상태를 방해 금지로 설정한 경우 해당 사용자에 대한 통화가 실패할 것으로 예상할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>예상 오류 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>예상 되는 오류가 발생 한 전화 회의 비율입니다. 예상 오류량을 총 세션으로 나눠서 계산됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>예기치 않은 오류량</strong></p></td>
<td><p>아니요</p></td>
<td><p>예기치 않은 오류가 &quot;&quot; 발생 한 총 전화 회의 수입니다.</p>
<p>예기치 않은 오류는 일반적으로 정상 상태의 시스템으로 보이지만 예기치 않게 발생한 오류입니다. 예를 들어 발신자가 보류 상태일 때는 통화가 종료되지 않아야 합니다. 하지만 통화가 종료되면 바로 예기치 않은 오류로 플래그 지정됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>예기치 않은 오류 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>예기치 않은 오류가 발생 한 전화 회의 비율입니다. 예기치 않은 오류량을 총 세션으로 나눠서 계산됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>성공적인 회의, 실패 한 회의 (예상 오류 및 예기치 않은 오류 모두) 및 분류 되지 않은 회의를 포함 한 총 회의 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

