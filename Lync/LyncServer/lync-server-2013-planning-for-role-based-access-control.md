---
title: 'Lync Server 2013: 역할 기반 액세스 제어 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1771eb906685294e588e0c67b1fa8fb1f67a8b6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="1a972-102">Lync Server 2013의 역할 기반 액세스 제어 계획</span><span class="sxs-lookup"><span data-stu-id="1a972-102">Planning for role-based access control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a972-103">_**마지막으로 수정한 주제:** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="1a972-103">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="1a972-104">보안을 위해 높은 표준을 유지 하면서 관리 작업을 위임할 수 있도록 Lync Server 2013는 RBAC (역할 기반 액세스 제어)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-104">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="1a972-105">RBAC를 사용 하는 경우 관리 역할에 사용자를 할당 하 여 관리 권한을 부여 받습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-105">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="1a972-106">Lync Server 2013에는 다양 한 기본 제공 관리 역할이 포함 되어 있으며 새 역할을 만들고 새 역할에 대 한 cmdlet의 사용자 지정 목록을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-106">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="1a972-107">또한 미리 정의된 RBAC 역할 및 사용자 지정 RBAC 역할 둘 다에 대해 허용되는 작업에 cmdlet 스크립트를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-107">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="1a972-108">향상 된 서버 보안 및 중앙 집중화</span><span class="sxs-lookup"><span data-stu-id="1a972-108">Better Server Security and Centralization</span></span>

<span data-ttu-id="1a972-109">RBAC를 사용 하는 경우 액세스 및 권한 부여는 사용자의 Lync 서버 역할에 정확히 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-109">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="1a972-110">이렇게 하면 관리자와 사용자에 게 해당 작업에 필요한 권한만 부여 하는 "최소 권한"의 보안 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-110">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1a972-111">RBAC 제한은 Lync Server 제어판 또는 Lync Server Management Shell을 사용 하 여 원격으로 작동 하는 관리자만 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-111">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="1a972-112">Lync Server를 실행 하는 서버에 앉아 있는 사용자는 RBAC에 의해 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-112">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="1a972-113">따라서 Lync 서버의 물리적 보안은 RBAC 제한을 유지 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-113">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="1a972-114">역할 및 범위</span><span class="sxs-lookup"><span data-stu-id="1a972-114">Roles and Scope</span></span>

