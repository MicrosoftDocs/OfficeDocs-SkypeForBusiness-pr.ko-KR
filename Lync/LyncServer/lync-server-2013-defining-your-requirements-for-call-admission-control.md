---
title: 'Lync Server 2013: 통화 허용 제어 서비스에 대한 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7737d303c7239df451c71b4f92d4dcd8dfe5b2e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="7b0cb-102">Lync Server 2013에서 통화 허용 제어 서비스에 대한 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="7b0cb-102">Defining your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b0cb-103">_**마지막으로 수정한 주제:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="7b0cb-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="7b0cb-104">CAC (통화 허용 제어)에 대 한 계획에는 엔터프라이즈 네트워크 토폴로지에 대 한 자세한 정보가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-104">Planning for call admission control (CAC) requires detailed information about your enterprise network topology.</span></span> <span data-ttu-id="7b0cb-105">통화 허용 제어 정책을 계획 하는 데 도움이 필요 하면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-105">To help plan your call admission control policies, follow these steps.</span></span>

1.  <span data-ttu-id="7b0cb-106">엔터프라이즈 네트워크 내에서 허브/백본 ( *네트워크 지역*이라고 함)를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-106">Identify the hubs/backbones (called *network regions*) within your enterprise network.</span></span>

2.  <span data-ttu-id="7b0cb-107">각 네트워크 지역 내의 사무실 또는 위치 ( *네트워크 사이트*라고 함)를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-107">Identify the offices or locations (called *network sites*) within each network region.</span></span>

3.  <span data-ttu-id="7b0cb-108">네트워크 지역 모든 쌍 간의 네트워크 경로를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-108">Determine the network route between every pair of network regions.</span></span>

4.  <span data-ttu-id="7b0cb-109">각 WAN 링크의 대역폭 제한을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-109">Determine the bandwidth limits for each WAN link.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7b0cb-110">대역폭 제한은 WAN 링크에서 엔터프라이즈 음성 및 오디오/비디오 트래픽에 할당 되는 대역폭의 양을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-110">Bandwidth limits refer to how much of the bandwidth on a WAN link is allocated to Enterprise Voice and audio/video traffic.</span></span> <span data-ttu-id="7b0cb-111">WAN 링크를 "대역폭 제한"으로 설명 하는 경우 WAN 링크에는 링크를 통해 예상 되는 최고 소통량 보다 낮은 대역폭 한도가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-111">When a WAN link is described as “bandwidth-constrained,” the WAN link has a bandwidth limit that is lower than the expected peak traffic over the link.</span></span>

    
    </div>

5.  <span data-ttu-id="7b0cb-112">각 네트워크 사이트에 할당 된 IP 서브넷을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-112">Identify the IP subnets that are assigned to each network site.</span></span>

<span data-ttu-id="7b0cb-113">이러한 개념을 설명 하기 위해 다음 그림에 표시 된 네트워크 토폴로지 예를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-113">To explain these concepts, we’ll use the example network topology shown in the following figure.</span></span>

<span data-ttu-id="7b0cb-114">**통화 허용 제어에 대 한 예제 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="7b0cb-114">**Example topology for call admission control**</span></span>

<span data-ttu-id="7b0cb-115">![Litware inc. 네트워크 토폴로지 예](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. 네트워크 토폴로지 예")</span><span class="sxs-lookup"><span data-stu-id="7b0cb-115">![Litware Inc. Network Topology Example](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. Network Topology Example")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7b0cb-116">모든 네트워크 사이트는 네트워크 지역과 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-116">All network sites are associated with a network region.</span></span> <span data-ttu-id="7b0cb-117">예를 들어 포틀랜드, Reno, Albuquerque는 북미 지역에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-117">For example, Portland, Reno, and Albuquerque are included in the North America region.</span></span> <span data-ttu-id="7b0cb-118">이 그림에서는 대역폭 제한을 사용 하 여 CAC 정책이 적용 된 WAN 링크만 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-118">In this figure, only WAN links that have CAC policies applied are shown, with bandwidth limits.</span></span> <span data-ttu-id="7b0cb-119">시카고, 뉴욕 및 디트로이트의 네트워크 사이트는 대역폭이 제한 되지 않으므로 북미 지역 타원형 내에 표시 되므로 CAC 정책은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-119">The network sites of Chicago, New York, and Detroit are shown inside the North America region oval because they are not bandwidth-constrained, and therefore do not require CAC policies.</span></span>



