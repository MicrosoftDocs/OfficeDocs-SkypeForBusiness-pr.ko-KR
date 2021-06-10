---
title: 네트워크 설정 구성 - 위치 기반 라우팅
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 직접 라우팅에 대한 Location-Based 네트워크 지역, 사이트 및 서브넷을 만들고 설정하는 방법을 알아보습니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7dd707a6066cfe9a8dfcbcc9b3ae36d450d1dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822948"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="92860-103">위치 기반 라우팅의 네트워크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="92860-103">Configure network settings for Location-Based Routing</span></span>

<span data-ttu-id="92860-104">아직 수행하지 않은 경우 직접 [](location-based-routing-plan.md) 라우팅에 대한 Location-Based 계획 및 라우팅을 참조하여 라우팅에 대한 네트워크 설정을 구성하기 전에 필요한 다른 단계를 Location-Based 합니다.</span><span class="sxs-lookup"><span data-stu-id="92860-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="92860-105">이 문서에서는 라우팅에 대한 네트워크 설정을 Location-Based 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="92860-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="92860-106">조직에서 전화 시스템 직접 라우팅을 배포한 후 다음 단계는 네트워크 지역, 네트워크 사이트 및 네트워크 서브넷을 만들고 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="92860-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="92860-107">네트워크 지역 정의</span><span class="sxs-lookup"><span data-stu-id="92860-107">Define network regions</span></span>

<span data-ttu-id="92860-108">네트워크 지역에는 네트워크 사이트 모음이 포함되어 있으며 여러 지리적 영역에 걸쳐 네트워크의 다양한 부분을 상호 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="92860-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="92860-109">네트워크 지역을 구성하는 방법에 대한 단계는 의 클라우드 [기능에 대한 네트워크 토폴로지 관리로 Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="92860-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="92860-110">네트워크 사이트 정의</span><span class="sxs-lookup"><span data-stu-id="92860-110">Define network sites</span></span>

<span data-ttu-id="92860-111">네트워크 사이트는 조직에 사무실, 건물 집합 또는 캠퍼스와 같은 물리적 장소가 있는 위치를 나타내고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92860-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="92860-112">토폴로지의 각 네트워크 사이트를 네트워크 지역과 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92860-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="92860-113">네트워크 사이트를 구성하는 방법에 대한 단계는 의 클라우드 기능에 대한 네트워크 [토폴로지 관리를 Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="92860-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="92860-114">라우팅을 Location-Based 위한 모범 사례는 고유한 PSTN 연결이 있는 각 위치에 대해 별도 사이트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="92860-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="92860-115">라우팅에 사용하도록 설정된 사이트 또는 Location-Based 라우팅에 사용할 수 없는 사이트를 Location-Based 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92860-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="92860-116">예를 들어 해당 사이트로 로밍할 때 Location-Based 라우팅을 사용하도록 설정된 사용자가 PSTN 호출을 Location-Based 수 있도록 할 수 있는 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92860-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="92860-117">네트워크 서브넷 정의</span><span class="sxs-lookup"><span data-stu-id="92860-117">Define network subnets</span></span>

<span data-ttu-id="92860-118">각 서브넷은 특정 네트워크 사이트와 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92860-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="92860-119">여러 서브넷을 동일한 네트워크 사이트와 연결할 수 있지만 여러 사이트를 동일한 서브넷과 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92860-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="92860-120">네트워크 서브넷을 구성하는 방법에 대한 단계는 의 클라우드 기능에 대한 네트워크 [토폴로지 관리로 Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="92860-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="92860-121">Location-Based 라우팅의 경우 Teams 엔드포인트가 네트워크에 연결할 수 있는 위치에 있는 IP 서브넷을 정의하고 정의된 네트워크에 연결하여 전화 우회를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92860-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="92860-122">이러한 서브넷 연결은 Location-Based 라우팅을 통해 지리적으로 엔드포인트를 찾을 수 있도록 하여 특정 PSTN 호출을 허용해야 하는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92860-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="92860-123">IPv6 및 IPv4 서브넷 모두 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="92860-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="92860-124">사이트에 Teams 엔드포인트가 있는지 여부를 결정할 때 라우팅 Location-Based 일치하는 IPv6 주소를 먼저 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="92860-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="92860-125">IPv6 주소가 없는 경우 Location-Based 라우팅에서 IPv4 주소를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="92860-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="92860-126">신뢰할 수 있는 IP 주소 정의(외부 서브넷)</span><span class="sxs-lookup"><span data-stu-id="92860-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="92860-127">신뢰할 수 있는 IP 주소는 엔터프라이즈 네트워크의 인터넷 외부 IP 주소로, 사용자의 엔드포인트가 회사 네트워크 내부에 있는지 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="92860-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="92860-128">신뢰할 수 있는 IP 주소를 구성하는 방법에 대한 단계는 의 클라우드 [기능에 대한 네트워크 토폴로지 관리로 Teams.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="92860-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="92860-129">사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 있는 IP 주소와 일치하는 Location-Based 라우팅을 검사하여 사용자의 엔드포인트가 있는 내부 서브넷을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92860-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="92860-130">사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 정의된 IP 주소와 일치하지 않는 경우 엔드포인트는 알 수 없는 위치에 있는 것으로 분류되고 라우팅을 사용하도록 설정된 사용자의 PSTN Location-Based 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="92860-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="92860-131">다음 단계</span><span class="sxs-lookup"><span data-stu-id="92860-131">Next steps</span></span>

<span data-ttu-id="92860-132">직접 [라우팅에 Location-Based 라우팅을 사용하도록 설정으로 이동합니다.](location-based-routing-enable.md)</span><span class="sxs-lookup"><span data-stu-id="92860-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="92860-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="92860-133">Related topics</span></span>

- [<span data-ttu-id="92860-134">클라우드 음성 기능에 대한 네트워크 Teams</span><span class="sxs-lookup"><span data-stu-id="92860-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
