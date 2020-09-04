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
description: 효율적이 고 비용 효율적인 통화 라우팅을 위해 클라우드 커넥터 에디션 PSTN 사이트를 계획 하는 방법을 알아보려면이 항목을 읽어 보십시오.
ms.openlocfilehash: 3b4320e12a87c771e28fce445102327c7783a5d2
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358804"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a><span data-ttu-id="938b2-103">클라우드 커넥터 버전 PSTN 사이트 계획</span><span class="sxs-lookup"><span data-stu-id="938b2-103">Plan for Cloud Connector Edition PSTN sites</span></span>

> [!Important]
> <span data-ttu-id="938b2-104">클라우드 커넥터 버전은 비즈니스용 Skype Online과 함께 2021 년 7 월 31 일에 사용 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="938b2-105">조직이 팀으로 업그레이드 된 후에는 [직접 라우팅을](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)사용 하 여 팀에 온-프레미스 전화 통신 네트워크를 연결 하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="938b2-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="938b2-106">효율적이 고 비용 효율적인 통화 라우팅을 위해 클라우드 커넥터 에디션 PSTN 사이트를 계획 하는 방법을 알아보려면이 항목을 읽어 보십시오.</span><span class="sxs-lookup"><span data-stu-id="938b2-106">Read this topic to learn how to plan your Cloud Connector Edition PSTN sites to ensure efficient and cost effective call routing.</span></span>
  
<span data-ttu-id="938b2-107">이 항목에서는 클라우드 커넥터 PSTN 사이트를 계획할 수 있도록 클라우드 커넥터 에디션 및 통화 라우팅에 대해 알아야 할 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-107">This topic describes what you need to know about Cloud Connector Edition and call routing so that you can plan your Cloud Connector PSTN sites.</span></span> <span data-ttu-id="938b2-108">PSTN 사이트는 클라우드 커넥터 기기를 동일한 위치에 배포 되는 동시에 연결 된 일반적인 PSTN 게이트웨이와 조합 하 여 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-108">A PSTN site is a combination of Cloud Connector appliances, deployed at the same location, and with common PSTN gateways connected to them.</span></span> <span data-ttu-id="938b2-109">이 항목에서는 클라우드 커넥터 사이트에서 가장 비용 효율적이 고 효율적인 방법으로 사이트에 할당 된 모든 사용자에 대해 인바운드 및 아웃 바운드 라우팅을 모두 처리할 수 있도록 클라우드 커넥터 site topology를 설정 하는 방법에 대해 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-109">This topic focuses on how to set up your Cloud Connector site topology to ensure that your Cloud Connector sites can handle both inbound and outbound routing for all users assigned to a site in the most cost efficient and effective way possible.</span></span> <span data-ttu-id="938b2-110">클라우드 커넥터 및 PSTN 사이트의 장점에 대 한 자세한 내용은 [비즈니스용 Skype 클라우드 Connector Edition에 대 한 계획](plan-skype-for-business-cloud-connector-edition.md)을 읽어 보시기으 하세요.</span><span class="sxs-lookup"><span data-stu-id="938b2-110">For more information about Cloud Connector and the benefits of PSTN sites, be sure to read [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a><span data-ttu-id="938b2-111">클라우드 커넥터 PSTN 사이트 및 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="938b2-111">Cloud Connector PSTN sites and call routing</span></span>

<span data-ttu-id="938b2-112">클라우드 커넥터 PSTN 사이트는 불필요 한 시외 및 국내 tariffs를 방지 하 고, 아웃 바운드 긴급 전화가 적절 한 트렁크로 라우팅되도록 하기 위해 만들어지는 토폴로지 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-112">Cloud Connector PSTN sites are a topology construct created to prevent unnecessary long distance and inter-country tariffs, and to ensure that outbound emergency calls are routed to the appropriate trunk.</span></span> <span data-ttu-id="938b2-113">응급 서비스에 대 한 통화를 포함 하 여 비용 효율적이 고 효율적인 통화 라우팅을 보장 하기 위해 PSTN 사이트와 사용자가 각 사이트에 할당 되는 방식을 신중 하 게 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-113">To ensure cost effective and efficient routing of calls, including calls to emergency services, you must carefully plan your PSTN sites and how users are assigned to each site.</span></span> 
  
