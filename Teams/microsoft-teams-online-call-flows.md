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
description: 다양한 토폴로지에서 Teams Office 365 및 피어 투 피어 미디어 통신에 사용되는 고유한 팀 흐름을 사용하는 방법에 대해 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 27a2c68483c3d54cb3f3572bbed3a06a53ccc67e
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059212"
---
# <a name="microsoft-teams-call-flows"></a><span data-ttu-id="79615-103">Microsoft Teams 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="79615-103">Microsoft Teams call flows</span></span>

> [!TIP]
> <span data-ttu-id="79615-104">이 세션을 통해 네트워크 Teams 활용하는 방법 및 네트워크 연결 최적화를 계획하는 방법에 대해 알아보고 네트워크 Teams [를 확인합니다.](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="79615-104">Watch this session to learn how Teams leverages your network and how to plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking).</span></span>

## <a name="overview"></a><span data-ttu-id="79615-105">개요</span><span class="sxs-lookup"><span data-stu-id="79615-105">Overview</span></span>

<span data-ttu-id="79615-106">이 문서에서는 다양한 토폴로지에서 Teams Microsoft 365 Office 365 호출 흐름을 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-106">This article describes how Teams uses Microsoft 365 or Office 365 call flows in various topologies.</span></span> <span data-ttu-id="79615-107">또한 피어 투 피어 Teams 통신에 사용되는 고유한 흐름을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-107">In addition, it describes unique Teams flows that are used for peer-to-peer media communication.</span></span> <span data-ttu-id="79615-108">이 문서에서는 이러한 흐름, 해당 목적 및 네트워크의 원본 및 종료를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-108">The document describes these flows, their purpose, and their origin and termination on the network.</span></span> <span data-ttu-id="79615-109">이 문서에서는 다음을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-109">For purposes of this article, assume the following:</span></span>

- <span data-ttu-id="79615-110">Flow X는 클라우드에서 서비스 또는 Microsoft 365 Office 365 위해 프레미스 클라이언트에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-110">Flow X is used by the on-premises client to communicate with the Microsoft 365 or Office 365 service in the cloud.</span></span> <span data-ttu-id="79615-111">이 네트워크는 고객 네트워크에서 시작되고, 네트워크 또는 네트워크의 엔드포인트로 Microsoft 365 Office 365.</span><span class="sxs-lookup"><span data-stu-id="79615-111">It originates from the customer network, and it terminates as an endpoint in Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="79615-112">Flow Y는 인터넷에서 종속성 또는 종속성이 있는 인터넷 Microsoft 365 Office 365 클라이언트에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-112">Flow Y is used by the on-premises client to communicate with a service on the Internet that Microsoft 365 or Office 365 has a dependency on.</span></span> <span data-ttu-id="79615-113">고객 네트워크에서 시작되고 인터넷의 엔드포인트로 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-113">It originates from the customer network, and it terminates as an endpoint on the Internet.</span></span>

<span data-ttu-id="79615-114">이 문서에서는 다음 정보를 다 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-114">This article covers the following information:</span></span>

- <span data-ttu-id="79615-115">**배경** 입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-115">**Background**.</span></span> <span data-ttu-id="79615-116">흐름이 전달할 수 있는 네트워크, 트래픽 유형, 고객 네트워크에서 서비스 Microsoft 365 또는 Office 365 연결 지침, 타사 구성 요소와의 상호 작동성, 미디어 흐름을 선택하는 데 사용되는 Teams 등의 배경 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-116">Provides background information such as networks that the flows may traverse, types of traffic, connectivity guidance from the customer network to Microsoft 365 or Office 365 service endpoints, interoperability with third-party components, and principles that are used by Teams to select media flows.</span></span>

- <span data-ttu-id="79615-117">**다양한 토폴로지의 통화 흐름입니다.**</span><span class="sxs-lookup"><span data-stu-id="79615-117">**Call flows in various topologies**.</span></span> <span data-ttu-id="79615-118">다양한 토폴로지에서 호출 흐름의 사용을 보여 주는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-118">Illustrates the use of call flows in various topologies.</span></span> <span data-ttu-id="79615-119">각 토폴로지에 대해 섹션은 지원되는 모든 흐름을 열기하고 이러한 흐름이 여러 사용 사례에서 사용되는 방법을 보여 주는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-119">For each topology, the section enumerates all supported flows and illustrates how these flows are used in several use cases.</span></span> <span data-ttu-id="79615-120">각 사용 사례에 대해 흐름 다이어그램을 사용하여 흐름의 순서 및 선택을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-120">For each use case, it describes the sequence and selection of flows using a flow diagram.</span></span>

- <span data-ttu-id="79615-121">**Teams 최적화를 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="79615-121">**Teams with Express Route optimization**.</span></span> <span data-ttu-id="79615-122">간단한 토폴로지로 설명된 Express Route가 최적화를 위해 배포될 때 이러한 흐름이 사용되는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-122">Describes how these flows are used when Express Route is deployed for optimization, illustrated using a simple topology.</span></span>

## <a name="background"></a><span data-ttu-id="79615-123">배경</span><span class="sxs-lookup"><span data-stu-id="79615-123">Background</span></span>

### <a name="network-segments"></a><span data-ttu-id="79615-124">네트워크 세그먼트</span><span class="sxs-lookup"><span data-stu-id="79615-124">Network segments</span></span>

<span data-ttu-id="79615-125">**고객 네트워크** 입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-125">**Customer network**.</span></span> <span data-ttu-id="79615-126">제어하고 관리하는 네트워크 세그먼트입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-126">This is the network segment that you control and manage.</span></span> <span data-ttu-id="79615-127">여기에는 유선 또는 무선, 사무실 건물 간 연결, 프레미스 데이터 센터에 대한 연결, 인터넷 공급자, Express Route 또는 기타 개인 피어링에 대한 연결 등 고객 사무실 내의 모든 고객 연결이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-127">This includes all customer connections within customer offices, whether wired or wireless, connections between office buildings, connections to on-premises datacenters, and your connections to Internet providers, Express Route, or any other private peering.</span></span>

<span data-ttu-id="79615-128">일반적으로 고객 네트워크에는 방화벽 및/또는 프록시 서버가 있는 여러 네트워크 경계가 있으며 조직의 보안 정책을 적용하고 설정하고 구성한 특정 네트워크 트래픽만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-128">Typically, a customer network has several network perimeters with firewalls and/or proxy servers, which enforce your organization's security policies, and that only allow certain network traffic that you have set up and configured.</span></span> <span data-ttu-id="79615-129">이 네트워크를 관리하기 때문에 네트워크의 성능을 직접 제어할 수 있으며 네트워크 내의 사이트와 네트워크에서 네트워크 또는 네트워크로의 성능의 유효성을 검사하기 위해 네트워크 평가를 완료하는 Microsoft 365 Office 365 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-129">Because you manage this network, you have direct control over the performance of the network, and we recommend that you complete network assessments to validate performance both within sites in your network and from your network to the Microsoft 365 or Office 365 network.</span></span>

<span data-ttu-id="79615-130">**인터넷**.</span><span class="sxs-lookup"><span data-stu-id="79615-130">**Internet**.</span></span> <span data-ttu-id="79615-131">이는 고객 네트워크 외부에서 Microsoft 365 또는 Office 365 사용자가 사용하는 전체 네트워크의 일부인 네트워크 세그먼트입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-131">This is the network segment that is part of your overall network that will be used by users who are connecting to Microsoft 365 or Office 365 from outside of the customer network.</span></span> <span data-ttu-id="79615-132">또한 고객 네트워크의 일부 트래픽에서 Microsoft 365 또는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="79615-132">It is also used by some traffic from the customer network to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="79615-133">**방문한 또는 게스트 개인 네트워크 입니다.**</span><span class="sxs-lookup"><span data-stu-id="79615-133">**Visited or guest private network**.</span></span> <span data-ttu-id="79615-134">이는 사용자와 게스트가 방문할 수 있는 공용 인터넷 외부의 네트워크 세그먼트입니다(예: 홈 사설 네트워크 또는 엔터프라이즈 사설 네트워크) 사용자와 해당 Teams 상호 작용하는 사용자와 해당 고객이 상주할 수 있는 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-134">This is the network segment outside your customer network, but not in the public Internet, that your users and their guests may visit (for example, a home private network or an enterprise private network, that does not deploy Teams, where your users and their customers that interact with Teams services may reside).</span></span>

> [!NOTE]
> <span data-ttu-id="79615-135">이러한 네트워크에 Microsoft 365 Office 365 연결도 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-135">Connectivity to Microsoft 365 or Office 365 is also applicable to these networks.</span></span>

<span data-ttu-id="79615-136">**Microsoft 365 또는 Office 365.**</span><span class="sxs-lookup"><span data-stu-id="79615-136">**Microsoft 365 or Office 365**.</span></span> <span data-ttu-id="79615-137">이 네트워크 세그먼트는 서비스 또는 Microsoft 365 Office 365 세그먼트입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-137">This is the network segment that supports Microsoft 365 or Office 365 services.</span></span> <span data-ttu-id="79615-138">대부분의 위치에서 고객 네트워크에 근접한 에지로 전 세계에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-138">It is distributed worldwide with edges in proximity to the customer network in most locations.</span></span> <span data-ttu-id="79615-139">함수에는 전송 릴레이, 회의 서버 및 미디어 프로세서가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-139">Functions include Transport Relay, conferencing server, and Media Processor.</span></span>

<span data-ttu-id="79615-140">**Express Route(선택 사항)**.</span><span class="sxs-lookup"><span data-stu-id="79615-140">**Express Route (optional)**.</span></span> <span data-ttu-id="79615-141">이는 전체 네트워크의 일부인 네트워크 세그먼트로, 네트워크 또는 네트워크 네트워크에 대한 전용 개인 Microsoft 365 Office 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-141">This is the network segment that is part of your overall network that will give you a dedicated, private connection to the Microsoft 365 or Office 365 network.</span></span>

### <a name="types-of-traffic"></a><span data-ttu-id="79615-142">트래픽 유형</span><span class="sxs-lookup"><span data-stu-id="79615-142">Types of traffic</span></span>

