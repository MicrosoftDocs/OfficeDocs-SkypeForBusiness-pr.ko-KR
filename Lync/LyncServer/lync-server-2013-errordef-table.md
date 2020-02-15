---
title: 'Lync Server 2013: ErrorDef 테이블'
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
ms.openlocfilehash: c490bc9b5058af75704ec3d10c3535581c56df2b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="c8369-102">Lync Server 2013의 ErrorDef 테이블</span><span class="sxs-lookup"><span data-stu-id="c8369-102">ErrorDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8369-103">_**마지막으로 수정 된 항목:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="c8369-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="c8369-104">ErrorDef 테이블에는 발생할 수 있는 각 유형의 오류에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8369-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="c8369-105">각 레코드는 오류 유형 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="c8369-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8369-106">열</span><span class="sxs-lookup"><span data-stu-id="c8369-106">Column</span></span></th>
<th><span data-ttu-id="c8369-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c8369-107">Data Type</span></span></th>
<th><span data-ttu-id="c8369-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="c8369-108">Key/Index</span></span></th>
<th><span data-ttu-id="c8369-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="c8369-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8369-110"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="c8369-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="c8369-111">int</span><span class="sxs-lookup"><span data-stu-id="c8369-111">int</span></span></p></td>
<td><p><span data-ttu-id="c8369-112">Primary</span><span class="sxs-lookup"><span data-stu-id="c8369-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c8369-113">이 오류 유형을 식별 하는 고유 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="c8369-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8369-114"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="c8369-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="c8369-115">int</span><span class="sxs-lookup"><span data-stu-id="c8369-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c8369-116">이 오류와 연결 된 표준 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c8369-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8369-117"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="c8369-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="c8369-118">int</span><span class="sxs-lookup"><span data-stu-id="c8369-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c8369-119">Microsoft 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c8369-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8369-120"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="c8369-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="c8369-121">임계값</span><span class="sxs-lookup"><span data-stu-id="c8369-121">Int</span></span></p></td>
<td><p><span data-ttu-id="c8369-122">외부</span><span class="sxs-lookup"><span data-stu-id="c8369-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c8369-123">통화의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c8369-123">Type of the call.</span></span> <span data-ttu-id="c8369-124">자세한 내용은 <a href="lync-server-2013-calltype-table.md">Lync Server 2013의 Calltype table</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c8369-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8369-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="c8369-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="c8369-126">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="c8369-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c8369-127">실패한 요청 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c8369-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="c8369-128">이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8369-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8369-129"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="c8369-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="c8369-130">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="c8369-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c8369-131">실패한 요청의 콘텐츠 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="c8369-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="c8369-132">이 데이터는 다음을 사용 하 여 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8369-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

