---
title: 'Lync Server 2013: 끝점 테이블'
description: 'Lync Server 2013: 끝점 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 614872eee41b5d8e56da4b96cf5bbe3a4a1cf4d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575624"
---
# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="48e0c-103">Lync Server 2013의 끝점 테이블</span><span class="sxs-lookup"><span data-stu-id="48e0c-103">Endpoint table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48e0c-104">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="48e0c-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="48e0c-105">끝점 테이블은 데이터베이스에 기록 된 세션에 참여 한 끝점에 대 한 정보를 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="48e0c-105">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="48e0c-106">테이블의 각 레코드는 하나의 끝점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="48e0c-106">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48e0c-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="48e0c-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="48e0c-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="48e0c-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="48e0c-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="48e0c-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="48e0c-110"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="48e0c-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48e0c-111"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="48e0c-111"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="48e0c-112">int</span><span class="sxs-lookup"><span data-stu-id="48e0c-112">int</span></span></p></td>
<td><p><span data-ttu-id="48e0c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="48e0c-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="48e0c-114">이 끝점을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="48e0c-114">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48e0c-115"><strong>이름</strong></span><span class="sxs-lookup"><span data-stu-id="48e0c-115"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="48e0c-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="48e0c-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="48e0c-117">고유한</span><span class="sxs-lookup"><span data-stu-id="48e0c-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="48e0c-118">끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="48e0c-118">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48e0c-119"><strong>르</strong></span><span class="sxs-lookup"><span data-stu-id="48e0c-119"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="48e0c-120">name</span><span class="sxs-lookup"><span data-stu-id="48e0c-120">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="48e0c-121">끝점의 OS (운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="48e0c-121">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48e0c-122"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="48e0c-122"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="48e0c-123">name</span><span class="sxs-lookup"><span data-stu-id="48e0c-123">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48e0c-124">끝점의 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="48e0c-124">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48e0c-125"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="48e0c-125"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="48e0c-126">smallint</span><span class="sxs-lookup"><span data-stu-id="48e0c-126">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48e0c-127">끝점의 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="48e0c-127">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48e0c-128"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="48e0c-128"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="48e0c-129">int</span><span class="sxs-lookup"><span data-stu-id="48e0c-129">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48e0c-130">끝점의 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="48e0c-130">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48e0c-131"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="48e0c-131"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="48e0c-132">tinyint</span><span class="sxs-lookup"><span data-stu-id="48e0c-132">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="48e0c-133">시스템이 가상화 된 환경에서 실행 되 고 있는지를 나타내는 비트 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="48e0c-133">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="48e0c-134">에이 – 없음</span><span class="sxs-lookup"><span data-stu-id="48e0c-134">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="48e0c-135">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="48e0c-135">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="48e0c-136">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="48e0c-136">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="48e0c-137">0x0004-가상 PC</span><span class="sxs-lookup"><span data-stu-id="48e0c-137">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="48e0c-138">0x0008-Xen PC</span><span class="sxs-lookup"><span data-stu-id="48e0c-138">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

