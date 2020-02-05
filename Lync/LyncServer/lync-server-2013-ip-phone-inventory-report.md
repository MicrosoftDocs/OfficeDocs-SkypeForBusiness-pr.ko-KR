---
title: 'Lync Server 2013: IP 전화 인벤토리 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fb9bb9a3ae48c8bf2fc9a5122e1b8004e0f6019
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a>Lync Server 2013의 IP 전화 인벤토리 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-12_

IP 전화 재고 보고서는 조직에서 현재 사용 중인 IP 전화에 대 한 정보를 보고 합니다. IP 인벤토리 보고서는 지정 된 보고 기간 동안 실제로 사용 된 IP 전화의 세부 목록을 제공 합니다. 그 외에,이 보고서를 통해 이전에는 오래 된 구형 전화기를 사용 하 고 있거나 교체 해야 하는지 여부를 관리자에 게 알릴 수 있습니다. 또한 거의 사용 하지 않는 조직에 부담이 큰 전화가 있다는 사실을 관리자에 게 알릴 수 있습니다. 이러한 종류의 정보는 새 전화를 구입 하거나 기존 전화를 재배포할 때 유용할 수 있습니다. (예를 들어, 휴대폰을 거의 사용 하지 않는 사용자가 전화기를 자주 사용 하는 사용자와 다른 사람으로 전환 하 라는 메시지가 표시 될 수 있습니다.)

실제 인벤토리 보고서로 사용 되는 경우에는이 보고서에 몇 가지 제한 사항이 있습니다. 한 가지 방법으로 IP 전화 보고서는 지정 된 기간 동안 Lync Server에 로그온 한 모든 전화기를 마지막 로그온 시간을 기준으로 정렬 하 여 표시 합니다. 지정 된 기간에 휴대폰에서 로그온 하지 않은 경우에는 목록 보고서에 해당 시간이 표시 되지 않습니다. 이는 시작 하기 전에 로그온 하 고 지정 된 시간 간격 동안 계속 로그온 한 전화를 포함 합니다. 예를 들어 2012 년 7 월부터 모든 전화 인벤터리를 보고 싶을 때 또한 여러 전화기가 2012 년 6 월 30 일에 Lync Server에 로그온 했 고, 7 월 1 일부로 계속 로그온 되어 있다고 가정 합니다. 해당 전화는 7 월 1 일의 인벤터리 보고서에 표시 되지 않습니다.

또한 인벤터리 보고서에는 조직에서 더 이상 사용 하지 않는 전화가 포함 될 수 있다는 점에 유의 해야 합니다. 예를 들어, 2012 년 7 월 1 일에 시스템에 로그온 한 Fabrikam 전화가 여러 개 있다고 가정 합니다. 5 일 후에 조직에서 해당 Fabrikam 전화를 모두 제거 하 고 최신 Contoso 모델로 바꿨습니다. Fabrikam 전화는 7 월 동안 시스템에 로그온 했기 때문에 "인벤터리" 보고서에 계속 표시 됩니다.

또한 IP 전화 인벤터리 보고서에는 다양 한 유형의 휴대폰에 대 한 요약 합계가 보고 되지 않습니다. 예를 들어 105 Polycom CX600 휴대폰을 사용 하 고 있다고 가정 합니다. 이 보고서는 귀하에 게 이러한 전화의 105 있다는 사실을 알려 주지 않습니다. 대신 Polycom Cx600에 대 한 105 별도의 항목만 표시 됩니다. Polycom Cx600에 대 한 105 항목이 있는지 확인 하는 유일한 방법은 각 항목의 수를 수동으로 계산 하는 것입니다.

<div>


> [!WARNING]  
> 또는 데이터를 내보내고 Microsoft Excel 또는 Windows PowerShell을 사용 하 여 해당 횟수를 계산 합니다.



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a>IP 전화 인벤토리 보고서에 액세스

모니터링 보고서 홈 페이지에서 IP 전화 인벤터리 보고서에 액세스할 수 있습니다. 사용자 URI 메트릭을 클릭 하면 해당 사용자의 사용자 활동 보고서에 액세스할 수 있습니다. 피어 투 피어 통화에 대 한 마지막 활동 메트릭을 클릭 하면 피어 투 피어 세션 세부 정보 보고서로 이동 합니다. 회의에 대해 동일한 메트릭을 클릭 하면 회의 세부 정보 보고서로 이동 합니다.

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>IP 전화 인벤토리 보고서를 최대한 활용 하기

특정 종류의 휴대폰에 대 한 사용 현황 정보에 관심이 있는 경우 (예: "Polycom CX600 휴대폰을 사용 하는 사용자는 빈도") 해당 특정 유형의 휴대폰을 기준으로 필터링 하 여 해당 정보를 IP 전화 재고 보고서에서 직접 확인할 수 있습니다. 그러나 모든 휴대폰에 대 한 요약 정보를 원하는 경우 (Polycom CX600를 사용 하는 사용자 수), LG-Nortel IP8540 등을 사용 하는 경우, 데이터를 내보내고 다른 응용 프로그램 (예: Windows PowerShell)을 사용 하 여 해당 유형의 작업을 수행 해야 합니다. 분석. 예를 들어 데이터를 쉼표로 구분 된 값 파일 (\\C: data\\IP\_Phone\_의\_보고서 .csv)로 내보내야 한다고 가정 합니다. 이 경우 다음 두 명령을 사용 하 여 모든 휴대폰에 대 한 요약 데이터를 제공할 수 있습니다.

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

