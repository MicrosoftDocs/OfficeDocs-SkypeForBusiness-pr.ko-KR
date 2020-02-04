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
ms.openlocfilehash: 2c09c5e911dcd63f50d8b15343075c5b3e05e631
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a><span data-ttu-id="cdde2-102">Lync Server 2013의 tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="cdde2-102">tblEnumValue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdde2-103">_**마지막으로 수정한 주제:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="cdde2-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="cdde2-104">tblEnumValue는 노드 테이블에 사용 되는 특성의 Visibility 및 Behavior 값을 포함 하는 하드 코드 된 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="cdde2-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="cdde2-105">열</span><span class="sxs-lookup"><span data-stu-id="cdde2-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdde2-106">열</span><span class="sxs-lookup"><span data-stu-id="cdde2-106">Column</span></span></th>
<th><span data-ttu-id="cdde2-107">유형</span><span class="sxs-lookup"><span data-stu-id="cdde2-107">Type</span></span></th>
<th><span data-ttu-id="cdde2-108">설명</span><span class="sxs-lookup"><span data-stu-id="cdde2-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdde2-109">고 대 Eid</span><span class="sxs-lookup"><span data-stu-id="cdde2-109">valueID</span></span></p></td>
<td><p><span data-ttu-id="cdde2-110">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="cdde2-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="cdde2-111">값의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="cdde2-111">ID of the value.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdde2-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="cdde2-112">attributeID</span></span></p></td>
<td><p><span data-ttu-id="cdde2-113">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="cdde2-113">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="cdde2-114">특성의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="cdde2-114">ID of the attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdde2-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="cdde2-115">attributeValue</span></span></p></td>
<td><p><span data-ttu-id="cdde2-116">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="cdde2-116">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="cdde2-117">값의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cdde2-117">Name of the value.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="cdde2-118">핵심</span><span class="sxs-lookup"><span data-stu-id="cdde2-118">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdde2-119">열</span><span class="sxs-lookup"><span data-stu-id="cdde2-119">Column</span></span></th>
<th><span data-ttu-id="cdde2-120">설명</span><span class="sxs-lookup"><span data-stu-id="cdde2-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdde2-121">고 대 Eid</span><span class="sxs-lookup"><span data-stu-id="cdde2-121">valueID</span></span></p></td>
<td><p><span data-ttu-id="cdde2-122">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="cdde2-122">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdde2-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="cdde2-123">attributeID</span></span></p></td>
<td><p><span data-ttu-id="cdde2-124">TblEnumAttribute의 조회가 포함 되어 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="cdde2-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="cdde2-125">테이블 값</span><span class="sxs-lookup"><span data-stu-id="cdde2-125">Table Values</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cdde2-126">고 대 Eid</span><span class="sxs-lookup"><span data-stu-id="cdde2-126">valueID</span></span></th>
<th><span data-ttu-id="cdde2-127">attributeID</span><span class="sxs-lookup"><span data-stu-id="cdde2-127">attributeID</span></span></th>
<th><span data-ttu-id="cdde2-128">attributeValue</span><span class="sxs-lookup"><span data-stu-id="cdde2-128">attributeValue</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cdde2-129">2</span><span class="sxs-lookup"><span data-stu-id="cdde2-129">2</span></span></p></td>
<td><p><span data-ttu-id="cdde2-130">1</span><span class="sxs-lookup"><span data-stu-id="cdde2-130">1</span></span></p></td>
<td><p><span data-ttu-id="cdde2-131">개인용</span><span class="sxs-lookup"><span data-stu-id="cdde2-131">private</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdde2-132">3</span><span class="sxs-lookup"><span data-stu-id="cdde2-132">3</span></span></p></td>
<td><p><span data-ttu-id="cdde2-133">1</span><span class="sxs-lookup"><span data-stu-id="cdde2-133">1</span></span></p></td>
<td><p><span data-ttu-id="cdde2-134">범위도</span><span class="sxs-lookup"><span data-stu-id="cdde2-134">scope</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdde2-135">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="cdde2-135">4</span></span></p></td>
<td><p><span data-ttu-id="cdde2-136">2</span><span class="sxs-lookup"><span data-stu-id="cdde2-136">2</span></span></p></td>
<td><p><span data-ttu-id="cdde2-137">크기로</span><span class="sxs-lookup"><span data-stu-id="cdde2-137">normal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cdde2-138">5mb</span><span class="sxs-lookup"><span data-stu-id="cdde2-138">5</span></span></p></td>
<td><p><span data-ttu-id="cdde2-139">2</span><span class="sxs-lookup"><span data-stu-id="cdde2-139">2</span></span></p></td>
<td><p><span data-ttu-id="cdde2-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="cdde2-140">auditorium</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cdde2-141">26</span><span class="sxs-lookup"><span data-stu-id="cdde2-141">6</span></span></p></td>
<td><p><span data-ttu-id="cdde2-142">1</span><span class="sxs-lookup"><span data-stu-id="cdde2-142">1</span></span></p></td>
<td><p><span data-ttu-id="cdde2-143">열면</span><span class="sxs-lookup"><span data-stu-id="cdde2-143">open</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="cdde2-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cdde2-144">See Also</span></span>


[<span data-ttu-id="cdde2-145">Lync Server 2013의 tblNode</span><span class="sxs-lookup"><span data-stu-id="cdde2-145">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

