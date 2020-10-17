---
title: 'Lync Server 2013: tblScopePrincipal'
description: 'Lync Server 2013: tblScopePrincipal.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63315f8525e5c2f05fe54a0f9ed9e8a97b9e8bce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555614"
---
# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="379a2-103">Lync Server 2013의 tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="379a2-103">tblScopePrincipal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="379a2-104">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="379a2-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="379a2-105">tblScopePrincipal에는 노드에 지정된 범위가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="379a2-105">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="379a2-106">단</span><span class="sxs-lookup"><span data-stu-id="379a2-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="379a2-107">열</span><span class="sxs-lookup"><span data-stu-id="379a2-107">Column</span></span></th>
<th><span data-ttu-id="379a2-108">유형</span><span class="sxs-lookup"><span data-stu-id="379a2-108">Type</span></span></th>
<th><span data-ttu-id="379a2-109">설명</span><span class="sxs-lookup"><span data-stu-id="379a2-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="379a2-110">Scopeprincipal.scopenodeid</span><span class="sxs-lookup"><span data-stu-id="379a2-110">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="379a2-111">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="379a2-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="379a2-112">해당 범위가 적용되는 노드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="379a2-112">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="379a2-113">Scopeprincipal.scopeprinid</span><span class="sxs-lookup"><span data-stu-id="379a2-113">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="379a2-114">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="379a2-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="379a2-115">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="379a2-115">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="379a2-116">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="379a2-116">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="379a2-117">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="379a2-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="379a2-118">범위 유형이 Deny인 경우 True이고 Allow이면 False입니다.</span><span class="sxs-lookup"><span data-stu-id="379a2-118">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="379a2-119">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="379a2-119">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="379a2-120">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="379a2-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="379a2-121">이 항목을 마지막으로 업데이트한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="379a2-121">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="379a2-122">키</span><span class="sxs-lookup"><span data-stu-id="379a2-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="379a2-123">열</span><span class="sxs-lookup"><span data-stu-id="379a2-123">Column</span></span></th>
<th><span data-ttu-id="379a2-124">설명</span><span class="sxs-lookup"><span data-stu-id="379a2-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="379a2-125">&lt;Scopeprincipal.scopenodeid, Scopeprincipal.scopeprinid&gt;</span><span class="sxs-lookup"><span data-stu-id="379a2-125">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="379a2-126">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="379a2-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="379a2-127">Scopeprincipal.scopenodeid</span><span class="sxs-lookup"><span data-stu-id="379a2-127">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="379a2-128">tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="379a2-128">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="379a2-129">Scopeprincipal.scopeprinid</span><span class="sxs-lookup"><span data-stu-id="379a2-129">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="379a2-130">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="379a2-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

