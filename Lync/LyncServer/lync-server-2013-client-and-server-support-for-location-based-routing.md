---
title: 'Lync Server 2013: Location-Based 라우팅을 위한 클라이언트 및 서버 지원'
description: 'Lync Server 2013: Location-Based 라우팅을 위한 클라이언트 및 서버 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20dca7444f58ee62dbc36edbb7d9e1c976a97807
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549634"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="76b2e-103">Lync Server 2013의 Location-Based 라우팅에 대 한 클라이언트 및 서버 지원</span><span class="sxs-lookup"><span data-stu-id="76b2e-103">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76b2e-104">_**마지막으로 수정 된 항목:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="76b2e-104">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="76b2e-105">Location-Based 라우팅은 Lync Server에 의해 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76b2e-105">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="76b2e-106">Lync Server는 사용자가 회사 네트워크 내에서 연결 하는 네트워크 사이트를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76b2e-106">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="76b2e-107">원격 사용자는 회사 네트워크 외부에 있기 때문에 해당 위치를 알 수 없는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76b2e-107">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="76b2e-108">Lync Server 지원</span><span class="sxs-lookup"><span data-stu-id="76b2e-108">Lync Server Support</span></span>

<span data-ttu-id="76b2e-109">Location-Based를 라우팅 하려면 Lync Server 2013 C U 1이 지정 된 토폴로지의 모든 프런트 엔드 풀 및 Standard Edition 서버에 배포 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76b2e-109">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="76b2e-110">Lync Server 2013 C U 1가 토폴로지의 특정 Lync 구성 요소에 설치 되어 있지 않으면 Location-Based 라우팅 제한을 완전히 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76b2e-110">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="76b2e-111">다음 표에는 Location-Based 라우팅에 대해 지원 되는 서버 역할 및 버전의 조합이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76b2e-111">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76b2e-112">풀 버전</span><span class="sxs-lookup"><span data-stu-id="76b2e-112">Pool version</span></span></th>
<th><span data-ttu-id="76b2e-113">중재 서버 버전</span><span class="sxs-lookup"><span data-stu-id="76b2e-113">Mediation Server version</span></span></th>
<th><span data-ttu-id="76b2e-114">지원</span><span class="sxs-lookup"><span data-stu-id="76b2e-114">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76b2e-115">Lync Server 2013 2 월 2013 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="76b2e-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="76b2e-116">Lync Server 2013 2 월 2013 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="76b2e-116">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="76b2e-117">예</span><span class="sxs-lookup"><span data-stu-id="76b2e-117">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76b2e-118">Lync Server 2013 2 월 2013 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="76b2e-118">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="76b2e-119">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76b2e-119">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="76b2e-120">아니요</span><span class="sxs-lookup"><span data-stu-id="76b2e-120">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76b2e-121">Lync Server 2013 2 월 2013 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="76b2e-121">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="76b2e-122">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="76b2e-122">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="76b2e-123">아니요</span><span class="sxs-lookup"><span data-stu-id="76b2e-123">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76b2e-124">Lync Server 2013 2 월 2013 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="76b2e-124">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="76b2e-125">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="76b2e-125">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="76b2e-126">아니요</span><span class="sxs-lookup"><span data-stu-id="76b2e-126">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76b2e-127">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76b2e-127">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="76b2e-128">그</span><span class="sxs-lookup"><span data-stu-id="76b2e-128">any</span></span></p></td>
<td><p><span data-ttu-id="76b2e-129">아니요</span><span class="sxs-lookup"><span data-stu-id="76b2e-129">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76b2e-130">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="76b2e-130">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="76b2e-131">그</span><span class="sxs-lookup"><span data-stu-id="76b2e-131">any</span></span></p></td>
<td><p><span data-ttu-id="76b2e-132">아니요</span><span class="sxs-lookup"><span data-stu-id="76b2e-132">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76b2e-133">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="76b2e-133">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="76b2e-134">그</span><span class="sxs-lookup"><span data-stu-id="76b2e-134">any</span></span></p></td>
<td><p><span data-ttu-id="76b2e-135">아니요</span><span class="sxs-lookup"><span data-stu-id="76b2e-135">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="76b2e-136">Lync 클라이언트 지원</span><span class="sxs-lookup"><span data-stu-id="76b2e-136">Lync Client Support</span></span>

<span data-ttu-id="76b2e-137">다음 표에서는 Location-Based 라우팅이 지 원하는 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="76b2e-137">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76b2e-138">클라이언트 유형</span><span class="sxs-lookup"><span data-stu-id="76b2e-138">Client type</span></span></th>
<th><span data-ttu-id="76b2e-139">지원</span><span class="sxs-lookup"><span data-stu-id="76b2e-139">Supported</span></span></th>
<th><span data-ttu-id="76b2e-140">세부 정보</span><span class="sxs-lookup"><span data-stu-id="76b2e-140">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76b2e-141">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="76b2e-141">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="76b2e-142">예</span><span class="sxs-lookup"><span data-stu-id="76b2e-142">yes</span></span></p></td>
<td><p><span data-ttu-id="76b2e-143">Lync 2013 년 2 월 2013 누적 업데이트 포함</span><span class="sxs-lookup"><span data-stu-id="76b2e-143">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76b2e-144">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="76b2e-144">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="76b2e-145">예</span><span class="sxs-lookup"><span data-stu-id="76b2e-145">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76b2e-146">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="76b2e-146">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="76b2e-147">아니요</span><span class="sxs-lookup"><span data-stu-id="76b2e-147">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76b2e-148">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="76b2e-148">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="76b2e-149">예</span><span class="sxs-lookup"><span data-stu-id="76b2e-149">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76b2e-150">Lync 전화 교환</span><span class="sxs-lookup"><span data-stu-id="76b2e-150">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="76b2e-151">예</span><span class="sxs-lookup"><span data-stu-id="76b2e-151">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76b2e-152">Lync for Windows 8</span><span class="sxs-lookup"><span data-stu-id="76b2e-152">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="76b2e-153">아니요</span><span class="sxs-lookup"><span data-stu-id="76b2e-153">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76b2e-154">Lync 모바일 2013</span><span class="sxs-lookup"><span data-stu-id="76b2e-154">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="76b2e-155">아니요</span><span class="sxs-lookup"><span data-stu-id="76b2e-155">no</span></span></p></td>
<td><p><span data-ttu-id="76b2e-156">Location-Based 라우팅이 사용 하도록 설정 된 사용자가 사용 하는 경우 Lync 모바일 2013 클라이언트에 대해 VoIP를 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76b2e-156">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76b2e-157">Lync 모바일 2010</span><span class="sxs-lookup"><span data-stu-id="76b2e-157">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="76b2e-158">예</span><span class="sxs-lookup"><span data-stu-id="76b2e-158">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="76b2e-159">Lync Mobile 2013 클라이언트에 대해 VoIP를 사용 하지 않도록 설정 하려면 위치 기반 라우팅을 사용 하도록 설정 된 모든 사용자에 대해 IP 오디오/비디오 설정을 사용 하지 않고 모바일 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="76b2e-159">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="76b2e-160">모바일 정책에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">get-csmobilitypolicy</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="76b2e-160">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="76b2e-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76b2e-161">See Also</span></span>


[<span data-ttu-id="76b2e-162">Lync Server 2013의 Location-Based 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="76b2e-162">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

