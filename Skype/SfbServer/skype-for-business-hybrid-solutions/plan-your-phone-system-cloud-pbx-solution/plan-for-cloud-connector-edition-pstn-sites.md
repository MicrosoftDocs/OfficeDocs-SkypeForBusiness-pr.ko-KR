---
title: 클라우드 커넥터 버전 PSTN 사이트 계획
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: 효율적이고 비용 효과적인 통화 라우팅을 보장하기 위해 Cloud Connector Edition PSTN 사이트를 계획하는 방법을 알아보는 이 항목을 읽어 읽습니다.
ms.openlocfilehash: b42f9109a52b5c30996abc3e42ef4ff0aa5f31dc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096232"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a><span data-ttu-id="fc686-103">클라우드 커넥터 버전 PSTN 사이트 계획</span><span class="sxs-lookup"><span data-stu-id="fc686-103">Plan for Cloud Connector Edition PSTN sites</span></span>

> [!Important]
> <span data-ttu-id="fc686-104">Cloud Connector Edition은 비즈니스용 Skype Online과 함께 2021년 7월 31일부터 사용이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="fc686-105">조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="fc686-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="fc686-106">효율적이고 비용 효과적인 통화 라우팅을 보장하기 위해 Cloud Connector Edition PSTN 사이트를 계획하는 방법을 알아보는 이 항목을 읽어 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-106">Read this topic to learn how to plan your Cloud Connector Edition PSTN sites to ensure efficient and cost effective call routing.</span></span>
  
<span data-ttu-id="fc686-107">이 항목에서는 클라우드 커넥터 PSTN 사이트를 계획할 수 있도록 클라우드 커넥터 버전 및 통화 라우팅에 대해 알아야 할 항목에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-107">This topic describes what you need to know about Cloud Connector Edition and call routing so that you can plan your Cloud Connector PSTN sites.</span></span> <span data-ttu-id="fc686-108">PSTN 사이트는 동일한 위치에 배포되고 공통 PSTN 게이트웨이가 연결된 클라우드 커넥터 어플라이언스의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-108">A PSTN site is a combination of Cloud Connector appliances, deployed at the same location, and with common PSTN gateways connected to them.</span></span> <span data-ttu-id="fc686-109">이 항목에서는 클라우드 커넥터 사이트에서 가장 비용 효율적이고 효과적인 방법으로 사이트에 할당된 모든 사용자에 대한 인바운드 및 아웃바운드 라우팅을 모두 처리할 수 있도록 클라우드 커넥터 사이트 토폴로지 설정 방법에 대해 중점적으로 다루고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-109">This topic focuses on how to set up your Cloud Connector site topology to ensure that your Cloud Connector sites can handle both inbound and outbound routing for all users assigned to a site in the most cost efficient and effective way possible.</span></span> <span data-ttu-id="fc686-110">클라우드 커넥터 및 PSTN 사이트의 이점에 대한 자세한 내용은 [Plan for Skype for Business Cloud Connector Edition 을 읽어야 합니다.](plan-skype-for-business-cloud-connector-edition.md)</span><span class="sxs-lookup"><span data-stu-id="fc686-110">For more information about Cloud Connector and the benefits of PSTN sites, be sure to read [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a><span data-ttu-id="fc686-111">클라우드 커넥터 PSTN 사이트 및 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="fc686-111">Cloud Connector PSTN sites and call routing</span></span>

<span data-ttu-id="fc686-112">클라우드 커넥터 PSTN 사이트는 불필요한 시거리 및 국가 간 관세를 방지하고 아웃바운드 긴급 통화가 적절한 트렁크로 라우팅되도록 만들어진 토폴로지 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-112">Cloud Connector PSTN sites are a topology construct created to prevent unnecessary long distance and inter-country tariffs, and to ensure that outbound emergency calls are routed to the appropriate trunk.</span></span> <span data-ttu-id="fc686-113">긴급 서비스에 대한 통화를 포함하여 비용 효율적이고 효율적인 통화 라우팅을 보장하려면 PSTN 사이트와 각 사이트에 사용자를 할당하는 방법을 신중하게 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-113">To ensure cost effective and efficient routing of calls, including calls to emergency services, you must carefully plan your PSTN sites and how users are assigned to each site.</span></span> 
  
