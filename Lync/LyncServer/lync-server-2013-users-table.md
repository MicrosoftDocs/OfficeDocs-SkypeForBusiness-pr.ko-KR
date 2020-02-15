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
ms.openlocfilehash: 67663afbd9e5b61b1b24478e003db91c5be511e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-table-in-lync-server-2013"></a><span data-ttu-id="7e25f-102">Lync Server 2013의 Users 테이블</span><span class="sxs-lookup"><span data-stu-id="7e25f-102">Users table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e25f-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="7e25f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="7e25f-104">Users 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="7e25f-104">The Users table is a supporting table.</span></span> <span data-ttu-id="7e25f-105">테이블의 각 레코드에는 데이터베이스의 레코드를 포함 하는 통화 또는 세션과 관련 된 한 사용자에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e25f-105">Each record in the table stores information about one user involved in calls or sessions that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7e25f-106">열</span><span class="sxs-lookup"><span data-stu-id="7e25f-106">Column</span></span></th>
<th><span data-ttu-id="7e25f-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="7e25f-107">Data Type</span></span></th>
<th><span data-ttu-id="7e25f-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="7e25f-108">Key/Index</span></span></th>
<th><span data-ttu-id="7e25f-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="7e25f-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e25f-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="7e25f-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="7e25f-111">datetime</span><span class="sxs-lookup"><span data-stu-id="7e25f-111">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7e25f-112">내부 사용에 대 한 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="7e25f-112">Time stamp for internal use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e25f-113"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="7e25f-113"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="7e25f-114">int</span><span class="sxs-lookup"><span data-stu-id="7e25f-114">int</span></span></p></td>
<td><p><span data-ttu-id="7e25f-115">Primary</span><span class="sxs-lookup"><span data-stu-id="7e25f-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="7e25f-116">이 사용자를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7e25f-116">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e25f-117"><strong>변수와 useruri</strong></span><span class="sxs-lookup"><span data-stu-id="7e25f-117"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="7e25f-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="7e25f-118">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7e25f-119">사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="7e25f-119">User URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7e25f-120"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="7e25f-120"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="7e25f-121">int</span><span class="sxs-lookup"><span data-stu-id="7e25f-121">int</span></span></p></td>
<td><p><span data-ttu-id="7e25f-122">외부</span><span class="sxs-lookup"><span data-stu-id="7e25f-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7e25f-123">이 사용자의 테 넌 트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7e25f-123">This user’s Tenant ID.</span></span> <span data-ttu-id="7e25f-124">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e25f-124">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7e25f-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="7e25f-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="7e25f-126">int</span><span class="sxs-lookup"><span data-stu-id="7e25f-126">int</span></span></p></td>
<td><p><span data-ttu-id="7e25f-127">외부</span><span class="sxs-lookup"><span data-stu-id="7e25f-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7e25f-128">이 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="7e25f-128">This user’s URI type.</span></span> <span data-ttu-id="7e25f-129">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e25f-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

