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
description: 이 항목을 읽으면 효율적인 통화 라우팅과 비용 효율적인 통신을 위해 클라우드 커넥터 에디션 PSTN 사이트를 계획 하는 방법을 알아보세요.
ms.openlocfilehash: 5f20a5cf7a3395d4695a0e38d21e595982dc6398
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812506"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a><span data-ttu-id="994e0-103">클라우드 커넥터 버전 PSTN 사이트 계획</span><span class="sxs-lookup"><span data-stu-id="994e0-103">Plan for Cloud Connector Edition PSTN sites</span></span>
 
<span data-ttu-id="994e0-104">이 항목을 읽으면 효율적인 통화 라우팅과 비용 효율적인 통신을 위해 클라우드 커넥터 에디션 PSTN 사이트를 계획 하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="994e0-104">Read this topic to learn how to plan your Cloud Connector Edition PSTN sites to ensure efficient and cost effective call routing.</span></span>
  
<span data-ttu-id="994e0-105">이 항목에서는 클라우드 커넥터의 PSTN 사이트를 계획할 수 있도록 클라우드 커넥터 에디션 및 통화 라우팅에 대해 알아야 할 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-105">This topic describes what you need to know about Cloud Connector Edition and call routing so that you can plan your Cloud Connector PSTN sites.</span></span> <span data-ttu-id="994e0-106">PSTN 사이트는 클라우드 커넥터 기기의 조합으로, 동일한 위치에 배포 되 고 공통 PSTN 게이트웨이와 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-106">A PSTN site is a combination of Cloud Connector appliances, deployed at the same location, and with common PSTN gateways connected to them.</span></span> <span data-ttu-id="994e0-107">이 항목에서는 클라우드 커넥터 사이트에서 가장 저렴 하 고 효과적인 방법으로 사이트에 할당 된 모든 사용자의 인바운드 및 아웃 바운드 라우팅 모두를 처리 하는 데 중점을 둘 수 있도록 클라우드 커넥터 사이트 토폴로지를 설정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-107">This topic focuses on how to set up your Cloud Connector site topology to ensure that your Cloud Connector sites can handle both inbound and outbound routing for all users assigned to a site in the most cost efficient and effective way possible.</span></span> <span data-ttu-id="994e0-108">클라우드 커넥터 및 PSTN 사이트의 이점에 대 한 자세한 내용은 비즈니스용 [Skype 클라우드 커넥터 에디션 요금제](plan-skype-for-business-cloud-connector-edition.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="994e0-108">For more information about Cloud Connector and the benefits of PSTN sites, be sure to read [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).</span></span> 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a><span data-ttu-id="994e0-109">클라우드 커넥터 PSTN 사이트 및 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="994e0-109">Cloud Connector PSTN sites and call routing</span></span>

<span data-ttu-id="994e0-110">클라우드 커넥터 PSTN 사이트는 불필요 한 시외 및 국내 국가 요금을 방지 하 고 아웃 바운드 긴급 통화가 적절 한 트렁크에 라우팅되도록 하기 위해 생성 되는 토폴로지 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-110">Cloud Connector PSTN sites are a topology construct created to prevent unnecessary long distance and inter-country tariffs, and to ensure that outbound emergency calls are routed to the appropriate trunk.</span></span> <span data-ttu-id="994e0-111">비상 서비스에 대 한 통화를 포함 하 여 비용 효율적이 고 효율적으로 통신 하려면 PSTN 사이트를 신중 하 게 계획 하 고 사용자가 각 사이트에 할당 되는 방법을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-111">To ensure cost effective and efficient routing of calls, including calls to emergency services, you must carefully plan your PSTN sites and how users are assigned to each site.</span></span> 
  
