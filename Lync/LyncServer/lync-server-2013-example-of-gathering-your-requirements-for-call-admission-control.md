---
title: 통화 허용 제어에 대 한 요구 사항 수집 예제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 204339161cf5af83f0d9e393a0a4db981c0e8445
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="a5980-102">예: Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 수집</span><span class="sxs-lookup"><span data-stu-id="a5980-102">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5980-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a5980-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a5980-p101">이 예에서는 CAC(통화 허용 제어)를 계획하고 구현하는 방법을 보여 줍니다. 이 과정은 크게 다음 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-p101">This example shows you how to plan for and implement call admission control (CAC). At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="a5980-106">모든 네트워크 허브 및 백본(*네트워크 지역*이라고 함) 확인</span><span class="sxs-lookup"><span data-stu-id="a5980-106">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="a5980-107">각 네트워크 지역에 대해 CAC를 관리할 Lync Server 중앙 사이트를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-107">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="a5980-108">각 네트워크 지역에 연결된 *네트워크 사이트* 확인 및 정의</span><span class="sxs-lookup"><span data-stu-id="a5980-108">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="a5980-109">WAN에 대 한 연결이 대역폭을 제한 하는 각 네트워크 사이트에 대해 WAN 연결의 대역폭 용량 및 네트워크 관리자가 Lync Server 미디어 트래픽에 대해 설정한 대역폭 제한에 대해 설명 합니다 (해당 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="a5980-109">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="a5980-110">WAN 연결에 대한 대역폭 제한이 없는 사이트는 포함하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-110">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="a5980-111">네트워크의 각 서브넷을 네트워크 사이트와 연결</span><span class="sxs-lookup"><span data-stu-id="a5980-111">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="a5980-112">네트워크 지역 간의 링크 매핑.</span><span class="sxs-lookup"><span data-stu-id="a5980-112">Map the links between the network regions.</span></span> <span data-ttu-id="a5980-113">각 링크에 대해 대역폭 용량 및 네트워크 관리자가 Lync Server 미디어 트래픽에 적용 한 모든 제한을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-113">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="a5980-114">모든 네트워크 지역 쌍 간의 경로 정의</span><span class="sxs-lookup"><span data-stu-id="a5980-114">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="a5980-115">필요한 정보 수집</span><span class="sxs-lookup"><span data-stu-id="a5980-115">Gather the Required Information</span></span>

