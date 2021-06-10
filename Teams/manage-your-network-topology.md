---
title: 클라우드 음성 기능에 대한 네트워크 토폴로지 관리 Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 클라우드 음성 기능에 대한 네트워크 설정을 구성하는 방법을 Microsoft Teams.
ms.openlocfilehash: c77f1e6d31953ce529bff1fab6aa16e1d889e29f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101064"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="12220-103">클라우드 음성 기능에 대한 네트워크 토폴로지 관리 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="12220-103">Manage your network topology for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="12220-104">조직에서 직접 라우팅 [](location-based-routing-plan.md) 또는 동적 긴급 호출에 대한 [](configure-dynamic-emergency-calling.md)위치 기반 라우팅을 배포하는 경우, 해당 조직에서 이러한 클라우드 음성 기능과 함께 사용하도록 네트워크 설정을 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="12220-104">If your organization is deploying [Location-Based Routing for Direct Routing](location-based-routing-plan.md) or [dynamic emergency calling](configure-dynamic-emergency-calling.md), you must configure network settings for use with these cloud voice features in Microsoft Teams.</span></span> <span data-ttu-id="12220-105">네트워크 설정은 클라이언트의 위치를 결정하고 네트워크 Teams, 네트워크 사이트, 서브넷 및 신뢰할 수 있는 IP 주소를 포함하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="12220-105">Network settings are used to determine the location of a Teams client and include network regions, network sites, subnets, and trusted IP addresses.</span></span> <span data-ttu-id="12220-106">배포하는 클라우드 음성 기능 및 기능에 따라 이러한 설정을 일부 또는 모두 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-106">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="12220-107">이러한 용어에 대한 자세한 내용은 클라우드 음성 기능에 [대한 네트워크 설정을 참조하세요.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="12220-107">To learn more about these terms, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="12220-108">관리 센터의 네트워크  토폴로지 페이지에서 또는 Microsoft Teams 사용하여 네트워크 설정을 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12220-108">You configure network settings on the **Network topology** page of the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="12220-109">관리 센터에서 네트워크 Microsoft Teams 구성</span><span class="sxs-lookup"><span data-stu-id="12220-109">Configure network settings in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="12220-110">네트워크 토폴로지 페이지의 네트워크 사이트 탭에서  네트워크 지역, 네트워크 사이트 및 서브넷을 **정의합니다.**</span><span class="sxs-lookup"><span data-stu-id="12220-110">You define network regions, network sites, and subnets on the **Network sites** tab of the **Network topology** page.</span></span> <span data-ttu-id="12220-111">여기서는 네트워크 사이트를 만들거나 수정하고, 사이트를 네트워크 지역과 연결하고, 서브넷을 사이트에 연결하고, 위치 기반 라우팅을 설정하고, 사이트에 긴급 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12220-111">Here, you can create or modify a network site, associate a site with a network region, associate a subnet to the site, turn on Location-based Routing, and assign emergency policies to the site.</span></span> <span data-ttu-id="12220-112">또한 모든 사이트에 전역적으로 사용할 수 있는 네트워크 지역을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12220-112">You can also add network regions that can be used globally for all sites.</span></span>

#### <a name="add-and-configure-a-network-site"></a><span data-ttu-id="12220-113">네트워크 사이트 추가 및 구성</span><span class="sxs-lookup"><span data-stu-id="12220-113">Add and configure a network site</span></span>

1. <span data-ttu-id="12220-114">관리 센터의 왼쪽 Microsoft Teams 위치 네트워크 토폴로지로 이동한 다음 네트워크 사이트   >   **탭을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12220-114">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="12220-115">추가 를 클릭한 다음 사이트에 대한 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-115">Click **Add**, and then enter a name and description for the site.</span></span>

    ![네트워크 사이트 추가 페이지의 스크린샷](media/manage-network-topology-add-site.png)

3. <span data-ttu-id="12220-117">사이트를 네트워크 지역과 연결하려면 네트워크 지역 **추가를** 클릭하고 기존  지역을 선택하거나 추가를 클릭하여 지역을 추가한 다음 링크를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12220-117">To associate the site with a network region, click **Add network region**, select an existing region or click **Add** to add a region, and then click **Link**.</span></span>  
4. <span data-ttu-id="12220-118">사이트에 Location-Based 라우팅을 사용하도록 설정하려면 위치 기반 라우팅 **을 를 차례로 하세요.**</span><span class="sxs-lookup"><span data-stu-id="12220-118">To enable Location-Based Routing for the site, turn on **Location based routing**.</span></span>
5. <span data-ttu-id="12220-119">사이트에 응급 서비스 정책을 할당하기 위해 다음 중 하나 또는 둘 다를 합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-119">To assign emergency services policies to the site, do one or both of the following:</span></span>

    - <span data-ttu-id="12220-120">조직에서 통화 계획을 사용하거나 직접 라우팅을 전화 시스템 경우 긴급 통화 정책에서 원하는 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-120">If your organization uses Calling Plans or deployed Phone System Direct Routing, under **Emergency calling policy**, select the policy that you want.</span></span>
    - <span data-ttu-id="12220-121">조직에서 직접 전화 시스템 배포한 경우 긴급 호출 라우팅 정책에서 원하는 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-121">If your organization deployed Phone System Direct Routing, under **Emergency call routing policy**, select the  policy that you want.</span></span>

6. <span data-ttu-id="12220-122">서브넷을 사이트에 연결하려면 **서브넷** 아래에서 서브넷 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12220-122">To associate a subnet to the site, under **Subnets**, click **Add subnets**.</span></span> <span data-ttu-id="12220-123">IP 버전, IP 주소, 네트워크 범위를 지정하고 설명을 추가한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12220-123">Specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span> <span data-ttu-id="12220-124">각 서브넷은 특정 사이트와 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-124">Each subnet must be associated with a specific site.</span></span>
7. <span data-ttu-id="12220-125">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-125">Click **Save**.</span></span>

#### <a name="modify-a-network-site"></a><span data-ttu-id="12220-126">네트워크 사이트 수정</span><span class="sxs-lookup"><span data-stu-id="12220-126">Modify a network site</span></span>

1. <span data-ttu-id="12220-127">관리 센터의 왼쪽 Microsoft Teams 위치 네트워크 토폴로지로 이동한 다음 네트워크 사이트   >   **탭을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12220-127">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="12220-128">사이트 이름의 왼쪽을 클릭하여 사이트를 선택한 다음 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12220-128">Select the site by clicking to the left of the site name, and then click **Edit**.</span></span>
3. <span data-ttu-id="12220-129">원하는 내용을 변경한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12220-129">Make the changes that you want, and then click **Save.**</span></span>

### <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="12220-130">외부 신뢰할 수 있는 IP 주소 관리</span><span class="sxs-lookup"><span data-stu-id="12220-130">Manage external trusted IP addresses</span></span>

<span data-ttu-id="12220-131">관리 센터의 네트워크 토폴로지 페이지의  신뢰할 수 있는 **IP** 탭에서 외부 Microsoft Teams 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-131">You manage external trusted IP addresses on the **Trusted IPs** tab on the **Network topology** page of the Microsoft Teams admin center.</span></span> <span data-ttu-id="12220-132">신뢰할 수 있는 외부 IP 주소를 무제한으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12220-132">You can add an unlimited number of external trusted IP addresses.</span></span>

#### <a name="add-a-trusted-ip-address"></a><span data-ttu-id="12220-133">신뢰할 수 있는 IP 주소 추가</span><span class="sxs-lookup"><span data-stu-id="12220-133">Add a trusted IP address</span></span>

1. <span data-ttu-id="12220-134">관리 센터의 왼쪽 탐색에서 Microsoft Teams 네트워크 토폴로지로 이동한 다음 신뢰할 수 있는  >   **IPS 탭을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12220-134">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="12220-135">새로 **고치기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12220-135">Click **New**.</span></span>
3. <span data-ttu-id="12220-136">신뢰할 수 **있는 IP** 주소 추가 창에서 IP 버전, IP 주소, 네트워크 범위를 지정하고 설명을 추가한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12220-136">In the **Add trusted IP address** pane, specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span>

    ![신뢰할 수 있는 IP 주소 추가 창의 스크린샷](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a><span data-ttu-id="12220-138">신뢰할 수 있는 IP 주소 편집</span><span class="sxs-lookup"><span data-stu-id="12220-138">Edit a trusted IP address</span></span>

1. <span data-ttu-id="12220-139">관리 센터의 왼쪽 탐색에서 Microsoft Teams 네트워크 토폴로지로 이동한 다음 신뢰할 수 있는  >   **IPS 탭을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12220-139">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="12220-140">IP 주소를 왼쪽으로 클릭한 다음 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12220-140">Select the IP address by clicking to the left of it, and then click **Edit**.</span></span>
3. <span data-ttu-id="12220-141">신뢰할 수 **있는 IP 주소 편집** 창에서 원하는 내용을 변경한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12220-141">In the **Edit trusted IP address** pane, make the changes that you want, and then click **Apply**.</span></span>

## <a name="configure-network-settings-using-powershell"></a><span data-ttu-id="12220-142">PowerShell을 사용하여 네트워크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="12220-142">Configure network settings using PowerShell</span></span>

<span data-ttu-id="12220-143">이 섹션의 단계를 완료하려면 PowerShell cmdlet에 대해 잘 알고 있는 것이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-143">To complete the steps in this section, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="12220-144">자세한 내용은 [PowerShell Teams 참조하세요.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="12220-144">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="12220-145">네트워크 지역 정의</span><span class="sxs-lookup"><span data-stu-id="12220-145">Define network regions</span></span>

 <span data-ttu-id="12220-146">[New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet을 사용하여 네트워크 지역을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-146">Use the [New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet to define network regions.</span></span> <span data-ttu-id="12220-147">RegionID 매개 변수는 지역의 지역을 나타내는 논리적 이름이며 종속성 또는 제한이 없는 것이고 CentralSite 사이트 ID 매개 변수는 &lt; &gt; 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="12220-147">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="12220-148">이 예제에서는 인도라는 네트워크 지역을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-148">In this example, we create a network region named India.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

<span data-ttu-id="12220-149">[Set-CsTenantNetworkRegion 을 참조합니다.](/powershell/module/skype/set-cstenantnetworkregion)</span><span class="sxs-lookup"><span data-stu-id="12220-149">See also [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworkregion).</span></span>

### <a name="define-network-sites"></a><span data-ttu-id="12220-150">네트워크 사이트 정의</span><span class="sxs-lookup"><span data-stu-id="12220-150">Define network sites</span></span>

<span data-ttu-id="12220-151">[New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet을 사용하여 네트워크 사이트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-151">Use the [New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> <span data-ttu-id="12220-152">각 네트워크 사이트는 네트워크 지역과 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-152">Each network site must be associated with a network region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="12220-153">이 예제에서는 인도 지역에 두 개의 새 네트워크 사이트인 Delhi 및 Hyderabad를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-153">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

<span data-ttu-id="12220-154">다음 표에는 이 예제에 정의된 네트워크 사이트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="12220-154">The following table shows the network sites defined in this example.</span></span>

||<span data-ttu-id="12220-155">사이트 1</span><span class="sxs-lookup"><span data-stu-id="12220-155">Site 1</span></span> |<span data-ttu-id="12220-156">사이트 2</span><span class="sxs-lookup"><span data-stu-id="12220-156">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="12220-157">사이트 ID</span><span class="sxs-lookup"><span data-stu-id="12220-157">Site ID</span></span>    |    <span data-ttu-id="12220-158">Site 1(Delhi)</span><span class="sxs-lookup"><span data-stu-id="12220-158">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="12220-159">Site 2(Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="12220-159">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="12220-160">지역 ID</span><span class="sxs-lookup"><span data-stu-id="12220-160">Region ID</span></span>  |     <span data-ttu-id="12220-161">지역 1(인도)</span><span class="sxs-lookup"><span data-stu-id="12220-161">Region 1 (India)</span></span>    |   <span data-ttu-id="12220-162">지역 1(인도)</span><span class="sxs-lookup"><span data-stu-id="12220-162">Region 1 (India)</span></span>      |

<span data-ttu-id="12220-163">[Set-CsTenantNetworkRegion 을 참조합니다.](/powershell/module/skype/set-cstenantnetworksite)</span><span class="sxs-lookup"><span data-stu-id="12220-163">See also [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworksite).</span></span>

### <a name="define-network-subnets"></a><span data-ttu-id="12220-164">네트워크 서브넷 정의</span><span class="sxs-lookup"><span data-stu-id="12220-164">Define network subnets</span></span>

<span data-ttu-id="12220-165">[New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet을 사용하여 네트워크 서브넷을 정의하고 네트워크 사이트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-165">Use the [New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="12220-166">각 네트워크 서브넷은 하나의 사이트와만 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12220-166">Each network subnet can only be associated with one site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="12220-167">이 예제에서는 서브넷 192.168.0.0과 델리 네트워크 사이트 간 및 서브넷 2001:4898:e8:25:844e:926f:85ad:dd8e 및 Hyderabad 네트워크 사이트 간에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-167">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

<span data-ttu-id="12220-168">다음 표에서는 이 예제에 정의된 서브넷을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="12220-168">The following table shows the subnets defined in this example.</span></span>

||<span data-ttu-id="12220-169">사이트 1</span><span class="sxs-lookup"><span data-stu-id="12220-169">Site 1</span></span> |<span data-ttu-id="12220-170">사이트 2</span><span class="sxs-lookup"><span data-stu-id="12220-170">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="12220-171">서브넷 ID</span><span class="sxs-lookup"><span data-stu-id="12220-171">Subnet ID</span></span>   |    <span data-ttu-id="12220-172">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="12220-172">192.168.0.0</span></span>     |  <span data-ttu-id="12220-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span><span class="sxs-lookup"><span data-stu-id="12220-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="12220-174">마스크</span><span class="sxs-lookup"><span data-stu-id="12220-174">Mask</span></span>  |     <span data-ttu-id="12220-175">24</span><span class="sxs-lookup"><span data-stu-id="12220-175">24</span></span>    |   <span data-ttu-id="12220-176">120</span><span class="sxs-lookup"><span data-stu-id="12220-176">120</span></span>      |
|<span data-ttu-id="12220-177">사이트 ID</span><span class="sxs-lookup"><span data-stu-id="12220-177">Site ID</span></span>  | <span data-ttu-id="12220-178">사이트(Delhi)</span><span class="sxs-lookup"><span data-stu-id="12220-178">Site (Delhi)</span></span> | <span data-ttu-id="12220-179">Site 2(Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="12220-179">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="12220-180">여러 서브넷의 경우 다음과 같은 스크립트를 사용하여 CSV 파일을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12220-180">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

<span data-ttu-id="12220-181">이 예제에서는 CSV 파일이 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="12220-181">In this example, the CSV file looks something like this:</span></span>

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```


<span data-ttu-id="12220-182">[Set-CsTenantNetworkSubnet 을 참조합니다.](/powershell/module/skype/set-cstenantnetworksubnet)</span><span class="sxs-lookup"><span data-stu-id="12220-182">See also [Set-CsTenantNetworkSubnet](/powershell/module/skype/set-cstenantnetworksubnet).</span></span>


### <a name="define-external-subnets-external-trusted-ip-addresses"></a><span data-ttu-id="12220-183">외부 서브넷 정의(외부 신뢰할 수 있는 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="12220-183">Define external subnets (external trusted IP addresses)</span></span>

<span data-ttu-id="12220-184">[New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet을 사용하여 외부 서브넷을 정의하고 테넌트에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="12220-184">Use the [New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="12220-185">테넌트에 대한 무제한 외부 서브넷을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12220-185">You can define an unlimited number of external subnets for a tenant.</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

<span data-ttu-id="12220-186">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="12220-186">For example:</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

<span data-ttu-id="12220-187">[Set-CsTenantTrustedIPAddress 를 참조합니다.](/powershell/module/skype/set-cstenanttrustedipaddress)</span><span class="sxs-lookup"><span data-stu-id="12220-187">See also [Set-CsTenantTrustedIPAddress](/powershell/module/skype/set-cstenanttrustedipaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="12220-188">관련 항목</span><span class="sxs-lookup"><span data-stu-id="12220-188">Related topics</span></span>

- [<span data-ttu-id="12220-189">클라우드 음성 기능에 대한 네트워크 Teams</span><span class="sxs-lookup"><span data-stu-id="12220-189">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
