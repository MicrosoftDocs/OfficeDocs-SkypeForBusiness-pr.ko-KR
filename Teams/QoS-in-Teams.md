---
title: Microsoft 팀에서 서비스 품질 구현
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Microsoft 팀의 QoS (서비스 품질)에 대 한 조직의 네트워크를 준비 하는 방법에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52b1d03be3e5d54260084bbf44ad6695404607c9
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766581"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a><span data-ttu-id="d0dca-103">Microsoft 팀에서 QoS (서비스 품질) 구현</span><span class="sxs-lookup"><span data-stu-id="d0dca-103">Implement Quality of Service (QoS) in Microsoft Teams</span></span>

<span data-ttu-id="d0dca-104">Microsoft 팀의 QoS (서비스 품질)를 사용 하면 네트워크 지연 (예: 음성 또는 비디오 스트림)에 영향을 주는 실시간 네트워크 트래픽이 중요 하지 않은 트래픽 앞 (즉, 다운로드 하는 추가 초가 큰 문제가 아닌 경우 새 앱 다운로드)로 "줄이 잘린" 것으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-104">Quality of Service (QoS) in Microsoft Teams allows real-time network traffic that's sensitive to network delays (for example, voice or video streams) to "cut in line" in front of traffic that's less sensitive (like downloading a new app, where an extra second to download isn't a large deal).</span></span> <span data-ttu-id="d0dca-105">QoS는 Windows 그룹 정책 개체와 포트 기반 액세스 제어 목록을 사용 하 여 실시간 스트림에서 모든 패킷을 식별 하 고 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-105">QoS uses Windows Group Policy Objects and Port-based Access Control Lists to identify and mark all packets in real-time streams.</span></span> <span data-ttu-id="d0dca-106">이는 네트워크에서 음성, 비디오, 화면 공유 스트림을 네트워크 대역폭의 전용 부분으로 제공 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-106">This helps your network to give voice, video, and screen share streams a dedicated portion of network bandwidth.</span></span>

<span data-ttu-id="d0dca-107">이 문서에 설명 된 문제가 발생 하는 대규모 사용자 그룹을 지 원하는 경우 QoS를 구현 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-107">If you support a large group of users who are experiencing any of the problems described in this article, then you probably need to implement QoS.</span></span> <span data-ttu-id="d0dca-108">사용자 수가 적은 소규모 기업에는 QoS가 필요 하지 않을 수 있지만,이 경우에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-108">A small business with few users might not need QoS, but even there it should be helpful.</span></span>

<span data-ttu-id="d0dca-109">일부 QoS 형식이 없는 경우 다음과 같은 음성 및 비디오의 품질 문제가 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-109">Without some form of QoS, you might see the following quality issues in voice and video:</span></span>

- <span data-ttu-id="d0dca-110">지터 – 다른 요금으로 도착 하는 미디어 패킷으로,이로 인해 통화에 단어나 음절이 누락 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-110">Jitter – media packets arriving at different rates, which can result in missing words or syllables in calls</span></span>
- <span data-ttu-id="d0dca-111">패킷 손실 – 손실 된 패킷, 음성 품질을 낮추고 음성을 이해 하기 어려울 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-111">Packet loss – packets dropped, which can also result in lower voice quality and hard to understand speech</span></span>
- <span data-ttu-id="d0dca-112">지연 왕복 시간 (RTT) – 대상에 도달 하는 데 오랜 시간이 소요 되는 미디어 패킷이 있어 대화 중 두 당사자 간의 지연이 눈에 띄게 하 고 다른 사람들이 서로 대화를 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-112">Delayed round-trip time (RTT) – media packets taking a long time to reach their destinations, which result in noticeable delays between two parties in a conversation and causes people to talk over each other</span></span>

<span data-ttu-id="d0dca-113">이러한 문제를 해결 하는 가장 복잡 한 방법은 인터넷을 통해 내부와 외부 모두 데이터 연결의 크기를 늘리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-113">The least complex way to address these issues is to increase the size of the data connections, both internally and out to the internet.</span></span> <span data-ttu-id="d0dca-114">QoS는 대개 비용을 초과 하기 때문에 대역폭을 추가 하는 대신 사용 하는 리소스를 보다 효과적으로 관리 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-114">Since that is often cost-prohibitive, QoS provides a way to more effectively manage the resources you have instead of adding bandwidth.</span></span> <span data-ttu-id="d0dca-115">품질 문제를 해결 하려면 먼저 QoS를 사용 하 고 필요한 경우에만 대역폭을 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-115">To address quality issues, we recommend that you first use QoS, then add bandwidth only where necessary.</span></span>

<span data-ttu-id="d0dca-116">QoS가 유효 하려면 조직 전체에 일관 된 QoS 설정을 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-116">For QoS to be effective, you must apply consistent QoS settings throughout your organization.</span></span> <span data-ttu-id="d0dca-117">QoS 우선 순위를 지원 하지 않는 경로의 일부는 통화, 비디오, 화면 공유의 품질을 저하 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-117">Any part of the path that fails to support your QoS priorities can degrade the quality of calls, video, and screen sharing.</span></span> <span data-ttu-id="d0dca-118">여기에는 모든 사용자 Pc 또는 장치, 네트워크 스위치, 인터넷 라우터에, 팀 서비스에 설정을 적용 하는 것이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-118">This includes applying settings to all user PCs or devices, network switches, routers to the internet, and the Teams service.</span></span>

