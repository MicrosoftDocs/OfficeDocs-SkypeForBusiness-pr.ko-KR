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
ms.openlocfilehash: a0e82ae8a0dd9961bfeb9d2a513cb77b0affb2c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="6678f-102">Lync Server 2013에서 위치 기반 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="6678f-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6678f-103">_**마지막으로 수정한 주제:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="6678f-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="6678f-104">Lync Server 2013 CU1 위치 기반 라우팅은 엔터프라이즈 음성의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="6678f-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="6678f-105">위치 기반 라우팅은 Lync Server 2013 CU1에서 통화가 라우팅되는 방법을 제어 하는 통화 관리 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="6678f-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="6678f-106">Lync 발신자의 위치를 기반으로 통화를 PBX 또는 PSTN 목적지로 라우팅할 수 있는지에 대 한 제한 사항을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6678f-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="6678f-107">위치 기반 라우팅은 호출자의 네트워크 위치를 기반으로 하는 PSTN 통화에 대 한 통화 권한 부여 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6678f-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="6678f-108">호출자의 위치는 호출자가 연결 된 네트워크 서브넷과 연결 된 네트워크 사이트를 기준으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6678f-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="6678f-109">위치 기반 라우팅을 구성 하려면 먼저 엔터프라이즈 음성을 구축한 다음 네트워크 지역, 사이트 및 서브넷을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6678f-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="6678f-110">위치 기반 라우팅의 사용을 위한 토대를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6678f-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="6678f-111">위치 기반 라우팅을 배포 하기 전에 먼저 엔터프라이즈 음성을 배포 하 고 네트워크 지역, 사이트를 구성 하 고 네트워크 서브넷을 네트워크 사이트에 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6678f-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="6678f-112">완료 되 면 위치 기반 라우팅을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6678f-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="6678f-113">네트워크 지역, 사이트 및 서브넷을 구성 하는 방법에 대 한 단계는 [Lync Server 2013의 고급 엔터프라이즈 음성 기능 배포](lync-server-2013-deploying-advanced-enterprise-voice-features.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6678f-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="6678f-114">이 섹션에서는 다음 예제를 사용 하 여 위치 기반 라우팅의 구성 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="6678f-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="6678f-115">![Enterprise Voice 위치 기반 라우팅 예제](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice 위치 기반 라우팅 예제")</span><span class="sxs-lookup"><span data-stu-id="6678f-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="6678f-116">다음 표에서는이 예제에 정의 된 사용자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6678f-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6678f-117">끝점 형식</span><span class="sxs-lookup"><span data-stu-id="6678f-117">Endpoint type</span></span></th>
<th><span data-ttu-id="6678f-118">위치</span><span class="sxs-lookup"><span data-stu-id="6678f-118">Location</span></span></th>
<th><span data-ttu-id="6678f-119">사용자</span><span class="sxs-lookup"><span data-stu-id="6678f-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6678f-120">Lync</span><span class="sxs-lookup"><span data-stu-id="6678f-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="6678f-121">뉴델리 기업 사무실</span><span class="sxs-lookup"><span data-stu-id="6678f-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="6678f-122">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="6678f-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6678f-123">Lync</span><span class="sxs-lookup"><span data-stu-id="6678f-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="6678f-124">Hyderabad 기업 사무실</span><span class="sxs-lookup"><span data-stu-id="6678f-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="6678f-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="6678f-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6678f-126">Lync</span><span class="sxs-lookup"><span data-stu-id="6678f-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="6678f-127">알 수 없음 (예: 호텔)</span><span class="sxs-lookup"><span data-stu-id="6678f-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="6678f-128">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="6678f-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6678f-129">PBX</span><span class="sxs-lookup"><span data-stu-id="6678f-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="6678f-130">뉴델리 기업 사무실</span><span class="sxs-lookup"><span data-stu-id="6678f-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="6678f-131">DEL-PBX-1, DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="6678f-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6678f-132">PBX</span><span class="sxs-lookup"><span data-stu-id="6678f-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="6678f-133">Hyderabad 기업 사무실</span><span class="sxs-lookup"><span data-stu-id="6678f-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="6678f-134">HYD-PBX-1, HYD-2</span><span class="sxs-lookup"><span data-stu-id="6678f-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6678f-135">PSTN</span><span class="sxs-lookup"><span data-stu-id="6678f-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="6678f-136">없는</span><span class="sxs-lookup"><span data-stu-id="6678f-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="6678f-137">PSTN-1, PSTN-2, PSTN-3</span><span class="sxs-lookup"><span data-stu-id="6678f-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="6678f-138">다음 표는이 예제 환경에 제시 된 시스템을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6678f-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6678f-139">시스템이</span><span class="sxs-lookup"><span data-stu-id="6678f-139">System</span></span></th>
<th><span data-ttu-id="6678f-140">위치</span><span class="sxs-lookup"><span data-stu-id="6678f-140">Location</span></span></th>
<th><span data-ttu-id="6678f-141">이름</span><span class="sxs-lookup"><span data-stu-id="6678f-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6678f-142">Lync Server 2013 CU1 풀</span><span class="sxs-lookup"><span data-stu-id="6678f-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="6678f-143">이상</span><span class="sxs-lookup"><span data-stu-id="6678f-143">any</span></span></p></td>
<td><p><span data-ttu-id="6678f-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="6678f-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6678f-145">Lync Server 2013 CU1, 중재 서버</span><span class="sxs-lookup"><span data-stu-id="6678f-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="6678f-146">이상</span><span class="sxs-lookup"><span data-stu-id="6678f-146">any</span></span></p></td>
<td><p><span data-ttu-id="6678f-147">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="6678f-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6678f-148">PSTN 게이트웨이 1</span><span class="sxs-lookup"><span data-stu-id="6678f-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="6678f-149">뉴델리</span><span class="sxs-lookup"><span data-stu-id="6678f-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="6678f-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="6678f-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6678f-151">PSTN 게이트웨이 2</span><span class="sxs-lookup"><span data-stu-id="6678f-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="6678f-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="6678f-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="6678f-153">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="6678f-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6678f-154">PBX 1</span><span class="sxs-lookup"><span data-stu-id="6678f-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="6678f-155">뉴델리</span><span class="sxs-lookup"><span data-stu-id="6678f-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="6678f-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="6678f-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6678f-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="6678f-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="6678f-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="6678f-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="6678f-159">빨강-PBX</span><span class="sxs-lookup"><span data-stu-id="6678f-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="6678f-160">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="6678f-160">In This Section</span></span>

  - [<span data-ttu-id="6678f-161">Lync Server 2013에서 엔터프라이즈 음성 구성</span><span class="sxs-lookup"><span data-stu-id="6678f-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="6678f-162">Lync Server 2013에서 네트워크 지역, 사이트 및 서브넷 배포</span><span class="sxs-lookup"><span data-stu-id="6678f-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="6678f-163">Lync Server 2013에서 위치 기반 라우팅 사용</span><span class="sxs-lookup"><span data-stu-id="6678f-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6678f-164">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6678f-164">See Also</span></span>


[<span data-ttu-id="6678f-165">Lync Server 2013에서 고급 엔터프라이즈 음성 기능 배포</span><span class="sxs-lookup"><span data-stu-id="6678f-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

