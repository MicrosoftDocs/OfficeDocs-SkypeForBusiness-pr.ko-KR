---
title: 'Lync Server 2013: Location-Based 라우팅 배포 프로세스'
description: 'Lync Server 2013: Location-Based 라우팅에 대 한 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c321d9b0eada6e9501b2ded69120feae36be171
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551064"
---
# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="5f7f0-103">Lync Server 2013의 Location-Based 라우팅 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="5f7f0-103">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f7f0-104">_**마지막으로 수정 된 항목:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="5f7f0-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="5f7f0-105">이 항목에서는 Location-Based 라우팅을 구성 하는 프로세스에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-105">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="5f7f0-106">Location-Based 라우팅을 구성 하려면 먼저 Enterprise Voice를 사용 하 여 Lync Server Enterprise Edition 또는 Standard Edition을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-106">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="5f7f0-107">Location-Based 라우팅에서 필요한 구성 요소는 Enterprise Voice를 배포할 때 이미 설치 되어 있고 사용 하도록 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-107">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="5f7f0-108">Location-Based 라우팅 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="5f7f0-108">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f7f0-109">단계</span><span class="sxs-lookup"><span data-stu-id="5f7f0-109">Phase</span></span></th>
<th><span data-ttu-id="5f7f0-110">단계</span><span class="sxs-lookup"><span data-stu-id="5f7f0-110">Steps</span></span></th>
<th><span data-ttu-id="5f7f0-111">필수 그룹 및 역할</span><span class="sxs-lookup"><span data-stu-id="5f7f0-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="5f7f0-112">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="5f7f0-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f7f0-113">Enterprise Voice 배포</span><span class="sxs-lookup"><span data-stu-id="5f7f0-113">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5f7f0-114">트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="5f7f0-114">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="5f7f0-115">음성 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="5f7f0-115">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="5f7f0-116">음성 경로 정의</span><span class="sxs-lookup"><span data-stu-id="5f7f0-116">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5f7f0-117">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="5f7f0-117">CSVoiceAdmins</span></span><br />
<span data-ttu-id="5f7f0-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5f7f0-118">CsAdministrator</span></span><br />
<span data-ttu-id="5f7f0-119">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5f7f0-119">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-120">Enterprise Voice 배포</span><span class="sxs-lookup"><span data-stu-id="5f7f0-120">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f7f0-121">Enterprise Voice 배포 확인</span><span class="sxs-lookup"><span data-stu-id="5f7f0-121">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5f7f0-122">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="5f7f0-122">CSVoiceAdmins</span></span><br />
<span data-ttu-id="5f7f0-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5f7f0-123">CsAdministrator</span></span><br />
<span data-ttu-id="5f7f0-124">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5f7f0-124">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f7f0-125">네트워크 지역, 사이트 및 서브넷 구성</span><span class="sxs-lookup"><span data-stu-id="5f7f0-125">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5f7f0-126">네트워크 지역 만들기</span><span class="sxs-lookup"><span data-stu-id="5f7f0-126">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="5f7f0-127">네트워크 사이트 만들기</span><span class="sxs-lookup"><span data-stu-id="5f7f0-127">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="5f7f0-128">서브넷을 네트워크 사이트와 연결</span><span class="sxs-lookup"><span data-stu-id="5f7f0-128">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5f7f0-129">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="5f7f0-129">CSVoiceAdmins</span></span><br />
<span data-ttu-id="5f7f0-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5f7f0-130">CsAdministrator</span></span><br />
<span data-ttu-id="5f7f0-131">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5f7f0-131">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-132">네트워크 지역, 사이트 및 서브넷 정보</span><span class="sxs-lookup"><span data-stu-id="5f7f0-132">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="5f7f0-133">네트워크 지역 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="5f7f0-133">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="5f7f0-134">네트워크 사이트 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="5f7f0-134">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="5f7f0-135">네트워크 사이트에 서브넷 연결</span><span class="sxs-lookup"><span data-stu-id="5f7f0-135">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f7f0-136">Location-Based 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="5f7f0-136">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5f7f0-137">음성 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="5f7f0-137">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="5f7f0-138">트렁크 별로 별도의 트렁크 구성 정의</span><span class="sxs-lookup"><span data-stu-id="5f7f0-138">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="5f7f0-139">음성 정책 수정</span><span class="sxs-lookup"><span data-stu-id="5f7f0-139">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="5f7f0-140">Location-Based 라우팅 구성 사용</span><span class="sxs-lookup"><span data-stu-id="5f7f0-140">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5f7f0-141">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="5f7f0-141">CSVoiceAdmins</span></span><br />
<span data-ttu-id="5f7f0-142">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5f7f0-142">CsAdministrator</span></span><br />
<span data-ttu-id="5f7f0-143">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5f7f0-143">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="5f7f0-144">샘플 배포</span><span class="sxs-lookup"><span data-stu-id="5f7f0-144">Sample Deployment</span></span>

