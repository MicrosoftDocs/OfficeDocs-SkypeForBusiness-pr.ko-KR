---
title: 클라우드 커넥터 버전에서 미디어 바이패스 계획
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e69ac58c-e8fe-40bc-a4c8-f0a0190fbaa7
description: 이 항목을 읽고 Cloud Connector Edition 버전 2.0 이상을 사용하여 미디어 우회를 구현하기 위한 계획 고려 사항을 검토합니다. 미디어 우회 배포에 대한 자세한 내용은 Deploy media bypass in Cloud Connector Edition를 참조하세요.
ms.openlocfilehash: bae10c77a6b382eaca7189ed6ae52960a6fb1bf9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096202"
---
# <a name="plan-for-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="4d0c1-104">클라우드 커넥터 버전에서 미디어 바이패스 계획</span><span class="sxs-lookup"><span data-stu-id="4d0c1-104">Plan for media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="4d0c1-105">이 항목을 읽고 Cloud Connector Edition 버전 2.0 이상을 사용하여 미디어 우회를 구현하기 위한 계획 고려 사항을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-105">Read this topic to review planning considerations for implementing media bypass with Cloud Connector Edition version 2.0 and later.</span></span> <span data-ttu-id="4d0c1-106">미디어 우회 배포에 대한 자세한 내용은 [Cloud Connector Edition에서 미디어 우회 배포를 참조하세요.](deploy-media-bypass-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="4d0c1-106">For information about deploying media bypass, see [Deploy media bypass in Cloud Connector Edition](deploy-media-bypass-in-cloud-connector.md).</span></span>
  
<span data-ttu-id="4d0c1-107">미디어 우회를 통해 클라이언트는 PSTN(Public Switched Telephone Network) 다음 홉(게이트웨이 또는 SBC(Session Border Controller))으로 직접 미디어를 보내고 미디어 경로에서 Cloud Connector Edition 구성 요소를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span>
  
<span data-ttu-id="4d0c1-108">미디어 우회는 대기 시간, 패킷 손실 가능성 및 잠재적인 오류 지점 수를 줄여 음성 품질을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-108">Media bypass can improve voice quality by reducing latency, the possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="4d0c1-109">우회된 통화에 대한 미디어 처리를 제거하면 클라우드 커넥터의 부하가 감소하여 동시 통화 수가 증가하고 확장성이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-109">Elimination of media processing for bypassed calls reduces the load on Cloud Connector, which enables a higher number of concurrent calls, and can improve scalability.</span></span> 
  
 <span data-ttu-id="4d0c1-110">미디어 처리 작업에서 클라우드 커넥터를 비우면 인프라에 필요한 Cloud Connector 어플라이언스 수가 줄어들 수 있으므로 가능하면 미디어 우회를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-110">Freeing Cloud Connector from media processing tasks may reduce the number of Cloud Connector appliances an infrastructure requires, so you should enable media bypass whenever possible.</span></span>
  
## <a name="how-media-bypass-affects-media-and-signaling-pathways"></a><span data-ttu-id="4d0c1-111">미디어 우회가 미디어 및 신호 경로에 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="4d0c1-111">How media bypass affects media and signaling pathways</span></span>

<span data-ttu-id="4d0c1-112">신호는 미디어 우회와 동일한 경로를 사용하나 미디어 흐름은 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-112">While signaling takes the same path with or without media bypass, the media flow will differ.</span></span> <span data-ttu-id="4d0c1-113">다음 다이어그램은 미디어 우회가 있는 경우와 없는 토폴로지의 미디어 및 신호 경로를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="4d0c1-113">The following diagrams show media and signaling pathways in topologies with and without media bypass.</span></span> 
  
