---
title: 비즈니스용 Skype 서버의 SIP 트렁크
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: 비즈니스용 Skype 서버 2013의 SIP 트렁크에 Enterprise Voice
ms.openlocfilehash: ca3e30c8974e5ac26c2d9c395da228f85c92bac0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110664"
---
# <a name="sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="e4028-103">비즈니스용 Skype 서버의 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="e4028-103">SIP trunking in Skype for Business Server</span></span>

<span data-ttu-id="e4028-104">비즈니스용 Skype 서버 2013의 SIP 트렁크에 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="e4028-104">Learn about SIP trunking in Skype for Business Server Enterprise Voice</span></span>

<span data-ttu-id="e4028-105">SIP(Session Initiation Protocol)는 기본 전화 서비스 및 인스턴트 메시징, 회의, 현재 상태 감지, 멀티미디어 등의 추가 실시간 통신 서비스에 대한 VoIP(Voice over IP) 통신 세션을 시작 및 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-105">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia.</span></span> <span data-ttu-id="e4028-106">이 섹션에서는 로컬 네트워크의 경계를 넘어 확장되는 SIP 연결 유형인 SIP 트렁크를 구현하기 위한 계획 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-106">This section provides planning information for implementing SIP trunks, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="e4028-107">SIP 트렁크란?</span><span class="sxs-lookup"><span data-stu-id="e4028-107">What is SIP Trunking?</span></span>

<span data-ttu-id="e4028-108">SIP 트렁크는 조직과 방화벽 너머의 ITSP(인터넷 전화 통신 서비스 공급자) 간의 SIP 통신 링크를 설정하는 IP 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-108">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall.</span></span> <span data-ttu-id="e4028-109">일반적으로 SIP 트렁크는 조직의 중앙 사이트를 ITSP에 연결하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-109">Typically, a SIP trunk is used to connect your organization's central site to an ITSP.</span></span> <span data-ttu-id="e4028-110">일부의 경우 분기 사이트를 ITSP에 연결하는 데에도 SIP 트렁크를 사용하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-110">In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<span data-ttu-id="e4028-111">SIP 트렁크 배포는 조직의 통신을 단순화하고 실시간 통신에 대한 향상된 최신 기능을 준비하는 데 큰 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-111">Deploying SIP trunking can be a big step toward simplifying your organization's telecommunications and preparing for up-to-date enhancements to real-time communications.</span></span> <span data-ttu-id="e4028-112">SIP 트렁크의 주요 이점 중 하나는 조직의 연결을 중앙 사이트의 PSTN(Public Switched Telephone Network)에 통합할 수 있는데, 이는 일반적으로 각 분기 사이트에서 별도의 트렁크가 필요한 선행 TDM(Time Division Multiplexing) 트렁크가 아니라는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-112">One of the primary advantages of SIP trunking is that you can consolidate your organization's connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

### <a name="cost-savings"></a><span data-ttu-id="e4028-113">비용 절감</span><span class="sxs-lookup"><span data-stu-id="e4028-113">Cost Savings</span></span>

<span data-ttu-id="e4028-114">SIP 트렁크와 관련된 비용 절감은 크게 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-114">The cost savings associated with SIP trunking can be substantial:</span></span>

- <span data-ttu-id="e4028-115">일반적으로 장거리 통화는 SIP 트렁크를 통해 비용이 훨씬 적습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-115">Long distance calls typically cost much less through a SIP trunk.</span></span>

- <span data-ttu-id="e4028-116">관리 가능성 비용을 절감하고 배포 복잡성을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-116">You can cut manageability costs and reduce the complexity of deployment.</span></span>

