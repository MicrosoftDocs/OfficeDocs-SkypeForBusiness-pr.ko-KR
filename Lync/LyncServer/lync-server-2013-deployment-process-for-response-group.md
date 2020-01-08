---
title: 'Lync Server 2013: 응답 그룹에 대 한 배포 프로세스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2151532b31f3c1660be98d11ac9d9c337ffecb64
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="4e760-102">Lync Server 2013의 응답 그룹에 대 한 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="4e760-102">Deployment process for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e760-103">_**마지막으로 수정한 주제:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="4e760-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="4e760-104">이 섹션에서는 응답 그룹 응용 프로그램 배포 단계에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="4e760-105">응답 그룹 배포 프로세스</span><span class="sxs-lookup"><span data-stu-id="4e760-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e760-106">단계의</span><span class="sxs-lookup"><span data-stu-id="4e760-106">Phase</span></span></th>
<th><span data-ttu-id="4e760-107">방법은</span><span class="sxs-lookup"><span data-stu-id="4e760-107">Steps</span></span></th>
<th><span data-ttu-id="4e760-108">필요한</span><span class="sxs-lookup"><span data-stu-id="4e760-108">Permissions</span></span></th>
<th><span data-ttu-id="4e760-109">배포 설명서</span><span class="sxs-lookup"><span data-stu-id="4e760-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e760-110">응답 그룹 응용 프로그램 설치</span><span class="sxs-lookup"><span data-stu-id="4e760-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="4e760-111">엔터프라이즈 음성을 배포할 때 응답 그룹 응용 프로그램이 기본적으로 설치 되 고 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="4e760-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="4e760-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="4e760-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Lync Server 2013에서 엔터프라이즈 음성 배포</a></span><span class="sxs-lookup"><span data-stu-id="4e760-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e760-114">응답 그룹의 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="4e760-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="4e760-115">Lync server 제어판, 응답 그룹 구성 도구, 에이전트 ' 로그인 및 로그 아웃 콘솔, 응답 그룹 클라이언트 웹 서비스는 웹 서비스의 일부로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="4e760-116">웹 서비스는 엔터프라이즈 버전 풀이나 Standard Edition 서버를 배포 하는 경우에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="4e760-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="4e760-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="4e760-118"><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 배포</a></span><span class="sxs-lookup"><span data-stu-id="4e760-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e760-119">Lync 2013 및 Enterprise Voice에 대해 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="4e760-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="4e760-120">Lync Server 및 Enterprise Voice의 에이전트로 사용할 사용자를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="4e760-121">사용자는 에이전트 그룹에 추가 하기 전에 먼저 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="4e760-122">일반적으로 사용자는 Enterprise Edition 또는 Standard Edition 서버 배포 중에 Lync Server를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="4e760-123">엔터프라이즈 음성 배포 중에 사용자가 엔터프라이즈 음성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="4e760-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="4e760-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="4e760-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="4e760-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="4e760-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4e760-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4e760-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Lync Server 2013의 사용자 계정을 사용 하지 않도록 설정 하거나 다시 사용 하도록 설정</a></span><span class="sxs-lookup"><span data-stu-id="4e760-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="4e760-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Lync Server 2013에서 엔터프라이즈 음성에 대 한 사용자 활성화</a></span><span class="sxs-lookup"><span data-stu-id="4e760-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e760-129">에이전트 그룹, 큐 및 워크플로로 구성 된 응답 그룹을 만들고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="4e760-130">Lync Server 제어판 또는 Lync Server 관리 셸을 사용 하 여 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="4e760-131">에이전트 그룹을 만들고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="4e760-132">큐를 만들고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="4e760-133">선택적으로 Lync Server Management Shell을 사용 하 여 미리 정의 된 응답 그룹 비즈니스 시간 및 휴일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="4e760-134">응답 그룹 구성 도구 또는 Lync Server Management Shell을 사용 하 여 사용자 지정 응답 그룹 비즈니스 시간 및 휴일을 비롯 한 워크플로 (헌트 그룹 또는 IVR (대화형 음성 응답) 통화 흐름)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="4e760-135">Lync Server 제어판을 통해 응답 그룹 구성 도구에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="4e760-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="4e760-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="4e760-137">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="4e760-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="4e760-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="4e760-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="4e760-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4e760-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="4e760-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4e760-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="4e760-141">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="4e760-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="4e760-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Lync Server 2013에서 응답 그룹 에이전트 그룹 만들기</a></span><span class="sxs-lookup"><span data-stu-id="4e760-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="4e760-143"><a href="lync-server-2013-create-response-group-queues.md">Lync Server 2013에서 응답 그룹 큐 만들기</a></span><span class="sxs-lookup"><span data-stu-id="4e760-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="4e760-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">) Lync Server 2013에서 응답 그룹 비즈니스 시간 정의</a></span><span class="sxs-lookup"><span data-stu-id="4e760-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="4e760-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">) Lync Server 2013에서 응답 그룹의 휴일 집합 정의</a></span><span class="sxs-lookup"><span data-stu-id="4e760-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="4e760-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Lync Server 2013에서 워크플로 만들기 또는 수정</a></span><span class="sxs-lookup"><span data-stu-id="4e760-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e760-147">) 응용 프로그램 수준 설정 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="4e760-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="4e760-148">Lync Server Management Shell을 사용 하 여 기본 음악 보관 구성, 기본 음악 오디오 파일, 에이전트 ringback 유예 기간, 통화 컨텍스트 구성을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="4e760-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="4e760-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="4e760-150">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="4e760-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="4e760-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="4e760-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="4e760-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4e760-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="4e760-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4e760-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4e760-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Lync Server 2013의 응용 프로그램 수준 응답 그룹 설정 관리</a></span><span class="sxs-lookup"><span data-stu-id="4e760-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e760-155">) 응답 그룹의 관리 위임</span><span class="sxs-lookup"><span data-stu-id="4e760-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="4e760-156">응답 그룹의 구성을 위임 하도록 CsResponseGroupManager 역할을 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="4e760-157">그러면 응답 그룹 관리자가 자신에 게 할당 된 응답 그룹을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="4e760-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="4e760-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="4e760-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="4e760-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="4e760-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="4e760-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="4e760-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4e760-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="4e760-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4e760-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4e760-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013의 역할 기반 액세스 제어 계획</a></span><span class="sxs-lookup"><span data-stu-id="4e760-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e760-164">응답 그룹 배포 확인</span><span class="sxs-lookup"><span data-stu-id="4e760-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="4e760-165">헌트 그룹과 대화형 음성 응답 워크플로에 대 한 응답 전화를 테스트 하 여 구성이 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e760-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
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

