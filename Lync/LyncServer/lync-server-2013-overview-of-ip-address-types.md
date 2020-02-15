---
title: 'Lync Server 2013: IP 주소 유형에 대 한 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: feb900c6f3d2ac426c184048986a7a751a205874
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="5dd74-102">Lync Server 2013의 IP 주소 유형 개요</span><span class="sxs-lookup"><span data-stu-id="5dd74-102">Overview of IP address types for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5dd74-103">_**마지막으로 수정 된 항목:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="5dd74-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="5dd74-104">Lync Server 2013에서 IP 주소를 구성할 때는 다음과 같은 세 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="5dd74-105">IP 버전 4 (IPv4), IP 버전 6 (IPv6) 또는 둘 다를 지원 하도록 Lync Server 2013을 구성할 수 있습니다 ( *이중 스택*이라고 함).</span><span class="sxs-lookup"><span data-stu-id="5dd74-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="5dd74-106">구성 유형마다 고려해야 할 몇 가지 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="5dd74-107">**Ipv4**   는 세계에서 ipv4 주소를 벗어나 실행 중 이므로 IPv6이 (가) 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="5dd74-108">궁극적으로 IPv6은 전 세계적으로 완벽 하 게 지원 되지만, 이때 엔터프라이즈가 통신 해야 하는 많은 회사 및 장치는 아직 i p v 6을 지원 하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="5dd74-109">IPv4 전용 구성은 Lync Server 구현이 대부분의 기존 장치와 통신할 수 있도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="5dd74-110">**Ipv6에만**   해당 되는 경우에는 전체 IPv6 구현에서 대부분의 기존 장치와의 통신을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="5dd74-111">**이중 스택**   이중 스택은 IPv4 및 IPv6 주소를 모두 사용 하도록 설정 된 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="5dd74-112">이 구성은 대부분의 경우 전체-IPv4에서 full-IPv6로 전환 하는 데는 몇 년이 소요 되기 때문에 Lync Server 2013에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="5dd74-113">다음 섹션에서는 다양 한 Lync Server 기능에 대 한 이러한 세 가지 구성 간의 호환성에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5dd74-p104">IPv6를 사용한 클라이언트 또는 서버 구성은 연구 또는 검사 목적으로만 지원됩니다. IPv6 전용 구성은 프로덕션 배포에는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="5dd74-116">클라이언트 등록</span><span class="sxs-lookup"><span data-stu-id="5dd74-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5dd74-117">클라이언트 끝점 네트워크</span><span class="sxs-lookup"><span data-stu-id="5dd74-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="5dd74-118">서버 네트워크</span><span class="sxs-lookup"><span data-stu-id="5dd74-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-119">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="5dd74-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd74-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="5dd74-122">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-123">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5dd74-124">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd74-125">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5dd74-126">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-127">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5dd74-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="5dd74-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd74-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="5dd74-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="5dd74-130">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="5dd74-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="5dd74-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="5dd74-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="5dd74-133">피어 투 피어 클라이언트</span><span class="sxs-lookup"><span data-stu-id="5dd74-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="5dd74-p105">피어 투 피어 통신에는 오디오, 오디오/비디오, 응용 프로그램 공유 및 파일 전송이 포함됩니다. 두 클라이언트가 성공적으로 등록된 후에는 다음 조합이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5dd74-136">클라이언트 끝점 1</span><span class="sxs-lookup"><span data-stu-id="5dd74-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="5dd74-137">클라이언트 끝점 2</span><span class="sxs-lookup"><span data-stu-id="5dd74-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-138">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="5dd74-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd74-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="5dd74-141">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-142">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5dd74-143">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd74-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="5dd74-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="5dd74-145">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="5dd74-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="5dd74-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="5dd74-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="5dd74-148">전화</span><span class="sxs-lookup"><span data-stu-id="5dd74-148">Conferencing</span></span>

