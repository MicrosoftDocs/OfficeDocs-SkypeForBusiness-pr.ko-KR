---
title: 직접 라우팅에 위치 기반 라우팅 사용
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 직접 라우팅에 대해 위치 기반 라우팅을 사용 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 48fbd1477194b7523b65ec527686b7304f0c37b2
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992023"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="f0d0a-103">직접 라우팅에 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="f0d0a-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="f0d0a-104">이 문서에 나와 있는 단계를 수행 하기 전에 위치 [기반 라우팅에 대 한 네트워크 설정 구성](location-based-routing-configure-network-settings.md)단계를 [직접 라우팅과 완료 하기 위한 계획 위치 기반 라우팅을](location-based-routing-plan.md) 읽어 주십시오.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="f0d0a-105">이 문서에서는 직접 라우팅에 위치 기반 라우팅을 사용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="f0d0a-106">전화 시스템 직접 라우팅을 배포 하 고 네트워크 지역, 사이트 및 서브넷을 설정한 후에는 위치 기반 라우팅을 사용할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="f0d0a-107">이 문서의 단계를 완료 하려면 PowerShell cmdlet에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="f0d0a-108">자세히 알아보려면 [팀 PowerShell 개요](teams-powershell-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="f0d0a-109">위치 기반 회람을 사용 해야 하는 경우는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="f0d0a-110">사용자</span><span class="sxs-lookup"><span data-stu-id="f0d0a-110">Users</span></span>
- <span data-ttu-id="f0d0a-111">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="f0d0a-111">Network sites</span></span>
- <span data-ttu-id="f0d0a-112">게이트웨이 구성</span><span class="sxs-lookup"><span data-stu-id="f0d0a-112">Gateway configurations</span></span>
- <span data-ttu-id="f0d0a-113">통화 정책</span><span class="sxs-lookup"><span data-stu-id="f0d0a-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="f0d0a-114">사용자의 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="f0d0a-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="f0d0a-115">[CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet을 사용 하 여 PSTN 사용량을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-115">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="f0d0a-116">여러 용도를 위해 각 용도를 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-116">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="f0d0a-117">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-117">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="f0d0a-118">[CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet을 사용 하 여 사용자를 적절 한 PSTN 용도에 연결 하는 음성 라우팅 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-118">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="f0d0a-119">음성 라우팅 정책에 PSTN 용도를 할당 하는 경우 다음 중 하나를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="f0d0a-120">사이트에 로컬 PSTN 게이트웨이를 사용 하는 음성 경로에 연결 된 PSTN 용도 사용</span><span class="sxs-lookup"><span data-stu-id="f0d0a-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="f0d0a-121">위치 기반 라우팅 제한이 필요 하지 않은 지역에 있는 PSTN 게이트웨이를 사용 하는 음성 경로에 연결 된 PSTN 사용량을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="f0d0a-122">이 예제에서는 두 개의 새로운 음성 라우팅 정책을 만들고 PSTN 용도를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="f0d0a-123">다음 표에는이 예제에 정의 된 음성 라우팅 정책이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="f0d0a-124">음성 라우팅 정책 1</span><span class="sxs-lookup"><span data-stu-id="f0d0a-124">Voice routing policy 1</span></span>|<span data-ttu-id="f0d0a-125">음성 라우팅 정책 2</span><span class="sxs-lookup"><span data-stu-id="f0d0a-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="f0d0a-126">온라인 음성 정책 ID</span><span class="sxs-lookup"><span data-stu-id="f0d0a-126">Online voice policy ID</span></span>   |<span data-ttu-id="f0d0a-127">이 (가) 뉴델리 온라인 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="f0d0a-127">Delhi online voice routing policy</span></span>   |<span data-ttu-id="f0d0a-128">Hyderabad 온라인 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="f0d0a-128">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="f0d0a-129">온라인 PSTN 용도</span><span class="sxs-lookup"><span data-stu-id="f0d0a-129">Online PSTN usages</span></span>  |<span data-ttu-id="f0d0a-130">시외</span><span class="sxs-lookup"><span data-stu-id="f0d0a-130">Long Distance</span></span>  |<span data-ttu-id="f0d0a-131">장거리, 지역, 내부</span><span class="sxs-lookup"><span data-stu-id="f0d0a-131">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="f0d0a-132">[CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet을 사용 하 여 라우팅 제한을 적용 해야 하는 사용자에 게 온라인 음성 라우팅 정책을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-132">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="f0d0a-133">네트워크 사이트용 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="f0d0a-133">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="f0d0a-134">[Set-Csten앤틸리스 site](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet을 사용 하 여 위치 기반 라우팅을 사용 하도록 설정 하 고 라우팅 제한을 적용 해야 하는 네트워크 사이트에 음성 라우팅 정책을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-134">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="f0d0a-135">이 예제에서는 뉴델리 사이트 및 Hyderabad 사이트에 대 한 위치 기반 라우팅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-135">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="f0d0a-136">다음 표에는이 예제에서 위치 기반 라우팅에 사용할 수 있는 사이트가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-136">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="f0d0a-137">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="f0d0a-137">Site 1 (Delhi)</span></span>  |<span data-ttu-id="f0d0a-138">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f0d0a-138">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="f0d0a-139">사이트 이름</span><span class="sxs-lookup"><span data-stu-id="f0d0a-139">Site name</span></span>    |<span data-ttu-id="f0d0a-140">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="f0d0a-140">Site 1 (Delhi)</span></span>    |<span data-ttu-id="f0d0a-141">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f0d0a-141">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="f0d0a-142">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="f0d0a-142">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="f0d0a-143">False</span><span class="sxs-lookup"><span data-stu-id="f0d0a-143">True</span></span>    |<span data-ttu-id="f0d0a-144">False</span><span class="sxs-lookup"><span data-stu-id="f0d0a-144">True</span></span>    |
    |<span data-ttu-id="f0d0a-145">네트</span><span class="sxs-lookup"><span data-stu-id="f0d0a-145">Subnets</span></span>     |<span data-ttu-id="f0d0a-146">서브넷 1 (뉴델리)</span><span class="sxs-lookup"><span data-stu-id="f0d0a-146">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="f0d0a-147">서브넷 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f0d0a-147">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="f0d0a-148">게이트웨이에 대 한 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="f0d0a-148">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="f0d0a-149">[새 CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet을 사용 하 여 각 게이트웨이 또는 네트워크 사이트에 대 한 게이트웨이 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-149">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="f0d0a-150">여러 게이트웨이가 시스템 (예: 게이트웨이 또는 PBX)과 연결 되어 있는 경우 위치 기반 라우팅 제한을 사용 하도록 각 게이트웨이를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-150">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="f0d0a-151">이 예제에서는 각 게이트웨이에 대해 하나의 게이트웨이 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-151">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="f0d0a-152">자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-152">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="f0d0a-153">[CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet을 사용 하 여 라우팅 제한을 적용 해야 하는 게이트웨이에 대 한 위치 기반 라우팅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-153">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="f0d0a-154">PSTN으로 호출을 라우팅하는 PSTN 게이트웨이로 통화를 라우팅하고 게이트웨이가 있는 네트워크 사이트를 연결 하는 게이트웨이에 대 한 위치 기반 라우팅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-154">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="f0d0a-155">이 예제에서는 뉴델리 및 Hyderabad 사이트의 PSTN 게이트웨이와 연결 된 각 게이트웨이에 대해 위치 기반 라우팅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-155">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="f0d0a-156">PSTN으로 호출을 라우팅되지 않는 게이트웨이에 대해 위치 기반 라우팅을 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-156">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="f0d0a-157">그러나이 경우에도 시스템이 있는 네트워크 사이트에 게이트웨이를 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-157">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="f0d0a-158">이 게이트웨이를 통해 연결 된 끝점에 도달 하는 PSTN 호출에 대해 위치 기반 라우팅 제한을 적용 해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-158">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="f0d0a-159">이 예제에서는 Hyderabad 사이트에서 PBX 시스템과 연결 된 각 게이트웨이에 대해 위치 기반 라우팅이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-159">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="f0d0a-160">PSTN으로 호출을 라우팅 하지 않는 시스템 (예: PBX)에 연결 된 끝점은 위치 기반 라우팅에 대해 사용 하도록 설정한 팀 사용자의 끝점과 유사 하 게 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-160">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="f0d0a-161">즉, 이러한 사용자는 사용자 위치에 관계 없이 팀 사용자에 게 전화를 걸거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-161">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="f0d0a-162">또한 시스템을 연결 하는 네트워크 사이트에 관계 없이 PSTN 네트워크 (예: 다른 PBX에 연결 된 끝점과 같은)에 대 한 통화를 라우팅 하지 않는 다른 시스템에서 전화를 걸거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-162">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="f0d0a-163">PSTN 끝점을 포함 하는 모든 인바운드 통화, 아웃 바운드 통화, 통화 전송 및 착신 전환에는 위치 기반 라우팅 enforcements 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-163">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="f0d0a-164">이러한 통화는 해당 시스템에 로컬으로 정의 된 PSTN 게이트웨이만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-164">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="f0d0a-165">다음 표에서는 PSTN 게이트웨이와 연결 된 두 개의 다른 네트워크 사이트와 PBX 시스템에 연결 된 두 개의 게이트웨이 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-165">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="f0d0a-166">게이트웨이 사용</span><span class="sxs-lookup"><span data-stu-id="f0d0a-166">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="f0d0a-167">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="f0d0a-167">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="f0d0a-168">PstnGateway: Gateway 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="f0d0a-168">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="f0d0a-169">False</span><span class="sxs-lookup"><span data-stu-id="f0d0a-169">True</span></span>     |   <span data-ttu-id="f0d0a-170">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="f0d0a-170">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="f0d0a-171">PstnGateway: Gateway 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="f0d0a-171">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="f0d0a-172">False</span><span class="sxs-lookup"><span data-stu-id="f0d0a-172">True</span></span>      |      <span data-ttu-id="f0d0a-173">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f0d0a-173">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="f0d0a-174">PstnGateway: 게이트웨이 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="f0d0a-174">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="f0d0a-175">해제</span><span class="sxs-lookup"><span data-stu-id="f0d0a-175">False</span></span>     |     <span data-ttu-id="f0d0a-176">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="f0d0a-176">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="f0d0a-177">PstnGateway: Gateway 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="f0d0a-177">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="f0d0a-178">해제</span><span class="sxs-lookup"><span data-stu-id="f0d0a-178">False</span></span>     |    <span data-ttu-id="f0d0a-179">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f0d0a-179">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="f0d0a-180">호출 정책에 대해 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="f0d0a-180">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="f0d0a-181">특정 사용자에 대해 위치 기반 라우팅을 적용 하려면, 사용자의 음성 정책을 설정 하 여 PTSN을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-181">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="f0d0a-182">[CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet을 사용 하 여 PSTN 유료 바이패스를 방지 하 여 위치 기반 라우팅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-182">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="f0d0a-183">이 예제에서는 PSTN 유료 바이패스를 User1's 호출 정책을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d0a-183">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

## <a name="related-topics"></a><span data-ttu-id="f0d0a-184">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f0d0a-184">Related topics</span></span>

- [<span data-ttu-id="f0d0a-185">팀의 클라우드 음성 기능에 대 한 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="f0d0a-185">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
