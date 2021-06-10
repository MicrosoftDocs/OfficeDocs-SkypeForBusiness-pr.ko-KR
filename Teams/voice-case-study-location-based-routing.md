---
title: Teams Contoso 사례 연구
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams 기업에 대한 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786075"
---
# <a name="contoso-case-study-location-based-routing"></a><span data-ttu-id="e638f-103">Contoso 사례 연구: Location-Based 라우팅</span><span class="sxs-lookup"><span data-stu-id="e638f-103">Contoso case study: Location-Based Routing</span></span>

<span data-ttu-id="e638f-104">Location-Based LBR(라우팅)은 통화를 배치하거나 받을 때 사용자의 실제 위치와 정책에 따라 수신자 우회를 제한하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-104">Location-Based Routing (LBR) is a feature that restricts toll bypass based on policy and the user's physical location at the time of placing or receiving a call.</span></span>  

## <a name="overview"></a><span data-ttu-id="e638f-105">개요</span><span class="sxs-lookup"><span data-stu-id="e638f-105">Overview</span></span>

<span data-ttu-id="e638f-106">Contoso에는 장거리 통화 비용을 절감하기 위해 PSTN(공용 전환 전화 네트워크) 공급자를 우회하는 것이 불법인 두 개의 사무실이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-106">Contoso has two offices in a country where it is illegal to bypass the Public Switched Telephone Network (PSTN) provider to decrease long-distance calling costs.</span></span> <span data-ttu-id="e638f-107">본점은 본점 및 두 번째 사무실에서 사용하는 인터넷 연결이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-107">The main office has an Internet connection that is used by the main office and by the second office.</span></span> <span data-ttu-id="e638f-108">각 사무실에는 PSTN 캐리어에 연결된 자체 SBC(세션 테두리 컨트롤러)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-108">Each office has their own Session Border Controller (SBC) connected to a PSTN carrier.</span></span>  
 
<span data-ttu-id="e638f-109">이 나라에서 Contoso는 해당 배포에 대해 LBR을 비즈니스용 Skype했습니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-109">In this country, Contoso had LBR configured for their Skype for Business deployment.</span></span> <span data-ttu-id="e638f-110">에 대한 LBR을 구성하는 Teams 결정하기 위해 Contoso는 직접 라우팅에 Location-Based 계획 Location-Based [를 읽습니다.](location-based-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="e638f-110">To determine how to configure LBR for Teams, Contoso read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md).</span></span> <span data-ttu-id="e638f-111">Contoso는 호출을 Teams 비즈니스용 Skype 수 있는 경우, 수신할 수 있는 경우, PSTN 호출을 사용자로 전송할 수 있는 Teams 경우, 다른 사용자를 PSTN 호출로 Teams 수 있는 경우와 동일한 시나리오를 따르는 것으로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-111">Contoso determined that Teams and Skype for Business follow the same scenarios on when a call can be placed, when it can be received, when a PSTN call can be transferred to a Teams user, and when you can transfer another Teams user to the PSTN call.</span></span>  

<span data-ttu-id="e638f-112">비즈니스용 Skype, LBR은 PSTN 캐리어에 연결하는 SBC(세션 테두리 컨트롤러) SIP 트렁크로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-112">For Skype for Business, LBR was configured with the Session Border Controller (SBC) SIP Trunk connecting to the PSTN carrier.</span></span> <span data-ttu-id="e638f-113">이 SBC의 경우 Contoso는 인증된 [SBC](direct-routing-border-controllers.md) 목록을 검토하고 배포된 SBC가 직접 라우팅에 대해 인증되지만 Media Bypass에 대해 인증되지 않은 것으로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-113">For this SBC, Contoso reviewed the [list of certified SBCs](direct-routing-border-controllers.md) and determined that the SBC deployed is certified for Direct Routing but is not certified for Media Bypass.</span></span> <span data-ttu-id="e638f-114">LBR을 지원하려면 직접 라우팅을 SBC 현장에 구성해야 합니다. 로컬 인터넷을 시작해야 합니다. 미디어 우회를 위해 SBC를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-114">To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass.</span></span> <span data-ttu-id="e638f-115">이 정보를 바탕으로 Contoso는 다음을 결정했다.</span><span class="sxs-lookup"><span data-stu-id="e638f-115">Based on this information, Contoso decided the following:</span></span>

