---
title: 클라우드 음성 기능에 대한 네트워크 설정
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 직접 라우팅 및 향상 된 응급 서비스에 대 한 위치 기반 라우팅에 대해 구성 해야 하는 네트워크 설정에 대해 알아봅니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bc2694760e93579a78cb849cc054d70a65431724
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139067"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="8469e-103">Microsoft 팀의 클라우드 음성 기능에 대 한 네트워크 설정</span><span class="sxs-lookup"><span data-stu-id="8469e-103">Network settings for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="8469e-104">네트워크 지역, 네트워크 사이트, 네트워크 서브넷 및 신뢰할 수 있는 IP 주소에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-104">Learn about network regions, network sites, network subnets, and trusted IP addresses.</span></span> <span data-ttu-id="8469e-105">이 조항 및 개념은 직접 라우팅과 [동적인 비상 전화](configure-dynamic-emergency-calling.md) [를 위한 위치 기반 라우팅](location-based-routing-plan.md) 에 대 한 클라우드 음성 설명서 전체에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-105">These terms and concepts are used throughout our cloud voice documentation for [Location-Based Routing for Direct Routing](location-based-routing-plan.md) and [dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span> <span data-ttu-id="8469e-106">조직에 이러한 클라우드 기능을 배포 하는 경우 Microsoft 팀에서 이러한 기능을 사용할 수 있도록 네트워크 설정을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-106">If you're deploying these cloud features in your organization, you must configure network settings for use with these features in Microsoft Teams.</span></span>

