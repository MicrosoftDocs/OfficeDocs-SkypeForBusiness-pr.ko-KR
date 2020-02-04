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
ms.openlocfilehash: 55a6ab9a8bf50639267824c8330701ee74cb3f5a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a><span data-ttu-id="14509-102">Lync Server 2013의 ErrorDef 테이블</span><span class="sxs-lookup"><span data-stu-id="14509-102">ErrorDef table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14509-103">_**마지막으로 수정한 주제:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="14509-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="14509-104">ErrorDef 테이블에는 발생할 수 있는 각 유형의 오류에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14509-104">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="14509-105">각 레코드는 오류 유형 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="14509-105">Each record is one type of error.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="14509-106">열</span><span class="sxs-lookup"><span data-stu-id="14509-106">Column</span></span></th>
<th><span data-ttu-id="14509-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="14509-107">Data Type</span></span></th>
<th><span data-ttu-id="14509-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="14509-108">Key/Index</span></span></th>
<th><span data-ttu-id="14509-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="14509-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14509-110"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="14509-110"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="14509-111">int</span><span class="sxs-lookup"><span data-stu-id="14509-111">int</span></span></p></td>
<td><p><span data-ttu-id="14509-112">주요한</span><span class="sxs-lookup"><span data-stu-id="14509-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="14509-113">이 유형의 오류를 식별 하는 고유 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="14509-113">Unique ID number identifying this type of error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14509-114"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="14509-114"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="14509-115">int</span><span class="sxs-lookup"><span data-stu-id="14509-115">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="14509-116">이 오류와 연결 된 표준 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="14509-116">Standard SIP response code associated with this error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14509-117"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="14509-117"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="14509-118">int</span><span class="sxs-lookup"><span data-stu-id="14509-118">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="14509-119">Microsoft 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="14509-119">Microsoft Diagnostic ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14509-120"><strong>CallTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="14509-120"><strong>CallTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="14509-121">Int</span><span class="sxs-lookup"><span data-stu-id="14509-121">Int</span></span></p></td>
<td><p><span data-ttu-id="14509-122">외부</span><span class="sxs-lookup"><span data-stu-id="14509-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="14509-123">통화의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="14509-123">Type of the call.</span></span> <span data-ttu-id="14509-124">자세한 내용은 <a href="lync-server-2013-calltype-table.md">Lync Server 2013의 Calltype 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="14509-124">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="14509-125"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="14509-125"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="14509-126">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="14509-126">varbinary(33)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="14509-127">실패 한 요청의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="14509-127">Type of request that failed.</span></span></p>
<p><span data-ttu-id="14509-128">이 구문을 사용 하 여이 데이터를 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14509-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="14509-129"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="14509-129"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="14509-130">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="14509-130">varbinary(257)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="14509-131">실패 한 요청의 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="14509-131">Content type of the request that failed.</span></span></p>
<p><span data-ttu-id="14509-132">이 데이터는이 syntaxt를 사용 하 여 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14509-132">This data can be converted to text format by using this syntaxt:</span></span></p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

