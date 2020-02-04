---
title: 'Lync Server 2013: 컨퍼런스 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36278c1053c2b5737e0de6caf914c050db93ea4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741608"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="e3e5b-102">Lync Server 2013의 회의 보기</span><span class="sxs-lookup"><span data-stu-id="e3e5b-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3e5b-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e3e5b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e3e5b-104">회의 보기는 회의에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="e3e5b-105">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3e5b-106">열</span><span class="sxs-lookup"><span data-stu-id="e3e5b-106">Column</span></span></th>
<th><span data-ttu-id="e3e5b-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e3e5b-107">Data Type</span></span></th>
<th><span data-ttu-id="e3e5b-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="e3e5b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3e5b-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e3e5b-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e3e5b-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="e3e5b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e3e5b-111">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-111">Time of session request.</span></span> <span data-ttu-id="e3e5b-112">세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e3e5b-113">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3e5b-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e3e5b-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e3e5b-115">int</span><span class="sxs-lookup"><span data-stu-id="e3e5b-115">int</span></span></p></td>
<td><p><span data-ttu-id="e3e5b-116">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-116">ID number to identify the session.</span></span> <span data-ttu-id="e3e5b-117">세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e3e5b-118">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3e5b-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e3e5b-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e3e5b-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e3e5b-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e3e5b-121">회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3e5b-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e3e5b-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e3e5b-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3e5b-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3e5b-124">회의 URI의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-124">Type of the conference URI.</span></span> <span data-ttu-id="e3e5b-125">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3e5b-126"><strong>인스턴스</strong></span><span class="sxs-lookup"><span data-stu-id="e3e5b-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e3e5b-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e3e5b-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e3e5b-128">되풀이 회의에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-128">Used for recurring conferences.</span></span> <span data-ttu-id="e3e5b-129">되풀이 회의의 각 인스턴스에는 동일한 ConferenceUri 있지만 다른 지 인 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3e5b-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="e3e5b-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e3e5b-131">dmtf</span><span class="sxs-lookup"><span data-stu-id="e3e5b-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="e3e5b-132">회의 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3e5b-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e3e5b-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e3e5b-134">dmtf</span><span class="sxs-lookup"><span data-stu-id="e3e5b-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="e3e5b-135">회의 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3e5b-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="e3e5b-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e3e5b-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e3e5b-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e3e5b-138">회의를 구성한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3e5b-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="e3e5b-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="e3e5b-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3e5b-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3e5b-141">회의를 구성한 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="e3e5b-142">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3e5b-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e3e5b-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e3e5b-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3e5b-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3e5b-145">회의를 구성한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="e3e5b-146">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3e5b-147"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="e3e5b-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e3e5b-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e3e5b-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3e5b-149">컨퍼런스를 호스팅한 풀의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3e5b-150"><strong>플래그</strong></span><span class="sxs-lookup"><span data-stu-id="e3e5b-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="e3e5b-151">smallint</span><span class="sxs-lookup"><span data-stu-id="e3e5b-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="e3e5b-152">회의 특성을 포함 하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="e3e5b-153">사용할 수 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e3e5b-153">Possible values are:</span></span></p>
<p><span data-ttu-id="e3e5b-154">0X01-가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="e3e5b-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

