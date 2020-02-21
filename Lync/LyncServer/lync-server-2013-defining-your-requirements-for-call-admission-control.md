---
title: 'Lync Server 2013: 통화 허용 제어에 대 한 요구 사항 정의'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6de02e10f884bf35c87ec8147c66bb720ad39c89
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213924"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="0f113-102">Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 정의</span><span class="sxs-lookup"><span data-stu-id="0f113-102">Defining your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f113-103">_**마지막으로 수정 된 항목:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="0f113-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="0f113-p101">CAC(통화 허용 제어) 계획에는 엔터프라이즈 네트워크 토폴로지에 대한 자세한 정보가 필요합니다. 다음 단계에 따라 통화 허용 제어 정책을 보다 쉽게 계획할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-p101">Planning for call admission control (CAC) requires detailed information about your enterprise network topology. To help plan your call admission control policies, follow these steps.</span></span>

1.  <span data-ttu-id="0f113-106">엔터프라이즈 네트워크 내의 허브/백본(*네트워크 지역*이라고 함) 확인</span><span class="sxs-lookup"><span data-stu-id="0f113-106">Identify the hubs/backbones (called *network regions*) within your enterprise network.</span></span>

2.  <span data-ttu-id="0f113-107">각 네트워크 지역 내의 사무실 또는 위치(*네트워크 사이트*라고 함) 확인</span><span class="sxs-lookup"><span data-stu-id="0f113-107">Identify the offices or locations (called *network sites*) within each network region.</span></span>

3.  <span data-ttu-id="0f113-108">모든 네트워크 지역 쌍 간의 네트워크 경로 확인</span><span class="sxs-lookup"><span data-stu-id="0f113-108">Determine the network route between every pair of network regions.</span></span>

4.  <span data-ttu-id="0f113-109">각 WAN 링크에 대한 대역폭 제한 확인</span><span class="sxs-lookup"><span data-stu-id="0f113-109">Determine the bandwidth limits for each WAN link.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0f113-110">대역폭 제한은 WAN 링크에서 엔터프라이즈 음성 및 오디오/비디오 트래픽에 할당 되는 대역폭의 양을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-110">Bandwidth limits refer to how much of the bandwidth on a WAN link is allocated to Enterprise Voice and audio/video traffic.</span></span> <span data-ttu-id="0f113-111">따라서 WAN 링크가 "대역폭이 제한된" 것으로 설명된 경우 링크에서 예상되는 최대 트래픽보다 낮은 대역폭 제한이 WAN 링크에 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-111">When a WAN link is described as “bandwidth-constrained,” the WAN link has a bandwidth limit that is lower than the expected peak traffic over the link.</span></span>

    
    </div>

5.  <span data-ttu-id="0f113-112">각 네트워크 사이트에 지정된 IP 서브넷 확인</span><span class="sxs-lookup"><span data-stu-id="0f113-112">Identify the IP subnets that are assigned to each network site.</span></span>

<span data-ttu-id="0f113-113">이러한 개념을 설명하기 위해 아래 그림에 표시된 네트워크 토폴로지 예를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-113">To explain these concepts, we’ll use the example network topology shown in the following figure.</span></span>

<span data-ttu-id="0f113-114">**통화 허용 제어 토폴로지의 예**</span><span class="sxs-lookup"><span data-stu-id="0f113-114">**Example topology for call admission control**</span></span>

<span data-ttu-id="0f113-115">![Litware Inc. 네트워크 토폴로지 예](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. 네트워크 토폴로지 예")</span><span class="sxs-lookup"><span data-stu-id="0f113-115">![Litware Inc. Network Topology Example](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. Network Topology Example")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0f113-p103">모든 네트워크 사이트는 네트워크 지역과 연결됩니다. 예를 들어 포틀랜드, 리노 및 앨버커키는 북미 지역에 포함됩니다. 이 그림에는 CAC 정책이 적용되는 WAN 링크에만 대역폭 제한이 표시되어 있습니다. 시카고, 뉴욕 및 디트로이트의 네트워크 사이트는 대역폭 제한이 없어 CAC 정책이 필요하지 않으므로 북미 지역 타원 안에 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-p103">All network sites are associated with a network region. For example, Portland, Reno, and Albuquerque are included in the North America region. In this figure, only WAN links that have CAC policies applied are shown, with bandwidth limits. The network sites of Chicago, New York, and Detroit are shown inside the North America region oval because they are not bandwidth-constrained, and therefore do not require CAC policies.</span></span>



