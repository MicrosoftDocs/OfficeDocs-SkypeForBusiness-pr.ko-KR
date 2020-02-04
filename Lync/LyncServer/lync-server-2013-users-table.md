---
title: 'Lync Server 2013: Users 테이블'
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
ms.openlocfilehash: c2be643f8a593af01ee47ad93d3910d44ee86e48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="ddaeb-102">Lync Server 2013의 Users 테이블</span><span class="sxs-lookup"><span data-stu-id="ddaeb-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ddaeb-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ddaeb-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ddaeb-104">사용자 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="ddaeb-104">The Users table is a supporting table.</span></span> <span data-ttu-id="ddaeb-105">테이블의 각 레코드에는 데이터베이스의 레코드를 포함 하는 호출 또는 세션과 관련 된 한 사용자에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ddaeb-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ddaeb-106">열</span><span class="sxs-lookup"><span data-stu-id="ddaeb-106">Column</span></span></th>
<th><span data-ttu-id="ddaeb-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ddaeb-107">Data Type</span></span></th>
<th><span data-ttu-id="ddaeb-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="ddaeb-108">Key/Index</span></span></th>
<th><span data-ttu-id="ddaeb-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="ddaeb-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ddaeb-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="ddaeb-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="ddaeb-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="ddaeb-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ddaeb-112">내부 사용을 위한 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="ddaeb-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddaeb-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="ddaeb-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="ddaeb-114">int</span><span class="sxs-lookup"><span data-stu-id="ddaeb-114">int</span></span></p></td>
<td><p><span data-ttu-id="ddaeb-115">주요한</span><span class="sxs-lookup"><span data-stu-id="ddaeb-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="ddaeb-116">이 사용자를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ddaeb-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddaeb-117"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="ddaeb-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ddaeb-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ddaeb-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="ddaeb-119">사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="ddaeb-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ddaeb-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="ddaeb-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="ddaeb-121">int</span><span class="sxs-lookup"><span data-stu-id="ddaeb-121">int</span></span></p></td>
<td><p><span data-ttu-id="ddaeb-122">외부</span><span class="sxs-lookup"><span data-stu-id="ddaeb-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ddaeb-123">이 사용자의 테 넌 트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ddaeb-123">This user’s Tenant ID.</span></span> <span data-ttu-id="ddaeb-124">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ddaeb-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ddaeb-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="ddaeb-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="ddaeb-126">int</span><span class="sxs-lookup"><span data-stu-id="ddaeb-126">int</span></span></p></td>
<td><p><span data-ttu-id="ddaeb-127">외부</span><span class="sxs-lookup"><span data-stu-id="ddaeb-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ddaeb-128">이 사용자의 URI 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ddaeb-128">This user’s URI type.</span></span> <span data-ttu-id="ddaeb-129">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ddaeb-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