<span data-ttu-id="1a972-115">RBAC에서는 특정 유형의 관리자 또는 기술자에 게 유용 하도록 디자인 된 cmdlet 목록을 사용 하도록 *역할이* 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-115">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician.</span></span> <span data-ttu-id="1a972-116">*범위* 는 역할에 정의 된 cmdlet이 작동할 수 있는 개체 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-116">A *scope* is the set of objects which the cmdlets defined in a role can operate on.</span></span> <span data-ttu-id="1a972-117">범위에 영향을 주는 개체는 사용자 계정 (조직 단위에 따라 그룹화) 또는 서버 (사이트별로 그룹화 됨) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-117">The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="1a972-118">다음 표에는 Lync Server에 미리 정의 된 역할이 나열 되어 있으며 각 역할에 대해 수행할 수 있는 작업 유형에 대 한 일반적인 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-118">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="1a972-119">네 번째 열에는 각 Lync Server 역할 (있는 경우)에 대 한 유사한 Microsoft Exchange Server 역할이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-119">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="1a972-120">미리 정의 된 관리 역할</span><span class="sxs-lookup"><span data-stu-id="1a972-120">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a972-121">역할</span><span class="sxs-lookup"><span data-stu-id="1a972-121">Role</span></span></th>
<th><span data-ttu-id="1a972-122">허용 된 작업</span><span class="sxs-lookup"><span data-stu-id="1a972-122">Tasks allowed</span></span></th>
<th><span data-ttu-id="1a972-123">기본 Active Directory 그룹</span><span class="sxs-lookup"><span data-stu-id="1a972-123">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="1a972-124">교환 동급</span><span class="sxs-lookup"><span data-stu-id="1a972-124">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a972-125">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-125">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-126">역할 만들기 및 역할에 사용자 지정 등 모든 관리 작업을 수행 하 고 모든 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-126">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles.</span></span> <span data-ttu-id="1a972-127">새 사이트, 풀 및 서비스를 추가 하 여 배포를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-127">Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="1a972-128">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-128">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-129">조직 관리</span><span class="sxs-lookup"><span data-stu-id="1a972-129">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a972-130">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-130">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-131">Lync Server 사용자를 사용 하거나 사용 하지 않도록 설정 하 고 사용자를 이동 하 고 기존 정책을 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-131">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="1a972-132">정책을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-132">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="1a972-133">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-133">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-134">메일 받는 사람</span><span class="sxs-lookup"><span data-stu-id="1a972-134">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a972-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-135">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-136">음성 관련 설정 및 정책을 만들고, 구성 하 고, 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-136">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="1a972-137">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-137">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-138">해당 없음</span><span class="sxs-lookup"><span data-stu-id="1a972-138">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a972-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-139">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-140">서버 및 서비스를 관리 하 고 모니터링 하 고 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-140">Can manage, monitor, and troubleshoot servers and services.</span></span> <span data-ttu-id="1a972-141">서버에 대 한 새 연결을 방지 하 고 서비스를 중지 및 시작 하 고 소프트웨어 업데이트를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-141">Can prevent new connections to servers, stop and start services, and apply software updates.</span></span> <span data-ttu-id="1a972-142">전역 구성 영향을 변경 하 여 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-142">Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="1a972-143">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-143">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-144">서버 관리</span><span class="sxs-lookup"><span data-stu-id="1a972-144">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a972-145">Csviewadministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-145">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-146">배포 상태를 모니터링 하기 위해 사용자 및 서버 정보를 포함 하 여 배포를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-146">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="1a972-147">Csviewadministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-147">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-148">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="1a972-148">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a972-149">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="1a972-149">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="1a972-150">사용자의 속성 및 정책을 포함 하 여 배포를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-150">Can view the deployment, including user's properties and policies.</span></span> <span data-ttu-id="1a972-151">특정 문제 해결 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-151">Can run specific troubleshooting tasks.</span></span> <span data-ttu-id="1a972-152">사용자 속성 또는 정책, 서버 구성 또는 서비스를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-152">Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="1a972-153">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="1a972-153">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="1a972-154">기술</span><span class="sxs-lookup"><span data-stu-id="1a972-154">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a972-155">CsArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-155">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-156">보관 구성 및 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-156">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="1a972-157">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-157">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-158">보존 관리, 법률 보류</span><span class="sxs-lookup"><span data-stu-id="1a972-158">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a972-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-159">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-160">사이트 내에서 응답 그룹 응용 프로그램의 구성을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-160">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="1a972-161">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-161">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-162">해당 없음</span><span class="sxs-lookup"><span data-stu-id="1a972-162">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a972-163">CsLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-163">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-164">9-1-1-1-1 위치 및 네트워크 식별자 만들기, 그리고 서로 연결을 비롯 한 향상 된 (E9-1) 관리 수준의 최소 권한입니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-164">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other.</span></span> <span data-ttu-id="1a972-165">이 역할은 항상 전역 범위를 사용 하 여 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-165">This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="1a972-166">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-166">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-167">해당 없음</span><span class="sxs-lookup"><span data-stu-id="1a972-167">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a972-168">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="1a972-168">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="1a972-169">특정 응답 그룹을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-169">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="1a972-170">CSResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="1a972-170">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="1a972-171">해당 없음</span><span class="sxs-lookup"><span data-stu-id="1a972-171">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a972-172">CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-172">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-173">영구 채팅 기능 및 특정 영구 채팅방을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-173">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="1a972-174">CSPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="1a972-174">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="1a972-175">해당 없음</span><span class="sxs-lookup"><span data-stu-id="1a972-175">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1a972-176">Lync Server에 제공 되는 미리 정의 된 모든 역할에는 전역 범위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-176">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="1a972-177">최소 권한 사례를 따르려면 제한 된 서버 또는 사용자만 관리 하려는 경우 전역 범위를 사용 하 여 역할에 사용자를 할당 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-177">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="1a972-178">이 작업을 수행 하려면 기존 역할에 기반을 둔 역할을 만들 수 있지만 범위가 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-178">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="1a972-179">범위 역할 만들기</span><span class="sxs-lookup"><span data-stu-id="1a972-179">Creating a Scoped Role</span></span>

