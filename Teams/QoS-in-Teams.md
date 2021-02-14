---
title: Microsoft Teams에서 서비스 품질 구현
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Microsoft Teams에서 QoS(서비스 품질)에 대한 조직의 네트워크를 준비하는 방법에 대해 자세히 배워야 합니다.
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
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a><span data-ttu-id="ea14b-103">Microsoft Teams에서 QoS(서비스 품질) 구현</span><span class="sxs-lookup"><span data-stu-id="ea14b-103">Implement Quality of Service (QoS) in Microsoft Teams</span></span>

<span data-ttu-id="ea14b-104">Microsoft Teams의 QoS(서비스 품질)를 사용하면 네트워크 지연(예: 음성 또는 비디오 스트림)에 민감한 실시간 네트워크 트래픽이 덜 민감하지 않은 트래픽(예: 다운로드할 추가 초가 큰 거래가 아닌 새 앱 다운로드) 앞에서 "줄을 끊습니다".</span><span class="sxs-lookup"><span data-stu-id="ea14b-104">Quality of Service (QoS) in Microsoft Teams allows real-time network traffic that's sensitive to network delays (for example, voice or video streams) to "cut in line" in front of traffic that's less sensitive (like downloading a new app, where an extra second to download isn't a large deal).</span></span> <span data-ttu-id="ea14b-105">QoS는 Windows 그룹 정책 개체 및 포트 기반 Access Control 목록을 사용하여 실시간 스트림에서 모든 패킷을 식별하고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-105">QoS uses Windows Group Policy Objects and Port-based Access Control Lists to identify and mark all packets in real-time streams.</span></span> <span data-ttu-id="ea14b-106">이렇게 하면 네트워크에서 음성, 비디오 및 화면 공유 스트림을 네트워크 대역폭의 전용 부분으로 스트림할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-106">This helps your network to give voice, video, and screen share streams a dedicated portion of network bandwidth.</span></span>

<span data-ttu-id="ea14b-107">이 문서에 설명된 문제가 발생하는 대규모 사용자 그룹을 지원하는 경우 QoS를 구현해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-107">If you support a large group of users who are experiencing any of the problems described in this article, then you probably need to implement QoS.</span></span> <span data-ttu-id="ea14b-108">사용자 수가 적은 소규모 기업에서는 QoS가 필요하지 않을 수 있지만, 이 경우에도 도움이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-108">A small business with few users might not need QoS, but even there it should be helpful.</span></span>

<span data-ttu-id="ea14b-109">어떤 형태의 QoS가 없는 경우 음성 및 비디오에 다음과 같은 품질 문제가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-109">Without some form of QoS, you might see the following quality issues in voice and video:</span></span>

- <span data-ttu-id="ea14b-110">지터 – 다른 요금으로 도착하는 미디어 패킷으로 인해 호출 시 단어 또는 음성이 누락될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-110">Jitter – media packets arriving at different rates, which can result in missing words or syllables in calls</span></span>
- <span data-ttu-id="ea14b-111">패킷 손실 – 패킷이 삭제되어 음성 품질이 낮아지며 음성을 이해하기 어려워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-111">Packet loss – packets dropped, which can also result in lower voice quality and hard to understand speech</span></span>
- <span data-ttu-id="ea14b-112">지연된 RTT(왕복 시간) – 미디어 패킷이 대상에 도달하는 데 시간이 오래 오래 발생하여 대화의 두 당사자 간에 눈에 띄는 지연이 발생하고 사람들이 서로 대화하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-112">Delayed round-trip time (RTT) – media packets taking a long time to reach their destinations, which result in noticeable delays between two parties in a conversation and causes people to talk over each other</span></span>

<span data-ttu-id="ea14b-113">이러한 문제를 해결하기 위해 가장 복잡한 방법은 내부 및 외부 모두에서 데이터 연결의 크기를 늘리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-113">The least complex way to address these issues is to increase the size of the data connections, both internally and out to the internet.</span></span> <span data-ttu-id="ea14b-114">비용이 많이 들기 때문에 QoS는 대역폭을 추가하는 대신 사용자가 사용하는 리소스를 보다 효과적으로 관리하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-114">Since that is often cost-prohibitive, QoS provides a way to more effectively manage the resources you have instead of adding bandwidth.</span></span> <span data-ttu-id="ea14b-115">품질 문제를 해결하기 위해 먼저 QoS를 사용한 다음 필요한 경우 대역폭을 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-115">To address quality issues, we recommend that you first use QoS, then add bandwidth only where necessary.</span></span>

<span data-ttu-id="ea14b-116">QoS가 유효하려면 조직 전체에서 일관된 QoS 설정을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-116">For QoS to be effective, you must apply consistent QoS settings throughout your organization.</span></span> <span data-ttu-id="ea14b-117">QoS 우선 순위를 지원하지 못하는 경로의 일부로 인해 통화, 비디오 및 화면 공유 품질이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-117">Any part of the path that fails to support your QoS priorities can degrade the quality of calls, video, and screen sharing.</span></span> <span data-ttu-id="ea14b-118">여기에는 모든 사용자 PC 또는 장치에 설정 적용, 네트워크 스위치, 인터넷에 대한 라우터 및 Teams 서비스에 대한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-118">This includes applying settings to all user PCs or devices, network switches, routers to the internet, and the Teams service.</span></span>

<span data-ttu-id="ea14b-119">_그림 1. 조직의 네트워크와 Microsoft 365 또는 Office 365 서비스 간의 관계_</span><span class="sxs-lookup"><span data-stu-id="ea14b-119">_Figure 1. The relationship between an organization's networks and Microsoft 365 or Office 365 services_</span></span>

<span data-ttu-id="ea14b-120">![네트워크와 서비스 간의 관계 그림](media/Qos-in-Teams-Image1.png "조직의 네트워크와 Microsoft 365 또는 Office 365 서비스 간의 관계: 프레미스 네트워크와 디바이스는 상호 연결 네트워크와 연결됩니다. 이 네트워크는 Microsoft 365 또는 Office 365 Cloud Voice 및 오디오 회의 서비스와 연결됩니다.")</span><span class="sxs-lookup"><span data-stu-id="ea14b-120">![Illustration of the relationship between networks and services](media/Qos-in-Teams-Image1.png "The relationship between an organization's networks and Microsoft 365 or Office 365 services: on-premises network and devices connect with an interconnect network, which in turn connects with Microsoft 365 or Office 365 Cloud Voice and Audio Conferencing services.")</span></span>

## <a name="qos-implementation-checklist"></a><span data-ttu-id="ea14b-121">QoS 구현 검사 목록</span><span class="sxs-lookup"><span data-stu-id="ea14b-121">QoS implementation checklist</span></span>

<span data-ttu-id="ea14b-122">높은 수준에서 QoS를 구현하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-122">At a high level, do the following to implement QoS:</span></span>

1. [<span data-ttu-id="ea14b-123">네트워크가 준비되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="ea14b-123">Make sure your network is ready</span></span>](#make-sure-your-network-is-ready)

1. [<span data-ttu-id="ea14b-124">QoS 구현 방법 선택</span><span class="sxs-lookup"><span data-stu-id="ea14b-124">Select a QoS implementation method</span></span>](#select-a-qos-implementation-method)

1. [<span data-ttu-id="ea14b-125">각 미디어 유형에 대한 초기 포트 범위 선택</span><span class="sxs-lookup"><span data-stu-id="ea14b-125">Choose initial port ranges for each media type</span></span>](#choose-initial-port-ranges-for-each-media-type)

1. <span data-ttu-id="ea14b-126">QoS 설정 구현:</span><span class="sxs-lookup"><span data-stu-id="ea14b-126">Implement QoS settings:</span></span>
   1. <span data-ttu-id="ea14b-127">GPO(그룹 정책 개체)를 [](QoS-in-Teams-clients.md) 사용하여 클라이언트 디바이스 포트 범위 및 표시 설정</span><span class="sxs-lookup"><span data-stu-id="ea14b-127">On clients using a Group Policy Object (GPO) to [set client device port ranges and markings](QoS-in-Teams-clients.md)</span></span>
   2. <span data-ttu-id="ea14b-128">라우터(제조업체 설명서 참조) 또는 기타 네트워크 디바이스에서</span><span class="sxs-lookup"><span data-stu-id="ea14b-128">On routers (see the manufacturer documentation) or other network devices.</span></span> <span data-ttu-id="ea14b-129">여기에는 포트 기반 ACL(Access Control 목록)을 포함하거나 단순히 QoS 큐 및 DSCP 표시를 정의하거나 모두를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-129">This might include port-based Access Control Lists (ACLs) or simply defining the QoS queues and DSCP markings, or all of these.</span></span>

      > [!IMPORTANT]
      > <span data-ttu-id="ea14b-130">클라이언트 원본 포트 및 "모든"의 원본 및 대상 IP 주소를 사용하여 이러한 QoS 정책을 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-130">We recommend implementing these QoS policies using the client source ports and a source and destination IP address of “any.”</span></span> <span data-ttu-id="ea14b-131">내부 네트워크에서 들어오는 미디어 트래픽과 외부 미디어 트래픽을 모두 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-131">This will catch both incoming and outgoing media traffic on the internal network.</span></span>  

   3. [<span data-ttu-id="ea14b-132">Teams 모임의 미디어 트래픽을 처리하는 방법 설정</span><span class="sxs-lookup"><span data-stu-id="ea14b-132">Set how you want to handle media traffic for Teams meetings</span></span>](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. <span data-ttu-id="ea14b-133">[네트워크에서 Teams 트래픽을 분석하여 QoS](#validate-your-qos-implementation) 구현의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-133">[Validate your QoS implementation](#validate-your-qos-implementation) by analyzing Teams traffic on the network.</span></span>

<span data-ttu-id="ea14b-134">QoS를 구현할 준비를 할 때 다음 지침을 염두에 두세요.</span><span class="sxs-lookup"><span data-stu-id="ea14b-134">As you prepare to implement QoS, keep the following guidelines in mind:</span></span>

- <span data-ttu-id="ea14b-135">Microsoft 365에 대한 가장 짧은 경로가 가장 짧습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-135">The shortest path to Microsoft 365 is best</span></span>
- <span data-ttu-id="ea14b-136">포트를 닫는 경우 품질 저하만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-136">Closing ports will only lead to quality degradation</span></span>
- <span data-ttu-id="ea14b-137">두 장애물(예: proxies)은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-137">Any obstacles in between, such as proxies, aren't recommended</span></span>
- <span data-ttu-id="ea14b-138">홉 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-138">Limit the number of hops:</span></span>
  - <span data-ttu-id="ea14b-139">클라이언트-네트워크 에지 – 3~5개 홉</span><span class="sxs-lookup"><span data-stu-id="ea14b-139">Client to network edge – 3 to 5 hops</span></span>
  - <span data-ttu-id="ea14b-140">ISP-Microsoft 네트워크 에지 - 3개 홉</span><span class="sxs-lookup"><span data-stu-id="ea14b-140">ISP to Microsoft network edge – 3 hops</span></span>
  - <span data-ttu-id="ea14b-141">최종 대상에 대한 Microsoft 네트워크 에지 - 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-141">Microsoft network edge to final destination – irrelevant</span></span>

<span data-ttu-id="ea14b-142">방화벽 포트 구성에 대한 자세한 내용은 [Office 365 URL 및 IP 범위로 이동하세요.](office-365-urls-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="ea14b-142">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

## <a name="make-sure-your-network-is-ready"></a><span data-ttu-id="ea14b-143">네트워크가 준비되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="ea14b-143">Make sure your network is ready</span></span>

<span data-ttu-id="ea14b-144">QoS 구현을 고려하는 경우 대역폭 요구 사항 및 기타 네트워크 요구 사항을 이미 [결정해야 합니다.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="ea14b-144">If you're considering a QoS implementation, you should already have determined your bandwidth requirements and other [network requirements](prepare-network.md).</span></span>
  
<span data-ttu-id="ea14b-145">네트워크의 트래픽 정체는 미디어 품질에 큰 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-145">Traffic congestion across a network will greatly impact media quality.</span></span> <span data-ttu-id="ea14b-146">대역폭이 부족하면 성능 저하 및 사용자 환경 저하가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-146">A lack of bandwidth leads to performance degradation and a poor user experience.</span></span> <span data-ttu-id="ea14b-147">Teams 채택 및 사용이 증가함에 따라 [보고,](use-call-analytics-to-troubleshoot-poor-call-quality.md)사용자당 통화 분석 및 [CQD(통화](turning-on-and-using-call-quality-dashboard.md) 품질 대시보드)를 사용하여 문제를 식별한 다음 QoS 및 선택적 대역폭 추가를 사용하여 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-147">As Teams adoption and usage grows, use reporting, [per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md), and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to identify problems and then make adjustments using QoS and selective bandwidth additions.</span></span>

### <a name="vpn-considerations"></a><span data-ttu-id="ea14b-148">VPN 고려 사항</span><span class="sxs-lookup"><span data-stu-id="ea14b-148">VPN considerations</span></span>

<span data-ttu-id="ea14b-149">QoS는 호출자 간의 모든 링크에서 구현된 경우 예상대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-149">QoS only works as expected when implemented on all links between callers.</span></span> <span data-ttu-id="ea14b-150">내부 네트워크에서 QoS를 사용하며 사용자가 원격 위치에서 로그인하는 경우 관리되는 내부 네트워크 내에서만 우선 순위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-150">If you use QoS on an internal network and a user signs in from a remote location, you can only prioritize within your internal, managed network.</span></span> <span data-ttu-id="ea14b-151">원격 위치는 VPN(가상 사설망)을 구현하여 관리되는 연결을 받을 수 있습니다. VPN은 본질적으로 패킷 오버헤드를 추가하고 실시간 트래픽에 지연을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-151">Although remote locations can receive a managed connection by implementing a virtual private network (VPN),  a VPN inherently adds packet overhead and creates delays in real-time traffic.</span></span> <span data-ttu-id="ea14b-152">VPN을 통해 실시간 통신 트래픽을 실행하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-152">We  recommend that you avoid running real-time communications traffic over a VPN.</span></span>

<span data-ttu-id="ea14b-153">대륙에 걸쳐 관리되는 링크가 있는 글로벌 조직에서는 해당 링크에 대한 대역폭이 LAN에 비해 제한되어 있기 때문에 QoS를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-153">In a global organization with managed links that span continents, we strongly recommend QoS because bandwidth for those links is limited in comparison to the LAN.</span></span>

## <a name="introduction-to-qos-queues"></a><span data-ttu-id="ea14b-154">QoS 큐 소개</span><span class="sxs-lookup"><span data-stu-id="ea14b-154">Introduction to QoS queues</span></span>

<span data-ttu-id="ea14b-155">QoS를 제공하려면 네트워크 디바이스는 트래픽을 분류하는 방법이 있어야 합니다. 음성 또는 비디오를 다른 네트워크 트래픽과 구분할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-155">To provide QoS, network devices must have a way to classify traffic and must be able to distinguish voice or video from other network traffic.</span></span>

<span data-ttu-id="ea14b-156">네트워크 트래픽이 라우터에 들어오면 트래픽이 큐에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-156">When network traffic enters a router, the traffic is placed into a queue.</span></span> <span data-ttu-id="ea14b-157">QoS 정책이 구성되지 않은 경우 하나의 큐만 있으며 모든 데이터는 동일한 우선 순위를 사용하여 선출형으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-157">If a QoS policy isn't configured, there is only one queue, and all data is treated as first-in, first-out with the same priority.</span></span> <span data-ttu-id="ea14b-158">즉, 음성 트래픽(지연에 매우 민감)은 몇 밀리초의 지연이 문제가 될 수 없는 트래픽 뒤에 늦어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-158">That means voice traffic (which is very sensitive to delays) might get stuck behind traffic where a delay of a few extra milliseconds wouldn't be a problem.</span></span>

<span data-ttu-id="ea14b-159">QoS를 구현할 때 Cisco의 우선 순위 큐 및 [CBWFQ(Class-Based Weighted Fair Queueing)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) 및 정체 방지 기능(예: [WRED(가중](https://en.wikipedia.org/wiki/Weighted_random_early_detection)임의 임의 초기 검색))과 같은 여러 정체 관리 기능 중 하나를 사용하여 여러 큐를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-159">When you implement QoS, you define multiple queues using one of several congestion management features, such as Cisco’s priority queuing and [Class-Based Weighted Fair Queueing (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) and congestion avoidance features, such as [weighted random early detection (WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection).</span></span>

<span data-ttu-id="ea14b-160">_그림 2. QoS 큐의 예_</span><span class="sxs-lookup"><span data-stu-id="ea14b-160">_Figure 2. Examples of QoS queues_</span></span>

<span data-ttu-id="ea14b-161">![QoS 큐 및 대역폭 구분 그림](media/Qos-in-Teams-Image2.png "사용 가능한 총 대역폭은 다른 우선 순위가 할당된 여러 큐(오디오, 비디오 및 기타 트래픽)로 나뉘어 있습니다.")</span><span class="sxs-lookup"><span data-stu-id="ea14b-161">![Illustration of QoS queues and bandwidth division](media/Qos-in-Teams-Image2.png "Total available bandwidth is divided among multiple queues—audio, video, and other traffic—that have been assigned different priorities.")</span></span>

<span data-ttu-id="ea14b-162">간단한 비유는 QoS가 데이터 네트워크에 가상 "카풀 차선"을 만들어 일부 데이터 형식이 지연되지 않을 수도, 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-162">A simple analogy is that QoS creates virtual "carpool lanes" in your data network so some types of data never or rarely encounter a delay.</span></span> <span data-ttu-id="ea14b-163">이러한 차선이 만들어질 경우 조직의 사용자에게 비즈니스급 환경을 제공하면서 상대적 크기를 조정하고 사용하는 연결 대역폭을 훨씬 더 효과적으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-163">Once you create those lanes, you can adjust their relative size and much more effectively manage the connection bandwidth you have, while still delivering business-grade experiences for your organization's users.</span></span>

## <a name="select-a-qos-implementation-method"></a><span data-ttu-id="ea14b-164">QoS 구현 방법 선택</span><span class="sxs-lookup"><span data-stu-id="ea14b-164">Select a QoS implementation method</span></span>

<span data-ttu-id="ea14b-165">네트워크 라우터에서 ACL(Access Control List)을 사용하여 포트 기반 태그 지정을 통해 QoS를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-165">You could implement QoS via port-based tagging, using Access Control Lists (ACLs) on your network's routers.</span></span> <span data-ttu-id="ea14b-166">포트 기반 태그 지정은 혼합된 Windows, Mac 및 Linux 환경에서 작동하고 가장 쉽게 구현할 수 있기 때문에 가장 신뢰할 수 있는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-166">Port-based tagging is the most reliable method because it works in mixed Windows, Mac, and Linux environments and is the easiest to implement.</span></span> <span data-ttu-id="ea14b-167">모바일 클라이언트는 DSCP 값을 사용하여 트래픽을 표시하는 메커니즘을 제공하지 않습니다. 따라서 이 메서드가 필요하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-167">Mobile clients don't provide a mechanism to mark traffic by using DSCP values, so they'll require this method.</span></span>  

<span data-ttu-id="ea14b-168">포트 기반 태그 지정을 사용하여 네트워크의 라우터는 들어오는 패킷을 검사하고 패킷이 특정 포트 또는 포트 범위를 사용하여 도착한 경우 특정 미디어 유형으로 식별하고 해당 유형의 큐에 추가하여 다른 디바이스가 해당 트래픽 유형을 인식하고 큐에서 우선 순위를 부여할 수 있도록 미리 정해진 [DSCP](https://tools.ietf.org/html/rfc2474) 표시를 IP 패킷 헤더에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-168">Using port-based tagging, your network's router examines an incoming packet, and if the packet arrived using a certain port or range of ports, it identifies it as a certain media type and puts it in the queue for that type, adding a predetermined [DSCP](https://tools.ietf.org/html/rfc2474) mark to the IP Packet header so other devices can recognize its traffic type and give it priority in their queue.</span></span>

<span data-ttu-id="ea14b-169">포트 기반 태그 지정은 플랫폼에서 작동하나 WAN 에지에서 트래픽만 표시하고(클라이언트 컴퓨터까지는 아는 것이 아는) 관리 오버헤드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-169">Although port-based tagging works across platforms, it only marks traffic at the WAN edge (not all the way to the client machine) and creates management overhead.</span></span> <span data-ttu-id="ea14b-170">이 방법을 구현하는 방법에 대한 지침은 라우터 제조업체에서 제공하는 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea14b-170">Refer to the documentation provided by the router manufacturer for instructions on implementing this method.</span></span>

### <a name="insert-dscp-markers"></a><span data-ttu-id="ea14b-171">DSCP 표식 삽입</span><span class="sxs-lookup"><span data-stu-id="ea14b-171">Insert DSCP markers</span></span>

<span data-ttu-id="ea14b-172">GPO(그룹 정책 개체)를 사용하여 QoS를 구현하여 클라이언트 디바이스가 특정 유형의 트래픽(예: 음성)으로 식별하는 IP 패킷 헤더에 DSCP 마커를 삽입하게 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-172">You could also implement QoS by using a Group Policy Object (GPO) to direct client devices to insert a DSCP marker in IP packet headers identifying it as particular type of traffic (for example, voice).</span></span> <span data-ttu-id="ea14b-173">라우터 및 기타 네트워크 디바이스는 이를 인식하고 트래픽을 우선 순위가 높은 별도의 큐에 넣도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-173">Routers and other network devices can be configured to recognize this and put the traffic in a separate, higher-priority queue.</span></span>

<span data-ttu-id="ea14b-174">이 시나리오는 완전히 유효하기는 하지만 도메인에 가입된 Windows 클라이언트에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-174">Although this scenario is entirely valid, it will only work for domain-joined Windows clients.</span></span> <span data-ttu-id="ea14b-175">도메인에 가입된 Windows 클라이언트가 아닌 모든 디바이스는 DSCP 태그 지정에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-175">Any device that isn't a domain-joined Windows client won't be enabled for DSCP tagging.</span></span> <span data-ttu-id="ea14b-176">Mac OS와 같은 클라이언트에는 하드 코딩된 태그가 있으며 항상 트래픽에 태그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-176">Clients such as Mac OS have hard-coded tags and will always tag traffic.</span></span>

<span data-ttu-id="ea14b-177">더하기 쪽에서 GPO를 통해 DSCP 표시를 제어하면 도메인에 가입된 모든 컴퓨터가 동일한 설정을 받고 관리자만 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-177">On the plus side, controlling the DSCP marking via GPO ensures that all domain-joined computers receive the same settings and that only an administrator can manage them.</span></span> <span data-ttu-id="ea14b-178">GPO를 사용할 수 있는 클라이언트는 원래 디바이스에서 태그가 지정된 다음, 구성된 네트워크 디바이스는 DSCP 코드로 실시간 스트림을 인식하고 적절한 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-178">Clients that can use GPO will be tagged on the originating device, and then configured network devices can recognize the real-time stream by the DSCP code and give it an appropriate priority.</span></span>

### <a name="best-practice"></a><span data-ttu-id="ea14b-179">모범 사례</span><span class="sxs-lookup"><span data-stu-id="ea14b-179">Best practice</span></span>

<span data-ttu-id="ea14b-180">가능한 경우 엔드포인트의 DSCP 표시와 라우터의 포트 기반 ACL을 조합하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-180">We recommend a combination of DSCP markings at the endpoint and port-based ACLs on routers, if possible.</span></span> <span data-ttu-id="ea14b-181">GPO를 사용하여 대부분의 클라이언트를 catch하고 포트 기반 DSCP 태그 지정을 사용하면 모바일, Mac 및 기타 클라이언트가 QoS 처리를 계속 받을 수 있습니다(최소한 부분적으로).</span><span class="sxs-lookup"><span data-stu-id="ea14b-181">Using a GPO to catch the majority of clients, and also using port-based DSCP tagging will ensure that mobile, Mac, and other clients will still get QoS treatment (at least partially).</span></span>

<span data-ttu-id="ea14b-182">DSCP 표시는 우편 작업자에게 배달이 얼마나 긴급한지와 빠른 배달을 위해 정렬하는 가장 좋은 방법을 나타내는 우편물 스탬프에 비유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-182">DSCP markings can be likened to postage stamps that indicate to postal workers how urgent the delivery is and how best to sort it for speedy delivery.</span></span> <span data-ttu-id="ea14b-183">실시간 미디어 스트림에 우선 순위를 제공하도록 네트워크를 구성한 후 손실된 패킷 및 늦은 패킷은 크게 감소해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-183">Once you've configured your network to give priority to real-time media streams, lost packets and late packets should diminish greatly.</span></span>

<span data-ttu-id="ea14b-184">네트워크의 모든 디바이스가 동일한 분류, 표시 및 우선 순위를 사용하고 나면 각 트래픽 유형에 사용되는 큐에 할당된 포트 범위의 크기를 변경하여 지연, 삭제된 패킷 및 지터를 줄이거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-184">Once all devices in the network are using the same classifications, markings, and priorities, it's possible to reduce or eliminate delays, dropped packets, and jitter by changing the size of the port ranges assigned to the queues used for each traffic type.</span></span> <span data-ttu-id="ea14b-185">Teams 관점에서 가장 중요한 구성 단계는 패킷의 분류 및 표시입니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-185">From the Teams perspective, the most important configuration step is the classification and marking of packets.</span></span> <span data-ttu-id="ea14b-186">그러나 종단적 QoS가 성공하려면 애플리케이션의 구성을 주 네트워크 구성과 신중하게 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-186">However, for end-to-end QoS to be successful, you also need to carefully align the application's configuration with the underlying network configuration.</span></span> <span data-ttu-id="ea14b-187">QoS가 완전히 구현된 후 지속적인 관리는 조직의 요구 및 실제 사용량에 따라 각 트래픽 유형에 할당된 포트 범위를 조정하는 질문입니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-187">Once QoS is fully implemented, ongoing management is a question of adjusting the port ranges assigned to each traffic type based on your organization's needs and actual usage.</span></span>

## <a name="choose-initial-port-ranges-for-each-media-type"></a><span data-ttu-id="ea14b-188">각 미디어 유형에 대한 초기 포트 범위 선택</span><span class="sxs-lookup"><span data-stu-id="ea14b-188">Choose initial port ranges for each media type</span></span>

<span data-ttu-id="ea14b-189">DSCP 값은 ACL 설정에 따라 클라이언트 또는 네트워크 자체에 의해 DSCP 표시가 할당되어 있는지 여부에 따라 해당 구성된 네트워크에 패킷 또는 스트림을 부여할 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-189">The DSCP value tells a correspondingly configured network what priority to give a packet or stream, whether the DSCP mark is assigned by clients or the network itself based on ACL settings.</span></span> <span data-ttu-id="ea14b-190">각 미디어 워크로드는 고유한 DSCP 값을 얻습니다(다른 서비스는 워크로드가 DSCP 마킹을 공유하도록 허용할 수 있습니다. Teams는 허용되지 않습니다) 및 각 미디어 유형에 사용되는 정의된 별도의 포트 범위를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-190">Each media workload gets its own unique DSCP value (other services might allow workloads to share a DSCP marking, Teams doesn't) and a defined and separate port range used for each media type.</span></span> <span data-ttu-id="ea14b-191">다른 환경에는 네트워크 워크로드의 우선 순위를 결정하는 데 도움이 되는 기존 QoS 전략이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-191">Other environments might have an existing QoS strategy in place, which will help you determine the priority of network workloads.</span></span>

<span data-ttu-id="ea14b-192">다른 실시간 스트리밍 워크로드에 대한 포트 범위의 상대 크기는 해당 워크로드에 전용으로 사용 가능한 총 대역폭의 비율을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-192">The relative size of the port ranges for different real-time streaming workloads sets the proportion of the total available bandwidth dedicated to that workload.</span></span> <span data-ttu-id="ea14b-193">이전 우편 비유로 돌아가기: "Air Mail" 스탬프가 있는 편지는 1시간 이내에 가장 가까운 공항으로 이동될 수 있습니다. "대량 메일" 표시가 표시된 작은 패키지는 일련의 트럭에 착륙하기 전에 하루 동안 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-193">To return to our earlier postal analogy: a letter with an "Air Mail" stamp might get taken within an hour to the nearest airport, while a small package marked "Bulk Mail" mark can wait for a day before traveling over land on a series of trucks.</span></span>

<span data-ttu-id="ea14b-194">_권장되는 초기 포트 범위_</span><span class="sxs-lookup"><span data-stu-id="ea14b-194">_Recommended initial port ranges_</span></span>

|<span data-ttu-id="ea14b-195">미디어 트래픽 유형</span><span class="sxs-lookup"><span data-stu-id="ea14b-195">Media traffic type</span></span>| <span data-ttu-id="ea14b-196">클라이언트 원본 포트 범위 </span><span class="sxs-lookup"><span data-stu-id="ea14b-196">Client source port range</span></span> |<span data-ttu-id="ea14b-197">프로토콜</span><span class="sxs-lookup"><span data-stu-id="ea14b-197">Protocol</span></span>|<span data-ttu-id="ea14b-198">DSCP 값</span><span class="sxs-lookup"><span data-stu-id="ea14b-198">DSCP value</span></span>|<span data-ttu-id="ea14b-199">DSCP 클래스</span><span class="sxs-lookup"><span data-stu-id="ea14b-199">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="ea14b-200">오디오</span><span class="sxs-lookup"><span data-stu-id="ea14b-200">Audio</span></span>| <span data-ttu-id="ea14b-201">50,000~50,019</span><span class="sxs-lookup"><span data-stu-id="ea14b-201">50,000–50,019</span></span>|<span data-ttu-id="ea14b-202">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ea14b-202">TCP/UDP</span></span>|<span data-ttu-id="ea14b-203">46</span><span class="sxs-lookup"><span data-stu-id="ea14b-203">46</span></span>|<span data-ttu-id="ea14b-204">Expedited Forwarding(EF)</span><span class="sxs-lookup"><span data-stu-id="ea14b-204">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="ea14b-205">비디오</span><span class="sxs-lookup"><span data-stu-id="ea14b-205">Video</span></span>| <span data-ttu-id="ea14b-206">50,020~50,039</span><span class="sxs-lookup"><span data-stu-id="ea14b-206">50,020–50,039</span></span>|<span data-ttu-id="ea14b-207">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ea14b-207">TCP/UDP</span></span>|<span data-ttu-id="ea14b-208">34</span><span class="sxs-lookup"><span data-stu-id="ea14b-208">34</span></span>|<span data-ttu-id="ea14b-209">Assured Forwarding(AF41)</span><span class="sxs-lookup"><span data-stu-id="ea14b-209">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="ea14b-210">응용 프로그램/화면 공유</span><span class="sxs-lookup"><span data-stu-id="ea14b-210">Application/Screen Sharing</span></span>| <span data-ttu-id="ea14b-211">50,040~50,059</span><span class="sxs-lookup"><span data-stu-id="ea14b-211">50,040–50,059</span></span>|<span data-ttu-id="ea14b-212">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ea14b-212">TCP/UDP</span></span>|<span data-ttu-id="ea14b-213">18</span><span class="sxs-lookup"><span data-stu-id="ea14b-213">18</span></span>|<span data-ttu-id="ea14b-214">Assured Forwarding(AF21)</span><span class="sxs-lookup"><span data-stu-id="ea14b-214">Assured Forwarding (AF21)</span></span>|
||||||

<span data-ttu-id="ea14b-215">이러한 설정을 사용할 때 다음에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="ea14b-215">Be aware of the following when you use these settings:</span></span>

- <span data-ttu-id="ea14b-216">향후 ExpressRoute를 구현할 계획이고 아직 QoS를 구현하지 않은 경우 DSCP 값이 보낸 사람에서 받는 사람으로 동일하게 하게 지침을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-216">If you plan to implement ExpressRoute in the future and haven't yet implemented QoS, we recommend that you follow the guidance so that DSCP values are the same from sender to receiver.</span></span>
- <span data-ttu-id="ea14b-217">모바일 클라이언트 및 Teams 장치를 포함한 모든 클라이언트는 이러한 포트 범위를 사용하며, 이러한 원본 포트 범위를 사용하는 구현하는 모든 DSCP 정책의 영향을 받을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-217">All clients, including mobile clients and Teams devices, will use these port ranges and will be affected by any DSCP policy you implement that uses these source port ranges.</span></span> <span data-ttu-id="ea14b-218">동적 포트를 계속 사용하는 클라이언트는 브라우저 기반 클라이언트(참가자가 브라우저를 사용하여 모임에 참가할 수 있도록 하는 클라이언트)뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-218">The only clients that will continue to use dynamic ports are the browser-based clients (clients that let participants join meetings by using their browsers).</span></span>
- <span data-ttu-id="ea14b-219">Mac 클라이언트는 동일한 포트 범위를 사용하나 오디오(EF) 및 비디오(AF41)에 하드 코딩된 값도 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-219">Although the Mac client uses the same port ranges, it also uses hard-coded values for audio (EF) and video (AF41).</span></span> <span data-ttu-id="ea14b-220">이러한 값은 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-220">These values aren't configurable.</span></span>
- <span data-ttu-id="ea14b-221">나중에 사용자 환경을 개선하기 위해 포트 범위를 조정해야 하는 경우 포트 범위는 겹칠 수 없습니다. 서로 인접해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-221">If you later need to adjust the port ranges to improve user experience, the port ranges can't overlap and should be adjacent to each other.</span></span>

## <a name="migrate-qos-to-teams"></a><span data-ttu-id="ea14b-222">Teams로 QoS 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="ea14b-222">Migrate QoS to Teams</span></span>

<span data-ttu-id="ea14b-223">이전에 QoS 태그 지정 및 포트 범위를 포함하여 비즈니스용 Skype Online을 배포한 경우 현재 배포 중입니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-223">If you've previously deployed Skype for Business Online, including QoS tagging and port ranges, and are now deploying.</span></span> <span data-ttu-id="ea14b-224">Teams, Teams는 기존 구성을 존중하며 비즈니스용 Skype 클라이언트와 동일한 포트 범위 및 태그 지정을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-224">Teams, Teams will respect the existing configuration and will use the same port ranges and tagging as the Skype for Business client.</span></span> <span data-ttu-id="ea14b-225">대부분의 경우 추가 구성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-225">In most cases, no additional configuration will be needed.</span></span>

> [!NOTE]
> <span data-ttu-id="ea14b-226">그룹 정책을 통해 애플리케이션 이름 QoS 태그를 지정하는 경우 애플리케이션 이름으로 Teams.exe 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-226">If you're using Application Name QoS tagging via Group Policy, you must add Teams.exe as the application name.</span></span>

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a><span data-ttu-id="ea14b-227">PowerShell을 사용하여 Windows의 Teams에서 QoS 구현</span><span class="sxs-lookup"><span data-stu-id="ea14b-227">Implement QoS in Teams on Windows using PowerShell</span></span>

<span data-ttu-id="ea14b-228">**오디오에 대한 QoS 설정**</span><span class="sxs-lookup"><span data-stu-id="ea14b-228">**Set QoS for audio**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000
-IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

<span data-ttu-id="ea14b-229">**비디오에 대한 QoS 설정**</span><span class="sxs-lookup"><span data-stu-id="ea14b-229">**Set QoS for video**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020
-IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

<span data-ttu-id="ea14b-230">**공유를 위한 QoS 설정**</span><span class="sxs-lookup"><span data-stu-id="ea14b-230">**Set QoS for sharing**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040
-IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a><span data-ttu-id="ea14b-231">Teams 관리 센터에서 원본 포트 관리</span><span class="sxs-lookup"><span data-stu-id="ea14b-231">Managing source ports in the Teams admin center</span></span>

<span data-ttu-id="ea14b-232">Teams에서 다양한 워크로드에서 사용하는 QoS 원본 포트를 적극적으로 관리하고 필요한 경우 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-232">In Teams, QoS source ports used by the different workloads should be actively managed, and adjusted as necessary.</span></span> <span data-ttu-id="ea14b-233">각 미디어 유형에 [](#choose-initial-port-ranges-for-each-media-type)대한 초기 포트 범위 선택에서 테이블을 참조하면 포트 범위를 조정할 수 있지만 DSCP 표시는 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-233">Referring to the table in [Choose initial port ranges for each media type](#choose-initial-port-ranges-for-each-media-type), the port ranges are adjustable, but the DSCP markings aren't configurable.</span></span> <span data-ttu-id="ea14b-234">이러한 설정을 구현한 후 특정 미디어 유형에 필요한 포트가 더 적거나 적을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-234">Once you have implemented these settings, you might find that more or fewer ports are needed for a given media type.</span></span> <span data-ttu-id="ea14b-235">[사용자당](use-call-analytics-to-troubleshoot-poor-call-quality.md) 통화 분석 및 [CQD(통화](turning-on-and-using-call-quality-dashboard.md) 품질 대시보드)는 Teams가 구현된 후 포트 범위를 조정하고 요구가 변경될 때 주기적으로 조정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-235">[Per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md) and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) should be used in making a decision to adjust port ranges after Teams has been implemented, and periodically as needs change.</span></span>

> [!NOTE]
> <span data-ttu-id="ea14b-236">비즈니스용 Skype Online의 원본 포트 범위 및 DSCP 표시를 기반으로 QoS를 이미 구성한 경우 동일한 구성이 Teams에 적용되어 더 이상 클라이언트 또는 네트워크에서 매핑을 변경할 필요는 없습니다. 하지만 비즈니스용 Skype Online에 대해 구성된 범위와 일치하도록 [Teams에서](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) 사용되는 범위를 설정해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-236">If you've already configured QoS based on source port ranges and DSCP markings for Skype for Business Online, the same configuration will apply to Teams and no further client or network changes to the mapping will be required, though you may have to [set the ranges used in Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) to match what was configured for Skype for Business Online.</span></span>

<span data-ttu-id="ea14b-237">이전에 비즈니스용 Skype Server를 배포한 경우 QoS 정책을 다시 검사해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-237">If you’ve previously deployed Skype for Business Server on-premises, you might need to re-examine your QoS policies.</span></span> <span data-ttu-id="ea14b-238">확인한 포트 범위 설정과 일치하도록 정책을 조정하여 Teams에 대한 고품질 사용자 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-238">Adjust the policies to match port range settings you've verified provide a quality user experience for Teams.</span></span>

## <a name="validate-your-qos-implementation"></a><span data-ttu-id="ea14b-239">QoS 구현 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ea14b-239">Validate your QoS implementation</span></span>

<span data-ttu-id="ea14b-240">QoS가 유효하기 위해 GPO에서 설정한 DSCP 값은 호출의 양쪽 끝에 존재해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-240">For QoS to be effective, the DSCP value set by the GPO needs to be present at both ends of a call.</span></span> <span data-ttu-id="ea14b-241">Teams 클라이언트에서 생성된 트래픽을 분석하여 Teams 워크로드 트래픽이 네트워크를 통해 이동하는 경우 DSCP 값이 변경되거나 제거되지 않는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-241">By analyzing the traffic generated by the Teams client, you can verify that the DSCP value isn’t changed or stripped out when the Teams workload traffic moves through the network.</span></span>

<span data-ttu-id="ea14b-242">네트워크 시작 지점에서 트래픽을 캡처하는 것이 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-242">Preferably, you capture traffic at the network egress point.</span></span> <span data-ttu-id="ea14b-243">스위치 또는 라우터에서 포트 미러링을 사용하여 이를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea14b-243">You can use port mirroring on a switch or router to help with this.</span></span>

## <a name="implement-qos-for-other-devices"></a><span data-ttu-id="ea14b-244">다른 디바이스에 대한 QoS 구현</span><span class="sxs-lookup"><span data-stu-id="ea14b-244">Implement QoS for other devices</span></span>

<span data-ttu-id="ea14b-245">Intune, Surface, iOS, Android 및 Mac용 QoS 구현에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ea14b-245">Read these topics for information about implementing QoS for Intune, Surface, iOS, Android, and Mac</span></span>

- [<span data-ttu-id="ea14b-246">Surface Hub 2S용 QoS</span><span class="sxs-lookup"><span data-stu-id="ea14b-246">QoS for Surface Hub 2S</span></span>](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [<span data-ttu-id="ea14b-247">Surface Hub용 QoS</span><span class="sxs-lookup"><span data-stu-id="ea14b-247">QoS for Surface Hub</span></span>](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [<span data-ttu-id="ea14b-248">iOS, Android 및 Mac용 QoS</span><span class="sxs-lookup"><span data-stu-id="ea14b-248">QoS for iOS, Android, and Mac</span></span>](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a><span data-ttu-id="ea14b-249">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ea14b-249">Related topics</span></span>

- [<span data-ttu-id="ea14b-250">비디오: 네트워크 계획</span><span class="sxs-lookup"><span data-stu-id="ea14b-250">Video: Network Planning</span></span>](https://aka.ms/teams-networking)

- [<span data-ttu-id="ea14b-251">Microsoft Teams에 대한 조직의 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="ea14b-251">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)

- [<span data-ttu-id="ea14b-252">Teams 클라이언트에서 QoS 구현</span><span class="sxs-lookup"><span data-stu-id="ea14b-252">Implement QoS in the Teams client</span></span>](QoS-in-Teams-clients.md)
