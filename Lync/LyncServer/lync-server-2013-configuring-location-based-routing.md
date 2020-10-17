---
title: 'Lync Server 2013: Location-Based 라우팅 구성'
description: 'Lync Server 2013: Location-Based 라우팅을 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 080c2a3a82a8714fc35ce882b0c6cb1630552f27
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570884"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="d1cd2-103">Lync Server 2013에서 Location-Based 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="d1cd2-103">Configuring Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1cd2-104">_**마지막으로 수정 된 항목:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="d1cd2-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="d1cd2-105">Lync Server 2013 C U 1 Location-Based 라우팅은 Enterprise Voice의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cd2-105">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="d1cd2-106">Location-Based 라우팅은 Lync Server 2013 C U 1에서 호출을 라우팅하는 방법을 제어 하는 통화 관리 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d1cd2-106">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="d1cd2-107">Lync 발신자의 위치에 따라 통화를 PBX 또는 PSTN 대상으로 라우팅할 수 있는지 여부에 대 한 제한을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cd2-107">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="d1cd2-108">Location-Based 라우팅은 발신자의 네트워크 위치를 기반으로 PSTN 통화에 통화 권한 부여 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cd2-108">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="d1cd2-109">발신자의 위치는 발신자가 연결 되는 네트워크 서브넷과 연결 된 네트워크 사이트를 기반으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1cd2-109">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="d1cd2-110">Location-Based 라우팅을 구성 하려면 먼저 Enterprise Voice를 배포한 다음 네트워크 지역, 사이트 및 서브넷을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cd2-110">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="d1cd2-111">이렇게 하면 Location-Based 라우팅을 사용 하기 위한 토대를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cd2-111">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="d1cd2-112">Location-Based 라우팅을 배포 하기 전에 먼저 Enterprise Voice를 배포 하 고 네트워크 지역 및 사이트를 구성 하 고 네트워크 사이트에 네트워크 서브넷을 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cd2-112">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="d1cd2-113">완료 되 면 Location-Based 라우팅을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1cd2-113">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="d1cd2-114">네트워크 지역, 사이트 및 서브넷을 구성 하는 방법에 대 한 단계는 [Lync Server 2013에서 고급 Enterprise Voice 기능 배포](lync-server-2013-deploying-advanced-enterprise-voice-features.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d1cd2-114">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="d1cd2-115">이 섹션에서는 다음 예제를 그림으로 사용 하 여 Location-Based 라우팅을 구성 하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1cd2-115">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="d1cd2-116">![Enterprise Voice 위치 기반 라우팅 예](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice 위치 기반 라우팅 예")</span><span class="sxs-lookup"><span data-stu-id="d1cd2-116">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="d1cd2-117">다음 표에서는이 예제에 정의 된 사용자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d1cd2-117">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1cd2-118">끝점 유형</span><span class="sxs-lookup"><span data-stu-id="d1cd2-118">Endpoint type</span></span></th>
<th><span data-ttu-id="d1cd2-119">위치</span><span class="sxs-lookup"><span data-stu-id="d1cd2-119">Location</span></span></th>
<th><span data-ttu-id="d1cd2-120">사용자</span><span class="sxs-lookup"><span data-stu-id="d1cd2-120">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1cd2-121">Lync</span><span class="sxs-lookup"><span data-stu-id="d1cd2-121">Lync</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-122">뉴델리 회사 사무실</span><span class="sxs-lookup"><span data-stu-id="d1cd2-122">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-123">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="d1cd2-123">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1cd2-124">Lync</span><span class="sxs-lookup"><span data-stu-id="d1cd2-124">Lync</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-125">Hyderabad 회사 사무실</span><span class="sxs-lookup"><span data-stu-id="d1cd2-125">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-126">HYD-1, HYD-2, HYD-3</span><span class="sxs-lookup"><span data-stu-id="d1cd2-126">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1cd2-127">Lync</span><span class="sxs-lookup"><span data-stu-id="d1cd2-127">Lync</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-128">알 수 없음 (예: 호텔)</span><span class="sxs-lookup"><span data-stu-id="d1cd2-128">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-129">UNK-1</span><span class="sxs-lookup"><span data-stu-id="d1cd2-129">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1cd2-130">전화가</span><span class="sxs-lookup"><span data-stu-id="d1cd2-130">PBX</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-131">뉴델리 회사 사무실</span><span class="sxs-lookup"><span data-stu-id="d1cd2-131">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-132">DEL-PBX-1, DEL-2</span><span class="sxs-lookup"><span data-stu-id="d1cd2-132">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1cd2-133">전화가</span><span class="sxs-lookup"><span data-stu-id="d1cd2-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-134">Hyderabad 회사 사무실</span><span class="sxs-lookup"><span data-stu-id="d1cd2-134">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-135">HYD-1, HYD-2</span><span class="sxs-lookup"><span data-stu-id="d1cd2-135">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1cd2-136">PSTN</span><span class="sxs-lookup"><span data-stu-id="d1cd2-136">PSTN</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-137">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="d1cd2-137">Unknown</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-138">PSTN-1, PSTN-2, PSTN-3</span><span class="sxs-lookup"><span data-stu-id="d1cd2-138">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="d1cd2-139">다음 표에서는이 예제 환경에 설명 된 시스템을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1cd2-139">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1cd2-140">컴퓨터</span><span class="sxs-lookup"><span data-stu-id="d1cd2-140">System</span></span></th>
<th><span data-ttu-id="d1cd2-141">위치</span><span class="sxs-lookup"><span data-stu-id="d1cd2-141">Location</span></span></th>
<th><span data-ttu-id="d1cd2-142">이름</span><span class="sxs-lookup"><span data-stu-id="d1cd2-142">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1cd2-143">Lync Server 2013 C U 1 풀</span><span class="sxs-lookup"><span data-stu-id="d1cd2-143">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-144">그</span><span class="sxs-lookup"><span data-stu-id="d1cd2-144">any</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-145">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="d1cd2-145">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1cd2-146">Lync Server 2013 C U 1, 중재 서버</span><span class="sxs-lookup"><span data-stu-id="d1cd2-146">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-147">그</span><span class="sxs-lookup"><span data-stu-id="d1cd2-147">any</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-148">PL1</span><span class="sxs-lookup"><span data-stu-id="d1cd2-148">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1cd2-149">PSTN 게이트웨이 1</span><span class="sxs-lookup"><span data-stu-id="d1cd2-149">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-150">Delhi</span><span class="sxs-lookup"><span data-stu-id="d1cd2-150">Delhi</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-151">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="d1cd2-151">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1cd2-152">PSTN 게이트웨이 2</span><span class="sxs-lookup"><span data-stu-id="d1cd2-152">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-153">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="d1cd2-153">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-154">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="d1cd2-154">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1cd2-155">PBX 1</span><span class="sxs-lookup"><span data-stu-id="d1cd2-155">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-156">Delhi</span><span class="sxs-lookup"><span data-stu-id="d1cd2-156">Delhi</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-157">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="d1cd2-157">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1cd2-158">PBX 2</span><span class="sxs-lookup"><span data-stu-id="d1cd2-158">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-159">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="d1cd2-159">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="d1cd2-160">적색-PBX</span><span class="sxs-lookup"><span data-stu-id="d1cd2-160">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="d1cd2-161">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d1cd2-161">In This Section</span></span>

  - [<span data-ttu-id="d1cd2-162">Lync Server 2013에서 Enterprise Voice 구성</span><span class="sxs-lookup"><span data-stu-id="d1cd2-162">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="d1cd2-163">Lync Server 2013에서 네트워크 지역, 사이트 및 서브넷 배포</span><span class="sxs-lookup"><span data-stu-id="d1cd2-163">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="d1cd2-164">Lync Server 2013에서 Location-Based 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="d1cd2-164">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1cd2-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1cd2-165">See Also</span></span>


[<span data-ttu-id="d1cd2-166">Lync Server 2013에서 고급 Enterprise Voice 기능 배포</span><span class="sxs-lookup"><span data-stu-id="d1cd2-166">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

