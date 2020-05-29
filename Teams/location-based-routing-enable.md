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
description: 사용자, 네트워크 사이트, 게이트웨이 구성, 통화 정책에 대해 위치 기반 라우팅을 사용 하도록 설정 하는 방법에 대해 알아봅니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4daf270dcd67dc732bba5e5fe134d5a0994dcd75
ms.sourcegitcommit: 2295a668a6f118b95f010e81150351741572b076
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412645"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="5f6e1-103">직접 라우팅에 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="5f6e1-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="5f6e1-104">이 문서에 나와 있는 단계를 수행 하기 전에 위치 [기반 라우팅에 대 한 네트워크 설정 구성](location-based-routing-configure-network-settings.md)단계를 [직접 라우팅과 완료 하기 위한 계획 위치 기반 라우팅을](location-based-routing-plan.md) 읽어 주십시오.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="5f6e1-105">이 문서에서는 직접 라우팅에 위치 기반 라우팅을 사용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="5f6e1-106">전화 시스템 직접 라우팅을 배포 하 고 네트워크 지역, 사이트 및 서브넷을 설정한 후에는 위치 기반 라우팅을 사용할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="5f6e1-107">이 문서의 단계를 완료 하려면 PowerShell cmdlet에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="5f6e1-108">자세히 알아보려면 [팀 PowerShell 개요](teams-powershell-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="5f6e1-109">위치 기반 회람을 사용 해야 하는 경우는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="5f6e1-110">사용자</span><span class="sxs-lookup"><span data-stu-id="5f6e1-110">Users</span></span>
- <span data-ttu-id="5f6e1-111">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="5f6e1-111">Network sites</span></span>
- <span data-ttu-id="5f6e1-112">게이트웨이 구성</span><span class="sxs-lookup"><span data-stu-id="5f6e1-112">Gateway configurations</span></span>
- <span data-ttu-id="5f6e1-113">통화 정책</span><span class="sxs-lookup"><span data-stu-id="5f6e1-113">Calling policies</span></span>

<span data-ttu-id="5f6e1-114">[Microsoft 팀 관리 센터](#using-the-microsoft-teams-admin-center) 또는 [powershel](#using-powershell)l을 사용 하 여 위치 기반 회람을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="5f6e1-115">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="5f6e1-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="5f6e1-116">사용자의 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="5f6e1-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="5f6e1-117">음성 라우팅 정책을 만들고 PSTN 용도를 정책에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="5f6e1-118">PSTN 용도를 정책에 할당 하는 경우 다음 중 하나를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="5f6e1-119">사이트에 로컬 PSTN 게이트웨이를 사용 하는 음성 경로에 연결 된 PSTN 용도를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="5f6e1-120">위치 기반 라우팅 제한이 필요 하지 않은 지역에 있는 PSTN 게이트웨이를 사용 하는 음성 경로에 연결 된 PSTN 사용량을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="5f6e1-121">라우팅 제한을 적용 해야 하는 사용자에 게 음성 라우팅 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="5f6e1-122">음성 라우팅 정책을 만들고 사용자에 게 할당 하는 방법에 대해 자세히 알아보려면 [Microsoft 팀에서 음성 라우팅 정책 관리](manage-voice-routing-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="5f6e1-123">네트워크 사이트용 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="5f6e1-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="5f6e1-124">라우팅 제한을 적용 해야 하는 사이트에 대해 위치 기반 라우팅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="5f6e1-125">이렇게 하려면 Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **위치**  >  **네트워크 토폴로지로**이동 하 여 네트워크 사이트를 선택 하 고 **편집**을 클릭 한 다음 **위치 기반 라우팅**설정을 켭니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="5f6e1-126">자세히 알아보려면 [네트워크 토폴로지 관리](manage-your-network-topology.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="5f6e1-127">게이트웨이에 대 한 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="5f6e1-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="5f6e1-128">PSTN으로 호출을 라우팅하는 PSTN 게이트웨이로 통화를 라우팅하고 게이트웨이가 있는 네트워크 사이트를 연결 하는 게이트웨이에 대 한 위치 기반 라우팅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="5f6e1-129">왼쪽 탐색 창에서 **음성**  >  **다이렉트 라우팅으로**이동한 다음 **SBCs** 탭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="5f6e1-130">SBC를 선택 하 고 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="5f6e1-131">**위치 기반 라우팅 및 미디어 최적화**에서 **위치 기반 라우팅 사용**을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="5f6e1-132">게이트웨이 사이트 ID를 지정한 다음 우회 모드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="5f6e1-133">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="5f6e1-134">호출 정책에 대해 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="5f6e1-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="5f6e1-135">특정 사용자에 대해 위치 기반 라우팅을 적용 하려면 PSTN 유료 바이패스를 방지 하는 사용자의 호출 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="5f6e1-136">이렇게 하려면 통화 정책에서 **무료 바이패스 방지** 설정을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="5f6e1-137">자세히 알아보려면 [팀에서 정책 호출](teams-calling-policy.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="5f6e1-138">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="5f6e1-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="5f6e1-139">사용자의 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="5f6e1-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="5f6e1-140">[CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet을 사용 하 여 PSTN 사용량을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-140">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="5f6e1-141">여러 용도를 위해 각 용도를 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="5f6e1-142">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="5f6e1-143">[CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet을 사용 하 여 사용자를 적절 한 PSTN 용도에 연결 하는 음성 라우팅 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-143">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="5f6e1-144">음성 라우팅 정책에 PSTN 용도를 할당 하는 경우 다음 중 하나를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="5f6e1-145">사이트에 로컬 PSTN 게이트웨이를 사용 하는 음성 경로에 연결 된 PSTN 용도 사용</span><span class="sxs-lookup"><span data-stu-id="5f6e1-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="5f6e1-146">위치 기반 라우팅 제한이 필요 하지 않은 지역에 있는 PSTN 게이트웨이를 사용 하는 음성 경로에 연결 된 PSTN 사용량을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="5f6e1-147">이 예제에서는 두 개의 새로운 음성 라우팅 정책을 만들고 PSTN 용도를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="5f6e1-148">다음 표에는이 예제에 정의 된 음성 라우팅 정책이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="5f6e1-149">음성 라우팅 정책 1</span><span class="sxs-lookup"><span data-stu-id="5f6e1-149">Voice routing policy 1</span></span>|<span data-ttu-id="5f6e1-150">음성 라우팅 정책 2</span><span class="sxs-lookup"><span data-stu-id="5f6e1-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="5f6e1-151">온라인 음성 정책 ID</span><span class="sxs-lookup"><span data-stu-id="5f6e1-151">Online voice policy ID</span></span>   |<span data-ttu-id="5f6e1-152">이 (가) 뉴델리 온라인 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="5f6e1-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="5f6e1-153">Hyderabad 온라인 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="5f6e1-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="5f6e1-154">온라인 PSTN 용도</span><span class="sxs-lookup"><span data-stu-id="5f6e1-154">Online PSTN usages</span></span>  |<span data-ttu-id="5f6e1-155">시외</span><span class="sxs-lookup"><span data-stu-id="5f6e1-155">Long Distance</span></span>  |<span data-ttu-id="5f6e1-156">장거리, 지역, 내부</span><span class="sxs-lookup"><span data-stu-id="5f6e1-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="5f6e1-157">[CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet을 사용 하 여 라우팅 제한을 적용 해야 하는 사용자에 게 온라인 음성 라우팅 정책을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="5f6e1-158">네트워크 사이트용 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="5f6e1-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="5f6e1-159">[Set-Csten앤틸리스 site](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet을 사용 하 여 위치 기반 라우팅을 사용 하도록 설정 하 고 라우팅 제한을 적용 해야 하는 네트워크 사이트에 음성 라우팅 정책을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-159">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="5f6e1-160">이 예제에서는 뉴델리 사이트 및 Hyderabad 사이트에 대 한 위치 기반 라우팅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="5f6e1-161">다음 표에는이 예제에서 위치 기반 라우팅에 사용할 수 있는 사이트가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="5f6e1-162">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="5f6e1-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="5f6e1-163">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="5f6e1-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="5f6e1-164">사이트 이름</span><span class="sxs-lookup"><span data-stu-id="5f6e1-164">Site name</span></span>    |<span data-ttu-id="5f6e1-165">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="5f6e1-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="5f6e1-166">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="5f6e1-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="5f6e1-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="5f6e1-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="5f6e1-168">False</span><span class="sxs-lookup"><span data-stu-id="5f6e1-168">True</span></span>    |<span data-ttu-id="5f6e1-169">False</span><span class="sxs-lookup"><span data-stu-id="5f6e1-169">True</span></span>    |
    |<span data-ttu-id="5f6e1-170">네트</span><span class="sxs-lookup"><span data-stu-id="5f6e1-170">Subnets</span></span>     |<span data-ttu-id="5f6e1-171">서브넷 1 (뉴델리)</span><span class="sxs-lookup"><span data-stu-id="5f6e1-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="5f6e1-172">서브넷 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="5f6e1-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="5f6e1-173">게이트웨이에 대 한 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="5f6e1-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="5f6e1-174">[새 CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet을 사용 하 여 각 게이트웨이 또는 네트워크 사이트에 대 한 게이트웨이 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-174">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="5f6e1-175">여러 게이트웨이가 시스템 (예: 게이트웨이 또는 PBX)과 연결 되어 있는 경우 위치 기반 라우팅 제한을 사용 하도록 각 게이트웨이를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="5f6e1-176">이 예제에서는 각 게이트웨이에 대해 하나의 게이트웨이 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="5f6e1-177">자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="5f6e1-178">[CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet을 사용 하 여 라우팅 제한을 적용 해야 하는 게이트웨이에 대 한 위치 기반 라우팅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-178">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="5f6e1-179">PSTN으로 호출을 라우팅하는 PSTN 게이트웨이로 통화를 라우팅하고 게이트웨이가 있는 네트워크 사이트를 연결 하는 게이트웨이에 대 한 위치 기반 라우팅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="5f6e1-180">이 예제에서는 뉴델리 및 Hyderabad 사이트의 PSTN 게이트웨이와 연결 된 각 게이트웨이에 대해 위치 기반 라우팅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="5f6e1-181">PSTN으로 호출을 라우팅되지 않는 게이트웨이에 대해 위치 기반 라우팅을 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="5f6e1-182">그러나이 경우에도 시스템이 있는 네트워크 사이트에 게이트웨이를 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="5f6e1-183">이 게이트웨이를 통해 연결 된 끝점에 도달 하는 PSTN 호출에 대해 위치 기반 라우팅 제한을 적용 해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="5f6e1-184">이 예제에서는 Hyderabad 사이트에서 PBX 시스템과 연결 된 각 게이트웨이에 대해 위치 기반 라우팅이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="5f6e1-185">호출 정책에 대해 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="5f6e1-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="5f6e1-186">특정 사용자에 대해 위치 기반 라우팅을 적용 하려면, 사용자의 음성 정책을 설정 하 여 PTSN을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="5f6e1-187">[CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet을 사용 하 여 PSTN 유료 바이패스를 방지 하 여 위치 기반 라우팅을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-187">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="5f6e1-188">이 예제에서는 PSTN 유료 바이패스를 User1's 호출 정책을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f6e1-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="5f6e1-189">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5f6e1-189">Related topics</span></span>

- [<span data-ttu-id="5f6e1-190">팀의 클라우드 음성 기능에 대 한 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="5f6e1-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
