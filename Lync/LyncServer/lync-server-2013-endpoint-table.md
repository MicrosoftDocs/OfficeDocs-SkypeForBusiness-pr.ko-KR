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
ms.openlocfilehash: 3cb9430ba8b8c169176d39768491f0122e644d39
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a><span data-ttu-id="ffd0d-102">Lync Server 2013의 끝점 테이블</span><span class="sxs-lookup"><span data-stu-id="ffd0d-102">Endpoint table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffd0d-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ffd0d-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ffd0d-104">끝점 테이블은 데이터베이스에 기록 된 세션에 참여 한 끝점에 대 한 정보를 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="ffd0d-104">The Endpoint table is a supporting table that stores information about the endpoints that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ffd0d-105">테이블의 각 레코드는 하나의 끝점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ffd0d-105">Each record in the table represents one endpoint.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffd0d-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="ffd0d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ffd0d-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="ffd0d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ffd0d-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="ffd0d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ffd0d-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="ffd0d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffd0d-110"><strong>EndpointKey</strong></span><span class="sxs-lookup"><span data-stu-id="ffd0d-110"><strong>EndpointKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ffd0d-111">int</span><span class="sxs-lookup"><span data-stu-id="ffd0d-111">int</span></span></p></td>
<td><p><span data-ttu-id="ffd0d-112">Primary</span><span class="sxs-lookup"><span data-stu-id="ffd0d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ffd0d-113">이 끝점을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ffd0d-113">Unique number identifying this endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffd0d-114"><strong>이름</strong></span><span class="sxs-lookup"><span data-stu-id="ffd0d-114"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="ffd0d-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ffd0d-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ffd0d-116">고유한</span><span class="sxs-lookup"><span data-stu-id="ffd0d-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="ffd0d-117">끝점 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ffd0d-117">Endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffd0d-118"><strong>르</strong></span><span class="sxs-lookup"><span data-stu-id="ffd0d-118"><strong>OS</strong></span></span></p></td>
<td><p><span data-ttu-id="ffd0d-119">name</span><span class="sxs-lookup"><span data-stu-id="ffd0d-119">nvarchar(128)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ffd0d-120">끝점의 OS (운영 체제)입니다.</span><span class="sxs-lookup"><span data-stu-id="ffd0d-120">Operating system (OS) of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffd0d-121"><strong>CPUName</strong></span><span class="sxs-lookup"><span data-stu-id="ffd0d-121"><strong>CPUName</strong></span></span></p></td>
<td><p><span data-ttu-id="ffd0d-122">name</span><span class="sxs-lookup"><span data-stu-id="ffd0d-122">nvarchar(128)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ffd0d-123">끝점의 CPU 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ffd0d-123">CPU name of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffd0d-124"><strong>CPUNumberOfCores</strong></span><span class="sxs-lookup"><span data-stu-id="ffd0d-124"><strong>CPUNumberOfCores</strong></span></span></p></td>
<td><p><span data-ttu-id="ffd0d-125">smallint</span><span class="sxs-lookup"><span data-stu-id="ffd0d-125">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ffd0d-126">끝점의 CPU 코어 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ffd0d-126">Number of CPU cores of the endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffd0d-127"><strong>CPUProcessorSpeed</strong></span><span class="sxs-lookup"><span data-stu-id="ffd0d-127"><strong>CPUProcessorSpeed</strong></span></span></p></td>
<td><p><span data-ttu-id="ffd0d-128">int</span><span class="sxs-lookup"><span data-stu-id="ffd0d-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ffd0d-129">끝점의 CPU 프로세서 속도입니다.</span><span class="sxs-lookup"><span data-stu-id="ffd0d-129">CPU processor speed of the endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffd0d-130"><strong>VirtualizationFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ffd0d-130"><strong>VirtualizationFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ffd0d-131">tinyint</span><span class="sxs-lookup"><span data-stu-id="ffd0d-131">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ffd0d-132">시스템이 가상화 된 환경에서 실행 되 고 있는지를 나타내는 비트 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="ffd0d-132">Bit flag that indicates if the system is running in a virtualized environment:</span></span></p>
<ul>
<li><p><span data-ttu-id="ffd0d-133">에이 – 없음</span><span class="sxs-lookup"><span data-stu-id="ffd0d-133">0x0000 – None</span></span></p></li>
<li><p><span data-ttu-id="ffd0d-134">0x0001 – HyperV</span><span class="sxs-lookup"><span data-stu-id="ffd0d-134">0x0001 – HyperV</span></span></p></li>
<li><p><span data-ttu-id="ffd0d-135">0x0002 – VMWare</span><span class="sxs-lookup"><span data-stu-id="ffd0d-135">0x0002 – VMWare</span></span></p></li>
<li><p><span data-ttu-id="ffd0d-136">0x0004-가상 PC</span><span class="sxs-lookup"><span data-stu-id="ffd0d-136">0x0004 – Virtual PC</span></span></p></li>
<li><p><span data-ttu-id="ffd0d-137">0x0008-Xen PC</span><span class="sxs-lookup"><span data-stu-id="ffd0d-137">0x0008 – Xen PC</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

