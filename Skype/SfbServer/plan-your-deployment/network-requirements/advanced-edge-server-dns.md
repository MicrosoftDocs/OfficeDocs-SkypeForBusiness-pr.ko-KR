---
title: 비즈니스용 Skype 서버에 대한 고급 에지 서버 DNS 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: '요약: 비즈니스용 Skype 서버 배포 옵션에 대한 시나리오를 검토합니다. 단일 서버를 사용하려는 경우 또는 DNS 또는 HLB가 있는 서버 풀을 선호하는 경우 이 항목은 도움이 됩니다.'
ms.openlocfilehash: 5a41baac30f3bf6a1e20ae34db009dae0cec40af
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825328"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a><span data-ttu-id="bf561-104">비즈니스용 Skype 서버에 대한 고급 에지 서버 DNS 계획</span><span class="sxs-lookup"><span data-stu-id="bf561-104">Advanced Edge Server DNS planning for Skype for Business Server</span></span>
 
<span data-ttu-id="bf561-105">**요약:** 비즈니스용 Skype 서버 배포 옵션에 대한 시나리오를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-105">**Summary:** Review scenarios for Skype for Business Server deployment options.</span></span> <span data-ttu-id="bf561-106">단일 서버를 사용하려는 경우 또는 DNS 또는 HLB가 있는 서버 풀을 선호하는 경우 이 항목은 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-106">Whether you want a single server or prefer a server pool with DNS or HLB, this topic should help.</span></span>
  
<span data-ttu-id="bf561-107">비즈니스용 Skype 서버의 DNS(Domain Name System) 계획에는 결정에 영향을 주게 될 수 있는 많은 요인이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-107">When it comes to Domain Name System (DNS) planning for Skype for Business Server, there are a lot of factors that may play into your decision.</span></span> <span data-ttu-id="bf561-108">조직의 도메인 구조가 이미 설정되어 있는 경우 진행 방법을 검토할 때 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-108">If your organization's domain structure's already in place, this may be a matter of reviewing how you're going to proceed.</span></span> <span data-ttu-id="bf561-109">아래에서 설명하는 항목부터 시작해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-109">We'll begin with the topics found below:</span></span>
  
