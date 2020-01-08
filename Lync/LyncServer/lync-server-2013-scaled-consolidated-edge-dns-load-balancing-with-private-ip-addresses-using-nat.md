---
title: 'Lync Server 2013: 조정된 통합 에지, NAT 사용 개인 IP 주소의 DNS 부하 분산'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: c7ca4ca8-c639-4d93-86d7-8891170cacbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398823(v=OCS.15)
ms:contentKeyID: 48185369
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ccae081e80b61be767dfbdc82664ff90d4dfabd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="95298-102">Lync Server 2013의 조정된 통합 에지, NAT 사용 개인 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="95298-102">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95298-103">_**마지막으로 수정한 주제:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="95298-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="95298-104">Edge 서버 풀 토폴로지에서는 두 개 이상의 Edge 서버가 데이터 센터의 경계 네트워크에 부하 분산 풀로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95298-104">In the Edge Server pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="95298-105">DNS (Domain Name System) 부하 분산이 외부 및 내부 Edge 인터페이스에 대 한 트래픽 소통에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95298-105">Domain Name System (DNS) load balancing is used for traffic to both the external and internal Edge interfaces.</span></span>

<span data-ttu-id="95298-106">조직에서 15000 이상의 액세스에 지 서비스 클라이언트 연결을 지원 해야 하는 경우, 1000 활성 Lync Server 웹 회의 서비스 클라이언트 연결 또는 500 동시 A/V Edge 세션을 사용 하거나, Edge 서버의 가용성을 높게 하는 것이 중요 한 경우이 토폴로지에서는 확장성 및 장애 조치 지원의 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="95298-106">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, or 500 concurrent A/V Edge sessions, and/or high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="95298-107">이 그림에는 Edge 서버와 프런트 엔드 풀 또는 서버 간의 내부 네트워크에 배포 된 선택적 서버 역할인 디렉터가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95298-107">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="95298-108">디렉터 토폴로지에 대 한 자세한 내용은 [Lync Server 2013의 디렉터에 필요한 구성 요소](lync-server-2013-components-required-for-the-director.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="95298-108">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="95298-109">그림은 단일 역 프록시를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="95298-109">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="95298-110">표시 되는 그림은 IP 주소 지정 방향과 예에 대 한 것 이지만 올바른 들어오고 나가는 트래픽에 대 한 실제 통신 흐름을 나타내지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95298-110">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="95298-111">이 그림은 가능 소통량에 대 한 높은 수준의 보기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="95298-111">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="95298-112">수신 (수신 대기 포트)에 관련 된 트래픽 흐름에 대 한 세부 정보 및 보내는 (대상 서버 또는 클라이언트에 게)는 각 시나리오의 포트 요약 다이어그램에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95298-112">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="95298-113">예를 들어 TCP 443는 실제로 경계 (Edge 또는 리버스 프록시)에만 사용할 수 있으며, 프로토콜 (TCP) 관점에서 양방향 으로만 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95298-113">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="95298-114">또한이 그림에는 NAT (네트워크 주소 변환)가 발생할 때 변경 되는 트래픽 특성 (대상 주소는 인바운드에서 변경 되 고 원본 주소는 아웃 바운드로 변경 됨)이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95298-114">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="95298-115">외부 및 내부 방화벽 예제와 서버 인터페이스가 참조용 으로만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95298-115">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="95298-116">마지막으로, 해당 하는 경우 기본 게이트웨이 및 경로 관계 예를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="95298-116">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="95298-117">또한 다이어그램은 <EM>.Com</EM> dns 영역을 사용 하 여 역방향 프록시와 경계 서버 모두에 대해 외부 dns 영역을 표시 하 고, <EM>.net</EM> dns 영역은 내부 DNS 영역을 참조 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="95298-117">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="95298-118">Microsoft Lync Server 2013에 대 한 새로운 기능은 IPv6 주소 지정을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="95298-118">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="95298-119">IPv4 주소 지정과 매우 유사 하 게 IPv6 주소는 지정 된 IPv6 주소 공간의 일부인 방식으로 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95298-119">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="95298-120">이 항목의 주소는 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="95298-120">The addresses in this topic are for example only.</span></span> <span data-ttu-id="95298-121">배포에서 작동 하는 IPv6 주소를 확보 하 고 올바른 범위를 제공 하 고 내부 및 외부 주소 지정과 상호 운용 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95298-121">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="95298-122">Windows Server는 IPv6 작업을 전환 하는 데 중요 한 기능과 *이중 스택*이라는 ipv6 통신에 IPv4를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="95298-122">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="95298-123">이중 스택은 IPv4 및 IPv6에 대 한 별도의 개별 네트워크 스택입니다.</span><span class="sxs-lookup"><span data-stu-id="95298-123">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="95298-124">이중 스택은 IPv4 및 IPv6에 대 한 주소 지정을 동시에 할당할 수 있도록 허용 하 고 서버가 요구 사항에 따라 다른 호스트 및 클라이언트와 통신할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="95298-124">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="95298-125">Ipv6 주소 지정에 사용 하는 일반적인 주소 유형은 IPv6 전역 주소 (공용 IPv4 주소와 유사), IPv6 고유 로컬 주소 (개인 IPv4 주소 범위와 유사) 및 IPv6 링크 로컬 주소 (자동 개인 IP와 유사)가 됩니다. IPv4 용 Windows Server의 주소)</span><span class="sxs-lookup"><span data-stu-id="95298-125">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="95298-126">IPv6에 대 한 nat (Network address translation) (네트워크 주소 변환 기술)는 NAT IPv6에서 IPv4 (일반적으로 NAT64로 지칭 됨)로, 그리고 IPv6에 대 한 NAT IPv6의 경우 (일반적으로 NAT66 이라고 함)에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95298-126">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="95298-127">NAT 기술이 있으면 Lync Server Edge 서버에 대해 제공 되는 5 가지 시나리오가 여전히 유효 하다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="95298-127">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="95298-128">IPv6은 복잡 한 항목이 며, 네트워크 팀과 인터넷 공급자를 사용 하 여 Windows server 수준 및 Lync Server 2013 수준에서 할당 하는 주소가 예상 대로 작동 하는지 확인 하는 데 세심 한 계획이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="95298-128">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="95298-129">IPv6 주소 지정 및 계획에 대 한 추가 리소스는이 항목의 끝부분에 있는 링크를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="95298-129">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="95298-130">![899546d4-2eef-44d2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef-44d2-8317-51c5f699cd2a")</span><span class="sxs-lookup"><span data-stu-id="95298-130">![899546d4-2eef-44d2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef-44d2-8317-51c5f699cd2a")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="95298-131">CAC (Call 허용 제어)를 사용 하는 경우에도 Edge Server 내부 인터페이스에 IPv4 주소를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95298-131">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="95298-132">CAC는 IPv4 주소를 사용 하며 작동 하는 데 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95298-132">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="95298-133">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="95298-133">In This Section</span></span>

  - [<span data-ttu-id="95298-134">Lync Server 2013의 인증서 요약 - 조정된 통합 에지, NAT 사용 개인 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="95298-134">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="95298-135">Lync Server 2013의 포트 요약 - 조정된 통합 에지, NAT 사용 개인 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="95298-135">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="95298-136">Lync Server 2013의 DNS 요약 - 조정된 통합 에지, NAT 사용 개인 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="95298-136">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="95298-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95298-137">See Also</span></span>


[<span data-ttu-id="95298-138">IP 버전 6 주소 지정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="95298-138">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="95298-139">IPv6 글로벌 유니캐스트 주소 형식</span><span class="sxs-lookup"><span data-stu-id="95298-139">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="95298-140">고유한 로컬 IPv6 유니캐스트 주소</span><span class="sxs-lookup"><span data-stu-id="95298-140">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

