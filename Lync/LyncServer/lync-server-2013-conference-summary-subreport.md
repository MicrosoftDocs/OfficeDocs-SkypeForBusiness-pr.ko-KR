---
title: 'Lync Server 2013: 컨퍼런스 요약 하위 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b87ea9648404f495f487a639a3b11900f91dcda4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a>Lync Server 2013의 컨퍼런스 요약 하위 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-06_

회의 요약 하위 보고서는 실패 한 회의 세션의 전체적인 보기를 제공 합니다. 이러한 실패 한 세션은 세션 유형: 포커스 세션 및 MCU 세션으로 더욱 세분화 됩니다.

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 다음 표에는 회의 요약 하위 보고서와 함께 사용할 수 있는 필터가 나열 되어 있습니다.

### <a name="conference-summary-subreport-filters"></a>컨퍼런스 요약 하위 보고서 필터

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
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>매트릭스

다음 표에는 회의 요약 하위 보고서에서 제공 하는 정보가 나열 되어 있습니다.

### <a name="conference-summary-subreport-metrics"></a>컨퍼런스 요약 하위 보고서 메트릭

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
<td><p><strong>총 컨퍼런스</strong></p></td>
<td><p>아니요</p></td>
<td><p>보유 한 총 컨퍼런스 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 회의 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>회의 세션의 총 수입니다. 단일 회의는 여러 세션을 가질 수 있습니다. 예를 들어 컨퍼런스에는 포커스 세션과 MCU 세션이 모두 포함 될 것입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>전체 세션 실패 율</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 모든 컨퍼런스의 백분율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>포커스 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>총 포커스 세션 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>초점 고장 속도</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 포커스 세션의 백분율입니다.</p></td>
</tr>
<tr class="even">
<td><p>MCU 세션</p></td>
<td><p>아니요</p></td>
<td><p>총 MCU 세션 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MCU 실패 율</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 MCU 세션의 백분율입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>모달에의 한 MCU 세션</strong></p></td>
<td><p>아니요</p></td>
<td><p>형식 (예: IM 회의)으로 그룹화 된 총 MCU 세션 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>모달의 실패 비율</strong></p></td>
<td><p>아니요</p></td>
<td><p>실패 한 MCU 세션의 백분율 (예: IM 회의)</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

