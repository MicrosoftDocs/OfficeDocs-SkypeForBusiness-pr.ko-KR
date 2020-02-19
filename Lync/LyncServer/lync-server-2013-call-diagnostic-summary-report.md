---
title: 'Lync Server 2013: 통화 진단 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ebd3da761fe9923f05c2ddd5dfced852b4b27e6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a>Lync Server 2013의 통화 진단 요약 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-06-06_

통화 진단 요약 보고서는 실패 한 피어-투-피어 및 회의 세션에 대 한 전체 확인을 제공 합니다. 이 보고서에는 두 세션 유형의 전체 오류율이 표시 되 고, 오류 정보는 세션 모달 형식에 따라 아래로 나뉩니다.

  - 인스턴트 메시징

  - 응용 프로그램 공유

  - 파일 전송

  - 오디오만

  - 비디오

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a>통화 진단 요약 보고서 액세스

통화 진단 요약 보고서는 모니터링 보고서 홈 페이지에서 액세스 합니다. 통화 진단 요약 보고서에서 보고서의 피어 투 피어 세션 요약 섹션에서 오류율을 클릭 하 여 [Lync Server 2013의 피어 투 피어 활동 진단 보고서](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) 에 액세스할 수 있습니다. 다음 회의 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 전화 회의 진단 보고서](lync-server-2013-conference-diagnostic-report.md) 에 액세스할 수도 있습니다.

  - 전체 세션 실패율

  - 회의 센터 실패율

  - MCU 실패율

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>통화 진단 요약 보고서의 효과적인 활용

통화 진단 요약 보고서에는 Microsoft Lync Server 2013에서 사용 되는 다양 한 형식의 실패율을 비교 하는 그래프가 포함 되어 있습니다. 이러한 그래프의 열은 실제로 hotlinks 예를 들어 피어 투 피어 세션에 대 한 인스턴트 메시징 열을 클릭 하면 호출 진단 요약 보고서에 포함 된 모든 인스턴트 메시징 세션에 대 한 추가 정보를 제공 하는 보고서 인 [Lync Server 2013의 피어 투 피어 활동 진단 보고서](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)인스턴스로 드릴 다운 됩니다.

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 통화 진단 요약 보고서를 사용 하면 세션에서 사용 되는 등록자 풀 또는에 지 서버와 같은 작업을 수행할 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 통화는 시간, 일, 주 및 월별로 그룹이 지정됩니다.

다음 표에서는 통화 진단 요약 보고서에서 사용할 수 있는 필터를 보여 줍니다.

### <a name="call-diagnostic-summary-report-filters"></a>통화 진단 요약 보고서 필터

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
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>피어 투 피어 세션에 대 한 메트릭

다음 표에서는 피어 투 피어 세션 (즉, 참가자가 두 개만 포함 되는 세션)에 대해 통화 진단 요약 보고서에 제공 되는 정보를 보여 줍니다.

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
<th>이 항목에 대한 정렬 가능 여부</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>총 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>수행 된 총 피어 투 피어 세션 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>실패율</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패한 피어 투 피어 세션의 비율입니다. 이 항목을 클릭 하면 보고서에 실패 한 피어 투 피어 세션에 대 한 자세한 정보가 표시 되는 피어 투 피어 활동 진단 보고서가 표시 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>회의 세션에 대 한 메트릭

다음 표에서는 회의 세션 (즉, 참가자가 세 명 이상인 세션)에 대해 통화 진단 보고서에 제공 되는 정보를 보여 줍니다.

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
<th>이 항목에 대한 정렬 가능 여부</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>총 전화 회의</strong></p></td>
<td><p>아니요</p></td>
<td><p>수행 된 총 전화 회의 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 전화 회의 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>수행 된 총 회의 세션 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>전체 세션 실패율</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 총 회의 세션의 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>회의 센터 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 총 포커스 기반 전화 회의 세션 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>회의 센터 실패율</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 집중 (Focus) 기반 회의 세션의 비율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>MCU 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 총 회의 서버 기반 (이전의 Multipoint 컨트롤 단위 또는 MCU) 전화 회의 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MCU 실패율</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 회의 서버 기반 (이전의 Multipoint Control Unit 또는 MCU) 회의의 비율입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

