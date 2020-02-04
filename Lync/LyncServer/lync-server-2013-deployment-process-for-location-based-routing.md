---
title: 'Lync Server 2013: 위치 기반 라우팅 배포 프로세스'
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
ms.openlocfilehash: 02e09106bc9d96fbfab2935aec07f3c472f49d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="4d1e8-102">Lync Server 2013의 위치 기반 라우팅 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="4d1e8-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d1e8-103">_**마지막으로 수정한 주제:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="4d1e8-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="4d1e8-104">이 항목에서는 위치 기반 라우팅 구성과 관련 된 프로세스에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="4d1e8-105">위치 기반 라우팅을 구성 하기 전에 먼저 Enterprise Voice를 사용 하 여 Lync Server Enterprise Edition 또는 Standard Edition을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="4d1e8-106">엔터프라이즈 음성을 배포 하는 경우 위치 기반 라우팅에 필요한 구성 요소가 이미 설치 및 활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="4d1e8-107">위치 기반 라우팅 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="4d1e8-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d1e8-108">단계의</span><span class="sxs-lookup"><span data-stu-id="4d1e8-108">Phase</span></span></th>
<th><span data-ttu-id="4d1e8-109">방법은</span><span class="sxs-lookup"><span data-stu-id="4d1e8-109">Steps</span></span></th>
<th><span data-ttu-id="4d1e8-110">필수 그룹 및 역할</span><span class="sxs-lookup"><span data-stu-id="4d1e8-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="4d1e8-111">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="4d1e8-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d1e8-112">Enterprise Voice 배포</span><span class="sxs-lookup"><span data-stu-id="4d1e8-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4d1e8-113">Trunks 구성</span><span class="sxs-lookup"><span data-stu-id="4d1e8-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="4d1e8-114">음성 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4d1e8-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="4d1e8-115">음성 경로 정의</span><span class="sxs-lookup"><span data-stu-id="4d1e8-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4d1e8-116">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="4d1e8-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="4d1e8-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4d1e8-117">CsAdministrator</span></span><br />
<span data-ttu-id="4d1e8-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4d1e8-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-119">엔터프라이즈 음성 배포</span><span class="sxs-lookup"><span data-stu-id="4d1e8-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1e8-120">엔터프라이즈 음성 배포 확인</span><span class="sxs-lookup"><span data-stu-id="4d1e8-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4d1e8-121">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="4d1e8-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="4d1e8-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4d1e8-122">CsAdministrator</span></span><br />
<span data-ttu-id="4d1e8-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4d1e8-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d1e8-124">네트워크 지역, 사이트 및 서브넷 구성</span><span class="sxs-lookup"><span data-stu-id="4d1e8-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4d1e8-125">네트워크 지역 만들기</span><span class="sxs-lookup"><span data-stu-id="4d1e8-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="4d1e8-126">네트워크 사이트 만들기</span><span class="sxs-lookup"><span data-stu-id="4d1e8-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="4d1e8-127">서브넷을 네트워크 사이트와 연결</span><span class="sxs-lookup"><span data-stu-id="4d1e8-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4d1e8-128">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="4d1e8-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="4d1e8-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4d1e8-129">CsAdministrator</span></span><br />
<span data-ttu-id="4d1e8-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4d1e8-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-131">네트워크 지역, 사이트 및 서브넷 정보</span><span class="sxs-lookup"><span data-stu-id="4d1e8-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="4d1e8-132">네트워크 지역 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="4d1e8-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="4d1e8-133">네트워크 사이트 만들기 또는 수정</span><span class="sxs-lookup"><span data-stu-id="4d1e8-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="4d1e8-134">서브넷을 네트워크 사이트에 연결</span><span class="sxs-lookup"><span data-stu-id="4d1e8-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1e8-135">위치 기반 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="4d1e8-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4d1e8-136">음성 라우팅 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="4d1e8-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="4d1e8-137">트렁크 당 별도의 트렁크 구성 정의</span><span class="sxs-lookup"><span data-stu-id="4d1e8-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="4d1e8-138">음성 정책 수정</span><span class="sxs-lookup"><span data-stu-id="4d1e8-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="4d1e8-139">위치 기반 라우팅 구성 사용</span><span class="sxs-lookup"><span data-stu-id="4d1e8-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4d1e8-140">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="4d1e8-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="4d1e8-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4d1e8-141">CsAdministrator</span></span><br />
<span data-ttu-id="4d1e8-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4d1e8-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="4d1e8-143">샘플 배포</span><span class="sxs-lookup"><span data-stu-id="4d1e8-143">Sample Deployment</span></span>

