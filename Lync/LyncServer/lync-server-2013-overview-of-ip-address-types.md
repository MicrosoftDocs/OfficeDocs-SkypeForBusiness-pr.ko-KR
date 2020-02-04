---
title: 'Lync Server 2013: IP 주소 유형의 개요'
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
ms.openlocfilehash: 9d1172fc7da9600de036312adb05548b51dea6b0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="0ff2c-102">Lync Server 2013에 대한 IP 주소 유형의 개요</span><span class="sxs-lookup"><span data-stu-id="0ff2c-102">Overview of IP address types for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ff2c-103">_**마지막으로 수정한 주제:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="0ff2c-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="0ff2c-104">Lync Server 2013에서 IP 주소를 구성할 때는 세 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="0ff2c-105">IP 버전 4 (IPv4)만 지원 하도록 Lync 서버 2013을 구성할 수 있으며 (IP 버전 6(Ipv6) 또는 둘 다 ( *이중 스택*이라고 함) 모두의 조합이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="0ff2c-106">각 구성 유형에 대해 고려해 야 할 몇 가지 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="0ff2c-107">**Ipv4**   는 ipv4 주소를 초과 하지 않기 때문에 IPv6만 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="0ff2c-108">궁극적으로 IPv6은 전세계에서 완벽 하 게 지원 되지만 이번에는 엔터프라이즈에서 아직 IPv6을 지원 하지 않는 것으로 통신 해야 하는 많은 회사 및 장치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="0ff2c-109">IPv4 전용 구성은 Lync 서버 구현이 대부분의 기존 장치와 통신할 수 있도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="0ff2c-110">**Ipv6에만**   해당 되는 경우, 전체 ipv6 구현은 지금 많은 기존 장치와의 통신을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="0ff2c-111">**이중 스택**   듀얼 스택은 IPv4 및 IPv6 주소를 모두 사용할 수 있는 네트워크입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="0ff2c-112">이 구성은 대부분의 경우 전체 IPv4에서 full-IPv6으로 전환 하는 데 몇 년이 소요 되므로 Lync Server 2013에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="0ff2c-113">다음 섹션에서는 다양 한 Lync Server 기능에 대 한 이러한 세 가지 구성 간의 호환성에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ff2c-114">IPv6을 사용 하는 클라이언트 또는 서버 구성은 랩 또는 유효성 검사 용도로만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-114">Client or server configuration with IPv6 only is supported only for lab or validation purposes.</span></span> <span data-ttu-id="0ff2c-115">IPv6 전용 구성은 프로덕션 배포에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-115">IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="0ff2c-116">클라이언트 등록</span><span class="sxs-lookup"><span data-stu-id="0ff2c-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ff2c-117">클라이언트 끝점 네트워크</span><span class="sxs-lookup"><span data-stu-id="0ff2c-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="0ff2c-118">서버 네트워크</span><span class="sxs-lookup"><span data-stu-id="0ff2c-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-119">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-120">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff2c-121">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-122">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-123">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-124">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff2c-125">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-126">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-127">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="0ff2c-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff2c-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="0ff2c-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-130">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="0ff2c-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="0ff2c-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="0ff2c-133">피어 투 피어 클라이언트</span><span class="sxs-lookup"><span data-stu-id="0ff2c-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="0ff2c-134">피어 투 피어 통신에는 오디오, 오디오/비디오, 응용 프로그램 공유, 파일 전송이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-134">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer.</span></span> <span data-ttu-id="0ff2c-135">두 클라이언트가 성공적으로 등록 되 면 다음 조합이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-135">After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ff2c-136">클라이언트 끝점 1</span><span class="sxs-lookup"><span data-stu-id="0ff2c-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="0ff2c-137">클라이언트 끝점 2</span><span class="sxs-lookup"><span data-stu-id="0ff2c-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-138">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-139">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff2c-140">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-141">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-142">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-143">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff2c-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="0ff2c-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-145">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="0ff2c-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="0ff2c-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="0ff2c-148">회의</span><span class="sxs-lookup"><span data-stu-id="0ff2c-148">Conferencing</span></span>

<span data-ttu-id="0ff2c-149">회의에는 오디오/비디오, 응용 프로그램 공유, 데이터 공동 작업 (whiteboarding 및 파일 공유)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ff2c-150">클라이언트 끝점 네트워크</span><span class="sxs-lookup"><span data-stu-id="0ff2c-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="0ff2c-151">서버 네트워크</span><span class="sxs-lookup"><span data-stu-id="0ff2c-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-152">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-153">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff2c-154">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-155">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-156">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-157">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff2c-158">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-159">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-160">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="0ff2c-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff2c-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="0ff2c-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-163">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="0ff2c-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="0ff2c-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="0ff2c-166">중재 서버/PSTN</span><span class="sxs-lookup"><span data-stu-id="0ff2c-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="0ff2c-167">Lync Server 2013는 트래픽이 IPv6 인터페이스를 사용 하는 경우에는 PSTN (공개 통신 네트워크) 호출의 미디어 바이패스를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="0ff2c-168">미디어 바이패스가 필요한 경우 PSTN 게이트웨이가 IPv4로 구성 되는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ff2c-169">기본 인터페이스 \*</span><span class="sxs-lookup"><span data-stu-id="0ff2c-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="0ff2c-170">PSTN 인터페이스 (중재 서버에서)</span><span class="sxs-lookup"><span data-stu-id="0ff2c-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="0ff2c-171">PSTN 게이트웨이 설정</span><span class="sxs-lookup"><span data-stu-id="0ff2c-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-172">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-173">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-174">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff2c-175">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-176">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-177">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-178">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-179">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="0ff2c-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0ff2c-181">\*기본 인터페이스는 Lync Server 구성 요소와 통신 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="0ff2c-182">원격 사용자 피어 투 피어 통신</span><span class="sxs-lookup"><span data-stu-id="0ff2c-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="0ff2c-183">원격 사용자와의 피어 투 피어 통신에는 인스턴트 메시지, 오디오/비디오, 응용 프로그램 공유, 파일 전송 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ff2c-184">원격 사용자 네트워크</span><span class="sxs-lookup"><span data-stu-id="0ff2c-184">Remote user network</span></span></th>
<th><span data-ttu-id="0ff2c-185">Edge 서버 (외부 가장자리)</span><span class="sxs-lookup"><span data-stu-id="0ff2c-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-186">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-187">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff2c-188">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-189">(Ipv4</span><span class="sxs-lookup"><span data-stu-id="0ff2c-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-190">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-191">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff2c-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="0ff2c-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-193">이중 스택</span><span class="sxs-lookup"><span data-stu-id="0ff2c-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="0ff2c-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="0ff2c-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="0ff2c-196">프런트 엔드 풀 및 Edge 풀 구성</span><span class="sxs-lookup"><span data-stu-id="0ff2c-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="0ff2c-197">다음 표에는 프런트 엔드 서버 풀과 내부 Edge 서버 풀 사이의 지원 행렬이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="0ff2c-198">프런트 엔드 풀 및 Edge 풀 (내부에 지) 행렬</span><span class="sxs-lookup"><span data-stu-id="0ff2c-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="0ff2c-199"><strong>Edge 풀: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="0ff2c-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff2c-200"><strong>Edge 풀: 이중 스택</strong></span><span class="sxs-lookup"><span data-stu-id="0ff2c-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff2c-201"><strong>Edge 풀: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="0ff2c-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff2c-202"><strong>프런트 엔드 풀: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="0ff2c-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff2c-203">예</span><span class="sxs-lookup"><span data-stu-id="0ff2c-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-204">예</span><span class="sxs-lookup"><span data-stu-id="0ff2c-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-205">아니요</span><span class="sxs-lookup"><span data-stu-id="0ff2c-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-206"><strong>프런트 엔드 풀: 이중 스택</strong></span><span class="sxs-lookup"><span data-stu-id="0ff2c-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff2c-207">예</span><span class="sxs-lookup"><span data-stu-id="0ff2c-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-208">예</span><span class="sxs-lookup"><span data-stu-id="0ff2c-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-209">아니요</span><span class="sxs-lookup"><span data-stu-id="0ff2c-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff2c-210"><strong>프런트 엔드 풀: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="0ff2c-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff2c-211">아니요</span><span class="sxs-lookup"><span data-stu-id="0ff2c-211">No</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-212">아니요</span><span class="sxs-lookup"><span data-stu-id="0ff2c-212">No</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-213">'</span><span class="sxs-lookup"><span data-stu-id="0ff2c-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0ff2c-214">\*랩 환경 에서만이 조합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="0ff2c-215">다음 표는 내부 및 외부 경계 인터페이스의 지원 되는 조합의 행렬입니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="0ff2c-216">Edge 풀 (내부에 지) 및 Edge 풀 (외부 가장자리) 행렬</span><span class="sxs-lookup"><span data-stu-id="0ff2c-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="0ff2c-217"><strong>Edge 풀 (외부 가장자리): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="0ff2c-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff2c-218"><strong>Edge 풀 (외부 가장자리): 이중 스택</strong></span><span class="sxs-lookup"><span data-stu-id="0ff2c-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff2c-219"><strong>Edge 풀 (외부에 지): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="0ff2c-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff2c-220"><strong>Edge 풀 (내부에 지): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="0ff2c-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff2c-221">예</span><span class="sxs-lookup"><span data-stu-id="0ff2c-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-222">예</span><span class="sxs-lookup"><span data-stu-id="0ff2c-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-223">아니요</span><span class="sxs-lookup"><span data-stu-id="0ff2c-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ff2c-224"><strong>Edge 풀 (내부에 지): 이중 스택</strong></span><span class="sxs-lookup"><span data-stu-id="0ff2c-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff2c-225">아니요</span><span class="sxs-lookup"><span data-stu-id="0ff2c-225">No</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-226">예</span><span class="sxs-lookup"><span data-stu-id="0ff2c-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-227">아니요</span><span class="sxs-lookup"><span data-stu-id="0ff2c-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ff2c-228"><strong>Edge 풀 (내부에 지): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="0ff2c-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="0ff2c-229">아니요</span><span class="sxs-lookup"><span data-stu-id="0ff2c-229">No</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-230">아니요</span><span class="sxs-lookup"><span data-stu-id="0ff2c-230">No</span></span></p></td>
<td><p><span data-ttu-id="0ff2c-231">'</span><span class="sxs-lookup"><span data-stu-id="0ff2c-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0ff2c-232">\*랩 환경 에서만이 조합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="0ff2c-233">IPv6에 대 한 고급 엔터프라이즈 음성 지원</span><span class="sxs-lookup"><span data-stu-id="0ff2c-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="0ff2c-234">CAC (호출 허용 제어), 향상 된 9-1-1 (E9-1-1) 또는 미디어 바이패스를 포함 하는 배포는 IPv4 전용 또는 듀얼 누적 구현으로 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ff2c-235">듀얼 누적 배포의 경우 Lync 클라이언트가 IPv6을 사용 하 여 Lync Server에 연결 하는 경우에도 Lync는 E9-1-1을 지원 하기 위해 적절 한 IPv4 주소를 매핑하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="0ff2c-236">IPv6 주소를 사용 하는 위치 정보 서비스는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="0ff2c-237">UM (통합 메시징)는 IPv6을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-237">Exchange Unified Messaging (UM) does not support IPv6.</span></span> <span data-ttu-id="0ff2c-238">Exchange UM의 경우 DNS 확인이 IPv6 주소를 반환 하지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-238">For Exchange UM, be sure that DNS resolution does not return an IPv6 address.</span></span> <span data-ttu-id="0ff2c-239">전화를 음성 메일로 보내면 IPv6을 사용 하면 오류를 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-239">Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="0ff2c-240">IPv6에 대 한 다른 Lync Server 2013 기능 지원</span><span class="sxs-lookup"><span data-stu-id="0ff2c-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="0ff2c-241">이전에 언급 한 기능 및 구성 요소 외에도 Lync Server 2013는 다음 기능에 대 한 IPv6을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="0ff2c-242">**영구 채팅**</span><span class="sxs-lookup"><span data-stu-id="0ff2c-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="0ff2c-243">토폴로지 작성기를 사용 하 여 영구 채팅을 위해 IPv6을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="0ff2c-244">영구 채팅 구성에 대 한 자세한 내용은 영구 채팅 서버 배포 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="0ff2c-245">**경력 (체감 품질) 및 통화 정보 기록 (CDR) 보고서**</span><span class="sxs-lookup"><span data-stu-id="0ff2c-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="0ff2c-246">모니터링 보고서에는 IPv4 또는 IPv6 유형에 관계 없이 모니터링 서버 데이터베이스에 저장 되는 IP 주소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ff2c-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