</div>

<span data-ttu-id="0f113-120">이 토폴로지의 예의 구성 요소는 다음 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-120">The components of this example topology are explained in the following sections.</span></span> <span data-ttu-id="0f113-121">대역폭 제한을 비롯 하 여이 토폴로지의 계획 방식에 대 한 자세한 내용은 [Example: Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 수집](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0f113-121">For details about how this topology was planned, including the bandwidth limits, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span></span>

<div>

## <a name="identify-network-regions"></a><span data-ttu-id="0f113-122">네트워크 지역 확인</span><span class="sxs-lookup"><span data-stu-id="0f113-122">Identify Network Regions</span></span>

<span data-ttu-id="0f113-123">네트워크 지역은 네트워크 백본 또는 네트워크 허브를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-123">A network region represents a network backbone or a network hub.</span></span>

<span data-ttu-id="0f113-p105">네트워크 백본 또는 허브는 네트워크의 여러 부분을 상호 연결하는 컴퓨터 네트워크 인프라의 일부로서, 서로 다른 LAN 또는 서브넷 간의 정보 교환 경로를 제공합니다. 백본은 소규모 위치에서 지리적으로 넓은 지역에 이르기까지 다양한 네트워크를 함께 묶을 수 있습니다. 따라서 백본의 용량은 일반적으로 백본에 연결된 네트워크의 용량보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-p105">A network backbone or hub is a part of computer network infrastructure that interconnects different parts of the network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks that connect to it.</span></span>

<span data-ttu-id="0f113-p106">여기에 설명된 토폴로지에는 북미, EMEA, APAC, 이렇게 세 개의 네트워크 지역이 있습니다. 네트워크 지역은 네트워크 사이트 컬렉션을 포함합니다(이 항목에 뒷 부분에 설명된 네트워크 사이트 정의 참조). 네트워크 운영 팀과 함께 네트워크 지역을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="0f113-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites (see the definition of network sites later in this topic). Work with your network operations team to identify your network regions.</span></span>

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a><span data-ttu-id="0f113-130">각 네트워크 지역에 중앙 사이트 연결</span><span class="sxs-lookup"><span data-stu-id="0f113-130">Associating a Central Site with each Network Region</span></span>

<span data-ttu-id="0f113-131">CAC를 사용 하려면 각 네트워크 지역에 대해 Lync Server 중앙 사이트가 정의 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-131">CAC requires that a Lync Server central site is defined for each network region.</span></span> <span data-ttu-id="0f113-132">중앙 사이트는 해당 네트워크 지역 내의 다른 모든 사이트에 대해 네트워크 연결 상태가 최상이고 대역폭이 가장 빠른 것으로 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-132">The central site is selected with the best network connectivity and highest bandwidth to all the other sites within that network region.</span></span> <span data-ttu-id="0f113-133">앞의 네트워크 토폴로지 예에서는 3개의 네트워크 지역이 표시되며, 각 지역에는 CAC 결정을 관리하는 중앙 사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-133">The preceding example of network topology shows three network regions, each with a central site that manages CAC decisions.</span></span> <span data-ttu-id="0f113-134">앞의 예에서 적합한 연결은 다음 표에 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-134">From the preceding example, the appropriate association is shown in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0f113-135">중앙 사이트가 반드시 네트워크 사이트에 해당 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-135">Central sites do not necessarily correspond to network sites.</span></span> <span data-ttu-id="0f113-136">이 설명서의 예에서는 시카고, London 및 베이징 라는 일부 중앙 사이트는 네트워크 사이트와 같은 이름을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-136">In the examples in this documentation, some central sites—Chicago, London, and Beijing—share the same name as the network sites.</span></span> <span data-ttu-id="0f113-137">그러나 중앙 사이트와 네트워크 사이트에 같은 이름이 공유 되는 경우에도 중앙 사이트는 Lync Server 토폴로지의 요소 이지만, 네트워크 사이트는 Lync Server 토폴로지가 있는 전체 네트워크의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-137">However, even if a central site and network site share the same name, the central site is an element of the Lync Server topology, whereas the network site is a part of the overall network in which the Lync Server topology resides.</span></span>



