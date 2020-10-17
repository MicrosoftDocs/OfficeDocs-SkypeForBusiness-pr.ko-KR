---
title: 'Lync Server 2013: 하드웨어 부하 분산 장치로 확장 된 통합에 지'
description: 'Lync Server 2013: 하드웨어 부하 분산 장치로 확장 된 통합에 지'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 808c03e0d6f2836719599c6cad9ec83e1c96b207
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547654"
---
# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="ca890-103">Lync Server 2013의 하드웨어 부하 분산 장치로 확장 된 통합에 지</span><span class="sxs-lookup"><span data-stu-id="ca890-103">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca890-104">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="ca890-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="ca890-105">에 지 풀 토폴로지에서는 두 개 이상의에 지 서버가 데이터 센터 경계 네트워크에서 부하 분산 풀로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-105">In the Edge pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="ca890-106">하드웨어 부하 분산은 외부 및 내부에 지 서버 인터페이스 둘 다에 대 한 트래픽에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-106">Hardware load balancing is used for traffic to both the external and internal Edge Server interfaces.</span></span>

<span data-ttu-id="ca890-107">조직에서 15000 개 이상의 액세스에 지 서비스 클라이언트 연결, 1000 활성 웹 회의에 지 서비스 클라이언트 연결 또는 500 동시 A/V에 지 서비스 세션을 지원 해야 하 고에 지 서버의 고가용성이 중요 한 경우이 토폴로지는 확장성 및 장애 조치 (failover) 지원의 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-107">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Web Conferencing Edge service client connections, or 500 concurrent A/V Edge service sessions, and high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="ca890-108">이 그림에는에 지 서버와 프런트 엔드 풀 또는 서버 간에 내부 네트워크에 배포 된 선택적 서버 역할인 디렉터는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-108">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="ca890-109">.</span><span class="sxs-lookup"><span data-stu-id="ca890-109">.</span></span> <span data-ttu-id="ca890-110">디렉터 토폴로지에 대 한 자세한 내용은 [Lync Server 2013의 디렉터에 필요한 구성 요소](lync-server-2013-components-required-for-the-director.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca890-110">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca890-111">표시된 그림은 설명을 위한 예제 IP 주소 지정을 보여주며, 정확한 수신 및 송신 트래픽을 사용한 실제 통신 흐름을 나타내지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-111">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="ca890-112">이 그림은 발생 가능한 트래픽을 대략적으로 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-112">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="ca890-113">수신(수신 대기 중인 포트로) 및 송신(대상 서버 또는 클라이언트로)과 관련된 트래픽 흐름의 세부 사항은 각 시나리오의 포트 요약 다이어그램에 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-113">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="ca890-114">예를 들어 TCP 443은 실제로 인바운드 (Edge Server 또는 역방향 프록시)에만 사용 되며 프로토콜 (TCP) 측면에서 양방향 흐름입니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-114">For example, TCP 443 is actually inbound (to the Edge Server or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="ca890-115">또한 이 그림에서는 NAT(network address translation)가 발생할 때 변경되는 트래픽의 특성을 보여줍니다(인바운드 시 대상 주소가 변경되고 아웃바운드 시 원본 주소가 변경됨).</span><span class="sxs-lookup"><span data-stu-id="ca890-115">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="ca890-116">외부 및 내부 방화벽 예와 서버 인터페이스는 참조 목적으로만 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-116">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="ca890-117">마지막으로 적용 가능한 경우 기본 게이트웨이 및 경로 관계 예가 표시되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-117">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="ca890-118">또한 다이어그램은 <EM>.Com</EM> dns 영역을 사용 하 여 역방향 프록시와에 지 서버 둘 다에 대해 외부 dns 영역을 나타내지만, <EM>.net</EM> dns 영역은 내부 dns 영역을 참조 한다는 점에 유의 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca890-118">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="ca890-119">Microsoft Lync Server 2013의 새로운 기능에서는 IPv6 주소 지정을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-119">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="ca890-120">IPv4 주소와 거의 마찬가지로 IPv6 주소를 할당할 때 할당된 IPv6 주소 공간에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-120">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="ca890-121">이 문서에 사용된 주소는 오직 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-121">The addresses in this topic are for example only.</span></span> <span data-ttu-id="ca890-122">배포 환경에서 작동하고 올바른 범위를 제공하며 내/외부 주소와 통합되는 IPv6 주소를 보유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-122">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="ca890-123">Windows Server에서는 IPv6 작업을 전환 하는 중요 한 기능과 *이중 스택*이라고 하는 ipv6 통신에 대 한 IPv4를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-123">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="ca890-124">이중 스택은 IPv4 및 IPv6 각각에 대한 별도의 네트워크 스택입니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-124">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="ca890-125">이중 스택을 사용하면 IPv4 및 IPv6의 주소를 동시에 할당할 수 있을 뿐 아니라 서버가 각 요구 사항에 기반하여 다른 호스트 및 클라이언트와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-125">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="ca890-126">IPv6 주소 지정에 사용할 일반적인 주소 유형은 IPv6 글로벌 주소 (공용 IPv4 주소와 유사함), ipv6 고유 로컬 주소 (개인 IPv4 주소 범위와 비슷함) 및 IPv6 링크 로컬 주소 (Windows Server의 IPv4의 경우 자동 개인 IP 주소와 유사함)가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-126">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="ca890-127">NAT IPv6에서 IPv4로의 변환(주로 NAT64라고 함) 및 NAT IPv6에서 IPv6로의 변환(주로 NAT66라고 함)을 허용하는 IPv6의 NAT(네트워크 주소 변환) 기술이 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-127">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="ca890-128">NAT 기술이 있다는 것은 Lync Server에 지 서버에 대해 제공 되는 5 가지 시나리오가 여전히 유효한 것임을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-128">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="ca890-129">IPv6은 복잡 한 주제 이며, Windows server 수준 및 Lync Server 2013 수준에서 할당 하는 주소가 예상 대로 작동 하는지 확인 하기 위해 네트워킹 팀 및 인터넷 공급자와의 신중한 계획이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-129">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="ca890-130">IPv6 주소 지정 및 계획에 대한 추가 리소스는 이 항목의 끝에 있는 링크를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca890-130">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="ca890-131">**하드웨어 부하 분산 장치 구성**</span><span class="sxs-lookup"><span data-stu-id="ca890-131">**Hardware Load Balancer Configuration**</span></span>

<span data-ttu-id="ca890-132">자세한 내용은 [Lync Server 2013의 외부 사용자 액세스에 필요한 구성 요소의](lync-server-2013-components-required-for-external-user-access.md)"A/V에 지에 대 한 하드웨어 부하 분산 장치 요구 사항" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ca890-132">For details, see the “Hardware Load Balancer Requirements for A/V Edge” section in [Components required for external user access in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).</span></span>

<span data-ttu-id="ca890-133">**확장 통합 에지 토폴로지(하드웨어 부하 분산됨)**</span><span class="sxs-lookup"><span data-stu-id="ca890-133">**Scaled consolidated edge topology (hardware load balanced)**</span></span>

<span data-ttu-id="ca890-134">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span><span class="sxs-lookup"><span data-stu-id="ca890-134">![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ca890-135">CAC (통화 허용 제어)를 사용 하는 경우에도에 지 서버 내부 인터페이스에 IPv4 주소를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-135">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="ca890-136">CAC는 IPv4 주소를 사용하며, 작동을 위해 이를 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca890-136">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ca890-137">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="ca890-137">In This Section</span></span>

  - [<span data-ttu-id="ca890-138">Lync Server 2013의 인증서 요약-하드웨어 부하 분산 장치로 확장 된 통합에 지</span><span class="sxs-lookup"><span data-stu-id="ca890-138">Certificate summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="ca890-139">포트 요약-Lync Server 2013의 하드웨어 부하 분산 장치로 확장 된 통합에 지</span><span class="sxs-lookup"><span data-stu-id="ca890-139">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="ca890-140">Lync Server 2013의 DNS 요약-하드웨어 부하 분산 장치로 확장 된 통합에 지</span><span class="sxs-lookup"><span data-stu-id="ca890-140">DNS summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca890-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca890-141">See Also</span></span>


[<span data-ttu-id="ca890-142">IP 버전 6 주소 지정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="ca890-142">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="ca890-143">IPv6 글로벌 유니캐스트 주소 형식</span><span class="sxs-lookup"><span data-stu-id="ca890-143">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="ca890-144">고유한 로컬 IPv6 유니캐스트 주소</span><span class="sxs-lookup"><span data-stu-id="ca890-144">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