- <span data-ttu-id="e4028-117">SIP 트렁크를 ITSP에 직접 연결하는 경우 상당히 낮은 비용으로 SIP 트렁크를 연결할 경우 BRI(기본 요금 인터페이스) 및 PRI(기본 요금 인터페이스) 수수료를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-117">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost.</span></span> <span data-ttu-id="e4028-118">TDM 트렁크에서 서비스 공급자는 분당 통화에 대해 요금을 부과합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-118">In TDM trunking, service providers charge for calls by the minute.</span></span> <span data-ttu-id="e4028-119">SIP 트렁크의 비용은 대역폭 사용량을 기반으로 할 수 있습니다. 이 경우 더 작고 경제적인 증분으로 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-119">The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments.</span></span> <span data-ttu-id="e4028-120">실제 비용은 선택한 ITSP의 서비스 모델에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-120">(The actual cost depends on the service model of the ITSP you choose.)</span></span>

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="e4028-121">SIP 트렁크와 PSTN 게이트웨이 또는 IP-PBX 호스팅 비교</span><span class="sxs-lookup"><span data-stu-id="e4028-121">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="e4028-122">SIP 트렁크는 서비스 공급자에 직접 연결하기 때문에 PSTN 게이트웨이와 관리 비용 및 복잡성을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-122">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity.</span></span> <span data-ttu-id="e4028-123">SIP 트렁크를 사용하는 경우 유지 관리 및 관리가 줄어들어 비용이 크게 절감될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-123">Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

### <a name="expanded-voip-services"></a><span data-ttu-id="e4028-124">확장된 VoIP 서비스</span><span class="sxs-lookup"><span data-stu-id="e4028-124">Expanded VoIP Services</span></span>

<span data-ttu-id="e4028-125">음성 기능은 종종 SIP 트렁크 배포의 주요 동기가 되지만 음성 지원은 첫 번째 단계에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-125">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="e4028-126">SIP 트렁크를 사용하면 VoIP 기능을 확장하고 비즈니스용 Skype 서버를 사용하도록 설정하여 보다 풍부한 서비스 집합을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-126">With SIP trunking, you can extend VoIP capabilities and enable Skype for Business Server to deliver a richer set of services.</span></span> <span data-ttu-id="e4028-127">예:</span><span class="sxs-lookup"><span data-stu-id="e4028-127">For example:</span></span>

- <span data-ttu-id="e4028-128">비즈니스용 Skype 서버를 실행하지 않는 장치에 대한 현재 상태 검색 기능이 향상되어 휴대폰과 더 잘 통합되어 사용자가 휴대폰 통화 중일 때를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-128">Enhanced presence detection for devices that are not running Skype for Business Server can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

- <span data-ttu-id="e4028-129">E9-1-1 긴급 통화를 통해 911 통화에 응답하는 기관은 자신의 전화 번호에서 발신자 위치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-129">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller's location from his or her telephone number.</span></span>

> [!NOTE]
> <span data-ttu-id="e4028-130">ITSP에 문의하여 조직에서 지원하고 사용하도록 설정할 수 있는 서비스 목록을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e4028-130">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>

### <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="e4028-131">SIP 트렁크와 Direct SIP 연결</span><span class="sxs-lookup"><span data-stu-id="e4028-131">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="e4028-132">트렁크 용어는 회로 전환 기술에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-132">The term trunk is derived from circuit-switched technology.</span></span> <span data-ttu-id="e4028-133">전화 전환 장비를 연결하는 전용 실제 선을 지칭합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-133">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="e4028-134">선행 TDM(시간 분할 다중화) 트렁크와 마찬가지로 SIP 트렁크는 두 개의 개별 SIP 네트워크인 비즈니스용 Skype 서버 엔터프라이즈와 ITSP 간의 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-134">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Skype for Business Server enterprise and the ITSP.</span></span> <span data-ttu-id="e4028-135">회로 전환 트렁크와 달리 SIP 트렁크는 지원되는 모든 SIP 트렁크 연결 유형에 대해 설정될 수 있는 가상 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-135">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span>