<span data-ttu-id="5f7f0-145">다음 배포는 Location-Based 라우팅에서 사용 하는 메커니즘을 추가로 보여 주기 위해 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-145">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="5f7f0-146">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="5f7f0-146">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="5f7f0-147">들어오는 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="5f7f0-147">Incoming PSTN calls</span></span>

<span data-ttu-id="5f7f0-148">관리자는 Location-Based 라우팅에서 "사이트 1 게이트웨이"로 통화를 라우팅하기 위해 정의 된 트렁크를 사용 하도록 설정 하 고 사이트 1에 "사이트 1 게이트웨이"를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-148">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="5f7f0-149">"사이트 1 게이트웨이"를 통해 라우팅되는 통화는 사이트 1에 있는 사용자 에게만 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-149">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="5f7f0-150">PSTN 전화 바이패스를 방지 하기 위해 사이트 2와 같이 다른 사이트의 사용자에 게 전송 되는 "사이트 1 게이트웨이"를 통해 라우팅되는 모든 호출이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-150">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="5f7f0-151">"Site 1 Gateway"를 통한 모든 수신 PSTN 통화는 사이트 1에 있는 끝점 으로만 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-151">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="5f7f0-152">예를 들어 "Lync 사용자 1"이 사이트 2로 이동 하는 경우 "Site 1 Gateway"를 통한 모든 수신 PSTN 전화를 사이트 2에 있는 "Lync 사용자 1" 끝점으로 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-152">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="5f7f0-153">"Lync 사용자 1"이 사용자의 위치를 확인할 수 없는 알 수 없는 네트워크 사이트에 연결 되어 있는 경우에도 동일한 라우팅 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-153">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="5f7f0-154">다음 표에서는이 컨텍스트에서 "Lync 사용자 1"의 사용자 환경에 대해 간략히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-154">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="5f7f0-155">네트워크 사이트 1에 있는 Lync 사용자 1 끝점</span><span class="sxs-lookup"><span data-stu-id="5f7f0-155">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="5f7f0-156">네트워크 사이트 2에 있는 Lync 사용자 1 끝점</span><span class="sxs-lookup"><span data-stu-id="5f7f0-156">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="5f7f0-157">Lync 사용자 1 끝점이 알 수 없는 네트워크 사이트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-157">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f7f0-158">Lync 사용자 1에 대 한 인바운드 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="5f7f0-158">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-159">통화가이 위치의 끝점으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-159">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-160">통화가이 위치의 끝점으로 라우팅되지 않음</span><span class="sxs-lookup"><span data-stu-id="5f7f0-160">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-161">통화가이 위치의 끝점으로 라우팅되지 않음</span><span class="sxs-lookup"><span data-stu-id="5f7f0-161">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="5f7f0-162">나가는 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="5f7f0-162">Outgoing PSTN calls</span></span>

