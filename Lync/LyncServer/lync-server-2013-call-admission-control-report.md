---
title: 'Lync Server 2013: 통화 허용 제어 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Admission Control Report
ms:assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615043(v=OCS.15)
ms:contentKeyID: 48185933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff036a27149db4360a938fe2ce9d63c2718f4d94
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-report-in-lync-server-2013"></a>Lync Server 2013의 통화 허용 제어 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-29_

통화 허용 제어 보고서는 통화 허용 제어에서 설정한 제한 하에서 수행한 피어 투 피어 및 회의 세션에 대 한 정보를 제공 합니다. Microsoft Lync Server 2010에서 도입 된 통화 허용 제어는 관리자가 대역폭 제약 조건을 기준으로 통신 세션을 허용 하거나 허용 하지 않는 방법을 제공 합니다. 예를 들어, 관리자는 음성 및 영상 통화에 사용할 수 있는 대역폭의 양을 제한 하는 정책을 만들 수 있습니다. 해당 대역폭 제한에 도달 하면 현재 통화 중 하나를 종료 하 고 필요한 네트워크 리소스를 해제할 때까지 새로운 음성 또는 영상 통화를 할 수 없습니다.

<div>

## <a name="accessing-the-call-admission-control-report"></a>통화 허용 컨트롤 보고서에 액세스

모니터링 보고서 홈 페이지에서 통화 허용 제어 보고서에 액세스할 수 있습니다. 통화 허용 제어 보고서에서 다음 보고서 중 하나로 드릴 다운할 수 있습니다.

  - 회의 세부 정보 보고서 –이 보고서에 액세스 하려면 회의 세션에서 세부 정보 메트릭을 클릭 합니다.

  - 피어 투 피어 세션 세부 정보 보고서 –이 보고서에 액세스 하려면 피어 투 피어 세션에 대 한 세부 정보 메트릭을 클릭 합니다.

</div>

<div>

## <a name="making-the-best-use-of-the-call-admission-control-report"></a>통화 허용 제어 보고서를 최대한 활용 하기

대역폭 부족으로 실패 한 통화 목록을 얻으려면 통화 범주 드롭다운 목록에서 통화 허용 제어로 인해 거부 된 통화를 선택 합니다. 반환 되는 대부분의 통화는 진단 ID가 5 일 수 있습니다.

대역폭이 부족 하 여 세션을 설정할 수 없습니다. PSTN re 경로를 시도 합니다.

이것은 통화 허용 제어 제한 사항으로 인해 VoIP 네트워크에서 전화를 걸 수 없음을 나타냅니다.

</div>

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 예를 들어, 통화 허용 제어 보고서를 사용 하면 호출을 시작한 사용자 또는 호출 하는 사용자에의 한 통화를 필터링 할 수 있습니다. 데이터 그룹화 방법을 선택할 수도 있습니다. 이 경우 통화는 시, 일, 주 또는 월로 그룹화 됩니다.

다음 표에는 통화 허용 컨트롤 보고서와 함께 사용할 수 있는 필터가 나와 있습니다.

### <a name="call-admission-control-report-filters"></a>통화 허용 제어 보고서 필터

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
<p>오후 7/17/12012 1:00</p>
<p>시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다. 날짜별로 데이터를 보려면 날짜만 입력 합니다.</p>
<p>7/17/12012</p>
<p>주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</p>
<p>7/13/2012</p>
<p>주는 항상 일요일 ~ 토요일을 실행 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>받는 사람</strong></p></td>
<td><p>시간 범위의 종료 날짜/시간입니다. 시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</p>
<p>오후 7/17/12012 1:00</p>
<p>종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다. 날짜별로 데이터를 보려면 날짜만 입력 합니다.</p>
<p>7/17/12012</p>
<p>주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</p>
<p>7/13/2012</p>
<p>주는 항상 일요일 ~ 토요일을 실행 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>풀</strong></p></td>
<td><p>등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다. 개별 풀을 선택 하거나 <strong>[모두]</strong> 를 클릭 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>활동 유형</strong></p></td>
<td><p>활동의 유형입니다. 다음 활동 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>피어 투 피어</p></li>
<li><p>회의</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>통화 범주</strong></p></td>
<td><p>CAC가 통화에 사용 된 이유를 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>통화 허용 제어로 인해 통화가 거부 됨</p></li>
<li><p>통화 허용 제어로 인해 PSTN을 통해 통화가 전환 되었습니다.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>피어 투 피어 세션에 대 한 메트릭

