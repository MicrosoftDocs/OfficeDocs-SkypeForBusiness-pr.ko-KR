---
title: 'Lync Server 2013: 사용자 보기'
description: 'Lync Server 2013: 사용자 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa606887e8050a51f1e5a87656bb74a7cd58bbc3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558914"
---
# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="432b0-103">Lync Server 2013의 사용자 보기</span><span class="sxs-lookup"><span data-stu-id="432b0-103">User view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="432b0-104">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="432b0-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="432b0-105">사용자 보기에는 데이터베이스의 레코드를 포함하는 통화 또는 세션에 포함된 사용자에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="432b0-105">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="432b0-106">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="432b0-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="432b0-107">열</span><span class="sxs-lookup"><span data-stu-id="432b0-107">Column</span></span></th>
<th><span data-ttu-id="432b0-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="432b0-108">Data Type</span></span></th>
<th><span data-ttu-id="432b0-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="432b0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="432b0-110">UserId</span><span class="sxs-lookup"><span data-stu-id="432b0-110">UserId</span></span></p></td>
<td><p><span data-ttu-id="432b0-111">int</span><span class="sxs-lookup"><span data-stu-id="432b0-111">int</span></span></p></td>
<td><p><span data-ttu-id="432b0-112">이 사용자를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="432b0-112">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="432b0-113">변수와 useruri</span><span class="sxs-lookup"><span data-stu-id="432b0-113">UserUri</span></span></p></td>
<td><p><span data-ttu-id="432b0-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="432b0-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="432b0-115">사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="432b0-115">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="432b0-116">TenantKey</span><span class="sxs-lookup"><span data-stu-id="432b0-116">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="432b0-117">고유</span><span class="sxs-lookup"><span data-stu-id="432b0-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="432b0-118">사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="432b0-118">Tenant of user.</span></span> <span data-ttu-id="432b0-119">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="432b0-119">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="432b0-120">UriType</span><span class="sxs-lookup"><span data-stu-id="432b0-120">UriType</span></span></p></td>
<td><p><span data-ttu-id="432b0-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="432b0-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="432b0-122">사용자 URI의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="432b0-122">Type of user URI.</span></span> <span data-ttu-id="432b0-123">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="432b0-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

