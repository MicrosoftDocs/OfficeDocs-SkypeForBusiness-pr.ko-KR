---
title: 'Lync Server 2013: tblPrincipalRole'
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
ms.openlocfilehash: 685e8ae3e767e3dc237da1698fd593a9c56021c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="d0fe2-102">Lync Server 2013의 tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="d0fe2-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0fe2-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="d0fe2-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="d0fe2-104">tblPrincipalRole 테이블에는 노드에 할당된 명시적 역할이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0fe2-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="d0fe2-105">단</span><span class="sxs-lookup"><span data-stu-id="d0fe2-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0fe2-106">열</span><span class="sxs-lookup"><span data-stu-id="d0fe2-106">Column</span></span></th>
<th><span data-ttu-id="d0fe2-107">형식</span><span class="sxs-lookup"><span data-stu-id="d0fe2-107">Type</span></span></th>
<th><span data-ttu-id="d0fe2-108">설명</span><span class="sxs-lookup"><span data-stu-id="d0fe2-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0fe2-109">Principalrole.prinrolenodeid</span><span class="sxs-lookup"><span data-stu-id="d0fe2-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="d0fe2-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="d0fe2-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d0fe2-111">해당 역할이 적용되는 노드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d0fe2-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0fe2-112">Principalrole.prinroleprinid</span><span class="sxs-lookup"><span data-stu-id="d0fe2-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="d0fe2-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="d0fe2-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d0fe2-114">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d0fe2-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0fe2-115">Principalrole.prinroletypeid</span><span class="sxs-lookup"><span data-stu-id="d0fe2-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="d0fe2-116">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="d0fe2-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d0fe2-117">역할 유형 ID(tblRoleType)입니다.</span><span class="sxs-lookup"><span data-stu-id="d0fe2-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0fe2-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="d0fe2-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="d0fe2-119">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="d0fe2-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="d0fe2-120">이 항목을 마지막으로 업데이트한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d0fe2-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="d0fe2-121">키</span><span class="sxs-lookup"><span data-stu-id="d0fe2-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0fe2-122">열</span><span class="sxs-lookup"><span data-stu-id="d0fe2-122">Column</span></span></th>
<th><span data-ttu-id="d0fe2-123">설명</span><span class="sxs-lookup"><span data-stu-id="d0fe2-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d0fe2-124">&lt;Principalrole.prinrolenodeid, Principalrole.prinroleprinid, Principalrole.prinroletypeid&gt;</span><span class="sxs-lookup"><span data-stu-id="d0fe2-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="d0fe2-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="d0fe2-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0fe2-126">Principalrole.prinrolenodeid</span><span class="sxs-lookup"><span data-stu-id="d0fe2-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="d0fe2-127">tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="d0fe2-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d0fe2-128">Principalrole.prinroleprinid</span><span class="sxs-lookup"><span data-stu-id="d0fe2-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="d0fe2-129">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="d0fe2-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d0fe2-130">Principalrole.prinroletypeid</span><span class="sxs-lookup"><span data-stu-id="d0fe2-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="d0fe2-131">tblRoleType.rtypeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="d0fe2-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

