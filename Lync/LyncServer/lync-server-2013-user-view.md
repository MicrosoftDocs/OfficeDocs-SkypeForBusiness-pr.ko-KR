---
title: 'Lync Server 2013: 사용자 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User view
ms:assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688100(v=OCS.15)
ms:contentKeyID: 49733699
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21c22bdfbf758545418a821edaba5d8aaf447b87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-view-in-lync-server-2013"></a><span data-ttu-id="8a3ce-102">Lync Server 2013의 사용자 보기</span><span class="sxs-lookup"><span data-stu-id="8a3ce-102">User view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a3ce-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8a3ce-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8a3ce-104">사용자 보기에는 통화와 관련 된 사용자에 대 한 정보 또는 데이터베이스에 레코드가 있는 세션이 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ce-104">The User view stores information about users who have been involved in calls or sessions that have records in the database.</span></span> <span data-ttu-id="8a3ce-105">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ce-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a3ce-106">열</span><span class="sxs-lookup"><span data-stu-id="8a3ce-106">Column</span></span></th>
<th><span data-ttu-id="8a3ce-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8a3ce-107">Data Type</span></span></th>
<th><span data-ttu-id="8a3ce-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="8a3ce-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a3ce-109">UserId</span><span class="sxs-lookup"><span data-stu-id="8a3ce-109">UserId</span></span></p></td>
<td><p><span data-ttu-id="8a3ce-110">int</span><span class="sxs-lookup"><span data-stu-id="8a3ce-110">int</span></span></p></td>
<td><p><span data-ttu-id="8a3ce-111">이 사용자를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ce-111">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a3ce-112">UserUri</span><span class="sxs-lookup"><span data-stu-id="8a3ce-112">UserUri</span></span></p></td>
<td><p><span data-ttu-id="8a3ce-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="8a3ce-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="8a3ce-114">사용자의 Uri입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ce-114">Uri of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8a3ce-115">TenantKey</span><span class="sxs-lookup"><span data-stu-id="8a3ce-115">TenantKey</span></span></p></td>
<td><p><span data-ttu-id="8a3ce-116">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="8a3ce-116">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="8a3ce-117">사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ce-117">Tenant of user.</span></span> <span data-ttu-id="8a3ce-118">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a3ce-118">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a3ce-119">UriType</span><span class="sxs-lookup"><span data-stu-id="8a3ce-119">UriType</span></span></p></td>
<td><p><span data-ttu-id="8a3ce-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8a3ce-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8a3ce-121">사용자 URI의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="8a3ce-121">Type of user URI.</span></span> <span data-ttu-id="8a3ce-122">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a3ce-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