</div>

### <a name="network-regions-central-sites-and-network-sites"></a><span data-ttu-id="0f113-138">네트워크 지역, 중앙 사이트 및 네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="0f113-138">Network regions, central sites, and network sites</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f113-139">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="0f113-139">Network Region</span></span></th>
<th><span data-ttu-id="0f113-140">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="0f113-140">Central Site</span></span></th>
<th><span data-ttu-id="0f113-141">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="0f113-141">Network Sites</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f113-142">북미</span><span class="sxs-lookup"><span data-stu-id="0f113-142">North America</span></span></p></td>
<td><p><span data-ttu-id="0f113-143">지사</span><span class="sxs-lookup"><span data-stu-id="0f113-143">Chicago</span></span></p></td>
<td><p><span data-ttu-id="0f113-144">지사</span><span class="sxs-lookup"><span data-stu-id="0f113-144">Chicago</span></span></p>
<p><span data-ttu-id="0f113-145">뉴욕</span><span class="sxs-lookup"><span data-stu-id="0f113-145">New York</span></span></p>
<p><span data-ttu-id="0f113-146">디트로이트</span><span class="sxs-lookup"><span data-stu-id="0f113-146">Detroit</span></span></p>
<p><span data-ttu-id="0f113-147">포틀랜드</span><span class="sxs-lookup"><span data-stu-id="0f113-147">Portland</span></span></p>
<p><span data-ttu-id="0f113-148">리노</span><span class="sxs-lookup"><span data-stu-id="0f113-148">Reno</span></span></p>
<p><span data-ttu-id="0f113-149">앨버커키</span><span class="sxs-lookup"><span data-stu-id="0f113-149">Albuquerque</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f113-150">슈팅</span><span class="sxs-lookup"><span data-stu-id="0f113-150">EMEA</span></span></p></td>
<td><p><span data-ttu-id="0f113-151">인</span><span class="sxs-lookup"><span data-stu-id="0f113-151">London</span></span></p></td>
<td><p><span data-ttu-id="0f113-152">인</span><span class="sxs-lookup"><span data-stu-id="0f113-152">London</span></span></p>
<p><span data-ttu-id="0f113-153">Cologne</span><span class="sxs-lookup"><span data-stu-id="0f113-153">Cologne</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f113-154">APAC</span><span class="sxs-lookup"><span data-stu-id="0f113-154">APAC</span></span></p></td>
<td><p><span data-ttu-id="0f113-155">베이징</span><span class="sxs-lookup"><span data-stu-id="0f113-155">Beijing</span></span></p></td>
<td><p><span data-ttu-id="0f113-156">베이징</span><span class="sxs-lookup"><span data-stu-id="0f113-156">Beijing</span></span></p>
<p><span data-ttu-id="0f113-157">Manila</span><span class="sxs-lookup"><span data-stu-id="0f113-157">Manila</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a><span data-ttu-id="0f113-158">네트워크 사이트 확인</span><span class="sxs-lookup"><span data-stu-id="0f113-158">Identify Network Sites</span></span>

<span data-ttu-id="0f113-p109">네트워크 사이트는 조직의 실제 장소(예: 사무실, 건물 또는 캠퍼스)가 있는 위치를 나타냅니다. LAN과 다른 사이트에 대한 WAN을 갖고 있는 실제 장소를 네트워크 사이트로 간주합니다. 조직의 모든 사무실을 조사하는 작업부터 시작합니다. 위의 토폴로지 예에서 북미 네트워크 지역은 뉴욕, 시카고, 디트로이트, 포틀랜드, 리노 및 앨버커키 네트워크 사이트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-p109">A network site represents a location where your organization has a physical venue—for example, offices, a set of buildings, or a campus. A physical venue with a LAN and has WAN connectivity to other sites is considered a network site. Start by inventorying all of your organization’s offices. In our example topology, the North America network region consists of the following network sites: New York, Chicago, Detroit, Portland, Reno, and Albuquerque.</span></span>

