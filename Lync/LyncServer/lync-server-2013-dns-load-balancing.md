---
title: 'Lync Server 2013: DNS 부하 분산'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79c2bb8e5bbcb9d00fe687d6f06ac6226a2edf6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528925"
---
# <a name="dns-load-balancing-in-lync-server-2013"></a><span data-ttu-id="f0e2e-102">Lync Server 2013의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="f0e2e-102">DNS load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0e2e-103">_**마지막으로 수정 된 항목:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="f0e2e-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="f0e2e-104">Lync Server에서는 네트워크의 부하 분산에 대 한 관리 오버 헤드를 크게 줄일 수 있는 소프트웨어 솔루션인 DNS 부하 분산을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-104">Lync Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="f0e2e-105">DNS 부하 분산은 SIP 트래픽, 미디어 트래픽 등 Lync Server에 고유한 네트워크 트래픽의 균형을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-105">DNS load balancing balances the network traffic that is unique to Lync Server, such as SIP traffic and media traffic.</span></span>

<span data-ttu-id="f0e2e-106">DNS 부하 분산을 배포 하는 경우 하드웨어 부하 분산 장치에 대 한 조직의 관리 오버 헤드가 최소화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-106">If you deploy DNS load balancing, your organization’s administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="f0e2e-107">또한 SIP 트래픽에 대한 부하 분산 장치의 잘못된 구성과 관련된 복잡한 문제를 해결할 필요가 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-107">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="f0e2e-108">또한 서버를 오프라인으로 설정할 수 있도록 서버 연결을 방지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-108">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="f0e2e-109">또한 DNS 부하 분산은 하드웨어 부하 분산 장치 문제가 기본 통화 라우팅과 같은 SIP 트래픽 요소에 영향을 주지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-109">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="f0e2e-110">DNS 부하 분산을 사용하는 경우에는 모든 트래픽 유형에 대해 하드웨어 부하 분산 장치를 사용하는 경우에 비해 저렴한 가격에 하드웨어 부하 분산 장치를 구입할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-110">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="f0e2e-111">Lync Server를 사용 하 여 상호 운용성 검증 테스트를 통과 한 부하 분산 장치를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-111">You should use load balancers that have passed interoperability qualification testing with Lync Server.</span></span> <span data-ttu-id="f0e2e-112">부하 분산 장치 상호 운용성 테스트에 대 한 자세한 내용은의 "Lync Server 2010 부하 분산 장치 파트너"를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) .</span><span class="sxs-lookup"><span data-stu-id="f0e2e-112">For details about load balancer interoperability testing, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<span data-ttu-id="f0e2e-113">DNS 부하 분산은 프런트 엔드 풀, 에지 서버 풀, 디렉터 풀 및 독립 실행형 중재 서버 풀에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-113">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="f0e2e-114">프런트 엔드 풀과 디렉터 풀의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="f0e2e-114">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="f0e2e-p104">프런트 엔드 풀과 디렉터 풀의 SIP 트래픽에 DNS 부하 분산을 사용할 수 있습니다. DNS 부하 분산을 배포한 경우에는 이러한 풀에 클라이언트-서버 HTTPS 트래픽 전용 하드웨어 부하 분산 장치를 사용해야 합니다. 하드웨어 부하 분산 장치는 포트 443 및 80을 통해 클라이언트에서 전송되는 HTTPS 트래픽에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-p104">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools. With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic. The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span>

<span data-ttu-id="f0e2e-118">이러한 풀에 여전히 하드웨어 부하 분산 장치가 필요하지만 설치 및 관리는 주로 HTTP 트래픽에 대한 것이며, 이는 하드웨어 부하 분산 장치 관리자에게 익숙한 일입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-118">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="f0e2e-119">DNS 부하 분산과 이전 클라이언트 및 서버 지원</span><span class="sxs-lookup"><span data-stu-id="f0e2e-119">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="f0e2e-120">DNS 부하 분산은 Lync Server 2013 또는 Lync Server 2010를 실행 하는 서버와 Lync 2013 및 Lync 2010 클라이언트에 대해서만 자동 장애 조치 (failover)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-120">DNS load balancing supports automatic failover only for servers running Lync Server 2013 or Lync Server 2010, and for Lync 2013 and Lync 2010 clients.</span></span> <span data-ttu-id="f0e2e-121">이전 버전의 클라이언트 및 Office Communications Server에서는 여전히 DNS 부하 분산을 실행 하는 풀에 연결할 수 있지만 DNS 부하 분산을 통해 참조 하는 첫 번째 서버에 연결을 설정할 수 없는 경우에는 풀의 다른 서버로 장애 조치 (failover) 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-121">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span>

