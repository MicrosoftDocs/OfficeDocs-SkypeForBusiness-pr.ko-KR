---
title: 'Lync Server 2013: 피어 투 피어 음성 및 비디오 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68cddb8296a94ff5d5b084895024d7379a42022c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a>Lync Server 2013의 피어 투 피어 음성 및 비디오 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-21_

피어 투 피어 음성 및 비디오 보고서는 지정 된 기간의 음성 및 영상 통화 분포에 대 한 자세한 정보 (예: 시간당 통화 또는 하루에 한 번)를 제공 합니다. 또한 보고서는 모든 음성 및 영상 통화를 보거나 성공 또는 실패 한 통화를 보는 옵션도 제공 합니다. 이 보고서에는 다음과 같은 그룹으로 구분 된 통화 정보가 표시 됩니다.

  - 풀 당 통화

  - 통화 유형별 통화 (예: Lync to Lync 통화 및 PSTN 네트워크의 사용자에 대 한 Lync 통화)

  - 액세스 유형별 통화 (내부 네트워크에 로그온 한 사용자와 외부 네트워크에 로그온 한 사용자)

  - 중재 서버 당 통화

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>피어 투 피어 음성 및 비디오 보고서에 액세스 하려면

피어 투 피어 음성 및 비디오 보고서에 액세스 하려면 동위 투 피어 활동 요약 보고서를 열고 다음 메트릭 중 하나를 클릭 합니다.

  - 총 피어 투 피어 오디오 세션

  - 총 피어 투 피어 오디오 시간

  - 총 피어 투 피어 비디오 세션

  - 총 피어 투 피어 비디오 통화

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>피어 투 피어 음성 및 비디오 보고서의 용도를 최대한 활용 하려면

피어 투 피어 음성 및 비디오 보고서를 필터링 하는 방법에는 여러 가지가 있습니다. 그러나 이러한 필터링 옵션은 기본적으로 보기에서 숨겨집니다. 사용할 수 있는 필터링 옵션을 보려면 보고서 창의 오른쪽 위 모서리에 있는 **매개 변수 표시/숨기기** 단추를 클릭 합니다.

</div>

<div>

## <a name="filters"></a>필터가

필터를 통해 보다 세부적으로 대상 지정 된 데이터 집합을 반환 하거나 다양 한 방법으로 데이터를 볼 수 있습니다. 다음 표에는 피어 투 피어 음성 및 비디오 보고서에 사용할 수 있는 필터가 나와 있습니다.

### <a name="peer-to-peer-voice-and-video-report-filters"></a>피어 투 피어 음성 및 비디오 보고서 필터

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
<td><p>시간 범위에 대 한 시작 날짜 및 시간입니다. 시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</p>
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
<td><p><strong>미디어 유형</strong></p></td>
<td><p>세션에 사용 되는 미디어 유형을 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>양방향</p></li>
<li><p>오디오</p></li>
<li><p>비디오만</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>통화 처리</strong></p></td>
<td><p>세션의 성공 또는 실패를 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>성공 통화</p></li>
<li><p>통화 실패</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>보고서 기준</strong></p></td>
<td><p>보고서에 사용할 값을 나타냅니다. 다음 중 하나를 선택 합니다.</p>
<ul>
<li><p>세션 수</p></li>
<li><p>통화 시간 (분)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>피어 투 피어 음성 및 풀 별 비디오 활동에 대 한 메트릭

다음 표에는 각 풀에 대 한 피어 투 피어 음성 및 비디오 보고서에서 제공 하는 정보가 나와 있습니다.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>피어 투 피어 음성 및 풀 별 비디오 활동에 대 한 메트릭

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
<td><p><strong>풀</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화에 사용 되는 등록자 풀 또는 Edge 서버의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>날짜/시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화가 발생 한 날짜 및 시간 간격입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 세션 수 또는 총 메시지 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>피어 투 피어 음성 및 통화 유형별 비디오 활동에 대 한 메트릭

다음 표에서는 각 통화 유형에 대 한 피어 투 피어 음성 및 비디오 보고서에 제공 되는 정보를 보여 줍니다.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>피어 투 피어 음성 및 통화 유형별 비디오 활동에 대 한 메트릭

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
<td><p><strong>통화 종류</strong></p></td>
<td><p>아니요</p></td>
<td><p>발생 한 통화 유형을 나타냅니다. 값은 다음 중 하나입니다.</p>
<ul>
<li><p>UC-UC</p></li>
<li><p>UC 대 PSTN</p></li>
<li><p>PSTN에서 UC로</p></li>
<li><p>PSTN에서 PSTN으로</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>날짜/시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화가 발생 한 날짜 및 시간 간격입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 세션 수 또는 총 메시지 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>피어 투 피어 음성 및 access 유형별 비디오 활동에 대 한 메트릭

다음 표에는 각 네트워크 액세스 형식에 대 한 피어 투 피어 음성 및 비디오 보고서에 제공 되는 정보가 나열 되어 있습니다.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>피어 투 피어 음성 및 access 유형별 비디오 활동에 대 한 메트릭

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
<td><p><strong>활동 유형</strong></p></td>
<td><p>아니요</p></td>
<td><p>전화를 걸 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온 되었는지 여부를 나타냅니다. 값은 일반적으로 다음 중 하나입니다.</p>
<ul>
<li><p>내부용</p></li>
<li><p>내부</p></li>
<li><p>섞여</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>날짜/시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화가 발생 한 날짜 및 시간 간격입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 세션 수 또는 총 메시지 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>중재 서버용 피어 투 피어 음성 및 비디오 활동에 대 한 메트릭

다음 표에는 각 중재 서버의 피어 투 피어 음성 및 비디오 보고서에 제공 되는 정보가 나열 되어 있습니다.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>중재 서버용 피어 투 피어 음성 및 비디오 활동에 대 한 메트릭

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
<td><p><strong>중재 서버</strong></p></td>
<td><p>아니요</p></td>
<td><p>중재 서버의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>날짜/시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화가 발생 한 날짜 및 시간 간격입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 세션 수 또는 총 메시지 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

