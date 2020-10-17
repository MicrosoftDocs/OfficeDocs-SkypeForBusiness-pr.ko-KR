---
title: 'Lync Server 2013: Location-Based 라우팅 및 문의 후 통화 전송'
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
ms.openlocfilehash: 75284736af1307aff4e9c51c8118cf64dbd08568
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513815"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="1d10d-102">Lync Server 2013의 라우팅 및 문의 후 통화 전송 Location-Based</span><span class="sxs-lookup"><span data-stu-id="1d10d-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d10d-103">_**마지막으로 수정 된 항목:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="1d10d-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="1d10d-104">Location-Based 라우팅 회의 응용 프로그램은 Lync 모임에 대 한 Location-Based 라우팅을 적용 하는 것 외에 PSTN 끝점으로 송신 되는 문의 후 통화 전송에 대 한 Location-Based 라우팅 제한이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="1d10d-105">문의 후 통화 전송은 두 당사자 중 한 사람이 새 사용자에 게 통화를 전송 하는 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="1d10d-106">예를 들어 PSTN 끝점이 사용자 A (Lync 수신자)를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="1d10d-107">사용자 A PSTN 사용자를 사용자 B (Lync 사용자)에 게 전달 해야 하는지 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="1d10d-108">사용자 A가 통화를 PSTN 사용자에 게 저장 하 고 사용자 B에 게 전화 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="1d10d-109">사용자 A는 통화 대기를 사용자 B에 게 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="1d10d-110">**통화 전송 통화 흐름 문의 후**</span><span class="sxs-lookup"><span data-stu-id="1d10d-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="1d10d-111">![회의 다이어그램의 위치 기반 라우팅](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "회의 다이어그램의 위치 기반 라우팅")</span><span class="sxs-lookup"><span data-stu-id="1d10d-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="1d10d-112">Location-Based 라우팅이 사용 하도록 설정 된 경우 이전 그림에 표시 된 것 처럼 PSTN 끝점의 통화 전송이 시작 되 면 두 개의 활성 통화, 즉 PSTN 사용자와 Lync 사용자 A 간의 통화, 그리고 Lync 사용자 A와 lync 사용자 B 간의 호출이 만들어집니다. Location-Based 라우팅 회의 응용 프로그램에서 다음 동작이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="1d10d-113">PSTN 통화에 대 한 SIP 트렁크 라우팅에 Lync 사용자 B (즉, 전송 대상)가 있는 네트워크 사이트로 PSTN 통화를 다시 라우팅할 수 있는 권한이 있는 경우에는 통화 전송이 허용 됩니다. 그렇지 않으면 문의 후 통화 전송이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="1d10d-114">이 인증은 현재 통화를 PSTN 끝점으로 라우팅하는 SIP 트렁크와 동일한 네트워크 사이트에 있는 전송 된 파티의 위치를 기반으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="1d10d-115">인바운드 PSTN 통화에 대 한 SIP 트렁크 라우팅에 전송 된 파티 (Lync user B)가 있는 네트워크 사이트로 통화를 라우팅할 권한이 없거나, 전송 된 파티가 알 수 없는 네트워크 사이트에 있는 경우에는 통화 전송 대상으로 PSTN 끝점으로 전송 되는 문의 후 호출이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="1d10d-116">다음 표에서는 문의 후 통화 전송에 대 한 Location-Based Routing 회의 응용 프로그램에서 Location-Based 라우팅 제한이 적용 되는 방식을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="1d10d-117">PBX 끝점이 네트워크 사이트에 직접 연결 되어 있지 않더라도 PBX에 연결 된 SIP 트렁크에 네트워크 사이트를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="1d10d-118">따라서 PBX 끝점이 네트워크 사이트에 간접적으로 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d10d-119">통화 전송 된 파티의 네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="1d10d-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="1d10d-120">통화 전송 대상의 네트워크 사이트</span><span class="sxs-lookup"><span data-stu-id="1d10d-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="1d10d-121">동작과</span><span class="sxs-lookup"><span data-stu-id="1d10d-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d10d-122">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="1d10d-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1d10d-123">같은 네트워크 사이트의 Lync 사용자 (예: 사이트 1)</span><span class="sxs-lookup"><span data-stu-id="1d10d-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="1d10d-124">문의 후 전송이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d10d-125">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="1d10d-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1d10d-126">서로 다른 네트워크 사이트의 Lync 사용자 (예: 사이트 2)</span><span class="sxs-lookup"><span data-stu-id="1d10d-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="1d10d-127">문의 후 전송을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d10d-128">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="1d10d-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1d10d-129">알 수 없는 네트워크 사이트의 Lync 사용자</span><span class="sxs-lookup"><span data-stu-id="1d10d-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="1d10d-130">문의 후 전송을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d10d-131">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="1d10d-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1d10d-132">페더레이션 Lync 사용자</span><span class="sxs-lookup"><span data-stu-id="1d10d-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="1d10d-133">문의 후 전송을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d10d-134">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="1d10d-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1d10d-135">동일한 사이트의 PBX 끝점 (예: 사이트 1)</span><span class="sxs-lookup"><span data-stu-id="1d10d-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="1d10d-136">문의 후 전송이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d10d-137">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="1d10d-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1d10d-138">다른 사이트의 PBX 끝점 (예: 사이트 2)</span><span class="sxs-lookup"><span data-stu-id="1d10d-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="1d10d-139">문의 후 전송을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d10d-140">동일한 사이트의 PBX 끝점 (예: 사이트 1)</span><span class="sxs-lookup"><span data-stu-id="1d10d-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="1d10d-141">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="1d10d-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1d10d-142">문의 후 전송이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d10d-143">다른 사이트의 PBX 끝점 (예: 사이트 2)</span><span class="sxs-lookup"><span data-stu-id="1d10d-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="1d10d-144">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="1d10d-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1d10d-145">문의 후 전송을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d10d-146">모든 사이트의 PBX 끝점</span><span class="sxs-lookup"><span data-stu-id="1d10d-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="1d10d-147">같은 네트워크 사이트의 Lync 사용자 (예: 사이트 1)</span><span class="sxs-lookup"><span data-stu-id="1d10d-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="1d10d-148">문의 후 전송이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d10d-149">모든 사이트의 PBX 끝점</span><span class="sxs-lookup"><span data-stu-id="1d10d-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="1d10d-150">서로 다른 네트워크 사이트의 Lync 사용자 (예: 사이트 2)</span><span class="sxs-lookup"><span data-stu-id="1d10d-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="1d10d-151">문의 후 전송이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d10d-152">모든 사이트의 PBX 끝점</span><span class="sxs-lookup"><span data-stu-id="1d10d-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="1d10d-153">알 수 없는 네트워크 사이트의 Lync 사용자</span><span class="sxs-lookup"><span data-stu-id="1d10d-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="1d10d-154">문의 후 전송이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d10d-155">모든 사이트의 PBX 끝점</span><span class="sxs-lookup"><span data-stu-id="1d10d-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="1d10d-156">페더레이션 Lync 사용자</span><span class="sxs-lookup"><span data-stu-id="1d10d-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="1d10d-157">문의 후 전송이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d10d-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

