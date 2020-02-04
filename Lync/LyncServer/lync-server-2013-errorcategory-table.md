---
title: 'Lync Server 2013: ErrorCategory 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5da1da6f54fa9099cc455040a71fb11c4fe070e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="92ee7-102">Lync Server 2013의 ErrorCategory 테이블</span><span class="sxs-lookup"><span data-stu-id="92ee7-102">ErrorCategory table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92ee7-103">_**마지막으로 수정한 주제:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="92ee7-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="92ee7-104">ErrorCategory 테이블에는 각 Microsoft Lync Server 2013 진단 분류에 대 한 친근 한 이름이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92ee7-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="92ee7-105">기본적으로 Lync Server 2013는 다음과 같은 분류를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="92ee7-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="92ee7-106">0--성공</span><span class="sxs-lookup"><span data-stu-id="92ee7-106">0 -- Success</span></span>

  - <span data-ttu-id="92ee7-107">1--실패 예상</span><span class="sxs-lookup"><span data-stu-id="92ee7-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="92ee7-108">2-예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="92ee7-108">2 – Unexpected failure</span></span>

<span data-ttu-id="92ee7-109">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="92ee7-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92ee7-110">열</span><span class="sxs-lookup"><span data-stu-id="92ee7-110">Column</span></span></th>
<th><span data-ttu-id="92ee7-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="92ee7-111">Data Type</span></span></th>
<th><span data-ttu-id="92ee7-112">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="92ee7-112">Key/Index</span></span></th>
<th><span data-ttu-id="92ee7-113">세부적인</span><span class="sxs-lookup"><span data-stu-id="92ee7-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92ee7-114"><strong>CategoryId</strong></span><span class="sxs-lookup"><span data-stu-id="92ee7-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="92ee7-115">tinyint</span><span class="sxs-lookup"><span data-stu-id="92ee7-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="92ee7-116">주요한</span><span class="sxs-lookup"><span data-stu-id="92ee7-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="92ee7-117">분류의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="92ee7-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92ee7-118"><strong>이름</strong></span><span class="sxs-lookup"><span data-stu-id="92ee7-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="92ee7-119">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="92ee7-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="92ee7-120">분류에 할당 된 값 및 식별 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="92ee7-120">Value and friendly name assigned to the classification.</span></span> <span data-ttu-id="92ee7-121">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="92ee7-121">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="92ee7-122">0--성공</span><span class="sxs-lookup"><span data-stu-id="92ee7-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="92ee7-123">1--실패 예상</span><span class="sxs-lookup"><span data-stu-id="92ee7-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="92ee7-124">2-예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="92ee7-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

