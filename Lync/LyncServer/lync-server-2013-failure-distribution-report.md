---
title: 'Lync Server 2013: 실패 분포 보고서'
description: 'Lync Server 2013: 실패 분포 보고서입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5a87f779f87d6b7002fa108f1969c33739eed9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564734"
---
# <a name="failure-distribution-report-in-lync-server-2013"></a>Lync Server 2013의 실패 분포 보고서

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-21_

실패 분포 보고서에서는 다음 범주의 실패한 세션 순위가 표시됩니다.

  - 상위 진단 이유

  - 상위 형식

  - 상위 풀

  - 상위 원본

  - 상위 구성 요소

  - 상위 출처 사용자

  - 상위 대상 사용자

  - 상위 출처 사용자 에이전트

이러한 범주를 사용하여 문제가 발생하는 정확한 위치를 확인할 수 있으며 경우에 따라서는 문제 발생 이유도 파악할 수 있습니다. 예를 들어 지정된 날에 실패한 오디오/비디오 세션 242개가 기록되었다고 가정하겠습니다. 실패 분포 보고서에는 이와 같은 실패한 세션 중 237개가 Dublin 풀에서 진행되었다고 표시될 수 있습니다. 이 경우 실패의 원인을 어디서부터 추적 및 진단할지를 쉽게 파악할 수 있습니다. **상위 풀** 범주에서 Dublin 풀을 클릭하면 해당 풀과 관련된 정보만 표시되는 실패 분포 보고서를 볼 수 있습니다. 그러면 Dublin 풀에서 오류가 많이 발생하는 이유 분석을 시작할 수 있습니다.

<div>

## <a name="viewing-the-failure-distribution-report"></a>실패 분포 보고서 보기

**예상 오류량** 또는 **예기치 않은 오류량** 메트릭을 클릭하여 다음 보고서 중 하나에서 실패 분포 보고서에 액세스할 수 있습니다.

  - [Lync Server 2013의 상위 실패 보고서](lync-server-2013-top-failures-report.md)

  - [Lync Server 2013의 전화 회의 진단 보고서](lync-server-2013-conference-diagnostic-report.md)

  - [Lync Server 2013의 피어 투 피어 활동 진단 보고서](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

실패 분포 보고서에서 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013에서 실패 목록 보고서](lync-server-2013-failure-list-report.md)를 볼 수 있습니다.

  - 상위 진단 이유(세션)

  - 상위 형식(세션)

  - 상위 풀(세션)

  - 상위 원본(세션)

  - 상위 구성 요소(세션)

  - 상위 출처 사용자(세션)

  - 상위 대상 사용자(세션)

  - 상위 출처 사용자 에이전트(세션)

</div>

<div>

## <a name="using-the-failure-distribution-report"></a>실패 분포 보고서 사용

모니터 크기 및 화면 해상도에 따라 실패 분포 보고서를 화면에서 볼 때 보고서에 표시되는 일부 데이터가 잘릴 수 있습니다. 사용자 에이전트 등 레이블이 매우 긴 메트릭의 경우는 특히 데이터가 잘릴 가능성이 높습니다. 예를 들어 이름이 "UCCAPI/4.0.7400.0 OC/4.0.7400.0(Microsoft Lync 2013)"인 사용자 에이전트의 경우 화면에 다음과 같이 일부분만 표시될 수 있습니다.

