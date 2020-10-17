---
title: 통화 허용 제어에 대 한 요구 사항 수집 예제
description: 통화 허용 제어에 대 한 요구 사항을 수집 하는 예제입니다.
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
ms.openlocfilehash: 25c0b450070bda62c2610d98cfff8c8cd16ad2af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564944"
---
# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="8719a-103">예: Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 수집</span><span class="sxs-lookup"><span data-stu-id="8719a-103">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8719a-104">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8719a-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8719a-p101">이 예에서는 CAC(통화 허용 제어)를 계획하고 구현하는 방법을 보여 줍니다. 이 과정은 크게 다음 작업으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-p101">This example shows you how to plan for and implement call admission control (CAC). At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="8719a-107">모든 네트워크 허브 및 백본(*네트워크 지역*이라고 함) 확인</span><span class="sxs-lookup"><span data-stu-id="8719a-107">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="8719a-108">각 네트워크 지역에 대해 CAC를 관리할 Lync Server 중앙 사이트를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-108">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="8719a-109">각 네트워크 지역에 연결된 *네트워크 사이트* 확인 및 정의</span><span class="sxs-lookup"><span data-stu-id="8719a-109">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="8719a-110">WAN에 대 한 연결이 대역폭을 제한 하는 각 네트워크 사이트에 대해 WAN 연결의 대역폭 용량 및 네트워크 관리자가 Lync Server 미디어 트래픽에 대해 설정한 대역폭 제한에 대해 설명 합니다 (해당 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="8719a-110">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="8719a-111">WAN 연결에 대한 대역폭 제한이 없는 사이트는 포함하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-111">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="8719a-112">네트워크의 각 서브넷을 네트워크 사이트와 연결</span><span class="sxs-lookup"><span data-stu-id="8719a-112">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="8719a-113">네트워크 지역 간의 링크 매핑.</span><span class="sxs-lookup"><span data-stu-id="8719a-113">Map the links between the network regions.</span></span> <span data-ttu-id="8719a-114">각 링크에 대해 대역폭 용량 및 네트워크 관리자가 Lync Server 미디어 트래픽에 적용 한 모든 제한을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-114">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="8719a-115">모든 네트워크 지역 쌍 간의 경로 정의</span><span class="sxs-lookup"><span data-stu-id="8719a-115">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="8719a-116">필요한 정보 수집</span><span class="sxs-lookup"><span data-stu-id="8719a-116">Gather the Required Information</span></span>