<span data-ttu-id="994e0-112">클라우드 커넥터 계획의 일부로, 사무실과 사용자가 어디에 있든, 그리고 PSTN trunks 통신 업체에서 종료 하는 위치에 대해 통신 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-112">As part of your planning for Cloud Connector, it is essential that you talk to your carriers about where your offices and users are located, and where the PSTN trunks terminate from the carrier.</span></span> <span data-ttu-id="994e0-113">해당 통신 업체와 협력 하 여 긴급 통화를 라우팅할 수 있는 방법을 결정 한 다음 해당 정보를 사용 하 여 클라우드 커넥터 PSTN 사이트를 정의 하 고 해당 사이트에 사용자를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-113">You need to work with your carriers to determine how emergency calls can be routed, and then use that information to define Cloud Connector PSTN sites and assign users to the appropriate sites.</span></span> <span data-ttu-id="994e0-114">예를 들어 PSTN 사이트가 늘어나는 데이터 센터에서 종료 하는 trunks 해당 사이트의 사용자에 게 할당 된 모든 번호에 대 한 인바운드 및 아웃 바운드 라우팅을 처리 하도록 구성 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-114">For example, you should ensure that the trunks that terminate at a datacenter where the PSTN site is stretched are configured to handle both inbound and outbound routing for all of the numbers assigned to the users at that site.</span></span> 
  
<span data-ttu-id="994e0-115">각 클라우드 커넥터 기기는 여러 IP 게이트웨이, IP Pbx 또는 SBCs (세션 경계 컨트롤러)에 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-115">Each Cloud Connector appliance can be connected to several IP Gateways, IP PBXs, or Session Border Controllers (SBCs).</span></span> <span data-ttu-id="994e0-116">게이트웨이와 Pbx가 telco trunks (PRI 또는 SIP trunks)에 연결 되어 있으므로, 클라우드 커넥터 기기는 인바운드 및 아웃 바운드 호출을 위해 PSTN trunks에 논리적으로 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-116">Because the Gateways and PBXs are connected to telco trunks (PRI or SIP trunks), Cloud Connector appliances are logically connected to PSTN trunks for inbound and outbound calls.</span></span> <span data-ttu-id="994e0-117">클라우드 커넥터 및 온-프레미스 PSTN 연결을 사용 하면 로컬 통신 회사에서 트렁크 및 관련 전화 번호를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-117">With Cloud Connector and on-premises PSTN connectivity, you obtain the trunk and the associated phone numbers from your local carrier.</span></span> <span data-ttu-id="994e0-118">비즈니스가 대기업 일 경우, 특히 두 개 이상의 도시, 주 또는 국가에 근무 하는 경우 둘 이상의 캐리어가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-118">If your business is a large enterprise, you might have more than one carrier—especially if your business spans more than one city, state, or country.</span></span> <span data-ttu-id="994e0-119">통신 회사는 전화 번호를 소유 하 고 있기 때문에 통신 회사는 비상 전화를 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-119">Because your carrier owns the phone number, the carrier is responsible for handling emergency calls.</span></span>
  
<span data-ttu-id="994e0-120">비즈니스용 Skype Online은 사이트의 모든 클라우드 커넥터 기기를 동등 하 게 처리 하 고, 동일한 사이트의 클라우드 커넥터 기기에 대 한 순환 기준으로 아웃 바운드 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-120">Skype for Business Online treats all Cloud Connector appliances in a site equally, and will route outbound calls on a rotating basis to Cloud Connector appliances in the same site.</span></span> <span data-ttu-id="994e0-121">사이트의 각 클라우드 커넥터는 동일한 PSTN trunks (완전히 메쉬) 집합에 교차 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-121">Each Cloud Connector in a site is cross connected to the same set of PSTN trunks (fully meshed).</span></span> <span data-ttu-id="994e0-122">각 사용자가 클라우드 커넥터 PSTN 사이트와 연결 되어 있으므로 해당 사용자 (정상 또는 긴급)의 모든 아웃 바운드 통화는 사용자가 연결 된 PSTN 사이트의 클라우드 커넥터 기기 중 하나에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-122">Because each user is associated with a Cloud Connector PSTN site, any outbound call from that user (normal or emergency) will be assigned to one of the Cloud Connector appliances in the PSTN site that the user is associated with.</span></span> 
  
