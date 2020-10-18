---
title: 'Lync Server 2013: tblPrincipalMeta'
description: 'Lync Server 2013: tblPrincipalMeta'
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
ms.openlocfilehash: 899fd1e450dac52afa56c1ee1de86da82b2db309
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573644"
---
# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="55a5b-103">Lync Server 2013의 tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="55a5b-103">tblPrincipalMeta in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55a5b-104">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="55a5b-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="55a5b-105">tblPrincipalMeta에는 Active Directory 도메인 서비스에서 새로 고쳐야 하는 사용자가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55a5b-105">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="55a5b-106">단</span><span class="sxs-lookup"><span data-stu-id="55a5b-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55a5b-107">열</span><span class="sxs-lookup"><span data-stu-id="55a5b-107">Column</span></span></th>
<th><span data-ttu-id="55a5b-108">유형</span><span class="sxs-lookup"><span data-stu-id="55a5b-108">Type</span></span></th>
<th><span data-ttu-id="55a5b-109">설명</span><span class="sxs-lookup"><span data-stu-id="55a5b-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55a5b-110">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="55a5b-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="55a5b-111">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="55a5b-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="55a5b-112">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="55a5b-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55a5b-113">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="55a5b-113">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="55a5b-114">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="55a5b-114">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="55a5b-115">사용자 회원 정보를 새로 고쳐야 하는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="55a5b-115">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55a5b-116">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="55a5b-116">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="55a5b-117">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="55a5b-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="55a5b-118">사용자 특성을 새로 고쳐야 하는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="55a5b-118">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55a5b-119">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="55a5b-119">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="55a5b-120">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="55a5b-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="55a5b-121">사용자가 삭제된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="55a5b-121">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55a5b-122">tryCount</span><span class="sxs-lookup"><span data-stu-id="55a5b-122">tryCount</span></span></p></td>
<td><p><span data-ttu-id="55a5b-123">int</span><span class="sxs-lookup"><span data-stu-id="55a5b-123">int</span></span></p></td>
<td><p><span data-ttu-id="55a5b-124">지금까지 AD DS에서 사용자를 새로 고치려는 시도가 발생한 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="55a5b-124">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55a5b-125">lastTry</span><span class="sxs-lookup"><span data-stu-id="55a5b-125">lastTry</span></span></p></td>
<td><p><span data-ttu-id="55a5b-126">datetime</span><span class="sxs-lookup"><span data-stu-id="55a5b-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="55a5b-p101">사용자를 새로 고치려는 가장 최근 시도의 타임스탬프입니다. 새로 고침이 아직 시도되지 않은 경우 Null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55a5b-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55a5b-129">nextTry</span><span class="sxs-lookup"><span data-stu-id="55a5b-129">nextTry</span></span></p></td>
<td><p><span data-ttu-id="55a5b-130">datetime</span><span class="sxs-lookup"><span data-stu-id="55a5b-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="55a5b-p102">다음 예약된 새로 고침의 타임스탬프입니다. 이후 새로 고침이 예약되지 않은 경우 Null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55a5b-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="55a5b-133">키</span><span class="sxs-lookup"><span data-stu-id="55a5b-133">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55a5b-134">열</span><span class="sxs-lookup"><span data-stu-id="55a5b-134">Column</span></span></th>
<th><span data-ttu-id="55a5b-135">설명</span><span class="sxs-lookup"><span data-stu-id="55a5b-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55a5b-136">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="55a5b-136">prinID</span></span></p></td>
<td><p><span data-ttu-id="55a5b-137">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="55a5b-137">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55a5b-138">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="55a5b-138">prinID</span></span></p></td>
<td><p><span data-ttu-id="55a5b-139">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="55a5b-139">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

