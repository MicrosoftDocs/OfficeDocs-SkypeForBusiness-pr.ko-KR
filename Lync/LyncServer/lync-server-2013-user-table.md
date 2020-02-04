---
title: 'Lync Server 2013: User 테이블'
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
ms.openlocfilehash: 8256dec91c93ca6e8f0fd3cfff65280a417324e4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="67896-102">Lync Server 2013의 User 테이블</span><span class="sxs-lookup"><span data-stu-id="67896-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67896-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="67896-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="67896-104">사용자 테이블은 데이터베이스에 기록 된 세션에 참가 한 다양 한 사용자의 목록을 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="67896-104">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="67896-105">테이블의 각 레코드는 한 명의 사용자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="67896-105">Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67896-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="67896-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="67896-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="67896-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="67896-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="67896-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="67896-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="67896-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67896-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="67896-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="67896-111">int</span><span class="sxs-lookup"><span data-stu-id="67896-111">int</span></span></p></td>
<td><p><span data-ttu-id="67896-112">주요한</span><span class="sxs-lookup"><span data-stu-id="67896-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="67896-113">이 사용자를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="67896-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67896-114"><strong>URL</strong></span><span class="sxs-lookup"><span data-stu-id="67896-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="67896-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="67896-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="67896-116">독특한</span><span class="sxs-lookup"><span data-stu-id="67896-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="67896-117">URI 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="67896-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67896-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="67896-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="67896-119">int</span><span class="sxs-lookup"><span data-stu-id="67896-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="67896-120">1은 알 수 없는 URI 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="67896-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="67896-121">2는 사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="67896-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="67896-122">4는 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="67896-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="67896-123">8은 phone URI입니다.</span><span class="sxs-lookup"><span data-stu-id="67896-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67896-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="67896-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="67896-125">int</span><span class="sxs-lookup"><span data-stu-id="67896-125">int</span></span></p></td>
<td><p><span data-ttu-id="67896-126">외부</span><span class="sxs-lookup"><span data-stu-id="67896-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="67896-127">테 넌 트 테이블에서 참조 하는 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="67896-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67896-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="67896-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="67896-129">dmtf</span><span class="sxs-lookup"><span data-stu-id="67896-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="67896-130">사용자가 음성 통화에 좋지 않은 경우의 최신 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="67896-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67896-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="67896-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="67896-132">dmtf</span><span class="sxs-lookup"><span data-stu-id="67896-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="67896-133">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67896-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

