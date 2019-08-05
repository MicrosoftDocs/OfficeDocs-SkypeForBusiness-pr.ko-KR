---
title: 비즈니스용 Skype 서버에 대 한 고급 Edge Server DNS 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: '요약: 비즈니스용 Skype 서버 배포 옵션에 대 한 시나리오를 검토 합니다. 이 항목은 단일 서버를 사용 하거나 DNS 또는 HLB 서버 풀을 사용할 수 있도록 하는 데 도움이 될 것입니다.'
ms.openlocfilehash: 497126188b830a61804bedb44c5e50eedec11dcb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187824"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a><span data-ttu-id="e8baa-104">비즈니스용 Skype 서버에 대 한 고급 Edge Server DNS 계획</span><span class="sxs-lookup"><span data-stu-id="e8baa-104">Advanced Edge Server DNS planning for Skype for Business Server</span></span>
 
<span data-ttu-id="e8baa-105">**요약:** 비즈니스용 Skype 서버 배포 옵션에 대 한 시나리오를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-105">**Summary:** Review scenarios for Skype for Business Server deployment options.</span></span> <span data-ttu-id="e8baa-106">이 항목은 단일 서버를 사용 하거나 DNS 또는 HLB 서버 풀을 사용할 수 있도록 하는 데 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-106">Whether you want a single server or prefer a server pool with DNS or HLB, this topic should help.</span></span>
  
<span data-ttu-id="e8baa-107">비즈니스용 Skype Server에 대 한 DNS (Domain Name System) 계획과 관련 된 경우에는 다양 한 요인에 따라 결정을 내릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-107">When it comes to Domain Name System (DNS) planning for Skype for Business Server, there are a lot of factors that may play into your decision.</span></span> <span data-ttu-id="e8baa-108">조직의 도메인 구조가 이미 존재 하는 경우에는 어떻게 진행할 지 검토 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-108">If your organization's domain structure's already in place, this may be a matter of reviewing how you're going to proceed.</span></span> <span data-ttu-id="e8baa-109">시작 하는 항목은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-109">We'll begin with the topics found below:</span></span>
  