</div>

<span data-ttu-id="7b0cb-120">이 예제 토폴로지의 구성 요소에 대해서는 다음 섹션에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-120">The components of this example topology are explained in the following sections.</span></span> <span data-ttu-id="7b0cb-121">대역폭 제한을 포함 하 여이 토폴로지가 계획 되는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 통화 허용 제어에 대 한 요구 사항 수집 예제](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-121">For details about how this topology was planned, including the bandwidth limits, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span></span>

<div>

## <a name="identify-network-regions"></a><span data-ttu-id="7b0cb-122">네트워크 지역 확인</span><span class="sxs-lookup"><span data-stu-id="7b0cb-122">Identify Network Regions</span></span>

<span data-ttu-id="7b0cb-123">네트워크 영역은 네트워크 백본 또는 네트워크 허브를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-123">A network region represents a network backbone or a network hub.</span></span>

<span data-ttu-id="7b0cb-124">네트워크 백본 또는 허브는 네트워크의 여러 부분을 상호 교환 하는 컴퓨터 네트워크 인프라의 일부 이며, 다양 한 Lan 또는 서브넷 간의 정보 교환을 위한 경로를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-124">A network backbone or hub is a part of computer network infrastructure that interconnects different parts of the network, providing a path for the exchange of information between different LANs or subnets.</span></span> <span data-ttu-id="7b0cb-125">백본은 다양 한 네트워크를 소규모 위치에서 넓은 지역으로 묶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-125">A backbone can tie together diverse networks from a small location to a wide geographic area.</span></span> <span data-ttu-id="7b0cb-126">일반적으로 백본 용량은 연결 하는 네트워크 보다 더 큽니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-126">The backbone's capacity is typically greater than that of the networks that connect to it.</span></span>

<span data-ttu-id="7b0cb-127">이 예제 토폴로지에는 북미, EMEA, APAC의 세 가지 네트워크 지역이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-127">Our example topology has three network regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="7b0cb-128">네트워크 지역에는 네트워크 사이트의 컬렉션이 포함 됩니다 (이 항목의 뒷부분에 나오는 네트워크 사이트의 정의 참조).</span><span class="sxs-lookup"><span data-stu-id="7b0cb-128">A network region contains a collection of network sites (see the definition of network sites later in this topic).</span></span> <span data-ttu-id="7b0cb-129">네트워크 운영 팀과 협력 하 여 네트워크 지역을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-129">Work with your network operations team to identify your network regions.</span></span>

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a><span data-ttu-id="7b0cb-130">각 네트워크 영역에 중앙 사이트 연결</span><span class="sxs-lookup"><span data-stu-id="7b0cb-130">Associating a Central Site with each Network Region</span></span>

<span data-ttu-id="7b0cb-131">CAC에서는 각 네트워크 지역에 대해 Lync Server 중앙 사이트가 정의 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-131">CAC requires that a Lync Server central site is defined for each network region.</span></span> <span data-ttu-id="7b0cb-132">중앙 사이트는 최상의 네트워크 연결을 선택 하 고 해당 네트워크 지역 내의 다른 모든 사이트에 가장 높은 대역폭을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-132">The central site is selected with the best network connectivity and highest bandwidth to all the other sites within that network region.</span></span> <span data-ttu-id="7b0cb-133">앞의 네트워크 토폴로지에 대 한 예는 각각 CAC 결정을 관리 하는 중앙 사이트를 포함 하는 세 개의 네트워크 지역을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-133">The preceding example of network topology shows three network regions, each with a central site that manages CAC decisions.</span></span> <span data-ttu-id="7b0cb-134">앞의 예제에서 적절 한 연관은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-134">From the preceding example, the appropriate association is shown in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7b0cb-135">중앙 사이트는 네트워크 사이트에 해당 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-135">Central sites do not necessarily correspond to network sites.</span></span> <span data-ttu-id="7b0cb-136">이 설명서의 예제에서 일부 중앙 사이트 (시카고, 런던, 베이징)는 네트워크 사이트와 같은 이름을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-136">In the examples in this documentation, some central sites—Chicago, London, and Beijing—share the same name as the network sites.</span></span> <span data-ttu-id="7b0cb-137">그러나 중앙 사이트와 네트워크 사이트에서 동일한 이름을 공유 하는 경우에도 중앙 사이트는 Lync Server 토폴로지의 요소 이지만, 네트워크 사이트는 Lync Server 토폴로지가 있는 전체 네트워크의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-137">However, even if a central site and network site share the same name, the central site is an element of the Lync Server topology, whereas the network site is a part of the overall network in which the Lync Server topology resides.</span></span>



