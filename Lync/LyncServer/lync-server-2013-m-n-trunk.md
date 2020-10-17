---
title: 'Lync Server 2013: M:N 트렁크'
description: 'Lync Server 2013: M:N 트렁크'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: M:N trunk
ms:assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398971(v=OCS.15)
ms:contentKeyID: 48185592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e0bcee237128046985b5313a47872ad83bf6513
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542564"
---
# <a name="mn-trunk-in-lync-server-2013"></a><span data-ttu-id="d5ea5-103">Lync Server 2013의 M:N 트렁크</span><span class="sxs-lookup"><span data-stu-id="d5ea5-103">M:N trunk in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5ea5-104">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d5ea5-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d5ea5-105">Lync Server 2013는 이전 릴리스에서 통화 라우팅을 위해 트렁크를 보다 유연 하 게 정의할 지를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-105">Lync Server 2013 supports greater flexibility in the definition of a trunk for call routing purposes from previous releases.</span></span> <span data-ttu-id="d5ea5-106">트렁크는 중재 서버와 수신 대기 포트 번호 (게이트웨이 및 수신 대기 포트 번호) 간의 논리적 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-106">A trunk is a logical association between a Mediation Server and listening port number with a gateway and a listening port number.</span></span> <span data-ttu-id="d5ea5-107">이는 중재 서버에 같은 게이트웨이에 대 한 여러 트렁크 있을 수 있음을 의미 합니다. 중재 서버에는 서로 다른 게이트웨이에 대 한 여러 트렁크 있을 수 있습니다. 반면, 게이트웨이는 중재 서버 마다 여러 트렁크 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-107">This implies several things: A Mediation Server can have multiple trunks to the same gateway; a Mediation Server can have multiple trunks to different gateways; conversely a gateway can have multiple trunks to different Mediation Servers.</span></span>

<span data-ttu-id="d5ea5-108">토폴로지 작성기를 사용 하 여 Lync 토폴로지에 게이트웨이를 추가 하는 경우에도 루트 트렁크를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-108">A root trunk is still required to be created when a gateway is added to the Lync topology using Topology Builder.</span></span> <span data-ttu-id="d5ea5-109">지정 된 중재 서버가 처리할 수 있는 게이트웨이 수는 사용량이 많은 시간에 서버의 처리 용량에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-109">The number of gateways that a given Mediation Server can handle depends on the processing capacity of the server during peak busy hours.</span></span> <span data-ttu-id="d5ea5-110">지원 가능성 설명서에서 [Lync server 2013](lync-server-2013-supported-hardware.md) 에 설명 된 대로 lync server 2013에 대 한 최소 하드웨어 요구 사항을 충족 하는 하드웨어에 중재 서버를 배포 하는 경우 독립 실행형 중재 서버에서 처리할 수 있는 활성 비 바이패스 호출 수가 대략 1000 개 통화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-110">If you deploy a Mediation Server on hardware that exceeds the minimum hardware requirements for Lync Server 2013, as described in [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation, then the estimate of how many active non-bypass calls a stand-alone Mediation Server can handle is approximately 1000 calls.</span></span> <span data-ttu-id="d5ea5-111">이러한 사양을 충족 하는 하드웨어에 배포 하는 경우 중재 서버는 코드 변환을 수행 해야 하지만 게이트웨이가 미디어 바이패스를 지원 하지 않더라도 여러 게이트웨이에 대 한 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-111">When deployed on hardware meeting these specifications, the Mediation Server is expected to perform transcoding, but still route calls for multiple gateways even if the gateways do not support media bypass.</span></span>

<span data-ttu-id="d5ea5-112">통화 경로를 정의 하는 경우 해당 경로와 연결 된 트렁크를 지정 하지만 해당 경로와 연결 된 중재 서버는 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-112">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with that route.</span></span> <span data-ttu-id="d5ea5-113">대신, 토폴로지 작성기를 사용 하 여 트렁크를 중재 서버와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-113">Instead, you use Topology Builder to associate trunks with Mediation Servers.</span></span> <span data-ttu-id="d5ea5-114">즉, 라우팅에서 통화에 사용할 트렁크를 결정 하면 해당 트렁크와 연결 된 중재 서버는 해당 통화에 대 한 신호를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-114">In other words, routing determines which trunk to use for a call, and, subsequently, the Mediation Server associated with that trunk is sent the signaling for that call.</span></span>