이는 다음과 같은 데이터를 반환 합니다.

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

마찬가지로,이 두 명령어는 시스템에 로그온 했지만 실제로는 전화를 거는 데 사용 되지 않은 것을 알려 줍니다 (마지막 활동 메트릭의 값이 비어 있는 경우 마지막 작업이 없음을 나타냄).

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

이것은 사용 되지 않은 각 전화기에 대해 다음과 비슷한 데이터를 반환 합니다.

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

Ip 휴대폰의 MAC 주소를 사용 하는 또 다른 흥미로운 방법은 MAC 주소 텍스트 상자에 해당 주소를 입력 하 여 해당 전화기를 마지막으로 사용한 사용자를 찾을 수 있습니다. 그러면 IP 전화 목록 보고서가 해당 전화기로 마지막으로 로그인 한 사용자의 SIP 주소를 다시 보고 합니다 (다른 항목 중). 또는 사용자의 SIP 주소 (사용자 URI 접두사 상자)를 입력 하 여 해당 사용자가 사용한 모든 전화를 찾을 수 있습니다.

</div>

<div>

## <a name="filters"></a>필터가

필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다. 예를 들어 IP 전화 인벤터리를 사용 하 여 특정 회사 또는 특정 버전의 휴대폰으로 제조 된 전화만 볼 수 있습니다. 데이터 그룹화 방법을 선택할 수도 있습니다. 이 경우, 등록은 시, 일, 주 또는 월로 그룹화 됩니다.

다음 표에는 IP 전화 인벤토리 보고서에 사용할 수 있는 필터가 나와 있습니다.

### <a name="ip-phone-inventory-report-filters"></a>IP 전화 인벤터리 보고서 필터

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
<td><p><strong>제조업체</strong></p></td>
<td><p>IP 전화기를 제조 하는 회사의 이름입니다. 이 필터의 값은 현재 데이터베이스에 있는 IP 전화를 기준으로 자동으로 채워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>하드웨어 버전</strong></p></td>
<td><p>IP 전화의 버전 번호입니다. 제조업체 및 하드웨어 버전 필터를 사용 하 여 특정 유형의 휴대폰을 고유 하 게 식별할 수 있습니다. 이 필터의 값은 현재 데이터베이스에 있는 IP 전화를 기준으로 자동으로 채워집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>사용자 에이전트</strong></p></td>
<td><p>IP 휴대폰에서 사용 하는 소프트웨어의 식별자입니다. 이 필터에 대 한 값은 현재 데이터베이스에 있는 IP 전화를 기준으로 자동으로 채워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>MAC 주소</strong></p></td>
<td><p>IP 휴대폰의 네트워크 인터페이스에 대 한 고유 식별자입니다. MAC (미디어 액세스 제어) 주소는 일반적으로 휴대폰을 제조 하 고 디바이스 하드웨어에 하드 연결 되어 있는 시점에 할당 됩니다.</p>
<p>특정 MAC 주소와 관련 된 레코드를 검색 하려면 해당 주소를 입력 하기만 하면 됩니다. 예를 들면 다음과 같습니다.</p>
<p>00-08-5D-16-16-48</p>
<p>전체 주소를 입력 해야 합니다. 일부 주소 (예: 00-08-5D)는 데이터를 반환 하지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>일 전 마지막 활동</strong></p></td>
<td><p>다음 값 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>1천만</p></li>
<li><p>명</p></li>
<li><p>30</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>마지막 로그 인 날짜 이전 시간</strong></p></td>
<td><p>다음 값 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>1천만</p></li>
<li><p>명</p></li>
<li><p>30</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>사용자 URI 접두사</strong></p></td>
<td><p>IP 전화를 사용한 사용자의 SIP 주소입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>매트릭스

다음 표에는 IP 전화 인벤토리 보고서에 제공 되는 정보가 나열 되어 있습니다.

### <a name="ip-phone-inventory-report-metrics"></a>IP 전화 인벤토리 보고서 메트릭

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
<td><p><strong>제조업체</strong></p></td>
<td><p>예</p></td>
<td><p>IP 전화기를 제조 하는 회사의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>하드웨어 버전</strong></p></td>
<td><p>예</p></td>
<td><p>IP 전화기의 버전 번호입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MAC 주소</strong></p></td>
<td><p>예</p></td>
<td><p>IP 휴대폰의 네트워크 인터페이스에 대 한 고유 식별자입니다. MAC 주소는 일반적으로 휴대폰을 제조할 때 할당 되며 디바이스 하드웨어에 하드 연결 되어 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>사용자 URI</strong></p></td>
<td><p>예</p></td>
<td><p>IP 전화를 사용한 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>사용자 에이전트</strong></p></td>
<td><p>예</p></td>
<td><p>IP 휴대폰에서 사용 하는 소프트웨어의 식별자입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>마지막 로그온 시간</strong></p></td>
<td><p>예</p></td>
<td><p>IP 전화가 Lync Server에 마지막으로 로그인 한 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>마지막 로그 인 시간</strong></p></td>
<td><p>예</p></td>
<td><p>IP 전화가 Lync Server에서 마지막으로 로그 오프 한 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>마지막 활동</strong></p></td>
<td><p>예</p></td>
<td><p>IP 전화기를 마지막으로 사용한 날짜 및 시간입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