<span data-ttu-id="fc686-114">클라우드 커넥터 계획의 일부로, 통신 사업자에 사무실과 사용자가 있는 위치와 PSTN 트렁크가 이동 통신 사업자에서 종료되는 위치를 통신사에 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-114">As part of your planning for Cloud Connector, it is essential that you talk to your carriers about where your offices and users are located, and where the PSTN trunks terminate from the carrier.</span></span> <span data-ttu-id="fc686-115">통신사와 함께 응급 통화를 라우팅할 수 있는 방법을 결정한 다음 해당 정보를 사용하여 클라우드 커넥터 PSTN 사이트를 정의하고 사용자를 적절한 사이트에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-115">You need to work with your carriers to determine how emergency calls can be routed, and then use that information to define Cloud Connector PSTN sites and assign users to the appropriate sites.</span></span> <span data-ttu-id="fc686-116">예를 들어 PSTN 사이트가 확장되는 데이터 센터에서 종료되는 트렁크가 해당 사이트의 사용자에게 할당된 모든 번호에 대한 인바운드 라우팅과 아웃바운드 라우팅을 모두 처리하도록 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-116">For example, you should ensure that the trunks that terminate at a datacenter where the PSTN site is stretched are configured to handle both inbound and outbound routing for all of the numbers assigned to the users at that site.</span></span> 
  
<span data-ttu-id="fc686-117">각 클라우드 커넥터 어플라이언스를 여러 IP 게이트웨이, IP PBX 또는 SBC(Session Border Controller)에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-117">Each Cloud Connector appliance can be connected to several IP Gateways, IP PBXs, or Session Border Controllers (SBCs).</span></span> <span data-ttu-id="fc686-118">게이트웨이 및 PBX는 텔코 트렁크(PRI 또는 SIP 트렁크)에 연결되어 있기 때문에 클라우드 커넥터 어플라이언스는 인바운드 및 아웃바운드 통화를 위해 PSTN 트렁크에 논리적으로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-118">Because the Gateways and PBXs are connected to telco trunks (PRI or SIP trunks), Cloud Connector appliances are logically connected to PSTN trunks for inbound and outbound calls.</span></span> <span data-ttu-id="fc686-119">클라우드 커넥터 및 사내 PSTN 연결을 사용하면 로컬 통신 사업자로부터 트렁크 및 관련 전화 번호를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-119">With Cloud Connector and on-premises PSTN connectivity, you obtain the trunk and the associated phone numbers from your local carrier.</span></span> <span data-ttu-id="fc686-120">비즈니스가 대기업인 경우, 특히 비즈니스가 여러 도시, 시 또는 국가에 걸쳐 있는 경우 여러 통신 사업자일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-120">If your business is a large enterprise, you might have more than one carrier—especially if your business spans more than one city, state, or country.</span></span> <span data-ttu-id="fc686-121">통신 사업자에서 전화번호를 소유하고 있기 때문에 통신사는 긴급 통화를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-121">Because your carrier owns the phone number, the carrier is responsible for handling emergency calls.</span></span>
  
<span data-ttu-id="fc686-122">비즈니스용 Skype Online은 사이트의 모든 클라우드 커넥터 어플라이언스를 동일하게 처리하고 아웃바운드 통화를 동일한 사이트의 클라우드 커넥터 어플라이언스로 회전하여 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-122">Skype for Business Online treats all Cloud Connector appliances in a site equally, and will route outbound calls on a rotating basis to Cloud Connector appliances in the same site.</span></span> <span data-ttu-id="fc686-123">사이트의 각 클라우드 커넥터는 동일한 PSTN 트렁크 집합(완전히 메시)에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-123">Each Cloud Connector in a site is cross connected to the same set of PSTN trunks (fully meshed).</span></span> <span data-ttu-id="fc686-124">각 사용자는 클라우드 커넥터 PSTN 사이트에 연결되어 있기 때문에 해당 사용자의 모든 아웃바운드 통화(일반 또는 긴급)는 사용자가 연결된 PSTN 사이트의 클라우드 커넥터 어플라이언스 중 하나에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-124">Because each user is associated with a Cloud Connector PSTN site, any outbound call from that user (normal or emergency) will be assigned to one of the Cloud Connector appliances in the PSTN site that the user is associated with.</span></span> 
  
