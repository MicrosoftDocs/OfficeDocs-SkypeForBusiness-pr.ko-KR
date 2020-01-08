---
title: 'Lync Server 2013: TraceRoute 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1dd0f9bc3bd900d71a316bf2ff1ab7612a51194
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="f00fa-102">Lync Server 2013의 TraceRoute 테이블</span><span class="sxs-lookup"><span data-stu-id="f00fa-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f00fa-103">_**마지막으로 수정한 주제:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="f00fa-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="f00fa-104">TraceRoute 테이블에는 통화의 라우팅 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f00fa-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="f00fa-105">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f00fa-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f00fa-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="f00fa-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f00fa-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="f00fa-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f00fa-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="f00fa-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f00fa-109"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="f00fa-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f00fa-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f00fa-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f00fa-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="f00fa-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f00fa-112">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="f00fa-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f00fa-113">통화가 시작 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f00fa-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f00fa-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f00fa-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f00fa-115">int</span><span class="sxs-lookup"><span data-stu-id="f00fa-115">int</span></span></p></td>
<td><p><span data-ttu-id="f00fa-116">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="f00fa-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f00fa-117">같은 날짜와 동시에 시작 했을 수 있는 여러 통화를 구분 하는 데 사용 되는 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f00fa-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f00fa-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f00fa-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f00fa-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="f00fa-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f00fa-120">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="f00fa-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f00fa-121">통화에 사용 되는 영상 회선 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f00fa-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="f00fa-122">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f00fa-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="f00fa-123">0 – 오디오</span><span class="sxs-lookup"><span data-stu-id="f00fa-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="f00fa-124">1-영상 통화</span><span class="sxs-lookup"><span data-stu-id="f00fa-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="f00fa-125">2-파노라마 비디오</span><span class="sxs-lookup"><span data-stu-id="f00fa-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="f00fa-126">3-응용 프로그램/데스크톱 공유</span><span class="sxs-lookup"><span data-stu-id="f00fa-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f00fa-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="f00fa-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="f00fa-128">다소</span><span class="sxs-lookup"><span data-stu-id="f00fa-128">bit</span></span></p></td>
<td><p><span data-ttu-id="f00fa-129">주요한</span><span class="sxs-lookup"><span data-stu-id="f00fa-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="f00fa-130">호출을 배치한 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="f00fa-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f00fa-131"><strong>홉당</strong></span><span class="sxs-lookup"><span data-stu-id="f00fa-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="f00fa-132">int</span><span class="sxs-lookup"><span data-stu-id="f00fa-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f00fa-133">네트워크 홉/</span><span class="sxs-lookup"><span data-stu-id="f00fa-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f00fa-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="f00fa-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f00fa-135">int</span><span class="sxs-lookup"><span data-stu-id="f00fa-135">int</span></span></p></td>
<td><p><span data-ttu-id="f00fa-136">외부</span><span class="sxs-lookup"><span data-stu-id="f00fa-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f00fa-137">IP 주소에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f00fa-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="f00fa-138">IP 주소 정보는 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a>에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f00fa-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f00fa-139"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="f00fa-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="f00fa-140">int</span><span class="sxs-lookup"><span data-stu-id="f00fa-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f00fa-141">왕복 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f00fa-141">Roundtrip time.</span></span> <span data-ttu-id="f00fa-142">왕복 시간은 음성 패킷이 목적지에 도달 하는 데 걸리는 시간을 측정 한 다음 받은 알림을 다시 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="f00fa-142">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

