---
title: 'Lync Server 2013: Conferences 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c5464d3161a52a31fddb1322c82181d6e7a97fe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="9bb54-102">Lync Server 2013의 Conferences 테이블</span><span class="sxs-lookup"><span data-stu-id="9bb54-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bb54-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9bb54-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9bb54-104">이 테이블의 각 레코드에는 한 회의에 대 한 통화 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bb54-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9bb54-105">열</span><span class="sxs-lookup"><span data-stu-id="9bb54-105">Column</span></span></th>
<th><span data-ttu-id="9bb54-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9bb54-106">Data Type</span></span></th>
<th><span data-ttu-id="9bb54-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="9bb54-107">Key/Index</span></span></th>
<th><span data-ttu-id="9bb54-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="9bb54-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9bb54-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9bb54-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9bb54-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="9bb54-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="9bb54-111">주요한</span><span class="sxs-lookup"><span data-stu-id="9bb54-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="9bb54-112">전화 회의 요청이 CDR 에이전트에 의해 캡처 된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb54-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="9bb54-113">회의 인스턴스를 고유 하 게 식별 하는 기본 키로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bb54-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bb54-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9bb54-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9bb54-115">int</span><span class="sxs-lookup"><span data-stu-id="9bb54-115">int</span></span></p></td>
<td><p><span data-ttu-id="9bb54-116">주요한</span><span class="sxs-lookup"><span data-stu-id="9bb54-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="9bb54-117">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb54-117">ID number to identify the session.</span></span> <span data-ttu-id="9bb54-118">회의 인스턴스를 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bb54-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bb54-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="9bb54-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="9bb54-120">int</span><span class="sxs-lookup"><span data-stu-id="9bb54-120">int</span></span></p></td>
<td><p><span data-ttu-id="9bb54-121">외부</span><span class="sxs-lookup"><span data-stu-id="9bb54-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9bb54-122">회의 URI.</span><span class="sxs-lookup"><span data-stu-id="9bb54-122">Conference URI.</span></span> <span data-ttu-id="9bb54-123">자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9bb54-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bb54-124"><strong>인스턴스</strong></span><span class="sxs-lookup"><span data-stu-id="9bb54-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="9bb54-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="9bb54-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9bb54-126">되풀이 회의에 유용 합니다. 각 되풀이 회의의 각 인스턴스는 동일한 <strong>ConferenceUri</strong>를 가지 지만 다양 한 다른 <strong>인스턴스</strong>를 보유 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bb54-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bb54-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="9bb54-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9bb54-128">dmtf</span><span class="sxs-lookup"><span data-stu-id="9bb54-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9bb54-129">회의 시작 시간.</span><span class="sxs-lookup"><span data-stu-id="9bb54-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bb54-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="9bb54-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9bb54-131">dmtf</span><span class="sxs-lookup"><span data-stu-id="9bb54-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9bb54-132">회의 시작 시간.</span><span class="sxs-lookup"><span data-stu-id="9bb54-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bb54-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="9bb54-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="9bb54-134">int</span><span class="sxs-lookup"><span data-stu-id="9bb54-134">int</span></span></p></td>
<td><p><span data-ttu-id="9bb54-135">외부</span><span class="sxs-lookup"><span data-stu-id="9bb54-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9bb54-136">회의를 캡처한 풀을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb54-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="9bb54-137">자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9bb54-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bb54-138"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="9bb54-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="9bb54-139">Int</span><span class="sxs-lookup"><span data-stu-id="9bb54-139">Int</span></span></p></td>
<td><p><span data-ttu-id="9bb54-140">외부</span><span class="sxs-lookup"><span data-stu-id="9bb54-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9bb54-141">이 컨퍼런스의 이끌이 URI를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb54-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="9bb54-142">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9bb54-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bb54-143"><strong>플래그</strong></span><span class="sxs-lookup"><span data-stu-id="9bb54-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="9bb54-144">smallint</span><span class="sxs-lookup"><span data-stu-id="9bb54-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9bb54-145">컨퍼런스 특성을 포함 하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb54-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="9bb54-146">사용할 수 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb54-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="9bb54-147">0X01</span><span class="sxs-lookup"><span data-stu-id="9bb54-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="9bb54-148">종합적인</span><span class="sxs-lookup"><span data-stu-id="9bb54-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="9bb54-149">트랜잭션과</span><span class="sxs-lookup"><span data-stu-id="9bb54-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bb54-150"><strong>처리</strong></span><span class="sxs-lookup"><span data-stu-id="9bb54-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="9bb54-151">다소</span><span class="sxs-lookup"><span data-stu-id="9bb54-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9bb54-152">모니터링 서비스에서 사용 하는 내부 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="9bb54-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="9bb54-153">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bb54-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9bb54-154">\*대부분의 세션에서 SessionIdSeq에는 값 1이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bb54-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="9bb54-155">두 세션이 정확히 동시에 시작 되 면 1에 대 한 SessionIdSeq는 1이 되 고 다른 하나는 2가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bb54-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

