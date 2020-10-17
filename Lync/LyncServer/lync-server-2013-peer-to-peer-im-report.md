---
title: 'Lync Server 2013: 피어-투-피어 IM 보고서'
description: 'Lync Server 2013: 피어 투 피어 IM 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eac6291d0f099af8269ed15f7dc8c654ac944ed0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557294"
---
# <a name="peer-to-peer-im-report-in-lync-server-2013"></a>Lync Server 2013의 피어 투 피어 IM 보고서

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-01_

피어-투-피어 IM 보고서는 풀과 인증 유형별로 구분된 피어-투-피어 IM(인스턴트 메시징) 세션에 대한 추세 정보를 제공합니다. 이 보고서는 지정된 기간(예: 일별 또는 시간별) 동안 진행된 세션의 총 수를 표시할 수도 있고, 해당 기간 동안 발송된 인스턴트 메시지의 총 수를 표시할 수도 있습니다.

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a>피어-투-피어 IM 보고서 액세스

[Lync Server 2013에서 피어 투 피어 활동 요약 보고서](lync-server-2013-peer-to-peer-activity-summary-report.md) 를 열고 다음 메트릭 중 하나를 클릭 하 여 피어 투 피어 IM 보고서에 액세스할 수 있습니다.

  - 총 피어 투 피어 IM 세션

  - 총 피어 투 피어 IM 메시지

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>피어 투 피어 IM 보고서를 가장 효율적으로 활용

기본적으로 피어 투 피어 IM 보고서에는 시간별(또는 설정에 따라 일별) 메시지 수가 표시됩니다. 그러나 특정일의 시간당 세션 수를 표시할 수도 있습니다. 이렇게 하려면 보고서 창 오른쪽 위에서 **매개 변수 표시/숨기기**를 클릭하고 **보고서 작성자** 목록에서 **세션 수**를 클릭합니다.

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에서는 피어 투 피어 IM 보고서에 사용할 수 있는 필터를 보여 줍니다.

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
<td><p><strong>시작</strong></p></td>
<td><p>시간 범위의 시작 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜와 시간을 모두 입력합니다.</p>
<p>7/7/2012 1:00 PM</p>
<p>시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</p>
<p>7/7/2012</p>
<p>주 또는 월별로 보려면 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</p>
<p>7/3/2012</p>
<p>주는 항상 일요일부터 토요일까지로 실행됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>시간 범위의 종료 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</p>
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
<td><p><strong>보고서 작성자</strong></p></td>
<td><p>보고서에 사용할 값을 나타냅니다. 다음 중 하나를 선택합니다.</p>
<ul>
<li><p>세션 수</p></li>
<li><p>메시지 수</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>풀별 피어 투 피어 IM 세션 메트릭

다음 표에서는 피어 투 피어 IM 보고서에서 제공되는 정보를 보여 줍니다.

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>풀별 피어 투 피어 IM 세션 메트릭

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
<td><p>등록자 풀 또는에 지 서버의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>날짜/시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션이 발생한 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>합계</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 세션 수 또는 총 메시지 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>인증 유형별 피어 투 피어 IM 세션 메트릭

다음 표에서는 피어 투 피어 세션의 참가자가 사용하는 각 인증 유형에 대해 피어 투 피어 IM 보고서에 제공되는 정보를 보여 줍니다.

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>인증 유형별 피어 투 피어 IM 세션 메트릭

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
<td><p><strong>인증 유형</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션 참가자가 사용하는 인증 유형입니다. 값은 일반적으로 다음 중 하나입니다.</p>
<ul>
<li><p>Enterprise</p></li>
<li><p>페더레이션된</p></li>
<li><p>C</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>날짜/시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션이 발생한 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>합계</strong></p></td>
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

