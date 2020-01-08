---
title: 'Lync Server 2013: 위치 기반 라우팅을 위한 클라이언트 및 서버 지원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3791b359422c4b5bef463a612db6f0b74c07f096
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="a9dc6-102">Lync Server 2013의 위치 기반 라우팅을 위한 클라이언트 및 서버 지원</span><span class="sxs-lookup"><span data-stu-id="a9dc6-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9dc6-103">_**마지막으로 수정한 주제:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="a9dc6-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="a9dc6-104">위치 기반 라우팅은 Lync Server에 의해 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9dc6-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="a9dc6-105">Lync Server는 사용자가 회사 네트워크 내에서 연결 하는 네트워크 사이트를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9dc6-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="a9dc6-106">원격 사용자는 회사 네트워크 외부에 있기 때문에 해당 위치는 알 수 없는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9dc6-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="a9dc6-107">Lync 서버 지원</span><span class="sxs-lookup"><span data-stu-id="a9dc6-107">Lync Server Support</span></span>

<span data-ttu-id="a9dc6-108">위치 기반 라우팅에는 Lync Server 2013 CU1이 지정 된 토폴로지의 모든 프런트 엔드 풀 및 Standard Edition 서버에 배포 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9dc6-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="a9dc6-109">Lync Server 2013 CU1이 토폴로지의 특정 Lync 구성 요소에 설치 되어 있지 않은 경우 위치 기반 라우팅 제한을 완전히 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9dc6-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="a9dc6-110">다음 표에서는 위치 기반 라우팅에 대해 지원 되는 서버 역할 및 버전의 조합을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9dc6-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9dc6-111">풀 버전</span><span class="sxs-lookup"><span data-stu-id="a9dc6-111">Pool version</span></span></th>
<th><span data-ttu-id="a9dc6-112">중재 서버 버전</span><span class="sxs-lookup"><span data-stu-id="a9dc6-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="a9dc6-113">지원</span><span class="sxs-lookup"><span data-stu-id="a9dc6-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9dc6-114">Lync Server 2013 2013 2 월 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="a9dc6-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-115">Lync Server 2013 2013 2 월 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="a9dc6-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-116">'</span><span class="sxs-lookup"><span data-stu-id="a9dc6-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9dc6-117">Lync Server 2013 2013 2 월 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="a9dc6-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9dc6-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-119">아니요</span><span class="sxs-lookup"><span data-stu-id="a9dc6-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9dc6-120">Lync Server 2013 2013 2 월 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="a9dc6-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a9dc6-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-122">아니요</span><span class="sxs-lookup"><span data-stu-id="a9dc6-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9dc6-123">Lync Server 2013 2013 2 월 누적 업데이트</span><span class="sxs-lookup"><span data-stu-id="a9dc6-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="a9dc6-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-125">아니요</span><span class="sxs-lookup"><span data-stu-id="a9dc6-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9dc6-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9dc6-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-127">이상</span><span class="sxs-lookup"><span data-stu-id="a9dc6-127">any</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-128">아니요</span><span class="sxs-lookup"><span data-stu-id="a9dc6-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9dc6-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a9dc6-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-130">이상</span><span class="sxs-lookup"><span data-stu-id="a9dc6-130">any</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-131">아니요</span><span class="sxs-lookup"><span data-stu-id="a9dc6-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9dc6-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="a9dc6-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-133">이상</span><span class="sxs-lookup"><span data-stu-id="a9dc6-133">any</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-134">아니요</span><span class="sxs-lookup"><span data-stu-id="a9dc6-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="a9dc6-135">Lync 클라이언트 지원</span><span class="sxs-lookup"><span data-stu-id="a9dc6-135">Lync Client Support</span></span>

<span data-ttu-id="a9dc6-136">다음 표에서는 위치 기반 라우팅이 지 원하는 클라이언트를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9dc6-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9dc6-137">클라이언트 유형</span><span class="sxs-lookup"><span data-stu-id="a9dc6-137">Client type</span></span></th>
<th><span data-ttu-id="a9dc6-138">지원</span><span class="sxs-lookup"><span data-stu-id="a9dc6-138">Supported</span></span></th>
<th><span data-ttu-id="a9dc6-139">세부적인</span><span class="sxs-lookup"><span data-stu-id="a9dc6-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9dc6-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="a9dc6-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-141">'</span><span class="sxs-lookup"><span data-stu-id="a9dc6-141">yes</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-142">Lync 2013 2 월 2013 누적 업데이트 포함</span><span class="sxs-lookup"><span data-stu-id="a9dc6-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9dc6-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="a9dc6-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-144">'</span><span class="sxs-lookup"><span data-stu-id="a9dc6-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9dc6-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="a9dc6-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-146">아니요</span><span class="sxs-lookup"><span data-stu-id="a9dc6-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9dc6-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="a9dc6-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-148">'</span><span class="sxs-lookup"><span data-stu-id="a9dc6-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9dc6-149">Lync 전화 교환</span><span class="sxs-lookup"><span data-stu-id="a9dc6-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-150">'</span><span class="sxs-lookup"><span data-stu-id="a9dc6-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9dc6-151">Windows 8 용 Lync</span><span class="sxs-lookup"><span data-stu-id="a9dc6-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-152">아니요</span><span class="sxs-lookup"><span data-stu-id="a9dc6-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9dc6-153">Lync 모바일 2013</span><span class="sxs-lookup"><span data-stu-id="a9dc6-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-154">아니요</span><span class="sxs-lookup"><span data-stu-id="a9dc6-154">no</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-155">위치 기반 라우팅이 설정 된 사용자가 사용 하는 경우 Lync 모바일 2013 클라이언트에 대해 VoIP를 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9dc6-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9dc6-156">Lync 모바일 2010</span><span class="sxs-lookup"><span data-stu-id="a9dc6-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="a9dc6-157">'</span><span class="sxs-lookup"><span data-stu-id="a9dc6-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="a9dc6-158">Lync Mobile 2013 클라이언트에 대 한 VoIP를 사용 하지 않도록 설정 하려면 위치 기반 라우팅에 대해 사용 하도록 설정 된 모든 사용자에 대해 IP 오디오/비디오 설정을 사용 하지 않도록 모바일 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9dc6-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="a9dc6-159">모바일 정책에 대 한 자세한 내용은 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9dc6-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a9dc6-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9dc6-160">See Also</span></span>


[<span data-ttu-id="a9dc6-161">Lync Server 2013의 위치 기반 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="a9dc6-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