<span data-ttu-id="4d1e8-144">다음 배포는 위치 기반 라우팅이 사용할 수 있는 메커니즘을 자세히 설명 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="4d1e8-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="4d1e8-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="4d1e8-146">수신 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="4d1e8-146">Incoming PSTN calls</span></span>

<span data-ttu-id="4d1e8-147">관리자는 위치 기반 라우팅에 대해 "사이트 1 게이트웨이"로 전화를 라우팅하고 "사이트 1 게이트웨이"를 사이트 1에 연결 하도록 정의 된 트렁크를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="4d1e8-148">"Site 1 Gateway"를 통해 라우팅되는 통화는 사이트 1에 있는 사용자 에게만 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="4d1e8-149">사이트 2와 같이 다른 사이트의 사용자에 게 전송 되는 "사이트 1 게이트웨이" 트렁크를 통해 라우팅된 모든 통화가 차단 되어 PSTN 유료 바이패스를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="4d1e8-150">"Site 1 Gateway"를 통한 모든 수신 PSTN 통화는 사이트 1에 있는 끝점 으로만 라우팅하도록 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="4d1e8-151">예를 들어 "Lync 사용자 1"이 사이트 2로 이동 하면 "Site 1 Gateway"를 통해 들어오는 모든 PSTN 호출은 사이트 2에 있는 "Lync 사용자 1" 끝점으로 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="4d1e8-152">"Lync 사용자 1"이 사용자의 위치를 확인할 수 없는 알 수 없는 네트워크 사이트로 이동 하는 경우에도 동일한 라우팅 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="4d1e8-153">다음 표에서는이 컨텍스트에서 "Lync 사용자 1"의 사용자 환경을 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="4d1e8-154">네트워크 사이트 1에 있는 Lync 사용자 1 끝점</span><span class="sxs-lookup"><span data-stu-id="4d1e8-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="4d1e8-155">네트워크 사이트 2에 있는 Lync 사용자 1 끝점</span><span class="sxs-lookup"><span data-stu-id="4d1e8-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="4d1e8-156">Lync 사용자 1 끝점이 알 수 없는 네트워크 사이트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d1e8-157">Lync 사용자 1에 게 들어오는 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="4d1e8-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-158">통화가이 위치의 끝점으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-159">이 위치의 끝점으로 호출이 라우팅되지 않음</span><span class="sxs-lookup"><span data-stu-id="4d1e8-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-160">이 위치의 끝점으로 호출이 라우팅되지 않음</span><span class="sxs-lookup"><span data-stu-id="4d1e8-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="4d1e8-161">발신 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="4d1e8-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="4d1e8-162">음성 경로는 사용자에 게 직접 할당 된 음성 정책 및 네트워크 사이트에 할당 된 음성 라우팅 정책에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="4d1e8-163">두 정책에는 호출을 다르게 라우팅하는 데 사용할 수 있는 경로에 대 한 참조가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="4d1e8-164">예를 들어 관리자는 네트워크 사이트 1에 있는 모든 사용자에 대해 음성 라우팅 정책을 정의 하 여 "사이트 1 게이트웨이"를 통해 모든 아웃 바운드 통화를 라우팅할 수 있지만, 일부 사용자의 음성 정책은 "Site 2 Gateway"를 통해 모든 아웃 바운드 통화에 대 한 경로를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="4d1e8-165">이러한 사용자는 네트워크 사이트 1에 있으며, 아웃 바운드 통화는 "Site 1 Gateway"를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="4d1e8-166">사용자가 위치 기반 라우팅에 대해 구성 된 네트워크 사이트에 있는 경우 네트워크 사이트의 음성 라우팅 정책 경로가 사용자의 음성 정책 경로를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="4d1e8-167">이 규칙은 사용자가 일시적으로 다른 사이트로 이동 하는 경우에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="4d1e8-168">이 경우 사용자는 항상 해당 위치에 로컬인 게이트웨이를 사용 합니다. "Lync 사용자 3"이 "Site 2"에 있는 경우 모든 아웃 바운드 통화는 "Site 2 Gateway"를 통해 라우팅되며, 사이트 1로 이동 하는 경우 사이트 1에 있는 사용자의 모든 아웃 바운드 통화가 "Site 1 Gateway"를 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="4d1e8-169">다음 표에서는 Lync 사용자 1의 사용자 환경이 다음 네트워크 사이트에서 나가는 호출을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="4d1e8-170">네트워크 사이트 1</span><span class="sxs-lookup"><span data-stu-id="4d1e8-170">Network site 1</span></span></th>
<th><span data-ttu-id="4d1e8-171">네트워크 사이트 2</span><span class="sxs-lookup"><span data-stu-id="4d1e8-171">Network site 2</span></span></th>
<th><span data-ttu-id="4d1e8-172">알 수 없는 네트워크 사이트 이거나 위치 기반 라우팅에 대해 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="4d1e8-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d1e8-173">아웃 바운드 통화 승인</span><span class="sxs-lookup"><span data-stu-id="4d1e8-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-174">Lync 사용자 1 음성 정책</span><span class="sxs-lookup"><span data-stu-id="4d1e8-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-175">Lync 사용자 1 음성 정책</span><span class="sxs-lookup"><span data-stu-id="4d1e8-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-176">Lync 사용자 1 음성 정책</span><span class="sxs-lookup"><span data-stu-id="4d1e8-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d1e8-177">아웃 바운드 통화 라우팅</span><span class="sxs-lookup"><span data-stu-id="4d1e8-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-178">사이트 1 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="4d1e8-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-179">사이트 2 음성 라우팅 정책</span><span class="sxs-lookup"><span data-stu-id="4d1e8-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-180">사용자의 음성 정책 및 위치 기반 라우팅에 사용할 수 없는 시스템만</span><span class="sxs-lookup"><span data-stu-id="4d1e8-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="4d1e8-181">통화 전달 및 전달</span><span class="sxs-lookup"><span data-stu-id="4d1e8-181">Call transfers and forwards</span></span>