<span data-ttu-id="5f7f0-163">음성 경로는 사용자에 게 직접 할당 된 음성 정책 및 네트워크 사이트에 할당 된 음성 라우팅 정책에서 모두 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-163">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="5f7f0-164">두 정책에는 호출을 다르게 라우팅하는 데 사용할 수 있는 경로에 대 한 참조가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-164">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="5f7f0-165">예를 들어 관리자는 네트워크 사이트 1에 있는 모든 사용자에 대 한 음성 라우팅 정책을 정의 하 여 모든 아웃 바운드 호출을 "사이트 1 게이트웨이"를 통해 라우팅할 수 있으며, 일부 사용자의 음성 정책은 "Site 2 Gateway"를 통해 모든 아웃 바운드 호출에 대 한 경로를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-165">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="5f7f0-166">이러한 사용자는 네트워크 사이트 1에 있고, 아웃 바운드 통화는 "사이트 1 게이트웨이"를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-166">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="5f7f0-167">사용자가 Location-Based 라우팅으로 구성 된 네트워크 사이트에 있는 경우 네트워크 사이트의 음성 라우팅 정책 경로가 사용자의 음성 정책 경로를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-167">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="5f7f0-168">이 규칙은 특히 다른 사이트로 일시적으로 이동 하는 사용자에 게 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-168">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="5f7f0-169">이 경우 사용자는 항상 해당 지역의 로컬 게이트웨이를 사용 합니다. "Lync 사용자 3"이 "사이트 2"에 있는 경우 모든 아웃 바운드 통화는 "Site 2 Gateway"를 통해 라우팅되고, 사이트 1로 이동 하는 경우 사이트 1에 있는 모든 아웃 바운드 통화는 "Site 1 Gateway"를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-169">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="5f7f0-170">다음 표에서는 Lync 사용자 1이 다음 네트워크 사이트에서 아웃 바운드 호출을 수행 하는 사용자 환경을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-170">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="5f7f0-171">네트워크 사이트 1</span><span class="sxs-lookup"><span data-stu-id="5f7f0-171">Network site 1</span></span></th>
<th><span data-ttu-id="5f7f0-172">네트워크 사이트 2</span><span class="sxs-lookup"><span data-stu-id="5f7f0-172">Network site 2</span></span></th>
<th><span data-ttu-id="5f7f0-173">알 수 없는 네트워크 사이트 또는 Location-Based 라우팅을 사용 하도록 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="5f7f0-173">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f7f0-174">아웃 바운드 호출 권한 부여</span><span class="sxs-lookup"><span data-stu-id="5f7f0-174">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-175">Lync 사용자 1 음성 정책</span><span class="sxs-lookup"><span data-stu-id="5f7f0-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-176">Lync 사용자 1 음성 정책</span><span class="sxs-lookup"><span data-stu-id="5f7f0-176">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-177">Lync 사용자 1 음성 정책</span><span class="sxs-lookup"><span data-stu-id="5f7f0-177">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f7f0-178">아웃 바운드 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="5f7f0-178">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-179">사이트 1 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="5f7f0-179">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-180">사이트 2 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="5f7f0-180">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-181">사용자의 음성 정책 및 Location-Based 라우팅을 사용 하도록 설정 되지 않은 시스템에만 해당</span><span class="sxs-lookup"><span data-stu-id="5f7f0-181">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="5f7f0-182">통화 전송 및 전달</span><span class="sxs-lookup"><span data-stu-id="5f7f0-182">Call transfers and forwards</span></span>

