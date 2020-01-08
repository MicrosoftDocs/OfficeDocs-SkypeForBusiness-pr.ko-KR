---
title: 'Lync Server 2013: 컨퍼런스 진단 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279d844a4c67d3b09b35fff92f6868cae8971059
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a>Lync Server 2013의 컨퍼런스 진단 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

컨퍼런스 진단 보고서는 모든 회의 세션의 성공 및 실패에 대 한 정보를 제공 합니다. Microsoft Lync Server는 서로 다른 종류의 오류를 구분 합니다.

  - **오류가 발생**했습니다. 일반적으로 예상 되는 오류는 대부분의 기술적인 측면 에서만 발생 합니다. 예를 들어 누군가 회의를 시작 하 고 누구나 참가할 수 있도록 하기 위해 연결이 중단 되었다고 가정해 보세요. 기술적으로 실패 하는 문제: 회의가 시작 되었지만 완료 되지 않았습니다. 그러나 모든 사용자가 참가 하기 전에 회의가 취소 되 면 해당 회의가 완료 되지 않을 것으로 예상 하는 것이 발생 합니다.

  - **예기치 않은 오류**. 예기치 않은 오류는 상황에 따라 발생 하는 것으로 예상 되지 않는 오류를 의미 합니다. 예를 들어 이끌이 모임 정책을 검색할 수 없기 때문에 회의를 받을 수 없습니다. 예기치 않은 오류: 이제 항상 사용자의 모임 정책을 검색할 수 있습니다.

성공, 예상 실패, 예기치 않은 실패 메트릭이 총 세션 메트릭에 추가 되지 않을 수 있습니다. 예를 들어 보고서에 다음 값이 표시 될 수 있습니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>회의</th>
<th>예상 되는 오류</th>
<th>예기치 않은 오류</th>
<th>총 세션</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2024</p></td>
<td><p>469</p></td>
<td><p>16</p></td>
<td><p>2521</p></td>
</tr>
</tbody>
</table>


2024 + 469 + 16을 추가 하는 경우 총 2509 세션을 받을 수 있지만 총 세션 열에는 총 2521 세션이 표시 됩니다. "누락 된" 12 개의 세션은 시스템에서 성공 또는 실패로 분류할 수 없는 세션입니다. 이는 타사 제품에 모니터링 서버에 익숙하지 않은 새로운 진단 코드가 도입 된 경우에 해당 될 수 있습니다. 이 경우 해당 제품을 사용 하 여 호출 하 고 해당 진단 코드를 보고 하면 항상 성공, 실패 또는 예기치 않은 오류에 대 한 분류할 수 없습니다.

<div>

## <a name="accessing-the-conference-diagnostic-report"></a>컨퍼런스 진단 보고서에 액세스

모니터링 보고서 홈 페이지에서 전화 회의 진단 보고서에 액세스할 수 있습니다. 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 실패 배포 보고서](lync-server-2013-failure-distribution-report.md) 에 액세스할 수 있습니다.

  - 예기치 않은 오류 볼륨

  - 예상 고장 볼륨

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a>컨퍼런스 진단 보고서를 최대한 활용 하기

회의 진단 보고서에 일련의 그래프가 포함 되어 있습니다. 그래프에 표시 되는 각 열은 실제로 하이퍼링크입니다. 열을 클릭 하면 [Lync Server 2013에서](lync-server-2013-failure-distribution-report.md) 해당 기간 및 해당 전화 형식의 실패 배포 보고서로 드릴 다운 합니다.

</div>

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 예를 들어 회의 진단 보고서를 사용 하면 수행 중인 회의 유형 (예: 포커스 기반 컨퍼런스) 또는 회의에 사용 되는 Edge 서버를 기준으로 필터링 할 수 있습니다. 데이터 그룹화 방법을 선택할 수도 있습니다. 이 경우 회의는 시간, 일, 주 또는 월로 그룹화 됩니다.

다음 표에는 컨퍼런스 진단 보고서에 사용할 수 있는 필터가 나와 있습니다.

### <a name="conference-diagnostic-report-filters"></a>컨퍼런스 진단 보고서 필터

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
<td><p><strong>간격만</strong></p></td>
<td><p>시간 간격. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>매시간 (최대 25 시간 표시할 수 있음)</p></li>
<li><p>매일 (최대 31 일이 표시 될 수 있음)</p></li>
<li><p>주간 (최대 12 주를 표시할 수 있음)</p></li>
<li><p>월간 (최대 12 개월을 표시할 수 있음)</p></li>
</ul>
<p>시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값만 표시할 수 있습니다. 예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>풀</strong></p></td>
<td><p>등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다. 개별 풀을 선택 하거나 <strong>[모두]</strong> 를 클릭 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>회의 세션</strong></p></td>
<td><p>회의 세션의 유형을 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>포커스 세션</p></li>
<li><p>모든 MCU 세션</p></li>
<li><p>메신저 대화 회의</p></li>
<li><p>응용 프로그램 공유</p></li>
<li><p>A/V 회의</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>매트릭스

다음 표에는 각 회의 세션 유형에 대해 회의 진단 보고서에서 제공 하는 정보가 나와 있습니다.

### <a name="conference-diagnostic-report-metrics"></a>컨퍼런스 진단 보고서 메트릭

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>이름</th>
<th>이 항목을 정렬할 수 있나요?</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>성공 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>성공한 총 회의 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>성공 백분율</strong></p></td>
<td><p>아니요</p></td>
<td><p>중대 한 문제에 대해 완료 된 회의 비율입니다. 성공 볼륨을 총 세션으로 나누는 방법으로 계산 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>예상 고장 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>예상 되는 오류가 &quot;&quot; 발생 한 총 컨퍼런스 수입니다.</p>
<p>예상 되는 실패는 예상 되는 오류입니다. 예를 들어 사용자가 자신의 상태를 방해 금지로 설정 하면 해당 사용자에 게 전화를 거는 데 실패 하는 것으로 예상 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>예상 되는 실패 백분율</strong></p></td>
<td><p>아니요</p></td>
<td><p>예상 되는 오류가 발생 한 회의 비율입니다. 예상 고장 볼륨을 총 세션으로 나누어 계산 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>예기치 않은 오류 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>예기치 않은 오류가 &quot;&quot; 발생 한 총 컨퍼런스 수입니다.</p>
<p>예기치 않은 오류가 발생 하는 것은 정상적인 시스템 때문 이라고 표시 되는 오류입니다. 예를 들어 호출자가 대기 상태로 설정 된 경우에는 통화가 종료 되지 않습니다. 이 문제가 발생 하면 예기치 않은 오류로 플래그가 지정 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>예기치 않은 오류 백분율</strong></p></td>
<td><p>아니요</p></td>
<td><p>예기치 않은 오류가 발생 한 회의의 백분율입니다. 예상 하지 못한 볼륨을 총 세션으로 나누면 계산 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>성공적인 컨퍼런스, 실패 한 컨퍼런스 (예상 오류 및 예기치 못한 오류 모두 포함), 범주화 되지 않은 회의 등의 총 회의 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

