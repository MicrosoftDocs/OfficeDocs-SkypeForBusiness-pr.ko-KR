---
title: 비즈니스용 Skype 서버의 SIP 트렁크
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: 비즈니스용 Skype Server Enterprise Voice의 SIP 트렁크에 대 한 자세한 정보
ms.openlocfilehash: 10d47b6a235ee45e68415db2ff9253fffe1e2697
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196899"
---
# <a name="sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="a9909-103">비즈니스용 Skype 서버의 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="a9909-103">SIP trunking in Skype for Business Server</span></span>

<span data-ttu-id="a9909-104">비즈니스용 Skype Server Enterprise Voice의 SIP 트렁크에 대 한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="a9909-104">Learn about SIP trunking in Skype for Business Server Enterprise Voice</span></span>

<span data-ttu-id="a9909-105">SIP (세션 초기화 프로토콜)는 기본 전화 서비스에 대 한 VoIP (Voice over IP) 통신 세션을 시작 하 고 관리 하는 데 사용 되며 인스턴트 메시지, 회의, 현재 상태 감지 등의 추가 실시간 통신 서비스를 위한 것입니다. 멀티미디어.</span><span class="sxs-lookup"><span data-stu-id="a9909-105">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia.</span></span> <span data-ttu-id="a9909-106">이 섹션에서는 로컬 네트워크 경계를 벗어나 확장 되는 sip 연결 유형인 SIP trunks 구현에 대 한 계획 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-106">This section provides planning information for implementing SIP trunks, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="a9909-107">SIP 트렁크?</span><span class="sxs-lookup"><span data-stu-id="a9909-107">What is SIP Trunking?</span></span>

<span data-ttu-id="a9909-108">SIP 트렁크는 사용자의 조직과 인터넷 통신 서비스 공급자 (방화벽)의 SIP 통신 연결을 설정 하는 IP 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-108">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall.</span></span> <span data-ttu-id="a9909-109">일반적으로 SIP 트렁크는 조직의 중앙 사이트를 ITSP에 연결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-109">Typically, a SIP trunk is used to connect your organization's central site to an ITSP.</span></span> <span data-ttu-id="a9909-110">일부 경우에는 SIP 트렁크를 사용 하 여 지점 사이트를 ITSP에 연결 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-110">In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<span data-ttu-id="a9909-111">SIP 트렁크 구축은 조직의 통신을 단순화 하 고 실시간 통신에 대 한 최신 개선 사항을 준비 하는 데 큰 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-111">Deploying SIP trunking can be a big step toward simplifying your organization's telecommunications and preparing for up-to-date enhancements to real-time communications.</span></span> <span data-ttu-id="a9909-112">SIP 트렁크의 주요 이점 중 하나는 해당 조직의 연결을 중앙 사이트의 PSTN (공개 통신 네트워크)에 통합할 수 있다는 것입니다. 일반적으로 TDM (시간 구분 멀티플렉싱) 트렁크와 달리 각 지점 사이트에서 별도의 트렁크가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-112">One of the primary advantages of SIP trunking is that you can consolidate your organization's connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

### <a name="cost-savings"></a><span data-ttu-id="a9909-113">비용 절감</span><span class="sxs-lookup"><span data-stu-id="a9909-113">Cost Savings</span></span>

<span data-ttu-id="a9909-114">SIP 트렁크 관련 된 비용 절감 효과는 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-114">The cost savings associated with SIP trunking can be substantial:</span></span>

- <span data-ttu-id="a9909-115">장거리 통화는 일반적으로 SIP 트렁크를 통해 더욱 저렴 한 비용을 부과 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-115">Long distance calls typically cost much less through a SIP trunk.</span></span>

- <span data-ttu-id="a9909-116">관리 효율성 비용을 절감 하 고 배포의 복잡성을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-116">You can cut manageability costs and reduce the complexity of deployment.</span></span>

