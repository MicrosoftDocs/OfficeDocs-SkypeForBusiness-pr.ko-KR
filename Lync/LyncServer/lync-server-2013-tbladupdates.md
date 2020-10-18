---
title: 'Lync Server 2013: tblADUpdates'
description: 'Lync Server 2013: tblADUpdates'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ab4418a10eac283d0f39d09b1c1fe15a32b2e68
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573684"
---
# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="02dc3-103">Lync Server 2013의 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="02dc3-103">tblADUpdates in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02dc3-104">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="02dc3-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="02dc3-105">tblADUpdates에는 이후 Active Directory 동기화 단계에서 아직 처리 되지 않은 Active Directory 도메인 서비스 변경 내용이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02dc3-105">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="02dc3-106">단</span><span class="sxs-lookup"><span data-stu-id="02dc3-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02dc3-107">열</span><span class="sxs-lookup"><span data-stu-id="02dc3-107">Column</span></span></th>
<th><span data-ttu-id="02dc3-108">유형</span><span class="sxs-lookup"><span data-stu-id="02dc3-108">Type</span></span></th>
<th><span data-ttu-id="02dc3-109">설명</span><span class="sxs-lookup"><span data-stu-id="02dc3-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02dc3-110">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="02dc3-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="02dc3-111">GUID, null이 아님</span><span class="sxs-lookup"><span data-stu-id="02dc3-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="02dc3-112">변경된 개체의 사용자 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="02dc3-112">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02dc3-113">prinADPath</span><span class="sxs-lookup"><span data-stu-id="02dc3-113">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="02dc3-114">nvarchar(384), null이 아님</span><span class="sxs-lookup"><span data-stu-id="02dc3-114">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="02dc3-115">개체의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="02dc3-115">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02dc3-116">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="02dc3-116">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="02dc3-117">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="02dc3-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="02dc3-118">개체의 특성이 하나 이상 변경된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="02dc3-118">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02dc3-119">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="02dc3-119">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="02dc3-120">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="02dc3-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="02dc3-121">구성원 자격이 변경된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="02dc3-121">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02dc3-122">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="02dc3-122">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="02dc3-123">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="02dc3-123">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="02dc3-124">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02dc3-124">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02dc3-125">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="02dc3-125">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="02dc3-126">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="02dc3-126">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="02dc3-127">개체가 삭제된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="02dc3-127">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02dc3-128">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="02dc3-128">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="02dc3-129">datetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="02dc3-129">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="02dc3-130">행이 삽입되었을 때의 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="02dc3-130">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

