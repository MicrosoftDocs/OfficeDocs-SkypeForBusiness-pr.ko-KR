---
title: 'Lync Server 2013: Media 테이블'
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
ms.openlocfilehash: 69f9ad10c5c06ab8a9d2bc95eddceb67b20e745c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="43945-102">Lync Server 2013의 Media 테이블</span><span class="sxs-lookup"><span data-stu-id="43945-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43945-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="43945-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="43945-104">각 레코드는 피어 투 피어 세션에 사용 되는 하나의 미디어 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="43945-104">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="43945-105">하나 이상의 미디어 유형이 사용 되는 경우 한 세션은 테이블의 여러 레코드로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43945-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="43945-106">미디어 테이블은 세션의 미디어 기간을 계산 하는 데 사용해 서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43945-106">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="43945-107">이 표에는 세션의 미디어 교환 신호 세부 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43945-107">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="43945-108">미디어 교환은 초대 요청에 의해 수행 되며 StartTime은 초대를 보낸 시간을 나타냅니다. 세션을 수락 하는 경우에만 미디어가 시작 되므로 초대 시간이 반드시 미디어 시작 시간을 의미 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="43945-108">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="43945-109">EndTime은 일반적으로이 세션의 종료 시간을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="43945-109">The EndTime usually means the end time of this session.</span></span>



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
<th><span data-ttu-id="43945-110">열</span><span class="sxs-lookup"><span data-stu-id="43945-110">Column</span></span></th>
<th><span data-ttu-id="43945-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="43945-111">Data Type</span></span></th>
<th><span data-ttu-id="43945-112">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="43945-112">Key/Index</span></span></th>
<th><span data-ttu-id="43945-113">세부적인</span><span class="sxs-lookup"><span data-stu-id="43945-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43945-114"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="43945-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="43945-115">dmtf</span><span class="sxs-lookup"><span data-stu-id="43945-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="43945-116">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="43945-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="43945-117">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="43945-117">Time of session request.</span></span> <span data-ttu-id="43945-118">세션을 고유 하 게 식별 하는 <strong>Sessionidseq</strong> 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43945-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="43945-119">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="43945-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43945-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="43945-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="43945-121">int</span><span class="sxs-lookup"><span data-stu-id="43945-121">int</span></span></p></td>
<td><p><span data-ttu-id="43945-122">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="43945-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="43945-123">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="43945-123">ID number to identify the session.</span></span> <span data-ttu-id="43945-124">세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43945-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="43945-125">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="43945-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43945-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="43945-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="43945-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="43945-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="43945-128">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="43945-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="43945-129">이 미디어 유형을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="43945-129">Unique number identifying this media type.</span></span> <span data-ttu-id="43945-130">자세한 내용은 <a href="lync-server-2013-medialist-table.md">Lync Server 2013의 Medialist 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="43945-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43945-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="43945-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="43945-132">dmtf</span><span class="sxs-lookup"><span data-stu-id="43945-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="43945-133">주요한</span><span class="sxs-lookup"><span data-stu-id="43945-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="43945-134">이것은 실제 미디어 시작 시간이 아닌 미디어 요청이 전송 된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="43945-134">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="43945-135"><strong>StartTime</strong> 에는 세션 설정 시간이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="43945-135"><strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43945-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="43945-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="43945-137">dmtf</span><span class="sxs-lookup"><span data-stu-id="43945-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="43945-138">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="43945-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