<span data-ttu-id="4d0c1-114">예를 들어 미디어 우회를 적용하지 않는 다음 토폴로지에서 비즈니스용 Skype 클라이언트는 외부 번호로 PSTN 통화를 걸면 SIP 신호가 Microsoft 365 또는 Office 365로 전달됩니다. 이 신호는 최종 사용자 음성 정책에 따라 신호 트래픽을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-114">For example, in the following topology—which does not employ media bypass—a Skype for Business client places a PSTN call to an external number, the SIP signaling goes to Microsoft 365 or Office 365, which directs the signaling traffic according to the end-user voice policy.</span></span> <span data-ttu-id="4d0c1-115">클라우드 커넥터 사용자의 경우 음성 정책은 신호 트래픽을 클라우드 커넥터 에지 서버로 전달한 다음 신호 트래픽을 클라우드 커넥터 중재 서버를 통해 PSTN SBC(Session Border Controller) 또는 게이트웨이로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-115">For Cloud Connector users, the voice policy directs signaling traffic to the Cloud Connector Edge Server, which then routes the signaling traffic to a PSTN Session Border Controller (SBC) or gateway via the Cloud Connector Mediation Server.</span></span> <span data-ttu-id="4d0c1-116">미디어는 다음 다이어그램과 같이 비즈니스용 Skype 클라이언트에서 클라우드 커넥터 중재 서버로 전송된 다음 SBC 또는 게이트웨이로 흐름됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-116">Media flows from the Skype for Business client to the Cloud Connector Mediation Server, and then to the SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="4d0c1-117">**미디어 우회 없이 미디어 및 신호 경로**</span><span class="sxs-lookup"><span data-stu-id="4d0c1-117">**Media and signaling pathways without media bypass**</span></span>

![신호 미디어 우회 없이](../../media/5cd7e3bf-2565-4bd9-ad5a-f03e13c01060.png)
  
<span data-ttu-id="4d0c1-119">PSTN의 인바운드 통화는 역방향의 동일한 신호 경로를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-119">An inbound call from the PSTN uses the same signaling path in the reverse direction.</span></span> <span data-ttu-id="4d0c1-120">내부 사용자의 경우 미디어는 결국 비즈니스용 Skype 클라이언트와 클라우드 커넥터 중재 서버, SBC 또는 게이트웨이 간에 계속 흐르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-120">For internal users, media will still ultimately flow between the Skype for Business client and the Cloud Connector Mediation Server and then the SBC or gateway.</span></span>
  
<span data-ttu-id="4d0c1-121">미디어 우회를 사용하는 다음 토폴로지에서 신호는 동일한 경로를 사용하지만 다음 다이어그램과 같이 미디어는 비즈니스용 Skype 클라이언트와 SBC 또는 게이트웨이 간에 직접 흐르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-121">In the next topology—which does employ media bypass—signaling takes the same path, but media flows directly between the Skype for Business client and the SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="4d0c1-122">**미디어 우회를 통해 미디어 및 신호 경로**</span><span class="sxs-lookup"><span data-stu-id="4d0c1-122">**Media and signaling pathways with media bypass**</span></span>

![신호 미디어 우회를 통해 신호](../../media/60400c38-4921-4964-89f2-5e53b68fb497.png)
  
## <a name="multi-site-scenario-and-media-bypass"></a><span data-ttu-id="4d0c1-124">다중 사이트 시나리오 및 미디어 우회</span><span class="sxs-lookup"><span data-stu-id="4d0c1-124">Multi-site scenario and media bypass</span></span>

<span data-ttu-id="4d0c1-125">미디어 우회는 단일 Cloud Connector 어플라이언스를 사용하여 여러 사이트에 전화 통신 서비스를 제공하려는 경우도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-125">Media bypass is also useful when you want to provide telephony services to multiple sites using a single Cloud Connector appliance.</span></span> <span data-ttu-id="4d0c1-126">클라우드 커넥터는 원본 또는 대상 번호를 기준으로 통화를 라우팅할 수 없습니다. 대부분의 기업은 라우팅 결정을 내리기 위해 클라우드 커넥터 뒤에 SBC 또는 게이트웨이를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-126">Because Cloud Connector cannot route calls based on source or destination numbers, most enterprises deploy an SBC or gateway behind Cloud Connector to make routing decisions.</span></span> <span data-ttu-id="4d0c1-127">이 시나리오의 미디어 우회는 다음 다이어그램과 같이 클라이언트와 중앙 SBC 또는 게이트웨이 간의 홉을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-127">Media bypass in this scenario eliminates the hop between the client and the central SBC or gateway, as shown in the following diagram:</span></span>
  