<span data-ttu-id="938b2-114">클라우드 커넥터 계획의 일부로, 사무실 및 사용자가 있는 위치 및 PSTN 트렁크가 통신 회사에서 종료 되는 위치에 대 한 정보를 매개체에 게 문의 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-114">As part of your planning for Cloud Connector, it is essential that you talk to your carriers about where your offices and users are located, and where the PSTN trunks terminate from the carrier.</span></span> <span data-ttu-id="938b2-115">전화 회의를 통해 긴급 통화를 라우팅할 방법을 결정 한 다음 해당 정보를 사용 하 여 클라우드 커넥터 PSTN 사이트를 정의 하 고 사용자를 해당 사이트에 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-115">You need to work with your carriers to determine how emergency calls can be routed, and then use that information to define Cloud Connector PSTN sites and assign users to the appropriate sites.</span></span> <span data-ttu-id="938b2-116">예를 들어 PSTN 사이트를 확장 하는 데이터 센터에서 종료 되는 트렁크는 해당 사이트의 사용자에 게 할당 된 모든 번호에 대 한 인바운드 및 아웃 바운드 라우팅을 모두 처리 하도록 구성 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-116">For example, you should ensure that the trunks that terminate at a datacenter where the PSTN site is stretched are configured to handle both inbound and outbound routing for all of the numbers assigned to the users at that site.</span></span> 
  
<span data-ttu-id="938b2-117">각 클라우드 커넥터 기기는 여러 IP 게이트웨이, IP Pbx 또는 sbc (Session Border Controller)에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-117">Each Cloud Connector appliance can be connected to several IP Gateways, IP PBXs, or Session Border Controllers (SBCs).</span></span> <span data-ttu-id="938b2-118">게이트웨이와 Pbx는 telco 트렁크 (PRI 또는 SIP 트렁크)에 연결 되므로, 클라우드 커넥터 기기는 인바운드 및 아웃 바운드 호출에 대 한 PSTN 트렁크에 논리적으로 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-118">Because the Gateways and PBXs are connected to telco trunks (PRI or SIP trunks), Cloud Connector appliances are logically connected to PSTN trunks for inbound and outbound calls.</span></span> <span data-ttu-id="938b2-119">클라우드 커넥터 및 온-프레미스 PSTN 연결을 사용 하 여 로컬 통신 회사에서 트렁크 및 관련 전화 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-119">With Cloud Connector and on-premises PSTN connectivity, you obtain the trunk and the associated phone numbers from your local carrier.</span></span> <span data-ttu-id="938b2-120">비즈니스가 대기업 일 경우, 특히 비즈니스가 도시, 주 또는 국가의 한 두 개 이상에 걸쳐 있는 경우 둘 이상의 캐리어가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-120">If your business is a large enterprise, you might have more than one carrier—especially if your business spans more than one city, state, or country.</span></span> <span data-ttu-id="938b2-121">해당 캐리어가 전화 번호를 소유 하기 때문에, 반송파는 긴급 통화 처리를 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-121">Because your carrier owns the phone number, the carrier is responsible for handling emergency calls.</span></span>
  
<span data-ttu-id="938b2-122">비즈니스용 Skype Online은 사이트의 모든 클라우드 커넥터 어플라이언스를 동일 하 게 취급 하며, 아웃 바운드 통화를 같은 사이트의 클라우드 커넥터 기기로 순환 방식으로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-122">Skype for Business Online treats all Cloud Connector appliances in a site equally, and will route outbound calls on a rotating basis to Cloud Connector appliances in the same site.</span></span> <span data-ttu-id="938b2-123">사이트의 각 클라우드 커넥터는 동일한 PSTN 트렁크 (완전히 연결 된) 집합에 교차 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-123">Each Cloud Connector in a site is cross connected to the same set of PSTN trunks (fully meshed).</span></span> <span data-ttu-id="938b2-124">각 사용자는 클라우드 커넥터 PSTN 사이트와 연결 되므로 해당 사용자 (정상 또는 긴급) 로부터의 모든 아웃 바운드 통화는 사용자와 연결 된 PSTN 사이트의 클라우드 커넥터 기기 중 하나에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-124">Because each user is associated with a Cloud Connector PSTN site, any outbound call from that user (normal or emergency) will be assigned to one of the Cloud Connector appliances in the PSTN site that the user is associated with.</span></span> 
  
