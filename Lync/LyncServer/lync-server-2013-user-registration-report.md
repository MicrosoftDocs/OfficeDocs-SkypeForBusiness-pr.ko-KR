---
title: 'Lync Server 2013: 사용자 등록 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd7ff808b766d7366e39595a46d1a2d7dfb75996
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a>Lync Server 2013의 사용자 등록 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-21_

사용자 등록 보고서는 지정 된 기간 (매시간, 매일, 매주, 매월) 동안 Microsoft Lync Server 2013에 로그온 한 사용자 수에 대 한 정보를 사용자 로그온 작업에 대 한 개요로 제공 합니다. 이 보고서에는 로그온한 사용자의 수만 표시됩니다. 즉, *누가* 로그온했는지는 확인할 수 없습니다. 모니터링 보고서는 어떤 사용자가 Lync Server 2013를 사용 하 고 있는지와 어떤 것이 아닌 경우에 대 한 정보를 제공 하지 않습니다. 그러나 사용자 활동 보고서를 사용하면 대략적인 사용자 정보를 파악할 수는 있습니다.

사용자 등록 보고서는 사용자 로그온에 대한 정보를 제공할 때 두 가지 주요 기준을 사용하여 정보를 구분합니다. 첫째로, 이 보고서에서는 로그온이 두 가지 기본 범주(내부 로그온/외부 로그온)로 구별됩니다. 내부 로그온은 회사 네트워크에 연결되어 있는 동안 조직 방화벽 내에서 로그온한 사용자를 나타냅니다. 외부 로그온은에 지 서버를 통해 방화벽 외부에서 로그온 한 사용자 (예: 인터넷에서 로그온 한 사용자가 외부 로그온으로 café)를 나타냅니다. 방화벽 외부에서 로그온하는 사용자 수를 확인해야 하는 경우 사용자 등록 보고서에서 해당 정보를 파악할 수 있습니다.

사용자 등록 보고서는 지정된 기간 동안의 *활성* 사용자 수에 대한 정보도 제공합니다. 활성 사용자는 IM (인스턴트 메시징) 세션에 참여 하거나, Lync 모임에 참가 하거나, 전화를 걸거나 받거나, 아니면 해당 기간 동안 Lync Server를 사용 하는 사용자입니다. 활성 사용자는 로그온하기는 했지만 시스템을 실제로 사용한 적은 없는 사용자와는 다릅니다.

<div>

## <a name="accessing-the-user-registration-report"></a>사용자 등록 보고서 액세스

사용자 등록 보고서는 모니터링 보고서 홈 페이지에서만 액세스할 수 있습니다. 이 보고서는 다른 보고서에 연결되지 않습니다.

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a>효율적인 사용자 등록 보고서 활용

Lync Server를 배포한 후에는 사용자가이 새로운 기술을 실제로 사용 하는지 어떻게 알 수 있나요? 이와 관련하여 몇 가지 제한이 있기는 하지만, 사용자 등록 보고서를 사용하면 해당 사항을 확인할 수 있습니다. 사용자가 Lync Server를 사용 하 고 있는지 여부를 확인 하려면 두 가지 작업을 수행 해야 합니다. 먼저 사용자 등록 보고서에서 고유 로그온 사용자 메트릭 값을 가져옵니다. 이 값은 Lync Server에 로그온 한 개별 개별 사용자의 수를 알려 줍니다.

비교를 통해 총 로그온 메트릭은 모든 사용자가 Lync Server에 로그온 한 총 시간 수를 표시 합니다. 예를 들어 Ken Myer가 하루에 여러 번 Lync Server에 로그온 했다고 가정 합니다. 이 경우 Ken Myer의 로그온은 총 로그온 메트릭에서는 5회의 개별 로그온 세션으로 계산되지만 고유 로그온 사용자 메트릭에서는 단일 로그온 사용자로 계산됩니다. 마찬가지로, 사용자가 여러 장치나 여러 위치에서 로그온하는 경우도 흔합니다. 예를 들어 사용자는 데스크톱 컴퓨터의 랩톱 컴퓨터를 사용 하 여 로그온 할 수 있으며 Lync Server에 자동으로 로그온 하는 IP 전화가 있을 수 있습니다. 이 예제의 경우 로그온 횟수는 3회이지만 고유 사용자는 1명입니다.

총 로그온과 고유 로그온 간의 차이를 보다 자세하게 파악하려면 아래 표에 나와 있는 지정된 기간 동안의 로그온을 살펴보십시오.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>사용자</th>
<th>로그온 시간</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>2012/7/7 오전 8:45</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>2012/7/7 오전 8:46</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>2012/7/7 오전 9:17</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>2012/7/7 오전 9:22</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>2012/7/7 오전 9:31</p></td>
</tr>
</tbody>
</table>


이 경우 총 로그온 횟수는 5회이지만 고유 로그온 사용자는 2명(3회 로그온한 Ken Myer, 2회 로그온한 Pilar Ackerman)입니다. 이처럼 로그온 횟수와 고유 로그온 사용자 수는 서로 다를 수 있습니다.