</div>

### <a name="network-regions-central-sites-and-network-sites"></a><span data-ttu-id="7b0cb-138">네트워크 지역, 중앙 사이트, 네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="7b0cb-138">Network regions, central sites, and network sites</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b0cb-139">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="7b0cb-139">Network Region</span></span></th>
<th><span data-ttu-id="7b0cb-140">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="7b0cb-140">Central Site</span></span></th>
<th><span data-ttu-id="7b0cb-141">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="7b0cb-141">Network Sites</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b0cb-142">북미</span><span class="sxs-lookup"><span data-stu-id="7b0cb-142">North America</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-143">시카고</span><span class="sxs-lookup"><span data-stu-id="7b0cb-143">Chicago</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-144">시카고</span><span class="sxs-lookup"><span data-stu-id="7b0cb-144">Chicago</span></span></p>
<p><span data-ttu-id="7b0cb-145">뉴욕</span><span class="sxs-lookup"><span data-stu-id="7b0cb-145">New York</span></span></p>
<p><span data-ttu-id="7b0cb-146">디트로이트</span><span class="sxs-lookup"><span data-stu-id="7b0cb-146">Detroit</span></span></p>
<p><span data-ttu-id="7b0cb-147">지사</span><span class="sxs-lookup"><span data-stu-id="7b0cb-147">Portland</span></span></p>
<p><span data-ttu-id="7b0cb-148">Reno</span><span class="sxs-lookup"><span data-stu-id="7b0cb-148">Reno</span></span></p>
<p><span data-ttu-id="7b0cb-149">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="7b0cb-149">Albuquerque</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b0cb-150">슈팅</span><span class="sxs-lookup"><span data-stu-id="7b0cb-150">EMEA</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-151">시흥시</span><span class="sxs-lookup"><span data-stu-id="7b0cb-151">London</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-152">시흥시</span><span class="sxs-lookup"><span data-stu-id="7b0cb-152">London</span></span></p>
<p><span data-ttu-id="7b0cb-153">Cologne</span><span class="sxs-lookup"><span data-stu-id="7b0cb-153">Cologne</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b0cb-154">APAC</span><span class="sxs-lookup"><span data-stu-id="7b0cb-154">APAC</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-155">베이징</span><span class="sxs-lookup"><span data-stu-id="7b0cb-155">Beijing</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-156">베이징</span><span class="sxs-lookup"><span data-stu-id="7b0cb-156">Beijing</span></span></p>
<p><span data-ttu-id="7b0cb-157">마닐라</span><span class="sxs-lookup"><span data-stu-id="7b0cb-157">Manila</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a><span data-ttu-id="7b0cb-158">네트워크 사이트 확인</span><span class="sxs-lookup"><span data-stu-id="7b0cb-158">Identify Network Sites</span></span>

<span data-ttu-id="7b0cb-159">네트워크 사이트는 조직에 실제 장소 (예: 사무실, 건물 집합 또는 캠퍼스)가 있는 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-159">A network site represents a location where your organization has a physical venue—for example, offices, a set of buildings, or a campus.</span></span> <span data-ttu-id="7b0cb-160">LAN을 사용 하는 물리적인 장소 이며 다른 사이트에 대 한 WAN 연결이 네트워크 사이트로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-160">A physical venue with a LAN and has WAN connectivity to other sites is considered a network site.</span></span> <span data-ttu-id="7b0cb-161">먼저 모든 조직의 사무실을 인벤토리 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-161">Start by inventorying all of your organization’s offices.</span></span> <span data-ttu-id="7b0cb-162">이 예제 토폴로지에서 북미 네트워크 지역은 뉴욕, 시카고, 디트로이트, 포틀랜드, Reno, Albuquerque 네트워크 사이트로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-162">In our example topology, the North America network region consists of the following network sites: New York, Chicago, Detroit, Portland, Reno, and Albuquerque.</span></span>

