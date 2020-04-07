---
title: 로컬 미디어 최적화 직접 라우팅
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: 직접 라우팅에 대 한 로컬 미디어 최적화 구성
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3097f97a856dc4e947281847c65669c23c73a408
ms.sourcegitcommit: 25e70de7c943e22fe6ac6e8d6b4353ca68f81f83
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2020
ms.locfileid: "43158106"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="b2db8-103">직접 라우팅에 대 한 로컬 미디어 최적화 구성</span><span class="sxs-lookup"><span data-stu-id="b2db8-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="b2db8-104">로컬 미디어 최적화 구성은 위치 기반 라우팅과 동적 비상 전화와 같이 다른 클라우드 음성 기능에 공통적으로 사용 되는 네트워크 설정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="b2db8-105">네트워크 지역, 네트워크 사이트, 네트워크 서브넷 및 신뢰할 수 있는 IP 주소에 대 한 자세한 내용은 [클라우드 음성 기능에 대 한 네트워크 설정을](cloud-voice-network-settings.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2db8-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="b2db8-106">로컬 미디어 최적화를 구성 하기 전에 [직접 라우팅에 대 한 로컬 미디어 최적화](direct-routing-media-optimization.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2db8-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="b2db8-107">로컬 미디어 최적화를 구성 하려면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="b2db8-108">팀 관리 센터 또는 PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="b2db8-109">자세한 내용은 [네트워크 토폴로지 관리](manage-your-network-topology.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2db8-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="b2db8-110">사용자 및 SBC 사이트를 구성 합니다 (이 문서에서 설명).</span><span class="sxs-lookup"><span data-stu-id="b2db8-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="b2db8-111">SBC 공급 업체 사양에 따라 로컬 미디어 최적화를 위해 SBCs를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="b2db8-112">다음 다이어그램에는이 문서의 예제에 사용 된 네트워크 설정이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="b2db8-113">![네트워크 설정 예를 보여 주는 다이어그램](media/direct-routing-media-op-9.png "네트워크 설정 예")</span><span class="sxs-lookup"><span data-stu-id="b2db8-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="b2db8-114">사용자 및 SBC 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="b2db8-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="b2db8-115">사용자 및 SBC 사이트를 구성 하려면 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="b2db8-116">[신뢰할 수 있는 외부 IP 주소를 관리](#manage-external-trusted-ip-addresses)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="b2db8-117">네트워크 지역, 네트워크 사이트 및 네트워크 서브넷을 구성 하 여 [네트워크 토폴로지를 정의](#define-the-network-topology) 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="b2db8-118">사이트 (들)에 관련 모드 및 프록시 SBC 값을 사용 하 여 SBC를 할당 하 여 [가상 네트워크 토폴로지를 정의](#define-the-virtual-network-topology) 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="b2db8-119">SBC 공급 업체 사양에 따라 로컬 미디어 최적화에 대 한 SBC 구성</span><span class="sxs-lookup"><span data-stu-id="b2db8-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="b2db8-120">이 문서에서는 Microsoft 구성 요소에 대 한 구성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="b2db8-121">SBC 구성에 대 한 자세한 내용은 SBC 공급 업체 documenation을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2db8-121">For information on SBC configuration, see your SBC vendor documenation.</span></span>

<span data-ttu-id="b2db8-122">로컬 미디어 최적화는 다음 SBC 공급 업체에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="b2db8-123">공급 업체</span><span class="sxs-lookup"><span data-stu-id="b2db8-123">Vendor</span></span> | <span data-ttu-id="b2db8-124">지원부</span><span class="sxs-lookup"><span data-stu-id="b2db8-124">Product</span></span> |    <span data-ttu-id="b2db8-125">소프트웨어 버전</span><span class="sxs-lookup"><span data-stu-id="b2db8-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="b2db8-126">오디오 코드</span><span class="sxs-lookup"><span data-stu-id="b2db8-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="b2db8-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="b2db8-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="b2db8-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="b2db8-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="b2db8-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="b2db8-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="b2db8-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="b2db8-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="b2db8-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="b2db8-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="b2db8-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="b2db8-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="b2db8-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="b2db8-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="b2db8-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="b2db8-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="b2db8-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="b2db8-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="b2db8-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="b2db8-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="b2db8-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="b2db8-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="b2db8-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="b2db8-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="b2db8-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="b2db8-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="b2db8-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="b2db8-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="b2db8-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="b2db8-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="b2db8-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="b2db8-142">7.20A.256</span></span> |
| [<span data-ttu-id="b2db8-143">리본 SBC 코어</span><span class="sxs-lookup"><span data-stu-id="b2db8-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="b2db8-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="b2db8-144">SBC 5110</span></span>         | <span data-ttu-id="b2db8-145">8.2</span><span class="sxs-lookup"><span data-stu-id="b2db8-145">8.2</span></span>  |
|            |  <span data-ttu-id="b2db8-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="b2db8-146">SBC 5210</span></span>         | <span data-ttu-id="b2db8-147">8.2</span><span class="sxs-lookup"><span data-stu-id="b2db8-147">8.2</span></span>  |
|            |  <span data-ttu-id="b2db8-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="b2db8-148">SBC 5400</span></span>         | <span data-ttu-id="b2db8-149">8.2</span><span class="sxs-lookup"><span data-stu-id="b2db8-149">8.2</span></span>  |
|            |  <span data-ttu-id="b2db8-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="b2db8-150">SBC 7000</span></span>         | <span data-ttu-id="b2db8-151">8.2</span><span class="sxs-lookup"><span data-stu-id="b2db8-151">8.2</span></span>  |
|            |  <span data-ttu-id="b2db8-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="b2db8-152">SBC SWe</span></span>          | <span data-ttu-id="b2db8-153">8.2</span><span class="sxs-lookup"><span data-stu-id="b2db8-153">8.2</span></span>  |
| [<span data-ttu-id="b2db8-154">리본 SBC 가장자리</span><span class="sxs-lookup"><span data-stu-id="b2db8-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Microsoft+Teams+Direct+Routing+-+On+Premises+Deployment)  |  <span data-ttu-id="b2db8-155">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="b2db8-155">SBC 1000</span></span>         | <span data-ttu-id="b2db8-156">8.1.1, 빌드 527</span><span class="sxs-lookup"><span data-stu-id="b2db8-156">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="b2db8-157">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="b2db8-157">SBC 2000</span></span>         | <span data-ttu-id="b2db8-158">8.1.1, 빌드 527</span><span class="sxs-lookup"><span data-stu-id="b2db8-158">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="b2db8-159">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="b2db8-159">SBC SWe Lite</span></span>     | <span data-ttu-id="b2db8-160">8.1.0, 빌드 222</span><span class="sxs-lookup"><span data-stu-id="b2db8-160">8.1.0, build 222</span></span> |
| [<span data-ttu-id="b2db8-161">TE-시스템</span><span class="sxs-lookup"><span data-stu-id="b2db8-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="b2db8-162">anynode</span><span class="sxs-lookup"><span data-stu-id="b2db8-162">anynode</span></span>          | <span data-ttu-id="b2db8-163">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="b2db8-163">4.0.1+</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="b2db8-164">신뢰할 수 있는 외부 IP 주소 관리</span><span class="sxs-lookup"><span data-stu-id="b2db8-164">Manage external trusted IP addresses</span></span>

<span data-ttu-id="b2db8-165">외부 신뢰할 수 있는 Ip는 기업 네트워크의 인터넷 외부 Ip입니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-165">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="b2db8-166">이러한 IP는 microsoft 팀 클라이언트가 Microsoft 365에 연결할 때 사용 하는 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-166">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="b2db8-167">사용자가 로컬 미디어 최적화를 사용 하는 각 사이트에 대해 이러한 외부 Ip를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-167">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="b2db8-168">각 사이트에 대 한 공용 IP 주소를 추가 하려면 CsTenantTrustedIPAddress cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-168">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="b2db8-169">테 넌 트에 대해 무제한의 신뢰 된 IP 주소를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-169">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="b2db8-170">Microsoft 365에서 표시 되는 외부 Ip가 IPv4 및 IPv6 주소 모두 인 경우 두 가지 유형의 IP 주소를 모두 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-170">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="b2db8-171">IPv4의 경우 mask 32를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-171">For IPv4, use mask 32.</span></span> <span data-ttu-id="b2db8-172">IPv6의 경우 마스크 128를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-172">For IPv6, use mask 128.</span></span> <span data-ttu-id="b2db8-173">Cmdlet에 다른 MaskBits를 지정 하 여 개별 외부 IP 주소와 외부 IP 서브넷을 모두 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-173">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="b2db8-174">신뢰할 수 있는 IP 주소를 추가 하는 예</span><span class="sxs-lookup"><span data-stu-id="b2db8-174">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="b2db8-175">네트워크 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="b2db8-175">Define the network topology</span></span>

<span data-ttu-id="b2db8-176">이 섹션에서는 네트워크 영역, 네트워크 사이트 및 네트워크 토폴로지의 네트워크 서브넷을 정의 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-176">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="b2db8-177">모든 매개 변수는 대/소문자를 구분 하므로 설치 중에 사용 된 것과 동일한 대/소문자를 사용 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-177">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="b2db8-178">(예를 들어, \ \ \ \ \ \ \ \ "베트남" 및 "베트남"는 다른 사이트로 간주 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="b2db8-178">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="b2db8-179">네트워크 지역 정의</span><span class="sxs-lookup"><span data-stu-id="b2db8-179">Define network regions</span></span>

<span data-ttu-id="b2db8-180">네트워크 지역을 정의 하려면 새-Csten앤틸리스 지역 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-180">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="b2db8-181">영역 Id 매개 변수는 영역의 지리를 나타내는 논리 이름이 며 종속성 또는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-181">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="b2db8-182">CentralSite <site ID> 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-182">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="b2db8-183">다음 예에서는 APAC 라는 네트워크 지역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-183">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="b2db8-184">네트워크 사이트 정의</span><span class="sxs-lookup"><span data-stu-id="b2db8-184">Define network sites</span></span>

<span data-ttu-id="b2db8-185">네트워크 사이트를 정의 하려면 새-Csten앤틸리스 Site cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-185">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="b2db8-186">각 네트워크 사이트는 네트워크 지역과 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-186">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="b2db8-187">다음 예에서는 APAC 지역에 베트남, 인도네시아, 싱가포르의 세 가지 새 네트워크 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-187">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="b2db8-188">네트워크 서브넷 정의</span><span class="sxs-lookup"><span data-stu-id="b2db8-188">Define network subnets</span></span>

<span data-ttu-id="b2db8-189">네트워크 서브넷을 정의 하 고 네트워크 사이트에 연결 하려면 새-Csten앤틸리스 Networksubnet cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-189">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="b2db8-190">각 네트워크 서브넷은 한 사이트에만 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-190">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="b2db8-191">다음 예에서는 세 개의 네트워크 서브넷을 정의 하 고이를 베트남, 인도네시아, 싱가포르의 세 가지 네트워크 사이트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-191">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="b2db8-192">가상 네트워크 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="b2db8-192">Define the virtual network topology</span></span> 

<span data-ttu-id="b2db8-193">먼저 테 넌 트 관리자가 새 CsOnlinePSTNGateway cmdlet을 사용 하 여 관련 SBC 각각에 대해 새 SBC 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-193">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="b2db8-194">테 넌 트 관리자는 CsOnlinePSTNGateway cmdlet을 사용 하 여 PSTN 게이트웨이 개체에 대 한 네트워크 사이트를 지정 하 여 가상 네트워크 토폴로지를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-194">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="b2db8-195">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="b2db8-195">Note the following:</span></span> 
   - <span data-ttu-id="b2db8-196">고객에 게 단일 SBC가 있는 경우-ProxySBC 매개 변수는 필수 $null 또는 SBC FQDN 값 (중앙 집중화 된 trunks 시나리오의 중앙 SBC) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-196">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="b2db8-197">MediaBypass 매개 변수는 로컬 미디어 최적화를 지원 하기 위해 $true으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-197">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="b2db8-198">SBC에-BypassMode 매개 변수가 설정 되어 있지 않은 경우에는 X MS 헤더가 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-198">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="b2db8-199">모든 매개 변수는 대/소문자를 구분 하므로 설치 중에 사용 된 것과 동일한 대/소문자를 사용 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-199">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="b2db8-200">(예를 들어, \ \ \ \ \ \ \ \ "베트남" 및 "베트남"는 다른 사이트로 간주 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="b2db8-200">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="b2db8-201">다음 예에서는 네트워크 사이트에 SBCs 세 개를 추가 합니다 (모드를 사용 하는 APAC 지역에서 베트남, 인도네시아, 싱가포르에는 항상 bypass).</span><span class="sxs-lookup"><span data-stu-id="b2db8-201">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="b2db8-202">참고: 로컬 미디어 최적화 및 LBR (위치 기반 라우팅)가 동시에 구성 되는 경우에도 중단 되지 않는 작업을 수행 하려면 각 다운스트림 SBC에 대해 $true에 대해 routing Sitelbrenabled 매개 변수를 설정 하 여 LBR에 대해 다운스트림 SBCs를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-202">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="b2db8-203">프록시 SBC에는이 설정이 필수가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-203">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="b2db8-204">직접적인 라우팅에는 위의 정보에 따라 다음 표에 표시 된 대로 SIP 초대 및 재 초대에 대 한 세 개의 독점 SIP 헤더가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-204">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="b2db8-205">BypassMode가 정의 된 경우 초대 및 재 초대에 대 한 직접 라우팅에 소개 되는 X MS 헤더:</span><span class="sxs-lookup"><span data-stu-id="b2db8-205">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="b2db8-206">헤더 이름</span><span class="sxs-lookup"><span data-stu-id="b2db8-206">Header name</span></span> | <span data-ttu-id="b2db8-207">최대값</span><span class="sxs-lookup"><span data-stu-id="b2db8-207">Values</span></span> | <span data-ttu-id="b2db8-208">메모</span><span class="sxs-lookup"><span data-stu-id="b2db8-208">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="b2db8-209">X-s i m 사용자 위치</span><span class="sxs-lookup"><span data-stu-id="b2db8-209">X-MS-UserLocation</span></span> | <span data-ttu-id="b2db8-210">내부/외부</span><span class="sxs-lookup"><span data-stu-id="b2db8-210">internal/external</span></span> | <span data-ttu-id="b2db8-211">사용자가 내부 인지 외부 인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-211">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="b2db8-212">요청-URI 초대 sip: + 84439263000@VNsbc.contoso.com SIP/2.0</span><span class="sxs-lookup"><span data-stu-id="b2db8-212">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="b2db8-213">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="b2db8-213">SBC FQDN</span></span> | <span data-ttu-id="b2db8-214">SBC가 직접 라우팅에 직접 연결 되지 않은 경우에도 통화를 대상으로 하는 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-214">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="b2db8-215">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="b2db8-215">X-MS-MediaPath</span></span> | <span data-ttu-id="b2db8-216">예: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b2db8-216">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="b2db8-217">사용자와 대상 SBC 사이의 미디어 경로에 사용 해야 하는 SBCs의 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-217">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="b2db8-218">최종 SBC는 항상 마지막입니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-218">The final SBC is always last</span></span> |
| <span data-ttu-id="b2db8-219">X-MS UserSite</span><span class="sxs-lookup"><span data-stu-id="b2db8-219">X-MS-UserSite</span></span> | <span data-ttu-id="b2db8-220">usersiteID</span><span class="sxs-lookup"><span data-stu-id="b2db8-220">usersiteID</span></span> | <span data-ttu-id="b2db8-221">테 넌 트 관리자가 정의한 문자열</span><span class="sxs-lookup"><span data-stu-id="b2db8-221">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="b2db8-222">통화 흐름</span><span class="sxs-lookup"><span data-stu-id="b2db8-222">Call flows</span></span> 

<span data-ttu-id="b2db8-223">다음은 두 가지 모드의 통화 흐름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-223">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="b2db8-224">항상 무시</span><span class="sxs-lookup"><span data-stu-id="b2db8-224">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="b2db8-225">로컬 사용자 용</span><span class="sxs-lookup"><span data-stu-id="b2db8-225">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="b2db8-226">항상 무시 모드</span><span class="sxs-lookup"><span data-stu-id="b2db8-226">Always Bypass mode</span></span>

<span data-ttu-id="b2db8-227">가장 간단 하 게 구성 하는 옵션은 항상 무시 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-227">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="b2db8-228">모든 사이트에서 모든 SBCs에 연결할 수 있는 경우 테 넌 트 관리자가 모든 사용자 및 SBCs에 대해 단일 사이트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-228">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="b2db8-229">예제는 다음과 같은 시나리오에 대해 항상 건너뛰기 모드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-229">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="b2db8-230">아웃 바운드 통화와 사용자가 SBC와 같은 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-230">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="b2db8-231">사용자가 SBC와 같은 위치에 있는 인바운드 통화</span><span class="sxs-lookup"><span data-stu-id="b2db8-231">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="b2db8-232">아웃 바운드 통화 및 외부 사용자</span><span class="sxs-lookup"><span data-stu-id="b2db8-232">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="b2db8-233">인바운드 전화 및 사용자가 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-233">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="b2db8-234">다음 표에는 예제에 사용 되는 FQDN 및 IP 주소가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-234">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="b2db8-235">Q</span><span class="sxs-lookup"><span data-stu-id="b2db8-235">FQDN</span></span> | <span data-ttu-id="b2db8-236">SBC 외부 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b2db8-236">SBC external IP address</span></span> | <span data-ttu-id="b2db8-237">SBC 내부 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b2db8-237">SBC internal IP Address</span></span> | <span data-ttu-id="b2db8-238">내부 서브넷</span><span class="sxs-lookup"><span data-stu-id="b2db8-238">Internal subnet</span></span> | <span data-ttu-id="b2db8-239">위치</span><span class="sxs-lookup"><span data-stu-id="b2db8-239">Location</span></span> | <span data-ttu-id="b2db8-240">외부 NAT (신뢰할 수 있는 IP)</span><span class="sxs-lookup"><span data-stu-id="b2db8-240">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="b2db8-241">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b2db8-241">VNsbc.contoso.com</span></span> | <span data-ttu-id="b2db8-242">없음</span><span class="sxs-lookup"><span data-stu-id="b2db8-242">None</span></span> | <span data-ttu-id="b2db8-243">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="b2db8-243">192.168.1.5</span></span> | <span data-ttu-id="b2db8-244">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="b2db8-244">192.168.1.0/24</span></span> | <span data-ttu-id="b2db8-245">베트남</span><span class="sxs-lookup"><span data-stu-id="b2db8-245">Vietnam</span></span> | <span data-ttu-id="b2db8-246">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="b2db8-246">172.16.240.110</span></span> |
| <span data-ttu-id="b2db8-247">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b2db8-247">IDsbc.contoso.com</span></span> | <span data-ttu-id="b2db8-248">없음</span><span class="sxs-lookup"><span data-stu-id="b2db8-248">None</span></span> | <span data-ttu-id="b2db8-249">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="b2db8-249">192.168.2.5</span></span> | <span data-ttu-id="b2db8-250">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="b2db8-250">192.168.2.0/24</span></span> | <span data-ttu-id="b2db8-251">인도네시아</span><span class="sxs-lookup"><span data-stu-id="b2db8-251">Indonesia</span></span> | <span data-ttu-id="b2db8-252">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="b2db8-252">172.16.240.120</span></span> |
| <span data-ttu-id="b2db8-253">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b2db8-253">proxysbc.contoso.com</span></span> | <span data-ttu-id="b2db8-254">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="b2db8-254">172.16.240.133</span></span> | <span data-ttu-id="b2db8-255">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="b2db8-255">192.168.3.5</span></span> | <span data-ttu-id="b2db8-256">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="b2db8-256">192.168.3.0/24</span></span> | <span data-ttu-id="b2db8-257">싱가포르</span><span class="sxs-lookup"><span data-stu-id="b2db8-257">Singapore</span></span> | <span data-ttu-id="b2db8-258">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="b2db8-258">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="b2db8-259">사용자가 항상 우회 하는 SBC와 같은 위치에 있는 아웃 바운드 통화</span><span class="sxs-lookup"><span data-stu-id="b2db8-259">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="b2db8-260">모드</span><span class="sxs-lookup"><span data-stu-id="b2db8-260">Mode</span></span> |    <span data-ttu-id="b2db8-261">사용자</span><span class="sxs-lookup"><span data-stu-id="b2db8-261">User</span></span> |  <span data-ttu-id="b2db8-262">위치</span><span class="sxs-lookup"><span data-stu-id="b2db8-262">Location</span></span> |  <span data-ttu-id="b2db8-263">통화 방향</span><span class="sxs-lookup"><span data-stu-id="b2db8-263">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="b2db8-264">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="b2db8-264">AlwaysBypass</span></span> |    <span data-ttu-id="b2db8-265">내부용</span><span class="sxs-lookup"><span data-stu-id="b2db8-265">Internal</span></span> |  <span data-ttu-id="b2db8-266">SBC와 동일한 사이트</span><span class="sxs-lookup"><span data-stu-id="b2db8-266">The same site as SBC</span></span> |  <span data-ttu-id="b2db8-267">위한</span><span class="sxs-lookup"><span data-stu-id="b2db8-267">Outbound</span></span> |

<span data-ttu-id="b2db8-268">다음 표에서는 최종 사용자 구성 및 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-268">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="b2db8-269">사용자의 실제 위치</span><span class="sxs-lookup"><span data-stu-id="b2db8-269">User physical location</span></span>| <span data-ttu-id="b2db8-270">사용자가/에서 전화를 걸거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-270">User makes or receives a call to/from number</span></span> | <span data-ttu-id="b2db8-271">사용자 전화 번호</span><span class="sxs-lookup"><span data-stu-id="b2db8-271">User phone number</span></span>  | <span data-ttu-id="b2db8-272">온라인 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="b2db8-272">Online Voice Routing Policy</span></span> | <span data-ttu-id="b2db8-273">SBC에 대해 구성 된 모드</span><span class="sxs-lookup"><span data-stu-id="b2db8-273">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="b2db8-274">베트남</span><span class="sxs-lookup"><span data-stu-id="b2db8-274">Vietnam</span></span> | <span data-ttu-id="b2db8-275">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="b2db8-275">+84 4 3926 3000</span></span> | <span data-ttu-id="b2db8-276">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="b2db8-276">+84 4 5555 5555</span></span>   | <span data-ttu-id="b2db8-277">우선 순위 1:\+^ 84 ({9}\d) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b2db8-277">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="b2db8-278">우선 순위 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b2db8-278">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="b2db8-279">VNsbc.contoso.com – 항상 무시</span><span class="sxs-lookup"><span data-stu-id="b2db8-279">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="b2db8-280">proxysbc.contoso.com – 항상 무시</span><span class="sxs-lookup"><span data-stu-id="b2db8-280">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="b2db8-281">다음 다이어그램은 항상 우회 모드를 사용 하는 아웃 바운드 호출에 대 한 SIP 사다리와 SBC와 같은 위치에 있는 사용자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-281">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="b2db8-282">![아웃 바운드 통화를 보여 주는 다이어그램](media/direct-routing-media-op-10.png "아웃 바운드 통화")</span><span class="sxs-lookup"><span data-stu-id="b2db8-282">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="b2db8-283">다음 표에는 다이렉트 라우팅이 보내는 X MS 헤더가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-283">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="b2db8-284">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2db8-284">Parameter</span></span> | <span data-ttu-id="b2db8-285">볼</span><span class="sxs-lookup"><span data-stu-id="b2db8-285">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="b2db8-286">초대 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b2db8-286">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="b2db8-287">온라인 음성 라우팅 정책에 정의 된 SBC의 대상 이름은 요청 URI로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-287">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="b2db8-288">X-MS UserLocation: internal</span><span class="sxs-lookup"><span data-stu-id="b2db8-288">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="b2db8-289">해당 사용자가 회사 네트워크 내에 있는 것으로 표시 된 필드</span><span class="sxs-lookup"><span data-stu-id="b2db8-289">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="b2db8-290">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b2db8-290">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="b2db8-291">클라이언트가 대상 SBC로 트래버스 해야 하는 SBC를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-291">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="b2db8-292">이 경우 항상 Bypass이 고 클라이언트는 헤더의 유일한 이름으로 전송 되는 대상 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-292">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="b2db8-293">X-MS UserSite: 베트남</span><span class="sxs-lookup"><span data-stu-id="b2db8-293">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="b2db8-294">사용자가 위치한 사이트 내에 표시 되는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-294">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="b2db8-295">사용자가 항상 우회 하는 SBC와 같은 위치에 있는 인바운드 통화</span><span class="sxs-lookup"><span data-stu-id="b2db8-295">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="b2db8-296">모드</span><span class="sxs-lookup"><span data-stu-id="b2db8-296">Mode</span></span> |    <span data-ttu-id="b2db8-297">사용자</span><span class="sxs-lookup"><span data-stu-id="b2db8-297">User</span></span> |  <span data-ttu-id="b2db8-298">위치</span><span class="sxs-lookup"><span data-stu-id="b2db8-298">Location</span></span> |  <span data-ttu-id="b2db8-299">통화 방향</span><span class="sxs-lookup"><span data-stu-id="b2db8-299">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="b2db8-300">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="b2db8-300">AlwaysBypass</span></span> |    <span data-ttu-id="b2db8-301">내부용</span><span class="sxs-lookup"><span data-stu-id="b2db8-301">Internal</span></span> | <span data-ttu-id="b2db8-302">SBC와 동일한 사이트</span><span class="sxs-lookup"><span data-stu-id="b2db8-302">The same site as SBC</span></span> | <span data-ttu-id="b2db8-303">Ipsec</span><span class="sxs-lookup"><span data-stu-id="b2db8-303">Inbound</span></span> |


<span data-ttu-id="b2db8-304">인바운드 호출에서는 사용자의 위치를 알 수 없으며 SBC는 사용자의 위치를 추측해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-304">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="b2db8-305">Guess가 올바르지 않으면 재 초대를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-305">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="b2db8-306">이 케이스는 사용자가 내부이 고 미디어가 직접 흐를 수 있으며 추가 작업이 필요 하지 않은 것으로 간주 됩니다 (재 초대).</span><span class="sxs-lookup"><span data-stu-id="b2db8-306">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="b2db8-307">직접 라우팅 서비스에 연결 된 SBC는 레코드 경로 및 연락처 필드를 제공 하 여 원래 SBC 위치를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-307">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="b2db8-308">이러한 필드를 기반으로 미디어 경로는 직접 라우팅에서 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-308">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="b2db8-309">참고: 사용자가 여러 끝점을 사용할 수 있는 경우 183의 지원은 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-309">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="b2db8-310">이 경우에는 직접적인 라우팅이 항상 180 벨을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-310">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="b2db8-311">다음 다이어그램에서는 AlwaysBypass mode를 사용 하 여 인바운드 호출에 대 한 SIP 사다리를 보여 주고 사용자가 SBC와 같은 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-311">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![SIP 사다리를 표시 하는 다이어그램](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="b2db8-313">아웃 바운드 통화 및 사용자가 항상 우회로 외부에 있는 경우</span><span class="sxs-lookup"><span data-stu-id="b2db8-313">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="b2db8-314">모드</span><span class="sxs-lookup"><span data-stu-id="b2db8-314">Mode</span></span> |    <span data-ttu-id="b2db8-315">사용자</span><span class="sxs-lookup"><span data-stu-id="b2db8-315">User</span></span> |  <span data-ttu-id="b2db8-316">사이트</span><span class="sxs-lookup"><span data-stu-id="b2db8-316">Site</span></span> |  <span data-ttu-id="b2db8-317">통화 방향</span><span class="sxs-lookup"><span data-stu-id="b2db8-317">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="b2db8-318">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="b2db8-318">AlwaysBypass</span></span> |  <span data-ttu-id="b2db8-319">내부</span><span class="sxs-lookup"><span data-stu-id="b2db8-319">External</span></span> |  <span data-ttu-id="b2db8-320">해당 없음</span><span class="sxs-lookup"><span data-stu-id="b2db8-320">N/A</span></span> | <span data-ttu-id="b2db8-321">위한</span><span class="sxs-lookup"><span data-stu-id="b2db8-321">Outbound</span></span> |


<span data-ttu-id="b2db8-322">다음 다이어그램에서는 AlwaysBypass 모드를 사용 하는 아웃 바운드 호출에 대 한 SIP 사다리를 보여 주고 사용자가 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-322">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![SIP 사다리를 표시 하는 다이어그램](media/direct-routing-media-op-12.png)

<span data-ttu-id="b2db8-324">다음 표에는 다이렉트 라우팅 서비스에서 보낸 X-MS 헤더가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-324">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="b2db8-325">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2db8-325">Parameter</span></span> |   <span data-ttu-id="b2db8-326">볼</span><span class="sxs-lookup"><span data-stu-id="b2db8-326">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="b2db8-327">초대 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b2db8-327">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="b2db8-328">온라인 음성 라우팅 정책에 정의 된 SBC의 대상 이름은 요청 URI로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-328">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="b2db8-329">X-MS UserLocation: 외부</span><span class="sxs-lookup"><span data-stu-id="b2db8-329">X-MS-UserLocation: external</span></span> | <span data-ttu-id="b2db8-330">해당 사용자가 회사 네트워크 외부에 있음을 표시 한 필드</span><span class="sxs-lookup"><span data-stu-id="b2db8-330">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="b2db8-331">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b2db8-331">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="b2db8-332">클라이언트가 대상 SBC로 트래버스 해야 하는 SBC를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-332">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="b2db8-333">이 경우 항상 우회 되 고 클라이언트가 외부에 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-333">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="b2db8-334">인바운드 통화 및 사용자가 항상 우회로 외부에 있는 경우</span><span class="sxs-lookup"><span data-stu-id="b2db8-334">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="b2db8-335">모드</span><span class="sxs-lookup"><span data-stu-id="b2db8-335">Mode</span></span> | <span data-ttu-id="b2db8-336">사용자</span><span class="sxs-lookup"><span data-stu-id="b2db8-336">User</span></span> | <span data-ttu-id="b2db8-337">사이트</span><span class="sxs-lookup"><span data-stu-id="b2db8-337">Site</span></span> |  <span data-ttu-id="b2db8-338">통화 방향</span><span class="sxs-lookup"><span data-stu-id="b2db8-338">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="b2db8-339">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="b2db8-339">AlwaysBypass</span></span> |  <span data-ttu-id="b2db8-340">내부</span><span class="sxs-lookup"><span data-stu-id="b2db8-340">External</span></span> |  <span data-ttu-id="b2db8-341">해당 없음</span><span class="sxs-lookup"><span data-stu-id="b2db8-341">N/A</span></span> |   <span data-ttu-id="b2db8-342">Ipsec</span><span class="sxs-lookup"><span data-stu-id="b2db8-342">Inbound</span></span> |

<span data-ttu-id="b2db8-343">인바운드 호출의 경우 직접 라우팅에 연결 된 SBC는 다시 초대를 보내야 합니다 (기본적으로 사용자의 위치가 외부에 있는 경우 로컬 미디어 후보가 항상 제공 됩니다).</span><span class="sxs-lookup"><span data-stu-id="b2db8-343">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="b2db8-344">X-MediaPath는 Record 경로 및 지정 된 SBC 사용자를 기준으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-344">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="b2db8-345">다음 다이어그램에서는 AlwaysBypass 모드를 사용 하는 인바운드 호출에 대 한 SIP 사다리를 보여 주고 사용자가 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-345">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![SIP 사다리를 표시 하는 다이어그램](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="b2db8-347">로컬 사용자 모드에만 해당</span><span class="sxs-lookup"><span data-stu-id="b2db8-347">Only for local users mode</span></span>

<span data-ttu-id="b2db8-348">대상 SBC의 로컬 미디어 후보는 사용자가 SBC와 같은 위치에 있는 경우에만 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-348">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="b2db8-349">다른 모든 경우 미디어는 프록시 SBC의 내부 또는 외부 IP를 통해 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-349">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="b2db8-350">다음과 같은 시나리오에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-350">The following scenarios are described:</span></span>

- [<span data-ttu-id="b2db8-351">아웃 바운드 통화와 사용자가 SBC와 같은 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-351">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="b2db8-352">사용자가 SBC와 같은 위치에 있는 인바운드 통화</span><span class="sxs-lookup"><span data-stu-id="b2db8-352">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="b2db8-353">사용자가 SBC와 같은 위치에 있지 않지만 회사 네트워크에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-353">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="b2db8-354">인바운드 통화와 사용자는 내부용 이지만 SBC와 같은 위치에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-354">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="b2db8-355">다음 표에는 최종 사용자 구성 및 작업이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-355">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="b2db8-356">사용자의 실제 위치</span><span class="sxs-lookup"><span data-stu-id="b2db8-356">User physical location</span></span> |  <span data-ttu-id="b2db8-357">사용자가/에서 전화를 걸거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-357">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="b2db8-358">사용자 전화 번호</span><span class="sxs-lookup"><span data-stu-id="b2db8-358">User phone number</span></span> | <span data-ttu-id="b2db8-359">온라인 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="b2db8-359">Online Voice Routing Policy</span></span> |   <span data-ttu-id="b2db8-360">SBC에 대해 구성 된 모드</span><span class="sxs-lookup"><span data-stu-id="b2db8-360">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="b2db8-361">베트남</span><span class="sxs-lookup"><span data-stu-id="b2db8-361">Vietnam</span></span> | <span data-ttu-id="b2db8-362">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="b2db8-362">+84 4 3926  3000</span></span> |  <span data-ttu-id="b2db8-363">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="b2db8-363">+84 4 5555 5555</span></span> | <span data-ttu-id="b2db8-364">우선 순위 1:\+^ 84 ({9}\d) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b2db8-364">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="b2db8-365">우선 순위 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b2db8-365">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="b2db8-366">VNsbc.contoso.com-모든 사용자에 게 Proxysbc.contoso.com – 항상 우회</span><span class="sxs-lookup"><span data-stu-id="b2db8-366">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="b2db8-367">사용자가 지역 사용자 용 으로만 SBC와 같은 위치에 있는 경우의 아웃 바운드 통화</span><span class="sxs-lookup"><span data-stu-id="b2db8-367">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="b2db8-368">모드</span><span class="sxs-lookup"><span data-stu-id="b2db8-368">Mode</span></span> | <span data-ttu-id="b2db8-369">사용자</span><span class="sxs-lookup"><span data-stu-id="b2db8-369">User</span></span> | <span data-ttu-id="b2db8-370">사이트</span><span class="sxs-lookup"><span data-stu-id="b2db8-370">Site</span></span> | <span data-ttu-id="b2db8-371">통화 방향</span><span class="sxs-lookup"><span data-stu-id="b2db8-371">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="b2db8-372">유일한 Forlocalusers</span><span class="sxs-lookup"><span data-stu-id="b2db8-372">OnlyForLocalUsers</span></span> |   <span data-ttu-id="b2db8-373">내부용</span><span class="sxs-lookup"><span data-stu-id="b2db8-373">Internal</span></span> |<span data-ttu-id="b2db8-374">SBC와 같음</span><span class="sxs-lookup"><span data-stu-id="b2db8-374">Same as SBC</span></span>   | <span data-ttu-id="b2db8-375">위한</span><span class="sxs-lookup"><span data-stu-id="b2db8-375">Outbound</span></span> |

<span data-ttu-id="b2db8-376">다음 다이어그램은 ' 없음 ' Localusers 모드를 사용 하는 아웃 바운드 호출을 보여 주며 사용자는 SBC와 같은 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-376">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="b2db8-377">이는 [사용자가 SBC와 같은 위치에 있을 때 나가는 호출](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)에 표시 되는 것과 동일한 흐름입니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-377">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![SIP 사다리를 표시 하는 다이어그램](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="b2db8-379">사용자가 지역 사용자 용 으로만 SBC와 같은 위치에 있는 경우의 인바운드 통화</span><span class="sxs-lookup"><span data-stu-id="b2db8-379">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="b2db8-380">모드</span><span class="sxs-lookup"><span data-stu-id="b2db8-380">Mode</span></span> | <span data-ttu-id="b2db8-381">사용자</span><span class="sxs-lookup"><span data-stu-id="b2db8-381">User</span></span> | <span data-ttu-id="b2db8-382">사이트</span><span class="sxs-lookup"><span data-stu-id="b2db8-382">Site</span></span> | <span data-ttu-id="b2db8-383">통화 방향</span><span class="sxs-lookup"><span data-stu-id="b2db8-383">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="b2db8-384">유일한 Forlocalusers</span><span class="sxs-lookup"><span data-stu-id="b2db8-384">OnlyForLocalUsers</span></span> |   <span data-ttu-id="b2db8-385">내부용</span><span class="sxs-lookup"><span data-stu-id="b2db8-385">Internal</span></span> | <span data-ttu-id="b2db8-386">SBC와 같음</span><span class="sxs-lookup"><span data-stu-id="b2db8-386">Same as SBC</span></span> | <span data-ttu-id="b2db8-387">Ipsec</span><span class="sxs-lookup"><span data-stu-id="b2db8-387">Inbound</span></span> |

<span data-ttu-id="b2db8-388">다음 다이어그램은이 모드를 사용 하는 인바운드 호출을 보여 주며 사용자는 SBC와 같은 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-388">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="b2db8-389">이는 [사용자가 SBC와 같은 위치에 있을 때 인바운드 호출](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)에 표시 되는 것과 동일한 흐름입니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-389">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![SIP 사다리를 표시 하는 다이어그램](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="b2db8-391">사용자가 SBC와 같은 위치에 있지 않지만 로컬 사용자 용으로 회사 네트워크에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-391">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="b2db8-392">모드</span><span class="sxs-lookup"><span data-stu-id="b2db8-392">Mode</span></span> | <span data-ttu-id="b2db8-393">사용자</span><span class="sxs-lookup"><span data-stu-id="b2db8-393">User</span></span> | <span data-ttu-id="b2db8-394">사이트</span><span class="sxs-lookup"><span data-stu-id="b2db8-394">Site</span></span> |<span data-ttu-id="b2db8-395">통화 방향</span><span class="sxs-lookup"><span data-stu-id="b2db8-395">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="b2db8-396">유일한 Forlocalusers</span><span class="sxs-lookup"><span data-stu-id="b2db8-396">OnlyForLocalUsers</span></span>  | <span data-ttu-id="b2db8-397">내부용</span><span class="sxs-lookup"><span data-stu-id="b2db8-397">Internal</span></span> |   <span data-ttu-id="b2db8-398">SBC와 다름</span><span class="sxs-lookup"><span data-stu-id="b2db8-398">Different from SBC</span></span> | <span data-ttu-id="b2db8-399">위한</span><span class="sxs-lookup"><span data-stu-id="b2db8-399">Outbound</span></span> |

<span data-ttu-id="b2db8-400">직접 라우팅은 SBC에 구성 된 사용자 및 모드의 보고 된 위치를 기반으로 X-MediaPath를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-400">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="b2db8-401">다음 다이어그램에는 없음 Forlocalusers 모드를 사용 하는 아웃 바운드 호출과 SBC와 같은 위치에 있지 않은 내부 사용자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-401">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![SIP 사다리를 표시 하는 다이어그램](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="b2db8-403">인바운드 통화와 사용자는 내부용 이지만 지역 사용자의 경우 SBC와 같은 위치에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-403">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="b2db8-404">모드</span><span class="sxs-lookup"><span data-stu-id="b2db8-404">Mode</span></span> |    <span data-ttu-id="b2db8-405">사용자</span><span class="sxs-lookup"><span data-stu-id="b2db8-405">User</span></span> |  <span data-ttu-id="b2db8-406">사이트</span><span class="sxs-lookup"><span data-stu-id="b2db8-406">Site</span></span> |  <span data-ttu-id="b2db8-407">통화 방향</span><span class="sxs-lookup"><span data-stu-id="b2db8-407">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="b2db8-408">유일한 Forlocalusers</span><span class="sxs-lookup"><span data-stu-id="b2db8-408">OnlyForLocalUsers</span></span> | <span data-ttu-id="b2db8-409">내부용</span><span class="sxs-lookup"><span data-stu-id="b2db8-409">Internal</span></span> |    <span data-ttu-id="b2db8-410">SBC와 다름</span><span class="sxs-lookup"><span data-stu-id="b2db8-410">Different from SBC</span></span> |    <span data-ttu-id="b2db8-411">Ipsec</span><span class="sxs-lookup"><span data-stu-id="b2db8-411">Inbound</span></span> |

<span data-ttu-id="b2db8-412">다음 다이어그램은 사용자 이름에는 없음 Forlocaluser 모드를 사용 하는 인바운드 호출과 SBC와 같은 위치에 있지 않은 내부 사용자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2db8-412">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![SIP 사다리를 표시 하는 다이어그램](media/direct-routing-media-op-17.png)









