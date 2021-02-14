---
title: 비즈니스용 Skype 서버에서 E9-1-1용 SIP 트렁크 디자인
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: 비즈니스용 Skype 서버에서 SIP 트렁크 공급자를 사용하는 E9-1-1 배포에 대한 SIP 트렁크 토폴로지 계획 Enterprise Voice.
ms.openlocfilehash: ef30d721b59f29885004ee948055a91ca8af9490
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825798"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="dca27-103">비즈니스용 Skype 서버에서 E9-1-1용 SIP 트렁크 디자인</span><span class="sxs-lookup"><span data-stu-id="dca27-103">Design the SIP trunk for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="dca27-104">비즈니스용 Skype 서버에서 SIP 트렁크 공급자를 사용하는 E9-1-1 배포에 대한 SIP 트렁크 토폴로지 계획 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="dca27-104">Planning your SIP trunking topologies for an E9-1-1 deployment that uses SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="dca27-105">비즈니스용 Skype 서버는 SIP 트렁크를 사용하여 긴급 통화를 E9-1-1 서비스 공급자에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-105">Skype for Business Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="dca27-106">하나의 중앙 사이트, 여러 중앙 사이트 또는 각 분기 사이트에서 E9-1-1에 대한 긴급 서비스 SIP 트렁크를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-106">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="dca27-107">그러나 발신자 사이트와 긴급 서비스 SIP 트렁크를 호스팅하는 사이트 간의 WAN 링크를 사용할 수 없는 경우 연결이 끊어진 사이트에서 사용자가 걸은 통화에는 로컬 PSTN(Public Switched Telephone Network) 게이트웨이를 통해 ECRC로 통화를 라우팅하는 특수한 전화 사용 레코드가 사용자의 음성 정책에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-107">However, if the WAN link between the caller's site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user's voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="dca27-108">통화 허용 제어 동시 통화 제한이 적용되는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-108">The same is true if call admission control concurrent call limits are in effect.</span></span>
  
<span data-ttu-id="dca27-109">비즈니스용 Skype 서버 환경에서는 두 가지 방법으로 SIP 트렁크를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-109">There are two ways to implement a SIP trunk in a Skype for Business Server environment:</span></span>
  
- <span data-ttu-id="dca27-110">SIP 트렁크 공급자와 통신하기 위해 공개적으로 라우트된 밖으로 연결되는 인터페이스를 사용하는 다중Homed 중재 서버를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-110">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span>
    
- <span data-ttu-id="dca27-111">SBC(On-premises Session Border Controller)를 사용하여 중재 서버와 SIP 트렁크 공급자 서비스 간의 보안 경계 지점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-111">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider's services.</span></span>
    
