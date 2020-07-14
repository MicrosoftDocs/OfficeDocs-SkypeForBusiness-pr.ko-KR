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
ms.openlocfilehash: e53f9156b6ab6d33223c9b1d3e11a604ba0c1c31
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121608"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="d82a3-103">직접 라우팅에 대 한 로컬 미디어 최적화 구성</span><span class="sxs-lookup"><span data-stu-id="d82a3-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="d82a3-104">로컬 미디어 최적화 구성은 위치 기반 라우팅과 동적 비상 전화와 같이 다른 클라우드 음성 기능에 공통적으로 사용 되는 네트워크 설정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="d82a3-105">네트워크 지역, 네트워크 사이트, 네트워크 서브넷 및 신뢰할 수 있는 IP 주소에 대 한 자세한 내용은 [클라우드 음성 기능에 대 한 네트워크 설정을](cloud-voice-network-settings.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d82a3-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="d82a3-106">로컬 미디어 최적화를 구성 하기 전에 [직접 라우팅에 대 한 로컬 미디어 최적화](direct-routing-media-optimization.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d82a3-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="d82a3-107">로컬 미디어 최적화를 구성 하려면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="d82a3-108">팀 관리 센터 또는 PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="d82a3-109">자세한 내용은 [네트워크 토폴로지 관리](manage-your-network-topology.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d82a3-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="d82a3-110">사용자 및 SBC 사이트를 구성 합니다 (이 문서에서 설명).</span><span class="sxs-lookup"><span data-stu-id="d82a3-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="d82a3-111">SBC 공급 업체 사양에 따라 로컬 미디어 최적화를 위해 SBCs를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="d82a3-112">다음 다이어그램에는이 문서의 예제에 사용 된 네트워크 설정이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="d82a3-113">![네트워크 설정 예를 보여 주는 다이어그램](media/direct-routing-media-op-9.png "네트워크 설정 예")</span><span class="sxs-lookup"><span data-stu-id="d82a3-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="d82a3-114">사용자 및 SBC 사이트 구성</span><span class="sxs-lookup"><span data-stu-id="d82a3-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="d82a3-115">사용자 및 SBC 사이트를 구성 하려면 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="d82a3-116">[신뢰할 수 있는 외부 IP 주소를 관리](#manage-external-trusted-ip-addresses)합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="d82a3-117">네트워크 지역, 네트워크 사이트 및 네트워크 서브넷을 구성 하 여 [네트워크 토폴로지를 정의](#define-the-network-topology) 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="d82a3-118">사이트 (들)에 관련 모드 및 프록시 SBC 값을 사용 하 여 SBC를 할당 하 여 [가상 네트워크 토폴로지를 정의](#define-the-virtual-network-topology) 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="d82a3-119">SBC 공급 업체 사양에 따라 로컬 미디어 최적화에 대 한 SBC 구성</span><span class="sxs-lookup"><span data-stu-id="d82a3-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="d82a3-120">이 문서에서는 Microsoft 구성 요소에 대 한 구성에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="d82a3-121">SBC 구성에 대 한 자세한 내용은 SBC 공급 업체 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d82a3-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="d82a3-122">로컬 미디어 최적화는 다음 SBC 공급 업체에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="d82a3-123">공급 업체</span><span class="sxs-lookup"><span data-stu-id="d82a3-123">Vendor</span></span> | <span data-ttu-id="d82a3-124">지원부</span><span class="sxs-lookup"><span data-stu-id="d82a3-124">Product</span></span> |    <span data-ttu-id="d82a3-125">소프트웨어 버전</span><span class="sxs-lookup"><span data-stu-id="d82a3-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="d82a3-126">오디오 코드</span><span class="sxs-lookup"><span data-stu-id="d82a3-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="d82a3-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="d82a3-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="d82a3-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="d82a3-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d82a3-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="d82a3-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="d82a3-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="d82a3-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d82a3-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="d82a3-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="d82a3-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="d82a3-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d82a3-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="d82a3-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="d82a3-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="d82a3-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d82a3-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="d82a3-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="d82a3-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="d82a3-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d82a3-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="d82a3-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="d82a3-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="d82a3-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d82a3-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="d82a3-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="d82a3-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="d82a3-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d82a3-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="d82a3-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="d82a3-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="d82a3-142">7.20A.256</span></span> |
| [<span data-ttu-id="d82a3-143">리본 SBC 코어</span><span class="sxs-lookup"><span data-stu-id="d82a3-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="d82a3-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="d82a3-144">SBC 5110</span></span>         | <span data-ttu-id="d82a3-145">8.2</span><span class="sxs-lookup"><span data-stu-id="d82a3-145">8.2</span></span>  |
|            |  <span data-ttu-id="d82a3-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="d82a3-146">SBC 5210</span></span>         | <span data-ttu-id="d82a3-147">8.2</span><span class="sxs-lookup"><span data-stu-id="d82a3-147">8.2</span></span>  |
|            |  <span data-ttu-id="d82a3-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="d82a3-148">SBC 5400</span></span>         | <span data-ttu-id="d82a3-149">8.2</span><span class="sxs-lookup"><span data-stu-id="d82a3-149">8.2</span></span>  |
|            |  <span data-ttu-id="d82a3-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="d82a3-150">SBC 7000</span></span>         | <span data-ttu-id="d82a3-151">8.2</span><span class="sxs-lookup"><span data-stu-id="d82a3-151">8.2</span></span>  |
|            |  <span data-ttu-id="d82a3-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="d82a3-152">SBC SWe</span></span>          | <span data-ttu-id="d82a3-153">8.2</span><span class="sxs-lookup"><span data-stu-id="d82a3-153">8.2</span></span>  |
| [<span data-ttu-id="d82a3-154">리본 SBC 가장자리</span><span class="sxs-lookup"><span data-stu-id="d82a3-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="d82a3-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="d82a3-155">SBC SWe Lite</span></span> | <span data-ttu-id="d82a3-156">8.1.5 (빌드 239)</span><span class="sxs-lookup"><span data-stu-id="d82a3-156">8.1.5 (build 239)</span></span> |
| [<span data-ttu-id="d82a3-157">TE-시스템</span><span class="sxs-lookup"><span data-stu-id="d82a3-157">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="d82a3-158">anynode</span><span class="sxs-lookup"><span data-stu-id="d82a3-158">anynode</span></span>          | <span data-ttu-id="d82a3-159">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="d82a3-159">4.0.1+</span></span> |
| [<span data-ttu-id="d82a3-160">Oracle</span><span class="sxs-lookup"><span data-stu-id="d82a3-160">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="d82a3-161">AP 1100</span><span class="sxs-lookup"><span data-stu-id="d82a3-161">AP 1100</span></span> | <span data-ttu-id="d82a3-162">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d82a3-162">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="d82a3-163">AP 3900</span><span class="sxs-lookup"><span data-stu-id="d82a3-163">AP 3900</span></span> | <span data-ttu-id="d82a3-164">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d82a3-164">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="d82a3-165">AP 4600</span><span class="sxs-lookup"><span data-stu-id="d82a3-165">AP 4600</span></span> | <span data-ttu-id="d82a3-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d82a3-166">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="d82a3-167">AP 6300</span><span class="sxs-lookup"><span data-stu-id="d82a3-167">AP 6300</span></span> | <span data-ttu-id="d82a3-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d82a3-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="d82a3-169">AP 6350</span><span class="sxs-lookup"><span data-stu-id="d82a3-169">AP 6350</span></span> | <span data-ttu-id="d82a3-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d82a3-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="d82a3-171">VME</span><span class="sxs-lookup"><span data-stu-id="d82a3-171">VME</span></span>     | <span data-ttu-id="d82a3-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d82a3-172">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="d82a3-173">신뢰할 수 있는 외부 IP 주소 관리</span><span class="sxs-lookup"><span data-stu-id="d82a3-173">Manage external trusted IP addresses</span></span>

<span data-ttu-id="d82a3-174">외부 신뢰할 수 있는 Ip는 기업 네트워크의 인터넷 외부 Ip입니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-174">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="d82a3-175">이러한 IP는 microsoft 팀 클라이언트가 Microsoft 365에 연결할 때 사용 하는 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-175">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="d82a3-176">사용자가 로컬 미디어 최적화를 사용 하는 각 사이트에 대해 이러한 외부 Ip를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-176">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="d82a3-177">각 사이트에 대 한 공용 IP 주소를 추가 하려면 CsTenantTrustedIPAddress cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-177">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="d82a3-178">테 넌 트에 대해 무제한의 신뢰 된 IP 주소를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-178">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="d82a3-179">Microsoft 365에서 표시 되는 외부 Ip가 IPv4 및 IPv6 주소 모두 인 경우 두 가지 유형의 IP 주소를 모두 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-179">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="d82a3-180">IPv4의 경우 mask 32를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-180">For IPv4, use mask 32.</span></span> <span data-ttu-id="d82a3-181">IPv6의 경우 마스크 128를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-181">For IPv6, use mask 128.</span></span> <span data-ttu-id="d82a3-182">Cmdlet에 다른 MaskBits를 지정 하 여 개별 외부 IP 주소와 외부 IP 서브넷을 모두 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-182">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="d82a3-183">신뢰할 수 있는 IP 주소를 추가 하는 예</span><span class="sxs-lookup"><span data-stu-id="d82a3-183">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="d82a3-184">네트워크 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="d82a3-184">Define the network topology</span></span>

<span data-ttu-id="d82a3-185">이 섹션에서는 네트워크 영역, 네트워크 사이트 및 네트워크 토폴로지의 네트워크 서브넷을 정의 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-185">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="d82a3-186">모든 매개 변수는 대/소문자를 구분 하므로 설치 중에 사용 된 것과 동일한 대/소문자를 사용 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-186">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="d82a3-187">(예를 들어, \ \ \ \ \ \ \ \ "베트남" 및 "베트남"는 다른 사이트로 간주 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="d82a3-187">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="d82a3-188">네트워크 지역 정의</span><span class="sxs-lookup"><span data-stu-id="d82a3-188">Define network regions</span></span>

<span data-ttu-id="d82a3-189">네트워크 지역을 정의 하려면 새-Csten앤틸리스 지역 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-189">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="d82a3-190">영역 Id 매개 변수는 영역의 지리를 나타내는 논리 이름이 며 종속성 또는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-190">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="d82a3-191">CentralSite <site ID> 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-191">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="d82a3-192">다음 예에서는 APAC 라는 네트워크 지역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-192">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="d82a3-193">네트워크 사이트 정의</span><span class="sxs-lookup"><span data-stu-id="d82a3-193">Define network sites</span></span>

<span data-ttu-id="d82a3-194">네트워크 사이트를 정의 하려면 새-Csten앤틸리스 Site cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-194">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="d82a3-195">각 네트워크 사이트는 네트워크 지역과 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-195">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="d82a3-196">다음 예에서는 APAC 지역에 베트남, 인도네시아, 싱가포르의 세 가지 새 네트워크 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-196">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="d82a3-197">네트워크 서브넷 정의</span><span class="sxs-lookup"><span data-stu-id="d82a3-197">Define network subnets</span></span>

<span data-ttu-id="d82a3-198">네트워크 서브넷을 정의 하 고 네트워크 사이트에 연결 하려면 새-Csten앤틸리스 Networksubnet cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-198">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="d82a3-199">각 네트워크 서브넷은 한 사이트에만 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-199">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="d82a3-200">다음 예에서는 세 개의 네트워크 서브넷을 정의 하 고이를 베트남, 인도네시아, 싱가포르의 세 가지 네트워크 사이트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-200">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="d82a3-201">가상 네트워크 토폴로지 정의</span><span class="sxs-lookup"><span data-stu-id="d82a3-201">Define the virtual network topology</span></span> 

<span data-ttu-id="d82a3-202">먼저 테 넌 트 관리자가 새 CsOnlinePSTNGateway cmdlet을 사용 하 여 관련 SBC 각각에 대해 새 SBC 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-202">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="d82a3-203">테 넌 트 관리자는 CsOnlinePSTNGateway cmdlet을 사용 하 여 PSTN 게이트웨이 개체에 대 한 네트워크 사이트를 지정 하 여 가상 네트워크 토폴로지를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-203">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="d82a3-204">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="d82a3-204">Note the following:</span></span> 
   - <span data-ttu-id="d82a3-205">고객에 게 단일 SBC가 있는 경우-ProxySBC 매개 변수는 필수 $null 또는 SBC FQDN 값 (중앙 집중화 된 trunks 시나리오의 중앙 SBC) 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-205">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="d82a3-206">MediaBypass 매개 변수는 로컬 미디어 최적화를 지원 하기 위해 $true으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-206">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="d82a3-207">SBC에-BypassMode 매개 변수가 설정 되어 있지 않은 경우에는 X MS 헤더가 전송 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-207">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="d82a3-208">모든 매개 변수는 대/소문자를 구분 하므로 설치 중에 사용 된 것과 동일한 대/소문자를 사용 하 고 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-208">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="d82a3-209">(예를 들어, \ \ \ \ \ \ \ \ "베트남" 및 "베트남"는 다른 사이트로 간주 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="d82a3-209">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="d82a3-210">다음 예에서는 네트워크 사이트에 SBCs 세 개를 추가 합니다 (모드를 사용 하는 APAC 지역에서 베트남, 인도네시아, 싱가포르에는 항상 bypass).</span><span class="sxs-lookup"><span data-stu-id="d82a3-210">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="d82a3-211">참고: 로컬 미디어 최적화 및 LBR (위치 기반 라우팅)가 동시에 구성 되는 경우에도 중단 되지 않는 작업을 수행 하려면 각 다운스트림 SBC에 대해 $true에 대해 routing Sitelbrenabled 매개 변수를 설정 하 여 LBR에 대해 다운스트림 SBCs를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-211">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="d82a3-212">프록시 SBC에는이 설정이 필수가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-212">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="d82a3-213">직접적인 라우팅에는 위의 정보에 따라 다음 표에 표시 된 대로 SIP 초대 및 재 초대에 대 한 세 개의 독점 SIP 헤더가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-213">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="d82a3-214">BypassMode가 정의 된 경우 초대 및 재 초대에 대 한 직접 라우팅에 소개 되는 X MS 헤더:</span><span class="sxs-lookup"><span data-stu-id="d82a3-214">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="d82a3-215">헤더 이름</span><span class="sxs-lookup"><span data-stu-id="d82a3-215">Header name</span></span> | <span data-ttu-id="d82a3-216">최대값</span><span class="sxs-lookup"><span data-stu-id="d82a3-216">Values</span></span> | <span data-ttu-id="d82a3-217">설명</span><span class="sxs-lookup"><span data-stu-id="d82a3-217">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="d82a3-218">X-s i m 사용자 위치</span><span class="sxs-lookup"><span data-stu-id="d82a3-218">X-MS-UserLocation</span></span> | <span data-ttu-id="d82a3-219">내부/외부</span><span class="sxs-lookup"><span data-stu-id="d82a3-219">internal/external</span></span> | <span data-ttu-id="d82a3-220">사용자가 내부 인지 외부 인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-220">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="d82a3-221">요청-URI 초대 sip: + 84439263000@VNsbc.contoso.com SIP/2.0</span><span class="sxs-lookup"><span data-stu-id="d82a3-221">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="d82a3-222">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="d82a3-222">SBC FQDN</span></span> | <span data-ttu-id="d82a3-223">SBC가 직접 라우팅에 직접 연결 되지 않은 경우에도 통화를 대상으로 하는 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-223">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="d82a3-224">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="d82a3-224">X-MS-MediaPath</span></span> | <span data-ttu-id="d82a3-225">예: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d82a3-225">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="d82a3-226">사용자와 대상 SBC 사이의 미디어 경로에 사용 해야 하는 SBCs의 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-226">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="d82a3-227">최종 SBC는 항상 마지막입니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-227">The final SBC is always last</span></span> |
| <span data-ttu-id="d82a3-228">X-MS UserSite</span><span class="sxs-lookup"><span data-stu-id="d82a3-228">X-MS-UserSite</span></span> | <span data-ttu-id="d82a3-229">usersiteID</span><span class="sxs-lookup"><span data-stu-id="d82a3-229">usersiteID</span></span> | <span data-ttu-id="d82a3-230">테 넌 트 관리자가 정의한 문자열</span><span class="sxs-lookup"><span data-stu-id="d82a3-230">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="d82a3-231">통화 흐름</span><span class="sxs-lookup"><span data-stu-id="d82a3-231">Call flows</span></span> 

<span data-ttu-id="d82a3-232">다음은 두 가지 모드의 통화 흐름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-232">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="d82a3-233">항상 무시</span><span class="sxs-lookup"><span data-stu-id="d82a3-233">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="d82a3-234">로컬 사용자 용</span><span class="sxs-lookup"><span data-stu-id="d82a3-234">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="d82a3-235">항상 무시 모드</span><span class="sxs-lookup"><span data-stu-id="d82a3-235">Always Bypass mode</span></span>

<span data-ttu-id="d82a3-236">가장 간단 하 게 구성 하는 옵션은 항상 무시 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-236">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="d82a3-237">모든 사이트에서 모든 SBCs에 연결할 수 있는 경우 테 넌 트 관리자가 모든 사용자 및 SBCs에 대해 단일 사이트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-237">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="d82a3-238">예제는 다음과 같은 시나리오에 대해 항상 건너뛰기 모드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-238">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="d82a3-239">아웃 바운드 통화와 사용자가 SBC와 같은 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-239">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="d82a3-240">사용자가 SBC와 같은 위치에 있는 인바운드 통화</span><span class="sxs-lookup"><span data-stu-id="d82a3-240">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="d82a3-241">아웃 바운드 통화 및 외부 사용자</span><span class="sxs-lookup"><span data-stu-id="d82a3-241">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="d82a3-242">인바운드 전화 및 사용자가 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-242">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="d82a3-243">다음 표에는 예제에 사용 되는 FQDN 및 IP 주소가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-243">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="d82a3-244">Q</span><span class="sxs-lookup"><span data-stu-id="d82a3-244">FQDN</span></span> | <span data-ttu-id="d82a3-245">SBC 외부 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d82a3-245">SBC external IP address</span></span> | <span data-ttu-id="d82a3-246">SBC 내부 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d82a3-246">SBC internal IP Address</span></span> | <span data-ttu-id="d82a3-247">내부 서브넷</span><span class="sxs-lookup"><span data-stu-id="d82a3-247">Internal subnet</span></span> | <span data-ttu-id="d82a3-248">위치</span><span class="sxs-lookup"><span data-stu-id="d82a3-248">Location</span></span> | <span data-ttu-id="d82a3-249">외부 NAT (신뢰할 수 있는 IP)</span><span class="sxs-lookup"><span data-stu-id="d82a3-249">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="d82a3-250">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d82a3-250">VNsbc.contoso.com</span></span> | <span data-ttu-id="d82a3-251">없음</span><span class="sxs-lookup"><span data-stu-id="d82a3-251">None</span></span> | <span data-ttu-id="d82a3-252">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="d82a3-252">192.168.1.5</span></span> | <span data-ttu-id="d82a3-253">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="d82a3-253">192.168.1.0/24</span></span> | <span data-ttu-id="d82a3-254">베트남</span><span class="sxs-lookup"><span data-stu-id="d82a3-254">Vietnam</span></span> | <span data-ttu-id="d82a3-255">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="d82a3-255">172.16.240.110</span></span> |
| <span data-ttu-id="d82a3-256">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d82a3-256">IDsbc.contoso.com</span></span> | <span data-ttu-id="d82a3-257">없음</span><span class="sxs-lookup"><span data-stu-id="d82a3-257">None</span></span> | <span data-ttu-id="d82a3-258">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="d82a3-258">192.168.2.5</span></span> | <span data-ttu-id="d82a3-259">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="d82a3-259">192.168.2.0/24</span></span> | <span data-ttu-id="d82a3-260">인도네시아</span><span class="sxs-lookup"><span data-stu-id="d82a3-260">Indonesia</span></span> | <span data-ttu-id="d82a3-261">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="d82a3-261">172.16.240.120</span></span> |
| <span data-ttu-id="d82a3-262">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d82a3-262">proxysbc.contoso.com</span></span> | <span data-ttu-id="d82a3-263">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="d82a3-263">172.16.240.133</span></span> | <span data-ttu-id="d82a3-264">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="d82a3-264">192.168.3.5</span></span> | <span data-ttu-id="d82a3-265">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="d82a3-265">192.168.3.0/24</span></span> | <span data-ttu-id="d82a3-266">싱가포르</span><span class="sxs-lookup"><span data-stu-id="d82a3-266">Singapore</span></span> | <span data-ttu-id="d82a3-267">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="d82a3-267">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="d82a3-268">사용자가 항상 우회 하는 SBC와 같은 위치에 있는 아웃 바운드 통화</span><span class="sxs-lookup"><span data-stu-id="d82a3-268">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="d82a3-269">모드</span><span class="sxs-lookup"><span data-stu-id="d82a3-269">Mode</span></span> |    <span data-ttu-id="d82a3-270">사용자</span><span class="sxs-lookup"><span data-stu-id="d82a3-270">User</span></span> |  <span data-ttu-id="d82a3-271">위치</span><span class="sxs-lookup"><span data-stu-id="d82a3-271">Location</span></span> |  <span data-ttu-id="d82a3-272">통화 방향</span><span class="sxs-lookup"><span data-stu-id="d82a3-272">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="d82a3-273">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="d82a3-273">AlwaysBypass</span></span> |    <span data-ttu-id="d82a3-274">내부용</span><span class="sxs-lookup"><span data-stu-id="d82a3-274">Internal</span></span> |  <span data-ttu-id="d82a3-275">SBC와 동일한 사이트</span><span class="sxs-lookup"><span data-stu-id="d82a3-275">The same site as SBC</span></span> |  <span data-ttu-id="d82a3-276">위한</span><span class="sxs-lookup"><span data-stu-id="d82a3-276">Outbound</span></span> |

<span data-ttu-id="d82a3-277">다음 표에서는 최종 사용자 구성 및 작업을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-277">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="d82a3-278">사용자의 실제 위치</span><span class="sxs-lookup"><span data-stu-id="d82a3-278">User physical location</span></span>| <span data-ttu-id="d82a3-279">사용자가/에서 전화를 걸거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-279">User makes or receives a call to/from number</span></span> | <span data-ttu-id="d82a3-280">사용자 전화 번호</span><span class="sxs-lookup"><span data-stu-id="d82a3-280">User phone number</span></span>  | <span data-ttu-id="d82a3-281">온라인 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="d82a3-281">Online Voice Routing Policy</span></span> | <span data-ttu-id="d82a3-282">SBC에 대해 구성 된 모드</span><span class="sxs-lookup"><span data-stu-id="d82a3-282">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="d82a3-283">베트남</span><span class="sxs-lookup"><span data-stu-id="d82a3-283">Vietnam</span></span> | <span data-ttu-id="d82a3-284">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="d82a3-284">+84 4 3926 3000</span></span> | <span data-ttu-id="d82a3-285">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="d82a3-285">+84 4 5555 5555</span></span>   | <span data-ttu-id="d82a3-286">우선 순위 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d82a3-286">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="d82a3-287">우선 순위 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d82a3-287">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="d82a3-288">VNsbc.contoso.com – 항상 무시</span><span class="sxs-lookup"><span data-stu-id="d82a3-288">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="d82a3-289">proxysbc.contoso.com – 항상 무시</span><span class="sxs-lookup"><span data-stu-id="d82a3-289">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="d82a3-290">다음 다이어그램은 항상 우회 모드를 사용 하는 아웃 바운드 호출에 대 한 SIP 사다리와 SBC와 같은 위치에 있는 사용자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-290">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="d82a3-291">![아웃 바운드 통화를 보여 주는 다이어그램](media/direct-routing-media-op-10.png "아웃 바운드 통화")</span><span class="sxs-lookup"><span data-stu-id="d82a3-291">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="d82a3-292">다음 표에는 다이렉트 라우팅이 보내는 X MS 헤더가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-292">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="d82a3-293">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d82a3-293">Parameter</span></span> | <span data-ttu-id="d82a3-294">볼</span><span class="sxs-lookup"><span data-stu-id="d82a3-294">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="d82a3-295">초대 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d82a3-295">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="d82a3-296">온라인 음성 라우팅 정책에 정의 된 SBC의 대상 FQDN이 요청 URI로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-296">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="d82a3-297">X-MS UserLocation: internal</span><span class="sxs-lookup"><span data-stu-id="d82a3-297">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="d82a3-298">해당 사용자가 회사 네트워크 내에 있는 것으로 표시 된 필드</span><span class="sxs-lookup"><span data-stu-id="d82a3-298">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="d82a3-299">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d82a3-299">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="d82a3-300">클라이언트가 대상 SBC로 트래버스 해야 하는 SBC를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-300">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="d82a3-301">이 경우 항상 Bypass이 고 클라이언트는 헤더의 유일한 이름으로 전송 되는 대상 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-301">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="d82a3-302">X-MS UserSite: 베트남</span><span class="sxs-lookup"><span data-stu-id="d82a3-302">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="d82a3-303">사용자가 위치한 사이트 내에 표시 되는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-303">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="d82a3-304">사용자가 항상 우회 하는 SBC와 같은 위치에 있는 인바운드 통화</span><span class="sxs-lookup"><span data-stu-id="d82a3-304">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="d82a3-305">모드</span><span class="sxs-lookup"><span data-stu-id="d82a3-305">Mode</span></span> |    <span data-ttu-id="d82a3-306">사용자</span><span class="sxs-lookup"><span data-stu-id="d82a3-306">User</span></span> |  <span data-ttu-id="d82a3-307">위치</span><span class="sxs-lookup"><span data-stu-id="d82a3-307">Location</span></span> |  <span data-ttu-id="d82a3-308">통화 방향</span><span class="sxs-lookup"><span data-stu-id="d82a3-308">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="d82a3-309">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="d82a3-309">AlwaysBypass</span></span> |    <span data-ttu-id="d82a3-310">내부용</span><span class="sxs-lookup"><span data-stu-id="d82a3-310">Internal</span></span> | <span data-ttu-id="d82a3-311">SBC와 동일한 사이트</span><span class="sxs-lookup"><span data-stu-id="d82a3-311">The same site as SBC</span></span> | <span data-ttu-id="d82a3-312">Ipsec</span><span class="sxs-lookup"><span data-stu-id="d82a3-312">Inbound</span></span> |


<span data-ttu-id="d82a3-313">인바운드 호출에서는 사용자의 위치를 알 수 없으며 SBC는 사용자의 위치를 추측해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-313">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="d82a3-314">Guess가 올바르지 않으면 재 초대를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-314">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="d82a3-315">이 케이스는 사용자가 내부이 고 미디어가 직접 흐를 수 있으며 추가 작업이 필요 하지 않은 것으로 간주 됩니다 (재 초대).</span><span class="sxs-lookup"><span data-stu-id="d82a3-315">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="d82a3-316">직접 라우팅 서비스에 연결 된 SBC는 레코드 경로 및 연락처 필드를 제공 하 여 원래 SBC 위치를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-316">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="d82a3-317">이러한 필드를 기반으로 미디어 경로는 직접 라우팅에서 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-317">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="d82a3-318">참고: 사용자가 여러 끝점을 사용할 수 있는 경우 183의 지원은 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-318">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="d82a3-319">이 경우에는 직접적인 라우팅이 항상 180 벨을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-319">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="d82a3-320">다음 다이어그램에서는 AlwaysBypass mode를 사용 하 여 인바운드 호출에 대 한 SIP 사다리를 보여 주고 사용자가 SBC와 같은 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-320">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![SIP 사다리를 표시 하는 다이어그램](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="d82a3-322">아웃 바운드 통화 및 사용자가 항상 우회로 외부에 있는 경우</span><span class="sxs-lookup"><span data-stu-id="d82a3-322">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="d82a3-323">모드</span><span class="sxs-lookup"><span data-stu-id="d82a3-323">Mode</span></span> |    <span data-ttu-id="d82a3-324">사용자</span><span class="sxs-lookup"><span data-stu-id="d82a3-324">User</span></span> |  <span data-ttu-id="d82a3-325">사이트</span><span class="sxs-lookup"><span data-stu-id="d82a3-325">Site</span></span> |  <span data-ttu-id="d82a3-326">통화 방향</span><span class="sxs-lookup"><span data-stu-id="d82a3-326">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="d82a3-327">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="d82a3-327">AlwaysBypass</span></span> |  <span data-ttu-id="d82a3-328">내부</span><span class="sxs-lookup"><span data-stu-id="d82a3-328">External</span></span> |  <span data-ttu-id="d82a3-329">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d82a3-329">N/A</span></span> | <span data-ttu-id="d82a3-330">위한</span><span class="sxs-lookup"><span data-stu-id="d82a3-330">Outbound</span></span> |


<span data-ttu-id="d82a3-331">다음 다이어그램에서는 AlwaysBypass 모드를 사용 하는 아웃 바운드 호출에 대 한 SIP 사다리를 보여 주고 사용자가 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-331">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![SIP 사다리를 표시 하는 다이어그램](media/direct-routing-media-op-12.png)

<span data-ttu-id="d82a3-333">다음 표에는 다이렉트 라우팅 서비스에서 보낸 X-MS 헤더가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-333">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="d82a3-334">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d82a3-334">Parameter</span></span> |   <span data-ttu-id="d82a3-335">볼</span><span class="sxs-lookup"><span data-stu-id="d82a3-335">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="d82a3-336">초대 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d82a3-336">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="d82a3-337">온라인 음성 라우팅 정책에 정의 된 SBC의 대상 FQDN은 요청 URI로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-337">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="d82a3-338">X-MS UserLocation: 외부</span><span class="sxs-lookup"><span data-stu-id="d82a3-338">X-MS-UserLocation: external</span></span> | <span data-ttu-id="d82a3-339">해당 사용자가 회사 네트워크 외부에 있음을 표시 한 필드</span><span class="sxs-lookup"><span data-stu-id="d82a3-339">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="d82a3-340">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d82a3-340">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="d82a3-341">클라이언트가 대상 SBC로 트래버스 해야 하는 SBC를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-341">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="d82a3-342">이 경우 항상 우회 되 고 클라이언트가 외부에 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-342">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="d82a3-343">인바운드 통화 및 사용자가 항상 우회로 외부에 있는 경우</span><span class="sxs-lookup"><span data-stu-id="d82a3-343">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="d82a3-344">모드</span><span class="sxs-lookup"><span data-stu-id="d82a3-344">Mode</span></span> | <span data-ttu-id="d82a3-345">사용자</span><span class="sxs-lookup"><span data-stu-id="d82a3-345">User</span></span> | <span data-ttu-id="d82a3-346">사이트</span><span class="sxs-lookup"><span data-stu-id="d82a3-346">Site</span></span> |  <span data-ttu-id="d82a3-347">통화 방향</span><span class="sxs-lookup"><span data-stu-id="d82a3-347">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="d82a3-348">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="d82a3-348">AlwaysBypass</span></span> |  <span data-ttu-id="d82a3-349">내부</span><span class="sxs-lookup"><span data-stu-id="d82a3-349">External</span></span> |  <span data-ttu-id="d82a3-350">해당 없음</span><span class="sxs-lookup"><span data-stu-id="d82a3-350">N/A</span></span> |   <span data-ttu-id="d82a3-351">Ipsec</span><span class="sxs-lookup"><span data-stu-id="d82a3-351">Inbound</span></span> |

<span data-ttu-id="d82a3-352">인바운드 호출의 경우 직접 라우팅에 연결 된 SBC는 다시 초대를 보내야 합니다 (기본적으로 사용자의 위치가 외부에 있는 경우 로컬 미디어 후보가 항상 제공 됩니다).</span><span class="sxs-lookup"><span data-stu-id="d82a3-352">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="d82a3-353">X-MediaPath는 Record 경로 및 지정 된 SBC 사용자를 기준으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-353">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="d82a3-354">다음 다이어그램에서는 AlwaysBypass 모드를 사용 하는 인바운드 호출에 대 한 SIP 사다리를 보여 주고 사용자가 외부에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-354">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![SIP 사다리를 표시 하는 다이어그램](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="d82a3-356">로컬 사용자 모드에만 해당</span><span class="sxs-lookup"><span data-stu-id="d82a3-356">Only for local users mode</span></span>

<span data-ttu-id="d82a3-357">대상 SBC의 로컬 미디어 후보는 사용자가 SBC와 같은 위치에 있는 경우에만 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-357">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="d82a3-358">다른 모든 경우 미디어는 프록시 SBC의 내부 또는 외부 IP를 통해 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-358">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="d82a3-359">다음과 같은 시나리오에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-359">The following scenarios are described:</span></span>

- [<span data-ttu-id="d82a3-360">아웃 바운드 통화와 사용자가 SBC와 같은 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-360">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="d82a3-361">사용자가 SBC와 같은 위치에 있는 인바운드 통화</span><span class="sxs-lookup"><span data-stu-id="d82a3-361">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="d82a3-362">사용자가 SBC와 같은 위치에 있지 않지만 회사 네트워크에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-362">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="d82a3-363">인바운드 통화와 사용자는 내부용 이지만 SBC와 같은 위치에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-363">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="d82a3-364">다음 표에는 최종 사용자 구성 및 작업이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-364">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="d82a3-365">사용자의 실제 위치</span><span class="sxs-lookup"><span data-stu-id="d82a3-365">User physical location</span></span> |  <span data-ttu-id="d82a3-366">사용자가/에서 전화를 걸거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-366">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="d82a3-367">사용자 전화 번호</span><span class="sxs-lookup"><span data-stu-id="d82a3-367">User phone number</span></span> | <span data-ttu-id="d82a3-368">온라인 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="d82a3-368">Online Voice Routing Policy</span></span> |   <span data-ttu-id="d82a3-369">SBC에 대해 구성 된 모드</span><span class="sxs-lookup"><span data-stu-id="d82a3-369">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="d82a3-370">베트남</span><span class="sxs-lookup"><span data-stu-id="d82a3-370">Vietnam</span></span> | <span data-ttu-id="d82a3-371">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="d82a3-371">+84 4 3926  3000</span></span> |  <span data-ttu-id="d82a3-372">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="d82a3-372">+84 4 5555 5555</span></span> | <span data-ttu-id="d82a3-373">우선 순위 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d82a3-373">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="d82a3-374">우선 순위 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d82a3-374">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="d82a3-375">VNsbc.contoso.com-모든 사용자에 게 Proxysbc.contoso.com – 항상 우회</span><span class="sxs-lookup"><span data-stu-id="d82a3-375">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="d82a3-376">사용자가 지역 사용자 용 으로만 SBC와 같은 위치에 있는 경우의 아웃 바운드 통화</span><span class="sxs-lookup"><span data-stu-id="d82a3-376">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="d82a3-377">모드</span><span class="sxs-lookup"><span data-stu-id="d82a3-377">Mode</span></span> | <span data-ttu-id="d82a3-378">사용자</span><span class="sxs-lookup"><span data-stu-id="d82a3-378">User</span></span> | <span data-ttu-id="d82a3-379">사이트</span><span class="sxs-lookup"><span data-stu-id="d82a3-379">Site</span></span> | <span data-ttu-id="d82a3-380">통화 방향</span><span class="sxs-lookup"><span data-stu-id="d82a3-380">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="d82a3-381">유일한 Forlocalusers</span><span class="sxs-lookup"><span data-stu-id="d82a3-381">OnlyForLocalUsers</span></span> |   <span data-ttu-id="d82a3-382">내부용</span><span class="sxs-lookup"><span data-stu-id="d82a3-382">Internal</span></span> |<span data-ttu-id="d82a3-383">SBC와 같음</span><span class="sxs-lookup"><span data-stu-id="d82a3-383">Same as SBC</span></span>   | <span data-ttu-id="d82a3-384">위한</span><span class="sxs-lookup"><span data-stu-id="d82a3-384">Outbound</span></span> |

<span data-ttu-id="d82a3-385">다음 다이어그램은 ' 없음 ' Localusers 모드를 사용 하는 아웃 바운드 호출을 보여 주며 사용자는 SBC와 같은 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-385">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="d82a3-386">이는 [사용자가 SBC와 같은 위치에 있을 때 나가는 호출](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)에 표시 되는 것과 동일한 흐름입니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-386">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![SIP 사다리를 표시 하는 다이어그램](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="d82a3-388">사용자가 지역 사용자 용 으로만 SBC와 같은 위치에 있는 경우의 인바운드 통화</span><span class="sxs-lookup"><span data-stu-id="d82a3-388">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="d82a3-389">모드</span><span class="sxs-lookup"><span data-stu-id="d82a3-389">Mode</span></span> | <span data-ttu-id="d82a3-390">사용자</span><span class="sxs-lookup"><span data-stu-id="d82a3-390">User</span></span> | <span data-ttu-id="d82a3-391">사이트</span><span class="sxs-lookup"><span data-stu-id="d82a3-391">Site</span></span> | <span data-ttu-id="d82a3-392">통화 방향</span><span class="sxs-lookup"><span data-stu-id="d82a3-392">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="d82a3-393">유일한 Forlocalusers</span><span class="sxs-lookup"><span data-stu-id="d82a3-393">OnlyForLocalUsers</span></span> |   <span data-ttu-id="d82a3-394">내부용</span><span class="sxs-lookup"><span data-stu-id="d82a3-394">Internal</span></span> | <span data-ttu-id="d82a3-395">SBC와 같음</span><span class="sxs-lookup"><span data-stu-id="d82a3-395">Same as SBC</span></span> | <span data-ttu-id="d82a3-396">Ipsec</span><span class="sxs-lookup"><span data-stu-id="d82a3-396">Inbound</span></span> |

<span data-ttu-id="d82a3-397">다음 다이어그램은이 모드를 사용 하는 인바운드 호출을 보여 주며 사용자는 SBC와 같은 위치에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-397">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="d82a3-398">이는 [사용자가 SBC와 같은 위치에 있을 때 인바운드 호출](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)에 표시 되는 것과 동일한 흐름입니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-398">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![SIP 사다리를 표시 하는 다이어그램](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="d82a3-400">사용자가 SBC와 같은 위치에 있지 않지만 로컬 사용자 용으로 회사 네트워크에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-400">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="d82a3-401">모드</span><span class="sxs-lookup"><span data-stu-id="d82a3-401">Mode</span></span> | <span data-ttu-id="d82a3-402">사용자</span><span class="sxs-lookup"><span data-stu-id="d82a3-402">User</span></span> | <span data-ttu-id="d82a3-403">사이트</span><span class="sxs-lookup"><span data-stu-id="d82a3-403">Site</span></span> |<span data-ttu-id="d82a3-404">통화 방향</span><span class="sxs-lookup"><span data-stu-id="d82a3-404">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="d82a3-405">유일한 Forlocalusers</span><span class="sxs-lookup"><span data-stu-id="d82a3-405">OnlyForLocalUsers</span></span>  | <span data-ttu-id="d82a3-406">내부용</span><span class="sxs-lookup"><span data-stu-id="d82a3-406">Internal</span></span> |   <span data-ttu-id="d82a3-407">SBC와 다름</span><span class="sxs-lookup"><span data-stu-id="d82a3-407">Different from SBC</span></span> | <span data-ttu-id="d82a3-408">위한</span><span class="sxs-lookup"><span data-stu-id="d82a3-408">Outbound</span></span> |

<span data-ttu-id="d82a3-409">직접 라우팅은 SBC에 구성 된 사용자 및 모드의 보고 된 위치를 기반으로 X-MediaPath를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-409">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="d82a3-410">다음 다이어그램에는 없음 Forlocalusers 모드를 사용 하는 아웃 바운드 호출과 SBC와 같은 위치에 있지 않은 내부 사용자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-410">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![SIP 사다리를 표시 하는 다이어그램](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="d82a3-412">인바운드 통화와 사용자는 내부용 이지만 지역 사용자의 경우 SBC와 같은 위치에 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-412">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="d82a3-413">모드</span><span class="sxs-lookup"><span data-stu-id="d82a3-413">Mode</span></span> |    <span data-ttu-id="d82a3-414">사용자</span><span class="sxs-lookup"><span data-stu-id="d82a3-414">User</span></span> |  <span data-ttu-id="d82a3-415">사이트</span><span class="sxs-lookup"><span data-stu-id="d82a3-415">Site</span></span> |  <span data-ttu-id="d82a3-416">통화 방향</span><span class="sxs-lookup"><span data-stu-id="d82a3-416">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="d82a3-417">유일한 Forlocalusers</span><span class="sxs-lookup"><span data-stu-id="d82a3-417">OnlyForLocalUsers</span></span> | <span data-ttu-id="d82a3-418">내부용</span><span class="sxs-lookup"><span data-stu-id="d82a3-418">Internal</span></span> |    <span data-ttu-id="d82a3-419">SBC와 다름</span><span class="sxs-lookup"><span data-stu-id="d82a3-419">Different from SBC</span></span> |    <span data-ttu-id="d82a3-420">Ipsec</span><span class="sxs-lookup"><span data-stu-id="d82a3-420">Inbound</span></span> |

<span data-ttu-id="d82a3-421">다음 다이어그램은 사용자 이름에는 없음 Forlocaluser 모드를 사용 하는 인바운드 호출과 SBC와 같은 위치에 있지 않은 내부 사용자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d82a3-421">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![SIP 사다리를 표시 하는 다이어그램](media/direct-routing-media-op-17.png)









