---
title: 'Lync Server 2013: 공용 IP 주소의 단일 통합 에지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with public IP addresses
ms:assetid: a92d1179-6a1f-4efe-908a-f8dfc5024f30
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205148(v=OCS.15)
ms:contentKeyID: 48185035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8189d360a43887e2992b8b8abf063ef96230e06e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="6010e-102">Lync Server 2013의 공용 IP 주소의 단일 통합 에지</span><span class="sxs-lookup"><span data-stu-id="6010e-102">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6010e-103">_**마지막으로 수정한 주제:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="6010e-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="6010e-104">조직의 15000 액세스에 대 한 Edge 서비스 클라이언트 연결에 대 한 지원이 필요 하 고, 1000 활성 Lync Server 웹 회의 서비스 클라이언트 연결 및 500 동시 A/V Edge 세션을 사용 하 고, Edge 서버의 가용성이 중요 하지 않은 경우,이 토폴로지에서는 낮은 하드웨어 비용 및 간단한 배포의 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-104">If your organization needs support for fewer than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, and 500 concurrent A/V Edge sessions, and high availability of the Edge Server is not important, this topology offers the advantages of lower hardware cost and simpler deployment.</span></span> <span data-ttu-id="6010e-105">용량이 더 많이 필요 하거나 고가용성이 필요한 경우에는 배율 조정 된 통합에 지 서버 토폴로지를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-105">If you need greater capacity or you require high availability, you should deploy a scaled consolidated Edge Server topology.</span></span>

  - <span></span>  
    [<span data-ttu-id="6010e-106">Lync Server 2013의 조정된 통합 에지, NAT 사용 개인 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="6010e-106">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [<span data-ttu-id="6010e-107">Lync Server 2013의 조정된 통합 에지, 공용 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="6010e-107">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [<span data-ttu-id="6010e-108">Lync Server 2013의 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지</span><span class="sxs-lookup"><span data-stu-id="6010e-108">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6010e-109">Edge 서버에서 공용 IP 주소를 사용 하는 경우에는 Edge 서버의 기본 게이트웨이가 더 이상 방화벽 또는 라우터가 아니지만 공용 경계에 있는 라우터 또는 방화벽으로 공용 주소가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-109">When using public IP address on the Edge Server, the default gateway on the Edge Server is no longer your firewall or router, but the router or firewall at your public perimeter edge – which will be a public address.</span></span> <span data-ttu-id="6010e-110">역방향 프록시는 가장 바깥쪽 경계 네트워크와 연결 된 라우터 또는 방화벽을 계속 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-110">The reverse proxy continues to use the router or firewall associated with the outermost perimeter network.</span></span> <span data-ttu-id="6010e-111">역방향 프록시와 공용 IP 주소에 대 한 Edge 서버의 차이점은 역방향 프록시는 여전히 NAT를 사용 하 고 있고 Edge 서버는 경로 관계를 사용 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-111">The difference between the reverse proxy and the Edge Server with public IP addresses is that the reverse proxy is still using NAT and the Edge Server is using a route relationship.</span></span>



</div>

<span data-ttu-id="6010e-112">이 그림에는 Edge 서버와 프런트 엔드 풀 또는 서버 간의 내부 네트워크에 배포 된 선택적 서버 역할인 디렉터가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-112">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="6010e-113">디렉터 토폴로지에 대 한 자세한 내용은 [Lync Server 2013의 디렉터에 필요한 구성 요소](lync-server-2013-components-required-for-the-director.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6010e-113">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="6010e-114">그림은 단일 역 프록시를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-114">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6010e-115">표시 되는 그림은 IP 주소 지정 방향과 예에 대 한 것 이지만 올바른 들어오고 나가는 트래픽에 대 한 실제 통신 흐름을 나타내지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-115">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="6010e-116">이 그림은 가능 소통량에 대 한 높은 수준의 보기를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-116">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="6010e-117">수신 (수신 대기 포트)에 관련 된 트래픽 흐름에 대 한 세부 정보 및 보내는 (대상 서버 또는 클라이언트에 게)는 각 시나리오의 포트 요약 다이어그램에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-117">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="6010e-118">예를 들어 TCP 443는 실제로 경계 (Edge 또는 리버스 프록시)에만 사용할 수 있으며, 프로토콜 (TCP) 관점에서 양방향 으로만 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-118">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="6010e-119">또한이 그림에는 NAT (네트워크 주소 변환)가 발생할 때 변경 되는 트래픽 특성 (대상 주소는 인바운드에서 변경 되 고 원본 주소는 아웃 바운드로 변경 됨)이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-119">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="6010e-120">외부 및 내부 방화벽 예제와 서버 인터페이스가 참조용 으로만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-120">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="6010e-121">마지막으로, 해당 하는 경우 기본 게이트웨이 및 경로 관계 예를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-121">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="6010e-122">또한 다이어그램은 <EM>.Com</EM> dns 영역을 사용 하 여 역방향 프록시와 경계 서버 모두에 대해 외부 dns 영역을 표시 하 고, <EM>.net</EM> dns 영역은 내부 DNS 영역을 참조 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="6010e-122">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="6010e-123">Microsoft Lync Server 2013에 대 한 새로운 기능은 IPv6 주소 지정을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-123">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="6010e-124">IPv4 주소 지정과 매우 유사 하 게 IPv6 주소는 지정 된 IPv6 주소 공간의 일부인 방식으로 할당 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-124">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="6010e-125">이 항목의 주소는 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-125">The addresses in this topic are for example only.</span></span> <span data-ttu-id="6010e-126">배포에서 작동 하는 IPv6 주소를 확보 하 고 올바른 범위를 제공 하 고 내부 및 외부 주소 지정과 상호 운용 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-126">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="6010e-127">Windows Server는 IPv6 작업을 전환 하는 데 중요 한 기능과 *이중 스택*이라는 ipv6 통신에 IPv4를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-127">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="6010e-128">이중 스택은 IPv4 및 IPv6에 대 한 별도의 개별 네트워크 스택입니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-128">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="6010e-129">이중 스택은 IPv4 및 IPv6에 대 한 주소 지정을 동시에 할당할 수 있도록 허용 하 고 서버가 요구 사항에 따라 다른 호스트 및 클라이언트와 통신할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-129">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="6010e-130">Ipv6 주소 지정에 사용 하는 일반적인 주소 유형은 IPv6 전역 주소 (공용 IPv4 주소와 유사), IPv6 고유 로컬 주소 (개인 IPv4 주소 범위와 유사) 및 IPv6 링크 로컬 주소 (자동 개인 IP와 유사)가 됩니다. IPv4 용 Windows Server의 주소)</span><span class="sxs-lookup"><span data-stu-id="6010e-130">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="6010e-131">IPv6에 대 한 nat (Network address translation) (네트워크 주소 변환 기술)는 NAT IPv6에서 IPv4 (일반적으로 NAT64로 지칭 됨)로, 그리고 IPv6에 대 한 NAT IPv6의 경우 (일반적으로 NAT66 이라고 함)에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-131">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="6010e-132">NAT 기술이 있으면 Lync Server Edge 서버에 대해 제공 되는 5 가지 시나리오가 여전히 유효 하다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-132">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="6010e-133">IPv6은 복잡 한 항목이 며, 네트워크 팀과 인터넷 공급자를 사용 하 여 Windows server 수준 및 Lync Server 2013 수준에서 할당 하는 주소가 예상 대로 작동 하는지 확인 하는 데 세심 한 계획이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-133">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="6010e-134">IPv6 주소 지정 및 계획에 대 한 추가 리소스는이 항목의 끝부분에 있는 링크를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6010e-134">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="6010e-135">**공용 IP 주소 토폴로지가 있는 단일 통합 된 Edge**</span><span class="sxs-lookup"><span data-stu-id="6010e-135">**Single Consolidated Edge with Public IP Addresses topology**</span></span>

<span data-ttu-id="6010e-136">![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")</span><span class="sxs-lookup"><span data-stu-id="6010e-136">![2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d](images/JJ205148.2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d(OCS.15).jpg "2db9f9e1-75aa-4de0-ab3f-c6effddb4f4d")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6010e-137">CAC (Call 허용 제어)를 사용 하는 경우에도 Edge Server 내부 인터페이스에 IPv4 주소를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-137">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="6010e-138">CAC는 IPv4 주소를 사용 하며 작동 하는 데 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6010e-138">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6010e-139">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="6010e-139">In This Section</span></span>

  - [<span data-ttu-id="6010e-140">Lync Server 2013의 인증서 요약 - 공용 IP 주소의 단일 통합 에지</span><span class="sxs-lookup"><span data-stu-id="6010e-140">Certificate summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="6010e-141">Lync Server 2013의 포트 요약 - 공용 IP 주소의 단일 통합 에지</span><span class="sxs-lookup"><span data-stu-id="6010e-141">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="6010e-142">Lync Server 2013의 DNS 요약 - 공용 IP 주소의 단일 통합 에지</span><span class="sxs-lookup"><span data-stu-id="6010e-142">DNS summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-single-consolidated-edge-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6010e-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6010e-143">See Also</span></span>


[<span data-ttu-id="6010e-144">IP 버전 6 주소 지정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="6010e-144">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="6010e-145">IPv6 글로벌 유니캐스트 주소 형식</span><span class="sxs-lookup"><span data-stu-id="6010e-145">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="6010e-146">고유한 로컬 IPv6 유니캐스트 주소</span><span class="sxs-lookup"><span data-stu-id="6010e-146">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