<span data-ttu-id="994e0-123">클라우드 커넥터는 연결 된 IP 게이트웨이, IP-Pbx, SBCs 또는 직접 PSTN trunks로의 정적 통화 라우팅을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-123">Cloud Connector does static call routing to its attached IP Gateways, IP-PBXs, SBCs or direct PSTN trunks.</span></span> <span data-ttu-id="994e0-124">클라우드 커넥터는 대상 (최소 비용 라우팅) 또는 원본 기반 (정적 또는 동적 비상 전화)을 기준으로 트렁크에 대 한 동적 라우팅을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-124">Cloud Connector is not yet capable of dynamic routing to a trunk based on destination (for least cost routing) or based on origin (static or dynamic emergency calling).</span></span> <span data-ttu-id="994e0-125">전화는 번호와 관련 된 트렁크 에서만 사용할 수 있기 때문에 인바운드 호출은 문제가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-125">Inbound calls are not a problem since the call can only come from a trunk associated with the number.</span></span> <span data-ttu-id="994e0-126">그러나 아웃 바운드 통화는 사이트의 모든 클라우드 커넥터 기기 (및 해당 클라우드 커넥터 기기에 연결 된 PSTN trunks)로 이동할 수 있으며, 원치 않는 시외 통화를 유발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-126">Outbound calls, however, can go to any Cloud Connector appliance in a site (and by extension the PSTN trunks attached to that Cloud Connector appliance) which can cause unwanted long distance calls.</span></span> <span data-ttu-id="994e0-127">또한 지역 번호 또는 통신 회사를 사용 하 여 클라우드 커넥터 PSTN 사이트를 데이터 센터에서 확장 하는 경우에도 긴급 호출이 진행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-127">Furthermore, emergency calls will not go through if the Cloud Connector PSTN site is stretched across datacenters with different area codes or carriers.</span></span>
  
## <a name="an-example"></a><span data-ttu-id="994e0-128">예제</span><span class="sxs-lookup"><span data-stu-id="994e0-128">An example</span></span>

<span data-ttu-id="994e0-129">다음 예에서는 trunks을 PSTN 사이트에 그룹화 하는 방법과 사용자를 사이트에 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-129">The following example shows how to group trunks to PSTN sites and how to assign users to the sites.</span></span> <span data-ttu-id="994e0-130">Contoso 회사의 경우 다음을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-130">For Contoso company, assume the following:</span></span>
  
- <span data-ttu-id="994e0-131">네 명의 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-131">There are four users:</span></span> 
    
  - <span data-ttu-id="994e0-132">Redmond WA (미국)의 사용자 A</span><span class="sxs-lookup"><span data-stu-id="994e0-132">User A in Redmond WA (USA)</span></span>
    
  - <span data-ttu-id="994e0-133">사용자 B 수원 WA (미국)</span><span class="sxs-lookup"><span data-stu-id="994e0-133">User B in Bellevue WA (USA)</span></span>
    
  - <span data-ttu-id="994e0-134">Centralia WA (미국)의 사용자 C</span><span class="sxs-lookup"><span data-stu-id="994e0-134">User C in Centralia WA (USA)</span></span>
    
  - <span data-ttu-id="994e0-135">포틀랜드 또는 (미국)의 사용자 D</span><span class="sxs-lookup"><span data-stu-id="994e0-135">User D in Portland OR (USA)</span></span>
    
- <span data-ttu-id="994e0-136">통신 회사 A는 전화 번호와 trunks을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-136">Carrier A provides phone numbers and trunks in:</span></span>
    
  - <span data-ttu-id="994e0-137">Redmond (지역 번호 425)</span><span class="sxs-lookup"><span data-stu-id="994e0-137">Redmond (area code 425)</span></span>
    
  - <span data-ttu-id="994e0-138">수원 (지역 번호 425)</span><span class="sxs-lookup"><span data-stu-id="994e0-138">Bellevue (area code 425)</span></span>
    
  - <span data-ttu-id="994e0-139">Centralia (지역 번호 360)</span><span class="sxs-lookup"><span data-stu-id="994e0-139">Centralia (area code 360)</span></span>
    
