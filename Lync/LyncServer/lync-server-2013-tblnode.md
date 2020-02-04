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
ms.openlocfilehash: 24ba45d9ba650a9de4359d64e3281fb488b6a279
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblnode-in-lync-server-2013"></a><span data-ttu-id="32225-102">Lync Server 2013의 tblNode</span><span class="sxs-lookup"><span data-stu-id="32225-102">tblNode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32225-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="32225-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="32225-104">tblNode에는 Lync Server 2013 제어판 및 관리 cmdlet에서 관리 되는 개체 트리 (범주 또는 채팅방 노드가 있음)가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32225-104">tblNode contains the object tree (with category or chat room nodes) as managed in the Lync Server 2013 Control Panel and administrative cmdlets.</span></span>

### <a name="columns"></a><span data-ttu-id="32225-105">열</span><span class="sxs-lookup"><span data-stu-id="32225-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32225-106">열</span><span class="sxs-lookup"><span data-stu-id="32225-106">Column</span></span></th>
<th><span data-ttu-id="32225-107">유형</span><span class="sxs-lookup"><span data-stu-id="32225-107">Type</span></span></th>
<th><span data-ttu-id="32225-108">설명</span><span class="sxs-lookup"><span data-stu-id="32225-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32225-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="32225-109">nodeID</span></span></p></td>
<td><p><span data-ttu-id="32225-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="32225-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="32225-111">노드 ID (고유 번호).</span><span class="sxs-lookup"><span data-stu-id="32225-111">Node ID (unique number).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32225-112">nodeGuid</span><span class="sxs-lookup"><span data-stu-id="32225-112">nodeGuid</span></span></p></td>
<td><p><span data-ttu-id="32225-113">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="32225-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="32225-114">노드 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-114">Node GUID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32225-115">parentID</span><span class="sxs-lookup"><span data-stu-id="32225-115">parentID</span></span></p></td>
<td><p><span data-ttu-id="32225-116">int</span><span class="sxs-lookup"><span data-stu-id="32225-116">int</span></span></p></td>
<td><p><span data-ttu-id="32225-117">부모의 노드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-117">Node ID of parent.</span></span> <span data-ttu-id="32225-118">루트 노드 (ID 1)는 자신을 부모로도 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="32225-118">The root node (with ID 1) includes itself as parent as well.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32225-119">종류</span><span class="sxs-lookup"><span data-stu-id="32225-119">nodeType</span></span></p></td>
<td><p><span data-ttu-id="32225-120">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="32225-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="32225-121">노드가 범주 이면 True입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-121">True if the node is a category.</span></span></p>
<p><span data-ttu-id="32225-122">노드가 채팅방 이면 False입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-122">False if the node is a chat room.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32225-123">nodeName</span><span class="sxs-lookup"><span data-stu-id="32225-123">nodeName</span></span></p></td>
<td><p><span data-ttu-id="32225-124">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="32225-124">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="32225-125">노드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-125">Node name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32225-126">nodeDesc</span><span class="sxs-lookup"><span data-stu-id="32225-126">nodeDesc</span></span></p></td>
<td><p><span data-ttu-id="32225-127">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="32225-127">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="32225-128">노드 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-128">Node description.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32225-129">있도록</span><span class="sxs-lookup"><span data-stu-id="32225-129">invite</span></span></p></td>
<td><p><span data-ttu-id="32225-130">다소</span><span class="sxs-lookup"><span data-stu-id="32225-130">bit</span></span></p></td>
<td><p><span data-ttu-id="32225-131">범주:</span><span class="sxs-lookup"><span data-stu-id="32225-131">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="32225-132">초대가 설정 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-132">True if invites are on.</span></span></p></li>
<li><p><span data-ttu-id="32225-133">초대가 해제 된 경우 False입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-133">False if invites are off.</span></span></p></li>
</ul>
<p><span data-ttu-id="32225-134">회의실:</span><span class="sxs-lookup"><span data-stu-id="32225-134">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="32225-135">초대가 해제 된 경우 False (상위 범주 무시)</span><span class="sxs-lookup"><span data-stu-id="32225-135">False if invites are off (overrides the parent category).</span></span></p></li>
<li><p><span data-ttu-id="32225-136">초대 설정이 상위 범주에서 상속 되는 경우 Null입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-136">Null if the invites setting is inherited from the parent category.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32225-137">사람이</span><span class="sxs-lookup"><span data-stu-id="32225-137">logged</span></span></p></td>
<td><p><span data-ttu-id="32225-138">다소</span><span class="sxs-lookup"><span data-stu-id="32225-138">bit</span></span></p></td>
<td><p><span data-ttu-id="32225-139">범주:</span><span class="sxs-lookup"><span data-stu-id="32225-139">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="32225-140">채팅 내역이 켜져 있는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-140">True if chat history is on.</span></span></p></li>
<li><p><span data-ttu-id="32225-141">대화 내용이 설정 되어 있지 않으면 False입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-141">False if chat history is off.</span></span></p></li>
</ul>
<p><span data-ttu-id="32225-142">회의실:</span><span class="sxs-lookup"><span data-stu-id="32225-142">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="32225-143">L.</span><span class="sxs-lookup"><span data-stu-id="32225-143">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32225-144">filePost</span><span class="sxs-lookup"><span data-stu-id="32225-144">filePost</span></span></p></td>
<td><p><span data-ttu-id="32225-145">다소</span><span class="sxs-lookup"><span data-stu-id="32225-145">bit</span></span></p></td>
<td><p><span data-ttu-id="32225-146">범주:</span><span class="sxs-lookup"><span data-stu-id="32225-146">For categories:</span></span></p>
<ul>
<li><p><span data-ttu-id="32225-147">파일 업로드가 허용 되는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-147">True if file uploads are allowed.</span></span></p></li>
<li><p><span data-ttu-id="32225-148">False 이면 파일 업로드를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32225-148">False if file uploads are disallowed.</span></span></p></li>
</ul>
<p><span data-ttu-id="32225-149">회의실:</span><span class="sxs-lookup"><span data-stu-id="32225-149">For rooms:</span></span></p>
<ul>
<li><p><span data-ttu-id="32225-150">L.</span><span class="sxs-lookup"><span data-stu-id="32225-150">Null.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32225-151">비활성화</span><span class="sxs-lookup"><span data-stu-id="32225-151">disabled</span></span></p></td>
<td><p><span data-ttu-id="32225-152">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="32225-152">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="32225-153">채팅방을 사용할 수 없는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-153">True if the chat room is disabled.</span></span> <span data-ttu-id="32225-154">채팅방에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32225-154">Applies only to chat rooms.</span></span> <span data-ttu-id="32225-155">(범주에 대 한 False)</span><span class="sxs-lookup"><span data-stu-id="32225-155">(False for categories.)</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32225-156">결과가</span><span class="sxs-lookup"><span data-stu-id="32225-156">behavior</span></span></p></td>
<td><p><span data-ttu-id="32225-157">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="32225-157">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="32225-158">동작 (EnumValue 테이블에서 조회):</span><span class="sxs-lookup"><span data-stu-id="32225-158">Behavior (looked up in EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="32225-159">4: 보통 (일반 채팅방).</span><span class="sxs-lookup"><span data-stu-id="32225-159">4: Normal (normal chat rooms).</span></span></p></li>
<li><p><span data-ttu-id="32225-160">5: Auditorium (Auditorium 채팅방은 발표자만 참가할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="32225-160">5: Auditorium (auditorium chat rooms, only presenters can contribute).</span></span></p></li>
</ul>
<p><span data-ttu-id="32225-161">채팅방에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32225-161">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32225-162">시도가</span><span class="sxs-lookup"><span data-stu-id="32225-162">visibility</span></span></p></td>
<td><p><span data-ttu-id="32225-163">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="32225-163">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="32225-164">가시성 (EnumValue 표를 통해 조회):</span><span class="sxs-lookup"><span data-stu-id="32225-164">Visibility (looked up on EnumValue table):</span></span></p>
<ul>
<li><p><span data-ttu-id="32225-165">2: 비공개</span><span class="sxs-lookup"><span data-stu-id="32225-165">2: Private</span></span></p></li>
<li><p><span data-ttu-id="32225-166">3: 범위 지정</span><span class="sxs-lookup"><span data-stu-id="32225-166">3: Scoped</span></span></p></li>
<li><p><span data-ttu-id="32225-167">6: 열림</span><span class="sxs-lookup"><span data-stu-id="32225-167">6: Open</span></span></p></li>
</ul>
<p><span data-ttu-id="32225-168">채팅방에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32225-168">Applies only to chat rooms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32225-169">siopID</span><span class="sxs-lookup"><span data-stu-id="32225-169">siopID</span></span></p></td>
<td><p><span data-ttu-id="32225-170">SHAP</span><span class="sxs-lookup"><span data-stu-id="32225-170">GUID</span></span></p></td>
<td><p><span data-ttu-id="32225-171">추가 기능 GUID가이 채팅방과 연결 되어 있는 경우이를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="32225-171">Add-In GUID if an add-in is associated with this chat room.</span></span> <span data-ttu-id="32225-172">(범주에는 추가 기능이 없습니다.)</span><span class="sxs-lookup"><span data-stu-id="32225-172">(Categories do not have add-ins.)</span></span></p>
<p><span data-ttu-id="32225-173">추가 기능 정보는 SiopWhiteList 테이블에서 조회 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32225-173">The add-in information is looked up in SiopWhiteList table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32225-174">nodeAddedBy</span><span class="sxs-lookup"><span data-stu-id="32225-174">nodeAddedBy</span></span></p></td>
<td><p><span data-ttu-id="32225-175">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="32225-175">int, not null</span></span></p></td>
<td><p><span data-ttu-id="32225-176">이 노드를 만든 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-176">ID of the principal that created this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32225-177">nodeAddedOn</span><span class="sxs-lookup"><span data-stu-id="32225-177">nodeAddedOn</span></span></p></td>
<td><p><span data-ttu-id="32225-178">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="32225-178">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="32225-179">노드 생성에 대 한 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-179">Time stamp of the node creation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32225-180">nodeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="32225-180">nodeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="32225-181">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="32225-181">int, not null</span></span></p></td>
<td><p><span data-ttu-id="32225-182">이 노드의 최신 업데이트를 수행한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-182">ID of the principal that did the latest update of this node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32225-183">nodeUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="32225-183">nodeUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="32225-184">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="32225-184">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="32225-185">이 노드의 최신 업데이트에 대 한 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-185">Time stamp of the latest update of this node.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32225-186">purgedOn</span><span class="sxs-lookup"><span data-stu-id="32225-186">purgedOn</span></span></p></td>
<td><p><span data-ttu-id="32225-187">dmtf</span><span class="sxs-lookup"><span data-stu-id="32225-187">datetime</span></span></p></td>
<td><p><span data-ttu-id="32225-188">이 노드에 영향을 주는 최신 지우기 작업의 시간 (tblScopedPrincipal table의 범위 제거 및 tblPrincipalRole 테이블에서 가져온 역할)</span><span class="sxs-lookup"><span data-stu-id="32225-188">Time of the latest purge operation (removal of scopes from tblScopedPrincipal table and roles from tblPrincipalRole table) that affected this node.</span></span> <span data-ttu-id="32225-189">이는 채팅 서비스의 내부 캐시 업데이트 메커니즘에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32225-189">This is used by the Chat service’s internal cache update mechanism.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="32225-190">핵심</span><span class="sxs-lookup"><span data-stu-id="32225-190">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32225-191">열</span><span class="sxs-lookup"><span data-stu-id="32225-191">Column</span></span></th>
<th><span data-ttu-id="32225-192">설명</span><span class="sxs-lookup"><span data-stu-id="32225-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32225-193">nodeID</span><span class="sxs-lookup"><span data-stu-id="32225-193">nodeID</span></span></p></td>
<td><p><span data-ttu-id="32225-194">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-194">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32225-195">결과가</span><span class="sxs-lookup"><span data-stu-id="32225-195">behavior</span></span></p></td>
<td><p><span data-ttu-id="32225-196">TblEnumValue Eid 테이블의 조회가 포함 되어 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-196">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32225-197">시도가</span><span class="sxs-lookup"><span data-stu-id="32225-197">visibility</span></span></p></td>
<td><p><span data-ttu-id="32225-198">TblEnumValue Eid 테이블의 조회가 포함 되어 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-198">Foreign key with lookup in tblEnumValue.valueID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32225-199">parentID</span><span class="sxs-lookup"><span data-stu-id="32225-199">parentID</span></span></p></td>
<td><p><span data-ttu-id="32225-200">NodeID 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-200">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32225-201">siopID</span><span class="sxs-lookup"><span data-stu-id="32225-201">siopID</span></span></p></td>
<td><p><span data-ttu-id="32225-202">TblSiopWhiteList의 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="32225-202">Foreign key with lookup in tblSiopWhiteList.siopId table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