고유한 로그온 수를 아는 것 외에도 Lync Server에 대해 사용 하도록 설정 된 총 사용자 수를 파악 해야 합니다. Lync Server 2013 관리 셸을 열고 다음 Windows PowerShell 명령을 실행 하 여이 값을 검색할 수 있습니다.

    (Get-CsUser).Count

위의 명령이 값 1236을 반환 하 고 고유 로그온 사용자 메트릭이 평균 값 667를 반환 하는 경우, 사용자가 Lync에 대해 거의 모든 부분을 사용 하도록 설정 하는 것은 실제로 매일 시스템에 로그온 하는 것을 제안 합니다 (즉, 667은 1236으로 구분 됨). ,이는 대략 54%입니다.

<div>


> [!WARNING]  
> 로그온 메트릭은 지정된 기간 동안 실제로 로그온한 사용자를 기록합니다. 그러나 시스템에 이미 로그온되어 있는 사용자는 추적하지 않습니다. 예를 들어 고유 로그온 사용자 메트릭에서 로그온 667회를 표시하는데 사용자 수는 1,236명이면 사용자 중 절반 정도가 시스템에 로그온함을 의미합니다. 그러나 로그온 데이터 확인을 시작한 시간에 사용자 300명이 시스템에 이미 로그온한 상태라고 가정해 보겠습니다. 이는 실제로 거의 1000 사용자가 Lync Server에 로그온 했을 것 이며,이는 사용자의 80%에 가까울수록 더 가까이 있다는 것을 의미 합니다.



</div>

고유 로그온 사용자 값은 고유 활성 사용자 메트릭과도 비교해야 합니다. 고유한 활성 사용자 메트릭은 Lync Server에 실제로 사용 된 고유한 사용자 수, 즉 전화를 걸거나 Lync 모임에 참가 했거나 IM 세션에 참가 했음을 알려 줍니다. 이는 사용자가 Windows를 시작할 때마다 자동으로 시작 되도록 Microsoft Lync 2013을 구성할 수 있기 때문에 유용한 정보입니다. 따라서 매일 Windows에 로그온 할 때 Lync에 자동으로 로그온 하는 사용자가 많고이 기간 동안에는 실제로 Lync Server를 사용 하지 않을 수 있습니다.

또한 고유한 활성 사용자 메트릭은 사용자가 대개 하루 종일 Windows를 로그 오프 하지 않는 조직에서 더 의미 있는 데이터를 제공 합니다. 대신 컴퓨터를 잠그고 Windows 및 Lync를 실행 하기만 하면 됩니다. 이러한 상황에서는 사용자가 로그온한 상태를 며칠씩 유지하고 로그오프하지는 않기 때문에 일별 로그온 수가 매우 적을 수 있습니다. 그러나 고유한 활성 사용자는 사용자가 Lync 또는 다른 Lync Server 클라이언트를 사용 중인지 여부를 알려 줍니다.

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 사용자 등록 보고서를 사용 하면 모든 등록자 풀 및에 지 서버에 대 한 데이터를 보거나 개별 풀에 대 한 데이터를 볼 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 등록은 시간, 일, 주 또는 월별로 그룹화됩니다.

다음 표에서는 사용자 등록 보고서에서 사용할 수 있는 필터를 보여 줍니다.

### <a name="user-registration-report-filters"></a>사용자 등록 보고서 필터

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
<td><p>시간 범위의 종료 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</p>
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
<td><p><strong>그룹</strong></p></td>
<td><p>등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 선택하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>선별한

다음 표에서는 사용자 등록 보고서에서 제공되는 정보를 보여 줍니다.

### <a name="user-registration-report-metrics"></a>사용자 등록 보고서 메트릭

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
<td><p>필터 도구 모음에서 선택한 시간 간격을 나타냅니다. 적용 가능한 경우 제공된 시간 간격을 클릭하여 해당 간격에 대한 세부 정보를 볼 수 있습니다. 예를 들어 일별 간격을 사용 중이고 2012/7/7을 클릭하면 해당 날짜의 사용자 등록 활동에 대한 시간별 세부 내역을 볼 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 로그온</strong></p></td>
<td><p>아니요</p></td>
<td><p>성공한 로그온 세션 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>내부 로그온</strong></p></td>
<td><p>아니요</p></td>
<td><p>내부 네트워크 내의 총 로그온 횟수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>외부 로그온</strong></p></td>
<td><p>아니요</p></td>
<td><p>에지 서버를 사용하는 내부 네트워크 외부에서의 총 로그온 횟수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>고유 로그온 사용자</strong></p></td>
<td><p>아니요</p></td>
<td><p>로그온 세션이 하나 이상 포함된 총 사용자 수입니다. 로그온 세션을 여러 개 갖고 있는 사용자도 한 명의 사용자로 계산되며 단일 로그온 세션을 갖고 있는 사용자와 동일합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>고유 활성 사용자</strong></p></td>
<td><p>아니요</p></td>
<td><p>피어 투 피어 또는 회의 세션에 포함된 총 사용자 수입니다. 세션을 여러 개 갖고 있는 사용자도 한 명의 사용자로 계산되며 단일 세션을 갖고 있는 사용자와 동일합니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