- [<span data-ttu-id="bf561-110">서비스를 찾기 위한 비즈니스용 Skype 클라이언트의 Walkthrough</span><span class="sxs-lookup"><span data-stu-id="bf561-110">Walkthrough of Skype for Business clients locating services</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [<span data-ttu-id="bf561-111">분할 DNS</span><span class="sxs-lookup"><span data-stu-id="bf561-111">Split-brain DNS</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [<span data-ttu-id="bf561-112">분할 DNS 없이 자동 구성</span><span class="sxs-lookup"><span data-stu-id="bf561-112">Automatic configuration without split-brain DNS</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [<span data-ttu-id="bf561-113">DNS 재해 복구</span><span class="sxs-lookup"><span data-stu-id="bf561-113">DNS disaster recovery</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [<span data-ttu-id="bf561-114">DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="bf561-114">DNS load balancing</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a><span data-ttu-id="bf561-115">서비스를 찾기 위한 비즈니스용 Skype 클라이언트의 Walkthrough</span><span class="sxs-lookup"><span data-stu-id="bf561-115">Walkthrough of Skype for Business clients locating services</span></span>
<span data-ttu-id="bf561-116"><a name="WalkthroughOfSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="bf561-116"><a name="WalkthroughOfSkype"> </a></span></span>

<span data-ttu-id="bf561-117">비즈니스용 Skype 클라이언트는 비즈니스용 Skype 서버에서 서비스를 찾고 액세스하는 방법에서 이전 버전의 Lync 클라이언트와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-117">Skype for Business clients are similar to previous versions of Lync clients in how they find and access services in Skype for Business Server.</span></span> <span data-ttu-id="bf561-118">이 섹션에서는 서버 위치 프로세스에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-118">This section details the server location process.</span></span>
  
1. <span data-ttu-id="bf561-119">lyncdiscoverinternal.\<domain\></span><span class="sxs-lookup"><span data-stu-id="bf561-119">lyncdiscoverinternal.\<domain\></span></span>
    
     <span data-ttu-id="bf561-120">*내부 웹 서비스의 자동 검색 서비스에 대한 호스트 레코드입니다.*</span><span class="sxs-lookup"><span data-stu-id="bf561-120">*This is an A host record for the Autodiscover service on the internal web services.*</span></span> 
    
2. <span data-ttu-id="bf561-121">lyncdiscover.\<domain\></span><span class="sxs-lookup"><span data-stu-id="bf561-121">lyncdiscover.\<domain\></span></span>
    
     <span data-ttu-id="bf561-122">*이 레코드는 외부 웹 서비스의 자동 검색 서비스에 대한 호스트 레코드입니다.*</span><span class="sxs-lookup"><span data-stu-id="bf561-122">*This is an A host record for the Autodiscover service on the external web services.*</span></span> 
    
3. <span data-ttu-id="bf561-123">_sipinternaltls._tcp.\<domain\></span><span class="sxs-lookup"><span data-stu-id="bf561-123">_sipinternaltls._tcp.\<domain\></span></span>
    
     <span data-ttu-id="bf561-124">*내부 TLS 연결에 대한 SRV 레코드입니다.*</span><span class="sxs-lookup"><span data-stu-id="bf561-124">*This is a SRV record for internal TLS connections.*</span></span> 
    
4. <span data-ttu-id="bf561-125">_sip._tls.\<domain\></span><span class="sxs-lookup"><span data-stu-id="bf561-125">_sip._tls.\<domain\></span></span>
    
     <span data-ttu-id="bf561-126">*외부 TLS 연결에 대한 SRV 레코드입니다.*</span><span class="sxs-lookup"><span data-stu-id="bf561-126">*This is a SRV record for external TLS connections.*</span></span> 
    
5. <span data-ttu-id="bf561-127">sipinternal.\<domain\></span><span class="sxs-lookup"><span data-stu-id="bf561-127">sipinternal.\<domain\></span></span>
    
     <span data-ttu-id="bf561-128">*이 레코드는 프런트 엔드 풀 또는 Director에 대한 호스트 레코드로, 내부 네트워크에서만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bf561-128">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
6. <span data-ttu-id="bf561-129">sip.\<domain\></span><span class="sxs-lookup"><span data-stu-id="bf561-129">sip.\<domain\></span></span>
    
     <span data-ttu-id="bf561-130">*이 레코드는 프런트 엔드 풀 또는 Director에 대한 호스트 레코드로, 내부 네트워크에서만 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="bf561-130">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
7. <span data-ttu-id="bf561-131">sipexternal.\<domain\></span><span class="sxs-lookup"><span data-stu-id="bf561-131">sipexternal.\<domain\></span></span>
    
     <span data-ttu-id="bf561-132">*클라이언트가 외부에 있는 경우 액세스 에지 서비스의 호스트 레코드입니다.*</span><span class="sxs-lookup"><span data-stu-id="bf561-132">*This is an A host record for the Access Edge service, when the client is external.*</span></span> 
    
<span data-ttu-id="bf561-133">자동 검색 서비스는 항상 서비스 위치에 대한 기본 방법인 선호되는 방식이고 다른 방법은 폴백 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-133">The Autodiscover service is always favored as that's the preferred method for service location, and the others are fallback methods.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bf561-134">SRV 레코드를 만들 때 DNS SRV 레코드가 만들어지고 있는 동일한 도메인의 DNS A(및 IPv6 주소 지정을 사용하는 경우 AAAA)를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-134">When you're creating SRV records, it's important to remember that they need to point to a DNS A (and AAAA if you're using IPv6 addressing) in the same domain in which the DNS SRV record's being created.</span></span> <span data-ttu-id="bf561-135">예를 들어 SRV 레코드가 SRV 레코드에 있는 contoso.com A(및 AAAA) 레코드는 SRV 레코드에 있을 수 fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="bf561-135">For example, if they SRV record's in contoso.com, the A (and AAAA) record it points to can't be in fabrikam.com.</span></span> 
  
<span data-ttu-id="bf561-136">원하는 경우 서비스를 수동으로 검색할 수 있도록 모바일 장치를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-136">If you're inclined to do it, you can set your mobile device up for manual discovery of services.</span></span> <span data-ttu-id="bf561-137">이 경우 각 사용자는 다음과 같이 프로토콜 및 경로를 포함하여 전체 내부 및 외부 자동iscover 서비스 URIS를 사용하여 모바일 장치 설정을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-137">If that's what you're looking to do, each user needs to configure their mobile device settings with the full internal and external Autodiscover service URIs, including the protocol and path, as follows:</span></span>
  
- <span data-ttu-id="bf561-138">외부 액세스의 경우: \<ExtPoolFQDN\> https:// /Autodiscover/autodiscoverservice.svc/Root</span><span class="sxs-lookup"><span data-stu-id="bf561-138">For external access: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root</span></span>
    
- <span data-ttu-id="bf561-139">내부 액세스: https:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.svc/Root</span><span class="sxs-lookup"><span data-stu-id="bf561-139">For internal access: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root</span></span>
    
<span data-ttu-id="bf561-140">수동 검색이 아니라 자동 검색을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-140">We do recommend you use automatic discovery as opposed to manual discovery.</span></span> <span data-ttu-id="bf561-141">그러나 일부 문제 해결 또는 테스트를 수행하고 있는 경우 수동 설정이 매우 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-141">But if you're doing some troubleshooting or testing, manual settings can be very helpful.</span></span>
  
## <a name="split-brain-dns"></a><span data-ttu-id="bf561-142">분할 DNS</span><span class="sxs-lookup"><span data-stu-id="bf561-142">Split-brain DNS</span></span>
<span data-ttu-id="bf561-143"><a name="SplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="bf561-143"><a name="SplitBrainDNS"> </a></span></span>

<span data-ttu-id="bf561-144">두 개의 DNS 영역이 동일한 네임스페이스를 사용하는 DNS 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-144">This is a DNS configuration where you have two DNS zones with the same namespace.</span></span> <span data-ttu-id="bf561-145">첫 번째 DNS 영역은 내부 요청을 처리하고 두 번째 DNS 영역은 외부 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-145">The first DNS zone handles internal requests, while the second DNS zone handles external requests.</span></span>
  
<span data-ttu-id="bf561-146">회사에서 이 작업을 하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="bf561-146">Why would a company do this?</span></span> <span data-ttu-id="bf561-147">내부 및 외부적으로 동일한 네임스페이스를 사용해야 하는 요구 사항이 있을 수 있지만, 이로 인해 많은 DNS SRV 및 A 레코드가 한 영역이나 다른 영역에서 고유하게 될 수 있으며 중복된 경우 이러한 레코드와 연결된 IP 주소는 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-147">They may have a requirement to use the same namespace internally and externally, but of course this will lead to many DNS SRV and A records being unique to one zone or another, and where there is duplication, the IP addresses associated with these records would be unique.</span></span>
  
<span data-ttu-id="bf561-148">이 경우 몇 가지 과제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-148">This presents some challenges.</span></span> <span data-ttu-id="bf561-149">가장 중요한 점은 이동성에 대해 분할 DNS가 **지원되지 않는다는** 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-149">The most important is that split-brain DNS is **not supported** for Mobility.</span></span> <span data-ttu-id="bf561-150">이는 LyncDiscover 및 LyncDiscoverInternal DNS 레코드(외부 DNS 서버에 LyncDiscover를 정의해야 하는 반면 LyncDiscoverInternal은 내부 DNS 서버에 정의해야 하기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-150">This is because of the LyncDiscover and LyncDiscoverInternal DNS records (LyncDiscover has to be defined on you external DNS server, while LyncDiscoverInternal has to be defined on your internal DNS server).</span></span>
  
<span data-ttu-id="bf561-151">여기서는 내부 및 외부 영역의 DNS 레코드를 나열하지만 에지 서버 환경 요구 사항 섹션에서 자세한 예를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-151">We'll list the DNS records for the internal and external zones here, but you can find detailed examples on the Edge Server environmental requirements section.</span></span>
  
### <a name="internal-dns"></a><span data-ttu-id="bf561-152">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="bf561-152">Internal DNS</span></span>

- <span data-ttu-id="bf561-153">예를 들어 권한이 있는 contoso.com 호출된 DNS 영역이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-153">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="bf561-154">이 내부 contoso.com 포함:</span><span class="sxs-lookup"><span data-stu-id="bf561-154">This internal contoso.com contains:</span></span>
    
  - <span data-ttu-id="bf561-155">프런트 엔드 풀, Director 풀 또는 Director 풀 이름 및 조직의 네트워크에서 비즈니스용 Skype 서버를 실행하는 모든 내부 서버에 대한 DNS A 및 AAAA(IPv6 주소 지정을 사용하는 경우) 레코드</span><span class="sxs-lookup"><span data-stu-id="bf561-155">DNS A and AAAA (if you're using IPv6 addressing) records for your Front End pool, Director pool or Director pool name, and all internal servers running Skype for Business Server in your organization's network.</span></span>
    
  - <span data-ttu-id="bf561-156">경계 네트워크의 각 비즈니스용 Skype 서버 에지 서버에 대한 에지 내부 인터페이스에 대한 DNS A 및 AAAA(IPv6 주소링을 사용하는 경우) 레코드</span><span class="sxs-lookup"><span data-stu-id="bf561-156">DNS A and AAAA (if you're using IPv6 addressing) records for your Edge internal interface for each Skype for Business Server Edge Server in your perimeter network.</span></span>
    
  - <span data-ttu-id="bf561-157">경계 네트워크의 각 역방향 프록시 서버(역방향 프록시 관리에 선택 사항)의 내부 인터페이스에 대한 DNS  A 및 AAAA(IPv6 주소링을 사용하는 경우) 레코드</span><span class="sxs-lookup"><span data-stu-id="bf561-157">DNS A and AAAA (if you're using IPv6 addressing) records for the internal interface of each reverse proxy server in your perimeter network (which is **optional** for management of a reverse proxy).</span></span>
    
  - <span data-ttu-id="bf561-158">DNS A 및 AAAA(IPv6 주소 사용 시) 및 내부 비즈니스용 Skype 서버 클라이언트 자동 구성에 대한 SRV 레코드(선택 **사항).**</span><span class="sxs-lookup"><span data-stu-id="bf561-158">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for internal Skype for Business Server client autoconfiguration (which is **optional** ).</span></span>
    
  - <span data-ttu-id="bf561-159">DNS A 및 AAAA(IPv6 주소 사용 시) 또는 CNAME 레코드를 사용하여 비즈니스용 Skype  서버 웹 서비스(선택 사항)를 자동으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-159">DNS A and AAAA (if you're using IPv6 addressing) or CNAME records for automatic discovery of Skype for Business Server Web Services (which is **optional** ).</span></span>
    
- <span data-ttu-id="bf561-160">경계 네트워크의 모든 비즈니스용 Skype 서버 내부 에지 인터페이스는 쿼리를 확인할 때 이 내부 DNS contoso.com.</span><span class="sxs-lookup"><span data-stu-id="bf561-160">All your Skype for Business Server internal Edge interfaces in your perimeter network use this internal DNS zone for resolving queries to contoso.com.</span></span>
    
- <span data-ttu-id="bf561-161">비즈니스용 Skype 서버를 실행하는 모든 서버 및 회사 네트워크에서 비즈니스용 Skype 서버를 실행하는 클라이언트는 쿼리를 해결하기 위해 내부 DNS 서버를 contoso.com 또는 각 에지 서버의 호스트 파일을 사용하고 다음 홉 서버에 대한 A 및 AAAA(IPv6 주소 처리를 사용하는 경우) 레코드(특히 Director 또는 Director 풀 VIP용)를 사용 , 프런트 엔드 풀 VIP 또는 Standard Edition Server)</span><span class="sxs-lookup"><span data-stu-id="bf561-161">All servers running Skype for Business Server, and clients running Skype for Business Server in the corporate network, point to internal DNS servers for resolving queries to contoso.com, or they use the Host file on each Edge Server and list A and AAAA (if you're using IPv6 addressing) records for the next hop server (specifically for the Director or Director pool VIP, Front End pool VIP, or Standard Edition server).</span></span>
    
### <a name="external-dns"></a><span data-ttu-id="bf561-162">외부 DNS</span><span class="sxs-lookup"><span data-stu-id="bf561-162">External DNS</span></span>

- <span data-ttu-id="bf561-163">예를 들어 권한이 있는 contoso.com 호출된 DNS 영역이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-163">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="bf561-164">이 외부 contoso.com 포함:</span><span class="sxs-lookup"><span data-stu-id="bf561-164">This external contoso.com contains:</span></span>
    
  - <span data-ttu-id="bf561-165">비즈니스용 Skype 서버 웹 서비스의 자동 검색을 위해 DNS A 및 AAAA(IPv6 주소 사용 시) 또는 CNAME 레코드</span><span class="sxs-lookup"><span data-stu-id="bf561-165">DNS A and AAAA (if you're using IPv6 addressing), or CNAME records, for automatic discovery of Skype for Business Server web services.</span></span> <span data-ttu-id="bf561-166">이동성에 사용하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-166">This is for use with mobility.</span></span>
    
  - <span data-ttu-id="bf561-167">경계 네트워크에서 각 비즈니스용 Skype 서버 에지 서버 또는 HLB(하드웨어 부하가 균형 조정된) VIP의 에지 외부 인터페이스에 대한 DNS A 및 AAAA(IPv6 주소를 사용하는 경우) 및 SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="bf561-167">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the Edge external interface of each Skype for Business Server Edge Server or hardware load balanced (HLB) VIP in the perimeter network.</span></span>
    
  - <span data-ttu-id="bf561-168">경계 네트워크에서 역방향 프록시 서버 또는 (역방향 프록시 서버 풀의 VIP)의 외부 인터페이스에 대한 DNS A 및 AAAA(IPv6 주소 사용 시) 및 SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="bf561-168">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the external interface of the Reverse proxy server or (VIP for a pool of Reverse proxy servers), in the perimeter network.</span></span>
    
  - <span data-ttu-id="bf561-169">DNS A 및 AAAA(IPv6 주소 사용 시) 및 비즈니스용 Skype 서버 클라이언트 자동 구성에 대한 SRV **레코드(선택 사항).**</span><span class="sxs-lookup"><span data-stu-id="bf561-169">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for Skype for Business Server client autoconfiguration ( **optional** ).</span></span>
    
## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="bf561-170">분할 DNS 없이 자동 구성</span><span class="sxs-lookup"><span data-stu-id="bf561-170">Automatic configuration without split-brain DNS</span></span>
<span data-ttu-id="bf561-171"><a name="NoSplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="bf561-171"><a name="NoSplitBrainDNS"> </a></span></span>

<span data-ttu-id="bf561-172">분할 DNS를 사용하지 않는 경우 여기에 있는 해결 방법을 사용하지 않는 한 비즈니스용 Skype를 실행하는 클라이언트의 내부 자동 구성이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-172">If you don't use split-brain DNS, internal automatic configuration of clients running Skype for Business won't work unless you're using one of the workarounds we have here.</span></span> <span data-ttu-id="bf561-173">그 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="bf561-173">Why not?</span></span> <span data-ttu-id="bf561-174">비즈니스용 Skype 서버는 자동 구성으로 지정된 프런트 엔드 풀의 도메인과 일치하도록 사용자의 SIP URI가 필요하기 때문에</span><span class="sxs-lookup"><span data-stu-id="bf561-174">Because Skype for Business Server requires the user's SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="bf561-175">이는 이전 버전의 Lync Server에서 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-175">This hasn't changed from earlier versions of Lync Server.</span></span>
  
<span data-ttu-id="bf561-176">따라서 두 개의 SIP 도메인이 사용 중이면 다음 DNS SRV 레코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-176">So, if you have two SIP domains in use, you'd need these DNS SRV records:</span></span>
  
- <span data-ttu-id="bf561-177">_sipinternaltls._tcp.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="bf561-177">_sipinternaltls._tcp.contoso.com.</span></span> <span data-ttu-id="bf561-178">86400 IN SRV 0 0 5061 pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-178">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>
    
     <span data-ttu-id="bf561-179">*사용자의 SIP 도메인이 프런트 엔드 풀(bob@contoso.com)의 도메인과 일치하기 때문에 이 레코드는 자동 구성에 대해 contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="bf561-179">*If a user signs in as bob@contoso.com, this record would work for automatic configuration, as the user's SIP domain matches the domain of the Front End pool (contoso.com).*</span></span> 
    
- <span data-ttu-id="bf561-180">_sipinternaltls._tcp.fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="bf561-180">_sipinternaltls._tcp.fabrikam.com.</span></span> <span data-ttu-id="bf561-181">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="bf561-181">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="bf561-182">*사용자가 로그인한 alice@fabrikam.com SIP 도메인이 해당 도메인의 프런트 엔드 풀과 일치하기 때문에 두 번째 도메인의 자동 구성에 대해 이 레코드가 작동하게 됩니다.*</span><span class="sxs-lookup"><span data-stu-id="bf561-182">*If a user signs in as alice@fabrikam.com, this record would work for automatic configuration of the second domain, again because the SIP domain matches the Front End pool for that domain.*</span></span> 
    
<span data-ttu-id="bf561-183">이 예제를 더 진행하기 위해 이 작업을 진행하면 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-183">To take the example further, this would not work:</span></span>
  
- <span data-ttu-id="bf561-184">_sipinternaltls._tcp.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="bf561-184">_sipinternaltls._tcp.litwareinc.com.</span></span> <span data-ttu-id="bf561-185">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="bf561-185">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="bf561-186">*SIP tim@litwareinc.com 도메인(litwareinc.com)이 풀(fabrikam.com)의 도메인과 일치하지 않는 경우 사용자 로그인은 자동 구성에 대해 작동하지 fabrikam.com.*</span><span class="sxs-lookup"><span data-stu-id="bf561-186">*A user signing in as tim@litwareinc.com won't work for automatic configuration, because his SIP domain (litwareinc.com) doesn't match the domain in the pool (fabrikam.com).*</span></span> 
    
<span data-ttu-id="bf561-187">이제 분할 DNS 없이 비즈니스용 Skype 클라이언트에 대한 자동 요구 사항이 필요한 경우 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-187">So now that we know all that, if you need automatic requirement for your Skype for Business clients without split-brain DNS, you have these options:</span></span>
  
- <span data-ttu-id="bf561-188">**그룹 정책 개체**</span><span class="sxs-lookup"><span data-stu-id="bf561-188">**Group Policy Objects**</span></span>
    
    <span data-ttu-id="bf561-189">GOS(그룹 정책 개체)를 사용하여 올바른 서버 값을 채우는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-189">You can use Group Policy Objects (GPOs) to populate the correct server values.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bf561-190">이 옵션은 자동 구성을 사용하도록 설정하지 않지만 수동 구성을 자동화합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-190">This option doesn't enable automatic configuration, but it does automate manual configuration.</span></span> <span data-ttu-id="bf561-191">이 방법을 사용하는 경우 자동 구성과 연결된 SRV 레코드는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-191">If this approach is used, the SRV records associated with automatic configuration aren't required.</span></span> 
  
- <span data-ttu-id="bf561-192">**일치하는 내부 영역**</span><span class="sxs-lookup"><span data-stu-id="bf561-192">**Matching internal zone**</span></span>
    
    <span data-ttu-id="bf561-193">내부 DNS에서 외부 DNS 영역과 일치하는 영역(예: contoso.com)을 만든 다음 자동 구성에 사용되는 비즈니스용 Skype 서버 풀에 해당하는 DNS A(및 IPv6 주소 주소를 사용하는 경우 AAAA) 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-193">You'll need to create a zone in your internal DNS that matches your external DNS zone (for example, contoso.com), and then create DNS A (and AAAA if you're using IPv6 addressing) records that correspond to the Skype for Business Server pool used for automatic configuration.</span></span>
    
    <span data-ttu-id="bf561-194">예를 들어 사용자가 pool01.contoso.net 있지만 비즈니스용 Skype에 bob@contoso.com 로그인하는 경우 contoso.com라는 내부 DNS 영역이 만들어지고 내부 DNS 영역 내부에 IPv6 주소가 사용 중이면 AAAA를 만들어야 pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="bf561-194">For example, if you have a user homed on pool01.contoso.net, but signs into Skype for Business as bob@contoso.com, create an internal DNS zone called contoso.com, and inside it you need to create a DNS A (and AAAA if IPv6 addressing's being used) record for pool01.contoso.com.</span></span>
    
- <span data-ttu-id="bf561-195">**핀 포인트 내부 영역**</span><span class="sxs-lookup"><span data-stu-id="bf561-195">**Pin-point internal zone**</span></span>
    
    <span data-ttu-id="bf561-196">내부 DNS에서 전체 영역 만들기가 옵션에 해당하지 않는 경우 자동 구성에 필요한 SRV 레코드에 해당하는 핀 포인트(전용) 영역이 만들어지며 이러한 영역은 dnscmd.exe.</span><span class="sxs-lookup"><span data-stu-id="bf561-196">If creating an entire zone in your internal DNS isn't an option for you, you can create pin-point (dedicated) zones that correspond to the SRV records required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="bf561-197">Dnscmd.exe 사용자 인터페이스가 핀 포인트 영역 만들기를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-197">Dnscmd.exe is required because the DNS user interface won't support the creation of pin-point zones.</span></span>
    
    <span data-ttu-id="bf561-198">예를 들어 SIP 도메인이 contoso.com 프런트 엔드 서버가 두 개 포함된 pool01이라는 프런트 엔드 풀이 있는 경우 내부 DNS에 다음과 같은 핀 포인트 영역과 A 레코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-198">For example, if your SIP domain is contoso.com, and you have a Front End pool called pool01 that contains two Front End Servers, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    <span data-ttu-id="bf561-199">환경에 두 번째 SIP 도메인이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-199">You may have a second SIP domain in your environment.</span></span> <span data-ttu-id="bf561-200">이 경우 내부 DNS에 다음과 같은 핀 포인트 영역 및 A 레코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-200">In that case, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> <span data-ttu-id="bf561-201">프런트 엔드 풀 FQDN이 두 번 나타나지만 서로 다른 IP 주소가 두 개 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-201">You'll see the Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="bf561-202">이는 DNS 부하 분산이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-202">That's because DNS load balancing is used.</span></span> <span data-ttu-id="bf561-203">HLB를 사용하는 경우 단일 프런트 엔드 풀 항목만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-203">If HLB is used, there'd only be a single Front End pool entry.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bf561-204">또한 프런트 엔드 풀 FQDN 값은 contoso.com 및 fabrikam.com 변경되지만 IP 주소는 동일하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-204">Also, the Front End pool FQDN values change between the contoso.com and fabrikam.com examples, but the IP addresses remain the same.</span></span> <span data-ttu-id="bf561-205">이는 두 SIP 도메인에서 로그인하는 사용자가 자동 구성을 위해 동일한 프런트 엔드 풀을 사용하게 있기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-205">That's because users who're signing in from either SIP domain will be using the same Front End pool for automatic configuration.</span></span> 
  
## <a name="dns-disaster-recovery"></a><span data-ttu-id="bf561-206">DNS 재해 복구</span><span class="sxs-lookup"><span data-stu-id="bf561-206">DNS disaster recovery</span></span>
<span data-ttu-id="bf561-207"><a name="DNSDR"> </a></span><span class="sxs-lookup"><span data-stu-id="bf561-207"><a name="DNSDR"> </a></span></span>

<span data-ttu-id="bf561-208">비즈니스용 Skype 서버 웹 트래픽을 DR(재해 복구) 및 장애 조치 사이트로 리디렉션하도록 DNS를 구성하려면 GeoDNS를 지원하는 DNS 공급자를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-208">To configure DNS to redirect Skype for Business Server web traffic to your disaster recover (DR) and failover sites, you need to use a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="bf561-209">재해 복구를 지원하기 위해 DNS 레코드를 설정하여 하나의 전체 프런트 엔드 풀이 다운된 경우에도 웹 서비스를 사용하는 기능이 계속 진행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-209">You can set up your DNS records to support disaster recover, so that features that use web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="bf561-210">이 DR 기능은 자동Iscover, Meet 및 전화 접속 단순 URL을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-210">This DR feature supports the Autodiscover, Meet and Dial-in simple URLs.</span></span>
  
<span data-ttu-id="bf561-211">GeoDNS 공급자에서 웹 서비스의 내부 및 외부 확인을 위해 추가 DNS 호스트 A(IPv6을 사용하는 경우 AAAA) 레코드를 정의하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-211">You define and configure additional DNS host A (AAAA if using IPv6) records for internal and external resolution of web services at your GeoDNS provider.</span></span> <span data-ttu-id="bf561-212">다음 세부 정보에서는 페어링된 풀, 지리적으로 분산된 풀 및  공급자가 지원하는 GeoDNS에 라운드 로빈 **DNS가** 있는 경우 또는 Pool1을 기본으로 사용하도록 구성되어 있으며 통신 손실 또는 정전이 발생하면 Pool2로 장애 조치(fail over)된다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-212">The following details assume paired pools, geographically dispersed, and that the GeoDNS supported by your provider **either** has round-robin DNS **or** is configured to use Pool1 as primary and fails over to Pool2 in the event of any communications loss or power failure.</span></span>
  
<span data-ttu-id="bf561-213">이 표의 모든 DNS 레코드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-213">All the DNS records in this table are examples.</span></span>
  
|<span data-ttu-id="bf561-214">**GeoDNS 레코드**</span><span class="sxs-lookup"><span data-stu-id="bf561-214">**GeoDNS record**</span></span>|<span data-ttu-id="bf561-215">**풀 레코드**</span><span class="sxs-lookup"><span data-stu-id="bf561-215">**Pool records**</span></span>|<span data-ttu-id="bf561-216">**CNAME 레코드**</span><span class="sxs-lookup"><span data-stu-id="bf561-216">**CNAME records**</span></span>|<span data-ttu-id="bf561-217">**DNS 설정(하나의 옵션 선택)**</span><span class="sxs-lookup"><span data-stu-id="bf561-217">**DNS settings (select one option)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bf561-218">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-218">Meet-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-219">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-219">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="bf561-220">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-220">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-221">Meet.contoso.com 별칭을 Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-221">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="bf561-222">Meet.contoso.com 별칭을 Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-222">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-223">풀 간 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="bf561-223">Round Robin between pools</span></span>  <br/> <span data-ttu-id="bf561-224">**또는**</span><span class="sxs-lookup"><span data-stu-id="bf561-224">**OR**</span></span> <br/> <span data-ttu-id="bf561-225">기본 사용, 오류가 있는 경우 보조에 연결</span><span class="sxs-lookup"><span data-stu-id="bf561-225">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="bf561-226">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-226">Meet-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-227">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-227">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="bf561-228">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-228">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-229">Meet.contoso.com 별칭을 Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-229">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="bf561-230">Meet.contoso.com 별칭을 Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-230">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-231">풀 간 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="bf561-231">Round Robin between pools</span></span>  <br/> <span data-ttu-id="bf561-232">**또는**</span><span class="sxs-lookup"><span data-stu-id="bf561-232">**OR**</span></span> <br/> <span data-ttu-id="bf561-233">기본 사용, 오류가 있는 경우 보조에 연결</span><span class="sxs-lookup"><span data-stu-id="bf561-233">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="bf561-234">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-234">Dialin-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-235">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-235">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="bf561-236">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-236">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-237">Dialin.contoso.com 별칭을 Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-237">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="bf561-238">Dialin.contoso.com 별칭을 Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-238">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-239">풀 간 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="bf561-239">Round Robin between pools</span></span>  <br/> <span data-ttu-id="bf561-240">**또는**</span><span class="sxs-lookup"><span data-stu-id="bf561-240">**OR**</span></span> <br/> <span data-ttu-id="bf561-241">기본 사용, 오류가 있는 경우 보조에 연결</span><span class="sxs-lookup"><span data-stu-id="bf561-241">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="bf561-242">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-242">Dialin-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-243">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-243">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="bf561-244">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-244">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-245">Dialin.contoso.com 별칭을 Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-245">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="bf561-246">Dialin.contoso.com 별칭을 Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-246">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-247">풀 간 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="bf561-247">Round Robin between pools</span></span>  <br/> <span data-ttu-id="bf561-248">**또는**</span><span class="sxs-lookup"><span data-stu-id="bf561-248">**OR**</span></span> <br/> <span data-ttu-id="bf561-249">기본 사용, 오류가 있는 경우 보조에 연결</span><span class="sxs-lookup"><span data-stu-id="bf561-249">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="bf561-250">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-250">Lyncdiscoverint-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-251">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-251">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="bf561-252">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-252">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-253">Lyncdiscoverinternal.contoso.com 별칭을 Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-253">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="bf561-254">Lyncdiscoverinternal.contoso.com 별칭을 Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-254">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-255">풀 간 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="bf561-255">Round Robin between pools</span></span>  <br/> <span data-ttu-id="bf561-256">**또는**</span><span class="sxs-lookup"><span data-stu-id="bf561-256">**OR**</span></span> <br/> <span data-ttu-id="bf561-257">기본 사용, 오류가 있는 경우 보조에 연결</span><span class="sxs-lookup"><span data-stu-id="bf561-257">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="bf561-258">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-258">Lyncdiscover-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-259">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-259">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="bf561-260">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-260">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-261">Lyncdiscover.contoso.com 별칭을 Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-261">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="bf561-262">Lyncdiscover.contoso.com 별칭을 Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-262">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-263">풀 간 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="bf561-263">Round Robin between pools</span></span>  <br/> <span data-ttu-id="bf561-264">**또는**</span><span class="sxs-lookup"><span data-stu-id="bf561-264">**OR**</span></span> <br/> <span data-ttu-id="bf561-265">기본 사용, 오류가 있는 경우 보조에 연결</span><span class="sxs-lookup"><span data-stu-id="bf561-265">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="bf561-266">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-266">Scheduler-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-267">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-267">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="bf561-268">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-268">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-269">Scheduler.contoso.com 별칭을 Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-269">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="bf561-270">Scheduler.contoso.com 별칭을 Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-270">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-271">풀 간 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="bf561-271">Round Robin between pools</span></span>  <br/> <span data-ttu-id="bf561-272">**또는**</span><span class="sxs-lookup"><span data-stu-id="bf561-272">**OR**</span></span> <br/> <span data-ttu-id="bf561-273">기본 사용, 오류가 있는 경우 보조에 연결</span><span class="sxs-lookup"><span data-stu-id="bf561-273">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="bf561-274">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-274">Scheduler-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-275">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-275">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="bf561-276">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-276">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-277">Scheduler.contoso.com 별칭을 Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-277">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="bf561-278">Scheduler.contoso.com 별칭을 Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-278">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-279">풀 간 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="bf561-279">Round Robin between pools</span></span>  <br/> <span data-ttu-id="bf561-280">**또는**</span><span class="sxs-lookup"><span data-stu-id="bf561-280">**OR**</span></span> <br/> <span data-ttu-id="bf561-281">기본 사용, 오류가 있는 경우 보조에 연결</span><span class="sxs-lookup"><span data-stu-id="bf561-281">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
   
## <a name="dns-load-balancing"></a><span data-ttu-id="bf561-282">DNS load balancing(DNS 부하 분산)</span><span class="sxs-lookup"><span data-stu-id="bf561-282">DNS load balancing</span></span>
<span data-ttu-id="bf561-283"><a name="DNSLB"> </a></span><span class="sxs-lookup"><span data-stu-id="bf561-283"><a name="DNSLB"> </a></span></span>

<span data-ttu-id="bf561-284">DNS 부하 분산은 일반적으로 응용 프로그램 수준에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-284">DNS load balancing is usually implemented at the application level.</span></span> <span data-ttu-id="bf561-285">응용 프로그램(예: 비즈니스용 Skype를 실행하는 클라이언트)은 풀 FQDN에 대한 DNS A 및 AAAA(IPv6 주소가 사용되는 경우) 레코드 쿼리에서 반환된 IP 주소 중 하나에 연결하여 풀의 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-285">The application (for example, a client running Skype for Business), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool FQDN.</span></span>
  
<span data-ttu-id="bf561-286">예를 들어 이름이 pool01.contoso.com 풀에 프런트 엔드 서버가 3대 있는 경우 다음과 같은 문제가 발생하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-286">For example, if there are three Front End Servers in a pool named pool01.contoso.com, the following would happen:</span></span>
  
- <span data-ttu-id="bf561-287">비즈니스용 Skype를 실행하는 클라이언트는 DNS에서 pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="bf561-287">Clients running Skype for Business query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="bf561-288">이 쿼리는 세 개의 IP 주소를 반환하고 다음과 같이 캐시합니다(순서대로).</span><span class="sxs-lookup"><span data-stu-id="bf561-288">The query returns three IP addresses and caches them as follows (in some order):</span></span>
    
   |||
   |:-----|:-----|
   |<span data-ttu-id="bf561-289">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-289">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-290">192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="bf561-290">192.168.10.90</span></span>  <br/> |
   |<span data-ttu-id="bf561-291">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-291">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-292">192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="bf561-292">192.168.10.91</span></span>  <br/> |
   |<span data-ttu-id="bf561-293">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bf561-293">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="bf561-294">192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="bf561-294">192.168.10.92</span></span>  <br/> |
   
- <span data-ttu-id="bf561-295">클라이언트는 IP 주소 중 하나에 대한 TCP 연결을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-295">The client tries to establish a TCP connection to one of the IP addresses.</span></span> <span data-ttu-id="bf561-296">실패하면 해당 목록에서 캐시된 다음 IP 주소를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-296">If that fails, it'll try the next IP address it's cached from that list.</span></span>
    
- <span data-ttu-id="bf561-297">TCP 연결이 성공하면 클라이언트는 TLS를 협상하여 TLS를 사용하여 TLS의 기본 등록 기관에 pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="bf561-297">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>
    
- <span data-ttu-id="bf561-298">클라이언트가 성공적으로 연결되지 않은 캐시된 항목을 모두 입력하면 사용자는 현재 비즈니스용 Skype 서버를 실행하는 서버를 사용할 수 없음을 알림으로 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-298">If the client tries all cached entries without a successful connection, the user receives a notification that no servers running Skype for Business Server are available at the moment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="bf561-299">DNS 기반 부하 분산은 DNS RR(DNS 라운드 로빈)와는 다르며, 일반적으로 DNS를 사용하여 풀의 서버에 대해 서로 다른 IP 주소 순서를 제공하여 부하 분산을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-299">DNS-based load balancing is different from DNS round robin (DNS RR), which typically refers to load balancing by relying on DNS to give a different order of IP addresses for the servers in your pool.</span></span> <span data-ttu-id="bf561-300">일반적으로 DNS RR은 부하 분산을 사용하도록 설정하지만 장애 조치(failover)를 사용하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-300">Typically, DNS RR enables load distribution, but it won't allow you to enable failover.</span></span> <span data-ttu-id="bf561-301">예를 들어 DNS A(또는 IPv6 시나리오의 AAAA) 쿼리에서 반환된 IP 주소 하나에 대한 연결이 실패하면 해당 연결이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-301">For example, if the connection to the one IP address returned by your DNS A (or AAAA in an IPv6 scenario) query fails, that connection will fail.</span></span> <span data-ttu-id="bf561-302">이렇게 하면 DNS 기반 부하 분산보다 DNS RR의 안정성이 낮아질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-302">That makes DNS RR less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="bf561-303">필요한 경우 DNS 기반 부하 분산과 함께 DNS RR을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-303">You can still use DNS RR in conjunction with DNS-based load balancing if you need to do that.</span></span> 
  
<span data-ttu-id="bf561-304">DNS 부하 분산을 사용하여 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-304">You use DNS load balancing to:</span></span>
  
- <span data-ttu-id="bf561-305">서버 대 서버 SIP를 에지 서버로 부하를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-305">Load balance server-to-server SIP to the Edge Servers.</span></span>
    
- <span data-ttu-id="bf561-306">회의, 응답 그룹 및 통화 파킹된 통화 자동 전화 교환 UCAS(통합 통신 응용 프로그램 서비스) 응용 프로그램의 부하를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-306">Load balance Unified Communication Application Services (UCAS) applications, such as Conferencing Auto Attendant, Response Group, and Call Park.</span></span>
    
- <span data-ttu-id="bf561-307">UCAS 응용 프로그램에 대한 새 연결을 방지합니다(드레인라고도 합니다).</span><span class="sxs-lookup"><span data-stu-id="bf561-307">Prevent new connections to UCAS applications (also known as draining).</span></span>
    
- <span data-ttu-id="bf561-308">클라이언트와 에지 서버 간의 모든 클라이언트-서버 트래픽 부하를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-308">Load balance all client-to-server traffic between clients and Edge Servers.</span></span>
    
<span data-ttu-id="bf561-309">다음에는 DNS 부하 분산을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-309">You can't use DNS load balancing for:</span></span>
  
- <span data-ttu-id="bf561-310">프런트 엔드 서버 또는 Director에 대한 클라이언트-서버 웹 트래픽</span><span class="sxs-lookup"><span data-stu-id="bf561-310">Client-to-server web traffic to your Front End Servers or a Director.</span></span>
    
<span data-ttu-id="bf561-311">쿼리에서 DNS 레코드를 음소거할 때 DNS SRV 레코드가 선택되는 방식에 대해 좀 더 깊이 있게 확인하려면 액세스 에지 서비스에서 항상 가장 낮은 숫자 우선 순위의 레코드를 선택하고, 동점 차단이 필요한 경우 가장 높은 숫자 가중치가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-311">To go a little more in-depth on how a DNS SRV record's selected when mutiple DNS records are returned by a query, the Access Edge service always picks the record with the lowest numeric priority and, if a tie-breaker is needed, the highest numeric weight.</span></span> <span data-ttu-id="bf561-312">이는 Internet [Engineering Task Force 설명서와 일치합니다.](https://www.ietf.org/rfc/rfc2782.txt)</span><span class="sxs-lookup"><span data-stu-id="bf561-312">This is consistent with [Internet Engineering Task Force documentation](https://www.ietf.org/rfc/rfc2782.txt).</span></span>
  
<span data-ttu-id="bf561-313">예를 들어 첫 번째 DNS SRV 레코드의 가중치가 20과 우선 순위 40인 경우 두 번째 DNS SRV 레코드의 가중치 10과 우선 순위 50이면 우선 순위가 40이기 때문에 첫 번째 레코드가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-313">So, for example, if your first DNS SRV record has a weight of 20 and a priority of 40, and your second DNS SRV record has a weight of 10 and a priority of 50, the first record's going to be chosen because it has the lower priority of 40.</span></span> <span data-ttu-id="bf561-314">우선 순위가 항상 우선하며 클라이언트가 먼저 대상으로 지정하는 호스트입니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-314">Priority always goes first, and that's the host that a client will target first.</span></span> <span data-ttu-id="bf561-315">우선 순위가 같은 대상이 두 개 있는 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="bf561-315">What if there are two targets with the same priority?</span></span> 
  
<span data-ttu-id="bf561-316">이 경우 가중치가 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-316">In that case, weight comes into consideration.</span></span> <span data-ttu-id="bf561-317">이 경우 더 큰 가중치가 선택될 확률이 높아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-317">Larger weights should be given a high probability, in this circumstance, of being selected.</span></span> <span data-ttu-id="bf561-318">DNS 관리자는 서버 선택이 없는 경우 가중치 0을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-318">DNS administrators should use weight 0 when there isn't any server selection to do.</span></span> <span data-ttu-id="bf561-319">가중치가 0보다 큰 레코드가 있는 경우 가중치 0의 레코드는 선택될 가능성이 매우 적습니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-319">In the presence of records containing weights greater than 0, records with weight 0 have a very small chance of bring selected.</span></span>
  
<span data-ttu-id="bf561-320">그렇다면 반환된 우선 순위와 가중치가 같은 여러 DNS SRV 레코드가 반환될 경우 어떻게 될까요?</span><span class="sxs-lookup"><span data-stu-id="bf561-320">So, then, what happens if multiple DNS SRV records with equal priority and weight as returned?</span></span> <span data-ttu-id="bf561-321">이 경우 액세스 에지 서비스는 DNS 서버에서 먼저 SRV 레코드를 선택하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf561-321">In this situation the Access Edge service will choose the SRV record that it got from the DNS server first.</span></span>
  