<span data-ttu-id="0f113-p110">모든 네트워크 사이트를 네트워크 지역과 연결해야 합니다. 네트워크 사이트에 제한된 WAN 링크가 있는지 여부에 따라 대역폭 정책이 네트워크 사이트에 연결됩니다. CAC 정책 및 이러한 정책을 사용하여 할당하는 대역폭에 대한 자세한 내용은 이 항목의 뒷부분에 나오는 "대역폭 정책 정의"를 참조하십시오. CAC를 구성하려면 네트워크 사이트를 네트워크 지역과 연결한 다음 지정된 사이트 또는 지역 간의 대역폭 제한 연결 및 사이트와 지역 간의 WAN 연결에 적용할 대역폭 할당 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-p110">You must associate every network site with a network region. Depending on whether the network site has a constrained WAN link, a bandwidth policy is associated with the network site. For details about CAC policies and the bandwidth that you allocate by using them, see "Define Bandwidth Policies" later in this topic. To configure CAC, you associate network sites with network regions, and then you create bandwidth-allocating policies to apply to the bandwidth-constrained connections between a given site or region and the WAN connections between the sites and regions.</span></span>

</div>

<div>

## <a name="identify-network-links"></a><span data-ttu-id="0f113-167">네트워크 링크 확인</span><span class="sxs-lookup"><span data-stu-id="0f113-167">Identify Network Links</span></span>

<span data-ttu-id="0f113-p111">네트워크 링크는 서로 다른 지역 및 사이트를 연결하는 실제 WAN 연결을 나타냅니다. 위의 토폴로지 예에는 지역 간을 연결하는 두 개의 네트워크 링크, 지역과 사이트를 연결하는 다섯 개의 네트워크 링크 및 두 사이트를 연결하는 하나의 네트워크 링크가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-p111">Network links represent connections to the physical WAN that links different regions and sites. In our example topology, there are two regional network links, five network links between regions and sites, and one network link between two sites.</span></span>

<span data-ttu-id="0f113-170">두 개의 지역 링크는 북미와 EMEA, APAC와 EMEA를 연결하며, 각각 NA-EMEA-LINK와 EMEA-APAC-LINK로 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-170">The two regional links are between North America and EMEA, represented as NA-EMEA-LINK, and between APAC and EMEA, represented as EMEA-APAC-LINK.</span></span>

<span data-ttu-id="0f113-p112">사이트 링크는 포틀랜드, 리노 및 앨버커키와 북미 지역을 연결하는 선, 마닐라와 APAC 지역을 연결하는 선, 그리고 콜로뉴와 EMEA 지역을 연결하는 선으로 표시되어 있습니다. 리노와 앨버커키 사이의 선은 이 두 사이트 간의 직접 네트워크 링크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-p112">The site links are indicated by the lines connecting Portland, Reno, and Albuquerque to the North America region, Manila to the APAC region, and Cologne to the EMEA region. The line between Reno and Albuquerque shows a direct network link between these two sites.</span></span>

</div>

<div>

## <a name="define-bandwidth-policies"></a><span data-ttu-id="0f113-173">대역폭 정책 정의</span><span class="sxs-lookup"><span data-stu-id="0f113-173">Define Bandwidth Policies</span></span>

<span data-ttu-id="0f113-p113">네트워크 운영 팀과 함께 조직의 WAN 링크를 통해 실시간 오디오 및 비디오 트래픽에 사용할 수 있는 WAN 대역폭을 확인합니다. 대역폭 정책은 일반적으로 대역폭 사용이 제한된 경우, 즉 오디오 및 비디오 형식에 할당될 수 있는 대역폭보다 많은 대역폭이 사용될 것으로 예상되는 경우 WAN 링크에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-p113">Work with your network operations team to determine how much WAN bandwidth is available for real-time audio and video traffic across the WAN links in your organization. Bandwidth policies are typically applied to WAN links if the bandwidth usage is constrained; that is, if it expected to be more than the bandwidth that can be allocated for audio and video modalities.</span></span>

