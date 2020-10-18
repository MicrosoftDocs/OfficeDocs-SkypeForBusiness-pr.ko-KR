---
title: 'Lync Server 2013: tblPrincipalRole'
description: 'Lync Server 2013: tblPrincipalRole'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58ffda3136c254ee77f14d33dcb42af5d172c4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573634"
---
# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="fcb14-103">Lync Server 2013의 tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="fcb14-103">tblPrincipalRole in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcb14-104">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="fcb14-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="fcb14-105">tblPrincipalRole 테이블에는 노드에 할당된 명시적 역할이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcb14-105">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="fcb14-106">단</span><span class="sxs-lookup"><span data-stu-id="fcb14-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcb14-107">열</span><span class="sxs-lookup"><span data-stu-id="fcb14-107">Column</span></span></th>
<th><span data-ttu-id="fcb14-108">유형</span><span class="sxs-lookup"><span data-stu-id="fcb14-108">Type</span></span></th>
<th><span data-ttu-id="fcb14-109">설명</span><span class="sxs-lookup"><span data-stu-id="fcb14-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcb14-110">Principalrole.prinrolenodeid</span><span class="sxs-lookup"><span data-stu-id="fcb14-110">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="fcb14-111">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="fcb14-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fcb14-112">해당 역할이 적용되는 노드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcb14-112">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb14-113">Principalrole.prinroleprinid</span><span class="sxs-lookup"><span data-stu-id="fcb14-113">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="fcb14-114">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="fcb14-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fcb14-115">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcb14-115">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb14-116">Principalrole.prinroletypeid</span><span class="sxs-lookup"><span data-stu-id="fcb14-116">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="fcb14-117">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="fcb14-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fcb14-118">역할 유형 ID(tblRoleType)입니다.</span><span class="sxs-lookup"><span data-stu-id="fcb14-118">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb14-119">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="fcb14-119">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="fcb14-120">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="fcb14-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fcb14-121">이 항목을 마지막으로 업데이트한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fcb14-121">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="fcb14-122">키</span><span class="sxs-lookup"><span data-stu-id="fcb14-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcb14-123">열</span><span class="sxs-lookup"><span data-stu-id="fcb14-123">Column</span></span></th>
<th><span data-ttu-id="fcb14-124">설명</span><span class="sxs-lookup"><span data-stu-id="fcb14-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcb14-125">&lt;Principalrole.prinrolenodeid, Principalrole.prinroleprinid, Principalrole.prinroletypeid&gt;</span><span class="sxs-lookup"><span data-stu-id="fcb14-125">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="fcb14-126">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="fcb14-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb14-127">Principalrole.prinrolenodeid</span><span class="sxs-lookup"><span data-stu-id="fcb14-127">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="fcb14-128">tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="fcb14-128">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcb14-129">Principalrole.prinroleprinid</span><span class="sxs-lookup"><span data-stu-id="fcb14-129">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="fcb14-130">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="fcb14-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcb14-131">Principalrole.prinroletypeid</span><span class="sxs-lookup"><span data-stu-id="fcb14-131">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="fcb14-132">tblRoleType.rtypeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="fcb14-132">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

