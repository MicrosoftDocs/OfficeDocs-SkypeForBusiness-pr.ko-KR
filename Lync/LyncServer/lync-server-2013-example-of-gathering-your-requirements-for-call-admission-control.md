---
title: 통화 허용 제어에 대 한 요구 사항을 수집 하는 예제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e17d9abb0387f0d77c696487558dec0c915b1651
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="25e7e-102">예: Lync Server 2013에서 통화 허용 제어에 대 한 요구 사항 수집</span><span class="sxs-lookup"><span data-stu-id="25e7e-102">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25e7e-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="25e7e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="25e7e-104">이 예제에서는 호출 허용 제어 (CAC)를 계획 하 고 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-104">This example shows you how to plan for and implement call admission control (CAC).</span></span> <span data-ttu-id="25e7e-105">상위 수준에서이는 다음 활동으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-105">At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="25e7e-106">모든 네트워크 허브 및 백본 ( *네트워크 지역*이라고 함)을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-106">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="25e7e-107">각 네트워크 지역에 대해 CAC를 관리 하는 Lync Server 중앙 사이트를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-107">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="25e7e-108">각 네트워크 영역에 연결 된 *네트워크 사이트* 를 식별 하 고 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-108">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="25e7e-109">WAN에 연결 된 각 네트워크 사이트에 대 한 대역폭이 제한 되는 경우 WAN 연결의 대역폭 용량과 네트워크 관리자가 Lync Server 미디어 트래픽에 대해 설정한 대역폭 제한에 대해 설명 합니다 (해당 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="25e7e-109">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="25e7e-110">WAN 연결이 대역폭이 제한 되지 않는 사이트는 포함할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-110">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="25e7e-111">네트워크의 각 서브넷을 네트워크 사이트와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-111">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="25e7e-112">네트워크 지역 간 링크를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-112">Map the links between the network regions.</span></span> <span data-ttu-id="25e7e-113">각 링크에 대해 네트워크 관리자가 Lync Server 미디어 트래픽에 설정한 대역폭 용량과 제한 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-113">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="25e7e-114">네트워크 지역의 모든 쌍 간의 경로를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-114">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="25e7e-115">필요한 정보 수집</span><span class="sxs-lookup"><span data-stu-id="25e7e-115">Gather the Required Information</span></span>

<span data-ttu-id="25e7e-116">통화 허용 제어를 준비 하려면 다음 단계에서 설명 하는 정보를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-116">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="25e7e-117">네트워크 지역을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-117">Identify your network regions.</span></span> <span data-ttu-id="25e7e-118">네트워크 영역은 네트워크 백본 또는 네트워크 허브를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-118">A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="25e7e-119">네트워크 백본 또는 네트워크 허브는 여러 네트워크 조각을 상호 관련 시키는 컴퓨터 네트워크 인프라의 일부 이며, 다양 한 Lan 또는 서브넷 간의 정보 교환 경로를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-119">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets.</span></span> <span data-ttu-id="25e7e-120">백본은 다양 한 네트워크를 소규모 위치에서 넓은 지역으로 묶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-120">A backbone can tie together diverse networks, from a small location to a wide geographic area.</span></span> <span data-ttu-id="25e7e-121">일반적으로 백본 용량이 연결 된 네트워크 보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-121">The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="25e7e-122">이 예제 토폴로지에는 북미, EMEA, APAC의 세 가지 네트워크 지역이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-122">Our example topology has three network regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="25e7e-123">네트워크 지역에는 네트워크 사이트 컬렉션이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-123">A network region contains a collection of network sites.</span></span> <span data-ttu-id="25e7e-124">네트워크 관리자와 협력 하 여 엔터프라이즈의 네트워크 지역을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-124">Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="25e7e-125">각 네트워크 영역의 연결 된 중앙 사이트를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-125">Identify each network region’s associated central site.</span></span> <span data-ttu-id="25e7e-126">중앙 사이트는 하나 이상의 프런트 엔드 서버를 포함 하며, 네트워크 지역의 WAN 연결을 통해 전달 되는 모든 미디어 트래픽에 대해 CAC를 관리 하는 Lync Server 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-126">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="25e7e-127">**세 개의 네트워크 지역으로 구분 된 엔터프라이즈 네트워크 예제**</span><span class="sxs-lookup"><span data-stu-id="25e7e-127">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="25e7e-128">네트워크 ![영역 3 개를 사용 하는 네트워크 토폴로지 예제]네트워크(images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "영역이 3 개 있는 네트워크 토폴로지 예")</span><span class="sxs-lookup"><span data-stu-id="25e7e-128">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="25e7e-129">MPLS (멀티 프로토콜 레이블 전환) 네트워크는 각 지리적 위치에 해당 하는 네트워크 사이트가 있는 네트워크 영역으로 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-129">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="25e7e-130">자세한 내용은 계획 설명서의 "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Lync Server 2013를 사용 하 여 MPLS 네트워크의 허용 제어에 전화 걸기</A>" 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25e7e-130">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="25e7e-131">앞의 예제 네트워크 토폴로지에는 세 개의 네트워크 영역이 있으며, 각 영역에는 CAC를 관리 하는 Lync Server 중앙 사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-131">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="25e7e-132">네트워크 지역에 적절 한 중앙 사이트가 지역 주변에서 선택 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-132">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="25e7e-133">네트워크 영역 내에서 미디어 소통량이 가장 오래 지속 되므로 지리적 위치에의 한 소유권은 다른 중앙 사이트를 사용할 수 없게 되는 경우에도 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-133">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="25e7e-134">이 예제에서 시카고 라는 Lync Server 배포는 북미 지역에 대 한 중앙 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-134">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="25e7e-135">북미 지역에 있는 모든 Lync 사용자는 시카고 배포의 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-135">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="25e7e-136">다음 표에는 세 가지 네트워크 지역 모두에 대 한 중앙 사이트가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-136">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="25e7e-137">네트워크 지역 및 연결 된 중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="25e7e-137">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="25e7e-138">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="25e7e-138">Network Region</span></span></th>
    <th><span data-ttu-id="25e7e-139">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="25e7e-139">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="25e7e-140">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-140">North America</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-141">시카고</span><span class="sxs-lookup"><span data-stu-id="25e7e-141">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="25e7e-142">슈팅</span><span class="sxs-lookup"><span data-stu-id="25e7e-142">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-143">시흥시</span><span class="sxs-lookup"><span data-stu-id="25e7e-143">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="25e7e-144">APAC</span><span class="sxs-lookup"><span data-stu-id="25e7e-144">APAC</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-145">베이징</span><span class="sxs-lookup"><span data-stu-id="25e7e-145">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="25e7e-146">Lync Server 토폴로지에 따라 동일한 중앙 사이트를 여러 네트워크 지역에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-146">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="25e7e-147">각 네트워크 지역에 대해 WAN 연결이 대역폭이 제한 되지 않은 모든 네트워크 사이트 (사무실 또는 장소)를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-147">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained.</span></span> <span data-ttu-id="25e7e-148">이러한 사이트는 대역폭이 제한 되지 않으므로 CAC 대역폭 정책을 적용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-148">Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="25e7e-149">다음 표에 나와 있는 예제에서 세 개의 네트워크 사이트에는 뉴욕, 시카고, 디트로이트 대역폭 제한 WAN 연결이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-149">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="25e7e-150">WAN 대역폭에 의해 제한 되지 않는 네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="25e7e-150">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="25e7e-151">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="25e7e-151">Network Site</span></span></th>
    <th><span data-ttu-id="25e7e-152">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="25e7e-152">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="25e7e-153">뉴욕</span><span class="sxs-lookup"><span data-stu-id="25e7e-153">New York</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-154">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-154">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="25e7e-155">시카고</span><span class="sxs-lookup"><span data-stu-id="25e7e-155">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-156">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-156">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="25e7e-157">디트로이트</span><span class="sxs-lookup"><span data-stu-id="25e7e-157">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-158">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-158">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="25e7e-159">각 네트워크 영역에 대해 대역폭 제한 WAN 링크를 통해 네트워크 지역에 연결 하는 모든 네트워크 사이트를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-159">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="25e7e-160">오디오 및 비디오 품질을 보장 하기 위해 이러한 대역폭 제한 네트워크 사이트에는 네트워크 지역으로 또는이 지에서 미디어 (음성 또는 비디오) 트래픽을 제한 하는 Wan 모니터링 및 CAC 대역폭 정책이 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-160">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="25e7e-161">다음 표에 표시 된 예제에는 WAN 대역폭 (포틀랜드, Reno 및 Albuquerque에 의해 제한 되는 세 가지 네트워크 사이트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-161">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="25e7e-162">WAN 대역폭에 의해 제한 되는 네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="25e7e-162">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="25e7e-163">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="25e7e-163">Network Site</span></span></th>
    <th><span data-ttu-id="25e7e-164">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="25e7e-164">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="25e7e-165">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="25e7e-165">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-166">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-166">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="25e7e-167">Reno</span><span class="sxs-lookup"><span data-stu-id="25e7e-167">Reno</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-168">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-168">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="25e7e-169">지사</span><span class="sxs-lookup"><span data-stu-id="25e7e-169">Portland</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-170">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-170">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="25e7e-171">**CAC 네트워크 지역 북미, 대역폭 (시카고, 뉴욕, 디트로이트) 및 WAN 대역폭 (포틀랜드, Reno 및 Albuquerque)에 의해 제한 되는 세 개의 네트워크 사이트를 포함 하는 세 개의 네트워크 사이트**</span><span class="sxs-lookup"><span data-stu-id="25e7e-171">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="25e7e-172">Wan 대역폭으로 제한 된 ![네트워크 사이트 예]wan(images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "대역폭으로 제한 된 네트워크 사이트 예")</span><span class="sxs-lookup"><span data-stu-id="25e7e-172">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="25e7e-173">각 대역폭 제한 WAN 링크에 대해 다음을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-173">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="25e7e-174">모든 동시 오디오 세션에 대해 설정 하려는 전체 대역폭 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-174">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="25e7e-175">새 오디오 세션으로 인해이 한도가 초과 되는 경우 Lync Server에서 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-175">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="25e7e-176">각 개별 오디오 세션에 대해 설정 하려는 대역폭 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-176">Bandwidth limit that you want to set for each individual audio session.</span></span> <span data-ttu-id="25e7e-177">기본 CAC 대역폭 제한은 175 kbps 이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-177">The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="25e7e-178">모든 동시 비디오 세션에 대해 설정 하려는 전체 대역폭 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-178">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="25e7e-179">새 비디오 세션으로 인해이 한도가 초과 되는 경우 Lync Server에서 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-179">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="25e7e-180">각 개별 비디오 세션에 대해 설정 하려는 대역폭 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-180">Bandwidth limit that you want to set for each individual video session.</span></span> <span data-ttu-id="25e7e-181">기본 CAC 대역폭 제한은 700 kbps 이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-181">The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="25e7e-182">WAN 대역폭 제약 조건 정보가 포함 되는 네트워크 사이트 (대역폭 (kbps))</span><span class="sxs-lookup"><span data-stu-id="25e7e-182">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="25e7e-183">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="25e7e-183">Network Site</span></span></th>
    <th><span data-ttu-id="25e7e-184">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="25e7e-184">Network Region</span></span></th>
    <th><span data-ttu-id="25e7e-185">BW 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-185">BW Limit</span></span></th>
    <th><span data-ttu-id="25e7e-186">오디오 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-186">Audio Limit</span></span></th>
    <th><span data-ttu-id="25e7e-187">오디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-187">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="25e7e-188">비디오 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-188">Video Limit</span></span></th>
    <th><span data-ttu-id="25e7e-189">비디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-189">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="25e7e-190">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="25e7e-190">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-191">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-191">North America</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-192">5,000</span><span class="sxs-lookup"><span data-stu-id="25e7e-192">5,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-193">2000</span><span class="sxs-lookup"><span data-stu-id="25e7e-193">2,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-194">175</span><span class="sxs-lookup"><span data-stu-id="25e7e-194">175</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-195">1400</span><span class="sxs-lookup"><span data-stu-id="25e7e-195">1,400</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-196">700</span><span class="sxs-lookup"><span data-stu-id="25e7e-196">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="25e7e-197">Reno</span><span class="sxs-lookup"><span data-stu-id="25e7e-197">Reno</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-198">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-198">North America</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-199">1만</span><span class="sxs-lookup"><span data-stu-id="25e7e-199">10,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-200">4000</span><span class="sxs-lookup"><span data-stu-id="25e7e-200">4,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-201">175</span><span class="sxs-lookup"><span data-stu-id="25e7e-201">175</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-202">2800</span><span class="sxs-lookup"><span data-stu-id="25e7e-202">2,800</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-203">700</span><span class="sxs-lookup"><span data-stu-id="25e7e-203">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="25e7e-204">지사</span><span class="sxs-lookup"><span data-stu-id="25e7e-204">Portland</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-205">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-205">North America</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-206">5,000</span><span class="sxs-lookup"><span data-stu-id="25e7e-206">5,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-207">4000</span><span class="sxs-lookup"><span data-stu-id="25e7e-207">4,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-208">175</span><span class="sxs-lookup"><span data-stu-id="25e7e-208">175</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-209">2800</span><span class="sxs-lookup"><span data-stu-id="25e7e-209">2,800</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-210">700</span><span class="sxs-lookup"><span data-stu-id="25e7e-210">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="25e7e-211">뉴욕</span><span class="sxs-lookup"><span data-stu-id="25e7e-211">New York</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-212">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-212">North America</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-213">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-213">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-214">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-215">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-216">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-217">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-217">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="25e7e-218">시카고</span><span class="sxs-lookup"><span data-stu-id="25e7e-218">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-219">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-219">North America</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-220">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-220">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-221">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-222">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-223">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-224">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-224">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="25e7e-225">디트로이트</span><span class="sxs-lookup"><span data-stu-id="25e7e-225">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-226">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-226">North America</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-227">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-227">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-228">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-229">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-230">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-231">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-231">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="25e7e-232">네트워크의 모든 서브넷에 대해 연결 된 네트워크 사이트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-232">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="25e7e-233">네트워크 사이트에 대역폭이 제한 되어 있지 않은 경우에도 네트워크의 모든 서브넷은 네트워크 사이트와 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-233">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained.</span></span> <span data-ttu-id="25e7e-234">이것은 call 허용 제어가 서브넷 정보를 사용 하 여 종점이 있는 네트워크 사이트를 결정 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-234">This is because call admission control uses subnet information to determine at which network site an endpoint is located.</span></span> <span data-ttu-id="25e7e-235">세션에서 두 당사자의 위치가 결정 되 면 통화 허용 제어에서 전화를 걸 충분 한 대역폭이 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-235">When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call.</span></span> <span data-ttu-id="25e7e-236">대역폭 한도가 없는 링크를 통해 세션이 설정 되 면 경고가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-236">When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="25e7e-237">오디오/비디오에 지 서버를 배포 하는 경우 각 Edge 서버의 공용 IP 주소는 Edge 서버가 배포 된 네트워크 사이트와 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-237">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="25e7e-238">A/V Edge 서버의 각 공용 IP 주소는 서브넷 마스크가 32 인 서브넷으로 네트워크 구성 설정에 추가 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-238">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="25e7e-239">예를 들어, 시카고에/V Edge 서버를 배포 하는 경우 해당 서버의 각 외부 IP 주소에 대해 서브넷 마스크가 32 인 서브넷을 만들고 네트워크 사이트 시카고를 해당 서브넷과 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-239">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="25e7e-240">공용 IP 주소에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">외부 A/V 방화벽 및 Lync Server 2013의 포트 요구 사항 결정</A> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25e7e-240">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="25e7e-241">네트워크에는 있지만 서브넷에 연결 되지 않았거나 IP 주소가 포함 된 서브넷이 네트워크 사이트와 연결 되어 있지 않은 경우 KHI (키 상태 표시기) 경고가 발생 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-241">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="25e7e-242">이 알림은 8 시간 내에 두 번 이상 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-242">This alert will not be raised more than once within an 8 hour period.</span></span> <span data-ttu-id="25e7e-243">관련 경고 정보 및 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-243">The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="25e7e-244"><STRONG>원본:</STRONG> CS (대역폭 정책 서비스) (Core)</span><span class="sxs-lookup"><span data-stu-id="25e7e-244"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="25e7e-245"><STRONG>이벤트 번호:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="25e7e-245"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="25e7e-246"><STRONG>수준:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="25e7e-246"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="25e7e-247"><STRONG>설명:</STRONG> 다음 IP 주소의 서브넷: &lt;ip 주소&gt; 목록이 구성 되지 않았거나 서브넷이 네트워크 사이트에 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-247"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="25e7e-248"><STRONG>원인:</STRONG> 해당 IP 주소에 대 한 서브넷이 네트워크 구성 설정에 없거나 서브넷이 네트워크 사이트에 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-248"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="25e7e-249"><STRONG>해결 방법:</STRONG> 앞의 IP 주소 목록에 해당 하는 서브넷을 네트워크 구성 설정에 추가 하 고 모든 서브넷을 네트워크 사이트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-249"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="25e7e-250">예를 들어 알림의 IP 주소 목록이 10.121.248.226 및 10.121.249.20를 지정 하는 경우 이러한 IP 주소가 서브넷과 연결 되어 있지 않거나 연결 된 서브넷이 네트워크 사이트에 속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-250">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site.</span></span> <span data-ttu-id="25e7e-251">10.121.248.0/24 및 10.121.249.0/24가 이러한 주소에 해당 하는 서브넷 이면 다음과 같이이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-251">If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="25e7e-252">IP 주소 10.121.248.226이 10.121.248.0/24 서브넷 및 IP 주소 10.121.249.20와 연결 되어 있는지 확인 하 고 10.121.249.0/24 서브넷과 연결 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-252">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="25e7e-253">10.121.248.0/24 및 10.121.249.0/24 서브넷이 각각 네트워크 사이트와 연결 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-253">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="25e7e-254">네트워크 사이트 및 관련 서브넷 (kbps (대역폭))</span><span class="sxs-lookup"><span data-stu-id="25e7e-254">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="25e7e-255">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="25e7e-255">Network Site</span></span></th>
    <th><span data-ttu-id="25e7e-256">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="25e7e-256">Network Region</span></span></th>
    <th><span data-ttu-id="25e7e-257">BW 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-257">BW Limit</span></span></th>
    <th><span data-ttu-id="25e7e-258">오디오 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-258">Audio Limit</span></span></th>
    <th><span data-ttu-id="25e7e-259">오디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-259">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="25e7e-260">비디오 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-260">Video Limit</span></span></th>
    <th><span data-ttu-id="25e7e-261">비디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-261">Video Session Limit</span></span></th>
    <th><span data-ttu-id="25e7e-262">네트</span><span class="sxs-lookup"><span data-stu-id="25e7e-262">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="25e7e-263">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="25e7e-263">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-264">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-264">North America</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-265">5,000</span><span class="sxs-lookup"><span data-stu-id="25e7e-265">5,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-266">2000</span><span class="sxs-lookup"><span data-stu-id="25e7e-266">2,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-267">175</span><span class="sxs-lookup"><span data-stu-id="25e7e-267">175</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-268">1400</span><span class="sxs-lookup"><span data-stu-id="25e7e-268">1,400</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-269">700</span><span class="sxs-lookup"><span data-stu-id="25e7e-269">700</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="25e7e-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="25e7e-271">Reno</span><span class="sxs-lookup"><span data-stu-id="25e7e-271">Reno</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-272">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-272">North America</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-273">1만</span><span class="sxs-lookup"><span data-stu-id="25e7e-273">10,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-274">4000</span><span class="sxs-lookup"><span data-stu-id="25e7e-274">4,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-275">175</span><span class="sxs-lookup"><span data-stu-id="25e7e-275">175</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-276">2800</span><span class="sxs-lookup"><span data-stu-id="25e7e-276">2,800</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-277">700</span><span class="sxs-lookup"><span data-stu-id="25e7e-277">700</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-278">157.57.210.0/23, 172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="25e7e-278">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="25e7e-279">지사</span><span class="sxs-lookup"><span data-stu-id="25e7e-279">Portland</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-280">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-280">North America</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-281">5,000</span><span class="sxs-lookup"><span data-stu-id="25e7e-281">5,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-282">4000</span><span class="sxs-lookup"><span data-stu-id="25e7e-282">4,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-283">175</span><span class="sxs-lookup"><span data-stu-id="25e7e-283">175</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-284">2800</span><span class="sxs-lookup"><span data-stu-id="25e7e-284">2,800</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-285">700</span><span class="sxs-lookup"><span data-stu-id="25e7e-285">700</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="25e7e-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="25e7e-287">뉴욕</span><span class="sxs-lookup"><span data-stu-id="25e7e-287">New York</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-288">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-288">North America</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-289">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-289">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-290">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-291">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-292">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-293">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="25e7e-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="25e7e-295">시카고</span><span class="sxs-lookup"><span data-stu-id="25e7e-295">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-296">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-296">North America</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-297">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-297">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-298">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-299">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-300">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-301">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-302">157.57.211.0/23, 172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="25e7e-302">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="25e7e-303">디트로이트</span><span class="sxs-lookup"><span data-stu-id="25e7e-303">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-304">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-304">North America</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-305">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-305">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-306">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-307">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-308">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-309">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="25e7e-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="25e7e-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="25e7e-311">Lync Server 호출 허용 제어에서 네트워크 지역 간 연결을 *지역 링크*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-311">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="25e7e-312">각 지역 링크에 대해 다음을 결정 합니다. 네트워크 사이트의 경우와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-312">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="25e7e-313">모든 동시 오디오 세션에 대해 설정 하려는 전체 대역폭 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-313">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="25e7e-314">새 오디오 세션으로 인해이 한도가 초과 되는 경우 Lync Server에서 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-314">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="25e7e-315">각 개별 오디오 세션에 대해 설정 하려는 대역폭 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-315">Bandwidth limit that you want to set for each individual audio session.</span></span> <span data-ttu-id="25e7e-316">기본 CAC 대역폭 제한은 175 kbps 이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-316">The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="25e7e-317">모든 동시 비디오 세션에 대해 설정 하려는 전체 대역폭 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-317">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="25e7e-318">새 비디오 세션으로 인해이 한도가 초과 되는 경우 Lync Server에서 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-318">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="25e7e-319">각 개별 비디오 세션에 대해 설정 하려는 대역폭 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-319">Bandwidth limit that you want to set for each individual video session.</span></span> <span data-ttu-id="25e7e-320">기본 CAC 대역폭 제한은 700 kbps 이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-320">The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="25e7e-321">**연결 된 대역폭 한도가 있는 네트워크 지역 링크**</span><span class="sxs-lookup"><span data-stu-id="25e7e-321">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="25e7e-322">![세 지역]간의(images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "제한 예")</span><span class="sxs-lookup"><span data-stu-id="25e7e-322">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="25e7e-323">지역 링크 대역폭 정보 (대역폭 (kbps))</span><span class="sxs-lookup"><span data-stu-id="25e7e-323">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="25e7e-324">지역 링크 이름</span><span class="sxs-lookup"><span data-stu-id="25e7e-324">Region Link Name</span></span></th>
    <th><span data-ttu-id="25e7e-325">첫 번째 지역</span><span class="sxs-lookup"><span data-stu-id="25e7e-325">First Region</span></span></th>
    <th><span data-ttu-id="25e7e-326">두 번째 지역</span><span class="sxs-lookup"><span data-stu-id="25e7e-326">Second Region</span></span></th>
    <th><span data-ttu-id="25e7e-327">BW 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-327">BW Limit</span></span></th>
    <th><span data-ttu-id="25e7e-328">오디오 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-328">Audio Limit</span></span></th>
    <th><span data-ttu-id="25e7e-329">오디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-329">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="25e7e-330">비디오 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-330">Video Limit</span></span></th>
    <th><span data-ttu-id="25e7e-331">비디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-331">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="25e7e-332">NA-EMEA-링크</span><span class="sxs-lookup"><span data-stu-id="25e7e-332">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-333">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-333">North America</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-334">슈팅</span><span class="sxs-lookup"><span data-stu-id="25e7e-334">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-335">5만</span><span class="sxs-lookup"><span data-stu-id="25e7e-335">50,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-336">2만</span><span class="sxs-lookup"><span data-stu-id="25e7e-336">20,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-337">175</span><span class="sxs-lookup"><span data-stu-id="25e7e-337">175</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-338">14000</span><span class="sxs-lookup"><span data-stu-id="25e7e-338">14,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-339">700</span><span class="sxs-lookup"><span data-stu-id="25e7e-339">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="25e7e-340">EMEA-APAC-링크</span><span class="sxs-lookup"><span data-stu-id="25e7e-340">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-341">슈팅</span><span class="sxs-lookup"><span data-stu-id="25e7e-341">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-342">APAC</span><span class="sxs-lookup"><span data-stu-id="25e7e-342">APAC</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-343">25000</span><span class="sxs-lookup"><span data-stu-id="25e7e-343">25,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-344">1만</span><span class="sxs-lookup"><span data-stu-id="25e7e-344">10,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-345">175</span><span class="sxs-lookup"><span data-stu-id="25e7e-345">175</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-346">7000</span><span class="sxs-lookup"><span data-stu-id="25e7e-346">7,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-347">700</span><span class="sxs-lookup"><span data-stu-id="25e7e-347">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="25e7e-348">네트워크 지역의 모든 쌍 간의 경로를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-348">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="25e7e-349">북미와 APAC 지역 간의 경로에는 직접 연결 하는 지역 링크가 없기 때문에 두 개의 링크가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-349">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="25e7e-350">지역 경로</span><span class="sxs-lookup"><span data-stu-id="25e7e-350">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="25e7e-351">지역 경로 이름</span><span class="sxs-lookup"><span data-stu-id="25e7e-351">Region Route Name</span></span></th>
    <th><span data-ttu-id="25e7e-352">첫 번째 지역</span><span class="sxs-lookup"><span data-stu-id="25e7e-352">First Region</span></span></th>
    <th><span data-ttu-id="25e7e-353">두 번째 지역</span><span class="sxs-lookup"><span data-stu-id="25e7e-353">Second Region</span></span></th>
    <th><span data-ttu-id="25e7e-354">지역 링크</span><span class="sxs-lookup"><span data-stu-id="25e7e-354">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="25e7e-355">NA-EMEA-경로</span><span class="sxs-lookup"><span data-stu-id="25e7e-355">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-356">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-356">North America</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-357">슈팅</span><span class="sxs-lookup"><span data-stu-id="25e7e-357">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-358">NA-EMEA-링크</span><span class="sxs-lookup"><span data-stu-id="25e7e-358">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="25e7e-359">EMEA-APAC-경로</span><span class="sxs-lookup"><span data-stu-id="25e7e-359">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-360">슈팅</span><span class="sxs-lookup"><span data-stu-id="25e7e-360">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-361">APAC</span><span class="sxs-lookup"><span data-stu-id="25e7e-361">APAC</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-362">EMEA-APAC-링크</span><span class="sxs-lookup"><span data-stu-id="25e7e-362">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="25e7e-363">NA-APAC-경로</span><span class="sxs-lookup"><span data-stu-id="25e7e-363">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-364">북미</span><span class="sxs-lookup"><span data-stu-id="25e7e-364">North America</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-365">APAC</span><span class="sxs-lookup"><span data-stu-id="25e7e-365">APAC</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-366">NA-EMEA-링크, EMEA-APAC-링크</span><span class="sxs-lookup"><span data-stu-id="25e7e-366">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="25e7e-367">단일 링크 ( *사이트 간* 링크)로 직접 연결 된 모든 네트워크 사이트 쌍에 대해 다음을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-367">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="25e7e-368">모든 동시 오디오 세션에 대해 설정 하려는 전체 대역폭 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-368">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="25e7e-369">새 오디오 세션으로 인해이 한도가 초과 되는 경우 Lync Server에서 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-369">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="25e7e-370">각 개별 오디오 세션에 대해 설정 하려는 대역폭 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-370">Bandwidth limit that you want to set for each individual audio session.</span></span> <span data-ttu-id="25e7e-371">기본 CAC 대역폭 제한은 175 kbps 이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-371">The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="25e7e-372">모든 동시 비디오 세션에 대해 설정 하려는 전체 대역폭 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-372">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="25e7e-373">새 비디오 세션으로 인해이 한도가 초과 되는 경우 Lync Server에서 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-373">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="25e7e-374">각 개별 비디오 세션에 대해 설정 하려는 대역폭 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-374">Bandwidth limit that you want to set for each individual video session.</span></span> <span data-ttu-id="25e7e-375">기본 CAC 대역폭 제한은 700 kbps 이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-375">The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="25e7e-376">**CAC 네트워크 지역 북미 Reno와 Albuquerque 사이의 사이트 간 링크에 대 한 대역폭 용량 및 대역폭 한계를 표시 합니다.**</span><span class="sxs-lookup"><span data-stu-id="25e7e-376">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="25e7e-377">Wan 대역폭의 제약을 받지 않는 네트워크 사이트 ![예](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Wan 대역폭으로 제한 된 네트워크 사이트 예")</span><span class="sxs-lookup"><span data-stu-id="25e7e-377">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="25e7e-378">두 네트워크 사이트 사이의 사이트 간 링크에 대 한 대역폭 정보 (kbps의 대역폭)</span><span class="sxs-lookup"><span data-stu-id="25e7e-378">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="25e7e-379">사이트 간 링크 이름</span><span class="sxs-lookup"><span data-stu-id="25e7e-379">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="25e7e-380">첫 번째 사이트</span><span class="sxs-lookup"><span data-stu-id="25e7e-380">First Site</span></span></th>
    <th><span data-ttu-id="25e7e-381">두 번째 사이트</span><span class="sxs-lookup"><span data-stu-id="25e7e-381">Second Site</span></span></th>
    <th><span data-ttu-id="25e7e-382">BW 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-382">BW Limit</span></span></th>
    <th><span data-ttu-id="25e7e-383">오디오 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-383">Audio Limit</span></span></th>
    <th><span data-ttu-id="25e7e-384">오디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-384">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="25e7e-385">비디오 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-385">Video Limit</span></span></th>
    <th><span data-ttu-id="25e7e-386">비디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="25e7e-386">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="25e7e-387">Reno-Albu-사이트 링크</span><span class="sxs-lookup"><span data-stu-id="25e7e-387">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-388">Reno</span><span class="sxs-lookup"><span data-stu-id="25e7e-388">Reno</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-389">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="25e7e-389">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-390">2만</span><span class="sxs-lookup"><span data-stu-id="25e7e-390">20,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-391">12000</span><span class="sxs-lookup"><span data-stu-id="25e7e-391">12,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-392">175</span><span class="sxs-lookup"><span data-stu-id="25e7e-392">175</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-393">5,000</span><span class="sxs-lookup"><span data-stu-id="25e7e-393">5,000</span></span></p></td>
    <td><p><span data-ttu-id="25e7e-394">700</span><span class="sxs-lookup"><span data-stu-id="25e7e-394">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="25e7e-395">다음 단계</span><span class="sxs-lookup"><span data-stu-id="25e7e-395">Next Steps</span></span>

<span data-ttu-id="25e7e-396">필요한 정보를 수집한 후 Lync Server 관리 셸 또는 Lync Server 제어판을 사용 하 여 CAC 배포를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-396">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="25e7e-397">Lync Server 제어판을 사용 하 여 대부분의 네트워크 구성 작업을 수행할 수 있지만 서브넷 및 사이트 링크를 만들려면 Lync Server 관리 셸을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e7e-397">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="25e7e-398">자세한 내용은 <STRONG>새 CsNetworkSubnet</STRONG> Cmdlet 및 <STRONG>new CsNetworkIntersitePolicy</STRONG> Cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25e7e-398">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

