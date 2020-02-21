---
title: 'Lync Server 2013: ConferenceUris 테이블'
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
ms.openlocfilehash: 4310c90bdf3381bf9a5b357d6b45c9252ab7136b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="e5c2c-102">Lync Server 2013의 ConferenceUris 테이블</span><span class="sxs-lookup"><span data-stu-id="e5c2c-102">ConferenceUris table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5c2c-103">_**마지막으로 수정 된 항목:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="e5c2c-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="e5c2c-104">ConfereneUris 테이블은 데이터베이스에 기록 된 전화 회의 세션에 참가 한 다양 한 전화 회의 Uri 목록을 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-104">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database.</span></span> <span data-ttu-id="e5c2c-105">테이블의 각 레코드는 하나의 회의 URI를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-105">Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5c2c-106">열</span><span class="sxs-lookup"><span data-stu-id="e5c2c-106">Column</span></span></th>
<th><span data-ttu-id="e5c2c-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e5c2c-107">Data Type</span></span></th>
<th><span data-ttu-id="e5c2c-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="e5c2c-108">Key/Index</span></span></th>
<th><span data-ttu-id="e5c2c-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e5c2c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5c2c-110"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="e5c2c-110"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="e5c2c-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e5c2c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5c2c-112">Primary</span><span class="sxs-lookup"><span data-stu-id="e5c2c-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="e5c2c-113">내부 사용 시간 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-113">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c2c-114"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="e5c2c-114"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5c2c-115">int</span><span class="sxs-lookup"><span data-stu-id="e5c2c-115">int</span></span></p></td>
<td><p><span data-ttu-id="e5c2c-116">Primary</span><span class="sxs-lookup"><span data-stu-id="e5c2c-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="e5c2c-117">이 회의 URI를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-117">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c2c-118"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e5c2c-118"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e5c2c-119">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e5c2c-119">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5c2c-120">전화 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-120">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5c2c-121"><strong>제외</strong></span><span class="sxs-lookup"><span data-stu-id="e5c2c-121"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="e5c2c-122">int</span><span class="sxs-lookup"><span data-stu-id="e5c2c-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5c2c-123">ConferenceUri의 체크섬입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-123">Checksum of ConferenceUri.</span></span> <span data-ttu-id="e5c2c-124">데이터베이스 검색 속도를 향상 시키는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-124">Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5c2c-125"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="e5c2c-125"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5c2c-126">int</span><span class="sxs-lookup"><span data-stu-id="e5c2c-126">int</span></span></p></td>
<td><p><span data-ttu-id="e5c2c-127">외부</span><span class="sxs-lookup"><span data-stu-id="e5c2c-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e5c2c-128">오디오/비디오 회의에 대 한 회의: 음성 채팅에 대 한 대화 또는 전화: 오디오와 같은 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-128">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="e5c2c-129">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 테이블의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e5c2c-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

