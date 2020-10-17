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
ms.openlocfilehash: 79d1b68cd10858812a1310ebbd1f2caae913da75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509325"
---
# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="ae58f-102">Lync Server 2013의 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="ae58f-102">tblEnumValue in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae58f-103">_**마지막으로 수정 된 항목:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="ae58f-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="ae58f-104">tblEnumValue는 Node 테이블에 사용된 특성의 표시 및 동작 값이 포함된 하드코드된 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="ae58f-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="ae58f-105">단</span><span class="sxs-lookup"><span data-stu-id="ae58f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae58f-106">열</span><span class="sxs-lookup"><span data-stu-id="ae58f-106">Column</span></span></th>
<th><span data-ttu-id="ae58f-107">유형</span><span class="sxs-lookup"><span data-stu-id="ae58f-107">Type</span></span></th>
<th><span data-ttu-id="ae58f-108">설명</span><span class="sxs-lookup"><span data-stu-id="ae58f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae58f-109">Tblenumvalue.valueid</span><span class="sxs-lookup"><span data-stu-id="ae58f-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="ae58f-110">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="ae58f-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="ae58f-111">값의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ae58f-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae58f-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="ae58f-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="ae58f-113">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="ae58f-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="ae58f-114">특성의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ae58f-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae58f-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="ae58f-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="ae58f-116">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="ae58f-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="ae58f-117">값의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ae58f-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="ae58f-118">키</span><span class="sxs-lookup"><span data-stu-id="ae58f-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae58f-119">열</span><span class="sxs-lookup"><span data-stu-id="ae58f-119">Column</span></span></th>
<th><span data-ttu-id="ae58f-120">설명</span><span class="sxs-lookup"><span data-stu-id="ae58f-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae58f-121">Tblenumvalue.valueid</span><span class="sxs-lookup"><span data-stu-id="ae58f-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="ae58f-122">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="ae58f-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae58f-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="ae58f-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="ae58f-124">tblEnumAttribute.attributeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="ae58f-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="ae58f-125">테이블 값</span><span class="sxs-lookup"><span data-stu-id="ae58f-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae58f-126">Tblenumvalue.valueid</span><span class="sxs-lookup"><span data-stu-id="ae58f-126">valueID</span></span></th>
<th><span data-ttu-id="ae58f-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="ae58f-127">attributeID</span></span></th>
<th><span data-ttu-id="ae58f-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="ae58f-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae58f-129">2</span><span class="sxs-lookup"><span data-stu-id="ae58f-129">2</span></span></p></td>
<td><p><span data-ttu-id="ae58f-130">1 </span><span class="sxs-lookup"><span data-stu-id="ae58f-130">1</span></span></p></td>
<td><p><span data-ttu-id="ae58f-131">유지</span><span class="sxs-lookup"><span data-stu-id="ae58f-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae58f-132">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="ae58f-132">3</span></span></p></td>
<td><p><span data-ttu-id="ae58f-133">1 </span><span class="sxs-lookup"><span data-stu-id="ae58f-133">1</span></span></p></td>
<td><p><span data-ttu-id="ae58f-134">scope</span><span class="sxs-lookup"><span data-stu-id="ae58f-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae58f-135">4 </span><span class="sxs-lookup"><span data-stu-id="ae58f-135">4</span></span></p></td>
<td><p><span data-ttu-id="ae58f-136">2</span><span class="sxs-lookup"><span data-stu-id="ae58f-136">2</span></span></p></td>
<td><p><span data-ttu-id="ae58f-137">보통인</span><span class="sxs-lookup"><span data-stu-id="ae58f-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae58f-138">5 </span><span class="sxs-lookup"><span data-stu-id="ae58f-138">5</span></span></p></td>
<td><p><span data-ttu-id="ae58f-139">2</span><span class="sxs-lookup"><span data-stu-id="ae58f-139">2</span></span></p></td>
<td><p><span data-ttu-id="ae58f-140">강당</span><span class="sxs-lookup"><span data-stu-id="ae58f-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae58f-141">6 </span><span class="sxs-lookup"><span data-stu-id="ae58f-141">6</span></span></p></td>
<td><p><span data-ttu-id="ae58f-142">1 </span><span class="sxs-lookup"><span data-stu-id="ae58f-142">1</span></span></p></td>
<td><p><span data-ttu-id="ae58f-143">열린</span><span class="sxs-lookup"><span data-stu-id="ae58f-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="ae58f-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae58f-144">See Also</span></span>


[<span data-ttu-id="ae58f-145">Lync Server 2013의 tblNode</span><span class="sxs-lookup"><span data-stu-id="ae58f-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