<span data-ttu-id="f0e2e-122">또한 Exchange UM을 사용 하는 경우에는 최소한의 Exchange 2010 SP1을 사용 하 여 Lync Server DNS 부하 분산을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-122">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Lync Server DNS load balancing.</span></span> <span data-ttu-id="f0e2e-123">이전 버전의 Exchange를 사용 하는 경우 사용자에 게 이러한 Exchange UM 시나리오에 대 한 장애 조치 (failover) 기능이 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-123">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="f0e2e-124">전화기에서 Enterprise Voice 음성 메일 재생</span><span class="sxs-lookup"><span data-stu-id="f0e2e-124">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="f0e2e-125">Exchange UM 자동 전화 교환의 통화 전송</span><span class="sxs-lookup"><span data-stu-id="f0e2e-125">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="f0e2e-126">다른 모든 Exchange UM 시나리오는 제대로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-126">All other Exchange UM scenarios will work properly.</span></span>

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="f0e2e-127">프런트 엔드 풀과 디렉터 풀에 DNS 부하 분산 배포</span><span class="sxs-lookup"><span data-stu-id="f0e2e-127">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="f0e2e-128">프런트 엔드 풀과 디렉터 풀에 DNS 부하 분산을 배포하려면 FQDN 및 DNS 레코드와 관련된 몇 가지 추가 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-128">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>

  - <span data-ttu-id="f0e2e-129">DNS 부하 분산을 사용하는 풀에는 두 개의 FQDN이 있어야 합니다. 하나는 DNS 부하 분산에 사용되고 풀에 있는 서버의 실제 IP를 확인하는 일반적인 풀 FQDN(예: pool01.contoso.com)이고, 또 하나는 풀의 가상 IP 주소를 확인하는 풀의 웹 서비스에 대한 FQDN(예: web01.contoso.com)입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-129">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span>
    
    <span data-ttu-id="f0e2e-130">토폴로지 작성기에서 풀에 대 한 DNS 부하 분산을 배포 하려는 경우 해당 풀의 웹 서비스에 대해이 추가 FQDN을 만들려면 **내부 웹 서비스 풀 Fqdn 재정의** 확인란을 선택 하 고 **이 풀에 대 한 웹 서비스 url 지정** 페이지에서 FQDN을 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-130">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool’s Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>

  - <span data-ttu-id="f0e2e-p107">DNS 부하 분산에 사용되는 FQDN을 지원하려면 풀 FQDN(예: pool01.contoso.com)을 풀에 있는 모든 서버의 IP 주소(예: 192.168.1.1, 192.168.1.2 등)로 확인하는 DNS를 프로비전해야 합니다. 이때 현재 배포된 서버의 IP 주소만 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-p107">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f0e2e-133">프런트 엔드 풀 또는 프런트 엔드 서버가 두 개 이상 있는 경우에는 외부 웹 서비스 FQDN이 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-133">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="f0e2e-134">예를 들어 프런트 엔드 서버의 외부 웹 서비스 FQDN을 <STRONG>pool01.contoso.com</STRONG>로 정의 하는 경우 다른 프런트 엔드 풀 또는 프런트 엔드 서버에 대해 <STRONG>pool01.contoso.com</STRONG> 를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-134">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span> <span data-ttu-id="f0e2e-135">디렉터를 배포 하는 경우에는 모든 디렉터 또는 디렉터 풀에 대해 정의 된 외부 웹 서비스 FQDN은 모든 프런트 엔드 풀 또는 프런트 엔드 서버 뿐만 아니라 다른 디렉터 또는 디렉터 풀에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-135">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="f0e2e-136">내부 웹 서비스를 자체 정의 된 FQDN으로 다시 정의 하려는 경우 각 FQDN은 다른 프런트 엔드 풀, 디렉터 또는 디렉터 풀에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-136">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="f0e2e-137">에지 서버 풀의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="f0e2e-137">DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="f0e2e-p109">에지 서버 풀에 DNS 부하 분산을 배포할 수 있습니다. 이 경우 몇 가지 사항을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-p109">You can deploy DNS load balancing on Edge Server pools. If you do, you must be aware of some considerations.</span></span>