<span data-ttu-id="e4028-136">반면에 Direct SIP 연결은 로컬 네트워크 경계를 가로지르지 않는 SIP 연결입니다(즉, 내부 네트워크 내에서 PSTN(공중 전화망) 게이트웨이 또는 PBX(Private Branch Exchange)에 연결됨).</span><span class="sxs-lookup"><span data-stu-id="e4028-136">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="e4028-137">비즈니스용 Skype 서버에서 직접 SIP 연결을 사용하는 방법에 대한 자세한 내용은 비즈니스용 Skype 서버에서 직접 SIP 연결을 [참조하세요.](direct-sip.md)</span><span class="sxs-lookup"><span data-stu-id="e4028-137">For details about how you can use direct SIP connections with Skype for Business Server, see [Direct SIP connections in Skype for Business Server](direct-sip.md).</span></span>

## <a name="how-do-i-implement-sip-trunking"></a><span data-ttu-id="e4028-138">SIP 트렁크를 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="e4028-138">How do I implement SIP Trunking?</span></span>

<span data-ttu-id="e4028-139">SIP 트렁크를 구현하려면 비즈니스용 Skype 서버 클라이언트와 서비스 공급자 간의 통신 세션에 대한 프록시 역할을 하는 중재 서버를 통해 연결을 라우팅하고 필요한 경우 미디어를 코드 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-139">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Skype for Business Server clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="e4028-140">각 중재 서버에는 내부 네트워크 인터페이스와 외부 네트워크 인터페이스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-140">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="e4028-141">내부 인터페이스는 프런트 엔드 서버에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-141">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="e4028-142">외부 인터페이스는 일반적으로 중재 서버를 PSTN(Public Switched Telephone Network) 게이트웨이 또는 IP-PBX에 연결하는 데 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-142">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="e4028-143">SIP 트렁크를 구현하기 위해 중재 서버의 외부 인터페이스를 ITSP의 외부 에지 구성 요소에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-143">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span> <span data-ttu-id="e4028-144">ITSP의 외부 에지 구성 요소는 SBC(Session Border Controller), 라우터 또는 게이트웨이일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-144">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>

<span data-ttu-id="e4028-145">중재 서버에 대한 자세한 내용은 비즈니스용 Skype 서버의 중재 서버 구성 요소를 [참조하세요.](mediation-server.md)</span><span class="sxs-lookup"><span data-stu-id="e4028-145">For details about Mediation Servers, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>

### <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="e4028-146">중앙 집중식 SIP 트렁크와 분산형 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="e4028-146">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="e4028-147">중앙 집중식 SIP 트렁크는 분기 사이트 트래픽을 비롯한 모든 VoIP 트래픽을 중앙 사이트를 통해 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-147">Centralized SIP trunking routes all VoIP traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="e4028-148">중앙 집중식 배포 모델은 단순하고 비용 효과적인 모델로, 일반적으로 비즈니스용 Skype 서버에서 SIP 트렁크를 구현하는 데 권장되는 접근 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-148">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Skype for Business Server.</span></span>

<span data-ttu-id="e4028-149">분산 SIP 트렁크는 하나 이상의 분기 사이트에서 로컬 SIP 트렁크를 구현하는 배포 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-149">Distributed SIP trunking is a deployment model in which you implement local SIP trunks at one or more branch sites.</span></span> <span data-ttu-id="e4028-150">그런 다음 VoIP 트래픽은 중앙 사이트를 거치지 않고 분기 사이트에서 서비스 공급자로 직접 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-150">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="e4028-151">분산형 SIP 트렁크는 다음과 같은 경우에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-151">Distributed SIP trunking is required only in the following cases:</span></span>

- <span data-ttu-id="e4028-152">분기 사이트에 지속 가능한 전화 연결(예: WAN이 다운된 경우)이 필요한 경우.</span><span class="sxs-lookup"><span data-stu-id="e4028-152">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="e4028-153">이 요구 사항은 각 분기 사이트에 대해 분석해야 합니다. 일부 분기는 중복 및 장애 조치(failover)가 필요할 수 있는 반면 다른 분기는 중복 및 장애 조치(failover)가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-153">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