<span data-ttu-id="7b0cb-163">모든 네트워크 사이트를 네트워크 지역에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-163">You must associate every network site with a network region.</span></span> <span data-ttu-id="7b0cb-164">네트워크 사이트에 제한 된 WAN 링크가 있는지 여부에 따라 대역폭 정책이 네트워크 사이트와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-164">Depending on whether the network site has a constrained WAN link, a bandwidth policy is associated with the network site.</span></span> <span data-ttu-id="7b0cb-165">CAC 정책 및이를 사용 하 여 할당 하는 대역폭에 대 한 자세한 내용은이 항목의 뒷부분에 나오는 "대역폭 정책 정의"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-165">For details about CAC policies and the bandwidth that you allocate by using them, see "Define Bandwidth Policies" later in this topic.</span></span> <span data-ttu-id="7b0cb-166">CAC를 구성 하려면 네트워크 사이트를 네트워크 영역과 연결 하 고, 해당 사이트 또는 지역과 사이트와 지역 간의 WAN 연결 간에 대역폭 제한 된 연결에 적용 되도록 대역폭 할당 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-166">To configure CAC, you associate network sites with network regions, and then you create bandwidth-allocating policies to apply to the bandwidth-constrained connections between a given site or region and the WAN connections between the sites and regions.</span></span>

</div>

<div>

## <a name="identify-network-links"></a><span data-ttu-id="7b0cb-167">네트워크 링크 식별</span><span class="sxs-lookup"><span data-stu-id="7b0cb-167">Identify Network Links</span></span>

<span data-ttu-id="7b0cb-168">네트워크 링크는 다른 지역과 사이트를 연결 하는 실제 WAN에 대 한 연결을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-168">Network links represent connections to the physical WAN that links different regions and sites.</span></span> <span data-ttu-id="7b0cb-169">이 예제 토폴로지에서는 두 개의 지역 네트워크 링크, 지역과 사이트 간 다섯 개의 네트워크 연결, 두 사이트 간의 네트워크 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-169">In our example topology, there are two regional network links, five network links between regions and sites, and one network link between two sites.</span></span>

<span data-ttu-id="7b0cb-170">두 지역 링크는 NA-EMEA-링크로 표시 되 고, EMEA-APAC 링크로 표시 되는 APAC와 EMEA 사이에 있는 북미와 EMEA 사이에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-170">The two regional links are between North America and EMEA, represented as NA-EMEA-LINK, and between APAC and EMEA, represented as EMEA-APAC-LINK.</span></span>

<span data-ttu-id="7b0cb-171">사이트 링크는 포틀랜드, Reno, Albuquerque를 북미 지역에 연결 하 고, APAC 지역으로 마닐라 하 고, EMEA 지역으로 Cologne 의해 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-171">The site links are indicated by the lines connecting Portland, Reno, and Albuquerque to the North America region, Manila to the APAC region, and Cologne to the EMEA region.</span></span> <span data-ttu-id="7b0cb-172">Reno와 Albuquerque 사이의 회선은 두 사이트 간의 직접 네트워크 링크를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-172">The line between Reno and Albuquerque shows a direct network link between these two sites.</span></span>

</div>

<div>

## <a name="define-bandwidth-policies"></a><span data-ttu-id="7b0cb-173">대역폭 정책 정의</span><span class="sxs-lookup"><span data-stu-id="7b0cb-173">Define Bandwidth Policies</span></span>

