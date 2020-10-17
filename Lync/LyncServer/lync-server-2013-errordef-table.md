---
title: 'Lync Server 2013: ErrorDef 테이블'
description: 'Lync Server 2013: ErrorDef 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58980a671b54007012bbbf6780e24c162aebe00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542754"
---
# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="60671-103">Lync Server 2013의 ErrorDef 테이블</span><span class="sxs-lookup"><span data-stu-id="60671-103">ErrorDef table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60671-104">_**마지막으로 수정 된 항목:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="60671-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="60671-105">ErrorDef 테이블에는 발생할 수 있는 각 유형의 오류에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60671-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="60671-106">각 레코드는 오류 유형 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="60671-106">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="60671-107">열</span><span class="sxs-lookup"><span data-stu-id="60671-107">Column</span></span></th>
<th><span data-ttu-id="60671-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="60671-108">Data Type</span></span></th>
<th><span data-ttu-id="60671-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="60671-109">Key/Index</span></span></th>
<th><span data-ttu-id="60671-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="60671-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="60671-111"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="60671-111"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="60671-112">int</span><span class="sxs-lookup"><span data-stu-id="60671-112">int</span></span></p></td>
<td><p><span data-ttu-id="60671-113">Primary</span><span class="sxs-lookup"><span data-stu-id="60671-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="60671-114">이 오류 유형을 식별 하는 고유 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="60671-114">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60671-115"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="60671-115"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="60671-116">int</span><span class="sxs-lookup"><span data-stu-id="60671-116">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="60671-117">이 오류와 연결 된 표준 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="60671-117">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60671-118"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="60671-118"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="60671-119">int</span><span class="sxs-lookup"><span data-stu-id="60671-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="60671-120">Microsoft 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="60671-120">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60671-121"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="60671-121"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="60671-122">임계값</span><span class="sxs-lookup"><span data-stu-id="60671-122">Int</span></span></p></td>
<td><p><span data-ttu-id="60671-123">외부</span><span class="sxs-lookup"><span data-stu-id="60671-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="60671-124">통화의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="60671-124">Type of the call.</span></span> <span data-ttu-id="60671-125">자세한 내용은 <a href="lync-server-2013-calltype-table.md">Lync Server 2013의 Calltype table</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="60671-125">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="60671-126"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="60671-126"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="60671-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="60671-127">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="60671-128">실패한 요청 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="60671-128">Type of request that failed.</span></span></p>
<p><span data-ttu-id="60671-129">이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60671-129">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="60671-130"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="60671-130"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="60671-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="60671-131">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="60671-132">실패한 요청의 콘텐츠 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="60671-132">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="60671-133">이 데이터는 다음을 사용 하 여 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60671-133">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

