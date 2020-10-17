---
title: 'Lync Server 2013: tblEnumValue'
description: 'Lync Server 2013: tblEnumValue.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159f90bb96c367fcb3e11725a582a9993080d3fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571374"
---
# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="20bed-103">Lync Server 2013의 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="20bed-103">tblEnumValue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20bed-104">_**마지막으로 수정 된 항목:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="20bed-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="20bed-105">tblEnumValue는 Node 테이블에 사용된 특성의 표시 및 동작 값이 포함된 하드코드된 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="20bed-105">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="20bed-106">단</span><span class="sxs-lookup"><span data-stu-id="20bed-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20bed-107">열</span><span class="sxs-lookup"><span data-stu-id="20bed-107">Column</span></span></th>
<th><span data-ttu-id="20bed-108">유형</span><span class="sxs-lookup"><span data-stu-id="20bed-108">Type</span></span></th>
<th><span data-ttu-id="20bed-109">설명</span><span class="sxs-lookup"><span data-stu-id="20bed-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20bed-110">Tblenumvalue.valueid</span><span class="sxs-lookup"><span data-stu-id="20bed-110">valueID</span></span></p></td>
<td><p><span data-ttu-id="20bed-111">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="20bed-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="20bed-112">값의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="20bed-112">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bed-113">attributeID</span><span class="sxs-lookup"><span data-stu-id="20bed-113">attributeID</span></span></p></td>
<td><p><span data-ttu-id="20bed-114">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="20bed-114">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="20bed-115">특성의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="20bed-115">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bed-116">attributeValue</span><span class="sxs-lookup"><span data-stu-id="20bed-116">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="20bed-117">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="20bed-117">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="20bed-118">값의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="20bed-118">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="20bed-119">키</span><span class="sxs-lookup"><span data-stu-id="20bed-119">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20bed-120">열</span><span class="sxs-lookup"><span data-stu-id="20bed-120">Column</span></span></th>
<th><span data-ttu-id="20bed-121">설명</span><span class="sxs-lookup"><span data-stu-id="20bed-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20bed-122">Tblenumvalue.valueid</span><span class="sxs-lookup"><span data-stu-id="20bed-122">valueID</span></span></p></td>
<td><p><span data-ttu-id="20bed-123">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="20bed-123">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bed-124">attributeID</span><span class="sxs-lookup"><span data-stu-id="20bed-124">attributeID</span></span></p></td>
<td><p><span data-ttu-id="20bed-125">tblEnumAttribute.attributeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="20bed-125">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="20bed-126">테이블 값</span><span class="sxs-lookup"><span data-stu-id="20bed-126">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20bed-127">Tblenumvalue.valueid</span><span class="sxs-lookup"><span data-stu-id="20bed-127">valueID</span></span></th>
<th><span data-ttu-id="20bed-128">attributeID</span><span class="sxs-lookup"><span data-stu-id="20bed-128">attributeID</span></span></th>
<th><span data-ttu-id="20bed-129">attributeValue</span><span class="sxs-lookup"><span data-stu-id="20bed-129">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20bed-130">2</span><span class="sxs-lookup"><span data-stu-id="20bed-130">2</span></span></p></td>
<td><p><span data-ttu-id="20bed-131">1 </span><span class="sxs-lookup"><span data-stu-id="20bed-131">1</span></span></p></td>
<td><p><span data-ttu-id="20bed-132">유지</span><span class="sxs-lookup"><span data-stu-id="20bed-132">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bed-133">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="20bed-133">3</span></span></p></td>
<td><p><span data-ttu-id="20bed-134">1 </span><span class="sxs-lookup"><span data-stu-id="20bed-134">1</span></span></p></td>
<td><p><span data-ttu-id="20bed-135">scope</span><span class="sxs-lookup"><span data-stu-id="20bed-135">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bed-136">4 </span><span class="sxs-lookup"><span data-stu-id="20bed-136">4</span></span></p></td>
<td><p><span data-ttu-id="20bed-137">2</span><span class="sxs-lookup"><span data-stu-id="20bed-137">2</span></span></p></td>
<td><p><span data-ttu-id="20bed-138">보통인</span><span class="sxs-lookup"><span data-stu-id="20bed-138">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20bed-139">5 </span><span class="sxs-lookup"><span data-stu-id="20bed-139">5</span></span></p></td>
<td><p><span data-ttu-id="20bed-140">2</span><span class="sxs-lookup"><span data-stu-id="20bed-140">2</span></span></p></td>
<td><p><span data-ttu-id="20bed-141">강당</span><span class="sxs-lookup"><span data-stu-id="20bed-141">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20bed-142">6 </span><span class="sxs-lookup"><span data-stu-id="20bed-142">6</span></span></p></td>
<td><p><span data-ttu-id="20bed-143">1 </span><span class="sxs-lookup"><span data-stu-id="20bed-143">1</span></span></p></td>
<td><p><span data-ttu-id="20bed-144">열린</span><span class="sxs-lookup"><span data-stu-id="20bed-144">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="20bed-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20bed-145">See Also</span></span>


[<span data-ttu-id="20bed-146">Lync Server 2013의 tblNode</span><span class="sxs-lookup"><span data-stu-id="20bed-146">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

