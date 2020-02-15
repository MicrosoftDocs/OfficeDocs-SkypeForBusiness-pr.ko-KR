---
title: 'Lync Server 2013: UserStatistics 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98c24093f332f568daadfb0cd336f0d5fde3eb35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="fcabb-102">Lync Server 2013의 UserStatistics 테이블</span><span class="sxs-lookup"><span data-stu-id="fcabb-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcabb-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="fcabb-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="fcabb-104">UserStatistics 테이블이 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="fcabb-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="fcabb-105">테이블의 각 레코드에는 개별 사용자의 시스템 사용에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcabb-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="fcabb-106">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fcabb-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcabb-107">열</span><span class="sxs-lookup"><span data-stu-id="fcabb-107">Column</span></span></th>
<th><span data-ttu-id="fcabb-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="fcabb-108">Data Type</span></span></th>
<th><span data-ttu-id="fcabb-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="fcabb-109">Key/Index</span></span></th>
<th><span data-ttu-id="fcabb-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="fcabb-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcabb-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="fcabb-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="fcabb-112">int</span><span class="sxs-lookup"><span data-stu-id="fcabb-112">int</span></span></p></td>
<td><p><span data-ttu-id="fcabb-113">Primary</span><span class="sxs-lookup"><span data-stu-id="fcabb-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="fcabb-114">이 사용자를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="fcabb-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcabb-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="fcabb-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fcabb-116">datetime</span><span class="sxs-lookup"><span data-stu-id="fcabb-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fcabb-117">사용자가 로그인 한 마지막 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fcabb-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcabb-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="fcabb-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fcabb-119">datetime</span><span class="sxs-lookup"><span data-stu-id="fcabb-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fcabb-120">사용자가 회의를 마지막으로 구성한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fcabb-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcabb-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="fcabb-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fcabb-122">datetime</span><span class="sxs-lookup"><span data-stu-id="fcabb-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fcabb-123">마지막으로 사용자에 게 통화 오류가 발생 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fcabb-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcabb-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="fcabb-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fcabb-125">datetime</span><span class="sxs-lookup"><span data-stu-id="fcabb-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fcabb-126">전화 회의 이끌이의 사용자에 게 통화 오류가 발생 한 마지막 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fcabb-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