<span data-ttu-id="7b0cb-174">네트워크 운영 팀과 협력 하 여 조직의 WAN 연결에서 실시간 오디오 및 비디오 트래픽에 사용할 수 있는 WAN 대역폭의 양을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-174">Work with your network operations team to determine how much WAN bandwidth is available for real-time audio and video traffic across the WAN links in your organization.</span></span> <span data-ttu-id="7b0cb-175">대역폭 정책은 대역폭 사용량이 제한 된 경우 일반적으로 WAN 링크에 적용 됩니다. 즉, 오디오 및 비디오 형식을 할당할 수 있는 대역폭 보다 더 많은 것으로 예상 되는 경우</span><span class="sxs-lookup"><span data-stu-id="7b0cb-175">Bandwidth policies are typically applied to WAN links if the bandwidth usage is constrained; that is, if it expected to be more than the bandwidth that can be allocated for audio and video modalities.</span></span>

<span data-ttu-id="7b0cb-176">CAC *대역폭 정책은* 실시간 오디오 및 비디오 형식을 예약할 수 있는 최대 대역폭을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-176">CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities.</span></span> <span data-ttu-id="7b0cb-177">CAC는 다른 트래픽에 대 한 대역폭을 제한 하지 않으므로 모든 네트워크 대역폭을 사용 하 여 대용량 파일 전송, 음악 스트리밍 등의 다른 데이터 트래픽을 방지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-177">Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.</span></span>

<span data-ttu-id="7b0cb-178">CAC 대역폭 정책은 다음 중 일부 또는 모두를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-178">CAC bandwidth policies can define any or all of the following:</span></span>

  - <span data-ttu-id="7b0cb-179">오디오에 대해 할당 된 최대 총 대역폭입니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-179">Maximum total bandwidth allocated for audio.</span></span>

  - <span data-ttu-id="7b0cb-180">비디오에 대해 할당 된 최대 총 대역폭입니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-180">Maximum total bandwidth allocated for video.</span></span>

  - <span data-ttu-id="7b0cb-181">단일 오디오 통화 (세션)에 할당 된 최대 대역폭.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-181">Maximum bandwidth allocated for a single audio call (session).</span></span>

  - <span data-ttu-id="7b0cb-182">단일 비디오 통화 (세션)에 대해 할당 된 최대 대역폭입니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-182">Maximum bandwidth allocated for a single video call (session).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7b0cb-183">모든 CAC 대역폭 값은 최대 <EM>단방향</EM> 대역폭 제한을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-183">All CAC bandwidth values represent the maximum <EM>unidirectional</EM> bandwidth limits.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="7b0cb-184">Lync Server 2013 음성 정책 기능은 사용자에 게 들어오는 호출에 대 한 대역폭 정책 검사를 재정의 하는 기능을 제공 합니다 (사용자가 설정한 발신 통화에는 해당 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="7b0cb-184">The Lync Server 2013 Voice Policy features provide the ability to override bandwidth policy checks for incoming calls to the user (not for outgoing calls that are placed by the user).</span></span> <span data-ttu-id="7b0cb-185">세션을 설정한 후에는 대역폭 소비가 정확 하 게 고려 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-185">After the session is established, the bandwidth consumption will be accurately accounted for.</span></span> <span data-ttu-id="7b0cb-186">이 설정은 가끔씩만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-186">This setting should be used sparingly.</span></span> <span data-ttu-id="7b0cb-187">자세한 내용은 <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">음성 정책 만들기 및 Lync server 2013에서 pstn 사용 레코드 구성</A> 또는 <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">음성 정책 수정 및 lync SERVER 2013의 pstn 사용 레코드 구성을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-187">For details, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="7b0cb-188">세션 별로 대역폭 사용률을 최적화 하려면 사용할 오디오 및 비디오 코덱 유형을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-188">To optimize bandwidth utilization on a per-session basis, consider the type of audio and video codecs that will be used.</span></span> <span data-ttu-id="7b0cb-189">특히 자주 사용 하는 것으로 예상 되는 코덱에 충분 한 대역폭을 할당 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-189">In particular, avoid allocating insufficient bandwidth for a codec that you expect to be used frequently.</span></span> <span data-ttu-id="7b0cb-190">반대로 더 많은 대역폭이 필요한 코덱을 사용 하 여 미디어를 방지 하려면 세션당 최대 대역폭을 설정 하 여 이러한 사용을 막을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-190">Conversely, if you want to prevent media from using a codec that requires more bandwidth, you should set the maximum bandwidth per session low enough to discourage such use.</span></span> <span data-ttu-id="7b0cb-191">오디오의 경우 모든 코덱에 모든 코덱이 제공 되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-191">For audio, not every codec is available for every scenario.</span></span> <span data-ttu-id="7b0cb-192">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-192">For example:</span></span>

  - <span data-ttu-id="7b0cb-193">Lync 끝점 간의 피어 투 피어 오디오 통화는 코덱의 대역폭과 우선 순위에 영향을 주는 경우 RTAudio (8kHz) 또는 RTAudio (16kHz)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-193">Peer-to-peer audio calls between Lync endpoints will use either RTAudio (8kHz) or RTAudio (16kHz) when you factor in the bandwidth and prioritization of codecs.</span></span>

  - <span data-ttu-id="7b0cb-194">Lync 끝점과 A/V 회의 서비스 간의 컨퍼런스 통화는 722 또는 Siren 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-194">Conference calls between Lync endpoints and the A/V Conferencing service will use either G.722 or Siren.</span></span>

  - <span data-ttu-id="7b0cb-195">Lync 끝점에서 보내거나 받을 때 PSTN (공개 통신 네트워크)에 대 한 통화는 711 또는 RTAudio (8kHz)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-195">Calls to the public switched telephone network (PSTN) either to or from Lync endpoints will use either G.711 or RTAudio (8kHz).</span></span>

