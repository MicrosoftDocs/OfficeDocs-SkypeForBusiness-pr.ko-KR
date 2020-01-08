---
title: 'Lync Server 2013: 컨퍼런스 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710aadb2770e9389d9e4becf206d68b8e8d815ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="a797a-102">Lync Server 2013의 회의 보기</span><span class="sxs-lookup"><span data-stu-id="a797a-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a797a-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a797a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a797a-104">회의 보기는 회의에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="a797a-105">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a797a-106">열</span><span class="sxs-lookup"><span data-stu-id="a797a-106">Column</span></span></th>
<th><span data-ttu-id="a797a-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a797a-107">Data Type</span></span></th>
<th><span data-ttu-id="a797a-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="a797a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a797a-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="a797a-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a797a-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="a797a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="a797a-111">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-111">Time of session request.</span></span> <span data-ttu-id="a797a-112">세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="a797a-113">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a797a-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a797a-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a797a-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a797a-115">int</span><span class="sxs-lookup"><span data-stu-id="a797a-115">int</span></span></p></td>
<td><p><span data-ttu-id="a797a-116">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-116">ID number to identify the session.</span></span> <span data-ttu-id="a797a-117">세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="a797a-118">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a797a-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a797a-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="a797a-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a797a-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a797a-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a797a-121">회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a797a-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="a797a-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="a797a-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a797a-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a797a-124">회의 URI의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-124">Type of the conference URI.</span></span> <span data-ttu-id="a797a-125">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a797a-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a797a-126"><strong>인스턴스</strong></span><span class="sxs-lookup"><span data-stu-id="a797a-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="a797a-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="a797a-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="a797a-128">되풀이 회의에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-128">Used for recurring conferences.</span></span> <span data-ttu-id="a797a-129">되풀이 회의의 각 인스턴스에는 동일한 ConferenceUri 있지만 다른 지 인 인스턴스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a797a-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="a797a-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a797a-131">dmtf</span><span class="sxs-lookup"><span data-stu-id="a797a-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="a797a-132">회의 시작 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a797a-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="a797a-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a797a-134">dmtf</span><span class="sxs-lookup"><span data-stu-id="a797a-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="a797a-135">회의 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a797a-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="a797a-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a797a-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a797a-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a797a-138">회의를 구성한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a797a-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="a797a-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="a797a-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a797a-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a797a-141">회의를 구성한 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="a797a-142">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a797a-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a797a-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="a797a-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="a797a-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a797a-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a797a-145">회의를 구성한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="a797a-146">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a797a-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a797a-147"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="a797a-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a797a-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="a797a-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a797a-149">컨퍼런스를 호스팅한 풀의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a797a-150"><strong>플래그</strong></span><span class="sxs-lookup"><span data-stu-id="a797a-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="a797a-151">smallint</span><span class="sxs-lookup"><span data-stu-id="a797a-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="a797a-152">회의 특성을 포함 하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="a797a-153">사용할 수 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a797a-153">Possible values are:</span></span></p>
<p><span data-ttu-id="a797a-154">0X01-가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="a797a-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

