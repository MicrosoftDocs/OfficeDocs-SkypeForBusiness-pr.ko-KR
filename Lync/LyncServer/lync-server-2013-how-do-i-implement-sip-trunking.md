---
title: 'Lync Server 2013: SIP 트렁크 구현 방법은 무엇입니까?'
description: 'Lync Server 2013: SIP 트렁크를 구현 하려면 어떻게 해야 하나요?'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10882adc0bff573868dcd07268ed0446385d895c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553154"
---
# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="3beb8-103">Lync Server 2013에서 SIP 트렁크를 구현 하려면 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="3beb8-103">How do I implement SIP trunking in Lync Server 2013?</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3beb8-104">_**마지막으로 수정 된 항목:** 2013-03-18_</span><span class="sxs-lookup"><span data-stu-id="3beb8-104">_**Topic Last Modified:** 2013-03-18_</span></span>

<span data-ttu-id="3beb8-105">SIP 트렁크을 구현 하려면 필요에 따라 Lync Server 2013 클라이언트와 서비스 공급자 및 코드 미디어 간의 통신 세션에 대 한 프록시 역할을 하는 중재 서버를 통해 연결을 라우팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-105">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="3beb8-106">각 중재 서버에는 내부 네트워크 인터페이스와 외부 네트워크 인터페이스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-106">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="3beb8-107">내부 인터페이스가 프런트 엔드 서버에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-107">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="3beb8-108">외부 인터페이스는 전통적으로 중재 서버를 PSTN (공중 전화망) 게이트웨이 또는 IP-PBX에 연결 하는 데 사용 되므로 일반적으로 게이트웨이 인터페이스 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-108">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="3beb8-109">SIP 트렁크를 구현 하려면 중재 서버의 외부 인터페이스를 ITSP의 외부에 지 구성 요소에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-109">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3beb8-110">ITSP의 외부에 지 구성 요소는 SBC (세션 경계 컨트롤러), 라우터 또는 gateway 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-110">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>



</div>

