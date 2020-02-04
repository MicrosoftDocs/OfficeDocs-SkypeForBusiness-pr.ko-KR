---
title: 'Lync Server 2013: UserAgent 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25d1cd6b48b09ad3083499ec3f173772d242ba6b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="4d33e-102">Lync Server 2013의 UserAgent 테이블</span><span class="sxs-lookup"><span data-stu-id="4d33e-102">UserAgent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d33e-103">_**마지막으로 수정한 주제:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="4d33e-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="4d33e-104">UserAgent 테이블은 데이터베이스에 기록 된 세션에 참가 한 다양 한 사용자 에이전트의 목록을 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-104">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="4d33e-105">테이블의 각 레코드는 한 명의 사용자 에이전트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-105">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d33e-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="4d33e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="4d33e-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="4d33e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="4d33e-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="4d33e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="4d33e-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="4d33e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d33e-110"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="4d33e-110"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="4d33e-111">int</span><span class="sxs-lookup"><span data-stu-id="4d33e-111">int</span></span></p></td>
<td><p><span data-ttu-id="4d33e-112">주요한</span><span class="sxs-lookup"><span data-stu-id="4d33e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="4d33e-113">이 사용자 에이전트를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-113">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d33e-114"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="4d33e-114"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="4d33e-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="4d33e-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4d33e-116">독특한</span><span class="sxs-lookup"><span data-stu-id="4d33e-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="4d33e-117">사용자 에이전트 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-117">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d33e-118"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="4d33e-118"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="4d33e-119">smallint</span><span class="sxs-lookup"><span data-stu-id="4d33e-119">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4d33e-120">1은 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-120">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="4d33e-121">2는 A/V 회의 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-121">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="4d33e-122">4 님이 Lync입니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-122">4 is Lync.</span></span></p>
<p><span data-ttu-id="4d33e-123">8은 IP 전화입니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-123">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="4d33e-124">16 개는 Live Meeting Console입니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-124">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="4d33e-125">32는 DVT (배포 유효성 검사 도구)입니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-125">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="4d33e-126">64는 Macintosh 컴퓨터의 Lync입니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-126">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="4d33e-127">128는 Office Communications Server 2007 R2 수행자입니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-127">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="4d33e-128">256는 회의 알림 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-128">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="4d33e-129">512는 회의 자동 전화 교환입니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-129">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="4d33e-130">1024는 응답 그룹 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-130">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="4d33e-131">2048는 음성 제어를 벗어납니다.</span><span class="sxs-lookup"><span data-stu-id="4d33e-131">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

