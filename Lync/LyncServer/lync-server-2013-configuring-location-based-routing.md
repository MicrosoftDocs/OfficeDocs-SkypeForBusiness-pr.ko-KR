---
title: 'Lync Server 2013: 위치 기반 라우팅 구성'
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
ms.openlocfilehash: 64e7df946d5e120352c2f0253a87197cb22b7276
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="d6d2c-102">Lync Server 2013에서 위치 기반 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="d6d2c-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6d2c-103">_**마지막으로 수정 된 항목:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="d6d2c-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="d6d2c-104">Lync Server 2013 C U 1, 위치 기반 라우팅은 Enterprise Voice의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2c-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="d6d2c-105">위치 기반 라우팅은 Lync Server 2013 C U 1에서 통화가 라우팅되는 방식을 제어 하는 통화 관리 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2c-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="d6d2c-106">Lync 발신자의 위치에 따라 통화를 PBX 또는 PSTN 대상으로 라우팅할 수 있는지 여부에 대 한 제한을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2c-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="d6d2c-107">위치 기반 라우팅은 발신자의 네트워크 위치를 기반으로 PSTN 통화에 통화 권한 부여 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2c-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="d6d2c-108">발신자의 위치는 발신자가 연결 되는 네트워크 서브넷과 연결 된 네트워크 사이트를 기반으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2c-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="d6d2c-109">위치 기반 라우팅을 구성 하려면 먼저 Enterprise Voice를 배포한 다음 네트워크 지역, 사이트 및 서브넷을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2c-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="d6d2c-110">이렇게 하면 위치 기반 라우팅을 사용 하기 위한 기초가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2c-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="d6d2c-111">위치 기반 라우팅을 배포 하려면 먼저 Enterprise Voice를 배포 하 고 네트워크 지역 및 사이트를 구성 하 고 네트워크 사이트에 네트워크 서브넷을 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2c-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="d6d2c-112">완료 되 면 위치 기반 라우팅을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2c-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="d6d2c-113">네트워크 지역, 사이트 및 서브넷을 구성 하는 방법에 대 한 단계는 [Lync Server 2013에서 고급 Enterprise Voice 기능 배포](lync-server-2013-deploying-advanced-enterprise-voice-features.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d6d2c-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="d6d2c-114">이 섹션에서는 다음 예제를 그림으로 사용 하 여 위치 기반 라우팅을 구성 하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2c-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="d6d2c-115">![Enterprise Voice 위치 기반 라우팅 예](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice 위치 기반 라우팅 예")</span><span class="sxs-lookup"><span data-stu-id="d6d2c-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="d6d2c-116">다음 표에서는이 예제에 정의 된 사용자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2c-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6d2c-117">끝점 유형</span><span class="sxs-lookup"><span data-stu-id="d6d2c-117">Endpoint type</span></span></th>
<th><span data-ttu-id="d6d2c-118">위치</span><span class="sxs-lookup"><span data-stu-id="d6d2c-118">Location</span></span></th>
<th><span data-ttu-id="d6d2c-119">사용자</span><span class="sxs-lookup"><span data-stu-id="d6d2c-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6d2c-120">Lync</span><span class="sxs-lookup"><span data-stu-id="d6d2c-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-121">뉴델리 회사 사무실</span><span class="sxs-lookup"><span data-stu-id="d6d2c-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-122">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="d6d2c-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d2c-123">Lync</span><span class="sxs-lookup"><span data-stu-id="d6d2c-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-124">Hyderabad 회사 사무실</span><span class="sxs-lookup"><span data-stu-id="d6d2c-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-125">HYD-1, HYD-2, HYD-3</span><span class="sxs-lookup"><span data-stu-id="d6d2c-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d2c-126">Lync</span><span class="sxs-lookup"><span data-stu-id="d6d2c-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-127">알 수 없음 (예: 호텔)</span><span class="sxs-lookup"><span data-stu-id="d6d2c-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-128">UNK-1</span><span class="sxs-lookup"><span data-stu-id="d6d2c-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d2c-129">전화가</span><span class="sxs-lookup"><span data-stu-id="d6d2c-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-130">뉴델리 회사 사무실</span><span class="sxs-lookup"><span data-stu-id="d6d2c-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-131">DEL-PBX-1, DEL-2</span><span class="sxs-lookup"><span data-stu-id="d6d2c-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d2c-132">전화가</span><span class="sxs-lookup"><span data-stu-id="d6d2c-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-133">Hyderabad 회사 사무실</span><span class="sxs-lookup"><span data-stu-id="d6d2c-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-134">HYD-1, HYD-2</span><span class="sxs-lookup"><span data-stu-id="d6d2c-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d2c-135">PSTN</span><span class="sxs-lookup"><span data-stu-id="d6d2c-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-136">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="d6d2c-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-137">PSTN-1, PSTN-2, PSTN-3</span><span class="sxs-lookup"><span data-stu-id="d6d2c-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="d6d2c-138">다음 표에서는이 예제 환경에 설명 된 시스템을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6d2c-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d6d2c-139">컴퓨터</span><span class="sxs-lookup"><span data-stu-id="d6d2c-139">System</span></span></th>
<th><span data-ttu-id="d6d2c-140">위치</span><span class="sxs-lookup"><span data-stu-id="d6d2c-140">Location</span></span></th>
<th><span data-ttu-id="d6d2c-141">이름</span><span class="sxs-lookup"><span data-stu-id="d6d2c-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d6d2c-142">Lync Server 2013 C U 1 풀</span><span class="sxs-lookup"><span data-stu-id="d6d2c-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-143">그</span><span class="sxs-lookup"><span data-stu-id="d6d2c-143">any</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="d6d2c-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d2c-145">Lync Server 2013 C U 1, 중재 서버</span><span class="sxs-lookup"><span data-stu-id="d6d2c-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-146">그</span><span class="sxs-lookup"><span data-stu-id="d6d2c-146">any</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-147">PL1</span><span class="sxs-lookup"><span data-stu-id="d6d2c-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d2c-148">PSTN 게이트웨이 1</span><span class="sxs-lookup"><span data-stu-id="d6d2c-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-149">Delhi</span><span class="sxs-lookup"><span data-stu-id="d6d2c-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="d6d2c-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d2c-151">PSTN 게이트웨이 2</span><span class="sxs-lookup"><span data-stu-id="d6d2c-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="d6d2c-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-153">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="d6d2c-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d6d2c-154">PBX 1</span><span class="sxs-lookup"><span data-stu-id="d6d2c-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-155">Delhi</span><span class="sxs-lookup"><span data-stu-id="d6d2c-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="d6d2c-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d6d2c-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="d6d2c-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="d6d2c-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="d6d2c-159">적색-PBX</span><span class="sxs-lookup"><span data-stu-id="d6d2c-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="d6d2c-160">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="d6d2c-160">In This Section</span></span>

  - [<span data-ttu-id="d6d2c-161">Lync Server 2013에서 Enterprise Voice 구성</span><span class="sxs-lookup"><span data-stu-id="d6d2c-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="d6d2c-162">Lync Server 2013에서 네트워크 지역, 사이트 및 서브넷 배포</span><span class="sxs-lookup"><span data-stu-id="d6d2c-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="d6d2c-163">Lync Server 2013에서 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="d6d2c-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d6d2c-164">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6d2c-164">See Also</span></span>


[<span data-ttu-id="d6d2c-165">Lync Server 2013에서 고급 Enterprise Voice 기능 배포</span><span class="sxs-lookup"><span data-stu-id="d6d2c-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

