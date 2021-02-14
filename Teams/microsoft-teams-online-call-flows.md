---
title: Microsoft Teams 통화 흐름
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: Teams가 피어 투 피어 미디어 통신에 사용되는 고유한 팀 흐름뿐만 아니라 다양한 토폴로지에서 Office 365 흐름을 사용하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 13bd0479436963402124e7edea049bcc250d3515
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638667"
---
# <a name="microsoft-teams-call-flows"></a><span data-ttu-id="17461-103">Microsoft Teams 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="17461-103">Microsoft Teams call flows</span></span>

> [!TIP]
> <span data-ttu-id="17461-104">이 세션에서는 Teams가 네트워크를 활용하는 방법과 최적의 네트워크 연결을 계획하는 방법( [Teams 네트워크 계획)을 알아보는 세션을 시청합니다.](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="17461-104">Watch this session to learn how Teams leverages your network and how to plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking).</span></span>

## <a name="overview"></a><span data-ttu-id="17461-105">개요</span><span class="sxs-lookup"><span data-stu-id="17461-105">Overview</span></span>

<span data-ttu-id="17461-106">이 문서에서는 Teams가 다양한 토폴로지에서 Microsoft 365 또는 Office 365 통화 흐름을 사용하는 방법을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-106">This article describes how Teams uses Microsoft 365 or Office 365 call flows in various topologies.</span></span> <span data-ttu-id="17461-107">또한 피어 투 피어 미디어 통신에 사용되는 고유한 Teams 흐름에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-107">In addition, it describes unique Teams flows that are used for peer-to-peer media communication.</span></span> <span data-ttu-id="17461-108">이 문서에서는 이러한 흐름, 해당 목적 및 네트워크의 원본 및 종료에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-108">The document describes these flows, their purpose, and their origin and termination on the network.</span></span> <span data-ttu-id="17461-109">이 문서에서는 다음을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-109">For purposes of this article, assume the following:</span></span>

- <span data-ttu-id="17461-110">Flow X는 클라우드에서 Microsoft 365 또는 Office 365 서비스와 통신하는 데는 클라우드 클라이언트에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-110">Flow X is used by the on-premises client to communicate with the Microsoft 365 or Office 365 service in the cloud.</span></span> <span data-ttu-id="17461-111">고객 네트워크에서 시작하여 Microsoft 365 또는 Office 365에서 엔드포인트로 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-111">It originates from the customer network, and it terminates as an endpoint in Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="17461-112">Flow Y는 Microsoft 365 또는 Office 365가 종속된 인터넷의 서비스와 통신하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-112">Flow Y is used by the on-premises client to communicate with a service on the Internet that Microsoft 365 or Office 365 has a dependency on.</span></span> <span data-ttu-id="17461-113">고객 네트워크에서 시작되고 인터넷의 엔드포인트로 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-113">It originates from the customer network, and it terminates as an endpoint on the Internet.</span></span>

<span data-ttu-id="17461-114">이 문서에서는 다음 정보를 다 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-114">This article covers the following information:</span></span>

- <span data-ttu-id="17461-115">**배경.**</span><span class="sxs-lookup"><span data-stu-id="17461-115">**Background**.</span></span> <span data-ttu-id="17461-116">흐름이 트래버스할 수 있는 네트워크, 트래픽 유형, 고객 네트워크에서 Microsoft 365 또는 Office 365 서비스 엔드포인트로의 연결 지침, 타사 구성 요소와의 상호 연동성, Teams에서 미디어 흐름을 선택하는 데 사용하는 원칙 등의 배경 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-116">Provides background information such as networks that the flows may traverse, types of traffic, connectivity guidance from the customer network to Microsoft 365 or Office 365 service endpoints, interoperability with third-party components, and principles that are used by Teams to select media flows.</span></span>

- <span data-ttu-id="17461-117">**다양한 토폴로지에서 흐름을 호출합니다.**</span><span class="sxs-lookup"><span data-stu-id="17461-117">**Call flows in various topologies**.</span></span> <span data-ttu-id="17461-118">다양한 토폴로지에서 호출 흐름을 사용하는 방법을 보여 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-118">Illustrates the use of call flows in various topologies.</span></span> <span data-ttu-id="17461-119">각 토폴로지의 경우 섹션에서는 지원되는 모든 흐름을 열회하고 이러한 흐름이 여러 사용 사례에서 사용되는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-119">For each topology, the section enumerates all supported flows and illustrates how these flows are used in several use cases.</span></span> <span data-ttu-id="17461-120">각 사용 사례에 대해 흐름 다이어그램을 사용하여 흐름의 시퀀스 및 선택을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-120">For each use case, it describes the sequence and selection of flows using a flow diagram.</span></span>

- <span data-ttu-id="17461-121">**Express 경로 최적화가 있는 Teams.**</span><span class="sxs-lookup"><span data-stu-id="17461-121">**Teams with Express Route optimization**.</span></span> <span data-ttu-id="17461-122">간단한 토폴로지로 설명된 Express Route가 최적화를 위해 배포될 때 이러한 흐름이 사용되는 방법을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-122">Describes how these flows are used when Express Route is deployed for optimization, illustrated using a simple topology.</span></span>

## <a name="background"></a><span data-ttu-id="17461-123">배경</span><span class="sxs-lookup"><span data-stu-id="17461-123">Background</span></span>

### <a name="network-segments"></a><span data-ttu-id="17461-124">네트워크 세그먼트</span><span class="sxs-lookup"><span data-stu-id="17461-124">Network segments</span></span>

<span data-ttu-id="17461-125">**고객 네트워크.**</span><span class="sxs-lookup"><span data-stu-id="17461-125">**Customer network**.</span></span> <span data-ttu-id="17461-126">제어하고 관리하는 네트워크 세그먼트입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-126">This is the network segment that you control and manage.</span></span> <span data-ttu-id="17461-127">여기에는 유선 또는 무선, 사무실 건물 간 연결, 프레미스 데이터 센터에 대한 연결, 인터넷 공급자, Express Route 또는 기타 개인 피어링에 대한 연결 등 고객 사무실 내의 모든 고객 연결이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-127">This includes all customer connections within customer offices, whether wired or wireless, connections between office buildings, connections to on-premises datacenters, and your connections to Internet providers, Express Route, or any other private peering.</span></span>

<span data-ttu-id="17461-128">일반적으로 고객 네트워크에는 방화벽 및/또는 프록시 서버가 있는 여러 네트워크 경계가 있습니다. 이 경계는 조직의 보안 정책을 적용하고 설정 및 구성한 특정 네트워크 트래픽만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-128">Typically, a customer network has several network perimeters with firewalls and/or proxy servers, which enforce your organization's security policies, and that only allow certain network traffic that you have set up and configured.</span></span> <span data-ttu-id="17461-129">이 네트워크를 관리하기 때문에 네트워크 성능을 직접 제어할 수 있으며 네트워크 내의 사이트와 네트워크에서 Microsoft 365 또는 Office 365 네트워크로의 성능 유효성을 검사하기 위해 네트워크 평가를 완료하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-129">Because you manage this network, you have direct control over the performance of the network, and we recommend that you complete network assessments to validate performance both within sites in your network and from your network to the Microsoft 365 or Office 365 network.</span></span>

<span data-ttu-id="17461-130">**인터넷.**</span><span class="sxs-lookup"><span data-stu-id="17461-130">**Internet**.</span></span> <span data-ttu-id="17461-131">고객 네트워크 외부에서 Microsoft 365 또는 Office 365에 연결하는 사용자가 사용할 전체 네트워크의 일부인 네트워크 세그먼트입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-131">This is the network segment that is part of your overall network that will be used by users who are connecting to Microsoft 365 or Office 365 from outside of the customer network.</span></span> <span data-ttu-id="17461-132">고객 네트워크에서 Microsoft 365 또는 Office 365로의 일부 트래픽에서도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-132">It is also used by some traffic from the customer network to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="17461-133">**방문한 또는 게스트 개인 네트워크.**</span><span class="sxs-lookup"><span data-stu-id="17461-133">**Visited or guest private network**.</span></span> <span data-ttu-id="17461-134">이는 사용자와 게스트가 방문할 수 있는 공용 인터넷 외부의 네트워크 세그먼트입니다(예: 홈 개인 네트워크 또는 엔터프라이즈 개인 네트워크, Teams 서비스를 조작하는 사용자와 해당 고객이 있을 수 있는 Teams를 배포하지 않는 경우).</span><span class="sxs-lookup"><span data-stu-id="17461-134">This is the network segment outside your customer network, but not in the public Internet, that your users and their guests may visit (for example, a home private network or an enterprise private network, that does not deploy Teams, where your users and their customers that interact with Teams services may reside).</span></span>

> [!NOTE]
> <span data-ttu-id="17461-135">Microsoft 365 또는 Office 365에 대한 연결은 이러한 네트워크에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-135">Connectivity to Microsoft 365 or Office 365 is also applicable to these networks.</span></span>

<span data-ttu-id="17461-136">**Microsoft 365 또는 Office 365.**</span><span class="sxs-lookup"><span data-stu-id="17461-136">**Microsoft 365 or Office 365**.</span></span> <span data-ttu-id="17461-137">Microsoft 365 또는 Office 365 서비스를 지원하는 네트워크 세그먼트입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-137">This is the network segment that supports Microsoft 365 or Office 365 services.</span></span> <span data-ttu-id="17461-138">대부분의 위치에서 고객 네트워크에 근접한 에지가 있는 전 세계에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-138">It is distributed worldwide with edges in proximity to the customer network in most locations.</span></span> <span data-ttu-id="17461-139">함수에는 전송 릴레이, 회의 서버 및 미디어 프로세서가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-139">Functions include Transport Relay, conferencing server, and Media Processor.</span></span>

<span data-ttu-id="17461-140">**Express Route(선택 사항)**.</span><span class="sxs-lookup"><span data-stu-id="17461-140">**Express Route (optional)**.</span></span> <span data-ttu-id="17461-141">Microsoft 365 또는 Office 365 네트워크에 대한 전용 개인 연결을 제공하게 될 전체 네트워크의 일부인 네트워크 세그먼트입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-141">This is the network segment that is part of your overall network that will give you a dedicated, private connection to the Microsoft 365 or Office 365 network.</span></span>

### <a name="types-of-traffic"></a><span data-ttu-id="17461-142">트래픽 유형</span><span class="sxs-lookup"><span data-stu-id="17461-142">Types of traffic</span></span>

