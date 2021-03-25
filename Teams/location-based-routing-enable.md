---
title: 직접 라우팅에 위치 기반 라우팅 사용
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 사용자, 네트워크 Location-Based 게이트웨이 구성 및 호출 정책을 사용하도록 설정하는 것을 포함하여 직접 라우팅에 대한 Location-Based 라우팅을 사용하도록 설정하는 방법에 대해 자세히 알아보습니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d43d650384dd538ff481ac9625c15b9a9f420d95
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120579"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="f24be-103">직접 라우팅에 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="f24be-103">Enable Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="f24be-104">이 문서의 단계를 수행하기 전에 직접 라우팅에 대한 Location-Based 계획 및 라우팅에 대한 네트워크 설정 구성의 Location-Based 완료해야 [합니다.](location-based-routing-configure-network-settings.md) [](location-based-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="f24be-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="f24be-105">이 문서에서는 직접 라우팅에 Location-Based 라우팅을 사용하도록 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="f24be-106">Phone System Direct 라우팅을 배포하고 네트워크 지역, 사이트 및 서브넷을 설정한 후 라우팅을 사용하도록 Location-Based 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="f24be-107">이 문서의 단계를 완료하려면 PowerShell cmdlet에 대해 잘 알고 있는 것이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="f24be-108">자세한 내용은 [Teams PowerShell 개요 를 참조하세요.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f24be-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="f24be-109">다음에 대해 Location-Based 라우팅을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="f24be-110">사용자</span><span class="sxs-lookup"><span data-stu-id="f24be-110">Users</span></span>
- <span data-ttu-id="f24be-111">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="f24be-111">Network sites</span></span>
- <span data-ttu-id="f24be-112">게이트웨이 구성</span><span class="sxs-lookup"><span data-stu-id="f24be-112">Gateway configurations</span></span>
- <span data-ttu-id="f24be-113">통화 정책</span><span class="sxs-lookup"><span data-stu-id="f24be-113">Calling policies</span></span>

<span data-ttu-id="f24be-114">[Microsoft Team](#using-the-microsoft-teams-admin-center) 관리 센터 또는 [PowerShel](#using-powershell)l을 사용하여 라우팅을 Location-Based 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="f24be-115">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="f24be-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="f24be-116">사용자 Location-Based 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="f24be-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="f24be-117">음성 라우팅 정책을 만들고 정책에 PSTN 사용량을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="f24be-118">정책에 PSTN 사용량을 할당할 때 다음 중 하나를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="f24be-119">사이트에 로컬 PSTN 게이트웨이를 사용하는 음성 경로에 연결된 PSTN 사용량을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="f24be-120">라우팅 제한이 필요하지 않은 지역에 있는 PSTN 게이트웨이를 사용하는 음성 경로에 Location-Based PSTN 사용량을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="f24be-121">라우팅 제한을 적용해야 하는 사용자에게 음성 라우팅 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="f24be-122">음성 라우팅 정책을 만들고 사용자에게 할당하는 방법에 대한 자세한 내용은 Microsoft Teams의 음성 라우팅 정책 관리를 [참조합니다.](manage-voice-routing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f24be-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="f24be-123">네트워크 Location-Based 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="f24be-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="f24be-124">라우팅 Location-Based 적용해야 하는 사이트에 대한 Location-Based 라우팅을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="f24be-125">이렇게하려면 Microsoft Teams 관리 센터의 왼쪽 탐색에서 위치 네트워크 토폴로지로 이동하여 네트워크 사이트를 선택하고 편집을 클릭한 다음 위치 기반 라우팅을  >   **를 켜면 됩니다.** </span><span class="sxs-lookup"><span data-stu-id="f24be-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="f24be-126">자세한 내용은 네트워크 토폴로지 [관리를 참조합니다.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="f24be-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="f24be-127">게이트웨이에 Location-Based 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="f24be-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="f24be-128">PSTN Location-Based 호출을 라우팅하는 PSTN 게이트웨이에 대한 호출을 라우팅하고 게이트웨이가 있는 네트워크 사이트를 연결하는 게이트웨이에 대한 라우팅을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="f24be-129">왼쪽 탐색에서 Voice   >  **Direct 라우팅으로** 이동한 다음 **SBC 탭을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f24be-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="f24be-130">SBC를 선택한 다음 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f24be-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="f24be-131">위치 **기반 라우팅** 및 미디어 최적화에서 위치 기반 라우팅 사용 **을 를 니다.**</span><span class="sxs-lookup"><span data-stu-id="f24be-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="f24be-132">게이트웨이 사이트 ID를 지정한 다음, 우회 모드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="f24be-133">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="f24be-134">호출 정책에 Location-Based 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="f24be-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="f24be-135">특정 Location-Based 라우팅을 적용하기 위해 사용자의 호출 정책을 설정하여 PSTN 통화 우회를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="f24be-136">이렇게 하여 통화  정책에서 호출 우회 방지 설정을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="f24be-137">자세한 내용은 Teams 의 [통화 정책을 참조합니다.](teams-calling-policy.md)</span><span class="sxs-lookup"><span data-stu-id="f24be-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="f24be-138">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="f24be-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="f24be-139">사용자 Location-Based 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="f24be-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="f24be-140">[Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet을 사용하여 PSTN 사용량을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-140">Use the [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="f24be-141">여러 사용의 경우 각 사용량을 콤마로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="f24be-142">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="f24be-143">[New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet을 사용하여 음성 라우팅 정책을 만들어 사용자를 적절한 PSTN 사용량과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-143">Use the [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="f24be-144">음성 라우팅 정책에 PSTN 사용량을 할당할 때 다음 중 하나를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="f24be-145">사이트에 로컬 PSTN 게이트웨이를 사용하는 음성 경로에 연결된 PSTN 사용량 사용</span><span class="sxs-lookup"><span data-stu-id="f24be-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="f24be-146">라우팅 제한이 필요하지 않은 지역에 있는 PSTN 게이트웨이를 사용하는 음성 경로에 Location-Based PSTN 사용량을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="f24be-147">이 예제에서는 두 개의 새 음성 라우팅 정책을 만들고 PSTN 사용량을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="f24be-148">다음 표에서는 이 예제에 정의된 음성 라우팅 정책을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="f24be-149">음성 라우팅 정책 1</span><span class="sxs-lookup"><span data-stu-id="f24be-149">Voice routing policy 1</span></span>|<span data-ttu-id="f24be-150">음성 라우팅 정책 2</span><span class="sxs-lookup"><span data-stu-id="f24be-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="f24be-151">온라인 음성 정책 ID</span><span class="sxs-lookup"><span data-stu-id="f24be-151">Online voice policy ID</span></span>   |<span data-ttu-id="f24be-152">Delhi 온라인 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="f24be-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="f24be-153">Hyderabad 온라인 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="f24be-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="f24be-154">온라인 PSTN 사용량</span><span class="sxs-lookup"><span data-stu-id="f24be-154">Online PSTN usages</span></span>  |<span data-ttu-id="f24be-155">장거리</span><span class="sxs-lookup"><span data-stu-id="f24be-155">Long Distance</span></span>  |<span data-ttu-id="f24be-156">장거리, 로컬, 내부</span><span class="sxs-lookup"><span data-stu-id="f24be-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="f24be-157">[Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet을 사용하여 라우팅 제한을 적용해야 하는 사용자에게 온라인 음성 라우팅 정책을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="f24be-158">네트워크 Location-Based 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="f24be-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="f24be-159">[Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet을 사용하여 Location-Based 라우팅을 사용하도록 설정하고 라우팅 제한을 적용해야 하는 네트워크 사이트에 음성 라우팅 정책을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-159">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="f24be-160">이 예제에서는 Delhi Location-Based 및 Hyderabad 사이트에 대한 Location-Based 라우팅을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="f24be-161">다음 표에서는 이 예제에서 Location-Based 라우팅에 사용하도록 설정된 사이트를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="f24be-162">Site 1(Delhi)</span><span class="sxs-lookup"><span data-stu-id="f24be-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="f24be-163">Site 2(Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f24be-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="f24be-164">사이트 이름</span><span class="sxs-lookup"><span data-stu-id="f24be-164">Site name</span></span>    |<span data-ttu-id="f24be-165">Site 1(Delhi)</span><span class="sxs-lookup"><span data-stu-id="f24be-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="f24be-166">Site 2(Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f24be-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="f24be-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="f24be-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="f24be-168">True</span><span class="sxs-lookup"><span data-stu-id="f24be-168">True</span></span>    |<span data-ttu-id="f24be-169">True</span><span class="sxs-lookup"><span data-stu-id="f24be-169">True</span></span>    |
    |<span data-ttu-id="f24be-170">서브넷</span><span class="sxs-lookup"><span data-stu-id="f24be-170">Subnets</span></span>     |<span data-ttu-id="f24be-171">서브넷 1(Delhi)</span><span class="sxs-lookup"><span data-stu-id="f24be-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="f24be-172">서브넷 2(Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f24be-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="f24be-173">게이트웨이에 Location-Based 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="f24be-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="f24be-174">[New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet을 사용하여 각 게이트웨이 또는 네트워크 사이트에 대한 게이트웨이 구성을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-174">Use the [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="f24be-175">여러 게이트웨이가 시스템(예: 게이트웨이 또는 PBX)에 연결되어 있는 경우 라우팅 제한을 사용하도록 각 게이트웨이를 Location-Based 합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="f24be-176">이 예제에서는 각 게이트웨이에 대해 하나의 게이트웨이 구성을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="f24be-177">자세한 내용은 직접 라우팅 [구성을 참조하세요.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="f24be-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="f24be-178">[Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet을 사용하여 라우팅 제한을 적용해야 하는 게이트웨이에 Location-Based 라우팅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-178">Use the [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="f24be-179">PSTN Location-Based 호출을 라우팅하는 PSTN 게이트웨이에 대한 호출을 라우팅하고 게이트웨이가 있는 네트워크 사이트를 연결하는 게이트웨이에 대한 라우팅을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="f24be-180">이 예제에서는 Location-Based 및 Hyderabad 사이트의 PSTN 게이트웨이에 연결된 각 게이트웨이에 대한 라우팅을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="f24be-181">PSTN에 Location-Based 라우팅하지 않는 게이트웨이에 대한 라우팅을 사용하도록 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="f24be-182">그러나 여전히 시스템이 있는 네트워크 사이트에 게이트웨이를 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="f24be-183">이 게이트웨이를 통해 Location-Based 엔드포인트에 도달하는 PSTN 호출에 대해 라우팅 제한을 적용해야 하기 때문이다.</span><span class="sxs-lookup"><span data-stu-id="f24be-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="f24be-184">이 예제에서는 Location-Based 및 Hyderabad 사이트의 PBX 시스템에 연결된 각 게이트웨이에 대해 라우팅을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="f24be-185">호출 정책에 Location-Based 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="f24be-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="f24be-186">특정 Location-Based 라우팅을 적용하기 위해 사용자의 음성 정책을 설정하여 PTSN의 에지 우회를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="f24be-187">[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet을 사용하여 PSTN Location-Based 우회를 방지하여 라우팅을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-187">Use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="f24be-188">이 예제에서는 User1의 호출 정책에 대한 PSTN 호출 우회를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="f24be-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="f24be-189">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f24be-189">Related topics</span></span>

- [<span data-ttu-id="f24be-190">Teams의 클라우드 음성 기능에 대한 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="f24be-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)