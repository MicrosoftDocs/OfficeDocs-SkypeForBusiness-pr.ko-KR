---
title: 'Lync Server 2013: 위치 데이터베이스 채우기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Populate the location database
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413069(v=OCS.15)
ms:contentKeyID: 48185939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08c1718c3d7ffdc79b82ac34016e79bf647ae6f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a>Lync Server 2013에서 위치 데이터베이스 채우기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-17_

네트워크 내에서 클라이언트를 자동으로 찾으려면 먼저 네트워크 요소를 도시 (즉, 거리) 주소로 매핑하는 network *wiremap 매핑*으로 위치 데이터베이스를 채워야 합니다. 서브넷, 무선 액세스 지점, 스위치 및 포트를 사용 하 여 wiremap 매핑 정의를 할 수 있습니다.

다음 표에 설명 된 열 서식이 포함 된 CSV 파일을 사용 하 여 위치 데이터베이스에 개별적으로 또는 대량으로 주소를 추가할 수 있습니다.

비상 위치 Id 번호 (ELIN) 게이트웨이를 사용 하는 경우 각 위치에 대 한 **CompanyName** 필드에 elin을 포함 합니다. 각각 세미콜론으로 구분 하 여 각 위치에 여러 개의 ELINs을 포함할 수 있습니다.


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
<td><p><strong>무선 액세스 지점의</strong></p></td>
<td><p>&lt;BSSID&gt;,&lt;설명&gt;,&lt;위치&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</p>
<p>... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;시&gt;,&lt;주&gt;,&lt;우편&gt;,&lt;국가&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>서브넷</strong></p></td>
<td><p>&lt;서브넷&gt;,&lt;설명&gt;,&lt;위치&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</p>
<p>... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;시&gt;,&lt;주&gt;,&lt;우편&gt;,&lt;국가&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>포트</strong></p></td>
<td><p>&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;설명&gt;,&lt;위치&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,...</p>
<p>... &lt;Predirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;구&gt;/&lt;군&gt;/&lt;시&gt;,&lt;주, PostalCode, 국가&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>바꾸려면</strong></p></td>
<td><p>&lt;ChassisID&gt;,&lt;설명&gt;,&lt;위치&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</p>
<p>... &lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;postdirectional&gt;,&lt;시&gt;,&lt;주&gt;,&lt;우편&gt;,&lt;국가&gt;</p></td>
</tr>
</tbody>
</table>


위치 데이터베이스를 채우지 않고 위치 정책에 **필요한 위치가** **예** 또는 **부인**로 설정 된 경우 클라이언트는 사용자에 게 위치를 수동으로 입력 하 라는 메시지를 표시 합니다.

위치 데이터베이스를 채우는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.

  - **Get-CsLisSubnet**

  - **Set-CsLisSubnet**

  - 제거-CsLisSubnet

  - **Get-CsLisWirelessAccessPoint**

  - **Set-CsLisWirelessAccessPoint**

  - **제거-CsLisWirelessAccessPoint**

  - **Get-CsLisSwitch**

  - **Set-CsLisSwitch**

  - **제거-CsLisSwitch**

  - **Get-CsLisPort**

  - **Set-CsLisPort**

  - **제거-CsLisPort**

<div>

## <a name="to-add-network-elements-to-the-location-database"></a>위치 데이터베이스에 네트워크 요소를 추가 하려면

1.  다음 cmdlet을 실행 하 여 위치 데이터베이스에 서브넷 위치를 추가 합니다.
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    게이트웨이에서 ELIN 대해 CompanyName 필드에 ELIN 넣으십시오. 두 개 이상의 ELIN을 포함할 수 있습니다. 예를 들면 다음과 같습니다.
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    또는 다음 cmdlet을 실행 하 고 "subnet. .csv" 이라는 파일을 사용 하 여 서브넷 위치를 대량으로 업데이트할 수 있습니다.
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  다음 cmdlet을 실행 하 여 위치 데이터베이스에 무선 위치를 추가 합니다.
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    또는 다음 cmdlet을 실행 하 고 "waps" 라는 파일을 사용 하 여 무선 위치를 대량으로 업데이트할 수 있습니다.
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  다음 cmdlet을 실행 하 여 위치 데이터베이스에 전환 위치를 추가 합니다.
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    또는 다음 cmdlet을 실행 하 고 "스위치인 .csv" 라는 파일을 사용 하 여 스위치 위치를 대량으로 업데이트할 수 있습니다.
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  다음 cmdlet을 실행 하 여 위치 데이터베이스에 포트 위치를 추가 합니다.
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    PortIDSubType의 기본값은 LocallyAssigned입니다. 또한이를 인터페이스 별칭 또는 InterfaceName로 설정할 수 있습니다.
    
    또는 다음 cmdlet을 실행 하 고 "포트인 .csv" 이라는 파일을 사용 하 여 포트 위치를 대량으로 업데이트할 수 있습니다.
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

