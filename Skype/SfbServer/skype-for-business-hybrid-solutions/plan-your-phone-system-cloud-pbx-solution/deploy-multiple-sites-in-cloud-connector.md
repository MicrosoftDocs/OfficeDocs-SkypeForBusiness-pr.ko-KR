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
description: 클라우드 커넥터 Edition에 여러 PSTN 사이트를 배포 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358924"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="be4c3-103">클라우드 커넥터에서 여러 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="be4c3-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="be4c3-104">클라우드 커넥터 버전은 비즈니스용 Skype Online과 함께 2021 년 7 월 31 일에 사용 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be4c3-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="be4c3-105">조직이 팀으로 업그레이드 된 후에는 [직접 라우팅을](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)사용 하 여 팀에 온-프레미스 전화 통신 네트워크를 연결 하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="be4c3-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="be4c3-106">클라우드 커넥터 Edition에 여러 PSTN 사이트를 배포 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="be4c3-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="be4c3-107">이 섹션에서는 여러 PSTN (공중 전화망) 사이트를 배포 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="be4c3-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="be4c3-108">단일 사이트를 배포 하는 것과 동일한 단계를 사용 하 여 한 번에 하나씩 사이트를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="be4c3-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="be4c3-109">이 항목에서는 여러 사이트 배포의 사이트 간 고려 사항 및 차이점에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="be4c3-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="be4c3-110">여러 PSTN (공중 전화망) 사이트</span><span class="sxs-lookup"><span data-stu-id="be4c3-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="be4c3-111">다음은 다양 한 PSTN 사이트에 대해 비즈니스용 Skype 클라우드 Connector Edition을 배포 하는 예제 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="be4c3-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="be4c3-112">배포를 시작 하기 전에 구성 설정이 올바른지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="be4c3-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="be4c3-113">PSTN 사이트 1</span><span class="sxs-lookup"><span data-stu-id="be4c3-113">PSTN Site 1</span></span>
  
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

<span data-ttu-id="be4c3-114">PSTN 사이트 2</span><span class="sxs-lookup"><span data-stu-id="be4c3-114">PSTN Site 2</span></span>
  
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

