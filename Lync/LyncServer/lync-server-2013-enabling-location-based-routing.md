---
title: 'Lync Server 2013: Location-Based 라우팅 사용'
description: 'Lync Server 2013: Location-Based 라우팅을 사용 하도록 설정 합니다.'
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
ms.openlocfilehash: 7844af5792468cd5645b6b42c857c63b943c2df1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557624"
---
# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="27819-103">Lync Server 2013에서 Location-Based 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="27819-103">Enabling Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27819-104">_**마지막으로 수정 된 항목:** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="27819-104">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="27819-105">Enterprise Voice가 배포 되 고 네트워크 지역에 있는 경우 사이트와 서브넷이 정의 되 면 Location-Based 라우팅을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27819-105">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="27819-106">다음 Enterprise Voice 요소에 대해 Location-Based 라우팅을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27819-106">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="27819-107">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="27819-107">Network sites</span></span>

  - <span data-ttu-id="27819-108">트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="27819-108">Trunk configurations</span></span>

  - <span data-ttu-id="27819-109">음성 정책</span><span class="sxs-lookup"><span data-stu-id="27819-109">Voice policies</span></span>

  - <span data-ttu-id="27819-110">라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="27819-110">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="27819-111">네트워크 사이트에 대 한 Location-Based 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="27819-111">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="27819-112">Enterprise Voice를 배포 하 고 네트워크 사이트를 구성한 후에는 Location-Based 라우팅을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27819-112">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="27819-113">먼저 네트워크 사이트를 적절 한 PSTN 사용에 연결 하는 음성 라우팅 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27819-113">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="27819-114">음성 라우팅 정책에 PSTN 사용을 할당할 때에는 사이트에 대 한 PSTN 게이트웨이 로컬을 사용 하는 음성 경로와 연결 된 PSTN 사용 또는 Location-Based 라우팅 제한이 필요 없는 지역에 있는 PSTN 게이트웨이로만 설정 해야 합니다. Lync Server Windows PowerShell 명령, Get-csvoiceroutingpolicy 또는 Lync Server 제어판을 사용 하 여 음성 라우팅 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27819-114">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="27819-115">자세한 내용은 [get-csvoiceroutingpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="27819-115">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="27819-116">이 예에서는 다음 표 및 Windows PowerShell 명령은 두 가지 음성 라우팅 정책 및이 시나리오에 정의 된 연결 된 PSTN 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="27819-116">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="27819-117">Location-Based 라우팅과 관련 된 설정만 설명을 위해 표에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27819-117">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="27819-118">음성 라우팅 정책 1</span><span class="sxs-lookup"><span data-stu-id="27819-118">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="27819-119">음성 라우팅 정책 2</span><span class="sxs-lookup"><span data-stu-id="27819-119">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27819-120">음성 정책 ID</span><span class="sxs-lookup"><span data-stu-id="27819-120">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="27819-121">뉴델리 voice 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="27819-121">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="27819-122">Hyderabad 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="27819-122">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27819-123">PSTN 사용</span><span class="sxs-lookup"><span data-stu-id="27819-123">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="27819-124">뉴델리 usage, PBX Del usage, PBX Hyd usage</span><span class="sxs-lookup"><span data-stu-id="27819-124">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="27819-125">Hyderabad 사용 현황, PBX Hyd usage, PBX Del usage</span><span class="sxs-lookup"><span data-stu-id="27819-125">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="27819-126">다음으로, 해당 하는 네트워크 사이트에 대 한 Location-Based 라우팅을 구성 하 고 음성 라우팅 정책을 이러한 정책에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="27819-126">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="27819-127">Lync Server Windows PowerShell 명령, 새 CsNetworkSite를 사용 하 여 Location-Based 라우팅을 사용 하도록 설정 하 고 라우팅 제한을 적용 해야 하는 네트워크 사이트에 음성 라우팅 정책을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="27819-127">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="27819-128">이 예제에서 다음 표에는이 시나리오에서 Lync Server Windows PowerShell을 사용 하 여 정의 된 두 개의 서로 다른 네트워크 사이트 (Hyderabad 및 2)에 대 한 Location-Based 라우팅이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27819-128">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="27819-129">Location-Based 라우팅과 관련 된 설정만 설명을 위해 표에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27819-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="27819-130">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="27819-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="27819-131">사이트 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="27819-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27819-132">사이트 이름</span><span class="sxs-lookup"><span data-stu-id="27819-132">Site Name</span></span></p></td>
