---
title: 'Lync Server 2013: 회의에 대 한 Location-Based 라우팅을 위한 요구 사항'
description: 'Lync Server 2013: 회의에 대 한 Location-Based 라우팅을 위한 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbaa1af2690c3148d2ecfb173b13be288a21d80f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542524"
---
# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="a0cce-103">Lync Server 2013에서 회의에 대 한 Location-Based 라우팅을 위한 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0cce-103">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0cce-104">_**마지막으로 수정 된 항목:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="a0cce-104">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="a0cce-105">Location-Based 라우팅 회의 응용 프로그램을 설치 하 고 구성 하는 데 필요한 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-105">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="a0cce-106">Lync Server 2013 누적 업데이트 2는 토폴로지의 모든 서버 또는 풀에 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-106">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a0cce-107">토폴로지의 Lync server 또는 풀에 Lync Server 2013 누적 업데이트 2 이상이 설치 되어 있지 않은 경우 Lync 모임에 대 한 Location-Based 라우팅을 적용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-107">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="a0cce-108">Lync Server 2013 Location-Based 라우팅은 Location-Based 라우팅 회의 응용 프로그램에 대 한 사전 필수 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-108">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="a0cce-109">Lync Server 2013 Location-Based 라우팅을 구성 하는 방법에 대 한 자세한 내용은 [Location-Based 라우팅 구성을](lync-server-2013-configuring-location-based-routing.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a0cce-109">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="a0cce-110">Location-Based 라우팅 회의 응용 프로그램의 요구 사항은 Lync Server 2013 Location-Based 라우팅에 대 한 요구 사항과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-110">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="a0cce-111">자세한 내용은 [Location-Based 라우팅 계획](lync-server-2013-planning-for-location-based-routing.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a0cce-111">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="a0cce-112">지원 되는 서버</span><span class="sxs-lookup"><span data-stu-id="a0cce-112">Supported Servers</span></span>

<span data-ttu-id="a0cce-113">Location-Based 라우팅 회의 응용 프로그램을 사용 하려면 토폴로지의 모든 Front-End 풀 및 Standard Edition 서버에 Lync Server 2013 누적 업데이트 2가 배포 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-113">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="a0cce-114">Lync Server 2013 누적 업데이트 2가 Location-Based 토폴로지의 일부 Lync 서버에 설치 되어 있지 않은 경우 Lync 모임 및 문의 후 통화 전송에 대 한 라우팅 제한을 완전히 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-114">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="a0cce-115">다음 표에는 Location-Based 라우팅을 지 원하는 서버 역할 및 버전의 조합이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-115">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0cce-116">Front-End 풀 버전</span><span class="sxs-lookup"><span data-stu-id="a0cce-116">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="a0cce-117">중재 서버 버전</span><span class="sxs-lookup"><span data-stu-id="a0cce-117">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="a0cce-118">지원</span><span class="sxs-lookup"><span data-stu-id="a0cce-118">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0cce-119">Lync Server 2013 누적 업데이트 2</span><span class="sxs-lookup"><span data-stu-id="a0cce-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="a0cce-120">Lync Server 2013 누적 업데이트 2</span><span class="sxs-lookup"><span data-stu-id="a0cce-120">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="a0cce-121">예</span><span class="sxs-lookup"><span data-stu-id="a0cce-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0cce-122">Lync Server 2013 누적 업데이트 2</span><span class="sxs-lookup"><span data-stu-id="a0cce-122">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="a0cce-123">Lync Server 2013 누적 업데이트 1</span><span class="sxs-lookup"><span data-stu-id="a0cce-123">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="a0cce-124">아니요</span><span class="sxs-lookup"><span data-stu-id="a0cce-124">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0cce-125">Lync Server 2013 누적 업데이트 2</span><span class="sxs-lookup"><span data-stu-id="a0cce-125">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="a0cce-126">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a0cce-126">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="a0cce-127">아니요</span><span class="sxs-lookup"><span data-stu-id="a0cce-127">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0cce-128">Lync Server 2013 누적 업데이트 2</span><span class="sxs-lookup"><span data-stu-id="a0cce-128">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="a0cce-129">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="a0cce-129">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="a0cce-130">아니요</span><span class="sxs-lookup"><span data-stu-id="a0cce-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0cce-131">Lync Server 2013 누적 업데이트 1</span><span class="sxs-lookup"><span data-stu-id="a0cce-131">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="a0cce-132">모두</span><span class="sxs-lookup"><span data-stu-id="a0cce-132">Any</span></span></p></td>
<td><p><span data-ttu-id="a0cce-133">아니요</span><span class="sxs-lookup"><span data-stu-id="a0cce-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0cce-134">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a0cce-134">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="a0cce-135">모두</span><span class="sxs-lookup"><span data-stu-id="a0cce-135">Any</span></span></p></td>
<td><p><span data-ttu-id="a0cce-136">아니요</span><span class="sxs-lookup"><span data-stu-id="a0cce-136">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0cce-137">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="a0cce-137">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="a0cce-138">모두</span><span class="sxs-lookup"><span data-stu-id="a0cce-138">Any</span></span></p></td>
<td><p><span data-ttu-id="a0cce-139">아니요</span><span class="sxs-lookup"><span data-stu-id="a0cce-139">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="a0cce-140">지원 되는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="a0cce-140">Supported Clients</span></span>

