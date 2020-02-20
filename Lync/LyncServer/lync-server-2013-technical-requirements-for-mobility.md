---
title: 'Lync Server 2013: 모바일 기능에 대 한 기술 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for mobility
ms:assetid: 831be681-4de0-4e42-b04f-8879ca4dcd23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690030(v=OCS.15)
ms:contentKeyID: 48184679
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 511e0ceb2d130d53c0f150e71af4074c25db465d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-mobility-in-lync-server-2013"></a><span data-ttu-id="7aa19-102">Lync Server 2013의 모바일 기능에 대 한 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7aa19-102">Technical requirements for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aa19-103">_**마지막으로 수정 된 항목:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="7aa19-103">_**Topic Last Modified:** 2014-07-24_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="7aa19-104">모바일 사용자는 특수한 계획을 세워야 하는 다양한 모바일 응용 프로그램 시나리오를 경험하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-104">Mobile users encounter various mobile application scenarios that require special planning.</span></span> <span data-ttu-id="7aa19-105">예를 들어, 다른 사용자가 3G 네트워크를 통해 연결 하는 방식으로 모바일 응용 프로그램을 사용 하기 시작한 다음 회사 Wi-fi 네트워크로 전환한 다음, 건물에서 나가면 다시 3G로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-105">For example, someone might start using a mobile application while away from work by connecting through the 3G network, then switch to the corporate Wi-Fi network when arriving at work, and then switch back to 3G when leaving the building.</span></span> <span data-ttu-id="7aa19-106">이와 같은 네트워크 전환을 지원하고 일관된 사용자 환경을 보장할 수 있도록 환경을 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-106">You need to plan your environment to support such network transitions and guarantee a consistent user experience.</span></span> <span data-ttu-id="7aa19-107">이 섹션에서는 모바일 응용 프로그램을 지원 하 고 이동성 리소스를 자동으로 검색 하기 위해 필요한 인프라 요구 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-107">This section describes the infrastructure requirements that you must have in order to support mobile applications and automatic discovery of mobility resources.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7aa19-108">모바일 응용 프로그램 에서도 다른 Lync Server 2013 서비스에 연결할 수 있지만 모든 모바일 응용 프로그램 웹 요청을 동일한 외부 웹 FQDN (정규화 된 도메인 이름)에 전송 해야 하는 요구 사항은 Lync Server 2013 Mobility Service에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-108">Although mobile applications can also connect to other Lync Server 2013 services, the requirement to send all mobile application web requests to the same external web fully qualified domain name (FQDN) applies only to the Lync Server 2013 Mobility Service.</span></span> <span data-ttu-id="7aa19-109">다른 모바일 서비스에는이 구성이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-109">Other mobility services do not require this configuration.</span></span>



</div>

<span data-ttu-id="7aa19-110">하드웨어 부하 분산 장치의 쿠키 선호도에 대 한 요구 사항은 크게 줄어들며 Lync Server 2013와 함께 제공 되는 Lync Mobile을 사용 하는 경우 TCP (전송 제어 프로토콜) 선호도를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-110">The requirement for cookie affinity in hardware load balancers is dramatically reduced, and you substitute Transmission Control Protocol (TCP) affinity if you are using the Lync Mobile delivered with Lync Server 2013.</span></span> <span data-ttu-id="7aa19-111">쿠키 선호도는 계속 사용할 수 있지만 웹 서비스에서 더 이상 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-111">Cookie affinity can still be used, but the web services no longer require it.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7aa19-112">모든 모바일 서비스 트래픽은 시작 지점의 위치 (내부 또는 외부)에 관계 없이 역방향 프록시를 통해 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-112">All Mobility Service traffic goes through the reverse proxy, regardless of where the origination point is—internal or external.</span></span> <span data-ttu-id="7aa19-113">단일 역방향 프록시의 팜 또는 역방향 프록시 기능을 제공 하는 장치에 대 한 내부 트래픽이 인터페이스를 통과 하 고 동일한 인터페이스를 즉시 수신 하려고 하면 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-113">In the case of a single reverse proxy or a farm of reverse proxies, or a device that is providing the reverse proxy function, an issue can arise when the internal traffic is egressing through an interface and attempting to immediately ingress on the same interface.</span></span> <span data-ttu-id="7aa19-114">이로 인해 TCP 패킷 스푸핑 또는 스푸핑 이라는 보안 규칙 위반이 발생 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-114">This often leads to a Security rule violation known as TCP packet spoofing or just spoofing.</span></span> <span data-ttu-id="7aa19-115">모바일이 작동 하려면 <EM>헤어 고정</EM> (패킷이나 패킷을 위한 송신 및 즉시 수신)을 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-115"><EM>Hair pinning</EM> (the egress and immediate ingress of a packet or series of packets) must be allowed in order for mobility to function.</span></span> <span data-ttu-id="7aa19-116">이 문제를 해결 하는 한 가지 방법은 방화벽에서 분리 된 역방향 프록시 (보안 목적을 위해 항상 방화벽에서 스푸핑 방지 규칙을 적용 해야 함)를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-116">One way to resolve this issue is to use a reverse proxy that is separate from the firewall (the spoofing prevention rule should always be enforced at the firewall, for security purposes).</span></span> <span data-ttu-id="7aa19-117">헤어핀은 방화벽 외부 인터페이스 대신 역방향 프록시의 외부 인터페이스에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-117">The hairpin can occur at the external interface of the reverse proxy instead of the firewall external interface.</span></span> <span data-ttu-id="7aa19-118">방화벽에서 스푸핑을 감지 하 고 역방향 프록시에서 규칙을 완화 하 여 모바일 기능에 필요한 헤어핀을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-118">You detect the spoofing at the firewall, and relax the rule at the reverse proxy, thereby allowing the hairpin that mobility requires.</span></span><BR><span data-ttu-id="7aa19-119">가능한 경우 DNS (Domain Name System) 호스트 또는 CNAME 레코드를 사용 하 여 헤어핀 동작 (방화벽이 아님)에 대 한 역방향 프록시를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-119">Use the Domain Name System (DNS) host or CNAME records to define the reverse proxy for the hairpin behavior (not the firewall), if at all possible.</span></span>