<span data-ttu-id="3beb8-111">중재 서버에 대 한 자세한 내용은 [Lync server 2013의 중재 서버 구성 요소](lync-server-2013-mediation-server-component.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3beb8-111">For details about Mediation Servers, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md).</span></span>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="3beb8-112">중앙 집중식 SIP 트렁크와 분산형 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="3beb8-112">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="3beb8-113">*중앙 집중식* SIP 트렁크는 분기 사이트 트래픽을 비롯 한 모든 VoIP (Voice over Internet Protocol) 트래픽을 중앙 사이트를 통해 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-113">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="3beb8-114">중앙 집중식 배포 모델은 비용 효율이 간단 하며 Lync Server 2013을 사용 하 여 SIP 트렁크을 구현 하는 경우에는 일반적으로 권장 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-114">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="3beb8-115">*분산* 된 SIP 트렁크는 하나 이상의 분기 사이트에서 로컬 SIP 트렁크를 구현 하는 배포 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-115">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="3beb8-116">그러면 VoIP 트래픽은 중앙 사이트를 거치지 않고 분기 사이트에서 서비스 공급자로 직접 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-116">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="3beb8-117">분산형 SIP 트렁크는 다음과 같은 경우에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-117">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="3beb8-118">분기 사이트에 지속 가능한 전화 연결(예: WAN이 다운된 경우)이 필요한 경우.</span><span class="sxs-lookup"><span data-stu-id="3beb8-118">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="3beb8-119">각 분기 사이트에 대해이 요구 사항을 분석 해야 합니다. 일부 분기에는 중복 및 장애 조치 (failover)가 필요할 수 있지만 그렇지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-119">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

  - <span data-ttu-id="3beb8-120">두 중앙 사이트 사이에 복원성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-120">Resiliency is required between two central sites.</span></span> <span data-ttu-id="3beb8-121">각 중앙 사이트에서 SIP 트렁크가 종료 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-121">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="3beb8-122">예를 들어 더블린 및 Tukwila 중앙 사이트가 있고 둘 다 사이트의 SIP 트렁크를 하나만 사용 하는 경우 트렁크가 다운 되 면 다른 사이트의 사용자가 PSTN 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-122">For example, if you have Dublin and Tukwila central sites and both use only one site’s SIP trunk, if the trunk goes down, the other site’s users cannot make PSTN calls.</span></span>

  - <span data-ttu-id="3beb8-123">분기 사이트와 중앙 사이트가 서로 다른 국가/지역에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-123">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="3beb8-124">호환성 및 규정 준수를 위해 국가/지역당 하나 이상의 SIP 트렁크가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-124">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="3beb8-125">예를 들어 유럽 연합에서 통신은 중앙 지점에서 로컬로 종료 하지 않고는 국가/지역을 나갈 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-125">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="3beb8-126">사이트의 지리적 위치 및 회사 내에서 예상 되는 트래픽 크기에 따라 모든 사용자를 중앙 SIP 트렁크를 통해 라우트 하지 않으려는 경우 또는 분기 사이트에서 SIP 트렁크를 통해 일부 사용자의 경로를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-126">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="3beb8-127">다음 질문에 대한 대답을 통해 요구 사항을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-127">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="3beb8-128">각 사이트의 크기 (Enterprise Voice를 사용할 수 있는 사용자 수)</span><span class="sxs-lookup"><span data-stu-id="3beb8-128">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

  - <span data-ttu-id="3beb8-129">각 사이트에서 대부분의 전화 통화를 받게 되는 직접 안쪽 전화 걸기 (온) 번호는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="3beb8-129">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="3beb8-130">중앙 집중식 또는 분산 SIP 트렁크 배포 여부에 대 한 결정에는 비용 이점 분석이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-130">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="3beb8-131">경우에 따라 분산형 배포 모델이 필요하지 않은 경우에도 이 모델이 훨씬 이익인 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-131">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="3beb8-132">완전히 중앙화된 배포에서는 모든 분기 사이트 트래픽이 WAN 링크를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-132">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="3beb8-133">WAN 링크에 필요한 대역폭에 대한 비용을 지불하는 대신 분산형 SIP 트렁크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-133">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="3beb8-134">예를 들어, 중앙 사이트에 대 한 페더레이션이 있는 분기 사이트에 Standard Edition server를 배포 하거나 소규모 게이트웨이를 사용 하 여 Sba (survivable 분기 어플라이언스 또는 Sba (survivable 분기 서버를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-134">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3beb8-135">분산 SIP 트렁크에 대 한 자세한 내용은 <A href="lync-server-2013-branch-site-sip-trunking.md">Branch SITE SIP 트렁크 In Lync Server 2013</A>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3beb8-135">For details about distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="3beb8-136">지원되는 SIP 트렁크 연결 유형</span><span class="sxs-lookup"><span data-stu-id="3beb8-136">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="3beb8-137">Lync Server에서는 SIP 트렁크에 대해 다음 연결 유형을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-137">Lync Server supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="3beb8-138">MPLS(Multiprotocol Label Switching)는 하나의 네트워크 노드에서 다음 네트워크 노드로 데이터를 전달하는 개인 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-138">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="3beb8-139">MPLS 네트워크의 대역폭은 다른 구독자와 공유되며, 각 데이터 패킷에는 구독자 간에 데이터를 구별하는 레이블이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-139">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s.</span></span> <span data-ttu-id="3beb8-140">이 연결 유형에는 VPN (가상 사설망)이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-140">This connection type does not require a virtual private network (VPN).</span></span> <span data-ttu-id="3beb8-141">그러나 VoIP 트래픽이 우선적으로 적용되지 않는 경우 과도한 IP 트래픽으로 인해 VoIP 작업이 방해를 받을 수 있다는 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-141">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="3beb8-142">임대 파이버-광 연결 또는 T1 회선과 같은 다른 트래픽이 없는 개인 연결은 대개 가장 안정적이 고 안전한 연결 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-142">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type.</span></span> <span data-ttu-id="3beb8-143">이 연결 유형은 통화 운반 용량을 가장 많이 제공 하지만 일반적으로 비용이 가장 높습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-143">This connection type provides the highest call-carrying capacity, but it is typically the most expensive.</span></span> <span data-ttu-id="3beb8-144">VPN은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-144">VPN is not required.</span></span> <span data-ttu-id="3beb8-145">개인 연결은 통화 볼륨이 높고 보안 및 가용성 요구 사항이 엄격한 조직에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-145">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="3beb8-146">인터넷은 비용이 저렴 한 연결 형식 이지만 안정성이 가장 낮은 것도 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-146">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="3beb8-147">인터넷 연결은 VPN을 필요로 하는 유일한 Lync Server SIP 트렁크 연결 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-147">Internet connection is the only Lync Server SIP trunking connection type that requires VPN.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="3beb8-148">연결 유형 선택</span><span class="sxs-lookup"><span data-stu-id="3beb8-148">Selecting a Connection Type</span></span>

<span data-ttu-id="3beb8-149">회사에 가장 적절한 SIP 트렁크 연결 유형은 요구 사항 및 예산에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-149">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="3beb8-150">중간 규모 또는 대기업의 경우 일반적으로 MPLS 네트워크가 가장 큰 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-150">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value.</span></span> <span data-ttu-id="3beb8-151">MPLS 네트워크는 전문화된 개인 네트워크보다 저렴한 비용으로 필요한 대역폭을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-151">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="3beb8-152">대기업에는 전용 섬유-파이버, T1, T3 또는 더 높은 연결 (유럽 연합의 경우 E1, E3 이상)이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-152">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

  - <span data-ttu-id="3beb8-153">통화 량이 적은 소규모 기업 또는 분기 사이트의 경우 인터넷을 통한 SIP 트렁크이 가장 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-153">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="3beb8-154">중간 규모 또는 대규모 사이트에는이 연결 유형을 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-154">This connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a><span data-ttu-id="3beb8-155">대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3beb8-155">Bandwidth Requirements</span></span>

<span data-ttu-id="3beb8-156">구현 해야 하는 대역폭의 양은 통화 용량 (지원 해야 하는 동시 호출 수)에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-156">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support).</span></span> <span data-ttu-id="3beb8-157">지불한 최대 용량을 충분히 활용할 수 있도록 대역폭 가용성을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-157">You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for.</span></span> <span data-ttu-id="3beb8-158">다음 수식을 사용 하 여 SIP 트렁크 최고 대역폭 요구 사항을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-158">Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="3beb8-159">SIP 트렁크 최대 대역폭 = 최대 동시 통화 x (64 kbps + 헤더 크기)</span><span class="sxs-lookup"><span data-stu-id="3beb8-159">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3beb8-160">헤더 크기는 최대 20 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-160">Header size is 20 bytes maximum.</span></span>



</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="3beb8-161">코덱 지원</span><span class="sxs-lookup"><span data-stu-id="3beb8-161">Codec Support</span></span>

<span data-ttu-id="3beb8-162">Lync Server 2013는 다음 코덱과 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-162">Lync Server 2013 supports only the following codecs:</span></span>

  - <span data-ttu-id="3beb8-163">G.711 a-law(주로 북미 이외의 다른 지역에서 사용)</span><span class="sxs-lookup"><span data-stu-id="3beb8-163">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="3beb8-164">G.711 µ-law(북미에서 사용)</span><span class="sxs-lookup"><span data-stu-id="3beb8-164">G.711 µ-law (used in North America)</span></span>

</div>

<div>

## <a name="internet-telephony-service-provider"></a><span data-ttu-id="3beb8-165">인터넷 전화 통신 서비스 공급자</span><span class="sxs-lookup"><span data-stu-id="3beb8-165">Internet Telephony Service Provider</span></span>

<span data-ttu-id="3beb8-166">SIP 트렁크 연결의 서비스 공급자 쪽을 구현하는 방법은 ITSP에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-166">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="3beb8-167">배포 정보에 대해서는 서비스 공급자에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="3beb8-167">For deployment information, contact your service provider.</span></span> <span data-ttu-id="3beb8-168">인증 된 SIP 트렁크 서비스 공급자 목록은 [Microsoft 통합 커뮤니케이션 오픈 상호 운용성 프로그램 웹 사이트](https://go.microsoft.com/fwlink/?linkid=287029)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3beb8-168">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](https://go.microsoft.com/fwlink/?linkid=287029).</span></span>

<span data-ttu-id="3beb8-169">Microsoft 인증 SIP 트렁크 공급자에 대한 자세한 내용은 Microsoft 담당자에게 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="3beb8-169">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3beb8-170">Microsoft 인증 서비스 공급자를 사용하여 ITSP가 SIP 트렁크를 트래버스하는 모든 기능(예: 세션 설정 및 관리와 모든 확장된 VoIP 서비스 지원)을 지원하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-170">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services).</span></span> <span data-ttu-id="3beb8-171">Microsoft 기술 지원은 인증 되지 않은 공급자를 사용 하는 구성으로 확장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-171">Microsoft technical support does not extend to configurations that use noncertified providers.</span></span> <span data-ttu-id="3beb8-172">현재 SIP 트렁크에 대해 인증 되지 않은 인터넷 서비스 공급자를 사용 하는 경우 해당 공급자를 ISP로 계속 사용 하도록 선택 하 고 SIP 트렁크에 대해 Microsoft에서 인증 한 공급자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3beb8-172">If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

