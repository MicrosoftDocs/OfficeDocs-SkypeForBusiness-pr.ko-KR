---
title: 'Lync Server 2013: 위치 기반 회의에 대 한 라우팅 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895a89ee59edaf973ae5194658c4cdf12564542e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="ba60d-102">Lync Server 2013에서 회의를 위한 위치 기반 라우팅 개요</span><span class="sxs-lookup"><span data-stu-id="ba60d-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba60d-103">_**마지막으로 수정한 주제:** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="ba60d-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="ba60d-104">위치 기반 라우팅 회의 응용 프로그램은 PSTN 유료 바이패스를 방지 하기 위한 메커니즘을 Lync 컨퍼런스에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="ba60d-105">이 응용 프로그램은 활성 회의를 모니터링 하 고 참여 하는 Lync 사용자의 위치를 기반으로 위치 기반 라우팅 제한을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="ba60d-106">위치 기반 라우팅 회의 응용 프로그램에서는 다음 조건이 충족 되는 경우 Lync 모임에 위치 기반 라우팅이 적용 되는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="ba60d-107">모임 이끌이는 위치 기반 회람을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="ba60d-108">위치 기반 라우팅 제한은 위치 기반 라우팅을 사용 하도록 설정 된 사용자가 구성한 회의에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="ba60d-109">하나 이상의 모임 참가자가 PSTN 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="ba60d-110">위치 기반 라우팅 제한은 PSTN 끝점을 포함 하는 회의에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="ba60d-111">PSTN에 전화를 연결 하는 데 사용 되는 PSTN 게이트웨이는 물론 이끌이와 참가자가 연결 되는 네트워크 사이트에 대 한 네트워크 사이트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="ba60d-112">위치 기반 라우팅 회의 응용 프로그램을 사용 하면 다른 네트워크 사이트의 Lync 사용자 및 PSTN 끝점을 같은 회의에 참가 시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="ba60d-113">모임 이끌이가 위치 기반 회람을 사용 하도록 설정 되어 있는 경우 회의 응용 프로그램에서 다음 제한 사항이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="ba60d-114">Lync 모임에 참가할 수 있는 끝점은 이미 전화 회의에 참가 한 끝점에 따라 다르며,이 제한은 참가 한 끝점 종료 및 새 끝점이 회의에 참가 함에 따라 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="ba60d-115">이끌이 및 참가자가 같은 네트워크 사이트에서 Lync 모임에 참가 하는 경우 PSTN 끝점, 같은 네트워크 사이트의 다른 참가자, 다른 네트워크 사이트의 다른 참가자 또는 알 수 없는 네트워크 사이트의 참가자가 사용할 수 있습니다. 합류.</span><span class="sxs-lookup"><span data-stu-id="ba60d-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="ba60d-116">이끌이 및 참가자가 서로 다른 네트워크나 알 수 없는 네트워크 사이트에서 모임에 참가 하는 경우 PSTN 호출이 위치 기반 라우팅에 대해 사용 하도록 설정 된 SIP 트렁크의 ingresses에서 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="ba60d-117">이끌이 및 참가자가 모두 동일한 네트워크 사이트의 모임에 참가 하 고 있으며 PSTN에서 같은 모임에 참가 하는 참가자가 있는 경우 다른 네트워크 사이트의 Lync 끝점은 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="ba60d-118">이러한 회의 위치 기반 라우팅 제한은 다음 표에 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba60d-119">지정 된 시점에 회의의 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="ba60d-120">회의에 참가할 수 있는 사용자 (들)</span><span class="sxs-lookup"><span data-stu-id="ba60d-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="ba60d-121">사용자가 회의에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba60d-122">단일 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="ba60d-123">동일한 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="ba60d-124">다른 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="ba60d-125">알 수 없는 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="ba60d-126">페더레이션 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="ba60d-127">PSTN 끝점에서 참가 하는 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="ba60d-128">없음</span><span class="sxs-lookup"><span data-stu-id="ba60d-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba60d-129">알 수 없는 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="ba60d-130">모든 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="ba60d-131">알 수 없는 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="ba60d-132">페더레이션 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="ba60d-133">PSTN 끝점을 통해 참가 하는 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba60d-134">다른 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="ba60d-135">네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="ba60d-136">알 수 없는 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="ba60d-137">페더레이션 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="ba60d-138">PSTN 끝점을 통해 참가 하는 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba60d-139">단일 네트워크 사이트의 Lync VoIP 클라이언트 사용자 및 PSTN 끝점에서 참가 하는 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="ba60d-140">동일한 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="ba60d-141">다른 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="ba60d-142">알 수 없는 네트워크 사이트의 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="ba60d-143">페더레이션 Lync VoIP 클라이언트 사용자</span><span class="sxs-lookup"><span data-stu-id="ba60d-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ba60d-144">다음은 위치 기반 라우팅 회의 응용 프로그램의 추가 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="ba60d-145">사용자가 전화 회의에 참가할 수 없는 경우에는 회의에 대 한 사용자 통화가 거부 되 고 Lync 클라이언트에서 통화가 완료 되지 않았거나 종료 되었음을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="ba60d-146">위치 기반 라우팅 enforcements를 사용 하 여 전화 회의에 참가 하는 PSTN 끝점은 위치 기반 라우팅에 대해 사용 하도록 설정 되지 않은 트렁크를 통해 끝점에 참가 하는 경우 상태에 관계 없이 전화 회의에 참가 하도록 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="ba60d-147">PSTN으로 호출 되지 않는 SIP 트렁크를 통해 Mediations 서버에 연결 된 PBX 시스템은 SIP 트렁크가 정의 된 동일한 네트워크 사이트에 있는 Lync 사용자와 동일한 enforcements를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="ba60d-148">예를 들어 PSTN 끝점은 PBX 사용자와 Lync 사용자 (동일한 네트워크 사이트에 있는 경우)와 회의에 참가할 수 있습니다. 그렇지 않으면 PBX 사용자가 Lync 사용자가 아닌 다른 네트워크 사이트에 있는 경우 PSTN 종점이 전화 회의에 참가할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba60d-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