<span data-ttu-id="7b0cb-196">다음 표를 사용 하 여 세션당 최대 대역폭 설정을 최적화 해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-196">Use the following table to help optimize the maximum per-session bandwidth settings.</span></span>

### <a name="bandwidth-utilization-by-codecs"></a><span data-ttu-id="7b0cb-197">코덱에의 한 대역폭 이용률</span><span class="sxs-lookup"><span data-stu-id="7b0cb-197">Bandwidth utilization by codecs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b0cb-198">코덱이나</span><span class="sxs-lookup"><span data-stu-id="7b0cb-198">Codec</span></span></th>
<th><span data-ttu-id="7b0cb-199">FEC (정방향 오류 수정 없음)의 대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b0cb-199">Bandwidth requirement with no forward error correction (FEC)</span></span></th>
<th><span data-ttu-id="7b0cb-200">FEC (정방향 오류 정정)의 대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b0cb-200">Bandwidth requirement with forward error correction (FEC)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b0cb-201">RTAudio (8kHz)</span><span class="sxs-lookup"><span data-stu-id="7b0cb-201">RTAudio (8kHz)</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-202">49.8 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-202">49.8 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-203">61.6 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-203">61.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b0cb-204">RTAudio (16kHz)</span><span class="sxs-lookup"><span data-stu-id="7b0cb-204">RTAudio (16kHz)</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-205">67 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-205">67 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-206">96 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-206">96 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b0cb-207">사이렌</span><span class="sxs-lookup"><span data-stu-id="7b0cb-207">Siren</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-208">57.6 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-208">57.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-209">73.6 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-209">73.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b0cb-210">711</span><span class="sxs-lookup"><span data-stu-id="7b0cb-210">G.711</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-211">102 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-211">102 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-212">166 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-212">166 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b0cb-213">722</span><span class="sxs-lookup"><span data-stu-id="7b0cb-213">G.722</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-214">105.6 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-214">105.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-215">169.6 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-215">169.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b0cb-216">RTVideo (CIF 15fps)</span><span class="sxs-lookup"><span data-stu-id="7b0cb-216">RTVideo (CIF 15 fps)</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-217">260 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-217">260 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-218">해당 없음</span><span class="sxs-lookup"><span data-stu-id="7b0cb-218">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b0cb-219">RTVideo (VGA 30fps)</span><span class="sxs-lookup"><span data-stu-id="7b0cb-219">RTVideo (VGA 30 fps)</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-220">610 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-220">610 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-221">해당 없음</span><span class="sxs-lookup"><span data-stu-id="7b0cb-221">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="7b0cb-222">대역폭 요구 사항은 이더넷 II, IP, 사용자 데이터 그램 프로토콜 (UDP), RTP (실시간 전송 프로토콜), SRTP (보안 실시간 전송 프로토콜)에 대 한 계정 오버 헤드를 차지 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-222">Bandwidth requirements take into account overhead for the following: Ethernet II, IP, User Datagram Protocol (UDP), RTP (real-time transport protocol), and SRTP (secure real-time transport protocol).</span></span> <span data-ttu-id="7b0cb-223">또한 RTCP 오버 헤드에는 10mbps가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-223">They also include 10 kbps for RTCP overhead.</span></span>



