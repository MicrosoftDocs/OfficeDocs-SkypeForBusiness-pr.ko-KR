---
title: 'Lync Server 2013: 피어 투 피어 IM 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f44d25ec36788e6964ea81bde71e82f3746c5aee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982805"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a>Lync Server 2013의 피어 투 피어 IM 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-01_

피어 투 피어 IM 보고서는 피어 투 피어 인스턴트 메시징 (IM) 세션에 대 한 추세 정보를 풀 및 인증 유형별로 분류 하 여 제공 합니다. 보고서에는 지정 된 기간 동안에 보유 한 총 세션 수 (예: 일일 또는 시간별) 또는 해당 기간 동안 보낸 총 인스턴트 메시지 수를 표시할 수 있습니다.

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a>피어 투 피어 IM 보고서에 액세스

[Lync Server 2013에서 피어 투 피어 활동 요약 보고서](lync-server-2013-peer-to-peer-activity-summary-report.md) 를 열고 다음 메트릭 중 하나를 클릭 하 여 피어 투 피어 IM 보고서에 액세스할 수 있습니다.

  - 총 피어 투 피어 IM 세션

  - 총 피어 투 피어 IM 메시지

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>피어 투 피어 IM 보고서를 최대한 활용 하기

기본적으로 피어 투 피어 IM 보고서에는 사용자가 시간 당 메시지 수 (또는 설정에 따라 일)가 표시 됩니다. 그러나 일일 세션당 일별 세션만 표시 하도록 선택할 수도 있습니다. 이렇게 하려면 보고서 창의 오른쪽 위 모서리에서 **매개 변수 숨기기/표시** 를 클릭 한 다음 **보고서** 목록에서 **세션 개수** 를 클릭 합니다.

</div>

<div>

## <a name="filters"></a>필터가

필터는 더욱 세밀 하 게 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있는 방법을 제공 합니다. 다음 표에는 피어 투 피어 IM 보고서에 사용할 수 있는 필터가 나와 있습니다.

### <a name="peer-to-peer-im-report-filters"></a>피어 투 피어 IM 보고서 필터

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
<td><p>시간 범위에 대 한 시작 날짜 및 시간입니다. 시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</p>
<p>오후 7/7/2012 1:00</p>
<p>시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다. 날짜별로 데이터를 보려면 날짜만 입력 합니다.</p>
<p>7/7/2012</p>
<p>주별 또는 월별로 보려면 주 또는 월에 속하는 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</p>
<p>7/3/2012</p>
<p>주는 항상 일요일 ~ 토요일을 실행 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>받는 사람</strong></p></td>
<td><p>시간 범위의 종료 날짜 및 시간입니다. 시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</p>
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
<p>시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하면 시작 날짜부터 시작 하 여 최대 값만 표시 됩니다. 예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>보고서 기준</strong></p></td>
<td><p>보고서에 사용할 값을 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>세션 수</p></li>
<li><p>메시지 수</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>풀에의 한 피어 투 피어 IM 세션에 대 한 메트릭

다음 표에는 피어 투 피어 IM 보고서에 제공 되는 정보가 나와 있습니다.

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>풀에의 한 피어 투 피어 IM 세션에 대 한 메트릭

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
<td><p>등록자 풀 또는 Edge 서버의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>날짜/시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션이 발생 한 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 세션 수 또는 총 메시지 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>인증 유형별 피어 투 피어 IM 세션에 대 한 메트릭

다음 표에는 피어 투 피어 세션에서 참가자가 사용 하는 각 유형의 인증에 대해 피어 투 피어 IM 보고서에 제공 되는 정보가 나열 되어 있습니다.

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>인증 유형별 피어 투 피어 IM 세션에 대 한 메트릭

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
<td><p><strong>인증 유형</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션 참가자가 사용 하는 인증 유형입니다. 값은 일반적으로 다음 중 하나입니다.</p>
<ul>
<li><p>Enterprise</p></li>
<li><p>제휴</p></li>
<li><p>PIC</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>날짜/시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션이 발생 한 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 세션 수 또는 총 메시지 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