- <span data-ttu-id="a9909-117">BRI (기본 속도 인터페이스) 및 주 SP에 대 한 SIP 트렁크를 직접 저렴 한 가격으로 연결 하는 경우에는이를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-117">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost.</span></span> <span data-ttu-id="a9909-118">TDM 트렁크에서 서비스 공급자는 1 분 통화에 대 한 요금을 부과 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-118">In TDM trunking, service providers charge for calls by the minute.</span></span> <span data-ttu-id="a9909-119">SIP 트렁크 비용은 저렴 하 고 경제적으로 구매할 수 있는 대역폭 사용량을 기준으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-119">The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments.</span></span> <span data-ttu-id="a9909-120">실제 비용은 선택한 ITSP의 서비스 모델에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-120">(The actual cost depends on the service model of the ITSP you choose.)</span></span>

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="a9909-121">SIP 트렁크 및 PSTN 게이트웨이 또는 ip-pbx 호스팅</span><span class="sxs-lookup"><span data-stu-id="a9909-121">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="a9909-122">SIP trunks는 서비스 공급자에 직접 연결 되므로 PSTN 게이트웨이와 해당 관리 비용 및 복잡도를 없앨 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-122">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity.</span></span> <span data-ttu-id="a9909-123">SIP 트렁크를 사용 하면 유지 관리 및 관리 감소를 통해 비용을 크게 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-123">Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

### <a name="expanded-voip-services"></a><span data-ttu-id="a9909-124">확장 된 VoIP 서비스</span><span class="sxs-lookup"><span data-stu-id="a9909-124">Expanded VoIP Services</span></span>

<span data-ttu-id="a9909-125">음성 기능은 종종 SIP 트렁크를 배포 하는 주요 동기 이지만, 음성 지원은 첫 번째 단계에 불과합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-125">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="a9909-126">SIP 트렁크을 사용 하면 VoIP 기능을 확장 하 고 비즈니스용 Skype 서버를 사용 하 여 다양 한 서비스 집합을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-126">With SIP trunking, you can extend VoIP capabilities and enable Skype for Business Server to deliver a richer set of services.</span></span> <span data-ttu-id="a9909-127">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-127">For example:</span></span>

- <span data-ttu-id="a9909-128">비즈니스용 Skype 서버를 실행 하 고 있지 않은 장치에 대 한 향상 된 현재 상태 감지 기능을 통해 휴대 전화를 사용 하는 사용자가 휴대폰 통화를 할 때 더 나은 통합을 제공 해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-128">Enhanced presence detection for devices that are not running Skype for Business Server can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

- <span data-ttu-id="a9909-129">E9-1-1-긴급 통화 911 전화를 받은 기관에서 전화 번호에서 발신자의 위치를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-129">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller's location from his or her telephone number.</span></span>

> [!NOTE]
> <span data-ttu-id="a9909-130">지원 되는 서비스 목록에 대 한 자세한 내용을 문의 하 여 조직에 대해 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-130">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>

### <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="a9909-131">SIP Trunks 및 직접 SIP 연결</span><span class="sxs-lookup"><span data-stu-id="a9909-131">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="a9909-132">트렁크는 회로 교환 기술에서 파생 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-132">The term trunk is derived from circuit-switched technology.</span></span> <span data-ttu-id="a9909-133">전화 교환 장비를 연결 하는 전용 물리적 회선을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-133">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="a9909-134">TDM (시간 구분 멀티플렉싱) trunks와 마찬가지로, SIP trunks는 두 개의 별도 SIP 네트워크 (비즈니스용 Skype Server enterprise 및 ITSP) 간 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-134">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Skype for Business Server enterprise and the ITSP.</span></span> <span data-ttu-id="a9909-135">회로 전환 trunks와 달리 SIP trunks는 지원 되는 SIP 트렁크 연결 형식에 따라 설정할 수 있는 가상 연결입니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-135">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span>

