---
title: 'Lync Server 2013: Location-Based 라우팅 및 문의 후 통화 전송'
description: 'Lync Server 2013: Location-Based 라우팅 및 문의 후 통화 전송입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d07cf6a33ff4d6ad57f8913a798fac3bc393a00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567674"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="af969-103">Lync Server 2013의 라우팅 및 문의 후 통화 전송 Location-Based</span><span class="sxs-lookup"><span data-stu-id="af969-103">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af969-104">_**마지막으로 수정 된 항목:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="af969-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="af969-105">Location-Based 라우팅 회의 응용 프로그램은 Lync 모임에 대 한 Location-Based 라우팅을 적용 하는 것 외에 PSTN 끝점으로 송신 되는 문의 후 통화 전송에 대 한 Location-Based 라우팅 제한이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af969-105">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="af969-106">문의 후 통화 전송은 두 당사자 중 한 사람이 새 사용자에 게 통화를 전송 하는 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="af969-106">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="af969-107">예를 들어 PSTN 끝점이 사용자 A (Lync 수신자)를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="af969-107">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="af969-108">사용자 A PSTN 사용자를 사용자 B (Lync 사용자)에 게 전달 해야 하는지 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af969-108">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="af969-109">사용자 A가 통화를 PSTN 사용자에 게 저장 하 고 사용자 B에 게 전화 합니다.</span><span class="sxs-lookup"><span data-stu-id="af969-109">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="af969-110">사용자 A는 통화 대기를 사용자 B에 게 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="af969-110">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="af969-111">**통화 전송 통화 흐름 문의 후**</span><span class="sxs-lookup"><span data-stu-id="af969-111">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="af969-112">![회의 다이어그램의 위치 기반 라우팅](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "회의 다이어그램의 위치 기반 라우팅")</span><span class="sxs-lookup"><span data-stu-id="af969-112">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="af969-113">Location-Based 라우팅이 사용 하도록 설정 된 경우 이전 그림에 표시 된 것 처럼 PSTN 끝점의 통화 전송이 시작 되 면 두 개의 활성 통화, 즉 PSTN 사용자와 Lync 사용자 A 간의 통화, 그리고 Lync 사용자 A와 lync 사용자 B 간의 호출이 만들어집니다. Location-Based 라우팅 회의 응용 프로그램에서 다음 동작이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af969-113">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="af969-114">PSTN 통화에 대 한 SIP 트렁크 라우팅에 Lync 사용자 B (즉, 전송 대상)가 있는 네트워크 사이트로 PSTN 통화를 다시 라우팅할 수 있는 권한이 있는 경우에는 통화 전송이 허용 됩니다. 그렇지 않으면 문의 후 통화 전송이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af969-114">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="af969-115">이 인증은 현재 통화를 PSTN 끝점으로 라우팅하는 SIP 트렁크와 동일한 네트워크 사이트에 있는 전송 된 파티의 위치를 기반으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af969-115">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="af969-116">인바운드 PSTN 통화에 대 한 SIP 트렁크 라우팅에 전송 된 파티 (Lync user B)가 있는 네트워크 사이트로 통화를 라우팅할 권한이 없거나, 전송 된 파티가 알 수 없는 네트워크 사이트에 있는 경우에는 통화 전송 대상으로 PSTN 끝점으로 전송 되는 문의 후 호출이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af969-116">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="af969-117">다음 표에서는 문의 후 통화 전송에 대 한 Location-Based Routing 회의 응용 프로그램에서 Location-Based 라우팅 제한이 적용 되는 방식을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="af969-117">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="af969-118">PBX 끝점이 네트워크 사이트에 직접 연결 되어 있지 않더라도 PBX에 연결 된 SIP 트렁크에 네트워크 사이트를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af969-118">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="af969-119">따라서 PBX 끝점이 네트워크 사이트에 간접적으로 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af969-119">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="af969-120">통화 전송 된 파티의 네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="af969-120">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="af969-121">통화 전송 대상의 네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="af969-121">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="af969-122">동작과</span><span class="sxs-lookup"><span data-stu-id="af969-122">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af969-123">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="af969-123">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="af969-124">같은 네트워크 사이트의 Lync 사용자 (예: 사이트 1)</span><span class="sxs-lookup"><span data-stu-id="af969-124">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="af969-125">문의 후 전송이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af969-125">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af969-126">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="af969-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="af969-127">서로 다른 네트워크 사이트의 Lync 사용자 (예: 사이트 2)</span><span class="sxs-lookup"><span data-stu-id="af969-127">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="af969-128">문의 후 전송을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af969-128">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af969-129">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="af969-129">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="af969-130">알 수 없는 네트워크 사이트의 Lync 사용자</span><span class="sxs-lookup"><span data-stu-id="af969-130">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="af969-131">문의 후 전송을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af969-131">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af969-132">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="af969-132">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="af969-133">페더레이션 Lync 사용자</span><span class="sxs-lookup"><span data-stu-id="af969-133">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="af969-134">문의 후 전송을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af969-134">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af969-135">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="af969-135">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="af969-136">동일한 사이트의 PBX 끝점 (예: 사이트 1)</span><span class="sxs-lookup"><span data-stu-id="af969-136">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="af969-137">문의 후 전송이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af969-137">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af969-138">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="af969-138">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="af969-139">다른 사이트의 PBX 끝점 (예: 사이트 2)</span><span class="sxs-lookup"><span data-stu-id="af969-139">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="af969-140">문의 후 전송을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af969-140">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af969-141">동일한 사이트의 PBX 끝점 (예: 사이트 1)</span><span class="sxs-lookup"><span data-stu-id="af969-141">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="af969-142">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="af969-142">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="af969-143">문의 후 전송이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af969-143">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af969-144">다른 사이트의 PBX 끝점 (예: 사이트 2)</span><span class="sxs-lookup"><span data-stu-id="af969-144">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="af969-145">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="af969-145">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="af969-146">문의 후 전송을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af969-146">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af969-147">모든 사이트의 PBX 끝점</span><span class="sxs-lookup"><span data-stu-id="af969-147">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="af969-148">같은 네트워크 사이트의 Lync 사용자 (예: 사이트 1)</span><span class="sxs-lookup"><span data-stu-id="af969-148">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="af969-149">문의 후 전송이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af969-149">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af969-150">모든 사이트의 PBX 끝점</span><span class="sxs-lookup"><span data-stu-id="af969-150">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="af969-151">서로 다른 네트워크 사이트의 Lync 사용자 (예: 사이트 2)</span><span class="sxs-lookup"><span data-stu-id="af969-151">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="af969-152">문의 후 전송이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af969-152">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="af969-153">모든 사이트의 PBX 끝점</span><span class="sxs-lookup"><span data-stu-id="af969-153">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="af969-154">알 수 없는 네트워크 사이트의 Lync 사용자</span><span class="sxs-lookup"><span data-stu-id="af969-154">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="af969-155">문의 후 전송이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af969-155">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="af969-156">모든 사이트의 PBX 끝점</span><span class="sxs-lookup"><span data-stu-id="af969-156">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="af969-157">페더레이션 Lync 사용자</span><span class="sxs-lookup"><span data-stu-id="af969-157">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="af969-158">문의 후 전송이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af969-158">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

