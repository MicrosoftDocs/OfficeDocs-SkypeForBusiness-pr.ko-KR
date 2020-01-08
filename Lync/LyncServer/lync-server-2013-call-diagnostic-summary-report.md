---
title: 'Lync Server 2013: 호출 진단 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e747d257e7c88973790e8fd0c9ba828949248598
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a>Lync Server 2013의 호출 진단 요약 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-06_

전화 진단 요약 보고서는 실패 한 피어 투 피어 및 회의 세션의 전반적인 모습을 제공 합니다. 이 보고서는 두 유형의 세션에 대 한 전체 오류율을 표시 하 고 오류 정보를 세션 형식으로 아래로 나눕니다.

  - 인스턴트 메시지

  - 응용 프로그램 공유

  - 파일 전송

  - 오디오

  - 비디오만

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a>전화 진단 요약 보고서에 액세스

모니터링 보고서 홈 페이지에서 전화 진단 요약 보고서에 액세스할 수 있습니다. 호출 진단 요약 보고서에서 보고서의 피어 투 피어 세션 요약 섹션에서 오류율을 클릭 하 여 [Lync Server 2013에서 피어 투 피어 작업 진단 보고서](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) 에 액세스할 수 있습니다. 다음 회의 메트릭 중 하나를 클릭 하 여 [Lync Server 2013에서 전화 회의 진단 보고서](lync-server-2013-conference-diagnostic-report.md) 에 액세스할 수도 있습니다.

  - 전체 세션 실패 율

  - 초점 고장 속도

  - MCU 실패 율

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>통화 진단 요약 보고서를 최대한 활용 하기

전화 진단 요약 보고서에는 Microsoft Lync Server 2013에서 사용 되는 다양 한 형식을의 실패율을 비교 하는 그래프가 포함 되어 있습니다. 이러한 그래프의 열은 실제로 hotlinks. 예를 들어 피어 투 피어 세션에 대해 인스턴트 메시지 열을 클릭 하면 [Lync Server 2013에서 피어 투 피어 작업 진단 보고서](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)의 인스턴스가 드릴 다운 되며,이는 전화 진단 요약 보고서에 포함 된 모든 인스턴트 메시징 세션에 대 한 추가 세부 정보를 제공 하는 보고서입니다.

</div>

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 예를 들어 통화 진단 요약 보고서를 사용 하 여 세션에 사용 되는 등록자 풀이나 Edge 서버와 같은 작업을 필터링 할 수 있습니다. 데이터 그룹화 방법을 선택할 수도 있습니다. 이 경우 통화는 시, 일, 주 또는 월로 그룹화 됩니다.

다음 표에는 호출 진단 요약 보고서와 함께 사용할 수 있는 필터가 나열 되어 있습니다.

### <a name="call-diagnostic-summary-report-filters"></a>전화 진단 요약 보고서 필터

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
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>피어 투 피어 세션에 대 한 메트릭

다음 표에는 피어 투 피어 세션 (즉, 두 명의 참가자만 참여 하는 세션)에 대 한 호출 진단 요약 보고서에 제공 되는 정보가 나열 되어 있습니다.

### <a name="metrics-for-peer-to-peer-sessions"></a>피어 투 피어 세션에 대 한 메트릭

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
<td><p><strong>총 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>수행 된 피어 투 피어 세션의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>실패 율</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 피어 투 피어 세션의 백분율입니다. 이 항목을 클릭 하면 실패 한 피어 투 피어 세션에 대 한 자세한 정보를 표시 하는 피어 투 피어 작업 진단 보고서가 보고서에 표시 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>회의 세션에 대 한 메트릭

다음 표에는 회의 세션 (즉, 세 명 이상의 참가자와 관련 된 세션)에 대 한 호출 진단 보고서에서 제공 하는 정보가 나열 되어 있습니다.

### <a name="metrics-for-conferencing-sessions"></a>회의 세션에 대 한 메트릭

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
<td><p><strong>총 컨퍼런스</strong></p></td>
<td><p>아니요</p></td>
<td><p>수행 된 총 컨퍼런스 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 회의 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>수행 된 총 회의 세션 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>전체 세션 실패 율</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 총 회의 세션의 백분율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>포커스 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 포커스 기반 회의 세션의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>초점 고장 속도</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 포커스 기반 회의 세션의 백분율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>MCU 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 총 회의 서버 기반 (이전의 Multipoint 컨트롤 단위 또는 MCU) 회의 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MCU 실패 율</strong></p></td>
<td><p>아니요</p></td>
<td><p>장애가 있는 회의 서버 기반 (이전의 Multipoint 컨트롤 단위 또는 MCU) 회의의 백분율입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

