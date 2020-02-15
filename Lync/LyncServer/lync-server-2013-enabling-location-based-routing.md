---
title: 'Lync Server 2013: 위치 기반 라우팅을 사용 하도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b254e7e05a0ac2117b12a0004435898069059f53
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a>Lync Server 2013에서 위치 기반 라우팅 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-04-26_

Enterprise Voice가 배포 되 고 네트워크 지역에 연결 되 면 사이트와 서브넷이 정의 되 고 위치 기반 라우팅을 사용 하도록 설정할 수 있습니다. 다음 Enterprise Voice 요소에 대해 위치 기반 라우팅을 사용 하도록 설정 해야 합니다.

  - 네트워크 사이트

  - 트렁크 구성

  - 음성 정책

  - 라우팅 구성

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>네트워크 사이트에 대 한 위치 기반 라우팅 사용

Enterprise Voice를 배포 하 고 네트워크 사이트를 구성한 후에는 위치 기반 라우팅을 구성할 준비가 된 것입니다. 먼저 네트워크 사이트를 적절 한 PSTN 사용에 연결 하는 음성 라우팅 정책을 만듭니다. 음성 라우팅 정책에 PSTN 사용을 할당할 때는 위치 기반 라우팅 제한이 필요 하지 않은 지역에 있는 pstn 게이트웨이를 사이트 또는 PSTN 게이트웨이로 사용 하는 음성 경로와 연결 된 PSTN 사용량을 사용 해야 합니다. Lync Server Windows PowerShell 명령, Get-csvoiceroutingpolicy 또는 Lync Server 제어판을 사용 하 여 음성 라우팅 정책을 만듭니다.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

자세한 내용은 [get-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy)를 참조 하십시오.

이 예에서는 다음 표 및 Windows PowerShell 명령은 두 가지 음성 라우팅 정책 및이 시나리오에 정의 된 연결 된 PSTN 사용을 보여 줍니다. 위치 기반 라우팅과 관련 된 설정만 설명을 위해 표에 포함 되어 있습니다.

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>음성 라우팅 정책 1</th>
<th>음성 라우팅 정책 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>음성 정책 ID</p></td>
<td><p>뉴델리 voice 라우팅 정책</p></td>
<td><p>Hyderabad 음성 라우팅 정책</p></td>
</tr>
<tr class="even">
<td><p>PSTN 사용</p></td>
<td><p>뉴델리 usage, PBX Del usage, PBX Hyd usage</p></td>
<td><p>Hyderabad 사용 현황, PBX Hyd usage, PBX Del usage</p></td>
</tr>
</tbody>
</table>

  

다음으로, 해당 하는 네트워크 사이트에 대 한 위치 기반 라우팅을 구성 하 고 음성 라우팅 정책을 여기에 연결 합니다. Lync Server Windows PowerShell 명령, 새 CsNetworkSite를 사용 하 여 위치 기반 라우팅을 사용 하도록 설정 하 고 라우팅 제한을 적용 해야 하는 네트워크 사이트에 음성 라우팅 정책을 연결 합니다.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

이 예에서 다음 표에는 Lync Server Windows PowerShell을 사용 하 여이 시나리오에 정의 된 두 개의 서로 다른 네트워크 사이트 (Hyderabad 및 2)에 대 한 위치 기반 라우팅이 나와 있습니다. 위치 기반 라우팅과 관련 된 설정만 설명을 위해 표에 포함 되어 있습니다.

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


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
<th>사이트 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>사이트 이름</p></td>
<td><p>사이트 1(뉴델리)</p></td>
<td><p>사이트 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>EnableLocationBasedRouting</p></td>
<td><p>참</p></td>
<td><p>참</p></td>
</tr>
<tr class="odd">
<td><p>음성 라우팅 정책</p></td>
<td><p>뉴델리 voice 라우팅 정책</p></td>
<td><p>Hyderabad 음성 라우팅 정책</p></td>
</tr>
<tr class="even">
<td><p>서브넷</p></td>
<td><p>서브넷 1 (gbps)</p></td>
<td><p>서브넷 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a>위치 기반 라우팅 사용 트렁크

위치 기반 라우팅을 위해 트렁크 구성을 사용 하도록 설정 하려면 각 트렁크 또는 각 네트워크 사이트에 대해 트렁크 구성을 만들어야 합니다. Lync Server Windows PowerShell 명령 Get-cstrunkconfiguration를 사용 하 여 트렁크 구성을 만듭니다. 트렁크가 지정 된 시스템과 연결 된 경우 (즉, 게이트웨이 또는 PBX) 각 트렁크 구성을 수정 하 여 위치 기반 라우팅 제한을 사용 하도록 설정 해야 합니다.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

자세한 내용은 [get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)를 참조 하십시오.

이 예의 경우 다음 Windows PowerShell 명령은이 시나리오에 정의 된 배포의 각 트렁크에 대해 트렁크 구성을 하나씩 만드는 방법을 보여 줍니다.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

트렁크에 따라 줄기 구성을 구성한 후에는 Lync Server Windows PowerShell 명령 Get-cstrunkconfiguration을 사용 하 여 라우팅 제한을 적용 해야 하는 트렁크에 대 한 위치 기반 라우팅을 사용 하도록 설정할 수 있습니다. PSTN으로 통화를 라우팅하는 PSTN 게이트웨이로 통화를 라우팅하는 트렁크에 대 한 위치 기반 라우팅을 사용 하도록 설정 하 고 게이트웨이가 있는 네트워크 사이트를 연결 합니다.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

