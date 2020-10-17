---
title: 'Lync Server 2013: User 테이블'
description: 'Lync Server 2013: User 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15d1ac08a229f4afea35a2727ef1105a5f24b826
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558904"
---
# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="fa80e-103">Lync Server 2013의 User 테이블</span><span class="sxs-lookup"><span data-stu-id="fa80e-103">User table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa80e-104">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fa80e-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fa80e-105">사용자 테이블은 데이터베이스에 기록 된 세션에 참여 한 다양 한 사용자의 목록을 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="fa80e-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="fa80e-106">테이블의 각 레코드는 한 명의 사용자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fa80e-106">Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa80e-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="fa80e-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="fa80e-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="fa80e-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="fa80e-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="fa80e-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="fa80e-110"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="fa80e-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa80e-111"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="fa80e-111"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="fa80e-112">int</span><span class="sxs-lookup"><span data-stu-id="fa80e-112">int</span></span></p></td>
<td><p><span data-ttu-id="fa80e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="fa80e-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="fa80e-114">이 사용자를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="fa80e-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa80e-115"><strong>SYSTEM.URI</strong></span><span class="sxs-lookup"><span data-stu-id="fa80e-115"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="fa80e-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="fa80e-116">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="fa80e-117">고유한</span><span class="sxs-lookup"><span data-stu-id="fa80e-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="fa80e-118">URI 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fa80e-118">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa80e-119"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="fa80e-119"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="fa80e-120">int</span><span class="sxs-lookup"><span data-stu-id="fa80e-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa80e-121">1은 알 수 없는 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="fa80e-121">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="fa80e-122">2는 사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="fa80e-122">2 is user URI.</span></span></p>
<p><span data-ttu-id="fa80e-123">4는 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="fa80e-123">4 is conference URI.</span></span></p>
<p><span data-ttu-id="fa80e-124">8은 전화 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="fa80e-124">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa80e-125"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="fa80e-125"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="fa80e-126">int</span><span class="sxs-lookup"><span data-stu-id="fa80e-126">int</span></span></p></td>
<td><p><span data-ttu-id="fa80e-127">외부</span><span class="sxs-lookup"><span data-stu-id="fa80e-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fa80e-128">테 넌 트 테이블에서 참조 되는 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="fa80e-128">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa80e-129"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="fa80e-129"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fa80e-130">datetime</span><span class="sxs-lookup"><span data-stu-id="fa80e-130">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa80e-131">사용자가 오디오를 잘못 호출한 경우의 최신 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="fa80e-131">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa80e-132"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="fa80e-132"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="fa80e-133">datetime</span><span class="sxs-lookup"><span data-stu-id="fa80e-133">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fa80e-134">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa80e-134">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

