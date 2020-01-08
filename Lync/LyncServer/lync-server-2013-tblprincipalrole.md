---
title: 'Lync Server 2013: tblPrincipalRole'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 560f454531060a8458c8c920a1e4c5921867f3e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a><span data-ttu-id="c0a3a-102">Lync Server 2013의 tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="c0a3a-102">tblPrincipalRole in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0a3a-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="c0a3a-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="c0a3a-104">tblPrincipalRole에는 노드에 할당 된 명시적 역할이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0a3a-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="c0a3a-105">열</span><span class="sxs-lookup"><span data-stu-id="c0a3a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0a3a-106">열</span><span class="sxs-lookup"><span data-stu-id="c0a3a-106">Column</span></span></th>
<th><span data-ttu-id="c0a3a-107">유형</span><span class="sxs-lookup"><span data-stu-id="c0a3a-107">Type</span></span></th>
<th><span data-ttu-id="c0a3a-108">설명</span><span class="sxs-lookup"><span data-stu-id="c0a3a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0a3a-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="c0a3a-109">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="c0a3a-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="c0a3a-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c0a3a-111">역할이 적용 되는 노드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c0a3a-111">Node ID that the role applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0a3a-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="c0a3a-112">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="c0a3a-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="c0a3a-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c0a3a-114">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="c0a3a-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0a3a-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="c0a3a-115">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="c0a3a-116">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="c0a3a-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c0a3a-117">역할 유형 ID (tblRoleType)입니다.</span><span class="sxs-lookup"><span data-stu-id="c0a3a-117">Role type ID (from tblRoleType).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0a3a-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="c0a3a-118">prinRoleUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="c0a3a-119">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="c0a3a-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="c0a3a-120">이 항목을 마지막으로 업데이트 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c0a3a-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="c0a3a-121">핵심</span><span class="sxs-lookup"><span data-stu-id="c0a3a-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0a3a-122">열</span><span class="sxs-lookup"><span data-stu-id="c0a3a-122">Column</span></span></th>
<th><span data-ttu-id="c0a3a-123">설명</span><span class="sxs-lookup"><span data-stu-id="c0a3a-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0a3a-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span><span class="sxs-lookup"><span data-stu-id="c0a3a-124">&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="c0a3a-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c0a3a-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0a3a-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="c0a3a-126">prinRoleNodeID</span></span></p></td>
<td><p><span data-ttu-id="c0a3a-127">NodeID 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c0a3a-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0a3a-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="c0a3a-128">prinRolePrinID</span></span></p></td>
<td><p><span data-ttu-id="c0a3a-129">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c0a3a-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0a3a-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="c0a3a-130">prinRoleTypeID</span></span></p></td>
<td><p><span data-ttu-id="c0a3a-131">TblRoleType의 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c0a3a-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