자세한 내용은 [get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)를 참조 하십시오.

이 예에서는 Hyderabad의 PSTN 게이트웨이와 연결 된 각 트렁크에 대해 위치 기반 라우팅을 사용 하도록 설정 되어 있습니다.

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

통화를 PSTN으로 라우트 하지 않는 트렁크에 대해 위치 기반 라우팅을 사용 하도록 설정 하지 마십시오. 그러나이 트렁크를 통해 연결 된 끝점에 대 한 PSTN 통화에 대해 위치 기반 라우팅 제한을 적용 해야 하는 경우에도 시스템을 사용 하는 네트워크 사이트에 트렁크를 연결 해야 합니다. 이 예에서는 Hyderabad에서 PBX 시스템과 연결 된 각 트렁크에 대해 위치 기반 라우팅을 사용 하도록 설정 되어 있지 않습니다.

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
PSTN으로 통화를 라우트 하지 않는 시스템에 연결 된 끝점 (즉, PBX)은 위치 기반 라우팅을 사용 하도록 설정 된 사용자의 Lync 끝점과 비슷한 제한이 적용 됩니다. 즉, 이러한 사용자는 사용자 위치에 관계 없이 Lync 사용자에 게 전화를 걸거나 받을 수 있습니다. 또한 시스템을 연결 하는 네트워크 사이트에 관계 없이 PSTN 네트워크로 통화를 라우팅하는 (즉, 다른 PBX에 연결 된 끝점) 다른 시스템과 주고받는 수신 전화를 걸 수 있습니다. PSTN 끝점을 포함 하는 모든 인바운드 통화, 아웃 바운드 통화, 통화 전송 및 착신 전환에는 위치 기반 라우팅 enforcements 적용 됩니다. 이러한 통화는 해당 시스템에 로컬로 정의 된 PSTN 게이트웨이를 사용 해야 합니다.

다음 표에서는 PSTN 게이트웨이 2 개와 PBX 시스템에 연결 된 2 개의 서로 다른 네트워크 사이트에 있는 네 가지 트렁크의 트렁크 구성을 보여 줍니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>이름</th>
<th>EnableLocationRestriction</th>
<th>NetworkSiteID</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>가 pstngateway: 트렁크 1 DEL-GW</p></td>
<td><p>참</p></td>
<td><p>사이트 1(뉴델리)</p></td>
</tr>
<tr class="even">
<td><p>가 pstngateway: 트렁크 2 HYD-GW</p></td>
<td><p>참</p></td>
<td><p>사이트 2 (Hyderabad)</p></td>
</tr>
<tr class="odd">
<td><p>가 pstngateway: 트렁크 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>사이트 1(뉴델리)</p></td>
</tr>
<tr class="even">
<td><p>가 pstngateway: 트렁크 4 HYD</p></td>
<td><p>False</p></td>
<td><p>사이트 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>음성 정책에 대 한 위치 기반 라우팅 사용

특정 사용자에 대해 위치 기반 라우팅을 적용 하려면 PSTN 전화 바이패스를 방지 하도록 해당 사용자의 음성 정책을 구성 합니다. Lync Server Windows PowerShell 명령 Set-csvoicepolicy를 사용 하 여 기존 정책을 사용 하는 경우 새 음성 정책을 만들거나 Set-csvoicepolicy을 만들어 PSTN 유료 바이패스를 방지 하 여 위치 기반 라우팅을 사용 하도록 설정 합니다.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

자세한 내용은 [set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy)를 참조 하십시오.

이 예에서는 다음 표 및 Windows PowerShell 명령을 사용 하 여이 시나리오에 정의 된 Hyderabad 음성 정책으로 PSTN 유료 바이패스를 방지 하는 방법을 보여 줍니다. 위치 기반 라우팅과 관련 된 설정만 설명을 위해 표에 포함 되어 있습니다.

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>음성 정책 1</th>
<th>음성 정책 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>음성 정책 ID</p></td>
<td><p>뉴델리 voice 정책</p></td>
<td><p>Hyderabad 음성 정책</p></td>
</tr>
<tr class="even">
<td><p>PSTN 사용</p></td>
<td><p>뉴델리 usage, PBX Del usage, PBX Hyd usage</p></td>
<td><p>Hyderabad 사용 현황, PBX Hyd usage, PBX Del usage</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>참</p></td>
<td><p>참</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>라우팅 구성에서 위치 기반 라우팅 사용

마지막으로 위치 기반 라우팅을 라우팅 구성에 대해 전역적으로 사용 하도록 설정 합니다. Lync Server Windows PowerShell 명령, 새 CsRoutingConfiguration을 사용 하 여 위치 기반 라우팅을 사용 하도록 설정 합니다.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

자세한 내용은 [설정-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration)를 참조 하세요.

<div>


> [!NOTE]  
> 전역 구성을 통해 위치 기반 라우팅을 사용 하도록 설정 해야 하지만, 적용할 규칙 집합은이 설명서에 지정 된 대로 구성 된 사이트, 사용자 및 트렁크 적용 됩니다.



</div>

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

