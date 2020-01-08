---
title: 'Lync Server 2013: 컨퍼런스 세부 정보 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac598c3f85211ad97f2d6266b74b6c524d76d006
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a>Lync Server 2013의 회의 세부 정보 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

회의 정보 보고서는 회의에 참가 한 모든 사용자에 대 한 자세한 정보를 제공 합니다. 예를 들어 사용자가 회의에 참가 한 날짜 및 시간과 사용자가 회의를 남긴 날짜 및 시간, 해당 사용자를 회의에 연결 하는 데 사용 된 끝점의 사용자 에이전트 등의 정보를 볼 수 있습니다. 각 회의에서 사용자의 역할에 대 한 정보를 볼 수도 있습니다 (예: 발표자 또는 참석자). 가장 중요 한 점은 회의를 성공적으로 참가 하 고 완료 하는 사용자와 회의를 성공적으로 참가 및 완료할 수 없었던 사용자를 빠르게 확인 하는 것입니다.

<div>

## <a name="accessing-the-conference-detail-report"></a>회의 세부 정보 보고서에 액세스

회의 세부 정보 보고서는 다음 보고서에서 액세스할 수 있습니다.

  - [Lync Server 2013의 통화 허용 제어 보고서](lync-server-2013-call-admission-control-report.md) (컨퍼런스에 대 한 세부 정보 메트릭 클릭)

  - [Lync Server 2013의 실패 목록 보고서](lync-server-2013-failure-list-report.md) (회의 메트릭 클릭)

  - [Lync Server 2013의 사용자 활동 보고서](lync-server-2013-user-activity-report.md) (컨퍼런스 URI 메트릭 클릭)

회의 정보 보고서에서 진단 보고서 (세부 정보) 메트릭을 클릭 하 여 [Lync Server 2013에서 진단 보고서](lync-server-2013-diagnostic-report.md) 에 액세스할 수 있습니다.

</div>

<div>

## <a name="filters"></a>필터가

없음. 회의 세부 정보 보고서에서 필터링 할 수 없습니다.

</div>

<div>

## <a name="metrics"></a>매트릭스

다음 표에는 회의 세부 정보 보고서의 컨퍼런스 Information 섹션에서 제공 하는 정보가 나열 되어 있습니다.

### <a name="conference-information-metrics"></a>컨퍼런스 정보 메트릭

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
<td><p><strong>컨퍼런스 URI</strong></p></td>
<td></td>
<td><p>회의에 할당 된 URI입니다. 예를 들면 다음과 같습니다.</p>
<p>sip: kmyer@litwareinc gruu, 불투명 = 앱: 회의: 포커스: id: drg2y8v4</p></td>
</tr>
<tr class="even">
<td><p><strong>풀 FQDN</strong></p></td>
<td></td>
<td><p>세션에 포함 된 레지스트라 풀 또는 Edge 서버의 정규화 된 도메인 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>시작 시간</strong></p></td>
<td></td>
<td><p>회의가 시작 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>구성 도우미</strong></p></td>
<td></td>
<td><p>회의를 구성한 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>종료 시간</strong></p></td>
<td></td>
<td><p>회의가 종료 된 날짜 및 시간입니다.</p></td>
</tr>
</tbody>
</table>


다음 표에는 회의 세부 정보 보고서의 회의 참여 섹션에서 제공 하는 정보가 나열 되어 있습니다.

### <a name="conference-participation-metrics"></a>회의 참여 메트릭

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
<td><p><strong>사용자</strong></p></td>
<td></td>
<td><p>회의에 참가 한 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>역할인</strong></p></td>
<td></td>
<td><p>회의 참가자가 재생 한 역할 (예: 발표자)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>연결성</strong></p></td>
<td></td>
<td><p>참가자의 네트워크 연결 (일반적으로 내부 또는 외부에서)</p></td>
</tr>
<tr class="even">
<td><p>참가 시간</p></td>
<td></td>
<td><p>참가자가 회의에 참가 한 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>휴가 시간</strong></p></td>
<td></td>
<td><p>참가자가 회의를 남겨진 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>사용자 에이전트</strong></p></td>
<td></td>
<td><p>참가자의 끝점에 사용 되는 소프트웨어의 식별자입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>진단 보고서</strong></p></td>
<td></td>
<td><p>진단 및 문제 해결 정보를 제공 합니다. 실패 한 세션에 대 한 SIP 응답 코드, 진단 헤더, 컨퍼런스 참가 시간, 진단 Id 등이 포함 됩니다.</p></td>
</tr>
</tbody>
</table>


다음 표에는 회의 세부 정보 보고서의 컨퍼런스 형식을 섹션에서 제공 하는 정보가 나열 되어 있습니다.

### <a name="conference-modalities-metrics"></a>컨퍼런스 형식을 메트릭

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
<td><p><strong>사용자</strong></p></td>
<td></td>
<td><p>회의에 참가 한 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>참가 시간</strong></p></td>
<td></td>
<td><p>참가자가 회의에 참가 한 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>휴가 시간</strong></p></td>
<td></td>
<td><p>참가자가 회의를 남겨진 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>회의 서버 URI</strong></p></td>
<td></td>
<td><p>회의에 사용 되는 회의 서버의 URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>진단 보고서</strong></p></td>
<td></td>
<td><p>진단 및 문제 해결 정보를 제공 합니다. 실패 한 세션에 대 한 SIP 응답 코드, 진단 헤더, 컨퍼런스 참가 시간, 진단 Id 등이 포함 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

