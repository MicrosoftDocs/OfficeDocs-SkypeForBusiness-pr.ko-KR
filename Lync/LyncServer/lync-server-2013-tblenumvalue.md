---
title: 'Lync Server 2013: tblEnumValue'
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
ms.openlocfilehash: 984dd5f161b31c40de914f363c0722657d3194ed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="07e9c-102">Lync Server 2013의 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="07e9c-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07e9c-103">_**마지막으로 수정 된 항목:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="07e9c-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="07e9c-104">tblEnumValue는 Node 테이블에 사용된 특성의 표시 및 동작 값이 포함된 하드코드된 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="07e9c-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="07e9c-105">단</span><span class="sxs-lookup"><span data-stu-id="07e9c-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07e9c-106">열</span><span class="sxs-lookup"><span data-stu-id="07e9c-106">Column</span></span></th>
<th><span data-ttu-id="07e9c-107">형식</span><span class="sxs-lookup"><span data-stu-id="07e9c-107">Type</span></span></th>
<th><span data-ttu-id="07e9c-108">설명</span><span class="sxs-lookup"><span data-stu-id="07e9c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07e9c-109">Tblenumvalue.valueid</span><span class="sxs-lookup"><span data-stu-id="07e9c-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="07e9c-110">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="07e9c-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="07e9c-111">값의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="07e9c-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e9c-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="07e9c-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="07e9c-113">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="07e9c-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="07e9c-114">특성의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="07e9c-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e9c-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="07e9c-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="07e9c-116">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="07e9c-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="07e9c-117">값의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="07e9c-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="07e9c-118">키</span><span class="sxs-lookup"><span data-stu-id="07e9c-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07e9c-119">열</span><span class="sxs-lookup"><span data-stu-id="07e9c-119">Column</span></span></th>
<th><span data-ttu-id="07e9c-120">설명</span><span class="sxs-lookup"><span data-stu-id="07e9c-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07e9c-121">Tblenumvalue.valueid</span><span class="sxs-lookup"><span data-stu-id="07e9c-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="07e9c-122">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="07e9c-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e9c-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="07e9c-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="07e9c-124">tblEnumAttribute.attributeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="07e9c-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="07e9c-125">테이블 값</span><span class="sxs-lookup"><span data-stu-id="07e9c-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="07e9c-126">Tblenumvalue.valueid</span><span class="sxs-lookup"><span data-stu-id="07e9c-126">valueID</span></span></th>
<th><span data-ttu-id="07e9c-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="07e9c-127">attributeID</span></span></th>
<th><span data-ttu-id="07e9c-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="07e9c-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07e9c-129">2</span><span class="sxs-lookup"><span data-stu-id="07e9c-129">2</span></span></p></td>
<td><p><span data-ttu-id="07e9c-130">개</span><span class="sxs-lookup"><span data-stu-id="07e9c-130">1</span></span></p></td>
<td><p><span data-ttu-id="07e9c-131">유지</span><span class="sxs-lookup"><span data-stu-id="07e9c-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e9c-132">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="07e9c-132">3</span></span></p></td>
<td><p><span data-ttu-id="07e9c-133">개</span><span class="sxs-lookup"><span data-stu-id="07e9c-133">1</span></span></p></td>
<td><p><span data-ttu-id="07e9c-134">scope</span><span class="sxs-lookup"><span data-stu-id="07e9c-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e9c-135">1-4</span><span class="sxs-lookup"><span data-stu-id="07e9c-135">4</span></span></p></td>
<td><p><span data-ttu-id="07e9c-136">2</span><span class="sxs-lookup"><span data-stu-id="07e9c-136">2</span></span></p></td>
<td><p><span data-ttu-id="07e9c-137">보통인</span><span class="sxs-lookup"><span data-stu-id="07e9c-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07e9c-138">2-5</span><span class="sxs-lookup"><span data-stu-id="07e9c-138">5</span></span></p></td>
<td><p><span data-ttu-id="07e9c-139">2</span><span class="sxs-lookup"><span data-stu-id="07e9c-139">2</span></span></p></td>
<td><p><span data-ttu-id="07e9c-140">강당</span><span class="sxs-lookup"><span data-stu-id="07e9c-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07e9c-141">6 </span><span class="sxs-lookup"><span data-stu-id="07e9c-141">6</span></span></p></td>
<td><p><span data-ttu-id="07e9c-142">개</span><span class="sxs-lookup"><span data-stu-id="07e9c-142">1</span></span></p></td>
<td><p><span data-ttu-id="07e9c-143">열린</span><span class="sxs-lookup"><span data-stu-id="07e9c-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="07e9c-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07e9c-144">See Also</span></span>


[<span data-ttu-id="07e9c-145">Lync Server 2013의 tblNode</span><span class="sxs-lookup"><span data-stu-id="07e9c-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

