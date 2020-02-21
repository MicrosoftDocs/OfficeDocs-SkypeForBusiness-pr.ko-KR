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
ms.openlocfilehash: 3052aa95aa6cd846717aa98c5778531aeee6f7e2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a><span data-ttu-id="175a5-102">Lync Server 2013의 ErrorCategory 테이블</span><span class="sxs-lookup"><span data-stu-id="175a5-102">ErrorCategory table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="175a5-103">_**마지막으로 수정 된 항목:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="175a5-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="175a5-104">ErrorCategory 테이블에는 각 Microsoft Lync Server 2013 진단 분류의 이름이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="175a5-104">The ErrorCategory table contains the friendly name for each Microsoft Lync Server 2013 diagnostic classification.</span></span> <span data-ttu-id="175a5-105">기본적으로 Lync Server 2013에서는 다음과 같은 분류를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="175a5-105">By default, Lync Server 2013 uses the following classifications:</span></span>

  - <span data-ttu-id="175a5-106">0 -- 성공</span><span class="sxs-lookup"><span data-stu-id="175a5-106">0 -- Success</span></span>

  - <span data-ttu-id="175a5-107">1--예상 오류</span><span class="sxs-lookup"><span data-stu-id="175a5-107">1 -- Expected failure</span></span>

  - <span data-ttu-id="175a5-108">2 -- 예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="175a5-108">2 – Unexpected failure</span></span>

<span data-ttu-id="175a5-109">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="175a5-109">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="175a5-110">열</span><span class="sxs-lookup"><span data-stu-id="175a5-110">Column</span></span></th>
<th><span data-ttu-id="175a5-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="175a5-111">Data Type</span></span></th>
<th><span data-ttu-id="175a5-112">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="175a5-112">Key/Index</span></span></th>
<th><span data-ttu-id="175a5-113">세부 정보</span><span class="sxs-lookup"><span data-stu-id="175a5-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="175a5-114"><strong>CategoryId</strong></span><span class="sxs-lookup"><span data-stu-id="175a5-114"><strong>CategoryId</strong></span></span></p></td>
<td><p><span data-ttu-id="175a5-115">tinyint</span><span class="sxs-lookup"><span data-stu-id="175a5-115">tinyint</span></span></p></td>
<td><p><span data-ttu-id="175a5-116">Primary</span><span class="sxs-lookup"><span data-stu-id="175a5-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="175a5-117">분류의 고유한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="175a5-117">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="175a5-118"><strong>이름</strong></span><span class="sxs-lookup"><span data-stu-id="175a5-118"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="175a5-119">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="175a5-119">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="175a5-p102">분류에 할당된 값과 이름입니다. 허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="175a5-p102">Value and friendly name assigned to the classification. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="175a5-122">0 -- 성공</span><span class="sxs-lookup"><span data-stu-id="175a5-122">0 -- Success</span></span></p></li>
<li><p><span data-ttu-id="175a5-123">1--예상 오류</span><span class="sxs-lookup"><span data-stu-id="175a5-123">1 -- Expected failure</span></span></p></li>
<li><p><span data-ttu-id="175a5-124">2 -- 예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="175a5-124">2 – Unexpected failure</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

