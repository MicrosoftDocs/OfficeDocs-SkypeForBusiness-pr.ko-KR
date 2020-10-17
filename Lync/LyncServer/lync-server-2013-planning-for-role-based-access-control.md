---
title: 'Lync Server 2013: 역할 기반 액세스 제어 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65f6411023c80a527cff31c389a8283d090dfc0d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528035"
---
# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="a0fcf-102">Lync Server 2013에서 역할 기반 액세스 제어 계획</span><span class="sxs-lookup"><span data-stu-id="a0fcf-102">Planning for role-based access control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0fcf-103">_**마지막으로 수정 된 항목:** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="a0fcf-103">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="a0fcf-104">보안에 대 한 높은 표준을 유지 하면서 관리 작업을 위임할 수 있도록 하기 위해 Lync Server 2013에서는 RBAC (역할 기반 액세스 제어)를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-104">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="a0fcf-105">RBAC를 사용하면 사용자를 관리 역할에 지정하여 관리 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-105">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="a0fcf-106">Lync Server 2013에는 다양 한 기본 제공 관리 역할 집합이 포함 되어 있으며, 새 역할을 만들고 각각의 새 역할에 대해 cmdlet의 사용자 지정 목록을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-106">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="a0fcf-107">또한 미리 정의된 RBAC 역할 및 사용자 지정 RBAC 역할 모두의 허용된 작업에 cmdlet 스크립트를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-107">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="a0fcf-108">향상된 서버 보안 및 중앙 집중화</span><span class="sxs-lookup"><span data-stu-id="a0fcf-108">Better Server Security and Centralization</span></span>

<span data-ttu-id="a0fcf-109">RBAC에서는 액세스 및 권한 부여가 사용자의 Lync Server 역할을 정확히 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-109">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="a0fcf-110">따라서 "최소 권한"의 보안 원칙을 적용하고 관리자 및 사용자에게 해당 작업을 수행하는 데 필요한 권한만 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-110">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a0fcf-111">RBAC 제한은 Lync Server 제어판 또는 Lync Server 관리 셸을 사용 하 여 원격으로 작동 하는 관리자 에게만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-111">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="a0fcf-112">Lync Server를 실행 하는 서버에서 사용 하는 사용자는 RBAC에 따라 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-112">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="a0fcf-113">따라서 Lync Server의 물리적 보안은 RBAC 제한을 유지 하는 데 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-113">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="a0fcf-114">역할 및 범위</span><span class="sxs-lookup"><span data-stu-id="a0fcf-114">Roles and Scope</span></span>