<span data-ttu-id="8719a-117">통화 허용 제어를 준비하려면 다음 단계에 설명된 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-117">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="8719a-p104">네트워크 지역을 확인합니다. 네트워크 지역은 네트워크 백본 또는 네트워크 허브를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-p104">Identify your network regions. A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="8719a-p105">네트워크 백본 또는 네트워크 허브는 네트워크의 여러 부분을 상호 연결하는 컴퓨터 네트워크 인프라의 일부로서, 서로 다른 LAN 또는 서브넷 간의 정보 교환 경로를 제공합니다. 백본은 소규모 위치에서 지리적으로 넓은 지역에 이르기까지 다양한 네트워크를 함께 묶을 수 있습니다. 따라서 백본의 용량은 일반적으로 백본에 연결된 네트워크의 용량보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-p105">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks, from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="8719a-p106">여기에 설명된 토폴로지에는 북미, EMEA, APAC, 이렇게 세 개의 네트워크 지역이 있습니다. 네트워크 지역은 네트워크 사이트 모음을 포함합니다. 네트워크 관리자와 함께 회사의 네트워크 지역을 정의하십시오.</span><span class="sxs-lookup"><span data-stu-id="8719a-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites. Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="8719a-126">각 네트워크 지역의 연결된 중앙 사이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-126">Identify each network region’s associated central site.</span></span> <span data-ttu-id="8719a-127">중앙 사이트는 하나 이상의 프런트 엔드 서버를 포함 하며, 네트워크 지역의 WAN 연결을 통과 하는 모든 미디어 트래픽에 대해 CAC를 관리 하는 Lync Server 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-127">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="8719a-128">**세 개의 네트워크 지역으로 분할된 엔터프라이즈 네트워크의 예**</span><span class="sxs-lookup"><span data-stu-id="8719a-128">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="8719a-129">![네트워크 지역이 3 개 있는 네트워크 토폴로지 예제](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "네트워크 지역이 3 개 있는 네트워크 토폴로지 예제")</span><span class="sxs-lookup"><span data-stu-id="8719a-129">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8719a-130">MPLS(Multiprotocol Label Switching) 네트워크는 각 지리적 위치에 해당하는 네트워크 사이트가 있는 네트워크 지역으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-130">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="8719a-131">자세한 내용은 계획 설명서에서 "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Lync Server 2013을 사용 하 여 MPLS 네트워크에 대 한 통화 허용 제어</A>" 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8719a-131">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="8719a-132">위의 예에서 네트워크 토폴로지에는 각각 CAC를 관리 하는 Lync Server 중앙 사이트가 있는 세 개의 네트워크 지역이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-132">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="8719a-133">네트워크 지역에 적합한 중앙 사이트는 지리적 근접성에 따라 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-133">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="8719a-134">미디어 트래픽은 네트워크 지역 내에서 부하가 가장 크기 때문에 지리적 근접성에 따라 소유권을 할당하면 네트워크 지역이 자동으로 포함되고 다른 중앙 사이트를 사용할 수 없는 경우에도 네트워크 지역이 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-134">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="8719a-135">이 예에서는 시카고 라는 Lync Server 배포가 북미 지역에 대 한 중앙 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-135">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="8719a-136">북미의 모든 Lync 사용자는 시카고 배포의 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-136">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="8719a-137">다음 표에서는 세 개의 네트워크 지역에 대한 중앙 사이트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-137">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="8719a-138">네트워크 지역 및 관련 중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="8719a-138">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="8719a-139">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="8719a-139">Network Region</span></span></th>
    <th><span data-ttu-id="8719a-140">중앙 사이트</span><span class="sxs-lookup"><span data-stu-id="8719a-140">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="8719a-141">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-141">North America</span></span></p></td>
    <td><p><span data-ttu-id="8719a-142">지사</span><span class="sxs-lookup"><span data-stu-id="8719a-142">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="8719a-143">슈팅</span><span class="sxs-lookup"><span data-stu-id="8719a-143">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="8719a-144">인</span><span class="sxs-lookup"><span data-stu-id="8719a-144">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="8719a-145">APAC</span><span class="sxs-lookup"><span data-stu-id="8719a-145">APAC</span></span></p></td>
    <td><p><span data-ttu-id="8719a-146">베이징</span><span class="sxs-lookup"><span data-stu-id="8719a-146">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8719a-147">Lync Server 토폴로지에 따라 동일한 중앙 사이트를 여러 네트워크 지역에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-147">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="8719a-p111">각 네트워크 지역에 대해 WAN 연결에 대역폭 제한이 없는 모든 네트워크 사이트(사무실 또는 위치)를 확인합니다. 이러한 사이트는 대역폭 제한이 없으므로 CAC 대역폭 정책을 적용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-p111">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained. Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="8719a-150">아래 표의 예에서는 WAN 링크에 대한 대역폭 제한이 없는 세 개의 네트워크 사이트(뉴욕, 시카고 및 디트로이트)를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-150">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="8719a-151">WAN 대역폭 제한이 없는 네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="8719a-151">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="8719a-152">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="8719a-152">Network Site</span></span></th>
    <th><span data-ttu-id="8719a-153">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="8719a-153">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="8719a-154">뉴욕</span><span class="sxs-lookup"><span data-stu-id="8719a-154">New York</span></span></p></td>
    <td><p><span data-ttu-id="8719a-155">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-155">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="8719a-156">지사</span><span class="sxs-lookup"><span data-stu-id="8719a-156">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="8719a-157">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-157">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="8719a-158">디트로이트</span><span class="sxs-lookup"><span data-stu-id="8719a-158">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="8719a-159">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-159">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="8719a-160">각 네트워크 지역에 대해 대역폭이 제한된 WAN 링크를 통해 네트워크 지역에 연결되는 모든 네트워크 사이트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-160">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="8719a-161">오디오 및 비디오 품질을 보장하기 위해 대역폭이 제한된 이러한 네트워크 사이트에서는 WAN을 모니터링하고 네트워크 지역에서 들어오고 나가는 미디어(음성 또는 비디오) 트래픽 흐름을 제한하는 CAC 대역폭 정책을 적용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-161">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="8719a-162">아래 표의 예에서는 WAN 대역폭이 제한된 세 개의 네트워크 사이트(포틀랜드, 리노 및 앨버커키)를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-162">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="8719a-163">WAN 대역폭이 제한된 네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="8719a-163">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="8719a-164">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="8719a-164">Network Site</span></span></th>
    <th><span data-ttu-id="8719a-165">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="8719a-165">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="8719a-166">앨버커키</span><span class="sxs-lookup"><span data-stu-id="8719a-166">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="8719a-167">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-167">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="8719a-168">리노</span><span class="sxs-lookup"><span data-stu-id="8719a-168">Reno</span></span></p></td>
    <td><p><span data-ttu-id="8719a-169">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-169">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="8719a-170">포틀랜드</span><span class="sxs-lookup"><span data-stu-id="8719a-170">Portland</span></span></p></td>
    <td><p><span data-ttu-id="8719a-171">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-171">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="8719a-172">**대역폭 제한이 없는 세 개의 네트워크 사이트(시카고, 뉴욕 및 디트로이트)와 WAN 대역폭이 제한된 세 개의 네트워크 사이트(포틀랜드, 리노 및 앨버커키)가 포함된 북미 CAC 네트워크 지역**</span><span class="sxs-lookup"><span data-stu-id="8719a-172">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="8719a-173">![WAN 대역폭에 의해 제한 되는 네트워크 사이트 예](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "WAN 대역폭에 의해 제한 되는 네트워크 사이트 예")</span><span class="sxs-lookup"><span data-stu-id="8719a-173">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="8719a-174">대역폭이 제한된 각 WAN 링크에 대해 다음 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-174">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="8719a-175">모든 동시 오디오 세션에 대해 설정할 전체 대역폭 제한.</span><span class="sxs-lookup"><span data-stu-id="8719a-175">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="8719a-176">새 오디오 세션으로 인해이 제한이 초과 되는 경우 Lync Server에서는 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-176">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="8719a-p113">각각의 개별 오디오 세션에 대해 설정할 대역폭 제한. 기본 CAC 대역폭 제한은 175kbps이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-p113">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="8719a-179">모든 동시 비디오 세션에 대해 설정할 전체 대역폭 제한.</span><span class="sxs-lookup"><span data-stu-id="8719a-179">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="8719a-180">새 비디오 세션으로 인해이 제한이 초과 되는 경우 Lync Server에서는 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-180">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="8719a-p115">각각의 개별 비디오 세션에 대해 설정할 대역폭 제한. 기본 CAC 대역폭 제한은 700kbps이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-p115">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="8719a-183">WAN 대역폭 제한 정보가 있는 네트워크 사이트(대역폭 단위: kbps)</span><span class="sxs-lookup"><span data-stu-id="8719a-183">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="8719a-184">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="8719a-184">Network Site</span></span></th>
    <th><span data-ttu-id="8719a-185">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="8719a-185">Network Region</span></span></th>
    <th><span data-ttu-id="8719a-186">대역폭 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-186">BW Limit</span></span></th>
    <th><span data-ttu-id="8719a-187">오디오 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-187">Audio Limit</span></span></th>
    <th><span data-ttu-id="8719a-188">오디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-188">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="8719a-189">비디오 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-189">Video Limit</span></span></th>
    <th><span data-ttu-id="8719a-190">비디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-190">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="8719a-191">앨버커키</span><span class="sxs-lookup"><span data-stu-id="8719a-191">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="8719a-192">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-192">North America</span></span></p></td>
    <td><p><span data-ttu-id="8719a-193">5,000</span><span class="sxs-lookup"><span data-stu-id="8719a-193">5,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-194">2,000</span><span class="sxs-lookup"><span data-stu-id="8719a-194">2,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-195">175</span><span class="sxs-lookup"><span data-stu-id="8719a-195">175</span></span></p></td>
    <td><p><span data-ttu-id="8719a-196">1400</span><span class="sxs-lookup"><span data-stu-id="8719a-196">1,400</span></span></p></td>
    <td><p><span data-ttu-id="8719a-197">700</span><span class="sxs-lookup"><span data-stu-id="8719a-197">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="8719a-198">리노</span><span class="sxs-lookup"><span data-stu-id="8719a-198">Reno</span></span></p></td>
    <td><p><span data-ttu-id="8719a-199">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-199">North America</span></span></p></td>
    <td><p><span data-ttu-id="8719a-200">10,000</span><span class="sxs-lookup"><span data-stu-id="8719a-200">10,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-201">4000</span><span class="sxs-lookup"><span data-stu-id="8719a-201">4,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-202">175</span><span class="sxs-lookup"><span data-stu-id="8719a-202">175</span></span></p></td>
    <td><p><span data-ttu-id="8719a-203">2800</span><span class="sxs-lookup"><span data-stu-id="8719a-203">2,800</span></span></p></td>
    <td><p><span data-ttu-id="8719a-204">700</span><span class="sxs-lookup"><span data-stu-id="8719a-204">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="8719a-205">포틀랜드</span><span class="sxs-lookup"><span data-stu-id="8719a-205">Portland</span></span></p></td>
    <td><p><span data-ttu-id="8719a-206">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-206">North America</span></span></p></td>
    <td><p><span data-ttu-id="8719a-207">5,000</span><span class="sxs-lookup"><span data-stu-id="8719a-207">5,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-208">4000</span><span class="sxs-lookup"><span data-stu-id="8719a-208">4,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-209">175</span><span class="sxs-lookup"><span data-stu-id="8719a-209">175</span></span></p></td>
    <td><p><span data-ttu-id="8719a-210">2800</span><span class="sxs-lookup"><span data-stu-id="8719a-210">2,800</span></span></p></td>
    <td><p><span data-ttu-id="8719a-211">700</span><span class="sxs-lookup"><span data-stu-id="8719a-211">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="8719a-212">뉴욕</span><span class="sxs-lookup"><span data-stu-id="8719a-212">New York</span></span></p></td>
    <td><p><span data-ttu-id="8719a-213">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-213">North America</span></span></p></td>
    <td><p><span data-ttu-id="8719a-214">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-215">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-216">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-217">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-217">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-218">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-218">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="8719a-219">지사</span><span class="sxs-lookup"><span data-stu-id="8719a-219">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="8719a-220">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-220">North America</span></span></p></td>
    <td><p><span data-ttu-id="8719a-221">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-222">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-223">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-224">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-224">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-225">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-225">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="8719a-226">디트로이트</span><span class="sxs-lookup"><span data-stu-id="8719a-226">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="8719a-227">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-227">North America</span></span></p></td>
    <td><p><span data-ttu-id="8719a-228">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-229">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-230">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-231">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-231">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-232">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-232">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="8719a-233">네트워크의 모든 서브넷에 대해 연결된 네트워크 사이트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-233">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="8719a-p116">네트워크의 모든 서브넷은 네트워크 사이트와 연결되어야 하며, 네트워크 사이트에 대한 대역폭 제한이 없는 경우에도 마찬가지입니다. 이는 통화 허용 제어에서 서브넷 정보를 사용하여 끝점이 있는 네트워크 사이트를 확인하기 때문입니다. 세션에 참가한 두 대상의 위치가 확인되면 통화 허용 제어에서 통화를 연결하기에 충분한 대역폭이 있는지 확인할 수 있습니다. 대역폭 제한이 없는 링크를 통해 세션이 설정된 경우 알림이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-p116">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained. This is because call admission control uses subnet information to determine at which network site an endpoint is located. When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call. When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="8719a-238">오디오/비디오 에지 서버를 배포하는 경우 각 에지 서버의 공용 IP 주소를 해당 에지 서버가 배포된 네트워크 사이트와 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-238">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="8719a-239">A/V 에지 서버의 각 공용 IP 주소는 서브넷 마스크가 32인 서브넷으로 네트워크 구성 설정에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-239">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="8719a-240">예를 들어 시카고에 A/V 에지 서버를 배포하는 경우 이러한 서버의 각 외부 IP 주소에 대해 서브넷 마스크가 32인 서브넷을 만들고 시카고 네트워크 사이트를 해당 서브넷과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-240">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="8719a-241">공용 IP 주소에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">External A/V 방화벽 및 Lync Server 2013에 대 한 포트 요구 사항 결정</A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8719a-241">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8719a-p118">네트워크에 있지만 서브넷과 연결되지 않은 IP 주소 목록 또는 IP 주소가 포함되어 있지만 네트워크 사이트에 연결되지 않은 서브넷 목록을 지정하는 KHI(Key Health Indicator) 알림이 표시됩니다. 이 알림은 8시간 간격으로 한 번만 발생합니다(해당되는 경우). 관련 알림 정보 및 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-p118">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8 hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="8719a-245"><STRONG>원본:</STRONG> CS 대역폭 정책 서비스 (핵심)</span><span class="sxs-lookup"><span data-stu-id="8719a-245"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="8719a-246"><STRONG>이벤트 번호:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="8719a-246"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="8719a-247"><STRONG>수준:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="8719a-247"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="8719a-248"><STRONG>설명:</STRONG> 다음 IP 주소에 대 한 서브넷: &lt; Ip 주소 목록이 &gt; 구성 되지 않았거나 서브넷이 네트워크 사이트에 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-248"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="8719a-249"><STRONG>원인:</STRONG> 해당 IP 주소에 대 한 서브넷이 네트워크 구성 설정에서 누락 되었거나 서브넷이 네트워크 사이트에 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-249"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="8719a-250"><STRONG>해결 방법:</STRONG> 위의 IP 주소 목록에 해당 하는 서브넷을 네트워크 구성 설정에 추가 하 고 모든 서브넷을 네트워크 사이트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-250"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="8719a-p119">예를 들어 알림에 표시된 IP 주소 목록이 10.121.248.226 및 10.121.249.20을 나타내는 경우 이러한 IP 주소가 서브넷에 연결되지 않았거나, 이러한 IP 주소가 연결된 서브넷이 네트워크 사이트 속해 있지 않습니다. 10.121.248.0/24 및 10.121.249.0/24가 이러한 주소에 해당하는 서브넷인 경우 다음과 같이 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-p119">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="8719a-253">IP 주소 10.121.248.226이 10.121.248.0/24 서브넷과 연결되고, IP 주소 10.121.249.20이 10.121.249.0/24 서브넷과 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-253">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="8719a-254">10.121.248.0/24 및 10.121.249.0/24 서브넷이 각각 네트워크 사이트와 연결되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-254">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="8719a-255">네트워크 사이트 및 연결된 서브넷(대역폭 단위: kbps)</span><span class="sxs-lookup"><span data-stu-id="8719a-255">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="8719a-256">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="8719a-256">Network Site</span></span></th>
    <th><span data-ttu-id="8719a-257">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="8719a-257">Network Region</span></span></th>
    <th><span data-ttu-id="8719a-258">대역폭 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-258">BW Limit</span></span></th>
    <th><span data-ttu-id="8719a-259">오디오 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-259">Audio Limit</span></span></th>
    <th><span data-ttu-id="8719a-260">오디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-260">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="8719a-261">비디오 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-261">Video Limit</span></span></th>
    <th><span data-ttu-id="8719a-262">비디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-262">Video Session Limit</span></span></th>
    <th><span data-ttu-id="8719a-263">서브넷</span><span class="sxs-lookup"><span data-stu-id="8719a-263">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="8719a-264">앨버커키</span><span class="sxs-lookup"><span data-stu-id="8719a-264">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="8719a-265">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-265">North America</span></span></p></td>
    <td><p><span data-ttu-id="8719a-266">5,000</span><span class="sxs-lookup"><span data-stu-id="8719a-266">5,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-267">2,000</span><span class="sxs-lookup"><span data-stu-id="8719a-267">2,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-268">175</span><span class="sxs-lookup"><span data-stu-id="8719a-268">175</span></span></p></td>
    <td><p><span data-ttu-id="8719a-269">1400</span><span class="sxs-lookup"><span data-stu-id="8719a-269">1,400</span></span></p></td>
    <td><p><span data-ttu-id="8719a-270">700</span><span class="sxs-lookup"><span data-stu-id="8719a-270">700</span></span></p></td>
    <td><p><span data-ttu-id="8719a-271">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="8719a-271">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="8719a-272">리노</span><span class="sxs-lookup"><span data-stu-id="8719a-272">Reno</span></span></p></td>
    <td><p><span data-ttu-id="8719a-273">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-273">North America</span></span></p></td>
    <td><p><span data-ttu-id="8719a-274">10,000</span><span class="sxs-lookup"><span data-stu-id="8719a-274">10,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-275">4000</span><span class="sxs-lookup"><span data-stu-id="8719a-275">4,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-276">175</span><span class="sxs-lookup"><span data-stu-id="8719a-276">175</span></span></p></td>
    <td><p><span data-ttu-id="8719a-277">2800</span><span class="sxs-lookup"><span data-stu-id="8719a-277">2,800</span></span></p></td>
    <td><p><span data-ttu-id="8719a-278">700</span><span class="sxs-lookup"><span data-stu-id="8719a-278">700</span></span></p></td>
    <td><p><span data-ttu-id="8719a-279">157.57.210.0/23, 172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="8719a-279">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="8719a-280">포틀랜드</span><span class="sxs-lookup"><span data-stu-id="8719a-280">Portland</span></span></p></td>
    <td><p><span data-ttu-id="8719a-281">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-281">North America</span></span></p></td>
    <td><p><span data-ttu-id="8719a-282">5,000</span><span class="sxs-lookup"><span data-stu-id="8719a-282">5,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-283">4000</span><span class="sxs-lookup"><span data-stu-id="8719a-283">4,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-284">175</span><span class="sxs-lookup"><span data-stu-id="8719a-284">175</span></span></p></td>
    <td><p><span data-ttu-id="8719a-285">2800</span><span class="sxs-lookup"><span data-stu-id="8719a-285">2,800</span></span></p></td>
    <td><p><span data-ttu-id="8719a-286">700</span><span class="sxs-lookup"><span data-stu-id="8719a-286">700</span></span></p></td>
    <td><p><span data-ttu-id="8719a-287">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="8719a-287">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="8719a-288">뉴욕</span><span class="sxs-lookup"><span data-stu-id="8719a-288">New York</span></span></p></td>
    <td><p><span data-ttu-id="8719a-289">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-289">North America</span></span></p></td>
    <td><p><span data-ttu-id="8719a-290">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-291">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-292">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-293">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-294">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-294">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-295">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="8719a-295">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="8719a-296">지사</span><span class="sxs-lookup"><span data-stu-id="8719a-296">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="8719a-297">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-297">North America</span></span></p></td>
    <td><p><span data-ttu-id="8719a-298">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-299">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-300">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-301">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-302">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-302">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-303">157.57.211.0/23, 172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="8719a-303">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="8719a-304">디트로이트</span><span class="sxs-lookup"><span data-stu-id="8719a-304">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="8719a-305">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-305">North America</span></span></p></td>
    <td><p><span data-ttu-id="8719a-306">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-307">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-308">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-309">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-310">(제한 없음)</span><span class="sxs-lookup"><span data-stu-id="8719a-310">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="8719a-311">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="8719a-311">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="8719a-312">Lync Server 통화 허용 제어에서는 네트워크 지역 간의 연결을 *지역 링크*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-312">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="8719a-313">각 지역 링크에 대해 네트워크 사이트와 마찬가지로 다음 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-313">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="8719a-314">모든 동시 오디오 세션에 대해 설정할 전체 대역폭 제한.</span><span class="sxs-lookup"><span data-stu-id="8719a-314">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="8719a-315">새 오디오 세션으로 인해이 제한이 초과 되는 경우 Lync Server에서는 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-315">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="8719a-p122">각각의 개별 오디오 세션에 대해 설정할 대역폭 제한. 기본 CAC 대역폭 제한은 175kbps이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-p122">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="8719a-318">모든 동시 비디오 세션에 대해 설정할 전체 대역폭 제한.</span><span class="sxs-lookup"><span data-stu-id="8719a-318">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="8719a-319">새 비디오 세션으로 인해이 제한이 초과 되는 경우 Lync Server에서는 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-319">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="8719a-p124">각각의 개별 비디오 세션에 대해 설정할 대역폭 제한. 기본 CAC 대역폭 제한은 700kbps이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-p124">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="8719a-322">**연관된 대역폭 제한이 있는 네트워크 지역 링크**</span><span class="sxs-lookup"><span data-stu-id="8719a-322">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="8719a-323">![3 개 지역 간의 제한 예제](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "3 개 지역 간의 제한 예제")</span><span class="sxs-lookup"><span data-stu-id="8719a-323">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="8719a-324">지역 링크 대역폭 정보(대역폭 단위: kbps)</span><span class="sxs-lookup"><span data-stu-id="8719a-324">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="8719a-325">지역 링크 이름</span><span class="sxs-lookup"><span data-stu-id="8719a-325">Region Link Name</span></span></th>
    <th><span data-ttu-id="8719a-326">첫 번째 지역</span><span class="sxs-lookup"><span data-stu-id="8719a-326">First Region</span></span></th>
    <th><span data-ttu-id="8719a-327">두 번째 지역</span><span class="sxs-lookup"><span data-stu-id="8719a-327">Second Region</span></span></th>
    <th><span data-ttu-id="8719a-328">대역폭 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-328">BW Limit</span></span></th>
    <th><span data-ttu-id="8719a-329">오디오 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-329">Audio Limit</span></span></th>
    <th><span data-ttu-id="8719a-330">오디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-330">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="8719a-331">비디오 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-331">Video Limit</span></span></th>
    <th><span data-ttu-id="8719a-332">비디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-332">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="8719a-333">NA-EMEA-링크</span><span class="sxs-lookup"><span data-stu-id="8719a-333">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="8719a-334">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-334">North America</span></span></p></td>
    <td><p><span data-ttu-id="8719a-335">슈팅</span><span class="sxs-lookup"><span data-stu-id="8719a-335">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="8719a-336">50,000</span><span class="sxs-lookup"><span data-stu-id="8719a-336">50,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-337">20,000</span><span class="sxs-lookup"><span data-stu-id="8719a-337">20,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-338">175</span><span class="sxs-lookup"><span data-stu-id="8719a-338">175</span></span></p></td>
    <td><p><span data-ttu-id="8719a-339">14000</span><span class="sxs-lookup"><span data-stu-id="8719a-339">14,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-340">700</span><span class="sxs-lookup"><span data-stu-id="8719a-340">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="8719a-341">EMEA-APAC-링크</span><span class="sxs-lookup"><span data-stu-id="8719a-341">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="8719a-342">슈팅</span><span class="sxs-lookup"><span data-stu-id="8719a-342">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="8719a-343">APAC</span><span class="sxs-lookup"><span data-stu-id="8719a-343">APAC</span></span></p></td>
    <td><p><span data-ttu-id="8719a-344">25,000</span><span class="sxs-lookup"><span data-stu-id="8719a-344">25,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-345">10,000</span><span class="sxs-lookup"><span data-stu-id="8719a-345">10,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-346">175</span><span class="sxs-lookup"><span data-stu-id="8719a-346">175</span></span></p></td>
    <td><p><span data-ttu-id="8719a-347">7000</span><span class="sxs-lookup"><span data-stu-id="8719a-347">7,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-348">700</span><span class="sxs-lookup"><span data-stu-id="8719a-348">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="8719a-349">모든 네트워크 지역 쌍 간의 경로 정의</span><span class="sxs-lookup"><span data-stu-id="8719a-349">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8719a-350">북미 지역과 APAC 지역 간의 경로에는 두 지역을 직접 연결하는 지역 링크가 없으므로 두 개의 링크가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-350">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="8719a-351">지역 경로</span><span class="sxs-lookup"><span data-stu-id="8719a-351">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="8719a-352">지역 경로 이름</span><span class="sxs-lookup"><span data-stu-id="8719a-352">Region Route Name</span></span></th>
    <th><span data-ttu-id="8719a-353">첫 번째 지역</span><span class="sxs-lookup"><span data-stu-id="8719a-353">First Region</span></span></th>
    <th><span data-ttu-id="8719a-354">두 번째 지역</span><span class="sxs-lookup"><span data-stu-id="8719a-354">Second Region</span></span></th>
    <th><span data-ttu-id="8719a-355">지역 링크</span><span class="sxs-lookup"><span data-stu-id="8719a-355">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="8719a-356">N-EMEA-ROUTE</span><span class="sxs-lookup"><span data-stu-id="8719a-356">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="8719a-357">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-357">North America</span></span></p></td>
    <td><p><span data-ttu-id="8719a-358">슈팅</span><span class="sxs-lookup"><span data-stu-id="8719a-358">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="8719a-359">NA-EMEA-링크</span><span class="sxs-lookup"><span data-stu-id="8719a-359">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="8719a-360">EMEA-APAC-경로</span><span class="sxs-lookup"><span data-stu-id="8719a-360">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="8719a-361">슈팅</span><span class="sxs-lookup"><span data-stu-id="8719a-361">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="8719a-362">APAC</span><span class="sxs-lookup"><span data-stu-id="8719a-362">APAC</span></span></p></td>
    <td><p><span data-ttu-id="8719a-363">EMEA-APAC-링크</span><span class="sxs-lookup"><span data-stu-id="8719a-363">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="8719a-364">NA-APAC-경로</span><span class="sxs-lookup"><span data-stu-id="8719a-364">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="8719a-365">북미</span><span class="sxs-lookup"><span data-stu-id="8719a-365">North America</span></span></p></td>
    <td><p><span data-ttu-id="8719a-366">APAC</span><span class="sxs-lookup"><span data-stu-id="8719a-366">APAC</span></span></p></td>
    <td><p><span data-ttu-id="8719a-367">NA-EMEA-LINK, EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="8719a-367">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="8719a-368">단일 링크(*사이트 간* 링크라고 함)로 직접 연결되는 모든 네트워크 사이트 쌍에 대해 다음 사항을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-368">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="8719a-369">모든 동시 오디오 세션에 대해 설정할 전체 대역폭 제한.</span><span class="sxs-lookup"><span data-stu-id="8719a-369">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="8719a-370">새 오디오 세션으로 인해이 제한이 초과 되는 경우 Lync Server에서는 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-370">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="8719a-p126">각각의 개별 오디오 세션에 대해 설정할 대역폭 제한. 기본 CAC 대역폭 제한은 175kbps이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-p126">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="8719a-373">모든 동시 비디오 세션에 대해 설정할 전체 대역폭 제한.</span><span class="sxs-lookup"><span data-stu-id="8719a-373">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="8719a-374">새 비디오 세션으로 인해이 제한이 초과 되는 경우 Lync Server에서는 세션을 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-374">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="8719a-p128">각각의 개별 비디오 세션에 대해 설정할 대역폭 제한. 기본 CAC 대역폭 제한은 700kbps이지만 관리자가 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-p128">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="8719a-377">**북미 CAC 네트워크 지역의 리노와 앨버커키 간의 사이트 간 링크에 대한 대역폭 용량 및 대역폭 제한**</span><span class="sxs-lookup"><span data-stu-id="8719a-377">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="8719a-378">![WAN 대역폭이 제한 된 네트워크 사이트 예제](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "WAN 대역폭이 제한 된 네트워크 사이트 예제")</span><span class="sxs-lookup"><span data-stu-id="8719a-378">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="8719a-379">두 네트워크 사이트 간의 사이트 간 링크에 대한 대역폭 정보(대역폭 단위: kbps)</span><span class="sxs-lookup"><span data-stu-id="8719a-379">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="8719a-380">사이트 간 링크 이름</span><span class="sxs-lookup"><span data-stu-id="8719a-380">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="8719a-381">첫 번째 사이트</span><span class="sxs-lookup"><span data-stu-id="8719a-381">First Site</span></span></th>
    <th><span data-ttu-id="8719a-382">두 번째 사이트</span><span class="sxs-lookup"><span data-stu-id="8719a-382">Second Site</span></span></th>
    <th><span data-ttu-id="8719a-383">대역폭 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-383">BW Limit</span></span></th>
    <th><span data-ttu-id="8719a-384">오디오 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-384">Audio Limit</span></span></th>
    <th><span data-ttu-id="8719a-385">오디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-385">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="8719a-386">비디오 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-386">Video Limit</span></span></th>
    <th><span data-ttu-id="8719a-387">비디오 세션 제한</span><span class="sxs-lookup"><span data-stu-id="8719a-387">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="8719a-388">리노-Albu-사이트 링크</span><span class="sxs-lookup"><span data-stu-id="8719a-388">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="8719a-389">리노</span><span class="sxs-lookup"><span data-stu-id="8719a-389">Reno</span></span></p></td>
    <td><p><span data-ttu-id="8719a-390">앨버커키</span><span class="sxs-lookup"><span data-stu-id="8719a-390">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="8719a-391">20,000</span><span class="sxs-lookup"><span data-stu-id="8719a-391">20,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-392">12000</span><span class="sxs-lookup"><span data-stu-id="8719a-392">12,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-393">175</span><span class="sxs-lookup"><span data-stu-id="8719a-393">175</span></span></p></td>
    <td><p><span data-ttu-id="8719a-394">5,000</span><span class="sxs-lookup"><span data-stu-id="8719a-394">5,000</span></span></p></td>
    <td><p><span data-ttu-id="8719a-395">700</span><span class="sxs-lookup"><span data-stu-id="8719a-395">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="8719a-396">다음 단계</span><span class="sxs-lookup"><span data-stu-id="8719a-396">Next Steps</span></span>

<span data-ttu-id="8719a-397">필요한 정보를 수집한 후에는 Lync Server 관리 셸 또는 Lync Server 제어판을 사용 하 여 CAC 배포를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-397">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="8719a-398">Lync Server 제어판을 사용 하 여 서브넷과 사이트 링크를 만들려면 대부분의 네트워크 구성 작업을 수행할 수 있지만 Lync Server 관리 셸을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8719a-398">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="8719a-399">자세한 내용은 <STRONG>새 CsNetworkSubnet</STRONG> Cmdlet 및 <STRONG>remove-csnetworkintersitepolicy</STRONG> Cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8719a-399">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