<span data-ttu-id="5f7f0-183">통화가 전송 되거나 전달 되 면 통화 라우팅은 Location-Based 라우팅에서 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-183">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="5f7f0-184">다음 표에서는 Lync 사용자 1이 PSTN 통화를 다른 Lync 사용자에 게 전송 하거나 전달 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-184">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f7f0-185">사용자가 착신 전환 또는 전달 시작</span><span class="sxs-lookup"><span data-stu-id="5f7f0-185">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="5f7f0-186">Lync 사용자 2</span><span class="sxs-lookup"><span data-stu-id="5f7f0-186">Lync user 2</span></span></th>
<th><span data-ttu-id="5f7f0-187">Lync 사용자 4</span><span class="sxs-lookup"><span data-stu-id="5f7f0-187">Lync user 4</span></span></th>
<th><span data-ttu-id="5f7f0-188">Location-Based 라우팅을 위해 네트워크 사이트의 Lync 사용자를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="5f7f0-188">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f7f0-189">Lync 사용자 1</span><span class="sxs-lookup"><span data-stu-id="5f7f0-189">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-190">착신 전환 또는 전송이 허용 됨</span><span class="sxs-lookup"><span data-stu-id="5f7f0-190">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-191">착신 전환 또는 전송이 허용 되지 않음</span><span class="sxs-lookup"><span data-stu-id="5f7f0-191">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-192">착신 전환 또는 전송이 허용 되지 않음</span><span class="sxs-lookup"><span data-stu-id="5f7f0-192">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="5f7f0-193">다음 표에서는 Location-Based 라우팅이 전송 중인 Lync 사용자의 위치 (Lync user 2, Lync 사용자 4 등)를 PSTN 끝점으로 이동 하는 방법에 따라 호출이 라우팅되는 방식에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-193">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f7f0-194">통화가 전송 되거나 전달 되는 끝점</span><span class="sxs-lookup"><span data-stu-id="5f7f0-194">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="5f7f0-195">Lync 사용자 2</span><span class="sxs-lookup"><span data-stu-id="5f7f0-195">Lync user 2</span></span></th>
<th><span data-ttu-id="5f7f0-196">Lync 사용자 4</span><span class="sxs-lookup"><span data-stu-id="5f7f0-196">Lync user 4</span></span></th>
<th><span data-ttu-id="5f7f0-197">Location-Based 라우팅을 위해 네트워크 사이트의 Lync 사용자를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="5f7f0-197">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f7f0-198">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="5f7f0-198">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-199">착신 전환 또는 전송은 사이트 1 음성 라우팅 정책을 통해 라우팅되고 사이트 1 게이트웨이를 통해 송신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-199">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-200">착신 전환 또는 전송은 사이트 2 음성 라우팅 정책 및 사이트 2 게이트웨이를 통해 egress를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-200">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-201">위치 기반 라우팅을 사용 하도록 설정 되지 않은 게이트웨이를 통해 착신 전환 또는 전송이 Lync 사용자 음성 정책을 통과 하 고 송신 됩니다 (사용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="5f7f0-201">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="5f7f0-202">동시 벨 울림</span><span class="sxs-lookup"><span data-stu-id="5f7f0-202">Simultaneous ringing</span></span>

<span data-ttu-id="5f7f0-203">샘플 토폴로지에서 위치 기반 라우팅을 구성한 후에는 다음과 같은 상호 작용이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-203">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="5f7f0-204">다음 표에서는 Location-Based 라우팅에서 다른 Lync 사용자에 대해 동시 신호음을 허용 하는지 여부를 보여 줍니다 (예: Lync user 2, Lync 사용자 4 등).</span><span class="sxs-lookup"><span data-stu-id="5f7f0-204">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f7f0-205">들어오는 PSTN 통화 대상</span><span class="sxs-lookup"><span data-stu-id="5f7f0-205">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="5f7f0-206">Lync 사용자 2</span><span class="sxs-lookup"><span data-stu-id="5f7f0-206">Lync user 2</span></span></th>
<th><span data-ttu-id="5f7f0-207">Lync 사용자 4</span><span class="sxs-lookup"><span data-stu-id="5f7f0-207">Lync user 4</span></span></th>
<th><span data-ttu-id="5f7f0-208">Location-Based 라우팅을 위해 네트워크 사이트의 Lync 사용자를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="5f7f0-208">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f7f0-209">Lync 사용자 1</span><span class="sxs-lookup"><span data-stu-id="5f7f0-209">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-210">동시 신호음 허용</span><span class="sxs-lookup"><span data-stu-id="5f7f0-210">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-211">동시 벨 울림은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-211">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-212">동시 벨 울림은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-212">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="5f7f0-213">다음 표에서는 Location-Based 라우팅에서 다른 Lync 사용자의 PSTN 끝점으로 동시 신호음을 허용 하는지 여부를 보여 줍니다 (예: Lync user 2, Lync 사용자 4 등).</span><span class="sxs-lookup"><span data-stu-id="5f7f0-213">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f7f0-214">동시 링 대상</span><span class="sxs-lookup"><span data-stu-id="5f7f0-214">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="5f7f0-215">Lync 사용자 2</span><span class="sxs-lookup"><span data-stu-id="5f7f0-215">Lync user 2</span></span></th>
<th><span data-ttu-id="5f7f0-216">Lync 사용자 4</span><span class="sxs-lookup"><span data-stu-id="5f7f0-216">Lync user 4</span></span></th>
<th><span data-ttu-id="5f7f0-217">Location-Based 라우팅을 위해 네트워크 사이트의 Lync 사용자를 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="5f7f0-217">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f7f0-218">Lync 사용자 1 휴대폰 (PSTN 끝점)</span><span class="sxs-lookup"><span data-stu-id="5f7f0-218">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-219">네트워크 사이트 1의 음성 라우팅 정책 및 사이트 1 게이트웨이를 통해 송신 된 통화</span><span class="sxs-lookup"><span data-stu-id="5f7f0-219">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-220">네트워크 사이트 2의 음성 라우팅 정책 및 사이트 2 게이트웨이를 통해 송신 된 통화</span><span class="sxs-lookup"><span data-stu-id="5f7f0-220">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="5f7f0-221">전화 건 사람이 발신자 음성 정책을 통해 라우팅되며, Location-Based 라우팅에 사용 하도록 설정 되지 않은 PSTN 게이트웨이를 통해 egress 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f7f0-221">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5f7f0-222">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f7f0-222">See Also</span></span>


[<span data-ttu-id="5f7f0-223">Lync Server 2013의 Location-Based 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="5f7f0-223">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