<span data-ttu-id="f0e2e-140">에지 서버에서 DNS 부하 분산을 사용하면 다음과 같은 시나리오에서 장애 조치 기능이 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-140">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>

  - <span data-ttu-id="f0e2e-141">Lync Server 2010 이전 버전의 Office Communications Server를 실행 하는 조직과의 페더레이션</span><span class="sxs-lookup"><span data-stu-id="f0e2e-141">Federation with organizations that are running versions of Office Communications Server released prior to Lync Server 2010.</span></span>

  - <span data-ttu-id="f0e2e-142">공용 IM (인스턴트 메시징) 서비스와 기타 사용자와의 인스턴트 메시지 교환 ( \! 예: Google 대화 같은 XMPP 기반 공급자 및 서버 포함)</span><span class="sxs-lookup"><span data-stu-id="f0e2e-142">Instant message exchange with users of public instant messaging (IM) services AOLand Yahoo\!, in addition to XMPP-based providers and servers, such as Google Talk.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="f0e2e-143">Google 토크는 현재 지원 되는 XMPP 파트너 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-143">Google Talk is currently the only supported XMPP partner.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="f0e2e-144">2012 년 9 월 1 일, Microsoft Lync 공용 IM 연결 사용자 구독 라이선스 ("PIC USL")를 신규 또는 갱신 동의를 위해 더 이상 구매할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-144">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="f0e2e-145">활성 라이선스를 사용 하는 고객은 Yahoo!에 계속 페더레이션 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-145">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="f0e2e-146">서비스 종료 날짜까지 메신저</span><span class="sxs-lookup"><span data-stu-id="f0e2e-146">Messenger until the service shut down date.</span></span> <span data-ttu-id="f0e2e-147">AOL 및 Yahoo!의 6 월 2014 일 종료 날짜</span><span class="sxs-lookup"><span data-stu-id="f0e2e-147">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="f0e2e-148">이 발표 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-148">has been announced.</span></span> <span data-ttu-id="f0e2e-149">자세한 내용은 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013에서 공용 인스턴트 메신저 연결에 대 한 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-149">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P></LI></UL>

    
    </div>

<span data-ttu-id="f0e2e-150">이러한 시나리오는 풀의 모든 에지 서버가 작동되고 실행 중인 한 적용되지만 하나의 에지 서버를 사용할 수 없는 경우 이 서버로 전송되는 요청은 다른 에지 서버로 라우팅되지 않고 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-150">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>

<span data-ttu-id="f0e2e-151">Exchange UM을 사용 하는 경우에는 최소 Exchange 2013을 사용 하 여 Edge에서 Lync Server DNS 부하 분산을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-151">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Lync Server DNS load balancing on Edge.</span></span> <span data-ttu-id="f0e2e-152">이전 버전의 Exchange를 사용 하는 경우 원격 사용자에 게 다음과 같은 Exchange UM 시나리오에 대 한 장애 조치 (failover) 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-152">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>

  - <span data-ttu-id="f0e2e-153">전화기에서 Enterprise Voice 음성 메일 재생</span><span class="sxs-lookup"><span data-stu-id="f0e2e-153">Playing their Enterprise Voice voice mail on their phone</span></span>

  - <span data-ttu-id="f0e2e-154">Exchange UM 자동 전화 교환의 통화 전송</span><span class="sxs-lookup"><span data-stu-id="f0e2e-154">Transferring calls from an Exchange UM Auto Attendant</span></span>

<span data-ttu-id="f0e2e-155">다른 모든 Exchange UM 시나리오는 제대로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-155">All other Exchange UM scenarios will work properly.</span></span>

