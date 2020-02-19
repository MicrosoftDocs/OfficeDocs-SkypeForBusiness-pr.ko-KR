---
title: 'Lync Server 2013: 위치 기반 라우팅을 위한 클라이언트 및 서버 지원'
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
ms.openlocfilehash: 3d78ae3fcfe9bd834fbddced1bdeccc20be45481
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="97e14-102">Lync Server 2013의 위치 기반 라우팅에 대 한 클라이언트 및 서버 지원</span><span class="sxs-lookup"><span data-stu-id="97e14-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97e14-103">_**마지막으로 수정 된 항목:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="97e14-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="97e14-104">Lync Server에서 위치 기반 라우팅이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97e14-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="97e14-105">Lync Server는 사용자가 회사 네트워크 내에서 연결 하는 네트워크 사이트를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97e14-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="97e14-106">원격 사용자는 회사 네트워크 외부에 있기 때문에 해당 위치를 알 수 없는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97e14-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="97e14-107">Lync Server 지원</span><span class="sxs-lookup"><span data-stu-id="97e14-107">Lync Server Support</span></span>

<span data-ttu-id="97e14-108">위치 기반 라우팅을 사용 하려면 Lync Server 2013 C U 1이 지정 된 토폴로지의 모든 프런트 엔드 풀 및 Standard Edition 서버에 배포 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97e14-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="97e14-109">Lync Server 2013 C U 1가 토폴로지의 특정 Lync 구성 요소에 설치 되어 있지 않으면 위치 기반 라우팅 제한을 완전히 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97e14-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="97e14-110">다음 표에는 위치 기반 라우팅에 대해 지원 되는 서버 역할 및 버전의 조합이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97e14-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97e14-111">풀 버전</span><span class="sxs-lookup"><span data-stu-id="97e14-111">Pool version</span></span></th>
<th><span data-ttu-id="97e14-112">중재 서버 버전</span><span class="sxs-lookup"><span data-stu-id="97e14-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="97e14-113">지원됨</span><span class="sxs-lookup"><span data-stu-id="97e14-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97e14-114">Lync Server 2013 2 월 2013 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="97e14-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="97e14-115">Lync Server 2013 2 월 2013 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="97e14-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="97e14-116">예</span><span class="sxs-lookup"><span data-stu-id="97e14-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e14-117">Lync Server 2013 2 월 2013 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="97e14-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="97e14-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97e14-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="97e14-119">아니요</span><span class="sxs-lookup"><span data-stu-id="97e14-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e14-120">Lync Server 2013 2 월 2013 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="97e14-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="97e14-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="97e14-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="97e14-122">아니요</span><span class="sxs-lookup"><span data-stu-id="97e14-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e14-123">Lync Server 2013 2 월 2013 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="97e14-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="97e14-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="97e14-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="97e14-125">아니요</span><span class="sxs-lookup"><span data-stu-id="97e14-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e14-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97e14-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="97e14-127">그</span><span class="sxs-lookup"><span data-stu-id="97e14-127">any</span></span></p></td>
<td><p><span data-ttu-id="97e14-128">아니요</span><span class="sxs-lookup"><span data-stu-id="97e14-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e14-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="97e14-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="97e14-130">그</span><span class="sxs-lookup"><span data-stu-id="97e14-130">any</span></span></p></td>
<td><p><span data-ttu-id="97e14-131">아니요</span><span class="sxs-lookup"><span data-stu-id="97e14-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e14-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="97e14-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="97e14-133">그</span><span class="sxs-lookup"><span data-stu-id="97e14-133">any</span></span></p></td>
<td><p><span data-ttu-id="97e14-134">아니요</span><span class="sxs-lookup"><span data-stu-id="97e14-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="97e14-135">Lync 클라이언트 지원</span><span class="sxs-lookup"><span data-stu-id="97e14-135">Lync Client Support</span></span>

<span data-ttu-id="97e14-136">다음 표에서는 위치 기반 라우팅이 지 원하는 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97e14-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97e14-137">클라이언트 유형</span><span class="sxs-lookup"><span data-stu-id="97e14-137">Client type</span></span></th>
<th><span data-ttu-id="97e14-138">지원됨</span><span class="sxs-lookup"><span data-stu-id="97e14-138">Supported</span></span></th>
<th><span data-ttu-id="97e14-139">세부 정보</span><span class="sxs-lookup"><span data-stu-id="97e14-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97e14-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="97e14-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="97e14-141">예</span><span class="sxs-lookup"><span data-stu-id="97e14-141">yes</span></span></p></td>
<td><p><span data-ttu-id="97e14-142">Lync 2013 년 2 월 2013 누적 업데이트 포함</span><span class="sxs-lookup"><span data-stu-id="97e14-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e14-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="97e14-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="97e14-144">예</span><span class="sxs-lookup"><span data-stu-id="97e14-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e14-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="97e14-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="97e14-146">아니요</span><span class="sxs-lookup"><span data-stu-id="97e14-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e14-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="97e14-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="97e14-148">예</span><span class="sxs-lookup"><span data-stu-id="97e14-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e14-149">Lync 전화 교환</span><span class="sxs-lookup"><span data-stu-id="97e14-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="97e14-150">예</span><span class="sxs-lookup"><span data-stu-id="97e14-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e14-151">Lync for Windows 8</span><span class="sxs-lookup"><span data-stu-id="97e14-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="97e14-152">아니요</span><span class="sxs-lookup"><span data-stu-id="97e14-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97e14-153">Lync 모바일 2013</span><span class="sxs-lookup"><span data-stu-id="97e14-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="97e14-154">아니요</span><span class="sxs-lookup"><span data-stu-id="97e14-154">no</span></span></p></td>
<td><p><span data-ttu-id="97e14-155">위치 기반 라우팅이 사용 하도록 설정 된 사용자가 사용 하는 경우 Lync 모바일 2013 클라이언트에 대해 VoIP를 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97e14-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97e14-156">Lync 모바일 2010</span><span class="sxs-lookup"><span data-stu-id="97e14-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="97e14-157">예</span><span class="sxs-lookup"><span data-stu-id="97e14-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="97e14-158">Lync Mobile 2013 클라이언트에 대해 VoIP를 사용 하지 않도록 설정 하려면 위치 기반 라우팅을 사용 하도록 설정 된 모든 사용자에 대해 IP 오디오/비디오 설정을 사용 하지 않고 모바일 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="97e14-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="97e14-159">모바일 정책에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">get-csmobilitypolicy</A>를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="97e14-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="97e14-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97e14-160">See Also</span></span>


[<span data-ttu-id="97e14-161">Lync Server 2013의 위치 기반 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="97e14-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