<span data-ttu-id="1a972-180">제한 된 범위 (범위 역할)를 사용 하 여 역할을 만드는 경우 범위를 기반으로 하는 기존 역할과 역할을 할당할 Active Directory 그룹을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-180">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="1a972-181">사용자가 지정한 Active Directory 그룹을 이미 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-181">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="1a972-182">다음 cmdlet은 미리 정의 된 관리 역할 중 하나의 권한을 가진 역할을 만드는 예 이며 범위가 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-182">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="1a972-183">새 역할을 만듭니다 `Site01 Server Administrators`.</span><span class="sxs-lookup"><span data-stu-id="1a972-183">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="1a972-184">역할에는 미리 정의 된 CsServerAdministrator 역할의 기능이 있지만, Site01 사이트에 있는 서버에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-184">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="1a972-185">이 cmdlet이 작동 하려면 Site01 사이트를 이미 정의 하 고 명명 된 `Site01 Server Administrators` 유니버설 보안 그룹이 이미 존재 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-185">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="1a972-186">이 cmdlet을 실행 한 후에는 `Site01 Server Administrators` 그룹의 구성원 인 모든 사용자에 게 Site01의 서버에 대 한 서버 관리자 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-186">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="1a972-187">또한 나중에이 유니버설 보안 그룹에 추가 되는 사용자도이 역할의 권한을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-187">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="1a972-188">역할 자체와 자신에 게 할당 된 유니버설 보안 그룹이 호출 `Site01 Server Administrators`되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-188">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="1a972-189">다음 예제에서는 서버 범위 대신 사용자 범위를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-189">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="1a972-190">이는 영업 `Sales Users Administrator` 조직 구성 단위에서 사용자 계정을 관리 하는 역할을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-190">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="1a972-191">이 cmdlet을 사용 하려면 Sales Administrator 유니버설 보안 그룹을 이미 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-191">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="1a972-192">새 역할 만들기</span><span class="sxs-lookup"><span data-stu-id="1a972-192">Creating a New Role</span></span>

<span data-ttu-id="1a972-193">미리 정의 된 역할 중 하나 또는 스크립트 또는 모듈 집합에 없는 cmdlet 집합에 액세스할 수 있는 역할을 만들려면 미리 정의 된 역할 중 하나를 템플릿으로 사용 하 여 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-193">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template.</span></span> <span data-ttu-id="1a972-194">역할을 실행할 수 있는 스크립트와 모듈은 다음 위치에 저장 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-194">Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="1a972-195">Lync\\모듈 경로-기본적으로 C: 프로그램 파일\\공통 파일\\Microsoft lync Server 2013\\모듈 Lync\\</span><span class="sxs-lookup"><span data-stu-id="1a972-195">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="1a972-196">사용자 스크립트\\경로-기본적으로 C: 프로그램 파일\\공통 파일\\Microsoft Lync Server 2013 AdminScripts\\</span><span class="sxs-lookup"><span data-stu-id="1a972-196">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="1a972-197">새 역할을 만들려면 **새 CsAdminRole** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-197">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="1a972-198">**새-CsAdminRole**을 실행 하기 전에 먼저이 역할과 연결 될 기본 유니버설 보안 그룹을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-198">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="1a972-199">다음 cmdlet은 새 역할을 만드는 예제 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-199">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="1a972-200">라는 `MyHelpDeskScriptRole`새 역할 유형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-200">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="1a972-201">새 역할에는 미리 정의 된 CsHelpDesk 역할의 기능이 있으며 "testscript" 라는 스크립트에서 함수를 추가로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-201">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="1a972-202">이 cmdlet이 제대로 작동 하려면 먼저 유니버설 보안 그룹 MyHelpDeskScriptRole를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-202">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="1a972-203">이 cmdlet을 실행 한 후에는이 역할에 사용자를 직접 할당 하거나 (전역 범위를 포함 하는 경우)이 역할을 기반으로 하는 범위 역할을 만들 수 있습니다 (이 경우에는이 문서의 이전에 범위 역할을 만들 때 설명).</span><span class="sxs-lookup"><span data-stu-id="1a972-203">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="1a972-204">사용자에 게 역할 지정</span><span class="sxs-lookup"><span data-stu-id="1a972-204">Assigning Roles to Users</span></span>