<span data-ttu-id="a9909-136">반면에 직접 SIP 연결은 로컬 네트워크 경계 (즉, 내부 네트워크 내에서 PSTN (공개 통신 네트워크) 게이트웨이 또는 PBX (개인 분기 교환)에 연결 되지 않는 SIP 연결입니다.)</span><span class="sxs-lookup"><span data-stu-id="a9909-136">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="a9909-137">비즈니스용 Skype 서버에서 직접 SIP 연결을 사용 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 직접 sip 연결](direct-sip.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9909-137">For details about how you can use direct SIP connections with Skype for Business Server, see [Direct SIP connections in Skype for Business Server](direct-sip.md).</span></span>

## <a name="how-do-i-implement-sip-trunking"></a><span data-ttu-id="a9909-138">SIP 트렁크 구현 하는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="a9909-138">How do I implement SIP Trunking?</span></span>

<span data-ttu-id="a9909-139">SIP 트렁크을 구현 하려면, 필요할 때 비즈니스용 Skype 서버 클라이언트와 서비스 공급자 및 transcodes 미디어 간의 통신 세션에 대 한 프록시 역할을 하는 중재 서버를 통해 연결을 라우팅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-139">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Skype for Business Server clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="a9909-140">각 중재 서버에는 내부 네트워크 인터페이스와 외부 네트워크 인터페이스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-140">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="a9909-141">내부 인터페이스가 프런트 엔드 서버에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-141">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="a9909-142">외부 인터페이스는 일반적으로 중재 서버를 PSTN (공개 교환 전화 네트워크) 게이트웨이 또는 IP-PBX에 연결 하는 데 사용 되기 때문에 게이트웨이 인터페이스 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-142">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="a9909-143">SIP 트렁크를 구현 하려면 중재 서버의 외부 인터페이스를 ITSP의 외부 edge 구성 요소에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-143">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span> <span data-ttu-id="a9909-144">ITSP의 외부에 지 구성 요소는 SBC (세션 경계 컨트롤러), 라우터 또는 게이트웨이 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-144">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>

<span data-ttu-id="a9909-145">중재 서버에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 중재 서버 구성 요소](mediation-server.md)조정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9909-145">For details about Mediation Servers, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>

### <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="a9909-146">중앙 집중화 및 분산 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="a9909-146">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="a9909-147">중앙 집중화 된 SIP 트렁크는 지점 사이트 트래픽을 포함 하 여 모든 VoIP 트래픽을 중앙 사이트를 통해 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-147">Centralized SIP trunking routes all VoIP traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="a9909-148">중앙 집중화 된 배포 모델은 간단 하 고 비용 효율적 이며, 일반적으로 비즈니스용 Skype 서버에서 SIP trunks을 구현 하는 데 권장 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-148">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Skype for Business Server.</span></span>

<span data-ttu-id="a9909-149">분산 SIP 트렁크 하나 이상의 지점 사이트에서 로컬 SIP trunks을 구현 하는 배포 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-149">Distributed SIP trunking is a deployment model in which you implement local SIP trunks at one or more branch sites.</span></span> <span data-ttu-id="a9909-150">그러면 중앙 사이트를 거치지 않고 지사 사이트에서 서비스 공급자로 직접 VoIP 트래픽을 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-150">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="a9909-151">분산 SIP 트렁크는 다음과 같은 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-151">Distributed SIP trunking is required only in the following cases:</span></span>

- <span data-ttu-id="a9909-152">지점 사이트에는 survivable 전화 연결이 필요 합니다 (예: WAN이 작동 하지 않는 경우).</span><span class="sxs-lookup"><span data-stu-id="a9909-152">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="a9909-153">이 요구 사항은 각 지점 사이트에 대해 분석 되어야 합니다. 일부 분기에는 중복 및 장애 조치가 필요할 수 있지만 다른 경우에는 그렇지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-153">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

