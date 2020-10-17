---
title: 'Lync Server 2013: 영구 채팅 서버 테이블 목록'
description: 'Lync Server 2013: 영구 채팅 서버 테이블 목록'
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
ms.openlocfilehash: 838e6d8f83b137923075851b29df4c602a487391
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550054"
---
# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="df6a7-103">Lync Server 2013의 영구 채팅 서버 테이블 목록</span><span class="sxs-lookup"><span data-stu-id="df6a7-103">List of Persistent Chat Server tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df6a7-104">_**마지막으로 수정 된 항목:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="df6a7-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="df6a7-105">영구 채팅 데이터베이스 스키마는 다음 테이블로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-105">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="df6a7-106">Active Directory 동기화</span><span class="sxs-lookup"><span data-stu-id="df6a7-106">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df6a7-107">목차가</span><span class="sxs-lookup"><span data-stu-id="df6a7-107">Table</span></span></th>
<th><span data-ttu-id="df6a7-108">설명</span><span class="sxs-lookup"><span data-stu-id="df6a7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df6a7-109"><a href="lync-server-2013-tbladcookie.md">Lync Server 2013의 tblADCookie</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-109"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-110">현재 LDAP (Lightweight Directory Access Protocol) 동기화 쿠키가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-110">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="df6a7-111">각 행은 영구 채팅 서버가 적극적으로 변경 내용을 모니터링 하는 Active Directory 도메인 서비스 도메인에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-111">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="df6a7-112">(이 표에는 영구 채팅 서버와 관련 된 Active Directory 도메인만 표시 됩니다.)</span><span class="sxs-lookup"><span data-stu-id="df6a7-112">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df6a7-113"><a href="lync-server-2013-tblprincipalmemberdifference.md">Lync Server 2013의 tblPrincipalMemberDifference</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-113"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-114">나중에 Active Directory 동기화 단계에서 아직 처리 되지 않은 그룹 구성원 자격 변경 내용 (추가 및 제거 된 구성원)을 포함 하며, Active Directory 동기화의 첫 단계에서 사용 되는 임시 테이블 (tblADUpdates 테이블 포함) 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-114">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="df6a7-115">멤버 자격 변경 내용은 tblPrincipal 테이블에 나열 된 그룹에 대해서만 저장 또는 처리 되거나 둘 다에 있거나 이미 나열 된 멤버를 포함 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-115">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df6a7-116"><a href="lync-server-2013-tbladupdates.md">Lync Server 2013의 tblADUpdates</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-116"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-117">후속 Active Directory 동기화 단계에서 아직 처리 되지 않은 Active Directory 도메인 서비스에 대 한 변경 내용을 포함 하 고, Active Directory 동기화의 첫 단계에서 사용 되는 임시 테이블 (tblPrincipalMemberDifference table과 함께) 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-117">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="df6a7-118">Active Directory에 대 한 변경 내용은 tblPrincipal 테이블에 이미 나열 된 보안 주체에 대해서만 저장 또는 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-118">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df6a7-119"><a href="lync-server-2013-tblprincipalmembers.md">Lync Server 2013의 tblPrincipalMembers</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-119"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-120">보안 주체 구성원을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-120">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df6a7-121"><a href="lync-server-2013-tblprincipalmeta.md">Lync Server 2013의 tblPrincipalMeta</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-121"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-122">Active Directory에서 새로 고쳐야 하는 보안 주체를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-122">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df6a7-123"><a href="lync-server-2013-tblskippedaffiliations.md">Lync Server 2013의 tblSkippedAffiliations</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-123"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-124">일반적으로 Active Directory 액세스 오류로 인해 새로 고칠 수 없는 이유를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-124">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="df6a7-125">이 테이블은 정보를 제공 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-125">This table is for informational purposes only.</span></span> <span data-ttu-id="df6a7-126">해당 콘텐츠는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-126">Its content is not used.</span></span></p>
<p><span data-ttu-id="df6a7-127">올바르게 새로 고칠 수 없는 인이 있는 주체는 tblPrincipalMeta 테이블에 보관 되며 또 다른 새로 고칠 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-127">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="df6a7-128">보안 주체, 소속, 노드, 범위 및 역할</span><span class="sxs-lookup"><span data-stu-id="df6a7-128">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df6a7-129">목차가</span><span class="sxs-lookup"><span data-stu-id="df6a7-129">Table</span></span></th>
<th><span data-ttu-id="df6a7-130">설명</span><span class="sxs-lookup"><span data-stu-id="df6a7-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df6a7-131"><a href="lync-server-2013-tblprincipaltype.md">Lync Server 2013의 tblPrincipalType</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-131"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-132">TblPrincipal 테이블에 있는 것을 분류 하기 위한 보안 주체 유형이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-132">Contains principal types to categorize what is in the tblPrincipal table.</span></span> <span data-ttu-id="df6a7-133">정적 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-133">This table is static.</span></span> <span data-ttu-id="df6a7-134">데이터베이스를 만드는 동안 설정 되며 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-134">It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df6a7-135"><a href="lync-server-2013-tblprincipal.md">Lync Server 2013의 tblPrincipal</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-135"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-136">모든 보안 주체 (사용자, 폴더, 그룹 등)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-136">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="df6a7-137">영구 채팅 서버는이를 단순 유형이 다른 목록으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-137">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="df6a7-138">각 보안 주체의 유형을 기반으로 하는 여러 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-138">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="df6a7-139">이러한 보안 주체 대부분은 Active Directory에 저장 된 개체의 캐시 된 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-139">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="df6a7-140">이러한 Active Directory 개체의 주 테이블에 캐시 된 복사본을 만드는 것을 <em>프로 비전</em>이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-140">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="df6a7-141">일부 보안 주체는 다른 사용자 보다 적극적으로 만들어지며 일부 Active Directory 개체는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-141">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df6a7-142"><a href="lync-server-2013-tblprincipalaffiliations.md">Lync Server 2013의 tblPrincipalAffiliations</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-142"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-143">Active Directory 보안 그룹, Active Directory 컨테이너 등에 있는 구성원을 설명 하는 보안 주체를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-143">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df6a7-144"><a href="lync-server-2013-tblnode.md">Lync Server 2013의 tblNode</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-144"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-145">Lync Server 제어판의 관리 되는 범주 노드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-145">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df6a7-146"><a href="lync-server-2013-tblroletype.md">Lync Server 2013의 tblRoleType</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-146"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-147">역할 유형 및 연결 된 권한 집합을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-147">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="df6a7-148">이 코드 체계표가 static입니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-148">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df6a7-149"><a href="lync-server-2013-tblscopeprincipal.md">Lync Server 2013의 tblScopePrincipal</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-149"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-150">노드에 할당 된 범위를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-150">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df6a7-151"><a href="lync-server-2013-tblprincipalrole.md">Lync Server 2013의 tblPrincipalRole</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-151"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-152">노드에 할당 된 역할을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-152">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df6a7-153"><a href="lync-server-2013-tblsiopwhitelist.md">Lync Server 2013의 tblSiopWhiteList</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-153"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-154">노드와 연결할 수 있는 등록 된 추가 기능을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-154">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df6a7-155"><a href="lync-server-2013-tblenumattribute.md">Lync Server 2013의 tblEnumAttribute</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-155"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-156">&quot; &quot; &quot; &quot; Tblnode 테이블에서 사용 되는 하드 코드 된 Visibility 및 Behavior 특성만 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-156">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df6a7-157"><a href="lync-server-2013-tblenumvalue.md">Lync Server 2013의 tblEnumValue</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-157"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-158">&quot;TblNode 테이블에서 사용 되는 하드 코드 된 Visibility "및" Behavior 특성의 값을 포함 합니다 &quot; .</span><span class="sxs-lookup"><span data-stu-id="df6a7-158">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="df6a7-159">초대, 채팅 및 기타 클라이언트 지원</span><span class="sxs-lookup"><span data-stu-id="df6a7-159">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df6a7-160">목차가</span><span class="sxs-lookup"><span data-stu-id="df6a7-160">Table</span></span></th>
<th><span data-ttu-id="df6a7-161">설명</span><span class="sxs-lookup"><span data-stu-id="df6a7-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df6a7-162"><a href="lync-server-2013-tblprincipalinvites.md">Lync Server 2013의 tblPrincipalInvites</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-162"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-163">자동 초대가 설정 된 모든 노드에 대해 시스템에서 프로 비전 된 모든 사용자에 대 한 초대를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-163">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df6a7-164"><a href="lync-server-2013-tblchat.md">Lync Server 2013의 tblChat</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-164"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-165">모든 채팅 메시지를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-165">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df6a7-166"><a href="lync-server-2013-tbllastinviteid.md">Lync Server 2013의 tblLastInviteId</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-166"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-167">각 사용자에 대해 생성 (및 tblPrincipalInvites 테이블에서 사용) 된 마지막 초대 ID를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-167">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df6a7-168"><a href="lync-server-2013-tbllastchatid.md">Lync Server 2013의 tblLastChatId</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-168"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-169">각 사용자에 대해 생성 (및 tblChat 테이블에서 사용) 된 마지막 채팅 ID를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-169">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df6a7-170"><a href="lync-server-2013-tblpreference.md">Lync Server 2013의 tblPreference 설정</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-170"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-171">사용자 클라이언트 기본 설정을 포함 합니다 (레거시 클라이언트만 사용 됨).</span><span class="sxs-lookup"><span data-stu-id="df6a7-171">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df6a7-172"><a href="lync-server-2013-tblfiletoken.md">Lync Server 2013의 tblFileToken</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-172"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-173">파일 전송 용도로 사용 되는 임시 토큰이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-173">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="df6a7-174">파일이 업로드 되거나 다운로드 될 때마다 영구 채팅 서비스가 클라이언트에서 웹 서비스 파일 저장소에 액세스 하는 데 사용 하는 토큰을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-174">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="df6a7-175">서버 지원</span><span class="sxs-lookup"><span data-stu-id="df6a7-175">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df6a7-176">목차가</span><span class="sxs-lookup"><span data-stu-id="df6a7-176">Table</span></span></th>
<th><span data-ttu-id="df6a7-177">설명</span><span class="sxs-lookup"><span data-stu-id="df6a7-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df6a7-178"><a href="lync-server-2013-tblserveridentity.md">Lync Server 2013의 tblServerIdentity</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-178"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-179">영구 채팅 서버 풀의 활성 서버를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-179">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df6a7-180"><a href="lync-server-2013-tbladminlock.md">Lync Server 2013의 tblAdminLock</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-180"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-181">일부 관리자 명령을 실행 하는 관리자 잠금을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-181">Contains the administrator lock to run some administrator commands.</span></span> <span data-ttu-id="df6a7-182">각 잠금 릴리스 후에는 tblSystemRevision 테이블의 시스템 수정 항목이 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-182">The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df6a7-183"><a href="lync-server-2013-tblsystemrevision.md">Lync Server 2013의 tblSystemRevision</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-183"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-184">TblAdminLock 테이블과 함께 여러 서버 간에 일관성을 유지 하는 데 사용 되는 수정 번호 항목을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-184">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df6a7-185"><a href="lync-server-2013-tblactivepeers.md">Lync Server 2013의 tblActivePeers</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-185"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-186">영구 채팅 서비스 간의 현재 피어-투-피어 연결을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-186">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df6a7-187"><a href="lync-server-2013-tblconfig.md">Lync Server 2013의 tblConfig</a></span><span class="sxs-lookup"><span data-stu-id="df6a7-187"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="df6a7-188">영구 채팅 서버에서 지원 되지 않는 구성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="df6a7-188">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

