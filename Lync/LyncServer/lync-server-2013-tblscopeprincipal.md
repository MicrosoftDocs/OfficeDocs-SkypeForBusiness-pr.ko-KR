---
title: 'Lync Server 2013: tblScopePrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece5ae542060835aefa05edb6e08b766293e2ac1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a><span data-ttu-id="b2953-102">Lync Server 2013의 tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="b2953-102">tblScopePrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2953-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b2953-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b2953-104">tblScopePrincipal에는 노드에 할당 된 범위가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2953-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>

### <a name="columns"></a><span data-ttu-id="b2953-105">열</span><span class="sxs-lookup"><span data-stu-id="b2953-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2953-106">열</span><span class="sxs-lookup"><span data-stu-id="b2953-106">Column</span></span></th>
<th><span data-ttu-id="b2953-107">유형</span><span class="sxs-lookup"><span data-stu-id="b2953-107">Type</span></span></th>
<th><span data-ttu-id="b2953-108">설명</span><span class="sxs-lookup"><span data-stu-id="b2953-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2953-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="b2953-109">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="b2953-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="b2953-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b2953-111">범위가 적용 되는 노드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b2953-111">Node ID that the scope applies to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2953-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="b2953-112">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="b2953-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="b2953-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b2953-114">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="b2953-114">Principal ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2953-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="b2953-115">scopeIsDenied</span></span></p></td>
<td><p><span data-ttu-id="b2953-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="b2953-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b2953-117">범위 형식이 Deny 이면 True이 고, 그렇지 않으면 false입니다. 허용 하는 경우 False</span><span class="sxs-lookup"><span data-stu-id="b2953-117">True if type of scope is Deny; False if Allow.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2953-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="b2953-118">scopeUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="b2953-119">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="b2953-119">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b2953-120">이 항목을 마지막으로 업데이트 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b2953-120">ID of the principal that last updated this entry.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b2953-121">핵심</span><span class="sxs-lookup"><span data-stu-id="b2953-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2953-122">열</span><span class="sxs-lookup"><span data-stu-id="b2953-122">Column</span></span></th>
<th><span data-ttu-id="b2953-123">설명</span><span class="sxs-lookup"><span data-stu-id="b2953-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2953-124">&lt;scopeNodeID, scopePrinID&gt;</span><span class="sxs-lookup"><span data-stu-id="b2953-124">&lt;scopeNodeID, scopePrinID&gt;</span></span></p></td>
<td><p><span data-ttu-id="b2953-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="b2953-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2953-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="b2953-126">scopeNodeID</span></span></p></td>
<td><p><span data-ttu-id="b2953-127">NodeID 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="b2953-127">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2953-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="b2953-128">scopePrinID</span></span></p></td>
<td><p><span data-ttu-id="b2953-129">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="b2953-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

