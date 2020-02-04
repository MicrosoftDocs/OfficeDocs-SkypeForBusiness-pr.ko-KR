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
ms.openlocfilehash: 079e6cb96a9401d909be4f459d7bbe7c3f6d4ed6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a>Lync Server 2013의 사용자 등록 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-21_

사용자 등록 보고서는 지정 된 기간 (매시간, 매일, 매주, 매월) 동안 Microsoft Lync Server 2013에 로그온 한 사용자 수에 대 한 정보를 사용자 로그온 활동에 대 한 개요로 제공 합니다. 보고서는 로그인 한 사용자 수만 알려줍니다. 로그온 한 사용자에 게 *는* 알려 주지 않습니다. 모니터링 보고서는 특정 사용자가 Lync Server 2013를 사용 하 고 있는지 여부에 대 한 정보를 제공 하지 않습니다. 그러나 사용자 활동 보고서를 사용 하 여 대략적인 예측 한 사용자 정보를 얻을 수 있습니다.

사용자 로그온에 대 한 정보를 제공할 때 사용자 등록 보고서는 두 가지 중요 한 차이점을 가져옵니다. 먼저, 로그온을 두 가지 기본 범주인 내부 로그온 및 외부 로그온으로 나눕니다. 내부 로그온은 조직의 방화벽 (즉, 회사 네트워크에 연결 된 상태) 내부에서 로그온 한 사용자를 나타냅니다. 외부 로그온은 Edge 서버를 통해 방화벽 외부에서 로그온 한 사용자를 나타냅니다 (예를 들어 인터넷 카페에서 로그온 한 사용자가 외부 로그인으로 간주). 사용자가 방화벽 외부에서 로그온 하는 횟수를 알아야 하는 경우 사용자 등록 보고서에이 정보를 제공할 수 있습니다.

또한 사용자 등록 보고서에는 특정 기간 동안 발생 한 *활성* 사용자 수가 기록 됩니다. 활성 사용자는 IM (인스턴트 메시징) 세션을 진행 하거나, Lync 모임에 참가 하거나, 전화를 걸거나 받거나, 그 기간 동안 Lync Server를 사용 하는 사용자입니다. 이는 로그온 한 사용자와 다르며, 실제로 시스템을 사용 하지는 않습니다.

<div>

## <a name="accessing-the-user-registration-report"></a>사용자 등록 보고서에 액세스

모니터링 보고서 홈 페이지 에서만 사용자 등록 보고서에 액세스할 수 있습니다. 사용자 등록 보고서는 다른 보고서에 연결 되지 않습니다.

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a>사용자 등록 보고서를 최대한 활용 하기

Lync Server를 배포한 후에는 다음을 수행 합니다. 사용자가 실제로이 새로운 기술을 사용 하 고 있는지 어떻게 알 수 있습니까? 여기에는 몇 가지 제한 사항이 있지만,이 질문에 대 한 답은 사용자 등록 보고서를 통해 확인할 수 있습니다. 사용자가 Lync Server를 사용 하 고 있는지 여부를 확인 하려면 두 가지 작업을 수행 해야 합니다. 먼저, 사용자 등록 보고서에서 고유한 로그온 사용자 메트릭의 값을 가져옵니다. 이 값을 통해 Lync Server에 로그온 한 개별 사용자의 수를 알 수 있습니다.

비교 하 여 총 로그온 메트릭은 사용자가 Lync Server에 로그온 한 총 시간을 보여 줍니다. 예를 들어 한 날에: 진구 Myer에서 Lync Server 5 개를 서로 다른 시간으로 로그온 했다고 가정 합니다. 이 경우: 진구 Myer는 총 로그온 메트릭에 대해 5 개의 개별 로그온 세션으로 계산 되지만, 고유한 로그온 사용자 메트릭에 대해 하나의 로그온 사용자만 사용 됩니다. 마찬가지로 사용자가 여러 장치 또는 여러 위치에서 로그온 하는 것은 드문 일입니다. 예를 들어 사용자는 데스크톱 컴퓨터, 랩톱 컴퓨터를 사용 하 여 로그온 할 수 있으며 Lync Server에 자동으로 로그인 하는 IP 전화를 가질 수 있습니다. 이 예제에는 세 개의 로그온이 있는 하나의 고유 사용자가 있습니다.

총 로그온과 고유 로그온 간의 차이에 대 한 자세한 설명을 보려면 다음 표의 지정 된 기간에 대 한 로그온을 고려 하세요.


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
<td><p>: 진구 Myer</p></td>
<td><p>오전 7/7/2012 8:45</p></td>
</tr>
<tr class="even">
<td><p>: 진구 Myer</p></td>
<td><p>오전 7/7/2012 8:46</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>오전 7/7/2012 9:17</p></td>
</tr>
<tr class="even">
<td><p>: 진구 Myer</p></td>
<td><p>오전 7/7/2012 9:22</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>오전 7/7/2012 9:31</p></td>
</tr>
</tbody>
</table>


총 5 개의 로그온이 있다는 점에 유의 하십시오. 그러나: 진구 Myer (3 번 로그온 한 경우) 및 Pilar Ackerman (두 번 로그인 한)에는 두 가지 고유한 로그온 사용자만 있습니다. 이는 로그온과 고유 로그온 사용자 간의 차이입니다.

