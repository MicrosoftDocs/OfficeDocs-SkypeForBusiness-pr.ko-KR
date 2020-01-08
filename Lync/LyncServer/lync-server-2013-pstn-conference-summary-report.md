---
title: 'Lync Server 2013: PSTN 컨퍼런스 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b98628ea56fb36ec594e5ea4ff9915e9785b3cfa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a>Lync Server 2013의 PSTN 회의 요약 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

Microsoft Lync Server 2013에서 PSTN 컨퍼런스는 하나 이상의 참가자가 PSTN (공공 교환 전화 네트워크) 전화기를 사용 하 여 오디오 부분에 전화를 거는 모든 회의입니다. PSTN 전화는 "유선전화", 휴대폰 또는 IP를 통해 음성을 사용 하지 않는 기타 전화기입니다. 이러한 회의는 모니터링 보고서의 PSTN 회의 라고 할 수 있지만, 일반적으로 전화 접속 회의로 알려져 있습니다.

PSTN 회의 요약 보고서는 조직에 있는 모든 PSTN 컨퍼런스 (즉, 하나 이상의 전화 접속 사용자가 있는 모든 회의)에 대 한 정보를 제공 합니다. 이 보고서에는 총 PSTN 회의 수, 해당 회의에 참여 한 총 사용자 수, 그리고 가장 중요 한 총 전화 접속 사용자 수 (총 PSTN 참가자 메트릭)에 대 한 정보가 포함 되어 있습니다.

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a>PSTN 회의 요약 보고서에 액세스

PSTN 회의 요약 보고서는 모니터링 보고서 홈 페이지 에서만 액세스할 수 있습니다. 이 보고서는 다른 보고서에 연결 되어 있지 않습니다. 각 끝점이이 정보를 제출 하는 데 책임이 있으므로 PSTN 회의에 대 한 자세한 호출 정보를 검색할 수 없습니다. PSTN 전화는 통화 정보를 추적 하거나 제출할 수 없습니다.

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>PSTN 회의 요약 보고서를 최대한 활용 하기

전화 접속 사용자를 포함 하는 모든 회의의 백분율을 확인 하려면 총 PSTN 회의 메트릭의 값을 [Lync Server 2013의 컨퍼런스 요약 보고서](lync-server-2013-conference-summary-report.md)에 있는 총 회의 메트릭으로 비교 합니다.

표시 해야 할 수 있는 것 처럼 많은 PSTN 회의가 표시 되지 않는 경우 전화 접속 사용자를 허용 하는 회의를 구성 하는 기능은 사용자에 게 할당 된 회의 정책에 따라 달라 집니다. 일부 사용자에 게 PS를 보류할 수 있는 권한이 있는 경우에 유의 하세요. TN-ZA&PLATFORM 회의는 매우 적은 PSTN 회의를 분명히 볼 수 있습니다. Lync Server Management Shell 내에서 다음 명령을 실행 하 여 사용자가 PSTN 회의를 예약할 수 있도록 허용 하는 회의 정책 (있는 경우)을 빠르게 확인할 수 있습니다.

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

이는 다음과 같은 데이터를 반환 합니다.

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

이는 다음과 같은 데이터를 반환 합니다.

</div>

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 예를 들어 PSTN 회의 요약 보고서를 사용 하 여 데이터를 그룹화 하는 방법을 선택할 수 있습니다. 이 경우 회의는 시간, 일, 주 또는 월로 그룹화 됩니다.

다음 표에는 PSTN 회의 요약 보고서에 사용할 수 있는 필터가 나와 있습니다.

### <a name="pstn-conference-summary-report-filters"></a>PSTN 회의 요약 보고서 필터

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
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>매트릭스

다음 표에는 PSTN 회의 요약 보고서의 정보가 나열 되어 있습니다.

### <a name="pstn-conference-summary-report-metrics"></a>PSTN 회의 요약 보고서 메트릭

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
<td><p><strong>마다</strong></p>
<p><strong>Daily</strong></p>
<p><strong>매주</strong></p>
<p><strong>월간</strong></p></td>
<td><p>아니요</p></td>
<td><p>선택한 시간 간격을 나타냅니다. 해당 되는 경우 지정 된 시간 간격을 클릭 하 여 해당 간격에 대 한 세부 정보를 볼 수 있습니다. 예를 들어 일일 기간을 사용 하는 경우 7/7/2012을 클릭 하면 해당 날짜에 대 한 사용자 등록 작업을 시간별로 분류 하 여 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 PSTN 컨퍼런스</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 접속 액세스를 허용 하는 총 컨퍼런스 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 참가자</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 접속 액세스를 허용 하는 회의에 참가 한 총 사용자 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 A/V 회의 시간 (분)</strong></p></td>
<td><p>아니요</p></td>
<td><p>오디오/시각 컨퍼런스 총 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 A/V 회의 참가자 통화 시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 오디오/시각적 참가자 시간입니다. 예를 들어 한 참가자가 A/V 회의에 5 분을 소요 하 고 다른 참가자가 같은 회의에서 3 분이 소요 되는 경우 총 A/V 회의 참가자 시간은 8 분입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 PSTN 참가자</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 접속 액세스를 허용 하는 회의에 전화를 건 총 사용자 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 PSTN 참가 시간 (분)</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 접속 사용자가 소비한 총 컨퍼런스 시간입니다. 예를 들어 전화 접속 참가 참석자 한 명에 5 분이 소요 되 고 다른 참가자가 같은 회의에서 3 분이 소요 되는 경우 총 PSTN 참가자 시간은 8 분입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>고유한 회의 이끌이</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 접속 액세스를 허용 하는 하나 이상의 회의를 구성한 총 사용자 수입니다. 두 개 이상의 회의를 구성한 사용자는 단일 컨퍼런스만 구성한 사용자와 같이 하나의 고유 이끌이로 간주 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

