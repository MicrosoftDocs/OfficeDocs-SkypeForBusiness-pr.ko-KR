---
title: 'Lync Server 2013: 영구 채팅 서버 테이블 목록'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4902f0710752dd38c146b01bddcc44e135735201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="bd145-102">Lync Server 2013의 영구 채팅 서버 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="bd145-102">List of Persistent Chat Server tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd145-103">_**마지막으로 수정한 주제:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="bd145-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="bd145-104">영구 채팅 데이터베이스 스키마는 다음 테이블로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-104">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="bd145-105">Active Directory 동기화</span><span class="sxs-lookup"><span data-stu-id="bd145-105">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd145-106">테이블로</span><span class="sxs-lookup"><span data-stu-id="bd145-106">Table</span></span></th>
<th><span data-ttu-id="bd145-107">설명</span><span class="sxs-lookup"><span data-stu-id="bd145-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd145-108"><a href="lync-server-2013-tbladcookie.md">Lync Server 2013의 tblADCookie</a></span><span class="sxs-lookup"><span data-stu-id="bd145-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-109">현재 LDAP (Lightweight Directory Access Protocol) 동기화 쿠키가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-109">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="bd145-110">각 행은 영구 채팅 서버에서 변경 내용을 적극적으로 모니터링 하는 Active Directory 도메인 서비스 도메인에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-110">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="bd145-111">(이 표에는 영구 채팅 서버와 관련 된 Active Directory 도메인만 표시 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="bd145-111">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd145-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013의 tblPrincipalMemberDifference</a></span><span class="sxs-lookup"><span data-stu-id="bd145-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-113">Active directory 동기화 단계에 의해 아직 처리 되지 않은 그룹 구성원 변경 내용 (구성원 추가 및 제거 됨)이 포함 되어 있으며 Active Directory Sync의 첫 번째 단계에서 사용 되는 임시 테이블 (tblADUpdates 테이블 포함) 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-113">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="bd145-114">멤버 자격 변경 내용은 tblPrincipal 테이블에 나열 된 그룹 또는 이미 나열 된 구성원에만 저장, 처리 또는 모두 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-114">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd145-115"><a href="lync-server-2013-tbladupdates.md">Lync Server 2013의 tblADUpdates</a></span><span class="sxs-lookup"><span data-stu-id="bd145-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-116">Active directory 동기화 단계에 의해 아직 처리 되지 않은 Active Directory 도메인 서비스에 대 한 변경 내용이 포함 되어 있으며, 임시 테이블 (tblPrincipalMemberDifference 테이블 포함) 중 하나를 사용 하 여 Active Directory의 첫 번째 단계에서 사용 됨 시키십시오.</span><span class="sxs-lookup"><span data-stu-id="bd145-116">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="bd145-117">Active Directory에 대 한 변경 내용은 tblPrincipal 테이블에 이미 나열 된 보안 주체에 대해서만 저장, 처리 또는 모두 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-117">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd145-118"><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013의 tblPrincipalMembers</a></span><span class="sxs-lookup"><span data-stu-id="bd145-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-119">주도자 구성원 자격을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-119">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd145-120"><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013의 tblPrincipalMeta</a></span><span class="sxs-lookup"><span data-stu-id="bd145-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-121">Active Directory에서 새로 고쳐야 하는 사용자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-121">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd145-122"><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013의 tblSkippedAffiliations</a></span><span class="sxs-lookup"><span data-stu-id="bd145-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-123">일반적으로 Active Directory access 오류로 인해 몇 가지 이유로 새로 고칠 수 없는 소속을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-123">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="bd145-124">이 표는 정보를 제공 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-124">This table is for informational purposes only.</span></span> <span data-ttu-id="bd145-125">해당 콘텐츠는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-125">Its content is not used.</span></span></p>
<p><span data-ttu-id="bd145-126">올바르게 새로 고칠 수 없는 소속을 포함 하는 주체는 tblPrincipalMeta 테이블에 보관 되며 또 다른 새로 고칠 기회가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-126">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="bd145-127">주도자, 소속, 노드, 범위, 역할</span><span class="sxs-lookup"><span data-stu-id="bd145-127">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd145-128">테이블로</span><span class="sxs-lookup"><span data-stu-id="bd145-128">Table</span></span></th>
<th><span data-ttu-id="bd145-129">설명</span><span class="sxs-lookup"><span data-stu-id="bd145-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd145-130"><a href="lync-server-2013-tblprincipaltype.md">Lync Server 2013의 tblPrincipalType</a></span><span class="sxs-lookup"><span data-stu-id="bd145-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-131">TblPrincipal 테이블에 있는 항목을 분류 하는 principal 형식이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-131">Contains principal types to categorize what is in the tblPrincipal table.</span></span> <span data-ttu-id="bd145-132">이 테이블은 정적입니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-132">This table is static.</span></span> <span data-ttu-id="bd145-133">데이터베이스를 만드는 동안 설정 되며 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-133">It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd145-134"><a href="lync-server-2013-tblprincipal.md">Lync Server 2013의 tblPrincipal</a></span><span class="sxs-lookup"><span data-stu-id="bd145-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-135">모든 주체 (사용자, 폴더, 그룹 등)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-135">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="bd145-136">영구 채팅 서버는이를 단순한 혼합 목록으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-136">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="bd145-137">다양 한 열은 각 주체의 유형을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-137">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="bd145-138">이러한 주도자는 대부분 Active Directory에 저장 된 개체의 캐시 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-138">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="bd145-139">이러한 Active Directory 개체의 주 테이블에서 캐시 된 복사본을 만드는 것을 <em>프로비저닝</em>이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-139">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="bd145-140">일부 주도자는 다른 사용자 보다 적극적으로 만들어지고 일부 Active Directory 개체는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-140">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd145-141"><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013의 tblPrincipalAffiliations</a></span><span class="sxs-lookup"><span data-stu-id="bd145-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-142">Active Directory 보안 그룹, Active Directory 컨테이너 등의 멤버 자격을 설명 하는 사용자의 소속을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-142">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd145-143"><a href="lync-server-2013-tblnode.md">Lync Server 2013의 tblNode</a></span><span class="sxs-lookup"><span data-stu-id="bd145-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-144">Lync Server 제어판에서 관리 되는 category 노드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-144">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd145-145"><a href="lync-server-2013-tblroletype.md">Lync Server 2013의 tblRoleType</a></span><span class="sxs-lookup"><span data-stu-id="bd145-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-146">역할 유형 및 연결 된 사용 권한 집합을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-146">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="bd145-147">이 조회 테이블은 정적입니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-147">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd145-148"><a href="lync-server-2013-tblscopeprincipal.md">Lync Server 2013의 tblScopePrincipal</a></span><span class="sxs-lookup"><span data-stu-id="bd145-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-149">노드에 할당 된 범위를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-149">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd145-150"><a href="lync-server-2013-tblprincipalrole.md">Lync Server 2013의 tblPrincipalRole</a></span><span class="sxs-lookup"><span data-stu-id="bd145-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-151">노드에 할당 된 역할을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-151">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd145-152"><a href="lync-server-2013-tblsiopwhitelist.md">Lync Server 2013의 tblSiopWhiteList</a></span><span class="sxs-lookup"><span data-stu-id="bd145-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-153">노드와 연결할 수 있는 등록 된 추가 기능을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-153">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd145-154"><a href="lync-server-2013-tblenumattribute.md">Lync Server 2013의 tblEnumAttribute</a></span><span class="sxs-lookup"><span data-stu-id="bd145-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-155">TblNode 테이블에 &quot;사용&quot; 되 &quot;는&quot; 하드 코드 된 Visibility 및 Behavior 특성만 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-155">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd145-156"><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013의 tblEnumValue</a></span><span class="sxs-lookup"><span data-stu-id="bd145-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-157">TblNode 테이블에 사용 되 &quot;는 하드 코드 된 Visibility&quot; "및" Behavior 특성의 값이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-157">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="bd145-158">초대, 채팅 및 기타 클라이언트 지원</span><span class="sxs-lookup"><span data-stu-id="bd145-158">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd145-159">테이블로</span><span class="sxs-lookup"><span data-stu-id="bd145-159">Table</span></span></th>
<th><span data-ttu-id="bd145-160">설명</span><span class="sxs-lookup"><span data-stu-id="bd145-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd145-161"><a href="lync-server-2013-tblprincipalinvites.md">Lync Server 2013의 tblPrincipalInvites</a></span><span class="sxs-lookup"><span data-stu-id="bd145-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-162">자동 초대를 사용 하는 모든 노드에 대해 시스템에서 프로 비전 된 모든 사용자에 대 한 초대를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-162">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd145-163"><a href="lync-server-2013-tblchat.md">Lync Server 2013의 tblChat</a></span><span class="sxs-lookup"><span data-stu-id="bd145-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-164">모든 채팅 메시지를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-164">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd145-165"><a href="lync-server-2013-tbllastinviteid.md">Lync Server 2013의 tblLastInviteId</a></span><span class="sxs-lookup"><span data-stu-id="bd145-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-166">각 사용자에 대해 생성 된 마지막 초대 ID (및 tblPrincipalInvites 테이블에 사용 됨)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-166">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd145-167"><a href="lync-server-2013-tbllastchatid.md">Lync Server 2013의 tblLastChatId</a></span><span class="sxs-lookup"><span data-stu-id="bd145-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-168">각 사용자에 대해 생성 된 마지막 채팅 ID (and, tblChat 테이블에서 사용 됨)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-168">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd145-169"><a href="lync-server-2013-tblpreference.md">Lync Server 2013의 tblPreference</a></span><span class="sxs-lookup"><span data-stu-id="bd145-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-170">사용자 클라이언트 기본 설정이 포함 되어 있습니다 (레거시 클라이언트에만 사용 됨).</span><span class="sxs-lookup"><span data-stu-id="bd145-170">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd145-171"><a href="lync-server-2013-tblfiletoken.md">Lync Server 2013의 tblFileToken</a></span><span class="sxs-lookup"><span data-stu-id="bd145-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-172">파일 전송 목적에 대 한 임시 토큰이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-172">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="bd145-173">파일을 업로드 하거나 다운로드할 때마다 영구 채팅 서비스에서 클라이언트가 웹 서비스 파일 저장소에 액세스 하는 데 사용 하는 토큰을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-173">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="bd145-174">서버 지원</span><span class="sxs-lookup"><span data-stu-id="bd145-174">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd145-175">테이블로</span><span class="sxs-lookup"><span data-stu-id="bd145-175">Table</span></span></th>
<th><span data-ttu-id="bd145-176">설명</span><span class="sxs-lookup"><span data-stu-id="bd145-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd145-177"><a href="lync-server-2013-tblserveridentity.md">Lync Server 2013의 tblServerIdentity</a></span><span class="sxs-lookup"><span data-stu-id="bd145-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-178">영구 채팅 서버 풀의 활성 서버를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-178">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd145-179"><a href="lync-server-2013-tbladminlock.md">Lync Server 2013의 tblAdminLock</a></span><span class="sxs-lookup"><span data-stu-id="bd145-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-180">일부 관리자 명령을 실행 하기 위한 관리자 잠금을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-180">Contains the administrator lock to run some administrator commands.</span></span> <span data-ttu-id="bd145-181">TblSystemRevision 테이블의 시스템 수정 항목이 잠금의 각 릴리스에 대해 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-181">The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd145-182"><a href="lync-server-2013-tblsystemrevision.md">Lync Server 2013의 tblSystemRevision</a></span><span class="sxs-lookup"><span data-stu-id="bd145-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-183">여러 서버에서 일관성을 유지 하기 위해 사용 되는 수정 번호 항목 (tblAdminLock 테이블과 함께)이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-183">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd145-184"><a href="lync-server-2013-tblactivepeers.md">Lync Server 2013의 tblActivePeers</a></span><span class="sxs-lookup"><span data-stu-id="bd145-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-185">영구 채팅 서비스 간의 현재 피어 투 피어 연결을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-185">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd145-186"><a href="lync-server-2013-tblconfig.md">Lync Server 2013의 tblConfig</a></span><span class="sxs-lookup"><span data-stu-id="bd145-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="bd145-187">영구 채팅 서버에서 지원 되지 않는 구성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd145-187">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

