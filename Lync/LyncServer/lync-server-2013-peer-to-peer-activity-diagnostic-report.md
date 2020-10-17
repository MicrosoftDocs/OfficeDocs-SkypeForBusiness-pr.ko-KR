---
title: 'Lync Server 2013: 피어 투 피어 활동 진단 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53e47232a6345749f78f6136929209722a83621e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524395"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a>Lync Server 2013의 피어 투 피어 활동 진단 보고서

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

피어 투 피어 활동 진단 보고서는 피어 투 피어 통신 세션의 성공 및 실패에 대한 정보를 제공합니다. Microsoft Lync Server 2013는 서로 다른 종류의 오류를 구분 합니다.

  - **예상 오류**입니다. 일반적으로 예상 되는 오류는 가장 기술적으로 발생 하는 오류에 불과합니다. 예를 들어 상대방에 게 전화를 걸고 전화를 받을 수 없는 경우를 가정해 보겠습니다. 통화가 응답 하지 않았으므로 기술적으로는 오류가 발생 하는 것으로 간주 됩니다. 반면에, Microsoft Lync Server 2013에서는 휴대폰에 응답할 수 없는 경우 휴대폰에 응답 하지 않을 것으로 예상 하 고 있습니다. 마찬가지로, 오프 라인 상태에 있는 사용자에 게 인스턴트 메시지를 보내거나 인스턴트 메시징을 지원 하지 않는 전화로 로그온 한 경우에도 예상 되는 오류가 발생 합니다.

  - **예기치 않은 오류**입니다. 예기치 않은 오류는 해당 상황에 따라 발생할 것으로 예상 되는 오류를 의미 합니다. 예를 들어 다른 사람에 게 전화를 걸고 해당 사용자가 통화에 응답할 수 있다고 가정 합니다. 그러나 Lync Server 2013에서 음성 메일로 통화를 라우팅하 려는 경우 Exchange 통합 메시징에 대 한 연결이 끊어져서 호출이 실패 합니다. 예기치 않은 오류입니다. 전화가 음성 메일로 라우팅될 수 있습니다. 일반적으로 오류가 발생 하는 경우는 예기치 않은 오류 이며, 사용자 교육 이나 유사한 조치를 통해 해결할 수 없는 문제입니다.

성공, 예상 오류 및 예기치 않은 오류 메트릭은 총 세션 메트릭에 추가되지 않을 수 있습니다. 예를 들어 위 그림에는 다음과 같은 값이 있습니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>성공</th>
<th>예상 오류</th>
<th>예기치 않은 오류</th>
<th>총 세션</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2024</p></td>
<td><p>469</p></td>
<td><p>16 </p></td>
<td><p>2521</p></td>
</tr>
</tbody>
</table>


이 경우 2024+469+16=총 세션 수는 2,509개가 되지만 총 세션 열에는 총 세션 수가 2,521개로 표시됩니다. "누락된" 12개 세션은 시스템에서 성공 또는 실패로 분류하지 못한 세션입니다. 타사 제품에서 Lync Server에 익숙하지 않은 새로운 진단 코드를 도입 하는 경우가 있습니다. 이와 같은 경우 해당 제품을 사용하여 전화를 걸고 해당 진단 코드를 보고하는 경우를 항상 성공, 예상 오류 또는 예기치 않은 오류로 분류할 수 있는 것은 아닙니다.

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>피어 투 피어 활동 진단 보고서 액세스

피어 투 피어 진단 보고서는 모니터링 보고서 홈 페이지에서 액세스합니다. 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 실패 분포 보고서](lync-server-2013-failure-distribution-report.md) 에 액세스할 수 있습니다.

  - 예기치 않은 오류량

  - 예상 오류량

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>피어 투 피어 활동 진단 보고서를 가장 효율적으로 활용

다양한 방법으로 피어 투 피어 활동 진단 보고서를 필터링할 수 있지만, 기본적으로 이러한 필터링 옵션은 보기에서 숨겨집니다. 사용 가능한 필터링 옵션을 보려면 보고서 창 오른쪽 위의 매개 변수 표시/숨기기 단추를 클릭합니다. 그러면 필터링 옵션을 사용할 수 있게 됩니다.

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 피어 투 피어 활동 진단 보고서를 통해 세션 형식(예: 인스턴트 메시징, 파일 전송 또는 응용 프로그램 공유)과 같은 항목으로 필터링할 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 통화는 시간, 일, 주 및 월별로 그룹이 지정됩니다.

다음 표에서는 피어 투 피어 활동 진단 보고서에 사용할 수 있는 필터를 보여 줍니다.

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a>피어 투 피어 활동 진단 보고서 필터

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
<tr class="even">
<td><p><strong>풀</strong></p></td>
<td><p>등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>형식</strong></p></td>
<td><p>발생한 통신 활동의 유형을 나타냅니다. 다음 중 하나를 선택합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>인스턴트 메시징</p></li>
<li><p>파일 전송</p></li>
<li><p>응용 프로그램 공유</p></li>
<li><p>오디오만</p></li>
<li><p>비디오</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a>메트릭(형식별)

다음 표에서는 각 형식에 대해 피어 투 피어 활동 진단 보고서에 제공되는 정보를 보여 줍니다.

### <a name="metrics-per-modality"></a>메트릭(형식별)

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
<td><p><strong>성공량</strong></p></td>
<td><p>아니요</p></td>
<td><p>성공한 총 피어 투 피어 세션 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>성공 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>중요 문제와 함께 완료된 피어 투 피어 세션의 비율입니다. 성공량을 총 세션으로 나눠서 계산됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>예상 오류량</strong></p></td>
<td><p>아니요</p></td>
<td><p>예상 오류가 발생 한 총 세션 수 &quot; &quot; 입니다.</p>
<p>예상 오류는 발생할 것으로 예상된 오류입니다. 예를 들어 사용자가 자신의 상태를 방해 금지로 설정한 경우 해당 사용자에 대한 통화가 실패할 것으로 예상할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>예상 오류 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>예상 오류가 발생한 피어 투 피어 세션의 비율입니다. 예상 오류량을 총 세션으로 나눠서 계산됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>예기치 않은 오류량</strong></p></td>
<td><p>아니요</p></td>
<td><p>&quot;예기치 않은 오류가 발생 한 총 세션 수 &quot; 입니다.</p>
<p>예기치 않은 오류는 일반적으로 정상 상태의 시스템으로 보이지만 예기치 않게 발생한 오류입니다. 예를 들어 발신자가 보류 상태일 때는 통화가 종료되지 않아야 합니다. 하지만 통화가 종료되면 바로 예기치 않은 오류로 플래그 지정됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>예기치 않은 오류 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>예기치 않은 오류가 발생한 피어 투 피어 세션의 비율입니다. 예기치 않은 오류량을 총 세션으로 나눠서 계산됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>성공한 세션, 실패한 세션(예상 오류 및 예기치 않은 오류 모두) 및 분류되지 않은 세션을 포함한 총 세션 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

