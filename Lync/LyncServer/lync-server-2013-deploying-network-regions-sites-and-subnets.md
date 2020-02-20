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
ms.openlocfilehash: eb1409213e2ba40936743e604af79d1fe564530c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="b37c0-102">Lync Server 2013에서 네트워크 지역, 사이트 및 서브넷 배포</span><span class="sxs-lookup"><span data-stu-id="b37c0-102">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b37c0-103">_**마지막으로 수정 된 항목:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="b37c0-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="b37c0-104">Enterprise Voice를 배포한 후에는 다음을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b37c0-104">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="b37c0-105">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="b37c0-105">Network regions</span></span>

  - <span data-ttu-id="b37c0-106">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="b37c0-106">Network sites</span></span>

  - <span data-ttu-id="b37c0-107">네트워크 서브넷</span><span class="sxs-lookup"><span data-stu-id="b37c0-107">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="b37c0-108">네트워크 지역 정의</span><span class="sxs-lookup"><span data-stu-id="b37c0-108">Define Network Regions</span></span>

<span data-ttu-id="b37c0-109">Lync Server Windows PowerShell 명령, 신규-CsNetworkRegion 또는 Lync Server 제어판을 사용 하 여 네트워크 지역을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b37c0-109">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="b37c0-110">자세한 내용은 [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b37c0-110">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="b37c0-111">이 예제의 경우 다음 Windows PowerShell 명령은이 시나리오에 정의 된 네트워크 지역 1 (인도)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b37c0-111">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="b37c0-112">네트워크 사이트 정의</span><span class="sxs-lookup"><span data-stu-id="b37c0-112">Define Network Sites</span></span>

<span data-ttu-id="b37c0-113">Lync Server Windows PowerShell 명령, 신규-CsNetworkSite 또는 Lync Server 제어판을 사용 하 여 네트워크 사이트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b37c0-113">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="b37c0-114">자세한 내용은 [새-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b37c0-114">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="b37c0-115">이 예제의 경우 다음 표 및 Lync Server Windows PowerShell 명령은이 시나리오에 정의 된 네트워크 사이트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b37c0-115">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="b37c0-116">위치 기반 라우팅과 관련 된 설정만 설명을 위해 표에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b37c0-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="b37c0-117">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="b37c0-117">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="b37c0-118">사이트 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b37c0-118">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b37c0-119">사이트 ID</span><span class="sxs-lookup"><span data-stu-id="b37c0-119">Site ID</span></span></p></td>
<td><p><span data-ttu-id="b37c0-120">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="b37c0-120">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="b37c0-121">사이트 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b37c0-121">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b37c0-122">지역 ID</span><span class="sxs-lookup"><span data-stu-id="b37c0-122">Region ID</span></span></p></td>
<td><p><span data-ttu-id="b37c0-123">지역 1 (인도)</span><span class="sxs-lookup"><span data-stu-id="b37c0-123">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="b37c0-124">지역 1 (인도)</span><span class="sxs-lookup"><span data-stu-id="b37c0-124">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="b37c0-125">네트워크 서브넷 정의</span><span class="sxs-lookup"><span data-stu-id="b37c0-125">Define Network Subnets</span></span>

<span data-ttu-id="b37c0-126">Lync Server Windows PowerShell 명령, 신규-CsNetworkSubnet 또는 Lync Server 제어판을 사용 하 여 네트워크 서브넷을 정의 하 고 네트워크 사이트에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b37c0-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="b37c0-127">자세한 내용은 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b37c0-127">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="b37c0-128">이 예의 경우 다음 표 및 Windows PowerShell 명령은이 시나리오에 정의 된 네트워크 사이트, Hyderabad 및 \에 네트워크 서브넷을 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b37c0-128">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="b37c0-129">위치 기반 라우팅과 관련 된 설정만 설명을 위해 표에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b37c0-129">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="b37c0-130">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="b37c0-130">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="b37c0-131">사이트 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b37c0-131">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b37c0-132">서브넷 ID</span><span class="sxs-lookup"><span data-stu-id="b37c0-132">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="b37c0-133">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="b37c0-133">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="b37c0-134">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="b37c0-134">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b37c0-135">숨길</span><span class="sxs-lookup"><span data-stu-id="b37c0-135">Mask</span></span></p></td>
<td><p><span data-ttu-id="b37c0-136">mb</span><span class="sxs-lookup"><span data-stu-id="b37c0-136">24</span></span></p></td>
<td><p><span data-ttu-id="b37c0-137">mb</span><span class="sxs-lookup"><span data-stu-id="b37c0-137">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b37c0-138">사이트 ID</span><span class="sxs-lookup"><span data-stu-id="b37c0-138">Site ID</span></span></p></td>
<td><p><span data-ttu-id="b37c0-139">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="b37c0-139">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="b37c0-140">사이트 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="b37c0-140">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b37c0-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b37c0-141">See Also</span></span>


[<span data-ttu-id="b37c0-142">Lync Server 2013에서 위치 기반 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="b37c0-142">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

