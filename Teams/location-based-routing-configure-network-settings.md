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
description: 직접 라우팅에 대한 Location-Based 네트워크 지역, 사이트 및 서브넷을 만들고 설정하는 방법을 배워야 합니다.
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
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="6e573-103">위치 기반 라우팅의 네트워크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="6e573-103">Configure network settings for Location-Based Routing</span></span>

<span data-ttu-id="6e573-104">아직 수행하지 않은 경우 직접 [](location-based-routing-plan.md) 라우팅에 대한 Location-Based 계획 및 라우팅을 참조하여 라우팅에 대한 네트워크 설정을 구성하기 전에 필요한 다른 단계를 Location-Based 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="6e573-105">이 문서에서는 라우팅에 대한 네트워크 설정을 구성하는 Location-Based 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="6e573-106">조직에서 전화 시스템 직접 라우팅을 배포한 후 다음 단계는 네트워크 지역, 네트워크 사이트 및 네트워크 서브넷을 만들고 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="6e573-107">네트워크 지역 정의</span><span class="sxs-lookup"><span data-stu-id="6e573-107">Define network regions</span></span>

<span data-ttu-id="6e573-108">네트워크 지역은 네트워크 사이트 모음을 포함하며 여러 지리적 영역에 걸쳐 네트워크의 다양한 부분을 상호 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="6e573-109">네트워크 지역을 구성하는 방법에 대한 단계는 Teams에서 클라우드 기능에 대한 네트워크 [토폴로지 관리로 이동하세요.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="6e573-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="6e573-110">네트워크 사이트 정의</span><span class="sxs-lookup"><span data-stu-id="6e573-110">Define network sites</span></span>

<span data-ttu-id="6e573-111">네트워크 사이트는 사무실, 건물 집합 또는 캠퍼스와 같은 물리적 장소가 있는 조직을 나타내는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="6e573-112">토폴로지의 각 네트워크 사이트를 네트워크 지역과 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="6e573-113">네트워크 사이트를 구성하는 방법에 대한 단계는 Teams에서 클라우드 기능에 대한 네트워크 [토폴로지 관리를 참조하세요.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="6e573-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="6e573-114">라우팅에 대한 Location-Based 방법은 고유한 PSTN 연결이 있는 각 위치에 대해 별도의 사이트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="6e573-115">Location-Based 라우팅에 사용할 수 있는 사이트 또는 Location-Based 사용할 수 없는 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="6e573-116">예를 들어 Location-Based 라우팅을 사용하도록 설정되지 않은 사이트를 만들어 Location-Based 라우팅을 사용하도록 설정된 사용자가 해당 사이트로 로밍할 때 PSTN 통화를 걸 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="6e573-117">네트워크 서브넷 정의</span><span class="sxs-lookup"><span data-stu-id="6e573-117">Define network subnets</span></span>

<span data-ttu-id="6e573-118">각 서브넷은 특정 네트워크 사이트와 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="6e573-119">여러 서브넷을 동일한 네트워크 사이트와 연결하지만 여러 사이트를 동일한 서브넷에 연결하지는 못합니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="6e573-120">네트워크 서브넷을 구성하는 방법에 대한 단계는 Teams에서 클라우드 기능에 대한 네트워크 [토폴로지 관리로 이동하세요.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="6e573-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="6e573-121">Location-Based 라우팅의 경우 Teams 엔드포인트가 네트워크에 연결할 수 있는 위치에 있는 IP 서브넷을 정의하고 정의된 네트워크에 연결하여 전화 우회를 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="6e573-122">이렇게 서브넷을 연결하면 라우팅이 Location-Based 엔드포인트를 지리적으로 찾아서 특정 PSTN 호출을 허용해야 하는지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="6e573-123">IPv6 및 IPv4 서브넷이 모두 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="6e573-124">Teams 엔드포인트가 사이트에 있는지 여부를 결정할 때 Location-Based 일치하는 IPv6 주소를 먼저 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="6e573-125">IPv6 주소가 없는 경우 Location-Based 라우팅에서 IPv4 주소를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="6e573-126">신뢰할 수 있는 IP 주소(외부 서브넷) 정의</span><span class="sxs-lookup"><span data-stu-id="6e573-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="6e573-127">신뢰할 수 있는 IP 주소는 엔터프라이즈 네트워크의 인터넷 외부 IP 주소로, 사용자의 엔드포인트가 회사 네트워크 내부에 있는지 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="6e573-128">신뢰할 수 있는 IP 주소를 구성하는 방법에 대한 단계는 Teams에서 클라우드 기능에 대한 네트워크 [토폴로지 관리로 이동하세요.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="6e573-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="6e573-129">사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 있는 IP 주소와 Location-Based 라우팅을 확인하여 사용자의 엔드포인트가 있는 내부 서브넷을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="6e573-130">사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 정의된 IP 주소와 일치하지 않는 경우 엔드포인트는 알 수 없는 위치에 있는 것으로 분류되고, Location-Based 라우팅을 사용하도록 설정된 사용자의 PSTN 호출은 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e573-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6e573-131">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6e573-131">Next steps</span></span>

<span data-ttu-id="6e573-132">직접 [라우팅에 Location-Based](location-based-routing-enable.md)라우팅 사용으로 이동</span><span class="sxs-lookup"><span data-stu-id="6e573-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6e573-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6e573-133">Related topics</span></span>

- [<span data-ttu-id="6e573-134">Teams의 클라우드 음성 기능에 대한 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="6e573-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