- <span data-ttu-id="a9909-154">두 중앙 사이트 간에 복원성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-154">Resiliency is required between two central sites.</span></span> <span data-ttu-id="a9909-155">각 중앙 사이트에서 SIP 트렁크가 종료 되는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-155">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="a9909-156">예를 들어 더블린 및 Tukwila 중앙 사이트가 있고 두 사이트의 SIP 트렁크만 사용 하는 경우 트렁크가 다운 되 면 다른 사이트의 사용자가 PSTN 통화를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-156">For example, if you have Dublin and Tukwila central sites and both use only one site's SIP trunk, if the trunk goes down, the other site's users cannot make PSTN calls.</span></span>

- <span data-ttu-id="a9909-157">분기 사이트와 중앙 사이트는 서로 다른 국가/지역에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-157">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="a9909-158">호환성과 법적 고 지는 국가/지역에 따라 적어도 하나 이상의 SIP 트렁크가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-158">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="a9909-159">예를 들어 유럽 연합에서 통신은 중앙 집중화 된 지점에서 로컬로 종료 하지 않고는 국가/지역에서 나갈 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-159">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="a9909-160">사이트의 지리적 위치와 엔터프라이즈 내에서 예상 되는 트래픽 크기에 따라 중앙 SIP 트렁크를 통해 모든 사용자를 라우팅 하지 않으려는 경우 또는 지점 사이트의 SIP 트렁크를 통해 일부 사용자의 경로를 설정 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-160">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="a9909-161">필요 사항을 분석 하려면 다음 질문에 대답 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9909-161">To analyze your needs, answer the following questions:</span></span>

- <span data-ttu-id="a9909-162">각 사이트의 크기 (즉, 엔터프라이즈 음성에 대해 설정 된 사용자 수)는 얼마나 되나요?</span><span class="sxs-lookup"><span data-stu-id="a9909-162">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

- <span data-ttu-id="a9909-163">각 사이트에서 바로 안쪽으로 거는 전화 접속 (a) 번호를 통해 가장 많은 전화를 받을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="a9909-163">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="a9909-164">중앙 집중화 또는 분산 SIP 트렁크 배포 여부에 대 한 결정에는 비용 이점 분석이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-164">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="a9909-165">때로는 필요 하지 않은 경우에도 분산 배포 모델을 선택 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-165">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="a9909-166">완전히 중앙 집중화 된 배포에서는 모든 지점 사이트 트래픽이 WAN 링크를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-166">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="a9909-167">WAN 연결에 필요한 대역폭을 지불 하는 대신 분산 SIP 트렁크를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-167">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="a9909-168">예를 들어 중앙 사이트에 페더레이션 하는 지점 사이트에 스탠더드 버전 서버를 배포 하거나 small gateway를 사용 하 여 Survivable Branch 기기 또는 Survivable Branch 서버를 배포 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-168">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="a9909-169">분산 SIP 트렁크에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 Branch 사이트 SIP 트렁크](branch-site.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9909-169">For details about distributed SIP trunking, see [Branch site SIP trunking in Skype for Business Server](branch-site.md).</span></span>

### <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="a9909-170">지원 되는 SIP 트렁크 연결 유형</span><span class="sxs-lookup"><span data-stu-id="a9909-170">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="a9909-171">비즈니스용 Skype 서버는 SIP 트렁크에 대해 다음 연결 유형을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-171">Skype for Business Server supports the following connection types for SIP trunking:</span></span>

- <span data-ttu-id="a9909-172">MPLS (멀티 프로토콜 레이블 전환)는 하나의 네트워크 노드에서 다음으로 데이터를 전송 하 고 전달 하는 개인 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-172">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="a9909-173">MPLS 네트워크의 대역폭은 다른 구독자와 공유 되며 각 데이터 패킷에는 다른 구독자의 데이터를 구분 하는 레이블이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-173">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber's data from another's.</span></span> <span data-ttu-id="a9909-174">이 연결 형식에는 가상 개인 네트워크 (VPN)가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-174">This connection type does not require a virtual private network (VPN).</span></span> <span data-ttu-id="a9909-175">잠재적인 단점은 VoIP 트래픽이 우선 순위로 지정 되지 않는 이상 과도 한 IP 트래픽이 VoIP 작업을 방해할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-175">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