<span data-ttu-id="4d0c1-128">**다중 사이트 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="4d0c1-128">**Multi-site application**</span></span>

![클라우드 커넥터 멀티사이트 예제](../../media/ace8dc3c-1082-46a2-b8b4-98cbf678620e.png)
  
1. <span data-ttu-id="4d0c1-130">SIP 트래픽은 취리히의 사용자에서 Microsoft 365 또는 Office 365로 흐르는 트래픽입니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-130">The SIP traffic flows from the user in Zurich to Microsoft 365 or Office 365.</span></span>
    
2. <span data-ttu-id="4d0c1-131">그런 다음 트래픽은 사용자 음성 라우팅 정책에 지정된 암스테르담의 클라우드 커넥터 어플라이언스로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-131">The traffic then routes to the Cloud Connector appliance in Amsterdam as specified in the user voice routing policy.</span></span>
    
3. <span data-ttu-id="4d0c1-132">암스테르담의 클라우드 커넥터 어플라이언스가 암스테르담의 중앙 게이트웨이로 SIP 트래픽을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-132">The Cloud Connector appliance in Amsterdam sends the SIP traffic to the central gateway in Amsterdam.</span></span>
    
4. <span data-ttu-id="4d0c1-133">암스테르담의 중앙 게이트웨이는 적절한 라우팅 결정을 내렸다가 취리히의 SBC 또는 게이트웨이로 트래픽을 보내고, 미디어는 비즈니스용 Skype 클라이언트와 SBC 또는 암스테르담의 게이트웨이 간에 직접 흐르는 동안에 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-133">The central gateway in Amsterdam makes the appropriate routing decisions, and then sends the traffic to an SBC or gateway in Zurich, while media flows directly between the Skype for Business client and SBC or gateway in Amsterdam.</span></span>
    
   <span data-ttu-id="4d0c1-134">이 방법을 사용하면 클라우드 커넥터가 중앙 집중화된 클라우드 커넥터 배포당 더 많은 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-134">This approach allows serving more users per one Cloud Connector deployment where Cloud Connector is centralized.</span></span> <span data-ttu-id="4d0c1-135">클라우드 커넥터가 미디어 경로에서 제거된 경우에도 중앙 집중식 다중 사이트 시나리오 미디어에서 중앙 SBC 또는 게이트웨이를 통과하는 데 필요한 경우 WAN을 두 번 트래버스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-135">Even though Cloud Connector is eliminated from the media path, in a centralized multi-site scenario media may still traverse the WAN twice as required to flow through the centralized SBC or gateway.</span></span>
  
<span data-ttu-id="4d0c1-136">클라이언트가 아웃바운드 통화를 걸고 회사 네트워크 외부에 있는 경우 미디어 트래픽은 다음 다이어그램과 같이 클라우드 커넥터의 Edge 및 중재 서버와 취리히와 암스테르담 간의 WAN 링크를 통해 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-136">If a client is outside the corporate network placing an outbound call, the media traffic flows via the Edge and Mediation servers of Cloud Connector and WAN link between Zurich and Amsterdam, as shown in the following diagram:</span></span>
  
![클라우드 커넥터 멀티사이트 예제 2](../../media/ef95839c-4552-440e-9698-7615707a1b50.png)
  
## <a name="supported-clients-for-media-bypass"></a><span data-ttu-id="4d0c1-138">미디어 우회에 지원되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="4d0c1-138">Supported clients for media bypass</span></span>

<span data-ttu-id="4d0c1-139">미디어 우회의 첫 번째 릴리스에서 지원되는 클라이언트는 엔터프라이즈용 Microsoft 365 앱 버전 16.0.7870.2020 이상에 있는 비즈니스용 Skype 2016 Windows 클라이언트뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-139">With the first release of media bypass, the only supported client is the Skype for Business 2016 Windows Client that is part of Microsoft 365 Apps for enterprise, version 16.0.7870.2020 or greater.</span></span> <span data-ttu-id="4d0c1-140">고객은 현재, 지연 또는 첫 번째 릴리스 지연 채널을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-140">Customers can use any channel: Current, Deferred, or First Release Deferred.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4d0c1-141">비즈니스용 Skype 클라이언트와 함께 클라이언트 VPN 솔루션을 사용하는 경우 미디어 우회는 VPN 분할 터널 구성에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-141">If you are using a client VPN solution in combination with the Skype for Business client, then media bypass is supported only with a VPN split-tunnel configuration.</span></span> 
  
