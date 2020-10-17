---
title: 'Lync Server 2013: 응답 그룹 통화 목록 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abb3a1b13bf7357a0a2ee31180557911fc37ae0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511765"
---
# <a name="response-group-call-list-report-in-lync-server-2013"></a>Lync Server 2013의 응답 그룹 통화 목록 보고서

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-22_

응답 그룹 응용 프로그램을 사용 하면 Microsoft Lync Server 2013에서 전화를 건 번호를 기반으로 통화에 응답 하 고 경로를 지정할 수 있으며, 선택적으로 발신자의 질문에 대 한 응답을 얻을 수 있습니다. 일반적으로 응답 그룹 통화는 개별 사람에 게 라우팅되지 않고 대신 에이전트 그룹 이라고 하는 사용자의 팀으로 라우팅됩니다. 예를 들어 사용자가 지원 센터 번호로 전화를 걸 경우 Lync Server 2013는 해당 통화를 처음 사용할 수 있는 지원 센터 에이전트로 자동으로 라우팅할 수 있습니다. 또는 Lync Server에서 일련의 질문을 할 수 있습니다 (하드웨어 문제가 있는 경우 1 번 누름). 소프트웨어 문제가 있는 경우 2를 누릅니다. 네트워크에 문제가 있는 경우 3을 누릅니다. ") 를 선택한 다음 해당 질문에 대 한 답변에 따라 가장 적합 한 지원 센터 에이전트로 통화를 라우팅합니다.

응답 그룹 통화 목록 보고서는 지정된 기간 및 지정된 통화 유형의 통화 컬렉션을 나타냅니다. 응답 그룹 통화 목록 보고서를 열기 위해 먼저 열어야 하는 응답 그룹 사용 보고서에서는 다음과 같은 통화 유형을 인식합니다.

  - **받은 통화**. 응답 그룹 응용 프로그램의 모든 인스턴스에서 수신된 총 통화 수입니다.

  - **성공한 통화**. 응답 그룹 응용 프로그램에 의해 선택 된 총 호출 수입니다.

  - **제공된 통화**. 응답 그룹 에이전트로 전송된 총 통화 수입니다.

  - **응답한 통화**. 응답 그룹 에이전트가 실제로 받은 총 통화 수입니다.

  - 중단된 통화 비율. 응답 그룹 응용 프로그램에서 수신되었지만 에이전트가 받지 않은 통화의 비율입니다. 이 값은 수신된 통화에서 응답한 통화를 빼고 이 값을 수신된 통화 수로 나눠서 계산됩니다. 예를 들어 수신된 통화가 10건이고 응답한 통화가 7건인 경우 10에서 7을 빼면 응답하지 않은 통화는 3건이 됩니다. 이 값을 다시 10으로 나누면 중단된 통화 비율이 30%로 계산됩니다.

  - **전송된 통화**. 큐 시간 초과 또는 큐 오버플로로 인해 전송된 총 응답 그룹 통화 수입니다.

<div>

## <a name="accessing-the-response-group-call-list-report"></a>응답 그룹 통화 목록 보고서 액세스

응답 그룹 통화 목록 보고서는 [Lync Server 2013의 응답 그룹 사용 보고서](lync-server-2013-response-group-usage-report.md)에 있는 다음 메트릭 중 하나를 클릭 하는 방법 으로만 액세스할 수 있습니다.

  - 받은 통화

  - 성공한 통화

  - 제공된 통화

  - 응답한 통화

  - 전송된 통화

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>응답 그룹 통화 목록 보고서의 효과적인 활용

응답 그룹 통화 목록 보고서를 사용하면 표시되는 데이터를 특정 응답 그룹 워크플로를 사용하는 통화로 제한할 수 있습니다. 이를 위해 워크플로 URI 상자에 워크플로 URI(워크플로의 SIP 주소)를 입력해야 합니다. 그러나 이렇게 하려면 실제로 워크플로 URI가 표시되어 있어야 합니다. 응답 그룹 통화 목록 보고서에 대한 필터링 옵션을 표시하려면 보고서 창 왼쪽 윗부분에 있는 매개 변수 표시/숨기기 단추를 클릭합니다.

응답 그룹 통화 목록에서는 응답 코드 또는 진단 ID 위에 마우스를 놓아도 이러한 메트릭에 대한 정보가 표시되지 않습니다. 추가 정보가 필요한 경우 응답 코드 및/또는 진단 ID를 기록한 다음 [Lync Server 2013의 상위 오류 보고서](lync-server-2013-top-failures-report.md)에서 해당 값을 검색할 수 있습니다.

"어떤 개별 워크플로에서 가장 많은 통화를 받았는가?"와 같은 질문에 대한 답을 확인하려면 다음과 같이 하면 됩니다.

1.  응답 그룹 사용 보고서에서 원하는 기간을 설정한 후 받은 통화 메트릭을 클릭합니다. 그러면 응답 그룹 통화 목록 보고서가 열립니다.

2.  응답 그룹 통화 목록 보고서에 표시되는 데이터를 내보냅니다. 예를 들어 데이터를 Microsoft Excel 형식으로 내보낸 후에 Excel을 사용하여 해당 데이터를 쉼표로 구분된 값 파일로 변환할 수 있습니다.

3.  Windows PowerShell을 사용하여 분석을 실행합니다.

예를 들어 데이터를 C: \\ 데이터 \\ 응답 그룹 통화 목록Report.csv에 저장 한 경우 \_ \_ \_ \_ 다음 명령을 사용 하 여 보고서에 나열 된 각 워크플로의 수신 된 총 통화 수를 반환할 수 있습니다.

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

다음과 같은 정보가 표시됩니다.

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에서는 응답 그룹 통화 목록 보고서에서 사용할 수 있는 필터를 보여 줍니다.

### <a name="response-group-call-list-report-filters"></a>응답 그룹 통화 목록 보고서 필터

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
<td><p><strong>워크플로 URI</strong></p></td>
<td><p>반환되는 데이터를 지정된 응답 그룹 워크플로로 제한할 수 있습니다. 이 필터를 사용하려면 워크플로 SIP 주소를 입력합니다. 예:</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><strong>착신</strong></p></td>
<td><p>다음 통화 유형 중 하나를 선택할 수 있습니다.</p>
<ul>
<li><p>받은 통화</p></li>
<li><p>성공한 통화</p></li>
<li><p>제공된 통화</p></li>
<li><p>응답한 통화</p></li>
<li><p>전송된 통화</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>메트릭

다음 표에서는 응답 그룹 응용 프로그램에서 수신된 각 통화에 대해 응답 그룹 통화 목록 보고서에 제공된 정보를 보여 줍니다.

### <a name="response-group-call-list-report-metrics"></a>응답 그룹 통화 목록 보고서 메트릭

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
<td><p><strong>최초</strong></p></td>
<td><p>아니요</p></td>
<td><p>발신자의 SIP 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>워크플로</strong></p></td>
<td><p>아니요</p></td>
<td><p>응답 그룹 워크플로의 SIP 주소입니다</p></td>
</tr>
<tr class="odd">
<td><p><strong>시작 시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화가 시작된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>종료 시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화가 종료된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>응답 코드</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션이 실패했을 때 전송된 SIP 응답 코드입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>진단 ID</strong></p></td>
<td><p>아니요</p></td>
<td><p>오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