고유한 로그온 횟수를 아는 것 외에도 Lync Server에 대해 사용 하도록 설정 된 총 사용자 수를 알고 있어야 합니다. 이 값은 Lync Server 2013 관리 셸을 열고 다음 Windows PowerShell 명령을 실행 하 여 검색할 수 있습니다.

    (Get-CsUser).Count

앞의 명령이 1236 및 고유 로그온 사용자 메트릭을 반환 하는 경우 사용자가 Lync에 대해 거의 매일 시스템에 로그인 하는 것을 제안 하는 평균값 667 (즉, 667을 1236로 나눈 값이 설정 됨)이 반환 됩니다. ,이는 대략 54%입니다.

<div>


> [!WARNING]  
> 로그온 메트릭은 지정 된 기간에 실제로 로그온 한 사용자를 기록 한다는 점에 유의 하세요. 시스템에 이미 로그온 한 사용자를 추적 하지 않습니다. 예를 들어 고유한 로그온 사용자 메트릭이 667 로그온을 표시 하 고 1236 사용자가 있는 경우 사용자가 시스템에 로그온 하 고 있다는 것을 제안 합니다. 그러나 300 사용자가 로그온 데이터를 확인 하기 시작 했을 때 이미 시스템에 로그온 되었다고 가정 합니다. 이것은 실제로 거의 1000 사용자가 Lync Server에 로그인 한 것을 의미 하는데,이는 사용자의 80%에 가까운 것으로 간주 됩니다.



</div>

또한 고유한 로그온 사용자 값을 고유 활성 사용자 메트릭의 값과 비교 해야 합니다. 고유한 활성 사용자 메트릭은 Lync Server를 사용 하 여 사용자에 게 전화를 걸거나 Lync 모임에 참가 했거나 메신저 대화 세션에 참가 하는 것을 나타냅니다. 이는 사용자가 Windows를 시작할 때마다 자동으로 시작 되도록 Microsoft Lync 2013을 구성할 수 있기 때문에 유용한 정보입니다. 이 때문에 하루에 Windows에 로그온 할 때 Lync에 자동으로 로그인 하는 사용자 수가 많을 수 있지만,이 기간 동안에는 실제로 Lync Server를 사용 하지 않습니다.

또한 고유한 활성 사용자 메트릭은 사용자가 일반적으로 일이 끝날 때 창을 로그 오프 하지 않는 조직에서 보다 의미 있는 데이터를 제공 합니다. 대신 컴퓨터를 잠그고 Windows 및 Lync가 실행 되는 것을 유지 합니다. 이러한 상황에서는 사용자가 며칠 전에 로그인 하 고 로그 오프할 수 없기 때문에 하루에 몇 번의 로그온이 끝날 수가 있습니다. 그러나 고유한 활성 사용자는 사용자가 현재 Lync 또는 다른 Lync Server 클라이언트를 사용 중인지 여부를 알려줍니다.

</div>

<div>

## <a name="filters"></a>필터가

필터는 더욱 세밀 하 게 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있는 방법을 제공 합니다. 예를 들어 사용자 등록 보고서를 사용 하면 모든 등록자 풀 및 Edge 서버의 데이터를 보거나 개별 풀에 대 한 데이터를 볼 수 있습니다. 데이터 그룹화 방법을 선택할 수도 있습니다. 이 경우, 등록은 시간, 일, 주 또는 월로 그룹화 됩니다.

다음 표에는 사용자 등록 보고서와 함께 사용할 수 있는 필터가 나열 되어 있습니다.

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
<td><p>시간 범위의 종료 날짜 및 시간입니다. 시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</p>
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
<p>시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값의 수만 표시 됩니다. 예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>풀</strong></p></td>
<td><p>등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다. 개별 풀을 선택 하거나 <strong>[모두]</strong> 를 선택 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>매트릭스

다음 표에는 사용자 등록 보고서에 제공 되는 정보가 나열 되어 있습니다.

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
<th>이 항목을 정렬할 수 있나요?</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>마다</strong></p>
<p><strong>Daily</strong></p>
<p><strong>매주</strong></p>
<p><strong>월간</strong></p></td>
<td><p>아니요</p></td>
<td><p>필터 도구 모음에서 선택한 시간 간격을 나타냅니다. 해당 되는 경우 지정 된 시간 간격을 클릭 하 여 해당 간격에 대 한 세부 정보를 볼 수 있습니다. 예를 들어 일일 기간을 사용 하는 경우 7/7/2012을 클릭 하면 해당 날짜에 대 한 사용자 등록 작업을 시간별로 분류 하 여 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>총 로그온 횟수</strong></p></td>
<td><p>아니요</p></td>
<td><p>성공한 로그온 세션의 총 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>내부 로그온</strong></p></td>
<td><p>아니요</p></td>
<td><p>내부 네트워크 내의 총 로그온 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>외부 로그온</strong></p></td>
<td><p>아니요</p></td>
<td><p>Edge 서버를 사용 하는 내부 네트워크 외부의 총 로그온 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>고유한 로그온 사용자</strong></p></td>
<td><p>아니요</p></td>
<td><p>하나 이상의 로그온 세션이 있는 총 사용자 수입니다. 여러 로그온 세션이 있는 사용자는 단일 로그온 세션만 갖는 사람과 같은 사용자로 간주 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>고유한 활성 사용자</strong></p></td>
<td><p>아니요</p></td>
<td><p>피어 투 피어 또는 회의 세션에 참여 한 총 사용자 수입니다. 여러 세션이 있는 사용자는 단일 세션을 소유한 사람과 같은 사용자로 간주 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

