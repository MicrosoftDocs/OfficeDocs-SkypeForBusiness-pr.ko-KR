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
ms.openlocfilehash: 7609747848e1943a08eff2fa77b87f0168710f81
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="5de15-102">Lync Server 2013의 UserStatistics 테이블</span><span class="sxs-lookup"><span data-stu-id="5de15-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5de15-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5de15-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5de15-104">UserStatistics 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="5de15-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="5de15-105">표의 각 레코드에는 시스템의 개별 사용자 사용에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5de15-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="5de15-106">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5de15-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5de15-107">열</span><span class="sxs-lookup"><span data-stu-id="5de15-107">Column</span></span></th>
<th><span data-ttu-id="5de15-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5de15-108">Data Type</span></span></th>
<th><span data-ttu-id="5de15-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="5de15-109">Key/Index</span></span></th>
<th><span data-ttu-id="5de15-110">세부적인</span><span class="sxs-lookup"><span data-stu-id="5de15-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5de15-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="5de15-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="5de15-112">int</span><span class="sxs-lookup"><span data-stu-id="5de15-112">int</span></span></p></td>
<td><p><span data-ttu-id="5de15-113">주요한</span><span class="sxs-lookup"><span data-stu-id="5de15-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="5de15-114">이 사용자를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5de15-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5de15-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="5de15-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5de15-116">dmtf</span><span class="sxs-lookup"><span data-stu-id="5de15-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5de15-117">사용자가 마지막으로 로그인 한 시간</span><span class="sxs-lookup"><span data-stu-id="5de15-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5de15-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="5de15-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5de15-119">dmtf</span><span class="sxs-lookup"><span data-stu-id="5de15-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5de15-120">사용자가 회의를 마지막으로 구성한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="5de15-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5de15-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="5de15-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5de15-122">dmtf</span><span class="sxs-lookup"><span data-stu-id="5de15-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5de15-123">마지막으로 사용자에 게 전화 실패가 발생 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="5de15-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5de15-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="5de15-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5de15-125">dmtf</span><span class="sxs-lookup"><span data-stu-id="5de15-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5de15-126">마지막으로 사용자에 게 컨퍼런스 이끌이로 인해 전화 실패가 발생 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="5de15-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

