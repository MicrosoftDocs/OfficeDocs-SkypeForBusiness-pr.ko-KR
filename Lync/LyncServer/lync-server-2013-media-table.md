---
title: 'Lync Server 2013: 미디어 테이블'
description: 'Lync Server 2013: 미디어 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31e30d1f91c59b8e3aa7915fc0d513618d0f709f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558034"
---
# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="6f528-103">Lync Server 2013의 미디어 테이블</span><span class="sxs-lookup"><span data-stu-id="6f528-103">Media table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f528-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6f528-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6f528-p101">각 레코드는 피어-투-피어 세션에 사용된 하나의 미디어 유형을 나타냅니다. 둘 이상의 미디어 유형이 사용된 경우 하나의 세션이 테이블에 여러 레코드로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f528-p101">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6f528-p102">Media 테이블을 사용하여 세션의 미디어 기간을 계산해서는 안 됩니다. 이 테이블에는 세션에 포함된 미디어 교환의 신호 세부 정보가 포함됩니다. 미디어 교환은 INVITE 요청에 의해 수행되며 StartTime은 INVITE가 전송된 시간을 나타냅니다. 미디어는 세션 참가자가 세션을 수락한 후에만 시작되므로 초대 시간이 반드시 미디어 시작 시간인 것은 아닙니다. EndTime은 일반적으로 이 세션의 종료 시간을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="6f528-p102">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f528-111">열</span><span class="sxs-lookup"><span data-stu-id="6f528-111">Column</span></span></th>
<th><span data-ttu-id="6f528-112">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6f528-112">Data Type</span></span></th>
<th><span data-ttu-id="6f528-113">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="6f528-113">Key/Index</span></span></th>
<th><span data-ttu-id="6f528-114">세부 정보</span><span class="sxs-lookup"><span data-stu-id="6f528-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f528-115"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="6f528-115"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6f528-116">datetime</span><span class="sxs-lookup"><span data-stu-id="6f528-116">datetime</span></span></p></td>
<td><p><span data-ttu-id="6f528-117">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="6f528-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6f528-118">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6f528-118">Time of session request.</span></span> <span data-ttu-id="6f528-119"><strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f528-119">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="6f528-120">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6f528-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f528-121"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6f528-121"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6f528-122">int</span><span class="sxs-lookup"><span data-stu-id="6f528-122">int</span></span></p></td>
<td><p><span data-ttu-id="6f528-123">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="6f528-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6f528-124">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="6f528-124">ID number to identify the session.</span></span> <span data-ttu-id="6f528-125"><strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f528-125">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="6f528-126">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6f528-126">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f528-127"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="6f528-127"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="6f528-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="6f528-128">tinyint</span></span></p></td>
<td><p><span data-ttu-id="6f528-129">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="6f528-129">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6f528-130">이 미디어 유형을 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="6f528-130">Unique number identifying this media type.</span></span> <span data-ttu-id="6f528-131">자세한 내용은 <a href="lync-server-2013-medialist-table.md">Lync Server 2013에서 Medialist 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6f528-131">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f528-132"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="6f528-132"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6f528-133">datetime</span><span class="sxs-lookup"><span data-stu-id="6f528-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="6f528-134">Primary</span><span class="sxs-lookup"><span data-stu-id="6f528-134">Primary</span></span></p></td>
<td><p><span data-ttu-id="6f528-p106">실제 미디어 시작 시간이 아니라 미디어 요청이 전송된 시간입니다. <strong>StartTime</strong>에는 세션 설정 시간이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f528-p106">This is the time that a media request was sent out, not the real media start time. <strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f528-137"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="6f528-137"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6f528-138">datetime</span><span class="sxs-lookup"><span data-stu-id="6f528-138">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f528-139">세션의 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6f528-139">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