<span data-ttu-id="0f113-p114">CAC *대역폭 정책*은 실시간 오디오 및 비디오 형식에 대해 예약할 수 있는 최대 대역폭을 정의합니다. CAC는 다른 트래픽의 대역폭을 제한하지 않기 때문에 대규모 파일 전송, 음악 스트리밍 등의 다른 데이터 트래픽이 네트워크 대역폭을 모두 사용하지 못하도록 방지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-p114">CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities. Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.</span></span>

<span data-ttu-id="0f113-178">CAC 대역폭 정책은 다음 중 일부 또는 전부를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-178">CAC bandwidth policies can define any or all of the following:</span></span>

  - <span data-ttu-id="0f113-179">오디오에 할당되는 최대 총 대역폭</span><span class="sxs-lookup"><span data-stu-id="0f113-179">Maximum total bandwidth allocated for audio.</span></span>

  - <span data-ttu-id="0f113-180">비디오에 할당되는 최대 총 대역폭</span><span class="sxs-lookup"><span data-stu-id="0f113-180">Maximum total bandwidth allocated for video.</span></span>

  - <span data-ttu-id="0f113-181">단일 음성 통화(세션)에 할당되는 최대 대역폭</span><span class="sxs-lookup"><span data-stu-id="0f113-181">Maximum bandwidth allocated for a single audio call (session).</span></span>

  - <span data-ttu-id="0f113-182">단일 화상 통화(세션)에 할당되는 최대 대역폭</span><span class="sxs-lookup"><span data-stu-id="0f113-182">Maximum bandwidth allocated for a single video call (session).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0f113-183">모든 CAC 대역폭 값은 최대 <EM>단방향</EM> 대역폭 제한을 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-183">All CAC bandwidth values represent the maximum <EM>unidirectional</EM> bandwidth limits.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0f113-184">Lync Server 2013 음성 정책 기능을 사용 하면 사용자에 게 제공 되는 발신 전화에 대해 대역폭 정책 검사를 사용자에 게 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-184">The Lync Server 2013 Voice Policy features provide the ability to override bandwidth policy checks for incoming calls to the user (not for outgoing calls that are placed by the user).</span></span> <span data-ttu-id="0f113-185">세션이 설정된 후에는 대역폭 소비가 정확하게 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-185">After the session is established, the bandwidth consumption will be accurately accounted for.</span></span> <span data-ttu-id="0f113-186">이 설정은 가급적 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-186">This setting should be used sparingly.</span></span> <span data-ttu-id="0f113-187">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">음성 정책 만들기 및 Lync server 2013에서 pstn 사용 레코드 구성 및</A> <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">lync SERVER 2013에서 pstn 사용 레코드 구성</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0f113-187">For details, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="0f113-p116">세션별 대역폭 사용량을 최적화하려면 사용할 오디오 및 비디오 코덱의 유형을 고려해야 합니다. 특히, 자주 사용할 것으로 예상되는 코덱에 대한 대역폭을 부족하게 할당하지 않아야 합니다. 반면, 미디어에서 많은 대역폭이 필요한 코덱을 사용하지 않도록 하려면 이러한 코덱을 사용할 수 없을 정도로 낮게 세션별 최대 대역폭을 설정해야 합니다. 오디오의 경우 일부 코덱은 일부 시나리오에 사용할 수 없습니다. 예:</span><span class="sxs-lookup"><span data-stu-id="0f113-p116">To optimize bandwidth utilization on a per-session basis, consider the type of audio and video codecs that will be used. In particular, avoid allocating insufficient bandwidth for a codec that you expect to be used frequently. Conversely, if you want to prevent media from using a codec that requires more bandwidth, you should set the maximum bandwidth per session low enough to discourage such use. For audio, not every codec is available for every scenario. For example:</span></span>

  - <span data-ttu-id="0f113-193">Lync 끝점 간의 피어 투 피어 오디오 통화는 코덱의 대역폭과 우선 순위에 영향을 주는 경우 RTAudio (8kHz) 또는 RTAudio (16kHz)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-193">Peer-to-peer audio calls between Lync endpoints will use either RTAudio (8kHz) or RTAudio (16kHz) when you factor in the bandwidth and prioritization of codecs.</span></span>

  - <span data-ttu-id="0f113-194">Lync 끝점과 A/V 회의 서비스 간의 전화 회의에서는 722 또는 Siren를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-194">Conference calls between Lync endpoints and the A/V Conferencing service will use either G.722 or Siren.</span></span>

  - <span data-ttu-id="0f113-195">공중 전화망 (PSTN)에 대 한 통화는 Lync 끝점에서 보내거나 온-g.711 또는 RTAudio (8kHz)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-195">Calls to the public switched telephone network (PSTN) either to or from Lync endpoints will use either G.711 or RTAudio (8kHz).</span></span>

