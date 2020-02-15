---
title: 'Lync Server 2013: 끝점 테이블'
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
ms.openlocfilehash: 201e2ae3b44f59f0edb128f58af6c18e18e51931
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="9b2e2-102">Lync Server 2013의 끝점 테이블</span><span class="sxs-lookup"><span data-stu-id="9b2e2-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b2e2-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="9b2e2-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="9b2e2-104">끝점 테이블은 데이터베이스에 기록 된 세션에 참여 한 끝점에 대 한 정보를 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e2-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="9b2e2-105">테이블의 각 레코드는 하나의 끝점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e2-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b2e2-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="9b2e2-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9b2e2-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="9b2e2-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9b2e2-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="9b2e2-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9b2e2-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="9b2e2-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b2e2-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="9b2e2-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="9b2e2-111">int</span><span class="sxs-lookup"><span data-stu-id="9b2e2-111">int</span></span></p></td>
<td><p><span data-ttu-id="9b2e2-112">Primary</span><span class="sxs-lookup"><span data-stu-id="9b2e2-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="9b2e2-113">이 끝점을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e2-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b2e2-114"><strong>이름</strong></span><span class="sxs-lookup"><span data-stu-id="9b2e2-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="9b2e2-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9b2e2-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9b2e2-116">고유한</span><span class="sxs-lookup"><span data-stu-id="9b2e2-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="9b2e2-117">끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e2-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b2e2-118"><strong>르</strong></span><span class="sxs-lookup"><span data-stu-id="9b2e2-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="9b2e2-119">name</span><span class="sxs-lookup"><span data-stu-id="9b2e2-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9b2e2-120">끝점의 OS (운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e2-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b2e2-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="9b2e2-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="9b2e2-122">name</span><span class="sxs-lookup"><span data-stu-id="9b2e2-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b2e2-123">끝점의 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e2-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b2e2-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="9b2e2-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="9b2e2-125">smallint</span><span class="sxs-lookup"><span data-stu-id="9b2e2-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b2e2-126">끝점의 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e2-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b2e2-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="9b2e2-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="9b2e2-128">int</span><span class="sxs-lookup"><span data-stu-id="9b2e2-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b2e2-129">끝점의 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e2-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b2e2-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9b2e2-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9b2e2-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="9b2e2-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b2e2-132">시스템이 가상화 된 환경에서 실행 되 고 있는지를 나타내는 비트 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="9b2e2-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="9b2e2-133">에이 – 없음</span><span class="sxs-lookup"><span data-stu-id="9b2e2-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="9b2e2-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="9b2e2-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="9b2e2-135">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="9b2e2-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="9b2e2-136">0x0004-가상 PC</span><span class="sxs-lookup"><span data-stu-id="9b2e2-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="9b2e2-137">0x0008-Xen PC</span><span class="sxs-lookup"><span data-stu-id="9b2e2-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