<td><p><span data-ttu-id="27819-133">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="27819-133">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="27819-134">사이트 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="27819-134">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27819-135">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="27819-135">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="27819-136">True</span><span class="sxs-lookup"><span data-stu-id="27819-136">True</span></span></p></td>
<td><p><span data-ttu-id="27819-137">True</span><span class="sxs-lookup"><span data-stu-id="27819-137">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27819-138">음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="27819-138">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="27819-139">뉴델리 voice 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="27819-139">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="27819-140">Hyderabad 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="27819-140">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27819-141">서브넷</span><span class="sxs-lookup"><span data-stu-id="27819-141">Subnets</span></span></p></td>
<td><p><span data-ttu-id="27819-142">서브넷 1 (gbps)</span><span class="sxs-lookup"><span data-stu-id="27819-142">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="27819-143">서브넷 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="27819-143">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="27819-144">트렁크로 Location-Based 라우팅을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="27819-144">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="27819-145">Location-Based 라우팅을 위해 트렁크 구성을 사용 하도록 설정 하려면 각 트렁크 또는 각 네트워크 사이트에 대해 트렁크 구성을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27819-145">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="27819-146">Lync Server Windows PowerShell 명령 Get-cstrunkconfiguration를 사용 하 여 트렁크 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27819-146">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="27819-147">트렁크가 지정 된 시스템과 연결 된 경우 (즉, 게이트웨이 또는 PBX) 각 트렁크 구성을 수정 하 여 Location-Based 라우팅 제한을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27819-147">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="27819-148">자세한 내용은 [get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="27819-148">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="27819-149">이 예의 경우 다음 Windows PowerShell 명령은이 시나리오에 정의 된 배포의 각 트렁크에 대해 트렁크 구성을 하나씩 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="27819-149">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="27819-150">트렁크에 따라 줄기 구성을 구성한 후에는 Lync Server Windows PowerShell 명령 Get-cstrunkconfiguration을 사용 하 여 라우팅 제한을 적용 해야 하는 트렁크에 대 한 Location-Based 라우팅을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27819-150">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="27819-151">PSTN에 대 한 통화를 라우팅하는 트렁크에 대 한 Location-Based 라우팅을 사용 하도록 설정 하 고 게이트웨이가 있는 네트워크 사이트를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="27819-151">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="27819-152">자세한 내용은 [get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="27819-152">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="27819-153">이 Location-Based 예에서는 Hyderabad의 PSTN 게이트웨이와 연결 된 각 트렁크에 대해 라우팅이 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27819-153">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="27819-154">통화를 PSTN으로 라우트 하지 않는 트렁크에 대해서는 Location-Based 라우팅을 사용 하도록 설정 하지 마십시오. 그러나이 트렁크를 통해 연결 된 끝점에 도달 하는 PSTN 통화에 대 한 라우팅 제한이 적용 되도록 하려면 해당 시스템을 가진 네트워크 사이트에 트렁크를 연결 해야 Location-Based 합니다.</span><span class="sxs-lookup"><span data-stu-id="27819-154">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="27819-155">이 예 Location-Based에서는 Hyderabad에서 PBX 시스템과 연결 된 각 트렁크에 대해 라우팅이 사용 하도록 설정 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27819-155">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="27819-156">PSTN으로 통화를 라우트 하지 않는 시스템에 연결 된 끝점 (즉, PBX)은 Location-Based 라우팅에 사용 하도록 설정 된 사용자의 Lync 끝점과 비슷한 제한이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27819-156">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="27819-157">즉, 이러한 사용자는 사용자 위치에 관계 없이 Lync 사용자에 게 전화를 걸거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27819-157">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="27819-158">또한 시스템을 연결 하는 네트워크 사이트에 관계 없이 PSTN 네트워크로 통화를 라우팅하는 (즉, 다른 PBX에 연결 된 끝점) 다른 시스템과 주고받는 수신 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27819-158">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="27819-159">PSTN 끝점을 포함 하는 모든 인바운드 통화, 아웃 바운드 통화, 통화 전송 및 통화 전달에 Location-Based 라우팅 enforcements이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27819-159">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="27819-160">이러한 통화는 해당 시스템에 로컬로 정의 된 PSTN 게이트웨이를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27819-160">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="27819-161">다음 표에서는 PSTN 게이트웨이 2 개와 PBX 시스템에 연결 된 2 개의 서로 다른 네트워크 사이트에 있는 네 가지 트렁크의 트렁크 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="27819-161">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="27819-162">이름</span><span class="sxs-lookup"><span data-stu-id="27819-162">Name</span></span></th>
<th><span data-ttu-id="27819-163">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="27819-163">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="27819-164">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="27819-164">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27819-165">가 pstngateway: 트렁크 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="27819-165">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="27819-166">True</span><span class="sxs-lookup"><span data-stu-id="27819-166">True</span></span></p></td>
<td><p><span data-ttu-id="27819-167">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="27819-167">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27819-168">가 pstngateway: 트렁크 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="27819-168">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="27819-169">True</span><span class="sxs-lookup"><span data-stu-id="27819-169">True</span></span></p></td>
<td><p><span data-ttu-id="27819-170">사이트 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="27819-170">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27819-171">가 pstngateway: 트렁크 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="27819-171">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="27819-172">False</span><span class="sxs-lookup"><span data-stu-id="27819-172">False</span></span></p></td>
<td><p><span data-ttu-id="27819-173">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="27819-173">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27819-174">가 pstngateway: 트렁크 4 HYD</span><span class="sxs-lookup"><span data-stu-id="27819-174">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="27819-175">False</span><span class="sxs-lookup"><span data-stu-id="27819-175">False</span></span></p></td>
<td><p><span data-ttu-id="27819-176">사이트 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="27819-176">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="27819-177">음성 정책에 대 한 Location-Based 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="27819-177">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="27819-178">특정 사용자에 게 Location-Based 라우팅을 적용 하려면 PSTN 전화 바이패스를 방지 하도록 해당 사용자의 음성 정책을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="27819-178">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="27819-179">Lync Server Windows PowerShell 명령 Set-csvoicepolicy를 사용 하 여 기존 정책을 사용 하는 경우 새 음성 정책을 만들거나 Set-csvoicepolicy을 만들어 PSTN 유료 바이패스를 방지 하 여 Location-Based 라우팅을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27819-179">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="27819-180">자세한 내용은 [set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="27819-180">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="27819-181">이 예에서는 다음 표 및 Windows PowerShell 명령을 사용 하 여이 시나리오에 정의 된 Hyderabad 음성 정책으로 PSTN 유료 바이패스를 방지 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="27819-181">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="27819-182">Location-Based 라우팅과 관련 된 설정만 설명을 위해 표에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27819-182">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="27819-183">음성 정책 1</span><span class="sxs-lookup"><span data-stu-id="27819-183">Voice policy 1</span></span></th>
<th><span data-ttu-id="27819-184">음성 정책 2</span><span class="sxs-lookup"><span data-stu-id="27819-184">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27819-185">음성 정책 ID</span><span class="sxs-lookup"><span data-stu-id="27819-185">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="27819-186">뉴델리 voice 정책</span><span class="sxs-lookup"><span data-stu-id="27819-186">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="27819-187">Hyderabad 음성 정책</span><span class="sxs-lookup"><span data-stu-id="27819-187">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27819-188">PSTN 사용</span><span class="sxs-lookup"><span data-stu-id="27819-188">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="27819-189">뉴델리 usage, PBX Del usage, PBX Hyd usage</span><span class="sxs-lookup"><span data-stu-id="27819-189">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="27819-190">Hyderabad 사용 현황, PBX Hyd usage, PBX Del usage</span><span class="sxs-lookup"><span data-stu-id="27819-190">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27819-191">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="27819-191">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="27819-192">True</span><span class="sxs-lookup"><span data-stu-id="27819-192">True</span></span></p></td>
<td><p><span data-ttu-id="27819-193">True</span><span class="sxs-lookup"><span data-stu-id="27819-193">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="27819-194">라우팅 구성에서 Location-Based 라우팅을 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="27819-194">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="27819-195">마지막으로 라우팅 구성에 대 한 Location-Based 라우팅을 전역적으로 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27819-195">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="27819-196">Lync Server Windows PowerShell 명령 New CsRoutingConfiguration을 사용 하 여 Location-Based 라우팅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27819-196">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="27819-197">자세한 내용은 [설정-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="27819-197">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="27819-198">전역 구성을 통해 Location-Based 라우팅을 사용 하도록 설정 해야 하는 경우에는이 문서에 지정 된 것 처럼 구성 된 사이트, 사용자 및 트렁크에만 적용 되는 규칙 집합을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27819-198">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="27819-199">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27819-199">See Also</span></span>


[<span data-ttu-id="27819-200">Lync Server 2013에서 Location-Based 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="27819-200">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