<span data-ttu-id="a0fcf-p104">RBAC에서 *역할*은 특정 유형의 관리자 또는 기술자에게 유용하도록 디자인된 cmdlet 목록을 사용하도록 설정됩니다. *범위*는 역할에 정의된 cmdlet이 작업을 수행할 수 있는 개체 집합입니다. 이 범위의 영향을 받는 개체는 사용자 계정(조직 구성 단위별로 그룹화) 또는 서버(사이트별로 그룹화)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-p104">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician. A *scope* is the set of objects which the cmdlets defined in a role can operate on. The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="a0fcf-118">다음 표에는 Lync Server의 미리 정의 된 역할과 각 역할에서 수행할 수 있는 작업 유형에 대 한 일반적인 개요가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-118">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="a0fcf-119">넷째 열에는 각 Lync Server 역할에 대 한 유사 Microsoft Exchange 서버 역할 (있는 경우)이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-119">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="a0fcf-120">미리 정의된 관리 역할</span><span class="sxs-lookup"><span data-stu-id="a0fcf-120">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a0fcf-121">역할</span><span class="sxs-lookup"><span data-stu-id="a0fcf-121">Role</span></span></th>
<th><span data-ttu-id="a0fcf-122">허용되는 작업</span><span class="sxs-lookup"><span data-stu-id="a0fcf-122">Tasks allowed</span></span></th>
<th><span data-ttu-id="a0fcf-123">기본 Active Directory 그룹</span><span class="sxs-lookup"><span data-stu-id="a0fcf-123">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="a0fcf-124">해당 Exchange 역할</span><span class="sxs-lookup"><span data-stu-id="a0fcf-124">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0fcf-125">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-125">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-p106">모든 관리 작업을 수행하고 역할 만들기, 역할에 사용자 지정 등의 모든 설정을 수정할 수 있습니다. 새 사이트, 풀 및 서비스를 추가하여 배포를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-p106">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles. Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-128">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-128">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-129">조직 관리</span><span class="sxs-lookup"><span data-stu-id="a0fcf-129">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0fcf-130">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-130">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-131">Lync Server에 대해 사용자를 사용 하거나 사용 하지 않도록 설정 하 고 사용자를 이동 하 고 기존 정책을 사용자에 게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-131">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="a0fcf-132">정책을 수정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-132">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-133">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-133">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-134">메일 받는 사람</span><span class="sxs-lookup"><span data-stu-id="a0fcf-134">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0fcf-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-135">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-136">음성 관련 설정 및 정책을 만들고 구성하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-136">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-137">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-137">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-138">해당 없음</span><span class="sxs-lookup"><span data-stu-id="a0fcf-138">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0fcf-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-139">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-p108">서버 및 서비스를 관리 및 모니터링하고 관련 문제를 해결할 수 있습니다. 서버에 대한 새 연결을 방지하고, 서비스를 시작하거나 중지하고, 소프트웨어 업데이트를 적용할 수 있습니다. 전역 구성에 영향을 주는 변경 작업은 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-p108">Can manage, monitor, and troubleshoot servers and services. Can prevent new connections to servers, stop and start services, and apply software updates. Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-143">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-143">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-144">서버 관리</span><span class="sxs-lookup"><span data-stu-id="a0fcf-144">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0fcf-145">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-145">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-146">사용자 및 서버 정보를 포함하여 배포를 보고 배포 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-146">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-147">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-147">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-148">보기 전용 조직 관리</span><span class="sxs-lookup"><span data-stu-id="a0fcf-148">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0fcf-149">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="a0fcf-149">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-p109">사용자의 속성 및 정책을 포함하여 배포를 볼 수 있으며, 특정 문제 해결 작업을 실행할 수 있습니다. 사용자 속성 또는 정책, 서버 구성 또는 서비스를 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-p109">Can view the deployment, including user's properties and policies. Can run specific troubleshooting tasks. Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-153">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="a0fcf-153">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-154">HelpDesk</span><span class="sxs-lookup"><span data-stu-id="a0fcf-154">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0fcf-155">CsArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-155">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-156">보관 구성 및 정책을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-156">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-157">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-157">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-158">보유 관리, 법적 보유</span><span class="sxs-lookup"><span data-stu-id="a0fcf-158">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0fcf-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-159">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-160">사이트 내에서 응답 그룹 응용 프로그램 구성을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-160">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-161">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-161">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-162">해당 없음</span><span class="sxs-lookup"><span data-stu-id="a0fcf-162">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0fcf-163">CsLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-163">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-p110">E9-1-1(Enhanced 9-1-1) 위치 및 네트워크 식별자를 만들고 서로 연결하는 등 E9-1-1 관리에 대한 최하위 수준의 권한을 가집니다. 이 역할은 항상 전역 범위로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-p110">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other. This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-166">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-166">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-167">해당 없음</span><span class="sxs-lookup"><span data-stu-id="a0fcf-167">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0fcf-168">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="a0fcf-168">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-169">특정 응답 그룹을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-169">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-170">CSResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="a0fcf-170">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-171">해당 없음</span><span class="sxs-lookup"><span data-stu-id="a0fcf-171">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0fcf-172">CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-172">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-173">영구 채팅 기능 및 특정 영구 채팅방을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-173">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-174">CSPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="a0fcf-174">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="a0fcf-175">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="a0fcf-175">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a0fcf-176">Lync Server에서 제공 되는 미리 정의 된 모든 역할에는 전역 범위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-176">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="a0fcf-177">최소 권한 원칙을 따르기 위해서는 제한된 서버 또는 사용자 집합만 관리하려는 경우 전체 범위로 설정된 역할에 사용자를 지정해서는 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-177">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="a0fcf-178">이를 위해서는 기존 역할을 기반으로 하지만 보다 제한된 범위를 갖는 역할을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-178">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="a0fcf-179">범위가 지정된 역할 만들기</span><span class="sxs-lookup"><span data-stu-id="a0fcf-179">Creating a Scoped Role</span></span>

