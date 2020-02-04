---
title: 'Lync Server 2013: 네트워크 지역, 사이트 및 서브넷 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying network regions, sites, and subnets
ms:assetid: c4b75601-3538-4d07-8d23-1ad90459ae48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994067(v=OCS.15)
ms:contentKeyID: 51803978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04c39a18147bad3f84bd345ec0a56b606db4cae4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="8307f-102">Lync Server 2013에서 네트워크 지역, 사이트 및 서브넷 배포</span><span class="sxs-lookup"><span data-stu-id="8307f-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8307f-103">_**마지막으로 수정한 주제:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="8307f-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="8307f-104">엔터프라이즈 음성이 배포 되 면 다음을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8307f-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="8307f-105">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="8307f-105">Network regions</span></span>

  - <span data-ttu-id="8307f-106">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="8307f-106">Network sites</span></span>

  - <span data-ttu-id="8307f-107">네트워크 서브넷</span><span class="sxs-lookup"><span data-stu-id="8307f-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="8307f-108">네트워크 지역 정의</span><span class="sxs-lookup"><span data-stu-id="8307f-108">Define Network Regions</span></span>

<span data-ttu-id="8307f-109">Lync Server Windows PowerShell 명령, 새 CsNetworkRegion 또는 Lync Server 제어판을 사용 하 여 네트워크 지역을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8307f-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="8307f-110">자세한 내용은 [새 CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8307f-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="8307f-111">이 예제에서는 다음 Windows PowerShell 명령은이 시나리오에 정의 된 네트워크 지역 (지역 1 (인도))을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8307f-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="8307f-112">네트워크 사이트 정의</span><span class="sxs-lookup"><span data-stu-id="8307f-112">Define Network Sites</span></span>

<span data-ttu-id="8307f-113">Lync Server Windows PowerShell 명령, 새 CsNetworkSite 또는 Lync Server 제어판을 사용 하 여 네트워크 사이트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8307f-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="8307f-114">자세한 내용은 [새 CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8307f-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="8307f-115">이 예제에서는 다음 표 및 Lync Server Windows PowerShell 명령은이 시나리오에 정의 된 네트워크 사이트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8307f-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="8307f-116">이 표에는 위치 기반 라우팅과 관련 하 여 설명 하는 설정만 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8307f-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
    New-CsNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="8307f-117">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="8307f-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="8307f-118">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="8307f-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8307f-119">사이트 ID</span><span class="sxs-lookup"><span data-stu-id="8307f-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="8307f-120">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="8307f-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="8307f-121">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="8307f-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8307f-122">지역 ID</span><span class="sxs-lookup"><span data-stu-id="8307f-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="8307f-123">지역 1 (인도)</span><span class="sxs-lookup"><span data-stu-id="8307f-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="8307f-124">지역 1 (인도)</span><span class="sxs-lookup"><span data-stu-id="8307f-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="8307f-125">네트워크 서브넷 정의</span><span class="sxs-lookup"><span data-stu-id="8307f-125">Define Network Subnets</span></span>

<span data-ttu-id="8307f-126">Lync Server Windows PowerShell 명령, 새 CsNetworkSubnet 또는 Lync Server 제어판을 사용 하 여 네트워크 서브넷을 정의 하 고 네트워크 사이트에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8307f-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="8307f-127">자세한 내용은 [새 CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8307f-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="8307f-128">이 예제에서 다음 표 및 Windows PowerShell 명령은이 시나리오에 정의 된 네트워크 사이트, 뉴델리 및 Hyderabad 네트워크 서브넷을 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8307f-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="8307f-129">이 표에는 위치 기반 라우팅과 관련 하 여 설명 하는 설정만 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8307f-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
    New-CsNetworkSubnet -SubnetID "192.168.1.0" -MaskBits "24" -NetworkSiteID "Hyderabad"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="8307f-130">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="8307f-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="8307f-131">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="8307f-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8307f-132">서브넷 ID</span><span class="sxs-lookup"><span data-stu-id="8307f-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="8307f-133">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="8307f-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="8307f-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="8307f-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8307f-135">마스킹하</span><span class="sxs-lookup"><span data-stu-id="8307f-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="8307f-136">fps</span><span class="sxs-lookup"><span data-stu-id="8307f-136">24</span></span></p></td>
<td><p><span data-ttu-id="8307f-137">fps</span><span class="sxs-lookup"><span data-stu-id="8307f-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8307f-138">사이트 ID</span><span class="sxs-lookup"><span data-stu-id="8307f-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="8307f-139">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="8307f-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="8307f-140">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="8307f-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8307f-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8307f-141">See Also</span></span>


[<span data-ttu-id="8307f-142">Lync Server 2013에서 위치 기반 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="8307f-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

