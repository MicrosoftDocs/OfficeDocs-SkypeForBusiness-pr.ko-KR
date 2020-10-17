---
title: 'Lync Server 2013: 네트워크 지역, 사이트 및 서브넷 배포'
description: 'Lync Server 2013: 네트워크 지역, 사이트 및 서브넷을 배포 합니다.'
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
ms.openlocfilehash: f1c4c08cd9b78b1439000cdb4a7bbe3ffc2f99d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561094"
---
# <a name="deploying-network-regions-sites-and-subnets-in-lync-server-2013"></a><span data-ttu-id="a1b43-103">Lync Server 2013에서 네트워크 지역, 사이트 및 서브넷 배포</span><span class="sxs-lookup"><span data-stu-id="a1b43-103">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1b43-104">_**마지막으로 수정 된 항목:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="a1b43-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="a1b43-105">Enterprise Voice를 배포한 후에는 다음을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b43-105">Once Enterprise Voice is deployed, you need to configure:</span></span>

  - <span data-ttu-id="a1b43-106">네트워크 지역</span><span class="sxs-lookup"><span data-stu-id="a1b43-106">Network regions</span></span>

  - <span data-ttu-id="a1b43-107">네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="a1b43-107">Network sites</span></span>

  - <span data-ttu-id="a1b43-108">네트워크 서브넷</span><span class="sxs-lookup"><span data-stu-id="a1b43-108">Network subnets</span></span>

<div>

## <a name="define-network-regions"></a><span data-ttu-id="a1b43-109">네트워크 지역 정의</span><span class="sxs-lookup"><span data-stu-id="a1b43-109">Define Network Regions</span></span>

<span data-ttu-id="a1b43-110">Lync Server Windows PowerShell 명령, 신규-CsNetworkRegion 또는 Lync Server 제어판을 사용 하 여 네트워크 지역을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b43-110">Use the Lync Server Windows PowerShell command, New-CsNetworkRegion, or Lync Server Control Panel to define network regions.</span></span>

    New-CsNetworkRegion -NetworkRegionID <region ID> -CentralSite <site ID>

<span data-ttu-id="a1b43-111">자세한 내용은 [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a1b43-111">For more information, see [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion).</span></span>

<span data-ttu-id="a1b43-112">이 예제의 경우 다음 Windows PowerShell 명령은이 시나리오에 정의 된 네트워크 지역 1 (인도)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1b43-112">For this example, the following Windows PowerShell command illustrates the network region, region 1 (India), defined in this scenario.</span></span>

    New-CsNetworkRegion -NetworkRegionID "India" -CentralSite "India Central Site"

<div>


</div>

</div>

<div>

## <a name="define-network-sites"></a><span data-ttu-id="a1b43-113">네트워크 사이트 정의</span><span class="sxs-lookup"><span data-stu-id="a1b43-113">Define Network Sites</span></span>

<span data-ttu-id="a1b43-114">Lync Server Windows PowerShell 명령, 신규-CsNetworkSite 또는 Lync Server 제어판을 사용 하 여 네트워크 사이트를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b43-114">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, or the Lync Server Control Panel to define network sites.</span></span>

    New-CsNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>

<span data-ttu-id="a1b43-115">자세한 내용은 [새-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a1b43-115">For more information, see [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite).</span></span>

<span data-ttu-id="a1b43-116">이 예제의 경우 다음 표 및 Lync Server Windows PowerShell 명령은이 시나리오에 정의 된 네트워크 사이트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1b43-116">For this example, the following table and Lync Server Windows PowerShell command illustrate the network sites defined in this scenario.</span></span> <span data-ttu-id="a1b43-117">Location-Based 라우팅과 관련 된 설정만 설명을 위해 표에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b43-117">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="a1b43-118">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="a1b43-118">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="a1b43-119">사이트 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="a1b43-119">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1b43-120">사이트 ID</span><span class="sxs-lookup"><span data-stu-id="a1b43-120">Site ID</span></span></p></td>
<td><p><span data-ttu-id="a1b43-121">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="a1b43-121">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="a1b43-122">사이트 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="a1b43-122">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1b43-123">지역 ID</span><span class="sxs-lookup"><span data-stu-id="a1b43-123">Region ID</span></span></p></td>
<td><p><span data-ttu-id="a1b43-124">지역 1 (인도)</span><span class="sxs-lookup"><span data-stu-id="a1b43-124">Region 1 (India)</span></span></p></td>
<td><p><span data-ttu-id="a1b43-125">지역 1 (인도)</span><span class="sxs-lookup"><span data-stu-id="a1b43-125">Region 1 (India)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-network-subnets"></a><span data-ttu-id="a1b43-126">네트워크 서브넷 정의</span><span class="sxs-lookup"><span data-stu-id="a1b43-126">Define Network Subnets</span></span>

<span data-ttu-id="a1b43-127">Lync Server Windows PowerShell 명령, 신규-CsNetworkSubnet 또는 Lync Server 제어판을 사용 하 여 네트워크 서브넷을 정의 하 고 네트워크 사이트에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1b43-127">Use the Lync Server Windows PowerShell command, New-CsNetworkSubnet, or the Lync Server Control Panel to define network subnets and assign them to network sites.</span></span>

    New-CsNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>

<span data-ttu-id="a1b43-128">자세한 내용은 [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a1b43-128">For more information, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<span data-ttu-id="a1b43-129">이 예의 경우 다음 표 및 Windows PowerShell 명령은이 시나리오에 정의 된 네트워크 사이트, Hyderabad 및 \에 네트워크 서브넷을 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1b43-129">For this example, the following table and Windows PowerShell commands illustrate the assignment of network subnets to the network sites, Delhi and Hyderabad, defined in this scenario.</span></span> <span data-ttu-id="a1b43-130">Location-Based 라우팅과 관련 된 설정만 설명을 위해 표에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1b43-130">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="a1b43-131">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="a1b43-131">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="a1b43-132">사이트 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="a1b43-132">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1b43-133">서브넷 ID</span><span class="sxs-lookup"><span data-stu-id="a1b43-133">Subnet ID</span></span></p></td>
<td><p><span data-ttu-id="a1b43-134">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="a1b43-134">192.168.0.0</span></span></p></td>
<td><p><span data-ttu-id="a1b43-135">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="a1b43-135">192.168.1.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1b43-136">숨길</span><span class="sxs-lookup"><span data-stu-id="a1b43-136">Mask</span></span></p></td>
<td><p><span data-ttu-id="a1b43-137">mb</span><span class="sxs-lookup"><span data-stu-id="a1b43-137">24</span></span></p></td>
<td><p><span data-ttu-id="a1b43-138">mb</span><span class="sxs-lookup"><span data-stu-id="a1b43-138">24</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1b43-139">사이트 ID</span><span class="sxs-lookup"><span data-stu-id="a1b43-139">Site ID</span></span></p></td>
<td><p><span data-ttu-id="a1b43-140">사이트 1(뉴델리)</span><span class="sxs-lookup"><span data-stu-id="a1b43-140">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="a1b43-141">사이트 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="a1b43-141">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1b43-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1b43-142">See Also</span></span>


[<span data-ttu-id="a1b43-143">Lync Server 2013에서 Location-Based 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="a1b43-143">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

