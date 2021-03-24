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
description: Cloud Connector Edition에서 여러 PSTN 사이트 배포에 대해 자세히 알아보습니다.
ms.openlocfilehash: 059b9a39a082e876b1dd9cd772a235c384a29107
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098404"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="17fb8-103">클라우드 커넥터에서 여러 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="17fb8-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="17fb8-104">Cloud Connector Edition은 비즈니스용 Skype Online과 함께 2021년 7월 31일부터 사용이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="17fb8-105">조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="17fb8-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="17fb8-106">Cloud Connector Edition에서 여러 PSTN 사이트 배포에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="17fb8-107">이 섹션에서는 여러 PSTN(Public Switched Telephone Network) 사이트를 배포하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="17fb8-108">사이트는 단일 사이트를 배포하는 단계와 동일한 단계를 사용하여 한 번씩 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="17fb8-109">이 항목에서는 여러 사이트 배포의 사이트 간 고려 사항과 차이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="17fb8-110">여러 PSTN(Public Switched Telephone Network) 사이트</span><span class="sxs-lookup"><span data-stu-id="17fb8-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="17fb8-111">다음에서는 서로 다른 PSTN 사이트에 대해 비즈니스용 Skype 클라우드 커넥터 Edition을 배포하는 예제 구성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="17fb8-112">배포를 시작하기 전에 구성 설정이 올바른지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="17fb8-113">PSTN 사이트 1</span><span class="sxs-lookup"><span data-stu-id="17fb8-113">PSTN Site 1</span></span>
  
```console
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

<span data-ttu-id="17fb8-114">PSTN 사이트 2</span><span class="sxs-lookup"><span data-stu-id="17fb8-114">PSTN Site 2</span></span>
  
```console
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