- [<span data-ttu-id="e8baa-110">서비스를 찾는 비즈니스용 Skype 클라이언트의 연습</span><span class="sxs-lookup"><span data-stu-id="e8baa-110">Walkthrough of Skype for Business clients locating services</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [<span data-ttu-id="e8baa-111">분할-두뇌 DNS</span><span class="sxs-lookup"><span data-stu-id="e8baa-111">Split-brain DNS</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [<span data-ttu-id="e8baa-112">분할 하는 DNS 없이 자동 구성</span><span class="sxs-lookup"><span data-stu-id="e8baa-112">Automatic configuration without split-brain DNS</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [<span data-ttu-id="e8baa-113">DNS 재해 복구</span><span class="sxs-lookup"><span data-stu-id="e8baa-113">DNS disaster recovery</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [<span data-ttu-id="e8baa-114">DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="e8baa-114">DNS load balancing</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a><span data-ttu-id="e8baa-115">서비스를 찾는 비즈니스용 Skype 클라이언트의 연습</span><span class="sxs-lookup"><span data-stu-id="e8baa-115">Walkthrough of Skype for Business clients locating services</span></span>
<span data-ttu-id="e8baa-116"><a name="WalkthroughOfSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="e8baa-116"></span></span>

<span data-ttu-id="e8baa-117">비즈니스용 skype 클라이언트는 비즈니스용 Skype 서버에서 서비스를 찾고 액세스 하는 방법에 대 한 이전 버전의 Lync 클라이언트와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-117">Skype for Business clients are similar to previous versions of Lync clients in how they find and access services in Skype for Business Server.</span></span> <span data-ttu-id="e8baa-118">이 섹션에서는 서버 위치 프로세스에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-118">This section details the server location process.</span></span>
  
1. <span data-ttu-id="e8baa-119">lyncdiscoverinternal. \<도메인\></span><span class="sxs-lookup"><span data-stu-id="e8baa-119">lyncdiscoverinternal.\<domain\></span></span>
    
     <span data-ttu-id="e8baa-120">*내부 웹 서비스의 자동 검색 서비스에 대 한 호스트 레코드입니다.*</span><span class="sxs-lookup"><span data-stu-id="e8baa-120">*This is an A host record for the Autodiscover service on the internal web services.*</span></span> 
    
2. <span data-ttu-id="e8baa-121">lyncdiscover. \<도메인\></span><span class="sxs-lookup"><span data-stu-id="e8baa-121">lyncdiscover.\<domain\></span></span>
    
     <span data-ttu-id="e8baa-122">*외부 웹 서비스의 자동 검색 서비스에 대 한 호스트 레코드입니다.*</span><span class="sxs-lookup"><span data-stu-id="e8baa-122">*This is an A host record for the Autodiscover service on the external web services.*</span></span> 
    
3. <span data-ttu-id="e8baa-123">_sipinternaltls._tcp. \<도메인\></span><span class="sxs-lookup"><span data-stu-id="e8baa-123">_sipinternaltls._tcp.\<domain\></span></span>
    
     <span data-ttu-id="e8baa-124">*내부 TLS 연결에 대 한 SRV 레코드입니다.*</span><span class="sxs-lookup"><span data-stu-id="e8baa-124">*This is a SRV record for internal TLS connections.*</span></span> 
    
4. <span data-ttu-id="e8baa-125">_sip. \<도메인\></span><span class="sxs-lookup"><span data-stu-id="e8baa-125">_sip._tls.\<domain\></span></span>
    
     <span data-ttu-id="e8baa-126">*외부 TLS 연결에 대 한 SRV 레코드입니다.*</span><span class="sxs-lookup"><span data-stu-id="e8baa-126">*This is a SRV record for external TLS connections.*</span></span> 
    
5. <span data-ttu-id="e8baa-127">sipinternal. \<도메인\></span><span class="sxs-lookup"><span data-stu-id="e8baa-127">sipinternal.\<domain\></span></span>
    
     <span data-ttu-id="e8baa-128">*이는 내부 네트워크 에서만 확인할 수 있는 프런트 엔드 풀 또는 디렉터에 대 한 호스트 레코드입니다.*</span><span class="sxs-lookup"><span data-stu-id="e8baa-128">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
6. <span data-ttu-id="e8baa-129">sip. \<도메인\></span><span class="sxs-lookup"><span data-stu-id="e8baa-129">sip.\<domain\></span></span>
    
     <span data-ttu-id="e8baa-130">*이는 내부 네트워크 에서만 확인할 수 있는 프런트 엔드 풀 또는 디렉터에 대 한 호스트 레코드입니다.*</span><span class="sxs-lookup"><span data-stu-id="e8baa-130">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
7. <span data-ttu-id="e8baa-131">sipexternal. \<도메인\></span><span class="sxs-lookup"><span data-stu-id="e8baa-131">sipexternal.\<domain\></span></span>
    
     <span data-ttu-id="e8baa-132">*클라이언트가 외부에 있는 경우 액세스에 지 서비스에 대 한 호스트 레코드입니다.*</span><span class="sxs-lookup"><span data-stu-id="e8baa-132">*This is an A host record for the Access Edge service, when the client is external.*</span></span> 
    
<span data-ttu-id="e8baa-133">자동 검색 서비스는 서비스 위치에 대 한 기본 설정 방식으로 항상 선호 되며 나머지는 fallback 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-133">The Autodiscover service is always favored as that's the preferred method for service location, and the others are fallback methods.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e8baa-134">SRV 레코드를 만드는 경우 DNS SRV 레코드를 만들 때 사용 하는 도메인에서 DNS A (IPv6 주소 지정을 사용 하는 경우 AAAA)를 가리켜야 한다는 것을 기억해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-134">When you're creating SRV records, it's important to remember that they need to point to a DNS A (and AAAA if you're using IPv6 addressing) in the same domain in which the DNS SRV record's being created.</span></span> <span data-ttu-id="e8baa-135">예를 들어 contoso.com에 해당 하는 레코드가 있는 경우에는 해당 레코드를 가리키는 A (및 AAAA) 레코드가 fabrikam.com에 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-135">For example, if they SRV record's in contoso.com, the A (and AAAA) record it points to can't be in fabrikam.com.</span></span> 
  
<span data-ttu-id="e8baa-136">이 작업을 inclined 경우 서비스를 수동으로 검색 하도록 모바일 장치를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-136">If you're inclined to do it, you can set your mobile device up for manual discovery of services.</span></span> <span data-ttu-id="e8baa-137">원하는 작업을 수행 하는 경우 각 사용자는 다음과 같이 프로토콜 및 경로를 포함 하 여 전체 내부 및 외부 자동 검색 서비스 Uri를 사용 하 여 모바일 장치 설정을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-137">If that's what you're looking to do, each user needs to configure their mobile device settings with the full internal and external Autodiscover service URIs, including the protocol and path, as follows:</span></span>
  
- <span data-ttu-id="e8baa-138">외부 액세스: https://\<extpoolfqdn/Autodiscover/autodiscoverservice.svc/Root\></span><span class="sxs-lookup"><span data-stu-id="e8baa-138">For external access: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root</span></span>
    
- <span data-ttu-id="e8baa-139">내부 액세스: https://\<intpoolfqdn/AutoDiscover/AutoDiscover.svc/Root\></span><span class="sxs-lookup"><span data-stu-id="e8baa-139">For internal access: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root</span></span>
    
<span data-ttu-id="e8baa-140">수동 검색 대신 자동 검색을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-140">We do recommend you use automatic discovery as opposed to manual discovery.</span></span> <span data-ttu-id="e8baa-141">그러나 일부 문제 해결 이나 테스트를 수행 하는 경우에는 수동 설정이 매우 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-141">But if you're doing some troubleshooting or testing, manual settings can be very helpful.</span></span>
  
## <a name="split-brain-dns"></a><span data-ttu-id="e8baa-142">분할-두뇌 DNS</span><span class="sxs-lookup"><span data-stu-id="e8baa-142">Split-brain DNS</span></span>
<span data-ttu-id="e8baa-143"><a name="SplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="e8baa-143"></span></span>

<span data-ttu-id="e8baa-144">이는 같은 네임 스페이스를 사용 하는 두 개의 DNS 영역이 있는 DNS 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-144">This is a DNS configuration where you have two DNS zones with the same namespace.</span></span> <span data-ttu-id="e8baa-145">첫 번째 DNS 영역은 내부 요청을 처리 하 고 두 번째 DNS 영역은 외부 요청을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-145">The first DNS zone handles internal requests, while the second DNS zone handles external requests.</span></span>
  
<span data-ttu-id="e8baa-146">회사가이 작업을 수행 하는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="e8baa-146">Why would a company do this?</span></span> <span data-ttu-id="e8baa-147">이러한 사용자는 내부 및 외부에서 동일한 네임 스페이스를 사용 해야 하는 경우가 있을 수 있지만, 이렇게 하면 여러 DNS SRV와 하나 이상의 영역에 대해 고유 하 고 중복 되는 레코드가 있는 경우 이러한 레코드와 연결 된 IP 주소는 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-147">They may have a requirement to use the same namespace internally and externally, but of course this will lead to many DNS SRV and A records being unique to one zone or another, and where there is duplication, the IP addresses associated with these records would be unique.</span></span>
  
<span data-ttu-id="e8baa-148">여기에 몇 가지 과제가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-148">This presents some challenges.</span></span> <span data-ttu-id="e8baa-149">가장 중요 한 것은 분할 두뇌 DNS가 이동성에 대해 **지원 되지** 않는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-149">The most important is that split-brain DNS is **not supported** for Mobility.</span></span> <span data-ttu-id="e8baa-150">이는 LyncDiscover 및 LyncDiscoverInternal DNS 레코드 (LyncDiscover가 외부 DNS 서버에 정의 되어야 하는 반면, 내부 DNS 서버에는 LyncDiscoverInternal가 정의 되어 있지 않기 때문입니다).</span><span class="sxs-lookup"><span data-stu-id="e8baa-150">This is because of the LyncDiscover and LyncDiscoverInternal DNS records (LyncDiscover has to be defined on you external DNS server, while LyncDiscoverInternal has to be defined on your internal DNS server).</span></span>
  
<span data-ttu-id="e8baa-151">여기에는 내부 및 외부 영역에 대 한 DNS 레코드가 나열 되지만 Edge 서버 환경 요구 사항 섹션에서 자세한 예제를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-151">We'll list the DNS records for the internal and external zones here, but you can find detailed examples on the Edge Server environmental requirements section.</span></span>
  
### <a name="internal-dns"></a><span data-ttu-id="e8baa-152">내부 DNS</span><span class="sxs-lookup"><span data-stu-id="e8baa-152">Internal DNS</span></span>

- <span data-ttu-id="e8baa-153">권한이 있는 (예:) contoso.com DNS 영역을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-153">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="e8baa-154">이 내부 contoso.com에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-154">This internal contoso.com contains:</span></span>
    
  - <span data-ttu-id="e8baa-155">프런트 엔드 풀, 디렉터 풀 또는 디렉터 풀 이름, 그리고 조직의 네트워크에서 비즈니스용 Skype 서버를 실행 하는 모든 내부 서버에 대 한 DNS A 및 AAAA (IPv6 주소 사용) 레코드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-155">DNS A and AAAA (if you're using IPv6 addressing) records for your Front End pool, Director pool or Director pool name, and all internal servers running Skype for Business Server in your organization's network.</span></span>
    
  - <span data-ttu-id="e8baa-156">경계 네트워크의 각 비즈니스용 Skype Server Edge 서버에 대 한 Edge 내부 인터페이스에 대 한 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-156">DNS A and AAAA (if you're using IPv6 addressing) records for your Edge internal interface for each Skype for Business Server Edge Server in your perimeter network.</span></span>
    
  - <span data-ttu-id="e8baa-157">경계 네트워크에서 각 역방향 프록시 서버의 내부 인터페이스에 대 한 DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 레코드 (역방향 프록시 관리의 경우 **선택 사항** ).</span><span class="sxs-lookup"><span data-stu-id="e8baa-157">DNS A and AAAA (if you're using IPv6 addressing) records for the internal interface of each reverse proxy server in your perimeter network (which is **optional** for management of a reverse proxy).</span></span>
    
  - <span data-ttu-id="e8baa-158">DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 및 내부 비즈니스용 Skype 서버 클라이언트 자동 구성에 대 한 SRV 레코드 ( **선택 사항** ).</span><span class="sxs-lookup"><span data-stu-id="e8baa-158">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for internal Skype for Business Server client autoconfiguration (which is **optional** ).</span></span>
    
  - <span data-ttu-id="e8baa-159">DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 또는 비즈니스용 Skype 서버 웹 서비스의 자동 검색을 위한 CNAME 레코드 ( **선택 사항** )</span><span class="sxs-lookup"><span data-stu-id="e8baa-159">DNS A and AAAA (if you're using IPv6 addressing) or CNAME records for automatic discovery of Skype for Business Server Web Services (which is **optional** ).</span></span>
    
- <span data-ttu-id="e8baa-160">주변 네트워크의 모든 비즈니스용 Skype Server 내부 Edge 인터페이스는 contoso.com에 대 한 쿼리 확인을 위해이 내부 DNS 영역을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-160">All your Skype for Business Server internal Edge interfaces in your perimeter network use this internal DNS zone for resolving queries to contoso.com.</span></span>
    
- <span data-ttu-id="e8baa-161">비즈니스용 Skype Server를 실행 하는 모든 서버와 회사 네트워크에서 비즈니스용 Skype Server를 실행 하는 클라이언트는 contoso.com에 대 한 쿼리 확인을 위한 내부 DNS 서버를 가리키거나 각 Edge 서버의 호스트 파일 및 목록 A 및 AAAA (사용 중인 경우)를 사용 합니다. IPv6 주소 지정) 다음 홉 서버 (특히 디렉터 또는 디렉터 풀 VIP, 프론트 End pool VIP 또는 Standard Edition 서버)에 대 한 레코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-161">All servers running Skype for Business Server, and clients running Skype for Business Server in the corporate network, point to internal DNS servers for resolving queries to contoso.com, or they use the Host file on each Edge Server and list A and AAAA (if you're using IPv6 addressing) records for the next hop server (specifically for the Director or Director pool VIP, Front End pool VIP, or Standard Edition server).</span></span>
    
### <a name="external-dns"></a><span data-ttu-id="e8baa-162">외부 DNS</span><span class="sxs-lookup"><span data-stu-id="e8baa-162">External DNS</span></span>

- <span data-ttu-id="e8baa-163">권한이 있는 (예:) contoso.com DNS 영역을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-163">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="e8baa-164">이 외부 contoso.com에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-164">This external contoso.com contains:</span></span>
    
  - <span data-ttu-id="e8baa-165">비즈니스용 Skype 서버 웹 서비스의 자동 검색을 위해 DNS A와 AAAA (IPv6 주소를 사용 하는 경우) 또는 CNAME 레코드</span><span class="sxs-lookup"><span data-stu-id="e8baa-165">DNS A and AAAA (if you're using IPv6 addressing), or CNAME records, for automatic discovery of Skype for Business Server web services.</span></span> <span data-ttu-id="e8baa-166">이는 이동성에 사용 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-166">This is for use with mobility.</span></span>
    
  - <span data-ttu-id="e8baa-167">DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 및 경계 네트워크의 각 비즈니스용 Skype Server Edge 서버 또는 HLB (하드웨어 부하 분산) VIP의 Edge 외부 인터페이스에 대 한 SRV 레코드.</span><span class="sxs-lookup"><span data-stu-id="e8baa-167">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the Edge external interface of each Skype for Business Server Edge Server or hardware load balanced (HLB) VIP in the perimeter network.</span></span>
    
  - <span data-ttu-id="e8baa-168">DNS A 및 AAAA (IPv6 주소를 사용 하는 경우) 및 역방향 프록시 서버의 외부 인터페이스에 대 한 SRV 레코드 (경계 네트워크의 경우 역방향 프록시 서버 풀의 VIP)</span><span class="sxs-lookup"><span data-stu-id="e8baa-168">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the external interface of the Reverse proxy server or (VIP for a pool of Reverse proxy servers), in the perimeter network.</span></span>
    
  - <span data-ttu-id="e8baa-169">DNS A와 AAAA (IPv6 주소를 사용 하는 경우) 및 비즈니스용 Skype 서버 클라이언트 자동 구성에 대 한 SRV 레코드 ( **선택 사항** ).</span><span class="sxs-lookup"><span data-stu-id="e8baa-169">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for Skype for Business Server client autoconfiguration ( **optional** ).</span></span>
    
## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="e8baa-170">분할 하는 DNS 없이 자동 구성</span><span class="sxs-lookup"><span data-stu-id="e8baa-170">Automatic configuration without split-brain DNS</span></span>
<span data-ttu-id="e8baa-171"><a name="NoSplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="e8baa-171"></span></span>

<span data-ttu-id="e8baa-172">분할 하는 DNS를 사용 하지 않는 경우에는 여기에서 제공 하는 해결 방법 중 하나를 사용 하지 않는 한 비즈니스용 Skype를 실행 하는 클라이언트의 내부 자동 구성이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-172">If you don't use split-brain DNS, internal automatic configuration of clients running Skype for Business won't work unless you're using one of the workarounds we have here.</span></span> <span data-ttu-id="e8baa-173">왜 안 돼요?</span><span class="sxs-lookup"><span data-stu-id="e8baa-173">Why not?</span></span> <span data-ttu-id="e8baa-174">비즈니스용 Skype Server에는 자동 구성에 대해 지정 된 프런트 엔드 풀의 도메인을 일치 시키기 위해 사용자의 SIP URI가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-174">Because Skype for Business Server requires the user's SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="e8baa-175">이는 이전 버전의 Lync Server에서 변경 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-175">This hasn't changed from earlier versions of Lync Server.</span></span>
  
<span data-ttu-id="e8baa-176">따라서 두 개의 SIP 도메인을 사용 하는 경우 다음과 같은 DNS SRV 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-176">So, if you have two SIP domains in use, you'd need these DNS SRV records:</span></span>
  
- <span data-ttu-id="e8baa-177">_sipinternaltls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="e8baa-177">_sipinternaltls._tcp.contoso.com.</span></span> <span data-ttu-id="e8baa-178">SRV 0 0 5061 pool01.contoso.com의 86400</span><span class="sxs-lookup"><span data-stu-id="e8baa-178">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>
    
     <span data-ttu-id="e8baa-179">*사용자가 bob@contoso.com로 로그인 하는 경우이 레코드는 사용자의 SIP 도메인이 프런트 엔드 풀 (contoso.com)의 도메인과 일치 하므로 자동 구성에 사용할 수 있습니다.*</span><span class="sxs-lookup"><span data-stu-id="e8baa-179">*If a user signs in as bob@contoso.com, this record would work for automatic configuration, as the user's SIP domain matches the domain of the Front End pool (contoso.com).*</span></span> 
    
- <span data-ttu-id="e8baa-180">_sipinternaltls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="e8baa-180">_sipinternaltls._tcp.fabrikam.com.</span></span> <span data-ttu-id="e8baa-181">SRV 0 0 5061 pool01.fabrikam.com의 86400</span><span class="sxs-lookup"><span data-stu-id="e8baa-181">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="e8baa-182">*사용자가 alice@fabrikam.com로 로그인 하는 경우이 레코드는 SIP 도메인이 해당 도메인의 프런트 엔드 풀과 일치 하기 때문에 두 번째 도메인의 자동 구성에 대해 작동 합니다.*</span><span class="sxs-lookup"><span data-stu-id="e8baa-182">*If a user signs in as alice@fabrikam.com, this record would work for automatic configuration of the second domain, again because the SIP domain matches the Front End pool for that domain.*</span></span> 
    
<span data-ttu-id="e8baa-183">이 예제를 더 자세히 살펴보려면 다음을 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-183">To take the example further, this would not work:</span></span>
  
- <span data-ttu-id="e8baa-184">_sipinternaltls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="e8baa-184">_sipinternaltls._tcp.litwareinc.com.</span></span> <span data-ttu-id="e8baa-185">SRV 0 0 5061 pool01.fabrikam.com의 86400</span><span class="sxs-lookup"><span data-stu-id="e8baa-185">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="e8baa-186">*Tim@litwareinc.com로 로그인 하는 사용자는 해당 SIP 도메인 (litwareinc.com)이 풀 (fabrikam.com)의 도메인과 일치 하지 않기 때문에 자동 구성에는 적용 되지 않습니다.*</span><span class="sxs-lookup"><span data-stu-id="e8baa-186">*A user signing in as tim@litwareinc.com won't work for automatic configuration, because his SIP domain (litwareinc.com) doesn't match the domain in the pool (fabrikam.com).*</span></span> 
    
<span data-ttu-id="e8baa-187">이제 모든 것을 알고 있으므로, 사용자는 비즈니스용 Skype 클라이언트에 대 한 자동 요구 사항이 있는 경우, 분할 하는 DNS가 필요 하지 않은 경우 다음과 같은 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-187">So now that we know all that, if you need automatic requirement for your Skype for Business clients without split-brain DNS, you have these options:</span></span>
  
- <span data-ttu-id="e8baa-188">**그룹 정책 개체**</span><span class="sxs-lookup"><span data-stu-id="e8baa-188">**Group Policy Objects**</span></span>
    
    <span data-ttu-id="e8baa-189">Gpo (그룹 정책 개체)를 사용 하 여 올바른 서버 값을 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-189">You can use Group Policy Objects (GPOs) to populate the correct server values.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e8baa-190">이 옵션은 자동 구성을 사용 하지 않지만 수동 구성은 자동화 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-190">This option doesn't enable automatic configuration, but it does automate manual configuration.</span></span> <span data-ttu-id="e8baa-191">이 방법을 사용 하는 경우 자동 구성에 연결 된 SRV 레코드가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-191">If this approach is used, the SRV records associated with automatic configuration aren't required.</span></span> 
  
- <span data-ttu-id="e8baa-192">**내부 영역이 일치 합니다.**</span><span class="sxs-lookup"><span data-stu-id="e8baa-192">**Matching internal zone**</span></span>
    
    <span data-ttu-id="e8baa-193">내부 DNS에 외부 DNS 영역과 일치 하는 영역 (예: contoso.com)을 만든 다음 자동으로 사용 되는 비즈니스용 Skype 서버 풀에 해당 하는 DNS A (및 IPv6 주소를 사용 하는 경우 AAAA)를 만들어야 합니다. 구성.</span><span class="sxs-lookup"><span data-stu-id="e8baa-193">You'll need to create a zone in your internal DNS that matches your external DNS zone (for example, contoso.com), and then create DNS A (and AAAA if you're using IPv6 addressing) records that correspond to the Skype for Business Server pool used for automatic configuration.</span></span>
    
    <span data-ttu-id="e8baa-194">예를 들어 사용자가 pool01.contoso.net에 가입한 경우 비즈니스용 Skype에 bob@contoso.com으로 로그인 하 고, contoso.com 이라는 내부 DNS 영역을 만들고, 그 안에 DNS A (및 AAAA IPv6 주소 지정을 사용 하 고 있는 경우) 레코드를 만들어야 합니다. pool01.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e8baa-194">For example, if you have a user homed on pool01.contoso.net, but signs into Skype for Business as bob@contoso.com, create an internal DNS zone called contoso.com, and inside it you need to create a DNS A (and AAAA if IPv6 addressing's being used) record for pool01.contoso.com.</span></span>
    
- <span data-ttu-id="e8baa-195">**핀 점 내부 영역**</span><span class="sxs-lookup"><span data-stu-id="e8baa-195">**Pin-point internal zone**</span></span>
    
    <span data-ttu-id="e8baa-196">내부 DNS에 전체 영역을 만드는 옵션이 없는 경우 자동 구성에 필요한 SRV 레코드에 해당 하는 pin 포인트 (전용) 영역을 만들고 dnscmd를 사용 하 여 해당 영역을 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-196">If creating an entire zone in your internal DNS isn't an option for you, you can create pin-point (dedicated) zones that correspond to the SRV records required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="e8baa-197">DNS 사용자 인터페이스가 pin 포인트 영역의 생성을 지원 하지 않으므로 Dnscmd이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-197">Dnscmd.exe is required because the DNS user interface won't support the creation of pin-point zones.</span></span>
    
    <span data-ttu-id="e8baa-198">예를 들어 SIP 도메인이 contoso.com 경우 두 프런트 엔드 서버를 포함 하는 pool01 라는 프런트 엔드 풀을 사용 하는 경우에는 내부 DNS에 다음과 같은 핀 점 영역과 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-198">For example, if your SIP domain is contoso.com, and you have a Front End pool called pool01 that contains two Front End Servers, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    <span data-ttu-id="e8baa-199">환경에 두 번째 SIP 도메인이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-199">You may have a second SIP domain in your environment.</span></span> <span data-ttu-id="e8baa-200">이 경우 내부 DNS에 다음과 같은 핀 위치 영역과 레코드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-200">In that case, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> <span data-ttu-id="e8baa-201">프런트 엔드 풀 FQDN은 두 번 나타나지만 서로 다른 IP 주소를 사용 하 여 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-201">You'll see the Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="e8baa-202">이것은 DNS 부하 분산이 사용 되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-202">That's because DNS load balancing is used.</span></span> <span data-ttu-id="e8baa-203">HLB를 사용 하는 경우 단일 프론트 엔드 풀 항목만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-203">If HLB is used, there'd only be a single Front End pool entry.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e8baa-204">또한 contoso.com 및 fabrikam.com 예제 간에 프런트 엔드 풀 FQDN 값이 변경 되지만 IP 주소는 동일 하 게 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-204">Also, the Front End pool FQDN values change between the contoso.com and fabrikam.com examples, but the IP addresses remain the same.</span></span> <span data-ttu-id="e8baa-205">이는 SIP 도메인에서 로그인 하는 사용자가 자동 구성에 동일한 프런트 엔드 풀을 사용 하는 것 이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-205">That's because users who're signing in from either SIP domain will be using the same Front End pool for automatic configuration.</span></span> 
  
## <a name="dns-disaster-recovery"></a><span data-ttu-id="e8baa-206">DNS 재해 복구</span><span class="sxs-lookup"><span data-stu-id="e8baa-206">DNS disaster recovery</span></span>
<span data-ttu-id="e8baa-207"><a name="DNSDR"> </a></span><span class="sxs-lookup"><span data-stu-id="e8baa-207"></span></span>

<span data-ttu-id="e8baa-208">비즈니스용 Skype 서버 웹 트래픽을 재해 복구 (DR) 및 장애 조치 사이트로 리디렉션하도록 DNS를 구성 하려면 GeoDNS를 지 원하는 DNS 공급자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-208">To configure DNS to redirect Skype for Business Server web traffic to your disaster recover (DR) and failover sites, you need to use a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="e8baa-209">장애 복구를 지원 하도록 DNS 레코드를 설정 하 여 전체 프런트 엔드 풀 하나가 다운 되는 경우에도 웹 서비스를 사용 하는 기능이 계속 작동 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-209">You can set up your DNS records to support disaster recover, so that features that use web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="e8baa-210">이 DR 기능은 자동 검색, 모임 및 전화 접속 간단한 Url을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-210">This DR feature supports the Autodiscover, Meet and Dial-in simple URLs.</span></span>
  
<span data-ttu-id="e8baa-211">GeoDNS 공급자에서 웹 서비스의 내부 및 외부 해상도에 대 한 추가 DNS 호스트 A (IPv6을 사용 하는 경우 AAAA) 레코드를 정의 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-211">You define and configure additional DNS host A (AAAA if using IPv6) records for internal and external resolution of web services at your GeoDNS provider.</span></span> <span data-ttu-id="e8baa-212">다음은 쌍으로 분산 된 풀이 있는 것으로 간주 하 고, 공급자가 지 원하는 GeoDNS에 라운드 로빈 DNS가 \*\*\*\* 있거나, Pool1를 기본으로 사용 하도록 구성 되어 있고 통신 시 Pool2에 대해 장애 조치를 수행 하는 경우 \*\*\*\* 손실 또는 전원 장애.</span><span class="sxs-lookup"><span data-stu-id="e8baa-212">The following details assume paired pools, geographically dispersed, and that the GeoDNS supported by your provider **either** has round-robin DNS **or** is configured to use Pool1 as primary and fails over to Pool2 in the event of any communications loss or power failure.</span></span>
  
<span data-ttu-id="e8baa-213">이 테이블의 모든 DNS 레코드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-213">All the DNS records in this table are examples.</span></span>
  
|<span data-ttu-id="e8baa-214">**GeoDNS 레코드**</span><span class="sxs-lookup"><span data-stu-id="e8baa-214">**GeoDNS record**</span></span>|<span data-ttu-id="e8baa-215">**풀 레코드**</span><span class="sxs-lookup"><span data-stu-id="e8baa-215">**Pool records**</span></span>|<span data-ttu-id="e8baa-216">**CNAME 레코드**</span><span class="sxs-lookup"><span data-stu-id="e8baa-216">**CNAME records**</span></span>|<span data-ttu-id="e8baa-217">**DNS 설정 (한 옵션 선택)**</span><span class="sxs-lookup"><span data-stu-id="e8baa-217">**DNS settings (select one option)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e8baa-218">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-218">Meet-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-219">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-219">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="e8baa-220">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-220">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-221">Meet.contoso.com Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-221">Meet.contoso.com to Meet-int.geolb.contoso.com</span></span>  <br/>   <br/> |<span data-ttu-id="e8baa-222">풀 간의 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="e8baa-222">Round Robin between pools</span></span>  <br/> <span data-ttu-id="e8baa-223">**또는**</span><span class="sxs-lookup"><span data-stu-id="e8baa-223">**OR**</span></span> <br/> <span data-ttu-id="e8baa-224">오류가 있는 경우 기본, 보조에 연결을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-224">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="e8baa-225">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-225">Meet-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-226">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-226">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="e8baa-227">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-227">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-228">Meet.contoso.com Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-228">Meet.contoso.com to Meet-ext.geolb.contoso.com</span></span>  <br/>   <br/> |<span data-ttu-id="e8baa-229">풀 간의 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="e8baa-229">Round Robin between pools</span></span>  <br/> <span data-ttu-id="e8baa-230">**또는**</span><span class="sxs-lookup"><span data-stu-id="e8baa-230">**OR**</span></span> <br/> <span data-ttu-id="e8baa-231">오류가 있는 경우 기본, 보조에 연결을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-231">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="e8baa-232">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-232">Dialin-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-233">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-233">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="e8baa-234">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-234">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-235">Meet.contoso.com Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-235">Meet.contoso.com to Meet-int.geolb.contoso.com</span></span>   <br/>  <br/> |<span data-ttu-id="e8baa-236">풀 간의 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="e8baa-236">Round Robin between pools</span></span>  <br/> <span data-ttu-id="e8baa-237">**또는**</span><span class="sxs-lookup"><span data-stu-id="e8baa-237">**OR**</span></span> <br/> <span data-ttu-id="e8baa-238">오류가 있는 경우 기본, 보조에 연결을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-238">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="e8baa-239">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-239">Dialin-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-240">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-240">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="e8baa-241">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-241">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-242">Meet.contoso.com Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-242">Meet.contoso.com to Meet-ext.geolb.contoso.com</span></span>  <br/>  <br/> |<span data-ttu-id="e8baa-243">풀 간의 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="e8baa-243">Round Robin between pools</span></span>  <br/> <span data-ttu-id="e8baa-244">**또는**</span><span class="sxs-lookup"><span data-stu-id="e8baa-244">**OR**</span></span> <br/> <span data-ttu-id="e8baa-245">오류가 있는 경우 기본, 보조에 연결을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-245">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="e8baa-246">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-246">Lyncdiscoverint-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-247">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-247">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="e8baa-248">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-248">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-249">Meet.contoso.com Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-249">Meet.contoso.com to Meet-int.geolb.contoso.com</span></span>   <br/>   <br/> |<span data-ttu-id="e8baa-250">풀 간의 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="e8baa-250">Round Robin between pools</span></span>  <br/> <span data-ttu-id="e8baa-251">**또는**</span><span class="sxs-lookup"><span data-stu-id="e8baa-251">**OR**</span></span> <br/> <span data-ttu-id="e8baa-252">오류가 있는 경우 기본, 보조에 연결을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-252">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="e8baa-253">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-253">Lyncdiscover-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-254">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-254">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="e8baa-255">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-255">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-256">Meet.contoso.com Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-256">Meet.contoso.com to Meet-ext.geolb.contoso.com</span></span>  <br/>  <br/> |<span data-ttu-id="e8baa-257">풀 간의 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="e8baa-257">Round Robin between pools</span></span>  <br/> <span data-ttu-id="e8baa-258">**또는**</span><span class="sxs-lookup"><span data-stu-id="e8baa-258">**OR**</span></span> <br/> <span data-ttu-id="e8baa-259">오류가 있는 경우 기본, 보조에 연결을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-259">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="e8baa-260">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-260">Scheduler-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-261">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-261">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="e8baa-262">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-262">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-263">Meet.contoso.com Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-263">Meet.contoso.com to Meet-int.geolb.contoso.com</span></span>   <br/>  <br/> |<span data-ttu-id="e8baa-264">풀 간의 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="e8baa-264">Round Robin between pools</span></span>  <br/> <span data-ttu-id="e8baa-265">**또는**</span><span class="sxs-lookup"><span data-stu-id="e8baa-265">**OR**</span></span> <br/> <span data-ttu-id="e8baa-266">오류가 있는 경우 기본, 보조에 연결을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-266">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="e8baa-267">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-267">Scheduler-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-268">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-268">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="e8baa-269">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-269">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-270">Meet.contoso.com Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-270">Meet.contoso.com to Meet-ext.geolb.contoso.com</span></span>   <br/>  <br/> |<span data-ttu-id="e8baa-271">풀 간의 라운드 로빈</span><span class="sxs-lookup"><span data-stu-id="e8baa-271">Round Robin between pools</span></span>  <br/> <span data-ttu-id="e8baa-272">**또는**</span><span class="sxs-lookup"><span data-stu-id="e8baa-272">**OR**</span></span> <br/> <span data-ttu-id="e8baa-273">오류가 있는 경우 기본, 보조에 연결을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-273">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
   
## <a name="dns-load-balancing"></a><span data-ttu-id="e8baa-274">DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="e8baa-274">DNS load balancing</span></span>
<span data-ttu-id="e8baa-275"><a name="DNSLB"> </a></span><span class="sxs-lookup"><span data-stu-id="e8baa-275"></span></span>

<span data-ttu-id="e8baa-276">DNS 부하 분산은 일반적으로 응용 프로그램 수준에서 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-276">DNS load balancing is usually implemented at the application level.</span></span> <span data-ttu-id="e8baa-277">응용 프로그램 (예: 비즈니스용 Skype를 실행 하는 클라이언트)은 DNS A 및 AAAA (IPv6 주소 지정을 사용 하는 경우)에서 반환 된 IP 주소 중 하나에 연결 하 여 풀의 서버에 연결 하려고 시도 합니다. 풀 FQDN에 대 한 레코드 쿼리.</span><span class="sxs-lookup"><span data-stu-id="e8baa-277">The application (for example, a client running Skype for Business), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool FQDN.</span></span>
  
<span data-ttu-id="e8baa-278">예를 들어 pool01.contoso.com 이라는 풀에 프런트 엔드 서버가 세 개 있는 경우 다음이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-278">For example, if there are three Front End Servers in a pool named pool01.contoso.com, the following would happen:</span></span>
  
- <span data-ttu-id="e8baa-279">Pool01.contoso.com 용 비즈니스용 Skype 쿼리 DNS를 실행 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-279">Clients running Skype for Business query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="e8baa-280">쿼리는 IP 주소를 세 개 반환 하 고 다음과 같이 (순서 대로) 캐시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-280">The query returns three IP addresses and caches them as follows (in some order):</span></span>
    
   |||
   |:-----|:-----|
   |<span data-ttu-id="e8baa-281">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-281">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-282">192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="e8baa-282">192.168.10.90</span></span>  <br/> |
   |<span data-ttu-id="e8baa-283">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-283">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-284">192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="e8baa-284">192.168.10.91</span></span>  <br/> |
   |<span data-ttu-id="e8baa-285">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e8baa-285">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="e8baa-286">192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="e8baa-286">192.168.10.92</span></span>  <br/> |
   
- <span data-ttu-id="e8baa-287">클라이언트가 IP 주소 중 하나에 TCP 연결을 설정 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-287">The client tries to establish a TCP connection to one of the IP addresses.</span></span> <span data-ttu-id="e8baa-288">이 문제가 발생 하면 해당 목록에서 캐시 된 다음 IP 주소를 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-288">If that fails, it'll try the next IP address it's cached from that list.</span></span>
    
- <span data-ttu-id="e8baa-289">TCP 연결이 성공 하면 클라이언트는 pool01.contoso.com의 기본 등록 기관에 연결 하도록 TLS를 협상 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-289">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>
    
- <span data-ttu-id="e8baa-290">연결에 성공 하지 않고 모든 캐시 된 항목을 시도 하면 사용자는 비즈니스용 Skype 서버를 실행 하는 서버를 현재 사용할 수 없다는 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-290">If the client tries all cached entries without a successful connection, the user receives a notification that no servers running Skype for Business Server are available at the moment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e8baa-291">DNS 기반 부하 분산은 dns를 사용 하 여 풀의 서버에 대 한 IP 주소를 다른 순서로 제공 하는 dns 라운드 로빈 (DNS RR)과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-291">DNS-based load balancing is different from DNS round robin (DNS RR), which typically refers to load balancing by relying on DNS to give a different order of IP addresses for the servers in your pool.</span></span> <span data-ttu-id="e8baa-292">일반적으로 DNS RR은 부하 분산을 가능 하 게 하지만 장애 조치를 사용 하도록 설정 하는 것을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-292">Typically, DNS RR enables load distribution, but it won't allow you to enable failover.</span></span> <span data-ttu-id="e8baa-293">예를 들어 DNS A (또는 IPv6 시나리오에서 AAAA)가 반환 하는 IP 주소에 대 한 연결에 실패 하면 해당 연결이 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-293">For example, if the connection to the one IP address returned by your DNS A (or AAAA in an IPv6 scenario) query fails, that connection will fail.</span></span> <span data-ttu-id="e8baa-294">Dns RR을 DNS 기반 부하 분산 보다 덜 안정적으로 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-294">That makes DNS RR less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="e8baa-295">이 작업을 수행 해야 하는 경우 dns 기반 부하 분산과 함께 DNS RR을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-295">You can still use DNS RR in conjunction with DNS-based load balancing if you need to do that.</span></span> 
  
<span data-ttu-id="e8baa-296">DNS 부하 분산을 사용 하 여 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-296">You use DNS load balancing to:</span></span>
  
- <span data-ttu-id="e8baa-297">서버 간 SIP에 대 한 부하를 Edge 서버로 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-297">Load balance server-to-server SIP to the Edge Servers.</span></span>
    
- <span data-ttu-id="e8baa-298">회의 자동 전화 교환, 응답 그룹, 통화 공원 등 통합 커뮤니케이션 응용 프로그램 서비스 (c) 응용 프로그램의 부하 분산.</span><span class="sxs-lookup"><span data-stu-id="e8baa-298">Load balance Unified Communication Application Services (UCAS) applications, such as Conferencing Auto Attendant, Response Group, and Call Park.</span></span>
    
- <span data-ttu-id="e8baa-299">응용 프로그램으로 새 연결 (드레이닝이 라고도 함)을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-299">Prevent new connections to UCAS applications (also known as draining).</span></span>
    
- <span data-ttu-id="e8baa-300">클라이언트와 Edge 서버 간의 모든 클라이언트 간 트래픽에 대 한 부하 균형을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-300">Load balance all client-to-server traffic between clients and Edge Servers.</span></span>
    
<span data-ttu-id="e8baa-301">다음에 대해 DNS 부하 분산을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-301">You can't use DNS load balancing for:</span></span>
  
- <span data-ttu-id="e8baa-302">프런트 엔드 서버 또는 디렉터에 대 한 클라이언트 대 서버 웹 트래픽</span><span class="sxs-lookup"><span data-stu-id="e8baa-302">Client-to-server web traffic to your Front End Servers or a Director.</span></span>
    
<span data-ttu-id="e8baa-303">쿼리를 통해 mutiple DNS 레코드를 반환 하는 경우 DNS SRV 레코드를 선택 하는 방법에 대 한 자세한 내용을 더 자세히 설명 하기 위해, Access Edge 서비스는 항상 가장 낮은 숫자 우선 순위의 레코드를 선택 하 고, 연결 분리기가 필요한 경우 가장 높은 숫자 가중치를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-303">To go a little more in-depth on how a DNS SRV record's selected when mutiple DNS records are returned by a query, the Access Edge service always picks the record with the lowest numeric priority and, if a tie-breaker is needed, the highest numeric weight.</span></span> <span data-ttu-id="e8baa-304">이는 [인터넷 엔지니어링 작업 힘 설명서](https://www.ietf.org/rfc/rfc2782.txt)와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-304">This is consistent with [Internet Engineering Task Force documentation](https://www.ietf.org/rfc/rfc2782.txt).</span></span>
  
<span data-ttu-id="e8baa-305">예를 들어 첫 번째 DNS SRV 레코드의 가중치가 20이 고 우선 순위가 40이 고 두 번째 DNS SRV 레코드의 가중치가 10이 고 우선 순위가 50 인 경우 첫 번째 레코드의 40 우선 순위가 낮은 것이 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-305">So, for example, if your first DNS SRV record has a weight of 20 and a priority of 40, and your second DNS SRV record has a weight of 10 and a priority of 50, the first record's going to be chosen because it has the lower priority of 40.</span></span> <span data-ttu-id="e8baa-306">우선 순위는 항상 먼저, 즉 클라이언트가 먼저 대상으로 하는 호스트입니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-306">Priority always goes first, and that's the host that a client will target first.</span></span> <span data-ttu-id="e8baa-307">우선 순위가 같은 대상이 두 개 있는 경우</span><span class="sxs-lookup"><span data-stu-id="e8baa-307">What if there are two targets with the same priority?</span></span> 
  
<span data-ttu-id="e8baa-308">이 경우에는 비중을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-308">In that case, weight comes into consideration.</span></span> <span data-ttu-id="e8baa-309">가중치가 클수록이 환경에서 선택 되는 확률이 높음으로 지정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-309">Larger weights should be given a high probability, in this circumstance, of being selected.</span></span> <span data-ttu-id="e8baa-310">DNS 관리자는 수행할 서버 선택이 없는 경우 가중치 0을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-310">DNS administrators should use weight 0 when there isn't any server selection to do.</span></span> <span data-ttu-id="e8baa-311">가중치가 0 보다 큰 레코드가 있는 경우 가중치가 0 인 레코드는 선택 된 상태로 만들 확률이 매우 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-311">In the presence of records containing weights greater than 0, records with weight 0 have a very small chance of bring selected.</span></span>
  
<span data-ttu-id="e8baa-312">따라서 우선 순위가 같고 가중치가 반환 되는 여러 DNS SRV 레코드가 있는 경우 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="e8baa-312">So, then, what happens if multiple DNS SRV records with equal priority and weight as returned?</span></span> <span data-ttu-id="e8baa-313">이 상황에서 액세스에 지 서비스는 먼저 DNS 서버에서 받은 SRV 레코드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8baa-313">In this situation the Access Edge service will choose the SRV record that it got from the DNS server first.</span></span>
  

