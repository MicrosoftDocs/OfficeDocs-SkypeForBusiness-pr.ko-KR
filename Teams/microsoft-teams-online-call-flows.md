---
title: Microsoft 팀 통화 흐름
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
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: 팀이 다양 한 토폴로지에서 Office 365 흐름을 사용 하는 방법에 대해 설명 합니다.
ms.openlocfilehash: 91be46f556419dfd1ba8c52a99b8f06a19c63542
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573415"
---
# <a name="microsoft-teams-call-flows"></a><span data-ttu-id="e01cc-103">Microsoft 팀 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="e01cc-103">Microsoft Teams call flows</span></span>

> [!Tip]
> <span data-ttu-id="e01cc-104">팀 네트워크를 활용 하는 방법과 최적의 네트워크 연결을 계획 하는 방법에 대 한 자세한 내용은 다음 세션을 시청 하세요. [팀 네트워크 계획](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="e01cc-104">Watch the following session to learn how Teams leverages your network and how to plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>

## <a name="overview"></a><span data-ttu-id="e01cc-105">개요</span><span class="sxs-lookup"><span data-stu-id="e01cc-105">Overview</span></span>
<span data-ttu-id="e01cc-106">이 문서에서는 팀이 다양 한 토폴로지에서 Office 365 호출 흐름을 사용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-106">This article describes how Teams uses Office 365 call flows in various topologies.</span></span> <span data-ttu-id="e01cc-107">또한 피어 투 피어 미디어 통신에 사용 되는 고유한 팀 흐름에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-107">In addition, it describes unique Teams flows that are used for peer-to-peer media communication.</span></span> <span data-ttu-id="e01cc-108">이 문서에서는 이러한 흐름, 해당 용도, 그리고 네트워크의 원본 및 종료에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-108">The document describes these flows, their purpose, and their origin and termination on the network.</span></span> <span data-ttu-id="e01cc-109">이 문서의 목적을 위해 다음과 같은 사항을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-109">For purposes of this article, assume the following:</span></span>

- <span data-ttu-id="e01cc-110">흐름 X는 온-프레미스 Office 365 클라이언트에서 클라우드의 Office 365 서비스와 통신 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-110">Flow X is used by the on-premises Office 365 client to communicate with the Office 365 service in the cloud.</span></span> <span data-ttu-id="e01cc-111">이는 고객 네트워크에서 발생 하며 Office 365의 끝점으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-111">It originates from the customer network, and it terminates as an endpoint in Office 365.</span></span>

- <span data-ttu-id="e01cc-112">흐름 Y는 온-프레미스 Office 365 클라이언트에서 Office 365에 종속 된 인터넷 서비스와 통신 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-112">Flow Y is used by the on-premises Office 365 client to communicate with a service on the Internet that Office 365 has a dependency on.</span></span> <span data-ttu-id="e01cc-113">이는 고객 네트워크에서 발생 하며 인터넷의 끝점으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-113">It originates from the customer network, and it terminates as an endpoint on the Internet.</span></span>

<span data-ttu-id="e01cc-114">이 문서에는 다음 섹션이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-114">The article contains the following sections:</span></span>

- <span data-ttu-id="e01cc-115">**백그라운드** -Office 365 흐름이 통과 하는 네트워크, 트래픽 종류, 고객 네트워크에서 Office 365 서비스 끝점으로의 연결 지침, 타사 구성 요소와의 상호 운용성 등의 배경 정보를 제공 합니다. 팀에서 미디어 흐름을 선택 하는 데 사용 하는 원칙입니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-115">**Background** - Provides background information, such as networks that Office 365 flows may traverse, type of traffic, connectivity guidance from the customer network to Office 365 service endpoints, interoperability with third-party components, and principles that are used by Teams to select media flows.</span></span>

- <span data-ttu-id="e01cc-116">**다양 한 토폴로지의 통화 흐름** -다양 한 토폴로지에서의 통화 흐름 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-116">**Call flows in various topologies** - Illustrates the use of call flows in various topologies.</span></span> <span data-ttu-id="e01cc-117">각 토폴로지에 대해 섹션은 지원 되는 모든 흐름을 열거 하 고 여러 사용 사례를 통해 이러한 흐름을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-117">For each topology, the section enumerates all supported flows and illustrates how these flows are used via several use cases.</span></span> <span data-ttu-id="e01cc-118">각 사용 사례에 대해 흐름 다이어그램을 통해 흐름의 순서 및 선택 영역을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-118">For each use case, it describes the sequence and selection of flows via a flow diagram.</span></span> 

- <span data-ttu-id="e01cc-119">**Express 경로 최적화를 사용** 하는 팀-빠른 경로가 최적화를 위해 배포 될 때 이러한 흐름을 사용 하는 방법을 설명 합니다 (간단한 토폴로지를 통해 설명).</span><span class="sxs-lookup"><span data-stu-id="e01cc-119">**Teams with Express Route optimization** - Describes how these flows are used when Express Route is deployed for optimization, illustrated via a simple topology.</span></span>

## <a name="background"></a><span data-ttu-id="e01cc-120">배경</span><span class="sxs-lookup"><span data-stu-id="e01cc-120">Background</span></span>
### <a name="network-segments"></a><span data-ttu-id="e01cc-121">네트워크 세그먼트</span><span class="sxs-lookup"><span data-stu-id="e01cc-121">Network segments</span></span>
<span data-ttu-id="e01cc-122">**고객 네트워크**: 사용자가 제어 하 고 관리 하는 네트워크 세그먼트입니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-122">**Customer network**: This is the network segment that you control and manage.</span></span> <span data-ttu-id="e01cc-123">여기에는 유선 또는 무선, 사무실 건물, 온-프레미스 데이터 센터, 인터넷 공급자, Express 경로 또는 기타 사설 피어 링에 대 한 연결 등 고객 사무실 내의 모든 고객 연결이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-123">This includes all customer connections within customer offices, whether wired or wireless, between office buildings, to on-premises datacenters, and your connections to Internet providers, Express Route, or any other private peering.</span></span> 

<span data-ttu-id="e01cc-124">일반적으로 고객 네트워크에는 방화벽 및/또는 프록시 서버와의 여러 네트워크 perimeters 있으므로 조직의 보안 정책을 적용 하 고 설정 하 고 구성한 특정 네트워크 트래픽만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-124">Typically, a customer network has several network perimeters with firewalls and/or proxy servers, which enforce your organization's security policies, and that only allow certain network traffic that you have set up and configured.</span></span> <span data-ttu-id="e01cc-125">이 네트워크를 관리 하기 때문에 네트워크의 성능을 직접 제어 하는 것이 좋으며 네트워크의 사이트 내에서 그리고 네트워크에서 Office 365 네트워크로의 성능에 대 한 유효성을 검사 하기 위해 네트워크 평가를 완료 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-125">Because you manage this network, you have direct control over the performance of the network, and it is highly recommended that you complete network assessments to validate performance both within sites in your network and from your network to the Office 365 network.</span></span> 

<span data-ttu-id="e01cc-126">**인터넷**: 고객 네트워크 외부에서 Office 365에 연결 하는 사용자가 사용할 전체 네트워크의 일부인 네트워크 세그먼트입니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-126">**Internet**: This is the network segment that is part of your overall network that will be used by users who are connecting to Office 365 from outside of the customer network.</span></span> <span data-ttu-id="e01cc-127">또한 일부는 고객 네트워크에서 Office 365에 이르기까지 일부 소통에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-127">It is also used by some traffic from the customer network to Office 365.</span></span> 

<span data-ttu-id="e01cc-128">**방문한/게스트 개인 네트워크**:이 네트워크 세그먼트는 사용자 및/또는 게스트가 방문할 수 있는 고객 네트워크 외부에 있지만, 공개 인터넷에 있지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-128">**Visited/Guest private network**: This is the network segment outside your customer network, but not in the public Internet, that your users and/or their guests may visit.</span></span> <span data-ttu-id="e01cc-129">예를 들어 홈 개인 네트워크 또는 팀 서비스와 상호 작용 하는 사용자 및/또는 고객이 상주할 수 있는 팀을 배포 하지 않는 엔터프라이즈 개인 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-129">For example, home private network or an Enterprise private network, that does not deploy Teams, where your users and/or their customers that interact with Teams services may reside.</span></span>

><span data-ttu-id="e01cc-130">**참고**: Office 365에 대 한 연결도 다음 네트워크에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-130">**Note**: Connectivity to Office 365 is also applicable to these networks.</span></span>

<span data-ttu-id="e01cc-131">**Office 365**: office 365 서비스를 지 원하는 네트워크 세그먼트입니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-131">**Office 365**: This is the network segment that supports Office 365 services.</span></span> <span data-ttu-id="e01cc-132">대부분의 지역에서 고객 네트워크에 근접 한 가장자리를 사용 하 여 전세계에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-132">It is distributed worldwide with edges in proximity to the customer network in most locations.</span></span> <span data-ttu-id="e01cc-133">이 문서에 언급 된 함수에는 전송 릴레이, 회의 서버, 미디어 프로세서 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-133">Functions mentioned in this document include Transport Relay, conferencing server, and Media Processor.</span></span> 

<span data-ttu-id="e01cc-134">**Express 경로 (선택 사항)**: 사용자가 Office 365 네트워크에 대 한 전용 개인 연결을 제공 하는 전체 네트워크의 일부인 네트워크 세그먼트입니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-134">**Express Route (optional)**: This is the network segment that is part of your overall network that will give you a dedicated, private connection to the Office 365 network.</span></span>

### <a name="types-of-traffic"></a><span data-ttu-id="e01cc-135">트래픽 종류</span><span class="sxs-lookup"><span data-stu-id="e01cc-135">Types of traffic</span></span>

<span data-ttu-id="e01cc-136">**실시간 미디어**: RTP (실시간 전송 프로토콜) 내에서 오디오, 비디오 및 화면 공유 작업을 지 원하는 데이터 캡슐화</span><span class="sxs-lookup"><span data-stu-id="e01cc-136">**Real-time media**: Data encapsulated within RTP (Real-time Transport Protocol) that supports audio, video and screen sharing workloads.</span></span> <span data-ttu-id="e01cc-137">일반적으로 미디어 트래픽은 매우 많은 대기 시간을 차지 하므로,이 트래픽을 최대한의 직접적인 경로를 사용 하 고, 품질 관점에서 대화형 실시간 미디어에 가장 적합 한 전송 계층 프로토콜로 UDP와 TCP를 함께 사용할 수 있도록 해야 합니다. .</span><span class="sxs-lookup"><span data-stu-id="e01cc-137">In general, media traffic is highly latency sensitive, so you would want this traffic to take the most direct path possible, and to use UDP versus TCP as the transport layer protocol, which is the best transport for interactive real time media from a quality perspective.</span></span> <span data-ttu-id="e01cc-138">(참고: 미디어는 마지막 수단으로 TCP/IP를 사용 하 고 HTTP 프로토콜 내 에서도 터널링 될 수 있지만 잘못 된 품질에 영향을 미치지 않습니다.) RTP 흐름은 페이로드만 암호화 되는 SRTP를 통해 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-138">(Note: As a last resort, media can use TCP/IP and also be tunneled within the HTTP protocol, but it is not recommended due to bad quality implications.) RTP flow is secured via SRTP, in which only the payload is encrypted.</span></span>

<span data-ttu-id="e01cc-139">**신호**: 클라이언트와 서버 간의 통신 링크 또는 활동을 제어 하는 데 사용 되는 다른 클라이언트 (예를 들어 통화가 시작 되는 경우) 및 인스턴트 메시지를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-139">**Signaling**: The communication link between the client and server, or other clients that are used to control activities (for example, when a call is initiated), and deliver instant messages.</span></span> <span data-ttu-id="e01cc-140">대부분의 신호 트래픽은 HTTPS 기반 REST 인터페이스를 사용 하지만 (예: Office 365와 세션 경계 컨트롤러 간 연결) SIP 프로토콜을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-140">Most signaling traffic uses the HTTPS-based REST interfaces, though in some scenarios (for example, connection between Office 365 and a Session Border Controller) it uses SIP protocol.</span></span> <span data-ttu-id="e01cc-141">이 소통량은 대기 시간에 대 한 중요 한 영향을 받지만, 끝점 간의 대기 시간이 몇 초를 초과 하는 경우 서비스 중단 또는 호출 시간 초과가 발생할 수 있다는 점을 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-141">It's important to understand that this traffic is much less sensitive to latency but may cause service outages or call timeouts if latency between the endpoints exceeds several seconds.</span></span> 

### <a name="connectivity-to-office-365"></a><span data-ttu-id="e01cc-142">Office 365에 대 한 연결</span><span class="sxs-lookup"><span data-stu-id="e01cc-142">Connectivity to Office 365</span></span>

<span data-ttu-id="e01cc-143">팀이 [인터넷에 연결](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10)되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-143">Teams requires [connectivity to the Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10).</span></span> <span data-ttu-id="e01cc-144">[Office 365 url 및 ip 주소 범위](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)에 팀 끝점 URL 및 ip 주소 범위가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-144">Teams endpoint URLs and IP address ranges are listed in [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="e01cc-145">(참고: TCP 포트 80 및 443에 대 한 연결이 열려 있고 UDP 포트 3478 ~ 3481이 필요 합니다.) 또한, 팀이 인터넷에 연결 되어 있어야 하는 비즈니스용 Skype Online에 종속 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-145">(Note: Open connectivity to TCP ports 80 and 443, and to UDP ports 3478 through 3481 is required.) Furthermore, Teams has a dependency on Skype for Business Online, which must also be connected to the Internet.</span></span>

<span data-ttu-id="e01cc-146">팀 미디어 흐름 연결은 표준 IETF ICE (대화형 연결 설정) 절차를 통해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-146">Teams media flows connectivity is implemented via standard IETF ICE (Interactive Connectivity Establishment) procedures.</span></span>

### <a name="interoperability-restrictions"></a><span data-ttu-id="e01cc-147">상호 운용성 제한</span><span class="sxs-lookup"><span data-stu-id="e01cc-147">Interoperability restrictions</span></span>
<span data-ttu-id="e01cc-148">**제 3 자 미디어 릴레이**: 팀 미디어 흐름 (즉, 미디어 끝점 중 하나가 팀) 인 경우 팀 또는 비즈니스용 Skype 기본 미디어 릴레이만 통과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-148">**Third party media relays**: A Teams media flow (that is, one of the media endpoints is Teams) may traverse only Teams or Skype for Business native media relays.</span></span> <span data-ttu-id="e01cc-149">타사 미디어 릴레이와의 상호 운용성은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-149">Interoperability with a third party media relay is not supported.</span></span> <span data-ttu-id="e01cc-150">(참고: PSTN을 사용 하는 경계의 타사 SBC는 RTP/RTCP 스트림을 종료 하 고 SRTP를 통해 보호 되며 다음 홉으로 릴레이 하지 않아야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="e01cc-150">(Note: A third party SBC on the boundary with PSTN must terminate RTP/RTCP stream, secured via SRTP, and not relay it to the next hop.)</span></span>

<span data-ttu-id="e01cc-151">**제 3 자 SIP 프록시 서버**: 타사 SBC 및/또는 게이트웨이에서 SIP 대화를 통해 신호를 보내는 팀이 팀 또는 비즈니스용 SKYPE 기본 SIP 프록시를 통과 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-151">**Third party SIP proxy servers**: A Teams signaling SIP dialog with a third party SBC and/or gateway may traverse Teams or Skype for Business native SIP proxies.</span></span> <span data-ttu-id="e01cc-152">타사 SIP 프록시와의 상호 운용성은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-152">Interoperability with a third party SIP proxy is not supported.</span></span>

<span data-ttu-id="e01cc-153">타사 **B2BUA (즉, SBC)**: PSTN에서/로의 팀 미디어 흐름은 제 3 자 SBC에 의해 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-153">**Third party B2BUA (that is, SBC)**: A Teams media flow from/to the PSTN is terminated by a third party SBC.</span></span> <span data-ttu-id="e01cc-154">그러나 팀 네트워크 내의 타사 SBC와의 상호 운용성 (즉, 타사 SBC mediates 두 팀/비즈니스용 Skype 끝점)은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-154">However, interoperability with a third party SBC within the Teams network (that is, a third party SBC mediates two Teams/Skype for Business endpoints) is not supported.</span></span>

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a><span data-ttu-id="e01cc-155">Microsoft 팀에 권장 되지 않는 기술</span><span class="sxs-lookup"><span data-stu-id="e01cc-155">Technologies that are not recommended with Microsoft Teams</span></span>

<span data-ttu-id="e01cc-156">**VPN 네트워크**: 미디어 트래픽 (즉, 흐름 2)에는 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-156">**VPN network**: It is not recommended for media traffic (that is, flow 2').</span></span> <span data-ttu-id="e01cc-157">VPN 클라이언트는에 https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/지정 된 대로 vpn 분할을 사용 하 고 외부 이외의 모든 사용자와 같은 미디어 트래픽을 라우팅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-157">The VPN client should use split VPN and route media traffic like any external non-VPN user, as specified in https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/.</span></span>

><span data-ttu-id="e01cc-158">**참고**: 제목은 Lync 이지만 팀에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-158">**Note**: Although the title is Lync, it is applicable to Teams as well.</span></span>

<span data-ttu-id="e01cc-159">**패킷 shapers**: 모든 종류의 패킷 snippers, 패킷 검사 또는 패킷 shaper 장치는 권장 되지 않으며 품질을 대폭 저하 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-159">**Packet shapers**: Any kind of packet snippers, packet inspection, or packet shaper devices are not recommended and may degrade quality significantly.</span></span> 

### <a name="principles"></a><span data-ttu-id="e01cc-160">원칙은</span><span class="sxs-lookup"><span data-stu-id="e01cc-160">Principles</span></span>
<span data-ttu-id="e01cc-161">Microsoft 팀의 통화 흐름을 이해 하는 데 도움이 되는 네 가지 일반적인 원칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-161">There are four general principles that help you understand call flows for Microsoft Teams:</span></span>
 
1.  <span data-ttu-id="e01cc-162">Microsoft 팀 회의는 첫 번째 참가자가 참여 한 동일한 지역에서 Office 365을 통해 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-162">A Microsoft Teams conference is hosted by Office 365 in the same region where the first participant joined.</span></span> <span data-ttu-id="e01cc-163">(참고: 일부 토폴로지에서는이 규칙에 대 한 예외가 발생 하는 경우이 문서에서 설명 하 고 적절 한 호출 흐름에 의해 제시 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="e01cc-163">(Note: If there will be exceptions to this rule in some topologies, then they will be described in this document, and illustrated by an appropriate call flow.)</span></span>

2.  <span data-ttu-id="e01cc-164">Office 365의 팀 미디어 끝점은 미디어 처리 요구 사항에 기반 하 여 통화 유형을 기반으로 하지 않는 경우에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-164">A Teams media endpoint in Office 365 is used based on media processing needs and not based on call type.</span></span> <span data-ttu-id="e01cc-165">예를 들어 지점 간 통화는 클라우드에서 미디어 끝점을 사용 하 여 레코딩 및/또는 녹음/녹화에 대 한 미디어를 처리 하는 반면, 참가자 두 명의 회의가 클라우드의 미디어 끝점을 사용 하지 못할 수 있습니다. 그러나 대부분의 컨퍼런스는 회의가 호스팅되는 위치에 할당 된 혼합 및 라우팅 목적으로 미디어 끝점을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-165">(For example, a point-to-point call may use a media endpoint in the cloud to process media for transcription and/or recording, while a conference with two participants may not use any media endpoint in the cloud.) However, most conferences will use a media endpoint for mixing and routing purposes, allocated where the conference is hosted.</span></span> <span data-ttu-id="e01cc-166">클라이언트에서 미디어 끝점으로 전송 된 미디어 트래픽은 직접 라우팅하거나 고객 네트워크 방화벽 제한으로 인해 필요한 경우 Office 365에서 전송 릴레이를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-166">The media traffic sent from a client to the media endpoint may be routed directly or use a Transport Relay in Office 365 if required due to customer network firewall restrictions.</span></span> 

3.  <span data-ttu-id="e01cc-167">피어 투 피어 통화에 대 한 미디어 트래픽은 호출이 클라우드에서 미디어 끝점을 요구 하지 않는다고 가정 하 여 사용할 수 있는 가장 직접적인 경로를 사용 합니다 (위 #2 참조).</span><span class="sxs-lookup"><span data-stu-id="e01cc-167">Media traffic for peer-to-peer calls take the most direct route that is available, assuming that the call doesn't mandate a media endpoint in the cloud (see #2 above).</span></span> <span data-ttu-id="e01cc-168">기본 설정 경로는 원격 피어 (클라이언트)로 직접 이동 하지만 해당 경로를 사용할 수 없는 경우 하나 이상의 전송 중계에서 트래픽을 릴레이 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-168">The preferred route is direct to the remote peer (client), but if that route isn't available, then one or more Transport Relays will relay traffic.</span></span> <span data-ttu-id="e01cc-169">미디어 트래픽은 미디어 품질에 영향을 주므로 패킷 shapers, VPN 서버 등의 서버에는이를 가로 방향으로 설정 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-169">It is recommended that media traffic shall not transverse servers such as packet shapers, VPN servers, and so on, since this will impact the media quality.</span></span>

4.  <span data-ttu-id="e01cc-170">신호 소통량은 항상 사용자에 게 가장 가까운 서버로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-170">Signaling traffic always goes to the closest server to the user.</span></span> 

<span data-ttu-id="e01cc-171">선택한 미디어 경로의 세부 정보에 대 한 자세한 내용은을 참조 https://www.youtube.com/watch?v=1tmHMIlAQdo하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-171">To learn more about the details on the media path that is chosen, see https://www.youtube.com/watch?v=1tmHMIlAQdo.</span></span>

## <a name="call-flows-in-various-topologies"></a><span data-ttu-id="e01cc-172">다양 한 토폴로지의 통화 흐름</span><span class="sxs-lookup"><span data-stu-id="e01cc-172">Call flows in various topologies</span></span>
### <a name="teams-topology"></a><span data-ttu-id="e01cc-173">팀 토폴로지</span><span class="sxs-lookup"><span data-stu-id="e01cc-173">Teams topology</span></span>
<span data-ttu-id="e01cc-174">이 토폴로지는 비즈니스용 Skype Server 또는 전화 시스템 다이렉트 라우팅과 같이 온-프레미스 배포를 사용 하지 않고 클라우드에서 팀 서비스를 활용 하는 고객에 게 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-174">This topology is used by customers that leverage Teams services from the cloud without any on-premises deployment, such as Skype for Business Server or Phone System Direct Routing.</span></span> <span data-ttu-id="e01cc-175">또한 Office 365에 대 한 인터페이스는 Azure Express 경로가 없는 인터넷을 통해 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-175">In addition, the interface to Office 365 is done via the Internet without Azure Express Route.</span></span> 

<span data-ttu-id="e01cc-176">[![Microsoft 팀 온라인 통화 흐름 그림 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-176">[![Microsoft Teams Online Call Flows Figure 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span></span>

<span data-ttu-id="e01cc-177">*그림 1-팀 토폴로지*</span><span class="sxs-lookup"><span data-stu-id="e01cc-177">*Figure 1 - Teams topology*</span></span>

<span data-ttu-id="e01cc-178">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-178">Note that:</span></span>

- <span data-ttu-id="e01cc-179">위의 다이어그램에 있는 화살표의 방향은 엔터프라이즈 perimeters 연결에 영향을 주는 통신의 시작 방향을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-179">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="e01cc-180">미디어에 대 한 UDP의 경우 첫 번째 패킷이 역방향으로 흐를 수 있지만 다른 방향의 패킷이 흐를 때까지 이러한 패킷이 차단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-180">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>
- <span data-ttu-id="e01cc-181">팀은 비즈니스용 Skype Online과 나란히 배포 되므로 클라이언트는 "팀/SFB 사용자"로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-181">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="e01cc-182">나중에이 문서에서 다음 선택적 토폴로지에 대 한 자세한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-182">You can find more information on the following optional topologies later in the article:</span></span>

- <span data-ttu-id="e01cc-183">비즈니스용 Skype 온-프레미스 배포는 **팀 하이브리드 토폴로지에서**설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-183">Skype for Business on-premises deployment is described in **Teams  hybrid topology**.</span></span>
- <span data-ttu-id="e01cc-184">휴대폰 시스템 다이렉트 라우팅 (PSTN 연결의 경우)은 **다이렉트 라우팅 토폴로지가 있는 팀**에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-184">Phone System Direct Routing (for PSTN connectivity) is described in **Teams with Direct Routing topology**.</span></span>
- <span data-ttu-id="e01cc-185">Express 경로는 **Express 경로 최적화를 사용 하 여 팀**에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-185">Express Route is described in  **Teams with Express Route optimization**.</span></span>

<span data-ttu-id="e01cc-186">**흐름 설명**:</span><span class="sxs-lookup"><span data-stu-id="e01cc-186">**Flow descriptions**:</span></span>
- <span data-ttu-id="e01cc-187">**흐름 2** – 사용자의 팀 경험의 일부로 고객 네트워크의 사용자가 인터넷으로 시작 하는 흐름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-187">**Flow 2** – Represents a flow initiated by a user on the customer network to the Internet as a part of the user's Teams experience.</span></span> <span data-ttu-id="e01cc-188">이러한 흐름의 예로는 DNS 및 피어 투 피어 미디어가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-188">Examples of these flows are DNS and peer-to-peer media.</span></span>
- <span data-ttu-id="e01cc-189">**흐름 2 '** – 고객 네트워크에 대 한 VPN을 사용 하 여 원격 모바일 팀 사용자가 시작한 흐름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-189">**Flow 2'** – Represents a flow initiated by a remote mobile Teams user, with VPN to the customer network.</span></span> 
- <span data-ttu-id="e01cc-190">**흐름 3** – 원격 모바일 팀 사용자가 Office 365/팀 끝점으로 시작 하는 흐름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-190">**Flow 3** – Represents a flow initiated by a remote mobile Teams user to Office 365/Teams endpoints.</span></span> 
- <span data-ttu-id="e01cc-191">**흐름 4** – 고객 네트워크의 사용자가 Office 365/팀 끝점으로 시작 하는 흐름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-191">**Flow 4** – Represents a flow initiated by a user on the customer network to Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="e01cc-192">**흐름 5** – 고객 네트워크 내의 팀 사용자와 다른 팀 또는 비즈니스용 Skype 사용자 간 피어 투 피어 미디어 흐름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-192">**Flow 5** – Represents a peer-to-peer media flow between a Teams user and another Teams or Skype for Business user within the customer network.</span></span>
- <span data-ttu-id="e01cc-193">**흐름 6** – 원격 모바일 팀 사용자와 다른 원격 모바일 팀과 인터넷을 통한 비즈니스용 Skype 사용자 간의 피어 투 피어 미디어 흐름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-193">**Flow 6** – Represents a peer-to-peer media flow between a remote mobile Teams user and another remote mobile Teams or Skype for Business user over the Internet.</span></span>

#### <a name="use-case-one-to-one"></a><span data-ttu-id="e01cc-194">사용 사례: 일대일</span><span class="sxs-lookup"><span data-stu-id="e01cc-194">Use case: One-to-one</span></span>
<span data-ttu-id="e01cc-195">일대일 통화는 호출자가 IP 주소/포트 (즉, 릴레이에 표시 되는 클라이언트의 공용 IP 주소) 후보를 포함 하는 여러 후보를 사용 하는 모델을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-195">One-to-one calls use a common model in which the caller will obtain a set of candidates consisting of IP addresses/ports--including local, relay, and reflexive (public IP address of client as seen by the relay) candidates.</span></span> <span data-ttu-id="e01cc-196">발신자는이 후보를 호출한 파티에 보냅니다. 또한 호출 당사자는 유사한 후보 집합을 가져와 호출자에 게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-196">The caller sends these candidates to the called party; the called party also obtains a similar set of candidates and sends them to the caller.</span></span> <span data-ttu-id="e01cc-197">STUN 연결 검사 메시지를 사용 하 여 어떤 호출자/호출 된 파티 미디어 경로가 작동 하 고 가장 적합 한 작업 경로가 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-197">STUN connectivity check messages are used to find which caller/called party media paths work, and the best working path is selected.</span></span> <span data-ttu-id="e01cc-198">미디어 (즉, SRTP를 통해 보안 된 RTP/RTCP packets)는 선택한 후보 쌍을 사용 하 여 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-198">Media (that is, RTP/RTCP packets secured via SRTP) are then sent using the selected candidate pair.</span></span> <span data-ttu-id="e01cc-199">전송 릴레이가 Office 365의 일부로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-199">The Transport relay is deployed as part of Office 365.</span></span>

<span data-ttu-id="e01cc-200">로컬 IP 주소/포트 후보자 또는 재귀 후보의 연결 되 면 클라이언트 (또는 NAT)를 통해 미디어에 대 한 직접 경로를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-200">If the local IP address/port candidates or the reflexive candidates have connectivity, then the direct path between the clients (or via a NAT) will be selected for media.</span></span> <span data-ttu-id="e01cc-201">클라이언트가 고객 네트워크에 있는 경우 직접 경로를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-201">If the clients are both on the customer network, then the direct path should be selected.</span></span> <span data-ttu-id="e01cc-202">이를 위해서는 고객 네트워크 내에서 직접 UDP 연결이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-202">This requires direct UDP connectivity within the customer network.</span></span> <span data-ttu-id="e01cc-203">클라이언트가 nomadic 클라우드 사용자 이면 NAT/방화벽에 따라 미디어에서 직접 연결을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-203">If the clients are both nomadic cloud users, then depending on the NAT/firewall, media may use direct connectivity.</span></span>

<span data-ttu-id="e01cc-204">클라이언트가 고객 네트워크 내부에 있고 한 클라이언트가 외부 (예: 모바일 클라우드 사용자) 인 경우에는 로컬 또는 재귀 후보자 간의 직접 연결이 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-204">If one client is internal on the customer network and one client is external (for example, a mobile cloud user), then it is unlikely that direct connectivity between the local or reflexive candidates is working.</span></span> <span data-ttu-id="e01cc-205">이 경우, 예를 들어 내부 클라이언트가 Office 365의 전송 릴레이에서 릴레이 후보를 획득 한 경우, 외부 클라이언트는 STUN/RTP/RTCP packets를 다음에 보낼 수 있어야 하는 경우와 같이 두 클라이언트의 전송 릴레이 후보 중 하나를 사용 하는 옵션이 있습니다. 전송 릴레이).</span><span class="sxs-lookup"><span data-stu-id="e01cc-205">In this case, an option is to use one of the Transport Relay candidates from either client (for example, the internal client obtained a relay candidate from the Transport relay in Office 365; the external client needs to be able to send STUN/RTP/RTCP packets to the transport relay).</span></span> <span data-ttu-id="e01cc-206">또 다른 옵션은 내부 클라이언트가 모바일 클라우드 클라이언트에서 받은 릴레이 후보로 전송 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-206">Another option is the internal client sends to the relay candidate obtained by the mobile cloud client.</span></span> <span data-ttu-id="e01cc-207">미디어에 대 한 UDP 연결을 적극 권장 하지만, TCP가 지원 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-207">Note that, although UDP connectivity for media is highly recommended, TCP is supported.</span></span>

<span data-ttu-id="e01cc-208">**상위 수준 단계**:</span><span class="sxs-lookup"><span data-stu-id="e01cc-208">**High-level steps**:</span></span>
1. <span data-ttu-id="e01cc-209">팀 사용자 A flow2를 통해 DNS (URL 도메인 이름)를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-209">Teams User A resolves URL domain name (DNS) via flow2</span></span>
2. <span data-ttu-id="e01cc-210">팀 사용자 A가 흐름 4를 통해 팀 전송 릴레이의 미디어 릴레이 포트를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-210">Teams User A allocates a media Relay port on Teams Transport Relay via flow 4</span></span>
3. <span data-ttu-id="e01cc-211">팀 사용자 A가 흐름 4를 통해 Office 365으로 "초대"를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-211">Teams User A sends "invite" with ICE candidates via flow 4 to Office 365</span></span>
4. <span data-ttu-id="e01cc-212">Office 365에서 흐름 4를 통해 팀 사용자 B에 게 알림 전송</span><span class="sxs-lookup"><span data-stu-id="e01cc-212">Office 365 sends notification to Teams User B via flow 4</span></span>
5. <span data-ttu-id="e01cc-213">팀 사용자 B가 흐름 4를 통해 팀 전송 릴레이의 미디어 릴레이 포트를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-213">Teams User B allocates a media Relay port on Teams Transport Relay via flow 4</span></span>
6. <span data-ttu-id="e01cc-214">팀 사용자 B는 흐름 4를 통해 "answer" 라는 발송 후보로 전송 되며 흐름 4를 통해 다시 팀 사용자 A로 착신 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-214">Teams User B sends "answer" with ICE candidates via flow 4, which is forwarded back to Teams User A via Flow 4</span></span>
7. <span data-ttu-id="e01cc-215">팀 사용자 A 및 팀 사용자 B가 ICE connectivity 테스트를 호출 하 고 가장 적합 한 미디어 경로가 선택 되어 있습니다 (다양 한 사용 사례를 보려면 아래 다이어그램 참조).</span><span class="sxs-lookup"><span data-stu-id="e01cc-215">Teams User A and Teams User B invoke ICE connectivity tests and the best available media path is selected (see diagrams below for various use cases)</span></span>
8. <span data-ttu-id="e01cc-216">팀 사용자가 흐름 4를 통해 Office 365로 원격 분석을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-216">Teams Users send telemetry to Office 365 via flow 4</span></span>

<span data-ttu-id="e01cc-217">**고객 네트워크 내:**</span><span class="sxs-lookup"><span data-stu-id="e01cc-217">**Within customer network:**</span></span>

<span data-ttu-id="e01cc-218">[![Microsoft 팀 온라인 통화 흐름 그림 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-218">[![Microsoft Teams Online Call Flows Figure 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span></span>

<span data-ttu-id="e01cc-219">*그림 2-고객 네트워크 내*</span><span class="sxs-lookup"><span data-stu-id="e01cc-219">*Figure 2 - Within customer network*</span></span>
 
<span data-ttu-id="e01cc-220">7 단계에서 피어 투 피어 미디어 흐름 5가 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-220">In step 7, peer-to-peer media flow 5 is selected.</span></span>
 
<span data-ttu-id="e01cc-221">미디어는 양방향입니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-221">Media is bidirectional.</span></span> <span data-ttu-id="e01cc-222">흐름 5의 방향은이 문서의 모든 흐름과 일관성을 유지 하면서 연결 관점에서 통신을 시작 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-222">The direction of flow 5 indicates that one side initiates the communication from a connectivity perspective, consistent with all the flows in this document.</span></span> <span data-ttu-id="e01cc-223">이 경우 두 종점이 모두 고객 네트워크 내에 있기 때문에 사용 되는 방향은 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-223">In this case, it doesn't matter which direction is used because both endpoints are within the customer network.</span></span>

<span data-ttu-id="e01cc-224">**외부 사용자에 대 한 고객 네트워크 (팀에서 전송 릴레이가 전달 하는 미디어 릴레이):**</span><span class="sxs-lookup"><span data-stu-id="e01cc-224">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="e01cc-225">[![Microsoft 팀 온라인 통화 흐름 그림 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-225">[![Microsoft Teams Online Call Flows Figure 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span></span>

<span data-ttu-id="e01cc-226">*그림 3-외부 사용자에 대 한 고객 네트워크 (팀에서 전송 릴레이가 전달 하는 미디어 릴레이)*</span><span class="sxs-lookup"><span data-stu-id="e01cc-226">*Figure 3 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="e01cc-227">7 단계에서 고객 네트워크에서 Office 365로 이동 하 고, 원격 모바일 팀 사용자에서 Office 365로 흐름 3을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-227">In step 7, flow 4, from customer network to Office 365, and flow 3, from remote mobile Teams user to Office 365, are selected.</span></span> <span data-ttu-id="e01cc-228">이러한 흐름은 Office 365 내의 팀 전송 릴레이가 릴레이 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-228">These flows are relayed by Teams Transport Relay within Office 365.</span></span>

<span data-ttu-id="e01cc-229">미디어는 양방향 이며, 방향은 연결 관점에서 통신을 시작 하는 측면을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-229">Media is bidirectional, where direction indicates which side initiates the communication from a connectivity perspective.</span></span> <span data-ttu-id="e01cc-230">이 경우 이러한 흐름은 다른 전송 프로토콜과 주소를 통해 신호 및 미디어에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-230">In this case, these flows are used for signaling and media, via different transport protocols and addresses.</span></span>

<span data-ttu-id="e01cc-231">**외부 사용자에 대 한 고객 네트워크 (직접 미디어):**</span><span class="sxs-lookup"><span data-stu-id="e01cc-231">**Customer network to external user (direct media):**</span></span>

<span data-ttu-id="e01cc-232">[![Microsoft 팀 온라인 통화 흐름 그림 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-232">[![Microsoft Teams Online Call Flows Figure 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span></span>

<span data-ttu-id="e01cc-233">*그림 4-외부 사용자에 대 한 고객 네트워크 (직접 미디어)*</span><span class="sxs-lookup"><span data-stu-id="e01cc-233">*Figure 4 - Customer network to external user (direct media)*</span></span>
 
<span data-ttu-id="e01cc-234">7 단계에서 고객 네트워크에서 인터넷 (클라이언트 피어)으로 흐름 2가 선택 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-234">In step 7, flow 2, from customer network to Internet (client's peer), is selected.</span></span>
- <span data-ttu-id="e01cc-235">원격 모바일 사용자와의 다이렉트 미디어 (즉, Office 365를 통해 릴레이할 수 없음)는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-235">Direct media with remote mobile user (that is, not relayed through Office 365) is optional.</span></span> <span data-ttu-id="e01cc-236">즉, 고객은이 경로를 차단 하 여 Office 365의 전송 릴레이를 통해 미디어 경로를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-236">In other words, customer may block this path to enforce a media path through Transport Relay in Office 365.</span></span>

- <span data-ttu-id="e01cc-237">미디어는 양방향입니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-237">Media is bidirectional.</span></span> <span data-ttu-id="e01cc-238">흐름 2에서 원격 모바일 사용자에 대 한 방향은 연결 관점에서 통신을 시작 한다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-238">The direction of flow 2 to remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span> 

<span data-ttu-id="e01cc-239">**내부 사용자에 대 한 VPN 사용자 (팀에서 전송 하는 미디어 릴레이)**</span><span class="sxs-lookup"><span data-stu-id="e01cc-239">**VPN user to internal user (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="e01cc-240">[![Microsoft 팀 온라인 통화 흐름 그림 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-240">[![Microsoft Teams Online Call Flows Figure 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span></span>

<span data-ttu-id="e01cc-241">*그림 5-내부 사용자에 대 한 VPN 사용자 (팀에서 전송 하는 미디어 릴레이)*</span><span class="sxs-lookup"><span data-stu-id="e01cc-241">*Figure 5 - VPN user to internal user (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="e01cc-242">VPN을 고객 네트워크로 보내는 신호는 흐름 2를 통해 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-242">Signaling between the VPN to the customer network is via flow 2'.</span></span> <span data-ttu-id="e01cc-243">고객 네트워크와 Office 365 간의 신호는 흐름 4를 통해 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-243">Signaling between the customer network and Office 365 is via flow 4.</span></span> <span data-ttu-id="e01cc-244">그러나 미디어는 VPN을 우회 하 고 Office 365의 흐름 3 및 4에서 팀 미디어 릴레이를 통해 라우팅되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-244">However, media bypasses the VPN and is routed via flows 3 and 4 through Teams media relay in Office 365.</span></span>

<span data-ttu-id="e01cc-245">**내부 사용자에 대 한 VPN 사용자 (직접 미디어)**</span><span class="sxs-lookup"><span data-stu-id="e01cc-245">**VPN user to internal user (direct media)**</span></span>

<span data-ttu-id="e01cc-246">[![Microsoft 팀 온라인 통화 흐름 그림 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-246">[![Microsoft Teams Online Call Flows Figure 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span></span>

<span data-ttu-id="e01cc-247">*그림 6-내부 사용자에 대 한 VPN 사용자 (직접 미디어)*</span><span class="sxs-lookup"><span data-stu-id="e01cc-247">*Figure 6 - VPN user to internal user (direct media)*</span></span>

<span data-ttu-id="e01cc-248">VPN을 고객 네트워크로 보내는 신호는 흐름 2를 통해 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-248">Signaling between the VPN to the customer network is via flow 2'.</span></span> <span data-ttu-id="e01cc-249">고객 네트워크와 Office 365 간의 신호는 흐름 4를 통해 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-249">Signaling between the customer network and Office 365 is via flow 4.</span></span> <span data-ttu-id="e01cc-250">그러나 미디어는 VPN을 우회 하 고 고객 네트워크의 흐름 2를 통해 인터넷에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-250">However, media bypasses the VPN and is routed via flow 2 from the customer network to the Internet.</span></span>

<span data-ttu-id="e01cc-251">미디어는 양방향입니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-251">Media is bidirectional.</span></span> <span data-ttu-id="e01cc-252">원격 모바일 사용자에 대 한 흐름 2의 방향은 연결 관점에서 통신을 시작 한다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-252">The direction of flow 2 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="e01cc-253">**외부 사용자에 대 한 VPN 사용자 (직접 미디어)**</span><span class="sxs-lookup"><span data-stu-id="e01cc-253">**VPN user to external user (direct media)**</span></span>

<span data-ttu-id="e01cc-254">[![Microsoft 팀 통화 흐름 그림 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-254">[![Microsoft Teams call flows Figure 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span></span>

<span data-ttu-id="e01cc-255">*그림 7-외부 사용자에 대 한 VPN 사용자 (직접 미디어)*</span><span class="sxs-lookup"><span data-stu-id="e01cc-255">*Figure 7 - VPN user to external user (direct media)*</span></span>

<span data-ttu-id="e01cc-256">VPN 사용자와 고객 네트워크 간 신호는 흐름 2 ' 및 흐름 4를 통해 Office 365를 통해 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-256">Signaling between the VPN user to the customer network is via flow 2' and via flow 4 to Office 365.</span></span> <span data-ttu-id="e01cc-257">그러나 미디어는 VPN을 우회 하 고 흐름 6을 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-257">However, media bypasses VPN and is routed via flow 6.</span></span>

<span data-ttu-id="e01cc-258">미디어는 양방향입니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-258">Media is bidirectional.</span></span> <span data-ttu-id="e01cc-259">원격 모바일 사용자에 대 한 흐름 6의 방향은 연결 관점에서 통신을 시작 한다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-259">The direction of flow 6 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a><span data-ttu-id="e01cc-260">사용 사례: Office 365 트렁크를 통해 PSTN에 대 한 팀</span><span class="sxs-lookup"><span data-stu-id="e01cc-260">Use Case: Teams to PSTN through Office 365 Trunk</span></span>
<span data-ttu-id="e01cc-261">Office 365에는 PSTN (공공 교환 전화 네트워크)에서 전화를 걸고 받을 수 있는 전화기 시스템이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-261">Office 365 has a Phone System that allows placing and receiving calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="e01cc-262">PSTN 트렁크가 전화 시스템 통화 요금제를 통해 연결 된 경우에는이 사용 사례에 대 한 특별 한 연결 요구 사항이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-262">If the PSTN trunk is connected via the Phone System Calling Plan, then there are no special connectivity requirements for this use case.</span></span> <span data-ttu-id="e01cc-263">(사용자의 온-프레미스 PSTN 트렁크를 Office 365에 연결 하려는 경우 전화 시스템 다이렉트 라우팅을 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="e01cc-263">(If you want to connect your own on-premises PSTN trunk to Office 365, you can use Phone System Direct Routing.)</span></span>

<span data-ttu-id="e01cc-264">[![Microsoft 팀 온라인 통화 흐름 그림 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-264">[![Microsoft Teams Online Call Flows Figure 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span></span>

<span data-ttu-id="e01cc-265">*그림 8-Office 365 트렁크를 통해 PSTN 용 팀*</span><span class="sxs-lookup"><span data-stu-id="e01cc-265">*Figure 8 - Teams to PSTN through Office 365 Trunk*</span></span>

#### <a name="use-case-teams-meeting"></a><span data-ttu-id="e01cc-266">사용 사례: 팀 모임</span><span class="sxs-lookup"><span data-stu-id="e01cc-266">Use Case: Teams Meeting</span></span>

<span data-ttu-id="e01cc-267">오디오/비디오/화면 공유 (VBSS) 회의 서버는 Office 365의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-267">The audio/video/screen sharing (VBSS) conferencing server is part of Office 365.</span></span> <span data-ttu-id="e01cc-268">이 주소에는 고객 네트워크에서 접근할 수 있어야 하 고 Nomadic 클라우드 클라이언트에서 연결할 수 있어야 하는 공용 IP 주소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-268">It has a public IP address that must be reachable from the customer network and must be reachable from a Nomadic Cloud client.</span></span> <span data-ttu-id="e01cc-269">각 클라이언트/끝점은 회의 서버에 연결할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-269">Each client/endpoint needs to be able to connect to the conferencing server.</span></span>

<span data-ttu-id="e01cc-270">내부 클라이언트는 일대일 통화에 대해 설명 하는 것과 동일한 방식으로 로컬, 재귀 및 릴레이 후보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-270">Internal clients will obtain local, reflexive, and relay candidates in the same manner as described for one-to-one calls.</span></span> <span data-ttu-id="e01cc-271">클라이언트는이 후보자를 초대의 회의 서버로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-271">The clients will send these candidates to the conferencing server in an invite.</span></span> <span data-ttu-id="e01cc-272">회의 서버에는 공용으로 연결할 수 있는 IP 주소가 있으므로 릴레이가 사용 되지 않으므로 해당 로컬 IP 주소 후보에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-272">The conferencing server does not use a relay since it has a publicly reachable IP address, so it responds with its local IP address candidate.</span></span> <span data-ttu-id="e01cc-273">클라이언트와 회의 서버는 일대일 통화에 대해 설명 된 것과 동일한 방식으로 연결을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-273">The client and conferencing server will check connectivity in the same manner described for one-to-one calls.</span></span> 

<span data-ttu-id="e01cc-274">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-274">Note that:</span></span>

- <span data-ttu-id="e01cc-275">팀 클라이언트는 비즈니스용 Skype 모임에 참가할 수 없으며 비즈니스용 Skype 클라이언트가 팀 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-275">Teams clients cannot join Skype for Business meetings, and Skype for Business clients cannot join Teams meetings.</span></span>

- <span data-ttu-id="e01cc-276">사용자가 모임 이끌이 PSTN 통화 및/또는 회의 프로 비전에 따라 선택적으로 "전화를 거는" 또는 "전화 걸기"로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-276">A PSTN user optionally "Dials IN" or "Dialed OUT", depending on the meeting's organizer PSTN Calling and/or conferencing provisioning.</span></span> 

- <span data-ttu-id="e01cc-277">게스트 사용자 또는 고객 사용자는 엄격한 규칙이 있는 FW/NAT를 통해 보호 되는 게스트 개인 네트워크에서 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-277">A guest user or a customer user may join from a guest private network, which is protected via FW/NAT with strict rules.</span></span>

<span data-ttu-id="e01cc-278">[![Microsoft 팀 온라인 통화 흐름 그림 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-278">[![Microsoft Teams Online Call Flows Figure 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span></span>

<span data-ttu-id="e01cc-279">*그림 9-팀 모임*</span><span class="sxs-lookup"><span data-stu-id="e01cc-279">*Figure 9 - Teams Meeting*</span></span>

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a><span data-ttu-id="e01cc-280">사용 사례: 비즈니스용 Skype를 사용 하 여 온-프레미스 페더레이션</span><span class="sxs-lookup"><span data-stu-id="e01cc-280">Use Case: Federation with Skype for Business on premises</span></span>

<span data-ttu-id="e01cc-281">**Office 365의 팀에서 전송 릴레이가 전달 하는 미디어 릴레이**</span><span class="sxs-lookup"><span data-stu-id="e01cc-281">**Media relayed by Teams Transport Relay in Office 365**</span></span>

<span data-ttu-id="e01cc-282">[![Microsoft 팀 온라인 통화 흐름 그림 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-282">[![Microsoft Teams Online Call Flows Figure 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span></span>

<span data-ttu-id="e01cc-283">*그림 10-Office 365에서 팀이 전송 하는 미디어 릴레이*</span><span class="sxs-lookup"><span data-stu-id="e01cc-283">*Figure 10 - Media relayed by Teams Transport Relay in Office 365*</span></span>

<span data-ttu-id="e01cc-284">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-284">Note that:</span></span>

- <span data-ttu-id="e01cc-285">페더레이션은 두 테 넌 트 간의 통신을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-285">Federation is, by definition, a communication between two tenants.</span></span> <span data-ttu-id="e01cc-286">이 경우 테 넌 트 A는 비즈니스용 Skype를 사용 하는 테 넌 트 B를 사용 하는 federates 팀을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-286">In this case, tenant A, which uses Teams, federates with tenant B, which uses Skype for Business on premises.</span></span> <span data-ttu-id="e01cc-287">테 넌 트 B도 Office 365를 사용 하는 경우 비즈니스용 Skype 클라이언트는 흐름 3을 사용 하 여 Office 365에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-287">If tenant B is also using Office 365, then the Skype for Business client would have used flow 3 to connect with Office 365.</span></span>

- <span data-ttu-id="e01cc-288">페더레이션된 Skype for Business 클라이언트에서 온-프레미스 비즈니스용 Skype Server로의 신호 및 미디어는이 문서의 범위를 벗어났습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-288">Signaling and media from the federated Skype for Business client to on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="e01cc-289">이해를 돕기 위해 여기에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-289">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="e01cc-290">Office 365의 게이트웨이에서 팀과 비즈니스용 Skype 간의 신호를 브리지로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-290">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="e01cc-291">이 경우 미디어는 Office 365의 팀 전송 릴레이가 흐름 4를 통해 고객 네트워크 및 원격 비즈니스용 Skype 클라이언트에 의해 릴레이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-291">Media in this case is relayed by Teams Transport Relay in Office 365 to the customer network and remote Skype for Business client via flow 4.</span></span>

<span data-ttu-id="e01cc-292">**페더레이션된 테 넌 트의 비즈니스용 Skype 미디어 릴레이에서 릴레이 된 미디어**</span><span class="sxs-lookup"><span data-stu-id="e01cc-292">**Media relayed by Skype for Business Media Relay in federated tenant**</span></span>

<span data-ttu-id="e01cc-293">[![Microsoft 팀 온라인 통화 흐름 그림 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-293">[![Microsoft Teams Online Call Flows Figure 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span></span>

<span data-ttu-id="e01cc-294">*그림 11-페더레이션된 테 넌 트의 비즈니스용 Skype 미디어 릴레이에서 릴레이 된 미디어*</span><span class="sxs-lookup"><span data-stu-id="e01cc-294">*Figure 11 - Media relayed by Skype for Business Media Relay in federated tenant*</span></span>

<span data-ttu-id="e01cc-295">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-295">Note that:</span></span>

- <span data-ttu-id="e01cc-296">페더레이션된 Skype for Business 클라이언트에서 온-프레미스 비즈니스용 Skype 서버의 신호 및 미디어는이 문서의 범위를 벗어났습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-296">Signaling and media from the federated Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="e01cc-297">이해를 돕기 위해 여기에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-297">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="e01cc-298">Office 365의 게이트웨이에서 팀과 비즈니스용 Skype 간의 신호를 브리지로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-298">Signaling between Teams and Skype for Business is bridged by a Gateway in Office 365.</span></span>

- <span data-ttu-id="e01cc-299">이 경우 미디어는 비즈니스용 Skype 온-프레미스 미디어 릴레이가 흐름 2를 통해 고객 네트워크에 릴레이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-299">Media in this case is relayed by Skype for Business on-premises Media Relay to the customer network via flow 2.</span></span> <span data-ttu-id="e01cc-300">(팀 사용자가 페더레이션된 고객 네트워크의 원격 미디어 릴레이로의 트래픽은 처음에는 역방향 방향의 트래픽이 흐름에 도달할 때까지 미디어 중계에 의해 차단 됨을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-300">(Note that traffic from Teams user to the remote Media Relay in the federated customer network will be initially blocked by the Media Relay until traffic in the reverse direction starts to flow.</span></span> <span data-ttu-id="e01cc-301">하지만 양방향 흐름은 양방향으로 연결을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-301">However, the bidirectional flow will open connectivity in both directions.)</span></span>

<span data-ttu-id="e01cc-302">**Direct (피어 투 피어)**</span><span class="sxs-lookup"><span data-stu-id="e01cc-302">**Direct (peer-to-peer)**</span></span>

<span data-ttu-id="e01cc-303">[![Microsoft 팀 온라인 통화 흐름 그림 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-303">[![Microsoft Teams Online Call Flows Figure 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span></span>

<span data-ttu-id="e01cc-304">*그림 12-다이렉트 (피어 투 피어)*</span><span class="sxs-lookup"><span data-stu-id="e01cc-304">*Figure 12 - Direct (peer-to-peer)*</span></span>

### <a name="teams-hybrid-topology"></a><span data-ttu-id="e01cc-305">팀 하이브리드 토폴로지</span><span class="sxs-lookup"><span data-stu-id="e01cc-305">Teams hybrid topology</span></span>
<span data-ttu-id="e01cc-306">이 토폴로지에는 비즈니스용 Skype 온-프레미스 배포가 있는 팀이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-306">This topology includes Teams with a Skype for Business on-premises deployment.</span></span>

<span data-ttu-id="e01cc-307">[![Microsoft 팀 온라인 통화 흐름 그림 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-307">[![Microsoft Teams Online Call Flows Figure 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span></span>

<span data-ttu-id="e01cc-308">*그림 13-팀 하이브리드 토폴로지*</span><span class="sxs-lookup"><span data-stu-id="e01cc-308">*Figure 13 - Teams hybrid topology*</span></span>
 
- <span data-ttu-id="e01cc-309">위의 다이어그램에 있는 화살표의 방향은 엔터프라이즈 perimeters 연결에 영향을 주는 통신의 시작 방향을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-309">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="e01cc-310">미디어에 대 한 UDP의 경우 첫 번째 패킷이 역방향으로 흐를 수 있지만 다른 방향의 패킷이 흐를 때까지 이러한 패킷이 차단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-310">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="e01cc-311">팀은 비즈니스용 Skype Online과 나란히 배포 되므로 클라이언트는 "팀/SFB 사용자"로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-311">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="e01cc-312">추가 흐름 (팀 토폴로지 맨 위):</span><span class="sxs-lookup"><span data-stu-id="e01cc-312">Additional flows (on top of Teams topology):</span></span>
- <span data-ttu-id="e01cc-313">**흐름 5a** – 고객 네트워크 내의 팀 사용자와 고객 네트워크 Edge의 비즈니스용 Skype 온-프레미스 미디어 릴레이 간 피어 투 피어 미디어 흐름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-313">**Flow 5A** – Represents a peer-to-peer media flow between a Teams user within the customer network and a Skype for Business on-premises media relay at the customer network edge.</span></span>

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a><span data-ttu-id="e01cc-314">사용 사례: 비즈니스용 Skype 일대일/one 팀</span><span class="sxs-lookup"><span data-stu-id="e01cc-314">Use Case: Teams to Skype for Business one-to-one</span></span>
<span data-ttu-id="e01cc-315">**고객 네트워크 내부의 하이브리드**</span><span class="sxs-lookup"><span data-stu-id="e01cc-315">**Hybrid within the customer network**</span></span>

<span data-ttu-id="e01cc-316">[![Microsoft 팀 온라인 통화 흐름 그림 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-316">[![Microsoft Teams Online Call Flows Figure 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span></span>

<span data-ttu-id="e01cc-317">*그림 14-고객 네트워크 내의 하이브리드*</span><span class="sxs-lookup"><span data-stu-id="e01cc-317">*Figure 14 - Hybrid within customer network*</span></span>
 
<span data-ttu-id="e01cc-318">Office 365의 게이트웨이에서 팀과 비즈니스용 Skype 간의 신호를 브리지로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-318">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span> <span data-ttu-id="e01cc-319">그러나 미디어는 고객 네트워크 내에서 흐름 5를 통해 직접 피어 투 피어에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-319">However, media is routed directly peer-to-peer within the customer network via flow 5.</span></span>

<span data-ttu-id="e01cc-320">**외부 비즈니스용 Skype 사용자와 하이브리드 고객 네트워크-Office 365에서 릴레이**</span><span class="sxs-lookup"><span data-stu-id="e01cc-320">**Hybrid customer network with external Skype for Business user – relayed by Office 365**</span></span>

<span data-ttu-id="e01cc-321">[![Microsoft 팀 온라인 통화 흐름 그림 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-321">[![Microsoft Teams Online Call Flows Figure 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span></span>

<span data-ttu-id="e01cc-322">*그림 15-외부 비즈니스용 Skype 사용자가 있는 하이브리드 고객 네트워크-Office 365에서 릴레이*</span><span class="sxs-lookup"><span data-stu-id="e01cc-322">*Figure 15 - Hybrid customer network with external Skype for Business user - relayed by Office 365*</span></span>

<span data-ttu-id="e01cc-323">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-323">Note that:</span></span>

- <span data-ttu-id="e01cc-324">비즈니스용 Skype 클라이언트에서 온-프레미스 비즈니스용 Skype 서버에 대 한 신호 및 미디어는이 문서의 범위를 벗어났습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-324">Signaling and media from the Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="e01cc-325">이해를 돕기 위해 여기에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-325">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="e01cc-326">Office 365의 게이트웨이에서 팀과 비즈니스용 Skype 간의 신호를 브리지로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-326">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="e01cc-327">미디어는 Office 365의 팀 전송 릴레이가 흐름 4를 통해 고객 네트워크로 릴레이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-327">Media is relayed through Teams Transport Relay in Office 365 to the customer network through flow 4.</span></span>

<span data-ttu-id="e01cc-328">**외부 비즈니스용 Skype 사용자와 하이브리드 고객 네트워크-온-프레미스 Edge로 릴레이**</span><span class="sxs-lookup"><span data-stu-id="e01cc-328">**Hybrid customer network with external Skype for Business user – relayed by on-premises Edge**</span></span>

<span data-ttu-id="e01cc-329">[![Microsoft 팀 온라인 통화 흐름 그림 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-329">[![Microsoft Teams Online Call Flows Figure 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span></span>

<span data-ttu-id="e01cc-330">*그림 16-온-프레미스 Edge로 릴레이할 비즈니스용 Skype 사용자와 하이브리드 고객 네트워크*</span><span class="sxs-lookup"><span data-stu-id="e01cc-330">*Figure 16 - Hybrid customer network with external Skype for Business user - relayed by on-premises Edge*</span></span>
 
<span data-ttu-id="e01cc-331">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-331">Note that:</span></span>

- <span data-ttu-id="e01cc-332">비즈니스용 Skype 클라이언트에서 온-프레미스 비즈니스용 Skype 서버에 대 한 신호 및 미디어는이 문서의 범위를 벗어났습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-332">Signaling and media from Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="e01cc-333">이해를 돕기 위해 여기에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-333">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="e01cc-334">신호는 Office 365의 게이트웨이에서 브리지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-334">Signaling is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="e01cc-335">미디어는 비즈니스용 Skype 온-프레미스 Edge 내의 비즈니스용 skype 미디어 릴레이에서 미디어 흐름 5A를 통해 고객 네트워크 내의 팀 사용자에 게 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-335">Media is relayed by Skype for Business Media Relay within Skype for Business on-premises Edge to Teams user within the customer network via media flow 5A.</span></span>

### <a name="teams-with-phone-system-direct-routing-topology"></a><span data-ttu-id="e01cc-336">전화 시스템 다이렉트 라우팅 토폴로지가 있는 팀</span><span class="sxs-lookup"><span data-stu-id="e01cc-336">Teams with Phone System Direct Routing topology</span></span>
<span data-ttu-id="e01cc-337">이 토폴로지에는 전화 시스템 다이렉트 라우팅이 있는 팀이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-337">This topology includes Teams with Phone System Direct Routing.</span></span> 

<span data-ttu-id="e01cc-338">직접 라우팅은 지원 되는 온-프레미스 고객 소유 세션 경계 컨트롤러 (SBC) 하드웨어 장치를 Office 365와 연결 하 여 타사의 PSTN (공개 통신 네트워크) 서비스 공급자를 사용할 수 있도록 합니다. 해당 장치</span><span class="sxs-lookup"><span data-stu-id="e01cc-338">Direct Routing enables you to use a third-party Public Switched Telephone Network (PSTN) service provider by pairing a supported on-premises customer-owned Session Border Controller (SBC) hardware device to Office 365, and then connecting the telephony trunk to that device.</span></span> 

<span data-ttu-id="e01cc-339">이 시나리오를 지원 하려면 고객은 Microsoft의 인증 파트너 중 하나에서 직접 라우팅에 대 한 인증 된 SBC를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-339">To support this scenario, the customer must deploy a certified SBC for Direct Routing from one of Microsoft's certified partners.</span></span> <span data-ttu-id="e01cc-340">SBC는 공급 업체에서 권장 하는 대로 구성 되어야 하 고, 직접 UDP 트래픽을 위해 Office 365에서 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-340">The SBC must be configured as recommended by the vendor, and be routable from Office 365 for direct UDP traffic.</span></span> <span data-ttu-id="e01cc-341">미디어는 팀 및/또는 비즈니스용 Skype 클라이언트에서 SBC로 직접 흐를 수 있습니다 (팀 게이트웨이 건너뜀) 또는 팀 게이트웨이를 통과 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-341">The media may flow directly from Teams and/or the Skype for Business client to the SBC (bypassing the Teams gateway) or traverse through the Teams gateway.</span></span> <span data-ttu-id="e01cc-342">SBC와의 연결은 팀 게이트웨이를 우회 하도록 구성 된 경우 SBC에서 ICE가 지원 되는 얼음에 기반을 둔 반면, Business/비즈니스용 Skype media 끝점은 얼음으로 가득 찬 것을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-342">The connectivity with the SBC, when the trunk is configured to bypass the Teams gateway, is based on ICE, where SBC supports ICE-Lite, while the Teams/Skype for Business media endpoint supports ICE Full.</span></span> 

<span data-ttu-id="e01cc-343">[![Microsoft 팀 온라인 통화 흐름 그림 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-343">[![Microsoft Teams Online Call Flows Figure 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span></span>

<span data-ttu-id="e01cc-344">\* 그림 17-전화 시스템 다이렉트 라우팅 토폴로지가 있는 팀</span><span class="sxs-lookup"><span data-stu-id="e01cc-344">\*Figure 17 - Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="e01cc-345">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-345">Note that:</span></span>

- <span data-ttu-id="e01cc-346">위의 다이어그램에 있는 화살표의 방향은 엔터프라이즈 perimeters 연결에 영향을 주는 통신의 시작 방향을 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-346">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="e01cc-347">미디어에 대 한 UDP의 경우 첫 번째 패킷이 역방향으로 흐를 수 있지만 다른 방향의 패킷이 흐를 때까지 이러한 패킷이 차단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-347">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="e01cc-348">팀은 비즈니스용 Skype Online과 나란히 배포 되므로 클라이언트는 "팀/SFB 사용자"로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-348">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="e01cc-349">추가 흐름 (팀 온라인 토폴로지 맨 위):</span><span class="sxs-lookup"><span data-stu-id="e01cc-349">Additional flows (on top of Teams online topology):</span></span>
- <span data-ttu-id="e01cc-350">**흐름 4 '** -Office 365부터 고객 네트워크 까지의 흐름을 나타내며, 클라우드의 SBC를 사용 하 여 클라우드에서 팀 미디어 서버 간 연결을 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-350">**Flow 4'** - Represents a flow from Office 365 to the customer network, used to establish a connection between the Teams media server in the cloud with the SBC on premises.</span></span>
- <span data-ttu-id="e01cc-351">**흐름 5b** – 우회 모드의 다이렉트 라우팅 SBC를 사용 하 여 고객 네트워크 내의 팀 사용자 간 미디어 흐름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-351">**Flow 5B** – Represents a media flow between the Teams user within the customer network with the Direct Routing SBC in bypass mode.</span></span>
- <span data-ttu-id="e01cc-352">**흐름 5c** – PSTN 연결 호출 우회 모드에서 직접 라우팅 sbc와 다른 직접 라우팅 sbc 사이의 미디어 흐름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-352">**Flow 5C** – Represents a media flow between the Direct Routing SBC to another Direct Routing SBC in a PSTN hairpin call bypass mode.</span></span>

<span data-ttu-id="e01cc-353">**직접적인 라우팅이 있는 내부 사용자 (Office 365의 팀에서 미디어를 릴레이 하는 방법 전송 릴레이)**</span><span class="sxs-lookup"><span data-stu-id="e01cc-353">**Internal user with Direct Routing (media relayed by Teams Transport Relay in Office 365)**</span></span>

<span data-ttu-id="e01cc-354">[![Microsoft 팀 온라인 통화 흐름 그림 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-354">[![Microsoft Teams Online Call Flows Figure 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span></span>

<span data-ttu-id="e01cc-355">*그림 18-직접 라우팅이 있는 내부 사용자 (Office 365의 팀에서 전송 릴레이가 미디어를 릴레이할 때)*</span><span class="sxs-lookup"><span data-stu-id="e01cc-355">*Figure 18 - Internal user with Direct Routing (media relayed by Teams Transport Relay in Office 365)*</span></span>

<span data-ttu-id="e01cc-356">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-356">Note that:</span></span>
 
- <span data-ttu-id="e01cc-357">SBC에는 Office 365에서 라우팅할 수 있는 공용 IP 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-357">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="e01cc-358">SBC에서 Office 365로 신호 및 미디어를 보내고, 흐름 4 및/또는 흐름 4를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-358">Signaling and media from the SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="e01cc-359">고객 네트워크 내의 클라이언트에서 Office 365으로 이동 하는 신호 및 미디어를 사용 하는 방법 4.</span><span class="sxs-lookup"><span data-stu-id="e01cc-359">Signaling and media from the client within the customer network to Office 365 use flow 4.</span></span>


<span data-ttu-id="e01cc-360">**직접 라우팅이 있는 원격 사용자 (미디어는 Office 365의 media server (MP)를 통해 라우트 됨)**</span><span class="sxs-lookup"><span data-stu-id="e01cc-360">**Remote user with Direct Routing (media is routed through a media server (MP) in Office 365)**</span></span>

<span data-ttu-id="e01cc-361">[![Microsoft 팀 온라인 통화 흐름 그림 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-361">[![Microsoft Teams Online Call Flows Figure 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span></span>

<span data-ttu-id="e01cc-362">*그림 19-직접 라우팅이 있는 원격 사용자 (미디어는 Office 365의 media server (MP)를 통해 라우트됩니다)*</span><span class="sxs-lookup"><span data-stu-id="e01cc-362">*Figure 19 - Remote user with Direct Routing (media is routed through a media server (MP) in Office 365)*</span></span>
 
<span data-ttu-id="e01cc-363">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-363">Note that:</span></span>

- <span data-ttu-id="e01cc-364">SBC에는 Office 365에서 라우팅할 수 있는 공용 IP 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-364">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="e01cc-365">SBC에서 Office 365로 신호 및 미디어를 보내고, 흐름 4 및/또는 흐름 4를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-365">Signaling and media from the SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="e01cc-366">인터넷의 클라이언트에서 Office 365로 신호 및 미디어를 사용 하는 것이 흐름 3</span><span class="sxs-lookup"><span data-stu-id="e01cc-366">Signaling and media from the client on the Internet to Office 365 use flow 3.</span></span>

<span data-ttu-id="e01cc-367">**내부 사용자 직접 라우팅 (미디어 바이패스)**</span><span class="sxs-lookup"><span data-stu-id="e01cc-367">**Internal user Direct Routing (media bypass)**</span></span>

<span data-ttu-id="e01cc-368">[![Microsoft 팀 온라인 통화 흐름 그림 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-368">[![Microsoft Teams Online Call Flows Figure 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span></span>

<span data-ttu-id="e01cc-369">*그림 20-내부 사용자 직접 라우팅 (미디어 바이패스)*</span><span class="sxs-lookup"><span data-stu-id="e01cc-369">*Figure 20 - Internal user Direct Routing (media bypass)*</span></span>
 
<span data-ttu-id="e01cc-370">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-370">Note that:</span></span>

- <span data-ttu-id="e01cc-371">SBC에는 Office 365에서 라우팅할 수 있는 공용 IP 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-371">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="e01cc-372">SBC에서 Office 365로 신호를 보내고 그 반대의 경우 흐름 4 및/또는 흐름 4 '를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-372">Signaling from SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="e01cc-373">고객 네트워크 내의 클라이언트에서 Office 365으로 전송 되는 신호는 흐름 4를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-373">Signaling from client within the customer network to Office 365 use flow 4.</span></span>

- <span data-ttu-id="e01cc-374">고객 네트워크 내의 클라이언트에서 고객 네트워크에 있는 SBC에 대 한 미디어는 flow 5B로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-374">Media from client within the customer network to SBC within the customer network use flow 5B.</span></span>

<span data-ttu-id="e01cc-375">**직접 라우팅이 있는 원격 사용자 (Office 365의 팀에서 전송 릴레이가 미디어를 우회 하 여 릴레이)**</span><span class="sxs-lookup"><span data-stu-id="e01cc-375">**Remote user with Direct Routing (media bypass relayed by Teams Transport Relay in Office 365)**</span></span>

<span data-ttu-id="e01cc-376">[![Microsoft 팀 온라인 통화 흐름 그림 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-376">[![Microsoft Teams Online Call Flows Figure 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span></span>

<span data-ttu-id="e01cc-377">*그림 21-직접 라우팅이 있는 원격 사용자 (Office 365의 팀에서 미디어를 사용 하 여 릴레이 전송 릴레이가 전달 됩니다.)*</span><span class="sxs-lookup"><span data-stu-id="e01cc-377">*Figure 21 - Remote user with Direct Routing (media bypass relayed by Teams Transport Relay in Office 365)*</span></span>

<span data-ttu-id="e01cc-378">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-378">Note that:</span></span>

- <span data-ttu-id="e01cc-379">SBC에는 Office 365 및 인터넷에서 라우팅할 수 있는 공용 IP 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-379">The SBC must have a public IP address that is routable from Office 365 and Internet.</span></span>

- <span data-ttu-id="e01cc-380">SBC에서 Office 365로 신호를 보내고 그 반대의 경우 흐름 4 및/또는 흐름 4를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-380">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="e01cc-381">인터넷의 클라이언트에서 Office 365로 신호를 보내는 것은 흐름 3을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-381">Signaling from the client on the Internet to Office 365 uses flow 3.</span></span>

- <span data-ttu-id="e01cc-382">고객 네트워크 내의 SBC에 대 한 인터넷 클라이언트의 미디어는 3 번 및 4 흐름을 사용 하 고, Office 365의 팀 전송 릴레이가 릴레이 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-382">Media from the client on the Internet to the SBC within the customer network uses flows 3 and 4, relayed by Teams Transport Relay in Office 365.</span></span> 

<span data-ttu-id="e01cc-383">**원격 사용자 직접 라우팅 (미디어 바이패스 다이렉트)**</span><span class="sxs-lookup"><span data-stu-id="e01cc-383">**Remote user Direct Routing (media bypass direct)**</span></span>

<span data-ttu-id="e01cc-384">[![Microsoft 팀 온라인 통화 흐름 그림 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-384">[![Microsoft Teams Online Call Flows Figure 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span></span>

<span data-ttu-id="e01cc-385">*그림 22-원격 사용자 직접 라우팅 (미디어 바이패스 다이렉트)*</span><span class="sxs-lookup"><span data-stu-id="e01cc-385">*Figure 22 - Remote user Direct Routing (media bypass direct)*</span></span>
 
<span data-ttu-id="e01cc-386">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-386">Note that:</span></span>

- <span data-ttu-id="e01cc-387">SBC에는 Office 365 및 인터넷에서 라우팅할 수 있는 공용 IP 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-387">The SBC must have a public IP address that is routable from Office 365 and the Internet.</span></span>

- <span data-ttu-id="e01cc-388">SBC에서 Office 365로 신호를 보내고 그 반대의 경우 흐름 4 및/또는 흐름 4를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-388">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="e01cc-389">인터넷의 클라이언트에서 Office 365로 신호를 보내는 것은 흐름 3을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-389">Signaling from the client on the Internet to Office 365 uses flow 3.</span></span>

- <span data-ttu-id="e01cc-390">고객 네트워크 내의 SBC에 대 한 인터넷 클라이언트의 미디어는 흐름 2를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-390">Media from the client on the Internet to the SBC within the customer network uses flow 2.</span></span>

<span data-ttu-id="e01cc-391">**다이렉트 라우팅 (미디어 바이패스) – PSTN 연결 통화 (착신 통화/전송로 인해)**</span><span class="sxs-lookup"><span data-stu-id="e01cc-391">**Direct Routing (media bypass) – PSTN hairpin call (due to call forward/transfer)**</span></span>

<span data-ttu-id="e01cc-392">[![Microsoft 팀 온라인 통화 흐름 그림 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-392">[![Microsoft Teams Online Call Flows Figure 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span></span>

<span data-ttu-id="e01cc-393">*그림 23-다이렉트 라우팅 (미디어 바이패스)-PSTN 연결 통화 (착신 통화/전송로 인해)*</span><span class="sxs-lookup"><span data-stu-id="e01cc-393">*Figure 23 - Direct Routing (media bypass) - PSTN hairpin call (due to call forward/transfer)*</span></span>
 
<span data-ttu-id="e01cc-394">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-394">Note that:</span></span>

- <span data-ttu-id="e01cc-395">SBC에는 Office 365에서 라우팅할 수 있는 공용 IP 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-395">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="e01cc-396">SBC에서 Office 365로 신호를 보내고 그 반대의 경우 흐름 4 및/또는 흐름 4를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-396">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="e01cc-397">클라이언트가 PSTN에서 PSTN으로 전화를 hairpinned 후 신호 및 미디어 루프를 벗어났습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-397">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="e01cc-398">고객 네트워크 내의 sbc 인스턴스 A의 미디어를 고객 네트워크 내의 SBC 인스턴스 B (여기서, A 및 B는 같은 인스턴스일 수 있음)에서 흐름 5C를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-398">Media from SBC instance A within the customer network to SBC instance B within the customer network (where, A and B can be the same instance) uses flow 5C.</span></span>

<span data-ttu-id="e01cc-399">**다이렉트 라우팅 (Office 365)-2 개의 테 넌 트를 통해 PSTN 연결 통화**</span><span class="sxs-lookup"><span data-stu-id="e01cc-399">**Direct Routing (media through Office 365) – PSTN hairpin call across two tenants**</span></span>

<span data-ttu-id="e01cc-400">[![Microsoft 팀 온라인 통화 흐름 그림 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-400">[![Microsoft Teams Online Call Flows Figure 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span></span>

<span data-ttu-id="e01cc-401">*그림 24-다이렉트 라우팅 (Office 365)-2 개의 테 넌 트를 통해 PSTN 연결 통화*</span><span class="sxs-lookup"><span data-stu-id="e01cc-401">*Figure 24 - Direct Routing (media through Office 365) – PSTN hairpin call across two tenants*</span></span>
 
<span data-ttu-id="e01cc-402">다음 사항에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="e01cc-402">Note that:</span></span>

- <span data-ttu-id="e01cc-403">SBC에는 Office 365에서 라우팅할 수 있는 공용 IP 주소가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-403">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="e01cc-404">SBC에서 Office 365로 신호를 보내고 그 반대의 경우 흐름 4 및/또는 흐름 4를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-404">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="e01cc-405">클라이언트가 PSTN에서 PSTN으로 전화를 hairpinned 후 신호 및 미디어 루프를 벗어났습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-405">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="e01cc-406">고객 네트워크 X의 sbc 인스턴스 B에 있는 SBC 인스턴스 A의 미디어는 Office 365 미디어 서버를 통해 릴레이 되어야 하며 우회 모드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-406">Media from SBC instance A within the customer network X to SBC instance B must be relayed through the Office 365 Media Server and can't use bypass mode.</span></span>

## <a name="teams-with-express-route-optimization"></a><span data-ttu-id="e01cc-407">Express 경로 최적화를 사용 하는 팀</span><span class="sxs-lookup"><span data-stu-id="e01cc-407">Teams with Express Route optimization</span></span>

<span data-ttu-id="e01cc-408">[![Microsoft 팀 온라인 통화 흐름 그림 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-408">[![Microsoft Teams Online Call Flows Figure 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span></span>

<span data-ttu-id="e01cc-409">*그림 25-Express 경로 최적화를 사용 하는 팀*</span><span class="sxs-lookup"><span data-stu-id="e01cc-409">*Figure 25 - Teams with Express Route optimization*</span></span>
 
<span data-ttu-id="e01cc-410">Express 경로를 정당화 및 배포 하는 경우 팀 흐름이 흐름 4에서 흐름 1, 흐름 4 '에서 흐름 1 '으로 다시 라우팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-410">In the case that Express Route is justified and deployed, then Teams flows could be re-routed from flow 4 to flow 1 and from flow 4' to flow 1'.</span></span> <span data-ttu-id="e01cc-411">그러나 팀 응용 프로그램에는 다른 Office 365에서 흐름 4 및 4를 통해 인터넷을 통해 전달 되는 하드 종속성이 있습니다. 따라서 이러한 흐름은 차단 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-411">However, Teams Application has a hard dependency on other Office 365 flows over the internet via flows 4 and 4'; hence these flows must not be blocked.</span></span> 

<span data-ttu-id="e01cc-412">비즈니스용 Skype 하이브리드 Edge 트래픽은 인터넷으로 라우팅되며, 외부 사용자와 통신 하 고 다른 테 넌 트와 페더레이션 하기 위해 경로를 표현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-412">Note that Skype for Business hybrid Edge traffic is routed to the Internet and not to Express Route to communicate with external users and federate with other tenants.</span></span> 

<span data-ttu-id="e01cc-413">비대칭 흐름을 방지 하려면 다시 라우팅이 양방향으로 진행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-413">To prevent asymmetrical flows, re-routing must be in both directions.</span></span> <span data-ttu-id="e01cc-414">즉, 고객 네트워크 내의 주소는 최적화에 기반 하 여 인터넷 또는 Express 경로를 통해 라우팅할 수 있지만 두 가지를 모두 사용 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-414">In other words, an address within the customer network is routable either through Internet or Express Route, based on optimization, but not through both.</span></span>

<span data-ttu-id="e01cc-415">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-415">For example:</span></span>

<span data-ttu-id="e01cc-416">**외부 사용자에 대 한 고객 네트워크 (팀에서 전송 릴레이가 전달 하는 미디어 릴레이):**</span><span class="sxs-lookup"><span data-stu-id="e01cc-416">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="e01cc-417">[![Microsoft 팀 온라인 통화 흐름 그림 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span><span class="sxs-lookup"><span data-stu-id="e01cc-417">[![Microsoft Teams Online Call Flows Figure 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span></span>

<span data-ttu-id="e01cc-418">*그림 26-외부 사용자에 대 한 고객 네트워크 (팀에서 전송 릴레이가 전달 하는 미디어 릴레이)*</span><span class="sxs-lookup"><span data-stu-id="e01cc-418">*Figure 26 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="e01cc-419">**상위 수준 단계:**</span><span class="sxs-lookup"><span data-stu-id="e01cc-419">**High Level Steps:**</span></span>
1. <span data-ttu-id="e01cc-420">고객 네트워크 내의 팀 사용자가 flow2를 통해 DNS (URL 도메인 이름)를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-420">Teams User within customer network resolves URL domain name (DNS) via flow2</span></span>
2. <span data-ttu-id="e01cc-421">고객 네트워크 내의 팀 사용자는 흐름 1을 통해 팀의 전송 릴레이가 미디어 릴레이 포트를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-421">Teams User within customer network allocates a media Relay port on Teams Transport Relay via flow 1</span></span>
3. <span data-ttu-id="e01cc-422">고객 네트워크 내의 팀 사용자는 흐름 1을 통해 Office 365를 통해 "초대"를 얼음 후보로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-422">Teams User within customer network sends "invite" with ICE candidates via flow 1 to Office 365</span></span>
4. <span data-ttu-id="e01cc-423">OFFICE 365에서는 흐름 3을 통해 외부 팀 사용자에 게 알림을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-423">OFFICE 365 sends notification to external Teams user via flow 3</span></span>
5. <span data-ttu-id="e01cc-424">팀 외부 사용자는 흐름 3을 통해 팀의 전송 릴레이에 미디어 릴레이 포트를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-424">Teams external user allocates a media Relay port on Teams Transport Relay via flow 3</span></span>
6. <span data-ttu-id="e01cc-425">팀 외부 사용자는 흐름 3을 통해 ICE 후보자와 "answer"를 전송 하 여 흐름 1 사용자 A로 다시 착신 전환 되는를 팀에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-425">Teams external user sends "answer" with ICE candidates via flow 3, which is forwarded back to Teams user A via Flow 1</span></span>
7. <span data-ttu-id="e01cc-426">팀 사용자 A 및 팀 사용자 B가 ICE connectivity 테스트를 호출 하 고, Office 365의 팀 전송 릴레이가 릴레이할 흐름 1 및 3을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-426">Teams User A and Teams User B invoke ICE connectivity tests and selects flows 1 and 3, which are relayed by Teams Transport Relay in Office 365</span></span>
8. <span data-ttu-id="e01cc-427">팀 사용자는 흐름 1 및 3을 통해 Office 365에 원격 분석을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-427">Teams Users send telemetry to Office 365 via flows 1 and 3</span></span>

><span data-ttu-id="e01cc-428">**참고**: 흐름 4를 요구 하는 다른 마이크로 서비스에서 팀 응용 프로그램에 대 한 종속성을 지원 하려면 흐름 4를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e01cc-428">**Note**: Flow 4 must be enabled to support dependencies of Teams application on other micro-services that mandates flow 4.</span></span>