- <span data-ttu-id="a9909-176">다른 트래픽이 없는 개인 연결 (예: 임대한 광섬유 연결 또는 T1 회선)은 일반적으로 가장 안정적이 고 안전한 연결 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-176">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type.</span></span> <span data-ttu-id="a9909-177">이 연결 유형은 가장 높은 통화 운반 용량을 제공 하지만 일반적으로 가장 비쌉니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-177">This connection type provides the highest call-carrying capacity, but it is typically the most expensive.</span></span> <span data-ttu-id="a9909-178">VPN이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-178">VPN is not required.</span></span> <span data-ttu-id="a9909-179">개인 연결은 높은 통화 볼륨이 나 엄격한 보안 및 가용성 요구 사항이 있는 조직에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-179">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

- <span data-ttu-id="a9909-180">인터넷은 가장 저렴 한 연결 형식 이지만 최소한의 신뢰성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-180">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="a9909-181">인터넷 연결은 VPN이 필요한 비즈니스용 Skype Server SIP 트렁크 연결 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-181">Internet connection is the only Skype for Business Server SIP trunking connection type that requires VPN.</span></span>

#### <a name="selecting-a-connection-type"></a><span data-ttu-id="a9909-182">연결 형식 선택</span><span class="sxs-lookup"><span data-stu-id="a9909-182">Selecting a Connection Type</span></span>

<span data-ttu-id="a9909-183">기업의 가장 적합 한 SIP 트렁크 연결 유형은 사용자의 요구와 예산에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-183">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

- <span data-ttu-id="a9909-184">중간 규모 또는 대기업의 경우 일반적으로 MPLS 네트워크에서 가장 큰 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-184">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value.</span></span> <span data-ttu-id="a9909-185">특별 한 사설 네트워크 보다 저렴 한 요금으로 필요한 대역폭을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-185">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

- <span data-ttu-id="a9909-186">대규모 기업은 개인 광섬유, T1, T3 이상 연결 (E1, E3 또는 그 이상의 유럽 연합)을 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-186">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

- <span data-ttu-id="a9909-187">낮은 규모의 중소기업 또는 저렴 한 통화를 사용 하는 지사 사이트의 경우 인터넷을 통해 SIP를 트렁크 하는 것이 가장 좋은 선택 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-187">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="a9909-188">중간 규모 또는 대규모 사이트에는이 연결 유형을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-188">This connection type is not recommended for mid-size or larger sites.</span></span>

### <a name="bandwidth-requirements"></a><span data-ttu-id="a9909-189">대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9909-189">Bandwidth Requirements</span></span>

<span data-ttu-id="a9909-190">구현에 필요한 대역폭의 양은 통화 용량 (지원할 동시 통화 수)에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-190">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support).</span></span> <span data-ttu-id="a9909-191">지불한 최고 용량을 충분히 활용할 수 있도록 대역폭 가용성을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-191">You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for.</span></span> <span data-ttu-id="a9909-192">다음 공식을 사용 하 여 SIP 트렁크 최고 대역폭 요구 사항을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-192">Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="a9909-193">SIP 트렁크 최고 대역폭 = 최대 동시 통화 x (64 kbps + 헤더 크기)</span><span class="sxs-lookup"><span data-stu-id="a9909-193">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

> [!NOTE]
> <span data-ttu-id="a9909-194">헤더 크기는 최대 20 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-194">Header size is 20 bytes maximum.</span></span>

### <a name="codec-support"></a><span data-ttu-id="a9909-195">코덱 지원</span><span class="sxs-lookup"><span data-stu-id="a9909-195">Codec Support</span></span>

<span data-ttu-id="a9909-196">비즈니스용 Skype 서버는 다음 코덱으로만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-196">Skype for Business Server supports only the following codecs:</span></span>