- <span data-ttu-id="e4028-154">두 중앙 사이트 간에는 탄력성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-154">Resiliency is required between two central sites.</span></span> <span data-ttu-id="e4028-155">각 중앙 사이트에서 SIP 트렁크가 종료되는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-155">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="e4028-156">예를 들어 Dublin 및 Tukwila 중앙 사이트가 있으며 둘 다 사이트의 SIP 트렁크를 하나만 사용하는 경우 트렁크가 다운될 경우 다른 사이트의 사용자가 PSTN 호출을 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-156">For example, if you have Dublin and Tukwila central sites and both use only one site's SIP trunk, if the trunk goes down, the other site's users cannot make PSTN calls.</span></span>

- <span data-ttu-id="e4028-157">분기 사이트와 중앙 사이트는 서로 다른 국가/지역에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-157">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="e4028-158">호환성 및 규정 준수를 위해 국가/지역당 하나 이상의 SIP 트렁크가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-158">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="e4028-159">예를 들어 유럽 연합에서 통신은 중앙 지점에서 로컬로 종료하지 않고는 국가/지역을 떠날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-159">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="e4028-160">사이트의 지리적 위치와 엔터프라이즈 내에서 예상되는 트래픽의 양에 따라 일부 사용자를 중앙 SIP 트렁크를 통해 라우팅하지 않을 수도, 아니면 분기 사이트의 SIP 트렁크를 통해 일부 사용자를 라우팅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-160">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="e4028-161">다음 질문에 대한 대답을 통해 요구 사항을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-161">To analyze your needs, answer the following questions:</span></span>

- <span data-ttu-id="e4028-162">각 사이트의 크리에이터스(즉, 사이트 사용 가능 사용자 수)Enterprise Voice?</span><span class="sxs-lookup"><span data-stu-id="e4028-162">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

- <span data-ttu-id="e4028-163">각 사이트의 DID(Direct Inward Dialing) 번호로 전화를 가장 많이 걸 수 있는 번호는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="e4028-163">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="e4028-164">중앙 집중식 SIP 트렁크를 배포할지 또는 분산된 SIP 트렁크를 배포할지 여부를 결정하려면 비용 이익 분석이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-164">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="e4028-165">경우에 따라 분산형 배포 모델이 필요하지 않은 경우에도 이 모델이 훨씬 이익인 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-165">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="e4028-166">완전히 중앙화된 배포에서는 모든 분기 사이트 트래픽이 WAN 링크를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-166">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="e4028-167">WAN 링크에 필요한 대역폭에 대한 비용을 지불하는 대신 분산형 SIP 트렁크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-167">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="e4028-168">예를 들어 중앙 사이트에 페더럴이 있는 분기 사이트에 Standard Edition 서버를 배포하거나 작은 게이트웨이를 통해 Survivable Branch Appliance 또는 Survivable Branch Server를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-168">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="e4028-169">분산된 SIP 트렁크에 대한 자세한 내용은 비즈니스용 Skype 서버의 분기 사이트 SIP 트렁크를 [참조하세요.](branch-site.md)</span><span class="sxs-lookup"><span data-stu-id="e4028-169">For details about distributed SIP trunking, see [Branch site SIP trunking in Skype for Business Server](branch-site.md).</span></span>

### <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="e4028-170">지원되는 SIP 트렁크 연결 유형</span><span class="sxs-lookup"><span data-stu-id="e4028-170">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="e4028-171">비즈니스용 Skype 서버는 SIP 트렁크에 대해 다음과 같은 연결 유형을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-171">Skype for Business Server supports the following connection types for SIP trunking:</span></span>