<span data-ttu-id="4d0c1-142">릴리스 채널에 대한 자세한 내용은 엔터프라이즈용 [Microsoft 365 앱의](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US)업데이트 채널 개요를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-142">For more information about the release channels, see [Overview of update channels for Microsoft 365 Apps for enterprise](https://support.office.com/article/Overview-of-update-channels-for-Office-365-ProPlus-9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
<span data-ttu-id="4d0c1-143">다른 채널에 있는 클라이언트의 현재 릴리스 버전은 엔터프라이즈용 [Microsoft 365 앱 업데이트에 대한 릴리스 정보를 참조하세요.](/officeupdates/release-notes-office365-proplus)</span><span class="sxs-lookup"><span data-stu-id="4d0c1-143">For the current release version of the clients in different channels, see [Release information for updates to Microsoft 365 Apps for enterprise](/officeupdates/release-notes-office365-proplus).</span></span> 
  
## <a name="cloud-connector-capacity-considerations-with-media-bypass"></a><span data-ttu-id="4d0c1-144">미디어 우회를 사용하여 클라우드 커넥터 용량 고려 사항</span><span class="sxs-lookup"><span data-stu-id="4d0c1-144">Cloud Connector capacity considerations with media bypass</span></span>

<span data-ttu-id="4d0c1-145">미디어 우회 없이 하드웨어에 따라 클라우드 커넥터 어플라이언스에서 미디어가 중재 서버를 통과해야 하는 동시 통화를 50~500개까지 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-145">Without media bypass—and depending on the hardware—a Cloud Connector appliance can handle from 50 to 500 simultaneous calls that require media to travel through a Mediation Server.</span></span> <span data-ttu-id="4d0c1-146">자세한 내용은 [Plan for Skype for Business Cloud Connector Edition을 참조하세요.](./plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="4d0c1-146">For more information, see [Plan for Skype for Business Cloud Connector Edition](./plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
<span data-ttu-id="4d0c1-147">미디어 우회를 사용하도록 설정하면 지원되는 버전의 내부 클라이언트가 중재 서버를 사용하지 않습니다. 따라서 내부 클라이언트 수가 크게 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-147">With media bypass enabled, internal clients on the supported version do not use the Mediation Server, so the number of internal clients can increase significantly.</span></span> 
  
<span data-ttu-id="4d0c1-148">위에서 설명한 대로 외부 클라이언트 또는 지원되지 않는 클라이언트는 미디어에 클라우드 커넥터 Edge 및 중재 서버를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-148">As noted above, external clients or unsupported clients will use the Cloud Connector Edge and Mediation servers for media.</span></span> <span data-ttu-id="4d0c1-149">사이트에 배치해야 하는 클라우드 커넥터 어플라이언스 수를 계산할 때 지원되지 않는 클라이언트의 외부 사용자 및 사용자의 트래픽을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-149">When calculating how many Cloud Connector appliances should be placed in a site, you must consider traffic from external users and users on unsupported clients.</span></span>
  
## <a name="cloud-connector-supports-always-bypass-mode"></a><span data-ttu-id="4d0c1-150">클라우드 커넥터에서 항상 우회 모드를 지원</span><span class="sxs-lookup"><span data-stu-id="4d0c1-150">Cloud Connector supports Always Bypass mode</span></span>

<span data-ttu-id="4d0c1-151">클라우드 커넥터는 항상 우회 모드만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-151">Cloud Connector supports Always Bypass mode only.</span></span> <span data-ttu-id="4d0c1-152">In on-premises environments, there are two options: Always Bypass and Use Site and Region Information.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-152">In on-premises environments, there are two options: Always Bypass and Use Site and Region Information.</span></span>
  