<span data-ttu-id="4d1e8-182">통화를 전송 하거나 전달 하는 경우에는 위치 기반 라우팅의 호출 라우팅이 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="4d1e8-183">다음 표에서는 Lync 사용자 1이 다른 Lync 사용자에 게 PSTN 통화를 전송 하거나 착신 전환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d1e8-184">사용자가 통화 전달 또는 전달 시작</span><span class="sxs-lookup"><span data-stu-id="4d1e8-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="4d1e8-185">Lync 사용자 2</span><span class="sxs-lookup"><span data-stu-id="4d1e8-185">Lync user 2</span></span></th>
<th><span data-ttu-id="4d1e8-186">Lync 사용자 4</span><span class="sxs-lookup"><span data-stu-id="4d1e8-186">Lync user 4</span></span></th>
<th><span data-ttu-id="4d1e8-187">네트워크 사이트의 Lync 사용자가 위치 기반 라우팅에 대해 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="4d1e8-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d1e8-188">Lync 사용자 1</span><span class="sxs-lookup"><span data-stu-id="4d1e8-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-189">착신 통화 또는 전송이 허용 됨</span><span class="sxs-lookup"><span data-stu-id="4d1e8-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-190">착신 통화 또는 전송이 허용 되지 않음</span><span class="sxs-lookup"><span data-stu-id="4d1e8-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-191">착신 통화 또는 전송이 허용 되지 않음</span><span class="sxs-lookup"><span data-stu-id="4d1e8-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="4d1e8-192">다음 표에서는 위치 기반 라우팅이 전송 되는 Lync 사용자 (Lync user 2, Lync 사용자 4 등)가 PSTN 끝점으로 이동 하는 위치에 따라 호출이 라우팅되는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d1e8-193">통화가 전송 되거나 전달 되는 끝점</span><span class="sxs-lookup"><span data-stu-id="4d1e8-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="4d1e8-194">Lync 사용자 2</span><span class="sxs-lookup"><span data-stu-id="4d1e8-194">Lync user 2</span></span></th>
<th><span data-ttu-id="4d1e8-195">Lync 사용자 4</span><span class="sxs-lookup"><span data-stu-id="4d1e8-195">Lync user 4</span></span></th>
<th><span data-ttu-id="4d1e8-196">네트워크 사이트의 Lync 사용자가 위치 기반 라우팅에 대해 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="4d1e8-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d1e8-197">PSTN 끝점</span><span class="sxs-lookup"><span data-stu-id="4d1e8-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-198">통화 전달 또는 전송이 사이트 1 음성 라우팅 정책 및 사이트 1 게이트웨이를 통해 egress를 통해 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-199">통화 전달 또는 전송이 사이트 2 음성 라우팅 정책 및 사이트 2 게이트웨이를 통해 egress를 통해 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-200">통화 전달 또는 전송이 Lync 사용자 음성 정책 및 위치 기반 라우팅에 사용할 수 없는 게이트웨이를 통해 송신 됩니다 (사용 가능한 경우).</span><span class="sxs-lookup"><span data-stu-id="4d1e8-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="4d1e8-201">동시 연결</span><span class="sxs-lookup"><span data-stu-id="4d1e8-201">Simultaneous ringing</span></span>

