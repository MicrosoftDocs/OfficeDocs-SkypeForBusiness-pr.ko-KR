---
title: 'Lync Server 2013: Conferences 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17cbadaf18fa36ca55f7755b5e679e564163a207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="b9d64-102">Lync Server 2013의 Conferences 테이블</span><span class="sxs-lookup"><span data-stu-id="b9d64-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9d64-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b9d64-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b9d64-104">이 테이블의 각 레코드에는 한 회의에 대 한 통화 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9d64-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9d64-105">열</span><span class="sxs-lookup"><span data-stu-id="b9d64-105">Column</span></span></th>
<th><span data-ttu-id="b9d64-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9d64-106">Data Type</span></span></th>
<th><span data-ttu-id="b9d64-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="b9d64-107">Key/Index</span></span></th>
<th><span data-ttu-id="b9d64-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="b9d64-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9d64-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b9d64-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b9d64-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="b9d64-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b9d64-111">주요한</span><span class="sxs-lookup"><span data-stu-id="b9d64-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="b9d64-112">전화 회의 요청이 CDR 에이전트에 의해 캡처 된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b9d64-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="b9d64-113">회의 인스턴스를 고유 하 게 식별 하는 기본 키로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9d64-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d64-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b9d64-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b9d64-115">int</span><span class="sxs-lookup"><span data-stu-id="b9d64-115">int</span></span></p></td>
<td><p><span data-ttu-id="b9d64-116">주요한</span><span class="sxs-lookup"><span data-stu-id="b9d64-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="b9d64-117">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b9d64-117">ID number to identify the session.</span></span> <span data-ttu-id="b9d64-118">회의 인스턴스를 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9d64-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9d64-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="b9d64-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9d64-120">int</span><span class="sxs-lookup"><span data-stu-id="b9d64-120">int</span></span></p></td>
<td><p><span data-ttu-id="b9d64-121">외부</span><span class="sxs-lookup"><span data-stu-id="b9d64-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b9d64-122">회의 URI.</span><span class="sxs-lookup"><span data-stu-id="b9d64-122">Conference URI.</span></span> <span data-ttu-id="b9d64-123">자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9d64-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d64-124"><strong>인스턴스</strong></span><span class="sxs-lookup"><span data-stu-id="b9d64-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="b9d64-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="b9d64-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b9d64-126">되풀이 회의에 유용 합니다. 각 되풀이 회의의 각 인스턴스는 동일한 <strong>ConferenceUri</strong>를 가지 지만 다양 한 다른 <strong>인스턴스</strong>를 보유 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9d64-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9d64-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="b9d64-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b9d64-128">dmtf</span><span class="sxs-lookup"><span data-stu-id="b9d64-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b9d64-129">회의 시작 시간.</span><span class="sxs-lookup"><span data-stu-id="b9d64-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d64-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="b9d64-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b9d64-131">dmtf</span><span class="sxs-lookup"><span data-stu-id="b9d64-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b9d64-132">회의 시작 시간.</span><span class="sxs-lookup"><span data-stu-id="b9d64-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9d64-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="b9d64-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9d64-134">int</span><span class="sxs-lookup"><span data-stu-id="b9d64-134">int</span></span></p></td>
<td><p><span data-ttu-id="b9d64-135">외부</span><span class="sxs-lookup"><span data-stu-id="b9d64-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b9d64-136">회의를 캡처한 풀을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b9d64-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="b9d64-137">자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9d64-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d64-138"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="b9d64-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9d64-139">Int</span><span class="sxs-lookup"><span data-stu-id="b9d64-139">Int</span></span></p></td>
<td><p><span data-ttu-id="b9d64-140">외부</span><span class="sxs-lookup"><span data-stu-id="b9d64-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b9d64-141">이 컨퍼런스의 이끌이 URI를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b9d64-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="b9d64-142">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9d64-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9d64-143"><strong>플래그</strong></span><span class="sxs-lookup"><span data-stu-id="b9d64-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="b9d64-144">smallint</span><span class="sxs-lookup"><span data-stu-id="b9d64-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b9d64-145">컨퍼런스 특성을 포함 하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="b9d64-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="b9d64-146">사용할 수 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b9d64-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="b9d64-147">0X01</span><span class="sxs-lookup"><span data-stu-id="b9d64-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="b9d64-148">종합적인</span><span class="sxs-lookup"><span data-stu-id="b9d64-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="b9d64-149">트랜잭션과</span><span class="sxs-lookup"><span data-stu-id="b9d64-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9d64-150"><strong>처리</strong></span><span class="sxs-lookup"><span data-stu-id="b9d64-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="b9d64-151">다소</span><span class="sxs-lookup"><span data-stu-id="b9d64-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b9d64-152">모니터링 서비스에서 사용 하는 내부 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b9d64-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="b9d64-153">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9d64-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b9d64-154">\*대부분의 세션에서 SessionIdSeq에는 값 1이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9d64-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="b9d64-155">두 세션이 정확히 동시에 시작 되 면 1에 대 한 SessionIdSeq는 1이 되 고 다른 하나는 2가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9d64-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