<span data-ttu-id="17461-143">**실시간 미디어.**</span><span class="sxs-lookup"><span data-stu-id="17461-143">**Real-time media**.</span></span> <span data-ttu-id="17461-144">오디오, 비디오 및 화면 공유 워크로드를 지원하는 RTP(실시간 전송 프로토콜) 내에서 캡슐화되는 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-144">Data encapsulated within Real-time Transport Protocol (RTP) that supports audio, video, and screen sharing workloads.</span></span> <span data-ttu-id="17461-145">일반적으로 미디어 트래픽은 대기 시간이 매우 길기 때문에 이 트래픽이 가능한 가장 직접적인 경로를 사용하게 하고, 품질 관점에서 대화형 실시간 미디어에 가장 적합한 전송 계층 프로토콜로 UDP와 TCP를 사용하려는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-145">In general, media traffic is highly latency sensitive, so you would want this traffic to take the most direct path possible, and to use UDP versus TCP as the transport layer protocol, which is the best transport for interactive real time media from a quality perspective.</span></span> <span data-ttu-id="17461-146">(마지막 수단으로 미디어는 TCP/IP를 사용할 수 있으며 HTTP 프로토콜 내에서 터널링될 수도 있지만 품질이 나쁘기 때문에 권장되지 않습니다.) RTP 흐름은 페이로드만 암호화되는 SRTP를 사용하여 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-146">(Note that as a last resort, media can use TCP/IP and also be tunneled within the HTTP protocol, but it is not recommended due to bad quality implications.) RTP flow is secured using SRTP, in which only the payload is encrypted.</span></span>

<span data-ttu-id="17461-147">**신호.**</span><span class="sxs-lookup"><span data-stu-id="17461-147">**Signaling**.</span></span> <span data-ttu-id="17461-148">클라이언트와 서버 간의 통신 링크 또는 활동을 제어하는 데 사용되는 다른 클라이언트(예: 호출이 시작될 때) 및 인스턴트 메시지를 전달하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-148">The communication link between the client and server, or other clients that are used to control activities (for example, when a call is initiated), and deliver instant messages.</span></span> <span data-ttu-id="17461-149">대부분의 신호 트래픽은 HTTPS 기반 REST 인터페이스를 사용하며, 일부 시나리오(예: Microsoft 365 또는 Office 365와 세션 테두리 컨트롤러 간의 연결)에서는 SIP 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-149">Most signaling traffic uses the HTTPS-based REST interfaces, though in some scenarios (for example, connection between Microsoft 365 or Office 365 and a Session Border Controller) it uses SIP protocol.</span></span> <span data-ttu-id="17461-150">이 트래픽은 대기 시간에 훨씬 덜 민감하지만 엔드포인트 간의 대기 시간이 몇 초를 초과하는 경우 서비스 중단 또는 호출 시간 제한이 발생할 수 있다는 것을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-150">It's important to understand that this traffic is much less sensitive to latency but may cause service outages or call timeouts if latency between the endpoints exceeds several seconds.</span></span>

### <a name="connectivity-to-microsoft-365-or-office-365"></a><span data-ttu-id="17461-151">Microsoft 365 또는 Office 365에 연결</span><span class="sxs-lookup"><span data-stu-id="17461-151">Connectivity to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="17461-152">Teams는 [인터넷에 연결해야 합니다.](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity)</span><span class="sxs-lookup"><span data-stu-id="17461-152">Teams requires [connectivity to the Internet](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity).</span></span> <span data-ttu-id="17461-153">Teams 엔드포인트 URL 및 IP 주소 범위는 [Office 365 URL](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)및 IP 주소 범위에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-153">Teams endpoint URLs and IP address ranges are listed in [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="17461-154">(TCP 포트 80 및 443 및 UDP 포트 3478~3481에 대한 개방형 연결이 필요합니다.) 또한 Teams는 비즈니스용 Skype Online에 종속되고 인터넷에도 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-154">(Note that open connectivity to TCP ports 80 and 443, and to UDP ports 3478 through 3481, is required.) Furthermore, Teams has a dependency on Skype for Business Online, which must also be connected to the Internet.</span></span>

<span data-ttu-id="17461-155">Teams 미디어 흐름 연결은 표준 IETF ICE(대화형 연결 수립) 절차를 사용하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-155">Teams media flows connectivity is implemented using standard IETF Interactive Connectivity Establishment (ICE) procedures.</span></span>

### <a name="interoperability-restrictions"></a><span data-ttu-id="17461-156">상호 연동성 제한</span><span class="sxs-lookup"><span data-stu-id="17461-156">Interoperability restrictions</span></span>

