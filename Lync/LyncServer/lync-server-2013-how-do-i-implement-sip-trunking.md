---
title: 'Lync Server 2013: SIP 트렁크를 구현하는 방법'
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
ms.openlocfilehash: de621d7508b69dd3adc3babf487406825f3a93f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="ee61d-102">Lync Server 2013에서 SIP 트렁크를 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="ee61d-102">How do I implement SIP trunking in Lync Server 2013?</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee61d-103">_**마지막으로 수정한 주제:** 2013-03-18_</span><span class="sxs-lookup"><span data-stu-id="ee61d-103">_**Topic Last Modified:** 2013-03-18_</span></span>

<span data-ttu-id="ee61d-104">SIP 트렁크을 구현 하려면 필요한 경우 Lync Server 2013 클라이언트와 서비스 공급자 및 transcodes 미디어 간의 통신 세션에 대 한 프록시 역할을 하는 조정 서버를 통해 연결을 라우팅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-104">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="ee61d-105">각 중재 서버에는 내부 네트워크 인터페이스와 외부 네트워크 인터페이스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-105">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="ee61d-106">내부 인터페이스가 프런트 엔드 서버에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-106">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="ee61d-107">외부 인터페이스는 일반적으로 중재 서버를 PSTN (공개 교환 전화 네트워크) 게이트웨이 또는 IP-PBX에 연결 하는 데 사용 되기 때문에 게이트웨이 인터페이스 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-107">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="ee61d-108">SIP 트렁크를 구현 하려면 중재 서버의 외부 인터페이스를 ITSP의 외부 edge 구성 요소에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-108">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ee61d-109">ITSP의 외부에 지 구성 요소는 SBC (세션 경계 컨트롤러), 라우터 또는 게이트웨이 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-109">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>



</div>

