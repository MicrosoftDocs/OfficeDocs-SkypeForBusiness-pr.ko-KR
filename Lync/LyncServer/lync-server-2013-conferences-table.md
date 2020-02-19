---
title: 'Lync Server 2013: 회의 테이블'
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
ms.openlocfilehash: e8cbb42d078ccba029ae0cf55c7b1ced803aa94f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="66268-102">Lync Server 2013의 회의 테이블</span><span class="sxs-lookup"><span data-stu-id="66268-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66268-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="66268-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="66268-104">이 테이블의 각 레코드에는 하나의 회의에 대 한 통화 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66268-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66268-105">열</span><span class="sxs-lookup"><span data-stu-id="66268-105">Column</span></span></th>
<th><span data-ttu-id="66268-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="66268-106">Data Type</span></span></th>
<th><span data-ttu-id="66268-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="66268-107">Key/Index</span></span></th>
<th><span data-ttu-id="66268-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="66268-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66268-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="66268-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66268-110">datetime</span><span class="sxs-lookup"><span data-stu-id="66268-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="66268-111">Primary</span><span class="sxs-lookup"><span data-stu-id="66268-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="66268-112">전화 회의 요청이 CDR 에이전트에 의해 캡처된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="66268-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="66268-113">전화 회의 인스턴스를 고유 하 게 식별 하기 위한 기본 키로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66268-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66268-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="66268-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="66268-115">int</span><span class="sxs-lookup"><span data-stu-id="66268-115">int</span></span></p></td>
<td><p><span data-ttu-id="66268-116">Primary</span><span class="sxs-lookup"><span data-stu-id="66268-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="66268-117">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="66268-117">ID number to identify the session.</span></span> <span data-ttu-id="66268-118"><strong>Sessionidtime</strong> 과 함께 회의 인스턴스를 고유 하 게 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66268-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66268-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="66268-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="66268-120">int</span><span class="sxs-lookup"><span data-stu-id="66268-120">int</span></span></p></td>
<td><p><span data-ttu-id="66268-121">외부</span><span class="sxs-lookup"><span data-stu-id="66268-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66268-122">전화 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="66268-122">Conference URI.</span></span> <span data-ttu-id="66268-123">자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="66268-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66268-124"><strong>인스턴스</strong></span><span class="sxs-lookup"><span data-stu-id="66268-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="66268-125">고유</span><span class="sxs-lookup"><span data-stu-id="66268-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66268-126">되풀이 회의에 유용 합니다. 되풀이 되는 회의의 각 인스턴스는 동일한 <strong>ConferenceUri</strong>을 갖고 있지만 서로 다른 <strong>인스턴스</strong>를 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66268-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66268-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="66268-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66268-128">datetime</span><span class="sxs-lookup"><span data-stu-id="66268-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66268-129">회의 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="66268-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66268-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="66268-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66268-131">datetime</span><span class="sxs-lookup"><span data-stu-id="66268-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66268-132">회의 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="66268-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66268-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="66268-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="66268-134">int</span><span class="sxs-lookup"><span data-stu-id="66268-134">int</span></span></p></td>
<td><p><span data-ttu-id="66268-135">외부</span><span class="sxs-lookup"><span data-stu-id="66268-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66268-136">전화 회의를 캡처한 풀을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="66268-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="66268-137">자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66268-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66268-138"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="66268-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="66268-139">임계값</span><span class="sxs-lookup"><span data-stu-id="66268-139">Int</span></span></p></td>
<td><p><span data-ttu-id="66268-140">외부</span><span class="sxs-lookup"><span data-stu-id="66268-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66268-141">이 회의의 이끌이 URI를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="66268-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="66268-142">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="66268-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66268-143"><strong>플래그가</strong></span><span class="sxs-lookup"><span data-stu-id="66268-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="66268-144">smallint</span><span class="sxs-lookup"><span data-stu-id="66268-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66268-145">전화 회의 특성을 포함 하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="66268-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="66268-146">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="66268-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="66268-147">0X01</span><span class="sxs-lookup"><span data-stu-id="66268-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="66268-148">통합</span><span class="sxs-lookup"><span data-stu-id="66268-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="66268-149">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="66268-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66268-150"><strong>전처리</strong></span><span class="sxs-lookup"><span data-stu-id="66268-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="66268-151">비트만</span><span class="sxs-lookup"><span data-stu-id="66268-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66268-152">모니터링 서비스에서 사용 하는 내부 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="66268-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="66268-153">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="66268-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="66268-154">\*대부분의 세션에서 SessionIdSeq는 값 1을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="66268-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="66268-155">두 세션을 정확히 동시에 시작 하는 경우에는 1을 위한 SessionIdSeq를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66268-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

