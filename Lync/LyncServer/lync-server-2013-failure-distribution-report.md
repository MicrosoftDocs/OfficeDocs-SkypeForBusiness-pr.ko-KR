---
title: 'Lync Server 2013: 실패 한 배포 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06481be824f6c51975431aeea2efe27e41eadabc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a>Lync Server 2013의 실패 한 배포 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-21_

실패 한 배포 보고서는 실패 한 세션의 순위를 다음 범주로 분류 합니다.

  - 주요 진단 이유

  - Top 형식을

  - 상위 풀

  - 상위 원본

  - 상위 구성 요소

  - 사용자의 상위

  - 상위 사용자

  - 사용자 에이전트의 상위

이러한 범주를 사용 하 여 문제가 발생 하는 위치와 문제가 발생 하는 경우를 정확 하 게 확인할 수 있습니다. 예를 들어 지정 된 날짜 동안 242 실패 한 오디오/비디오 세션을 기록 했다고 가정해 보세요. 실패 한 배포 보고서에 대 한 자세한 내용은 실패 한 세션의 237가 더블린 풀에 발생 한 것으로 표시 될 수 있습니다. 이를 통해 추적 하 고 해당 오류에 대 한 원인을 진단할 때 시작 하는 것이 좋습니다. **상위 풀** 범주 아래에 있는 더블린 풀을 클릭 하면 해당 풀에 대 한 실패 분포 보고서가 표시 됩니다. 그런 다음 더블린 풀이 많은 어려움을 겪고 있는 이유를 분석을 시작할 수 있습니다.

<div>

## <a name="viewing-the-failure-distribution-report"></a>실패 한 배포 보고서 보기

**예상 고장 볼륨** 또는 **예기치 않은 오류 볼륨** 메트릭 중 하나를 클릭 하 여 다음 보고서에서 실패 배포 보고서에 액세스할 수 있습니다.

  - [Lync Server 2013의 상위 오류 보고서](lync-server-2013-top-failures-report.md)

  - [Lync Server 2013의 컨퍼런스 진단 보고서](lync-server-2013-conference-diagnostic-report.md)

  - [Lync Server 2013의 피어 투 피어 작업 진단 보고서](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

실패 한 배포 보고서에서 다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013에서 실패 목록 보고서](lync-server-2013-failure-list-report.md)를 볼 수 있습니다.

  - 주요 진단 이유 (세션)

  - 최상위 형식을 (세션)

  - 상위 풀 (세션)

  - 상위 원본 (세션)

  - 상위 구성 요소 (세션)

  - 사용자 (세션)의 상위

  - 상위 사용자 (세션)

  - 사용자 에이전트 (세션)에서 맨 위로

</div>

<div>

## <a name="using-the-failure-distribution-report"></a>실패 한 배포 보고서 사용

모니터 크기와 화면 해상도에 따라 실패 배포 보고서에 표시 되는 일부 데이터가 화면에 표시 될 때 잘릴 수 있습니다. 이는 매우 긴 레이블을 포함할 수 있는 사용자 에이전트와 같은 메트릭의 경우 특히 그렇습니다. 예를 들어 "e: CAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)"와 같은 이름이 있는 사용자 에이전트는 화면에 부분적 으로만 나타날 것입니다.

S e u i CAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft와 ...

다행히 잘린 값을 마우스로 눌러 전체 레이블을 볼 수 있습니다.

실패 분포 보고서를 사용 하 여 필터링 할 수 있는 한 가지 흥미로운 메트릭은 진단 ID입니다. 다른 보고서에 동일한 진단 ID가 표시 되는 경우 실패 한 배포 보고서에서 해당 ID에 대해 필터링 할 수 있으며, 오류가 발생 한 세션 중에 해당 ID가 보고 되는 빈도에 대 한 자세한 내용을 확인 하세요.

</div>

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 예를 들어 실패 한 배포 보고서를 사용 하 여 활동 유형 (피어 투 피어 세션 또는 회의 세션) 또는 실패 한 각 세션과 함께 제공 되는 진단 ID를 기준으로 필터링 할 수 있습니다.

다음 표에는 실패 분포 보고서에 사용할 수 있는 필터가 나와 있습니다.

### <a name="failure-distribution-report-filters"></a>실패 한 배포 보고서 필터

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
<td><p><strong>풀</strong></p></td>
<td><p>등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다. 개별 풀을 선택 하거나 <strong>[모두]</strong> 를 클릭 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>활동 유형</strong></p></td>
<td><p>필터링 할 활동의 유형입니다. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>피어 투 피어</p></li>
<li><p>회의</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>세션 범주</strong></p></td>
<td><p>활동의 성공 또는 실패 여부를 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>시간당</p></li>
<li><p>예상 실패</p></li>
<li><p>예기치 않은 오류</p></li>
</ul>
<p>&quot;예상 되는&quot; 실패는 예상 되는 오류입니다. 예를 들어 사용자가 자신의 상태를 방해 금지로 설정 하면 해당 사용자에 게 전화를 거는 데 실패 하는 것으로 예상 됩니다. &quot;예기치 않은 오류가&quot; 발생 하는 것은 정상적인 시스템 때문 이라고 표시 되는 오류입니다. 예를 들어 호출자가 대기 상태로 설정 된 경우에는 통화가 종료 되지 않습니다. 이 문제가 발생 하면 예기치 않은 오류로 플래그가 지정 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>진단 ID</strong></p></td>
<td><p>오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다. 진단 헤더는 선택 사항으로,이 헤더를 포함 하지 않는 SIP 세션이 있을 수 있으며, 진단 Id는 일부 종류의 문제가 발생 하는 세션에 대해서만 보고 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a>주요 진단 이유에 대 한 메트릭

