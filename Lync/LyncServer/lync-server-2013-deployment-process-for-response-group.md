---
title: 'Lync Server 2013: 응답 그룹 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c87519c26a0804ad6c9f275d2e12c4a26988d29
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="02ef8-102">Lync Server 2013의 응답 그룹 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="02ef8-102">Deployment process for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02ef8-103">_**마지막으로 수정 된 항목:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="02ef8-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="02ef8-104">이 섹션에서는 응답 그룹 응용 프로그램 배포와 관련 된 단계 및 단계에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="02ef8-105">응답 그룹 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="02ef8-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02ef8-106">단계</span><span class="sxs-lookup"><span data-stu-id="02ef8-106">Phase</span></span></th>
<th><span data-ttu-id="02ef8-107">단계</span><span class="sxs-lookup"><span data-stu-id="02ef8-107">Steps</span></span></th>
<th><span data-ttu-id="02ef8-108">권한</span><span class="sxs-lookup"><span data-stu-id="02ef8-108">Permissions</span></span></th>
<th><span data-ttu-id="02ef8-109">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="02ef8-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02ef8-110">응답 그룹 응용 프로그램 설치</span><span class="sxs-lookup"><span data-stu-id="02ef8-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="02ef8-111">Enterprise Voice를 배포할 때 응답 그룹 응용 프로그램이 기본적으로 설치 및 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="02ef8-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="02ef8-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="02ef8-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Lync Server 2013에서 Enterprise Voice 배포</a></span><span class="sxs-lookup"><span data-stu-id="02ef8-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02ef8-114">응답 그룹 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="02ef8-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="02ef8-115">Lync Server cmdlet, Lync Server 제어판, 응답 그룹 구성 도구, 에이전트의 로그인 및 로그 아웃 콘솔 및 응답 그룹 클라이언트 웹 서비스는 웹 서비스의 일부로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="02ef8-116">웹 서비스는 Enterprise Edition 풀이나 Standard Edition Server 배포 시 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="02ef8-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="02ef8-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="02ef8-118"><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 배포</a></span><span class="sxs-lookup"><span data-stu-id="02ef8-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02ef8-119">사용자가 Lync 2013 및 Enterprise Voice를 사용할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="02ef8-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="02ef8-120">Lync Server 및 Enterprise Voice를 위한 에이전트로 사용할 사용자를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="02ef8-121">에이전트 그룹에 사용자를 추가하려면 해당 사용자가 사용되도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="02ef8-122">일반적으로 사용자는 Enterprise Edition 또는 Standard Edition 서버 배포 중에 Lync Server를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="02ef8-123">Enterprise Voice 배포 중에 사용자가 Enterprise Voice를 사용할 수 있도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="02ef8-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="02ef8-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="02ef8-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="02ef8-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="02ef8-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="02ef8-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="02ef8-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Lync Server 2013에 대해 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정</a></span><span class="sxs-lookup"><span data-stu-id="02ef8-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="02ef8-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Lync Server 2013에서 Enterprise Voice를 사용할 수 있도록 사용자 설정</a></span><span class="sxs-lookup"><span data-stu-id="02ef8-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02ef8-129">에이전트 그룹, 큐 및 워크플로로 구성 된 응답 그룹 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="02ef8-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="02ef8-130">Lync Server 제어판 또는 Lync Server 관리 셸을 사용 하 여 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="02ef8-131">에이전트 그룹을 만들고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="02ef8-132">큐를 만들고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="02ef8-133">필요한 경우 Lync Server 관리 셸을 사용 하 여 미리 정의 된 응답 그룹 업무 시간 및 휴일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="02ef8-134">응답 그룹 구성 도구 또는 Lync Server 관리 셸을 사용 하 여 사용자 지정 응답 그룹 업무 시간 및 휴일을 포함 하 여 워크플로 (헌트 그룹 또는 IVR (대화형 음성 응답) 호출 흐름)를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="02ef8-135">Lync Server 제어판을 통해 응답 그룹 구성 도구에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="02ef8-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="02ef8-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="02ef8-137">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="02ef8-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="02ef8-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="02ef8-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="02ef8-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="02ef8-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="02ef8-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="02ef8-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="02ef8-141">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="02ef8-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="02ef8-142"><a href="lync-server-2013-create-response-group-agent-groups.md">응답 그룹 에이전트 그룹 만들기 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="02ef8-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="02ef8-143"><a href="lync-server-2013-create-response-group-queues.md">Lync Server 2013에서 응답 그룹 큐 만들기</a></span><span class="sxs-lookup"><span data-stu-id="02ef8-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="02ef8-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">반드시 Lync Server 2013에서 응답 그룹 업무 시간 정의</a></span><span class="sxs-lookup"><span data-stu-id="02ef8-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="02ef8-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">반드시 Lync Server 2013에서 응답 그룹 휴일 집합 정의</a></span><span class="sxs-lookup"><span data-stu-id="02ef8-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="02ef8-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Lync Server 2013에서 워크플로 만들기 또는 수정</a></span><span class="sxs-lookup"><span data-stu-id="02ef8-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02ef8-147">반드시 응용 프로그램 수준 설정 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="02ef8-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="02ef8-148">Lync Server 관리 셸을 사용 하 여 기본 음악 대기 구성, 기본 음악 대기 오디오 파일, 에이전트의 되 걸기 유예 기간 및 통화 컨텍스트 구성을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="02ef8-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="02ef8-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="02ef8-150">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="02ef8-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="02ef8-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="02ef8-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="02ef8-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="02ef8-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="02ef8-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="02ef8-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="02ef8-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Lync Server 2013에서 응용 프로그램 수준 응답 그룹 설정 관리</a></span><span class="sxs-lookup"><span data-stu-id="02ef8-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02ef8-155">반드시 응답 그룹 관리 위임</span><span class="sxs-lookup"><span data-stu-id="02ef8-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="02ef8-156">사용자에 게 CsResponseGroupManager 역할을 할당 하 여 응답 그룹의 구성을 위임 합니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="02ef8-157">그러면 응답 그룹 관리자가 자신에 게 할당 된 응답 그룹을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="02ef8-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="02ef8-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="02ef8-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="02ef8-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="02ef8-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="02ef8-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="02ef8-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="02ef8-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="02ef8-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="02ef8-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="02ef8-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013에서 역할 기반 액세스 제어 계획</a></span><span class="sxs-lookup"><span data-stu-id="02ef8-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02ef8-164">응답 그룹 배포 확인</span><span class="sxs-lookup"><span data-stu-id="02ef8-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="02ef8-165">헌트 그룹 및 대화형 음성 응답 워크플로에 대한 통화 응답을 테스트하여 구성이 예상대로 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="02ef8-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