<span data-ttu-id="be4c3-115">추가 하려는 각 PSTN 사이트에 대해 [클라우드 커넥터에 단일 사이트 배포](deploy-a-single-site-in-cloud-connector.md)의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="be4c3-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="be4c3-116">HA (고가용성)를 준비 하기 위한 공유 폴더는 PSTN 사이트 별로 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="be4c3-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="be4c3-117">PSTN 사이트 간에 공유 폴더가 달라 **야 합니다** .</span><span class="sxs-lookup"><span data-stu-id="be4c3-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="be4c3-118">여러 사이트에 같은 공유 폴더를 사용 하지 마십시오. ></span><span class="sxs-lookup"><span data-stu-id="be4c3-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="be4c3-119">다중 사이트 배포에 비해 HA (고가용성)가 적용 되는 단일 사이트</span><span class="sxs-lookup"><span data-stu-id="be4c3-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="be4c3-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="be4c3-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="be4c3-121">다음 표에는 단일 사이트에서 HA를 지원 하 고 여러 사이트를 배포할 때의 차이점이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be4c3-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="be4c3-122">**종류**</span><span class="sxs-lookup"><span data-stu-id="be4c3-122">**Category**</span></span>|<span data-ttu-id="be4c3-123">**항목**</span><span class="sxs-lookup"><span data-stu-id="be4c3-123">**Item**</span></span>|<span data-ttu-id="be4c3-124">**HA를 사용한 단일 사이트**</span><span class="sxs-lookup"><span data-stu-id="be4c3-124">**Single-Site with HA**</span></span>|<span data-ttu-id="be4c3-125">**다중 사이트**</span><span class="sxs-lookup"><span data-stu-id="be4c3-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="be4c3-126">구성</span><span class="sxs-lookup"><span data-stu-id="be4c3-126">Configure</span></span>  <br/> |<span data-ttu-id="be4c3-127">기기 호스트 이름</span><span class="sxs-lookup"><span data-stu-id="be4c3-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="be4c3-128">**여러** 기기에서 다름</span><span class="sxs-lookup"><span data-stu-id="be4c3-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="be4c3-129">PSTN 사이트에서 **다름**</span><span class="sxs-lookup"><span data-stu-id="be4c3-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="be4c3-130">설정</span><span class="sxs-lookup"><span data-stu-id="be4c3-130">Setup</span></span>  <br/> |<span data-ttu-id="be4c3-131">공유 폴더</span><span class="sxs-lookup"><span data-stu-id="be4c3-131">Shared folder</span></span>  <br/> |<span data-ttu-id="be4c3-132">기기에서 **같은** 공유 폴더 필요</span><span class="sxs-lookup"><span data-stu-id="be4c3-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="be4c3-133">여러 기기에서 **다른** 공유 폴더 필요</span><span class="sxs-lookup"><span data-stu-id="be4c3-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="be4c3-134">구성</span><span class="sxs-lookup"><span data-stu-id="be4c3-134">Configure</span></span>  <br/> |<span data-ttu-id="be4c3-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="be4c3-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="be4c3-136">모든 기기에 **동일한** 도메인 필요</span><span class="sxs-lookup"><span data-stu-id="be4c3-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="be4c3-137">PSTN 사이트에서 **동일한** 도메인 필요</span><span class="sxs-lookup"><span data-stu-id="be4c3-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="be4c3-138">구성</span><span class="sxs-lookup"><span data-stu-id="be4c3-138">Configure</span></span>  <br/> |<span data-ttu-id="be4c3-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="be4c3-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="be4c3-140">도메인 이름 및 순서는 모든 기기에서 **동일** 해야 함</span><span class="sxs-lookup"><span data-stu-id="be4c3-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="be4c3-141">도메인 이름 및 순서는 PSTN 사이트에서 **동일** 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be4c3-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="be4c3-142">구성</span><span class="sxs-lookup"><span data-stu-id="be4c3-142">Configure</span></span>  <br/> |<span data-ttu-id="be4c3-143">사이트 이름</span><span class="sxs-lookup"><span data-stu-id="be4c3-143">Site name</span></span>  <br/> |<span data-ttu-id="be4c3-144">**동일** 기기 간의 사이트 이름</span><span class="sxs-lookup"><span data-stu-id="be4c3-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="be4c3-145">**다양** PSTN 사이트 간의 사이트 이름</span><span class="sxs-lookup"><span data-stu-id="be4c3-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="be4c3-146">구성</span><span class="sxs-lookup"><span data-stu-id="be4c3-146">Configure</span></span>  <br/> |<span data-ttu-id="be4c3-147">서버 이름</span><span class="sxs-lookup"><span data-stu-id="be4c3-147">Server names</span></span>  <br/> |<span data-ttu-id="be4c3-148">**여러** 기기에서 다름</span><span class="sxs-lookup"><span data-stu-id="be4c3-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="be4c3-149">PSTN 사이트에서 **다름**</span><span class="sxs-lookup"><span data-stu-id="be4c3-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="be4c3-150">구성</span><span class="sxs-lookup"><span data-stu-id="be4c3-150">Configure</span></span>  <br/> |<span data-ttu-id="be4c3-151">내부 풀 Fqdn</span><span class="sxs-lookup"><span data-stu-id="be4c3-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="be4c3-152">여러 기기에서 **동일**</span><span class="sxs-lookup"><span data-stu-id="be4c3-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="be4c3-153">PSTN 사이트에서 **동일**</span><span class="sxs-lookup"><span data-stu-id="be4c3-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="be4c3-154">구성</span><span class="sxs-lookup"><span data-stu-id="be4c3-154">Configure</span></span>  <br/> |<span data-ttu-id="be4c3-155">내부 Ip</span><span class="sxs-lookup"><span data-stu-id="be4c3-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="be4c3-156">**여러** 기기에서 다름</span><span class="sxs-lookup"><span data-stu-id="be4c3-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="be4c3-157">PSTN 사이트에서 **다름**</span><span class="sxs-lookup"><span data-stu-id="be4c3-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="be4c3-158">구성</span><span class="sxs-lookup"><span data-stu-id="be4c3-158">Configure</span></span>  <br/> |<span data-ttu-id="be4c3-159">외부 FQDN</span><span class="sxs-lookup"><span data-stu-id="be4c3-159">External FQDN</span></span>  <br/> |<span data-ttu-id="be4c3-160">여러 기기에서 **동일**</span><span class="sxs-lookup"><span data-stu-id="be4c3-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="be4c3-161">PSTN 사이트에서 **다름**</span><span class="sxs-lookup"><span data-stu-id="be4c3-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="be4c3-162">구성</span><span class="sxs-lookup"><span data-stu-id="be4c3-162">Configure</span></span>  <br/> |<span data-ttu-id="be4c3-163">외부 Ip</span><span class="sxs-lookup"><span data-stu-id="be4c3-163">External IPs</span></span>  <br/> |<span data-ttu-id="be4c3-164">**여러** 기기에서 다름</span><span class="sxs-lookup"><span data-stu-id="be4c3-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="be4c3-165">PSTN 사이트에서 **다름**</span><span class="sxs-lookup"><span data-stu-id="be4c3-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="be4c3-166">구성</span><span class="sxs-lookup"><span data-stu-id="be4c3-166">Configure</span></span>  <br/> |<span data-ttu-id="be4c3-167">PSTN GW 설정</span><span class="sxs-lookup"><span data-stu-id="be4c3-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="be4c3-168">여러 기기에서 **동일**</span><span class="sxs-lookup"><span data-stu-id="be4c3-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="be4c3-169">PSTN 사이트에서 **다름**</span><span class="sxs-lookup"><span data-stu-id="be4c3-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="be4c3-170">구성</span><span class="sxs-lookup"><span data-stu-id="be4c3-170">Configure</span></span>  <br/> |<span data-ttu-id="be4c3-171">DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="be4c3-171">DNS record</span></span>  <br/> |<span data-ttu-id="be4c3-172">**동일한** 외부 액세스 fqdn 및 **서로 다른** IP 주소를 사용 하 여 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="be4c3-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="be4c3-173">**다른** 외부 액세스 fqdn 및 **서로 다른** IP 주소를 사용 하 여 레코드 추가</span><span class="sxs-lookup"><span data-stu-id="be4c3-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="be4c3-174">설정</span><span class="sxs-lookup"><span data-stu-id="be4c3-174">Setup</span></span>  <br/> |<span data-ttu-id="be4c3-175">하이브리드 테 넌 트</span><span class="sxs-lookup"><span data-stu-id="be4c3-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="be4c3-176">Set HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="be4c3-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="be4c3-177">대체에 대해 PeerDestination 설정</span><span class="sxs-lookup"><span data-stu-id="be4c3-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="be4c3-178">Set HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="be4c3-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="be4c3-179">대체에 대해 PeerDestination 설정</span><span class="sxs-lookup"><span data-stu-id="be4c3-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="be4c3-180">설정</span><span class="sxs-lookup"><span data-stu-id="be4c3-180">Setup</span></span>  <br/> |<span data-ttu-id="be4c3-181">게이트웨이</span><span class="sxs-lookup"><span data-stu-id="be4c3-181">Gateway</span></span>  <br/> |<span data-ttu-id="be4c3-182">이 사이트의 MS GW **M:n** 매핑</span><span class="sxs-lookup"><span data-stu-id="be4c3-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="be4c3-183">각 PSTN 사이트의 PSTN 게이트웨이는 동일한 사이트의 중재 서버에만 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be4c3-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="be4c3-184">설정</span><span class="sxs-lookup"><span data-stu-id="be4c3-184">Setup</span></span>  <br/> |<span data-ttu-id="be4c3-185">사용자</span><span class="sxs-lookup"><span data-stu-id="be4c3-185">User</span></span>  <br/> |<span data-ttu-id="be4c3-186">Set UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="be4c3-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="be4c3-187">Set UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="be4c3-187">Set UserPSTNSettings</span></span>  <br/> |
   

