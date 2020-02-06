---
title: 비즈니스용 Skype 서버의 Edge 서버 시나리오
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: 비즈니스용 Skype 서버에서 Edge 서버 토폴로지를 계획 하는 데 도움이 되도록 이러한 시나리오를 검토 합니다.'
ms.openlocfilehash: a1d721ffabb78985d90848784cd587bda96300d5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803358"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="a14ac-103">비즈니스용 Skype 서버의 Edge 서버 시나리오</span><span class="sxs-lookup"><span data-stu-id="a14ac-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="a14ac-104">**요약:** 비즈니스용 Skype 서버에서 Edge 서버 토폴로지를 계획 하는 데 도움이 되도록 이러한 시나리오를 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="a14ac-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="a14ac-105">구현 하려는 비즈니스용 Skype 서버 Edge 서버 토폴로지를 시각화 하 고 결정 하는 데 도움이 되는 몇 가지 시나리오 다이어그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="a14ac-106">좋은 후보자를 선택한 후에는 처리 해야 하는 환경 요구 사항에 대해 자세히 읽어 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="a14ac-107">다음은 시나리오에 적용 될 수 있으므로 먼저 언급 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="a14ac-108">이러한 수치 (예: 샘플 IPv4 및 IPv6 데이터)만 표시 되며, 실제 통신 흐름을 나타내지 않고, 가능 소통량에 대 한 높은 수준의 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-108">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic.</span></span> <span data-ttu-id="a14ac-109">포트 세부 정보는 아래의 각 시나리오에 대 한 포트 다이어그램 에서도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-109">Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="a14ac-110">이 다이어그램은 내부에 대 한 외부 인터페이스 및 .net에 대 한 .com을 표시 합니다 (샘플 자료 이기도 함). 물론 사용자의 고유한 최종 가장자리 요금제를 함께 배치 하는 경우에는 자신의 항목이 매우 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="a14ac-111">다이어그램에는 디렉터 (선택적 구성 요소)가 포함 되지 않지만이에 대 한 자세한 내용은 다른 계획 항목에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="a14ac-112">위에서 설명한 것 처럼 다이어그램에 샘플 IPv6 데이터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="a14ac-113">비즈니스용 [Skype server의 Edge 서버 배포 계획](edge-server-deployments.md) 에 있는 대부분의 설명서는 IPv4를 참조 하지만, IPv6을 사용 하려는 경우에는 확실히 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="a14ac-114">지정 된 주소 공간에는 IPv6 주소가 필요 하며, IPv4 Ip와 마찬가지로 내부 및 외부 주소 지정을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="a14ac-115">Windows 덕분에 IPv4 및 IPv6에 대 한 별도의 네트워크 스택과 혼합 된 이중 스택 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="a14ac-116">필요한 경우 IPv4 및 IPv6 주소를 동시에 지정할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="a14ac-117">NAT64 (IPv6 to IPv4) 및 NAT66 (ipv6 to IPv6))를 허용 하는 NAT 장치가 있으며,이는 비즈니스용 Skype 서버에서 사용 하기에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a14ac-118">CAC (Call 허용 제어)를 사용 하는 경우 내부 인터페이스에서 IPv4를 사용 하 여 작동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="a14ac-119">개인 IP 주소 및 NAT를 사용 하는 단일 통합 비즈니스용 Skype 서버에 지 서버</span><span class="sxs-lookup"><span data-stu-id="a14ac-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="a14ac-120">이 시나리오에서는 고가용성을 위한 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-120">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="a14ac-121">이는 하드웨어를 덜 소모 하 고 배포를 단순화 한다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-121">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="a14ac-122">고가용성이 필요한 경우 아래에서 배율 통합 시나리오를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="a14ac-122">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![NAT를 사용 하는 개인 IP가 있는 단일 통합 된 가장자리에 대 한 edge 시나리오](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="a14ac-124">포트 다이어그램</span><span class="sxs-lookup"><span data-stu-id="a14ac-124">Port diagram</span></span>

<span data-ttu-id="a14ac-125">또한 통합 된 단일 Edge 서버의 포트에 대 한 다이어그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Edge 시나리오 단일 통합 모서리의 네트워크 경계](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="a14ac-127">공용 IP 주소를 사용 하는 단일 통합 비즈니스용 Skype 서버에 지 서버</span><span class="sxs-lookup"><span data-stu-id="a14ac-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="a14ac-128">이 시나리오에서는 고가용성을 위한 옵션이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-128">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="a14ac-129">이는 하드웨어를 덜 소모 하 고 배포를 단순화 한다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-129">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="a14ac-130">고가용성이 필요한 경우 아래에서 배율 통합 시나리오를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="a14ac-130">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![공용 IP를 사용 하는 단일 통합 Edge에 대 한 edge 시나리오](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="a14ac-132">포트 다이어그램</span><span class="sxs-lookup"><span data-stu-id="a14ac-132">Port diagram</span></span>

<span data-ttu-id="a14ac-133">또한 통합 된 단일 Edge 서버의 포트에 대 한 다이어그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Edge 시나리오 단일 통합 모서리의 네트워크 경계](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="a14ac-135">확장 된 통합 비즈니스용 Skype Server Edge 풀, DNS 부하 분산, 개인 IP 주소 및 NAT</span><span class="sxs-lookup"><span data-stu-id="a14ac-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="a14ac-136">이 시나리오에서는 Edge 배포에서 고가용성을 사용할 수 있으며,이를 통해 확장성 및 장애 조치 지원의 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![통합 된 Edge의 경계, NAT를 사용 하는 사설 IP로 DNS LB에 대 한 edge 시나리오](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="a14ac-138">포트 다이어그램</span><span class="sxs-lookup"><span data-stu-id="a14ac-138">Port diagram</span></span>

<span data-ttu-id="a14ac-139">또한 DNS 부하 분산을 사용 하 여 확장 통합 된 Edge 풀에 대 한 다이어그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![네트워크 경계 Edge 시나리오에서 DNS LB를 사용 하 여 통합 된 가장자리에 맞게 조정](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="a14ac-141">DNS 부하 분산 및 공용 IP 주소를 사용 하 여 비즈니스에 맞게 통합 된 비즈니스용 Skype 서버에 지 풀</span><span class="sxs-lookup"><span data-stu-id="a14ac-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="a14ac-142">이 시나리오에서는 Edge 배포에서 고가용성을 사용할 수 있으며,이를 통해 확장성 및 장애 조치 지원의 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![통합 된 가장자리를 확장 하는 edge 시나리오, 공용 IP에서 DNS LB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="a14ac-144">포트 다이어그램</span><span class="sxs-lookup"><span data-stu-id="a14ac-144">Port diagram</span></span>

<span data-ttu-id="a14ac-145">또한 DNS 부하 분산을 사용 하 여 확장 통합 된 Edge 풀에 대 한 다이어그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![네트워크 경계 Edge 시나리오에서 DNS LB를 사용 하 여 통합 된 가장자리에 맞게 조정](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="a14ac-147">하드웨어 부하 분산을 사용 하 여 확장 된 비즈니스용 Skype 서버 Edge 풀의 통합</span><span class="sxs-lookup"><span data-stu-id="a14ac-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="a14ac-148">이 시나리오에서는 Edge 배포에서 고가용성을 사용할 수 있으며,이를 통해 확장성 및 장애 조치 지원의 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a14ac-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![HLB 통합 가장자리의 크기를 조정 하는 edge 시나리오](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
