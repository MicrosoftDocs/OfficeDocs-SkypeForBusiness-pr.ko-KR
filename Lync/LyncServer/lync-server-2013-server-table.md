---
title: 'Lync Server 2013: Server 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 363c07a6ab3be8f5acdf0286a4223f96a8bd3700
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="3ffdd-102">Lync Server 2013의 Server 테이블</span><span class="sxs-lookup"><span data-stu-id="3ffdd-102">Server table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ffdd-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="3ffdd-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="3ffdd-104">서버 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="3ffdd-104">The Server table is a supporting table.</span></span> <span data-ttu-id="3ffdd-105">각 레코드는 하나의 서버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3ffdd-105">Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3ffdd-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="3ffdd-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3ffdd-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="3ffdd-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3ffdd-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="3ffdd-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3ffdd-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="3ffdd-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3ffdd-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="3ffdd-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="3ffdd-111">int</span><span class="sxs-lookup"><span data-stu-id="3ffdd-111">int</span></span></p></td>
<td><p><span data-ttu-id="3ffdd-112">주요한</span><span class="sxs-lookup"><span data-stu-id="3ffdd-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="3ffdd-113">서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="3ffdd-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ffdd-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="3ffdd-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="3ffdd-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3ffdd-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3ffdd-116">색인</span><span class="sxs-lookup"><span data-stu-id="3ffdd-116">index</span></span></p></td>
<td><p><span data-ttu-id="3ffdd-117">MAC 주소 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3ffdd-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ffdd-118"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="3ffdd-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="3ffdd-119">int</span><span class="sxs-lookup"><span data-stu-id="3ffdd-119">int</span></span></p></td>
<td><p><span data-ttu-id="3ffdd-120">외부</span><span class="sxs-lookup"><span data-stu-id="3ffdd-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3ffdd-121">1: 중재 서버</span><span class="sxs-lookup"><span data-stu-id="3ffdd-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="3ffdd-122">2: a/V 회의 Server16394: A/v Edge service32769: Gateway</span><span class="sxs-lookup"><span data-stu-id="3ffdd-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3ffdd-123"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="3ffdd-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="3ffdd-124">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="3ffdd-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3ffdd-125">서버가 속한 풀.</span><span class="sxs-lookup"><span data-stu-id="3ffdd-125">Pool the server belongs to.</span></span> <span data-ttu-id="3ffdd-126">A/V 회의 서버에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ffdd-126">Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3ffdd-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="3ffdd-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="3ffdd-128">dmtf</span><span class="sxs-lookup"><span data-stu-id="3ffdd-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3ffdd-129">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ffdd-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