- <span data-ttu-id="e4028-172">MPLS(Multiprotocol Label Switching)는 하나의 네트워크 노드에서 다음 네트워크 노드로 데이터를 전달하는 개인 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-172">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="e4028-173">MPLS 네트워크의 대역폭은 다른 구독자와 공유하며, 각 데이터 패킷에는 구독자의 데이터를 다른 구독자의 데이터와 구분하는 레이블이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-173">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber's data from another's.</span></span> <span data-ttu-id="e4028-174">이 연결 형식에는 VPN(가상 사설망)이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-174">This connection type does not require a virtual private network (VPN).</span></span> <span data-ttu-id="e4028-175">그러나 VoIP 트래픽이 우선적으로 적용되지 않는 경우 과도한 IP 트래픽으로 인해 VoIP 작업이 방해를 받을 수 있다는 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-175">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

- <span data-ttu-id="e4028-176">다른 트래픽이 없는 개인 연결(예: 임대된 광섬유 연결 또는 T1 줄)은 일반적으로 가장 안정적이고 안전한 연결 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-176">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type.</span></span> <span data-ttu-id="e4028-177">이 연결 유형은 통화 수행 용량이 가장 높지만 일반적으로 비용이 가장 많이 드는 연결 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-177">This connection type provides the highest call-carrying capacity, but it is typically the most expensive.</span></span> <span data-ttu-id="e4028-178">VPN은 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-178">VPN is not required.</span></span> <span data-ttu-id="e4028-179">개인 연결은 통화량이 높거나 엄격한 보안 및 가용성 요구 사항이 있는 조직에 적절합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-179">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

- <span data-ttu-id="e4028-180">인터넷은 비용이 가장 저렴한 연결 유형이지만 안정성도 가장 저렴합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-180">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="e4028-181">VPN이 필요한 유일한 비즈니스용 Skype 서버 SIP 트렁크 연결 유형은 인터넷 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-181">Internet connection is the only Skype for Business Server SIP trunking connection type that requires VPN.</span></span>

#### <a name="selecting-a-connection-type"></a><span data-ttu-id="e4028-182">연결 유형 선택</span><span class="sxs-lookup"><span data-stu-id="e4028-182">Selecting a Connection Type</span></span>

<span data-ttu-id="e4028-183">회사에 가장 적절한 SIP 트렁크 연결 유형은 요구 사항 및 예산에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-183">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

- <span data-ttu-id="e4028-184">중소기업의 경우 일반적으로 MPLS 네트워크가 가장 큰 가치를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-184">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value.</span></span> <span data-ttu-id="e4028-185">MPLS 네트워크는 전문화된 개인 네트워크보다 저렴한 비용으로 필요한 대역폭을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-185">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

- <span data-ttu-id="e4028-186">대기업은 개인 광섬유, T1, T3 이상 연결(유럽 연합의 경우 E1, E3 이상)이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-186">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

- <span data-ttu-id="e4028-187">통화량이 적은 소규모 기업 또는 분기 사이트의 경우 인터넷을 통한 SIP 트렁크를 가장 적합한 선택이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-187">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="e4028-188">이 연결 유형은 중간 규모 또는 대규모 사이트에는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-188">This connection type is not recommended for mid-size or larger sites.</span></span>

### <a name="bandwidth-requirements"></a><span data-ttu-id="e4028-189">대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4028-189">Bandwidth Requirements</span></span>

<span data-ttu-id="e4028-190">구현에 필요한 대역폭의 양은 통화 용량(지원할 수 있어야 하는 동시 통화 수)에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-190">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support).</span></span> <span data-ttu-id="e4028-191">지불한 최대 용량을 모두 활용할 수 있도록 대역폭 가용성을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-191">You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for.</span></span> <span data-ttu-id="e4028-192">다음 수식을 사용하여 SIP 트렁크 최대 대역폭 요구 사항을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-192">Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="e4028-193">SIP 트렁크 최대 대역폭 = 최대 동시 통화 x(64 kbps + 헤더 크기)</span><span class="sxs-lookup"><span data-stu-id="e4028-193">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