<span data-ttu-id="d0dca-119">_그림 1. 조직의 네트워크와 Microsoft 365 또는 Office 365 서비스 간의 관계_</span><span class="sxs-lookup"><span data-stu-id="d0dca-119">_Figure 1. The relationship between an organization's networks and Microsoft 365 or Office 365 services_</span></span>

<span data-ttu-id="d0dca-120">![네트워크와 서비스 간의 관계를 보여 주는 그림](media/Qos-in-Teams-Image1.png "조직의 네트워크와 Microsoft 365 또는 Office 365 서비스 간의 관계: 온-프레미스 네트워크 및 장치는 interconnect 네트워크로 연결 되며,이는 다시 Microsoft 365 또는 Office 365 클라우드 음성 및 오디오 회의 서비스와 연결 됩니다.")</span><span class="sxs-lookup"><span data-stu-id="d0dca-120">![Illustration of the relationship between networks and services](media/Qos-in-Teams-Image1.png "The relationship between an organization's networks and Microsoft 365 or Office 365 services: on-premises network and devices connect with an interconnect network, which in turn connects with Microsoft 365 or Office 365 Cloud Voice and Audio Conferencing services.")</span></span>

## <a name="qos-implementation-checklist"></a><span data-ttu-id="d0dca-121">QoS 구현 검사 목록</span><span class="sxs-lookup"><span data-stu-id="d0dca-121">QoS implementation checklist</span></span>

<span data-ttu-id="d0dca-122">높은 수준에서 QoS를 구현 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-122">At a high level, do the following to implement QoS:</span></span>

