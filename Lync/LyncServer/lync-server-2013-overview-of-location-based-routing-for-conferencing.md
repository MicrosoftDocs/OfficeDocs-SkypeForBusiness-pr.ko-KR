---
title: 'Lync Server 2013: 회의에 대 한 위치 기반 라우팅 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 863cd213fb28d3adeedc04a5d46e4310ea4cd83b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="ef7b9-102">Lync Server 2013의 회의에 대 한 위치 기반 라우팅 개요</span><span class="sxs-lookup"><span data-stu-id="ef7b9-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef7b9-103">_**마지막으로 수정 된 항목:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="ef7b9-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="ef7b9-104">위치 기반 라우팅 회의 응용 프로그램은 PSTN 전화 바이패스를 방지 하기 위한 메커니즘을 Lync 회의에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="ef7b9-105">이 응용 프로그램은 활성 회의를 모니터링 하 고 참여 하는 Lync 사용자의 위치에 따라 위치 기반 라우팅 제한을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="ef7b9-106">위치 기반 라우팅 회의 응용 프로그램은 다음 조건이 충족 될 경우 Lync 모임에 대해 위치 기반 라우팅을 적용할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="ef7b9-107">모임 이끌이가 위치 기반 라우팅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="ef7b9-108">위치 기반 라우팅 제한은 위치 기반 라우팅을 사용 하도록 설정 된 사용자가 구성한 전화 회의에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="ef7b9-109">하나 이상의 모임 참가자가 PSTN 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="ef7b9-110">위치 기반 라우팅 제한은 PSTN 끝점이 포함 된 회의에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="ef7b9-111">회의를 PSTN에 연결 하는 데 사용 되는 PSTN 게이트웨이가 있는 네트워크 사이트와 이끌이 및 참가자가 연결할 네트워크 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="ef7b9-112">위치 기반 라우팅 회의 응용 프로그램을 사용 하면 Lync 사용자 및 PSTN 끝점이 서로 다른 네트워크 사이트에서 동일한 회의에 참가 하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="ef7b9-113">모임 이끌이가 위치 기반 라우팅을 사용 하도록 설정 된 경우에는 회의 응용 프로그램에서 다음과 같은 제한이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="ef7b9-114">Lync 모임에 참가할 수 있는 끝점은 이미 전화 회의에 참가 한 끝점에 의존 하며,이 제한은 연결 된 끝점 탈퇴 및 새 끝점이 전화 회의에 참가 하는 것으로 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="ef7b9-115">이끌이 및 참가자가 동일한 네트워크 사이트에서 Lync 모임에 참가 하는 경우 PSTN 끝점, 같은 네트워크 사이트의 다른 참가자, 다른 네트워크 사이트 또는 알 수 없는 네트워크 사이트의 참가자가 보낸 다른 참가자를 사용할 수 있습니다. 조인과.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="ef7b9-116">이끌이 및 참가자가 다른 네트워크나 알 수 없는 네트워크 사이트에서 모임에 참가 하는 경우 PSTN 전화가 위치 기반 라우팅을 위해 사용 하도록 설정 된 SIP 트렁크에서 ingresses 경우 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="ef7b9-117">이끌이 및 참가자가 동일한 네트워크 사이트의 모임에 모두 참가 하 고 있고 PSTN에서 같은 모임에 참가 하는 참가자가 있는 경우 다른 네트워크 사이트의 Lync 끝점이 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="ef7b9-118">다음 표에는 이러한 회의 위치 기반 라우팅 제한이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef7b9-119">지정 된 시점에 회의의 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="ef7b9-120">회의에 참가할 수 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="ef7b9-121">사용자가 회의에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef7b9-122">단일 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="ef7b9-123">동일한 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="ef7b9-124">다른 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="ef7b9-125">알 수 없는 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="ef7b9-126">페더레이션 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="ef7b9-127">PSTN 끝점에서 참가 한 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="ef7b9-128">없음</span><span class="sxs-lookup"><span data-stu-id="ef7b9-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef7b9-129">알 수 없는 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="ef7b9-130">모든 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="ef7b9-131">알 수 없는 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="ef7b9-132">페더레이션 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="ef7b9-133">PSTN 끝점을 통한 사용자 참가</span><span class="sxs-lookup"><span data-stu-id="ef7b9-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef7b9-134">다른 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="ef7b9-135">모든 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="ef7b9-136">알 수 없는 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="ef7b9-137">페더레이션 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="ef7b9-138">PSTN 끝점을 통한 사용자 참가</span><span class="sxs-lookup"><span data-stu-id="ef7b9-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef7b9-139">단일 네트워크 사이트 및 PSTN 끝점에서 가입한 사용자의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="ef7b9-140">동일한 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="ef7b9-141">다른 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="ef7b9-142">알 수 없는 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="ef7b9-143">페더레이션 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ef7b9-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ef7b9-144">다음은 위치 기반 라우팅 회의 응용 프로그램의 추가 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="ef7b9-145">사용자가 전화 회의에 참가 하도록 허용 되지 않으면 전화 회의에 대 한 통화 호출이 거부 되 고 Lync 클라이언트는 통화가 완료 되지 않았거나 종료 되었음을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="ef7b9-146">위치 기반 라우팅 enforcements 전화 회의에 참가 하는 PSTN 끝점은 위치 기반 라우팅을 사용 하도록 설정 되지 않은 트렁크를 통해 끝점이 연결 되는 경우 해당 상태에 관계 없이 회의에 참가 하도록 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="ef7b9-147">PSTN으로 전화를 걸 수 없는 SIP 트렁크를 통해 Mediations 서버에 연결 된 PBX 시스템은 SIP 트렁크가 정의 된 동일한 네트워크 사이트에 있는 Lync 사용자와 동일한 enforcements을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="ef7b9-148">예를 들어 PSTN 끝점이 동일한 네트워크 사이트에 있는 경우 PBX 사용자 및 Lync 사용자와 회의에 참가할 수 있습니다. 그렇지 않으면 PBX 사용자가 Lync 사용자와 다른 네트워크 사이트에 있는 경우 PSTN 끝점이 회의에 참가할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef7b9-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

