---
title: 위치 기반 라우팅의 네트워크 설정 구성
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 직접 라우팅에 대 한 위치 기반 라우팅에 대 한 네트워크 지역, 사이트 및 서브넷을 만들고 설정 하는 방법에 대해 알아봅니다.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 18df741dad691ba24d6950f132086b1f49b40684
ms.sourcegitcommit: 021c86bf579e315f15815dcddf232a0c651cbf6b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615848"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="9a1fb-103">위치 기반 라우팅의 네트워크 설정 구성</span><span class="sxs-lookup"><span data-stu-id="9a1fb-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="9a1fb-104">아직 수행 하지 않은 경우 위치 기반 라우팅에 대 한 네트워크 설정을 구성 하기 전에 수행 해야 하는 다른 단계를 검토 하도록 [직접 라우팅 계획 위치 기반 라우팅을](location-based-routing-plan.md) 읽어 보세요.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="9a1fb-105">이 문서에서는 위치 기반 라우팅에 대 한 네트워크 설정을 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="9a1fb-106">조직에 직접 전화 시스템 라우팅을 배포한 후 다음 단계는 네트워크 지역, 네트워크 사이트 및 네트워크 서브넷을 만들고 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="9a1fb-107">네트워크 지역 정의</span><span class="sxs-lookup"><span data-stu-id="9a1fb-107">Define network regions</span></span>

<span data-ttu-id="9a1fb-108">네트워크 지역에는 네트워크 사이트 컬렉션이 포함 되며 여러 지리적 영역에 걸친 네트워크의 다양 한 부분을 상호 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="9a1fb-109">네트워크 지역을 구성 하는 방법에 대 한 단계는 [팀의 클라우드 기능에 대 한 네트워크 토폴로지 관리](manage-your-network-topology.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="9a1fb-110">네트워크 사이트 정의</span><span class="sxs-lookup"><span data-stu-id="9a1fb-110">Define network sites</span></span>

<span data-ttu-id="9a1fb-111">네트워크 사이트는 사무실, 건물 집합 또는 캠퍼스와 같이 조직이 실제 장소를 보유 하 고 있는 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="9a1fb-112">토폴로지의 각 네트워크 사이트를 네트워크 영역과 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="9a1fb-113">네트워크 사이트를 구성 하는 방법에 대 한 단계는 [팀에서 클라우드 기능에 대 한 네트워크 토폴로지 관리](manage-your-network-topology.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="9a1fb-114">위치 기반 라우팅에 대 한 모범 사례는 고유한 PSTN 연결이 있는 각 위치에 대해 별도의 사이트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="9a1fb-115">위치 기반 라우팅이나 위치 기반 라우팅에 사용할 수 없는 사이트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="9a1fb-116">예를 들어 위치 기반 라우팅에 대해 사용 하도록 설정 되지 않은 사이트를 만들어 해당 사이트로 로밍할 때 PSTN 통화를 할 수 있도록 위치 기반 회람을 사용 하도록 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="9a1fb-117">네트워크 서브넷 정의</span><span class="sxs-lookup"><span data-stu-id="9a1fb-117">Define network subnets</span></span>

<span data-ttu-id="9a1fb-118">각 서브넷은 특정 네트워크 사이트에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="9a1fb-119">여러 서브넷을 동일한 네트워크 사이트에 연결할 수 있지만 여러 사이트를 동일한 서브넷에 연결할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="9a1fb-120">네트워크 서브넷을 구성 하는 방법에 대 한 단계는 [팀의 클라우드 기능에 대 한 네트워크 토폴로지 관리](manage-your-network-topology.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="9a1fb-121">위치 기반 라우팅의 경우 팀 끝점이 네트워크에 연결 될 수 있는 위치에 있는 IP 서브넷을 정의 하 고 정의 된 네트워크에 연결 해야 수신자의 부담을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="9a1fb-122">서브넷 연결을 사용 하면 위치 기반 라우팅이 끝점을 찾아 지리적으로 지정 된 PSTN 통화를 허용 해야 하는지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="9a1fb-123">IPv6 및 IPv4 서브넷이 모두 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="9a1fb-124">팀 종단점이 사이트에 있는지 여부를 결정할 때 위치 기반 라우팅은 먼저 일치 하는 IPv6 주소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="9a1fb-125">IPv6 주소가 없으면 위치 기반 라우팅이 IPv4 주소를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="9a1fb-126">신뢰할 수 있는 IP 주소 정의 (외부 서브넷)</span><span class="sxs-lookup"><span data-stu-id="9a1fb-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="9a1fb-127">신뢰할 수 있는 IP 주소는 엔터프라이즈 네트워크의 인터넷 외부 IP 주소 이며 사용자의 끝점이 회사 네트워크 내에 있는지 여부를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="9a1fb-128">신뢰할 수 있는 IP 주소를 구성 하는 방법에 대 한 단계는 [팀의 클라우드 기능에 대 한 네트워크 토폴로지 관리](manage-your-network-topology.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="9a1fb-129">사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 있는 IP 주소와 일치 하는 경우 위치 기반 라우팅에서 사용자의 끝점이 있는 내부 서브넷을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-129">If the user’s external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user’s endpoint is located.</span></span> <span data-ttu-id="9a1fb-130">사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 정의 된 IP 주소와 일치 하지 않는 경우 끝점은 알 수 없는 위치에 있는 것으로 분류 되며 위치 기반 라우팅에 대해 사용 하도록 설정 된 사용자에 대 한 PSTN 호출이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-130">If the user’s external IP address doesn’t match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9a1fb-131">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9a1fb-131">Next steps</span></span>

<span data-ttu-id="9a1fb-132">[직접 라우팅에 대해 위치 기반 라우팅 사용](location-based-routing-enable.md)으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a1fb-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9a1fb-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="9a1fb-133">Related topics</span></span>

- [<span data-ttu-id="9a1fb-134">팀의 클라우드 음성 기능에 대 한 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="9a1fb-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