</div>

<span data-ttu-id="7aa19-120">Lync Server 2013는 Lync 2010 모바일 및 Lync 2013 모바일 클라이언트용 모바일 서비스를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-120">Lync Server 2013 supports mobility services for Lync 2010 Mobile and Lync 2013 mobile clients.</span></span> <span data-ttu-id="7aa19-121">두 클라이언트 모두 Lync Server 2013 자동 검색 서비스를 사용 하 여 모바일 진입점을 찾았지만 사용 하는 모바일 서비스에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-121">Both clients use the Lync Server 2013 Autodiscover Service to find its mobility entry point, but differ on which mobility service they use.</span></span> <span data-ttu-id="7aa19-122">Lync 2010 Mobile은 Lync Server 2010 용 누적 업데이트: 11 월 2011 일에 도입 된 *Mcx*라는 모바일 서비스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-122">Lync 2010 Mobile uses the Mobility Service known as *Mcx*, introduced with the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="7aa19-123">Lync 2013 모바일 클라이언트는 통합 커뮤니케이션 웹 API 또는 기타 *wa*를 모바일 서비스 공급자로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-123">Lync 2013 mobile clients use the Unified Communications Web API, or *UCWA*, as their mobility service provider.</span></span>

<div>

## <a name="internal-and-external-dns-configuration"></a><span data-ttu-id="7aa19-124">내부 및 외부 DNS 구성</span><span class="sxs-lookup"><span data-stu-id="7aa19-124">Internal and External DNS Configuration</span></span>

<span data-ttu-id="7aa19-125">모바일 서비스 Mcx (Lync Server 2010:11 월 2011) 및 (Lync Server 용 누적 업데이트에 도입 되었습니다. 2013 2013 년 2 월)에는 동일한 방식으로 DNS를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-125">The Mobility Services Mcx (introduced with the Cumulative Update for Lync Server 2010: November 2011) and UCWA (introduced in the Cumulative Updates for Lync Server 2013: February 2013) use DNS in the same way.</span></span>