<span data-ttu-id="a0fcf-180">제한된 범위를 갖는 역할(범위가 지정된 역할)을 만들 때는 역할의 기반이 되는 기존 역할 및 역할에 지정할 Active Directory 그룹과 함께 범위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-180">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="a0fcf-181">지정하는 Active Directory 그룹은 이미 만들어져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-181">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="a0fcf-182">다음 cmdlet은 미리 정의된 관리 역할 중 하나의 권한을 갖지만 범위가 제한된 역할을 만드는 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-182">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="a0fcf-183">라는 새 역할을 만듭니다 `Site01 Server Administrators` .</span><span class="sxs-lookup"><span data-stu-id="a0fcf-183">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="a0fcf-184">이 역할은 미리 정의된 CsServerAdministrator 역할의 기능을 갖지만 Site01 사이트에 있는 서버로만 범위가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-184">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="a0fcf-185">이 cmdlet이 작동 하려면 Site01 사이트가 이미 정의 되어 있어야 하며, 라는 유니버설 보안 그룹이 `Site01 Server Administrators` 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-185">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="a0fcf-186">이 cmdlet이 실행 된 후에는 그룹의 구성원 인 모든 사용자에 게 `Site01 Server Administrators` Site01 서버에 대 한 서버 관리자 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-186">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="a0fcf-187">또한 나중에이 유니버설 보안 그룹에 추가 되는 모든 사용자는이 역할의 권한을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-187">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="a0fcf-188">역할 자체와 자신에 게 할당 된 유니버설 보안 그룹이 호출 된다는 점에 유의 하십시오 `Site01 Server Administrators` .</span><span class="sxs-lookup"><span data-stu-id="a0fcf-188">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="a0fcf-189">다음 예에서는 서버 범위 대신 사용자 범위를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-189">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="a0fcf-190">`Sales Users Administrator`영업 조직 구성 단위에서 사용자 계정을 관리 하는 역할을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-190">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="a0fcf-191">이 cmdlet이 작동 하려면 Sales사용자 관리자 유니버설 보안 그룹이 이미 만들어져 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-191">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="a0fcf-192">새 역할 만들기</span><span class="sxs-lookup"><span data-stu-id="a0fcf-192">Creating a New Role</span></span>

<span data-ttu-id="a0fcf-p115">미리 정의된 역할 중에서 찾을 수 없는 cmdlet 집합에 액세스하거나 스크립트 또는 모듈 집합에 액세스하는 역할을 만들려는 경우에도 미리 정의된 역할 중 하나를 템플릿으로 사용해서 작업을 시작합니다. 역할이 실행할 수 있어야 하는 스크립트 및 모듈은 다음 위치에 저장되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-p115">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template. Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="a0fcf-195">Lync 모듈 경로 (기본적으로 C: \\ 프로그램 파일 \\ 공용 파일) \\ Microsoft lync Server 2013 \\ Modules \\ Lync</span><span class="sxs-lookup"><span data-stu-id="a0fcf-195">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="a0fcf-196">사용자 스크립트 경로 (기본적으로 C: \\ Program files \\ Common Files \\ Microsoft Lync Server 2013 \\ \adminscripts</span><span class="sxs-lookup"><span data-stu-id="a0fcf-196">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="a0fcf-197">새 역할을 만들려면 **New-CsAdminRole** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-197">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="a0fcf-198">**새-CsAdminRole**을 실행 하기 전에 먼저이 역할과 연결 될 기본 유니버설 보안 그룹을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-198">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="a0fcf-199">다음 cmdlet은 새 역할을 만드는 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-199">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="a0fcf-200">라는 새 역할 유형을 만듭니다 `MyHelpDeskScriptRole` .</span><span class="sxs-lookup"><span data-stu-id="a0fcf-200">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="a0fcf-201">이 새 역할은 미리 정의된 CsHelpDesk 역할의 기능을 포함하며 추가적으로 “testscript”라는 스크립트의 기능을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-201">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="a0fcf-202">이 cmdlet이 작동 하려면 먼저 유니버설 보안 그룹 MyHelpDeskScriptRole를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-202">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="a0fcf-203">이 cmdlet이 실행된 후에는 이 역할에 사용자를 직접 지정하거나(전역 범주를 갖는 경우), 이 문서의 앞 부분에 있는 범위가 지정된 역할 만들기에서 설명한 대로 이 역할을 기반으로 범위가 지정된 역할을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-203">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="a0fcf-204">사용자에게 역할 지정</span><span class="sxs-lookup"><span data-stu-id="a0fcf-204">Assigning Roles to Users</span></span>

