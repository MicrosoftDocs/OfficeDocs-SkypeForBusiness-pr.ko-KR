---
title: 'Lync Server 2013: 컨퍼런스 활동 보고서'
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
ms.openlocfilehash: c098bc3a1c8b937b72707c76a3943866ad7b9fbb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a>Lync Server 2013의 컨퍼런스 활동 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

컨퍼런스 활동 보고서를 사용 하 여 매일 보유 하 고 있는 컨퍼런스 수와 이러한 회의가 어디에 있습니까?와 같은 질문에 쉽게 대답할 수 있습니다. 이와 같은 정보는 고유한 권한 뿐만 아니라 문제 해결 도구 이기도 합니다. 예를 들어 사용자가 하루 중간에 특히 느린 네트워크를 complaining 가정해 보겠습니다. 회의 활동 보고서를 신속 하 게 살펴보기 할 수 있는 이유는 무엇 인가요? 오전 10:00, 2:00 PM 시간 사이에 더 많은 회의가 예정 되어 있는 것입니다.

느린 네트워크로 인해 문제가 발생 하는 경우 사용자가 하루 보다 덜 trafficked 시간에 일부 회의를 다시 예약 하도록 할 수 있습니다.

<div>

## <a name="accessing-the-conference-activity-report"></a>컨퍼런스 활동 보고서에 액세스

회의 활동 보고서에는 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 회의 요약 보고서](lync-server-2013-conference-summary-report.md) 에서 액세스할 수 있습니다.

  - 총 컨퍼런스

  - 총 참가자

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a>컨퍼런스 활동 보고서를 최대한 활용 하기

기본적으로 컨퍼런스 활동 보고서에는 지정 된 기간에 대 한 총 컨퍼런스 수 (예: 하루 총 회의 수 또는 일일 총 컨퍼런스 수)가 표시 됩니다. 그러나 해당 기간 또는 총 참가자 수 (분)에 대 한 총 참가자 수를 표시 하도록 선택할 수도 있습니다. 이렇게 하려면 매개 변수 표시/숨기기 단추를 클릭 하 여 필터링 옵션을 표시 하 고 보고서 드롭다운 목록에서 다음 중 하나를 선택 합니다.

  - 참가자 수

  - 참가자 통화 시간

  - 컨퍼런스 수

</div>

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 다음 표에는 회의 활동 보고서에 사용할 수 있는 필터가 나와 있습니다.

### <a name="conference-activity-report-filters"></a>컨퍼런스 활동 보고서 필터

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
<td><p><strong>보고서 기준</strong></p></td>
<td><p>보고서에 사용할 값을 나타냅니다. 다음 중 하나를 선택할 수 있습니다.</p>
<ul>
<li><p>참가자 수</p></li>
<li><p>참가자 통화 시간</p></li>
<li><p>컨퍼런스 수</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a>풀 별 컨퍼런스에 대 한 메트릭

다음 표에는 각 풀에 대 한 회의 활동 보고서의 정보가 나열 되어 있습니다.

### <a name="metrics-for-conferences-by-pool"></a>풀 별 컨퍼런스에 대 한 메트릭

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
<td><p><strong>풀</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의에 사용 되는 등록자 풀 또는 Edge 서버의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>날짜/시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의가 보류 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 참가자 수, 총 참가자 시간 또는 총 회의 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a>서버 유형별 회의 메트릭

다음 표에는 각 유형의 서버에 대 한 회의 활동 보고서의 정보가 나열 되어 있습니다.

### <a name="metrics-for-conferences-by-server-type"></a>서버 유형별 회의 메트릭

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
<td><p><strong>회의 서버 유형</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의에 사용 되는 서버 유형으로, 일반적으로 다음 중 하나입니다.</p>
<ul>
<li><p>웹 회의 서버</p></li>
<li><p>IM 회의 서버</p></li>
<li><p>전화 통신 회의 서버</p></li>
<li><p>AV 회의 서버</p></li>
<li><p>응용 프로그램 공유</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>날짜/시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의가 보류 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 참가자 수, 총 참가자 시간 또는 총 회의 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

