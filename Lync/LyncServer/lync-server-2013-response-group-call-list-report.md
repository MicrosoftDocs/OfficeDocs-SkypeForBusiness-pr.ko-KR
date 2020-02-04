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
ms.openlocfilehash: 94c06e2029ca1a22a0a9f73249cff3251e2fcbc2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a>Lync Server 2013의 응답 그룹 통화 목록 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-22_

응답 그룹 응용 프로그램은 Microsoft Lync Server 2013에서 전화를 걸고, 선택적으로 발신자의 질문에 대 한 회신에 대 한 응답 및 라우팅 방법을 제공 합니다. 일반적으로 응답 그룹 통화는 개인 사람에 게 라우팅되지 않지만, 대신 상담원 그룹 이라고 하는 사용자의 팀으로 라우팅됩니다. 예를 들어 사용자가 지원 센터 번호로 전화를 걸 경우 Lync Server 2013는 해당 통화를 사용 가능한 첫 번째 지원 센터 에이전트로 자동으로 라우팅할 수 있습니다. 또는 Lync Server가 일련의 질문을 할 수 있습니다 (하드웨어 문제가 있는 경우 1 번 누름). 소프트웨어 문제가 있는 경우 2를 누릅니다. 네트워크 문제가 발생 하는 경우 3을 누릅니다. ") 그런 다음 해당 질문에 대 한 답변을 기준으로 가장 적절 한 지원 센터 상담원에 게 통화를 전달 합니다.

응답 그룹 통화 목록 보고서는 지정 된 기간 및 지정 된 통화 유형에 대해 이루어진 통화 모음을 나타냅니다. 응답 그룹 통화 목록 보고서를 열기 전에 먼저 열려 있어야 하는 Response 그룹 사용 보고서에서 다음 통화 유형을 인식 합니다.

  - **전화 받음**. 응답 그룹 응용 프로그램의 모든 인스턴스에서 받은 총 통화 수입니다.

  - **통화 했습니다**. 응답 그룹 응용 프로그램이 선택한 총 통화 수입니다.

  - **제공**되는 통화. 응답 그룹 에이전트로 전송 된 총 통화 수입니다.

  - **통화 응답**. 응답 그룹 에이전트에서 실제로 응답 한 총 통화 수입니다.

  - 중단 된 통화의 백분율입니다. 응답 그룹 응용 프로그램에서 받았지만 에이전트에서 응답 하지 않은 통화의 백분율입니다. 이 값은 수신 전화에서 응답 한 전화를 뺀 다음 해당 값을 수신 된 통화 수로 나누는 방법으로 계산 됩니다. 예를 들어 10 개의 통화를 받고 7 개가 응답 한 경우에는 3 개의 응답 하지 않은 통화를 종료 하 고 10에서 7을 뺍니다. 이 값을 10으로 나누면 30%의 통화 백분율이 중단 됩니다.

  - **통화를 전송**했습니다. 큐 시간 제한 또는 큐 오버플로 때문에 전송 된 총 응답 그룹 통화 수입니다.

<div>

## <a name="accessing-the-response-group-call-list-report"></a>응답 그룹 통화 목록 보고서에 액세스

응답 그룹 통화 목록 보고서에는 [Lync Server 2013의 응답 그룹 사용 보고서](lync-server-2013-response-group-usage-report.md)에 있는 다음 메트릭 중 하나를 클릭 하 여 액세스할 수 있습니다.

  - 수신 전화

  - 성공한 통화

  - 제공 되는 통화

  - 응답 한 전화

  - 통화 전송

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>응답 그룹 통화 목록 보고서를 최대한 활용 하기

응답 그룹 통화 목록 보고서를 사용 하 여 표시 된 데이터를 특정 응답 그룹 워크플로를 포함 하는 통화로 제한할 수 있습니다. 이렇게 하려면 워크플로 uri 상자에 워크플로 URI (워크플로의 SIP 주소)를 입력 해야 합니다. 이 작업을 수행 하기 전에 실제로 워크플로 URI 상자를 볼 수 있어야 합니다. 응답 그룹 통화 목록 보고서에 대 한 필터링 옵션을 표시 하려면 보고서 창의 왼쪽 위 부분에 있는 매개 변수 표시/숨기기 단추를 클릭 합니다.

응답 그룹 통화 목록에는 해당 메트릭 중 하나 위에 마우스를 놓고 응답 코드 또는 진단 ID에 대 한 정보가 표시 되지 않는다는 점에 유의 하세요. 추가 정보가 필요한 경우 응답 코드 및/또는 진단 ID를 기록한 다음 [Lync Server 2013의 상위 오류 보고서](lync-server-2013-top-failures-report.md)에서 해당 값을 검색할 수 있습니다.

"이 문제가 발생 하는 개별 워크플로가 가장 많은 호출을 받음" 등의 질문은 다음과 같이 할 수 있습니다.

1.  응답 그룹 사용 현황 보고서에서 원하는 기간을 설정한 다음 받은 통화 메트릭을 클릭 합니다. 그러면 응답 그룹 통화 목록 보고서가 열립니다.

2.  응답 그룹 통화 목록 보고서에 표시 된 데이터를 내보냅니다. 예를 들어 Microsoft Excel 형식으로 데이터를 내보낸 다음 Excel을 사용 하 여 해당 데이터를 쉼표로 구분 된 값 파일로 변환할 수 있습니다.

3.  Windows PowerShell을 사용 하 여 분석을 실행 합니다.

예를 들어 데이터를\\C: 데이터\\응답\_그룹\_통화\_목록\_보고서 .csv로 저장 한 경우 다음 명령을 사용 하 여 보고서에 나열 된 각 워크플로에 대 한 총 수신 통화 수를 반환할 수 있습니다.

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

이 정보는 다음과 유사 합니다.

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 다음 표에는 응답 그룹 통화 목록 보고서와 함께 사용할 수 있는 필터가 나와 있습니다.

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
<td><p><strong>워크플로 URI</strong></p></td>
<td><p>반환 되는 데이터를 지정 된 응답 그룹 워크플로로 제한할 수 있습니다. 이 필터를 사용 하려면 워크플로 SIP 주소를 입력 합니다. 예를 들면 다음과 같습니다.</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><strong>전화가</strong></p></td>
<td><p>다음 통화 유형 중 하나를 선택할 수 있습니다.</p>
<ul>
<li><p>수신 전화</p></li>
<li><p>성공한 통화</p></li>
<li><p>제공 되는 통화</p></li>
<li><p>응답 한 전화</p></li>
<li><p>통화 전송</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>매트릭스

다음 표에는 응답 그룹 응용 프로그램이 받은 각 통화에 대 한 응답 그룹 통화 목록 보고서에 제공 되는 정보가 나열 되어 있습니다.

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
<th>이 항목을 정렬할 수 있나요?</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>호출인</strong></p></td>
<td><p>아니요</p></td>
<td><p>발신자의 SIP 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>워크플로입니다</strong></p></td>
<td><p>아니요</p></td>
<td><p>응답 그룹 워크플로의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>시작 시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화가 시작 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>종료 시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화가 종료 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>응답 코드</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션이 실패 했을 때 전송 된 SIP 응답 코드입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>진단 ID</strong></p></td>
<td><p>아니요</p></td>
<td><p>오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

