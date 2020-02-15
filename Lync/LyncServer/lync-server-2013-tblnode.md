---
title: 'Lync Server 2013: tblNode'
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
ms.openlocfilehash: 81a57d54663b1adf837a4ca38896dd7da3eff883
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="163dd-102">Lync Server 2013의 tblNode</span><span class="sxs-lookup"><span data-stu-id="163dd-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="163dd-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="163dd-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="163dd-104">tblNode에는 Lync Server 2013 제어판 및 관리 cmdlet에서 관리 되는 개체 트리 (범주 또는 대화방 노드 포함)가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="163dd-105">단</span><span class="sxs-lookup"><span data-stu-id="163dd-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="163dd-106">열</span><span class="sxs-lookup"><span data-stu-id="163dd-106">Column</span></span></th>
<th><span data-ttu-id="163dd-107">형식</span><span class="sxs-lookup"><span data-stu-id="163dd-107">Type</span></span></th>
<th><span data-ttu-id="163dd-108">설명</span><span class="sxs-lookup"><span data-stu-id="163dd-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="163dd-109">입니다</span><span class="sxs-lookup"><span data-stu-id="163dd-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="163dd-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="163dd-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="163dd-111">노드 ID(고유 번호)입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163dd-112">Tblnode.nodeguid</span><span class="sxs-lookup"><span data-stu-id="163dd-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="163dd-113">GUID, null이 아님</span><span class="sxs-lookup"><span data-stu-id="163dd-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="163dd-114">노드 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="163dd-115">아닌 parentid</span><span class="sxs-lookup"><span data-stu-id="163dd-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="163dd-116">int</span><span class="sxs-lookup"><span data-stu-id="163dd-116">int</span></span></p></td>
<td><p><span data-ttu-id="163dd-p101">부모의 노드 ID입니다. 루트 노드(ID 1)는 그 자신을 부모로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-p101">Node ID of parent. The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163dd-119">nodeType</span><span class="sxs-lookup"><span data-stu-id="163dd-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="163dd-120">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="163dd-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="163dd-121">노드가 범주인 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="163dd-122">노드가 대화방인 경우 False입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="163dd-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="163dd-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="163dd-124">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="163dd-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="163dd-125">노드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163dd-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="163dd-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="163dd-127">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="163dd-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="163dd-128">노드 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="163dd-129">invite</span><span class="sxs-lookup"><span data-stu-id="163dd-129">invite</span></span></p></td>
<td><p><span data-ttu-id="163dd-130">비트만</span><span class="sxs-lookup"><span data-stu-id="163dd-130">bit</span></span></p></td>
<td><p><span data-ttu-id="163dd-131">범주인 경우:</span><span class="sxs-lookup"><span data-stu-id="163dd-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="163dd-132">초대가 설정된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="163dd-133">초대가 해제된 경우 False입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="163dd-134">대화방인 경우:</span><span class="sxs-lookup"><span data-stu-id="163dd-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="163dd-135">초대가 해제된 경우 False입니다(부모 범주 재정의).</span><span class="sxs-lookup"><span data-stu-id="163dd-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="163dd-136">부모 범주에서 초대 설정이 상속된 경우 Null입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163dd-137">된다</span><span class="sxs-lookup"><span data-stu-id="163dd-137">logged</span></span></p></td>
<td><p><span data-ttu-id="163dd-138">비트만</span><span class="sxs-lookup"><span data-stu-id="163dd-138">bit</span></span></p></td>
<td><p><span data-ttu-id="163dd-139">범주인 경우:</span><span class="sxs-lookup"><span data-stu-id="163dd-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="163dd-140">대화 기록이 설정된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="163dd-141">대화 기록이 해제된 경우 Fasle입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="163dd-142">대화방인 경우:</span><span class="sxs-lookup"><span data-stu-id="163dd-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="163dd-143">아니어야.</span><span class="sxs-lookup"><span data-stu-id="163dd-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="163dd-144">filePost</span><span class="sxs-lookup"><span data-stu-id="163dd-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="163dd-145">비트만</span><span class="sxs-lookup"><span data-stu-id="163dd-145">bit</span></span></p></td>
<td><p><span data-ttu-id="163dd-146">범주인 경우:</span><span class="sxs-lookup"><span data-stu-id="163dd-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="163dd-147">파일 업로드가 허용된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="163dd-148">파일 업로드가 허용되지 않은 경우 False입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="163dd-149">대화방인 경우:</span><span class="sxs-lookup"><span data-stu-id="163dd-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="163dd-150">아니어야.</span><span class="sxs-lookup"><span data-stu-id="163dd-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163dd-151">있지</span><span class="sxs-lookup"><span data-stu-id="163dd-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="163dd-152">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="163dd-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="163dd-p102">대화방이 비활성화된 경우 True입니다. 대화방에만 적용됩니다. 범주의 경우 False입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-p102">True if the chat room is disabled. Applies only to chat rooms. (False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163dd-156">동작과</span><span class="sxs-lookup"><span data-stu-id="163dd-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="163dd-157">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="163dd-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="163dd-158">동작(EnumValue 테이블에서 조회됨):</span><span class="sxs-lookup"><span data-stu-id="163dd-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="163dd-159">4: 일반(일반 대화방)</span><span class="sxs-lookup"><span data-stu-id="163dd-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="163dd-160">5: 강당(강당 대화방, 발표자만 기여할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="163dd-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="163dd-161">대화방에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="163dd-162">잘</span><span class="sxs-lookup"><span data-stu-id="163dd-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="163dd-163">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="163dd-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="163dd-164">표시 유형(EnumValue 테이블에서 조회됨):</span><span class="sxs-lookup"><span data-stu-id="163dd-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="163dd-165">2: 개인</span><span class="sxs-lookup"><span data-stu-id="163dd-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="163dd-166">3: 범위 지정</span><span class="sxs-lookup"><span data-stu-id="163dd-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="163dd-167">6: 열려 있음</span><span class="sxs-lookup"><span data-stu-id="163dd-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="163dd-168">대화방에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163dd-169">Tblsiopwhitelist.siopid</span><span class="sxs-lookup"><span data-stu-id="163dd-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="163dd-170">GUID</span><span class="sxs-lookup"><span data-stu-id="163dd-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="163dd-p103">추가 기능이 이 대화방과 연결된 경우 추가 기능 GUID입니다. (범주에는 추가 기능이 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="163dd-p103">Add-In GUID if an add-in is associated with this chat room. (Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="163dd-173">추가 기능 정보는 SiopWhiteList 테이블에서 조회됩니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="163dd-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="163dd-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="163dd-175">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="163dd-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="163dd-176">이 노드를 만든 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163dd-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="163dd-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="163dd-178">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="163dd-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="163dd-179">노드 작성의 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="163dd-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="163dd-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="163dd-181">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="163dd-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="163dd-182">이 노드를 마지막으로 업데이트한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163dd-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="163dd-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="163dd-184">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="163dd-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="163dd-185">이 노드를 마지막으로 업데이트한 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="163dd-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="163dd-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="163dd-187">datetime</span><span class="sxs-lookup"><span data-stu-id="163dd-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="163dd-p104">이 노드에 영향을 준 최근의 삭제 작업(ScopedPrincipal 테이블에서 범위 및 PrincipalRole 테이블에서 역할 제거)의 시간입니다. 채팅 서비스의 내부 캐시 업데이트 메커니즘에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-p104">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node. This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="163dd-190">키</span><span class="sxs-lookup"><span data-stu-id="163dd-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="163dd-191">열</span><span class="sxs-lookup"><span data-stu-id="163dd-191">Column</span></span></th>
<th><span data-ttu-id="163dd-192">설명</span><span class="sxs-lookup"><span data-stu-id="163dd-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="163dd-193">입니다</span><span class="sxs-lookup"><span data-stu-id="163dd-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="163dd-194">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163dd-195">동작과</span><span class="sxs-lookup"><span data-stu-id="163dd-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="163dd-196">tblEnumValue.valueID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="163dd-197">잘</span><span class="sxs-lookup"><span data-stu-id="163dd-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="163dd-198">tblEnumValue.valueID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="163dd-199">아닌 parentid</span><span class="sxs-lookup"><span data-stu-id="163dd-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="163dd-200">tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="163dd-201">Tblsiopwhitelist.siopid</span><span class="sxs-lookup"><span data-stu-id="163dd-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="163dd-202">tblSiopWhiteList.siopId 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="163dd-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