<span data-ttu-id="d5ea5-115">중재 서버는 풀로 배포할 수 있습니다. 이 풀은 프런트 엔드 풀을 사용 하 여 배치 된 하거나 독립 실행형 풀로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-115">The Mediation Server can be deployed as a pool; this pool can be collocated with a Front End pool, or it can be deployed as a stand-alone pool.</span></span> <span data-ttu-id="d5ea5-116">중재 서버가 프런트 엔드 풀을 사용 하 여 배치 된 경우 풀 크기는 최대 12 (등록자 풀 크기 제한)가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-116">When a Mediation Server is collocated with a Front End pool, the pool size can be at most 12 (the limit of the Registrar pool size).</span></span> <span data-ttu-id="d5ea5-117">이러한 새로운 기능을 함께 통해 중재 서버에 대 한 안정성 및 배포 유연성이 향상 되지만 다음과 같은 피어 엔터티에서 관련 기능이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-117">Taken together, these new capabilities increase the reliability and deployment flexibility for Mediation Servers, but they require associated capabilities in the following peer entities:</span></span>

  - <span data-ttu-id="d5ea5-118">**PSTN 게이트웨이**</span><span class="sxs-lookup"><span data-stu-id="d5ea5-118">**PSTN gateway.**</span></span> <span data-ttu-id="d5ea5-119">Lync Server 2013 적격 게이트웨이는 DNS 부하 분산을 구현 해야 하며,이 경우 정규화 된 공공 전화망 (PSTN) 게이트웨이가 하나의 중재 서버 풀에 대 한 부하 분산 장치로 작동할 수 있으며, 따라서 풀 전체에 걸쳐 통화 부하를 분산 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-119">A Lync Server 2013 qualified gateway must implement DNS load balancing, which enables a qualified public switched telephone network (PSTN) gateway to act as a load balancer for one pool of Mediation Servers, and thereby to load-balance calls across the pool.</span></span>

  - <span data-ttu-id="d5ea5-120">**세션 테두리 컨트롤러입니다.**</span><span class="sxs-lookup"><span data-stu-id="d5ea5-120">**Session Border Controller.**</span></span> <span data-ttu-id="d5ea5-121">SIP 트렁크의 경우 피어 엔터티는 인터넷 전화 통신 서비스 공급자의 SBC (세션 경계 컨트롤러)입니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-121">For a SIP trunk, the peer entity is a Session Border Controller (SBC) at an Internet telephony service provider.</span></span> <span data-ttu-id="d5ea5-122">중재 서버 풀에서 SBC 까지의 방향으로 SBC는 풀의 중재 서버에서 연결을 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-122">In the direction from the Mediation Server pool to the SBC, the SBC can receive connections from any Mediation Server in the pool.</span></span> <span data-ttu-id="d5ea5-123">SBC에서 풀로의 방향으로, 풀의 중재 서버에 트래픽을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-123">In the direction from the SBC to the pool, traffic can be sent to any Mediation Server in the pool.</span></span> <span data-ttu-id="d5ea5-124">서비스 공급자 및 SBC에서 지 원하는 경우 DNS 부하 분산을 통해이를 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-124">One method of achieving this is through DNS load balancing, if supported by the service provider and SBC.</span></span> <span data-ttu-id="d5ea5-125">또 다른 방법은 서비스 공급자에 게 풀에 있는 모든 중재 서버의 IP 주소를 제공 하 고, 서비스 공급자는 각 중재 서버에 대 한 별도의 SIP 트렁크로이를 SBC에 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-125">An alternative is to give the service provider the IP addresses of all Mediation Servers in the pool, and the service provider will provision these in their SBC as a separate SIP trunk for each Mediation Server.</span></span> <span data-ttu-id="d5ea5-126">그러면 서비스 공급자는 자체 서버에 대 한 부하 분산을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-126">The service provider will then handle the load balancing for its own servers.</span></span> <span data-ttu-id="d5ea5-127">일부 서비스 공급자 또는 sbc는 이러한 기능을 지원 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-127">Not all service providers or SBCs may support these capabilities.</span></span> <span data-ttu-id="d5ea5-128">또한 서비스 공급자는이 기능에 대 한 추가 요금을 부과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-128">Furthermore, the service provider may charge extra for this capability.</span></span> <span data-ttu-id="d5ea5-129">일반적으로 SBC로의 각 SIP 트렁크는 월별 수수료를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-129">Typically, each SIP trunk to the SBC incurs a monthly fee.</span></span>

  - <span data-ttu-id="d5ea5-130">**IP-PBX**</span><span class="sxs-lookup"><span data-stu-id="d5ea5-130">**IP-PBX.**</span></span> <span data-ttu-id="d5ea5-131">중재 서버 풀에서 IP PBX SIP 종료 까지의 방향의 IP-PBX는 풀의 중재 서버에서 연결을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-131">In the direction from the Mediation Server pool to the IP-PBX SIP termination, the IP-PBX can receive connections from any Mediation Server in the pool.</span></span> <span data-ttu-id="d5ea5-132">IP-PBX에서 풀로 향하는 트래픽은 풀의 중재 서버에 트래픽을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-132">In the direction from the IP-PBX to the pool, traffic can be sent to any Mediation Server in the pool.</span></span> <span data-ttu-id="d5ea5-133">대부분의 IP-PBXs는 DNS 부하 분산을 지원 하지 않으므로 각 직접 SIP 연결을 IP PBX에서 풀의 각 중재 서버로 정의 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-133">Because most IP-PBXs do not support DNS load balancing, we recommend that individual direct SIP connections be defined from the IP-PBX to each Mediation Server in the pool.</span></span> <span data-ttu-id="d5ea5-134">그러면 IP-PBX는 트렁크 그룹을 통해 트래픽을 분산 하 여 자체 부하 분산을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-134">The IP-PBX will then handle its own load balancing by distributing traffic over the trunk group.</span></span> <span data-ttu-id="d5ea5-135">이는 트렁크 그룹의 IP-PBX에 일관 된 라우팅 규칙 집합이 있다는 것을 전제로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-135">The assumption is that the trunk group has a consistent set of routing rules at the IP-PBX.</span></span> <span data-ttu-id="d5ea5-136">특정 IP-PBX가이 트렁크 그룹 개념을 지원 하 고이를 IP PBX의 자체 중복성과 어떻게 교차할 지에 관계 없이 중재 서버 클러스터가 IP PBX와 올바르게 상호 작용할 수 있는지 여부를 결정 하기 전에 클러스터링 아키텍처를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-136">Whether a particular IP-PBX supports this trunk group concept and how it intersects with the IP-PBX’s own redundancy and clustering architecture needs to be determined before you can decide whether a Mediation Server cluster can interact correctly with an IP-PBX.</span></span>

