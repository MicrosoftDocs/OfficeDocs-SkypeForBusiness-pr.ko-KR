---
title: 'Lync Server 2013: tblEnumAttribute'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48183523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3b015d1148c3c820c27cdbe48e191bd09d2f55e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509355"
---
# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="f62e7-102">Lync Server 2013의 tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="f62e7-102">tblEnumAttribute in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f62e7-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="f62e7-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="f62e7-104">tblEnumAttribute는 Node 테이블에 사용된 Visibility 및 Behavior 특성이 들어 있는 하드코드된 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="f62e7-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="f62e7-105">단</span><span class="sxs-lookup"><span data-stu-id="f62e7-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f62e7-106">열</span><span class="sxs-lookup"><span data-stu-id="f62e7-106">Column</span></span></th>
<th><span data-ttu-id="f62e7-107">유형</span><span class="sxs-lookup"><span data-stu-id="f62e7-107">Type</span></span></th>
<th><span data-ttu-id="f62e7-108">설명</span><span class="sxs-lookup"><span data-stu-id="f62e7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f62e7-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="f62e7-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="f62e7-110">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="f62e7-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="f62e7-111">특성의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f62e7-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f62e7-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="f62e7-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="f62e7-113">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="f62e7-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="f62e7-114">특성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f62e7-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="f62e7-115">키</span><span class="sxs-lookup"><span data-stu-id="f62e7-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f62e7-116">열</span><span class="sxs-lookup"><span data-stu-id="f62e7-116">Column</span></span></th>
<th><span data-ttu-id="f62e7-117">설명</span><span class="sxs-lookup"><span data-stu-id="f62e7-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f62e7-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="f62e7-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="f62e7-119">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="f62e7-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="f62e7-120">테이블 값</span><span class="sxs-lookup"><span data-stu-id="f62e7-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f62e7-121">attributeID</span><span class="sxs-lookup"><span data-stu-id="f62e7-121">attributeID</span></span></th>
<th><span data-ttu-id="f62e7-122">attributeName</span><span class="sxs-lookup"><span data-stu-id="f62e7-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f62e7-123">1 </span><span class="sxs-lookup"><span data-stu-id="f62e7-123">1</span></span></p></td>
<td><p><span data-ttu-id="f62e7-124">가시성.</span><span class="sxs-lookup"><span data-stu-id="f62e7-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f62e7-125">2</span><span class="sxs-lookup"><span data-stu-id="f62e7-125">2</span></span></p></td>
<td><p><span data-ttu-id="f62e7-126">동작과.</span><span class="sxs-lookup"><span data-stu-id="f62e7-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="f62e7-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f62e7-127">See Also</span></span>


[<span data-ttu-id="f62e7-128">Lync Server 2013의 tblNode</span><span class="sxs-lookup"><span data-stu-id="f62e7-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