<span data-ttu-id="938b2-125">클라우드 커넥터는 연결 된 IP 게이트웨이, IP-Pbx, 국내 또는 direct PSTN 트렁크에 대 한 정적 통화 라우팅을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-125">Cloud Connector does static call routing to its attached IP Gateways, IP-PBXs, SBCs or direct PSTN trunks.</span></span> <span data-ttu-id="938b2-126">클라우드 커넥터는 대상 (최소 비용 라우팅) 또는 원본 기반 (정적 또는 동적 통화 호출)을 기반으로 하는 트렁크에 동적 라우팅을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-126">Cloud Connector is not yet capable of dynamic routing to a trunk based on destination (for least cost routing) or based on origin (static or dynamic emergency calling).</span></span> <span data-ttu-id="938b2-127">전화를 번호와 연결 된 트렁크 에서만 가져올 수 있으므로 인바운드 호출은 문제가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-127">Inbound calls are not a problem since the call can only come from a trunk associated with the number.</span></span> <span data-ttu-id="938b2-128">그러나 아웃 바운드 통화는 사이트의 모든 클라우드 커넥터 기기로 이동 하거나 내선 번호 트렁크이 클라우드 커넥터 기기에 연결 된 PSTN을 통해 시외 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-128">Outbound calls, however, can go to any Cloud Connector appliance in a site (and by extension the PSTN trunks attached to that Cloud Connector appliance) which can cause unwanted long distance calls.</span></span> <span data-ttu-id="938b2-129">또한 지역 코드나 캐리어가 서로 다른 데이터 센터에서 클라우드 커넥터 PSTN 사이트를 확장 하는 경우에도 비상 통화가 진행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-129">Furthermore, emergency calls will not go through if the Cloud Connector PSTN site is stretched across datacenters with different area codes or carriers.</span></span>
  
## <a name="an-example"></a><span data-ttu-id="938b2-130">예제</span><span class="sxs-lookup"><span data-stu-id="938b2-130">An example</span></span>

<span data-ttu-id="938b2-131">다음 예에서는 트렁크를 PSTN 사이트로 그룹화 하는 방법과 사이트에 사용자를 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-131">The following example shows how to group trunks to PSTN sites and how to assign users to the sites.</span></span> <span data-ttu-id="938b2-132">Contoso 회사의 경우 다음을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-132">For Contoso company, assume the following:</span></span>
  
- <span data-ttu-id="938b2-133">다음과 같은 네 명의 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-133">There are four users:</span></span> 
    
  - <span data-ttu-id="938b2-134">Redmond WA의 사용자 A (미국)</span><span class="sxs-lookup"><span data-stu-id="938b2-134">User A in Redmond WA (USA)</span></span>
    
  - <span data-ttu-id="938b2-135">Bellevue WA의 사용자 B (미국)</span><span class="sxs-lookup"><span data-stu-id="938b2-135">User B in Bellevue WA (USA)</span></span>
    
  - <span data-ttu-id="938b2-136">Centralia WA의 사용자 C (미국)</span><span class="sxs-lookup"><span data-stu-id="938b2-136">User C in Centralia WA (USA)</span></span>
    
  - <span data-ttu-id="938b2-137">포틀랜드 또는 미국 내 사용자 D</span><span class="sxs-lookup"><span data-stu-id="938b2-137">User D in Portland OR (USA)</span></span>
    
- <span data-ttu-id="938b2-138">캐리어 A는 전화 번호와 트렁크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-138">Carrier A provides phone numbers and trunks in:</span></span>
    
  - <span data-ttu-id="938b2-139">Redmond (지역 번호 425)</span><span class="sxs-lookup"><span data-stu-id="938b2-139">Redmond (area code 425)</span></span>
    
  - <span data-ttu-id="938b2-140">Bellevue (지역 번호 425)</span><span class="sxs-lookup"><span data-stu-id="938b2-140">Bellevue (area code 425)</span></span>
    
  - <span data-ttu-id="938b2-141">Centralia (지역 번호 360)</span><span class="sxs-lookup"><span data-stu-id="938b2-141">Centralia (area code 360)</span></span>
    
