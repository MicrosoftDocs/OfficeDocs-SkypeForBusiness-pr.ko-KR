---
title: 'Lync Server 2013: 주요 오류 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a62dce5d074b19c2bc8958715ced61bb54a4c8e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a>Lync Server 2013의 상위 오류 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

상위 오류 보고서에서는 가장 일반적으로 보고 되는 오류와 시간에 따른 추세를 살펴봅니다. 실패는 다음 두 메트릭의 조합에 기반 합니다.

  - **진단 ID**입니다. SIP 메시지에 첨부 되는 고유 식별자 (ms-진단 헤더 형식)입니다. 진단 Id는 통화 관련 문제를 해결 하는 데 유용한 정보를 제공 합니다.

  - **응답 코드**. 응답 코드는 sip 통신 세션에서 SIP 요청에 응답 하는 데 사용 됩니다. 예를 들어: 진구에서 Pilar Ackerman로 초대 요청을 보내는 경우 (즉,: 진구 Myer 호출 Pilar Ackerman가 있다고 가정 합니다.) Pilar 경우 휴대폰에서 응답 코드 200 (OK)를 보내: 진구 님이 Pilar에 게 응답 했음을 알립니다. 상위 오류 보고서에는 호출 실패에 대 한 응답으로 보낸 응답 코드만 포함 됩니다. Lync Server는 통화 도중에 발급 된 모든 응답 코드를 추적 하지 않습니다.

이러한 정보는 오류가 발생 한 총 세션 수에 대해서는 보고 되지 않으며, 실패의 영향을 받은 총 사용자의 수에도 해당 됩니다.

<div>

## <a name="accessing-the-top-failures-report"></a>상위 오류 보고서에 액세스

상위 오류 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다. 보고 된 세션 메트릭을 클릭 하면 [Lync Server 2013의 실패 분포 보고서](lync-server-2013-failure-distribution-report.md)로 이동 합니다.

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a>상위 오류 보고서를 최대한 활용 하기

상위 오류 보고서는 매우 중요 한 것으로, 한 번에 최대 5 개의 진단 Id를 필터링 할 수 있습니다. (일반적으로 한 번에 하나의 사용자 SIP 주소와 같이 한 항목 에서만 필터링 할 수 있습니다.) 여러 진단 Id를 필터링 하려면 각 ID를 쉼표로 구분 하 여 진단 Id 상자에 입력 하면 됩니다. (원하는 경우 각 쉼표 뒤에 공백을 남길 수 있습니다.) 예를 들어:

1011, 2412, 1033, 52116, 1008

이 작업을 수행 하면 해당 다섯 가지 진단 Id 중 하나 이상을 보고 한 실패 한 호출만 표시 됩니다.

마우스를 응답 코드 위에 두면 질문에 대 한 응답 코드의 의미를 알려 주는 도구 설명이 표시 됩니다. 예를 들어 응답 코드 486 위에 마우스를 놓으면 다음 메시지가 표시 됩니다.

여기에서 통화 중입니다.

</div>

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 예를 들어 상위 오류 보고서를 사용 하 여 반환 된 데이터를 활동 유형 (피어 투 피어 세션 또는 회의 세션) 또는 실패 한 세션과 함께 제공 되는 SIP 응답 코드에 따라 필터링 할 수 있습니다. 데이터 그룹화 방법을 선택할 수도 있습니다. 이 경우 사용량은 시간, 일, 주 또는 월로 그룹화 됩니다.

다음 표에는 상위 오류 보고서에 사용할 수 있는 필터가 나열 되어 있습니다.

### <a name="top-failures-report-filters"></a>상위 오류 보고서 필터

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
<td><p><strong>활동 유형</strong></p></td>
<td><p>활동의 유형입니다. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>피어 투 피어</p></li>
<li><p>회의</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>모달</strong></p></td>
<td><p>이번에는 <strong>[All]</strong>옵션만 사용할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>풀</strong></p></td>
<td><p>등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다. 개별 풀을 선택 하거나 <strong>[모두]</strong> 를 클릭 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>범주만</strong></p></td>
<td><p>발생 한 오류 유형. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>예상 및 예기치 않은 오류</p></li>
<li><p>예기치 않은 오류</p></li>
</ul>
<p>&quot;예상 되는&quot; 실패는 예상 되는 오류입니다. 예를 들어 사용자가 자신의 상태를 방해 금지로 설정 하면 해당 사용자에 게 전화를 거는 데 실패 하는 것으로 예상 됩니다. &quot;예기치 않은 오류가&quot; 발생 하는 것은 정상적인 시스템 때문 이라고 표시 되는 오류입니다. 예를 들어 호출자가 대기 상태로 설정 된 경우에는 통화가 종료 되지 않습니다. 이 문제가 발생 하면 예기치 않은 오류로 플래그가 지정 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>응답 코드</strong></p></td>
<td><p>회의에 실패 한 경우 SIP 응답 코드가 전송 됩니다. 전체 응답 코드를 입력 합니다 (예:).</p>
<p>400</p></td>
</tr>
<tr class="even">
<td><p><strong>진단 ID</strong></p></td>
<td><p>오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다. 진단 헤더는 선택 사항으로,이 헤더를 포함 하지 않는 SIP 세션이 있을 수 있으며, 진단 Id는 일부 종류의 문제가 발생 하는 세션에 대해서만 보고 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>매트릭스

다음 표에는 상위 오류 보고서에 제공 되는 정보가 나열 되어 있습니다.

### <a name="top-failures-report-metrics"></a>상위 오류 보고서 메트릭

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
<td><p>예</p></td>
<td><p>보고 된 세션의 수를 기준으로 상대 순위를 지정 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>보고 된 세션</strong></p></td>
<td><p>예</p></td>
<td><p>진단 ID 및 SIP 응답 코드에 따라 실패 한 총 세션 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>사용자에 게 영향을 받음</strong></p></td>
<td><p>예</p></td>
<td><p>실패 한 세션의 영향을 받는 총 사용자 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>오류 정보</strong></p></td>
<td><p>아니요</p></td>
<td><p>진단 ID, SIP 응답 코드, 세션이 실패 한 이유에 대 한 설명 등 오류에 대 한 자세한 정보입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>과거 추세</strong></p></td>
<td><p>아니요</p></td>
<td><p>시간이 지남에 따라 실패 한 세션을 그래프로 보여줍니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

