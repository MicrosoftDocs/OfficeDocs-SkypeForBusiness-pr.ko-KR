---
title: 'Lync Server 2013: tblADUpdates'
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
ms.openlocfilehash: ee3f0d881e26c3d26773b1b59feca3d1d02665dd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a><span data-ttu-id="64310-102">Lync Server 2013의 tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="64310-102">tblADUpdates in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64310-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="64310-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="64310-104">tblADUpdates에는 이후 Active Directory 동기화 단계에서 아직 처리 되지 않은 Active Directory 도메인 서비스 변경 내용이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64310-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>

### <a name="columns"></a><span data-ttu-id="64310-105">단</span><span class="sxs-lookup"><span data-stu-id="64310-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="64310-106">열</span><span class="sxs-lookup"><span data-stu-id="64310-106">Column</span></span></th>
<th><span data-ttu-id="64310-107">형식</span><span class="sxs-lookup"><span data-stu-id="64310-107">Type</span></span></th>
<th><span data-ttu-id="64310-108">설명</span><span class="sxs-lookup"><span data-stu-id="64310-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="64310-109">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="64310-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="64310-110">GUID, null이 아님</span><span class="sxs-lookup"><span data-stu-id="64310-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="64310-111">변경된 개체의 사용자 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="64310-111">Principal GUID of the object that changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64310-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="64310-112">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="64310-113">nvarchar(384), null이 아님</span><span class="sxs-lookup"><span data-stu-id="64310-113">nvarchar (384), not null</span></span></p></td>
<td><p><span data-ttu-id="64310-114">개체의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="64310-114">Distinguished name of the object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64310-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="64310-115">prinAttributesChanged</span></span></p></td>
<td><p><span data-ttu-id="64310-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="64310-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="64310-117">개체의 특성이 하나 이상 변경된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="64310-117">True if at least one attribute of the object changed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64310-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="64310-118">prinMembersChanged</span></span></p></td>
<td><p><span data-ttu-id="64310-119">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="64310-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="64310-120">구성원 자격이 변경된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="64310-120">True if the membership changed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64310-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="64310-121">prinAffiliationsChanged</span></span></p></td>
<td><p><span data-ttu-id="64310-122">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="64310-122">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="64310-123">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64310-123">Not used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="64310-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="64310-124">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="64310-125">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="64310-125">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="64310-126">개체가 삭제된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="64310-126">True if the object was deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="64310-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="64310-127">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="64310-128">datetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="64310-128">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="64310-129">행이 삽입되었을 때의 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="64310-129">Time stamp of when the row was inserted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