<span data-ttu-id="4d0c1-153">항상 우회는 내부 클라이언트가 있는 모든 PSTN 통화에 대해 원본 또는 대상 지점으로 미디어 우회가 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-153">Always Bypass means that media bypass will be attempted for all PSTN calls with internal clients as an origin or destination point.</span></span> <span data-ttu-id="4d0c1-154">클라이언트가 내부인지 외부인지 확인하기 위해 중재 서버 가상 컴퓨터의 웹 사이트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-154">To determine if the client is internal or external, a web site on the mediation server virtual machine is used.</span></span> <span data-ttu-id="4d0c1-155">클라이언트가 사이트에 도달할 수 있는 경우 내부 및 미디어 우회가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-155">If the client can reach the site, it is considered internal and media bypass is used.</span></span> <span data-ttu-id="4d0c1-156">클라이언트가 사이트에 도달할 수 없는 경우(예: 클라이언트가 홈 네트워크에 있는 경우) 미디어 우회가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-156">If the client cannot reach the site (for example the client is on a home network), media bypass is not used.</span></span> 
  
<span data-ttu-id="4d0c1-157">항상 우회를 사용하려면 PSTN 사이트 내의 PSTN 게이트웨이와 사용자 간의 방해되지 않은 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-157">Always Bypass requires unobstructed connectivity between users and the PSTN gateways within a PSTN Site.</span></span> 
  
<span data-ttu-id="4d0c1-158">자세한 내용은 [Plan for Skype for Business Cloud Connector Edition을 참조하세요.](./plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="4d0c1-158">For more information, see [Plan for Skype for Business Cloud Connector Edition](./plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
<span data-ttu-id="4d0c1-159">예를 들어 아래 다이어그램에서 유럽 사용자는 암스테르담의 세 SC(Session Border Controller)에 잘 연결되어 있어야 하지만 미국 서부 사용자는 시애틀의 두 SBC에 잘 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-159">For example, in the diagram below, Europe users must be well connected to the three Session Border Controllers (SBCs) in Amsterdam while US West users must be well connected to the two SBCs in Seattle.</span></span> <span data-ttu-id="4d0c1-160">잘 연결되면 SBC 또는 게이트웨이와 동일한 네트워크 사이트에 위치하거나 적절한 대역폭을 사용하는 WAN 링크를 통해 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-160">Well connected means that they are either located in the same network sites as the SBCs or gateways, or over WAN links that have proper bandwidth.</span></span>
  
![클라우드 커넥터 용량](../../media/efb2269b-d44f-474e-aea8-c5158e729cfe.png)
  
> [!NOTE]
> <span data-ttu-id="4d0c1-162">취리히의 사용자가 시애틀 사무실로 출장하는 경우 내부 네트워크를 사용하여 유럽에서 이동하는 사용자와 게이트웨이 간의 미디어 트래픽을 전달하려는 경우(인터넷을 사용하는 것이 아니라) 유럽 SBC 또는 게이트웨이가 있는 암스테르담 사무실과 시애틀 사무실이 연결되어 있는지도 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-162">If a user from Zurich travels to the Seattle office, and you want to use the internal network to deliver media traffic between the traveling user and gateways in Europe (as opposed to going over the Internet), then you must make sure the Seattle office and the Amsterdam office where European SBCs or gateways are located qualify as well connected.</span></span> 
  
## <a name="codecs-used-in-media-bypass"></a><span data-ttu-id="4d0c1-163">미디어 우회에 사용되는 코덱</span><span class="sxs-lookup"><span data-stu-id="4d0c1-163">Codecs used in media bypass</span></span>

<span data-ttu-id="4d0c1-164">미디어 우회를 사용하도록 설정하면 클라이언트와 SBC 또는 게이트웨이 간의 미디어 트래픽이 G.711 코덱을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d0c1-164">With media bypass enabled, media traffic between a client and an SBC or gateway uses the G.711 codec.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4d0c1-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d0c1-165">See also</span></span>

[<span data-ttu-id="4d0c1-166">클라우드 커넥터 버전에서 미디어 우회 배포</span><span class="sxs-lookup"><span data-stu-id="4d0c1-166">Deploy media bypass in Cloud Connector Edition</span></span>](deploy-media-bypass-in-cloud-connector.md)