---
title: 'Lync Server 2013: 네트워크 지역, 사이트 및 서브넷 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04c39a18147bad3f84bd345ec0a56b606db4cae4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a>Lync Server 2013에서 네트워크 지역, 사이트 및 서브넷 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-03-12_

엔터프라이즈 음성이 배포 되 면 다음을 구성 해야 합니다.

  - 네트워크 지역

  - 네트워크 사이트

  - 네트워크 서브넷

<div>

## <a name="define-network-regions"></a>네트워크 지역 정의

Lync Server Windows PowerShell 명령, 새 CsNetworkRegion 또는 Lync Server 제어판을 사용 하 여 네트워크 지역을 정의 합니다.

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

자세한 내용은 [새 CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)을 참조 하세요.

이 예제에서는 다음 Windows PowerShell 명령은이 시나리오에 정의 된 네트워크 지역 (지역 1 (인도))을 보여 줍니다.

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a>네트워크 사이트 정의

Lync Server Windows PowerShell 명령, 새 CsNetworkSite 또는 Lync Server 제어판을 사용 하 여 네트워크 사이트를 정의 합니다.

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

자세한 내용은 [새 CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)를 참조 하세요.

이 예제에서는 다음 표 및 Lync Server Windows PowerShell 명령은이 시나리오에 정의 된 네트워크 사이트를 보여 줍니다. 이 표에는 위치 기반 라우팅과 관련 하 여 설명 하는 설정만 나와 있습니다.

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>사이트 1(뉴델리)</th>
<th>Site 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>사이트 ID</p></td>
<td><p>사이트 1(뉴델리)</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>지역 ID</p></td>
<td><p>지역 1 (인도)</p></td>
<td><p>지역 1 (인도)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a>네트워크 서브넷 정의

Lync Server Windows PowerShell 명령, 새 CsNetworkSubnet 또는 Lync Server 제어판을 사용 하 여 네트워크 서브넷을 정의 하 고 네트워크 사이트에 할당 합니다.

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

자세한 내용은 [새 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)을 참조 하세요.

이 예제에서 다음 표 및 Windows PowerShell 명령은이 시나리오에 정의 된 네트워크 사이트, 뉴델리 및 Hyderabad 네트워크 서브넷을 할당 하는 방법을 보여 줍니다. 이 표에는 위치 기반 라우팅과 관련 하 여 설명 하는 설정만 나와 있습니다.

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>사이트 1(뉴델리)</th>
<th>Site 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>서브넷 ID</p></td>
<td><p>192.168.0.0</p></td>
<td><p>192.168.1.0</p></td>
</tr>
<tr class="even">
<td><p>마스킹하</p></td>
<td><p>fps</p></td>
<td><p>fps</p></td>
</tr>
<tr class="odd">
<td><p>사이트 ID</p></td>
<td><p>사이트 1(뉴델리)</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 위치 기반 라우팅 구성](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

