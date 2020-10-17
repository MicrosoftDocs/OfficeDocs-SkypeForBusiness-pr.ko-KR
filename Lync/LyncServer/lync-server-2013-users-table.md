---
title: 'Lync Server 2013: Users 테이블'
description: 'Lync Server 2013: Users 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Users table
ms:assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412791(v=OCS.15)
ms:contentKeyID: 48185032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b1418e162a04e46ee0dfeca082aa66b0665fc77
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548634"
---
# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="f2308-103">Lync Server 2013의 Users 테이블</span><span class="sxs-lookup"><span data-stu-id="f2308-103">Users table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2308-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f2308-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f2308-105">Users 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="f2308-105">The Users table is a supporting table.</span></span> <span data-ttu-id="f2308-106">테이블의 각 레코드에는 데이터베이스의 레코드를 포함 하는 통화 또는 세션과 관련 된 한 사용자에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2308-106">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2308-107">열</span><span class="sxs-lookup"><span data-stu-id="f2308-107">Column</span></span></th>
<th><span data-ttu-id="f2308-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f2308-108">Data Type</span></span></th>
<th><span data-ttu-id="f2308-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="f2308-109">Key/Index</span></span></th>
<th><span data-ttu-id="f2308-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="f2308-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2308-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="f2308-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="f2308-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f2308-112">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2308-113">내부 사용에 대 한 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="f2308-113">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2308-114"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="f2308-114"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2308-115">int</span><span class="sxs-lookup"><span data-stu-id="f2308-115">int</span></span></p></td>
<td><p><span data-ttu-id="f2308-116">Primary</span><span class="sxs-lookup"><span data-stu-id="f2308-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="f2308-117">이 사용자를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="f2308-117">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2308-118"><strong>변수와 useruri</strong></span><span class="sxs-lookup"><span data-stu-id="f2308-118"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f2308-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f2308-119">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f2308-120">사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="f2308-120">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2308-121"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="f2308-121"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2308-122">int</span><span class="sxs-lookup"><span data-stu-id="f2308-122">int</span></span></p></td>
<td><p><span data-ttu-id="f2308-123">외부</span><span class="sxs-lookup"><span data-stu-id="f2308-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2308-124">이 사용자의 테 넌 트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f2308-124">This user’s Tenant ID.</span></span> <span data-ttu-id="f2308-125">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f2308-125">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2308-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="f2308-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="f2308-127">int</span><span class="sxs-lookup"><span data-stu-id="f2308-127">int</span></span></p></td>
<td><p><span data-ttu-id="f2308-128">외부</span><span class="sxs-lookup"><span data-stu-id="f2308-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f2308-129">이 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="f2308-129">This user’s URI type.</span></span> <span data-ttu-id="f2308-130">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f2308-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

