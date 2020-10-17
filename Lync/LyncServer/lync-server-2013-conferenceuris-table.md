---
title: 'Lync Server 2013: ConferenceUris 테이블'
description: 'Lync Server 2013: ConferenceUris 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a142aa9ad1fe4d3ae92aa3e21aa9eee505457cbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566744"
---
# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="9f105-103">Lync Server 2013의 ConferenceUris 테이블</span><span class="sxs-lookup"><span data-stu-id="9f105-103">ConferenceUris table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f105-104">_**마지막으로 수정 된 항목:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="9f105-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="9f105-105">ConfereneUris 테이블은 데이터베이스에 기록 된 전화 회의 세션에 참가 한 다양 한 전화 회의 Uri 목록을 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="9f105-105">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="9f105-106">테이블의 각 레코드는 하나의 회의 URI를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9f105-106">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f105-107">열</span><span class="sxs-lookup"><span data-stu-id="9f105-107">Column</span></span></th>
<th><span data-ttu-id="9f105-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9f105-108">Data Type</span></span></th>
<th><span data-ttu-id="9f105-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="9f105-109">Key/Index</span></span></th>
<th><span data-ttu-id="9f105-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="9f105-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f105-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="9f105-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="9f105-112">datetime</span><span class="sxs-lookup"><span data-stu-id="9f105-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="9f105-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9f105-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="9f105-114">내부 사용 시간 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="9f105-114">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f105-115"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="9f105-115"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="9f105-116">int</span><span class="sxs-lookup"><span data-stu-id="9f105-116">int</span></span></p></td>
<td><p><span data-ttu-id="9f105-117">Primary</span><span class="sxs-lookup"><span data-stu-id="9f105-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="9f105-118">이 회의 URI를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9f105-118">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f105-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="9f105-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9f105-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9f105-120">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f105-121">전화 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9f105-121">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f105-122"><strong>제외</strong></span><span class="sxs-lookup"><span data-stu-id="9f105-122"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="9f105-123">int</span><span class="sxs-lookup"><span data-stu-id="9f105-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9f105-124">ConferenceUri의 체크섬입니다.</span><span class="sxs-lookup"><span data-stu-id="9f105-124">Checksum of ConferenceUri.</span></span> <span data-ttu-id="9f105-125">데이터베이스 검색 속도를 향상 시키는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f105-125">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f105-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="9f105-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="9f105-127">int</span><span class="sxs-lookup"><span data-stu-id="9f105-127">int</span></span></p></td>
<td><p><span data-ttu-id="9f105-128">외부</span><span class="sxs-lookup"><span data-stu-id="9f105-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9f105-129">오디오/비디오 회의에 대 한 회의: 음성 채팅에 대 한 대화 또는 전화: 오디오와 같은 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="9f105-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="9f105-130">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 테이블의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9f105-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

