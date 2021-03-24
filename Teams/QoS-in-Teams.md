---
title: Microsoft Teams에서 서비스 품질 구현
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Microsoft Teams에서 QoS(품질 품질)에 대한 조직의 네트워크를 준비하는 방법에 대해 자세히 알아보습니다.
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
ms.openlocfilehash: 87f3577d34df6d2b0665a45b60b441d29cd0265b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092616"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a><span data-ttu-id="af138-103">Microsoft Teams에서 QoS(서비스 품질) 구현</span><span class="sxs-lookup"><span data-stu-id="af138-103">Implement Quality of Service (QoS) in Microsoft Teams</span></span>

<span data-ttu-id="af138-104">Microsoft Teams의 QoS(서비스 품질)를 사용하면 네트워크 지연(예: 음성 또는 비디오 스트림)에 민감한 실시간 네트워크 트래픽이 덜 민감하지 않은 트래픽 앞에서 "줄을 끊습니다"(예: 다운로드할 추가 초가 큰 거래가 아닌 경우).</span><span class="sxs-lookup"><span data-stu-id="af138-104">Quality of Service (QoS) in Microsoft Teams allows real-time network traffic that's sensitive to network delays (for example, voice or video streams) to "cut in line" in front of traffic that's less sensitive (like downloading a new app, where an extra second to download isn't a large deal).</span></span> <span data-ttu-id="af138-105">QoS는 Windows 그룹 정책 개체 및 포트 기반 액세스 제어 목록을 사용하여 실시간 스트림에서 모든 패킷을 식별하고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-105">QoS uses Windows Group Policy Objects and Port-based Access Control Lists to identify and mark all packets in real-time streams.</span></span> <span data-ttu-id="af138-106">이렇게 하면 네트워크에서 음성, 비디오 및 화면 공유가 네트워크 대역폭의 전용 부분을 스트리밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-106">This helps your network to give voice, video, and screen share streams a dedicated portion of network bandwidth.</span></span>

<span data-ttu-id="af138-107">이 문서에 설명된 문제 중 한 가지가 발생하는 대규모 사용자 그룹을 지원하는 경우 QoS를 구현해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-107">If you support a large group of users who are experiencing any of the problems described in this article, then you probably need to implement QoS.</span></span> <span data-ttu-id="af138-108">사용자 수가 적은 소규모 기업에서는 QoS가 필요하지 않을 수 있지만, 이 경우에도 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-108">A small business with few users might not need QoS, but even there it should be helpful.</span></span>

<span data-ttu-id="af138-109">일부 형태의 QoS가 없는 경우 음성 및 비디오에서 다음과 같은 품질 문제가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-109">Without some form of QoS, you might see the following quality issues in voice and video:</span></span>

- <span data-ttu-id="af138-110">Jitter – 다른 요금으로 도착하는 미디어 패킷으로 인해 통화에서 단어나 음성이 누락될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-110">Jitter – media packets arriving at different rates, which can result in missing words or syllables in calls</span></span>
- <span data-ttu-id="af138-111">패킷 손실 – 패킷이 삭제되어 음성 품질이 낮아지며 음성을 이해하기가 어려워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-111">Packet loss – packets dropped, which can also result in lower voice quality and hard to understand speech</span></span>
- <span data-ttu-id="af138-112">RTT(지연된 왕복 시간) – 미디어 패킷이 대상에 도달하는 데 시간이 오래 늦어 대화의 두 당사자 간에 눈에 띄게 지연되고 사람들이 서로 대화할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-112">Delayed round-trip time (RTT) – media packets taking a long time to reach their destinations, which result in noticeable delays between two parties in a conversation and causes people to talk over each other</span></span>

<span data-ttu-id="af138-113">이러한 문제를 해결하기 위해 가장 복잡한 방법은 데이터 연결의 크기를 늘리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="af138-113">The least complex way to address these issues is to increase the size of the data connections, both internally and out to the internet.</span></span> <span data-ttu-id="af138-114">비용이 많이 들기 때문에 QoS는 대역폭을 추가하는 대신 사용자가 확보한 리소스를 보다 효과적으로 관리할 수 있는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-114">Since that is often cost-prohibitive, QoS provides a way to more effectively manage the resources you have instead of adding bandwidth.</span></span> <span data-ttu-id="af138-115">품질 문제를 해결하기 위해 먼저 QoS를 사용한 다음 필요한 경우 대역폭을 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-115">To address quality issues, we recommend that you first use QoS, then add bandwidth only where necessary.</span></span>

<span data-ttu-id="af138-116">QoS가 효과적이기 위해 조직 전체에서 일관된 QoS 설정을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-116">For QoS to be effective, you must apply consistent QoS settings throughout your organization.</span></span> <span data-ttu-id="af138-117">QoS 우선 순위를 지원하지 못하는 경로의 일부가 통화, 비디오 및 화면 공유의 품질을 저하할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-117">Any part of the path that fails to support your QoS priorities can degrade the quality of calls, video, and screen sharing.</span></span> <span data-ttu-id="af138-118">여기에는 모든 사용자 PC 또는 디바이스, 네트워크 스위치, 인터넷에 라우터 및 Teams 서비스에 설정을 적용하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="af138-118">This includes applying settings to all user PCs or devices, network switches, routers to the internet, and the Teams service.</span></span>

<span data-ttu-id="af138-119">_그림 1. 조직의 네트워크와 Microsoft 365 또는 Office 365 서비스 간의 관계_</span><span class="sxs-lookup"><span data-stu-id="af138-119">_Figure 1. The relationship between an organization's networks and Microsoft 365 or Office 365 services_</span></span>

<span data-ttu-id="af138-120">![네트워크와 서비스 간의 관계에 대한 그림](media/Qos-in-Teams-Image1.png "조직의 네트워크와 Microsoft 365 또는 Office 365 서비스 간의 관계: On-프레미스 네트워크 및 디바이스는 상호 연결 네트워크와 연결됩니다. 따라서 Microsoft 365 또는 Office 365 클라우드 음성 및 오디오 회의 서비스와 연결됩니다.")</span><span class="sxs-lookup"><span data-stu-id="af138-120">![Illustration of the relationship between networks and services](media/Qos-in-Teams-Image1.png "The relationship between an organization's networks and Microsoft 365 or Office 365 services: on-premises network and devices connect with an interconnect network, which in turn connects with Microsoft 365 or Office 365 Cloud Voice and Audio Conferencing services.")</span></span>

## <a name="qos-implementation-checklist"></a><span data-ttu-id="af138-121">QoS 구현 검사 목록</span><span class="sxs-lookup"><span data-stu-id="af138-121">QoS implementation checklist</span></span>

<span data-ttu-id="af138-122">높은 수준에서 QoS를 구현하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-122">At a high level, do the following to implement QoS:</span></span>

1. <span data-ttu-id="af138-123">[네트워크가 준비되어 있는지 확인합니다.](#make-sure-your-network-is-ready)</span><span class="sxs-lookup"><span data-stu-id="af138-123">[Make sure your network is ready](#make-sure-your-network-is-ready).</span></span>

1. <span data-ttu-id="af138-124">[QoS](#select-a-qos-implementation-method)구현 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-124">[Select a QoS implementation method](#select-a-qos-implementation-method).</span></span>

1. <span data-ttu-id="af138-125">[각 미디어 유형에 대한 초기 포트 범위를 선택 합니다.](#choose-initial-port-ranges-for-each-media-type)</span><span class="sxs-lookup"><span data-stu-id="af138-125">[Choose initial port ranges for each media type](#choose-initial-port-ranges-for-each-media-type).</span></span>

1. <span data-ttu-id="af138-126">QoS 설정 구현:</span><span class="sxs-lookup"><span data-stu-id="af138-126">Implement QoS settings:</span></span>
   1. <span data-ttu-id="af138-127">GPO(그룹 정책 개체)를 사용하여 클라이언트 디바이스 포트 범위 및 표시를 설정하는 [클라이언트에서](QoS-in-Teams-clients.md)</span><span class="sxs-lookup"><span data-stu-id="af138-127">On clients using a Group Policy Object (GPO) to [set client device port ranges and markings](QoS-in-Teams-clients.md).</span></span>
   2. <span data-ttu-id="af138-128">라우터(제조업체 설명서 참조) 또는 기타 네트워크 디바이스에서</span><span class="sxs-lookup"><span data-stu-id="af138-128">On routers (see the manufacturer documentation) or other network devices.</span></span> <span data-ttu-id="af138-129">여기에는 ACL(포트 기반 액세스 제어 목록)을 포함하거나 QoS 큐 및 DSCP 표시를 정의하거나 이러한 모든 항목만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-129">This might include port-based Access Control Lists (ACLs) or simply defining the QoS queues and DSCP markings, or all of these.</span></span>

      > [!IMPORTANT]
      > <span data-ttu-id="af138-130">클라이언트 원본 포트 및 "any"의 원본 및 대상 IP 주소를 사용하여 이러한 QoS 정책을 구현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-130">We recommend implementing these QoS policies using the client source ports and a source and destination IP address of “any.”</span></span> <span data-ttu-id="af138-131">이렇게 하면 내부 네트워크에서 들어오는 미디어 트래픽과 외부 미디어 트래픽이 모두 포획됩니다.</span><span class="sxs-lookup"><span data-stu-id="af138-131">This will catch both incoming and outgoing media traffic on the internal network.</span></span>  

   3. <span data-ttu-id="af138-132">Teams 모임의 미디어 트래픽을 [처리하는 방법을 설정합니다.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)</span><span class="sxs-lookup"><span data-stu-id="af138-132">[Set how you want to handle media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>

5. <span data-ttu-id="af138-133">네트워크의 Teams 트래픽을 분석하여 [QoS](#validate-your-qos-implementation) 구현의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-133">[Validate your QoS implementation](#validate-your-qos-implementation) by analyzing Teams traffic on the network.</span></span>

<span data-ttu-id="af138-134">QoS를 구현할 준비를 할 때 다음 지침을 염두에 두세요.</span><span class="sxs-lookup"><span data-stu-id="af138-134">As you prepare to implement QoS, keep the following guidelines in mind:</span></span>

- <span data-ttu-id="af138-135">Microsoft 365에 대한 가장 짧은 경로가 가장 짧습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-135">The shortest path to Microsoft 365 is best.</span></span>
- <span data-ttu-id="af138-136">포트를 닫는 경우 품질 저하만 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-136">Closing ports will only lead to quality degradation.</span></span>
- <span data-ttu-id="af138-137">그 사이에 있는 장애물(예: proxies)은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-137">Any obstacles in between, such as proxies, aren't recommended.</span></span>
- <span data-ttu-id="af138-138">홉 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-138">Limit the number of hops:</span></span>
  - <span data-ttu-id="af138-139">클라이언트에서 네트워크 에지로 – 3~5개 홉</span><span class="sxs-lookup"><span data-stu-id="af138-139">Client to network edge – 3 to 5 hops</span></span>
  - <span data-ttu-id="af138-140">MICROSOFT 네트워크 에지로 ISP - 3홉</span><span class="sxs-lookup"><span data-stu-id="af138-140">ISP to Microsoft network edge – 3 hops</span></span>
  - <span data-ttu-id="af138-141">Microsoft 네트워크 에지에서 최종 대상까지 - 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-141">Microsoft network edge to final destination – irrelevant</span></span>

<span data-ttu-id="af138-142">방화벽 포트 구성에 대한 자세한 내용은 [Office 365 URL 및 IP 범위로 이동하세요.](office-365-urls-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="af138-142">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

## <a name="make-sure-your-network-is-ready"></a><span data-ttu-id="af138-143">네트워크가 준비되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-143">Make sure your network is ready</span></span>

<span data-ttu-id="af138-144">QoS 구현을 고려하는 경우 대역폭 요구 사항 및 기타 네트워크 요구 사항을 이미 [결정해야 합니다.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="af138-144">If you're considering a QoS implementation, you should already have determined your bandwidth requirements and other [network requirements](prepare-network.md).</span></span>
  
<span data-ttu-id="af138-145">네트워크의 트래픽 정체는 미디어 품질에 크게 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af138-145">Traffic congestion across a network will greatly impact media quality.</span></span> <span data-ttu-id="af138-146">대역폭이 부족하면 성능 저하와 사용자 환경이 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="af138-146">A lack of bandwidth leads to performance degradation and a poor user experience.</span></span> <span data-ttu-id="af138-147">Teams 채택 및 사용량이 증가함에 따라 [보고,](use-call-analytics-to-troubleshoot-poor-call-quality.md)사용자당 통화 분석 및 [CQD(품질 대시보드)를](turning-on-and-using-call-quality-dashboard.md) 사용하여 문제를 식별한 다음 QoS 및 선택적 대역폭 추가를 사용하여 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-147">As Teams adoption and usage grows, use reporting, [per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md), and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to identify problems and then make adjustments using QoS and selective bandwidth additions.</span></span>

### <a name="vpn-considerations"></a><span data-ttu-id="af138-148">VPN 고려 사항</span><span class="sxs-lookup"><span data-stu-id="af138-148">VPN considerations</span></span>

<span data-ttu-id="af138-149">QoS는 호출자 간의 모든 링크에서 구현될 때만 예상대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-149">QoS only works as expected when implemented on all links between callers.</span></span> <span data-ttu-id="af138-150">내부 네트워크에서 QoS를 사용하며 사용자가 원격 위치에서 로그인하는 경우 관리되는 내부 네트워크 내에서만 우선 순위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-150">If you use QoS on an internal network and a user signs in from a remote location, you can only prioritize within your internal, managed network.</span></span> <span data-ttu-id="af138-151">원격 위치는 VPN(가상 사설 네트워크)을 구현하여 관리되는 연결을 받을 수 있습니다. VPN은 기본적으로 패킷 오버헤드를 추가하고 실시간 트래픽에 지연을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af138-151">Although remote locations can receive a managed connection by implementing a virtual private network (VPN),  a VPN inherently adds packet overhead and creates delays in real-time traffic.</span></span> <span data-ttu-id="af138-152">VPN을 통해 실시간 통신 트래픽을 실행하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-152">We  recommend that you avoid running real-time communications traffic over a VPN.</span></span>

<span data-ttu-id="af138-153">대륙을 아우르는 관리되는 링크가 있는 글로벌 조직에서는 이러한 링크에 대한 대역폭이 LAN과 비교하여 제한되어 있기 때문에 QoS를 강력히 추천합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-153">In a global organization with managed links that span continents, we strongly recommend QoS because bandwidth for those links is limited in comparison to the LAN.</span></span>

## <a name="introduction-to-qos-queues"></a><span data-ttu-id="af138-154">QoS 큐 소개</span><span class="sxs-lookup"><span data-stu-id="af138-154">Introduction to QoS queues</span></span>

<span data-ttu-id="af138-155">QoS를 제공하려면 네트워크 디바이스는 트래픽을 분류하는 방법이 있어야 합니다. 다른 네트워크 트래픽과 음성 또는 비디오를 구분할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-155">To provide QoS, network devices must have a way to classify traffic and must be able to distinguish voice or video from other network traffic.</span></span>

<span data-ttu-id="af138-156">네트워크 트래픽이 라우터에 들어오면 트래픽이 큐에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="af138-156">When network traffic enters a router, the traffic is placed into a queue.</span></span> <span data-ttu-id="af138-157">QoS 정책이 구성되지 않은 경우 하나의 큐만 있으며 모든 데이터는 동일한 우선 순위가 있는 선행, 선출으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="af138-157">If a QoS policy isn't configured, there is only one queue, and all data is treated as first-in, first-out with the same priority.</span></span> <span data-ttu-id="af138-158">즉, 음성 트래픽(지연에 매우 민감)이 트래픽 뒤에 늦어지며 몇 밀리초의 지연이 문제가되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-158">That means voice traffic (which is very sensitive to delays) might get stuck behind traffic where a delay of a few extra milliseconds wouldn't be a problem.</span></span>

<span data-ttu-id="af138-159">QoS를 구현할 때 Cisco의 우선 순위 큐 및 [CBWFQ(Class-Based Weighted Fair Queueing)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) 및 정체 방지 기능(예: [WRED)과](https://en.wikipedia.org/wiki/Weighted_random_early_detection)같은 여러 정체 관리 기능 중 하나를 사용하여 여러 큐를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-159">When you implement QoS, you define multiple queues using one of several congestion management features, such as Cisco’s priority queuing and [Class-Based Weighted Fair Queueing (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) and congestion avoidance features, such as [weighted random early detection (WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection).</span></span>

<span data-ttu-id="af138-160">_그림 2. QoS 큐의 예_</span><span class="sxs-lookup"><span data-stu-id="af138-160">_Figure 2. Examples of QoS queues_</span></span>

<span data-ttu-id="af138-161">![QoS 큐 및 대역폭 분할 그림](media/Qos-in-Teams-Image2.png "사용 가능한 총 대역폭은 여러 큐(오디오, 비디오 및 기타 트래픽)로 나뉘며, 우선 순위가 서로 다릅니다.")</span><span class="sxs-lookup"><span data-stu-id="af138-161">![Illustration of QoS queues and bandwidth division](media/Qos-in-Teams-Image2.png "Total available bandwidth is divided among multiple queues—audio, video, and other traffic—that have been assigned different priorities.")</span></span>

<span data-ttu-id="af138-162">간단한 비유는 QoS가 데이터 네트워크에서 가상 "카풀 차선"을 만들어 일부 유형의 데이터가 지연되거나 거의 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-162">A simple analogy is that QoS creates virtual "carpool lanes" in your data network so some types of data never or rarely encounter a delay.</span></span> <span data-ttu-id="af138-163">이러한 차선을 만들면 조직의 사용자에 대한 비즈니스 등급 환경을 제공하면서 상대 크기를 조정하고 연결 대역폭을 훨씬 효율적으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-163">Once you create those lanes, you can adjust their relative size and much more effectively manage the connection bandwidth you have, while still delivering business-grade experiences for your organization's users.</span></span>

## <a name="select-a-qos-implementation-method"></a><span data-ttu-id="af138-164">QoS 구현 방법 선택</span><span class="sxs-lookup"><span data-stu-id="af138-164">Select a QoS implementation method</span></span>

<span data-ttu-id="af138-165">네트워크의 라우터에서 ACL(액세스 제어 목록)을 사용하여 포트 기반 태그를 통해 QoS를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-165">You could implement QoS via port-based tagging, using Access Control Lists (ACLs) on your network's routers.</span></span> <span data-ttu-id="af138-166">포트 기반 태그 지정은 혼합된 Windows, Mac 및 Linux 환경에서 작동하고 구현하기 가장 쉬운 방식이기 때문에 가장 신뢰할 수 있는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="af138-166">Port-based tagging is the most reliable method because it works in mixed Windows, Mac, and Linux environments and is the easiest to implement.</span></span> <span data-ttu-id="af138-167">모바일 클라이언트는 DSCP 값을 사용하여 트래픽을 표시하는 메커니즘을 제공하지 않습니다. 따라서 이 메서드가 필요하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af138-167">Mobile clients don't provide a mechanism to mark traffic by using DSCP values, so they'll require this method.</span></span>  

<span data-ttu-id="af138-168">포트 기반 태그를 사용하여 네트워크의 라우터는 들어오는 패킷을 검사하고 패킷이 특정 포트 또는 포트 범위를 사용하여 도착한 경우 해당 패킷을 특정 미디어 유형으로 식별하고 해당 형식의 큐에 넣습니다. IP 패킷 헤더에 미리 정해진 [DSCP](https://tools.ietf.org/html/rfc2474) 표시를 추가하여 다른 디바이스가 트래픽 유형을 인식하고 큐에서 우선 순위를 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-168">Using port-based tagging, your network's router examines an incoming packet, and if the packet arrived using a certain port or range of ports, it identifies it as a certain media type and puts it in the queue for that type, adding a predetermined [DSCP](https://tools.ietf.org/html/rfc2474) mark to the IP Packet header so other devices can recognize its traffic type and give it priority in their queue.</span></span>

<span data-ttu-id="af138-169">포트 기반 태그는 플랫폼에서 작동하나 WAN 에지에서만 트래픽을 표시하고(클라이언트 컴퓨터로의 모든 방식이 아는 것은 아 않습니다. ) 관리 오버헤드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="af138-169">Although port-based tagging works across platforms, it only marks traffic at the WAN edge (not all the way to the client machine) and creates management overhead.</span></span> <span data-ttu-id="af138-170">이 메서드를 구현하는 방법에 대한 지침은 라우터 제조업체에서 제공하는 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af138-170">Refer to the documentation provided by the router manufacturer for instructions on implementing this method.</span></span>

### <a name="insert-dscp-markers"></a><span data-ttu-id="af138-171">DSCP 마커 삽입</span><span class="sxs-lookup"><span data-stu-id="af138-171">Insert DSCP markers</span></span>

<span data-ttu-id="af138-172">GPO(그룹 정책 개체)를 사용하여 특정 트래픽 유형(예: 음성)으로 식별하는 IP 패킷 헤더에 DSCP 마커를 삽입하는 클라이언트 디바이스를 지시하여 QoS를 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-172">You could also implement QoS by using a Group Policy Object (GPO) to direct client devices to insert a DSCP marker in IP packet headers identifying it as particular type of traffic (for example, voice).</span></span> <span data-ttu-id="af138-173">라우터 및 기타 네트워크 디바이스는 이를 인식하고 트래픽을 우선 순위가 높은 별도의 큐에 넣도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-173">Routers and other network devices can be configured to recognize this and put the traffic in a separate, higher-priority queue.</span></span>

<span data-ttu-id="af138-174">이 시나리오는 완전히 유효하기는 하지만 도메인에 가입된 Windows 클라이언트에만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-174">Although this scenario is entirely valid, it will only work for domain-joined Windows clients.</span></span> <span data-ttu-id="af138-175">도메인에 가입된 Windows 클라이언트가 아닌 디바이스는 DSCP 태그 지정에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-175">Any device that isn't a domain-joined Windows client won't be enabled for DSCP tagging.</span></span> <span data-ttu-id="af138-176">실행 중인 macOS와 같은 다른 클라이언트에는 하드 코딩된 태그가 있으며 항상 트래픽에 태그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-176">Other clients, such as those running macOS, have hard-coded tags and will always tag traffic.</span></span>

<span data-ttu-id="af138-177">또한 GPO를 통해 DSCP 마킹을 제어하면 도메인에 가입된 모든 컴퓨터가 동일한 설정을 받고 관리자만 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-177">On the plus side, controlling the DSCP marking via GPO ensures that all domain-joined computers receive the same settings and that only an administrator can manage them.</span></span> <span data-ttu-id="af138-178">GPO를 사용할 수 있는 클라이언트는 원래 디바이스에 태그가 지정된 다음, 구성된 네트워크 디바이스는 DSCP 코드로 실시간 스트림을 인식하고 적절한 우선 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-178">Clients that can use GPO will be tagged on the originating device, and then configured network devices can recognize the real-time stream by the DSCP code and give it an appropriate priority.</span></span>

### <a name="best-practice"></a><span data-ttu-id="af138-179">모범 사례</span><span class="sxs-lookup"><span data-stu-id="af138-179">Best practice</span></span>

<span data-ttu-id="af138-180">가능한 경우 엔드포인트의 DSCP 표시와 라우터의 포트 기반 ACL을 조합하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-180">We recommend a combination of DSCP markings at the endpoint and port-based ACLs on routers, if possible.</span></span> <span data-ttu-id="af138-181">GPO를 사용하여 대부분의 클라이언트를 포획하고 포트 기반 DSCP 태그를 사용하면 모바일, Mac 및 기타 클라이언트가 여전히 QoS 처리(부분적으로)를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-181">Using a GPO to catch the majority of clients, and also using port-based DSCP tagging will ensure that mobile, Mac, and other clients will still get QoS treatment (at least partially).</span></span>

<span data-ttu-id="af138-182">DSCP 표시는 배달이 얼마나 긴급한지와 빠른 배달을 위해 정렬하는 가장 좋은 방법을 나타내는 우편물 스탬프에 비유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-182">DSCP markings can be likened to postage stamps that indicate to postal workers how urgent the delivery is and how best to sort it for speedy delivery.</span></span> <span data-ttu-id="af138-183">실시간 미디어 스트림에 우선 순위를 제공하도록 네트워크를 구성한 후 패킷 손실 및 늦은 패킷은 크게 감소해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-183">Once you've configured your network to give priority to real-time media streams, lost packets and late packets should diminish greatly.</span></span>

<span data-ttu-id="af138-184">네트워크의 모든 디바이스가 동일한 분류, 표시 및 우선 순위를 사용하는 경우 각 트래픽 유형에 사용되는 큐에 할당된 포트 범위의 크기를 변경하여 지연, 삭제된 패킷 및 지터를 줄이거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-184">Once all devices in the network are using the same classifications, markings, and priorities, it's possible to reduce or eliminate delays, dropped packets, and jitter by changing the size of the port ranges assigned to the queues used for each traffic type.</span></span> <span data-ttu-id="af138-185">Teams 관점에서 가장 중요한 구성 단계는 패킷의 분류 및 표시입니다.</span><span class="sxs-lookup"><span data-stu-id="af138-185">From the Teams perspective, the most important configuration step is the classification and marking of packets.</span></span> <span data-ttu-id="af138-186">그러나 종단 내지 엔드 QoS가 성공하려면 애플리케이션의 구성을 주된 네트워크 구성과 신중하게 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-186">However, for end-to-end QoS to be successful, you also need to carefully align the application's configuration with the underlying network configuration.</span></span> <span data-ttu-id="af138-187">QoS가 완전히 구현된 후 지속적인 관리는 조직의 요구와 실제 사용량에 따라 각 트래픽 유형에 할당된 포트 범위를 조정하는 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="af138-187">Once QoS is fully implemented, ongoing management is a question of adjusting the port ranges assigned to each traffic type based on your organization's needs and actual usage.</span></span>

## <a name="choose-initial-port-ranges-for-each-media-type"></a><span data-ttu-id="af138-188">각 미디어 유형에 대한 초기 포트 범위 선택</span><span class="sxs-lookup"><span data-stu-id="af138-188">Choose initial port ranges for each media type</span></span>

<span data-ttu-id="af138-189">DSCP 값은 DSCP 표시가 클라이언트에 의해 할당되거나 ACL 설정에 따라 네트워크 자체에 할당되어 있는지 여부에 따라 해당 구성된 네트워크에 패킷 또는 스트림을 제공해야 하는 우선 순위를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-189">The DSCP value tells a correspondingly configured network what priority to give a packet or stream, whether the DSCP mark is assigned by clients or the network itself based on ACL settings.</span></span> <span data-ttu-id="af138-190">각 미디어 워크로드는 고유한 DSCP 값을 얻습니다(다른 서비스는 워크로드가 DSCP 마킹을 공유할 수 있도록 허용할 수 있습니다. Teams는 없습니다) 및 각 미디어 유형에 사용되는 정의된 별도의 포트 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="af138-190">Each media workload gets its own unique DSCP value (other services might allow workloads to share a DSCP marking, Teams doesn't) and a defined and separate port range used for each media type.</span></span> <span data-ttu-id="af138-191">다른 환경에는 기존 QoS 전략이 있을 수 있습니다. 이는 네트워크 워크로드의 우선 순위를 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af138-191">Other environments might have an existing QoS strategy in place, which will help you determine the priority of network workloads.</span></span>

<span data-ttu-id="af138-192">서로 다른 실시간 스트리밍 워크로드에 대한 포트 범위의 상대 크기는 해당 워크로드에 전용으로 사용 가능한 총 대역폭의 비율을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-192">The relative size of the port ranges for different real-time streaming workloads sets the proportion of the total available bandwidth dedicated to that workload.</span></span> <span data-ttu-id="af138-193">이전 우편 비유로 돌아가기 위해 " Air Mail" 스탬프가 있는 편지는 가장 가까운 공항으로 1시간 이내에 도착할 수 있습니다. "Bulk Mail" 표시가 표시된 작은 패키지는 일련의 트럭을 통해 육로로 이동하기 전에 하루를 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-193">To return to our earlier postal analogy: a letter with an "Air Mail" stamp might get taken within an hour to the nearest airport, while a small package marked "Bulk Mail" mark can wait for a day before traveling over land on a series of trucks.</span></span>

<span data-ttu-id="af138-194">_권장되는 초기 포트 범위_</span><span class="sxs-lookup"><span data-stu-id="af138-194">_Recommended initial port ranges_</span></span>

|<span data-ttu-id="af138-195">미디어 트래픽 유형</span><span class="sxs-lookup"><span data-stu-id="af138-195">Media traffic type</span></span>| <span data-ttu-id="af138-196">클라이언트 원본 포트 범위 </span><span class="sxs-lookup"><span data-stu-id="af138-196">Client source port range</span></span> |<span data-ttu-id="af138-197">프로토콜</span><span class="sxs-lookup"><span data-stu-id="af138-197">Protocol</span></span>|<span data-ttu-id="af138-198">DSCP 값</span><span class="sxs-lookup"><span data-stu-id="af138-198">DSCP value</span></span>|<span data-ttu-id="af138-199">DSCP 클래스</span><span class="sxs-lookup"><span data-stu-id="af138-199">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="af138-200">오디오</span><span class="sxs-lookup"><span data-stu-id="af138-200">Audio</span></span>| <span data-ttu-id="af138-201">50,000~50,019</span><span class="sxs-lookup"><span data-stu-id="af138-201">50,000–50,019</span></span>|<span data-ttu-id="af138-202">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="af138-202">TCP/UDP</span></span>|<span data-ttu-id="af138-203">46</span><span class="sxs-lookup"><span data-stu-id="af138-203">46</span></span>|<span data-ttu-id="af138-204">Expedited Forwarding(EF)</span><span class="sxs-lookup"><span data-stu-id="af138-204">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="af138-205">비디오</span><span class="sxs-lookup"><span data-stu-id="af138-205">Video</span></span>| <span data-ttu-id="af138-206">50,020~50,039</span><span class="sxs-lookup"><span data-stu-id="af138-206">50,020–50,039</span></span>|<span data-ttu-id="af138-207">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="af138-207">TCP/UDP</span></span>|<span data-ttu-id="af138-208">34</span><span class="sxs-lookup"><span data-stu-id="af138-208">34</span></span>|<span data-ttu-id="af138-209">Assured Forwarding(AF41)</span><span class="sxs-lookup"><span data-stu-id="af138-209">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="af138-210">응용 프로그램/화면 공유</span><span class="sxs-lookup"><span data-stu-id="af138-210">Application/Screen Sharing</span></span>| <span data-ttu-id="af138-211">50,040~50,059</span><span class="sxs-lookup"><span data-stu-id="af138-211">50,040–50,059</span></span>|<span data-ttu-id="af138-212">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="af138-212">TCP/UDP</span></span>|<span data-ttu-id="af138-213">18</span><span class="sxs-lookup"><span data-stu-id="af138-213">18</span></span>|<span data-ttu-id="af138-214">Assured Forwarding(AF21)</span><span class="sxs-lookup"><span data-stu-id="af138-214">Assured Forwarding (AF21)</span></span>|
||||||

<span data-ttu-id="af138-215">이러한 설정을 사용할 때 다음을 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="af138-215">Be aware of the following when you use these settings:</span></span>

- <span data-ttu-id="af138-216">향후 ExpressRoute를 구현할 계획이고 아직 QoS를 구현하지 않은 경우 DSCP 값이 보낸 사람에서 받는 사람으로 동일한지 지침을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-216">If you plan to implement ExpressRoute in the future and haven't yet implemented QoS, we recommend that you follow the guidance so that DSCP values are the same from sender to receiver.</span></span>

- <span data-ttu-id="af138-217">모바일 클라이언트 및 Teams 디바이스를 비롯한 모든 클라이언트는 이러한 포트 범위를 사용하며, 이러한 원본 포트 범위를 사용하는 구현하는 모든 DSCP 정책의 영향을 받는다.</span><span class="sxs-lookup"><span data-stu-id="af138-217">All clients, including mobile clients and Teams devices, will use these port ranges and will be affected by any DSCP policy you implement that uses these source port ranges.</span></span> <span data-ttu-id="af138-218">동적 포트를 계속 사용할 클라이언트는 브라우저 기반 클라이언트(참가자가 브라우저를 사용하여 모임에 참가할 수 있도록 하는 클라이언트)입니다.</span><span class="sxs-lookup"><span data-stu-id="af138-218">The only clients that will continue to use dynamic ports are the browser-based clients (clients that let participants join meetings by using their browsers).</span></span>

- <span data-ttu-id="af138-219">Mac 클라이언트는 동일한 포트 범위를 사용하나 오디오(EF) 및 비디오(AF41)에 대해 하드 코딩된 값도 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-219">Although the Mac client uses the same port ranges, it also uses hard-coded values for audio (EF) and video (AF41).</span></span> <span data-ttu-id="af138-220">이러한 값은 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-220">These values aren't configurable.</span></span>

- <span data-ttu-id="af138-221">나중에 사용자 환경을 개선하기 위해 포트 범위를 조정해야 하는 경우 포트 범위는 겹칠 수 없습니다. 서로 인접해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-221">If you later need to adjust the port ranges to improve user experience, the port ranges can't overlap and should be adjacent to each other.</span></span>

## <a name="migrate-qos-to-teams"></a><span data-ttu-id="af138-222">QoS를 Teams로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="af138-222">Migrate QoS to Teams</span></span>

<span data-ttu-id="af138-223">이전에 비즈니스용 Skype Online(QoS 태그 지정 및 포트 범위 포함)을 배포한 경우 이제 배포 중입니다.</span><span class="sxs-lookup"><span data-stu-id="af138-223">If you've previously deployed Skype for Business Online, including QoS tagging and port ranges, and are now deploying.</span></span> <span data-ttu-id="af138-224">Teams, Teams는 기존 구성을 존중하며 비즈니스용 Skype 클라이언트와 동일한 포트 범위 및 태그 지정을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af138-224">Teams, Teams will respect the existing configuration and will use the same port ranges and tagging as the Skype for Business client.</span></span> <span data-ttu-id="af138-225">대부분의 경우 추가 구성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-225">In most cases, no additional configuration will be needed.</span></span>

> [!NOTE]
> <span data-ttu-id="af138-226">그룹 정책을 통해 애플리케이션 이름 QoS 태그를 사용하는 경우 애플리케이션 이름으로 Teams.exe 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-226">If you're using Application Name QoS tagging via Group Policy, you must add Teams.exe as the application name.</span></span>

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a><span data-ttu-id="af138-227">PowerShell을 사용하여 Windows의 Teams에서 QoS 구현</span><span class="sxs-lookup"><span data-stu-id="af138-227">Implement QoS in Teams on Windows using PowerShell</span></span>

<span data-ttu-id="af138-228">**오디오용 QoS 설정**</span><span class="sxs-lookup"><span data-stu-id="af138-228">**Set QoS for audio**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

<span data-ttu-id="af138-229">**비디오용 QoS 설정**</span><span class="sxs-lookup"><span data-stu-id="af138-229">**Set QoS for video**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

<span data-ttu-id="af138-230">**공유를 위한 QoS 설정**</span><span class="sxs-lookup"><span data-stu-id="af138-230">**Set QoS for sharing**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a><span data-ttu-id="af138-231">Teams 관리 센터에서 원본 포트 관리</span><span class="sxs-lookup"><span data-stu-id="af138-231">Managing source ports in the Teams admin center</span></span>

<span data-ttu-id="af138-232">Teams에서 다양한 워크로드에서 사용되는 QoS 원본 포트를 적극적으로 관리하고 필요한 경우 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-232">In Teams, QoS source ports used by the different workloads should be actively managed, and adjusted as necessary.</span></span> <span data-ttu-id="af138-233">각 미디어 유형에 [](#choose-initial-port-ranges-for-each-media-type)대한 초기 포트 범위 선택에서 표를 참조하면 포트 범위를 조정할 수 있지만 DSCP 표시는 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-233">Referring to the table in [Choose initial port ranges for each media type](#choose-initial-port-ranges-for-each-media-type), the port ranges are adjustable, but the DSCP markings aren't configurable.</span></span> <span data-ttu-id="af138-234">이러한 설정을 구현한 후 특정 미디어 유형에 더 많은 포트가 필요하거나 적은 수의 포트가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-234">Once you have implemented these settings, you might find that more or fewer ports are needed for a given media type.</span></span> <span data-ttu-id="af138-235">[사용자당 통화](use-call-analytics-to-troubleshoot-poor-call-quality.md) 분석 및 [CQD(통화](turning-on-and-using-call-quality-dashboard.md) 품질 대시보드)는 Teams가 구현된 후 포트 범위를 조정하고 요구가 변경될 때 주기적으로 포트 범위를 조정하는 결정을 내리는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="af138-235">[Per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md) and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) should be used in making a decision to adjust port ranges after Teams has been implemented, and periodically as needs change.</span></span>

> [!NOTE]
> <span data-ttu-id="af138-236">비즈니스용 Skype Online용 원본 포트 범위 및 DSCP 마킹에 따라 QoS를 이미 구성한 경우 Teams에 동일한 구성이 적용될 수 있으며, 비즈니스용 Skype Online에 대해 구성된 범위와 일치하도록 Teams에서 사용하는 범위를 설정해야 할 수 있습니다. [](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)</span><span class="sxs-lookup"><span data-stu-id="af138-236">If you've already configured QoS based on source port ranges and DSCP markings for Skype for Business Online, the same configuration will apply to Teams and no further client or network changes to the mapping will be required, though you may have to [set the ranges used in Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) to match what was configured for Skype for Business Online.</span></span>

<span data-ttu-id="af138-237">이전에 비즈니스용 Skype Server On-프레미스를 배포한 경우 QoS 정책을 다시 검사해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-237">If you’ve previously deployed Skype for Business Server on-premises, you might need to re-examine your QoS policies.</span></span> <span data-ttu-id="af138-238">확인한 포트 범위 설정과 일치하도록 정책을 조정하여 Teams에 대한 고품질 사용자 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-238">Adjust the policies to match port range settings you've verified provide a quality user experience for Teams.</span></span>

## <a name="validate-your-qos-implementation"></a><span data-ttu-id="af138-239">QoS 구현 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="af138-239">Validate your QoS implementation</span></span>

<span data-ttu-id="af138-240">QoS가 효과적이기 위해 GPO에서 설정한 DSCP 값이 호출의 양쪽 끝에 존재해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-240">For QoS to be effective, the DSCP value set by the GPO needs to be present at both ends of a call.</span></span> <span data-ttu-id="af138-241">Teams 클라이언트에서 생성된 트래픽을 분석하여 Teams 워크로드 트래픽이 네트워크를 통해 이동하면 DSCP 값이 변경되거나 제거되지 않는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-241">By analyzing the traffic generated by the Teams client, you can verify that the DSCP value isn’t changed or stripped out when the Teams workload traffic moves through the network.</span></span>

<span data-ttu-id="af138-242">바람직하게는 네트워크 시작 지점에서 트래픽을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="af138-242">Preferably, you capture traffic at the network egress point.</span></span> <span data-ttu-id="af138-243">스위치 또는 라우터에서 포트 미러링을 사용하여 이를 도울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af138-243">You can use port mirroring on a switch or router to help with this.</span></span>

## <a name="implement-qos-for-other-devices"></a><span data-ttu-id="af138-244">다른 디바이스에 대한 QoS 구현</span><span class="sxs-lookup"><span data-stu-id="af138-244">Implement QoS for other devices</span></span>

<span data-ttu-id="af138-245">Intune, Surface, iOS, Android 및 Mac용 QoS 구현에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af138-245">Read these topics for information about implementing QoS for Intune, Surface, iOS, Android, and Mac</span></span>

- [<span data-ttu-id="af138-246">Surface Hub 2S용 QoS</span><span class="sxs-lookup"><span data-stu-id="af138-246">QoS for Surface Hub 2S</span></span>](/surface-hub/surface-hub-2s-manage-intune)

- [<span data-ttu-id="af138-247">Surface Hub용 QoS</span><span class="sxs-lookup"><span data-stu-id="af138-247">QoS for Surface Hub</span></span>](/surface-hub/surface-hub-qos)

- [<span data-ttu-id="af138-248">iOS, Android 및 Mac용 QoS</span><span class="sxs-lookup"><span data-stu-id="af138-248">QoS for iOS, Android, and Mac</span></span>](./meeting-settings-in-teams.md?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a><span data-ttu-id="af138-249">관련 항목</span><span class="sxs-lookup"><span data-stu-id="af138-249">Related topics</span></span>

- [<span data-ttu-id="af138-250">비디오: 네트워크 계획</span><span class="sxs-lookup"><span data-stu-id="af138-250">Video: Network Planning</span></span>](https://aka.ms/teams-networking)

- [<span data-ttu-id="af138-251">Microsoft Teams에 대한 조직의 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="af138-251">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)

- [<span data-ttu-id="af138-252">Teams 클라이언트에서 QoS 구현</span><span class="sxs-lookup"><span data-stu-id="af138-252">Implement QoS in the Teams client</span></span>](QoS-in-Teams-clients.md)