<span data-ttu-id="a5980-116">통화 허용 제어를 준비하려면 다음 단계에 설명된 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-116">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="a5980-p104">네트워크 지역을 확인합니다. 네트워크 지역은 네트워크 백본 또는 네트워크 허브를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-p104">Identify your network regions. A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="a5980-p105">네트워크 백본 또는 네트워크 허브는 네트워크의 여러 부분을 상호 연결하는 컴퓨터 네트워크 인프라의 일부로서, 서로 다른 LAN 또는 서브넷 간의 정보 교환 경로를 제공합니다. 백본은 소규모 위치에서 지리적으로 넓은 지역에 이르기까지 다양한 네트워크를 함께 묶을 수 있습니다. 따라서 백본의 용량은 일반적으로 백본에 연결된 네트워크의 용량보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-p105">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks, from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="a5980-p106">여기에 설명된 토폴로지에는 북미, EMEA, APAC, 이렇게 세 개의 네트워크 지역이 있습니다. 네트워크 지역은 네트워크 사이트 모음을 포함합니다. 네트워크 관리자와 함께 회사의 네트워크 지역을 정의하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5980-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites. Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="a5980-125">각 네트워크 지역의 연결된 중앙 사이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-125">Identify each network region’s associated central site.</span></span> <span data-ttu-id="a5980-126">중앙 사이트는 하나 이상의 프런트 엔드 서버를 포함 하며, 네트워크 지역의 WAN 연결을 통과 하는 모든 미디어 트래픽에 대해 CAC를 관리 하는 Lync Server 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-126">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="a5980-127">**세 개의 네트워크 지역으로 분할된 엔터프라이즈 네트워크의 예**</span><span class="sxs-lookup"><span data-stu-id="a5980-127">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="a5980-128">![네트워크 지역이 3 개 있는 네트워크 토폴로지 예제](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "네트워크 지역이 3 개 있는 네트워크 토폴로지 예제")</span><span class="sxs-lookup"><span data-stu-id="a5980-128">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a5980-129">MPLS(Multiprotocol Label Switching) 네트워크는 각 지리적 위치에 해당하는 네트워크 사이트가 있는 네트워크 지역으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-129">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="a5980-130">자세한 내용은 계획 설명서에서 "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Lync Server 2013을 사용 하 여 MPLS 네트워크에 대 한 통화 허용 제어</A>" 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5980-130">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="a5980-131">위의 예에서 네트워크 토폴로지에는 각각 CAC를 관리 하는 Lync Server 중앙 사이트가 있는 세 개의 네트워크 지역이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-131">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="a5980-132">네트워크 지역에 적합한 중앙 사이트는 지리적 근접성에 따라 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-132">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="a5980-133">미디어 트래픽은 네트워크 지역 내에서 부하가 가장 크기 때문에 지리적 근접성에 따라 소유권을 할당하면 네트워크 지역이 자동으로 포함되고 다른 중앙 사이트를 사용할 수 없는 경우에도 네트워크 지역이 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-133">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="a5980-134">이 예에서는 시카고 라는 Lync Server 배포가 북미 지역에 대 한 중앙 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-134">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="a5980-135">북미의 모든 Lync 사용자는 시카고 배포의 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-135">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="a5980-136">다음 표에서는 세 개의 네트워크 지역에 대한 중앙 사이트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-136">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="a5980-137">네트워크 지역 및 관련 중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="a5980-137">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="a5980-138">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="a5980-138">Network Region</span></span></th>
    <th><span data-ttu-id="a5980-139">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="a5980-139">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="a5980-140">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-140">North America</span></span></p></td>
    <td><p><span data-ttu-id="a5980-141">지사</span><span class="sxs-lookup"><span data-stu-id="a5980-141">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a5980-142">슈팅</span><span class="sxs-lookup"><span data-stu-id="a5980-142">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="a5980-143">인</span><span class="sxs-lookup"><span data-stu-id="a5980-143">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a5980-144">APAC</span><span class="sxs-lookup"><span data-stu-id="a5980-144">APAC</span></span></p></td>
    <td><p><span data-ttu-id="a5980-145">베이징</span><span class="sxs-lookup"><span data-stu-id="a5980-145">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a5980-146">Lync Server 토폴로지에 따라 동일한 중앙 사이트를 여러 네트워크 지역에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-146">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="a5980-p111">각 네트워크 지역에 대해 WAN 연결에 대역폭 제한이 없는 모든 네트워크 사이트(사무실 또는 위치)를 확인합니다. 이러한 사이트는 대역폭 제한이 없으므로 CAC 대역폭 정책을 적용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-p111">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained. Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="a5980-149">아래 표의 예에서는 WAN 링크에 대한 대역폭 제한이 없는 세 개의 네트워크 사이트(뉴욕, 시카고 및 디트로이트)를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-149">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="a5980-150">WAN 대역폭 제한이 없는 네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="a5980-150">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="a5980-151">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="a5980-151">Network Site</span></span></th>
    <th><span data-ttu-id="a5980-152">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="a5980-152">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="a5980-153">뉴욕</span><span class="sxs-lookup"><span data-stu-id="a5980-153">New York</span></span></p></td>
    <td><p><span data-ttu-id="a5980-154">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-154">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a5980-155">지사</span><span class="sxs-lookup"><span data-stu-id="a5980-155">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="a5980-156">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-156">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a5980-157">디트로이트</span><span class="sxs-lookup"><span data-stu-id="a5980-157">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="a5980-158">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-158">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="a5980-159">각 네트워크 지역에 대해 대역폭이 제한된 WAN 링크를 통해 네트워크 지역에 연결되는 모든 네트워크 사이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-159">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="a5980-160">오디오 및 비디오 품질을 보장하기 위해 대역폭이 제한된 이러한 네트워크 사이트에서는 WAN을 모니터링하고 네트워크 지역에서 들어오고 나가는 미디어(음성 또는 비디오) 트래픽 흐름을 제한하는 CAC 대역폭 정책을 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-160">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="a5980-161">아래 표의 예에서는 WAN 대역폭이 제한된 세 개의 네트워크 사이트(포틀랜드, 리노 및 앨버커키)를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-161">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="a5980-162">WAN 대역폭이 제한된 네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="a5980-162">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="a5980-163">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="a5980-163">Network Site</span></span></th>
    <th><span data-ttu-id="a5980-164">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="a5980-164">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="a5980-165">앨버커키</span><span class="sxs-lookup"><span data-stu-id="a5980-165">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="a5980-166">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-166">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a5980-167">리노</span><span class="sxs-lookup"><span data-stu-id="a5980-167">Reno</span></span></p></td>
    <td><p><span data-ttu-id="a5980-168">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-168">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a5980-169">포틀랜드</span><span class="sxs-lookup"><span data-stu-id="a5980-169">Portland</span></span></p></td>
    <td><p><span data-ttu-id="a5980-170">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-170">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="a5980-171">**대역폭 제한이 없는 세 개의 네트워크 사이트(시카고, 뉴욕 및 디트로이트)와 WAN 대역폭이 제한된 세 개의 네트워크 사이트(포틀랜드, 리노 및 앨버커키)가 포함된 북미 CAC 네트워크 지역**</span><span class="sxs-lookup"><span data-stu-id="a5980-171">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="a5980-172">![WAN 대역폭에 의해 제한 되는 네트워크 사이트 예](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "WAN 대역폭에 의해 제한 되는 네트워크 사이트 예")</span><span class="sxs-lookup"><span data-stu-id="a5980-172">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="a5980-173">대역폭이 제한된 각 WAN 링크에 대해 다음 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-173">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="a5980-174">모든 동시 오디오 세션에 대해 설정할 전체 대역폭 제한.</span><span class="sxs-lookup"><span data-stu-id="a5980-174">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="a5980-175">새 오디오 세션으로 인해이 제한이 초과 되는 경우 Lync Server에서는 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-175">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="a5980-p113">각각의 개별 오디오 세션에 대해 설정할 대역폭 제한. 기본 CAC 대역폭 제한은 175kbps이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-p113">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="a5980-178">모든 동시 비디오 세션에 대해 설정할 전체 대역폭 제한.</span><span class="sxs-lookup"><span data-stu-id="a5980-178">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="a5980-179">새 비디오 세션으로 인해이 제한이 초과 되는 경우 Lync Server에서는 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-179">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="a5980-p115">각각의 개별 비디오 세션에 대해 설정할 대역폭 제한. 기본 CAC 대역폭 제한은 700kbps이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-p115">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="a5980-182">WAN 대역폭 제한 정보가 있는 네트워크 사이트(대역폭 단위: kbps)</span><span class="sxs-lookup"><span data-stu-id="a5980-182">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="a5980-183">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="a5980-183">Network Site</span></span></th>
    <th><span data-ttu-id="a5980-184">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="a5980-184">Network Region</span></span></th>
    <th><span data-ttu-id="a5980-185">대역폭 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-185">BW Limit</span></span></th>
    <th><span data-ttu-id="a5980-186">오디오 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-186">Audio Limit</span></span></th>
    <th><span data-ttu-id="a5980-187">오디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-187">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="a5980-188">비디오 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-188">Video Limit</span></span></th>
    <th><span data-ttu-id="a5980-189">비디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-189">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="a5980-190">앨버커키</span><span class="sxs-lookup"><span data-stu-id="a5980-190">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="a5980-191">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-191">North America</span></span></p></td>
    <td><p><span data-ttu-id="a5980-192">5,000</span><span class="sxs-lookup"><span data-stu-id="a5980-192">5,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-193">2,000</span><span class="sxs-lookup"><span data-stu-id="a5980-193">2,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-194">175</span><span class="sxs-lookup"><span data-stu-id="a5980-194">175</span></span></p></td>
    <td><p><span data-ttu-id="a5980-195">1400</span><span class="sxs-lookup"><span data-stu-id="a5980-195">1,400</span></span></p></td>
    <td><p><span data-ttu-id="a5980-196">700</span><span class="sxs-lookup"><span data-stu-id="a5980-196">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a5980-197">리노</span><span class="sxs-lookup"><span data-stu-id="a5980-197">Reno</span></span></p></td>
    <td><p><span data-ttu-id="a5980-198">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-198">North America</span></span></p></td>
    <td><p><span data-ttu-id="a5980-199">10,000</span><span class="sxs-lookup"><span data-stu-id="a5980-199">10,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-200">4000</span><span class="sxs-lookup"><span data-stu-id="a5980-200">4,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-201">175</span><span class="sxs-lookup"><span data-stu-id="a5980-201">175</span></span></p></td>
    <td><p><span data-ttu-id="a5980-202">2800</span><span class="sxs-lookup"><span data-stu-id="a5980-202">2,800</span></span></p></td>
    <td><p><span data-ttu-id="a5980-203">700</span><span class="sxs-lookup"><span data-stu-id="a5980-203">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a5980-204">포틀랜드</span><span class="sxs-lookup"><span data-stu-id="a5980-204">Portland</span></span></p></td>
    <td><p><span data-ttu-id="a5980-205">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-205">North America</span></span></p></td>
    <td><p><span data-ttu-id="a5980-206">5,000</span><span class="sxs-lookup"><span data-stu-id="a5980-206">5,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-207">4000</span><span class="sxs-lookup"><span data-stu-id="a5980-207">4,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-208">175</span><span class="sxs-lookup"><span data-stu-id="a5980-208">175</span></span></p></td>
    <td><p><span data-ttu-id="a5980-209">2800</span><span class="sxs-lookup"><span data-stu-id="a5980-209">2,800</span></span></p></td>
    <td><p><span data-ttu-id="a5980-210">700</span><span class="sxs-lookup"><span data-stu-id="a5980-210">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a5980-211">뉴욕</span><span class="sxs-lookup"><span data-stu-id="a5980-211">New York</span></span></p></td>
    <td><p><span data-ttu-id="a5980-212">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-212">North America</span></span></p></td>
    <td><p><span data-ttu-id="a5980-213">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-213">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-214">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-215">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-216">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-217">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-217">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a5980-218">지사</span><span class="sxs-lookup"><span data-stu-id="a5980-218">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="a5980-219">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-219">North America</span></span></p></td>
    <td><p><span data-ttu-id="a5980-220">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-220">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-221">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-222">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-223">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-224">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-224">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a5980-225">디트로이트</span><span class="sxs-lookup"><span data-stu-id="a5980-225">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="a5980-226">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-226">North America</span></span></p></td>
    <td><p><span data-ttu-id="a5980-227">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-227">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-228">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-229">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-230">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-231">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-231">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="a5980-232">네트워크의 모든 서브넷에 대해 연결된 네트워크 사이트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-232">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="a5980-p116">네트워크의 모든 서브넷은 네트워크 사이트와 연결되어야 하며, 네트워크 사이트에 대한 대역폭 제한이 없는 경우에도 마찬가지입니다. 이는 통화 허용 제어에서 서브넷 정보를 사용하여 끝점이 있는 네트워크 사이트를 확인하기 때문입니다. 세션에 참가한 두 대상의 위치가 확인되면 통화 허용 제어에서 통화를 연결하기에 충분한 대역폭이 있는지 확인할 수 있습니다. 대역폭 제한이 없는 링크를 통해 세션이 설정된 경우 알림이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-p116">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained. This is because call admission control uses subnet information to determine at which network site an endpoint is located. When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call. When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="a5980-237">오디오/비디오 에지 서버를 배포하는 경우 각 에지 서버의 공용 IP 주소를 해당 에지 서버가 배포된 네트워크 사이트와 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-237">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="a5980-238">A/V 에지 서버의 각 공용 IP 주소는 서브넷 마스크가 32인 서브넷으로 네트워크 구성 설정에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-238">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="a5980-239">예를 들어 시카고에 A/V 에지 서버를 배포하는 경우 이러한 서버의 각 외부 IP 주소에 대해 서브넷 마스크가 32인 서브넷을 만들고 시카고 네트워크 사이트를 해당 서브넷과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-239">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="a5980-240">공용 IP 주소에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">External A/V 방화벽 및 Lync Server 2013에 대 한 포트 요구 사항 결정</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5980-240">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a5980-p118">네트워크에 있지만 서브넷과 연결되지 않은 IP 주소 목록 또는 IP 주소가 포함되어 있지만 네트워크 사이트에 연결되지 않은 서브넷 목록을 지정하는 KHI(Key Health Indicator) 알림이 표시됩니다. 이 알림은 8시간 간격으로 한 번만 발생합니다(해당되는 경우). 관련 알림 정보 및 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-p118">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8 hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="a5980-244"><STRONG>원본:</STRONG> CS 대역폭 정책 서비스 (핵심)</span><span class="sxs-lookup"><span data-stu-id="a5980-244"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="a5980-245"><STRONG>이벤트 번호:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="a5980-245"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="a5980-246"><STRONG>수준:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="a5980-246"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="a5980-247"><STRONG>설명:</STRONG> 다음 IP 주소에 대 한 서브넷: &lt;ip 주소&gt; 목록이 구성 되지 않았거나 서브넷이 네트워크 사이트에 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-247"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="a5980-248"><STRONG>원인:</STRONG> 해당 IP 주소에 대 한 서브넷이 네트워크 구성 설정에서 누락 되었거나 서브넷이 네트워크 사이트에 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-248"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="a5980-249"><STRONG>해결 방법:</STRONG> 위의 IP 주소 목록에 해당 하는 서브넷을 네트워크 구성 설정에 추가 하 고 모든 서브넷을 네트워크 사이트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-249"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="a5980-p119">예를 들어 알림에 표시된 IP 주소 목록이 10.121.248.226 및 10.121.249.20을 나타내는 경우 이러한 IP 주소가 서브넷에 연결되지 않았거나, 이러한 IP 주소가 연결된 서브넷이 네트워크 사이트 속해 있지 않습니다. 10.121.248.0/24 및 10.121.249.0/24가 이러한 주소에 해당하는 서브넷인 경우 다음과 같이 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-p119">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="a5980-252">IP 주소 10.121.248.226이 10.121.248.0/24 서브넷과 연결되고, IP 주소 10.121.249.20이 10.121.249.0/24 서브넷과 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-252">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="a5980-253">10.121.248.0/24 및 10.121.249.0/24 서브넷이 각각 네트워크 사이트와 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-253">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="a5980-254">네트워크 사이트 및 연결된 서브넷(대역폭 단위: kbps)</span><span class="sxs-lookup"><span data-stu-id="a5980-254">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="a5980-255">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="a5980-255">Network Site</span></span></th>
    <th><span data-ttu-id="a5980-256">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="a5980-256">Network Region</span></span></th>
    <th><span data-ttu-id="a5980-257">대역폭 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-257">BW Limit</span></span></th>
    <th><span data-ttu-id="a5980-258">오디오 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-258">Audio Limit</span></span></th>
    <th><span data-ttu-id="a5980-259">오디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-259">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="a5980-260">비디오 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-260">Video Limit</span></span></th>
    <th><span data-ttu-id="a5980-261">비디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-261">Video Session Limit</span></span></th>
    <th><span data-ttu-id="a5980-262">서브넷</span><span class="sxs-lookup"><span data-stu-id="a5980-262">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="a5980-263">앨버커키</span><span class="sxs-lookup"><span data-stu-id="a5980-263">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="a5980-264">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-264">North America</span></span></p></td>
    <td><p><span data-ttu-id="a5980-265">5,000</span><span class="sxs-lookup"><span data-stu-id="a5980-265">5,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-266">2,000</span><span class="sxs-lookup"><span data-stu-id="a5980-266">2,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-267">175</span><span class="sxs-lookup"><span data-stu-id="a5980-267">175</span></span></p></td>
    <td><p><span data-ttu-id="a5980-268">1400</span><span class="sxs-lookup"><span data-stu-id="a5980-268">1,400</span></span></p></td>
    <td><p><span data-ttu-id="a5980-269">700</span><span class="sxs-lookup"><span data-stu-id="a5980-269">700</span></span></p></td>
    <td><p><span data-ttu-id="a5980-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="a5980-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a5980-271">리노</span><span class="sxs-lookup"><span data-stu-id="a5980-271">Reno</span></span></p></td>
    <td><p><span data-ttu-id="a5980-272">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-272">North America</span></span></p></td>
    <td><p><span data-ttu-id="a5980-273">10,000</span><span class="sxs-lookup"><span data-stu-id="a5980-273">10,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-274">4000</span><span class="sxs-lookup"><span data-stu-id="a5980-274">4,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-275">175</span><span class="sxs-lookup"><span data-stu-id="a5980-275">175</span></span></p></td>
    <td><p><span data-ttu-id="a5980-276">2800</span><span class="sxs-lookup"><span data-stu-id="a5980-276">2,800</span></span></p></td>
    <td><p><span data-ttu-id="a5980-277">700</span><span class="sxs-lookup"><span data-stu-id="a5980-277">700</span></span></p></td>
    <td><p><span data-ttu-id="a5980-278">157.57.210.0/23, 172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="a5980-278">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a5980-279">포틀랜드</span><span class="sxs-lookup"><span data-stu-id="a5980-279">Portland</span></span></p></td>
    <td><p><span data-ttu-id="a5980-280">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-280">North America</span></span></p></td>
    <td><p><span data-ttu-id="a5980-281">5,000</span><span class="sxs-lookup"><span data-stu-id="a5980-281">5,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-282">4000</span><span class="sxs-lookup"><span data-stu-id="a5980-282">4,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-283">175</span><span class="sxs-lookup"><span data-stu-id="a5980-283">175</span></span></p></td>
    <td><p><span data-ttu-id="a5980-284">2800</span><span class="sxs-lookup"><span data-stu-id="a5980-284">2,800</span></span></p></td>
    <td><p><span data-ttu-id="a5980-285">700</span><span class="sxs-lookup"><span data-stu-id="a5980-285">700</span></span></p></td>
    <td><p><span data-ttu-id="a5980-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="a5980-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a5980-287">뉴욕</span><span class="sxs-lookup"><span data-stu-id="a5980-287">New York</span></span></p></td>
    <td><p><span data-ttu-id="a5980-288">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-288">North America</span></span></p></td>
    <td><p><span data-ttu-id="a5980-289">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-289">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-290">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-291">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-292">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-293">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="a5980-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a5980-295">지사</span><span class="sxs-lookup"><span data-stu-id="a5980-295">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="a5980-296">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-296">North America</span></span></p></td>
    <td><p><span data-ttu-id="a5980-297">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-297">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-298">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-299">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-300">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-301">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-302">157.57.211.0/23, 172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="a5980-302">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a5980-303">디트로이트</span><span class="sxs-lookup"><span data-stu-id="a5980-303">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="a5980-304">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-304">North America</span></span></p></td>
    <td><p><span data-ttu-id="a5980-305">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-305">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-306">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-307">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-308">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-309">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="a5980-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="a5980-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="a5980-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="a5980-311">Lync Server 통화 허용 제어에서는 네트워크 지역 간의 연결을 *지역 링크*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-311">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="a5980-312">각 지역 링크에 대해 네트워크 사이트와 마찬가지로 다음 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-312">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="a5980-313">모든 동시 오디오 세션에 대해 설정할 전체 대역폭 제한.</span><span class="sxs-lookup"><span data-stu-id="a5980-313">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="a5980-314">새 오디오 세션으로 인해이 제한이 초과 되는 경우 Lync Server에서는 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-314">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="a5980-p122">각각의 개별 오디오 세션에 대해 설정할 대역폭 제한. 기본 CAC 대역폭 제한은 175kbps이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-p122">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="a5980-317">모든 동시 비디오 세션에 대해 설정할 전체 대역폭 제한.</span><span class="sxs-lookup"><span data-stu-id="a5980-317">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="a5980-318">새 비디오 세션으로 인해이 제한이 초과 되는 경우 Lync Server에서는 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-318">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="a5980-p124">각각의 개별 비디오 세션에 대해 설정할 대역폭 제한. 기본 CAC 대역폭 제한은 700kbps이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-p124">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="a5980-321">**연관된 대역폭 제한이 있는 네트워크 지역 링크**</span><span class="sxs-lookup"><span data-stu-id="a5980-321">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="a5980-322">![3 개 지역 간의 제한 예제](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "3 개 지역 간의 제한 예제")</span><span class="sxs-lookup"><span data-stu-id="a5980-322">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="a5980-323">지역 링크 대역폭 정보(대역폭 단위: kbps)</span><span class="sxs-lookup"><span data-stu-id="a5980-323">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="a5980-324">지역 링크 이름</span><span class="sxs-lookup"><span data-stu-id="a5980-324">Region Link Name</span></span></th>
    <th><span data-ttu-id="a5980-325">첫 번째 지역</span><span class="sxs-lookup"><span data-stu-id="a5980-325">First Region</span></span></th>
    <th><span data-ttu-id="a5980-326">두 번째 지역</span><span class="sxs-lookup"><span data-stu-id="a5980-326">Second Region</span></span></th>
    <th><span data-ttu-id="a5980-327">대역폭 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-327">BW Limit</span></span></th>
    <th><span data-ttu-id="a5980-328">오디오 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-328">Audio Limit</span></span></th>
    <th><span data-ttu-id="a5980-329">오디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-329">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="a5980-330">비디오 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-330">Video Limit</span></span></th>
    <th><span data-ttu-id="a5980-331">비디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-331">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="a5980-332">NA-EMEA-링크</span><span class="sxs-lookup"><span data-stu-id="a5980-332">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="a5980-333">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-333">North America</span></span></p></td>
    <td><p><span data-ttu-id="a5980-334">슈팅</span><span class="sxs-lookup"><span data-stu-id="a5980-334">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="a5980-335">50,000</span><span class="sxs-lookup"><span data-stu-id="a5980-335">50,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-336">20,000</span><span class="sxs-lookup"><span data-stu-id="a5980-336">20,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-337">175</span><span class="sxs-lookup"><span data-stu-id="a5980-337">175</span></span></p></td>
    <td><p><span data-ttu-id="a5980-338">14000</span><span class="sxs-lookup"><span data-stu-id="a5980-338">14,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-339">700</span><span class="sxs-lookup"><span data-stu-id="a5980-339">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a5980-340">EMEA-APAC-링크</span><span class="sxs-lookup"><span data-stu-id="a5980-340">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="a5980-341">슈팅</span><span class="sxs-lookup"><span data-stu-id="a5980-341">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="a5980-342">APAC</span><span class="sxs-lookup"><span data-stu-id="a5980-342">APAC</span></span></p></td>
    <td><p><span data-ttu-id="a5980-343">25,000</span><span class="sxs-lookup"><span data-stu-id="a5980-343">25,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-344">10,000</span><span class="sxs-lookup"><span data-stu-id="a5980-344">10,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-345">175</span><span class="sxs-lookup"><span data-stu-id="a5980-345">175</span></span></p></td>
    <td><p><span data-ttu-id="a5980-346">7000</span><span class="sxs-lookup"><span data-stu-id="a5980-346">7,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-347">700</span><span class="sxs-lookup"><span data-stu-id="a5980-347">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="a5980-348">모든 네트워크 지역 쌍 간의 경로 정의</span><span class="sxs-lookup"><span data-stu-id="a5980-348">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a5980-349">북미 지역과 APAC 지역 간의 경로에는 두 지역을 직접 연결하는 지역 링크가 없으므로 두 개의 링크가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-349">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="a5980-350">지역 경로</span><span class="sxs-lookup"><span data-stu-id="a5980-350">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="a5980-351">지역 경로 이름</span><span class="sxs-lookup"><span data-stu-id="a5980-351">Region Route Name</span></span></th>
    <th><span data-ttu-id="a5980-352">첫 번째 지역</span><span class="sxs-lookup"><span data-stu-id="a5980-352">First Region</span></span></th>
    <th><span data-ttu-id="a5980-353">두 번째 지역</span><span class="sxs-lookup"><span data-stu-id="a5980-353">Second Region</span></span></th>
    <th><span data-ttu-id="a5980-354">지역 링크</span><span class="sxs-lookup"><span data-stu-id="a5980-354">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="a5980-355">N-EMEA-ROUTE</span><span class="sxs-lookup"><span data-stu-id="a5980-355">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="a5980-356">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-356">North America</span></span></p></td>
    <td><p><span data-ttu-id="a5980-357">슈팅</span><span class="sxs-lookup"><span data-stu-id="a5980-357">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="a5980-358">NA-EMEA-링크</span><span class="sxs-lookup"><span data-stu-id="a5980-358">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="a5980-359">EMEA-APAC-경로</span><span class="sxs-lookup"><span data-stu-id="a5980-359">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="a5980-360">슈팅</span><span class="sxs-lookup"><span data-stu-id="a5980-360">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="a5980-361">APAC</span><span class="sxs-lookup"><span data-stu-id="a5980-361">APAC</span></span></p></td>
    <td><p><span data-ttu-id="a5980-362">EMEA-APAC-링크</span><span class="sxs-lookup"><span data-stu-id="a5980-362">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="a5980-363">NA-APAC-경로</span><span class="sxs-lookup"><span data-stu-id="a5980-363">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="a5980-364">북미</span><span class="sxs-lookup"><span data-stu-id="a5980-364">North America</span></span></p></td>
    <td><p><span data-ttu-id="a5980-365">APAC</span><span class="sxs-lookup"><span data-stu-id="a5980-365">APAC</span></span></p></td>
    <td><p><span data-ttu-id="a5980-366">NA-EMEA-LINK, EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="a5980-366">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="a5980-367">단일 링크(*사이트 간* 링크라고 함)로 직접 연결되는 모든 네트워크 사이트 쌍에 대해 다음 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-367">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="a5980-368">모든 동시 오디오 세션에 대해 설정할 전체 대역폭 제한.</span><span class="sxs-lookup"><span data-stu-id="a5980-368">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="a5980-369">새 오디오 세션으로 인해이 제한이 초과 되는 경우 Lync Server에서는 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-369">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="a5980-p126">각각의 개별 오디오 세션에 대해 설정할 대역폭 제한. 기본 CAC 대역폭 제한은 175kbps이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-p126">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="a5980-372">모든 동시 비디오 세션에 대해 설정할 전체 대역폭 제한.</span><span class="sxs-lookup"><span data-stu-id="a5980-372">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="a5980-373">새 비디오 세션으로 인해이 제한이 초과 되는 경우 Lync Server에서는 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-373">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="a5980-p128">각각의 개별 비디오 세션에 대해 설정할 대역폭 제한. 기본 CAC 대역폭 제한은 700kbps이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-p128">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="a5980-376">**북미 CAC 네트워크 지역의 리노와 앨버커키 간의 사이트 간 링크에 대한 대역폭 용량 및 대역폭 제한**</span><span class="sxs-lookup"><span data-stu-id="a5980-376">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="a5980-377">![WAN 대역폭이 제한 된 네트워크 사이트 예제](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "WAN 대역폭이 제한 된 네트워크 사이트 예제")</span><span class="sxs-lookup"><span data-stu-id="a5980-377">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="a5980-378">두 네트워크 사이트 간의 사이트 간 링크에 대한 대역폭 정보(대역폭 단위: kbps)</span><span class="sxs-lookup"><span data-stu-id="a5980-378">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="a5980-379">사이트 간 링크 이름</span><span class="sxs-lookup"><span data-stu-id="a5980-379">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="a5980-380">첫 번째 사이트</span><span class="sxs-lookup"><span data-stu-id="a5980-380">First Site</span></span></th>
    <th><span data-ttu-id="a5980-381">두 번째 사이트</span><span class="sxs-lookup"><span data-stu-id="a5980-381">Second Site</span></span></th>
    <th><span data-ttu-id="a5980-382">대역폭 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-382">BW Limit</span></span></th>
    <th><span data-ttu-id="a5980-383">오디오 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-383">Audio Limit</span></span></th>
    <th><span data-ttu-id="a5980-384">오디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-384">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="a5980-385">비디오 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-385">Video Limit</span></span></th>
    <th><span data-ttu-id="a5980-386">비디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="a5980-386">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="a5980-387">리노-Albu-사이트 링크</span><span class="sxs-lookup"><span data-stu-id="a5980-387">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="a5980-388">리노</span><span class="sxs-lookup"><span data-stu-id="a5980-388">Reno</span></span></p></td>
    <td><p><span data-ttu-id="a5980-389">앨버커키</span><span class="sxs-lookup"><span data-stu-id="a5980-389">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="a5980-390">20,000</span><span class="sxs-lookup"><span data-stu-id="a5980-390">20,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-391">12000</span><span class="sxs-lookup"><span data-stu-id="a5980-391">12,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-392">175</span><span class="sxs-lookup"><span data-stu-id="a5980-392">175</span></span></p></td>
    <td><p><span data-ttu-id="a5980-393">5,000</span><span class="sxs-lookup"><span data-stu-id="a5980-393">5,000</span></span></p></td>
    <td><p><span data-ttu-id="a5980-394">700</span><span class="sxs-lookup"><span data-stu-id="a5980-394">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="a5980-395">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a5980-395">Next Steps</span></span>

<span data-ttu-id="a5980-396">필요한 정보를 수집한 후에는 Lync Server 관리 셸 또는 Lync Server 제어판을 사용 하 여 CAC 배포를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-396">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a5980-397">Lync Server 제어판을 사용 하 여 서브넷과 사이트 링크를 만들려면 대부분의 네트워크 구성 작업을 수행할 수 있지만 Lync Server 관리 셸을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5980-397">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="a5980-398">자세한 내용은 <STRONG>새 CsNetworkSubnet</STRONG> Cmdlet 및 <STRONG>remove-csnetworkintersitepolicy</STRONG> Cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5980-398">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