<span data-ttu-id="0f113-196">다음 표는 세션별 최대 대역폭 설정을 최적화하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-196">Use the following table to help optimize the maximum per-session bandwidth settings.</span></span>

### <a name="bandwidth-utilization-by-codecs"></a><span data-ttu-id="0f113-197">코덱별 대역폭 사용량</span><span class="sxs-lookup"><span data-stu-id="0f113-197">Bandwidth utilization by codecs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f113-198">코덱</span><span class="sxs-lookup"><span data-stu-id="0f113-198">Codec</span></span></th>
<th><span data-ttu-id="0f113-199">FEC(정방향 오류 정정)가 없는 대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f113-199">Bandwidth requirement with no forward error correction (FEC)</span></span></th>
<th><span data-ttu-id="0f113-200">FEC(정방향 오류 정정)가 있는 대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f113-200">Bandwidth requirement with forward error correction (FEC)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f113-201">RTAudio(8kHz)</span><span class="sxs-lookup"><span data-stu-id="0f113-201">RTAudio (8kHz)</span></span></p></td>
<td><p><span data-ttu-id="0f113-202">49.8kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-202">49.8 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-203">61.6kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-203">61.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f113-204">RTAudio(16kHz)</span><span class="sxs-lookup"><span data-stu-id="0f113-204">RTAudio (16kHz)</span></span></p></td>
<td><p><span data-ttu-id="0f113-205">67kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-205">67 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-206">96kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-206">96 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f113-207">Siren</span><span class="sxs-lookup"><span data-stu-id="0f113-207">Siren</span></span></p></td>
<td><p><span data-ttu-id="0f113-208">57.6kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-208">57.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-209">73.6kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-209">73.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f113-210">G.711</span><span class="sxs-lookup"><span data-stu-id="0f113-210">G.711</span></span></p></td>
<td><p><span data-ttu-id="0f113-211">102kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-211">102 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-212">166kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-212">166 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f113-213">722</span><span class="sxs-lookup"><span data-stu-id="0f113-213">G.722</span></span></p></td>
<td><p><span data-ttu-id="0f113-214">105.6kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-214">105.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-215">169.6kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-215">169.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f113-216">RTVideo(CIF 15fps)</span><span class="sxs-lookup"><span data-stu-id="0f113-216">RTVideo (CIF 15 fps)</span></span></p></td>
<td><p><span data-ttu-id="0f113-217">260kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-217">260 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-218">해당 없음</span><span class="sxs-lookup"><span data-stu-id="0f113-218">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f113-219">RTVideo(VGA 30fps)</span><span class="sxs-lookup"><span data-stu-id="0f113-219">RTVideo (VGA 30 fps)</span></span></p></td>
<td><p><span data-ttu-id="0f113-220">610kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-220">610 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-221">해당 없음</span><span class="sxs-lookup"><span data-stu-id="0f113-221">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="0f113-p117">대역폭 요구 사항에는 Ethernet II, IP, UDP(User Datagram Protocol), RTP(Real-time Transport Protocol) 및 SRTP(실시간 전송 프로토콜)에 대한 오버헤드가 고려되어 있으며, RTCP 오버헤드에 대한 10kbps도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-p117">Bandwidth requirements take into account overhead for the following: Ethernet II, IP, User Datagram Protocol (UDP), RTP (real-time transport protocol), and SRTP (secure real-time transport protocol). They also include 10 kbps for RTCP overhead.</span></span>