다음 표에는 피어 투 피어 세션 (즉, 두 명의 참가자만 참여 하는 세션)에 대 한 호출 허용 제어 보고서에 제공 되는 정보가 나열 되어 있습니다.

### <a name="metrics-for-peer-to-peer-sessions"></a>피어 투 피어 세션에 대 한 메트릭

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
<td><p><strong>도</strong></p></td>
<td><p>아니요</p></td>
<td><p>이 항목을 클릭 하면 보고서에는 지정 된 세션에 대 한 피어 투 피어 세션 세부 정보 보고서가 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>사용자의</strong></p></td>
<td><p>예</p></td>
<td><p>세션을 시작한 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>사용자에 게</strong></p></td>
<td><p>예</p></td>
<td><p>세션에 참가 하도록 초대 받은 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>형식을</strong></p></td>
<td><p>예</p></td>
<td><p>세션 중 사용 된 통신 형식을 (오디오 및 비디오 등)</p></td>
</tr>
<tr class="odd">
<td><p><strong>초대 시간</strong></p></td>
<td><p>예</p></td>
<td><p>초기 세션 초대를 보낸 사람 사용자에 게 보낸 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>응답 시간</strong></p></td>
<td><p>예</p></td>
<td><p>초대 수락을 받은 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>종료 시간</strong></p></td>
<td><p>예</p></td>
<td><p>세션이 종료 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>진단 ID</strong></p></td>
<td><p>예</p></td>
<td><p>오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다. 진단 헤더는 선택 사항으로,이 헤더를 포함 하지 않는 SIP 세션이 있을 수 있으며, 진단 Id는 일부 종류의 문제가 발생 하는 세션에 대해서만 보고 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>회의 세션에 대 한 메트릭

다음 표에서는 회의 세션 (즉, 세 명 이상의 참가자와 관련 된 세션)의 호출 허용 제어 보고서에 제공 되는 정보를 보여 줍니다.

### <a name="metrics-for-conferencing-sessions"></a>회의 세션에 대 한 메트릭

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
<td><p>예</p></td>
<td><p>회의의 고유 식별자입니다. 이 항목을 클릭 하면 보고서에 개별 회의 참가자가 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>구성 도우미</strong></p></td>
<td><p>예</p></td>
<td><p>회의를 구성한 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>풀</strong></p></td>
<td><p>예</p></td>
<td><p>에 지 서버를 사용 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>시작 시간</strong></p></td>
<td><p>예</p></td>
<td><p>회의가 시작 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>종료 시간</strong></p></td>
<td><p>예</p></td>
<td><p>회의가 종료 된 날짜 및 시간입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-individual-conference-participants"></a>개별 회의 참가자에 대 한 메트릭

다음 표에는 개별 회의 참가자를 위해 통화 허용 제어 보고서에 제공 되는 정보가 나열 되어 있습니다.

### <a name="metrics-for-individual-conference-participants"></a>개별 회의 참가자에 대 한 메트릭

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
<td><p><strong>역할인</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의 참가자가 재생 한 역할 (예: 발표자)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>참여자</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의 참가자의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>연결성</strong></p></td>
<td><p>아니요</p></td>
<td><p>참가자의 네트워크 연결 (일반적으로 내부 또는 외부에서)</p></td>
</tr>
<tr class="even">
<td><p><strong>모달</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의 유형 (예: A/V 회의).</p></td>
</tr>
<tr class="odd">
<td><p><strong>참가 시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>참가자가 회의에 참가 한 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>휴가 시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>참가자가 회의를 남겨진 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>진단 ID</strong></p></td>
<td><p>아니요</p></td>
<td><p>오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다. 진단 헤더는 선택 사항으로,이 헤더를 포함 하지 않는 SIP 세션이 있을 수 있으며, 진단 Id는 일부 종류의 문제가 발생 하는 세션에 대해서만 보고 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

