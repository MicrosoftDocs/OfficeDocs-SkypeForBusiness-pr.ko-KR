---
title: 'Lync Server 2013: 컨퍼런스 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68858d56c47953a99928a59e5f83485ba9d305cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a>Lync Server 2013의 컨퍼런스 요약 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-09-03_

회의 요약 보고서는 온라인 회의 세션의 전체 보기를 제공 합니다. 일반적으로 컨퍼런스에는 2 명 이상의 사용자가 포함 되며 Microsoft Lync Server 2013 회의 서비스를 사용 해야 합니다. 일반적으로 피어 투 피어 세션에는 두 명의 사용자만 포함 되며 Lync Server의 회의 서비스를 사용할 필요가 없습니다. 피어 투 피어 작업은 [Lync Server 2013의 피어 투 피어 작업 요약 보고서](lync-server-2013-peer-to-peer-activity-summary-report.md)에 보고 됩니다.

회의 요약 보고서는 특정 기간 (매시간, 매일, 매주, 매월) 동안 얼마나 많은 회의가 진행 되었는지 알려 주고 해당 회의에 참여 한 총 사용자 수와 고유한 컨퍼런스 총 수를 알려 주는 것도 아닙니다. 이끌이가.

"고유" 이끌이는 하나 이상의 회의를 예약 하는 사람입니다. 예를 들어 Pilar Ackerman은 한 회의를 한 명의 고유한 이끌이만으로 간주 합니다. : 진구 Myer에서 148 회의를 하는 경우 1 개의 고유 이끌이로 간주 됩니다. 예를 들어 아래 표에는 예약 된 8 개의 회의가 표시 되지만,: 진구 Myer, Pilar Ackerman, David Ahs)와 같은 세 가지 고유한 조직자만 나와 있습니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>컨퍼런스 이끌이</th>
<th>컨퍼런스 날짜</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>: 진구 Myer</p></td>
<td><p>오전 7/7/2012 10:00</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>오전 7/7/2012 10:00</p></td>
</tr>
<tr class="odd">
<td><p>: 진구 Myer</p></td>
<td><p>오전 7/7/2012 11:00</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>오전 7/7/2012 11:00</p></td>
</tr>
<tr class="odd">
<td><p>: 진구 Myer</p></td>
<td><p>오후 7/7/2012 1:00</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>오후 7/7/2012 2:00</p></td>
</tr>
<tr class="odd">
<td><p>: 진구 Myer</p></td>
<td><p>오전 7/2/2012 10:00</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>오전 7/2/2012 10:00</p></td>
</tr>
</tbody>
</table>


회의 요약 보고서에는 오디오 및/또는 비디오가 포함 된 회의 수도 표시 됩니다.

<div>

## <a name="accessing-the-conference-summary-report"></a>회의 요약 보고서에 액세스

회의 요약 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다. 다음 메트릭 중 하나를 클릭 하 여 컨퍼런스 활동 보고서를 드릴 다운할 수 있습니다.

  - 총 컨퍼런스

  - 총 참가자

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a>회의 요약 보고서를 최대한 활용 하기

회의 요약 보고서에 사용 되는 대부분의 메트릭 값 합계는 보고서의 맨 아래에서 찾을 수 있습니다. 아래로 스크롤하여 지정 된 기간 동안 보유 한 총 회의 수 및 해당 회의에 참가 한 총 컨퍼런스 수 등의 값을 확인 합니다. 보고서의 맨 아래에서 합산 되지 않는 하나의 메트릭은 총 고유한 회의 이끌이입니다. 왜 안 돼요? 한 가지 이유는 다음과 같습니다. 월의 데이터를 보고 있다고 가정 합니다. 1 일에 34 고유한 회의 이끌이를가지고 있습니다. 일 2에 27 개의 고유한 컨퍼런스 이끌이를가지고 있습니다. 2 일 동안 61 고유한 회의 이끌이가 있다는 의미 입니까? 필요 하지 않습니다. 매일 2 일에 회의를 이끄는 모든 27 명의 사용자가 일 1에 회의를 이끄는 34 사람 중에 있을 수 있습니다. 예를 들어이 간단한 보고서에서는: 진구 Myer 및 Pilar Ackerman이 7/7/2012 및 7/2/2012에서 모두 예약한 회의를 수행 하는 것을 참고 하세요.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>컨퍼런스 이끌이</th>
<th>컨퍼런스 날짜</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>: 진구 Myer</p></td>
<td><p>오전 7/7/2012 10:00</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>오전 7/7/2012 10:00</p></td>
</tr>
<tr class="odd">
<td><p>: 진구 Myer</p></td>
<td><p>오전 7/7/2012 11:00</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>오전 7/7/2012 11:00</p></td>
</tr>
<tr class="odd">
<td><p>: 진구 Myer</p></td>
<td><p>오후 7/7/2012 1:00</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>오후 7/7/2012 2:00</p></td>
</tr>
<tr class="odd">
<td><p>: 진구 Myer</p></td>
<td><p>오전 7/2/2012 10:00</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>오전 7/2/2012 10:00</p></td>
</tr>
</tbody>
</table>


