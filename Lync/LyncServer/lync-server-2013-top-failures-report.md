---
title: 'Lync Server 2013: Top Failures 보고서'
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
ms.openlocfilehash: 972c9e97015f5a39ace3cf1fc68051cc0afcc988
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a>Lync Server 2013의 상위 실패 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

Top Failures 보고서는 가장 일반적으로 보고되는 오류 및 해당 추세를 시간별로 조사합니다. 오류는 다음과 같은 두 가지 측정 단위의 조합을 기반으로 합니다.

  - **진단 ID**. SIP 메시지에 연결된 고유 식별자입니다(ms-diagnostics 헤더 형식). 진단 ID는 통화 관련 문제 해결에 유용한 정보를 제공합니다.

  - **응답 코드**. 응답 코드는 SIP 통신 세션에서 SIP 요청에 응답하기 위해 사용됩니다. 예를 들어 Ken이 Pilar Ackerman에게 INVITE 요청을 보낸다고 가정해보십시오(즉, Ken Myer가 Pilar Ackerman을 호출한다고 가정). Pilar가 응답하면 해당 전화기가 응답 코드 200(OK)을 전송해서 Ken의 전화에서 Pilar가 응답했는지를 확인할 수 있게 해줍니다. Top Failures 보고서에는 통화 실패에 대 한 응답으로 전송 된 응답 코드만 포함 됩니다. Lync Server는 통화 중에 발생 한 모든 응답 코드를 추적 하지 않습니다.

정보는 오류가 발생한 총 세션 수뿐만 아니라 이 오류로 영향을 받는 총 사용자 수에 대해서도 보고됩니다.

<div>

## <a name="accessing-the-top-failures-report"></a>Top Failures 보고서 액세스

Top Failures 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다. 보고 된 세션 메트릭을 클릭 하면 [Lync Server 2013의 실패 분포 보고서](lync-server-2013-failure-distribution-report.md)로 이동 합니다.

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a>Top Failures 보고서의 모범 사례 만들기

Top Failures 보고서는 한 가지 측면에서 일반적이지 않습니다. 이 보고서는 진단 ID를 한 번에 최대 5개까지 필터링할 수 있습니다. 일반적으로는 사용자 SIP 주소 하나와 같이 항목을 한 번에 하나만 필터링할 수 있습니다. 여러 진단 ID를 필터링하려면 진단 ID 상자에 각 ID를 입력하기만 하면 됩니다. ID는 쉼표로 구분합니다. 필요한 경우 각 쉼표 다음에 빈 칸을 남길 수 있습니다. 예를 들면 다음과 같습니다.

1011, 2412, 1033, 52116, 1008

이를 수행하면 이러한 5개의 진단 ID 중 하나 이상을 보고한 실패한 통화만 표시됩니다.

응답 코드 위에 마우스를 두면 해당 응답 코드의 의미가 표시된 도구 상자가 나타납니다. 예를 들어 응답 코드 486 위에 마우스를 두면 다음 메시지가 표시됩니다.

여기에서 사용 중입니다.

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 상위 실패 보고서에서는 활동 유형(피어 투 피어 세션 또는 회의 세션)과 같은 항목이나 실패한 세션에 수반된 SIP 응답 코드별로 반환된 데이터를 필터링할 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 사용은 시간, 일, 주 및 월별로 그룹이 지정됩니다.

다음 표에서는 상위 실패 보고서에 사용할 수 있는 필터를 보여 줍니다.

### <a name="top-failures-report-filters"></a>상위 실패 보고서 필터

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
<td><p><strong>From</strong></p></td>
<td><p>시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</p>
<p>7/7/2012 1:00 PM</p>
<p>시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</p>
<p>7/7/2012</p>
<p>주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</p>
<p>7/3/2012</p>
<p>주는 항상 일요일부터 토요일까지입니다.</p></td>
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
<td><p><strong>활동 유형</strong></p></td>
<td><p>활동 유형입니다. 다음 중 하나를 선택합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>피어-투-피어</p></li>
<li><p>전화</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>형식</strong></p></td>
<td><p>현재까지 사용 가능한 유일한 옵션은 <strong>[모두]</strong>입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>그룹</strong></p></td>
<td><p>등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>범주</strong></p></td>
<td><p>발생한 오류 유형입니다. 다음 중 하나를 선택합니다.</p>
<ul>
<li><p>예상 오류 및 예기치 않은 오류 모두</p></li>
<li><p>예기치 않은 오류</p></li>
</ul>
<p>&quot;예상 되는&quot; 실패는 발생할 것으로 예상 되는 오류입니다. 예를 들어 사용자가 자신의 상태를 방해 금지로 설정한 경우 해당 사용자에 대한 통화가 실패할 것으로 예상할 수 있습니다. &quot;예기치 않은 오류가&quot; 발생 하는 것은 정상적인 시스템이 아닌 것 처럼 보이는 오류입니다. 예를 들어 발신자가 보류 상태일 때는 통화가 종료되지 않아야 합니다. 하지만 통화가 종료되면 바로 예기치 않은 오류로 플래그 지정됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>응답 코드</strong></p></td>
<td><p>회의가 실패했을 때 전송된 SIP 응답 코드입니다. 전체 응답 코드를 입력합니다. 예:</p>
<p>400</p></td>
</tr>
<tr class="even">
<td><p><strong>진단 ID</strong></p></td>
<td><p>오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다. 진단 헤더는 선택 사항이며(이러한 헤더를 포함하지 않는 SIP 세션도 가능함) 진단 ID는 일부 유형의 문제가 발생한 세션에 대해서만 보고됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>선별한

다음 표에서는 상위 실패 보고서에서 제공되는 정보를 보여 줍니다.

### <a name="top-failures-report-metrics"></a>상위 실패 보고서 메트릭

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
<td><p>예</p></td>
<td><p>보고된 세션 수에 따른 상대적 순위입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>보고된 세션</strong></p></td>
<td><p>예</p></td>
<td><p>진단 ID 및 SIP 응답 코드에 따른 실패한 총 세션 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>영향 받은 사용자</strong></p></td>
<td><p>예</p></td>
<td><p>실패한 세션의 영향을 받은 총 사용자 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>실패 정보</strong></p></td>
<td><p>아니요</p></td>
<td><p>진단 ID, SIP 응답 코드, 세션이 실패한 이유에 대한 설명을 비롯한 실패에 대한 자세한 정보입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>지난 추세</strong></p></td>
<td><p>아니요</p></td>
<td><p>시간별로 실패한 세션의 그래프입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