다음 표에는 가장 자주 보고 되는 진단 ID를 기준으로 실패 배포 보고서에 제공 되는 정보가 나열 되어 있습니다.

### <a name="metrics-for-top-diagnostic-reasons"></a>주요 진단 이유에 대 한 메트릭

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
<td><p><strong>순위</strong></p></td>
<td><p>아니요</p></td>
<td><p>진단 Id를 기준으로 실패 한 세션의 상대 순위입니다. 진단 ID는 오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 연결 된 고유 식별자 (ms-진단 헤더 형식)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>주요 진단 이유</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션에서 생성 된 진단 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>지정 된 진단 ID가 생성 된 총 실패 한 세션 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a>Top 형식을에 대 한 메트릭

다음 표에서는 실패 배포 보고서에 제공 되는 정보를 가장 많이 발생 하는 세션 형식을에 따라 나열 합니다.

### <a name="metrics-for-top-modalities"></a>Top 형식을에 대 한 메트릭

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
<td><p><strong>순위</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션 유형에 따라 실패 한 세션 (예: 오디오/비디오 컨퍼런스 또는 피어 투 피어 파일 전송 세션)을 기준으로 상대 순위를 지정 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Top 형식을</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션 유형입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>지정 된 모달을 포함 하는 실패 한 총 세션 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a>최상위 풀에 대 한 메트릭

다음 표에서는 오류가 발생 한 배포 보고서에 제공 되는 정보를 가장 많이 발생 한 풀에 기반 하 여 보여 줍니다.

### <a name="metrics-for-top-pools"></a>최상위 풀에 대 한 메트릭

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
<td><p><strong>순위</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션이 수행 된 등록자 풀이나 Edge 서버를 기반으로 하는 실패 한 세션의 상대 순위입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>상위 풀</strong></p></td>
<td><p>아니요</p></td>
<td><p>등록자 풀 또는 Edge 서버의 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>등록자 풀 또는 Edge 서버 당 실패 한 총 세션 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a>상위 원본에 대 한 메트릭

다음 표에서는 실패 한 배포 보고서에서 발생 하는 대부분의 오류가 발생 한 컴퓨터를 기준으로 제공 되는 정보를 보여 줍니다.

### <a name="metrics-for-top-sources"></a>상위 원본에 대 한 메트릭

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
<td><p><strong>순위</strong></p></td>
<td><p>아니요</p></td>
<td><p>컴퓨터당 상대적인 순위 지정 실패 한 세션</p></td>
</tr>
<tr class="even">
<td><p><strong>상위 원본</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 세션과 관련 된 컴퓨터의 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>컴퓨터당 총 failed sessions 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a>최상위 구성 요소에 대 한 메트릭

다음 표에는 대부분의 오류가 발생 한 Microsoft Lync Server 2010 구성 요소를 기반으로 실패 배포 보고서에 제공 되는 정보가 나열 되어 있습니다.

### <a name="metrics-for-top-components"></a>최상위 구성 요소에 대 한 메트릭

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
<td><p><strong>순위</strong></p></td>
<td><p>아니요</p></td>
<td><p>Lync Server 2010 구성 요소 (예: ExumRouting, GroupChat 또는 MediationServer)를 기반으로 하는 실패 한 세션의 상대 순위입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>상위 구성 요소</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 세션과 관련 된 구성 요소의 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>구성 요소 당 실패 한 세션의 총 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a>사용자의 상위에 대 한 메트릭

다음 표에는 다른 사용자에 게 전화를 거는 경우 ("보낸 사람" 사용자)를 사용 하 여 발생 하는 대부분의 경우 오류 배포 보고서에 제공 되는 정보가 나열 되어 있습니다.

### <a name="metrics-for-top-from-users"></a>사용자의 상위에 대 한 메트릭

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
<td><p><strong>순위</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션에 참가 하도록 초대 된 사용자에 따라 실패 한 세션의 상대 순위입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>사용자의 상위</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션에 참가 하도록 초대 받은 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>사용자 당 실패 한 세션의 총 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a>상위 사용자에 대 한 메트릭

다음 표에는 다른 사용자가 전화를 거는 경우 ("받는 사람" 사용자)를 사용 하 여 오류가 발생 한 사용자를 기준으로 실패 배포 보고서에 제공 되는 정보가 나열 되어 있습니다.


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
<td><p><strong>순위</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션을 시작한 사용자에 따라 실패 한 세션의 상대 순위입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>상위 사용자</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션을 시작한 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>사용자 당 실패 한 세션의 총 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a>상위 사용자 에이전트에 대 한 메트릭

다음 표에는 오류가 발생 한 끝점 소프트웨어에 따라 실패 배포 보고서에 제공 되는 정보가 나열 되어 있습니다.

### <a name="metrics-for-top-user-agents"></a>상위 사용자 에이전트에 대 한 메트릭

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
<td><p><strong>순위</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션과 관련 된 사용자 에이전트 (소프트웨어)를 기반으로 하는 실패 한 세션의 상대 순위입니다. 예: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</p></td>
</tr>
<tr class="even">
<td><p><strong>상위 사용자 에이전트</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 세션과 관련 된 사용자 에이전트의 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>사용자 에이전트 당 실패 한 총 세션 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