</div>

<span data-ttu-id="0f113-224">G.722.1 코덱과 Siren 코덱은 유사하지만 비트 전송률이 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-224">The G.722.1 and Siren codecs are similar, but they offer different bit rates.</span></span>

<span data-ttu-id="0f113-225">Lync Server 회의에 대 한 기본 코덱 인 722은 g.722.1 코덱과 및 Siren 코덱과 완전히 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-225">G.722, the default codec for Lync Server conferencing, is completely different from the G.722.1 and Siren codecs.</span></span>

<span data-ttu-id="0f113-226">다음과 같은 경우에는 Siren 코덱이 Lync Server에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-226">The Siren codec is used in Lync Server in the following situations:</span></span>

  - <span data-ttu-id="0f113-227">대역폭 정책이 너무 낮게 설정되어 G.722를 사용할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="0f113-227">If the bandwidth policy is set too low for G.722 to be used.</span></span>

  - <span data-ttu-id="0f113-228">Communications Server 2007 또는 Communications Server 2007 R2 클라이언트가 Lync Server 회의 서비스에 연결 하는 경우 (해당 클라이언트는 722 코덱을 지원 하지 않음)</span><span class="sxs-lookup"><span data-stu-id="0f113-228">If a Communications Server 2007 or Communications Server 2007 R2 client connects to a Lync Server conferencing service (because those clients do not support the G.722 codec).</span></span>

