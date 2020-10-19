---
title: 'Lync Server 2013: UriTypes 테이블'
description: 'Lync Server 2013: UriTypes 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UriTypes table
ms:assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398587(v=OCS.15)
ms:contentKeyID: 48184553
ms.date: 06/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97a63173b7ada258e7da22591b28a6a0410e666a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569894"
---
# <a name="uritypes-table-in-lync-server-2013"></a><span data-ttu-id="4ce43-103">Lync Server 2013의 UriTypes 테이블</span><span class="sxs-lookup"><span data-stu-id="4ce43-103">UriTypes table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ce43-104">_**마지막으로 수정 된 항목:** 2015-06-16_</span><span class="sxs-lookup"><span data-stu-id="4ce43-104">_**Topic Last Modified:** 2015-06-16_</span></span>

<span data-ttu-id="4ce43-105">UriTypes 테이블에는 Microsoft Lync Server 2013에서 모니터링 되는 서로 다른 URI (Uniform resource identifier) 유형이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce43-105">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4ce43-106">열</span><span class="sxs-lookup"><span data-stu-id="4ce43-106">Column</span></span></th>
<th><span data-ttu-id="4ce43-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4ce43-107">Data Type</span></span></th>
<th><span data-ttu-id="4ce43-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="4ce43-108">Key/Index</span></span></th>
<th><span data-ttu-id="4ce43-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="4ce43-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4ce43-110"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="4ce43-110"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="4ce43-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="4ce43-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4ce43-112">Primary</span><span class="sxs-lookup"><span data-stu-id="4ce43-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4ce43-113">URI 유형에 지정된 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4ce43-113">Unique identifier assigned to a URI type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4ce43-114"><strong>UriType</strong></span><span class="sxs-lookup"><span data-stu-id="4ce43-114"><strong>UriType</strong></span></span></p></td>
<td><p><span data-ttu-id="4ce43-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4ce43-115">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4ce43-p101">다른 URI 유형에 대한 설명입니다. 허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4ce43-p101">Descriptions of the different URI types. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="4ce43-118">1-전화 Uri</span><span class="sxs-lookup"><span data-stu-id="4ce43-118">1 – Phone Uri</span></span></p></li>
<li><p><span data-ttu-id="4ce43-119">0 – 사용자 Uri</span><span class="sxs-lookup"><span data-stu-id="4ce43-119">0 – User Uri</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

