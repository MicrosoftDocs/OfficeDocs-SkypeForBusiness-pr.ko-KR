---
title: 비즈니스용 Skype 서버의 중재 서버에 대한 배포 지침
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
ms.collection: IT_Skype16
ms.assetid: 7cc22b87-18d9-45e6-8402-015abd20f2e5
description: 이 항목에서는 중재 서버 배포에 대한 계획 지침을 설명합니다.
ms.openlocfilehash: 245916286fe5f1590581989b8a09daf637c03aa9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800093"
---
# <a name="deployment-guidelines-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="f1c65-103">비즈니스용 Skype 서버의 중재 서버에 대한 배포 지침</span><span class="sxs-lookup"><span data-stu-id="f1c65-103">Deployment guidelines for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="f1c65-104">이 항목에서는 중재 서버 배포에 대한 계획 지침을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-104">This topic describes planning guidelines for Mediation Server deployment.</span></span>
  
## <a name="collocated-or-stand-alone-mediation-server"></a><span data-ttu-id="f1c65-105">함께 사용되거나 독립 실행형 중재 서버인가요?</span><span class="sxs-lookup"><span data-stu-id="f1c65-105">Collocated or Stand-alone Mediation Server?</span></span>

<span data-ttu-id="f1c65-106">중재 서버는 기본적으로 중앙 사이트의 프런트 엔드 풀에 Standard Edition 서버 또는 프런트 엔드 서버에 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-106">Mediation Server is, by default, collocated on the Standard Edition server or Front End Server in a Front End pool at central sites.</span></span> <span data-ttu-id="f1c65-107">처리할 수 있는 PSTN(Public Switched Telephone Network) 통화 수와 풀에 필요한 컴퓨터 수는 다음에 따라 달라지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-107">The number of public switched telephone network (PSTN) calls that can be handled and the number of machines required in the pool will depend on:</span></span>
  
- <span data-ttu-id="f1c65-108">중재 서버 풀에서 제어하는 게이트웨이 피어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-108">The number of gateway peers that the Mediation Server pool controls.</span></span>
    
- <span data-ttu-id="f1c65-109">이러한 게이트웨이를 통한 대량 트래픽 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-109">The high-volume traffic periods through those gateways.</span></span>
    
- <span data-ttu-id="f1c65-110">미디어가 중재 서버를 우회하는 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-110">The percentage of calls that are calls whose media bypass the Mediation Server.</span></span>
    
<span data-ttu-id="f1c65-111">계획할 때 미디어 우회를 지원하지 않는 PSTN 통화 및 A/V 회의에 대한 미디어 처리 요구 사항과 지원해야 하는 통화 수에 대한 신호 조작을 처리하는 데 필요한 처리를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-111">When you're planning, be sure to take into account the media processing requirements for PSTN calls and A/V conferences that don't support media bypass, as well as the processing needed to handle signaling interactions for the number of busy-hour calls that need to be supported.</span></span> <span data-ttu-id="f1c65-112">CPU가 충분하지 않은 경우 중재 서버의 독립 실행형 풀을 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-112">If you don't have enough CPU, you'll need to deploy a stand-alone pool of Mediation Servers.</span></span> <span data-ttu-id="f1c65-113">또한 PSTN 게이트웨이, IP-PBX 및 SBC는 하나의 풀에 함께 있는 중재 서버에 의해 제어되는 하위 집합과 하나 이상의 독립 실행형 풀에 있는 독립 실행형 중재 서버로 분할해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-113">Additionally, PSTN gateways, IP-PBXs, and SBCs will need to be split into subsets that are controlled by the collocated Mediation Servers in one pool and the stand-alone Mediation Servers in one or more stand-alone pools.</span></span>
  
<span data-ttu-id="f1c65-114">중재 서버 풀과 상호 작용할 수 없는 PSTN 게이트웨이, IP-PBX 또는 SC(Session Border Controller)를 배포한 경우 단일 중재 서버로 구성된 독립 실행형 풀과 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-114">If you deployed PSTN gateways, IP-PBXs, or Session Border Controllers (SBCs) that lack the ability to interact with a pool of Mediation Servers, they'll need to be associated with a stand-alone pool consisting of a single Mediation Server.</span></span> <span data-ttu-id="f1c65-115">PSTN 게이트웨이, IP-PBXs 또는 SBC에서 필요한 몇 가지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-115">Some of the things your PSTN gateways, IP-PBXs or SBCs would need to do include:</span></span>
  
