---
title: 'Lync Server 2013: 위치 데이터베이스 채우기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Populate the location database
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413069(v=OCS.15)
ms:contentKeyID: 48185939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0216cada44f2512e33a0b33b627ed9a6d6582cda
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a>Lync Server 2013에서 위치 데이터베이스 채우기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-17_

네트워크에서 클라이언트를 자동으로 찾으려면 먼저 네트워크 요소를 구/군/시 주소로 매핑하는 네트워크 *와이어맵(wiremap)* 으로 위치 데이터베이스를 채워야 합니다. 서브넷, 무선 액세스 지점, 스위치 및 포트를 사용하여 와이어맵(wiremap)을 정의할 수 있습니다.

위치 데이터베이스에는 주소를 개별적으로 추가하거나 다음 표에 설명된 열 형식이 포함된 CSV 파일을 사용하여 일괄적으로 추가할 수 있습니다.

ELIN(Emergency Location Identification Number) 게이트웨이를 사용하는 경우 각 위치의 **CompanyName** 필드에 ELIN을 포함합니다. 각 위치마다 세미콜론으로 구분하여 여러 ELIN을 포함할 수 있습니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>네트워크 요소</th>
<th>필수 열</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>무선 액세스 지점</strong></p></td>
<td><p>&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</p>
<p>... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;구&gt;/&lt;군&gt;/&lt;시&gt;,&lt;시/도, PostalCode, 국가&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>서브넷</strong></p></td>
<td><p>&lt;서브넷&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</p>
<p>... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;구&gt;/&lt;군&gt;/&lt;시&gt;,&lt;시/도, PostalCode, 국가&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>Port</strong></p></td>
<td><p>&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,...</p>
<p>... &lt;Predirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;구&gt;/&lt;군&gt;/&lt;시&gt;,&lt;PostalCode, 국가&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Switch</strong></p></td>
<td><p>&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</p>
<p>... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;구&gt;/&lt;군&gt;/&lt;시&gt;,&lt;시/도, PostalCode, 국가&gt;</p></td>
</tr>
</tbody>
</table>


위치 정책에서 **위치 필요**가 **예**나 **고지 사항**으로 설정되었을 때 위치 데이터베이스를 채우지 않으면 위치를 수동으로 입력하라는 메시지가 클라이언트에 표시됩니다.

위치 데이터베이스를 채우는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.

  - **CsLisSubnet**

  - **CsLisSubnet**

  - CsLisSubnet을 제거 합니다.

  - **CsLisWirelessAccessPoint**

  - **CsLisWirelessAccessPoint**

  - **CsLisWirelessAccessPoint을 제거 합니다.**

  - **CsLisSwitch**

  - **CsLisSwitch**

  - **CsLisSwitch을 제거 합니다.**

  - **CsLisPort**

  - **CsLisPort**

  - **CsLisPort을 제거 합니다.**

<div>

## <a name="to-add-network-elements-to-the-location-database"></a>위치 데이터베이스에 네트워크 요소를 추가하려면

1.  다음 cmdlet를 실행하여 위치 데이터베이스에 서브넷 위치를 추가합니다.
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    ELIN 게이트웨이의 경우, CompanyName 필드에 ELIN을 추가합니다. 두 개 이상의 ELIN을 포함할 수 있습니다. 예를 들면 다음과 같습니다.
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    또는 다음 cmdlet를 실행하고 'subnets.csv' 파일을 사용하여 서브넷 위치를 일괄적으로 업데이트할 수도 있습니다.
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  다음 cmdlet를 실행하여 위치 데이터베이스에 무선 위치를 추가합니다.
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    또는 다음 cmdlet를 실행하고 csv 파일 ‘waps.csv’를 사용하여 무선 위치를 일괄적으로 업데이트할 수 있습니다.
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  다음 cmdlet를 실행하여 위치 데이터베이스에 스위치 위치를 추가합니다.
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    또는 다음 cmdlet를 실행하고 csv 파일 ‘switches.csv’를 사용하여 스위치 위치를 일괄적으로 업데이트할 수 있습니다.
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  다음 cmdlet를 실행하여 위치 데이터베이스에 포트 위치를 추가합니다.
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    PortIDSubType의 기본값은 LocallyAssigned이며, 이 값을 InterfaceAlias 또는 InterfaceName으로 설정할 수도 있습니다.
    
    또는 다음 cmdlet를 실행하고 'ports.csv' 파일을 사용하여 포트 위치를 일괄적으로 업데이트할 수도 있습니다.
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