1. [<span data-ttu-id="d0dca-123">네트워크가 준비 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="d0dca-123">Make sure your network is ready</span></span>](#make-sure-your-network-is-ready)

1. [<span data-ttu-id="d0dca-124">QoS 구현 방법 선택</span><span class="sxs-lookup"><span data-stu-id="d0dca-124">Select a QoS implementation method</span></span>](#select-a-qos-implementation-method)

1. [<span data-ttu-id="d0dca-125">각 미디어 유형의 초기 포트 범위 선택</span><span class="sxs-lookup"><span data-stu-id="d0dca-125">Choose initial port ranges for each media type</span></span>](#choose-initial-port-ranges-for-each-media-type)

1. <span data-ttu-id="d0dca-126">QoS 설정 구현:</span><span class="sxs-lookup"><span data-stu-id="d0dca-126">Implement QoS settings:</span></span>
   1. <span data-ttu-id="d0dca-127">GPO (그룹 정책 개체)를 사용 하 여 [클라이언트 장치 포트 범위 및 표식을 설정](QoS-in-Teams-clients.md) 하는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="d0dca-127">On clients using a Group Policy Object (GPO) to [set client device port ranges and markings](QoS-in-Teams-clients.md)</span></span>
   2. <span data-ttu-id="d0dca-128">라우터 (제조업체 설명서 참조) 또는 기타 네트워크 장치</span><span class="sxs-lookup"><span data-stu-id="d0dca-128">On routers (see the manufacturer documentation) or other network devices.</span></span> <span data-ttu-id="d0dca-129">여기에는 포트 기반 Acl (액세스 제어 목록)이 포함 되거나 QoS 큐 및 DSCP 표시 또는 이러한 모든 항목을 정의할 수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-129">This might include port-based Access Control Lists (ACLs) or simply defining the QoS queues and DSCP markings, or all of these.</span></span>

      > [!IMPORTANT]
      > <span data-ttu-id="d0dca-130">클라이언트 원본 포트와 "모든"의 원본 및 대상 IP 주소를 사용 하 여 이러한 QoS 정책을 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-130">We recommend implementing these QoS policies using the client source ports and a source and destination IP address of “any.”</span></span> <span data-ttu-id="d0dca-131">이렇게 하면 내부 네트워크의 들어오고 나가는 미디어 소통량이 모두 포착 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-131">This will catch both incoming and outgoing media traffic on the internal network.</span></span>  

   3. [<span data-ttu-id="d0dca-132">팀 모임에 대 한 미디어 트래픽을 처리 하는 방법을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-132">Set how you want to handle media traffic for Teams meetings</span></span>](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. <span data-ttu-id="d0dca-133">네트워크에서 팀 트래픽을 분석 하 여 [QoS 구현에 대 한 유효성을 검사](#validate-your-qos-implementation) 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-133">[Validate your QoS implementation](#validate-your-qos-implementation) by analyzing Teams traffic on the network.</span></span>

<span data-ttu-id="d0dca-134">QoS를 구현할 준비가 되 면 다음 지침을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-134">As you prepare to implement QoS, keep the following guidelines in mind:</span></span>

- <span data-ttu-id="d0dca-135">Microsoft 365의 최단 경로는 가장 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-135">The shortest path to Microsoft 365 is best</span></span>
- <span data-ttu-id="d0dca-136">포트를 닫으면 음질이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-136">Closing ports will only lead to quality degradation</span></span>
- <span data-ttu-id="d0dca-137">프록시 등의 장애를 하는 것은 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-137">Any obstacles in between, such as proxies, aren't recommended</span></span>
- <span data-ttu-id="d0dca-138">홉 수 제한:</span><span class="sxs-lookup"><span data-stu-id="d0dca-138">Limit the number of hops:</span></span>
  - <span data-ttu-id="d0dca-139">클라이언트-네트워크에 지-3 ~ 5 홉</span><span class="sxs-lookup"><span data-stu-id="d0dca-139">Client to network edge – 3 to 5 hops</span></span>
  - <span data-ttu-id="d0dca-140">ISP-Microsoft 네트워크에 지-3 홉</span><span class="sxs-lookup"><span data-stu-id="d0dca-140">ISP to Microsoft network edge – 3 hops</span></span>
  - <span data-ttu-id="d0dca-141">Microsoft 네트워크 edge에서 최종 목적지까지-관련이 없음</span><span class="sxs-lookup"><span data-stu-id="d0dca-141">Microsoft network edge to final destination – irrelevant</span></span>

<span data-ttu-id="d0dca-142">방화벽 포트를 구성 하는 방법에 대 한 자세한 내용은 [Office 365 url 및 IP 범위로](office-365-urls-ip-address-ranges.md)이동 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0dca-142">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

## <a name="make-sure-your-network-is-ready"></a><span data-ttu-id="d0dca-143">네트워크가 준비 되었는지 확인</span><span class="sxs-lookup"><span data-stu-id="d0dca-143">Make sure your network is ready</span></span>

<span data-ttu-id="d0dca-144">QoS 구현을 고려 하는 경우에는 이미 대역폭 요구 사항 및 기타 [네트워크 요구 사항을](prepare-network.md)결정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-144">If you're considering a QoS implementation, you should already have determined your bandwidth requirements and other [network requirements](prepare-network.md).</span></span>
  
<span data-ttu-id="d0dca-145">네트워크를 통한 트래픽 정체는 미디어 품질에 큰 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-145">Traffic congestion across a network will greatly impact media quality.</span></span> <span data-ttu-id="d0dca-146">대역폭 부족으로 인해 성능이 저하 되 고 사용자 환경이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-146">A lack of bandwidth leads to performance degradation and a poor user experience.</span></span> <span data-ttu-id="d0dca-147">팀을 도입 하 고 사용 하는 데는 보고, 사용자별 [통화 분석](use-call-analytics-to-troubleshoot-poor-call-quality.md), [통화 품질 대시보드 (cqd)](turning-on-and-using-call-quality-dashboard.md) 를 사용 하 여 문제를 식별 하 고 QoS 및 선택적 대역폭 추가를 사용 하 여 조정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-147">As Teams adoption and usage grows, use reporting, [per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md), and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to identify problems and then make adjustments using QoS and selective bandwidth additions.</span></span>

### <a name="vpn-considerations"></a><span data-ttu-id="d0dca-148">VPN 고려 사항</span><span class="sxs-lookup"><span data-stu-id="d0dca-148">VPN considerations</span></span>

<span data-ttu-id="d0dca-149">QoS는 호출자 간의 모든 링크에서 구현 되는 경우 예상 대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-149">QoS only works as expected when implemented on all links between callers.</span></span> <span data-ttu-id="d0dca-150">내부 네트워크에서 QoS를 사용 하 고 사용자가 원격 위치에서 로그인 하는 경우 내부 관리 네트워크 내 에서만 우선 순위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-150">If you use QoS on an internal network and a user signs in from a remote location, you can only prioritize within your internal, managed network.</span></span> <span data-ttu-id="d0dca-151">원격 위치에서 VPN (가상 사설망)을 구현 하 여 관리 되는 연결을 받을 수 있지만 VPN은 본질적으로 패킷 오버 헤드를 추가 하 고 실시간 트래픽에 대 한 지연을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-151">Although remote locations can receive a managed connection by implementing a virtual private network (VPN),  a VPN inherently adds packet overhead and creates delays in real-time traffic.</span></span> <span data-ttu-id="d0dca-152">VPN을 통해 실시간 통신 소통량을 실행 하는 것을 방지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-152">We  recommend that you avoid running real-time communications traffic over a VPN.</span></span>

<span data-ttu-id="d0dca-153">대륙에 걸친 관리 링크가 있는 전역 조직에서는 이러한 링크에 대 한 대역폭이 LAN에 비해 제한 되어 있으므로 QoS를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-153">In a global organization with managed links that span continents, we strongly recommend QoS because bandwidth for those links is limited in comparison to the LAN.</span></span>

## <a name="introduction-to-qos-queues"></a><span data-ttu-id="d0dca-154">QoS 큐 소개</span><span class="sxs-lookup"><span data-stu-id="d0dca-154">Introduction to QoS queues</span></span>

<span data-ttu-id="d0dca-155">QoS를 제공 하려면 네트워크 장치에 트래픽을 분류 하는 방법이 있어야 하며 다른 네트워크 트래픽과 음성 또는 비디오를 구별할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-155">To provide QoS, network devices must have a way to classify traffic and must be able to distinguish voice or video from other network traffic.</span></span>

<span data-ttu-id="d0dca-156">네트워크 트래픽이 라우터로 들어가면 소통량이 대기열에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-156">When network traffic enters a router, the traffic is placed into a queue.</span></span> <span data-ttu-id="d0dca-157">QoS 정책이 구성 되지 않은 경우 하나의 큐만 있으며 모든 데이터는 동일한 우선 순위로 첫 번째 항목으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-157">If a QoS policy isn't configured, there is only one queue, and all data is treated as first-in, first-out with the same priority.</span></span> <span data-ttu-id="d0dca-158">즉, 지연 하는 것이 매우 중요 한 음성 소통량이 발생 하는 것은 몇 가지 추가 밀리초의 지연이 문제가 되지 않는 트래픽 뒤에 있을 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-158">That means voice traffic (which is very sensitive to delays) might get stuck behind traffic where a delay of a few extra milliseconds wouldn't be a problem.</span></span>

<span data-ttu-id="d0dca-159">QoS를 구현할 때 Cisco의 우선 순위 대기열 및 [클래스 기반 가중치가 지정 공정 (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) 및 혼잡 방지 기능 (예: 가중치가 지정 된 [임의 조기 검색) (wred)](https://en.wikipedia.org/wiki/Weighted_random_early_detection)등의 여러 혼잡 관리 기능 중 하나를 사용 하 여 여러 개의 큐를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-159">When you implement QoS, you define multiple queues using one of several congestion management features, such as Cisco’s priority queuing and [Class-Based Weighted Fair Queueing (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) and congestion avoidance features, such as [weighted random early detection (WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection).</span></span>

<span data-ttu-id="d0dca-160">_그림 2. QoS 큐의 예_</span><span class="sxs-lookup"><span data-stu-id="d0dca-160">_Figure 2. Examples of QoS queues_</span></span>

<span data-ttu-id="d0dca-161">![QoS 큐 및 대역폭 디비전 그림](media/Qos-in-Teams-Image2.png "사용할 수 있는 총 대역폭이 서로 다른 우선 순위를 할당 한 여러 큐 (오디오, 비디오 및 기타 트래픽) 간에 나뉘어 있습니다.")</span><span class="sxs-lookup"><span data-stu-id="d0dca-161">![Illustration of QoS queues and bandwidth division](media/Qos-in-Teams-Image2.png "Total available bandwidth is divided among multiple queues—audio, video, and other traffic—that have been assigned different priorities.")</span></span>

<span data-ttu-id="d0dca-162">간단한 비유는 QoS에서 데이터 네트워크에 가상 "carpool 레인"을 만들기 때문에 일부 데이터 형식에는 지연이 발생 하지 않을 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-162">A simple analogy is that QoS creates virtual "carpool lanes" in your data network so some types of data never or rarely encounter a delay.</span></span> <span data-ttu-id="d0dca-163">이러한 레인을 만든 후에는 해당 하는 상대적 크기를 조정할 수 있으며, 사용자에 게 제공 되는 연결 대역폭을 더욱 효과적으로 관리 하는 동시에 조직에서 사용 하는 비즈니스에 대 한 환경을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-163">Once you create those lanes, you can adjust their relative size and much more effectively manage the connection bandwidth you have, while still delivering business-grade experiences for your organization's users.</span></span>

## <a name="select-a-qos-implementation-method"></a><span data-ttu-id="d0dca-164">QoS 구현 방법 선택</span><span class="sxs-lookup"><span data-stu-id="d0dca-164">Select a QoS implementation method</span></span>

<span data-ttu-id="d0dca-165">네트워크 라우터의 Acl (액세스 제어 목록)을 사용 하 여 포트 기반 태깅을 통해 QoS를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-165">You could implement QoS via port-based tagging, using Access Control Lists (ACLs) on your network's routers.</span></span> <span data-ttu-id="d0dca-166">포트 기반 태깅은 혼합 Windows, Mac 및 Linux 환경에서 작동 하 고 구현 하기가 가장 쉽고 가장 신뢰할 수 있는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-166">Port-based tagging is the most reliable method because it works in mixed Windows, Mac, and Linux environments and is the easiest to implement.</span></span> <span data-ttu-id="d0dca-167">모바일 클라이언트는 DSCP 값을 사용 하 여 트래픽을 표시 하는 메커니즘을 제공 하지 않으므로이 방법이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-167">Mobile clients don't provide a mechanism to mark traffic by using DSCP values, so they'll require this method.</span></span>  

<span data-ttu-id="d0dca-168">포트 기반 태깅을 사용 하면 네트워크 라우터가 들어오는 패킷을 검사 하 고, 특정 포트 또는 포트 범위를 사용 하 여 패킷이 도착 하는 경우, 다른 장치가 해당 트래픽 유형을 인식 하 고 해당 사용자의 큐에 우선 순위를 지정할 수 있도록 IP 패킷 헤더에 미리 정의 된 [DSCP](https://tools.ietf.org/html/rfc2474) 표시를 추가 하 여 해당 형식의 큐에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-168">Using port-based tagging, your network's router examines an incoming packet, and if the packet arrived using a certain port or range of ports, it identifies it as a certain media type and puts it in the queue for that type, adding a predetermined [DSCP](https://tools.ietf.org/html/rfc2474) mark to the IP Packet header so other devices can recognize its traffic type and give it priority in their queue.</span></span>

<span data-ttu-id="d0dca-169">포트 기반 태그는 플랫폼에서 작동 하지만 WAN edge의 트래픽만 클라이언트 컴퓨터에 표시 되는 것이 아니라 관리 오버 헤드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-169">Although port-based tagging works across platforms, it only marks traffic at the WAN edge (not all the way to the client machine) and creates management overhead.</span></span> <span data-ttu-id="d0dca-170">이 방법을 구현 하는 방법에 대 한 지침은 라우터 제조업체에서 제공 하는 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0dca-170">Refer to the documentation provided by the router manufacturer for instructions on implementing this method.</span></span>

### <a name="insert-dscp-markers"></a><span data-ttu-id="d0dca-171">DSCP 표식 삽입</span><span class="sxs-lookup"><span data-stu-id="d0dca-171">Insert DSCP markers</span></span>

<span data-ttu-id="d0dca-172">또한 GPO (그룹 정책 개체)를 사용 하 여 클라이언트 장치를 특정 유형의 트래픽 (예: 음성)으로 식별 하는 IP 패킷 헤더에 DSCP 마커를 삽입 하도록 하 여 QoS를 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-172">You could also implement QoS by using a Group Policy Object (GPO) to direct client devices to insert a DSCP marker in IP packet headers identifying it as particular type of traffic (for example, voice).</span></span> <span data-ttu-id="d0dca-173">라우터 및 기타 네트워크 장치가이를 인식 하 고 우선 순위가 높은 별도의 큐에 트래픽을 전송 하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-173">Routers and other network devices can be configured to recognize this and put the traffic in a separate, higher-priority queue.</span></span>

<span data-ttu-id="d0dca-174">이 시나리오는 완전히 유효 하지만 도메인에 가입 된 Windows 클라이언트에 대해서만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-174">Although this scenario is entirely valid, it will only work for domain-joined Windows clients.</span></span> <span data-ttu-id="d0dca-175">도메인에 가입 된 Windows 클라이언트가 아닌 모든 장치는 DSCP 태깅에 대해 사용 하도록 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-175">Any device that isn't a domain-joined Windows client won't be enabled for DSCP tagging.</span></span> <span data-ttu-id="d0dca-176">Mac OS와 같은 클라이언트는 하드 코딩 된 태그를 포함 하며 항상 트래픽에 태그를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-176">Clients such as Mac OS have hard-coded tags and will always tag traffic.</span></span>

<span data-ttu-id="d0dca-177">플러스 측면에서, GPO를 통해 DSCP 표시를 제어 하면 모든 도메인 참가 컴퓨터가 동일한 설정을 받고 관리자만 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-177">On the plus side, controlling the DSCP marking via GPO ensures that all domain-joined computers receive the same settings and that only an administrator can manage them.</span></span> <span data-ttu-id="d0dca-178">GPO를 사용할 수 있는 클라이언트는 원래 장치에서 태그가 지정 되 고, 구성 된 네트워크 디바이스는 DSCP 코드에서 실시간 스트림을 인식 하 고 적절 한 우선 순위를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-178">Clients that can use GPO will be tagged on the originating device, and then configured network devices can recognize the real-time stream by the DSCP code and give it an appropriate priority.</span></span>

### <a name="best-practice"></a><span data-ttu-id="d0dca-179">모범 사례</span><span class="sxs-lookup"><span data-stu-id="d0dca-179">Best practice</span></span>

<span data-ttu-id="d0dca-180">끝점 및 포트 기반 Acl (가능 하면 라우터의 경우)에 DSCP 표시를 조합 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-180">We recommend a combination of DSCP markings at the endpoint and port-based ACLs on routers, if possible.</span></span> <span data-ttu-id="d0dca-181">GPO를 사용 하 여 대부분의 클라이언트를 catch 하 고 포트 기반 DSCP 태깅을 사용 하면 모바일, Mac 및 다른 클라이언트가 계속 QoS 처리를 할 수 있습니다 (최소한 부분적).</span><span class="sxs-lookup"><span data-stu-id="d0dca-181">Using a GPO to catch the majority of clients, and also using port-based DSCP tagging will ensure that mobile, Mac, and other clients will still get QoS treatment (at least partially).</span></span>

<span data-ttu-id="d0dca-182">DSCP 표시는 우편 작업자에 게 배달이 얼마나 긴급 한지, 그리고 빠른 전달을 위해 정렬 하는 방법에 대 한 우표 스탬프로 likened 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-182">DSCP markings can be likened to postage stamps that indicate to postal workers how urgent the delivery is and how best to sort it for speedy delivery.</span></span> <span data-ttu-id="d0dca-183">실시간 미디어 스트림에 우선 순위를 부여 하도록 네트워크를 구성 하면 손실 된 패킷과 지연 패킷이 크게 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-183">Once you've configured your network to give priority to real-time media streams, lost packets and late packets should diminish greatly.</span></span>

<span data-ttu-id="d0dca-184">네트워크의 모든 장치가 동일한 분류, 표시 및 우선 순위를 사용 하는 경우 각 트래픽 형식에 사용 되는 큐에 할당 된 포트 범위 크기를 변경 하 여 지연, 손실 된 패킷 및 지터를 줄이거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-184">Once all devices in the network are using the same classifications, markings, and priorities, it's possible to reduce or eliminate delays, dropped packets, and jitter by changing the size of the port ranges assigned to the queues used for each traffic type.</span></span> <span data-ttu-id="d0dca-185">팀 관점에서 가장 중요 한 구성 단계는 패킷의 분류와 표시입니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-185">From the Teams perspective, the most important configuration step is the classification and marking of packets.</span></span> <span data-ttu-id="d0dca-186">그러나 종단 간 QoS를 성공적으로 수행 하려면 기본 네트워크 구성으로 응용 프로그램의 구성을 주의 해 서 정렬 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-186">However, for end-to-end QoS to be successful, you also need to carefully align the application's configuration with the underlying network configuration.</span></span> <span data-ttu-id="d0dca-187">QoS가 완벽 하 게 구현 되는 경우, 진행 중인 관리는 조직의 필요 성과 실제 사용량에 따라 각 트래픽 유형에 할당 된 포트 범위를 조정 하는 질문입니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-187">Once QoS is fully implemented, ongoing management is a question of adjusting the port ranges assigned to each traffic type based on your organization's needs and actual usage.</span></span>

## <a name="choose-initial-port-ranges-for-each-media-type"></a><span data-ttu-id="d0dca-188">각 미디어 유형의 초기 포트 범위 선택</span><span class="sxs-lookup"><span data-stu-id="d0dca-188">Choose initial port ranges for each media type</span></span>

<span data-ttu-id="d0dca-189">DSCP 값은 패킷 또는 스트림에 제공 되는 우선 순위 (dscp 표시가 클라이언트에 의해 할당 되는지 여부 또는 ACL 설정에 따라 네트워크 자체에 의해 지정 됨)에 대 한 우선순위를 구성 된 네트워크에 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-189">The DSCP value tells a correspondingly configured network what priority to give a packet or stream, whether the DSCP mark is assigned by clients or the network itself based on ACL settings.</span></span> <span data-ttu-id="d0dca-190">각 미디어 작업 부하에는 고유한 DSCP 값 (다른 서비스를 사용 하 여 DSCP 표시, 팀이 아닌 사용자 공유) 및 각 미디어 유형에 사용 되는 정의 된 별도의 포트 범위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-190">Each media workload gets its own unique DSCP value (other services might allow workloads to share a DSCP marking, Teams doesn't) and a defined and separate port range used for each media type.</span></span> <span data-ttu-id="d0dca-191">다른 환경에는 네트워크 작업의 우선 순위를 결정 하는 데 도움이 되는 기존 QoS 전략이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-191">Other environments might have an existing QoS strategy in place, which will help you determine the priority of network workloads.</span></span>

<span data-ttu-id="d0dca-192">다양 한 실시간 스트리밍 작업의 포트 범위에 대 한 상대적 크기는 해당 작업 부하 전용의 총 사용 가능 대역폭의 비율을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-192">The relative size of the port ranges for different real-time streaming workloads sets the proportion of the total available bandwidth dedicated to that workload.</span></span> <span data-ttu-id="d0dca-193">앞에서 설명한 우편으로 돌아가려면 "Air Mail" 스탬프가 있는 문자는 1 시간 내에 가장 가까운 공항으로, "대량 메일" 표시로 표시 된 작은 패키지는 여러 개의 트럭을 통해 여행 하기 전에 하루 동안 대기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-193">To return to our earlier postal analogy: a letter with an "Air Mail" stamp might get taken within an hour to the nearest airport, while a small package marked "Bulk Mail" mark can wait for a day before traveling over land on a series of trucks.</span></span>

<span data-ttu-id="d0dca-194">_권장 되는 초기 포트 범위_</span><span class="sxs-lookup"><span data-stu-id="d0dca-194">_Recommended initial port ranges_</span></span>

|<span data-ttu-id="d0dca-195">미디어 트래픽 유형</span><span class="sxs-lookup"><span data-stu-id="d0dca-195">Media traffic type</span></span>| <span data-ttu-id="d0dca-196">클라이언트 원본 포트 범위 </span><span class="sxs-lookup"><span data-stu-id="d0dca-196">Client source port range</span></span> |<span data-ttu-id="d0dca-197">프로토콜</span><span class="sxs-lookup"><span data-stu-id="d0dca-197">Protocol</span></span>|<span data-ttu-id="d0dca-198">DSCP 값</span><span class="sxs-lookup"><span data-stu-id="d0dca-198">DSCP value</span></span>|<span data-ttu-id="d0dca-199">DSCP 클래스</span><span class="sxs-lookup"><span data-stu-id="d0dca-199">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="d0dca-200">오디오</span><span class="sxs-lookup"><span data-stu-id="d0dca-200">Audio</span></span>| <span data-ttu-id="d0dca-201">50,000~50,019</span><span class="sxs-lookup"><span data-stu-id="d0dca-201">50,000–50,019</span></span>|<span data-ttu-id="d0dca-202">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="d0dca-202">TCP/UDP</span></span>|<span data-ttu-id="d0dca-203">46</span><span class="sxs-lookup"><span data-stu-id="d0dca-203">46</span></span>|<span data-ttu-id="d0dca-204">Expedited Forwarding(EF)</span><span class="sxs-lookup"><span data-stu-id="d0dca-204">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="d0dca-205">비디오</span><span class="sxs-lookup"><span data-stu-id="d0dca-205">Video</span></span>| <span data-ttu-id="d0dca-206">50,020~50,039</span><span class="sxs-lookup"><span data-stu-id="d0dca-206">50,020–50,039</span></span>|<span data-ttu-id="d0dca-207">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="d0dca-207">TCP/UDP</span></span>|<span data-ttu-id="d0dca-208">34</span><span class="sxs-lookup"><span data-stu-id="d0dca-208">34</span></span>|<span data-ttu-id="d0dca-209">Assured Forwarding(AF41)</span><span class="sxs-lookup"><span data-stu-id="d0dca-209">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="d0dca-210">응용 프로그램/화면 공유</span><span class="sxs-lookup"><span data-stu-id="d0dca-210">Application/Screen Sharing</span></span>| <span data-ttu-id="d0dca-211">50,040~50,059</span><span class="sxs-lookup"><span data-stu-id="d0dca-211">50,040–50,059</span></span>|<span data-ttu-id="d0dca-212">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="d0dca-212">TCP/UDP</span></span>|<span data-ttu-id="d0dca-213">awg</span><span class="sxs-lookup"><span data-stu-id="d0dca-213">18</span></span>|<span data-ttu-id="d0dca-214">Assured Forwarding(AF21)</span><span class="sxs-lookup"><span data-stu-id="d0dca-214">Assured Forwarding (AF21)</span></span>|
||||||

<span data-ttu-id="d0dca-215">이러한 설정을 사용할 때는 다음에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-215">Be aware of the following when you use these settings:</span></span>

- <span data-ttu-id="d0dca-216">향후에는 Express 경로를 구현 하 고 아직 QoS를 구현 하지 않은 경우에는 DSCP 값이 보낸 사람이 받는 사람에 게 동일 하도록 지침을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-216">If you plan to implement ExpressRoute in the future and haven't yet implemented QoS, we recommend that you follow the guidance so that DSCP values are the same from sender to receiver.</span></span>
- <span data-ttu-id="d0dca-217">모바일 클라이언트와 팀 디바이스를 비롯 한 모든 클라이언트는 이러한 포트 범위를 사용 하 고, 이러한 원본 포트 범위를 사용 하는 모든 DSCP 정책에 의해 영향을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-217">All clients, including mobile clients and Teams devices, will use these port ranges and will be affected by any DSCP policy you implement that uses these source port ranges.</span></span> <span data-ttu-id="d0dca-218">동적 포트를 계속 사용 하는 유일한 클라이언트는 브라우저 기반 클라이언트 (브라우저를 사용 하 여 참가자가 모임에 참가할 수 있도록 하는 클라이언트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-218">The only clients that will continue to use dynamic ports are the browser-based clients (clients that let participants join meetings by using their browsers).</span></span>
- <span data-ttu-id="d0dca-219">Mac 클라이언트는 동일한 포트 범위를 사용 하지만 오디오 (EF) 및 비디오 (AF41)에 하드 코드 된 값도 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-219">Although the Mac client uses the same port ranges, it also uses hard-coded values for audio (EF) and video (AF41).</span></span> <span data-ttu-id="d0dca-220">이러한 값은 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-220">These values aren't configurable.</span></span>
- <span data-ttu-id="d0dca-221">나중에 사용자 환경을 개선 하기 위해 포트 범위를 조정 해야 하는 경우 포트 범위가 겹칠 수 없으며 서로 인접해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-221">If you later need to adjust the port ranges to improve user experience, the port ranges can't overlap and should be adjacent to each other.</span></span>

## <a name="migrate-qos-to-teams"></a><span data-ttu-id="d0dca-222">팀에 QoS 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="d0dca-222">Migrate QoS to Teams</span></span>

<span data-ttu-id="d0dca-223">이전에 QoS 태깅 및 포트 범위를 포함 하 여 비즈니스용 Skype Online을 배포한 경우 지금 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-223">If you've previously deployed Skype for Business Online, including QoS tagging and port ranges, and are now deploying.</span></span> <span data-ttu-id="d0dca-224">팀은 기존 구성을 존중 하 고 비즈니스용 Skype 클라이언트와 동일한 포트 범위와 태그를 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-224">Teams, Teams will respect the existing configuration and will use the same port ranges and tagging as the Skype for Business client.</span></span> <span data-ttu-id="d0dca-225">대부분의 경우 추가 구성은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-225">In most cases, no additional configuration will be needed.</span></span>

> [!NOTE]
> <span data-ttu-id="d0dca-226">그룹 정책을 통해 응용 프로그램 이름 QoS 태그를 사용 하는 경우 응용 프로그램 이름으로 Teams.exe 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-226">If you're using Application Name QoS tagging via Group Policy, you must add Teams.exe as the application name.</span></span>

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a><span data-ttu-id="d0dca-227">PowerShell을 사용 하 여 Windows 팀에서 QoS 구현</span><span class="sxs-lookup"><span data-stu-id="d0dca-227">Implement QoS in Teams on Windows using PowerShell</span></span>

<span data-ttu-id="d0dca-228">**오디오에 대 한 QoS 설정**</span><span class="sxs-lookup"><span data-stu-id="d0dca-228">**Set QoS for audio**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000
-IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

<span data-ttu-id="d0dca-229">**비디오에 대 한 QoS 설정**</span><span class="sxs-lookup"><span data-stu-id="d0dca-229">**Set QoS for video**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020
-IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

<span data-ttu-id="d0dca-230">**공유에 대 한 QoS 설정**</span><span class="sxs-lookup"><span data-stu-id="d0dca-230">**Set QoS for sharing**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040
-IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a><span data-ttu-id="d0dca-231">팀 관리 센터의 원본 포트 관리</span><span class="sxs-lookup"><span data-stu-id="d0dca-231">Managing source ports in the Teams admin center</span></span>

<span data-ttu-id="d0dca-232">팀에서 여러 작업 부하에 사용 되는 QoS 원본 포트는 적극적으로 관리 되 고 필요에 따라 조정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-232">In Teams, QoS source ports used by the different workloads should be actively managed, and adjusted as necessary.</span></span> <span data-ttu-id="d0dca-233">[각 미디어 유형의 초기 포트 범위 선택](#choose-initial-port-ranges-for-each-media-type)에서 테이블을 참조 하면 포트 범위는 조정할 수 있지만 DSCP 표시는 구성 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-233">Referring to the table in [Choose initial port ranges for each media type](#choose-initial-port-ranges-for-each-media-type), the port ranges are adjustable, but the DSCP markings aren't configurable.</span></span> <span data-ttu-id="d0dca-234">이러한 설정을 구현한 후에는 지정 된 미디어 형식에 대해 더 많거나 적은 포트가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-234">Once you have implemented these settings, you might find that more or fewer ports are needed for a given media type.</span></span> <span data-ttu-id="d0dca-235">팀을 구현 하 고 주기적으로 변경 해야 하는 경우 포트 범위를 조정 하기로 결정 하는 데는 [사용자 단위 호출 분석](use-call-analytics-to-troubleshoot-poor-call-quality.md) 및 [call Quality 대시보드 (cqd)](turning-on-and-using-call-quality-dashboard.md) 를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-235">[Per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md) and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) should be used in making a decision to adjust port ranges after Teams has been implemented, and periodically as needs change.</span></span>

> [!NOTE]
> <span data-ttu-id="d0dca-236">비즈니스용 Skype Online에 대 한 원본 포트 범위 및 DSCP 표시를 기반으로 QoS를 이미 구성한 경우 팀에 [사용 되는 범위](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) 를 비즈니스용 skype online에 대해 구성 된 것과 일치 시 키 지 않도록 설정 해야 하는 것은 아니지만, 매핑에 대 한 추가 클라이언트 또는 네트워크 변경은 필요 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-236">If you've already configured QoS based on source port ranges and DSCP markings for Skype for Business Online, the same configuration will apply to Teams and no further client or network changes to the mapping will be required, though you may have to [set the ranges used in Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) to match what was configured for Skype for Business Online.</span></span>

<span data-ttu-id="d0dca-237">이전에 비즈니스용 Skype 서버를 온-프레미스로 배포한 경우에는 QoS 정책을 다시 검사 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-237">If you’ve previously deployed Skype for Business Server on-premises, you might need to re-examine your QoS policies.</span></span> <span data-ttu-id="d0dca-238">정책을 조정 하 여 팀에 대 한 품질 사용자 환경 제공을 확인 한 포트 범위 설정에 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-238">Adjust the policies to match port range settings you've verified provide a quality user experience for Teams.</span></span>

## <a name="validate-your-qos-implementation"></a><span data-ttu-id="d0dca-239">QoS 구현 확인</span><span class="sxs-lookup"><span data-stu-id="d0dca-239">Validate your QoS implementation</span></span>

<span data-ttu-id="d0dca-240">QoS가 유효 하기 위해서는 GPO가 설정 하는 DSCP 값이 통화의 양끝에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-240">For QoS to be effective, the DSCP value set by the GPO needs to be present at both ends of a call.</span></span> <span data-ttu-id="d0dca-241">팀 클라이언트에서 생성 된 트래픽을 분석 하 여 팀 작업 부하 트래픽이 네트워크를 통해 이동할 때 DSCP 값이 변경 되거나 제거 되지 않았는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-241">By analyzing the traffic generated by the Teams client, you can verify that the DSCP value isn’t changed or stripped out when the Teams workload traffic moves through the network.</span></span>

<span data-ttu-id="d0dca-242">가능 하면 네트워크 송신 지점에서 트래픽을 캡처 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0dca-242">Preferably, you capture traffic at the network egress point.</span></span> <span data-ttu-id="d0dca-243">스위치 또는 라우터에서 포트 미러링을 사용 하 여이 작업을 도울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0dca-243">You can use port mirroring on a switch or router to help with this.</span></span>

## <a name="implement-qos-for-other-devices"></a><span data-ttu-id="d0dca-244">다른 장치에 대 한 QoS 구현</span><span class="sxs-lookup"><span data-stu-id="d0dca-244">Implement QoS for other devices</span></span>

<span data-ttu-id="d0dca-245">Intune, Surface, iOS, Android 및 Mac 용 QoS를 구현 하는 방법에 대 한 자세한 내용은 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0dca-245">Read these topics for information about implementing QoS for Intune, Surface, iOS, Android, and Mac</span></span>

- [<span data-ttu-id="d0dca-246">Surface Hub 2S 용 QoS</span><span class="sxs-lookup"><span data-stu-id="d0dca-246">QoS for Surface Hub 2S</span></span>](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [<span data-ttu-id="d0dca-247">Surface Hub 용 QoS</span><span class="sxs-lookup"><span data-stu-id="d0dca-247">QoS for Surface Hub</span></span>](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [<span data-ttu-id="d0dca-248">IOS, Android 및 Mac의 QoS</span><span class="sxs-lookup"><span data-stu-id="d0dca-248">QoS for iOS, Android, and Mac</span></span>](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a><span data-ttu-id="d0dca-249">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d0dca-249">Related topics</span></span>

- [<span data-ttu-id="d0dca-250">비디오: 네트워크 계획</span><span class="sxs-lookup"><span data-stu-id="d0dca-250">Video: Network Planning</span></span>](https://aka.ms/teams-networking)

- [<span data-ttu-id="d0dca-251">Microsoft Teams에 대한 조직의 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="d0dca-251">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)

- [<span data-ttu-id="d0dca-252">팀 클라이언트에서 QoS 구현</span><span class="sxs-lookup"><span data-stu-id="d0dca-252">Implement QoS in the Teams client</span></span>](QoS-in-Teams-clients.md)