<span data-ttu-id="d5ea5-137">중재 서버 풀에는 상호 작용 하는 피어 게이트웨이가 균일 하 게 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-137">A Mediation Server pool must have a uniform view of the peer gateway with which it interacts.</span></span> <span data-ttu-id="d5ea5-138">즉, 풀의 모든 구성원이 구성 저장소에서 피어 게이트웨이의 동일한 정의에 액세스 하 고 나가는 호출을 위해 상호 작용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-138">This means that all members of the pool access the same definition of the peer gateway from the configuration store and are equally likely to interact with it for outgoing calls.</span></span> <span data-ttu-id="d5ea5-139">따라서 일부 중재 서버가 나가는 통화에 대해 특정 게이트웨이 피어와도 통신 하도록 풀을 분할할 수 있는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-139">Therefore, there is no way to segment the pool so that some Mediation Servers communicate with only certain gateway peers for outgoing calls.</span></span> <span data-ttu-id="d5ea5-140">이러한 조각화가 필요한 경우 별도의 중재 서버 풀을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-140">If such segmentation is necessary, a separate pool of Mediation Servers must be used.</span></span> <span data-ttu-id="d5ea5-141">예를 들어이 항목의 앞부분에서 설명한 대로 PSTN 게이트웨이, SIP 트렁크 또는 IP-PBXs와 상호 작용 하는 데 사용 되는 연결 된 기능이 없는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-141">This would be the case, for example, if the associated capabilities in PSTN gateways, SIP trunks, or IP-PBXs to interact with a pool as detailed earlier in this topic are not present.</span></span>

<span data-ttu-id="d5ea5-142">특정 PSTN 게이트웨이, IP-PBX 또는 SIP 트렁크 피어는 여러 중재 서버 또는 트렁크으로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-142">A particular PSTN gateway, IP-PBX, or SIP trunk peer can route to multiple Mediation Servers or trunks.</span></span> <span data-ttu-id="d5ea5-143">중재 서버의 특정 풀이 제어할 수 있는 게이트웨이 수는 미디어 바이패스를 사용 하는 호출 수에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-143">The number of gateways that a particular pool of Mediation Servers can control depends on the number of calls that use media bypass.</span></span> <span data-ttu-id="d5ea5-144">많은 수의 통화에서 미디어 바이패스를 사용 하는 경우에는 신호 계층 처리만 필요 하기 때문에 풀의 중재 서버가 더 많은 통화를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5ea5-144">If a large number of calls use media bypass, a Mediation Server in the pool can handle many more calls, because only signaling layer processing is necessary.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