### <a name="bandwidth-utilization-by-scenario"></a><span data-ttu-id="0f113-229">시나리오별 대역폭 사용량</span><span class="sxs-lookup"><span data-stu-id="0f113-229">Bandwidth utilization by scenario</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f113-230">시나리오</span><span class="sxs-lookup"><span data-stu-id="0f113-230">Scenario</span></span></th>
<th><span data-ttu-id="0f113-231">수량에 최적화된 대역폭 요구 사항(kbps)</span><span class="sxs-lookup"><span data-stu-id="0f113-231">Bandwidth requirement optimized for quantity (kbps)</span></span></th>
<th><span data-ttu-id="0f113-232">균형 조정 모드에 적절한 대역폭 요구 사항(kbps)</span><span class="sxs-lookup"><span data-stu-id="0f113-232">Bandwidth requirement for Balanced mode (kbps)</span></span></th>
<th><span data-ttu-id="0f113-233">품질에 최적화된 대역폭 요구 사항(kbps)</span><span class="sxs-lookup"><span data-stu-id="0f113-233">Bandwidth requirement optimized for quality (kbps)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f113-234">피어 투 피어 음성 통화</span><span class="sxs-lookup"><span data-stu-id="0f113-234">Peer-to-peer audio calls</span></span></p></td>
<td><p><span data-ttu-id="0f113-235">45kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-235">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-236">62kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-236">62 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-237">91kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-237">91 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f113-238">전화 회의</span><span class="sxs-lookup"><span data-stu-id="0f113-238">Conference calls</span></span></p></td>
<td><p><span data-ttu-id="0f113-239">53kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-239">53 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-240">101kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-240">101 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-241">165kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-241">165 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f113-242">PSTN 통화 (Lync 2013와 PSTN 게이트웨이 간, 미디어 바이패스 포함)</span><span class="sxs-lookup"><span data-stu-id="0f113-242">PSTN calls (between Lync 2013 and PSTN gateway, with media bypass)</span></span></p></td>
<td><p><span data-ttu-id="0f113-243">97kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-243">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-244">97kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-244">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-245">161kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-245">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f113-246">PSTN 통화 (Lync 2013 및 중재 서버 간, 미디어 바이패스 제외)</span><span class="sxs-lookup"><span data-stu-id="0f113-246">PSTN calls (between Lync 2013 and Mediation Server, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="0f113-247">45kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-247">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-248">97kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-248">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-249">161kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-249">161 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f113-250">PSTN 통화 (중재 서버와 PSTN 게이트웨이 간, 미디어 바이패스 제외)</span><span class="sxs-lookup"><span data-stu-id="0f113-250">PSTN calls (between Mediation Server and PSTN gateway, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="0f113-251">97kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-251">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-252">97kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-252">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-253">161kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-253">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f113-254">Lync-Polycom 통화</span><span class="sxs-lookup"><span data-stu-id="0f113-254">Lync - Polycom calls</span></span></p></td>
<td><p><span data-ttu-id="0f113-255">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-255">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-256">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-256">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="0f113-257">101 Kbps</span><span class="sxs-lookup"><span data-stu-id="0f113-257">101 Kbps</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="0f113-258">IP 서브넷 확인</span><span class="sxs-lookup"><span data-stu-id="0f113-258">Identify IP Subnets</span></span>

<span data-ttu-id="0f113-p118">각 네트워크 사이트에 대해 네트워크 관리자와 함께 각 네트워크 사이트에 지정된 IP 서브넷을 확인해야 합니다. 네트워크 관리자가 네트워크 지역 및 네트워크 사이트에 대한 IP 서브넷을 이미 구성한 경우에는 작업이 훨씬 간편합니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-p118">For each network site, you will need to work with your network administrator to determine what IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="0f113-p119">위의 예에서 북미 지역의 뉴욕 사이트에는 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23 및 172.29.81.0/24 IP 서브넷이 지정되어 있습니다. 주로 디트로이트에서 근무하는 Bob이 교육을 받기 위해 뉴욕 사무실에 출장을 왔다고 가정해 보겠습니다. Bob이 컴퓨터를 켜고 네트워크에 연결하면 컴퓨터에서 뉴욕에 예약된 네 개 범위 중 하나의 IP 주소(예: 172.29.80.103)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-p119">In our example, the New York site in the North America region is assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suppose Bob, who typically works in Detroit, travels to the New York office for training. When he turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges reserved for New York, for example 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0f113-264">서버에서 네트워크를 구성하는 동안 지정된 IP 서브넷을 미디어 바이패스에 사용하려면 IP 서브넷이 클라이언트 컴퓨터에서 제공한 형식과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-264">The IP subnets specified during network configuration on the server must match the format provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="0f113-265">Lync 클라이언트는 해당 로컬 IP 주소를 사용 하 고 연결 된 서브넷 마스크와 함께 IP 주소를 마스크 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-265">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="0f113-266">각 클라이언트에 연결된 바이패스 ID를 확인할 때 등록자는 각 네트워크 사이트에 연결된 IP 서브넷 목록이 클라이언트에서 제공한 서브넷과 정확히 일치하는지 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-266">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet provided by the client for an exact match.</span></span> <span data-ttu-id="0f113-267">따라서 서버에서 네트워크를 구성할 때 가상 서브넷 대신 실제 서브넷을 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-267">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="0f113-268">미디어 바이패스가 아니라 통화 허용 제어를 배포한 경우에는 가상 서브넷을 구성한 경우에도 통화 허용 제어가 제대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-268">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="0f113-269">예를 들어 클라이언트에서 ip 서브넷 마스크가 255.255.255.0 인 172.29.81.57의 IP 주소를 사용 하는 컴퓨터에 로그인 하는 경우 Lync 2013는 서브넷 172.29.81.0와 연결 된 바이패스 ID를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-269">For example, if a client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, Lync 2013 will request the bypass ID associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="0f113-270">서브넷이 172.29.0.0/16으로 정의 된 경우 클라이언트가 가상 서브넷에 속해 있더라도 등록자는 특별히 서브넷 172.29.81.0를 찾고 있기 때문에 해당 등록자는이 일치를 고려 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-270">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="0f113-271">따라서 관리자는 네트워크 구성 중에 서브넷으로 또는 DHCP에 의해 프로 비전 되는 Lync 클라이언트에서 제공 하는 대로 서브넷을 정확히 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f113-271">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration either statically or by DHCP.)</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

