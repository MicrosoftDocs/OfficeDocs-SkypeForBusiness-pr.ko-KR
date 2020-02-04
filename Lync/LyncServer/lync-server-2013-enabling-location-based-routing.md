---
title: 'Lync Server 2013: 위치 기반 라우팅 사용'
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
ms.openlocfilehash: e21e1a285fa5b2129d4d0ed0b5d75e8dcee42f2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="0e9ef-102">Lync Server 2013에서 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="0e9ef-102">Enabling Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e9ef-103">_**마지막으로 수정한 주제:** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="0e9ef-103">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="0e9ef-104">Enterprise Voice를 배포 하 고 네트워크 영역, 사이트 및 서브넷을 정의한 후에는 위치 기반 라우팅을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-104">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="0e9ef-105">다음 엔터프라이즈 음성 요소에 대해 위치 기반 라우팅이 사용 하도록 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-105">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="0e9ef-106">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="0e9ef-106">Network sites</span></span>

  - <span data-ttu-id="0e9ef-107">트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="0e9ef-107">Trunk configurations</span></span>

  - <span data-ttu-id="0e9ef-108">음성 정책</span><span class="sxs-lookup"><span data-stu-id="0e9ef-108">Voice policies</span></span>

  - <span data-ttu-id="0e9ef-109">라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="0e9ef-109">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="0e9ef-110">네트워크 사이트에 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="0e9ef-110">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="0e9ef-111">Enterprise Voice를 배포 하 고 네트워크 사이트를 구성한 후에는 위치 기반 라우팅을 구성할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-111">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="0e9ef-112">먼저, 네트워크 사이트를 적절 한 PSTN 용도에 연결 하는 음성 라우팅 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-112">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="0e9ef-113">음성 라우팅 정책에 PSTN 용도를 할당할 때 사이트 또는 위치 기반 라우팅 제한이 필요 하지 않은 지역에 있는 pstn 게이트웨이를 사용 하는 음성 경로에 연결 된 PSTN 사용량만 사용 해야 합니다. Lync Server Windows PowerShell command, CsVoiceRoutingPolicy 또는 Lync Server 제어판을 사용 하 여 음성 라우팅 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-113">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="0e9ef-114">자세한 내용은 [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-114">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="0e9ef-115">이 예제에서 다음 표 및 Windows PowerShell 명령은 두 가지 음성 라우팅 정책 및이 시나리오에 정의 된 해당 PSTN 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-115">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="0e9ef-116">이 표에는 위치 기반 라우팅과 관련 하 여 설명 하는 설정만 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="0e9ef-117">음성 라우팅 정책 1</span><span class="sxs-lookup"><span data-stu-id="0e9ef-117">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="0e9ef-118">음성 라우팅 정책 2</span><span class="sxs-lookup"><span data-stu-id="0e9ef-118">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e9ef-119">음성 정책 ID</span><span class="sxs-lookup"><span data-stu-id="0e9ef-119">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-120">뉴델리 voice 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="0e9ef-120">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-121">Hyderabad 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="0e9ef-121">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e9ef-122">PSTN 용도</span><span class="sxs-lookup"><span data-stu-id="0e9ef-122">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-123">뉴델리 사용, PBX Del 사용, PBX Hyd 사용</span><span class="sxs-lookup"><span data-stu-id="0e9ef-123">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-124">Hyderabad 사용, PBX Hyd 사용, PBX Del 사용</span><span class="sxs-lookup"><span data-stu-id="0e9ef-124">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="0e9ef-125">그 다음에는 해당 네트워크 사이트에 대 한 위치 기반 라우팅을 구성 하 고 사용자의 음성 라우팅 정책을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-125">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="0e9ef-126">Lync Server Windows PowerShell 명령, 새 CsNetworkSite를 사용 하 여 위치 기반 라우팅을 사용 하도록 설정 하 고 라우팅 제한을 적용 해야 하는 네트워크 사이트에 음성 라우팅 정책을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="0e9ef-127">이 예제에서 다음 표에는 Lync Server Windows PowerShell을 사용 하 여이 시나리오에 정의 된 두 개의 다른 네트워크 사이트, 뉴델리 및 Hyderabad에 대 한 위치 기반 라우팅이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-127">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="0e9ef-128">이 표에는 위치 기반 라우팅과 관련 하 여 설명 하는 설정만 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-128">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="0e9ef-129">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="0e9ef-129">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="0e9ef-130">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0e9ef-130">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e9ef-131">사이트 이름</span><span class="sxs-lookup"><span data-stu-id="0e9ef-131">Site Name</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-132">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="0e9ef-132">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-133">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0e9ef-133">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e9ef-134">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="0e9ef-134">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-135">False</span><span class="sxs-lookup"><span data-stu-id="0e9ef-135">True</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-136">False</span><span class="sxs-lookup"><span data-stu-id="0e9ef-136">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e9ef-137">음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="0e9ef-137">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-138">뉴델리 voice 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="0e9ef-138">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-139">Hyderabad 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="0e9ef-139">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e9ef-140">네트</span><span class="sxs-lookup"><span data-stu-id="0e9ef-140">Subnets</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-141">서브넷 1 (뉴델리)</span><span class="sxs-lookup"><span data-stu-id="0e9ef-141">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-142">서브넷 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0e9ef-142">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="0e9ef-143">Trunks에 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="0e9ef-143">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="0e9ef-144">위치 기반 라우팅에 트렁크 구성을 사용할 수 있으려면 먼저 각 트렁크 또는 각 네트워크 사이트에 트렁크 구성을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-144">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="0e9ef-145">Lync Server Windows PowerShell 명령 Set-cstrunkconfiguration를 사용 하 여 트렁크 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-145">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="0e9ef-146">지정 된 시스템 (예: 게이트웨이 또는 PBX)에 여러 trunks 연결 된 경우 위치 기반 라우팅 제한을 사용 하도록 각 트렁크 구성을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-146">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="0e9ef-147">자세한 내용은 [New-set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-147">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="0e9ef-148">이 예제에서 다음 Windows PowerShell 명령은이 시나리오에 정의 된 배포의 각 트렁크에 대 한 트렁크 구성 하나를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-148">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="0e9ef-149">트렁크에 트렁크 구성을 구성한 후에는 Lync Server Windows PowerShell 명령 Set-cstrunkconfiguration를 사용 하 여 라우팅 제한을 적용 해야 하는 trunks에 대 한 위치 기반 라우팅을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-149">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="0e9ef-150">PSTN에 대 한 호출을 라우팅하고 게이트웨이가 있는 네트워크 사이트를 연결 하는 PSTN 게이트웨이에 대 한 통화 경로를 설정 하는 trunks에 위치 기반 라우팅을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-150">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="0e9ef-151">자세한 내용은 [New-set-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-151">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="0e9ef-152">이 예제에서는 Hyderabad의 PSTN 게이트웨이와 연결 된 각 트렁크에 대해 위치 기반 라우팅이 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-152">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="0e9ef-153">PSTN으로 통화를 라우팅 하지 않는 trunks에 대해 위치 기반 라우팅을 사용 하지 마세요. 그러나이 트렁크를 통해 연결 된 끝점에 도달 하는 PSTN 통화에 대해 위치 기반 라우팅 제한을 적용 해야 하는 네트워크 사이트에도 트렁크를 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-153">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="0e9ef-154">이 예에서는 Hyderabad에서 PBX 시스템과 연결 된 각 트렁크에 대해 위치 기반 라우팅이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-154">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="0e9ef-155">PSTN으로 통화를 라우팅 하지 않는 시스템 (예: PBX)에 연결 된 끝점은 위치 기반 라우팅에 대해 사용 하도록 설정 된 사용자의 Lync 끝점과 비슷한 제한을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-155">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="0e9ef-156">즉, 이러한 사용자는 사용자 위치에 관계 없이 Lync 사용자에 게 전화를 걸거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-156">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="0e9ef-157">또한 시스템을 연결 하는 네트워크 사이트에 관계 없이 PSTN 네트워크 (예: 다른 PBX에 연결 된 끝점)에 대 한 통화를 라우팅 하지 않는 다른 시스템에 대 한 수신 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-157">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="0e9ef-158">PSTN 끝점을 포함 하는 모든 인바운드 통화, 아웃 바운드 통화, 통화 전송 및 착신 전환에는 위치 기반 라우팅 enforcements 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-158">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="0e9ef-159">그러한 호출은 해당 시스템에 로컬로 정의 된 PSTN 게이트웨이만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-159">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="0e9ef-160">다음 표에서는 PSTN 게이트웨이와 연결 된 두 개의 다른 네트워크 사이트와 PBX 시스템에 연결 된 두 개의 trunks의 트렁크 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-160">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e9ef-161">이름</span><span class="sxs-lookup"><span data-stu-id="0e9ef-161">Name</span></span></th>
<th><span data-ttu-id="0e9ef-162">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="0e9ef-162">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="0e9ef-163">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="0e9ef-163">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e9ef-164">PstnGateway: 트렁크 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="0e9ef-164">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-165">False</span><span class="sxs-lookup"><span data-stu-id="0e9ef-165">True</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-166">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="0e9ef-166">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e9ef-167">PstnGateway: 트렁크 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="0e9ef-167">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-168">False</span><span class="sxs-lookup"><span data-stu-id="0e9ef-168">True</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-169">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0e9ef-169">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e9ef-170">PstnGateway: 트렁크 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="0e9ef-170">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-171">해제</span><span class="sxs-lookup"><span data-stu-id="0e9ef-171">False</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-172">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="0e9ef-172">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e9ef-173">PstnGateway: 트렁크 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="0e9ef-173">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-174">해제</span><span class="sxs-lookup"><span data-stu-id="0e9ef-174">False</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-175">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="0e9ef-175">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="0e9ef-176">음성 정책에 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="0e9ef-176">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="0e9ef-177">특정 사용자에 대 한 위치 기반 라우팅을 적용 하려면 PSTN 유료 바이패스를 방지 하도록 해당 사용자의 음성 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-177">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="0e9ef-178">Lync Server Windows PowerShell 명령 CsVoicePolicy를 사용 하 여 기존 정책을 사용 하는 경우 새 음성 정책 또는 CsVoicePolicy 설정을 만들어 PSTN 유료 바이패스를 방지 하 여 위치 기반 라우팅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-178">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="0e9ef-179">자세한 내용은 [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-179">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="0e9ef-180">이 예제에서는 다음 표 및 Windows PowerShell 명령을 사용 하 여이 시나리오에 정의 된 뉴델리 및 Hyderabad voice 정책에 대 한 PSTN 유료 바이패스를 방지 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-180">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="0e9ef-181">이 표에는 위치 기반 라우팅과 관련 하 여 설명 하는 설정만 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-181">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="0e9ef-182">음성 정책 1</span><span class="sxs-lookup"><span data-stu-id="0e9ef-182">Voice policy 1</span></span></th>
<th><span data-ttu-id="0e9ef-183">음성 정책 2</span><span class="sxs-lookup"><span data-stu-id="0e9ef-183">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e9ef-184">음성 정책 ID</span><span class="sxs-lookup"><span data-stu-id="0e9ef-184">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-185">뉴델리 voice 정책</span><span class="sxs-lookup"><span data-stu-id="0e9ef-185">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-186">Hyderabad 음성 정책</span><span class="sxs-lookup"><span data-stu-id="0e9ef-186">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e9ef-187">PSTN 용도</span><span class="sxs-lookup"><span data-stu-id="0e9ef-187">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-188">뉴델리 사용, PBX Del 사용, PBX Hyd 사용</span><span class="sxs-lookup"><span data-stu-id="0e9ef-188">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-189">Hyderabad 사용, PBX Hyd 사용, PBX Del 사용</span><span class="sxs-lookup"><span data-stu-id="0e9ef-189">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e9ef-190">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="0e9ef-190">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-191">False</span><span class="sxs-lookup"><span data-stu-id="0e9ef-191">True</span></span></p></td>
<td><p><span data-ttu-id="0e9ef-192">False</span><span class="sxs-lookup"><span data-stu-id="0e9ef-192">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="0e9ef-193">라우팅 구성에서 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="0e9ef-193">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="0e9ef-194">마지막으로, 라우팅 구성에 대 한 위치 기반 라우팅을 전역적으로 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-194">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="0e9ef-195">Lync Server Windows PowerShell 명령, 새 CsRoutingConfiguration을 사용 하 여 위치 기반 라우팅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-195">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="0e9ef-196">자세한 내용은 [CsRoutingConfiguration 설정을](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-196">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e9ef-197">전역 구성을 통해 위치 기반 라우팅을 사용 하도록 설정 해야 하지만, 적용할 규칙 집합은이 설명서에 지정 된 대로 구성 된 사이트, 사용자 및 trunks 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e9ef-197">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0e9ef-198">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e9ef-198">See Also</span></span>


[<span data-ttu-id="0e9ef-199">Lync Server 2013에서 위치 기반 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="0e9ef-199">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

