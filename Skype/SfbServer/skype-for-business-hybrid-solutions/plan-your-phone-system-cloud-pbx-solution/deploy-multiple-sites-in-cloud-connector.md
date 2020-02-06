---
title: 클라우드 커넥터에서 여러 사이트 배포
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: 클라우드 커넥터 에디션에 여러 PSTN 사이트를 배포 하는 방법에 대해 알아보세요.
ms.openlocfilehash: 98890bb3ffe53497c5e915acba5c073c4316f3b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799698"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="f6f45-103">클라우드 커넥터에서 여러 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="f6f45-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="f6f45-104">클라우드 커넥터 에디션에 여러 PSTN 사이트를 배포 하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="f6f45-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="f6f45-105">이 섹션에서는 여러 PSTN (공개 교환 전화 네트워크) 사이트를 배포 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f45-105">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="f6f45-106">사이트는 단일 사이트 배포와 동일한 단계를 사용 하 여 한 번에 하나씩 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6f45-106">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="f6f45-107">이 항목에서는 여러 사이트 배포의 사이트 간 고려 사항 및 차이점에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f45-107">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="f6f45-108">여러 PSTN (공개 교환 전화 네트워크) 사이트</span><span class="sxs-lookup"><span data-stu-id="f6f45-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="f6f45-109">다음은 다양 한 PSTN 사이트에 대해 비즈니스용 Skype 클라우드 커넥터 에디션을 배포 하는 예제 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6f45-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="f6f45-110">배포를 시작 하기 전에 구성 설정이 올바른지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="f6f45-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="f6f45-111">PSTN 사이트 1</span><span class="sxs-lookup"><span data-stu-id="f6f45-111">PSTN Site 1</span></span>
  
```
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

<span data-ttu-id="f6f45-112">PSTN 사이트 2</span><span class="sxs-lookup"><span data-stu-id="f6f45-112">PSTN Site 2</span></span>
  
```
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