<span data-ttu-id="7aa19-126">자동 검색을 사용 하는 경우 모바일 장치는 DNS를 사용 하 여 리소스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-126">When you use Automatic Discovery, mobile devices use DNS to locate resources.</span></span> <span data-ttu-id="7aa19-127">DNS 조회 중에는 내부 DNS 레코드 (lyncdiscoverinternal)와 연결 된 FQDN을 먼저 연결 하려고 시도 합니다.\< 내부 도메인 이름\>)</span><span class="sxs-lookup"><span data-stu-id="7aa19-127">During the DNS lookup, a connection is first attempted to the FQDN that is associated with the internal DNS record (lyncdiscoverinternal.\<internal domain name\>).</span></span> <span data-ttu-id="7aa19-128">내부 DNS 레코드를 사용 하 여 연결을 설정할 수 없는 경우에는 외부 DNS 레코드 (lyncdiscover)를 사용 하 여 연결\< 을 시도 합니다. microsoft.rtc.management.xds.sipdomain object\>)</span><span class="sxs-lookup"><span data-stu-id="7aa19-128">If a connection cannot be made by using the internal DNS record, a connection is attempted by using the external DNS record (lyncdiscover.\<sipdomain\>).</span></span> <span data-ttu-id="7aa19-129">네트워크 내부의 모바일 장치가 내부 자동 검색 서비스 URL에 연결 되 고 네트워크 외부의 모바일 장치가 외부 자동 검색 서비스 URL에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-129">A mobile device that is internal to the network connects to the internal Autodiscover Service URL, and a mobile device that is external to the network connects to the external Autodiscover Service URL.</span></span> <span data-ttu-id="7aa19-130">외부 자동 검색 요청은 역방향 프록시를 통과 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-130">External Autodiscover requests go through the reverse proxy.</span></span> <span data-ttu-id="7aa19-131">Lync Server 2013 자동 검색 서비스는 모바일 서비스 (Mcx 및 인천 wa) Url을 포함 하 여 사용자의 홈 풀에 대 한 모든 웹 서비스 Url을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-131">The Lync Server 2013 Autodiscover Service returns all Web Services URLs for the user's home pool, including the Mobility Service (Mcx and UCWA) URLs.</span></span> <span data-ttu-id="7aa19-132">그러나 내부 Mobility Service URL과 외부 Mobility Service URL은 모두 외부 웹 서비스 FQDN에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-132">However, both the internal Mobility Service URL and the external Mobility Service URL are associated with the external Web Services FQDN.</span></span> <span data-ttu-id="7aa19-133">따라서 모바일 장치가 네트워크 내부에 있든 외부에 있는지 여부에 관계 없이 장치는 항상 역방향 프록시를 통해 외부 Lync Server 2013 Mobility Service에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-133">Therefore, regardless of whether a mobile device is internal or external to the network, the device always connects to the Lync Server 2013 Mobility Service externally through the reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7aa19-134">배포는 내부 및 외부에서 사용 하기 위해 여러 개의 고유한 네임 스페이스로 구성 될 수 있다는 점을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-134">It is important to understand that your deployment can consist of multiple distinct namespaces for internal and external use.</span></span> <span data-ttu-id="7aa19-135">SIP 도메인 이름은 내부 배포 도메인 이름과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-135">Your SIP domain name may be different than the internal deployment domain name.</span></span> <span data-ttu-id="7aa19-136">예를 들어 SIP 도메인은 <STRONG>contoso.com</STRONG>수 있지만 내부 배포가 <STRONG>contoso.net</STRONG>될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-136">For example, your SIP domain may be <STRONG>contoso.com</STRONG>, while your internal deployment may be <STRONG>contoso.net</STRONG>.</span></span> <span data-ttu-id="7aa19-137">Lync Server에 로그인 하는 사용자는 <STRONG>john@contoso.com</STRONG>와 같은 SIP 도메인 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-137">Users who log in to Lync Server will use the SIP domain name, such as <STRONG>john@contoso.com</STRONG>.</span></span> <span data-ttu-id="7aa19-138">외부 웹 서비스에 주소를 지정 하는 경우 (토폴로지 작성기에서 <STRONG>외부 웹 서비스로</STRONG>정의 됨) 도메인 이름 및 SIP 도메인 이름은 DNS에 정의 된 대로 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-138">When addressing the external web services (defined in Topology Builder as <STRONG>External web services</STRONG>), the domain name and the SIP domain name will be consistent, as defined in DNS.</span></span> <span data-ttu-id="7aa19-139">내부 웹 서비스를 처리할 때 (토폴로지 작성기에 <STRONG>내부 웹 서비스로</STRONG>정의 됨) 내부 웹 서비스의 기본 이름은 프런트 엔드 서버, 프런트 엔드 풀, 디렉터 또는 디렉터 풀의 FQDN이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-139">When addressing the internal Web services (defined in Topology Builder as <STRONG>Internal web services</STRONG>), the default name of the internal web services will be the FQDN of the Front End Server, Front End pool, Director, or Director pool.</span></span> <span data-ttu-id="7aa19-140">내부 웹 서비스 이름을 재정의 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-140">You have the option to override the internal web services name.</span></span> <span data-ttu-id="7aa19-141">내부 웹 서비스에 대 한 내부 도메인 이름을 사용 하 고 (SIP 도메인 이름이 아님) DNS 호스트 A (또는 i p v 6) 레코드를 정의 하 여 재정의 된 이름을 반영 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-141">You should use the internal domain name (and not the SIP domain name) for internal web services and define the DNS host A (or, for IPv6, AAAA) record to reflect the overridden name.</span></span> <span data-ttu-id="7aa19-142">예를 들어 기본 내부 웹 서비스 FQDN은 <STRONG>pool01.contoso.net</STRONG>일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-142">For example, the default internal web services FQDN may be <STRONG>pool01.contoso.net</STRONG>.</span></span> <span data-ttu-id="7aa19-143">재정의 된 내부 웹 서비스 FQDN은 <STRONG>webpool.contoso.net</STRONG>일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-143">An overridden internal web services FQDN may be <STRONG>webpool.contoso.net</STRONG>.</span></span> <span data-ttu-id="7aa19-144">이러한 방식으로 웹 서비스를 정의 하면 서비스의 내부 및 외부 집약성을 사용 하는 사용자의 집약성이 관찰 되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-144">Defining the web services in this way helps to ensure that the internal and external locality of the services—and not the locality of the user who is using them—is observed.</span></span><BR><span data-ttu-id="7aa19-145">그러나 웹 서비스가 토폴로지 작성기에 정의 되 고 내부 웹 서비스 이름을 다시 정의할 수 있으므로 (예를 들어 웹 서비스 이름을 확인 하는 인증서 및이를 정의 하는 DNS 레코드를 정의 하는 경우)에는 일관성을 유지할 수 있습니다. 원하는 도메인 이름 (SIP 도메인 이름 포함)을 가진 내부 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="7aa19-145">However, because the web services are defined in Topology Builder and the internal web services name can be overridden, as long as the resulting web services name, the certificate that validates it, and the DNS records that define it, are consistent, you can define the internal web services with any domain name—including the SIP domain name—that you want.</span></span> <span data-ttu-id="7aa19-146">궁극적으로 IP 주소에 대 한 이름 확인은 DNS 호스트 레코드 및 일관성 있는 네임 스페이스에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-146">Ultimately, the resolution for the name to the IP address is determined by DNS host records and a consistent namespace.</span></span><BR><span data-ttu-id="7aa19-147">이 항목 및 예제를 위해 내부 도메인 이름을 사용 하 여 토폴로지와 DNS 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-147">For the purposes of this topic and the examples, the internal domain name is used to illustrate the topology and the DNS definitions.</span></span>



