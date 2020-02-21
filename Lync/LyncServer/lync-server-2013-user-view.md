---
title: 'Lync Server 2013: 사용자 보기'
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
ms.openlocfilehash: 12499f63e262d681297b8289231f58262ba75999
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="8c90e-102">Lync Server 2013의 사용자 보기</span><span class="sxs-lookup"><span data-stu-id="8c90e-102">User view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c90e-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8c90e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8c90e-104">사용자 보기에는 데이터베이스의 레코드를 포함하는 통화 또는 세션에 포함된 사용자에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c90e-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="8c90e-105">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8c90e-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c90e-106">열</span><span class="sxs-lookup"><span data-stu-id="8c90e-106">Column</span></span></th>
<th><span data-ttu-id="8c90e-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c90e-107">Data Type</span></span></th>
<th><span data-ttu-id="8c90e-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="8c90e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c90e-109">UserId</span><span class="sxs-lookup"><span data-stu-id="8c90e-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="8c90e-110">int</span><span class="sxs-lookup"><span data-stu-id="8c90e-110">int</span></span></p></td>
<td><p><span data-ttu-id="8c90e-111">이 사용자를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8c90e-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c90e-112">변수와 useruri</span><span class="sxs-lookup"><span data-stu-id="8c90e-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="8c90e-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8c90e-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8c90e-114">사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="8c90e-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c90e-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="8c90e-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="8c90e-116">고유</span><span class="sxs-lookup"><span data-stu-id="8c90e-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="8c90e-117">사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="8c90e-117">Tenant of user.</span></span> <span data-ttu-id="8c90e-118">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8c90e-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c90e-119">UriType</span><span class="sxs-lookup"><span data-stu-id="8c90e-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="8c90e-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8c90e-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8c90e-121">사용자 URI의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="8c90e-121">Type of user URI.</span></span> <span data-ttu-id="8c90e-122">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8c90e-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