<span data-ttu-id="1a972-205">각 Lync Server 역할이 기본 Active Directory 유니버설 보안 그룹과 연결 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-205">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="1a972-206">기본 그룹에 추가 하는 모든 사용자는 해당 역할의 기능을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-206">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="1a972-207">이전 섹션의 예제에서는 새 역할을 만들고 기존 유니버설 보안 그룹을 새 역할에 할당 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-207">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="1a972-208">한 명 이상의 사용자에 게 기존 역할을 할당 하려면 해당 사용자를 역할과 연결 된 그룹에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-208">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="1a972-209">개별 사용자와 유니버설 보안 그룹을 이러한 그룹에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-209">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="1a972-210">예를 들어 **Csadministrator** 역할은 Active Directory의 **CS 관리자** 유니버설 보안 그룹에 자동으로 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-210">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="1a972-211">이 유니버설 보안 그룹은 Lync Server를 배포할 때 Active Directory에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-211">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="1a972-212">사용자 또는 그룹에 게이 권한을 부여 하려면, 간단히 **CS 관리자** 그룹에 추가 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-212">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="1a972-213">각 역할에 해당 하는 기본 Active Directory 그룹에 추가 되는 여러 RBAC 역할이 사용자에 게 제공 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-213">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="1a972-214">역할을 만들 때 나중에 기본 Active Directory 그룹에 추가 되는 사용자는 해당 역할의 기능을 얻게 된다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="1a972-214">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="1a972-215">역할의 기능 수정</span><span class="sxs-lookup"><span data-stu-id="1a972-215">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="1a972-216">역할이 실행할 수 있는 cmdlet 및 스크립트 목록을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-216">You can modify the list of cmdlets and scripts that a role can run.</span></span> <span data-ttu-id="1a972-217">사용자 지정 역할이 실행할 수 있는 cmdlet 및 스크립트를 수정할 수 있지만 미리 정의 된 역할에 대 한 스크립트만 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-217">You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles.</span></span> <span data-ttu-id="1a972-218">입력 하는 각 cmdlet은 cmdlet 또는 스크립트를 추가, 제거 또는 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-218">Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="1a972-219">역할을 수정 하려면 **Set-CsAdminRole** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-219">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="1a972-220">다음 cmdlet은 역할에서 하나의 스크립트를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-220">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="1a972-221">RBAC에 대 한 계획</span><span class="sxs-lookup"><span data-stu-id="1a972-221">Planning for RBAC</span></span>

<span data-ttu-id="1a972-222">Lync Server 배포에 대 한 모든 종류의 관리자 권한을 부여할 각 사용자에 대해 수행 해야 하는 작업을 정확히 고려 하 고 해당 작업에 필요한 최소 권한 및 범위를 가진 역할에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-222">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="1a972-223">필요한 경우 **Set-CsAdminRole** cmdlet을 사용 하 여이 사용자의 작업에 필요한 cmdlet만 사용 하 여 새 역할을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-223">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="1a972-224">CsAdministrator 역할이 있는 사용자는 CsAdministrator를 기반으로 하는 역할을 포함 하 여 모든 유형의 역할을 만들고 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-224">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them.</span></span> <span data-ttu-id="1a972-225">가장 좋은 방법은 신뢰할 수 있는 사용자의 소규모 집합에 CsAdministrator 역할을 할당 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1a972-225">The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

