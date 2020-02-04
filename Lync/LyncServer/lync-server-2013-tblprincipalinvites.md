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
ms.openlocfilehash: 75d842772c8c0e02352eacf7f80711aa79c29461
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalinvites-in-lync-server-2013"></a><span data-ttu-id="98469-102">Lync Server 2013의 tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="98469-102">tblPrincipalInvites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98469-103">_**마지막으로 수정한 주제:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="98469-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="98469-104">tblPrincipalInvites는 자동 초대를 사용 하는 모든 노드에 대해 프로 비전 된 모든 사용자에 대 한 초대를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="98469-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>

### <a name="columns"></a><span data-ttu-id="98469-105">열</span><span class="sxs-lookup"><span data-stu-id="98469-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98469-106">열</span><span class="sxs-lookup"><span data-stu-id="98469-106">Column</span></span></th>
<th><span data-ttu-id="98469-107">유형</span><span class="sxs-lookup"><span data-stu-id="98469-107">Type</span></span></th>
<th><span data-ttu-id="98469-108">설명</span><span class="sxs-lookup"><span data-stu-id="98469-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98469-109">prinID</span><span class="sxs-lookup"><span data-stu-id="98469-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="98469-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="98469-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="98469-111">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="98469-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98469-112">invID</span><span class="sxs-lookup"><span data-stu-id="98469-112">invID</span></span></p></td>
<td><p><span data-ttu-id="98469-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="98469-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="98469-114">TblLastInviteId 테이블에서 생성 된 고유 순차 번호 (주체 ID 당)입니다.</span><span class="sxs-lookup"><span data-stu-id="98469-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98469-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="98469-115">nodeID</span></span></p></td>
<td><p><span data-ttu-id="98469-116">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="98469-116">int, not null</span></span></p></td>
<td><p><span data-ttu-id="98469-117">노드 ID (대화방에만 해당).</span><span class="sxs-lookup"><span data-stu-id="98469-117">Node ID (chat room only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98469-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="98469-118">createdOn</span></span></p></td>
<td><p><span data-ttu-id="98469-119">datetime, null 아님</span><span class="sxs-lookup"><span data-stu-id="98469-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="98469-120">생성 시간.</span><span class="sxs-lookup"><span data-stu-id="98469-120">Time of creation.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="98469-121">핵심</span><span class="sxs-lookup"><span data-stu-id="98469-121">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98469-122">열</span><span class="sxs-lookup"><span data-stu-id="98469-122">Column</span></span></th>
<th><span data-ttu-id="98469-123">설명</span><span class="sxs-lookup"><span data-stu-id="98469-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98469-124">&lt;prinID, nodeID&gt;</span><span class="sxs-lookup"><span data-stu-id="98469-124">&lt;prinID, nodeID&gt;</span></span></p></td>
<td><p><span data-ttu-id="98469-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="98469-125">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98469-126">prinID</span><span class="sxs-lookup"><span data-stu-id="98469-126">prinID</span></span></p></td>
<td><p><span data-ttu-id="98469-127">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="98469-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98469-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="98469-128">nodeID</span></span></p></td>
<td><p><span data-ttu-id="98469-129">NodeID 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="98469-129">Foreign key with lookup in tblNode.nodeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

