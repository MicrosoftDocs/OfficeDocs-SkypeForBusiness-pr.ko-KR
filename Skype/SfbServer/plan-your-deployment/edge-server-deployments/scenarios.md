---
title: 비즈니스용 Skype 서버의 에지 서버 시나리오
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: '요약: 비즈니스용 Skype 서버에서 에지 서버 토폴로지 계획에 도움이 되는 이러한 시나리오를 검토합니다.'
ms.openlocfilehash: cfcc1e8b34576fbec85464fb8d5e35903b47d8ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813798"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="f52f4-103">비즈니스용 Skype 서버의 에지 서버 시나리오</span><span class="sxs-lookup"><span data-stu-id="f52f4-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="f52f4-104">**요약:** 이러한 시나리오를 검토하여 비즈니스용 Skype 서버에서 에지 서버 토폴로지 계획에 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="f52f4-105">구현할 비즈니스용 Skype 서버 에지 서버 토폴로지의 시각화 및 결정에 도움이 되는 몇 가지 시나리오 다이어그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="f52f4-106">좋은 후보를 선택하고 나면 해결해야 하는 환경 요구 사항을 읽어 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="f52f4-107">다음은 모든 시나리오에 적용할 수 있으므로 먼저 언급하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="f52f4-108">예를 들어 예제 IPv4 및 IPv6 데이터가 포함된 등의 용도로만 표시되는 이러한 수치는 실제 통신 흐름을 나타내는 것이 아니라 가능한 트래픽에 대한 높은 수준의 보기를 나타내기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-108">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic.</span></span> <span data-ttu-id="f52f4-109">아래의 각 시나리오에 대한 포트 다이어그램에서도 포트 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-109">Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="f52f4-110">다이어그램은 외부 인터페이스의 경우 .com을 표시하고 내부에는 .net(샘플 자료)을 보여 주며, 물론 최종 에지 계획을 세우면 항목 자체가 상당히 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="f52f4-111">어떤 다이어그램에서도 선택적 구성 요소인 Director를 포함하지 않지만 별도로 읽을 수 있습니다(다른 계획 항목에 설명).</span><span class="sxs-lookup"><span data-stu-id="f52f4-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="f52f4-112">위에서 설명한 대로 다이어그램에는 예제 IPv6 데이터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="f52f4-113">비즈니스용 [Skype](edge-server-deployments.md) 서버의 에지 서버 배포 계획에 있는 대부분의 설명서는 IPv4를 참조하지만 IPv6을 사용하려는 경우 확실히 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="f52f4-114">할당된 주소 공간에 IPv6 주소가 필요하며 IPv4 IP와 같은 내부 및 외부 주소로 작업해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="f52f4-115">Windows 덕분에 IPv4 및 IPv6에 대해 별도의 고유한 네트워크 스택인 이중 스택 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="f52f4-116">이렇게 하면 필요한 경우 IPv4 및 IPv6 주소를 동시 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="f52f4-117">NAT64(IPv6 - IPv4) 및 NAT66(IPv6 - IPv6)을 허용하는 NAT 장치가 있으며 비즈니스용 Skype 서버에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f52f4-118">CAC(통화 제어)를 사용하는 경우 내부 인터페이스에서 IPv4를 사용하여 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="f52f4-119">개인 IP 주소 및 NAT가 있는 단일 통합 비즈니스용 Skype 서버 에지 서버</span><span class="sxs-lookup"><span data-stu-id="f52f4-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="f52f4-120">이 시나리오에서는 고가용성을 위한 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-120">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="f52f4-121">이는 하드웨어에 대한 소비가 적고 배포가 더 간단하다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-121">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="f52f4-122">고가용성이 필요한 경우 아래에서 조정된 통합 시나리오를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="f52f4-122">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![NAT를 사용하는 개인 IP를 사용하는 단일 통합 에지 시나리오](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="f52f4-124">포트 다이어그램</span><span class="sxs-lookup"><span data-stu-id="f52f4-124">Port diagram</span></span>

<span data-ttu-id="f52f4-125">단일 통합 에지 서버에 대한 포트에 대한 다이어그램도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![에지 시나리오 단일 통합 에지의 네트워크 경계](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="f52f4-127">공용 IP 주소의 단일 통합 비즈니스용 Skype 서버 에지 서버</span><span class="sxs-lookup"><span data-stu-id="f52f4-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="f52f4-128">이 시나리오에서는 고가용성을 위한 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-128">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="f52f4-129">이는 하드웨어에 대한 소비가 적고 배포가 더 단순하다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-129">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="f52f4-130">고가용성이 필요한 경우 아래에서 조정된 통합 시나리오를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="f52f4-130">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![공용 IP를 통해 단일 통합 에지에 대한 에지 시나리오](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="f52f4-132">포트 다이어그램</span><span class="sxs-lookup"><span data-stu-id="f52f4-132">Port diagram</span></span>

<span data-ttu-id="f52f4-133">단일 통합 에지 서버에 대한 포트에 대한 다이어그램도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![에지 시나리오 단일 통합 에지의 네트워크 경계](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="f52f4-135">DNS 부하 분산을 사용하는 확장된 통합 비즈니스용 Skype 서버 에지 풀, 개인 IP 주소 및 NAT</span><span class="sxs-lookup"><span data-stu-id="f52f4-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="f52f4-136">이 시나리오에서는 에지 배포에서 고가용성을 사용할 수 있으며, 이 경우 확장성 및 장애 조치(failover) 지원의 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![확장 통합 에지, NAT 사용 개인 IP를 사용하는 DNS LB에 대한 에지 시나리오](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="f52f4-138">포트 다이어그램</span><span class="sxs-lookup"><span data-stu-id="f52f4-138">Port diagram</span></span>

<span data-ttu-id="f52f4-139">DNS 부하 분산을 사용하는 조정된 통합 에지 풀에 대한 다이어그램도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![DNS LB를 사용하는 에지 시나리오 확장 통합 에지의 네트워크 경계](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="f52f4-141">DNS 부하 분산 및 공용 IP 주소를 사용하는 확장된 통합 비즈니스용 Skype 서버 에지 풀</span><span class="sxs-lookup"><span data-stu-id="f52f4-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="f52f4-142">이 시나리오에서는 에지 배포에서 고가용성을 사용할 수 있으며, 이 경우 확장성 및 장애 조치(failover) 지원의 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![확장 통합 에지, 공용 IP를 사용하는 DNS LB에 대한 에지 시나리오](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="f52f4-144">포트 다이어그램</span><span class="sxs-lookup"><span data-stu-id="f52f4-144">Port diagram</span></span>

<span data-ttu-id="f52f4-145">DNS 부하 분산을 사용하는 조정된 통합 에지 풀에 대한 다이어그램도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![DNS LB를 사용하는 에지 시나리오 확장 통합 에지의 네트워크 경계](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="f52f4-147">하드웨어 부하 분산을 통해 확장된 통합 비즈니스용 Skype 서버 에지 풀</span><span class="sxs-lookup"><span data-stu-id="f52f4-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="f52f4-148">이 시나리오에서는 에지 배포에서 고가용성을 사용할 수 있으며, 이 경우 확장성 및 장애 조치(failover) 지원의 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f52f4-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![HLB를 통해 확장된 통합 에지에 대한 에지 시나리오](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