<span data-ttu-id="f6f45-113">추가 하려는 각 PSTN 사이트에 대해 [클라우드 커넥터에 단일 사이트 배포](deploy-a-single-site-in-cloud-connector.md)의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f6f45-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f6f45-114">HA (고가용성)를 준비 하는 공유 폴더는 PSTN 사이트 별로입니다.</span><span class="sxs-lookup"><span data-stu-id="f6f45-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="f6f45-115">공유 폴더는 PSTN 사이트 간에 달라 **야 합니다** .</span><span class="sxs-lookup"><span data-stu-id="f6f45-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="f6f45-116">여러 사이트에 같은 공유 폴더를 사용 하지 마세요. ></span><span class="sxs-lookup"><span data-stu-id="f6f45-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="f6f45-117">멀티 사이트 배포에 비해 HA (고가용성)가 포함 된 단일 사이트</span><span class="sxs-lookup"><span data-stu-id="f6f45-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="f6f45-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="f6f45-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="f6f45-119">다음 표에는 HA 지원과 다중 사이트 배포의 단일 사이트 간 차이점이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6f45-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="f6f45-120">**범주만**</span><span class="sxs-lookup"><span data-stu-id="f6f45-120">**Category**</span></span>|<span data-ttu-id="f6f45-121">**항목과**</span><span class="sxs-lookup"><span data-stu-id="f6f45-121">**Item**</span></span>|<span data-ttu-id="f6f45-122">**HA를 사용 하는 단일 사이트**</span><span class="sxs-lookup"><span data-stu-id="f6f45-122">**Single-Site with HA**</span></span>|<span data-ttu-id="f6f45-123">**다중 사이트**</span><span class="sxs-lookup"><span data-stu-id="f6f45-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f6f45-124">구성할</span><span class="sxs-lookup"><span data-stu-id="f6f45-124">Configure</span></span>  <br/> |<span data-ttu-id="f6f45-125">기기 호스트 이름</span><span class="sxs-lookup"><span data-stu-id="f6f45-125">Appliance Host Name</span></span> <br/> |<span data-ttu-id="f6f45-126">가전 기기에서 **다름**</span><span class="sxs-lookup"><span data-stu-id="f6f45-126">**Different** across appliances</span></span> <br/> |<span data-ttu-id="f6f45-127">PSTN 사이트에서 **다름**</span><span class="sxs-lookup"><span data-stu-id="f6f45-127">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f6f45-128">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="f6f45-128">Setup</span></span>  <br/> |<span data-ttu-id="f6f45-129">공유 폴더</span><span class="sxs-lookup"><span data-stu-id="f6f45-129">Shared folder</span></span>  <br/> |<span data-ttu-id="f6f45-130">기기에서 **같은** 공유 폴더 필요</span><span class="sxs-lookup"><span data-stu-id="f6f45-130">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="f6f45-131">기기 간에 **다른** 공유 폴더가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f45-131">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="f6f45-132">구성할</span><span class="sxs-lookup"><span data-stu-id="f6f45-132">Configure</span></span>  <br/> |<span data-ttu-id="f6f45-133">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="f6f45-133">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="f6f45-134">모든 기기에 **같은** 도메인이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f45-134">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="f6f45-135">PSTN 사이트에서 **같은** 도메인이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f45-135">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f6f45-136">구성할</span><span class="sxs-lookup"><span data-stu-id="f6f45-136">Configure</span></span>  <br/> |<span data-ttu-id="f6f45-137">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="f6f45-137">SIPDomains</span></span>  <br/> |<span data-ttu-id="f6f45-138">도메인 이름 및 주문은 기기에서 **동일** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f45-138">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="f6f45-139">도메인 이름 및 주문은 PSTN 사이트에서 **동일** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f45-139">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f6f45-140">구성할</span><span class="sxs-lookup"><span data-stu-id="f6f45-140">Configure</span></span>  <br/> |<span data-ttu-id="f6f45-141">사이트 이름</span><span class="sxs-lookup"><span data-stu-id="f6f45-141">Site name</span></span>  <br/> |<span data-ttu-id="f6f45-142">**같은** 기기 간의 사이트 이름</span><span class="sxs-lookup"><span data-stu-id="f6f45-142">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="f6f45-143">**다른** PSTN 사이트 간 사이트 이름</span><span class="sxs-lookup"><span data-stu-id="f6f45-143">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f6f45-144">구성할</span><span class="sxs-lookup"><span data-stu-id="f6f45-144">Configure</span></span>  <br/> |<span data-ttu-id="f6f45-145">서버 이름</span><span class="sxs-lookup"><span data-stu-id="f6f45-145">Server names</span></span>  <br/> |<span data-ttu-id="f6f45-146">가전 기기에서 **다름**</span><span class="sxs-lookup"><span data-stu-id="f6f45-146">**Different** across appliances</span></span> <br/> |<span data-ttu-id="f6f45-147">PSTN 사이트에서 **다름**</span><span class="sxs-lookup"><span data-stu-id="f6f45-147">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f6f45-148">구성할</span><span class="sxs-lookup"><span data-stu-id="f6f45-148">Configure</span></span>  <br/> |<span data-ttu-id="f6f45-149">내부 풀 Fqdn</span><span class="sxs-lookup"><span data-stu-id="f6f45-149">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="f6f45-150">기기에서 **동일** 하 게</span><span class="sxs-lookup"><span data-stu-id="f6f45-150">**Same** across appliances</span></span> <br/> |<span data-ttu-id="f6f45-151">PSTN 사이트에서 **동일**</span><span class="sxs-lookup"><span data-stu-id="f6f45-151">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f6f45-152">구성할</span><span class="sxs-lookup"><span data-stu-id="f6f45-152">Configure</span></span>  <br/> |<span data-ttu-id="f6f45-153">내부 Ip</span><span class="sxs-lookup"><span data-stu-id="f6f45-153">Internal IPs</span></span>  <br/> |<span data-ttu-id="f6f45-154">가전 기기에서 **다름**</span><span class="sxs-lookup"><span data-stu-id="f6f45-154">**Different** across appliances</span></span> <br/> |<span data-ttu-id="f6f45-155">PSTN 사이트에서 **다름**</span><span class="sxs-lookup"><span data-stu-id="f6f45-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f6f45-156">구성할</span><span class="sxs-lookup"><span data-stu-id="f6f45-156">Configure</span></span>  <br/> |<span data-ttu-id="f6f45-157">외부 FQDN</span><span class="sxs-lookup"><span data-stu-id="f6f45-157">External FQDN</span></span>  <br/> |<span data-ttu-id="f6f45-158">기기에서 **동일** 하 게</span><span class="sxs-lookup"><span data-stu-id="f6f45-158">**Same** across appliances</span></span> <br/> |<span data-ttu-id="f6f45-159">PSTN 사이트에서 **다름**</span><span class="sxs-lookup"><span data-stu-id="f6f45-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f6f45-160">구성할</span><span class="sxs-lookup"><span data-stu-id="f6f45-160">Configure</span></span>  <br/> |<span data-ttu-id="f6f45-161">외부 Ip</span><span class="sxs-lookup"><span data-stu-id="f6f45-161">External IPs</span></span>  <br/> |<span data-ttu-id="f6f45-162">가전 기기에서 **다름**</span><span class="sxs-lookup"><span data-stu-id="f6f45-162">**Different** across appliances</span></span> <br/> |<span data-ttu-id="f6f45-163">PSTN 사이트에서 **다름**</span><span class="sxs-lookup"><span data-stu-id="f6f45-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f6f45-164">구성할</span><span class="sxs-lookup"><span data-stu-id="f6f45-164">Configure</span></span>  <br/> |<span data-ttu-id="f6f45-165">PSTN GW 설정</span><span class="sxs-lookup"><span data-stu-id="f6f45-165">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="f6f45-166">기기에서 **동일** 하 게</span><span class="sxs-lookup"><span data-stu-id="f6f45-166">**Same** across appliances</span></span> <br/> |<span data-ttu-id="f6f45-167">PSTN 사이트에서 **다름**</span><span class="sxs-lookup"><span data-stu-id="f6f45-167">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="f6f45-168">구성할</span><span class="sxs-lookup"><span data-stu-id="f6f45-168">Configure</span></span>  <br/> |<span data-ttu-id="f6f45-169">DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="f6f45-169">DNS record</span></span>  <br/> |<span data-ttu-id="f6f45-170">**동일한** 외부 액세스 fqdn 및 **다른** IP 주소를 사용 하 여 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="f6f45-170">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="f6f45-171">**다른** 외부 액세스 fqdn 및 **다른** IP 주소를 사용 하 여 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="f6f45-171">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="f6f45-172">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="f6f45-172">Setup</span></span>  <br/> |<span data-ttu-id="f6f45-173">하이브리드 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="f6f45-173">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="f6f45-174">Set HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="f6f45-174">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="f6f45-175">Fallback에 대 한 PeerDestination 설정</span><span class="sxs-lookup"><span data-stu-id="f6f45-175">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="f6f45-176">Set HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="f6f45-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="f6f45-177">Fallback에 대 한 PeerDestination 설정</span><span class="sxs-lookup"><span data-stu-id="f6f45-177">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="f6f45-178">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="f6f45-178">Setup</span></span>  <br/> |<span data-ttu-id="f6f45-179">게이트웨이와</span><span class="sxs-lookup"><span data-stu-id="f6f45-179">Gateway</span></span>  <br/> |<span data-ttu-id="f6f45-180">이 사이트의 MS GW **M:n** 매핑</span><span class="sxs-lookup"><span data-stu-id="f6f45-180">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="f6f45-181">각 PSTN 사이트의 PSTN 게이트웨이는 동일한 사이트의 중재 서버에만 연결 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6f45-181">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="f6f45-182">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="f6f45-182">Setup</span></span>  <br/> |<span data-ttu-id="f6f45-183">사용자</span><span class="sxs-lookup"><span data-stu-id="f6f45-183">User</span></span>  <br/> |<span data-ttu-id="f6f45-184">Set UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="f6f45-184">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="f6f45-185">Set UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="f6f45-185">Set UserPSTNSettings</span></span>  <br/> |
   