<span data-ttu-id="79615-143">**실시간 미디어**.</span><span class="sxs-lookup"><span data-stu-id="79615-143">**Real-time media**.</span></span> <span data-ttu-id="79615-144">오디오, 비디오 및 화면 공유 워크로드를 지원하는 RTP(실시간 전송 프로토콜) 내에 캡슐화된 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-144">Data encapsulated within Real-time Transport Protocol (RTP) that supports audio, video, and screen sharing workloads.</span></span> <span data-ttu-id="79615-145">일반적으로 미디어 트래픽은 대기 시간이 매우 중요하기 때문에 이 트래픽이 가능한 가장 직접적인 경로를 취하고 UDP와 TCP를 전송 계층 프로토콜로 사용하게 하려는데, 이는 양질의 관점에서 대화형 실시간 미디어에 가장 적합한 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-145">In general, media traffic is highly latency sensitive, so you would want this traffic to take the most direct path possible, and to use UDP versus TCP as the transport layer protocol, which is the best transport for interactive real-time media from a quality perspective.</span></span> <span data-ttu-id="79615-146">(마지막 수단으로 미디어는 TCP/IP를 사용할 수 있으며 HTTP 프로토콜 내에서 터널링할 수도 있지만 품질에 좋지 않은 의미로 인해 권장되지 않습니다.) RTP 흐름은 페이로드만 암호화되는 SRTP를 사용하여 보호됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-146">(Note that as a last resort, media can use TCP/IP and also be tunneled within the HTTP protocol, but it is not recommended due to bad quality implications.) RTP flow is secured using SRTP, in which only the payload is encrypted.</span></span>

<span data-ttu-id="79615-147">**신호 입니다.**</span><span class="sxs-lookup"><span data-stu-id="79615-147">**Signaling**.</span></span> <span data-ttu-id="79615-148">클라이언트와 서버 또는 작업을 제어하는 데 사용되는 다른 클라이언트(예: 호출이 시작될 때)와 인스턴트 메시지를 전달하는 데 사용되는 다른 클라이언트 간의 통신 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-148">The communication link between the client and server, or other clients that are used to control activities (for example, when a call is initiated), and deliver instant messages.</span></span> <span data-ttu-id="79615-149">대부분의 신호 트래픽은 HTTPS 기반 REST 인터페이스를 사용하며, 일부 시나리오에서는 SIP 프로토콜을 사용합니다(예: Microsoft 365 또는 Office 365 세션 테두리 컨트롤러 간의 연결).</span><span class="sxs-lookup"><span data-stu-id="79615-149">Most signaling traffic uses the HTTPS-based REST interfaces, though in some scenarios (for example, connection between Microsoft 365 or Office 365 and a Session Border Controller) it uses SIP protocol.</span></span> <span data-ttu-id="79615-150">이 트래픽은 대기 시간에 훨씬 덜 민감하지만 엔드포인트 간의 대기 시간이 몇 초를 초과하면 서비스 중단 또는 호출 시간 제한이 발생할 수 있다는 것을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-150">It's important to understand that this traffic is much less sensitive to latency but may cause service outages or call timeouts if latency between the endpoints exceeds several seconds.</span></span>

### <a name="connectivity-to-microsoft-365-or-office-365"></a><span data-ttu-id="79615-151">Microsoft 365 또는 Office 365</span><span class="sxs-lookup"><span data-stu-id="79615-151">Connectivity to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="79615-152">Teams [인터넷에 연결해야 합니다.](/office365/enterprise/assessing-network-connectivity)</span><span class="sxs-lookup"><span data-stu-id="79615-152">Teams requires [connectivity to the Internet](/office365/enterprise/assessing-network-connectivity).</span></span> <span data-ttu-id="79615-153">Teams 엔드포인트 URL 및 IP 주소 범위는 URL 및 IP Office 365 범위에 [나열됩니다.](/office365/enterprise/urls-and-ip-address-ranges)</span><span class="sxs-lookup"><span data-stu-id="79615-153">Teams endpoint URLs and IP address ranges are listed in [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="79615-154">(TCP 포트 80 및 443 및 UDP 포트 3478~3481에 대한 연결이 필요합니다.) 또한 Teams 인터넷에 연결해야 하는 비즈니스용 Skype Online에 대한 종속성도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-154">(Note that open connectivity to TCP ports 80 and 443, and to UDP ports 3478 through 3481, is required.) Furthermore, Teams has a dependency on Skype for Business Online, which must also be connected to the Internet.</span></span>

<span data-ttu-id="79615-155">Teams 흐름 연결은 표준 IETF 대화형 연결 수립(ICE) 프로시저를 사용하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-155">Teams media flows connectivity is implemented using standard IETF Interactive Connectivity Establishment (ICE) procedures.</span></span>

### <a name="interoperability-restrictions"></a><span data-ttu-id="79615-156">상호 연동성 제한 사항</span><span class="sxs-lookup"><span data-stu-id="79615-156">Interoperability restrictions</span></span>

