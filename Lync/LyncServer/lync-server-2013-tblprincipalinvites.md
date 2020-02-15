---
title: 'Lync Server 2013: tblPrincipalInvites'
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
ms.openlocfilehash: a4316e86d29013587b2302d18a840a4a1859f9ad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="4f44a-102">Lync Server 2013의 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="4f44a-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f44a-103">_**마지막으로 수정 된 항목:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="4f44a-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="4f44a-104">tblPrincipalInvites에는 자동 초대가 켜진 모든 노드에 대해 프로비전된 모든 사용자에 대한 초대가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f44a-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="4f44a-105">단</span><span class="sxs-lookup"><span data-stu-id="4f44a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f44a-106">열</span><span class="sxs-lookup"><span data-stu-id="4f44a-106">Column</span></span></th>
<th><span data-ttu-id="4f44a-107">형식</span><span class="sxs-lookup"><span data-stu-id="4f44a-107">Type</span></span></th>
<th><span data-ttu-id="4f44a-108">설명</span><span class="sxs-lookup"><span data-stu-id="4f44a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f44a-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="4f44a-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="4f44a-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="4f44a-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4f44a-111">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4f44a-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f44a-112">invID</span><span class="sxs-lookup"><span data-stu-id="4f44a-112">invID</span></span></p></td>
<td><p><span data-ttu-id="4f44a-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="4f44a-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4f44a-114">tblLastInviteId 테이블에서 생성된 고유한 일련 번호(계정 ID당 하나)입니다.</span><span class="sxs-lookup"><span data-stu-id="4f44a-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f44a-115">입니다</span><span class="sxs-lookup"><span data-stu-id="4f44a-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="4f44a-116">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="4f44a-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="4f44a-117">노드 ID(대화방 전용)입니다.</span><span class="sxs-lookup"><span data-stu-id="4f44a-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f44a-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="4f44a-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="4f44a-119">datetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="4f44a-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="4f44a-120">만든 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4f44a-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="4f44a-121">키</span><span class="sxs-lookup"><span data-stu-id="4f44a-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f44a-122">열</span><span class="sxs-lookup"><span data-stu-id="4f44a-122">Column</span></span></th>
<th><span data-ttu-id="4f44a-123">설명</span><span class="sxs-lookup"><span data-stu-id="4f44a-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f44a-124">&lt;Tblprincipal.prinid,입니다&gt;</span><span class="sxs-lookup"><span data-stu-id="4f44a-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="4f44a-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="4f44a-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f44a-126">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="4f44a-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="4f44a-127">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="4f44a-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f44a-128">입니다</span><span class="sxs-lookup"><span data-stu-id="4f44a-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="4f44a-129">tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="4f44a-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

