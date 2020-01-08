---
title: 'Lync Server 2013: 위치 기반 라우팅 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170ca1af77a84b655e90d5587fcd101cccf83c8a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a>Lync Server 2013에서 위치 기반 라우팅 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-04-26_

Enterprise Voice를 배포 하 고 네트워크 영역, 사이트 및 서브넷을 정의한 후에는 위치 기반 라우팅을 사용 하도록 설정할 수 있습니다. 다음 엔터프라이즈 음성 요소에 대해 위치 기반 라우팅이 사용 하도록 설정 되어 있어야 합니다.

  - 네트워크 사이트

  - 트렁크 구성

  - 음성 정책

  - 라우팅 구성

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>네트워크 사이트에 위치 기반 라우팅 사용

Enterprise Voice를 배포 하 고 네트워크 사이트를 구성한 후에는 위치 기반 라우팅을 구성할 준비가 된 것입니다. 먼저, 네트워크 사이트를 적절 한 PSTN 용도에 연결 하는 음성 라우팅 정책을 만듭니다. 음성 라우팅 정책에 PSTN 용도를 할당할 때 사이트 또는 위치 기반 라우팅 제한이 필요 하지 않은 지역에 있는 pstn 게이트웨이를 사용 하는 음성 경로에 연결 된 PSTN 사용량만 사용 해야 합니다. Lync Server Windows PowerShell command, CsVoiceRoutingPolicy 또는 Lync Server 제어판을 사용 하 여 음성 라우팅 정책을 만듭니다.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

자세한 내용은 [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy)를 참조 하세요.

이 예제에서 다음 표 및 Windows PowerShell 명령은 두 가지 음성 라우팅 정책 및이 시나리오에 정의 된 해당 PSTN 사용을 보여 줍니다. 이 표에는 위치 기반 라우팅과 관련 하 여 설명 하는 설정만 나와 있습니다.

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
<td><p>PSTN 용도</p></td>
<td><p>뉴델리 사용, PBX Del 사용, PBX Hyd 사용</p></td>
<td><p>Hyderabad 사용, PBX Hyd 사용, PBX Del 사용</p></td>
</tr>
</tbody>
</table>

  

그 다음에는 해당 네트워크 사이트에 대 한 위치 기반 라우팅을 구성 하 고 사용자의 음성 라우팅 정책을 연결 합니다. Lync Server Windows PowerShell 명령, 새 CsNetworkSite를 사용 하 여 위치 기반 라우팅을 사용 하도록 설정 하 고 라우팅 제한을 적용 해야 하는 네트워크 사이트에 음성 라우팅 정책을 연결 합니다.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

이 예제에서 다음 표에는 Lync Server Windows PowerShell을 사용 하 여이 시나리오에 정의 된 두 개의 다른 네트워크 사이트, 뉴델리 및 Hyderabad에 대 한 위치 기반 라우팅이 나와 있습니다. 이 표에는 위치 기반 라우팅과 관련 하 여 설명 하는 설정만 나와 있습니다.

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
<th>Site 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>사이트 이름</p></td>
<td><p>사이트 1(뉴델리)</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>EnableLocationBasedRouting</p></td>
<td><p>False</p></td>
<td><p>False</p></td>
</tr>
<tr class="odd">
<td><p>음성 라우팅 정책</p></td>
<td><p>뉴델리 voice 라우팅 정책</p></td>
<td><p>Hyderabad 음성 라우팅 정책</p></td>
</tr>
<tr class="even">
<td><p>네트</p></td>
<td><p>서브넷 1 (뉴델리)</p></td>
<td><p>서브넷 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a>Trunks에 위치 기반 라우팅 사용

위치 기반 라우팅에 트렁크 구성을 사용할 수 있으려면 먼저 각 트렁크 또는 각 네트워크 사이트에 트렁크 구성을 만들어야 합니다. Lync Server Windows PowerShell 명령 Set-cstrunkconfiguration를 사용 하 여 트렁크 구성을 만듭니다. 지정 된 시스템 (예: 게이트웨이 또는 PBX)에 여러 trunks 연결 된 경우 위치 기반 라우팅 제한을 사용 하도록 각 트렁크 구성을 수정 해야 합니다.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

자세한 내용은 [New-set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)를 참조 하세요.

이 예제에서 다음 Windows PowerShell 명령은이 시나리오에 정의 된 배포의 각 트렁크에 대 한 트렁크 구성 하나를 만드는 방법을 보여 줍니다.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

트렁크에 트렁크 구성을 구성한 후에는 Lync Server Windows PowerShell 명령 Set-cstrunkconfiguration를 사용 하 여 라우팅 제한을 적용 해야 하는 trunks에 대 한 위치 기반 라우팅을 사용 하도록 설정할 수 있습니다. PSTN에 대 한 호출을 라우팅하고 게이트웨이가 있는 네트워크 사이트를 연결 하는 PSTN 게이트웨이에 대 한 통화 경로를 설정 하는 trunks에 위치 기반 라우팅을 사용 합니다.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

