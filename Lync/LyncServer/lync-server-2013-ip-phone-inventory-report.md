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
ms.openlocfilehash: 5566f5e38608d2802c8ad699e3599f70c87be4e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a>Lync Server 2013의 IP 전화 인벤토리 보고서

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-12_

IP 전화 인벤토리 보고서는 조직에서 현재 사용 중인 IP 전화에 대 한 정보를 보고 합니다. IP 인벤토리 보고서에는 지정 된 보고 기간 동안 실제로 사용 된 IP 전화의 자세한 목록이 제공 됩니다. 무엇 보다도이 보고서를 통해 관리자는 기존에 사용 중인 오래 된 전화를 교체 해야 하는지 여부를 알 수 있습니다. 또한 조직에 거의 사용 되지 않는 고가의 전화가 있음을 관리자에 게 알릴 수 있습니다. 이러한 유형의 정보는 새 전화를 구입 하거나 기존 전화를 재배포할 때 유용할 수 있습니다. 예를 들어 전화를 많이 사용 하는 사용자가 휴대폰을 자주 사용 하는 사용자와 휴대폰을 교체 하 라는 메시지가 표시 될 수 있습니다.

이 보고서는 실제 인벤토리 보고서로 사용 될 때 몇 가지 제한 사항이 있음을 유의 해야 합니다. 예를 들어 IP 전화 보고서에는 지정 된 기간 동안 Lync Server에 로그온 한 모든 전화가 마지막 로그온 시간을 기준으로 정렬 되어 표시 됩니다. 지정 된 기간 동안 전화가 로그온 하지 않은 경우에는 해당 장치가 인벤토리 보고서에 나열 되지 않습니다. 시작 하기 전에 로그온 하 여 지정 된 시간 간격 동안 계속 로그온 한 전화를 포함 합니다. 예를 들어 2012 년 7 월의 모든 전화 인벤토리를 확인 하려는 경우를 가정해 보겠습니다. 또한 여러 전화가 Lync Server에 2012 년 6 월 30 일에 로그온 하 여 7 월 1 일부 터 계속 로그온 되어 있다고 가정해 보겠습니다. 해당 전화가 7 월 1 일에 대 한 인벤토리 보고서에 표시 되지 않습니다.

또한 조직에서 더 이상 사용 하지 않는 전화가 인벤토리 보고서에 포함 될 수 있다는 점에 유의 해야 합니다. 예를 들어 시스템에 여러 Fabrikam 전화기가 2012 년 7 월 1 일에 로그온 했다고 가정 합니다. 5 일 후 조직에서 이러한 모든 Fabrikam 전화를 제거 하 고 새로운 Contoso 모델로 교체 했습니다. Fabrikam 전화는 7 월 한 달 동안 시스템에 로그온 했기 때문에 "인벤터리" 보고서에 계속 표시 됩니다.

또한 IP 전화 인벤토리 보고서에는 다양 한 유형의 휴대폰에 대 한 요약 합계가 보고 되지 않습니다. 예를 들어 105 Polycom CX600 휴대폰을 가정해 보겠습니다. 이 보고서에는 이러한 전화의 105이 있음을 알리는 메시지가 나타나지 않습니다. 대신, Polycom Cx600에 대해 105 별도의 항목을 표시 하는 것이 좋습니다. Polycom Cx600에 대 한 항목의 수가 105 개 있다는 것을 확인 하는 유일한 방법은 이러한 각 항목의 수를 수동으로 계산 하는 것입니다.

<div>


> [!WARNING]  
> 또는 데이터를 내보낸 다음 Microsoft Excel 또는 Windows PowerShell을 사용 하 여 해당 횟수를 계산 합니다.



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a>IP 전화 인벤토리 보고서 액세스

IP 전화 인벤토리 보고서는 모니터링 보고서 홈 페이지에서 액세스 합니다. 사용자 URI 메트릭을 클릭 하면 해당 사용자에 대 한 사용자 활동 보고서에 액세스할 수 있습니다. 피어 투 피어 통화에 대 한 마지막 활동 메트릭을 클릭 하면 피어 투 피어 세션 세부 정보 보고서로 이동 됩니다. 회의에 대해 같은 메트릭을 클릭 하면 전화 회의 정보 보고서로 이동 합니다.

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>IP 전화 인벤토리 보고서의 효과적인 활용

특정 유형의 휴대폰에 대 한 사용 현황 정보에 관심이 있는 경우 (예: "Polycom CX600 휴대폰을 사용 하는 사용자는?") 해당 특정 유형의 전화를 필터링 하 여 IP 전화 인벤토리 보고서에서 해당 정보를 직접 확인할 수 있습니다. 그러나 모든 휴대폰에 대 한 요약 정보 (Polycom CX600을 사용 하는 사용자 수, LG-Nortel IP8540 등)를 원하는 경우에는 데이터를 내보내고 다른 응용 프로그램 (예: Windows PowerShell)을 사용 하 여 해당 유형의 작업을 수행 해야 합니다. 분석할. 예를 들어 데이터를 쉼표로 구분 된 값 파일 (\\C: data\\IP\_전화\_인벤토리\_보고서 .csv)로 내보내는 경우를 가정해 보겠습니다. 이 경우 다음 두 명령을 사용 하 여 모든 휴대폰에 대 한 요약 데이터를 제공할 수 있습니다.

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