<span data-ttu-id="5dd74-149">회의에는 오디오/비디오, 응용 프로그램 공유 및 데이터 공동 작업(화이트보드 및 파일 공유)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5dd74-150">클라이언트 끝점 네트워크</span><span class="sxs-lookup"><span data-stu-id="5dd74-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="5dd74-151">서버 네트워크</span><span class="sxs-lookup"><span data-stu-id="5dd74-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-152">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="5dd74-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd74-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="5dd74-155">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-156">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5dd74-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd74-158">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5dd74-159">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-160">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5dd74-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="5dd74-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd74-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="5dd74-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="5dd74-163">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="5dd74-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="5dd74-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="5dd74-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="5dd74-166">중재 서버/PSTN</span><span class="sxs-lookup"><span data-stu-id="5dd74-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="5dd74-167">Lync Server 2013에서는 트래픽이 IPv6 인터페이스를 통해 수행 되는 경우 공중 전화망 (PSTN) 통화에 대 한 미디어 바이패스를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="5dd74-168">미디어 바이패스가 필요할 경우 PSTN 게이트웨이를 IPv4로 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5dd74-169">기본 인터페이스\*</span><span class="sxs-lookup"><span data-stu-id="5dd74-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="5dd74-170">PSTN 인터페이스(중재 서버)</span><span class="sxs-lookup"><span data-stu-id="5dd74-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="5dd74-171">PSTN 게이트웨이 설정</span><span class="sxs-lookup"><span data-stu-id="5dd74-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="5dd74-173">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5dd74-174">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd74-175">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5dd74-176">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5dd74-177">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-178">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5dd74-179">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5dd74-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="5dd74-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5dd74-181">\*기본 인터페이스는 Lync Server 구성 요소와 통신 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="5dd74-182">원격 사용자 피어 투 피어 통신</span><span class="sxs-lookup"><span data-stu-id="5dd74-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="5dd74-183">원격 사용자와의 피어 투 피어 통신에는 인스턴트 메시징, 오디오/비디오, 응용 프로그램 공유 및 파일 전송이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5dd74-184">원격 사용자 네트워크</span><span class="sxs-lookup"><span data-stu-id="5dd74-184">Remote user network</span></span></th>
<th><span data-ttu-id="5dd74-185">에지 서버(외부 에지)</span><span class="sxs-lookup"><span data-stu-id="5dd74-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-186">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="5dd74-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd74-188">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5dd74-189">IPv4</span><span class="sxs-lookup"><span data-stu-id="5dd74-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-190">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="5dd74-191">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd74-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="5dd74-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="5dd74-193">이중 스택</span><span class="sxs-lookup"><span data-stu-id="5dd74-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="5dd74-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="5dd74-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="5dd74-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="5dd74-196">프런트 엔드 풀과 에지 풀 구성</span><span class="sxs-lookup"><span data-stu-id="5dd74-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="5dd74-197">다음 표에서는 프런트 엔드 서버 풀과 내부에 지 서버 풀 간의 지원 매트릭스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="5dd74-198">프런트 엔드 풀과 에지 풀(내부 에지) 매트릭스</span><span class="sxs-lookup"><span data-stu-id="5dd74-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="5dd74-199"><strong>에지 풀: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="5dd74-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="5dd74-200"><strong>에지 풀: 이중 스택</strong></span><span class="sxs-lookup"><span data-stu-id="5dd74-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="5dd74-201"><strong>에지 풀: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="5dd74-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd74-202"><strong>프런트 엔드 풀: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="5dd74-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="5dd74-203">예</span><span class="sxs-lookup"><span data-stu-id="5dd74-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dd74-204">예</span><span class="sxs-lookup"><span data-stu-id="5dd74-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dd74-205">아니요</span><span class="sxs-lookup"><span data-stu-id="5dd74-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-206"><strong>프런트 엔드 풀: 이중 스택</strong></span><span class="sxs-lookup"><span data-stu-id="5dd74-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="5dd74-207">예</span><span class="sxs-lookup"><span data-stu-id="5dd74-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dd74-208">예</span><span class="sxs-lookup"><span data-stu-id="5dd74-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dd74-209">아니요</span><span class="sxs-lookup"><span data-stu-id="5dd74-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd74-210"><strong>프런트 엔드 풀: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="5dd74-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="5dd74-211">아니요</span><span class="sxs-lookup"><span data-stu-id="5dd74-211">No</span></span></p></td>
<td><p><span data-ttu-id="5dd74-212">아니요</span><span class="sxs-lookup"><span data-stu-id="5dd74-212">No</span></span></p></td>
<td><p><span data-ttu-id="5dd74-213">예\*</span><span class="sxs-lookup"><span data-stu-id="5dd74-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5dd74-214">\*이 조합은 랩 환경 에서만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="5dd74-215">다음 표는 지원되는 내부 및 외부 에지 인터페이스 조합 매트릭스입니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="5dd74-216">에지 풀(내부 에지)과 에지 풀(외부 에지) 매트릭스</span><span class="sxs-lookup"><span data-stu-id="5dd74-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="5dd74-217"><strong>에지 풀(외부 에지) : IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="5dd74-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="5dd74-218"><strong>에지 풀(외부 에지): 이중 스택</strong></span><span class="sxs-lookup"><span data-stu-id="5dd74-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="5dd74-219"><strong>에지 풀(외부 에지) : IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="5dd74-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd74-220"><strong>에지 풀(내부 에지) : IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="5dd74-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="5dd74-221">예</span><span class="sxs-lookup"><span data-stu-id="5dd74-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dd74-222">예</span><span class="sxs-lookup"><span data-stu-id="5dd74-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dd74-223">아니요</span><span class="sxs-lookup"><span data-stu-id="5dd74-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dd74-224"><strong>에지 풀(내부 에지): 이중 스택</strong></span><span class="sxs-lookup"><span data-stu-id="5dd74-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="5dd74-225">아니요</span><span class="sxs-lookup"><span data-stu-id="5dd74-225">No</span></span></p></td>
<td><p><span data-ttu-id="5dd74-226">예</span><span class="sxs-lookup"><span data-stu-id="5dd74-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="5dd74-227">아니요</span><span class="sxs-lookup"><span data-stu-id="5dd74-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dd74-228"><strong>에지 풀(내부 에지) : IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="5dd74-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="5dd74-229">아니요</span><span class="sxs-lookup"><span data-stu-id="5dd74-229">No</span></span></p></td>
<td><p><span data-ttu-id="5dd74-230">아니요</span><span class="sxs-lookup"><span data-stu-id="5dd74-230">No</span></span></p></td>
<td><p><span data-ttu-id="5dd74-231">예\*</span><span class="sxs-lookup"><span data-stu-id="5dd74-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5dd74-232">\*이 조합은 랩 환경 에서만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="5dd74-233">IPv6에 대한 고급 Enterprise Voice 지원</span><span class="sxs-lookup"><span data-stu-id="5dd74-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="5dd74-234">CAC(통화 허용 제어 서비스), E9-1-1(고급 9-1-1) 또는 미디어 바이패스를 포함하는 배포는 IPv4 전용 또는 이중 스택 구현으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5dd74-235">이중 스택 배포에서 Lync 클라이언트가 i p v 6을 사용 하 여 Lync Server에 연결 하더라도 Lync에서는 적절 한 IPv4 주소를 E9-1-1을 지원 하도록 매핑하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="5dd74-236">IPv6 주소를 사용 하는 위치 정보 서비스는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="5dd74-p107">Exchange UM(통합 메시징)에서는 IPv6을 지원하지 않습니다. Exchange UM의 경우 DNS 확인 시 IPv6 주소가 반환되지 않습니다. IPv6을 사용하면 통화가 음성 사서함로 올바르게 전송될 때 실패할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="5dd74-240">IPv6에 대 한 기타 Lync Server 2013 기능 지원</span><span class="sxs-lookup"><span data-stu-id="5dd74-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="5dd74-241">앞에서 설명한 기능 및 구성 요소 외에도 Lync Server 2013에서는 다음 기능에 대해 i p v 6을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="5dd74-242">**영구 채팅**</span><span class="sxs-lookup"><span data-stu-id="5dd74-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="5dd74-243">토폴로지 작성기를 사용 하 여 영구 채팅을 위해 IPv6을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="5dd74-244">영구 채팅을 구성 하는 방법에 대 한 자세한 내용은 배포 영구 채팅 서버 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5dd74-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="5dd74-245">**QoE(체감 품질)과 CDR(통화 정보 기록) 보고서**</span><span class="sxs-lookup"><span data-stu-id="5dd74-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="5dd74-246">모니터링 보고서에는 IPv4 형식인지 IPv6 형식인지에 관계 없이 모니터링 서버 데이터베이스에 저장된 IP 주소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5dd74-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

