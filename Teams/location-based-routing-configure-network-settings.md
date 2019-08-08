---
title: 위치 기반 라우팅에 대 한 네트워크 설정 구성
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 직접 라우팅에 대 한 위치 기반 라우팅에 대 한 네트워크 지역, 사이트 및 서브넷을 만들고 설정 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f6f6f1e74cc50b37ade03e97106d2befe36a6dd
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245109"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="b094f-103">위치 기반 라우팅에 대 한 네트워크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="b094f-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="b094f-104">아직 수행 하지 않은 경우 위치 기반 라우팅에 대 한 네트워크 설정을 구성 하기 전에 수행 해야 하는 다른 단계를 검토 하도록 [직접 라우팅 계획 위치 기반 라우팅을](location-based-routing-plan.md) 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="b094f-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="b094f-105">이 문서에서는 위치 기반 라우팅에 대 한 네트워크 설정을 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="b094f-106">조직에 직접 전화 시스템 라우팅을 배포한 후 다음 단계는 네트워크 지역, 네트워크 사이트 및 네트워크 서브넷을 만들고 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="b094f-107">이 문서의 단계를 완료 하려면 PowerShell cmdlet에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="b094f-108">자세히 알아보려면 [팀 PowerShell 개요](teams-powershell-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b094f-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="b094f-109">네트워크 지역 정의</span><span class="sxs-lookup"><span data-stu-id="b094f-109">Define network regions</span></span>
 <span data-ttu-id="b094f-110">네트워크 영역은 여러 지리적 영역에 걸친 네트워크의 다양 한 부분을 상호 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="b094f-111">[새-Csten앤틸리스 지역](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet을 사용 하 여 네트워크 지역을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-111">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet to define network regions.</span></span> <span data-ttu-id="b094f-112">영역 ID 매개 변수는 영역의 지리를 나타내는 논리 이름이 며, 종속성 또는 제한이 없으며 CentralSite &lt;site ID&gt; 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-112">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="b094f-113">이 예제에서는 인도 라는 네트워크 영역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="b094f-114">네트워크 사이트 정의</span><span class="sxs-lookup"><span data-stu-id="b094f-114">Define network sites</span></span>

<span data-ttu-id="b094f-115">[새-Csten앤틸리스 site](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet을 사용 하 여 네트워크 사이트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-115">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="b094f-116">이 예제에서는 인도 지역에 2 개의 새 네트워크 사이트, 뉴델리 및 Hyderabad을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="b094f-117">다음 표에는이 예제에 정의 된 네트워크 사이트가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="b094f-118">사이트 1</span><span class="sxs-lookup"><span data-stu-id="b094f-118">Site 1</span></span> |<span data-ttu-id="b094f-119">사이트 2</span><span class="sxs-lookup"><span data-stu-id="b094f-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b094f-120">사이트 ID</span><span class="sxs-lookup"><span data-stu-id="b094f-120">Site ID</span></span>    |    <span data-ttu-id="b094f-121">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="b094f-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="b094f-122">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b094f-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="b094f-123">지역 ID</span><span class="sxs-lookup"><span data-stu-id="b094f-123">Region ID</span></span>  |     <span data-ttu-id="b094f-124">지역 1 (인도)</span><span class="sxs-lookup"><span data-stu-id="b094f-124">Region 1 (India)</span></span>    |   <span data-ttu-id="b094f-125">지역 1 (인도)</span><span class="sxs-lookup"><span data-stu-id="b094f-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="b094f-126">네트워크 서브넷 정의</span><span class="sxs-lookup"><span data-stu-id="b094f-126">Define network subnets</span></span>

<span data-ttu-id="b094f-127">[새-Csten앤틸리스 subnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet을 사용 하 여 네트워크 서브넷을 정의 하 고 네트워크 사이트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-127">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="b094f-128">각 내부 서브넷은 한 사이트에만 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="b094f-129">이 예제에서는 서브넷 192.168.0.0과 뉴델리 네트워크 사이트 간 연결과 서브넷 2001 간 연결 (4898: e8:25:844e: 926f: 85ad: dd8e 및 Hyderabad network site를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="b094f-130">다음 표에는이 예제에 정의 된 서브넷이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="b094f-131">사이트 1</span><span class="sxs-lookup"><span data-stu-id="b094f-131">Site 1</span></span> |<span data-ttu-id="b094f-132">사이트 2</span><span class="sxs-lookup"><span data-stu-id="b094f-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b094f-133">서브넷 ID</span><span class="sxs-lookup"><span data-stu-id="b094f-133">Subnet ID</span></span>   |    <span data-ttu-id="b094f-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="b094f-134">192.168.0.0</span></span>     |  <span data-ttu-id="b094f-135">2001:4898: e8:25:844e: 926f: 85ad: dd8e</span><span class="sxs-lookup"><span data-stu-id="b094f-135">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="b094f-136">마스킹하</span><span class="sxs-lookup"><span data-stu-id="b094f-136">Mask</span></span>  |     <span data-ttu-id="b094f-137">fps</span><span class="sxs-lookup"><span data-stu-id="b094f-137">24</span></span>    |   <span data-ttu-id="b094f-138">120</span><span class="sxs-lookup"><span data-stu-id="b094f-138">120</span></span>      |
|<span data-ttu-id="b094f-139">사이트 ID</span><span class="sxs-lookup"><span data-stu-id="b094f-139">Site ID</span></span>  | <span data-ttu-id="b094f-140">사이트 (뉴델리)</span><span class="sxs-lookup"><span data-stu-id="b094f-140">Site (Delhi)</span></span> | <span data-ttu-id="b094f-141">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b094f-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="b094f-142">여러 서브넷의 경우 다음과 같은 스크립트를 사용 하 여 CSV 파일을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="b094f-143">이 예제에서 CSV 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="b094f-144">외부 서브넷 정의</span><span class="sxs-lookup"><span data-stu-id="b094f-144">Define external subnets</span></span>
<span data-ttu-id="b094f-145">[New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet을 사용 하 여 외부 서브넷을 정의 하 고 테 넌 트에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-145">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="b094f-146">테 넌 트에 대해 무제한 개수의 서브넷을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="b094f-147">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="b094f-148">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b094f-148">Next steps</span></span>
<span data-ttu-id="b094f-149">[직접 라우팅에 대해 위치 기반 라우팅 사용](location-based-routing-enable.md)으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b094f-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="b094f-150">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b094f-150">Related topics</span></span>
- [<span data-ttu-id="b094f-151">직접 라우팅에 대 한 위치 기반 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="b094f-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="b094f-152">위치 기반 라우팅 용어</span><span class="sxs-lookup"><span data-stu-id="b094f-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
