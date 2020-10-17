---
title: 'Lync Server 2013: PSTN 전화 회의 요약 보고서'
description: 'Lync Server 2013: PSTN 전화 회의 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3bc468e494577c229562a1cb7cfddaf839f946f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562774"
---
# <a name="pstn-conference-summary-report-in-lync-server-2013"></a>Lync Server 2013의 PSTN 전화 회의 요약 보고서

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-22_

Microsoft Lync Server 2013에서 PSTN 전화 회의는 하나 이상의 참가자가 PSTN (공중 전화망) 전화기를 사용 하 여 오디오 부분에 전화를 거는 모든 회의입니다. PSTN 전화는 "일반 전화선으로", 휴대폰 또는 다른 전화기를 사용 하 여 IP를 통해 음성을 사용할 수 없습니다. 모니터링 보고서에서 PSTN 회의 라고 하지만 이러한 회의는 일반적으로 전화 접속 회의 라고 합니다.

PSTN 전화 회의 요약 보고서에서는 조직에서 수행된 모든 PSTN 전화 회의에 대한 정보를 제공합니다(즉, 전화 접속 사용자가 한 명 이상 포함된 모든 회의). 보고서에는 총 PSTN 전화 회의 수, 이러한 회의에 참가한 총 사용자 수, 그리고 가장 중요한 총 전화 접속 사용자 수(총 PSTN 참가자 메트릭)가 포함됩니다.

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a>PSTN 전화 회의 요약 보고서 액세스

PSTN 전화 회의 요약 보고서는 모니터링 보고서 홈 페이지에서만 액세스할 수 있습니다. 이 보고서는 다른 보고서에 연결되지 않습니다. PSTN 전화 회의에 대해서는 개별 끝점이 이 정보를 제출하기 때문에 자세한 통화 정보를 검색할 수 없습니다. PSTN 전화는 통화 세부 정보를 추적하거나 제출할 수 없습니다.

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>PSTN 전화 회의 요약 보고서의 모범 사례 만들기

전화 접속 사용자를 포함 하는 모든 회의의 비율을 확인 하려면 총 PSTN 전화 회의 메트릭의 값을 [Lync Server 2013의 전화 회의 요약 보고서](lync-server-2013-conference-summary-report.md)에 있는 총 회의 메트릭으로 비교 합니다.

PSTN 전화 회의 수가 예상한 것보다 적은 경우, 전화 접속 사용자를 허용하는 회의를 구성하는 기능이 사용자에게 지정된 회의 정책에 따라 달라진다는 것에 유의하십시오. PSTN 전화 회의를 주최하도록 허용된 사용자 수가 적을수록 PSTN 전화 회의 수가 줄어듭니다. Lync Server 관리 셸 내에서 다음 명령을 실행하면 사용자가 PSTN 전화 회의를 예약하도록 허용하는 회의 정책(있는 경우)을 빠르게 확인할 수 있습니다.

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

그러면 다음과 비슷한 데이터가 반환됩니다.

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

그러면 다음과 비슷한 데이터가 반환됩니다.

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 PSTN 전화 회의 요약 보고서에서는 데이터의 그룹화 방법을 선택할 수 있습니다. 이 경우 전화 회의는 시간, 일, 주 또는 월별로 그룹화됩니다.

다음 표에서는 PSTN 전화 회의 요약 보고서에서 사용할 수 있는 필터를 보여 줍니다.

### <a name="pstn-conference-summary-report-filters"></a>PSTN 전화 회의 요약 보고서 필터

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
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>메트릭

다음 표에서는 PSTN 전화 회의 요약 보고서의 정보를 보여 줍니다.

### <a name="pstn-conference-summary-report-metrics"></a>PSTN 전화 회의 요약 보고서 메트릭

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
<td><p><strong>매시간</strong></p>
<p><strong>매일</strong></p>
<p><strong>매주</strong></p>
<p><strong>월간</strong></p></td>
<td><p>아니요</p></td>
<td><p>선택한 시간 간격을 나타냅니다. 적용 가능한 경우 제공된 시간 간격을 클릭하여 해당 간격에 대한 자세한 정보를 볼 수 있습니다. 예를 들어 일별 간격을 사용 중이고 7/7/2012를 클릭하면 해당 날짜에 사용자 등록 활동에 대한 시간별 세부 내역을 볼 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 PSTN 전화 회의</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 접속 액세스가 허용된 총 전화 회의 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 참가자</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 접속 액세스가 허용된 전화 회의에 참가한 총 사용자 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 A/V 회의 시간(분)</strong></p></td>
<td><p>아니요</p></td>
<td><p>오디오/비디오 회의의 총 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 A/V 회의 참가 시간(분)</strong></p></td>
<td><p>아니요</p></td>
<td><p>오디오/비디오 참가자의 총 시간입니다. 예를 들어 한 사용자가 A/V 회의에서 5분을 소비하고 다른 참가자 같은 회의에서 3분을 소비한 경우 총 A/V 회의 참가자 시간은 8분입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 PSTN 참가자</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 접속 액세스가 허용된 전화 회의에 전화 접속한 총 사용자 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 PSTN 참가자 시간(분)</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 접속 사용자가 소비한 총 전화 회의 시간입니다. 예를 들어 한 전화 접속 사용자가 한 회의에서 5분을 소비하고 다른 참가자 같은 회의에서 3분을 소비한 경우 총 PSTN 참가자 시간은 8분입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>고유한 전화 회의 이끌이</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 접속 액세스가 허용된 전화 회의를 하나 이상 구성한 총 사용자 수입니다. 회의를 하나 이상 구성한 사용자는 단일 회의만 구성한 사용자와 같이 한 명의 고유한 이끌이로 계산됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