<span data-ttu-id="17461-157">**타사 미디어 릴레이.**</span><span class="sxs-lookup"><span data-stu-id="17461-157">**Third-party media relays**.</span></span> <span data-ttu-id="17461-158">Teams 미디어 흐름(즉, 미디어 끝점 중 하나는 Teams)은 Teams 또는 비즈니스용 Skype 네이티브 미디어 릴레이만 트래버스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-158">A Teams media flow (that is, where one of the media endpoints is Teams) may traverse only Teams or Skype for Business native media relays.</span></span> <span data-ttu-id="17461-159">타사 미디어 릴레이와의 상호 연동성은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-159">Interoperability with a third-party media relay is not supported.</span></span> <span data-ttu-id="17461-160">(PSTN을 사용하는 경계의 타사 SBC는 SRTP를 사용하여 보호되는 RTP/RTCP 스트림을 종료하고 다음 홉에 릴레이하지 말아야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="17461-160">(Note that a third-party SBC on the boundary with PSTN must terminate RTP/RTCP stream, secured using SRTP, and not relay it to the next hop.)</span></span>

<span data-ttu-id="17461-161">**타사 SIP 프록시 서버.**</span><span class="sxs-lookup"><span data-stu-id="17461-161">**Third-party SIP proxy servers**.</span></span> <span data-ttu-id="17461-162">타사 SBC 및/또는 게이트웨이를 통해 SIP 대화 상자를 신호를 전송하는 Teams는 Teams 또는 비즈니스용 Skype 네이티브 SIPx를 트래버스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-162">A Teams signaling SIP dialog with a third-party SBC and/or gateway may traverse Teams or Skype for Business native SIP proxies.</span></span> <span data-ttu-id="17461-163">타사 SIP 프록시와의 상호 연동성은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-163">Interoperability with a third-party SIP proxy is not supported.</span></span>

<span data-ttu-id="17461-164">**타사 B2BUA(또는 SBC)**</span><span class="sxs-lookup"><span data-stu-id="17461-164">**Third-party B2BUA (or SBC)**.</span></span> <span data-ttu-id="17461-165">PSTN과의 Teams 미디어 흐름은 타사 SBC에 의해 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-165">A Teams media flow to and from the PSTN is terminated by a third-party SBC.</span></span> <span data-ttu-id="17461-166">그러나 Teams 네트워크 내에서 타사 SBC와의 상호 연동성(타사 SBC가 Teams 또는 비즈니스용 Skype 엔드포인트 두 개를 중재하는 경우)은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-166">However, interoperability with a third-party SBC within the Teams network (where a third-party SBC mediates two Teams or Skype for Business endpoints) is not supported.</span></span>

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a><span data-ttu-id="17461-167">Microsoft Teams에서 권장되지 않는 기술</span><span class="sxs-lookup"><span data-stu-id="17461-167">Technologies that are not recommended with Microsoft Teams</span></span>

<span data-ttu-id="17461-168">**VPN 네트워크.**</span><span class="sxs-lookup"><span data-stu-id="17461-168">**VPN network**.</span></span> <span data-ttu-id="17461-169">미디어 트래픽(또는 흐름 2)에는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-169">It is not recommended for media traffic (or flow 2').</span></span> <span data-ttu-id="17461-170">VPN 클라이언트는 분할된 VPN을 사용하고 Lync 미디어에서 VPN 터널을 우회하도록 설정에 지정된 모든 외부 비 VPN 사용자와 같은 미디어 트래픽을 [라우팅해야 합니다.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210)</span><span class="sxs-lookup"><span data-stu-id="17461-170">The VPN client should use split VPN and route media traffic like any external non-VPN user, as specified in [Enabling Lync media to bypass a VPN tunnel](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210).</span></span>

> [!NOTE]
> <span data-ttu-id="17461-171">타이틀은 Lync를 나타내지만 Teams에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-171">Although the title indicates Lync, it is applicable to Teams as well.</span></span>

<span data-ttu-id="17461-172">**패킷 셰이더.**</span><span class="sxs-lookup"><span data-stu-id="17461-172">**Packet shapers**.</span></span> <span data-ttu-id="17461-173">모든 종류의 패킷 캡처, 패킷 검사 또는 패킷 셰이더 디바이스는 권장되지 않고 품질이 크게 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-173">Any kind of packet snippers, packet inspection, or packet shaper devices are not recommended and may degrade quality significantly.</span></span>

### <a name="principles"></a><span data-ttu-id="17461-174">원칙</span><span class="sxs-lookup"><span data-stu-id="17461-174">Principles</span></span>

<span data-ttu-id="17461-175">Microsoft Teams의 통화 흐름을 이해하는 데 도움이 되는 네 가지 일반적인 원칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-175">There are four general principles that help you understand call flows for Microsoft Teams:</span></span>

- <span data-ttu-id="17461-176">Microsoft Teams 회의는 첫 번째 참가자가 참가한 동일한 지역에서 Microsoft 365 또는 Office 365에서 주최됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-176">A Microsoft Teams conference is hosted by Microsoft 365 or Office 365 in the same region where the first participant joined.</span></span> <span data-ttu-id="17461-177">(일부 토폴로지에서 이 규칙에 대한 예외가 있는 경우 이 문서에서 설명하고 적절한 호출 흐름에 의해 설명됩니다.)</span><span class="sxs-lookup"><span data-stu-id="17461-177">(Note that if there are exceptions to this rule in some topologies, they will be described in this document and illustrated by an appropriate call flow.)</span></span>

- <span data-ttu-id="17461-178">Microsoft 365 또는 Office 365의 Teams 미디어 엔드포인트는 통화 유형이 아닌 미디어 처리 요구에 따라 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-178">A Teams media endpoint in Microsoft 365 or Office 365 is used based on media processing needs and not based on call type.</span></span> <span data-ttu-id="17461-179">(예를 들어 지점 간 호출은 클라우드의 미디어 엔드포인트를 사용하여 전사 또는 기록을 위해 미디어를 처리하고 두 참가자와의 회의는 클라우드에서 미디어 엔드포인트를 사용하지 않을 수 있습니다.) 그러나 대부분의 회의는 믹싱 및 라우팅을 위해 미디어 엔드포인트를 사용하며, 회의가 호스트되는 위치로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-179">(For example, a point-to-point call may use a media endpoint in the cloud to process media for transcription or recording, while a conference with two participants may not use any media endpoint in the cloud.) However, most conferences will use a media endpoint for mixing and routing purposes, allocated where the conference is hosted.</span></span> <span data-ttu-id="17461-180">클라이언트에서 미디어 엔드포인트로 전송된 미디어 트래픽은 고객 네트워크 방화벽 제한으로 인해 필요한 경우 Microsoft 365 또는 Office 365에서 전송 릴레이를 직접 라우팅하거나 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-180">The media traffic sent from a client to the media endpoint may be routed directly or use a Transport Relay in Microsoft 365 or Office 365 if required due to customer network firewall restrictions.</span></span>

- <span data-ttu-id="17461-181">피어 투 피어 호출에 대한 미디어 트래픽은 호출이 클라우드의 미디어 엔드포인트를 지시하지 않는다고 전제로 하여 사용할 수 있는 가장 직접적인 경로를 취합니다(이전 원칙 참조).</span><span class="sxs-lookup"><span data-stu-id="17461-181">Media traffic for peer-to-peer calls take the most direct route that is available, assuming that the call doesn't mandate a media endpoint in the cloud (see previous principle).</span></span> <span data-ttu-id="17461-182">기본 경로는 원격 피어(클라이언트)로 직접 연결되지만 해당 경로를 사용할 수 없는 경우 하나 이상의 전송 릴레이가 트래픽을 릴레이합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-182">The preferred route is direct to the remote peer (client), but if that route isn't available, then one or more Transport Relays will relay traffic.</span></span> <span data-ttu-id="17461-183">미디어 품질에 영향을 미치기 때문에 미디어 트래픽은 패킷 셰이더, VPN 서버 등의 서버를 버스하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-183">It is recommended that media traffic shall not transverse servers such as packet shapers, VPN servers, and so on, since this will impact the media quality.</span></span>

- <span data-ttu-id="17461-184">신호 트래픽은 항상 사용자에게 가장 가까운 서버로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-184">Signaling traffic always goes to the closest server to the user.</span></span>

<span data-ttu-id="17461-185">선택한 미디어 경로에 대한 자세한 내용은 Microsoft Teams의 미디어 흐름 이해 [- BRK4016을 참조합니다.](https://www.youtube.com/watch?v=1tmHMIlAQdo)</span><span class="sxs-lookup"><span data-stu-id="17461-185">To learn more about the details on the media path that is chosen, see [Understanding Media Flows in Microsoft Teams - BRK4016](https://www.youtube.com/watch?v=1tmHMIlAQdo).</span></span>

## <a name="call-flows-in-various-topologies"></a><span data-ttu-id="17461-186">다양한 토폴로지의 호출 흐름</span><span class="sxs-lookup"><span data-stu-id="17461-186">Call flows in various topologies</span></span>

### <a name="teams-topology"></a><span data-ttu-id="17461-187">Teams 토폴로지</span><span class="sxs-lookup"><span data-stu-id="17461-187">Teams topology</span></span>

<span data-ttu-id="17461-188">이 토폴로지는 비즈니스용 Skype 서버 또는 전화 시스템 직접 라우팅과 같은 모든 프레미스 배포 없이 클라우드에서 Teams 서비스를 활용하는 고객이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-188">This topology is used by customers that leverage Teams services from the cloud without any on-premises deployment, such as Skype for Business Server or Phone System Direct Routing.</span></span> <span data-ttu-id="17461-189">또한 Microsoft 365 또는 Office 365에 대한 인터페이스는 Azure Express Route 없이 인터넷을 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-189">In addition, the interface to Microsoft 365 or Office 365 is done over the Internet without Azure Express Route.</span></span>

<span data-ttu-id="17461-190">[![Microsoft Teams Online 통화 흐름 그림 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span><span class="sxs-lookup"><span data-stu-id="17461-190">[![Microsoft Teams Online Call Flows Figure 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span></span>

<span data-ttu-id="17461-191">*그림 1 - Teams 토폴로지*</span><span class="sxs-lookup"><span data-stu-id="17461-191">*Figure 1 - Teams topology*</span></span>

<span data-ttu-id="17461-192">다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-192">Note that:</span></span>

- <span data-ttu-id="17461-193">위 다이어그램의 화살표 방향은 엔터프라이즈 경계의 연결에 영향을 주는 통신의 시작 방향을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-193">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="17461-194">미디어용 UDP의 경우 첫 번째 패킷이 역방향으로 흐를 수 있지만, 다른 방향의 패킷이 흐를 때까지 이러한 패킷이 차단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-194">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>
- <span data-ttu-id="17461-195">Teams는 비즈니스용 Skype Online과 나란히 배포되어 클라이언트가 "Teams/SFB 사용자"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-195">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="17461-196">이 문서의 나중에 다음 선택적 토폴로지에 대한 자세한 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-196">You can find more information on the following optional topologies later in the article:</span></span>

- <span data-ttu-id="17461-197">비즈니스용 Skype-프레미스 배포는 Teams 하이브리드 **토폴로지에서 설명합니다.**</span><span class="sxs-lookup"><span data-stu-id="17461-197">Skype for Business on-premises deployment is described in **Teams hybrid topology**.</span></span>
- <span data-ttu-id="17461-198">전화 시스템 직접 라우팅(PSTN 연결용)은 직접 라우팅 토폴로지가 있는 **Teams에서 설명됩니다.**</span><span class="sxs-lookup"><span data-stu-id="17461-198">Phone System Direct Routing (for PSTN connectivity) is described in **Teams with Direct Routing topology**.</span></span>
- <span data-ttu-id="17461-199">Express Route는 **Teams에서 Express Route 최적화를 통해 설명됩니다.**</span><span class="sxs-lookup"><span data-stu-id="17461-199">Express Route is described in **Teams with Express Route optimization**.</span></span>

<span data-ttu-id="17461-200">**흐름 설명:**</span><span class="sxs-lookup"><span data-stu-id="17461-200">**Flow descriptions**:</span></span>

- <span data-ttu-id="17461-201">**흐름 2** – 고객의 Teams 환경의 일부로 고객 네트워크의 사용자가 인터넷에 시작한 흐름을 나타 내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-201">**Flow 2** – Represents a flow initiated by a user on the customer network to the Internet as a part of the user's Teams experience.</span></span> <span data-ttu-id="17461-202">이러한 흐름의 예로는 DNS 및 피어 투 피어 미디어가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-202">Examples of these flows are DNS and peer-to-peer media.</span></span>
- <span data-ttu-id="17461-203">**흐름 2'** – 고객 네트워크에 대한 VPN을 사용하여 원격 모바일 Teams 사용자가 시작한 흐름을 나타내며,</span><span class="sxs-lookup"><span data-stu-id="17461-203">**Flow 2'** – Represents a flow initiated by a remote mobile Teams user, with VPN to the customer network.</span></span>
- <span data-ttu-id="17461-204">**흐름 3** – 원격 모바일 Teams 사용자가 Microsoft 365 또는 Office 365/Teams 엔드포인트로 시작한 흐름을 나타내며,</span><span class="sxs-lookup"><span data-stu-id="17461-204">**Flow 3** – Represents a flow initiated by a remote mobile Teams user to Microsoft 365 or Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="17461-205">**흐름 4** – 고객 네트워크의 사용자가 Microsoft 365 또는 Office 365/Teams 엔드포인트에 대해 시작한 흐름을 나타내며,</span><span class="sxs-lookup"><span data-stu-id="17461-205">**Flow 4** – Represents a flow initiated by a user on the customer network to Microsoft 365 or Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="17461-206">**흐름 5** – Teams 사용자와 다른 Teams 또는 고객 네트워크 내의 비즈니스용 Skype 사용자 간에 피어 투 피어 미디어 흐름을 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-206">**Flow 5** – Represents a peer-to-peer media flow between a Teams user and another Teams or Skype for Business user within the customer network.</span></span>
- <span data-ttu-id="17461-207">**Flow 6** – 원격 모바일 Teams 사용자와 다른 원격 모바일 Teams 또는 인터넷을 통해 비즈니스용 Skype 사용자 간에 피어 투 피어 미디어 흐름을 나타 내는 경우</span><span class="sxs-lookup"><span data-stu-id="17461-207">**Flow 6** – Represents a peer-to-peer media flow between a remote mobile Teams user and another remote mobile Teams or Skype for Business user over the Internet.</span></span>

#### <a name="use-case-one-to-one"></a><span data-ttu-id="17461-208">사용 사례: 일대일</span><span class="sxs-lookup"><span data-stu-id="17461-208">Use case: One-to-one</span></span>

<span data-ttu-id="17461-209">일대일 호출은 호출자가 로컬, 릴레이 및 reflexive(릴레이에서 볼 수 있는 클라이언트의 공용 IP 주소)를 포함하여 IP 주소/포트로 구성된 후보 집합을 얻는 공통 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-209">One-to-one calls use a common model in which the caller will obtain a set of candidates consisting of IP addresses/ports, including local, relay, and reflexive (public IP address of client as seen by the relay) candidates.</span></span> <span data-ttu-id="17461-210">호출자는 이러한 후보를 호출된 파티에 전송합니다. 또한 호출된 파티는 비슷한 후보 집합을 획득하여 발신자에게 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-210">The caller sends these candidates to the called party; the called party also obtains a similar set of candidates and sends them to the caller.</span></span> <span data-ttu-id="17461-211">STUN 연결 확인 메시지는 어떤 호출자/호출자 미디어 경로가 작동하고, 최상의 작업 경로가 선택된 것을 찾는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-211">STUN connectivity check messages are used to find which caller/called party media paths work, and the best working path is selected.</span></span> <span data-ttu-id="17461-212">미디어(즉, SRTP를 사용하여 보호되는 RTP/RTCP 패킷)는 선택한 후보 쌍을 사용하여 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-212">Media (that is, RTP/RTCP packets secured using SRTP) are then sent using the selected candidate pair.</span></span> <span data-ttu-id="17461-213">전송 릴레이는 Microsoft 365 및 Office 365의 일부로 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-213">The Transport relay is deployed as part of Microsoft 365 and Office 365.</span></span>

<span data-ttu-id="17461-214">로컬 IP 주소/포트 후보 또는 반사 후보가 연결되면 클라이언트 간의 직접 경로(또는 NAT 사용)가 미디어에 대해 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-214">If the local IP address/port candidates or the reflexive candidates have connectivity, then the direct path between the clients (or using a NAT) will be selected for media.</span></span> <span data-ttu-id="17461-215">클라이언트가 모두 고객 네트워크에 있는 경우 직접 경로를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-215">If the clients are both on the customer network, then the direct path should be selected.</span></span> <span data-ttu-id="17461-216">이렇게 하려면 고객 네트워크 내에서 직접 UDP 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-216">This requires direct UDP connectivity within the customer network.</span></span> <span data-ttu-id="17461-217">클라이언트가 모두 유성 클라우드 사용자인 경우 NAT/방화벽에 따라 미디어가 직접 연결을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-217">If the clients are both nomadic cloud users, then depending on the NAT/firewall, media may use direct connectivity.</span></span>

<span data-ttu-id="17461-218">한 클라이언트가 고객 네트워크에 내부에 있으며 한 클라이언트가 외부 클라이언트(예: 모바일 클라우드 사용자)인 경우 로컬 또는 반사 후보 간의 직접 연결이 작동하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-218">If one client is internal on the customer network and one client is external (for example, a mobile cloud user), then it is unlikely that direct connectivity between the local or reflexive candidates is working.</span></span> <span data-ttu-id="17461-219">이 경우 옵션은 두 클라이언트에서 전송 릴레이 후보 중 하나를 사용하는 것입니다(예: 내부 클라이언트가 Microsoft 365 또는 Office 365의 전송 릴레이에서 릴레이 후보를 획득했습니다. 외부 클라이언트는 STUN/RTP/RTCP 패킷을 전송 릴레이로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-219">In this case, an option is to use one of the Transport Relay candidates from either client (for example, the internal client obtained a relay candidate from the Transport relay in Microsoft 365 or Office 365; the external client needs to be able to send STUN/RTP/RTCP packets to the transport relay).</span></span> <span data-ttu-id="17461-220">또 다른 옵션은 내부 클라이언트가 모바일 클라우드 클라이언트에서 획득한 릴레이 후보로 보내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-220">Another option is the internal client sends to the relay candidate obtained by the mobile cloud client.</span></span> <span data-ttu-id="17461-221">미디어에 대한 UDP 연결이 권장되는 경우 TCP가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-221">Note that, although UDP connectivity for media is highly recommended, TCP is supported.</span></span>

<span data-ttu-id="17461-222">**고급 단계:**</span><span class="sxs-lookup"><span data-stu-id="17461-222">**High-level steps**:</span></span>

1. <span data-ttu-id="17461-223">Teams 사용자 A는 흐름 2를 사용하여 DNS(URL 도메인 이름)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-223">Teams User A resolves URL domain name (DNS) using flow 2.</span></span>
1. <span data-ttu-id="17461-224">Teams 사용자 A는 흐름 4를 사용하여 Teams 전송 릴레이에 미디어 릴레이 포트를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-224">Teams User A allocates a media Relay port on Teams Transport Relay using flow 4.</span></span>
1. <span data-ttu-id="17461-225">Teams 사용자 A는 흐름 4를 사용하여 ICE 후보와 함께 "초대"를 Microsoft 365 또는 Office 365로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-225">Teams User A sends "invite" with ICE candidates using flow 4 to Microsoft 365 or Office 365.</span></span>
1. <span data-ttu-id="17461-226">Microsoft 365 또는 Office 365는 흐름 4를 사용하여 Teams 사용자 B에게 알림을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-226">Microsoft 365 or Office 365 sends notification to Teams User B using flow 4.</span></span>
1. <span data-ttu-id="17461-227">Teams 사용자 B는 흐름 4를 사용하여 Teams 전송 릴레이에 미디어 릴레이 포트를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-227">Teams User B allocates a media Relay port on Teams Transport Relay using flow 4.</span></span>
1. <span data-ttu-id="17461-228">Teams 사용자 B는 흐름 4를 사용하여 ICE 후보와 "답변"을 전송합니다. 흐름 4를 사용하여 Teams 사용자 A에게 다시 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-228">Teams User B sends "answer" with ICE candidates using flow 4, which is forwarded back to Teams User A using Flow 4.</span></span>
1. <span data-ttu-id="17461-229">Teams 사용자 A와 Teams 사용자 B가 ICE 연결 테스트를 호출하고 사용 가능한 최상의 미디어 경로가 선택됩니다(다양한 사용 사례는 아래 다이어그램 참조).</span><span class="sxs-lookup"><span data-stu-id="17461-229">Teams User A and Teams User B invoke ICE connectivity tests and the best available media path is selected (see diagrams below for various use cases).</span></span>
1. <span data-ttu-id="17461-230">Teams 사용자는 흐름 4를 사용하여 Microsoft 365 또는 Office 365에 원격 분석 데이터를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-230">Teams Users send telemetry to Microsoft 365 or Office 365 using flow 4.</span></span>

<span data-ttu-id="17461-231">**고객 네트워크 내에서:**</span><span class="sxs-lookup"><span data-stu-id="17461-231">**Within customer network:**</span></span>

<span data-ttu-id="17461-232">[![Microsoft Teams Online 통화 흐름 그림 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span><span class="sxs-lookup"><span data-stu-id="17461-232">[![Microsoft Teams Online Call Flows Figure 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span></span>

<span data-ttu-id="17461-233">*그림 2 - 고객 네트워크 내*</span><span class="sxs-lookup"><span data-stu-id="17461-233">*Figure 2 - Within customer network*</span></span>

<span data-ttu-id="17461-234">7단계에서 피어 투 피어 미디어 흐름 5가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-234">In step 7, peer-to-peer media flow 5 is selected.</span></span>

<span data-ttu-id="17461-235">미디어는 양방향입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-235">Media is bidirectional.</span></span> <span data-ttu-id="17461-236">흐름 5의 방향은 한 쪽이 연결 관점에서 통신을 시작하고 이 문서의 모든 흐름과 일치하다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-236">The direction of flow 5 indicates that one side initiates the communication from a connectivity perspective, consistent with all the flows in this document.</span></span> <span data-ttu-id="17461-237">이 경우 두 엔드포인트가 모두 고객 네트워크 내에 있기 때문에 어떤 방향이 사용되는지 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-237">In this case, it doesn't matter which direction is used because both endpoints are within the customer network.</span></span>

<span data-ttu-id="17461-238">**고객 네트워크-외부 사용자(Teams 전송 릴레이에서 릴레이된 미디어):**</span><span class="sxs-lookup"><span data-stu-id="17461-238">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="17461-239">[![Microsoft Teams Online 통화 흐름 그림 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span><span class="sxs-lookup"><span data-stu-id="17461-239">[![Microsoft Teams Online Call Flows Figure 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span></span>

<span data-ttu-id="17461-240">*그림 3 - 외부 사용자에 대한 고객 네트워크(Teams 전송 릴레이에서 릴레이된 미디어)*</span><span class="sxs-lookup"><span data-stu-id="17461-240">*Figure 3 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="17461-241">7단계에서는 고객 네트워크에서 Microsoft 365 또는 Office 365로의 흐름 4, 그리고 원격 모바일 Teams 사용자에서 Microsoft 365 또는 Office 365로의 흐름 3이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-241">In step 7, flow 4, from customer network to Microsoft 365 or Office 365, and flow 3, from remote mobile Teams user to Microsoft 365 or Office 365, are selected.</span></span> <span data-ttu-id="17461-242">이러한 흐름은 Microsoft 365 또는 Office 365 내에서 Teams 전송 릴레이에 의해 릴레이됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-242">These flows are relayed by Teams Transport Relay within Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="17461-243">미디어는 양방향입니다. 여기서 방향은 연결 관점에서 통신을 시작하는 쪽을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="17461-243">Media is bidirectional, where direction indicates which side initiates the communication from a connectivity perspective.</span></span> <span data-ttu-id="17461-244">이 경우 이러한 흐름은 서로 다른 전송 프로토콜 및 주소를 사용하여 신호 및 미디어에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-244">In this case, these flows are used for signaling and media, using different transport protocols and addresses.</span></span>

<span data-ttu-id="17461-245">**외부 사용자(직접 미디어)에 대한 고객 네트워크:**</span><span class="sxs-lookup"><span data-stu-id="17461-245">**Customer network to external user (direct media):**</span></span>

<span data-ttu-id="17461-246">[![Microsoft Teams Online 통화 흐름 그림 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span><span class="sxs-lookup"><span data-stu-id="17461-246">[![Microsoft Teams Online Call Flows Figure 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span></span>

<span data-ttu-id="17461-247">*그림 4 - 외부 사용자에 대한 고객 네트워크(직접 미디어)*</span><span class="sxs-lookup"><span data-stu-id="17461-247">*Figure 4 - Customer network to external user (direct media)*</span></span>

<span data-ttu-id="17461-248">7단계에서 고객 네트워크에서 인터넷(클라이언트의 피어)으로의 흐름 2가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-248">In step 7, flow 2, from customer network to the Internet (client's peer), is selected.</span></span>

- <span data-ttu-id="17461-249">원격 모바일 사용자가 있는 직접 미디어(Microsoft 365 또는 Office 365를 통해 릴레이되지 않은)는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-249">Direct media with remote mobile user (not relayed through Microsoft 365 or Office 365) is optional.</span></span> <span data-ttu-id="17461-250">즉, 고객이 Microsoft 365 또는 Office 365에서 전송 릴레이를 통해 미디어 경로를 적용하기 위해 이 경로를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-250">In other words, customer may block this path to enforce a media path through Transport Relay in Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="17461-251">미디어는 양방향입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-251">Media is bidirectional.</span></span> <span data-ttu-id="17461-252">흐름 2에서 원격 모바일 사용자로의 방향은 한 쪽이 연결 관점에서 통신을 시작하고 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-252">The direction of flow 2 to remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="17461-253">**내부 사용자(Teams 전송 릴레이에서 릴레이된 미디어)에 대한 VPN 사용자**</span><span class="sxs-lookup"><span data-stu-id="17461-253">**VPN user to internal user (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="17461-254">[![Microsoft Teams Online 통화 흐름 그림 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span><span class="sxs-lookup"><span data-stu-id="17461-254">[![Microsoft Teams Online Call Flows Figure 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span></span>

<span data-ttu-id="17461-255">*그림 5 - 내부 사용자에 대한 VPN 사용자(Teams 전송 릴레이에서 릴레이된 미디어)*</span><span class="sxs-lookup"><span data-stu-id="17461-255">*Figure 5 - VPN user to internal user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="17461-256">고객 네트워크에 대한 VPN 간 신호는 흐름 2를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-256">Signaling between the VPN to the customer network is using flow 2'.</span></span> <span data-ttu-id="17461-257">고객 네트워크와 Microsoft 365 또는 Office 365 간의 신호는 흐름 4를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-257">Signaling between the customer network and Microsoft 365 or Office 365 is using flow 4.</span></span> <span data-ttu-id="17461-258">그러나 미디어는 VPN을 무시하고 Microsoft 365 또는 Office 365의 Teams 미디어 릴레이를 통해 흐름 3 및 4를 사용하여 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-258">However, media bypasses the VPN and is routed using flows 3 and 4 through Teams media relay in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="17461-259">**내부 사용자(직접 미디어)에 대한 VPN 사용자**</span><span class="sxs-lookup"><span data-stu-id="17461-259">**VPN user to internal user (direct media)**</span></span>

<span data-ttu-id="17461-260">[![Microsoft Teams Online 통화 흐름 그림 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span><span class="sxs-lookup"><span data-stu-id="17461-260">[![Microsoft Teams Online Call Flows Figure 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span></span>

<span data-ttu-id="17461-261">*그림 6 - 내부 사용자(직접 미디어)에 대한 VPN 사용자*</span><span class="sxs-lookup"><span data-stu-id="17461-261">*Figure 6 - VPN user to internal user (direct media)*</span></span>

<span data-ttu-id="17461-262">고객 네트워크에 대한 VPN 간 신호는 흐름 2를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-262">Signaling between the VPN to the customer network is using flow 2'.</span></span> <span data-ttu-id="17461-263">고객 네트워크와 Microsoft 365 또는 Office 365 간의 신호는 흐름 4를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-263">Signaling between the customer network and Microsoft 365 or Office 365 is using flow 4.</span></span> <span data-ttu-id="17461-264">그러나 미디어는 VPN을 무시하고 고객 네트워크에서 인터넷으로 흐름 2를 사용하여 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-264">However, media bypasses the VPN and is routed using flow 2 from the customer network to the Internet.</span></span>

<span data-ttu-id="17461-265">미디어는 양방향입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-265">Media is bidirectional.</span></span> <span data-ttu-id="17461-266">원격 모바일 사용자에 대한 흐름 2의 방향은 한 쪽이 연결 관점에서 통신을 시작하도록 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="17461-266">The direction of flow 2 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="17461-267">**외부 사용자(직접 미디어)에 대한 VPN 사용자**</span><span class="sxs-lookup"><span data-stu-id="17461-267">**VPN user to external user (direct media)**</span></span>

<span data-ttu-id="17461-268">[![Microsoft Teams 통화 흐름 그림 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span><span class="sxs-lookup"><span data-stu-id="17461-268">[![Microsoft Teams call flows Figure 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span></span>

<span data-ttu-id="17461-269">*그림 7 - 외부 사용자(직접 미디어)에 대한 VPN 사용자*</span><span class="sxs-lookup"><span data-stu-id="17461-269">*Figure 7 - VPN user to external user (direct media)*</span></span>

<span data-ttu-id="17461-270">VPN 사용자와 고객 네트워크에 대한 신호는 흐름 2를 사용하고 흐름 4를 사용하여 Microsoft 365 또는 Office 365로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-270">Signaling between the VPN user to the customer network is using flow 2' and using flow 4 to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="17461-271">그러나 미디어는 VPN을 무시하고 흐름 6을 사용하여 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-271">However, media bypasses VPN and is routed using flow 6.</span></span>

<span data-ttu-id="17461-272">미디어는 양방향입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-272">Media is bidirectional.</span></span> <span data-ttu-id="17461-273">원격 모바일 사용자에 대한 흐름 6의 방향은 한 쪽이 연결 관점에서 통신을 시작하도록 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="17461-273">The direction of flow 6 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

#### <a name="use-case-teams-to-pstn-through-microsoft-365-or-office-365-trunk"></a><span data-ttu-id="17461-274">사용 사례: Microsoft 365 또는 Office 365 트렁크를 통해 Teams에서 PSTN으로</span><span class="sxs-lookup"><span data-stu-id="17461-274">Use Case: Teams to PSTN through Microsoft 365 or Office 365 Trunk</span></span>

<span data-ttu-id="17461-275">Microsoft 365 및 Office 365에는 PSTN(공용 전환 전화 네트워크)에서 전화를 걸고 받을 수 있는 전화 시스템이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-275">Microsoft 365 and Office 365 have a Phone System that allows placing and receiving calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="17461-276">PSTN 트렁크가 전화 시스템 통화 계획을 사용하여 연결된 경우 이 사용 사례에 대한 특별한 연결 요구 사항이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-276">If the PSTN trunk is connected using the Phone System Calling Plan, then there are no special connectivity requirements for this use case.</span></span> <span data-ttu-id="17461-277">(Microsoft 365 또는 Office 365에 자체의 PSTN 트렁크를 연결하려는 경우 전화 시스템 직접 라우팅을 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="17461-277">(If you want to connect your own on-premises PSTN trunk to Microsoft 365 or Office 365, you can use Phone System Direct Routing.)</span></span>

<span data-ttu-id="17461-278">[![Microsoft Teams Online 통화 흐름 그림 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span><span class="sxs-lookup"><span data-stu-id="17461-278">[![Microsoft Teams Online Call Flows Figure 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span></span>

<span data-ttu-id="17461-279">*그림 8 - Office 365 트렁크를 통해 Teams에서 PSTN으로*</span><span class="sxs-lookup"><span data-stu-id="17461-279">*Figure 8 - Teams to PSTN through Office 365 Trunk*</span></span>

#### <a name="use-case-teams-meeting"></a><span data-ttu-id="17461-280">사용 사례: Teams 모임</span><span class="sxs-lookup"><span data-stu-id="17461-280">Use case: Teams meeting</span></span>

<span data-ttu-id="17461-281">오디오/비디오/화면 공유(VBSS) 회의 서버는 Microsoft 365 및 Office 365의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-281">The audio/video/screen sharing (VBSS) conferencing server is part of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="17461-282">고객 네트워크에서 연결 가능해야 하는 공용 IP 주소가 있으며 Nomadic Cloud 클라이언트에서 연결 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-282">It has a public IP address that must be reachable from the customer network and must be reachable from a Nomadic Cloud client.</span></span> <span data-ttu-id="17461-283">각 클라이언트/엔드포인트는 회의 서버에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-283">Each client/endpoint needs to be able to connect to the conferencing server.</span></span>

<span data-ttu-id="17461-284">내부 클라이언트는 일대일 호출에 대해 설명한 방식으로 로컬, 반사 및 릴레이 후보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-284">Internal clients will obtain local, reflexive, and relay candidates in the same manner as described for one-to-one calls.</span></span> <span data-ttu-id="17461-285">클라이언트는 초대의 회의 서버에 이러한 후보를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-285">The clients will send these candidates to the conferencing server in an invite.</span></span> <span data-ttu-id="17461-286">회의 서버는 공개적으로 연결 가능한 IP 주소가 있으므로 릴레이를 사용하지 않습니다. 따라서 로컬 IP 주소 후보로 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-286">The conferencing server does not use a relay since it has a publicly reachable IP address, so it responds with its local IP address candidate.</span></span> <span data-ttu-id="17461-287">클라이언트 및 회의 서버는 일대일 호출에 대해 설명한 동일한 방식으로 연결을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-287">The client and conferencing server will check connectivity in the same manner described for one-to-one calls.</span></span>

<span data-ttu-id="17461-288">다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-288">Note that:</span></span>

- <span data-ttu-id="17461-289">Teams 클라이언트는 비즈니스용 Skype 모임에 참가할 수 없습니다. 비즈니스용 Skype 클라이언트는 Teams 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-289">Teams clients cannot join Skype for Business meetings, and Skype for Business clients cannot join Teams meetings.</span></span>

- <span data-ttu-id="17461-290">모임의 이끌이 PSTN 통화 및/또는 회의 프로비전에 따라 PSTN 사용자가 선택적으로 "전화 접속"되거나 "전화 걸기"됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-290">A PSTN user optionally "Dials IN" or is "Dialed OUT", depending on the meeting's organizer PSTN Calling and/or conferencing provisioning.</span></span>

- <span data-ttu-id="17461-291">게스트 사용자 또는 고객 사용자는 엄격한 규칙으로 FW/NAT를 사용하여 보호되는 게스트 개인 네트워크에서 조인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-291">A guest user or a customer user may join from a guest private network, which is protected using FW/NAT with strict rules.</span></span>

<span data-ttu-id="17461-292">[![Microsoft Teams Online 통화 흐름 그림 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span><span class="sxs-lookup"><span data-stu-id="17461-292">[![Microsoft Teams Online Call Flows Figure 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span></span>

<span data-ttu-id="17461-293">*그림 9 - Teams 모임*</span><span class="sxs-lookup"><span data-stu-id="17461-293">*Figure 9 - Teams Meeting*</span></span>

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a><span data-ttu-id="17461-294">사용 사례: 비즈니스용 Skype를 사용하여 프레미스로 페더맹</span><span class="sxs-lookup"><span data-stu-id="17461-294">Use case: Federation with Skype for Business on premises</span></span>

<span data-ttu-id="17461-295">**Microsoft 365 또는 Office 365에서 Teams 전송 릴레이로 릴레이된 미디어**</span><span class="sxs-lookup"><span data-stu-id="17461-295">**Media relayed by Teams Transport Relay in Microsoft 365 or Office 365**</span></span>

<span data-ttu-id="17461-296">[![Microsoft Teams Online 통화 흐름 그림 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span><span class="sxs-lookup"><span data-stu-id="17461-296">[![Microsoft Teams Online Call Flows Figure 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span></span>

<span data-ttu-id="17461-297">*그림 10 - Office 365에서 Teams 전송 릴레이로 릴레이된 미디어*</span><span class="sxs-lookup"><span data-stu-id="17461-297">*Figure 10 - Media relayed by Teams Transport Relay in Office 365*</span></span>

<span data-ttu-id="17461-298">다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-298">Note that:</span></span>

- <span data-ttu-id="17461-299">페더넌트는 기본적으로 두 테넌트 간의 통신입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-299">Federation is, by definition, a communication between two tenants.</span></span> <span data-ttu-id="17461-300">이 경우 Teams를 사용하는 테넌트 A는 비즈니스용 Skype를 사용하는 테넌트 B와 페더넌트됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-300">In this case, tenant A, which uses Teams, federates with tenant B, which uses Skype for Business on premises.</span></span> <span data-ttu-id="17461-301">테넌트 B가 Microsoft 365 또는 Office 365를 사용하는 경우 비즈니스용 Skype 클라이언트는 흐름 3을 사용하여 Microsoft 365 또는 Office 365에 연결했습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-301">If tenant B is also using Microsoft 365 or Office 365, then the Skype for Business client would have used flow 3 to connect with Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="17461-302">페더링된 비즈니스용 Skype 클라이언트에서 프레미스 비즈니스용 Skype Server로의 신호 및 미디어는 이 문서의 범위를 벗어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-302">Signaling and media from the federated Skype for Business client to on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="17461-303">그러나 명확성을 위해 여기에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-303">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="17461-304">Teams와 비즈니스용 Skype 간의 신호는 게이트웨이에 의해 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-304">Signaling between Teams and Skype for Business is bridged by a gateway.</span></span>

- <span data-ttu-id="17461-305">이 경우 미디어는 Teams 전송 릴레이를 통해 고객 네트워크 및 흐름 4를 사용하는 원격 비즈니스용 Skype 클라이언트에 릴레이됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-305">Media in this case is relayed by Teams Transport Relay to the customer network and remote Skype for Business client using flow 4.</span></span>

<span data-ttu-id="17461-306">**페더레이된 테넌트에서 비즈니스용 Skype 미디어 릴레이로 릴레이된 미디어**</span><span class="sxs-lookup"><span data-stu-id="17461-306">**Media relayed by Skype for Business Media Relay in federated tenant**</span></span>

<span data-ttu-id="17461-307">[![Microsoft Teams Online 통화 흐름 그림 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span><span class="sxs-lookup"><span data-stu-id="17461-307">[![Microsoft Teams Online Call Flows Figure 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span></span>

<span data-ttu-id="17461-308">*그림 11 - 페더레이된 테넌트에서 비즈니스용 Skype 미디어 릴레이로 릴레이된 미디어*</span><span class="sxs-lookup"><span data-stu-id="17461-308">*Figure 11 - Media relayed by Skype for Business Media Relay in federated tenant*</span></span>

<span data-ttu-id="17461-309">다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-309">Note that:</span></span>

- <span data-ttu-id="17461-310">페더링된 비즈니스용 Skype 클라이언트에서 비즈니스용 Skype 서버로의 신호 및 미디어는 이 문서의 범위를 벗어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-310">Signaling and media from the federated Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="17461-311">그러나 명확성을 위해 여기에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-311">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="17461-312">Teams와 비즈니스용 Skype 간의 신호는 게이트웨이에 의해 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-312">Signaling between Teams and Skype for Business is bridged by a Gateway.</span></span>

- <span data-ttu-id="17461-313">이 경우 미디어는 흐름 2를 사용하여 비즈니스용 Skype의 프레미스 미디어 릴레이를 통해 고객 네트워크에 릴레이됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-313">Media in this case is relayed by Skype for Business on-premises Media Relay to the customer network using flow 2.</span></span> <span data-ttu-id="17461-314">(페더레이된 고객 네트워크의 원격 미디어 릴레이로의 트래픽은 역방향의 트래픽이 흐르기 시작할 때까지 미디어 릴레이에 의해 처음에 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-314">(Note that traffic from Teams user to the remote Media Relay in the federated customer network will be initially blocked by the Media Relay until traffic in the reverse direction starts to flow.</span></span> <span data-ttu-id="17461-315">그러나 양방향 흐름은 양방향으로 연결이 열립니다.)</span><span class="sxs-lookup"><span data-stu-id="17461-315">However, the bidirectional flow will open connectivity in both directions.)</span></span>

<span data-ttu-id="17461-316">**직접(피어 투 피어)**</span><span class="sxs-lookup"><span data-stu-id="17461-316">**Direct (peer-to-peer)**</span></span>

<span data-ttu-id="17461-317">[![Microsoft Teams Online 통화 흐름 그림 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span><span class="sxs-lookup"><span data-stu-id="17461-317">[![Microsoft Teams Online Call Flows Figure 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span></span>

<span data-ttu-id="17461-318">*그림 12 - 직접(피어 투 피어)*</span><span class="sxs-lookup"><span data-stu-id="17461-318">*Figure 12 - Direct (peer-to-peer)*</span></span>

### <a name="teams-hybrid-topology"></a><span data-ttu-id="17461-319">Teams 하이브리드 토폴로지</span><span class="sxs-lookup"><span data-stu-id="17461-319">Teams hybrid topology</span></span>

<span data-ttu-id="17461-320">이 토폴로지에는 비즈니스용 Skype의 온라인 프레미스 배포가 있는 Teams가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-320">This topology includes Teams with a Skype for Business on-premises deployment.</span></span>

<span data-ttu-id="17461-321">[![Microsoft Teams Online 통화 흐름 그림 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span><span class="sxs-lookup"><span data-stu-id="17461-321">[![Microsoft Teams Online Call Flows Figure 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span></span>

<span data-ttu-id="17461-322">*그림 13 - Teams 하이브리드 토폴로지*</span><span class="sxs-lookup"><span data-stu-id="17461-322">*Figure 13 - Teams hybrid topology*</span></span>

- <span data-ttu-id="17461-323">위 다이어그램의 화살표 방향은 엔터프라이즈 경계의 연결에 영향을 주는 통신의 시작 방향을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-323">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="17461-324">미디어용 UDP의 경우 첫 번째 패킷이 역방향으로 흐를 수 있지만, 다른 방향의 패킷이 흐를 때까지 이러한 패킷이 차단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-324">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="17461-325">Teams는 비즈니스용 Skype Online과 나란히 배포되어 클라이언트가 "Teams/SFB 사용자"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-325">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="17461-326">추가 흐름(Teams 토폴로지 위에):</span><span class="sxs-lookup"><span data-stu-id="17461-326">Additional flow (on top of Teams topology):</span></span>

- <span data-ttu-id="17461-327">**Flow 5A** – 고객 네트워크 내의 Teams 사용자와 고객 네트워크 에지의 비즈니스용 Skype On-프레미스 미디어 릴레이 간의 피어 투 피어 미디어 흐름을 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-327">**Flow 5A** – Represents a peer-to-peer media flow between a Teams user within the customer network and a Skype for Business on-premises media relay at the customer network edge.</span></span>

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a><span data-ttu-id="17461-328">사용 사례: Teams에서 비즈니스용 Skype로 일대일</span><span class="sxs-lookup"><span data-stu-id="17461-328">Use case: Teams to Skype for Business one-to-one</span></span>

<span data-ttu-id="17461-329">**고객 네트워크 내의 하이브리드**</span><span class="sxs-lookup"><span data-stu-id="17461-329">**Hybrid within the customer network**</span></span>

<span data-ttu-id="17461-330">[![Microsoft Teams Online 통화 흐름 그림 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span><span class="sxs-lookup"><span data-stu-id="17461-330">[![Microsoft Teams Online Call Flows Figure 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span></span>

<span data-ttu-id="17461-331">*그림 14 - 고객 네트워크 내 하이브리드*</span><span class="sxs-lookup"><span data-stu-id="17461-331">*Figure 14 - Hybrid within customer network*</span></span>

<span data-ttu-id="17461-332">Teams와 비즈니스용 Skype 간의 신호는 게이트웨이에 의해 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-332">Signaling between Teams and Skype for Business is bridged by a gateway.</span></span> <span data-ttu-id="17461-333">그러나 미디어는 흐름 5를 사용하여 고객 네트워크 내에서 직접 피어 투 피어로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-333">However, media is routed directly peer-to-peer within the customer network using flow 5.</span></span>

<span data-ttu-id="17461-334">**외부 비즈니스용 Skype 사용자가 있는 하이브리드 고객 네트워크 - Microsoft 365 또는 Office 365에서 릴레이**</span><span class="sxs-lookup"><span data-stu-id="17461-334">**Hybrid customer network with external Skype for Business user – relayed by Microsoft 365 or Office 365**</span></span>

<span data-ttu-id="17461-335">[![Microsoft Teams Online 통화 흐름 그림 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span><span class="sxs-lookup"><span data-stu-id="17461-335">[![Microsoft Teams Online Call Flows Figure 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span></span>

<span data-ttu-id="17461-336">*그림 15 - 외부 비즈니스용 Skype 사용자가 있는 하이브리드 고객 네트워크 - Office 365에서 릴레이*</span><span class="sxs-lookup"><span data-stu-id="17461-336">*Figure 15 - Hybrid customer network with external Skype for Business user - relayed by Office 365*</span></span>

<span data-ttu-id="17461-337">다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-337">Note that:</span></span>

- <span data-ttu-id="17461-338">비즈니스용 Skype 클라이언트에서 비즈니스용 Skype 서버로의 신호 및 미디어는 이 문서의 범위를 벗어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-338">Signaling and media from the Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="17461-339">그러나 명확성을 위해 여기에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-339">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="17461-340">Teams와 비즈니스용 Skype 간의 신호는 게이트웨이에 의해 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-340">Signaling between Teams and Skype for Business is bridged by a gateway.</span></span>

- <span data-ttu-id="17461-341">미디어는 Teams 전송 릴레이를 통해 흐름 4를 통해 고객 네트워크에 릴레이됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-341">Media is relayed through Teams Transport Relay to the customer network through flow 4.</span></span>

<span data-ttu-id="17461-342">**외부 비즈니스용 Skype 사용자가 있는 하이브리드 고객 네트워크 - 릴레이된 On-Premises Edge**</span><span class="sxs-lookup"><span data-stu-id="17461-342">**Hybrid customer network with external Skype for Business user – relayed by on-premises Edge**</span></span>

<span data-ttu-id="17461-343">[![Microsoft Teams Online 통화 흐름 그림 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span><span class="sxs-lookup"><span data-stu-id="17461-343">[![Microsoft Teams Online Call Flows Figure 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span></span>

<span data-ttu-id="17461-344">*그림 16 - 외부 비즈니스용 Skype 사용자가 있는 하이브리드 고객 네트워크 - 릴레이*</span><span class="sxs-lookup"><span data-stu-id="17461-344">*Figure 16 - Hybrid customer network with external Skype for Business user - relayed by on-premises Edge*</span></span>

<span data-ttu-id="17461-345">다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-345">Note that:</span></span>

- <span data-ttu-id="17461-346">비즈니스용 Skype 클라이언트에서 비즈니스용 Skype 서버로의 신호 및 미디어는 이 문서의 범위를 벗어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-346">Signaling and media from Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="17461-347">그러나 명확성을 위해 여기에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-347">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="17461-348">신호는 게이트웨이에 의해 브리지됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-348">Signaling is bridged by a gateway.</span></span>

- <span data-ttu-id="17461-349">미디어는 비즈니스용 Skype의 비즈니스용 Skype 미디어 릴레이에서 5A 미디어 흐름을 사용하여 고객 네트워크 내의 Teams 사용자에게 릴레이됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-349">Media is relayed by Skype for Business Media Relay within Skype for Business on-premises Edge to Teams user within the customer network using media flow 5A.</span></span>

### <a name="teams-with-phone-system-direct-routing-topology"></a><span data-ttu-id="17461-350">전화 시스템 직접 라우팅 토폴로지가 있는 Teams</span><span class="sxs-lookup"><span data-stu-id="17461-350">Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="17461-351">이 토폴로지에는 전화 시스템 직접 라우팅이 있는 Teams가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-351">This topology includes Teams with Phone System Direct Routing.</span></span>

<span data-ttu-id="17461-352">직접 라우팅을 사용하면 지원되는 SBC(고객 소유 세션 테두리 컨트롤러) 하드웨어 디바이스를 Microsoft 365 또는 Office 365에 페어링한 다음 해당 장치에 전화 통신 트렁크를 연결하여 타사 PSTN(공용 전환 전화 네트워크) 서비스 공급자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-352">Direct Routing enables you to use a third-party Public Switched Telephone Network (PSTN) service provider by pairing a supported on-premises customer-owned Session Border Controller (SBC) hardware device to Microsoft 365 or Office 365, and then connecting the telephony trunk to that device.</span></span>

<span data-ttu-id="17461-353">이 시나리오를 지원하려면 고객은 Microsoft의 인증된 파트너 중 하나에서 직접 라우팅을 위한 인증된 SBC를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-353">To support this scenario, the customer must deploy a certified SBC for Direct Routing from one of Microsoft's certified partners.</span></span> <span data-ttu-id="17461-354">SBC는 공급업체에서 권장하는 것으로 구성되어야하며 직접 UDP 트래픽에 대해 Microsoft 365 또는 Office 365에서 라우팅할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-354">The SBC must be configured as recommended by the vendor, and be routable from Microsoft 365 or Office 365 for direct UDP traffic.</span></span> <span data-ttu-id="17461-355">미디어는 Teams 및/또는 비즈니스용 Skype 클라이언트에서 SBC(Teams 게이트웨이 우회)로 직접 전달되거나 Teams 게이트웨이를 통과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-355">The media may flow directly from Teams and/or the Skype for Business client to the SBC (bypassing the Teams gateway) or traverse through the Teams gateway.</span></span> <span data-ttu-id="17461-356">트렁크가 Teams 게이트웨이를 우회하도록 구성된 경우 SBC와의 연결은 ICE를 기반으로 하여 SBC에서 ICE-Lite를 지원하는 반면, Teams/비즈니스용 Skype 미디어 엔드포인트는 ICE 전체 양식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-356">The connectivity with the SBC, when the trunk is configured to bypass the Teams gateway, is based on ICE, where SBC supports ICE-Lite, while the Teams/Skype for Business media endpoint supports ICE Full Form.</span></span>

<span data-ttu-id="17461-357">[![Microsoft Teams Online 통화 흐름 그림 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span><span class="sxs-lookup"><span data-stu-id="17461-357">[![Microsoft Teams Online Call Flows Figure 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span></span>

<span data-ttu-id="17461-358">\*그림 17 - 전화 시스템 직접 라우팅 토폴로지가 있는 Teams</span><span class="sxs-lookup"><span data-stu-id="17461-358">\*Figure 17 - Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="17461-359">다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-359">Note that:</span></span>

- <span data-ttu-id="17461-360">위 다이어그램의 화살표 방향은 엔터프라이즈 경계의 연결에 영향을 주는 통신의 시작 방향을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-360">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="17461-361">미디어용 UDP의 경우 첫 번째 패킷이 역방향으로 흐를 수 있지만, 다른 방향의 패킷이 흐를 때까지 이러한 패킷이 차단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-361">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="17461-362">Teams는 비즈니스용 Skype Online과 나란히 배포되어 클라이언트가 "Teams/SFB 사용자"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-362">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="17461-363">추가 흐름(Teams 온라인 토폴로지 위에):</span><span class="sxs-lookup"><span data-stu-id="17461-363">Additional flows (on top of Teams online topology):</span></span>

- <span data-ttu-id="17461-364">**Flow 4'** - Microsoft 365 또는 Office 365에서 고객 네트워크로의 흐름을 나타내며, 클라우드의 Teams 미디어 서버와 SBC의 프레미스 간 연결을 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-364">**Flow 4'** - Represents a flow from Microsoft 365 or Office 365 to the customer network, used to establish a connection between the Teams media server in the cloud with the SBC on premises.</span></span>
- <span data-ttu-id="17461-365">**흐름 5B** – 우회 모드의 직접 라우팅 SBC를 통해 고객 네트워크 내의 Teams 사용자 간에 미디어 흐름을 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-365">**Flow 5B** – Represents a media flow between the Teams user within the customer network with the Direct Routing SBC in bypass mode.</span></span>
- <span data-ttu-id="17461-366">**흐름 5C** – PSTN 스털빈 호출 우회 모드에서 직접 라우팅 SBC에서 다른 직접 라우팅 SBC로의 미디어 흐름을 나타 내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-366">**Flow 5C** – Represents a media flow between the Direct Routing SBC to another Direct Routing SBC in a PSTN hairpin call bypass mode.</span></span>

<span data-ttu-id="17461-367">**직접 라우팅이 있는 내부 사용자(Teams 전송 릴레이에서 릴레이된 미디어)**</span><span class="sxs-lookup"><span data-stu-id="17461-367">**Internal user with Direct Routing (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="17461-368">[![Microsoft Teams Online 통화 흐름 그림 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span><span class="sxs-lookup"><span data-stu-id="17461-368">[![Microsoft Teams Online Call Flows Figure 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span></span>

<span data-ttu-id="17461-369">*그림 18 - 직접 라우팅이 있는 내부 사용자(Teams 전송 릴레이에서 릴레이된 미디어)*</span><span class="sxs-lookup"><span data-stu-id="17461-369">*Figure 18 - Internal user with Direct Routing (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="17461-370">다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-370">Note that:</span></span>

- <span data-ttu-id="17461-371">SBC에는 Microsoft 365 또는 Office 365에서 라우팅할 수 있는 공용 IP 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-371">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="17461-372">SBC에서 Microsoft 365 또는 Office 365로의 신호 및 미디어와 미디어는 흐름 4 및/또는 흐름 4를 사용하는 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-372">Signaling and media from the SBC to Microsoft 365 or Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="17461-373">고객 네트워크 내의 클라이언트에서 Microsoft 365 또는 Office 365로의 신호 및 미디어는 흐름 4를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-373">Signaling and media from the client within the customer network to Microsoft 365 or Office 365 use flow 4.</span></span>

<span data-ttu-id="17461-374">**직접 라우팅이 있는 원격 사용자(미디어는 미디어 서버(MP)를 통해 라우팅)**</span><span class="sxs-lookup"><span data-stu-id="17461-374">**Remote user with Direct Routing (media is routed through a media server (MP))**</span></span>

<span data-ttu-id="17461-375">[![Microsoft Teams Online 통화 흐름 그림 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span><span class="sxs-lookup"><span data-stu-id="17461-375">[![Microsoft Teams Online Call Flows Figure 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span></span>

<span data-ttu-id="17461-376">*그림 19 - 직접 라우팅이 있는 원격 사용자(미디어는 미디어 서버(MP)를 통해 라우팅)*</span><span class="sxs-lookup"><span data-stu-id="17461-376">*Figure 19 - Remote user with Direct Routing (media is routed through a media server (MP))*</span></span>

<span data-ttu-id="17461-377">다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-377">Note that:</span></span>

- <span data-ttu-id="17461-378">SBC에는 Microsoft 365 또는 Office 365에서 라우팅할 수 있는 공용 IP 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-378">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="17461-379">SBC에서 Microsoft 365 또는 Office 365로의 신호 및 미디어와 미디어는 흐름 4 및/또는 흐름 4를 사용하는 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-379">Signaling and media from the SBC to Microsoft 365 or Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="17461-380">인터넷의 클라이언트에서 Microsoft 365 또는 Office 365로의 신호 및 미디어는 흐름 3을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-380">Signaling and media from the client on the Internet to Microsoft 365 or Office 365 use flow 3.</span></span>

<span data-ttu-id="17461-381">**내부 사용자 직접 라우팅(미디어 우회)**</span><span class="sxs-lookup"><span data-stu-id="17461-381">**Internal user Direct Routing (media bypass)**</span></span>

<span data-ttu-id="17461-382">[![Microsoft Teams Online 통화 흐름 그림 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span><span class="sxs-lookup"><span data-stu-id="17461-382">[![Microsoft Teams Online Call Flows Figure 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span></span>

<span data-ttu-id="17461-383">*그림 20 - 내부 사용자 직접 라우팅(미디어 우회)*</span><span class="sxs-lookup"><span data-stu-id="17461-383">*Figure 20 - Internal user Direct Routing (media bypass)*</span></span>

<span data-ttu-id="17461-384">다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-384">Note that:</span></span>

- <span data-ttu-id="17461-385">SBC에는 Microsoft 365 또는 Office 365에서 라우팅할 수 있는 공용 IP 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-385">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="17461-386">SBC에서 Microsoft 365 또는 Office 365로 신호를 전송하는 경우와 흐름 4 및/또는 흐름 4를 사용하는 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-386">Signaling from SBC to Microsoft 365 or Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="17461-387">고객 네트워크 내의 클라이언트에서 Microsoft 365 또는 Office 365로 신호를 전송하는 경우 흐름 4를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-387">Signaling from client within the customer network to Microsoft 365 or Office 365 use flow 4.</span></span>

- <span data-ttu-id="17461-388">고객 네트워크 내의 클라이언트에서 고객 네트워크 내의 SBC로의 미디어는 흐름 5B를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-388">Media from client within the customer network to SBC within the customer network use flow 5B.</span></span>

<span data-ttu-id="17461-389">**직접 라우팅이 있는 원격 사용자(Teams 전송 릴레이에서 릴레이된 미디어 우회)**</span><span class="sxs-lookup"><span data-stu-id="17461-389">**Remote user with Direct Routing (media bypass relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="17461-390">[![Microsoft Teams Online 통화 흐름 그림 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span><span class="sxs-lookup"><span data-stu-id="17461-390">[![Microsoft Teams Online Call Flows Figure 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span></span>

<span data-ttu-id="17461-391">*그림 21 - 직접 라우팅이 있는 원격 사용자(Teams 전송 릴레이에서 릴레이된 미디어 우회)*</span><span class="sxs-lookup"><span data-stu-id="17461-391">*Figure 21 - Remote user with Direct Routing (media bypass relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="17461-392">다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-392">Note that:</span></span>

- <span data-ttu-id="17461-393">SBC에는 Microsoft 365 또는 Office 365 및 인터넷에서 라우팅할 수 있는 공용 IP 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-393">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365 and Internet.</span></span>

- <span data-ttu-id="17461-394">SBC에서 Microsoft 365 또는 Office 365로 신호를 전송하고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-394">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="17461-395">인터넷의 클라이언트에서 Microsoft 365 또는 Office 365로의 신호는 흐름 3을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-395">Signaling from the client on the Internet to Microsoft 365 or Office 365 uses flow 3.</span></span>

- <span data-ttu-id="17461-396">인터넷의 클라이언트에서 고객 네트워크 내의 SBC로의 미디어는 Teams 전송 릴레이에서 릴레이된 흐름 3 및 4를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-396">Media from the client on the Internet to the SBC within the customer network uses flows 3 and 4, relayed by Teams Transport Relay.</span></span>

<span data-ttu-id="17461-397">**원격 사용자 직접 라우팅(미디어 우회 직접)**</span><span class="sxs-lookup"><span data-stu-id="17461-397">**Remote user Direct Routing (media bypass direct)**</span></span>

<span data-ttu-id="17461-398">[![Microsoft Teams Online 통화 흐름 그림 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span><span class="sxs-lookup"><span data-stu-id="17461-398">[![Microsoft Teams Online Call Flows Figure 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span></span>

<span data-ttu-id="17461-399">*그림 22 - 원격 사용자 직접 라우팅(미디어 우회 직접)*</span><span class="sxs-lookup"><span data-stu-id="17461-399">*Figure 22 - Remote user Direct Routing (media bypass direct)*</span></span>

<span data-ttu-id="17461-400">다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-400">Note that:</span></span>

- <span data-ttu-id="17461-401">SBC에는 Microsoft 365 또는 Office 365 및 인터넷에서 라우팅할 수 있는 공용 IP 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-401">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365 and the Internet.</span></span>

- <span data-ttu-id="17461-402">SBC에서 Microsoft 365 또는 Office 365로 신호를 전송하고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-402">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="17461-403">인터넷의 클라이언트에서 Microsoft 365 또는 Office 365로의 신호는 흐름 3을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-403">Signaling from the client on the Internet to Microsoft 365 or Office 365 uses flow 3.</span></span>

- <span data-ttu-id="17461-404">인터넷의 클라이언트에서 고객 네트워크 내의 SBC로의 미디어는 흐름 2를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-404">Media from the client on the Internet to the SBC within the customer network uses flow 2.</span></span>

<span data-ttu-id="17461-405">**직접 라우팅(미디어 우회) – PSTN 스위인 호출(전달/전송으로 인해)**</span><span class="sxs-lookup"><span data-stu-id="17461-405">**Direct Routing (media bypass) – PSTN hairpin call (due to call forward/transfer)**</span></span>

<span data-ttu-id="17461-406">[![Microsoft Teams Online 통화 흐름 그림 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span><span class="sxs-lookup"><span data-stu-id="17461-406">[![Microsoft Teams Online Call Flows Figure 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span></span>

<span data-ttu-id="17461-407">*그림 23 - 직접 라우팅(미디어 우회) - PSTN 스위인 호출(전달/전송으로 인해)*</span><span class="sxs-lookup"><span data-stu-id="17461-407">*Figure 23 - Direct Routing (media bypass) - PSTN hairpin call (due to call forward/transfer)*</span></span>

<span data-ttu-id="17461-408">다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-408">Note that:</span></span>

- <span data-ttu-id="17461-409">SBC에는 Microsoft 365 또는 Office 365에서 라우팅할 수 있는 공용 IP 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-409">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="17461-410">SBC에서 Microsoft 365 또는 Office 365로 신호를 전송하고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-410">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="17461-411">호출이 PSTN에서 PSTN으로 연결된 후 클라이언트가 신호 및 미디어 루프에서 아웃됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-411">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="17461-412">고객 네트워크 내의 SBC 인스턴스 A에서 고객 네트워크 내의 SBC 인스턴스 B로의 미디어(여기서 A와 B는 동일한 인스턴스일 수 있습니다)는 흐름 5C를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-412">Media from SBC instance A within the customer network to SBC instance B within the customer network (where, A and B can be the same instance) uses flow 5C.</span></span>

<span data-ttu-id="17461-413">**직접 라우팅(Microsoft 365 또는 Office 365를 통한 미디어) – 두 테넌트에 대한 PSTN 이발 통화**</span><span class="sxs-lookup"><span data-stu-id="17461-413">**Direct Routing (media through Microsoft 365 or Office 365) – PSTN hairpin call across two tenants**</span></span>

<span data-ttu-id="17461-414">[![Microsoft Teams Online 통화 흐름 그림 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span><span class="sxs-lookup"><span data-stu-id="17461-414">[![Microsoft Teams Online Call Flows Figure 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span></span>

<span data-ttu-id="17461-415">*그림 24 - 직접 라우팅(Microsoft 365 또는 Office 365를 통한 미디어) – 두 테넌트에 대한 PSTN 이발 통화*</span><span class="sxs-lookup"><span data-stu-id="17461-415">*Figure 24 - Direct Routing (media through Microsoft 365 or Office 365) – PSTN hairpin call across two tenants*</span></span>

<span data-ttu-id="17461-416">다음에 유의합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-416">Note that:</span></span>

- <span data-ttu-id="17461-417">SBC에는 Microsoft 365 또는 Office 365에서 라우팅할 수 있는 공용 IP 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-417">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="17461-418">SBC에서 Microsoft 365 또는 Office 365로 신호를 전송하고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="17461-418">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="17461-419">호출이 PSTN에서 PSTN으로 연결된 후 클라이언트가 신호 및 미디어 루프에서 아웃됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-419">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="17461-420">고객 네트워크 X 내의 SBC 인스턴스 A에서 SBC 인스턴스 B로의 미디어는 Microsoft 365 또는 Office 365 Media Server를 통해 릴레이되어야 합니다. 우회 모드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-420">Media from SBC instance A within the customer network X to SBC instance B must be relayed through the Microsoft 365 or Office 365 Media Server and can't use bypass mode.</span></span>

## <a name="teams-with-express-route-optimization"></a><span data-ttu-id="17461-421">Express 경로 최적화가 있는 Teams</span><span class="sxs-lookup"><span data-stu-id="17461-421">Teams with Express Route optimization</span></span>

<span data-ttu-id="17461-422">[![Microsoft Teams Online 통화 흐름 그림 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span><span class="sxs-lookup"><span data-stu-id="17461-422">[![Microsoft Teams Online Call Flows Figure 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span></span>

<span data-ttu-id="17461-423">*그림 25 - Express 경로 최적화가 있는 Teams*</span><span class="sxs-lookup"><span data-stu-id="17461-423">*Figure 25 - Teams with Express Route optimization*</span></span>

<span data-ttu-id="17461-424">Express Route가 정당화되고 배포된 경우 Teams 흐름을 흐름 4에서 흐름 1로, 흐름 4에서 흐름 1로 다시 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-424">In the case that Express Route is justified and deployed, then Teams flows could be re-routed from flow 4 to flow 1 and from flow 4' to flow 1'.</span></span> <span data-ttu-id="17461-425">그러나 Teams 애플리케이션은 흐름 4 및 4를 사용하는 인터넷을 통해 다른 Microsoft 365 또는 Office 365 흐름에 대한 종속성은 까다로워야 합니다. 따라서 이러한 흐름을 차단하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-425">However, the Teams application has a hard dependency on other Microsoft 365 or Office 365 flows over the Internet using flows 4 and 4'; hence these flows must not be blocked.</span></span>

<span data-ttu-id="17461-426">비즈니스용 Skype 하이브리드 에지 트래픽은 외부 사용자와 통신하고 다른 테넌트와 페더해지기 위해 Express Route가 아닌 인터넷으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-426">Note that Skype for Business hybrid Edge traffic is routed to the Internet and not to Express Route to communicate with external users and federate with other tenants.</span></span>

<span data-ttu-id="17461-427">비대칭 흐름을 방지하려면 다시 라우팅이 양방향이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-427">To prevent asymmetrical flows, re-routing must be in both directions.</span></span> <span data-ttu-id="17461-428">즉, 고객 네트워크 내의 주소는 최적화에 따라 인터넷 또는 Express 경로를 통해 라우팅할 수 있지만 둘 다를 통해 라우팅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17461-428">In other words, an address within the customer network is routable either through Internet or Express Route, based on optimization, but not through both.</span></span>


<span data-ttu-id="17461-429">**고객 네트워크-외부 사용자(Teams 전송 릴레이에서 릴레이된 미디어):**</span><span class="sxs-lookup"><span data-stu-id="17461-429">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="17461-430">[![Microsoft Teams Online 통화 흐름 그림 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span><span class="sxs-lookup"><span data-stu-id="17461-430">[![Microsoft Teams Online Call Flows Figure 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span></span>

<span data-ttu-id="17461-431">*그림 26 - 외부 사용자에 대한 고객 네트워크(Teams 전송 릴레이에서 릴레이된 미디어)*</span><span class="sxs-lookup"><span data-stu-id="17461-431">*Figure 26 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="17461-432">**높은 수준의 단계:**</span><span class="sxs-lookup"><span data-stu-id="17461-432">**High Level Steps:**</span></span>

1. <span data-ttu-id="17461-433">고객 네트워크 내의 Teams 사용자는 flow2를 사용하여 DNS(URL 도메인 이름)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-433">Teams User within customer network resolves URL domain name (DNS) using flow2.</span></span>
1. <span data-ttu-id="17461-434">고객 네트워크 내의 Teams 사용자는 흐름 1을 사용하여 Teams 전송 릴레이에 미디어 릴레이 포트를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-434">Teams User within customer network allocates a media Relay port on Teams Transport Relay using flow 1.</span></span>
1. <span data-ttu-id="17461-435">고객 네트워크 내의 Teams 사용자는 흐름 1을 사용하여 ICE 후보와 함께 "초대"를 Microsoft 365 또는 Office 365로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-435">Teams User within customer network sends "invite" with ICE candidates using flow 1 to Microsoft 365 or Office 365.</span></span>
1. <span data-ttu-id="17461-436">Microsoft 365 또는 Office 365는 흐름 3을 사용하여 외부 Teams 사용자에게 알림을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-436">Microsoft 365 or Office 365 sends notification to external Teams user using flow 3.</span></span>
1. <span data-ttu-id="17461-437">Teams 외부 사용자는 흐름 3을 사용하여 Teams 전송 릴레이에 미디어 릴레이 포트를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-437">Teams external user allocates a media Relay port on Teams Transport Relay using flow 3.</span></span>
1. <span data-ttu-id="17461-438">Teams 외부 사용자는 흐름 3을 사용하여 ICE 후보와 "답변"을 보내며, 흐름 1을 사용하는 Teams 사용자 A에게 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="17461-438">Teams external user sends "answer" with ICE candidates using flow 3, which is forwarded back to Teams user A using Flow 1.</span></span>
1. <span data-ttu-id="17461-439">Teams 사용자 A와 Teams 사용자 B는 ICE 연결 테스트를 호출하고 Teams 전송 릴레이에서 릴레이되는 흐름 1과 3을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-439">Teams User A and Teams User B invoke ICE connectivity tests and selects flows 1 and 3, which are relayed by Teams Transport Relay.</span></span>
1. <span data-ttu-id="17461-440">Teams 사용자는 흐름 1과 3을 사용하여 Microsoft 365 또는 Office 365에 원격 분석 데이터를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-440">Teams Users send telemetry to Microsoft 365 or Office 365 using flows 1 and 3.</span></span>

> [!NOTE]
> <span data-ttu-id="17461-441">흐름 4를 사용하도록 설정하여 흐름 4를 요구하는 다른 마이크로 서비스에서 Teams 애플리케이션의 종속성 지원이 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17461-441">Flow 4 must be enabled to support dependencies of Teams application on other micro-services that mandates flow 4.</span></span>
