---
title: 'Lync Server 2013: tblPrincipalInvites'
description: 'Lync Server 2013: tblPrincipalInvites'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558650(v=OCS.15)
ms:contentKeyID: 48184141
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d30d741864ed2a3cfbec8329215be33c21b3b262
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564674"
---
# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="aca67-103">Lync Server 2013의 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="aca67-103">tblPrincipalInvites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aca67-104">_**마지막으로 수정 된 항목:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="aca67-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="aca67-105">tblPrincipalInvites에는 자동 초대가 켜진 모든 노드에 대해 프로비전된 모든 사용자에 대한 초대가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="aca67-105">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="aca67-106">단</span><span class="sxs-lookup"><span data-stu-id="aca67-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aca67-107">열</span><span class="sxs-lookup"><span data-stu-id="aca67-107">Column</span></span></th>
<th><span data-ttu-id="aca67-108">유형</span><span class="sxs-lookup"><span data-stu-id="aca67-108">Type</span></span></th>
<th><span data-ttu-id="aca67-109">설명</span><span class="sxs-lookup"><span data-stu-id="aca67-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aca67-110">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="aca67-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="aca67-111">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="aca67-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="aca67-112">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="aca67-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aca67-113">invID</span><span class="sxs-lookup"><span data-stu-id="aca67-113">invID</span></span></p></td>
<td><p><span data-ttu-id="aca67-114">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="aca67-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="aca67-115">tblLastInviteId 테이블에서 생성된 고유한 일련 번호(계정 ID당 하나)입니다.</span><span class="sxs-lookup"><span data-stu-id="aca67-115">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aca67-116">입니다</span><span class="sxs-lookup"><span data-stu-id="aca67-116">nodeID</span></span></p></td>
<td><p><span data-ttu-id="aca67-117">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="aca67-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="aca67-118">노드 ID(대화방 전용)입니다.</span><span class="sxs-lookup"><span data-stu-id="aca67-118">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aca67-119">createdOn</span><span class="sxs-lookup"><span data-stu-id="aca67-119">createdOn</span></span></p></td>
<td><p><span data-ttu-id="aca67-120">datetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="aca67-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="aca67-121">만든 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="aca67-121">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="aca67-122">키</span><span class="sxs-lookup"><span data-stu-id="aca67-122">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aca67-123">열</span><span class="sxs-lookup"><span data-stu-id="aca67-123">Column</span></span></th>
<th><span data-ttu-id="aca67-124">설명</span><span class="sxs-lookup"><span data-stu-id="aca67-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aca67-125">&lt;Tblprincipal.prinid,입니다&gt;</span><span class="sxs-lookup"><span data-stu-id="aca67-125">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="aca67-126">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="aca67-126">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aca67-127">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="aca67-127">prinID</span></span></p></td>
<td><p><span data-ttu-id="aca67-128">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="aca67-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aca67-129">입니다</span><span class="sxs-lookup"><span data-stu-id="aca67-129">nodeID</span></span></p></td>
<td><p><span data-ttu-id="aca67-130">tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="aca67-130">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