<span data-ttu-id="ee61d-110">중재 서버에 대 한 자세한 내용은 [Lync server 2013에서 중재 서버 구성 요소](lync-server-2013-mediation-server-component.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ee61d-110">For details about Mediation Servers, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md).</span></span>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="ee61d-111">중앙 집중화 및 분산 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="ee61d-111">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="ee61d-112">*중앙 집중화* SIP 트렁크는 지점 사이트 트래픽을 포함 하 여 모든 Voice over 인터넷 프로토콜 (VoIP) 트래픽을 중앙 사이트를 통해 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-112">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="ee61d-113">중앙 집중화 된 배포 모델은 간단 하 고 비용 효율적 이며, 일반적으로 Lync Server 2013에서 SIP trunks을 구현 하는 데 권장 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-113">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="ee61d-114">*분산* SIP 트렁크 하나 이상의 지점 사이트에서 로컬 SIP 트렁크를 구현 하는 배포 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-114">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="ee61d-115">그러면 중앙 사이트를 거치지 않고 지사 사이트에서 서비스 공급자로 직접 VoIP 트래픽을 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-115">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="ee61d-116">분산 SIP 트렁크는 다음과 같은 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-116">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="ee61d-117">지점 사이트에는 survivable 전화 연결이 필요 합니다 (예: WAN이 작동 하지 않는 경우).</span><span class="sxs-lookup"><span data-stu-id="ee61d-117">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="ee61d-118">이 요구 사항은 각 지점 사이트에 대해 분석 되어야 합니다. 일부 분기에는 중복 및 장애 조치가 필요할 수 있지만 다른 경우에는 그렇지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-118">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

  - <span data-ttu-id="ee61d-119">두 중앙 사이트 간에 복원성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-119">Resiliency is required between two central sites.</span></span> <span data-ttu-id="ee61d-120">각 중앙 사이트에서 SIP 트렁크가 종료 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-120">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="ee61d-121">예를 들어 더블린 및 Tukwila 중앙 사이트가 있고 두 사이트의 SIP 트렁크만 사용 하는 경우 트렁크가 다운 되 면 다른 사이트의 사용자가 PSTN 통화를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-121">For example, if you have Dublin and Tukwila central sites and both use only one site’s SIP trunk, if the trunk goes down, the other site’s users cannot make PSTN calls.</span></span>

  - <span data-ttu-id="ee61d-122">분기 사이트와 중앙 사이트는 서로 다른 국가/지역에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-122">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="ee61d-123">호환성과 법적 고 지는 국가/지역에 따라 적어도 하나 이상의 SIP 트렁크가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-123">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="ee61d-124">예를 들어 유럽 연합에서 통신은 중앙 집중화 된 지점에서 로컬로 종료 하지 않고는 국가/지역에서 나갈 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-124">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="ee61d-125">사이트의 지리적 위치와 엔터프라이즈 내에서 예상 되는 트래픽 크기에 따라 중앙 SIP 트렁크를 통해 모든 사용자를 라우팅 하지 않으려는 경우 또는 지점 사이트의 SIP 트렁크를 통해 일부 사용자의 경로를 설정 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-125">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="ee61d-126">필요 사항을 분석 하려면 다음 질문에 대답 하세요.</span><span class="sxs-lookup"><span data-stu-id="ee61d-126">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="ee61d-127">각 사이트의 크기 (즉, 엔터프라이즈 음성에 대해 설정 된 사용자 수)는 얼마나 되나요?</span><span class="sxs-lookup"><span data-stu-id="ee61d-127">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

  - <span data-ttu-id="ee61d-128">각 사이트에서 바로 안쪽으로 거는 전화 접속 (a) 번호를 통해 가장 많은 전화를 받을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="ee61d-128">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="ee61d-129">중앙 집중화 또는 분산 SIP 트렁크 배포 여부에 대 한 결정에는 비용 이점 분석이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-129">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="ee61d-130">때로는 필요 하지 않은 경우에도 분산 배포 모델을 선택 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-130">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="ee61d-131">완전히 중앙 집중화 된 배포에서는 모든 지점 사이트 트래픽이 WAN 링크를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-131">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="ee61d-132">WAN 연결에 필요한 대역폭을 지불 하는 대신 분산 SIP 트렁크를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-132">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="ee61d-133">예를 들어 중앙 사이트에 페더레이션 하는 지점 사이트에 스탠더드 버전 서버를 배포 하거나 small gateway를 사용 하 여 Survivable Branch 기기 또는 Survivable Branch 서버를 배포 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-133">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ee61d-134">분산 SIP 트렁크에 대 한 자세한 내용은 <A href="lync-server-2013-branch-site-sip-trunking.md">Lync Server 2013에서 분기 사이트 SIP 트렁크</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ee61d-134">For details about distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="ee61d-135">지원 되는 SIP 트렁크 연결 유형</span><span class="sxs-lookup"><span data-stu-id="ee61d-135">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="ee61d-136">Lync Server는 SIP 트렁크에 대해 다음 연결 유형을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-136">Lync Server supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="ee61d-137">MPLS (멀티 프로토콜 레이블 전환)는 하나의 네트워크 노드에서 다음으로 데이터를 전송 하 고 전달 하는 개인 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-137">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="ee61d-138">MPLS 네트워크의 대역폭은 다른 구독자와 공유 되며 각 데이터 패킷에는 다른 구독자의 데이터를 구분 하는 레이블이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-138">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s.</span></span> <span data-ttu-id="ee61d-139">이 연결 형식에는 가상 개인 네트워크 (VPN)가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-139">This connection type does not require a virtual private network (VPN).</span></span> <span data-ttu-id="ee61d-140">잠재적인 단점은 VoIP 트래픽이 우선 순위로 지정 되지 않는 이상 과도 한 IP 트래픽이 VoIP 작업을 방해할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-140">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="ee61d-141">다른 트래픽이 없는 개인 연결 (예: 임대한 광섬유 연결 또는 T1 회선)은 일반적으로 가장 안정적이 고 안전한 연결 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-141">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type.</span></span> <span data-ttu-id="ee61d-142">이 연결 유형은 가장 높은 통화 운반 용량을 제공 하지만 일반적으로 가장 비쌉니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-142">This connection type provides the highest call-carrying capacity, but it is typically the most expensive.</span></span> <span data-ttu-id="ee61d-143">VPN이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-143">VPN is not required.</span></span> <span data-ttu-id="ee61d-144">개인 연결은 높은 통화 볼륨이 나 엄격한 보안 및 가용성 요구 사항이 있는 조직에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-144">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="ee61d-145">인터넷은 가장 저렴 한 연결 형식 이지만 최소한의 신뢰성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-145">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="ee61d-146">인터넷 연결은 VPN을 필요로 하는 유일한 Lync Server SIP 트렁크 연결 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-146">Internet connection is the only Lync Server SIP trunking connection type that requires VPN.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="ee61d-147">연결 형식 선택</span><span class="sxs-lookup"><span data-stu-id="ee61d-147">Selecting a Connection Type</span></span>

<span data-ttu-id="ee61d-148">기업의 가장 적합 한 SIP 트렁크 연결 유형은 사용자의 요구와 예산에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-148">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="ee61d-149">중간 규모 또는 대기업의 경우 일반적으로 MPLS 네트워크에서 가장 큰 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-149">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value.</span></span> <span data-ttu-id="ee61d-150">특별 한 사설 네트워크 보다 저렴 한 요금으로 필요한 대역폭을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-150">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="ee61d-151">대규모 기업은 개인 광섬유, T1, T3 이상 연결 (E1, E3 또는 그 이상의 유럽 연합)을 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-151">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

  - <span data-ttu-id="ee61d-152">낮은 규모의 중소기업 또는 저렴 한 통화를 사용 하는 지사 사이트의 경우 인터넷을 통해 SIP를 트렁크 하는 것이 가장 좋은 선택 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-152">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="ee61d-153">중간 규모 또는 대규모 사이트에는이 연결 유형을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-153">This connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a><span data-ttu-id="ee61d-154">대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ee61d-154">Bandwidth Requirements</span></span>

<span data-ttu-id="ee61d-155">구현에 필요한 대역폭의 양은 통화 용량 (지원할 동시 통화 수)에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-155">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support).</span></span> <span data-ttu-id="ee61d-156">지불한 최고 용량을 충분히 활용할 수 있도록 대역폭 가용성을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-156">You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for.</span></span> <span data-ttu-id="ee61d-157">다음 공식을 사용 하 여 SIP 트렁크 최고 대역폭 요구 사항을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-157">Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="ee61d-158">SIP 트렁크 최고 대역폭 = 최대 동시 통화 x (64 kbps + 헤더 크기)</span><span class="sxs-lookup"><span data-stu-id="ee61d-158">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ee61d-159">헤더 크기는 최대 20 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-159">Header size is 20 bytes maximum.</span></span>



</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="ee61d-160">코덱 지원</span><span class="sxs-lookup"><span data-stu-id="ee61d-160">Codec Support</span></span>

<span data-ttu-id="ee61d-161">Lync 서버 2013는 다음 코덱으로만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-161">Lync Server 2013 supports only the following codecs:</span></span>

  - <span data-ttu-id="ee61d-162">711 a-법률 (주로 북미 지역 외에 사용)</span><span class="sxs-lookup"><span data-stu-id="ee61d-162">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="ee61d-163">711 μ-사법 기관 (북미 지역에서 사용)</span><span class="sxs-lookup"><span data-stu-id="ee61d-163">G.711 µ-law (used in North America)</span></span>

</div>

<div>

## <a name="internet-telephony-service-provider"></a><span data-ttu-id="ee61d-164">인터넷 전화 통신 서비스 공급자</span><span class="sxs-lookup"><span data-stu-id="ee61d-164">Internet Telephony Service Provider</span></span>

<span data-ttu-id="ee61d-165">SIP 트렁크 연결의 서비스 공급자 쪽을 구현 하는 방법은 ITSP에 따라 달라 지는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-165">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="ee61d-166">배포 정보는 서비스 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="ee61d-166">For deployment information, contact your service provider.</span></span> <span data-ttu-id="ee61d-167">인증 된 SIP 트렁크 서비스 공급자 목록은 [Microsoft 통합 커뮤니케이션 오픈 상호 운용성 프로그램 웹 사이트](http://go.microsoft.com/fwlink/?linkid=287029)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ee61d-167">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](http://go.microsoft.com/fwlink/?linkid=287029).</span></span>

<span data-ttu-id="ee61d-168">Microsoft 인증 SIP 트렁크 공급자에 대 한 자세한 내용은 Microsoft 담당자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="ee61d-168">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ee61d-169">Microsoft 인증 서비스 공급자를 사용 하 여 현재 ITSP가 SIP 트렁크를 통과 하는 모든 기능을 지원 하는지 확인 해야 합니다 (예: 세션 설정 및 관리, 모든 확장 된 VoIP 서비스 지원).</span><span class="sxs-lookup"><span data-stu-id="ee61d-169">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services).</span></span> <span data-ttu-id="ee61d-170">Microsoft 기술 지원은 인증 되지 않은 공급자를 사용 하는 구성으로 확장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-170">Microsoft technical support does not extend to configurations that use noncertified providers.</span></span> <span data-ttu-id="ee61d-171">현재 SIP 트렁크 인증을 받지 않은 인터넷 서비스 공급자를 사용 하는 경우 해당 공급자를 ISP로 계속 사용할 수 있도록 선택 하 고 Microsoft에서 SIP 트렁크에 대해 인증 한 공급자를 사용 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee61d-171">If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

