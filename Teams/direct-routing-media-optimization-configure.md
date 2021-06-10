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
description: 직접 라우팅을 위한 로컬 미디어 최적화 구성
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576990"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="776f2-103">직접 라우팅을 위한 로컬 미디어 최적화 구성</span><span class="sxs-lookup"><span data-stu-id="776f2-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="776f2-104">로컬 미디어 최적화 구성은 라우팅 및 동적 긴급 호출과 같은 다른 클라우드 음성 기능에 Location-Based 네트워크 설정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="776f2-105">네트워크 지역, 네트워크 사이트, 네트워크 서브넷 및 신뢰할 수 있는 IP 주소에 대한 자세한 내용은 클라우드 음성 기능에 대한 네트워크 설정을 [참조하세요.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="776f2-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="776f2-106">로컬 미디어 최적화를 구성하기 전에 직접 라우팅에 대한 로컬 미디어 최적화 [를 참조합니다.](direct-routing-media-optimization.md)</span><span class="sxs-lookup"><span data-stu-id="776f2-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="776f2-107">로컬 미디어 최적화를 구성하려면 다음 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="776f2-108">관리 센터 또는 Teams 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="776f2-109">자세한 내용은 네트워크 [토폴로지 관리를 참조합니다.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="776f2-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="776f2-110">사용자 및 SBC 사이트를 구성합니다(이 문서에 설명된 바와 같이).</span><span class="sxs-lookup"><span data-stu-id="776f2-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="776f2-111">로컬 미디어 최적화용 SBC를 구성합니다(SBC 공급업체 사양에 따라).</span><span class="sxs-lookup"><span data-stu-id="776f2-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="776f2-112">다음 다이어그램은 이 문서 전체의 예제에 사용된 네트워크 설정을 보여 주었다.</span><span class="sxs-lookup"><span data-stu-id="776f2-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="776f2-113">![예제에 대한 네트워크 설정을 보여주는 다이어그램](media/direct-routing-media-op-9.png "예제에 대한 네트워크 설정")</span><span class="sxs-lookup"><span data-stu-id="776f2-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="776f2-114">사용자 및 SBC 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="776f2-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="776f2-115">사용자 및 SBC 사이트를 구성하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="776f2-116">[외부 신뢰할 수 있는 IP 주소를 관리합니다.](#manage-external-trusted-ip-addresses)</span><span class="sxs-lookup"><span data-stu-id="776f2-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="776f2-117">[네트워크 지역,](#define-the-network-topology) 네트워크 사이트 및 네트워크 서브넷을 구성하여 네트워크 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="776f2-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="776f2-118">[관련 모드](#define-the-virtual-network-topology) 및 프록시 SBC 값을 사용하여 사이트에 SBC를 할당하여 가상 네트워크 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="776f2-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="776f2-119">SBC 공급업체 사양에 따라 로컬 미디어 최적화를 위한 SBC 구성</span><span class="sxs-lookup"><span data-stu-id="776f2-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="776f2-120">이 문서에서는 Microsoft 구성 요소에 대한 구성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="776f2-121">SBC 구성에 대한 자세한 내용은 SBC 공급업체 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="776f2-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="776f2-122">로컬 미디어 최적화는 다음 SBC 공급업체에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="776f2-123">공급업체</span><span class="sxs-lookup"><span data-stu-id="776f2-123">Vendor</span></span> | <span data-ttu-id="776f2-124">제품</span><span class="sxs-lookup"><span data-stu-id="776f2-124">Product</span></span> |    <span data-ttu-id="776f2-125">소프트웨어 버전</span><span class="sxs-lookup"><span data-stu-id="776f2-125">Software version</span></span> |
|:------------|:-------|:-------|
| [<span data-ttu-id="776f2-126">오디오 코드</span><span class="sxs-lookup"><span data-stu-id="776f2-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="776f2-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="776f2-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="776f2-128">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="776f2-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="776f2-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="776f2-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="776f2-130">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="776f2-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="776f2-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="776f2-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="776f2-132">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="776f2-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="776f2-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="776f2-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="776f2-134">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="776f2-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="776f2-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="776f2-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="776f2-136">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="776f2-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="776f2-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="776f2-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="776f2-138">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="776f2-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="776f2-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="776f2-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="776f2-140">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="776f2-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="776f2-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="776f2-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="776f2-142">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="776f2-142">7.20A.256</span></span> |
| [<span data-ttu-id="776f2-143">리본 SBC Core</span><span class="sxs-lookup"><span data-stu-id="776f2-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="776f2-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="776f2-144">SBC 5110</span></span>         | <span data-ttu-id="776f2-145">8.2</span><span class="sxs-lookup"><span data-stu-id="776f2-145">8.2</span></span>  |
|            |  <span data-ttu-id="776f2-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="776f2-146">SBC 5210</span></span>         | <span data-ttu-id="776f2-147">8.2</span><span class="sxs-lookup"><span data-stu-id="776f2-147">8.2</span></span>  |
|            |  <span data-ttu-id="776f2-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="776f2-148">SBC 5400</span></span>         | <span data-ttu-id="776f2-149">8.2</span><span class="sxs-lookup"><span data-stu-id="776f2-149">8.2</span></span>  |
|            |  <span data-ttu-id="776f2-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="776f2-150">SBC 7000</span></span>         | <span data-ttu-id="776f2-151">8.2</span><span class="sxs-lookup"><span data-stu-id="776f2-151">8.2</span></span>  |
|            |  <span data-ttu-id="776f2-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="776f2-152">SBC SWe</span></span>          | <span data-ttu-id="776f2-153">8.2</span><span class="sxs-lookup"><span data-stu-id="776f2-153">8.2</span></span>  |
| [<span data-ttu-id="776f2-154">리본 SBC Edge</span><span class="sxs-lookup"><span data-stu-id="776f2-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="776f2-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="776f2-155">SBC SWe Lite</span></span> | <span data-ttu-id="776f2-156">8.1.5</span><span class="sxs-lookup"><span data-stu-id="776f2-156">8.1.5</span></span> |
|               | <span data-ttu-id="776f2-157">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="776f2-157">SBC 1000</span></span> | <span data-ttu-id="776f2-158">8.1.5</span><span class="sxs-lookup"><span data-stu-id="776f2-158">8.1.5</span></span>  |
|               | <span data-ttu-id="776f2-159">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="776f2-159">SBC 2000</span></span> | <span data-ttu-id="776f2-160">8.1.5</span><span class="sxs-lookup"><span data-stu-id="776f2-160">8.1.5</span></span>  |
| [<span data-ttu-id="776f2-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="776f2-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="776f2-162">anynode</span><span class="sxs-lookup"><span data-stu-id="776f2-162">anynode</span></span>          | <span data-ttu-id="776f2-163">4.0.1+</span><span class="sxs-lookup"><span data-stu-id="776f2-163">4.0.1+</span></span> |
| [<span data-ttu-id="776f2-164">Oracle</span><span class="sxs-lookup"><span data-stu-id="776f2-164">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="776f2-165">AP 1100</span><span class="sxs-lookup"><span data-stu-id="776f2-165">AP 1100</span></span> | <span data-ttu-id="776f2-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="776f2-166">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="776f2-167">AP 3900</span><span class="sxs-lookup"><span data-stu-id="776f2-167">AP 3900</span></span> | <span data-ttu-id="776f2-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="776f2-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="776f2-169">AP 4600</span><span class="sxs-lookup"><span data-stu-id="776f2-169">AP 4600</span></span> | <span data-ttu-id="776f2-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="776f2-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="776f2-171">AP 6300</span><span class="sxs-lookup"><span data-stu-id="776f2-171">AP 6300</span></span> | <span data-ttu-id="776f2-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="776f2-172">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="776f2-173">AP 6350</span><span class="sxs-lookup"><span data-stu-id="776f2-173">AP 6350</span></span> | <span data-ttu-id="776f2-174">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="776f2-174">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="776f2-175">VME</span><span class="sxs-lookup"><span data-stu-id="776f2-175">VME</span></span>     | <span data-ttu-id="776f2-176">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="776f2-176">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="776f2-177">외부 신뢰할 수 있는 IP 주소 관리</span><span class="sxs-lookup"><span data-stu-id="776f2-177">Manage external trusted IP addresses</span></span>

<span data-ttu-id="776f2-178">외부 신뢰할 수 있는 IPS는 엔터프라이즈 네트워크의 인터넷 외부 IPS입니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-178">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="776f2-179">이러한 IP는 클라이언트에 연결할 때 Microsoft Teams 클라이언트에서 사용하는 IP Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="776f2-179">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="776f2-180">로컬 미디어 최적화를 사용하는 사용자가 있는 각 사이트에 대해 이러한 외부 IPS를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-180">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="776f2-181">각 사이트에 대한 공용 IP 주소를 추가하기 위해 New-CsTenantTrustedIPAddress cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-181">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="776f2-182">테넌트에 대한 신뢰할 수 있는 IP 주소를 무제한으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-182">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="776f2-183">외부 IP가 IPv4 Microsoft 365 IPv6 주소인 경우 두 유형의 IP 주소를 모두 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-183">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="776f2-184">IPv4의 경우 마스크 32를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-184">For IPv4, use mask 32.</span></span> <span data-ttu-id="776f2-185">IPv6의 경우 마스크 128을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-185">For IPv6, use mask 128.</span></span> <span data-ttu-id="776f2-186">cmdlet에 다른 MaskBits를 지정하여 개별 외부 IP 주소와 외부 IP 서브넷을 둘 다 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-186">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="776f2-187">신뢰할 수 있는 IP 주소를 추가하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-187">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="776f2-188">네트워크 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="776f2-188">Define the network topology</span></span>

<span data-ttu-id="776f2-189">이 섹션에서는 네트워크 토폴로지에 대한 네트워크 지역, 네트워크 사이트 및 네트워크 서브넷을 정의하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-189">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="776f2-190">모든 매개 변수는 대소문자에 민감하기 때문에 설정 중에 사용된 동일한 사례를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-190">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="776f2-191">(예를 들어 GatewaySiteID 값 "베트남" 및 "베트남"은 다른 사이트로 처리됩니다.)</span><span class="sxs-lookup"><span data-stu-id="776f2-191">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="776f2-192">네트워크 지역 정의</span><span class="sxs-lookup"><span data-stu-id="776f2-192">Define network regions</span></span>

<span data-ttu-id="776f2-193">네트워크 지역을 정의하기 위해 New-CsTenantNetworkRegion cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-193">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="776f2-194">RegionID 매개 변수는 지역의 지역을 나타내는 논리적 이름로 종속성 또는 제한 사항이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-194">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="776f2-195">CentralSite <site ID> 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-195">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="776f2-196">다음 예제에서는 APAC라는 네트워크 지역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-196">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="776f2-197">네트워크 사이트 정의</span><span class="sxs-lookup"><span data-stu-id="776f2-197">Define network sites</span></span>

<span data-ttu-id="776f2-198">네트워크 사이트를 정의하기 위해 New-CsTenantNetworkSite cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-198">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="776f2-199">각 네트워크 사이트는 네트워크 지역과 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-199">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="776f2-200">다음 예제에서는 APAC 지역에 베트남, 인도네시아 및 싱가포르의 세 개의 새 네트워크 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-200">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="776f2-201">네트워크 서브넷 정의</span><span class="sxs-lookup"><span data-stu-id="776f2-201">Define network subnets</span></span>

<span data-ttu-id="776f2-202">네트워크 서브넷을 정의하고 네트워크 사이트에 연결하기 위해 New-CsTenantNetworkSubnet cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-202">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="776f2-203">각 네트워크 서브넷은 하나의 사이트와만 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-203">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="776f2-204">다음 예제에서는 세 개의 네트워크 서브넷을 정의하고 세 개의 네트워크 사이트(베트남, 인도네시아 및 싱가포르)와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-204">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="776f2-205">가상 네트워크 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="776f2-205">Define the virtual network topology</span></span> 

<span data-ttu-id="776f2-206">먼저 테넌트 관리자는 New-CsOnlinePSTNGateway cmdlet을 사용하여 각 관련 SBC에 대한 새 SBC 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-206">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="776f2-207">테넌트 관리자는 다음 cmdlet을 사용하여 PSTN 게이트웨이 개체에 대한 네트워크 사이트를 지정하여 가상 네트워크 토폴로지 Set-CsOnlinePSTNGateway 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-207">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="776f2-208">다음에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="776f2-208">Note the following:</span></span> 
   - <span data-ttu-id="776f2-209">고객이 단일 SBC를 사용하는 경우 -ProxySBC 매개 변수는 필수 $null SBC FQDN 값(중앙 SBC와 중앙 트렁크 시나리오)되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-209">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="776f2-210">로컬 미디어 최적화를 지원하려면 -MediaBypass 매개 변수를 $true 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-210">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="776f2-211">SBC에 -BypassMode 매개 변수 집합이 없는 경우 X-MS 헤더는 전송되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-211">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="776f2-212">모든 매개 변수는 대소문자 구분이 있으므로 설정 중에 사용된 동일한 사례를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-212">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="776f2-213">(예를 들어 GatewaySiteID 값 "베트남" 및 "베트남"은 다른 사이트로 처리됩니다.)</span><span class="sxs-lookup"><span data-stu-id="776f2-213">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="776f2-214">다음 예제에서는 Always bypass 모드가 있는 APAC 지역의 네트워크 사이트 베트남, 인도네시아 및 싱가포르에 3개의 SBC를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-214">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="776f2-215">참고: 로컬 미디어 최적화 및 LBR(Location-Based 라우팅)을 동시에 구성할 때 작업을 확정하려면 GatewaySiteLbrEnabled 매개 변수를 각 다운스트림 SBC에 대해 $true 설정하여 LBR에 대해 다운스트림 SBC를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-215">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="776f2-216">(이 설정은 프록시 SBC에 필수가 아닙니다.)</span><span class="sxs-lookup"><span data-stu-id="776f2-216">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="776f2-217">위의 정보를 기반으로 직접 라우팅에는 다음 표와 같이 SIP 초대 및 다시 초대에 대한 3개의 독점 SIP 헤더가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-217">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="776f2-218">BypassMode가 정의되어 있는 경우 초대 및 Re-Invites 직접 라우팅에 소개된 X-MS 헤더:</span><span class="sxs-lookup"><span data-stu-id="776f2-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="776f2-219">헤더 이름</span><span class="sxs-lookup"><span data-stu-id="776f2-219">Header name</span></span> | <span data-ttu-id="776f2-220">값</span><span class="sxs-lookup"><span data-stu-id="776f2-220">Values</span></span> | <span data-ttu-id="776f2-221">설명</span><span class="sxs-lookup"><span data-stu-id="776f2-221">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="776f2-222">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="776f2-222">X-MS-UserLocation</span></span> | <span data-ttu-id="776f2-223">내부/외부</span><span class="sxs-lookup"><span data-stu-id="776f2-223">internal/external</span></span> | <span data-ttu-id="776f2-224">사용자가 내부 또는 외부인지 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-224">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="776f2-225">Request-URI INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="776f2-225">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="776f2-226">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="776f2-226">SBC FQDN</span></span> | <span data-ttu-id="776f2-227">SBC가 직접 라우팅에 연결되지 않은 경우에도 호출을 대상으로 하는 FQDN</span><span class="sxs-lookup"><span data-stu-id="776f2-227">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="776f2-228">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="776f2-228">X-MS-MediaPath</span></span> | <span data-ttu-id="776f2-229">예: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="776f2-229">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="776f2-230">사용자와 대상 SBC 간의 미디어 경로에 사용해야 하는 SBC의 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-230">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="776f2-231">최종 SBC는 항상 마지막</span><span class="sxs-lookup"><span data-stu-id="776f2-231">The final SBC is always last</span></span> |
| <span data-ttu-id="776f2-232">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="776f2-232">X-MS-UserSite</span></span> | <span data-ttu-id="776f2-233">usersiteID</span><span class="sxs-lookup"><span data-stu-id="776f2-233">usersiteID</span></span> | <span data-ttu-id="776f2-234">테넌트 관리자가 정의한 문자열</span><span class="sxs-lookup"><span data-stu-id="776f2-234">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="776f2-235">통화 흐름</span><span class="sxs-lookup"><span data-stu-id="776f2-235">Call flows</span></span> 

<span data-ttu-id="776f2-236">다음은 두 가지 모드에 대한 호출 흐름을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-236">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="776f2-237">Always Bypass</span><span class="sxs-lookup"><span data-stu-id="776f2-237">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="776f2-238">로컬 사용자만 해당</span><span class="sxs-lookup"><span data-stu-id="776f2-238">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="776f2-239">Always Bypass 모드</span><span class="sxs-lookup"><span data-stu-id="776f2-239">Always Bypass mode</span></span>

<span data-ttu-id="776f2-240">Always Bypass 모드는 구성하는 가장 간단한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-240">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="776f2-241">테넌트 관리자는 모든 사이트에서 모든 SBC에 도달할 수 있는 경우 모든 사용자 및 SBC에 대해 단일 사이트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-241">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="776f2-242">예제에서는 다음 시나리오에 대해 Always bypass 모드를 보여 니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-242">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="776f2-243">아웃바운드 호출 및 사용자가 SBC와 동일한 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-243">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="776f2-244">인바운드 호출 및 사용자가 SBC와 동일한 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-244">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="776f2-245">아웃바운드 호출 및 사용자가 외부</span><span class="sxs-lookup"><span data-stu-id="776f2-245">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="776f2-246">인바운드 호출 및 사용자가 외부</span><span class="sxs-lookup"><span data-stu-id="776f2-246">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="776f2-247">다음 표에서는 예제에 사용된 FQDN 및 IP 주소를 보여 주었다.</span><span class="sxs-lookup"><span data-stu-id="776f2-247">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="776f2-248">FQDN</span><span class="sxs-lookup"><span data-stu-id="776f2-248">FQDN</span></span> | <span data-ttu-id="776f2-249">SBC 외부 IP 주소</span><span class="sxs-lookup"><span data-stu-id="776f2-249">SBC external IP address</span></span> | <span data-ttu-id="776f2-250">SBC 내부 IP 주소</span><span class="sxs-lookup"><span data-stu-id="776f2-250">SBC internal IP Address</span></span> | <span data-ttu-id="776f2-251">내부 서브넷</span><span class="sxs-lookup"><span data-stu-id="776f2-251">Internal subnet</span></span> | <span data-ttu-id="776f2-252">위치</span><span class="sxs-lookup"><span data-stu-id="776f2-252">Location</span></span> | <span data-ttu-id="776f2-253">외부 NAT(신뢰할 수 있는 IP)</span><span class="sxs-lookup"><span data-stu-id="776f2-253">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="776f2-254">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="776f2-254">VNsbc.contoso.com</span></span> | <span data-ttu-id="776f2-255">없음</span><span class="sxs-lookup"><span data-stu-id="776f2-255">None</span></span> | <span data-ttu-id="776f2-256">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="776f2-256">192.168.1.5</span></span> | <span data-ttu-id="776f2-257">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="776f2-257">192.168.1.0/24</span></span> | <span data-ttu-id="776f2-258">베트남</span><span class="sxs-lookup"><span data-stu-id="776f2-258">Vietnam</span></span> | <span data-ttu-id="776f2-259">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="776f2-259">172.16.240.110</span></span> |
| <span data-ttu-id="776f2-260">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="776f2-260">IDsbc.contoso.com</span></span> | <span data-ttu-id="776f2-261">없음</span><span class="sxs-lookup"><span data-stu-id="776f2-261">None</span></span> | <span data-ttu-id="776f2-262">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="776f2-262">192.168.2.5</span></span> | <span data-ttu-id="776f2-263">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="776f2-263">192.168.2.0/24</span></span> | <span data-ttu-id="776f2-264">인도네시아</span><span class="sxs-lookup"><span data-stu-id="776f2-264">Indonesia</span></span> | <span data-ttu-id="776f2-265">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="776f2-265">172.16.240.120</span></span> |
| <span data-ttu-id="776f2-266">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="776f2-266">proxysbc.contoso.com</span></span> | <span data-ttu-id="776f2-267">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="776f2-267">172.16.240.133</span></span> | <span data-ttu-id="776f2-268">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="776f2-268">192.168.3.5</span></span> | <span data-ttu-id="776f2-269">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="776f2-269">192.168.3.0/24</span></span> | <span data-ttu-id="776f2-270">싱가포르</span><span class="sxs-lookup"><span data-stu-id="776f2-270">Singapore</span></span> | <span data-ttu-id="776f2-271">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="776f2-271">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="776f2-272">아웃바운드 호출 및 사용자는 Always Bypass를 통해 SBC와 동일한 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-272">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="776f2-273">모드</span><span class="sxs-lookup"><span data-stu-id="776f2-273">Mode</span></span> |    <span data-ttu-id="776f2-274">사용자</span><span class="sxs-lookup"><span data-stu-id="776f2-274">User</span></span> |  <span data-ttu-id="776f2-275">위치</span><span class="sxs-lookup"><span data-stu-id="776f2-275">Location</span></span> |  <span data-ttu-id="776f2-276">통화 방향</span><span class="sxs-lookup"><span data-stu-id="776f2-276">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="776f2-277">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="776f2-277">AlwaysBypass</span></span> |    <span data-ttu-id="776f2-278">내부</span><span class="sxs-lookup"><span data-stu-id="776f2-278">Internal</span></span> |  <span data-ttu-id="776f2-279">SBC와 동일한 사이트</span><span class="sxs-lookup"><span data-stu-id="776f2-279">The same site as SBC</span></span> |  <span data-ttu-id="776f2-280">아웃바운드</span><span class="sxs-lookup"><span data-stu-id="776f2-280">Outbound</span></span> |

<span data-ttu-id="776f2-281">다음 표에서는 최종 사용자 구성 및 작업을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-281">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="776f2-282">사용자 물리적 위치</span><span class="sxs-lookup"><span data-stu-id="776f2-282">User physical location</span></span>| <span data-ttu-id="776f2-283">사용자가 번호로/받는 전화 걸기 또는 수신</span><span class="sxs-lookup"><span data-stu-id="776f2-283">User makes or receives a call to/from number</span></span> | <span data-ttu-id="776f2-284">사용자 전화 번호</span><span class="sxs-lookup"><span data-stu-id="776f2-284">User phone number</span></span>  | <span data-ttu-id="776f2-285">온라인 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="776f2-285">Online Voice Routing Policy</span></span> | <span data-ttu-id="776f2-286">SBC에 대해 구성된 모드</span><span class="sxs-lookup"><span data-stu-id="776f2-286">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="776f2-287">베트남</span><span class="sxs-lookup"><span data-stu-id="776f2-287">Vietnam</span></span> | <span data-ttu-id="776f2-288">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="776f2-288">+84 4 3926 3000</span></span> | <span data-ttu-id="776f2-289">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="776f2-289">+84 4 5555 5555</span></span>   | <span data-ttu-id="776f2-290">우선 순위 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="776f2-290">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="776f2-291">우선 순위 2: .\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="776f2-291">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="776f2-292">VNsbc.contoso.com – Always Bypass</span><span class="sxs-lookup"><span data-stu-id="776f2-292">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="776f2-293">proxysbc.contoso.com – Always Bypass</span><span class="sxs-lookup"><span data-stu-id="776f2-293">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="776f2-294">다음 다이어그램은 Always bypass 모드로 아웃바운드 호출에 대한 SIP 사다리와 SBC와 동일한 위치에 있는 사용자를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="776f2-294">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="776f2-295">![아웃바운드 호출을 보여주는 다이어그램](media/direct-routing-media-op-10.png "아웃바운드 호출")</span><span class="sxs-lookup"><span data-stu-id="776f2-295">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="776f2-296">다음 표에서는 직접 라우팅으로 전송된 X-MS 헤더를 보여 주었다.</span><span class="sxs-lookup"><span data-stu-id="776f2-296">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="776f2-297">매개 변수</span><span class="sxs-lookup"><span data-stu-id="776f2-297">Parameter</span></span> | <span data-ttu-id="776f2-298">설명</span><span class="sxs-lookup"><span data-stu-id="776f2-298">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="776f2-299">+8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="776f2-299">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="776f2-300">온라인 음성 라우팅 정책에 정의된 SBC의 대상 FQDN이 요청 URI에서 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-300">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="776f2-301">X-MS-UserLocation: 내부</span><span class="sxs-lookup"><span data-stu-id="776f2-301">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="776f2-302">사용자가 회사 네트워크 내부에 있는 것으로 표시된 필드</span><span class="sxs-lookup"><span data-stu-id="776f2-302">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="776f2-303">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="776f2-303">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="776f2-304">클라이언트가 대상 SBC로 트래버스해야 하는 SBC를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-304">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="776f2-305">이 경우 Always Bypass가 있으며 클라이언트는 헤더의 유일한 이름으로 전송된 대상 이름 내부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-305">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="776f2-306">X-MS-UserSite: 베트남</span><span class="sxs-lookup"><span data-stu-id="776f2-306">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="776f2-307">사용자가 있는 사이트 내에 표시된 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-307">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="776f2-308">인바운드 호출 및 사용자는 Always Bypass를 통해 SBC와 동일한 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-308">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="776f2-309">모드</span><span class="sxs-lookup"><span data-stu-id="776f2-309">Mode</span></span> |    <span data-ttu-id="776f2-310">사용자</span><span class="sxs-lookup"><span data-stu-id="776f2-310">User</span></span> |  <span data-ttu-id="776f2-311">위치</span><span class="sxs-lookup"><span data-stu-id="776f2-311">Location</span></span> |  <span data-ttu-id="776f2-312">통화 방향</span><span class="sxs-lookup"><span data-stu-id="776f2-312">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="776f2-313">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="776f2-313">AlwaysBypass</span></span> |    <span data-ttu-id="776f2-314">내부</span><span class="sxs-lookup"><span data-stu-id="776f2-314">Internal</span></span> | <span data-ttu-id="776f2-315">SBC와 동일한 사이트</span><span class="sxs-lookup"><span data-stu-id="776f2-315">The same site as SBC</span></span> | <span data-ttu-id="776f2-316">인바운드</span><span class="sxs-lookup"><span data-stu-id="776f2-316">Inbound</span></span> |


<span data-ttu-id="776f2-317">인바운드 호출 시 사용자의 위치를 알 수 없는 경우 SBC는 사용자가 있는 위치를 추측해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-317">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="776f2-318">추측이 정확하지 않은 경우 다시 초대해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-318">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="776f2-319">이 경우 사용자가 내부에 있으며 미디어가 직접 흐름할 수 있으며 추가 작업이 필요하지 않습니다(다시 초대).를 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-319">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="776f2-320">직접 라우팅 서비스에 연결된 SBC는 필드 및 연락처 필드를 제공하여 원래 SBC Record-Route 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-320">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="776f2-321">이러한 필드를 기반으로 미디어 경로는 직접 라우팅으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-321">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="776f2-322">참고: 사용자가 여러 엔드포인트를 사용할 수 있는 경우 183을 지원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-322">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="776f2-323">이 경우 직접 라우팅은 항상 180 Ringing을 사용하게됩니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-323">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="776f2-324">다음 다이어그램에서는 AlwaysBypass 모드를 사용하여 인바운드 호출에 대한 SIP 사다리가 표시되어 있으며 사용자는 SBC와 동일한 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-324">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![SIP 사다리가 있는 다이어그램](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="776f2-326">아웃바운드 호출 및 사용자가 Always Bypass를 통해 외부</span><span class="sxs-lookup"><span data-stu-id="776f2-326">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="776f2-327">모드</span><span class="sxs-lookup"><span data-stu-id="776f2-327">Mode</span></span> |    <span data-ttu-id="776f2-328">사용자</span><span class="sxs-lookup"><span data-stu-id="776f2-328">User</span></span> |  <span data-ttu-id="776f2-329">사이트</span><span class="sxs-lookup"><span data-stu-id="776f2-329">Site</span></span> |  <span data-ttu-id="776f2-330">통화 방향</span><span class="sxs-lookup"><span data-stu-id="776f2-330">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="776f2-331">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="776f2-331">AlwaysBypass</span></span> |  <span data-ttu-id="776f2-332">외부</span><span class="sxs-lookup"><span data-stu-id="776f2-332">External</span></span> |  <span data-ttu-id="776f2-333">해당 없음</span><span class="sxs-lookup"><span data-stu-id="776f2-333">N/A</span></span> | <span data-ttu-id="776f2-334">아웃바운드</span><span class="sxs-lookup"><span data-stu-id="776f2-334">Outbound</span></span> |


<span data-ttu-id="776f2-335">다음 다이어그램에서는 AlwaysBypass 모드를 사용하여 아웃바운드 호출에 대한 SIP 사다리가 표시되어 사용자가 외부입니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-335">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![SIP 사다리가 있는 다이어그램](media/direct-routing-media-op-12.png)

<span data-ttu-id="776f2-337">다음 표에서는 직접 라우팅 서비스에 의해 전송된 X-MS 헤더를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-337">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="776f2-338">매개 변수</span><span class="sxs-lookup"><span data-stu-id="776f2-338">Parameter</span></span> |   <span data-ttu-id="776f2-339">설명</span><span class="sxs-lookup"><span data-stu-id="776f2-339">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="776f2-340">+8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="776f2-340">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="776f2-341">온라인 음성 라우팅 정책에 정의된 SBC의 대상 FQDN이 요청 URI에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-341">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="776f2-342">X-MS-UserLocation: 외부</span><span class="sxs-lookup"><span data-stu-id="776f2-342">X-MS-UserLocation: external</span></span> | <span data-ttu-id="776f2-343">필드는 사용자가 회사 네트워크 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-343">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="776f2-344">X-MS-MediaPath: proxysbc.contoso.com VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="776f2-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="776f2-345">클라이언트가 대상 SBC로 트래버스해야 하는 SBC를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-345">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="776f2-346">이 경우 Always Bypass가 있으며 클라이언트는 외부입니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-346">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="776f2-347">인바운드 호출 및 Always Bypass를 통해 외부</span><span class="sxs-lookup"><span data-stu-id="776f2-347">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="776f2-348">모드</span><span class="sxs-lookup"><span data-stu-id="776f2-348">Mode</span></span> | <span data-ttu-id="776f2-349">사용자</span><span class="sxs-lookup"><span data-stu-id="776f2-349">User</span></span> | <span data-ttu-id="776f2-350">사이트</span><span class="sxs-lookup"><span data-stu-id="776f2-350">Site</span></span> |  <span data-ttu-id="776f2-351">통화 방향</span><span class="sxs-lookup"><span data-stu-id="776f2-351">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="776f2-352">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="776f2-352">AlwaysBypass</span></span> |  <span data-ttu-id="776f2-353">외부</span><span class="sxs-lookup"><span data-stu-id="776f2-353">External</span></span> |  <span data-ttu-id="776f2-354">해당 없음</span><span class="sxs-lookup"><span data-stu-id="776f2-354">N/A</span></span> |   <span data-ttu-id="776f2-355">인바운드</span><span class="sxs-lookup"><span data-stu-id="776f2-355">Inbound</span></span> |

<span data-ttu-id="776f2-356">인바운드 호출의 경우 직접 라우팅에 연결된 SBC는 사용자의 위치가 외부인 경우 다시 초대(기본적으로 로컬 미디어 후보는 항상 제공)를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-356">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="776f2-357">X-MediaPath는 지정한 SBC Record-Route 기준으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-357">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="776f2-358">다음 다이어그램에서는 AlwaysBypass 모드를 사용하여 인바운드 호출에 대한 SIP 사다리가 표시되어 사용자가 외부입니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-358">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![SIP 사다리가 있는 다이어그램](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="776f2-360">로컬 사용자 모드만</span><span class="sxs-lookup"><span data-stu-id="776f2-360">Only for local users mode</span></span>

<span data-ttu-id="776f2-361">대상 SBC의 로컬 미디어 후보는 사용자가 SBC와 동일한 위치에 있는 경우만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="776f2-362">다른 모든 경우 미디어는 프록시 SBC의 내부 또는 외부 IP를 통해 흐르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-362">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="776f2-363">다음 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-363">The following scenarios are described:</span></span>

- [<span data-ttu-id="776f2-364">아웃바운드 호출 및 사용자가 SBC와 동일한 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-364">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="776f2-365">인바운드 호출 및 사용자가 SBC와 동일한 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-365">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="776f2-366">사용자가 SBC와 동일한 위치에 있지 않지만 회사 네트워크에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-366">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="776f2-367">인바운드 호출 및 사용자는 내부이지만 SBC와 동일한 위치에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-367">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="776f2-368">다음 표에서는 최종 사용자 구성 및 작업을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-368">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="776f2-369">사용자 물리적 위치</span><span class="sxs-lookup"><span data-stu-id="776f2-369">User physical location</span></span> |  <span data-ttu-id="776f2-370">사용자가 번호로/받는 전화 걸기 또는 수신</span><span class="sxs-lookup"><span data-stu-id="776f2-370">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="776f2-371">사용자 전화 번호</span><span class="sxs-lookup"><span data-stu-id="776f2-371">User phone number</span></span> | <span data-ttu-id="776f2-372">온라인 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="776f2-372">Online Voice Routing Policy</span></span> |   <span data-ttu-id="776f2-373">SBC에 대해 구성된 모드</span><span class="sxs-lookup"><span data-stu-id="776f2-373">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="776f2-374">베트남</span><span class="sxs-lookup"><span data-stu-id="776f2-374">Vietnam</span></span> | <span data-ttu-id="776f2-375">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="776f2-375">+84 4 3926  3000</span></span> |  <span data-ttu-id="776f2-376">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="776f2-376">+84 4 5555 5555</span></span> | <span data-ttu-id="776f2-377">우선 순위 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="776f2-377">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="776f2-378">우선 순위 2: .\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="776f2-378">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="776f2-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span><span class="sxs-lookup"><span data-stu-id="776f2-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="776f2-380">아웃바운드 호출 및 사용자는 로컬 사용자 전용으로 SBC와 동일한 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-380">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="776f2-381">모드</span><span class="sxs-lookup"><span data-stu-id="776f2-381">Mode</span></span> | <span data-ttu-id="776f2-382">사용자</span><span class="sxs-lookup"><span data-stu-id="776f2-382">User</span></span> | <span data-ttu-id="776f2-383">사이트</span><span class="sxs-lookup"><span data-stu-id="776f2-383">Site</span></span> | <span data-ttu-id="776f2-384">통화 방향</span><span class="sxs-lookup"><span data-stu-id="776f2-384">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="776f2-385">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="776f2-385">OnlyForLocalUsers</span></span> |   <span data-ttu-id="776f2-386">내부</span><span class="sxs-lookup"><span data-stu-id="776f2-386">Internal</span></span> |<span data-ttu-id="776f2-387">SBC와 동일</span><span class="sxs-lookup"><span data-stu-id="776f2-387">Same as SBC</span></span>   | <span data-ttu-id="776f2-388">아웃바운드</span><span class="sxs-lookup"><span data-stu-id="776f2-388">Outbound</span></span> |

<span data-ttu-id="776f2-389">다음 다이어그램은 OnlyForLocalUsers 모드로 아웃바운드 호출을 보여 주며 사용자는 SBC와 동일한 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-389">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="776f2-390">사용자가 SBC와 동일한 위치에 있는 경우 아웃바운드 호출에 표시된 [흐름과 동일합니다.](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)</span><span class="sxs-lookup"><span data-stu-id="776f2-390">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![SIP 사다리가 있는 다이어그램](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="776f2-392">인바운드 호출 및 사용자는 로컬 사용자 전용으로 SBC와 동일한 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-392">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="776f2-393">모드</span><span class="sxs-lookup"><span data-stu-id="776f2-393">Mode</span></span> | <span data-ttu-id="776f2-394">사용자</span><span class="sxs-lookup"><span data-stu-id="776f2-394">User</span></span> | <span data-ttu-id="776f2-395">사이트</span><span class="sxs-lookup"><span data-stu-id="776f2-395">Site</span></span> | <span data-ttu-id="776f2-396">통화 방향</span><span class="sxs-lookup"><span data-stu-id="776f2-396">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="776f2-397">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="776f2-397">OnlyForLocalUsers</span></span> |   <span data-ttu-id="776f2-398">내부</span><span class="sxs-lookup"><span data-stu-id="776f2-398">Internal</span></span> | <span data-ttu-id="776f2-399">SBC와 동일</span><span class="sxs-lookup"><span data-stu-id="776f2-399">Same as SBC</span></span> | <span data-ttu-id="776f2-400">인바운드</span><span class="sxs-lookup"><span data-stu-id="776f2-400">Inbound</span></span> |

<span data-ttu-id="776f2-401">다음 다이어그램은 OnlyForLocalUsers 모드로 인바운드 호출을 보여 주며 사용자는 SBC와 동일한 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-401">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="776f2-402">사용자가 SBC와 동일한 위치에 있는 경우 인바운드 호출에 표시된 흐름과 [동일합니다.](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)</span><span class="sxs-lookup"><span data-stu-id="776f2-402">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![SIP 사다리가 있는 다이어그램](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="776f2-404">사용자가 SBC와 동일한 위치에 있지 않지만 로컬 사용자만 있는 회사 네트워크에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-404">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="776f2-405">모드</span><span class="sxs-lookup"><span data-stu-id="776f2-405">Mode</span></span> | <span data-ttu-id="776f2-406">사용자</span><span class="sxs-lookup"><span data-stu-id="776f2-406">User</span></span> | <span data-ttu-id="776f2-407">사이트</span><span class="sxs-lookup"><span data-stu-id="776f2-407">Site</span></span> |<span data-ttu-id="776f2-408">통화 방향</span><span class="sxs-lookup"><span data-stu-id="776f2-408">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="776f2-409">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="776f2-409">OnlyForLocalUsers</span></span>  | <span data-ttu-id="776f2-410">내부</span><span class="sxs-lookup"><span data-stu-id="776f2-410">Internal</span></span> |   <span data-ttu-id="776f2-411">SBC와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-411">Different from SBC</span></span> | <span data-ttu-id="776f2-412">아웃바운드</span><span class="sxs-lookup"><span data-stu-id="776f2-412">Outbound</span></span> |

<span data-ttu-id="776f2-413">직접 라우팅은 SBC에 구성된 사용자 및 모드의 보고된 위치를 기반으로 X-MediaPath를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-413">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="776f2-414">다음 다이어그램은 OnlyForLocalUsers 모드와 SBC와 동일한 위치에 있지 않은 내부 사용자를 사용하여 아웃바운드 호출을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-414">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![SIP 사다리가 있는 다이어그램](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="776f2-416">인바운드 호출 및 사용자는 내부이지만 로컬 사용자만 있는 SBC와 동일한 위치에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-416">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="776f2-417">모드</span><span class="sxs-lookup"><span data-stu-id="776f2-417">Mode</span></span> |    <span data-ttu-id="776f2-418">사용자</span><span class="sxs-lookup"><span data-stu-id="776f2-418">User</span></span> |  <span data-ttu-id="776f2-419">사이트</span><span class="sxs-lookup"><span data-stu-id="776f2-419">Site</span></span> |  <span data-ttu-id="776f2-420">통화 방향</span><span class="sxs-lookup"><span data-stu-id="776f2-420">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="776f2-421">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="776f2-421">OnlyForLocalUsers</span></span> | <span data-ttu-id="776f2-422">내부</span><span class="sxs-lookup"><span data-stu-id="776f2-422">Internal</span></span> |    <span data-ttu-id="776f2-423">SBC와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-423">Different from SBC</span></span> |    <span data-ttu-id="776f2-424">인바운드</span><span class="sxs-lookup"><span data-stu-id="776f2-424">Inbound</span></span> |

<span data-ttu-id="776f2-425">다음 다이어그램은 OnlyForLocalUsers 모드로 인바운드 호출을 보여 주며 SBC와 동일한 위치에 있지 않은 내부 사용자를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="776f2-425">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![SIP 사다리가 있는 다이어그램](media/direct-routing-media-op-17.png)









