---
title: 'Lync Server 2013: 피어-투-피어 음성 및 비디오 보고서'
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
ms.openlocfilehash: dcb58becb1b495c16338ef9590ede8fb4005bc2d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a>Lync Server 2013의 피어 투 피어 음성 및 비디오 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-21_

피어 투 피어 음성 및 비디오 보고서는 지정된 시간 동안의 음성 및 비디오 통화 배포 상황에 대한 자세한 정보(예를 들면, 시간당 통화 수 또는 일별 통화 수)를 제공합니다. 이 보고서는 발생된 모든 음성 및 비디오 통화를 보거나 성공 또는 실패한 통화만 볼 수 있는 옵션도 제공합니다. 이 보고서에는 다음 그룹으로 세분되는 통화 정보가 표시됩니다.

  - 풀별 통화 수

  - 통화 유형별 통화 (예: Lync to Lync call 및 PSTN 네트워크의 사용자에 대 한 Lync 호출)

  - 액세스 유형별 통화 수(내부 네트워크에 로그온한 사용자와 외부 네트워크에 로그온한 사용자)

  - 중재 서버당 통화 수

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>피어 투 피어 음성 및 비디오 보고서에 액세스하려면

피어 투 피어 활동 요약 보고서를 열고 다음 메트릭 중 하나를 클릭해야 피어 투 피어 음성 및 비디오 보고서에 액세스할 수 있습니다.

  - 총 피어 투 피어 오디오 세션

  - 총 피어 투 피어 오디오 시간(분)

  - 총 피어 투 피어 비디오 세션

  - 총 피어 투 피어 비디오 시간(분)

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>피어 투 피어 음성 및 비디오 보고서를 최대한 활용하려면

여러 방식으로 피어 투 피어 음성 및 비디오 보고서를 필터링할 수 있습니다. 하지만 이러한 필터링 옵션은 기본적으로 보기에서 숨겨져 있습니다. 사용할 수 있는 필터링 옵션을 보려면 보고서 창의 오른쪽 위에 있는 **매개 변수 표시/숨기기** 단추를 클릭합니다.

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에서는 피어 투 피어 음성 및 비디오 보고서에 사용할 수 있는 필터를 보여 줍니다.

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
<td><p><strong>From</strong></p></td>
<td><p>시간 범위의 시작 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜와 시간을 모두 입력합니다.</p>
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
<td><p><strong>미디어 유형</strong></p></td>
<td><p>세션에 사용된 미디어 유형을 나타냅니다. 다음 중 하나를 선택합니다.</p>
<ul>
<li><p>모두</p></li>
<li><p>오디오만</p></li>
<li><p>비디오</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>통화 처리</strong></p></td>
<td><p>세션의 성공 또는 실패를 나타냅니다. 다음 중 하나를 선택합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>성공한 통화</p></li>
<li><p>실패한 통화</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>보고서 작성자</strong></p></td>
<td><p>보고서에 사용할 값을 나타냅니다. 다음 중 하나를 선택합니다.</p>
<ul>
<li><p>세션 수</p></li>
<li><p>통화 시간(분)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>풀별 피어 투 피어 음성 및 비디오 활동 메트릭

다음 표에서는 각 풀에 대해 피어 투 피어 음성 및 비디오 보고서에 제공되는 정보를 보여 줍니다.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>풀별 피어 투 피어 음성 및 비디오 활동 메트릭

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
<td><p><strong>그룹</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화에 사용 되는 등록자 풀 또는에 지 서버의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>날짜/시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화가 발생한 날짜 및 시간 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>합계</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 세션 수 또는 총 메시지 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>통화 유형별 피어 투 피어 음성 및 비디오 활동 메트릭

다음 표에서는 수행된 통화의 각 유형에 대해 피어 투 피어 음성 및 비디오 보고서에 제공되는 정보를 보여 줍니다.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>통화 유형별 피어 투 피어 음성 및 비디오 활동 메트릭

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
<td><p><strong>통화 유형</strong></p></td>
<td><p>아니요</p></td>
<td><p>수행된 통화의 유형을 나타냅니다. 값은 다음 중 하나입니다.</p>
<ul>
<li><p>UC-UC</p></li>
<li><p>UC-PSTN</p></li>
<li><p>PSTN-UC</p></li>
<li><p>PSTN-PSTN</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>날짜/시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화가 발생한 날짜 및 시간 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>합계</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 세션 수 또는 총 메시지 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>액세스 유형별 피어 투 피어 음성 및 비디오 활동 메트릭

다음 표에서는 각 네트워크 액세스 유형에 대해 피어 투 피어 음성 및 비디오 보고서에 제공되는 정보를 보여 줍니다.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>액세스 유형별 피어 투 피어 음성 및 비디오 활동 메트릭

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
<td><p><strong>활동 유형</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화가 시도되었을 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온되어 있는지를 나타냅니다. 값은 일반적으로 다음 중 하나입니다.</p>
<ul>
<li><p>Internal</p></li>
<li><p>외부:</p></li>
<li><p>여러</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>날짜/시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화가 발생한 날짜 및 시간 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>합계</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 세션 수 또는 총 메시지 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>중재 서버별 피어 투 피어 음성 및 비디오 활동 메트릭

다음 표에서는 각 중재 서버에 대해 피어 투 피어 음성 및 비디오 보고서에 제공 되는 정보를 보여 줍니다.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>중재 서버별 피어 투 피어 음성 및 비디오 활동 메트릭

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
<td><p><strong>중재 서버</strong></p></td>
<td><p>아니요</p></td>
<td><p>중재 서버의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>날짜/시간</strong></p></td>
<td><p>아니요</p></td>
<td><p>통화가 발생한 날짜 및 시간 기간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>합계</strong></p></td>
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