</div>

<span data-ttu-id="7b0cb-224">722.1 및 Siren 코덱은 비슷하지만 다양 한 비트 전송률을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-224">The G.722.1 and Siren codecs are similar, but they offer different bit rates.</span></span>

<span data-ttu-id="7b0cb-225">722는 Lync Server 회의의 기본 코덱으로 722.1 및 Siren 코덱과 완전히 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-225">G.722, the default codec for Lync Server conferencing, is completely different from the G.722.1 and Siren codecs.</span></span>

<span data-ttu-id="7b0cb-226">다음과 같은 경우에는 Lync Server에서 Siren 코덱이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-226">The Siren codec is used in Lync Server in the following situations:</span></span>

  - <span data-ttu-id="7b0cb-227">대역폭 정책이 722에 대해 너무 낮게 설정 된 경우 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-227">If the bandwidth policy is set too low for G.722 to be used.</span></span>

  - <span data-ttu-id="7b0cb-228">통신 서버 2007 또는 통신 서버 2007 R2 클라이언트가 Lync Server 회의 서비스에 연결 되는 경우 (해당 클라이언트는 722 코덱을 지원 하지 않기 때문)</span><span class="sxs-lookup"><span data-stu-id="7b0cb-228">If a Communications Server 2007 or Communications Server 2007 R2 client connects to a Lync Server conferencing service (because those clients do not support the G.722 codec).</span></span>