- <span data-ttu-id="938b2-142">반송파 B는 다음 위치에 전화 번호와 트렁크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-142">Carrier B provides phone numbers and trunks in:</span></span>
    
  -  <span data-ttu-id="938b2-143">포틀랜드 (지역 번호 503)</span><span class="sxs-lookup"><span data-stu-id="938b2-143">Portland (area code 503)</span></span>
    
<span data-ttu-id="938b2-144">Redmond의 사용자 A (Data Center A) 및 Bellevue (Data Center B)의 user B는 서로의 옆에 있고 같은 지역 번호 (425)에 있으므로 통신 회사 A는 Bellevue의 트렁크에 있는 Redmond의 사용자 A 로부터 비상 전화를 걸 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-144">Because user A in Redmond (Data Center A) and user B in Bellevue (Data Center B) are in suburbs next to each other and in the same area code (425), Carrier A should be able to take an Emergency Call from user A in Redmond on the trunk in Bellevue.</span></span> 
  
<span data-ttu-id="938b2-145">따라서 사용자 A와 B 및 Bellevue 및 Redmond의 클라우드 커넥터 트렁크는 다음 다이어그램에 나와 있는 것과 같은 클라우드 커넥터 PSTN 사이트에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-145">Consequently, users A and B, and the Cloud Connector trunks for Bellevue and Redmond, can likely be in the same Cloud Connector PSTN site as shown in the following diagram.</span></span> <span data-ttu-id="938b2-146">한 사무실에 있는 사용자의 비상 전화를 다른 회사의 트렁크으로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-146">Emergency calls from users in one office can be routed to trunks in the other.</span></span> <span data-ttu-id="938b2-147">하지만이 작업을 수행할 수 있는 통신 회사를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-147">You should, however, check with your carrier that this will work.</span></span>
  
![PSTN 사이트를 설정 하는 방법](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
<span data-ttu-id="938b2-149">다음과 같은 예도 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-149">Consider the following examples as well:</span></span>
  
- <span data-ttu-id="938b2-150">전화 통신 회사 A에서 번호를 제공 하는 Centralia의 사용자 C는 2 시간 후, 다른 지역 번호 (360), Bellevue 및 Redmond 425 지역 코드의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-150">User C in Centralia, whose number is provided by Carrier A, is a two hour drive away, and in a different area code (360), from other Carrier A users in the Bellevue and Redmond 425 area code.</span></span> 
    
    <span data-ttu-id="938b2-151">따라서 통신 회사 A에서 전화를 받는 경우에도 Centralia 지역 코드 360의 반송파 통화 라우팅 소프트웨어가 Bellevue 지역 425 번호의 사용자 B 로부터 들어오는 긴급 통화를 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-151">Therefore, even if a call is coming from Carrier A, it is possible that the carrier's call routing software in Centralia area code 360 may reject an incoming emergency call originating from user B in Bellevue area code 425.</span></span> <span data-ttu-id="938b2-152">이 경우에는 반송파가 Centralia PSTN 사이트에서 클라우드 커넥터 및 연결 된 트렁크가 거리와 지역 코드를 통해 호출을 처리할 수 있는지 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-152">In this case it is critical that the carrier confirm that Cloud Connector and its associated trunks in the Centralia PSTN sites can handle calls across distances and area codes.</span></span>
    
- <span data-ttu-id="938b2-153">포틀랜드의 사용자 D는 캐리어 B에서 제공 하는 수 및 트렁크를 사용 하므로, 반송파 A가 소유한 전화 번호 로부터 긴급 통화를 받을 가능성이 적습니다. 따라서 포틀랜드의 사용자 D와 클라우드 커넥터 기기와 연결 된 트렁크는 서로 다른 PSTN 사이트에 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="938b2-153">User D in Portland uses a number and trunk provided by Carrier B, so it is highly unlikely that Carrier B will take an emergency call from a phone number that is owned by Carrier A. So user D and the Cloud Connector appliance and associated trunks in Portland will have to be located in a different PSTN site.</span></span>
    