<span data-ttu-id="8469e-107">이 문서에서는 위치 기반 라우팅과 동적 비상 전화에 공통적인 네트워크 설정에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-107">This article gives you an overview of the network settings that are common to Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="8469e-108">배포 하는 클라우드 음성 기능 및 기능에 따라 이러한 설정을 일부 또는 모두 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-108">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="8469e-109">이러한 설정을 구성 하는 방법에 대 한 단계는 [팀에서 클라우드 기능에 대 한 네트워크 토폴로지 관리](manage-your-network-topology.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8469e-109">For steps on how to configure these settings, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8469e-110">네트워크 설정에 대 한 기능별 요구 사항은 해당 기능에 대 한 구성 항목에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-110">Any feature-specific requirements for network settings are documented in the configuration topics for that feature.</span></span>

## <a name="network-region"></a><span data-ttu-id="8469e-111">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="8469e-111">Network region</span></span>

<span data-ttu-id="8469e-112">네트워크 지역에는 네트워크 사이트 컬렉션이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-112">A network region contains a collection of network sites.</span></span> <span data-ttu-id="8469e-113">여러 지리적 영역에 걸친 네트워크의 다양 한 부분을 상호 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-113">It interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="8469e-114">예를 들어 조직에 인도에 있는 사이트가 여러 개 있는 경우 "인도"를 네트워크 지역으로 지정 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-114">For example, if your organization has many sites located in India, you may choose to designate "India" as a network region.</span></span> <span data-ttu-id="8469e-115">각 네트워크 사이트는 네트워크 지역과 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-115">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="8469e-116">직접적인 라우팅과 향상 된 응급 서비스에 대 한 위치 기반 라우팅과 동일한 네트워크 지역을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-116">The same network regions are shared by Location-Based Routing for Direct Routing and enhanced emergency services.</span></span> <span data-ttu-id="8469e-117">이미 하나의 기능에 대 한 네트워크 지역을 만든 경우에는 다른 기능에 대 한 새 네트워크 지역을 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-117">If you already created network regions for one feature, you don't have to create new network regions for the other feature.</span></span>

## <a name="network-site"></a><span data-ttu-id="8469e-118">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="8469e-118">Network site</span></span>

<span data-ttu-id="8469e-119">네트워크 사이트는 사무실, 건물 집합 또는 캠퍼스와 같이 조직이 실제 장소를 보유 하 고 있는 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-119">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="8469e-120">네트워크 사이트는 IP 서브넷의 모음으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-120">Network sites are defined as a collection of IP subnets.</span></span> <span data-ttu-id="8469e-121">각 네트워크 사이트는 네트워크 지역과 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-121">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="8469e-122">또한 네트워크 사이트를 사용 하 여 비상 전화를 사용 하도록 설정 하 고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-122">You can also use network sites to enable and configure emergency calling.</span></span>

## <a name="network-subnet"></a><span data-ttu-id="8469e-123">네트워크 서브넷</span><span class="sxs-lookup"><span data-stu-id="8469e-123">Network subnet</span></span>

<span data-ttu-id="8469e-124">각 서브넷은 특정 네트워크 사이트에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-124">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="8469e-125">클라이언트의 위치는 네트워크 서브넷 및 연결 된 네트워크 사이트를 기준으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-125">A client's location is determined based on the network subnet and the associated network site.</span></span> <span data-ttu-id="8469e-126">여러 서브넷을 동일한 네트워크 사이트에 연결할 수 있지만 여러 사이트를 동일한 서브넷에 연결할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-126">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span>

<span data-ttu-id="8469e-127">서브넷 정보는 새 세션이 시작 될 때 끝점을 배치할 네트워크 사이트를 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-127">Subnet information is used to determine the network site on which an endpoint is located when a new session is initiated.</span></span> <span data-ttu-id="8469e-128">세션에서 각 파티의 위치를 알고 있는 경우 클라우드 음성 기능은 해당 정보를 적용 하 여 전화 설정 또는 라우팅 처리 방법을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-128">When the location of each party in a session is known, the cloud voice feature can apply that information to determine how to handle call setup or routing.</span></span>

<span data-ttu-id="8469e-129">각 네트워크 사이트에 대해 네트워크 관리자와 협력 하 여 각 네트워크 사이트에 할당 되는 IP 서브넷을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-129">For each network site, work with your network admin to determine which IP subnets are assigned to each network site.</span></span> <span data-ttu-id="8469e-130">예를 들어 북미 지역의 뉴욕 사이트에는 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24의 IP 서브넷이 할당 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-130">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span></span> <span data-ttu-id="8469e-131">일반적으로 디트로이트에서 작동 하는 사용자의 경우, 교육을 위해 뉴욕 사무실로 이동 하 고, 컴퓨터를 설정 하 여 네트워크에 연결 하면 컴퓨터는 뉴욕에 대해 할당 된 4 개의 범위 (예: 172.29.80.103) 중 하나에 IP 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-131">If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York, for example, 172.29.80.103.</span></span>

## <a name="trusted-ip-address"></a><span data-ttu-id="8469e-132">신뢰할 수 있는 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8469e-132">Trusted IP address</span></span>

<span data-ttu-id="8469e-133">신뢰할 수 있는 IP 주소는 엔터프라이즈 네트워크의 인터넷 외부 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-133">Trusted IP addresses are the internet external IP addresses of the enterprise network.</span></span> <span data-ttu-id="8469e-134">특정 사이트 일치를 확인 하기 전에 사용자의 끝점이 회사 네트워크 내에 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-134">They determine whether the user's endpoint is inside the corporate network before checking for a specific site match.</span></span>

<span data-ttu-id="8469e-135">사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 있는 IP 주소와 일치 하는 경우 클라우드 음성 기능은 사용자의 끝점이 있는 내부 서브넷을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-135">If the user's external IP address matches an IP address that's in the trusted IP address list, the cloud voice feature checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="8469e-136">IPv4 또는 IPv6 IP 주소에 대해 일치가 이루어질 수 있으며, 네트워크 설정으로 전송 되는 IP 패킷의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-136">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span> <span data-ttu-id="8469e-137">공용 IP 주소에 IPv4와 IPv6이 모두 있는 경우에는 둘 다 신뢰할 수 있는 IP 주소로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-137">(If a public IP address has both IPv4 and IPv6, you must add both as trusted IP addresses.)</span></span>

<span data-ttu-id="8469e-138">사용자의 외부 IP 주소가 신뢰할 수 있는 IP 주소 목록에 있는 IP 주소와 일치 하지 않는 경우 끝점은 알 수 없는 위치에 있는 것으로 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8469e-138">If the user's external IP address doesn't match an IP address that's in the trusted IP address list, the endpoint is classified as being at an unknown location.</span></span>