<span data-ttu-id="4d1e8-202">샘플 토폴로지에서 위치 기반 라우팅이 구성 되 면 다음 조작이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="4d1e8-203">다음 표에서는 위치 기반 라우팅이 다른 Lync 사용자 (예: Lync 사용자 2, Lync 사용자 4 등)에 대해 동시 연결을 허용 하는지 여부를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d1e8-204">들어오는 PSTN 통화 대상</span><span class="sxs-lookup"><span data-stu-id="4d1e8-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="4d1e8-205">Lync 사용자 2</span><span class="sxs-lookup"><span data-stu-id="4d1e8-205">Lync user 2</span></span></th>
<th><span data-ttu-id="4d1e8-206">Lync 사용자 4</span><span class="sxs-lookup"><span data-stu-id="4d1e8-206">Lync user 4</span></span></th>
<th><span data-ttu-id="4d1e8-207">네트워크 사이트의 Lync 사용자가 위치 기반 라우팅에 대해 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="4d1e8-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d1e8-208">Lync 사용자 1</span><span class="sxs-lookup"><span data-stu-id="4d1e8-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-209">동시 신호음 허용</span><span class="sxs-lookup"><span data-stu-id="4d1e8-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-210">동시 링을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-211">동시 링을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="4d1e8-212">다음 표에서는 위치 기반 라우팅이 다른 Lync 사용자의 PSTN 끝점으로 동시 신호음을 허용 하는지 여부 (즉, Lync 사용자 2, Lync 사용자 4 등)를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d1e8-213">동시 링 대상</span><span class="sxs-lookup"><span data-stu-id="4d1e8-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="4d1e8-214">Lync 사용자 2</span><span class="sxs-lookup"><span data-stu-id="4d1e8-214">Lync user 2</span></span></th>
<th><span data-ttu-id="4d1e8-215">Lync 사용자 4</span><span class="sxs-lookup"><span data-stu-id="4d1e8-215">Lync user 4</span></span></th>
<th><span data-ttu-id="4d1e8-216">네트워크 사이트의 Lync 사용자가 위치 기반 라우팅에 대해 설정 되지 않음</span><span class="sxs-lookup"><span data-stu-id="4d1e8-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d1e8-217">Lync 사용자 1 휴대 전화 (PSTN 끝점)</span><span class="sxs-lookup"><span data-stu-id="4d1e8-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-218">네트워크 사이트 1의 음성 라우팅 정책 및 사이트 1 게이트웨이를 통해 송신을 통해 전달 되는 통화</span><span class="sxs-lookup"><span data-stu-id="4d1e8-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-219">네트워크 사이트 2의 음성 라우팅 정책 및 사이트 2 게이트웨이를 통해 송신을 통해 전달 되는 통화</span><span class="sxs-lookup"><span data-stu-id="4d1e8-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="4d1e8-220">발신자 음성 정책에 따라 통신 하 고, 위치 기반 라우팅에 사용 되지 않는 PSTN 게이트웨이를 통해 egress가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1e8-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4d1e8-221">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d1e8-221">See Also</span></span>


[<span data-ttu-id="4d1e8-222">Lync Server 2013의 위치 기반 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="4d1e8-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

