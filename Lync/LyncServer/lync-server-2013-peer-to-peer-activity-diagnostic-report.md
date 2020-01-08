---
title: 'Lync Server 2013: 피어 투 피어 작업 진단 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f435a4b0ff0ec42e8898260c3ada528963bbebb1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a>Lync Server 2013의 피어 투 피어 작업 진단 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

피어 투 피어 작업 진단 보고서는 피어 투 피어 통신 세션의 성공 및 실패에 대 한 정보를 제공 합니다. Microsoft Lync Server 2013는 서로 다른 종류의 오류를 구분 합니다.

  - **오류가 발생**했습니다. 일반적으로 예상 되는 오류는 대부분의 기술적인 측면 에서만 발생 합니다. 예를 들어 다른 사람에 게 전화를 걸 때, 사무실 밖에 서 전화를 받을 수 없는 경우 호출이 응답 되지 않았으므로 기술적으로는 오류로 간주 됩니다. 다른 한편으로는이 문제가 발생 했습니다. Microsoft Lync Server 2013는 휴대폰에 응답 하는 데 사용할 수 없는 경우 휴대폰에 응답 하지 않을 것으로 예상 합니다. 마찬가지로, 오프 라인 상태에 있는 사용자에 게 인스턴트 메시지를 보내거나 메신저를 지원 하지 않는 전화기로 로그온 한 경우에도 예상 되는 오류가 발생 합니다.

  - **예기치 않은 오류**. 예기치 않은 오류는 상황에 따라 발생 하는 것으로 예상 되지 않는 오류를 의미 합니다. 예를 들어 다른 사람에 게 전화를 걸고 해당 사용자가 전화를 받을 수 있습니다. 그러나 Lync Server 2013에서 음성 메일로 통화를 회람 하려고 하면 Exchange 통합 메시징의 연결이 끊어져서 호출에 실패 합니다. 예기치 않은 오류가 발생 했습니다 .이 통화는 항상 보이스 메일로 라우팅될 수 있습니다. 일반적으로 예기치 않은 오류가 발생 하는 경우에는 사용자 교육 이나 유사한 조치를 통해 해결할 수 없는 문제가 발생 합니다.

성공, 예상 실패, 예기치 않은 실패 메트릭이 총 세션 메트릭에 추가 되지 않을 수 있습니다. 예를 들어 앞의 그림에는 다음 값이 있습니다.


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


2024 + 469 + 16을 추가 하는 경우 총 2509 세션을 받을 수 있지만 총 세션 열에는 총 2521 세션이 표시 됩니다. "누락 된" 12 개 세션은 시스템에서 성공 또는 실패로 분류할 수 없는 세션입니다. 이는 타사 제품이 Lync Server에 익숙하지 않은 새로운 진단 코드를 도입 하는 경우에 해당 될 수 있습니다. 이 경우 해당 제품을 사용 하 여 호출 하 고 해당 진단 코드를 보고 하면 항상 성공, 실패 또는 예기치 않은 오류에 대 한 분류할 수 없습니다.

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>피어 투 피어 작업 진단 보고서에 액세스

피어 투 피어 진단 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다. 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 실패 배포 보고서](lync-server-2013-failure-distribution-report.md) 에 액세스할 수 있습니다.

  - 예기치 않은 오류 볼륨

  - 예상 고장 볼륨

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>피어 투 피어 작업 진단 보고서를 최대한 활용 하기

피어 투 피어 작업 진단 보고서를 필터링 하는 방법에는 여러 가지가 있지만 기본적으로 이러한 필터링 옵션은 보기에서 숨겨집니다. 사용할 수 있는 필터링 옵션을 보려면 보고서 창의 오른쪽 위 모서리에 있는 매개 변수 표시/숨기기 단추를 클릭 합니다. 이 작업을 수행 하면 필터링 옵션을 사용할 수 있습니다.

</div>

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 예를 들어 피어 투 피어 작업 진단 보고서를 사용 하 여 세션 형식 (예: 인스턴트 메시지, 파일 전송 또는 응용 프로그램 공유) 등의 항목을 필터링 할 수 있습니다. 데이터 그룹화 방법을 선택할 수도 있습니다. 이 경우 통화는 시, 일, 주 또는 월로 그룹화 됩니다.

다음 표에는 피어 투 피어 작업 진단 보고서에 사용할 수 있는 필터가 나와 있습니다.

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a>피어 투 피어 작업 진단 보고서 필터

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
<td><p><strong>모달</strong></p></td>
<td><p>발생 한 통신 활동 유형을 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>인스턴트 메시지</p></li>
<li><p>파일 전송</p></li>
<li><p>응용 프로그램 공유</p></li>
<li><p>오디오</p></li>
<li><p>비디오만</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a>메트릭 (각에 대 한 모달)

다음 표에는 각 모달 피어 투 피어 작업 진단 보고서에 제공 된 정보가 나열 되어 있습니다.

### <a name="metrics-per-modality"></a>메트릭 (각에 대 한 모달)

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
<td><p>성공한 피어 투 피어 세션의 총 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>성공 백분율</strong></p></td>
<td><p>아니요</p></td>
<td><p>중대 한 문제가 발생 하 여 완료 된 피어 투 피어 세션의 백분율입니다. 성공 볼륨을 총 세션으로 나누는 방법으로 계산 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>예상 고장 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>예상 되는 오류가 &quot;&quot; 발생 한 총 세션 수입니다.</p>
<p>예상 되는 실패는 예상 되는 오류입니다. 예를 들어 사용자가 자신의 상태를 방해 금지로 설정 하면 해당 사용자에 게 전화를 거는 데 실패 하는 것으로 예상 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>예상 되는 실패 백분율</strong></p></td>
<td><p>아니요</p></td>
<td><p>예상 되는 오류가 발생 한 피어 투 피어 세션의 백분율입니다. 예상 고장 볼륨을 총 세션으로 나누어 계산 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>예기치 않은 오류 볼륨</strong></p></td>
<td><p>아니요</p></td>
<td><p>예기치 않은 오류가 &quot;&quot; 발생 한 총 세션 수입니다.</p>
<p>예기치 않은 오류가 발생 하는 것은 정상적인 시스템 때문 이라고 표시 되는 오류입니다. 예를 들어 호출자가 대기 상태로 설정 된 경우에는 통화가 종료 되지 않습니다. 이 문제가 발생 하면 예기치 않은 오류로 플래그가 지정 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>예기치 않은 오류 백분율</strong></p></td>
<td><p>아니요</p></td>
<td><p>예기치 않은 오류가 발생 한 피어 투 피어 세션의 백분율입니다. 예상 하지 못한 볼륨을 총 세션으로 나누면 계산 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>성공한 세션, 실패 한 세션 (예상 되는 실패 및 예기치 못한 실패), 범주화 되지 않은 세션 등의 총 세션 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

