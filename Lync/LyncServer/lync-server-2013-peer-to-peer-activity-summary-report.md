---
title: 'Lync Server 2013: 피어-투-피어 활동 요약 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03a3015f24bae2595ac845c351c32ccb5d36c5f7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a>Lync Server 2013의 피어 투 피어 활동 요약 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-21_

피어 투 피어 활동 요약 보고서는 피어 투 피어 통신 세션에 대 한 전체 보기를 제공 합니다. 피어 투 피어 세션에는 일반적으로 두 명의 사용자만 포함 되며 Lync Server 회의 서비스는 사용할 필요가 없습니다. 일반적으로 회의에는 두 명 이상의 사용자가 포함 되므로 Microsoft Lync Server 2013 회의 서비스를 사용 해야 합니다. 전화 회의 활동이 전화 회의 요약 보고서에 보고 됩니다.

피어 투 피어 활동 요약 보고서는 다음과 같은 질문에 답할 수 있도록 도와줍니다.

  - 사용자가 일반적인 날에 얼마나 많은 피어 투 피어 인스턴트 메시지를 보낼 것인가?

  - 실제로 Lync Server 응용 프로그램 공유 및 파일 전송 기능을 활용 하는 사용자가 있나요?

  - 사용자가 하루 중 특정 시간에 느린 속도로 네트워크를 불만 했습니다. 이러한 기간 동안 피어 투 피어 오디오 및 비디오 세션에 소요 되는 시간은 몇 분 입니까?

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>피어 투 피어 활동 요약 보고서 액세스

모니터링 보고서 홈 페이지에서 피어 투 피어 활동 요약 보고서에 액세스 합니다. [Lync Server 2013에서](lync-server-2013-peer-to-peer-im-report.md) 다음 메트릭 중 하나를 클릭 하 여 피어 투 피어 IM 보고서를 엽니다.

  - 총 피어 투 피어 IM 세션

  - 총 피어 투 피어 IM 메시지

마찬가지로 다음 메트릭 중 하나를 클릭 하 여 피어 투 피어 음성 및 비디오 보고서를 열 수 있습니다.

  - 총 피어 투 피어 오디오 세션

  - 총 피어 투 피어 오디오 세션 시간 (분)

  - 총 피어 투 피어 오디오 세션

  - 총 피어 투 피어 오디오 세션 시간 (분)

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>피어 투 피어 활동 요약 보고서의 모범 사례 만들기

피어 투 피어 활동 요약 보고서 아래쪽에서 총 피어 투 피어 IM 세션 및 총 피어 투 피어 IM 메시지와 같은 메트릭에 대 한 합계를 찾을 수 있습니다. 보고서 본문에서 찾은 자세한 정보를 요약 하 여 보여 줍니다.

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 피어 투 피어 활동 요약 보고서를 사용 하 여 데이터를 그룹화 하는 방법을 선택할 수 있습니다. 이 경우 작업은 시, 일, 주 또는 월별로 그룹화 됩니다.

다음 표에서는 피어 투 피어 활동 요약 보고서에 사용할 수 있는 필터를 보여 줍니다.

### <a name="peer-to-peer-activity-summary-report-filters"></a>피어-투-피어 활동 요약 보고서 필터

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
<p>2012/7/17 오후 1:00</p>
<p>시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</p>
<p>7/17/12012</p>
<p>주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</p>
<p>7/13/2012</p>
<p>주는 항상 일요일부터 토요일까지로 실행됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>시간 범위의 종료 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</p>
<p>2012/7/17 오후 1:00</p>
<p>종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</p>
<p>7/17/12012</p>
<p>주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</p>
<p>7/13/2012</p>
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
<p>시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 시작 날짜가 7/17/12012이 고 종료 날짜가 2/28/2012 인 일별 간격을 선택 하는 경우 데이터는 8/7/12012 12:00 오전에서 9/7/12012 12:00까지, 즉 총 31 일 분량의 데이터에 표시 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>선별한

다음 표에서는 피어 투 피어 활동 요약 보고서에서 제공 되는 정보를 보여 줍니다.

### <a name="peer-to-peer-activity-summary-report-metrics"></a>피어 투 피어 활동 요약 보고서 메트릭

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
<td><p><strong>매시간</strong></p>
<p><strong>매일</strong></p>
<p><strong>매주</strong></p>
<p><strong>월간</strong></p></td>
<td><p>아니요</p></td>
<td><p>필터 도구 모음에서 선택한 시간 간격을 나타냅니다. 적용 가능한 경우 제공된 시간 간격을 클릭하여 해당 간격에 대한 세부 정보를 볼 수 있습니다. 예를 들어 일별 간격을 사용 하는 상태에서 7/17/12012를 클릭 하면 해당 날짜에 대 한 사용자 등록 작업을 시간별로 분석 하 여 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 피어 투 피어 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>세션 유형에 관계 없이 수행 된 총 피어 투 피어 세션 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 피어 투 피어 IM 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>피어 투 피어 IM (인스턴트 메시징) 세션의 총 수입니다. 이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 IM 보고서가 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 피어 투 피어 IM 메시지</strong></p></td>
<td><p>아니요</p></td>
<td><p>피어 투 피어 세션에서 전송 된 총 인스턴트 메시지 수입니다. 이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 IM 보고서가 표시 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 피어 투 피어 오디오 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 피어 투 피어 오디오 통화 수입니다. 이 필드를 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 음성 및 비디오 보고서가 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 피어 투 피어 오디오 세션 시간 (분)</strong></p></td>
<td><p>아니요</p></td>
<td><p>피어 투 피어 오디오 세션에 소요 된 총 시간입니다. 이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 음성 및 비디오 보고서가 표시 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>평균 피어 투 피어 오디오 세션 시간 (분)</strong></p></td>
<td><p>아니요</p></td>
<td><p>피어 투 피어 오디오 세션에 소요 된 평균 시간입니다. 총 오디오 세션 시간을 총 오디오 세션 수로 나누어서 계산 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 피어 투 피어 비디오 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 피어 투 피어 비디오 통화 수입니다. 비디오 세션은 오디오 세션으로도 계산 되며, 각 비디오 세션은 하나의 비디오 세션 및 하나의 오디오 세션으로 계산 됩니다. 이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 음성 및 비디오 보고서가 표시 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 피어 투 피어 비디오 세션 시간 (분)</strong></p></td>
<td><p>아니요</p></td>
<td><p>피어 투 피어 비디오 세션에서 소요 된 총 시간입니다. 이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 피어 투 피어 음성 및 비디오 보고서가 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>평균 피어 투 피어 비디오 세션 시간 (분)</strong></p></td>
<td><p>아니요</p></td>
<td><p>피어 투 피어 비디오 세션에 소요 된 평균 시간입니다. 총 비디오 세션 시간을 총 비디오 세션 수로 나누면 계산 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>총 피어 투 피어 파일 전송 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>파일 전송이 포함 된 총 피어 투 피어 세션 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 피어 투 피어 응용 프로그램 공유 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>응용 프로그램 공유가 포함 된 총 피어 투 피어 세션 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