이 명령을 실행하면 다음과 같은 데이터가 반환됩니다.

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

마찬가지로, 이러한 두 명령은 시스템에 로그온 되어 있지만 실제로 통화를 수행 하는 데 사용 되지 않은 경우 (마지막 활동 메트릭 값이 비어 있는 경우 마지막 활동이 없음을 나타내는 경우)를 나타냅니다.

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

이는 사용 되지 않은 각 전화에 대해 다음과 비슷한 데이터를 반환 합니다.

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

Ip 전화 인벤토리 보고서를 사용 하는 또 다른 흥미로운 방법은 다음과 같습니다. IP 전화의 MAC 주소가 있는 경우 MAC 주소 텍스트 상자에 해당 주소를 입력 하기만 하면 해당 전화를 마지막으로 사용한 사용자를 찾을 수 있습니다. 그러면 IP 전화 인벤토리 보고서에서 이전에 해당 전화기로 로그온 한 사용자의 SIP 주소를 보고 합니다. 또는 사용자 SIP 주소 (사용자 URI 접두사 상자)를 입력 하 여 해당 사용자가 사용 하는 모든 전화를 찾을 수 있습니다.

</div>

<div>

## <a name="filters"></a>필터

필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 IP 전화 재고를 사용 하면 특정 회사에서 제조한 전화나 해당 휴대폰의 특정 버전을 볼 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 등록은 시, 일, 주 또는 월별로 그룹화 됩니다.

다음 표에서는 IP 전화 인벤토리 보고서에서 사용할 수 있는 필터를 보여 줍니다.

### <a name="ip-phone-inventory-report-filters"></a>IP 전화 인벤토리 보고서 필터

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
<p>주는 항상 일요일부터 토요일까지로 실행됩니다.</p></td>
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
<td><p><strong>회사</strong></p></td>
<td><p>IP 전화를 제조한 회사의 이름입니다. 이 필터의 값은 현재 데이터베이스에 있는 IP 전화를 기반으로 자동으로 채워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>하드웨어 버전</strong></p></td>
<td><p>IP 전화의 버전 번호입니다. 제조업체 및 하드웨어 버전 필터를 사용 하 여 특정 유형의 전화를 고유 하 게 식별할 수 있습니다. 이 필터의 값은 현재 데이터베이스에 있는 IP 전화를 기반으로 자동으로 채워집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>사용자 에이전트</strong></p></td>
<td><p>IP 전화에 사용 된 소프트웨어의 식별자입니다. 이 필터의 값은 현재 데이터베이스에 있는 IP 전화를 기반으로 자동으로 채워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>MAC 주소</strong></p></td>
<td><p>IP 전화의 네트워크 인터페이스에 대 한 고유 식별자입니다. MAC (미디어 액세스 제어) 주소는 일반적으로 전화기가 제조 되는 시점에 할당 되며 장치 하드웨어에 유선으로 연결 됩니다.</p>
<p>특정 MAC 주소와 관련 된 레코드를 검색 하려면 해당 주소를 입력 하면 됩니다. 예:</p>
<p>00-08-5D-16-16-48</p>
<p>전체 주소를 입력 해야 합니다. 일부 주소 (예: 00-08-5D)는 데이터를 반환 하지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>다음 일 이전의 마지막 활동</strong></p></td>
<td><p>다음 값 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>10 </p></li>
<li><p>20cm(8</p></li>
<li><p>kb</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>다음 일 이전의 마지막 로그 오프 시간</strong></p></td>
<td><p>다음 값 중 하나를 선택 합니다.</p>
<ul>
<li><p>모든</p></li>
<li><p>10 </p></li>
<li><p>20cm(8</p></li>
<li><p>kb</p></li>
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

## <a name="metrics"></a>선별한

다음 표에서는 IP 전화 인벤토리 보고서에 제공 되는 정보를 보여 줍니다.

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
<th>이 항목에 대한 정렬 가능 여부</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>회사</strong></p></td>
<td><p>예</p></td>
<td><p>IP 전화를 제조한 회사의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>하드웨어 버전</strong></p></td>
<td><p>예</p></td>
<td><p>IP 전화의 버전 번호입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MAC 주소</strong></p></td>
<td><p>예</p></td>
<td><p>IP 전화의 네트워크 인터페이스에 대 한 고유 식별자입니다. 일반적으로 MAC 주소는 전화가 제조 되는 시점에 할당 되며 장치 하드웨어에 유선으로 연결 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>사용자 URI</strong></p></td>
<td><p>예</p></td>
<td><p>IP 전화를 사용한 사용자의 SIP 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>사용자 에이전트</strong></p></td>
<td><p>예</p></td>
<td><p>IP 전화에 사용 된 소프트웨어의 식별자입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>마지막 로그온 시간</strong></p></td>
<td><p>예</p></td>
<td><p>IP 전화가 Lync Server에 마지막으로 로그온 한 날짜 및 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>마지막 로그 오프 시간</strong></p></td>
<td><p>예</p></td>
<td><p>IP 전화가 Lync Server에서 마지막으로 로그 오프 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>마지막 활동</strong></p></td>
<td><p>예</p></td>
<td><p>IP 전화를 마지막으로 사용한 날짜 및 시간입니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