<span data-ttu-id="fc686-125">Cloud Connector는 연결된 IP 게이트웨이, IP-PBX, SBC 또는 직접 PSTN 트렁크로의 고정 통화 라우팅을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-125">Cloud Connector does static call routing to its attached IP Gateways, IP-PBXs, SBCs or direct PSTN trunks.</span></span> <span data-ttu-id="fc686-126">클라우드 커넥터는 아직 대상(최소 비용 라우팅) 또는 원점(정적 또는 동적 긴급 통화)을 기반으로 트렁크로 동적 라우팅을 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-126">Cloud Connector is not yet capable of dynamic routing to a trunk based on destination (for least cost routing) or based on origin (static or dynamic emergency calling).</span></span> <span data-ttu-id="fc686-127">인바운드 통화는 번호와 연결된 트렁크에서만 올 수 있는 것이기 때문에 문제가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-127">Inbound calls are not a problem since the call can only come from a trunk associated with the number.</span></span> <span data-ttu-id="fc686-128">그러나 아웃바운드 통화는 사이트의 모든 Cloud Connector 어플라이언스 및 확장에 따라 클라우드 커넥터 어플라이언스에 연결된 PSTN 트렁크로 이동하여 원치 않는 장거리 통화를 발생될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-128">Outbound calls, however, can go to any Cloud Connector appliance in a site (and by extension the PSTN trunks attached to that Cloud Connector appliance) which can cause unwanted long distance calls.</span></span> <span data-ttu-id="fc686-129">또한 클라우드 커넥터 PSTN 사이트가 지역 코드 또는 통신 사업자에 따라 데이터 센터 전체로 확장되는 경우 긴급 통화가 진행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-129">Furthermore, emergency calls will not go through if the Cloud Connector PSTN site is stretched across datacenters with different area codes or carriers.</span></span>
  
## <a name="an-example"></a><span data-ttu-id="fc686-130">예제</span><span class="sxs-lookup"><span data-stu-id="fc686-130">An example</span></span>

<span data-ttu-id="fc686-131">다음 예제에서는 트렁크를 PSTN 사이트로 그룹화하는 방법과 사이트에 사용자를 할당하는 방법을 보여 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-131">The following example shows how to group trunks to PSTN sites and how to assign users to the sites.</span></span> <span data-ttu-id="fc686-132">Contoso 회사의 경우 다음을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-132">For Contoso company, assume the following:</span></span>
  
- <span data-ttu-id="fc686-133">4개의 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-133">There are four users:</span></span> 
    
  - <span data-ttu-id="fc686-134">Redmond WA(미국)의 사용자 A</span><span class="sxs-lookup"><span data-stu-id="fc686-134">User A in Redmond WA (USA)</span></span>
    
  - <span data-ttu-id="fc686-135">Bellevue WA(미국)의 사용자 B</span><span class="sxs-lookup"><span data-stu-id="fc686-135">User B in Bellevue WA (USA)</span></span>
    
  - <span data-ttu-id="fc686-136">중앙아 WA(미국)의 사용자 C</span><span class="sxs-lookup"><span data-stu-id="fc686-136">User C in Centralia WA (USA)</span></span>
    
  - <span data-ttu-id="fc686-137">포틀랜드 OR(미국)의 사용자 D</span><span class="sxs-lookup"><span data-stu-id="fc686-137">User D in Portland OR (USA)</span></span>
    
- <span data-ttu-id="fc686-138">통신사 A는 다음에 전화 번호와 트렁크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-138">Carrier A provides phone numbers and trunks in:</span></span>
    
  - <span data-ttu-id="fc686-139">Redmond(지역 코드 425)</span><span class="sxs-lookup"><span data-stu-id="fc686-139">Redmond (area code 425)</span></span>
    
  - <span data-ttu-id="fc686-140">Bellevue(지역 코드 425)</span><span class="sxs-lookup"><span data-stu-id="fc686-140">Bellevue (area code 425)</span></span>
    
  - <span data-ttu-id="fc686-141">중앙아(지역 코드 360)</span><span class="sxs-lookup"><span data-stu-id="fc686-141">Centralia (area code 360)</span></span>
    
