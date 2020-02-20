---
title: 'Lync Server 2013: tblScopePrincipal'
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
ms.openlocfilehash: 147d71ada1d0db26e95868a7115556d30cbc2435
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="e7099-102">Lync Server 2013의 tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="e7099-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7099-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e7099-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e7099-104">tblScopePrincipal에는 노드에 지정된 범위가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e7099-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="e7099-105">단</span><span class="sxs-lookup"><span data-stu-id="e7099-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7099-106">열</span><span class="sxs-lookup"><span data-stu-id="e7099-106">Column</span></span></th>
<th><span data-ttu-id="e7099-107">형식</span><span class="sxs-lookup"><span data-stu-id="e7099-107">Type</span></span></th>
<th><span data-ttu-id="e7099-108">설명</span><span class="sxs-lookup"><span data-stu-id="e7099-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7099-109">Scopeprincipal.scopenodeid</span><span class="sxs-lookup"><span data-stu-id="e7099-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="e7099-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e7099-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e7099-111">해당 범위가 적용되는 노드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e7099-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7099-112">Scopeprincipal.scopeprinid</span><span class="sxs-lookup"><span data-stu-id="e7099-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="e7099-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e7099-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e7099-114">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e7099-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7099-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="e7099-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="e7099-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e7099-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e7099-117">범위 유형이 Deny인 경우 True이고 Allow이면 False입니다.</span><span class="sxs-lookup"><span data-stu-id="e7099-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7099-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="e7099-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="e7099-119">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e7099-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="e7099-120">이 항목을 마지막으로 업데이트한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e7099-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="e7099-121">키</span><span class="sxs-lookup"><span data-stu-id="e7099-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7099-122">열</span><span class="sxs-lookup"><span data-stu-id="e7099-122">Column</span></span></th>
<th><span data-ttu-id="e7099-123">설명</span><span class="sxs-lookup"><span data-stu-id="e7099-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7099-124">&lt;Scopeprincipal.scopenodeid, Scopeprincipal.scopeprinid&gt;</span><span class="sxs-lookup"><span data-stu-id="e7099-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="e7099-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e7099-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7099-126">Scopeprincipal.scopenodeid</span><span class="sxs-lookup"><span data-stu-id="e7099-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="e7099-127">tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e7099-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7099-128">Scopeprincipal.scopeprinid</span><span class="sxs-lookup"><span data-stu-id="e7099-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="e7099-129">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e7099-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