<span data-ttu-id="dca27-112">두 번째 방법을 사용할 경우 선택한 SBC 작성 및 모델이 인증되었는지 확인하고 PIDF-LO(Presence Information Data Format Location Object) 위치 데이터를 SIP INVITE의 일부로 전달하도록 지원하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-112">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="dca27-113">그렇지 않으면 해당 위치 정보가 제거된 상태로 통화가 긴급 서비스 제공자에게 도착합니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-113">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="dca27-114">인증된 SBC에 대한 자세한 내용은 ["Microsoft Lync에](https://go.microsoft.com/fwlink/p/?LinkId=248425) 대해 자격을 갖춘 인프라" 및 "비즈니스용 Skype의 전화 통신 [인프라"를 참조하세요.](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)</span><span class="sxs-lookup"><span data-stu-id="dca27-114">For details about certified SBCs, see   ["Infrastructure Qualified for Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) and ["Telephony Infrastructure for Skype for Business"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).</span></span> 
  
<span data-ttu-id="dca27-115">E9-1-1 서비스 공급자는 중복을 위해 SC 쌍에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-115">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="dca27-116">중재 서버 토폴로지 및 통화 라우팅 구성과 관련하여 몇 가지 결정을 내릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-116">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="dca27-117">두 SBC를 모두 같은 피어로 처리하고 이들 간의 통화에 라운드 로빈 라우팅을 사용합니까? 아니면 SBC 하나를 기본 SBC로 지정하고 다른 SBC를 보조로 지정합니까?</span><span class="sxs-lookup"><span data-stu-id="dca27-117">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>
  
<span data-ttu-id="dca27-118">비즈니스용 Skype 서버에서 SIP 트렁크를 배포하는 데 대한 자세한 내용은 비즈니스용 [Skype 서버의 SIP](sip-trunking.md)트렁크를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dca27-118">For details about deploying a SIP trunk in Skype for Business Server, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span> <span data-ttu-id="dca27-119">다음 질문은 E9-1-1을 위한 SP 트렁크 배포 방법을 결정하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-119">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>
  
 <span data-ttu-id="dca27-120">**SIP 트렁크를 배포할 때 사용할 연결(전용 임대 연결 또는 공유 인터넷 연결)**</span><span class="sxs-lookup"><span data-stu-id="dca27-120">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>
  
> <span data-ttu-id="dca27-p105">긴급 통화는 항상 연결되어야 합니다. 따라서 전용선을 사용하면 연결이 네트워크의 다른 트래픽에 의해 선취되지 않으며, QoS(서비스 품질)를 구현할 수 있습니다. 공용 인터넷을 통해 긴급 서비스 제공자에 연결할 경우 긴급 통화의 기밀성을 보장해야 하며 IPSec 암호화가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-p105">It is important that emergency calls always connect. A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS). Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span> 
    
 <span data-ttu-id="dca27-124">**E9-1-1 배포는 내재해성을 위해 설계합니까?**</span><span class="sxs-lookup"><span data-stu-id="dca27-124">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>
  
> <span data-ttu-id="dca27-125">이 배포는 긴급 솔루션이므로 복구가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-125">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="dca27-126">재해 내재해성 위치에 기본 및 보조 중재 서버 및 SIP 트렁크를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-126">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="dca27-127">지원할 사용자에게 가장 가까운 기본 중재 서버를 배포하고 다른 지리적 위치에 있는 보조 중재 서버를 통해 장애 조치(failover) 통화를 라우팅하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-127">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span> 
    
 <span data-ttu-id="dca27-128">**각 지점에 대해 별도의 SIP 트렁크를 배포할지 여부**</span><span class="sxs-lookup"><span data-stu-id="dca27-128">**Should you deploy a separate SIP trunk for each branch office?**</span></span>
  
> <span data-ttu-id="dca27-129">비즈니스용 Skype 서버는 지점에서 음성 탄력성 처리를 위한 몇 가지 전략을 제공합니다. 예를 들어, 탄력적인 데이터 네트워크가 있는 경우, 각 분기에 SIP 트렁크를 배포하거나, 정전 시 로컬 게이트웨이로 통화를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-129">Skype for Business Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="dca27-130">자세한 내용은 비즈니스용 [Skype 서버의 SIP 트렁크를 참조하세요.](sip-trunking.md)</span><span class="sxs-lookup"><span data-stu-id="dca27-130">For details, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
    
 <span data-ttu-id="dca27-131">**CAC(통화 허용 제어)가 사용하도록 설정되는지 여부**</span><span class="sxs-lookup"><span data-stu-id="dca27-131">**Is call admission control (CAC) enabled?**</span></span>
  
> <span data-ttu-id="dca27-132">비즈니스용 Skype 서버는 일반 통화와 다른 응급 통화를 처리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-132">Skype for Business Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="dca27-133">따라서 대역폭 관리 또는 CAC(통화 허용 제어)가 E9-1-1 구성에 좋지 않은 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-133">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="dca27-134">CAC가 사용하도록 설정되어 있으며 긴급 통화를 라우팅하는 링크에서 구성된 제한을 초과한 경우, 긴급 통화가 차단되거나 로컬 PSTN 게이트웨이로 라우팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-134">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="dca27-135">이 항목의 앞 부분에 표시된 것처럼 이러한 통화는 위치 데이터를 포함하지 않으며 수동으로 ECRC로 라우팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dca27-135">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>
    