> [!NOTE]
> <span data-ttu-id="e4028-194">헤더 크기는 최대 20비트입니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-194">Header size is 20 bytes maximum.</span></span>

### <a name="codec-support"></a><span data-ttu-id="e4028-195">코덱 지원</span><span class="sxs-lookup"><span data-stu-id="e4028-195">Codec Support</span></span>

<span data-ttu-id="e4028-196">비즈니스용 Skype 서버는 다음 코덱만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-196">Skype for Business Server supports only the following codecs:</span></span>

- <span data-ttu-id="e4028-197">G.711 a-law(주로 북미 이외의 다른 지역에서 사용)</span><span class="sxs-lookup"><span data-stu-id="e4028-197">G.711 a-law (used primarily outside North America)</span></span>

- <span data-ttu-id="e4028-198">G.711 µ-law(북미에서 사용)</span><span class="sxs-lookup"><span data-stu-id="e4028-198">G.711 µ-law (used in North America)</span></span>

### <a name="internet-telephony-service-provider"></a><span data-ttu-id="e4028-199">인터넷 전화 통신 서비스 공급자</span><span class="sxs-lookup"><span data-stu-id="e4028-199">Internet Telephony Service Provider</span></span>

<span data-ttu-id="e4028-200">SIP 트렁크 연결의 서비스 공급자 쪽을 구현하는 방법은 ITSP에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-200">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="e4028-201">배포 정보에 대해서는 서비스 공급자에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="e4028-201">For deployment information, contact your service provider.</span></span> <span data-ttu-id="e4028-202">인증된 SIP 트렁크 서비스 공급자 목록은 [Microsoft Unified Communications Open Interoperability Program website](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e4028-202">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md).</span></span>

<span data-ttu-id="e4028-203">Microsoft 인증 SIP 트렁크 공급자에 대한 자세한 내용은 Microsoft 담당자에게 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="e4028-203">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4028-204">Microsoft 인증 서비스 공급자를 사용하여 ITSP가 SIP 트렁크를 트래버스하는 모든 기능(예: 세션 설정 및 관리와 모든 확장된 VoIP 서비스 지원)을 지원하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-204">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services).</span></span> <span data-ttu-id="e4028-205">Microsoft 기술 지원은 인증되지 않은 공급자를 사용하는 구성으로 확장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-205">Microsoft technical support does not extend to configurations that use noncertified providers.</span></span> <span data-ttu-id="e4028-206">현재 SIP 트렁크에 대해 인증되지 않은 인터넷 서비스 공급자를 사용하는 경우 해당 공급자를 ISP로 계속 사용하고 SIP 트렁크를 위해 Microsoft에서 인증한 공급자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-206">If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>

### <a name="topologies-and-components-for-sip-trunking"></a><span data-ttu-id="e4028-207">SIP 트렁크용 토폴로지 및 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e4028-207">Topologies and Components for SIP Trunking</span></span>

<span data-ttu-id="e4028-208">다음 그림에서는 비즈니스용 Skype 서버의 SIP 트렁크 토폴로지가 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-208">The following figure depicts the SIP trunking topology in Skype for Business Server.</span></span>

<span data-ttu-id="e4028-209">**SIP 트렁크 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="e4028-209">**SIP trunking topology**</span></span>