회의를 구성한 고유 사용자의 총 수를 더 잘 이해 하려면 시간 간격을 변경 하세요. 예를 들어 일이 아닌 월별로 데이터를 봅니다.

</div>

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 예를 들어 회의 요약 보고서를 사용 하 여 데이터를 그룹화 하는 방법을 선택할 수 있습니다. 이 경우 시간, 일, 주 또는 월로 그룹화 된 컨퍼런스.

다음 표에는 회의 요약 보고서에 사용할 수 있는 필터가 나열 되어 있습니다.

### <a name="conference-summary-report-filters"></a>회의 요약 보고서 필터

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
<p>시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값의 수만 표시 됩니다. 예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>매트릭스

다음 표에는 회의 요약 보고서에서 제공 하는 정보가 나와 있습니다.

### <a name="conference-summary-report-metrics"></a>회의 요약 보고서 메트릭

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
<td><p>필터 도구 모음에서 선택한 시간 간격을 나타냅니다. 해당 되는 경우 지정 된 시간 간격을 클릭 하 여 해당 간격에 대 한 세부 정보를 볼 수 있습니다. 예를 들어 일일 기간을 사용 하는 경우 7/7/2012을 클릭 하면 해당 날짜에 대 한 사용자 등록 작업을 시간별로 분류 하 여 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 컨퍼런스</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화 회의 유형에 관계 없이 보유 한 총 컨퍼런스 수입니다. 이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 컨퍼런스 활동 보고서가 표시 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 참가자</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의에 참가 한 총 사용자의 수입니다. 이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 컨퍼런스 활동 보고서가 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>회의 당 평균 참가자 수</strong></p></td>
<td><p>아니요</p></td>
<td><p>지정 된 회의에 참여 한 평균 사용자 수입니다. 총 회의를 총 참가자로 나누어 결정 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 A/V 회의</strong></p></td>
<td><p>아니요</p></td>
<td><p>오디오 또는 비디오를 포함 한 총 컨퍼런스 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 A/V 회의 시간 (분)</strong></p></td>
<td><p>아니요</p></td>
<td><p>오디오/비디오 회의에 소요 된 총 시간 (분)입니다.</p>
<p>총 A/V 회의 시간 메트릭은 A/V 회의를 포함 하 여 모든 오디오/시각적 회의 유형을 요약 합니다. 메신저 대화 회의 앱 공유 회의 데이터 회의 및 PSTN 회의.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 A/V 회의 참가자 통화 시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>오디오/비디오 회의에 소요 된 총 참가자 통화 수입니다. 예를 들어 한 명의 사용자가 오디오/비디오 회의에서 5 분 정도 소요 되는 경우 두 번째 사용자는 같은 회의에서 3 분이 소요 됩니다. 이를 통해 총 8 분의 참가자가 5 분 + 3 분이 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>평균 A/V 회의 시간 (분)</strong></p></td>
<td><p>아니요</p></td>
<td><p>오디오/비디오 회의 당 평균 분 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>고유한 회의 이끌이의 총 수입니다.</strong></p></td>
<td><p>아니요</p></td>
<td><p>하나 이상의 회의를 구성한 총 사용자 수입니다. 두 개 이상의 회의를 구성한 사용자는 단일 컨퍼런스만 구성한 사용자와 같이 하나의 고유 이끌이로 간주 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 컨퍼런스 메시지</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의 중에 전송 된 총 인스턴트 메시지 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