- <span data-ttu-id="a9909-197">711 a-법률 (주로 북미 지역 외에 사용)</span><span class="sxs-lookup"><span data-stu-id="a9909-197">G.711 a-law (used primarily outside North America)</span></span>

- <span data-ttu-id="a9909-198">711 μ-사법 기관 (북미 지역에서 사용)</span><span class="sxs-lookup"><span data-stu-id="a9909-198">G.711 µ-law (used in North America)</span></span>

### <a name="internet-telephony-service-provider"></a><span data-ttu-id="a9909-199">인터넷 전화 통신 서비스 공급자</span><span class="sxs-lookup"><span data-stu-id="a9909-199">Internet Telephony Service Provider</span></span>

<span data-ttu-id="a9909-200">SIP 트렁크 연결의 서비스 공급자 쪽을 구현 하는 방법은 ITSP에 따라 달라 지는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-200">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="a9909-201">배포 정보는 서비스 공급자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9909-201">For deployment information, contact your service provider.</span></span> <span data-ttu-id="a9909-202">인증 된 SIP 트렁크 서비스 공급자 목록은 [Microsoft 통합 커뮤니케이션 오픈 상호 운용성 프로그램 웹 사이트](https://go.microsoft.com/fwlink/p/?LinkId=287029)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9909-202">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](https://go.microsoft.com/fwlink/p/?LinkId=287029).</span></span>

<span data-ttu-id="a9909-203">Microsoft 인증 SIP 트렁크 공급자에 대 한 자세한 내용은 Microsoft 담당자에 게 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9909-203">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9909-204">Microsoft 인증 서비스 공급자를 사용 하 여 현재 ITSP가 SIP 트렁크를 통과 하는 모든 기능을 지원 하는지 확인 해야 합니다 (예: 세션 설정 및 관리, 모든 확장 된 VoIP 서비스 지원).</span><span class="sxs-lookup"><span data-stu-id="a9909-204">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services).</span></span> <span data-ttu-id="a9909-205">Microsoft 기술 지원은 인증 되지 않은 공급자를 사용 하는 구성으로 확장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-205">Microsoft technical support does not extend to configurations that use noncertified providers.</span></span> <span data-ttu-id="a9909-206">현재 SIP 트렁크 인증을 받지 않은 인터넷 서비스 공급자를 사용 하는 경우 해당 공급자를 ISP로 계속 사용할 수 있도록 선택 하 고 Microsoft에서 SIP 트렁크에 대해 인증 한 공급자를 사용 하도록 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-206">If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>

### <a name="topologies-and-components-for-sip-trunking"></a><span data-ttu-id="a9909-207">SIP 트렁크 토폴로지 및 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a9909-207">Topologies and Components for SIP Trunking</span></span>

<span data-ttu-id="a9909-208">다음 그림은 비즈니스용 Skype 서버의 SIP 트렁크 토폴로지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-208">The following figure depicts the SIP trunking topology in Skype for Business Server.</span></span>

<span data-ttu-id="a9909-209">**SIP 트렁크 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="a9909-209">**SIP trunking topology**</span></span>