![SIP 트렁크 토폴로지](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

<span data-ttu-id="e4028-p125">다이어그램에 나온 것처럼 엔터프라이즈 네트워크 및 PSTN(공중 전화망) 서비스 공급자 간의 연결에 IP VPN(가상 사설망)이 사용됩니다. 이 사설망의 목적은 IP 연결을 제공하고 보안을 향상시키며 선택적으로 QoS(서비스 품질) 보증을 얻는 것입니다. VPN의 특성으로 인해 SIP 신호 트래픽을 위한 TLS(Transport Layer Security)나 미디어 트래픽을 위한 SRTP(실시간 전송 프로토콜)를 사용할 필요가 없습니다. 따라서 엔터프라이즈와 서비스 공급자 간의 연결은 SIP를 위한 일반 TCP 연결 및 IP VPN을 통해 터널링되는 미디어를 위한 UDP를 통한 일반 RTP(실시간 전송 프로토콜)로 구성됩니다. 이때 VPN 라우터 간 모든 방화벽에서는 VPN 라우터가 통신할 수 있도록 포트를 열어 놓아야 하고 VPN 라우터의 외부 에지에 대한 IP 주소는 공개적으로 라우팅 가능한 주소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-p125">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider. The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees. Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic. Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN. Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4028-216">서비스 공급자에게 문의하여 장애 조치(failover)를 비롯한 고가용성 지원을 제공하는지 여부를 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="e4028-216">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="e4028-217">이 경우 설정 절차를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-217">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="e4028-218">예를 들어 각 중재 서버에서 하나의 IP 주소와 하나의 SIP 트렁크만 구성해야 하는지 아니면 각 중재 서버에서 여러 SIP 트렁크를 구성해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="e4028-218">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span> <span data-ttu-id="e4028-219">> 중앙 사이트가 여러 개 있는 경우 서비스 공급자가 다른 중앙 사이트와의 연결을 사용하도록 설정할 수 있는지도 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-219">> If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>

> [!NOTE]
> <span data-ttu-id="e4028-220">SIP 트렁크의 경우 독립 실행형 중재 서버를 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-220">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="e4028-221">자세한 내용은 배포 설명서의 [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e4028-221">For details, see [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers) in the Deployment documentation.</span></span>

### <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="e4028-222">SIP 트렁크에 대해 중재 서버 보호</span><span class="sxs-lookup"><span data-stu-id="e4028-222">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="e4028-p128">보안을 위해 두 VPN 라우터 간의 각 연결에 대해 VLAN(가상 LAN)을 설치해야 합니다. VLAN의 실제 설치 프로세스는 라우터 제조업체별로 다릅니다. 자세한 내용은 라우터 공급업체에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="e4028-p128">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers. The actual process for setting up a VLAN varies from one router manufacturer to another. For details, contact your router vendor.</span></span>

<span data-ttu-id="e4028-226">다음 지침을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-226">We recommend that you follow these guidelines:</span></span>

- <span data-ttu-id="e4028-227">중재 서버와 경계 네트워크의 VPN 라우터(DMZ, 비무장 영역 및 스크린된 서브넷) 사이에 VLAN(가상 LAN)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-227">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

- <span data-ttu-id="e4028-228">라우터에서 VLAN으로 브로드캐스트나 멀티캐스트 패킷이 전송되는 것을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-228">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

- <span data-ttu-id="e4028-229">라우터에서 중재 서버가 아니라 다른 곳으로 트래픽을 라우팅하는 라우팅 규칙을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-229">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="e4028-230">VPN 서버를 사용하는 경우 다음 지침을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-230">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

- <span data-ttu-id="e4028-231">VPN 서버와 중재 서버 간에 VLAN을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-231">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

- <span data-ttu-id="e4028-232">VPN 서버에서 VLAN으로 브로드캐스트나 멀티캐스트 패킷이 전송되는 것을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-232">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

- <span data-ttu-id="e4028-233">VPN 서버 트래픽을 중재 서버가 있는 모든 곳으로 라우팅하는 라우팅 규칙을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-233">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

- <span data-ttu-id="e4028-234">GRE(Generic Routing Encapsulation)를 사용하여 VPN의 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="e4028-234">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4028-235">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4028-235">See also</span></span>

[<span data-ttu-id="e4028-236">비즈니스용 Skype 서버의 분기 사이트 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="e4028-236">Branch site SIP trunking in Skype for Business Server</span></span>](branch-site.md)