</div>

<span data-ttu-id="7aa19-148">다음 다이어그램에서는 내부 및 외부 DNS 구성을 사용 하는 경우 자동 검색 서비스와 모바일 서비스에 대 한 모바일 응용 프로그램 웹 요청의 흐름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-148">The following diagram illustrates the flow of mobile application web requests for the Mobility Service and for the Autodiscover Service when using an internal and external DNS configuration.</span></span>

<span data-ttu-id="7aa19-149">**자동 검색을 사용 하는 모바일 서비스 흐름**</span><span class="sxs-lookup"><span data-stu-id="7aa19-149">**Mobility service flow using AutoDiscover**</span></span>

<span data-ttu-id="7aa19-150">![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")</span><span class="sxs-lookup"><span data-stu-id="7aa19-150">![cdb96424-96f2-4abf-88d7-1d32d1010ffd](images/Hh690030.cdb96424-96f2-4abf-88d7-1d32d1010ffd(OCS.15).jpg "cdb96424-96f2-4abf-88d7-1d32d1010ffd")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7aa19-151">이 다이어그램은 일반 웹 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-151">The diagram illustrates generic web services.</span></span> <span data-ttu-id="7aa19-152">Mobility 라는 가상 디렉터리는 Mobility services Mcx 및/또는 WA를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-152">A virtual directory named Mobility depicts the Mobility services Mcx and/or UCWA.</span></span> <span data-ttu-id="7aa19-153">Lync Server 2013:2 월 2013에 대 한 누적 업데이트를 적용 하지 않은 경우 내부 및 외부 웹 서비스에 정의 된 가상 디렉터리를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-153">If you have not applied the Cumulative Updates for Lync Server 2013: February 2013, you may or may not have the virtual directory Ucwa defined on your internal and external Web services.</span></span> <span data-ttu-id="7aa19-154">가상 디렉터리 자동 검색을 갖게 되 고 가상 디렉터리 Mcx가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-154">You will have a virtual directory Autodiscover, and you may have a virtual directory Mcx.</span></span><BR><span data-ttu-id="7aa19-155">배포 된 모바일 서비스 기술에 관계 없이 동일한 방식으로 자동 검색 및 서비스 검색이 동일 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-155">Autodiscover and the discovery of services work the same way, regardless of the mobility services technology that you have deployed.</span></span>



</div>

<span data-ttu-id="7aa19-p110">회사 네트워크 내부와 외부에서 모두 모바일 사용자를 지원하려면 내부 및 외부 웹 FQDN이 몇 가지 선행 조건을 충족해야 합니다. 또한 구현하도록 선택하는 기능에 따라 다른 요구 사항도 충족해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-p110">To support mobile users from both inside and outside the corporate network, your internal and external web FQDNs must meet some prerequisites. In addition, you may need to meet other requirements, depending on the features you choose to implement:</span></span>

  - <span data-ttu-id="7aa19-158">자동 검색을 위한 새 DNS, CNAME 또는 A (호스트, if IPv6, AAAA) 레코드</span><span class="sxs-lookup"><span data-stu-id="7aa19-158">New DNS, CNAME or A (host, if IPv6, AAAA) records, for automatic discovery.</span></span>

  - <span data-ttu-id="7aa19-159">새 방화벽 규칙 (Wi-fi 네트워크를 통한 푸시 알림을 지원 하려는 경우)</span><span class="sxs-lookup"><span data-stu-id="7aa19-159">New firewall rule, if you want to support push notifications through your Wi-Fi network.</span></span>

  - <span data-ttu-id="7aa19-160">자동 검색을 위한 내부 서버 인증서 및 역방향 프록시 인증서의 주체 대체 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-160">Subject alternative names on internal server certificates and reverse proxy certificates, for automatic discovery.</span></span>

  - <span data-ttu-id="7aa19-161">프런트 엔드 서버 하드웨어 부하 분산 장치 구성에서 원본 선호도를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-161">Front End Server hardware load balancer configuration changes source affinity.</span></span>

<span data-ttu-id="7aa19-162">모바일 서비스 및 자동 검색 서비스를 지원 하려면 토폴로지가 다음 요구 사항을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-162">Your topology must meet the following requirements to support the Mobility Service and the Autodiscover Service:</span></span>

  - <span data-ttu-id="7aa19-163">프런트 엔드 풀 내부 웹 FQDN은 프런트 엔드 풀 외부 웹 FQDN과 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-163">The Front End pool internal web FQDN must be distinct from the Front End pool external web FQDN.</span></span>

  - <span data-ttu-id="7aa19-164">내부 웹 FQDN은 회사 네트워크 내부에서만 확인되어야 하며 액세스 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-164">The internal web FQDN must only resolve to and be accessible from inside the corporate network.</span></span>

  - <span data-ttu-id="7aa19-165">외부 웹 FQDN은 인터넷을 통해서만 확인 되 고 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-165">The external web FQDN must only resolve to and be accessible from the Internet.</span></span>

  - <span data-ttu-id="7aa19-p111">회사 네트워크 내부 사용자의 경우 Mobility Service URL의 주소는 외부 웹 FQDN으로 지정되어야 합니다. 이는 Mobility Service에 대한 요구 사항으로, 이 URL에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-p111">For a user who is inside the corporate network, the Mobility Service URL must be addressed to the external web FQDN. This requirement is for the Mobility Service and applies only to this URL.</span></span>

  - <span data-ttu-id="7aa19-168">회사 네트워크 외부에 있는 사용자의 경우에는 요청이 프런트 엔드 풀 또는 디렉터의 외부 웹 FQDN으로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-168">For a user who is outside the corporate network, the request must go to the external web FQDN of the Front End pool or Director.</span></span>

<span data-ttu-id="7aa19-169">자동 검색을 지원하는 경우 각 SIP 도메인에 대해 다음 DNS 레코드를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-169">If you support automatic discovery, you need to create the following DNS records for each SIP domain:</span></span>

  - <span data-ttu-id="7aa19-170">조직 네트워크 내에서 연결 하는 모바일 사용자를 지원 하기 위한 내부 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="7aa19-170">An internal DNS record to support mobile users who connect from within your organization's network.</span></span>

  - <span data-ttu-id="7aa19-171">인터넷에서 연결 하는 모바일 사용자를 지원 하기 위한 외부 또는 공용 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="7aa19-171">An external, or public, DNS record to support mobile users who connect from the Internet.</span></span>

<span data-ttu-id="7aa19-172">내부 자동 검색 URL은 네트워크 외부에서 주소를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-172">The internal automatic discovery URL should not be addressable from outside your network.</span></span> <span data-ttu-id="7aa19-173">외부 자동 검색 URL은 네트워크 내에서 주소를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-173">The external automatic discovery URL should not be addressable from within your network.</span></span> <span data-ttu-id="7aa19-174">그러나 외부 URL에 대해이 요구 사항을 충족할 수 없는 경우에는 내부 URL이 항상 먼저 시도 되므로 모바일 클라이언트 기능에 영향을 주지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-174">However, if you cannot meet this requirement for the external URL, mobile client functionally will probably not be affected, because the internal URL is always tried first.</span></span>

<span data-ttu-id="7aa19-175">DNS 레코드는 CNAME 레코드 또는 A (호스트, if IPv6, AAAA) 레코드가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-175">The DNS records can be either CNAME records or A (host, if IPv6, AAAA) records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7aa19-176">모바일 장치는 서로 다른 도메인에서 여러 SSL(Secure Sockets Layer) 인증서를 지원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-176">Mobile device clients do not support multiple Secure Sockets Layer (SSL) certificates from different domains.</span></span> <span data-ttu-id="7aa19-177">따라서 HTTPS를 통해서는 다른 도메인으로의 CNAME 리디렉션이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-177">Therefore, CNAME redirection to different domains is not supported over HTTPS.</span></span> <span data-ttu-id="7aa19-178">예를 들어 director.contoso.net 주소로 리디렉션되는 lyncdiscover.contoso.com의 DNS CNAME 레코드는 HTTPS에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-178">For example, a DNS CNAME record for lyncdiscover.contoso.com that redirects to an address of director.contoso.net is not supported over HTTPS.</span></span> <span data-ttu-id="7aa19-179">이러한 토폴로지에서는 HTTP를 통해 CNAME 리디렉션이 확인되도록 모바일 장치 클라이언트가 첫 번째 요청에 대해 HTTP를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-179">In such a topology, a mobile device client needs to use HTTP for the first request, so that the CNAME redirection is resolved over HTTP.</span></span> <span data-ttu-id="7aa19-180">후속 요청에서는 HTTPS를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-180">Subsequent requests then use HTTPS.</span></span> <span data-ttu-id="7aa19-181">이 시나리오를 지원하려면 포트 80(HTTP)에 대한 웹 게시 규칙을 사용하여 역방향 프록시를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-181">To support this scenario, you need to configure your reverse proxy with a web publishing rule for port 80 (HTTP).</span></span> <span data-ttu-id="7aa19-182">자세한 내용은 <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Lync Server 2013에서 모바일 기능에 대 한 역방향 프록시 구성</A>의 "포트 80에 대 한 웹 게시 규칙을 만들려면"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7aa19-182">For details, see "To create a web publishing rule for port 80" in <A href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Configuring the reverse proxy for mobility in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="7aa19-183">동일한 도메인으로의 CNAME 리디렉션은 HTTPS를 통해 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-183">CNAME redirection to the same domain is supported over HTTPS.</span></span> <span data-ttu-id="7aa19-184">이 경우 대상 도메인의 인증서가 원래 도메인을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-184">In this case, the destination domain's certificate covers the originating domain.</span></span>



</div>

<span data-ttu-id="7aa19-185">시나리오에 필요한 DNS 레코드에 대 한 자세한 내용은 [Lync Server 2013에서 dns 요약-자동 검색](lync-server-2013-dns-summary-autodiscover.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa19-185">For details about the DNS records required for your scenario, see [DNS summary - Autodiscover in Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md).</span></span>

</div>

<div>

## <a name="port-and-firewall-requirements"></a><span data-ttu-id="7aa19-186">포트 및 방화벽 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7aa19-186">Port and Firewall Requirements</span></span>

<span data-ttu-id="7aa19-187">푸시 알림을 지원하며 Apple 모바일 장치에서 Wi-Fi 네트워크를 통해 푸시 알림을 받도록 하려면 엔터프라이즈 Wi-Fi 네트워크에서 포트 5223도 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-187">If you support push notifications and want Apple mobile devices to receive push notifications over your Wi-Fi network, you also need to open port 5223 on your enterprise Wi-Fi network.</span></span> <span data-ttu-id="7aa19-188">포트 5223은 APNS(Apple 푸시 알림 서비스)에서 사용되는 아웃바운드 TCP 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-188">Port 5223 is an outbound TCP port used by the Apple Push Notification Service (APNS).</span></span> <span data-ttu-id="7aa19-189">모바일 장치가 연결을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-189">The mobile device initiates the connection.</span></span> <span data-ttu-id="7aa19-190">자세한 내용은를 참조 [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) 하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa19-190">For details, see [http://support.apple.com/kb/TS1629](http://support.apple.com/kb/ts1629) .</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="7aa19-191">Lync 2013 모바일 클라이언트를 사용 하는 Apple 장치에는 푸시 알림이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-191">An Apple device using the Lync 2013 Mobile client does not require push notifications.</span></span>



</div>

<span data-ttu-id="7aa19-192">사용자가 SBA (Sba (survivable Branch 기기)에 있는 경우에는 다음 포트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-192">Note that if a user is homed on a Survivable Branch Appliance (SBA) then the following ports are required:</span></span>

  - <span data-ttu-id="7aa19-193">UcwaSipExternalListeningPort에는 포트 5088이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-193">UcwaSipExternalListeningPort requires port 5088</span></span>

  - <span data-ttu-id="7aa19-194">UcwaSipPrimaryListeningPort에는 포트 5089이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-194">UcwaSipPrimaryListeningPort requires port 5089</span></span>

<span data-ttu-id="7aa19-195">자동 검색을 위한 포트 및 프로토콜 요구 사항에 대 한 자세한 내용 및 지침은 [포트 요약-자동 검색에서 Lync Server 2013](lync-server-2013-port-summary-autodiscover.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa19-195">For additional details and guidance on port and protocol requirements for Autodiscover, see [Port summary - Autodiscover in Lync Server 2013](lync-server-2013-port-summary-autodiscover.md).</span></span>

</div>

<div>

## <a name="certificate-requirements"></a><span data-ttu-id="7aa19-196">인증서 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7aa19-196">Certificate Requirements</span></span>

<span data-ttu-id="7aa19-197">Lync 모바일 클라이언트에 대해 자동 검색을 지원하는 경우에는 모바일 클라이언트로부터의 보안 연결을 지원하기 위해 인증서의 주체 대체 이름 목록을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-197">If you support automatic discovery for Lync mobile clients, you need to modify the subject alternative name lists on certificates to support secure connections from the mobile clients.</span></span> <span data-ttu-id="7aa19-198">이 섹션에서 설명 하는 각 프런트 엔드 서버와 자동 검색 서비스를 실행 하는 디렉터에 대 한 주체 대체 이름 항목을 추가 하 여 새 인증서를 요청 하 고 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-198">You need to request and assign new certificates, adding the subject alternative name entries described in this section, for each Front End Server and Director that runs the Autodiscover Service.</span></span> <span data-ttu-id="7aa19-199">이 경우 역방향 프록시용 인증서에서도 주체 대체 이름 목록을 수정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-199">The recommended approach is to also modify the subject alternative names lists on certificates for your reverse proxies.</span></span> <span data-ttu-id="7aa19-200">조직의 모든 SIP 도메인에 대해 주체 대체 이름 항목을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-200">You need to add subject alternative name entries for every SIP domain in your organization.</span></span>

<span data-ttu-id="7aa19-201">내부 인증 기관을 통해 인증서를 다시 발급하는 과정은 일반적으로는 간단하지만, 역방향 프록시에서 사용되는 공용 인증서에 여러 주체 대체 이름 항목을 추가하려면 비용이 많이 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-201">Reissuing certificates by using an internal certificate authority is typically a simple process, but adding multiple subject alternative name entries to public certificates used by the reverse proxy can be expensive.</span></span> <span data-ttu-id="7aa19-202">SIP 도메인이 여러 개인 경우 주체 대체 이름 추가 비용이 매우 크므로, HTTPS를 사용하는 포트 443(기본 구성)이 아닌 HTTP를 사용하는 포트 80을 통해 초기 자동 검색 서비스 요청을 수행하도록 역방향 프록시를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-202">If you have many SIP domains, making the addition of subject alternative names very expensive, you can configure the reverse proxy to make the initial Autodiscover Service request over port 80 using HTTP, instead of port 443 using HTTPS (the default configuration).</span></span> <span data-ttu-id="7aa19-203">그러면 요청이 디렉터 또는 프런트 엔드 풀의 포트 8080로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-203">The request is then redirected to port 8080 on the Director or Front End pool.</span></span> <span data-ttu-id="7aa19-204">포트 80에서 초기 자동 검색 서비스 요청을 게시할 때는 요청에서 HTTPS가 아닌 HTTP를 사용하므로 역방향 프록시용 인증서를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-204">When you publish the initial Autodiscover Service request on port 80, you do not need to change certificates for the reverse proxy, because the request uses HTTP rather than HTTPS.</span></span> <span data-ttu-id="7aa19-205">이 방법이 지원 되지만 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-205">This approach is supported, but we do not recommend it.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="7aa19-206">IIS(인터넷 정보 서비스) 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7aa19-206">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="7aa19-207">모바일 기능에 IIS 7.5, IIS 8.0 또는 IIS 8.5을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-207">We recommend that you use IIS 7.5, IIS 8.0, or IIS 8.5 for mobility.</span></span> <span data-ttu-id="7aa19-208">모바일 서비스 설치 관리자는 성능을 개선 하기 위해 ASP.NET에서 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-208">The Mobility Service installer sets flags in ASP.NET to improve performance.</span></span> <span data-ttu-id="7aa19-209">IIS 7.5은 windows Server 2008 r 2에 기본적으로 설치 되 고, IIS 8.0은 Windows Server 2012에 설치 되며, IIS 8.5은 Windows Server 2012 r 2에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-209">IIS 7.5 is installed by default on Windows Server 2008 R2, IIS 8.0 is installed on Windows Server 2012, and IIS 8.5 is installed on Windows Server 2012 R2.</span></span> <span data-ttu-id="7aa19-210">모바일 서비스 설치 관리자가 자동으로 ASP.NET 설정을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-210">The Mobility Service installer automatically changes the ASP.NET settings.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="7aa19-211">하드웨어 부하 분산 장치 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7aa19-211">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="7aa19-212">프런트 엔드 풀을 지 원하는 하드웨어 부하 분산 장치에 대해 웹 서비스 트래픽용 외부 웹 서비스 Vip (가상 Ip)를 원본에 대해 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-212">On the hardware load balancer that is supporting the Front End pool, the external Web Services virtual IPs (VIPs) for Web Services traffic must be configured for source.</span></span> <span data-ttu-id="7aa19-213">원본 선호도는 단일 클라이언트 로부터의 여러 연결이 세션 상태를 유지 하기 위해 하나의 서버로 전송 되도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-213">Source affinity helps to ensure that multiple connections from a single client are sent to one server to maintain session state.</span></span> <span data-ttu-id="7aa19-214">선호도 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 부하 분산 요구 사항](lync-server-2013-load-balancing-requirements.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa19-214">For details about affinity requirements, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<span data-ttu-id="7aa19-215">내부 Wi-fi 네트워크를 통해서만 Lync 모바일 클라이언트를 지원 하려는 경우에는 외부 웹 서비스 Vip에 대해 설명 된 대로 원본에 대 한 내부 웹 서비스 VIP를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-215">If you plan to support Lync mobile clients only over your internal Wi-Fi network, you should configure the internal Web Services VIPS for source as described for external Web Services VIPs.</span></span> <span data-ttu-id="7aa19-216">이러한 상황에서는 하드웨어 부하 분산 장치에서\_내부 웹 서비스 vip에 대해 원본 주소 선호도를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-216">In this situation, you should use source\_addr (or TCP) affinity for the internal Web Services VIPs on the hardware load balancer.</span></span> <span data-ttu-id="7aa19-217">자세한 내용은 [Lync Server 2013의 부하 분산 요구 사항](lync-server-2013-load-balancing-requirements.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7aa19-217">For details, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

</div>

<div>

## <a name="reverse-proxy-requirements"></a><span data-ttu-id="7aa19-218">역방향 프록시 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7aa19-218">Reverse Proxy Requirements</span></span>

<span data-ttu-id="7aa19-219">Lync 모바일 클라이언트에 대 한 자동 검색을 지 원하는 경우 현재 게시 규칙을 다음과 같이 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-219">If you support automatic discovery for Lync mobile clients, you need to update the current publishing rule as follows:</span></span>

  - <span data-ttu-id="7aa19-220">역방향 프록시 인증서에서 주체 대체 이름 목록을 업데이트 하 고 초기 자동 검색 서비스 요청에 HTTPS를 사용 하기로 결정 한 경우에는 lyncdiscover에 대 한 웹 게시 규칙을 업데이트 해야 합니다. \<microsoft.rtc.management.xds.sipdomain object\></span><span class="sxs-lookup"><span data-stu-id="7aa19-220">If you decide to update the subject alternative names lists on the reverse proxy certificates and use HTTPS for the initial Autodiscover Service request, you must update the web publishing rule for lyncdiscover.\<sipdomain\>.</span></span> <span data-ttu-id="7aa19-221">일반적으로 프런트 엔드 풀의 외부 웹 서비스 URL에 대 한 게시 규칙과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-221">Typically, this is combined with the publishing rule for the external Web Services URL on the Front End pool.</span></span>

  - <span data-ttu-id="7aa19-222">역방향 프록시 인증서에서 주체 대체 이름 목록을 업데이트 하지 않아도 되도록 초기 자동 검색 서비스 요청에 대해 HTTP를 사용 하려는 경우에는 포트 HTTP/TCP 80에 대 한 새 웹 게시 규칙 (아직 없는 경우)을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aa19-222">If you decide to use HTTP for the initial Autodiscover Service request so that you do not need to update the subject alternative names list on the reverse proxy certificates, you must create a new web publishing rule for port HTTP/TCP 80, if one does not already exist.</span></span> <span data-ttu-id="7aa19-223">HTTP/TCP 80에 대 한 규칙이 이미 있는 경우에는 lyncdiscover를 포함 하도록 해당 규칙을 업데이트할 수 있습니다. \<microsoft.rtc.management.xds.sipdomain object\> 항목</span><span class="sxs-lookup"><span data-stu-id="7aa19-223">If a rule for HTTP/TCP 80 does already exist, you can update that rule to include the lyncdiscover.\<sipdomain\> entry.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

