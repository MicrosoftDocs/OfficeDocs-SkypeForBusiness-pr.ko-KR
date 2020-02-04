---
title: 'Lync Server 2013: tblPrincipalMeta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 848f4dc19ddf64c53c2dd30ae6ca4c8036b67c79
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="19120-102">Lync Server 2013의 tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="19120-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19120-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="19120-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="19120-104">tblPrincipalMeta에는 Active Directory 도메인 서비스에서 새로 고쳐야 하는 사용자가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19120-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="19120-105">열</span><span class="sxs-lookup"><span data-stu-id="19120-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19120-106">열</span><span class="sxs-lookup"><span data-stu-id="19120-106">Column</span></span></th>
<th><span data-ttu-id="19120-107">유형</span><span class="sxs-lookup"><span data-stu-id="19120-107">Type</span></span></th>
<th><span data-ttu-id="19120-108">설명</span><span class="sxs-lookup"><span data-stu-id="19120-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19120-109">prinID</span><span class="sxs-lookup"><span data-stu-id="19120-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="19120-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="19120-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="19120-111">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="19120-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19120-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="19120-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="19120-113">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="19120-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="19120-114">Principal 소속을 새로 고쳐야 하는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="19120-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19120-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="19120-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="19120-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="19120-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="19120-117">Principal 특성을 새로 고쳐야 하는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="19120-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19120-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="19120-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="19120-119">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="19120-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="19120-120">보안 주체가 삭제 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="19120-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19120-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="19120-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="19120-122">int</span><span class="sxs-lookup"><span data-stu-id="19120-122">int</span></span></p></td>
<td><p><span data-ttu-id="19120-123">지금까지 발생 한 AD DS에서 보안 주체의 새로 고침 시도 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="19120-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19120-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="19120-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="19120-125">dmtf</span><span class="sxs-lookup"><span data-stu-id="19120-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="19120-126">주 사용자를 새로 고치기 위한 최신 시도의 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="19120-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="19120-127">아직 새로 고침이 시도 되지 않은 경우 null이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19120-127">Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19120-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="19120-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="19120-129">dmtf</span><span class="sxs-lookup"><span data-stu-id="19120-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="19120-130">예정 된 다음 새로 고침에 대 한 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="19120-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="19120-131">추가 새로 고침이 예약 되지 않은 경우 null이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19120-131">Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="19120-132">핵심</span><span class="sxs-lookup"><span data-stu-id="19120-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19120-133">열</span><span class="sxs-lookup"><span data-stu-id="19120-133">Column</span></span></th>
<th><span data-ttu-id="19120-134">설명</span><span class="sxs-lookup"><span data-stu-id="19120-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19120-135">prinID</span><span class="sxs-lookup"><span data-stu-id="19120-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="19120-136">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="19120-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19120-137">prinID</span><span class="sxs-lookup"><span data-stu-id="19120-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="19120-138">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="19120-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