- <span data-ttu-id="fc686-142">통신사 B는 다음에 전화 번호와 트렁크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-142">Carrier B provides phone numbers and trunks in:</span></span>
    
  -  <span data-ttu-id="fc686-143">포틀랜드(지역 코드 503)</span><span class="sxs-lookup"><span data-stu-id="fc686-143">Portland (area code 503)</span></span>
    
<span data-ttu-id="fc686-144">Redmond의 사용자 A(데이터 센터 A)와 Bellevue의 사용자 B(데이터 센터 B)는 서로 옆에 있으며 동일한 지역 번호(425)에 있기 때문에 통신사 A는 Bellevue의 트렁크에 있는 Redmond의 사용자 A로부터 긴급 통화를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-144">Because user A in Redmond (Data Center A) and user B in Bellevue (Data Center B) are in suburbs next to each other and in the same area code (425), Carrier A should be able to take an Emergency Call from user A in Redmond on the trunk in Bellevue.</span></span> 
  
<span data-ttu-id="fc686-145">따라서 사용자 A와 B와 Bellevue 및 Redmond의 클라우드 커넥터 트렁크는 다음 다이어그램과 같이 동일한 클라우드 커넥터 PSTN 사이트에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-145">Consequently, users A and B, and the Cloud Connector trunks for Bellevue and Redmond, can likely be in the same Cloud Connector PSTN site as shown in the following diagram.</span></span> <span data-ttu-id="fc686-146">한 사무실에 있는 사용자의 긴급 통화를 다른 사무실의 트렁크로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-146">Emergency calls from users in one office can be routed to trunks in the other.</span></span> <span data-ttu-id="fc686-147">그러나 통신사에 확인하여 이 작업을 할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-147">You should, however, check with your carrier that this will work.</span></span>
  
![PSTN 사이트를 설정하는 방법](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
<span data-ttu-id="fc686-149">다음 예제도 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="fc686-149">Consider the following examples as well:</span></span>
  
- <span data-ttu-id="fc686-150">Centralia의 C 사용자 C는 2시간 거리에 있으며 Bellevue 및 Redmond 425 지역 코드의 다른 통신사 A 사용자와 다른 지역 코드(360)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-150">User C in Centralia, whose number is provided by Carrier A, is a two hour drive away, and in a different area code (360), from other Carrier A users in the Bellevue and Redmond 425 area code.</span></span> 
    
    <span data-ttu-id="fc686-151">따라서 통신사 A로부터 전화를 받는 경우에도 중앙 지역 코드 360의 통신 사업자 통화 라우팅 소프트웨어가 Bellevue 영역 코드 425의 사용자 B로부터 들어오는 긴급 통화를 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-151">Therefore, even if a call is coming from Carrier A, it is possible that the carrier's call routing software in Centralia area code 360 may reject an incoming emergency call originating from user B in Bellevue area code 425.</span></span> <span data-ttu-id="fc686-152">이 경우 통신 사업자는 중앙아 PSTN 사이트의 클라우드 커넥터 및 연결된 트렁크가 거리 및 지역 코드에서 통화를 처리할 수 있도록 하는지 확인하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-152">In this case it is critical that the carrier confirm that Cloud Connector and its associated trunks in the Centralia PSTN sites can handle calls across distances and area codes.</span></span>
    
- <span data-ttu-id="fc686-153">포틀랜드의 사용자 D는 통신사 B가 제공한 번호와 트렁크를 사용하며, 따라서 통신사 B가 통신사 A가 소유한 전화 번호에서 긴급 통화를 할 가능성은 매우 낮습니다. 따라서 포틀랜드의 사용자 D와 Cloud Connector 어플라이언스 및 연결된 트렁크는 다른 PSTN 사이트에 위치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc686-153">User D in Portland uses a number and trunk provided by Carrier B, so it is highly unlikely that Carrier B will take an emergency call from a phone number that is owned by Carrier A. So user D and the Cloud Connector appliance and associated trunks in Portland will have to be located in a different PSTN site.</span></span>
