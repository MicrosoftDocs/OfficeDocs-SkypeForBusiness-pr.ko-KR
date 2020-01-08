---
title: 'Lync Server 2013: ConferenceUris 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2b1ab44b564d649b6c8fb812077645c6dc13093
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="5cf94-102">Lync Server 2013의 ConferenceUris 테이블</span><span class="sxs-lookup"><span data-stu-id="5cf94-102">ConferenceUris table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cf94-103">_**마지막으로 수정한 주제:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="5cf94-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="5cf94-104">ConfereneUris 테이블은 데이터베이스에 기록 된 회의 세션에 참가 한 다양 한 회의 Uri 목록을 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="5cf94-104">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="5cf94-105">테이블의 각 레코드는 하나의 회의 URI를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5cf94-105">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cf94-106">열</span><span class="sxs-lookup"><span data-stu-id="5cf94-106">Column</span></span></th>
<th><span data-ttu-id="5cf94-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5cf94-107">Data Type</span></span></th>
<th><span data-ttu-id="5cf94-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="5cf94-108">Key/Index</span></span></th>
<th><span data-ttu-id="5cf94-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="5cf94-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cf94-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="5cf94-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="5cf94-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="5cf94-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5cf94-112">주요한</span><span class="sxs-lookup"><span data-stu-id="5cf94-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="5cf94-113">내부에 사용 되는 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="5cf94-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cf94-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="5cf94-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="5cf94-115">int</span><span class="sxs-lookup"><span data-stu-id="5cf94-115">int</span></span></p></td>
<td><p><span data-ttu-id="5cf94-116">주요한</span><span class="sxs-lookup"><span data-stu-id="5cf94-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="5cf94-117">이 회의 URI를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5cf94-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cf94-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="5cf94-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5cf94-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5cf94-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5cf94-120">회의 URI.</span><span class="sxs-lookup"><span data-stu-id="5cf94-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cf94-121"><strong>검사</strong></span><span class="sxs-lookup"><span data-stu-id="5cf94-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="5cf94-122">int</span><span class="sxs-lookup"><span data-stu-id="5cf94-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5cf94-123">ConferenceUri의 검사 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5cf94-123">Checksum of ConferenceUri.</span></span> <span data-ttu-id="5cf94-124">데이터베이스 검색 속도를 향상 시키는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cf94-124">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cf94-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="5cf94-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="5cf94-126">int</span><span class="sxs-lookup"><span data-stu-id="5cf94-126">int</span></span></p></td>
<td><p><span data-ttu-id="5cf94-127">외부</span><span class="sxs-lookup"><span data-stu-id="5cf94-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5cf94-128">회의: IM 회의에 대 한 채팅 또는 컨퍼런스: 오디오/비디오 회의를 위한 오디오-영상 통화 등의 URI 형식</span><span class="sxs-lookup"><span data-stu-id="5cf94-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="5cf94-129">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 테이블의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5cf94-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