- <span data-ttu-id="994e0-140">통신 회사 B는 전화 번호와 trunks을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-140">Carrier B provides phone numbers and trunks in:</span></span>
    
  -  <span data-ttu-id="994e0-141">포틀랜드 (지역 번호 503)</span><span class="sxs-lookup"><span data-stu-id="994e0-141">Portland (area code 503)</span></span>
    
<span data-ttu-id="994e0-142">Redmond (데이터 센터 A) 및 사용자 B 수원 (데이터 센터 B)의 사용자 A는 서로 인접 하 고 동일한 지역 번호 (425)에 있으므로, 반송파 A가 수원의 트렁크에서 Redmond의 사용자 A 로부터 비상 전화를 걸 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-142">Because user A in Redmond (Data Center A) and user B in Bellevue (Data Center B) are in suburbs next to each other and in the same area code (425), Carrier A should be able to take an Emergency Call from user A in Redmond on the trunk in Bellevue.</span></span> 
  
<span data-ttu-id="994e0-143">따라서 사용자 A 및 B와 수원 및 Redmond 용 클라우드 커넥터 trunks는 다음 다이어그램에 표시 된 것 처럼 동일한 클라우드 커넥터 PSTN 사이트에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-143">Consequently, users A and B, and the Cloud Connector trunks for Bellevue and Redmond, can likely be in the same Cloud Connector PSTN site as shown in the following diagram.</span></span> <span data-ttu-id="994e0-144">한 사무실의 사용자가 보낸 비상 전화는 다른 곳에서 trunks로 라우팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-144">Emergency calls from users in one office can be routed to trunks in the other.</span></span> <span data-ttu-id="994e0-145">그러나이 작업을 수행할 수 있는 통신 업체에 문의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-145">You should, however, check with your carrier that this will work.</span></span>
  
![PSTN 사이트를 설정 하는 방법](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
<span data-ttu-id="994e0-147">다음 예제도 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="994e0-147">Consider the following examples as well:</span></span>
  
- <span data-ttu-id="994e0-148">해당 번호를 반송파 A로 제공 하는 Centralia의 사용자 C는 2 시간 드라이브와 다른 통신 지역 번호 (360)에서 수원 및 Redmond 425 지역 코드의 사용자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-148">User C in Centralia, whose number is provided by Carrier A, is a two hour drive away, and in a different area code (360), from other Carrier A users in the Bellevue and Redmond 425 area code.</span></span> 
    
    <span data-ttu-id="994e0-149">따라서 통신 회사 A에서 전화를 거는 경우 Centralia 지역 번호 360의 통신 회사 전화 라우팅 소프트웨어가 수원 지역 번호 425의 사용자 B 로부터 들어오는 비상 전화를 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-149">Therefore, even if a call is coming from Carrier A, it is possible that the carrier's call routing software in Centralia area code 360 may reject an incoming emergency call originating from user B in Bellevue area code 425.</span></span> <span data-ttu-id="994e0-150">이 경우 반송파는 Centralia PSTN 사이트의 클라우드 커넥터 및 연결 된 trunks 거리 및 지역 코드를 통해 통화를 처리할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-150">In this case it is critical that the carrier confirm that Cloud Connector and its associated trunks in the Centralia PSTN sites can handle calls across distances and area codes.</span></span>
    
- <span data-ttu-id="994e0-151">포틀랜드의 사용자 D는 반송파 B에서 제공 하는 번호와 트렁크를 사용 하므로, 반송파 A가 소유한 전화 번호로 비상 전화를 받을 가능성이 높습니다. 따라서 포틀랜드의 사용자 D와 클라우드 커넥터 기기 및 연결 된 trunks는 다른 PSTN 사이트에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="994e0-151">User D in Portland uses a number and trunk provided by Carrier B, so it is highly unlikely that Carrier B will take an emergency call from a phone number that is owned by Carrier A. So user D and the Cloud Connector appliance and associated trunks in Portland will have to be located in a different PSTN site.</span></span>
    

