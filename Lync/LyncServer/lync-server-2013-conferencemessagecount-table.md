---
title: 'Lync Server 2013: ConferenceMessageCount 테이블'
description: 'Lync Server 2013: ConferenceMessageCount 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount table
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398590(v=OCS.15)
ms:contentKeyID: 48184570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 271b654c09ab1aef194eb613e660de208aea1534
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561624"
---
# <a name="conferencemessagecount-table-in-lync-server-2013"></a><span data-ttu-id="05923-103">Lync Server 2013의 ConferenceMessageCount 테이블</span><span class="sxs-lookup"><span data-stu-id="05923-103">ConferenceMessageCount table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05923-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="05923-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="05923-105">이 테이블의 각 레코드는 하나의 IM 회의에 있는 한 명의 사용자를 나타내며 해당 사용자가 보낸 메시지 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="05923-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="05923-106">각 회의는이 테이블의 여러 레코드로 표시 됩니다. 각 사용자에 대 한 레코드 1 개</span><span class="sxs-lookup"><span data-stu-id="05923-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05923-107">열</span><span class="sxs-lookup"><span data-stu-id="05923-107">Column</span></span></th>
<th><span data-ttu-id="05923-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="05923-108">Data Type</span></span></th>
<th><span data-ttu-id="05923-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="05923-109">Key/Index</span></span></th>
<th><span data-ttu-id="05923-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="05923-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05923-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="05923-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05923-112">datetime</span><span class="sxs-lookup"><span data-stu-id="05923-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="05923-113">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="05923-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="05923-114">전화 회의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="05923-114">Time of conference instance.</span></span> <span data-ttu-id="05923-115">이를 <strong>Sessionidseq</strong> 와 함께 사용 하 여 전화 회의 인스턴스를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="05923-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="05923-116">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05923-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05923-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="05923-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="05923-118">int</span><span class="sxs-lookup"><span data-stu-id="05923-118">int</span></span></p></td>
<td><p><span data-ttu-id="05923-119">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="05923-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="05923-120">전화 회의 인스턴스를 식별 하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="05923-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="05923-121"><strong>Sessionidtime</strong> 과 함께 회의 인스턴스를 고유 하 게 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05923-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="05923-122">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="05923-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05923-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="05923-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="05923-124">int</span><span class="sxs-lookup"><span data-stu-id="05923-124">int</span></span></p></td>
<td><p><span data-ttu-id="05923-125">외부</span><span class="sxs-lookup"><span data-stu-id="05923-125">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05923-126">이 사용자를 식별 하는 고유한 번호로, <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05923-126">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05923-127"><strong>MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="05923-127"><strong>MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="05923-128">smallint</span><span class="sxs-lookup"><span data-stu-id="05923-128">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="05923-129">이 회의 중에이 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="05923-129">The number of messages sent by this user during this conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