- <span data-ttu-id="f1c65-116">풀의 중재 서버에서 네트워크 계층 DNS(Domain Name System) 부하 분산을 수행하거나, 그렇지 않으면 트래픽을 풀의 모든 중재 서버로 균일하게 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-116">Perform network layer Domain Name System (DNS) load balancing across Mediation Servers in a pool (or otherwise route traffic uniformly to all Mediation Servers in a pool).</span></span>
    
- <span data-ttu-id="f1c65-117">풀에 있는 중재 서버의 트래픽을 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-117">Accept traffic from any Mediation Server in a pool.</span></span>
    
<span data-ttu-id="f1c65-118">비즈니스용 Skype 계획 도구를 사용하여 중재 서버를 프런트 엔드 풀과 함께 함께 설치하여 부하를 처리할 수 있는지 여부를 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-118">You can use the Skype for Business Planning Tool to evaluate whether collocating the Mediation Server with your Front End pool can handle the load.</span></span> <span data-ttu-id="f1c65-119">환경이 이러한 요구 사항을 충족할 수 없는 경우 독립 실행형 중재 서버 풀을 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-119">If your environment can't meet these requirements, then you'll need to deploy a stand-alone Mediation Server pool.</span></span>
  
## <a name="central-site-and-branch-site-considerations"></a><span data-ttu-id="f1c65-120">중앙 사이트 및 분기 사이트 고려 사항</span><span class="sxs-lookup"><span data-stu-id="f1c65-120">Central Site and Branch Site Considerations</span></span>

 <span data-ttu-id="f1c65-121">중앙 사이트의 중재 서버는 분기 사이트의 IP-PBX 또는 PSTN 게이트웨이에 대한 통화를 라우팅하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-121">Mediation Servers at the central site can be used to route calls for IP-PBXs or PSTN gateways at branch sites.</span></span> <span data-ttu-id="f1c65-122">그러나 SIP 트렁크를 배포하는 경우 각 트렁크가 종료되는 사이트에 중재 서버를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-122">If you deploy SIP trunks, however, you have to deploy a Mediation Server at the site where each trunk terminates.</span></span> <span data-ttu-id="f1c65-123">중앙 사이트에 중재 서버를 두면 분기 사이트의 IP-PBX 또는 PSTN 게이트웨이에 대한 통화를 라우팅할 때 미디어 우회를 사용할 필요가 없지만 미디어 우회를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-123">Having a Mediation Server at the central site route calls for an IP-PBX or PSTN gateway at a branch site doesn't require the use of media bypass, but a media bypass is recommended.</span></span> <span data-ttu-id="f1c65-124">미디어 우회를 사용하도록 설정할 수 있는 경우 미디어 경로가 신호 경로를 따라야 할 필요는 아니기 때문에 미디어 경로 대기 시간이 줄어들고 결과적으로 미디어 품질이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-124">That's because, if you can enable media bypass, it'll reduce media path latency and, consequently, result in improved media quality because the media path isn't required to follow the signaling path.</span></span> <span data-ttu-id="f1c65-125">미디어 바이패스는 풀의 처리 부하도 감소시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-125">Media bypass will also decrease the processing load on the pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f1c65-126">미디어 우회가 모든 PSTN 게이트웨이, IP-PBX 및 SBC와 상호 연결되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-126">Media bypass won't interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="f1c65-127">Microsoft는 인증된 파트너와 함께 PSTN 게이트웨이 및 SBC 집합을 테스트하고 Cisco IP-PBX를 통해 몇 가지 테스트를 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-127">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="f1c65-128">미디어 우회는 Unified Communications Open Interoperability Program에 나열된 제품 및 버전에서만 지원됩니다. Lync Server at Explore 테스트된 장치, 인프라 및 도구로 비즈니스용 Skype 환경을 지원하고 [확장합니다.](http://partnersolutions.skypeforbusiness.com/solutionscatalog)</span><span class="sxs-lookup"><span data-stu-id="f1c65-128">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program - Lync Server at [Explore tested devices, infrastructure, and tools that support and extend your Skype for Business experience](http://partnersolutions.skypeforbusiness.com/solutionscatalog).</span></span> 
  