<span data-ttu-id="f0e2e-p112">내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다. 즉, 한 에지 인터페이스에서는 DNS 부하 분산을 사용하고 다른 에지 인터페이스에서는 하드웨어 부하 분산을 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-p112">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="f0e2e-158">에지 서버 풀에 DNS 부하 분산 배포</span><span class="sxs-lookup"><span data-stu-id="f0e2e-158">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="f0e2e-159">에지 서버 풀의 외부 인터페이스에 DNS 부하 분산을 배포하려면 다음 DNS 항목이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-159">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>

  - <span data-ttu-id="f0e2e-160">액세스에 지 서비스의 경우 풀의 각 서버에 대해 하나의 항목이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-160">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="f0e2e-161">각 항목은 액세스에 지 서비스의 FQDN (예: sip.contoso.com)을 풀에 있는에 지 서버 중 하나에 있는 액세스에 지 서비스의 IP 주소로 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-161">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="f0e2e-162">웹 회의에 지 서비스의 경우 풀의 각 서버에 대해 항목이 하나씩 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-162">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="f0e2e-163">각 항목은 웹 회의에 지 서비스의 FQDN (예: webconf.contoso.com)을 풀에 있는에 지 서버 중 하나에 있는 웹 회의에 지 서비스의 IP 주소로 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-163">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>

  - <span data-ttu-id="f0e2e-164">오디오/비디오에 지 서비스의 경우 풀의 각 서버에 대해 하나의 항목이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-164">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="f0e2e-165">각 항목은 오디오/비디오에 지 서비스의 FQDN (예: av.contoso.com)을 풀에 있는에 지 서버 중 하나에 있는 A/V에 지 서비스의 IP 주소로 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-165">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>

<span data-ttu-id="f0e2e-166">에지 서버 풀의 내부 인터페이스에 DNS 부하 분산을 배포하려면 에지 서버 풀의 내부 FQDN을 풀에 있는 각 서버의 IP 주소로 확인하는 DNS A 레코드를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-166">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="f0e2e-167">중재 서버 풀에서 DNS 부하 분산 사용</span><span class="sxs-lookup"><span data-stu-id="f0e2e-167">Using DNS Load Balancing on Mediation Server Pools</span></span>

<span data-ttu-id="f0e2e-p116">독립 실행형 중재 서버 풀에서 DNS 부하 분산을 사용할 수 있습니다. 모든 SIP 및 미디어 트래픽은 DNS 부하 분산에 의해 균형이 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-p116">You can use DNS load balancing on stand-alone Mediation Server pools. All SIP and media traffic is balanced by DNS load balancing.</span></span>

<span data-ttu-id="f0e2e-170">중재 서버 풀에 DNS 부하 분산을 배포하려면 풀 FQDN(예: mediationpool1.contoso.com)을 풀에 있는 모든 서버의 IP 주소(예: 192.168.1.1, 192.168.1.2 등)로 확인하는 DNS를 프로비전해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-170">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="f0e2e-171">DNS 부하 분산을 사용 하 여 서버에 대 한 트래픽 차단</span><span class="sxs-lookup"><span data-stu-id="f0e2e-171">Blocking Traffic to a Server With DNS Load Balancing</span></span>

<span data-ttu-id="f0e2e-172">DNS 부하 분산을 사용 하는 경우 특정 컴퓨터로의 트래픽을 차단 해야 하는 경우에는 풀 FQDN에서 IP 주소 항목을 제거 하는 것 만으로는 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-172">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="f0e2e-173">또한 컴퓨터에 대 한 DNS 항목도 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-173">You must remove the DNS entry for the computer as well.</span></span>

<span data-ttu-id="f0e2e-174">서버 간 트래픽의 경우 Lync Server 2013에서는 토폴로지를 지 원하는 부하 분산을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-174">Note that for server-to-server traffic, Lync Server 2013 uses topology-aware load balancing.</span></span> <span data-ttu-id="f0e2e-175">서버는 중앙 관리 저장소에서 게시 된 토폴로지를 읽어 토폴로지의 서버 Fqdn을 가져오고 서버 간에 트래픽을 자동으로 분산 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-175">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="f0e2e-176">서버에서 서버 간 트래픽을 수신 하지 못하도록 차단 하려면 토폴로지에서 서버를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0e2e-176">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