<span data-ttu-id="79615-157">**타사 미디어 릴레이**.</span><span class="sxs-lookup"><span data-stu-id="79615-157">**Third-party media relays**.</span></span> <span data-ttu-id="79615-158">Teams 미디어 흐름(즉, 미디어 엔드포인트 중 Teams)은 네이티브 미디어 릴레이에서만 Teams 비즈니스용 Skype 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-158">A Teams media flow (that is, where one of the media endpoints is Teams) may traverse only Teams or Skype for Business native media relays.</span></span> <span data-ttu-id="79615-159">타사 미디어 릴레이와의 상호 연동성은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-159">Interoperability with a third-party media relay is not supported.</span></span> <span data-ttu-id="79615-160">(PSTN을 사용하는 경계의 타사 SBC는 SRTP를 사용하여 보호된 RTP/RTCP 스트림을 종료하고 다음 홉에 릴레이하지 말아야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="79615-160">(Note that a third-party SBC on the boundary with PSTN must terminate RTP/RTCP stream, secured using SRTP, and not relay it to the next hop.)</span></span>

<span data-ttu-id="79615-161">**타사 SIP 프록시 서버 입니다.**</span><span class="sxs-lookup"><span data-stu-id="79615-161">**Third-party SIP proxy servers**.</span></span> <span data-ttu-id="79615-162">타사 SBC 및/Teams SIP 대화 상자를 통해 네이티브 SIP Teams 또는 비즈니스용 Skype 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-162">A Teams signaling SIP dialog with a third-party SBC and/or gateway may traverse Teams or Skype for Business native SIP proxies.</span></span> <span data-ttu-id="79615-163">타사 SIP 프록시와의 상호 연동성은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-163">Interoperability with a third-party SIP proxy is not supported.</span></span>

<span data-ttu-id="79615-164">**타사 B2BUA(또는 SBC) 입니다.**</span><span class="sxs-lookup"><span data-stu-id="79615-164">**Third-party B2BUA (or SBC)**.</span></span> <span data-ttu-id="79615-165">PSTN Teams 미디어 흐름은 타사 SBC에 의해 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-165">A Teams media flow to and from the PSTN is terminated by a third-party SBC.</span></span> <span data-ttu-id="79615-166">그러나 타사 SBC와의 상호 Teams(타사 SBC가 두 개의 Teams 또는 비즈니스용 Skype 엔드포인트를 중재하는 경우)는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-166">However, interoperability with a third-party SBC within the Teams network (where a third-party SBC mediates two Teams or Skype for Business endpoints) is not supported.</span></span>

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a><span data-ttu-id="79615-167">권장되지 않는 기술 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79615-167">Technologies that are not recommended with Microsoft Teams</span></span>

<span data-ttu-id="79615-168">**VPN 네트워크** 입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-168">**VPN network**.</span></span> <span data-ttu-id="79615-169">미디어 트래픽(또는 흐름 2')에는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-169">It is not recommended for media traffic (or flow 2').</span></span> <span data-ttu-id="79615-170">VPN 클라이언트는 [Lync](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210)미디어를 사용하여 VPN 터널을 우회하는 Teams 외부 비 VPN 사용자와 같은 미디어 트래픽을 분할 터널링 및 라우팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-170">The VPN client should use split tunneling and route Teams media traffic like any external non-VPN user, as specified in [Enabling Lync media to bypass a VPN tunnel](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210).</span></span>

> [!NOTE]
> <span data-ttu-id="79615-171">타이틀은 Lync를 나타내지만, 타이틀도 Lync에 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-171">Although the title indicates Lync, it is applicable to Teams as well.</span></span>

<span data-ttu-id="79615-172">**패킷 셰이프.**</span><span class="sxs-lookup"><span data-stu-id="79615-172">**Packet shapers**.</span></span> <span data-ttu-id="79615-173">모든 종류의 패킷 스니퍼, 패킷 검사 또는 패킷 셰이퍼 디바이스는 미디어 트래픽에 Teams 권장되지 않고 품질이 크게 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-173">Any kind of packet snipper, packet inspection, or packet shaper devices are not recommended for Teams media traffic and may degrade quality significantly.</span></span>

### <a name="principles"></a><span data-ttu-id="79615-174">원칙</span><span class="sxs-lookup"><span data-stu-id="79615-174">Principles</span></span>

<span data-ttu-id="79615-175">호출 흐름을 이해하는 데 도움이 되는 네 가지 일반적인 원칙은 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="79615-175">There are four general principles that help you understand call flows for Microsoft Teams:</span></span>

- <span data-ttu-id="79615-176">Microsoft Teams 첫 번째 Microsoft 365 참가한 Microsoft 365 Office 365 지역을 통해 개최됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-176">A Microsoft Teams conference is hosted by Microsoft 365 or Office 365 in the same region where the first participant joined.</span></span> <span data-ttu-id="79615-177">(일부 토폴로지에서 이 규칙에 대한 예외가 있는 경우 이 문서에 설명되어 적절한 호출 흐름에 의해 설명됩니다.)</span><span class="sxs-lookup"><span data-stu-id="79615-177">(Note that if there are exceptions to this rule in some topologies, they will be described in this document and illustrated by an appropriate call flow.)</span></span>

- <span data-ttu-id="79615-178">Teams 또는 Microsoft 365 Office 365 미디어 엔드포인트는 통화 유형에 기반하지 않는 미디어 처리 요구 사항을 기반으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-178">A Teams media endpoint in Microsoft 365 or Office 365 is used based on media processing needs and not based on call type.</span></span> <span data-ttu-id="79615-179">(예를 들어 지점 간 통화는 클라우드의 미디어 엔드포인트를 사용하여 전사 또는 기록을 위해 미디어를 처리하고, 두 참가자가 있는 컨퍼런스는 클라우드에서 미디어 엔드포인트를 사용하지 않을 수 있습니다.) 그러나 대부분의 컨퍼런스는 미디어 엔드포인트를 사용하여 회의가 호스트되는 위치로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-179">(For example, a point-to-point call may use a media endpoint in the cloud to process media for transcription or recording, while a conference with two participants may not use any media endpoint in the cloud.) However, most conferences will use a media endpoint for mixing and routing purposes, allocated where the conference is hosted.</span></span> <span data-ttu-id="79615-180">클라이언트에서 미디어 엔드포인트로 전송된 미디어 트래픽은 고객 네트워크 방화벽 제한으로 Microsoft 365 또는 Office 365 전송 릴레이를 직접 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-180">The media traffic sent from a client to the media endpoint may be routed directly or use a Transport Relay in Microsoft 365 or Office 365 if required due to customer network firewall restrictions.</span></span>

- <span data-ttu-id="79615-181">피어 투 피어 호출에 대한 미디어 트래픽은 호출이 클라우드에서 미디어 엔드포인트를 지시하지 않는다고 생각하면 사용할 수 있는 가장 직접적인 경로를 사용하게 됩니다(이전 원칙 참조).</span><span class="sxs-lookup"><span data-stu-id="79615-181">Media traffic for peer-to-peer calls takes the most direct route that is available, assuming that the call doesn't mandate a media endpoint in the cloud (see previous principle).</span></span> <span data-ttu-id="79615-182">기본 설정 경로는 원격 피어(클라이언트)로 직접 이동되지만 해당 경로를 사용할 수 없는 경우 하나 이상의 전송 릴레이가 트래픽을 릴레이합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-182">The preferred route is direct to the remote peer (client), but if that route isn't available, then one or more Transport Relays will relay traffic.</span></span> <span data-ttu-id="79615-183">미디어 트래픽은 미디어 품질에 영향을 주기 때문에 패킷 셰이더, VPN 서버 등의 서버를 횡단하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-183">It is recommended that media traffic shall not transverse servers such as packet shapers, VPN servers, and so on, since this will impact the media quality.</span></span>

- <span data-ttu-id="79615-184">신호 트래픽은 항상 사용자에게 가장 가까운 서버로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-184">Signaling traffic always goes to the closest server to the user.</span></span>

<span data-ttu-id="79615-185">선택한 미디어 경로에 대한 자세한 내용은 [BRK4016의 미디어 흐름 이해를 Microsoft Teams 참조합니다.](https://www.youtube.com/watch?v=1tmHMIlAQdo)</span><span class="sxs-lookup"><span data-stu-id="79615-185">To learn more about the details on the media path that is chosen, see [Understanding Media Flows in Microsoft Teams - BRK4016](https://www.youtube.com/watch?v=1tmHMIlAQdo).</span></span>

## <a name="call-flows-in-various-topologies"></a><span data-ttu-id="79615-186">다양한 토폴로지의 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="79615-186">Call flows in various topologies</span></span>

### <a name="teams-topology"></a><span data-ttu-id="79615-187">Teams 토폴로지</span><span class="sxs-lookup"><span data-stu-id="79615-187">Teams topology</span></span>

<span data-ttu-id="79615-188">이 토폴로지는 직접 라우팅과 같은 Teams 배포하지 않고 클라우드에서 비즈니스용 Skype 서버 서비스를 전화 시스템 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-188">This topology is used by customers that leverage Teams services from the cloud without any on-premises deployment, such as Skype for Business Server or Phone System Direct Routing.</span></span> <span data-ttu-id="79615-189">또한 Azure Express 경로 없이 Microsoft 365 Office 365 인터페이스가 인터넷을 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-189">In addition, the interface to Microsoft 365 or Office 365 is done over the Internet without Azure Express Route.</span></span>

<span data-ttu-id="79615-190">[![Microsoft Teams 온라인 통화 흐름 그림 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span><span class="sxs-lookup"><span data-stu-id="79615-190">[![Microsoft Teams Online Call Flows Figure 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span></span>

<span data-ttu-id="79615-191">*그림 1 - Teams 토폴로지*</span><span class="sxs-lookup"><span data-stu-id="79615-191">*Figure 1 - Teams topology*</span></span>

<span data-ttu-id="79615-192">참고:</span><span class="sxs-lookup"><span data-stu-id="79615-192">Note that:</span></span>

- <span data-ttu-id="79615-193">위의 다이어그램의 화살표 방향은 엔터프라이즈 경계의 연결에 영향을 주는 통신의 시작 방향을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-193">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="79615-194">미디어용 UDP의 경우 첫 번째 패킷이 역방향으로 흐를 수 있지만 다른 방향으로 패킷이 흐를 때까지 이러한 패킷이 차단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-194">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>
- <span data-ttu-id="79615-195">Teams 온라인과 나란히 배포되는 비즈니스용 Skype 클라이언트는 "Teams/SFB 사용자"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-195">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="79615-196">문서 의 2부에서 다음 선택적 토폴로지에 대한 자세한 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-196">You can find more information on the following optional topologies later in the article:</span></span>

- <span data-ttu-id="79615-197">비즈니스용 Skype 배포는 하이브리드 토폴로지에서 Teams **설명합니다.**</span><span class="sxs-lookup"><span data-stu-id="79615-197">Skype for Business on-premises deployment is described in **Teams hybrid topology**.</span></span>
- <span data-ttu-id="79615-198">전화 시스템 PSTN 연결에 대한 직접 라우팅은 직접 라우팅 **토폴로지와** 함께 Teams 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-198">Phone System Direct Routing (for PSTN connectivity) is described in **Teams with Direct Routing topology**.</span></span>
- <span data-ttu-id="79615-199">Express Route는 Express route 최적화를 Teams **설명되어 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="79615-199">Express Route is described in **Teams with Express Route optimization**.</span></span>

<span data-ttu-id="79615-200">**Flow 설명**:</span><span class="sxs-lookup"><span data-stu-id="79615-200">**Flow descriptions**:</span></span>

- <span data-ttu-id="79615-201">**Flow 2** – 고객 네트워크의 사용자가 인터넷으로 시작한 흐름을 사용자의 경험의 일부로 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-201">**Flow 2** – Represents a flow initiated by a user on the customer network to the Internet as a part of the user's Teams experience.</span></span> <span data-ttu-id="79615-202">이러한 흐름의 예로는 DNS 및 피어 투 피어 미디어가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-202">Examples of these flows are DNS and peer-to-peer media.</span></span>
- <span data-ttu-id="79615-203">**Flow 2'** – 원격 모바일 Teams 사용자에 의해 시작된 흐름을 나타내며, VPN을 고객 네트워크에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-203">**Flow 2'** – Represents a flow initiated by a remote mobile Teams user, with VPN to the customer network.</span></span>
- <span data-ttu-id="79615-204">**Flow 3** – 원격 모바일 Teams 사용자가 엔드포인트를 Microsoft 365 Office 365/Teams 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-204">**Flow 3** – Represents a flow initiated by a remote mobile Teams user to Microsoft 365 or Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="79615-205">**Flow 4** – 고객 네트워크의 사용자가 엔드포인트를 Microsoft 365 또는 Office 365 Teams 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-205">**Flow 4** – Represents a flow initiated by a user on the customer network to Microsoft 365 or Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="79615-206">**Flow 5** – 고객 Teams 사용자와 다른 사용자 Teams 또는 비즈니스용 Skype 피어 투 피어 미디어 흐름을 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-206">**Flow 5** – Represents a peer-to-peer media flow between a Teams user and another Teams or Skype for Business user within the customer network.</span></span>
- <span data-ttu-id="79615-207">**Flow 6** – 원격 모바일 Teams 사용자와 인터넷을 통해 다른 원격 모바일 Teams 또는 비즈니스용 Skype 피어 투 피어 미디어 흐름을 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-207">**Flow 6** – Represents a peer-to-peer media flow between a remote mobile Teams user and another remote mobile Teams or Skype for Business user over the Internet.</span></span>

#### <a name="use-case-one-to-one"></a><span data-ttu-id="79615-208">사용 사례: 일대일</span><span class="sxs-lookup"><span data-stu-id="79615-208">Use case: One-to-one</span></span>

<span data-ttu-id="79615-209">일대일 호출은 호출자가 로컬, 릴레이 및 반사(릴레이에서 볼 수 있는 클라이언트의 공용 IP 주소)를 포함하여 IP 주소/포트로 구성된 후보 집합을 얻는 일반적인 모델을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-209">One-to-one calls use a common model in which the caller will obtain a set of candidates consisting of IP addresses/ports, including local, relay, and reflexive (public IP address of client as seen by the relay) candidates.</span></span> <span data-ttu-id="79615-210">호출자는 이러한 후보를 호출된 파티로 보내고, 호출된 파티는 유사한 후보 집합을 획득하여 호출자에 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-210">The caller sends these candidates to the called party; the called party also obtains a similar set of candidates and sends them to the caller.</span></span> <span data-ttu-id="79615-211">STUN 연결 확인 메시지는 어떤 호출자/호출된 파티 미디어 경로가 작동하고 최상의 작업 경로가 선택되어 있는지 찾는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-211">STUN connectivity check messages are used to find which caller/called party media paths work, and the best working path is selected.</span></span> <span data-ttu-id="79615-212">미디어(즉, SRTP를 사용하여 보호된 RTP/RTCP 패킷)는 선택한 후보 쌍을 사용하여 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-212">Media (that is, RTP/RTCP packets secured using SRTP) are then sent using the selected candidate pair.</span></span> <span data-ttu-id="79615-213">전송 릴레이는 Microsoft 365 및 Office 365.</span><span class="sxs-lookup"><span data-stu-id="79615-213">The Transport relay is deployed as part of Microsoft 365 and Office 365.</span></span>

<span data-ttu-id="79615-214">로컬 IP 주소/포트 후보 또는 반사 후보에 연결이 있는 경우 클라이언트 간의 직접 경로(또는 NAT 사용)는 미디어에 대해 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-214">If the local IP address/port candidates or the reflexive candidates have connectivity, then the direct path between the clients (or using a NAT) will be selected for media.</span></span> <span data-ttu-id="79615-215">클라이언트가 고객 네트워크에 있는 경우 직접 경로를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-215">If the clients are both on the customer network, then the direct path should be selected.</span></span> <span data-ttu-id="79615-216">이렇게 하려면 고객 네트워크 내에서 직접 UDP 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-216">This requires direct UDP connectivity within the customer network.</span></span> <span data-ttu-id="79615-217">클라이언트가 유성 클라우드 사용자인 경우 NAT/방화벽에 따라 미디어에서 직접 연결을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-217">If the clients are both nomadic cloud users, then depending on the NAT/firewall, media may use direct connectivity.</span></span>

<span data-ttu-id="79615-218">한 클라이언트가 고객 네트워크의 내부에 있으며 하나의 클라이언트가 외부(예: 모바일 클라우드 사용자)인 경우 로컬 또는 반사 후보 간의 직접 연결은 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-218">If one client is internal on the customer network and one client is external (for example, a mobile cloud user), then it is unlikely that direct connectivity between the local or reflexive candidates is working.</span></span> <span data-ttu-id="79615-219">이 경우 옵션은 두 클라이언트에서 전송 릴레이 후보 중 하나를 사용하는 것입니다(예: 내부 클라이언트는 전송 릴레이에서 전송 릴레이 후보를 Microsoft 365 Office 365, 외부 클라이언트가 STUN/RTP/RTCP 패킷을 전송 릴레이로 보낼 수 있게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-219">In this case, an option is to use one of the Transport Relay candidates from either client (for example, the internal client obtained a relay candidate from the Transport relay in Microsoft 365 or Office 365; the external client needs to be able to send STUN/RTP/RTCP packets to the transport relay).</span></span> <span data-ttu-id="79615-220">또 다른 옵션은 내부 클라이언트가 모바일 클라우드 클라이언트에서 얻은 릴레이 후보로 전송하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-220">Another option is the internal client sends to the relay candidate obtained by the mobile cloud client.</span></span> <span data-ttu-id="79615-221">미디어에 대한 UDP 연결은 매우 권장되는 것이지만 TCP가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-221">Note that, although UDP connectivity for media is highly recommended, TCP is supported.</span></span>

<span data-ttu-id="79615-222">**고급 단계:**</span><span class="sxs-lookup"><span data-stu-id="79615-222">**High-level steps**:</span></span>

1. <span data-ttu-id="79615-223">Teams 사용자 A는 흐름 2를 사용하여 DNS(URL 도메인 이름)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-223">Teams User A resolves URL domain name (DNS) using flow 2.</span></span>
1. <span data-ttu-id="79615-224">Teams 사용자 A는 흐름 4를 사용하여 전송 Teams 릴레이에 미디어 릴레이 포트를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-224">Teams User A allocates a media Relay port on Teams Transport Relay using flow 4.</span></span>
1. <span data-ttu-id="79615-225">Teams 사용자 A는 흐름 4를 사용하여 ICE 후보와 함께 "초대"를 Microsoft 365 또는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="79615-225">Teams User A sends "invite" with ICE candidates using flow 4 to Microsoft 365 or Office 365.</span></span>
1. <span data-ttu-id="79615-226">Microsoft 365 또는 Office 365 흐름 4를 사용하여 Teams 사용자 B에게 알림을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-226">Microsoft 365 or Office 365 sends notification to Teams User B using flow 4.</span></span>
1. <span data-ttu-id="79615-227">Teams 사용자 B는 흐름 4를 사용하여 전송 Teams 미디어 릴레이 포트를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-227">Teams User B allocates a media Relay port on Teams Transport Relay using flow 4.</span></span>
1. <span data-ttu-id="79615-228">Teams 사용자 B는 흐름 4를 사용하여 ICE 후보와 "응답"을 보내며, 이 Teams 4를 사용하여 Teams 사용자 A로 Flow 합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-228">Teams User B sends "answer" with ICE candidates using flow 4, which is forwarded back to Teams User A using Flow 4.</span></span>
1. <span data-ttu-id="79615-229">Teams 사용자 A 및 Teams 사용자 B는 ICE 연결 테스트를 호출하고 사용 가능한 최상의 미디어 경로가 선택됩니다(다양한 사용 사례에 대한 아래 다이어그램 참조).</span><span class="sxs-lookup"><span data-stu-id="79615-229">Teams User A and Teams User B invoke ICE connectivity tests and the best available media path is selected (see diagrams below for various use cases).</span></span>
1. <span data-ttu-id="79615-230">Teams 사용자는 흐름 4를 사용하여 원격 분석 Microsoft 365 Office 365 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-230">Teams Users send telemetry to Microsoft 365 or Office 365 using flow 4.</span></span>

<span data-ttu-id="79615-231">**고객 네트워크 내에서:**</span><span class="sxs-lookup"><span data-stu-id="79615-231">**Within customer network:**</span></span>

<span data-ttu-id="79615-232">[![Microsoft Teams 온라인 통화 흐름 그림 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span><span class="sxs-lookup"><span data-stu-id="79615-232">[![Microsoft Teams Online Call Flows Figure 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span></span>

<span data-ttu-id="79615-233">*그림 2 - 고객 네트워크 내에서*</span><span class="sxs-lookup"><span data-stu-id="79615-233">*Figure 2 - Within customer network*</span></span>

<span data-ttu-id="79615-234">7단계에서 피어 투 피어 미디어 흐름 5가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-234">In step 7, peer-to-peer media flow 5 is selected.</span></span>

<span data-ttu-id="79615-235">미디어는 양방향입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-235">Media is bidirectional.</span></span> <span data-ttu-id="79615-236">흐름 5의 방향은 한 쪽이 이 문서의 모든 흐름과 일치하여 연결 관점에서 통신을 시작했다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-236">The direction of flow 5 indicates that one side initiates the communication from a connectivity perspective, consistent with all the flows in this document.</span></span> <span data-ttu-id="79615-237">이 경우 두 엔드포인트가 고객 네트워크 내에 있기 때문에 사용되는 방향은 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-237">In this case, it doesn't matter which direction is used because both endpoints are within the customer network.</span></span>

<span data-ttu-id="79615-238">**외부 사용자에 대한 고객 네트워크(전송 릴레이로 Teams):**</span><span class="sxs-lookup"><span data-stu-id="79615-238">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="79615-239">[![Microsoft Teams 온라인 통화 흐름 그림 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span><span class="sxs-lookup"><span data-stu-id="79615-239">[![Microsoft Teams Online Call Flows Figure 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span></span>

<span data-ttu-id="79615-240">*그림 3 - 외부 사용자에 대한 고객 네트워크(전송 릴레이로 Teams 미디어)*</span><span class="sxs-lookup"><span data-stu-id="79615-240">*Figure 3 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="79615-241">7단계에서 고객 네트워크에서 원격 모바일 Microsoft 365 또는 Office 365 흐름 3, 원격 모바일 Teams 사용자에서 Microsoft 365 또는 Office 365 흐름이 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-241">In step 7, flow 4, from customer network to Microsoft 365 or Office 365, and flow 3, from remote mobile Teams user to Microsoft 365 or Office 365, are selected.</span></span> <span data-ttu-id="79615-242">이러한 흐름은 Teams 또는 Teams 전송 릴레이로 Microsoft 365 Office 365.</span><span class="sxs-lookup"><span data-stu-id="79615-242">These flows are relayed by Teams Transport Relay within Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="79615-243">미디어는 양방향입니다. 여기서 방향은 연결 관점에서 통신을 시작하는 쪽을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="79615-243">Media is bidirectional, where direction indicates which side initiates the communication from a connectivity perspective.</span></span> <span data-ttu-id="79615-244">이 경우 이러한 흐름은 서로 다른 전송 프로토콜 및 주소를 사용하여 신호 및 미디어에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-244">In this case, these flows are used for signaling and media, using different transport protocols and addresses.</span></span>

<span data-ttu-id="79615-245">**외부 사용자(직접 미디어)에 대한 고객 네트워크:**</span><span class="sxs-lookup"><span data-stu-id="79615-245">**Customer network to external user (direct media):**</span></span>

<span data-ttu-id="79615-246">[![Microsoft Teams 온라인 통화 흐름 그림 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span><span class="sxs-lookup"><span data-stu-id="79615-246">[![Microsoft Teams Online Call Flows Figure 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span></span>

<span data-ttu-id="79615-247">*그림 4 - 외부 사용자에 대한 고객 네트워크(직접 미디어)*</span><span class="sxs-lookup"><span data-stu-id="79615-247">*Figure 4 - Customer network to external user (direct media)*</span></span>

<span data-ttu-id="79615-248">7단계에서 고객 네트워크에서 인터넷(클라이언트의 피어)으로의 흐름 2가 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-248">In step 7, flow 2, from customer network to the Internet (client's peer), is selected.</span></span>

- <span data-ttu-id="79615-249">원격 모바일 사용자가 있는 직접 미디어(Microsoft 365 또는 Office 365)는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-249">Direct media with remote mobile user (not relayed through Microsoft 365 or Office 365) is optional.</span></span> <span data-ttu-id="79615-250">즉, 고객은 이 경로를 차단하여 전송 릴레이를 통해 미디어 경로를 Microsoft 365 또는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="79615-250">In other words, customer may block this path to enforce a media path through Transport Relay in Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="79615-251">미디어는 양방향입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-251">Media is bidirectional.</span></span> <span data-ttu-id="79615-252">흐름 2에서 원격 모바일 사용자로의 방향은 한 쪽이 연결 관점에서 통신을 시작했다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-252">The direction of flow 2 to remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="79615-253">**내부 사용자에 VPN 사용자(전송 릴레이로 Teams 미디어)**</span><span class="sxs-lookup"><span data-stu-id="79615-253">**VPN user to internal user (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="79615-254">[![Microsoft Teams 온라인 통화 흐름 그림 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span><span class="sxs-lookup"><span data-stu-id="79615-254">[![Microsoft Teams Online Call Flows Figure 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span></span>

<span data-ttu-id="79615-255">*그림 5 - 내부 사용자에 VPN 사용자(전송 릴레이로 Teams 미디어)*</span><span class="sxs-lookup"><span data-stu-id="79615-255">*Figure 5 - VPN user to internal user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="79615-256">VPN 간을 고객 네트워크로 신호하는 것은 흐름 2'를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-256">Signaling between the VPN to the customer network is using flow 2'.</span></span> <span data-ttu-id="79615-257">고객 네트워크와 Microsoft 365 또는 Office 365 신호는 흐름 4를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-257">Signaling between the customer network and Microsoft 365 or Office 365 is using flow 4.</span></span> <span data-ttu-id="79615-258">그러나 미디어는 VPN을 우회하고 흐름 3 및 4에서 Teams 미디어 릴레이를 사용하여 Microsoft 365 Office 365.</span><span class="sxs-lookup"><span data-stu-id="79615-258">However, media bypasses the VPN and is routed using flows 3 and 4 through Teams media relay in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="79615-259">**내부 사용자에 대한 VPN 사용자(직접 미디어)**</span><span class="sxs-lookup"><span data-stu-id="79615-259">**VPN user to internal user (direct media)**</span></span>

<span data-ttu-id="79615-260">[![Microsoft Teams 온라인 통화 흐름 그림 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span><span class="sxs-lookup"><span data-stu-id="79615-260">[![Microsoft Teams Online Call Flows Figure 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span></span>

<span data-ttu-id="79615-261">*그림 6 - 내부 사용자에 VPN 사용자(직접 미디어)*</span><span class="sxs-lookup"><span data-stu-id="79615-261">*Figure 6 - VPN user to internal user (direct media)*</span></span>

<span data-ttu-id="79615-262">VPN 간을 고객 네트워크로 신호하는 것은 흐름 2'를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-262">Signaling between the VPN to the customer network is using flow 2'.</span></span> <span data-ttu-id="79615-263">고객 네트워크와 Microsoft 365 또는 Office 365 신호는 흐름 4를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-263">Signaling between the customer network and Microsoft 365 or Office 365 is using flow 4.</span></span> <span data-ttu-id="79615-264">그러나 미디어는 VPN을 무시하고 고객 네트워크에서 인터넷으로 흐름 2를 사용하여 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-264">However, media bypasses the VPN and is routed using flow 2 from the customer network to the Internet.</span></span>

<span data-ttu-id="79615-265">미디어는 양방향입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-265">Media is bidirectional.</span></span> <span data-ttu-id="79615-266">원격 모바일 사용자로 흐름 2의 방향은 한 쪽이 연결 관점에서 통신을 시작했다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-266">The direction of flow 2 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="79615-267">**외부 사용자에 대한 VPN 사용자(직접 미디어)**</span><span class="sxs-lookup"><span data-stu-id="79615-267">**VPN user to external user (direct media)**</span></span>

<span data-ttu-id="79615-268">[![Microsoft Teams 흐름 그림 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span><span class="sxs-lookup"><span data-stu-id="79615-268">[![Microsoft Teams call flows Figure 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span></span>

<span data-ttu-id="79615-269">*그림 7 - 외부 사용자에 대한 VPN 사용자(직접 미디어)*</span><span class="sxs-lookup"><span data-stu-id="79615-269">*Figure 7 - VPN user to external user (direct media)*</span></span>

<span data-ttu-id="79615-270">VPN 사용자 간을 고객 네트워크에 신호하는 것은 흐름 2'를 사용하고 흐름 4를 사용하여 Microsoft 365 또는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="79615-270">Signaling between the VPN user to the customer network is using flow 2' and using flow 4 to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="79615-271">그러나 미디어는 VPN을 우회하고 흐름 6을 사용하여 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-271">However, media bypasses VPN and is routed using flow 6.</span></span>

<span data-ttu-id="79615-272">미디어는 양방향입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-272">Media is bidirectional.</span></span> <span data-ttu-id="79615-273">흐름 6을 원격 모바일 사용자로 이동하는 방향은 한 쪽이 연결 관점에서 통신을 시작했다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-273">The direction of flow 6 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

#### <a name="use-case-teams-to-pstn-through-microsoft-365-or-office-365-trunk"></a><span data-ttu-id="79615-274">사용 사례: Teams 또는 Microsoft 365 통해 PSTN에 Office 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-274">Use Case: Teams to PSTN through Microsoft 365 or Office 365 Trunk</span></span>

<span data-ttu-id="79615-275">Microsoft 365 Office 365 PSTN(공용 전화 시스템 전화 네트워크)에서 전화를 걸고 받을 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-275">Microsoft 365 and Office 365 have a Phone System that allows placing and receiving calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="79615-276">PSTN 트렁크가 호출 전화 시스템 사용하여 연결된 경우 이 사용 사례에 대한 특별한 연결 요구 사항이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-276">If the PSTN trunk is connected using the Phone System Calling Plan, then there are no special connectivity requirements for this use case.</span></span> <span data-ttu-id="79615-277">(사용자 자신의 On-프레미스 PSTN 트렁크를 Microsoft 365 Office 365 직접 라우팅을 전화 시스템 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="79615-277">(If you want to connect your own on-premises PSTN trunk to Microsoft 365 or Office 365, you can use Phone System Direct Routing.)</span></span>

<span data-ttu-id="79615-278">[![Microsoft Teams 온라인 통화 흐름 그림 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span><span class="sxs-lookup"><span data-stu-id="79615-278">[![Microsoft Teams Online Call Flows Figure 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span></span>

<span data-ttu-id="79615-279">*그림 8 - Teams 트렁크를 통해 PSTN으로 Office 365*</span><span class="sxs-lookup"><span data-stu-id="79615-279">*Figure 8 - Teams to PSTN through Office 365 Trunk*</span></span>

#### <a name="use-case-teams-meeting"></a><span data-ttu-id="79615-280">사용 사례: Teams 모임</span><span class="sxs-lookup"><span data-stu-id="79615-280">Use case: Teams meeting</span></span>

<span data-ttu-id="79615-281">VBSS(오디오/비디오/화면 공유) 회의 서버는 Microsoft 365 Office 365.</span><span class="sxs-lookup"><span data-stu-id="79615-281">The audio/video/screen sharing (VBSS) conferencing server is part of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="79615-282">고객 네트워크에서 도달할 수 있어야 하는 공용 IP 주소가 있으며 Nomadic Cloud 클라이언트에서 연결 가능해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-282">It has a public IP address that must be reachable from the customer network and must be reachable from a Nomadic Cloud client.</span></span> <span data-ttu-id="79615-283">각 클라이언트/엔드포인트는 회의 서버에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-283">Each client/endpoint needs to be able to connect to the conferencing server.</span></span>

<span data-ttu-id="79615-284">내부 클라이언트는 일대일 호출에 대해 설명한 방식으로 로컬, 반사 및 릴레이 후보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-284">Internal clients will obtain local, reflexive, and relay candidates in the same manner as described for one-to-one calls.</span></span> <span data-ttu-id="79615-285">클라이언트는 초대에서 회의 서버에 이러한 후보를 보낼 것입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-285">The clients will send these candidates to the conferencing server in an invite.</span></span> <span data-ttu-id="79615-286">회의 서버는 공개적으로 연결 가능한 IP 주소가 있으므로 릴레이를 사용하지 않습니다. 따라서 해당 로컬 IP 주소 후보와 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-286">The conferencing server does not use a relay since it has a publicly reachable IP address, so it responds with its local IP address candidate.</span></span> <span data-ttu-id="79615-287">클라이언트 및 회의 서버는 일대일 호출에 대해 설명된 방식으로 연결을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-287">The client and conferencing server will check connectivity in the same manner described for one-to-one calls.</span></span>

<span data-ttu-id="79615-288">참고:</span><span class="sxs-lookup"><span data-stu-id="79615-288">Note that:</span></span>

- <span data-ttu-id="79615-289">Teams 클라이언트는 비즈니스용 Skype 모임에 참가할 수 비즈니스용 Skype 클라이언트가 Teams 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-289">Teams clients cannot join Skype for Business meetings, and Skype for Business clients cannot join Teams meetings.</span></span>

- <span data-ttu-id="79615-290">PSTN 사용자는 모임의 이끌이 PSTN 호출 및/또는 회의 프로비전에 따라 선택적으로 "IN 전화 걸기" 또는 "전화 걸기"입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-290">A PSTN user optionally "Dials IN" or is "Dialed OUT", depending on the meeting's organizer PSTN Calling and/or conferencing provisioning.</span></span>

- <span data-ttu-id="79615-291">게스트 사용자 또는 고객 사용자는 엄격한 규칙으로 FW/NAT를 사용하여 보호되는 게스트 개인 네트워크에서 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-291">A guest user or a customer user may join from a guest private network, which is protected using FW/NAT with strict rules.</span></span>

<span data-ttu-id="79615-292">[![Microsoft Teams 온라인 통화 흐름 그림 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span><span class="sxs-lookup"><span data-stu-id="79615-292">[![Microsoft Teams Online Call Flows Figure 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span></span>

<span data-ttu-id="79615-293">*그림 9 - Teams 모임*</span><span class="sxs-lookup"><span data-stu-id="79615-293">*Figure 9 - Teams Meeting*</span></span>

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a><span data-ttu-id="79615-294">사용 사례: 비즈니스용 Skype 페더럴</span><span class="sxs-lookup"><span data-stu-id="79615-294">Use case: Federation with Skype for Business on premises</span></span>

<span data-ttu-id="79615-295">**또는 Teams 전송 릴레이로 Microsoft 365 Office 365**</span><span class="sxs-lookup"><span data-stu-id="79615-295">**Media relayed by Teams Transport Relay in Microsoft 365 or Office 365**</span></span>

<span data-ttu-id="79615-296">[![Microsoft Teams 온라인 통화 흐름 그림 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span><span class="sxs-lookup"><span data-stu-id="79615-296">[![Microsoft Teams Online Call Flows Figure 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span></span>

<span data-ttu-id="79615-297">*그림 10 - Teams 전송 릴레이로 Office 365*</span><span class="sxs-lookup"><span data-stu-id="79615-297">*Figure 10 - Media relayed by Teams Transport Relay in Office 365*</span></span>

<span data-ttu-id="79615-298">참고:</span><span class="sxs-lookup"><span data-stu-id="79615-298">Note that:</span></span>

- <span data-ttu-id="79615-299">페더넌트는 정의에 따라 두 테넌트 간의 통신입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-299">Federation is, by definition, a communication between two tenants.</span></span> <span data-ttu-id="79615-300">이 경우, Teams 사용하는 테넌트 A는 비즈니스용 Skype 페더테이트합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-300">In this case, tenant A, which uses Teams, federates with tenant B, which uses Skype for Business on premises.</span></span> <span data-ttu-id="79615-301">테넌트 B가 Microsoft 365 또는 Office 365 경우 비즈니스용 Skype 클라이언트는 흐름 3을 사용하여 Microsoft 365 Office 365.</span><span class="sxs-lookup"><span data-stu-id="79615-301">If tenant B is also using Microsoft 365 or Office 365, then the Skype for Business client would have used flow 3 to connect with Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="79615-302">페더링된 비즈니스용 Skype 클라이언트에서 비즈니스용 Skype 서버 미디어는 이 문서의 범위를 벗어날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-302">Signaling and media from the federated Skype for Business client to on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="79615-303">그러나 명확성을 위해 여기에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-303">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="79615-304">게이트웨이에서 Teams 비즈니스용 Skype 신호가 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-304">Signaling between Teams and Skype for Business is bridged by a gateway.</span></span>

- <span data-ttu-id="79615-305">이 경우 미디어는 흐름 4를 사용하여 고객 Teams 원격 비즈니스용 Skype 전송 릴레이를 통해 릴레이됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-305">Media in this case is relayed by Teams Transport Relay to the customer network and remote Skype for Business client using flow 4.</span></span>

<span data-ttu-id="79615-306">**페더리드 테넌트에서 비즈니스용 Skype 미디어 릴레이로 릴레이된 미디어**</span><span class="sxs-lookup"><span data-stu-id="79615-306">**Media relayed by Skype for Business Media Relay in federated tenant**</span></span>

<span data-ttu-id="79615-307">[![Microsoft Teams 온라인 통화 흐름 그림 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span><span class="sxs-lookup"><span data-stu-id="79615-307">[![Microsoft Teams Online Call Flows Figure 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span></span>

<span data-ttu-id="79615-308">*그림 11 - 페더레이드 테넌트에서 비즈니스용 Skype 미디어 릴레이로 릴레이된 미디어*</span><span class="sxs-lookup"><span data-stu-id="79615-308">*Figure 11 - Media relayed by Skype for Business Media Relay in federated tenant*</span></span>

<span data-ttu-id="79615-309">참고:</span><span class="sxs-lookup"><span data-stu-id="79615-309">Note that:</span></span>

- <span data-ttu-id="79615-310">페더링된 비즈니스용 Skype 클라이언트에서 비즈니스용 Skype 서버 미디어는 이 문서의 범위를 벗어날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-310">Signaling and media from the federated Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="79615-311">그러나 명확성을 위해 여기에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-311">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="79615-312">게이트웨이에서 Teams 비즈니스용 Skype 신호가 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-312">Signaling between Teams and Skype for Business is bridged by a Gateway.</span></span>

- <span data-ttu-id="79615-313">이 경우 미디어는 흐름 2를 사용하여 비즈니스용 Skype 미디어 릴레이를 통해 고객 네트워크에 릴레이됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-313">Media in this case is relayed by Skype for Business on-premises Media Relay to the customer network using flow 2.</span></span> <span data-ttu-id="79615-314">(페더레이드된 Teams 네트워크의 원격 미디어 릴레이로의 트래픽은 처음에는 역방향의 트래픽이 흐르기 시작할 때까지 미디어 릴레이에 의해 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-314">(Note that traffic from Teams user to the remote Media Relay in the federated customer network will be initially blocked by the Media Relay until traffic in the reverse direction starts to flow.</span></span> <span data-ttu-id="79615-315">그러나 양방향 흐름은 양방향으로 연결이 열립니다.)</span><span class="sxs-lookup"><span data-stu-id="79615-315">However, the bidirectional flow will open connectivity in both directions.)</span></span>

<span data-ttu-id="79615-316">**직접(피어 투 피어)**</span><span class="sxs-lookup"><span data-stu-id="79615-316">**Direct (peer-to-peer)**</span></span>

<span data-ttu-id="79615-317">[![Microsoft Teams 온라인 통화 흐름 그림 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span><span class="sxs-lookup"><span data-stu-id="79615-317">[![Microsoft Teams Online Call Flows Figure 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span></span>

<span data-ttu-id="79615-318">*그림 12 - 직접(피어 투 피어)*</span><span class="sxs-lookup"><span data-stu-id="79615-318">*Figure 12 - Direct (peer-to-peer)*</span></span>

### <a name="teams-hybrid-topology"></a><span data-ttu-id="79615-319">Teams 토폴로지</span><span class="sxs-lookup"><span data-stu-id="79615-319">Teams hybrid topology</span></span>

<span data-ttu-id="79615-320">이 토폴로지에는 Teams 비즈니스용 Skype 배포가 포함된 토폴로지가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-320">This topology includes Teams with a Skype for Business on-premises deployment.</span></span>

<span data-ttu-id="79615-321">[![Microsoft Teams 온라인 통화 흐름 그림 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span><span class="sxs-lookup"><span data-stu-id="79615-321">[![Microsoft Teams Online Call Flows Figure 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span></span>

<span data-ttu-id="79615-322">*그림 13 - Teams 토폴로지*</span><span class="sxs-lookup"><span data-stu-id="79615-322">*Figure 13 - Teams hybrid topology*</span></span>

- <span data-ttu-id="79615-323">위의 다이어그램의 화살표 방향은 엔터프라이즈 경계의 연결에 영향을 주는 통신의 시작 방향을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-323">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="79615-324">미디어용 UDP의 경우 첫 번째 패킷이 역방향으로 흐를 수 있지만 다른 방향으로 패킷이 흐를 때까지 이러한 패킷이 차단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-324">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="79615-325">Teams 온라인과 나란히 배포되는 비즈니스용 Skype 클라이언트는 "Teams/SFB 사용자"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-325">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="79615-326">추가 흐름(토폴로지 위에 Teams):</span><span class="sxs-lookup"><span data-stu-id="79615-326">Additional flow (on top of Teams topology):</span></span>

- <span data-ttu-id="79615-327">**Flow 5A** – 고객 네트워크 내의 Teams 사용자와 고객 네트워크 에지의 비즈니스용 Skype 프레미스 미디어 릴레이 간의 피어 투 피어 미디어 흐름을 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-327">**Flow 5A** – Represents a peer-to-peer media flow between a Teams user within the customer network and a Skype for Business on-premises media relay at the customer network edge.</span></span>

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a><span data-ttu-id="79615-328">사용 사례: Teams 비즈니스용 Skype 일대일</span><span class="sxs-lookup"><span data-stu-id="79615-328">Use case: Teams to Skype for Business one-to-one</span></span>

<span data-ttu-id="79615-329">**고객 네트워크 내에서 하이브리드**</span><span class="sxs-lookup"><span data-stu-id="79615-329">**Hybrid within the customer network**</span></span>

<span data-ttu-id="79615-330">[![Microsoft Teams 온라인 통화 흐름 그림 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span><span class="sxs-lookup"><span data-stu-id="79615-330">[![Microsoft Teams Online Call Flows Figure 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span></span>

<span data-ttu-id="79615-331">*그림 14 - 고객 네트워크 내의 하이브리드*</span><span class="sxs-lookup"><span data-stu-id="79615-331">*Figure 14 - Hybrid within customer network*</span></span>

<span data-ttu-id="79615-332">게이트웨이에서 Teams 비즈니스용 Skype 신호가 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-332">Signaling between Teams and Skype for Business is bridged by a gateway.</span></span> <span data-ttu-id="79615-333">그러나 미디어는 흐름 5를 사용하여 고객 네트워크 내에서 직접 피어 투 피어로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-333">However, media is routed directly peer-to-peer within the customer network using flow 5.</span></span>

<span data-ttu-id="79615-334">**외부 사용자와 비즈니스용 Skype 하이브리드 고객 네트워크 - Microsoft 365 또는 Office 365**</span><span class="sxs-lookup"><span data-stu-id="79615-334">**Hybrid customer network with external Skype for Business user – relayed by Microsoft 365 or Office 365**</span></span>

<span data-ttu-id="79615-335">[![Microsoft Teams 온라인 통화 흐름 그림 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span><span class="sxs-lookup"><span data-stu-id="79615-335">[![Microsoft Teams Online Call Flows Figure 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span></span>

<span data-ttu-id="79615-336">*그림 15 - 외부 사용자와 비즈니스용 Skype 하이브리드 고객 네트워크 - Office 365*</span><span class="sxs-lookup"><span data-stu-id="79615-336">*Figure 15 - Hybrid customer network with external Skype for Business user - relayed by Office 365*</span></span>

<span data-ttu-id="79615-337">참고:</span><span class="sxs-lookup"><span data-stu-id="79615-337">Note that:</span></span>

- <span data-ttu-id="79615-338">클라이언트에서 비즈니스용 Skype 클라이언트에서 비즈니스용 Skype 서버 이 문서의 범위를 벗어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-338">Signaling and media from the Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="79615-339">그러나 명확성을 위해 여기에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-339">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="79615-340">게이트웨이에서 Teams 비즈니스용 Skype 신호가 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-340">Signaling between Teams and Skype for Business is bridged by a gateway.</span></span>

- <span data-ttu-id="79615-341">미디어는 흐름 4를 통해 Teams 전송 릴레이를 통해 고객 네트워크에 릴레이됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-341">Media is relayed through Teams Transport Relay to the customer network through flow 4.</span></span>

<span data-ttu-id="79615-342">**외부 사용자와 비즈니스용 Skype 하이브리드 고객 네트워크 - On-Premises Edge에서 릴레이**</span><span class="sxs-lookup"><span data-stu-id="79615-342">**Hybrid customer network with external Skype for Business user – relayed by on-premises Edge**</span></span>

<span data-ttu-id="79615-343">[![Microsoft Teams 온라인 통화 흐름 그림 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span><span class="sxs-lookup"><span data-stu-id="79615-343">[![Microsoft Teams Online Call Flows Figure 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span></span>

<span data-ttu-id="79615-344">*그림 16 - 외부 사용자와 비즈니스용 Skype 하이브리드 고객 네트워크 - On-Premises Edge에서 릴레이*</span><span class="sxs-lookup"><span data-stu-id="79615-344">*Figure 16 - Hybrid customer network with external Skype for Business user - relayed by on-premises Edge*</span></span>

<span data-ttu-id="79615-345">참고:</span><span class="sxs-lookup"><span data-stu-id="79615-345">Note that:</span></span>

- <span data-ttu-id="79615-346">클라이언트에서 비즈니스용 Skype 클라이언트에서 비즈니스용 Skype 서버 미디어는 이 문서의 범위를 벗어날 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-346">Signaling and media from Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="79615-347">그러나 명확성을 위해 여기에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-347">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="79615-348">신호는 게이트웨이에 의해 브리지됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-348">Signaling is bridged by a gateway.</span></span>

- <span data-ttu-id="79615-349">미디어는 비즈니스용 Skype 5A를 사용하여 비즈니스용 Skype 프레미스 에지 내에서 Teams 릴레이됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-349">Media is relayed by Skype for Business Media Relay within Skype for Business on-premises Edge to Teams user within the customer network using media flow 5A.</span></span>

### <a name="teams-with-phone-system-direct-routing-topology"></a><span data-ttu-id="79615-350">Teams 직접 전화 시스템 토폴로지와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-350">Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="79615-351">이 토폴로지에는 직접 Teams 전화 시스템 포함된 토폴로지가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-351">This topology includes Teams with Phone System Direct Routing.</span></span>

<span data-ttu-id="79615-352">직접 라우팅을 사용하면 지원되는 SBC(고객 소유의 SBC) 하드웨어 디바이스를 연결한 후 전화 통신 트렁크를 해당 디바이스에 연결하여 타사 PSTN(공용 전환 전화 네트워크) 서비스 공급자를 사용할 수 Microsoft 365 Office 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-352">Direct Routing enables you to use a third-party Public Switched Telephone Network (PSTN) service provider by pairing a supported on-premises customer-owned Session Border Controller (SBC) hardware device to Microsoft 365 or Office 365, and then connecting the telephony trunk to that device.</span></span>

<span data-ttu-id="79615-353">이 시나리오를 지원하려면 고객은 Microsoft의 인증된 파트너 중 하나에서 직접 라우팅에 대한 인증된 SBC를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-353">To support this scenario, the customer must deploy a certified SBC for Direct Routing from one of Microsoft's certified partners.</span></span> <span data-ttu-id="79615-354">SBC는 공급업체에서 권장하는 Microsoft 365 UDP 트래픽에 Microsoft 365 Office 365 라우팅할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-354">The SBC must be configured as recommended by the vendor, and be routable from Microsoft 365 or Office 365 for direct UDP traffic.</span></span> <span data-ttu-id="79615-355">미디어는 Teams 및/또는 비즈니스용 Skype 클라이언트에서 SBC(Teams 게이트웨이를 무시)로 직접 흐르거나 Teams 게이트웨이를 통과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-355">The media may flow directly from Teams and/or the Skype for Business client to the SBC (bypassing the Teams gateway) or traverse through the Teams gateway.</span></span> <span data-ttu-id="79615-356">트렁크를 무시하도록 트렁크를 Teams SBC와의 연결은 SBC가 ICE-Lite를 지원하는 ICE를 기반으로 하는 반면, Teams/비즈니스용 Skype 미디어 엔드포인트는 ICE 전체 양식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-356">The connectivity with the SBC, when the trunk is configured to bypass the Teams gateway, is based on ICE, where SBC supports ICE-Lite, while the Teams/Skype for Business media endpoint supports ICE Full Form.</span></span>

<span data-ttu-id="79615-357">[![Microsoft Teams 온라인 통화 흐름 그림 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span><span class="sxs-lookup"><span data-stu-id="79615-357">[![Microsoft Teams Online Call Flows Figure 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span></span>

<span data-ttu-id="79615-358">\*그림 17 - Teams 전화 시스템 토폴로지가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="79615-358">\*Figure 17 - Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="79615-359">참고:</span><span class="sxs-lookup"><span data-stu-id="79615-359">Note that:</span></span>

- <span data-ttu-id="79615-360">위의 다이어그램의 화살표 방향은 엔터프라이즈 경계의 연결에 영향을 주는 통신의 시작 방향을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-360">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="79615-361">미디어용 UDP의 경우 첫 번째 패킷이 역방향으로 흐를 수 있지만 다른 방향으로 패킷이 흐를 때까지 이러한 패킷이 차단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-361">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="79615-362">Teams 온라인과 나란히 배포되는 비즈니스용 Skype 클라이언트는 "Teams/SFB 사용자"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-362">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="79615-363">추가 흐름(온라인 토폴로지 위에 Teams):</span><span class="sxs-lookup"><span data-stu-id="79615-363">Additional flows (on top of Teams online topology):</span></span>

- <span data-ttu-id="79615-364">**Flow 4'** - Microsoft 365 Office 365 네트워크로의 흐름을 나타내며, 클라우드의 미디어 Teams SBC와의 연결을 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-364">**Flow 4'** - Represents a flow from Microsoft 365 or Office 365 to the customer network, used to establish a connection between the Teams media server in the cloud with the SBC on premises.</span></span>
- <span data-ttu-id="79615-365">**Flow 5B** – 우회 모드에서 직접 라우팅 SBC를 Teams 네트워크 내의 사용자 간에 미디어 흐름을 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-365">**Flow 5B** – Represents a media flow between the Teams user within the customer network with the Direct Routing SBC in bypass mode.</span></span>
- <span data-ttu-id="79615-366">**Flow 5C** – PSTN 헤어 펜 호출 우회 모드에서 직접 라우팅 SBC 간에 다른 직접 라우팅 SBC 간 미디어 흐름을 나타내고</span><span class="sxs-lookup"><span data-stu-id="79615-366">**Flow 5C** – Represents a media flow between the Direct Routing SBC to another Direct Routing SBC in a PSTN hairpin call bypass mode.</span></span>

<span data-ttu-id="79615-367">**직접 라우팅이 있는 내부 사용자(전송 릴레이로 Teams 미디어)**</span><span class="sxs-lookup"><span data-stu-id="79615-367">**Internal user with Direct Routing (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="79615-368">[![Microsoft Teams 온라인 통화 흐름 그림 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span><span class="sxs-lookup"><span data-stu-id="79615-368">[![Microsoft Teams Online Call Flows Figure 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span></span>

<span data-ttu-id="79615-369">*그림 18 - 직접 라우팅이 있는 내부 사용자(전송 릴레이로 Teams 미디어)*</span><span class="sxs-lookup"><span data-stu-id="79615-369">*Figure 18 - Internal user with Direct Routing (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="79615-370">참고:</span><span class="sxs-lookup"><span data-stu-id="79615-370">Note that:</span></span>

- <span data-ttu-id="79615-371">SBC에는 공용 IP 주소가 있어야 Microsoft 365 또는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="79615-371">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="79615-372">SBC에서 신호 및 미디어를 Microsoft 365 또는 Office 365 흐름 4 및/또는 흐름 4'를 사용하는 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-372">Signaling and media from the SBC to Microsoft 365 or Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="79615-373">고객 네트워크 내의 클라이언트에서 흐름 4를 Microsoft 365 Office 365 신호 및 미디어입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-373">Signaling and media from the client within the customer network to Microsoft 365 or Office 365 use flow 4.</span></span>

<span data-ttu-id="79615-374">**직접 라우팅이 있는 원격 사용자(미디어는 MP(미디어 서버)를 통해 라우팅)**</span><span class="sxs-lookup"><span data-stu-id="79615-374">**Remote user with Direct Routing (media is routed through a media server (MP))**</span></span>

<span data-ttu-id="79615-375">[![Microsoft Teams 온라인 통화 흐름 그림 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span><span class="sxs-lookup"><span data-stu-id="79615-375">[![Microsoft Teams Online Call Flows Figure 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span></span>

<span data-ttu-id="79615-376">*그림 19 - 직접 라우팅이 있는 원격 사용자(미디어는 MP(미디어 서버)를 통해 라우팅)*</span><span class="sxs-lookup"><span data-stu-id="79615-376">*Figure 19 - Remote user with Direct Routing (media is routed through a media server (MP))*</span></span>

<span data-ttu-id="79615-377">참고:</span><span class="sxs-lookup"><span data-stu-id="79615-377">Note that:</span></span>

- <span data-ttu-id="79615-378">SBC에는 공용 IP 주소가 있어야 Microsoft 365 또는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="79615-378">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="79615-379">SBC에서 신호 및 미디어를 Microsoft 365 또는 Office 365 흐름 4 및/또는 흐름 4'를 사용하는 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-379">Signaling and media from the SBC to Microsoft 365 or Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="79615-380">인터넷의 클라이언트에서 흐름 3을 Microsoft 365 Office 365 신호 및 미디어.</span><span class="sxs-lookup"><span data-stu-id="79615-380">Signaling and media from the client on the Internet to Microsoft 365 or Office 365 use flow 3.</span></span>

<span data-ttu-id="79615-381">**내부 사용자 직접 라우팅(미디어 우회)**</span><span class="sxs-lookup"><span data-stu-id="79615-381">**Internal user Direct Routing (media bypass)**</span></span>

<span data-ttu-id="79615-382">[![Microsoft Teams 온라인 통화 흐름 그림 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span><span class="sxs-lookup"><span data-stu-id="79615-382">[![Microsoft Teams Online Call Flows Figure 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span></span>

<span data-ttu-id="79615-383">*그림 20 - 내부 사용자 직접 라우팅(미디어 우회)*</span><span class="sxs-lookup"><span data-stu-id="79615-383">*Figure 20 - Internal user Direct Routing (media bypass)*</span></span>

<span data-ttu-id="79615-384">참고:</span><span class="sxs-lookup"><span data-stu-id="79615-384">Note that:</span></span>

- <span data-ttu-id="79615-385">SBC에는 공용 IP 주소가 있어야 Microsoft 365 또는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="79615-385">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="79615-386">SBC에서 Microsoft 365 또는 Office 365 흐름 4 및/또는 흐름 4'를 사용하는 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-386">Signaling from SBC to Microsoft 365 or Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="79615-387">고객 네트워크 내의 클라이언트에서 흐름 4를 Microsoft 365 Office 365 신호.</span><span class="sxs-lookup"><span data-stu-id="79615-387">Signaling from client within the customer network to Microsoft 365 or Office 365 use flow 4.</span></span>

- <span data-ttu-id="79615-388">고객 네트워크 내의 클라이언트에서 SBC로의 미디어는 흐름 5B를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-388">Media from client within the customer network to SBC within the customer network use flow 5B.</span></span>

<span data-ttu-id="79615-389">**직접 라우팅을 사용하여 원격 사용자(전송 릴레이로 Teams 미디어 우회)**</span><span class="sxs-lookup"><span data-stu-id="79615-389">**Remote user with Direct Routing (media bypass relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="79615-390">[![Microsoft Teams 온라인 통화 흐름 그림 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span><span class="sxs-lookup"><span data-stu-id="79615-390">[![Microsoft Teams Online Call Flows Figure 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span></span>

<span data-ttu-id="79615-391">*그림 21 - 직접 라우팅을 사용하여 원격 사용자(전송 릴레이로 Teams 릴레이된 미디어 우회)*</span><span class="sxs-lookup"><span data-stu-id="79615-391">*Figure 21 - Remote user with Direct Routing (media bypass relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="79615-392">참고:</span><span class="sxs-lookup"><span data-stu-id="79615-392">Note that:</span></span>

- <span data-ttu-id="79615-393">SBC에는 공용 IP 주소가 있어야 합니다. Microsoft 365 및 인터넷에서 라우팅할 Office 365 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-393">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365 and Internet.</span></span>

- <span data-ttu-id="79615-394">SBC에서 Microsoft 365 또는 Office 365 신호는 흐름 4 및/또는 흐름 4'를 사용하는 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-394">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="79615-395">인터넷의 클라이언트에서 흐름 3을 Microsoft 365 Office 365 신호.</span><span class="sxs-lookup"><span data-stu-id="79615-395">Signaling from the client on the Internet to Microsoft 365 or Office 365 uses flow 3.</span></span>

- <span data-ttu-id="79615-396">인터넷의 클라이언트에서 고객 네트워크 내의 SBC로의 미디어는 전송 릴레이를 통해 릴레이된 흐름 3과 4를 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-396">Media from the client on the Internet to the SBC within the customer network uses flows 3 and 4, relayed by Teams Transport Relay.</span></span>

<span data-ttu-id="79615-397">**원격 사용자 직접 라우팅(미디어 우회 직접)**</span><span class="sxs-lookup"><span data-stu-id="79615-397">**Remote user Direct Routing (media bypass direct)**</span></span>

<span data-ttu-id="79615-398">[![Microsoft Teams 온라인 통화 흐름 그림 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span><span class="sxs-lookup"><span data-stu-id="79615-398">[![Microsoft Teams Online Call Flows Figure 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span></span>

<span data-ttu-id="79615-399">*그림 22 - 원격 사용자 직접 라우팅(미디어 우회 직접)*</span><span class="sxs-lookup"><span data-stu-id="79615-399">*Figure 22 - Remote user Direct Routing (media bypass direct)*</span></span>

<span data-ttu-id="79615-400">참고:</span><span class="sxs-lookup"><span data-stu-id="79615-400">Note that:</span></span>

- <span data-ttu-id="79615-401">SBC에는 공용 IP 주소가 있어야 합니다. Microsoft 365 또는 인터넷에서 라우팅할 Office 365 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-401">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365 and the Internet.</span></span>

- <span data-ttu-id="79615-402">SBC에서 Microsoft 365 또는 Office 365 신호는 흐름 4 및/또는 흐름 4'를 사용하는 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-402">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="79615-403">인터넷의 클라이언트에서 흐름 3을 Microsoft 365 Office 365 신호.</span><span class="sxs-lookup"><span data-stu-id="79615-403">Signaling from the client on the Internet to Microsoft 365 or Office 365 uses flow 3.</span></span>

- <span data-ttu-id="79615-404">인터넷의 클라이언트에서 고객 네트워크 내의 SBC로의 미디어는 흐름 2를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-404">Media from the client on the Internet to the SBC within the customer network uses flow 2.</span></span>

<span data-ttu-id="79615-405">**직접 라우팅(미디어 우회) – PSTN 헤어 펜 호출(앞으로/전송으로 인해)**</span><span class="sxs-lookup"><span data-stu-id="79615-405">**Direct Routing (media bypass) – PSTN hairpin call (due to call forward/transfer)**</span></span>

<span data-ttu-id="79615-406">[![Microsoft Teams 온라인 통화 흐름 그림 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span><span class="sxs-lookup"><span data-stu-id="79615-406">[![Microsoft Teams Online Call Flows Figure 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span></span>

<span data-ttu-id="79615-407">*그림 23 - 직접 라우팅(미디어 우회) - PSTN 헤어 펜 호출(앞으로/전송으로 인해)*</span><span class="sxs-lookup"><span data-stu-id="79615-407">*Figure 23 - Direct Routing (media bypass) - PSTN hairpin call (due to call forward/transfer)*</span></span>

<span data-ttu-id="79615-408">참고:</span><span class="sxs-lookup"><span data-stu-id="79615-408">Note that:</span></span>

- <span data-ttu-id="79615-409">SBC에는 공용 IP 주소가 있어야 Microsoft 365 또는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="79615-409">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="79615-410">SBC에서 Microsoft 365 또는 Office 365 신호는 흐름 4 및/또는 흐름 4'를 사용하는 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-410">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="79615-411">호출이 PSTN에서 PSTN으로 머리를 털고 나면 클라이언트가 신호 및 미디어 루프에서 입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-411">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="79615-412">고객 네트워크 내의 SBC 인스턴스 A에서 고객 네트워크 내의 SBC 인스턴스 B(여기서 A 및 B가 동일한 인스턴스일 수 있는 경우)는 흐름 5C를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-412">Media from SBC instance A within the customer network to SBC instance B within the customer network (where, A and B can be the same instance) uses flow 5C.</span></span>

<span data-ttu-id="79615-413">**직접 라우팅(Microsoft 365 또는 Office 365 통해 미디어) – 두 테넌트에서 PSTN 헤어 펜 호출**</span><span class="sxs-lookup"><span data-stu-id="79615-413">**Direct Routing (media through Microsoft 365 or Office 365) – PSTN hairpin call across two tenants**</span></span>

<span data-ttu-id="79615-414">[![Microsoft Teams 온라인 통화 흐름 그림 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span><span class="sxs-lookup"><span data-stu-id="79615-414">[![Microsoft Teams Online Call Flows Figure 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span></span>

<span data-ttu-id="79615-415">*그림 24 - 직접 라우팅(Microsoft 365 또는 Office 365 통해 미디어) – 두 테넌트에서 PSTN 헤어 펜 호출*</span><span class="sxs-lookup"><span data-stu-id="79615-415">*Figure 24 - Direct Routing (media through Microsoft 365 or Office 365) – PSTN hairpin call across two tenants*</span></span>

<span data-ttu-id="79615-416">참고:</span><span class="sxs-lookup"><span data-stu-id="79615-416">Note that:</span></span>

- <span data-ttu-id="79615-417">SBC에는 공용 IP 주소가 있어야 Microsoft 365 또는 Office 365.</span><span class="sxs-lookup"><span data-stu-id="79615-417">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="79615-418">SBC에서 Microsoft 365 또는 Office 365 신호는 흐름 4 및/또는 흐름 4'를 사용하는 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-418">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="79615-419">호출이 PSTN에서 PSTN으로 머리를 털고 나면 클라이언트가 신호 및 미디어 루프에서 입니다.</span><span class="sxs-lookup"><span data-stu-id="79615-419">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="79615-420">고객 네트워크 X 내의 SBC 인스턴스 A에서 SBC 인스턴스 B로의 미디어는 Media Server 또는 Microsoft 365 Office 365 릴레이해야 하며 우회 모드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-420">Media from SBC instance A within the customer network X to SBC instance B must be relayed through the Microsoft 365 or Office 365 Media Server and can't use bypass mode.</span></span>

## <a name="teams-with-express-route-optimization"></a><span data-ttu-id="79615-421">Teams 최적화를 통해 사용</span><span class="sxs-lookup"><span data-stu-id="79615-421">Teams with Express Route optimization</span></span>

<span data-ttu-id="79615-422">[![Microsoft Teams 온라인 통화 흐름 그림 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span><span class="sxs-lookup"><span data-stu-id="79615-422">[![Microsoft Teams Online Call Flows Figure 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span></span>

<span data-ttu-id="79615-423">*그림 25 - Teams 최적화를 통해*</span><span class="sxs-lookup"><span data-stu-id="79615-423">*Figure 25 - Teams with Express Route optimization*</span></span>

<span data-ttu-id="79615-424">Express Route가 정당화되고 배포되는 경우 Teams 흐름을 흐름 4에서 흐름 1로, 흐름 4에서 흐름 1'로 다시 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-424">In the case that Express Route is justified and deployed, then Teams flows could be re-routed from flow 4 to flow 1 and from flow 4' to flow 1'.</span></span> <span data-ttu-id="79615-425">그러나 Teams 애플리케이션은 흐름 4 및 4'를 사용하여 인터넷을 통해 Microsoft 365 Office 365 다른 애플리케이션에 대한 하드 종속성이 있습니다. 따라서 이러한 흐름을 차단하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-425">However, the Teams application has a hard dependency on other Microsoft 365 or Office 365 flows over the Internet using flows 4 and 4'; hence these flows must not be blocked.</span></span>

<span data-ttu-id="79615-426">하이브리드 비즈니스용 Skype 트래픽은 외부 사용자와 통신하고 다른 테넌트와 페더테인하기 위해 Express Route가 아닌 인터넷으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="79615-426">Note that Skype for Business hybrid Edge traffic is routed to the Internet and not to Express Route to communicate with external users and federate with other tenants.</span></span>

<span data-ttu-id="79615-427">비대칭 흐름을 방지하려면 다시 라우팅을 양방향으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-427">To prevent asymmetrical flows, re-routing must be in both directions.</span></span> <span data-ttu-id="79615-428">즉, 고객 네트워크 내의 주소는 최적화에 따라 인터넷 또는 Express Route를 통해 라우팅할 수 있지만 둘 다를 통해 라우팅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79615-428">In other words, an address within the customer network is routable either through Internet or Express Route, based on optimization, but not through both.</span></span>


<span data-ttu-id="79615-429">**외부 사용자에 대한 고객 네트워크(전송 릴레이로 Teams):**</span><span class="sxs-lookup"><span data-stu-id="79615-429">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="79615-430">[![Microsoft Teams 온라인 통화 흐름 그림 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span><span class="sxs-lookup"><span data-stu-id="79615-430">[![Microsoft Teams Online Call Flows Figure 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span></span>

<span data-ttu-id="79615-431">*그림 26 - 외부 사용자에 대한 고객 네트워크(전송 릴레이로 Teams 미디어)*</span><span class="sxs-lookup"><span data-stu-id="79615-431">*Figure 26 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="79615-432">**고급 단계:**</span><span class="sxs-lookup"><span data-stu-id="79615-432">**High-Level Steps:**</span></span>

1. <span data-ttu-id="79615-433">Teams 고객 네트워크 내의 사용자는 flow2를 사용하여 DNS(URL 도메인 이름)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-433">Teams User within customer network resolves URL domain name (DNS) using flow2.</span></span>
1. <span data-ttu-id="79615-434">Teams 고객 네트워크 내의 사용자는 흐름 1을 사용하여 전송 Teams 미디어 릴레이 포트를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-434">Teams User within customer network allocates a media Relay port on Teams Transport Relay using flow 1.</span></span>
1. <span data-ttu-id="79615-435">Teams 고객 네트워크 내의 사용자는 흐름 1을 사용하여 ICE 후보와 함께 "초대"를 Microsoft 365 Office 365.</span><span class="sxs-lookup"><span data-stu-id="79615-435">Teams User within customer network sends "invite" with ICE candidates using flow 1 to Microsoft 365 or Office 365.</span></span>
1. <span data-ttu-id="79615-436">Microsoft 365 또는 Office 365 흐름 3을 사용하여 외부 Teams 사용자에게 알림을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-436">Microsoft 365 or Office 365 sends notification to external Teams user using flow 3.</span></span>
1. <span data-ttu-id="79615-437">Teams 외부 사용자가 흐름 3을 사용하여 전송 Teams 릴레이에 미디어 릴레이 포트를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-437">Teams external user allocates a media Relay port on Teams Transport Relay using flow 3.</span></span>
1. <span data-ttu-id="79615-438">Teams 외부 사용자는 흐름 3을 사용하여 ICE 후보와 "응답"을 보내며, 이 경우 Teams 1을 사용하여 사용자 A에게 Flow 합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-438">Teams external user sends "answer" with ICE candidates using flow 3, which is forwarded back to Teams user A using Flow 1.</span></span>
1. <span data-ttu-id="79615-439">Teams 사용자 A 및 Teams 사용자 B는 ICE 연결 테스트를 호출하고 전송 릴레이에서 릴레이되는 흐름 1과 3을 Teams 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-439">Teams User A and Teams User B invoke ICE connectivity tests and selects flows 1 and 3, which are relayed by Teams Transport Relay.</span></span>
1. <span data-ttu-id="79615-440">Teams 사용자는 흐름 1 및 3을 사용하여 Microsoft 365 Office 365 원격 분석 데이터를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="79615-440">Teams Users send telemetry to Microsoft 365 or Office 365 using flows 1 and 3.</span></span>

> [!NOTE]
> <span data-ttu-id="79615-441">Flow 4를 사용하도록 설정하여 흐름 4를 Teams 다른 마이크로 서비스에 대한 애플리케이션의 종속성 지원</span><span class="sxs-lookup"><span data-stu-id="79615-441">Flow 4 must be enabled to support dependencies of Teams application on other micro-services that mandates flow 4.</span></span>