### <a name="bandwidth-utilization-by-scenario"></a><span data-ttu-id="7b0cb-229">시나리오에의 한 대역폭 사용률</span><span class="sxs-lookup"><span data-stu-id="7b0cb-229">Bandwidth utilization by scenario</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7b0cb-230">시나리오</span><span class="sxs-lookup"><span data-stu-id="7b0cb-230">Scenario</span></span></th>
<th><span data-ttu-id="7b0cb-231">용량에 최적화 된 대역폭 요구 사항 (kbps)</span><span class="sxs-lookup"><span data-stu-id="7b0cb-231">Bandwidth requirement optimized for quantity (kbps)</span></span></th>
<th><span data-ttu-id="7b0cb-232">균형 모드 (kbps) 대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7b0cb-232">Bandwidth requirement for Balanced mode (kbps)</span></span></th>
<th><span data-ttu-id="7b0cb-233">음질에 맞게 최적화 된 대역폭 요구 사항 (kbps)</span><span class="sxs-lookup"><span data-stu-id="7b0cb-233">Bandwidth requirement optimized for quality (kbps)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7b0cb-234">피어 투 피어 오디오 통화</span><span class="sxs-lookup"><span data-stu-id="7b0cb-234">Peer-to-peer audio calls</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-235">45 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-235">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-236">62 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-236">62 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-237">91 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-237">91 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b0cb-238">컨퍼런스 통화</span><span class="sxs-lookup"><span data-stu-id="7b0cb-238">Conference calls</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-239">53 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-239">53 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-240">101 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-240">101 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-241">165 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-241">165 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b0cb-242">PSTN 통화 (Lync 2013 및 PSTN 게이트웨이 간, 미디어 바이패스 사용)</span><span class="sxs-lookup"><span data-stu-id="7b0cb-242">PSTN calls (between Lync 2013 and PSTN gateway, with media bypass)</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-243">97 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-243">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-244">97 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-244">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-245">161 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-245">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b0cb-246">PSTN 통화 (Lync 2013 및 중재 서버 간, 미디어 바이패스 없음)</span><span class="sxs-lookup"><span data-stu-id="7b0cb-246">PSTN calls (between Lync 2013 and Mediation Server, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-247">45 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-247">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-248">97 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-248">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-249">161 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-249">161 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7b0cb-250">PSTN 통화 (중재 서버와 PSTN 게이트웨이 간의 미디어 바이패스 없음)</span><span class="sxs-lookup"><span data-stu-id="7b0cb-250">PSTN calls (between Mediation Server and PSTN gateway, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-251">97 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-251">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-252">97 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-252">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-253">161 kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-253">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7b0cb-254">Lync-Polycom 통화</span><span class="sxs-lookup"><span data-stu-id="7b0cb-254">Lync - Polycom calls</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-255">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-255">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-256">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-256">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="7b0cb-257">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="7b0cb-257">101 Kbps</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="7b0cb-258">IP 서브넷 확인</span><span class="sxs-lookup"><span data-stu-id="7b0cb-258">Identify IP Subnets</span></span>

<span data-ttu-id="7b0cb-259">각 네트워크 사이트에 대해 네트워크 관리자와 협력 하 여 각 네트워크 사이트에 할당 되는 IP 서브넷을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-259">For each network site, you will need to work with your network administrator to determine what IP subnets are assigned to each network site.</span></span> <span data-ttu-id="7b0cb-260">네트워크 관리자가 이미 네트워크 지역 및 네트워크 사이트로 IP 서브넷을 구성한 경우에는 작업이 대폭 간소화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-260">If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="7b0cb-261">이 예제에서 북미 지역의 뉴욕 사이트에는 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24의 IP 서브넷이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-261">In our example, the New York site in the North America region is assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span></span> <span data-ttu-id="7b0cb-262">일반적으로 디트로이트에서 작동 하는 Bob이 뉴욕 사무실로 이동 하 여 교육을 할 수 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-262">Suppose Bob, who typically works in Detroit, travels to the New York office for training.</span></span> <span data-ttu-id="7b0cb-263">컴퓨터를 설정 하 고 네트워크에 연결 하면 컴퓨터는 뉴욕에 대해 예약 된 4 개 범위 (예: 172.29.80.103) 중 하나에서 IP 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-263">When he turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges reserved for New York, for example 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="7b0cb-264">서버에서 네트워크 구성 중에 지정 된 IP 서브넷은 미디어 바이패스에 따라 올바르게 사용 되기 위해 클라이언트 컴퓨터에서 제공 하는 형식과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-264">The IP subnets specified during network configuration on the server must match the format provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="7b0cb-265">Lync 클라이언트는 해당 로컬 IP 주소를 사용 하 고 연결 된 서브넷 마스크를 사용 하 여 IP 주소를 마스크 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-265">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="7b0cb-266">각 클라이언트와 연결 된 우회 ID를 결정할 때, 레지스트라는 정확히 일치 하는 클라이언트가 제공 하는 서브넷에 대해 각 네트워크 사이트와 연결 된 IP 서브넷 목록을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-266">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet provided by the client for an exact match.</span></span> <span data-ttu-id="7b0cb-267">이러한 이유로, 서버에서 네트워크를 구성 하는 동안 입력 된 서브넷이 가상 서브넷 대신 실제 서브넷이 되는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-267">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="7b0cb-268">(통화 허용 제어를 배포 하지만 미디어 바이패스는 아닌 경우 가상 서브넷을 구성한 경우에도 통화 허용 제어가 올바르게 작동 합니다.)</span><span class="sxs-lookup"><span data-stu-id="7b0cb-268">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="7b0cb-269">예를 들어 클라이언트가 ip 서브넷 마스크가 255.255.255.0 인 172.29.81.57의 IP 주소를 사용 하 여 컴퓨터에 로그인 하는 경우 Lync 2013은 서브넷 172.29.81.0와 연결 된 우회 ID를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-269">For example, if a client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, Lync 2013 will request the bypass ID associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="7b0cb-270">서브넷이 172.29.0.0/16으로 정의 된 경우에는 클라이언트가 가상 서브넷에 속해 있지만, 레지스트라는 특별히 서브넷 172.29.81.0를 찾고 있기 때문에이에 대 한 일치가 고려 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b0cb-270">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="7b0cb-271">따라서 관리자가 Lync 클라이언트에서 제공한 대로 서브넷을 정확히 입력 해야 합니다 (네트워크 구성 중에는 정적 또는 DHCP를 통해 서브넷으로 프로 비전 됨).</span><span class="sxs-lookup"><span data-stu-id="7b0cb-271">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration either statically or by DHCP.)</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

