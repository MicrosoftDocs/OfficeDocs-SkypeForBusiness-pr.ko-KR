---
title: 'Lync Server 2013: Server 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebfc08cd5a27527d5afebdae8b2fea8335f93dcb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510235"
---
# <a name="server-table-in-lync-server-2013"></a><span data-ttu-id="e5154-102">Lync Server 2013의 Server 테이블</span><span class="sxs-lookup"><span data-stu-id="e5154-102">Server table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5154-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e5154-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e5154-p101">Server 테이블은 지원 테이블입니다. 각 레코드는 하나의 서버를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5154-p101">The Server table is a supporting table. Each record represents one server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5154-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="e5154-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e5154-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="e5154-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e5154-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="e5154-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e5154-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="e5154-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5154-110"><strong>ServerKey</strong></span><span class="sxs-lookup"><span data-stu-id="e5154-110"><strong>ServerKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e5154-111">int</span><span class="sxs-lookup"><span data-stu-id="e5154-111">int</span></span></p></td>
<td><p><span data-ttu-id="e5154-112">Primary</span><span class="sxs-lookup"><span data-stu-id="e5154-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e5154-113">이 서버를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e5154-113">Unique number identifying the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5154-114"><strong>FQDNOrIP</strong></span><span class="sxs-lookup"><span data-stu-id="e5154-114"><strong>FQDNOrIP</strong></span></span></p></td>
<td><p><span data-ttu-id="e5154-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e5154-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5154-116">인덱스</span><span class="sxs-lookup"><span data-stu-id="e5154-116">index</span></span></p></td>
<td><p><span data-ttu-id="e5154-117">MAC 주소 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e5154-117">MAC address string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5154-118"><strong>ServerType</strong></span><span class="sxs-lookup"><span data-stu-id="e5154-118"><strong>ServerType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5154-119">int</span><span class="sxs-lookup"><span data-stu-id="e5154-119">int</span></span></p></td>
<td><p><span data-ttu-id="e5154-120">외부</span><span class="sxs-lookup"><span data-stu-id="e5154-120">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e5154-121">1: 중재 서버</span><span class="sxs-lookup"><span data-stu-id="e5154-121">1: Mediation Server</span></span></p>
<p><span data-ttu-id="e5154-122">2: A/V 회의 서버 16394: A/V 에지 서버 32769: 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="e5154-122">2: A/V Conferencing Server16394: A/V Edge service32769: Gateway</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5154-123"><strong>PoolName</strong></span><span class="sxs-lookup"><span data-stu-id="e5154-123"><strong>PoolName</strong></span></span></p></td>
<td><p><span data-ttu-id="e5154-124">nvarchar (512)</span><span class="sxs-lookup"><span data-stu-id="e5154-124">nvarchar(512)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5154-p102">서버가 속하는 풀입니다. A/V 회의 서버에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5154-p102">Pool the server belongs to. Only applicable for the A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5154-127"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="e5154-127"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="e5154-128">datetime</span><span class="sxs-lookup"><span data-stu-id="e5154-128">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5154-129">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5154-129">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