<span data-ttu-id="f1c65-129">분기 사이트 복구가 필요한 경우에는 SBA(Survivable Branch Appliance) 또는 프런트 엔드 서버, 중재 서버 및 게이트웨이의 조합을 분기 사이트에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-129">If branch site resiliency is required, a Survivable Branch Appliance or combination of a Front End Server, a Mediation Server, and a gateway must be deployed at the branch site.</span></span> <span data-ttu-id="f1c65-130">분기 사이트 탄력성의 경우 현재 상태 및 회의가 사이트에서 탄력적이지 않다고 가정합니다. 음성에 대한 분기 사이트 계획에 대한 지침은 비즈니스용 Skype Enterprise Voice 대한 계획을 [참조하세요.](../enterprise-voice-solution/enterprise-voice-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="f1c65-130">(The assumption with branch site resiliency is that presence and conferencing are not resilient at the site.) For guidance on branch site planning for voice, see [Plan for Enterprise Voice resiliency in Skype for Business Server](../enterprise-voice-solution/enterprise-voice-resiliency.md).</span></span>
  
<span data-ttu-id="f1c65-131">IP-PBX와의 상호 작용의 경우 IP-PBX가 여러 초기 대화 및 RFC 3960 조작과의 초기 미디어 상호 작용을 올바르게 지원하지 않는 경우 IP-PBX에서 Lync 끝점으로의 수신 전화에 대해 인사말의 처음 몇 단어를 클리핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-131">For interactions with an IP-PBX, if the IP-PBX does not correctly support early media interactions with multiple early dialogs and RFC 3960 interactions, there can be clipping of the first few words of the greeting for incoming calls from the IP-PBX to Lync endpoints.</span></span> <span data-ttu-id="f1c65-132">신호가 완료되는 데 시간이 더 필요하기 때문에 중앙 사이트의 중재 서버가 분기 사이트에서 경로가 종료되는 IP-PBX에 대한 통화를 라우팅하는 경우 이 동작이 더 심각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-132">This behavior can be more severe if a Mediation Server at a central site is routing calls for an IP-PBX where the route terminates at a branch site, because more time is needed for signaling to complete.</span></span> <span data-ttu-id="f1c65-133">이 동작이 경험하는 경우 분기 사이트에 중재 서버를 배포하는 것만이 처음 몇 단어의 클리핑을 줄이는 유일한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-133">If you experience this behavior, deploying a Mediation Server at the branch site is the only way to reduce clipping of the first few words.</span></span>
  
<span data-ttu-id="f1c65-134">끝으로, 중앙 사이트에 TDM PBX가 있거나, IP-PBX가 PSTN 게이트웨이의 필요성을 해소하지 못한 경우 통화 경로에 중재 서버와 PBX를 연결하는 게이트웨이를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-134">Finally, if your central site has a TDM PBX, or if your IP-PBX does not eliminate the need for a PSTN gateway, then you must deploy a gateway on the call route connecting Mediation Server and the PBX.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f1c65-135">독립 실행형 중재 서버의 미디어 성능을 향상하려면 이러한 서버의 네트워크 어댑터에서 RSS(수신 쪽 크기 조정)를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-135">To improve the media performance of standalone Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on these servers.</span></span> <span data-ttu-id="f1c65-136">RSS를 사용하면 들어오는 패킷을 서버의 여러 프로세서에서 병렬로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1c65-136">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="f1c65-137">자세한 내용은["Windows Server의 수신측 확장 기능 향상"을 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkId=268731)</span><span class="sxs-lookup"><span data-stu-id="f1c65-137">For details, see "[Receive-Side Scaling Enhancements in Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=268731)".</span></span> <span data-ttu-id="f1c65-138">RSS를 사용하도록 설정하는 방법에 대한 자세한 내용은 네트워크 어댑터 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f1c65-138">For details about how to enable RSS, see your network adapter documentation.</span></span> 
  

