---
title: 'Lync Server 2013: tblNode'
description: 'Lync Server 2013: tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a5d630621c32cbc54501249c7a679bf4023c60
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547554"
---
# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="5b3f6-103">Lync Server 2013의 tblNode</span><span class="sxs-lookup"><span data-stu-id="5b3f6-103">tblNode in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b3f6-104">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="5b3f6-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="5b3f6-105">tblNode에는 Lync Server 2013 제어판 및 관리 cmdlet에서 관리 되는 개체 트리 (범주 또는 대화방 노드 포함)가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-105">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="5b3f6-106">단</span><span class="sxs-lookup"><span data-stu-id="5b3f6-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b3f6-107">열</span><span class="sxs-lookup"><span data-stu-id="5b3f6-107">Column</span></span></th>
<th><span data-ttu-id="5b3f6-108">유형</span><span class="sxs-lookup"><span data-stu-id="5b3f6-108">Type</span></span></th>
<th><span data-ttu-id="5b3f6-109">설명</span><span class="sxs-lookup"><span data-stu-id="5b3f6-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b3f6-110">입니다</span><span class="sxs-lookup"><span data-stu-id="5b3f6-110">nodeID</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-111">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5b3f6-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-112">노드 ID(고유 번호)입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-112">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b3f6-113">Tblnode.nodeguid</span><span class="sxs-lookup"><span data-stu-id="5b3f6-113">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-114">GUID, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5b3f6-114">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-115">노드 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-115">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b3f6-116">아닌 parentid</span><span class="sxs-lookup"><span data-stu-id="5b3f6-116">parentID</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-117">int</span><span class="sxs-lookup"><span data-stu-id="5b3f6-117">int</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-p101">부모의 노드 ID입니다. 루트 노드(ID 1)는 그 자신을 부모로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-p101">Node ID of parent. The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b3f6-120">nodeType</span><span class="sxs-lookup"><span data-stu-id="5b3f6-120">nodeType</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-121">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5b3f6-121">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-122">노드가 범주인 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-122">True if the node is a category.</span></span></p>
<p><span data-ttu-id="5b3f6-123">노드가 대화방인 경우 False입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-123">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b3f6-124">nodeName</span><span class="sxs-lookup"><span data-stu-id="5b3f6-124">nodeName</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-125">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="5b3f6-125">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-126">노드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-126">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b3f6-127">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="5b3f6-127">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-128">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="5b3f6-128">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-129">노드 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-129">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b3f6-130">invite</span><span class="sxs-lookup"><span data-stu-id="5b3f6-130">invite</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-131">비트만</span><span class="sxs-lookup"><span data-stu-id="5b3f6-131">bit</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-132">범주인 경우:</span><span class="sxs-lookup"><span data-stu-id="5b3f6-132">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b3f6-133">초대가 설정된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-133">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="5b3f6-134">초대가 해제된 경우 False입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-134">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="5b3f6-135">대화방인 경우:</span><span class="sxs-lookup"><span data-stu-id="5b3f6-135">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b3f6-136">초대가 해제된 경우 False입니다(부모 범주 재정의).</span><span class="sxs-lookup"><span data-stu-id="5b3f6-136">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="5b3f6-137">부모 범주에서 초대 설정이 상속된 경우 Null입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-137">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b3f6-138">된다</span><span class="sxs-lookup"><span data-stu-id="5b3f6-138">logged</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-139">비트만</span><span class="sxs-lookup"><span data-stu-id="5b3f6-139">bit</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-140">범주인 경우:</span><span class="sxs-lookup"><span data-stu-id="5b3f6-140">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b3f6-141">대화 기록이 설정된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-141">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="5b3f6-142">대화 기록이 해제된 경우 Fasle입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-142">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="5b3f6-143">대화방인 경우:</span><span class="sxs-lookup"><span data-stu-id="5b3f6-143">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b3f6-144">아니어야.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-144">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b3f6-145">filePost</span><span class="sxs-lookup"><span data-stu-id="5b3f6-145">filePost</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-146">비트만</span><span class="sxs-lookup"><span data-stu-id="5b3f6-146">bit</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-147">범주인 경우:</span><span class="sxs-lookup"><span data-stu-id="5b3f6-147">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b3f6-148">파일 업로드가 허용된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-148">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="5b3f6-149">파일 업로드가 허용되지 않은 경우 False입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-149">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="5b3f6-150">대화방인 경우:</span><span class="sxs-lookup"><span data-stu-id="5b3f6-150">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="5b3f6-151">아니어야.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-151">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b3f6-152">비활성화됨</span><span class="sxs-lookup"><span data-stu-id="5b3f6-152">disabled</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-153">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5b3f6-153">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-p102">대화방이 비활성화된 경우 True입니다. 대화방에만 적용됩니다. 범주의 경우 False입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-p102">True if the chat room is disabled. Applies only to chat rooms. (False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b3f6-157">동작과</span><span class="sxs-lookup"><span data-stu-id="5b3f6-157">behavior</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-158">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5b3f6-158">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-159">동작(EnumValue 테이블에서 조회됨):</span><span class="sxs-lookup"><span data-stu-id="5b3f6-159">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="5b3f6-160">4: 일반(일반 대화방)</span><span class="sxs-lookup"><span data-stu-id="5b3f6-160">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="5b3f6-161">5: 강당(강당 대화방, 발표자만 기여할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="5b3f6-161">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="5b3f6-162">대화방에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-162">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b3f6-163">잘</span><span class="sxs-lookup"><span data-stu-id="5b3f6-163">visibility</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-164">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5b3f6-164">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-165">표시 유형(EnumValue 테이블에서 조회됨):</span><span class="sxs-lookup"><span data-stu-id="5b3f6-165">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="5b3f6-166">2: 개인</span><span class="sxs-lookup"><span data-stu-id="5b3f6-166">2: Private</span></span></p></li>
<li><p><span data-ttu-id="5b3f6-167">3: 범위 지정</span><span class="sxs-lookup"><span data-stu-id="5b3f6-167">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="5b3f6-168">6: 열려 있음</span><span class="sxs-lookup"><span data-stu-id="5b3f6-168">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="5b3f6-169">대화방에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-169">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b3f6-170">Tblsiopwhitelist.siopid</span><span class="sxs-lookup"><span data-stu-id="5b3f6-170">siopID</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-171">GUID</span><span class="sxs-lookup"><span data-stu-id="5b3f6-171">GUID</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-p103">추가 기능이 이 대화방과 연결된 경우 추가 기능 GUID입니다. (범주에는 추가 기능이 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="5b3f6-p103">Add-In GUID if an add-in is associated with this chat room. (Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="5b3f6-174">추가 기능 정보는 SiopWhiteList 테이블에서 조회됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-174">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b3f6-175">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="5b3f6-175">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-176">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5b3f6-176">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-177">이 노드를 만든 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-177">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b3f6-178">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="5b3f6-178">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-179">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5b3f6-179">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-180">노드 작성의 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-180">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b3f6-181">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="5b3f6-181">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-182">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5b3f6-182">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-183">이 노드를 마지막으로 업데이트한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-183">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b3f6-184">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="5b3f6-184">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-185">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="5b3f6-185">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-186">이 노드를 마지막으로 업데이트한 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-186">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b3f6-187">purgedOn</span><span class="sxs-lookup"><span data-stu-id="5b3f6-187">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-188">datetime</span><span class="sxs-lookup"><span data-stu-id="5b3f6-188">datetime</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-p104">이 노드에 영향을 준 최근의 삭제 작업(ScopedPrincipal 테이블에서 범위 및 PrincipalRole 테이블에서 역할 제거)의 시간입니다. 채팅 서비스의 내부 캐시 업데이트 메커니즘에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-p104">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node. This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="5b3f6-191">키</span><span class="sxs-lookup"><span data-stu-id="5b3f6-191">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b3f6-192">열</span><span class="sxs-lookup"><span data-stu-id="5b3f6-192">Column</span></span></th>
<th><span data-ttu-id="5b3f6-193">설명</span><span class="sxs-lookup"><span data-stu-id="5b3f6-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b3f6-194">입니다</span><span class="sxs-lookup"><span data-stu-id="5b3f6-194">nodeID</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-195">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-195">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b3f6-196">동작과</span><span class="sxs-lookup"><span data-stu-id="5b3f6-196">behavior</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-197">tblEnumValue.valueID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-197">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b3f6-198">잘</span><span class="sxs-lookup"><span data-stu-id="5b3f6-198">visibility</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-199">tblEnumValue.valueID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-199">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b3f6-200">아닌 parentid</span><span class="sxs-lookup"><span data-stu-id="5b3f6-200">parentID</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-201">tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-201">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b3f6-202">Tblsiopwhitelist.siopid</span><span class="sxs-lookup"><span data-stu-id="5b3f6-202">siopID</span></span></p></td>
<td><p><span data-ttu-id="5b3f6-203">tblSiopWhiteList.siopId 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="5b3f6-203">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