<span data-ttu-id="17fb8-115">추가할 각 PSTN 사이트에 대해 클라우드 커넥터에서 단일 사이트 [배포의 단계를 따릅니다.](deploy-a-single-site-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="17fb8-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="17fb8-116">HA(고가용성)를 준비하기 위한 공유 폴더는 PSTN 사이트당입니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="17fb8-117">공유 **폴더는** PSTN 사이트 간에 달라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="17fb8-118">여러 사이트에 동일한 공유 폴더를 사용하지 않습니다.></span><span class="sxs-lookup"><span data-stu-id="17fb8-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="17fb8-119">다중 사이트 배포에 비해 HA(고가용성)가 있는 단일 사이트</span><span class="sxs-lookup"><span data-stu-id="17fb8-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="17fb8-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="17fb8-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="17fb8-121">다음 표에는 HA 지원이 있는 단일 사이트와 다중 사이트 배포 간의 차이점이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="17fb8-122">**범주**</span><span class="sxs-lookup"><span data-stu-id="17fb8-122">**Category**</span></span>|<span data-ttu-id="17fb8-123">**항목**</span><span class="sxs-lookup"><span data-stu-id="17fb8-123">**Item**</span></span>|<span data-ttu-id="17fb8-124">**HA가 있는 단일 사이트**</span><span class="sxs-lookup"><span data-stu-id="17fb8-124">**Single-Site with HA**</span></span>|<span data-ttu-id="17fb8-125">**다중 사이트**</span><span class="sxs-lookup"><span data-stu-id="17fb8-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="17fb8-126">구성</span><span class="sxs-lookup"><span data-stu-id="17fb8-126">Configure</span></span>  <br/> |<span data-ttu-id="17fb8-127">Appliance 호스트 이름</span><span class="sxs-lookup"><span data-stu-id="17fb8-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="17fb8-128">**다양한** 어플라이언스</span><span class="sxs-lookup"><span data-stu-id="17fb8-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="17fb8-129"> PSTN 사이트마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="17fb8-130">설정</span><span class="sxs-lookup"><span data-stu-id="17fb8-130">Setup</span></span>  <br/> |<span data-ttu-id="17fb8-131">공유 폴더</span><span class="sxs-lookup"><span data-stu-id="17fb8-131">Shared folder</span></span>  <br/> |<span data-ttu-id="17fb8-132">여러  어플라이언스에서 동일한 공유 폴더 필요</span><span class="sxs-lookup"><span data-stu-id="17fb8-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="17fb8-133">여러 **어플라이언스에** 다른 공유 폴더 필요</span><span class="sxs-lookup"><span data-stu-id="17fb8-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="17fb8-134">구성</span><span class="sxs-lookup"><span data-stu-id="17fb8-134">Configure</span></span>  <br/> |<span data-ttu-id="17fb8-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="17fb8-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="17fb8-136">여러 **어플라이언스에** 동일한 도메인 필요</span><span class="sxs-lookup"><span data-stu-id="17fb8-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="17fb8-137">PSTN **사이트에** 동일한 도메인 필요</span><span class="sxs-lookup"><span data-stu-id="17fb8-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="17fb8-138">구성</span><span class="sxs-lookup"><span data-stu-id="17fb8-138">Configure</span></span>  <br/> |<span data-ttu-id="17fb8-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="17fb8-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="17fb8-140">여러 어플라이언스에서 도메인 **이름과** 순서가 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="17fb8-141">도메인 이름 및 순서는 PSTN 사이트에서 동일해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="17fb8-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="17fb8-142">구성</span><span class="sxs-lookup"><span data-stu-id="17fb8-142">Configure</span></span>  <br/> |<span data-ttu-id="17fb8-143">사이트 이름</span><span class="sxs-lookup"><span data-stu-id="17fb8-143">Site name</span></span>  <br/> |<span data-ttu-id="17fb8-144">**동일** 어플라이언스 전체의 사이트 이름</span><span class="sxs-lookup"><span data-stu-id="17fb8-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="17fb8-145">**서로 다른** PSTN 사이트의 사이트 이름</span><span class="sxs-lookup"><span data-stu-id="17fb8-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="17fb8-146">구성</span><span class="sxs-lookup"><span data-stu-id="17fb8-146">Configure</span></span>  <br/> |<span data-ttu-id="17fb8-147">서버 이름</span><span class="sxs-lookup"><span data-stu-id="17fb8-147">Server names</span></span>  <br/> |<span data-ttu-id="17fb8-148">**다양한** 어플라이언스</span><span class="sxs-lookup"><span data-stu-id="17fb8-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="17fb8-149"> PSTN 사이트마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="17fb8-150">구성</span><span class="sxs-lookup"><span data-stu-id="17fb8-150">Configure</span></span>  <br/> |<span data-ttu-id="17fb8-151">내부 풀 FQDNs</span><span class="sxs-lookup"><span data-stu-id="17fb8-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="17fb8-152">**여러** 어플라이언스에서 동일</span><span class="sxs-lookup"><span data-stu-id="17fb8-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="17fb8-153"> PSTN 사이트 전체에서 동일</span><span class="sxs-lookup"><span data-stu-id="17fb8-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="17fb8-154">구성</span><span class="sxs-lookup"><span data-stu-id="17fb8-154">Configure</span></span>  <br/> |<span data-ttu-id="17fb8-155">내부 IPS</span><span class="sxs-lookup"><span data-stu-id="17fb8-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="17fb8-156">**다양한** 어플라이언스</span><span class="sxs-lookup"><span data-stu-id="17fb8-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="17fb8-157"> PSTN 사이트마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="17fb8-158">구성</span><span class="sxs-lookup"><span data-stu-id="17fb8-158">Configure</span></span>  <br/> |<span data-ttu-id="17fb8-159">외부 FQDN</span><span class="sxs-lookup"><span data-stu-id="17fb8-159">External FQDN</span></span>  <br/> |<span data-ttu-id="17fb8-160">**여러** 어플라이언스에서 동일</span><span class="sxs-lookup"><span data-stu-id="17fb8-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="17fb8-161"> PSTN 사이트마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="17fb8-162">구성</span><span class="sxs-lookup"><span data-stu-id="17fb8-162">Configure</span></span>  <br/> |<span data-ttu-id="17fb8-163">외부 IPS</span><span class="sxs-lookup"><span data-stu-id="17fb8-163">External IPs</span></span>  <br/> |<span data-ttu-id="17fb8-164">**다양한** 어플라이언스</span><span class="sxs-lookup"><span data-stu-id="17fb8-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="17fb8-165"> PSTN 사이트마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="17fb8-166">구성</span><span class="sxs-lookup"><span data-stu-id="17fb8-166">Configure</span></span>  <br/> |<span data-ttu-id="17fb8-167">PSTN GW 설정</span><span class="sxs-lookup"><span data-stu-id="17fb8-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="17fb8-168">**여러** 어플라이언스에서 동일</span><span class="sxs-lookup"><span data-stu-id="17fb8-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="17fb8-169"> PSTN 사이트마다 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="17fb8-170">구성</span><span class="sxs-lookup"><span data-stu-id="17fb8-170">Configure</span></span>  <br/> |<span data-ttu-id="17fb8-171">DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="17fb8-171">DNS record</span></span>  <br/> |<span data-ttu-id="17fb8-172">동일한 외부  액세스 FQDNS 및 **다른** IP 주소가 있는 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="17fb8-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="17fb8-173">다른 외부  액세스 FQDNS 및 **다른** IP 주소가 있는 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="17fb8-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="17fb8-174">설정</span><span class="sxs-lookup"><span data-stu-id="17fb8-174">Setup</span></span>  <br/> |<span data-ttu-id="17fb8-175">하이브리드 테넌트</span><span class="sxs-lookup"><span data-stu-id="17fb8-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="17fb8-176">HybridPSTNSite 설정</span><span class="sxs-lookup"><span data-stu-id="17fb8-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="17fb8-177">폴백에 대한 PeerDestination 설정</span><span class="sxs-lookup"><span data-stu-id="17fb8-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="17fb8-178">HybridPSTNSite 설정</span><span class="sxs-lookup"><span data-stu-id="17fb8-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="17fb8-179">폴백에 대한 PeerDestination 설정</span><span class="sxs-lookup"><span data-stu-id="17fb8-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="17fb8-180">설정</span><span class="sxs-lookup"><span data-stu-id="17fb8-180">Setup</span></span>  <br/> |<span data-ttu-id="17fb8-181">게이트웨이</span><span class="sxs-lookup"><span data-stu-id="17fb8-181">Gateway</span></span>  <br/> |<span data-ttu-id="17fb8-182">이 사이트의 MS GW **M:N** 매핑</span><span class="sxs-lookup"><span data-stu-id="17fb8-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="17fb8-183">각 PSTN 사이트의 PSTN 게이트웨이는 동일한 사이트의 중재 서버에만 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17fb8-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="17fb8-184">설정</span><span class="sxs-lookup"><span data-stu-id="17fb8-184">Setup</span></span>  <br/> |<span data-ttu-id="17fb8-185">사용자</span><span class="sxs-lookup"><span data-stu-id="17fb8-185">User</span></span>  <br/> |<span data-ttu-id="17fb8-186">UserPSTNSettings 설정</span><span class="sxs-lookup"><span data-stu-id="17fb8-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="17fb8-187">UserPSTNSettings 설정</span><span class="sxs-lookup"><span data-stu-id="17fb8-187">Set UserPSTNSettings</span></span>  <br/> |