- <span data-ttu-id="e638f-116">기존 SBC가 Media bypass에 Teams 때까지 LBR의 사용이 지연됩니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-116">To delay the enablement of Teams LBR until the existing SBC is certified for Media Bypass.</span></span>   

- <span data-ttu-id="e638f-117">Contoso는 직접 경로에 기본 사이트 SBC를 사용하기로 Office 365.</span><span class="sxs-lookup"><span data-stu-id="e638f-117">Contoso decided to use the main site SBC for the Direct Route to Office 365.</span></span>  <span data-ttu-id="e638f-118">기본 사이트 SBC는 원격 사이트의 프록시 SBC입니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-118">The main site SBC will be the proxy SBC for the remote site.</span></span>  

- <span data-ttu-id="e638f-119">Contoso는 인도에 있는 타사 컨설턴트가 국가의 전화 통신 회사와의 LBR 구성 인증을 지원하기 위해 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-119">Contoso used a third-party consultant based in India to assist with certification of the LBR configuration with the telephony company in country.</span></span>  

- <span data-ttu-id="e638f-120">사무실 외부에서 PSTN 통화를 하는 사용자를 지원하기 위해 회사에서 발급한 휴대폰을 해당 직원에게 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-120">To support users working from outside of the office to place PSTN calls, the company issued mobile phone was provided to their employees.</span></span> 

<span data-ttu-id="e638f-121">다음 다이어그램은 라우팅이 필요한 전화 통신 규정이 있는 국가에 대한 배포 전후 Location-Based 보여 니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-121">The following diagrams show the before and after deployments for a country with telephony regulations that require Location-Based Routing:</span></span>

<span data-ttu-id="e638f-122">**원래 배포**</span><span class="sxs-lookup"><span data-stu-id="e638f-122">**Original deployment**</span></span>

![상태 이전을 보여주는 다이어그램](media/voice-case-study-5.png)

<span data-ttu-id="e638f-124">**직접 라우팅을 통해 배포**</span><span class="sxs-lookup"><span data-stu-id="e638f-124">**Deployment with Direct Routing**</span></span>

![상태 이전을 보여주는 다이어그램](media/voice-case-study-6.png)


## <a name="configuration"></a><span data-ttu-id="e638f-126">구성:</span><span class="sxs-lookup"><span data-stu-id="e638f-126">Configuration:</span></span> 

<span data-ttu-id="e638f-127">에서 네트워크 구성 요소를 Teams Contoso는 클라우드 음성 기능에 대한 네트워크 토폴로지 관리의 지침을 [따릅니다.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="e638f-127">To configure the network components in Teams, Contoso followed the instructions in [Manage your network topology for cloud voice features](manage-your-network-topology.md).</span></span> <span data-ttu-id="e638f-128">Contoso는 다음 단계를 완료하여 라우팅을 Location-Based 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-128">Contoso completed the below steps to configure Location-Based Routing:</span></span> 

- <span data-ttu-id="e638f-129">네트워크 지역 정의 - 하나의 네트워크 지역이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-129">Define Network regions -  One network region was defined.</span></span> 

- <span data-ttu-id="e638f-130">네트워크 사이트 정의 - 두 개의 네트워크 사이트가 정의되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-130">Define Network sites - Two network sites were defined.</span></span> <span data-ttu-id="e638f-131">지역의 각 사무실 위치에 대한 하나의 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-131">One site for each office location in the region.</span></span>

- <span data-ttu-id="e638f-132">네트워크 서브넷 정의 - 사무실 위치 내의 각 층에는 유선 및 무선 네트워크에 대한 자체 서브넷이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-132">Define Network subnets - Each floor within an office location has their own subnet for the wired and wireless network.</span></span> <span data-ttu-id="e638f-133">이 구성으로 인해 Contoso에 대한 서브넷이 20개나 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-133">This configuration resulted in 20 subnets for Contoso.</span></span> 

- <span data-ttu-id="e638f-134">신뢰할 수 있는 IP 주소 정의 - SBC의 외부 연결 IP 주소가 신뢰할 수 있는 IP 주소에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e638f-134">Define trusted IP addresses - The external facing IP addresses for the SBC were added to the trusted IP address.</span></span>  

