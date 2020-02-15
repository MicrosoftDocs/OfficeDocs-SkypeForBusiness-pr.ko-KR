---
title: 'Lync Server 2013: 응답 그룹 응용 프로그램 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d63f13442588a84039fee6e1147a9c29e821e14a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="c06b9-102">Lync Server 2013의 응답 그룹 응용 프로그램 개요</span><span class="sxs-lookup"><span data-stu-id="c06b9-102">Overview of the Response Group application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c06b9-103">_**마지막으로 수정 된 항목:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="c06b9-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="c06b9-104">발신자가 응답 그룹을 호출 하면 통화가 헌트 그룹을 기반으로 하는 에이전트로 또는 발신자의 IVR (대화형 음성 응답) 질문에 대 한 답변으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-104">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="c06b9-105">응답 그룹 응용 프로그램은 표준 응답 그룹 라우팅 메서드를 사용 하 여 다음 사용 가능한 에이전트로 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-105">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="c06b9-106">통화 라우팅 방법에는 직렬, 가장 오래 된 유휴, 병렬, 라운드 로빈 및 전화 교환 라우팅이 포함 됩니다 (현재 현재 상태에 관계 없이 모든 수신 전화에 대해 동시에 모든 에이전트가 호출 됨).</span><span class="sxs-lookup"><span data-stu-id="c06b9-106">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="c06b9-107">사용할 수 있는 에이전트가 없는 경우에는 에이전트를 사용할 수 있을 때까지 통화가 큐에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-107">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="c06b9-108">큐에서 발신자는 사용 가능한 에이전트가 통화를 수락할 때까지 음악을 듣습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-108">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="c06b9-109">큐가 꽉 찼거나 통화 시간이 초과 되 면 발신자가 메시지를 듣고 연결이 끊어지거나 다른 대상으로 전송 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-109">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="c06b9-110">에이전트에서 통화를 수락 하면 관리자가 응답 그룹을 구성 하는 방법에 따라 발신자가 에이전트의 id를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-110">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="c06b9-111">에이전트는 공식 일 수 있으며,이 경우 그룹에 대 한 호출을 수락 하기 전에 그룹에 로그인 해야 하거나 비공식를 사용 하 여 호출을 수락 하는 그룹에 로그인 하거나이를 제외 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-111">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c06b9-p102">온-프레미스 사용자만 에이전트가 될 수 있습니다. 에이전트를 온-프레미스에서 온라인으로 이동하면 응답 그룹 통화가 해당 에이전트에게 라우팅되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-p102">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c06b9-114">응답 그룹 응용 프로그램은 일치 하는 내부 서비스를 사용 하 여 통화를 대기 시키고 사용 가능한 에이전트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-114">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="c06b9-115">응답 그룹 응용 프로그램을 실행 하는 각 컴퓨터는 Match service를 실행 하지만 Lync Server 풀 당 서비스를 수행 하는 하나의 일치가 동시에 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-115">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="c06b9-116">계획 되지 않은 중단 중에 현재 서비스를 사용할 수 없게 되는 active Match 서비스를 만드는 수동 일치 중 하나가 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-116">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="c06b9-117">응답 그룹 응용 프로그램은 계속 해 서 통화 라우팅과 큐가 중단 되지 않도록 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-117">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="c06b9-118">그러나 서비스 전환이 일치 하 게 되 면 전송 중인 모든 통화는 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-118">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="c06b9-119">예를 들어 다운 되는 프런트 엔드 서버로 인해 전환이 발생 하는 경우 해당 프런트 엔드 서버에서 서비스를 수행 하는 활성 일치에 의해서도 현재 처리 중인 통화도 모두 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-119">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="c06b9-120">Lync Server 2013에서는 응답 그룹 관리를 위해 두 가지 관리 역할 (응답 그룹 관리자 및 응답 그룹 관리자)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-120">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="c06b9-121">응답 그룹 관리자는 모든 응답 그룹의 모든 측면을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-121">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="c06b9-122">응답 그룹 관리자는 특정 측면과 자신이 소유한 응답 그룹만 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-122">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="c06b9-123">Enterprise Voice를 사용 하도록 설정 된 사용자에 게 특정 응답 그룹에 대 한 제한 된 책임을 위임할 수 있으므로 새 관리자 역할은 관리 비용을 줄이는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-123">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="c06b9-124">새 관리자 역할을 수용할 수 있도록 Lync Server 2013 Response 그룹 응용 프로그램은 관리 되거나 관리 되지 않는 **워크플로 유형을** 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-124">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="c06b9-125">다음 표에서는 관리 및 관리 되지 않는 응답 그룹에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-125">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="c06b9-126">관리 및 관리 되지 않는 응답 그룹</span><span class="sxs-lookup"><span data-stu-id="c06b9-126">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c06b9-127">응답 그룹 유형</span><span class="sxs-lookup"><span data-stu-id="c06b9-127">Response group type</span></span></th>
<th><span data-ttu-id="c06b9-128">설명</span><span class="sxs-lookup"><span data-stu-id="c06b9-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c06b9-129">관리 되지 않는</span><span class="sxs-lookup"><span data-stu-id="c06b9-129">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c06b9-130">관리 되지 않는 응답 그룹에는 할당 된 관리자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-130">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="c06b9-131">응답 그룹 관리자만 이러한 응답 그룹을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-131">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="c06b9-132">여러 관리 되지 않는 응답 그룹이 큐 또는 에이전트 그룹을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-132">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="c06b9-133">응답 그룹을 이전 버전에서 Lync Server 2013로 마이그레이션하는 경우 유형이 관리 되지 않는 것으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-133">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c06b9-134">되</span><span class="sxs-lookup"><span data-stu-id="c06b9-134">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c06b9-135">응답 그룹 관리자는 관리 되는 응답 그룹의 모든 측면을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-135">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="c06b9-136">응답 그룹 관리자는 명시적으로 할당 되지 않은 응답 그룹을 보거나 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-136">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="c06b9-137">응답 그룹 관리자는 명시적으로 할당 된 응답 그룹에 대 한 일부 설정만 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-137">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="c06b9-138">관리 되는 응답 그룹은 다른 응답 그룹 (관리 또는 비관리)과 큐 또는 에이전트 그룹을 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-138">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c06b9-139">다음 표에서는 응답 그룹 관리자가 자신에 게 할당 된 응답 그룹에 대해 수행할 수 있는 작업 및 수행이 불가능 한 조치에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-139">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="c06b9-140">응답 그룹 관리자 기능</span><span class="sxs-lookup"><span data-stu-id="c06b9-140">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c06b9-141">다음을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-141">Can configure:</span></span></th>
<th><span data-ttu-id="c06b9-142">만들기, 삭제 또는 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-142">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="c06b9-143">수 없습니다</span><span class="sxs-lookup"><span data-stu-id="c06b9-143">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="c06b9-144">Agent</span><span class="sxs-lookup"><span data-stu-id="c06b9-144">Agents</span></span></p></li>
<li><p><span data-ttu-id="c06b9-145">환영 메시지</span><span class="sxs-lookup"><span data-stu-id="c06b9-145">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="c06b9-146">응답 그룹 이름</span><span class="sxs-lookup"><span data-stu-id="c06b9-146">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="c06b9-147">설명</span><span class="sxs-lookup"><span data-stu-id="c06b9-147">Description</span></span></p></li>
<li><p><span data-ttu-id="c06b9-148">표시 번호</span><span class="sxs-lookup"><span data-stu-id="c06b9-148">Display number</span></span></p></li>
<li><p><span data-ttu-id="c06b9-149">업무 시간</span><span class="sxs-lookup"><span data-stu-id="c06b9-149">Business hours</span></span></p></li>
<li><p><span data-ttu-id="c06b9-150">통화 대기음</span><span class="sxs-lookup"><span data-stu-id="c06b9-150">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="c06b9-151">상태 (활성/비활성)</span><span class="sxs-lookup"><span data-stu-id="c06b9-151">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="c06b9-152">헌트 그룹 워크플로 또는 IVR (대화형 음성 응답) 워크플로</span><span class="sxs-lookup"><span data-stu-id="c06b9-152">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c06b9-153">에이전트 그룹</span><span class="sxs-lookup"><span data-stu-id="c06b9-153">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="c06b9-154">큐</span><span class="sxs-lookup"><span data-stu-id="c06b9-154">Queues</span></span></p></li>
<li><p><span data-ttu-id="c06b9-155">휴일 집합</span><span class="sxs-lookup"><span data-stu-id="c06b9-155">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c06b9-156">모든 유형의 워크플로 만들기 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="c06b9-156">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="c06b9-157"><strong>SIP URI</strong>, <strong>전화 번호</strong>또는 <strong>워크플로 유형과</strong>같은 핵심 응답 그룹 설정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-157">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c06b9-158">응답 그룹 관리자는 다음 도구를 사용 하 여 지정 된 응답 그룹을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-158">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="c06b9-159">Lync Server 제어판</span><span class="sxs-lookup"><span data-stu-id="c06b9-159">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c06b9-160">응답 그룹 관리자는이 도구를 사용 하 여 응답 그룹 설정만 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-160">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="c06b9-161">관리자가 다른 Lync Server 설정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-161">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="c06b9-162">응답 그룹 구성 도구</span><span class="sxs-lookup"><span data-stu-id="c06b9-162">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="c06b9-163">Communications Server 관리 셸</span><span class="sxs-lookup"><span data-stu-id="c06b9-163">Lync Server Management Shell</span></span>

<span data-ttu-id="c06b9-164">응답 그룹은 부서나 작업 그룹 환경에 맞게 확장 되며 자세한 내용은 [Lync Server 2013의 응답 그룹에 대 한 용량 계획](lync-server-2013-capacity-planning-for-response-group.md)및 완전히 새로운 전화 통신 설치 환경에서 배포할 수 있습니다 .를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c06b9-164">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="c06b9-165">엔터프라이즈 음성 배포 및 로컬 반송파 네트워크에서 들어오는 호출을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-165">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="c06b9-166">상담원은 Lync 2013, Lync 2010, Lync 2010 Attendant 또는 Lync Phone Edition을 사용 하 여 전달 된 통화를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-166">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="c06b9-167">응답 그룹 응용 프로그램은 Enterprise Voice의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-167">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="c06b9-168">Enterprise Voice를 배포 하면 응답 그룹 응용 프로그램이 자동으로 설치 되 고 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c06b9-168">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

