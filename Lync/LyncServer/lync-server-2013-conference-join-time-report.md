---
title: 'Lync Server 2013: 컨퍼런스 참가 시간 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fac854b9e296d744473593562f32430c6e21fc87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a>Lync Server 2013의 컨퍼런스 참가 시간 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-04-23_

컨퍼런스 참가 시간 요약을 통해 사용자가 회의에 참가 하는 데 걸리는 시간을 확인할 수 있습니다. 이 보고서에는 평균 참가 시간 (밀리초)이 표시 되 고, 2 초 이내에 회의에 참가할 수 있는 사용자 수, 회의에 참가 하기 위해 2 ~ 5 초 사이에 필요한 사용자 수를 알 수 있는 분류도 제공 됩니다.

<div>

## <a name="accessing-the-conference-join-time-report"></a>컨퍼런스 참가 시간 보고서에 액세스

회의 참가 시간 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다.

</div>

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 다음 표에는 컨퍼런스 참가 시간 보고서와 함께 사용할 수 있는 필터가 나열 되어 있습니다.

### <a name="conference-join-time-report-filters"></a>컨퍼런스 참가 시간 보고서 필터

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
<td><p>세션의 유형입니다. 사용 가능한 값은 다음과 같습니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>포커스 세션 (포커스는 온라인 모임에 대 한 중앙 정책 및 상태 관리자 이며, 회의의 모든 측면을 조정 합니다.)</p></li>
<li><p>응용 프로그램 공유</p></li>
<li><p>A/V 회의</p></li>
</ul>
<p>[모두]를 선택 하면 총 컨퍼런스 참가 시간이 보고서의 맨 위에 표시 됩니다. 이러한 합계는 Microsoft Exchange 또는 Microsoft Outlook을 사용 하 여 예약한 회의에만 해당 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>매트릭스

다음 표에는 컨퍼런스 참가 시간 보고서에 제공 되는 정보가 나열 되어 있습니다.

### <a name="conference-join-time-report-metrics"></a>컨퍼런스 참가 시간 보고서 메트릭

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
<td><p><strong>시작일</strong></p>
<p>이 메트릭의 실제 제목은 선택한 간격에 따라 달라 집니다.</p></td>
<td><p>아니요</p></td>
<td><p>회의가 발생 한 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>성공한 세션, 실패 한 세션 (예상 되는 실패 및 예기치 못한 실패), 범주화 되지 않은 세션 등의 총 세션 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>평균 (밀리초)</strong></p></td>
<td><p>아니요</p></td>
<td><p>참가자가 회의에 참가 하는 데 걸린 평균 시간 (밀리초)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>세션 &lt; 2 초, 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>2 초 이내로 회의에 참가할 수 있는 참가자의 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션 &lt; 2 초, 백분율</strong></p></td>
<td><p>아니요</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>세션 2-5 초, 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의에 참가 하는 데 2 초와 5 초 사이에 걸린 참가자의 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션 2-5 초, 백분율</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의에 참가 하기 위해 2 초와 5 초 사이에 걸린 총 통화 참가자의 백분율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>세션 5-10 초, 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의에 참가 하는 데 5 초에서 10 초가 소요 되는 참가자의 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션 5-10 초, 백분율</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의에 참가 하는 데 5 초에서 10 초가 소요 되는 총 통화 참가자의 백분율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>세션 &gt; 10 초, 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의에 참가 하는 데 10 초가 소요 되는 참가자의 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션 &gt; 10 초, 백분율</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 회의에 참가 하는 데 10 초가 소요 되는 총 통화 참가자의 백분율입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