<span data-ttu-id="a0fcf-205">각 Lync Server 역할은 기본 Active Directory 유니버설 보안 그룹과 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-205">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="a0fcf-206">기본 그룹에 추가하는 모든 사용자는 해당 역할의 기능을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-206">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="a0fcf-207">이전 섹션의 예에서는 새 역할을 만들고 기존 유니버설 보안 그룹을 새 역할에 할당 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-207">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="a0fcf-208">한 명 이상의 사용자에게 기존 역할을 지정하려면 해당 역할과 연결된 그룹에 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-208">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="a0fcf-209">개별 사용자와 유니버설 보안 그룹을 모두 이러한 그룹에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-209">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="a0fcf-210">예를 들어 **Csadministrator** 역할은 Active Directory의 **CS Administrators** 유니버설 보안 그룹에 자동으로 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-210">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="a0fcf-211">이 유니버설 보안 그룹은 Lync Server를 배포할 때 Active Directory에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-211">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="a0fcf-212">사용자 또는 그룹에 이 권한을 부여하려면 해당 사용자 또는 그룹을 **CS Administrators** 그룹에 추가하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-212">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="a0fcf-213">각 역할에 해당하는 기본 Active Directory 그룹에 사용자를 추가하여 사용자에게 여러 RBAC 역할을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-213">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="a0fcf-214">역할을 만든 경우 기본 Active Directory 그룹에 나중에 추가되는 사용자에게도 해당 역할의 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-214">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="a0fcf-215">역할의 기능 수정</span><span class="sxs-lookup"><span data-stu-id="a0fcf-215">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="a0fcf-p121">역할이 실행할 수 있는 cmdlet 및 스크립트 목록을 수정할 수 있습니다. 사용자 지정 역할이 실행할 수 있는 cmdlet 및 스크립트를 모두 수정할 수 있지만 미리 정의된 역할의 경우 스크립트만 수정할 수 있습니다. 입력하는 각 cmdlet은 cmdlet 또는 스크립트를 추가, 제거 또는 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-p121">You can modify the list of cmdlets and scripts that a role can run. You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles. Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="a0fcf-219">역할을 수정하려면 **Set-CsAdminRole** cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-219">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="a0fcf-220">다음 cmdlet은 역할에서 스크립트 하나를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-220">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="a0fcf-221">RBAC 계획</span><span class="sxs-lookup"><span data-stu-id="a0fcf-221">Planning for RBAC</span></span>

<span data-ttu-id="a0fcf-222">Lync Server 배포에 대 한 관리 권한을 부여할 각 사용자에 대해 수행 해야 하는 작업을 정확 하 게 고려 하 고 작업에 필요한 최소 권한 및 범위를 가진 역할에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-222">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="a0fcf-223">필요에 따라 **Set-CsAdminRole** cmdlet을 사용해서 이 사용자의 작업에 필요한 cmdlet만 포함된 새 역할을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-223">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="a0fcf-p124">CsAdministrator 역할을 가진 사용자는 CsAdministrator를 기반으로 하는 역할을 포함하여 모든 유형의 역할을 만들고 각 역할에 사용자를 지정할 수 있습니다. 따라서 신뢰할 수 있는 소수의 사용자에게만 CsAdministrator 역할을 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcf-p124">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them. The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