![SIP 트렁크 토폴로지](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

<span data-ttu-id="a9909-211">다이어그램에 표시 된 대로 IP 가상 개인 네트워크 (VPN)는 엔터프라이즈 네트워크와 PSTN (공개 통신 네트워크) 서비스 공급자 간의 연결에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-211">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider.</span></span> <span data-ttu-id="a9909-212">이 개인 네트워크의 용도는 IP 연결을 제공 하 고 보안을 강화 하며 서비스 품질 (옵션) 보장을 받을 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-212">The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees.</span></span> <span data-ttu-id="a9909-213">VPN의 특성상 SIP 신호 소통량에는 TLS (전송 계층 보안)를 사용 하거나 미디어 트래픽에 대 한 보안 실시간 전송 프로토콜 (SRTP)을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-213">Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic.</span></span> <span data-ttu-id="a9909-214">따라서 엔터프라이즈와 서비스 공급자 간의 연결은 IP VPN을 통해 터널링 된 미디어에 대 한 UDP를 통해 SIP 및 일반 실시간 전송 프로토콜 (터널)에 대 한 일반 TCP 연결로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-214">Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN.</span></span> <span data-ttu-id="a9909-215">Vpn 라우터 간의 모든 방화벽이 VPN 라우터 통신을 허용 하도록 포트가 열려 있는지 확인 하 고 VPN 라우터의 외부 경계에 있는 IP 주소를 공개적으로 라우팅할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-215">Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9909-216">서비스 공급자에 게 문의 하 여 장애 조치를 포함 하 여 고가용성에 대 한 지원을 제공 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-216">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="a9909-217">이 경우 설정 절차를 결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-217">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="a9909-218">예를 들어 각 중재 서버에서 하나의 IP 주소와 하나의 SIP 트렁크만 구성 해야 하나요, 아니면 각 중재 서버에서 여러 SIP trunks를 구성 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="a9909-218">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span> <span data-ttu-id="a9909-219">> 여러 중앙 사이트가 있는 경우 서비스 공급자에 게 다른 중앙 사이트와의 연결을 설정 하는 기능이 있는지 여부를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-219">> If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>

> [!NOTE]
> <span data-ttu-id="a9909-220">SIP 트렁크의 경우 독립 실행형 중재 서버를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-220">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="a9909-221">자세한 내용은 배포 설명서에서 [중재 서버 배포 및 피어 정의](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9909-221">For details, see [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx) in the Deployment documentation.</span></span>

### <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="a9909-222">SIP 트렁크 중재 서버 보안 유지</span><span class="sxs-lookup"><span data-stu-id="a9909-222">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="a9909-223">보안을 위해서는 두 VPN 라우터 간의 각 연결에 대해 VLAN (가상 LAN)을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-223">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers.</span></span> <span data-ttu-id="a9909-224">VLAN을 설정 하는 실제 프로세스는 라우터 제조업체 마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-224">The actual process for setting up a VLAN varies from one router manufacturer to another.</span></span> <span data-ttu-id="a9909-225">자세한 내용은 라우터 공급 업체에 문의 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9909-225">For details, contact your router vendor.</span></span>

<span data-ttu-id="a9909-226">다음 지침을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-226">We recommend that you follow these guidelines:</span></span>

- <span data-ttu-id="a9909-227">중재 서버와 경계 네트워크 (DMZ, 완충 영역 및 스크린 된 서브넷이 라고도 함)의 VPN 라우터 사이에 VLAN (가상 LAN)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-227">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

- <span data-ttu-id="a9909-228">브로드캐스트 또는 멀티 캐스트 패킷을 라우터에서 VLAN으로 전송 하는 것을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-228">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

- <span data-ttu-id="a9909-229">라우터에서 중재 서버를 제외한 아무 곳에 나 트래픽을 라우팅하는 라우팅 규칙을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-229">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="a9909-230">VPN 서버를 사용 하는 경우 다음 지침을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-230">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

- <span data-ttu-id="a9909-231">VPN 서버와 중재 서버 간에 VLAN을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-231">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

- <span data-ttu-id="a9909-232">브로드캐스트 또는 멀티 캐스트 패킷을 VPN 서버에서 VLAN으로 전송 하도록 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-232">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

- <span data-ttu-id="a9909-233">중재 서버를 제외한 아무 곳으로도 VPN 서버 트래픽을 라우팅하는 라우팅 규칙을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-233">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

- <span data-ttu-id="a9909-234">GRE (generic routing 캡슐화)를 사용 하 여 VPN의 데이터를 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9909-234">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

## <a name="see-also"></a><span data-ttu-id="a9909-235">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9909-235">See also</span></span>

[<span data-ttu-id="a9909-236">비즈니스용 Skype Server의 지점 사이트 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="a9909-236">Branch site SIP trunking in Skype for Business Server</span></span>](branch-site.md)