UCCAPI/4.0.7400.0 OC/4.0.7400.0(Microsoft Ly...

이 경우 잘린 값 위에 마우스를 놓기만 하면 전체 레이블을 볼 수 있습니다.

실패 분포 보고서를 사용하여 필터링할 수 있는 메트릭 중 주목할 만한 항목은 진단 ID입니다. 같은 진단 ID가 다른 보고서에도 나타나는 경우 실패 분포 보고서에서 해당 ID를 필터링하면 실패한 세션 중에 해당 ID가 보고된 정확한 위치 및 빈도를 매우 상세하게 확인할 수 있습니다.

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 오류 분포 보고서를 사용하면 활동 유형(피어 투 피어 세션 또는 회의 세션)과 같은 항목 또는 각 실패한 세션에 수반되는 진단 ID에 따라 필터링을 수행할 수 있습니다.

다음 표에서는 오류 분포 보고서에 사용할 수 있는 필터를 보여 줍니다.

### <a name="failure-distribution-report-filters"></a>오류 분포 보고서 필터

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
<td><p><strong>풀</strong></p></td>
<td><p>등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>활동 유형</strong></p></td>
<td><p>필터링할 활동 유형입니다. 다음 중 하나를 선택합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>피어-투-피어</p></li>
<li><p>회의</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>세션 범주</strong></p></td>
<td><p>문제가 있는 활동이 성공 또는 실패했는지를 나타냅니다. 다음 중 하나를 선택합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>Success</p></li>
<li><p>예상 오류</p></li>
<li><p>예기치 않은 오류</p></li>
</ul>
<p>예상 되는 실패는 발생할 것으로 예상 되는 &quot; &quot; 오류입니다. 예를 들어 사용자가 자신의 상태를 방해 금지로 설정한 경우 해당 사용자에 대한 통화가 실패할 것으로 예상할 수 있습니다. 예기치 않은 오류가 발생 하는 것 &quot; &quot; 은 정상적인 시스템이 아닌 것 처럼 보이는 오류입니다. 예를 들어 발신자가 보류 상태일 때는 통화가 종료되지 않아야 합니다. 하지만 통화가 종료되면 바로 예기치 않은 오류로 플래그 지정됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>진단 ID</strong></p></td>
<td><p>오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다. 진단 헤더는 선택 사항이며(이러한 헤더를 포함하지 않는 SIP 세션도 가능함) 진단 ID는 일부 유형의 문제가 발생한 세션에 대해서만 보고됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a>상위 진단 이유에 대한 메트릭

다음 표에서는 가장 자주 보고되는 진단 ID에 따라 오류 분포 보고서에 제공된 정보를 보여 줍니다.

### <a name="metrics-for-top-diagnostic-reasons"></a>상위 진단 이유에 대한 메트릭

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
<td><p><strong>오름차순</strong></p></td>
<td><p>아니요</p></td>
<td><p>진단 ID에 따른 실패한 세션의 상대적 순위입니다. 진단 ID는 오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>상위 진단 이유</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션에서 생성된 진단 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>지정된 진단 ID가 생성된 실패한 총 세션 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a>상위 형식에 대한 메트릭

다음 표에서는 대부분의 오류가 발생한 세션 형식에 따라 오류 분포 보고서에 제공된 정보를 보여 줍니다.

### <a name="metrics-for-top-modalities"></a>상위 형식에 대한 메트릭

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
<td><p><strong>오름차순</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션 유형을 기반으로 하는 실패한 세션의 상대적 순위입니다(예: 오디오/비디오 회의 또는 피어 투 피어 파일 전송 세션).</p></td>
</tr>
<tr class="even">
<td><p><strong>상위 형식</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션 유형</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>지정된 형식을 포함하는 실패한 총 세션 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a>상위 풀에 대한 메트릭

다음 표에서는 대부분의 오류가 발생한 풀에 따라 오류 분포 보고서에 제공된 정보를 보여 줍니다.

### <a name="metrics-for-top-pools"></a>상위 풀에 대한 메트릭

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
<td><p><strong>오름차순</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션이 수행 된 등록자 풀 또는에 지 서버를 기반으로 하는 실패 한 세션의 상대적 순위입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>상위 풀</strong></p></td>
<td><p>아니요</p></td>
<td><p>등록자 풀 또는에 지 서버의 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>등록자 풀 또는에 지 서버 당 실패 한 총 세션 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a>상위 원본에 대한 메트릭

다음 표에서는 대부분의 오류가 발생한 컴퓨터에 따라 오류 분포 보고서에 제공된 정보를 보여 줍니다.

### <a name="metrics-for-top-sources"></a>상위 원본에 대한 메트릭

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
<td><p><strong>오름차순</strong></p></td>
<td><p>아니요</p></td>
<td><p>컴퓨터당 실패한 세션의 상대적 순위입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>상위 원본</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패한 세션에 관련된 컴퓨터 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>컴퓨터당 실패한 총 세션 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a>상위 구성 요소에 대한 메트릭

다음 표에서는 대부분의 오류가 발생 한 Microsoft Lync Server 2010 구성 요소를 기반으로 오류 분포 보고서에 제공 된 정보를 보여 줍니다.

### <a name="metrics-for-top-components"></a>상위 구성 요소에 대한 메트릭

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
<td><p><strong>오름차순</strong></p></td>
<td><p>아니요</p></td>
<td><p>Lync Server 2010 구성 요소를 기반으로 하는 실패 한 세션의 상대적 순위입니다 (예: ExumRouting, GroupChat 또는 MediationServer).</p></td>
</tr>
<tr class="even">
<td><p><strong>상위 구성 요소</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패한 세션에 관련된 구성 요소 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>구성 요소당 실패한 총 세션 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a>상위 출처 사용자에 대한 메트릭

다음 표에서는 다른 사용자에 대한 통화를 시도할 때 대부분의 오류가 발생한 사용자("시작" 사용자)를 기반으로 오류 분포 보고서에 제공된 정보를 보여 줍니다.

### <a name="metrics-for-top-from-users"></a>상위 출처 사용자에 대한 메트릭

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
<td><p><strong>오름차순</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션에 참가하도록 초대된 사용자를 기반으로 하는 실패한 세션의 상대적 순위입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>상위 출처 사용자</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션에 참가하도록 초대된 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>사용자당 실패한 총 세션 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a>상위 대상 사용자에 대한 메트릭

다음 표에서는 다른 사용자의 통화 시도 시에 대부분의 오류가 발생한 사용자("대상" 사용자)를 기반으로 오류 분포 보고서에 제공된 정보를 보여 줍니다.


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
<td><p><strong>오름차순</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션을 시작한 사용자를 기반으로 하는 실패한 세션의 상대적 순위입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>상위 대상 사용자</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션을 시작한 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>사용자당 실패한 총 세션 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a>최상위 사용자 에이전트에 대한 메트릭

다음 표에서는 대부분의 오류가 발생한 끝점 소프트웨어에 따라 오류 분포 보고서에 제공된 정보를 보여 줍니다.

### <a name="metrics-for-top-user-agents"></a>최상위 사용자 에이전트에 대한 메트릭

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
<td><p><strong>오름차순</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션에 관련된 사용자 에이전트(소프트웨어)를 기반으로 하는 실패한 세션의 상대적 순위입니다. 예: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</p></td>
</tr>
<tr class="even">
<td><p><strong>최상위 사용자 에이전트</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패한 세션에 관련된 사용자 에이전트의 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>사용자 에이전트당 실패한 총 세션 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