<span data-ttu-id="a0cce-141">Lync meeting Location-Based 라우팅을 지 원하는 Lync 클라이언트는 Lync Server 2013 Location-Based 라우팅을 지 원하는 것과 동일한 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-141">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="a0cce-142">자세한 내용은 [클라이언트 및 서버 지원에서 Location-Based 라우팅을](lync-server-2013-client-and-server-support-for-location-based-routing.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a0cce-142">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="a0cce-143">문의 후 통화 전송에 대 한 중재 서버 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0cce-143">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="a0cce-144">Location-Based 라우팅 회의 응용 프로그램을 사용 하려면 문의 후 call 전송에 Location-Based 라우팅 제한을 적용 하기 위해 독립 실행형 중재 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-144">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="a0cce-145">문의 후 통화 전송의 Location-Based 라우팅을 적용 하려면 중재 서버가 Location-Based 라우팅이 필요한 네트워크 지역에서 하나의 중재 서버 피어 (예: PBX, SIP 게이트웨이 등)에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-145">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="a0cce-146">추가 중재 서버 피어가 같은 네트워크 지역에 배포 되는 경우 중재 서버 피어는 다른 중재 서버에 연결 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-146">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="a0cce-147">이 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-147">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="a0cce-148">여러 중재 서버 피어에 대 한 단일 중재 서버 문의 후 호출 전송이 여러 피어 (예: Pbx 및 게이트웨이)로 구성 된 중재 서버를 통해 중재 서버 피어로 라우팅되는 경우, 문의 후 통화 전송이 일부 SIP 트렁크를 허용 하지만 다른 SIP 트렁크를 통해서는 허용 되지 않는 경우 PSTN을 우회 하지 않도록 문의 후 호출 전송이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-148">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="a0cce-149">예를 들어 PSTN 게이트웨이 중재 서버 피어 및 PBX 중재 서버 피어를 제공 하는 단일 중재 서버의 경우에는 다음과 같은 동작이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-149">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="a0cce-150">지정 된 사이트 (예: 사이트 1)의 Lync 사용자가 문의 후 전송을 통해 다른 사이트 (즉, 사이트 2)의 Lync 사용자에 게 PSTN 끝점을 사용 하 여 통화를 전송 하려고 하면 PSTN 전화 바이패스를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="a0cce-151">지정 된 사이트 (즉, 1)의 Lync 사용자가 같은 사이트 (즉, 사이트 1)에서 PBX 끝점이 있는 통화를 다른 사이트 (즉, 사이트 2)의 온-문의 후 transfer를 통해 Lync 사용자에 게 전송 하려고 하면 잠재적인 PSTN 무료 수신에 대 한 전화가 발생 하지 않더라도 통화를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-151">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="a0cce-152">중재 서버 피어 당 별도의 중재 서버</span><span class="sxs-lookup"><span data-stu-id="a0cce-152">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="a0cce-153">중재 서버 피어에서 문의 후 전송을 대상으로 하는 경우 문의 후 전송은 중재 서버에서 서비스 되는 단일 중재 서버 피어에 대해 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-153">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="a0cce-154">이 통화는 사이트의 다른 모든 Mediations 서버 피어가 별도의 중재 서버에서 서비스를 제공 하는 것과 상관 없이 PSTN 유료 바이패스로 인해 허용 되거나 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-154">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="a0cce-155">예를 들어 PSTN 게이트웨이 중재 서버 피어 및 PBX 중재 서버 피어를 제공 하는 별도의 중재 서버가 있는 경우에는 다음과 같은 동작이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-155">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="a0cce-156">지정 된 사이트 (예: 사이트 1)의 Lync 사용자가 문의 후 전송을 통해 다른 사이트 (즉, 사이트 2)의 Lync 사용자에 게 PSTN 끝점을 사용 하 여 통화를 전송 하려고 하면 PSTN 전화 바이패스를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="a0cce-157">지정 된 사이트 (즉, 1)의 Lync 사용자가 같은 사이트 (즉, 사이트 1)에서 PBX 끝점이 있는 통화를 다른 사이트 (즉, 사이트 2)의 온-문의 후 transfer를 통해 Lync 사용자에 게 전송 하려고 하면 잠재적인 PSTN 수신자가 바이패스 되는 경우 통화가 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-157">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="a0cce-158">Location-Based 라우팅 회의 응용 프로그램에서 지원 하지 않는 기능</span><span class="sxs-lookup"><span data-stu-id="a0cce-158">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="a0cce-159">Location-Based 라우팅 회의 응용 프로그램에서는 다음과 같은 기능을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-159">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="a0cce-160">전화 접속 회의</span><span class="sxs-lookup"><span data-stu-id="a0cce-160">Dial-in conferencing.</span></span> <span data-ttu-id="a0cce-161">Location-Based 라우팅은 전화 접속 회의에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-161">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="a0cce-162">전화 회의 이끌이가 Location-Based 라우팅에 대해 사용 하도록 설정 된 Lync 사용자 인 경우에도 지정 된 회의에 대 한 전화 접속 요청이 Location-Based 라우팅에서 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-162">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="a0cce-163">Location-Based 라우팅 제한을 적용 해야 하는 지역에서는 회의 액세스 번호를 프로 비전 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a0cce-163">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