자세한 내용은 [New-set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)를 참조 하세요.

이 예제에서는 Hyderabad의 PSTN 게이트웨이와 연결 된 각 트렁크에 대해 위치 기반 라우팅이 사용 하도록 설정 되어 있습니다.

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

PSTN으로 통화를 라우팅 하지 않는 trunks에 대해 위치 기반 라우팅을 사용 하지 마세요. 그러나이 트렁크를 통해 연결 된 끝점에 도달 하는 PSTN 통화에 대해 위치 기반 라우팅 제한을 적용 해야 하는 네트워크 사이트에도 트렁크를 연결 해야 합니다. 이 예에서는 Hyderabad에서 PBX 시스템과 연결 된 각 트렁크에 대해 위치 기반 라우팅이 사용 되지 않습니다.

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
PSTN으로 통화를 라우팅 하지 않는 시스템 (예: PBX)에 연결 된 끝점은 위치 기반 라우팅에 대해 사용 하도록 설정 된 사용자의 Lync 끝점과 비슷한 제한을 받습니다. 즉, 이러한 사용자는 사용자 위치에 관계 없이 Lync 사용자에 게 전화를 걸거나 받을 수 있습니다. 또한 시스템을 연결 하는 네트워크 사이트에 관계 없이 PSTN 네트워크 (예: 다른 PBX에 연결 된 끝점)에 대 한 통화를 라우팅 하지 않는 다른 시스템에 대 한 수신 전화를 걸 수 있습니다. PSTN 끝점을 포함 하는 모든 인바운드 통화, 아웃 바운드 통화, 통화 전송 및 착신 전환에는 위치 기반 라우팅 enforcements 적용 됩니다. 그러한 호출은 해당 시스템에 로컬로 정의 된 PSTN 게이트웨이만 사용 해야 합니다.

다음 표에서는 PSTN 게이트웨이와 연결 된 두 개의 다른 네트워크 사이트와 PBX 시스템에 연결 된 두 개의 trunks의 트렁크 구성을 보여 줍니다.


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
<td><p>PstnGateway: 트렁크 1 DEL-GW</p></td>
<td><p>False</p></td>
<td><p>사이트 1(뉴델리)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: 트렁크 2 HYD-GW</p></td>
<td><p>False</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway: 트렁크 3 DEL-PBX</p></td>
<td><p>해제</p></td>
<td><p>사이트 1(뉴델리)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: 트렁크 4 HYD-PBX</p></td>
<td><p>해제</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>음성 정책에 위치 기반 라우팅 사용

특정 사용자에 대 한 위치 기반 라우팅을 적용 하려면 PSTN 유료 바이패스를 방지 하도록 해당 사용자의 음성 정책을 구성 합니다. Lync Server Windows PowerShell 명령 CsVoicePolicy를 사용 하 여 기존 정책을 사용 하는 경우 새 음성 정책 또는 CsVoicePolicy 설정을 만들어 PSTN 유료 바이패스를 방지 하 여 위치 기반 라우팅을 사용 하도록 설정 합니다.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

자세한 내용은 [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy)를 참조 하세요.

이 예제에서는 다음 표 및 Windows PowerShell 명령을 사용 하 여이 시나리오에 정의 된 뉴델리 및 Hyderabad voice 정책에 대 한 PSTN 유료 바이패스를 방지 하는 방법을 보여 줍니다. 이 표에는 위치 기반 라우팅과 관련 하 여 설명 하는 설정만 나와 있습니다.

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
<td><p>PSTN 용도</p></td>
<td><p>뉴델리 사용, PBX Del 사용, PBX Hyd 사용</p></td>
<td><p>Hyderabad 사용, PBX Hyd 사용, PBX Del 사용</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>False</p></td>
<td><p>False</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>라우팅 구성에서 위치 기반 라우팅 사용

마지막으로, 라우팅 구성에 대 한 위치 기반 라우팅을 전역적으로 사용 하도록 설정 합니다. Lync Server Windows PowerShell 명령, 새 CsRoutingConfiguration을 사용 하 여 위치 기반 라우팅을 사용 하도록 설정 합니다.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

자세한 내용은 [CsRoutingConfiguration 설정을](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration)참조 하세요.

<div>


> [!NOTE]  
> 전역 구성을 통해 위치 기반 라우팅을 사용 하도록 설정 해야 하지만, 적용할 규칙 집합은이 설명서에 지정 된 대로 구성 된 사이트, 사용자 및 trunks 적용 됩니다.



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

