---
title: 'Lync Server 2013: tblEnumAttribute'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblEnumAttribute
ms:assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558617(v=OCS.15)
ms:contentKeyID: 48183523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2662f5d0ea9b55f8e3f5320b2e385157bef8bce9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumattribute-in-lync-server-2013"></a><span data-ttu-id="fe990-102">Lync Server 2013의 tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="fe990-102">tblEnumAttribute in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe990-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="fe990-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="fe990-104">tblEnumAttribute는 노드 테이블에 사용 되는 Visibility 및 Behavior 특성을 포함 하는 하드 코드 된 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="fe990-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>

### <a name="columns"></a><span data-ttu-id="fe990-105">열</span><span class="sxs-lookup"><span data-stu-id="fe990-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe990-106">열</span><span class="sxs-lookup"><span data-stu-id="fe990-106">Column</span></span></th>
<th><span data-ttu-id="fe990-107">유형</span><span class="sxs-lookup"><span data-stu-id="fe990-107">Type</span></span></th>
<th><span data-ttu-id="fe990-108">설명</span><span class="sxs-lookup"><span data-stu-id="fe990-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe990-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="fe990-109">attributeID</span></span></p></td>
<td><p><span data-ttu-id="fe990-110">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="fe990-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="fe990-111">특성의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fe990-111">ID of the attribute.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe990-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="fe990-112">attributeName</span></span></p></td>
<td><p><span data-ttu-id="fe990-113">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="fe990-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="fe990-114">특성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fe990-114">Name of the attribute.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="fe990-115">키</span><span class="sxs-lookup"><span data-stu-id="fe990-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe990-116">열</span><span class="sxs-lookup"><span data-stu-id="fe990-116">Column</span></span></th>
<th><span data-ttu-id="fe990-117">설명</span><span class="sxs-lookup"><span data-stu-id="fe990-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe990-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="fe990-118">attributeID</span></span></p></td>
<td><p><span data-ttu-id="fe990-119">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="fe990-119">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a><span data-ttu-id="fe990-120">테이블 값</span><span class="sxs-lookup"><span data-stu-id="fe990-120">Table Values</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe990-121">attributeID</span><span class="sxs-lookup"><span data-stu-id="fe990-121">attributeID</span></span></th>
<th><span data-ttu-id="fe990-122">attributeName</span><span class="sxs-lookup"><span data-stu-id="fe990-122">attributeName</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe990-123">1</span><span class="sxs-lookup"><span data-stu-id="fe990-123">1</span></span></p></td>
<td><p><span data-ttu-id="fe990-124">시도가.</span><span class="sxs-lookup"><span data-stu-id="fe990-124">Visibility.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe990-125">2</span><span class="sxs-lookup"><span data-stu-id="fe990-125">2</span></span></p></td>
<td><p><span data-ttu-id="fe990-126">결과가.</span><span class="sxs-lookup"><span data-stu-id="fe990-126">Behavior.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="fe990-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe990-127">See Also</span></span>


[<span data-ttu-id="fe990-128">Lync Server 2013의 tblNode</span><span class="sxs-lookup"><span data-stu-id="fe990-128">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

