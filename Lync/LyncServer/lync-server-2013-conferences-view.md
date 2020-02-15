---
title: 'Lync Server 2013: 회의 보기'
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
ms.openlocfilehash: 56f292a35f5e4f24ba5226e06a308e780ce5c687
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="68cd9-102">Lync Server 2013의 회의 보기</span><span class="sxs-lookup"><span data-stu-id="68cd9-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68cd9-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="68cd9-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="68cd9-104">회의 보기에는 회의에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="68cd9-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="68cd9-105">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="68cd9-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68cd9-106">열</span><span class="sxs-lookup"><span data-stu-id="68cd9-106">Column</span></span></th>
<th><span data-ttu-id="68cd9-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="68cd9-107">Data Type</span></span></th>
<th><span data-ttu-id="68cd9-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="68cd9-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68cd9-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="68cd9-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="68cd9-110">datetime</span><span class="sxs-lookup"><span data-stu-id="68cd9-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="68cd9-111">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="68cd9-111">Time of session request.</span></span> <span data-ttu-id="68cd9-112">SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="68cd9-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="68cd9-113">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="68cd9-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68cd9-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="68cd9-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="68cd9-115">int</span><span class="sxs-lookup"><span data-stu-id="68cd9-115">int</span></span></p></td>
<td><p><span data-ttu-id="68cd9-116">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="68cd9-116">ID number to identify the session.</span></span> <span data-ttu-id="68cd9-117">SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="68cd9-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="68cd9-118">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="68cd9-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68cd9-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="68cd9-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="68cd9-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="68cd9-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="68cd9-121">회의의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="68cd9-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68cd9-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="68cd9-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="68cd9-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68cd9-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68cd9-124">회의 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="68cd9-124">Type of the conference URI.</span></span> <span data-ttu-id="68cd9-125">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="68cd9-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68cd9-126"><strong>인스턴스</strong></span><span class="sxs-lookup"><span data-stu-id="68cd9-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="68cd9-127">고유</span><span class="sxs-lookup"><span data-stu-id="68cd9-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="68cd9-p105">되풀이 회의에 유용합니다. 되풀이 회의의 각 인스턴스에는 동일한 ConferenceUri가 포함되지만 ConfInstance가 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="68cd9-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68cd9-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="68cd9-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="68cd9-131">datetime</span><span class="sxs-lookup"><span data-stu-id="68cd9-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="68cd9-132">회의의 시작 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="68cd9-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68cd9-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="68cd9-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="68cd9-134">datetime</span><span class="sxs-lookup"><span data-stu-id="68cd9-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="68cd9-135">회의의 종료 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="68cd9-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68cd9-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="68cd9-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="68cd9-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="68cd9-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="68cd9-138">회의를 구성한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="68cd9-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68cd9-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="68cd9-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="68cd9-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68cd9-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68cd9-141">회의를 구성한 사용자의 URI 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="68cd9-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="68cd9-142">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="68cd9-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68cd9-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="68cd9-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="68cd9-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68cd9-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68cd9-145">회의를 구성한사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="68cd9-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="68cd9-146">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68cd9-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68cd9-147"><strong>그룹</strong></span><span class="sxs-lookup"><span data-stu-id="68cd9-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="68cd9-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="68cd9-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="68cd9-149">회의를 호스팅한 풀의 정규화된 도메인 이름입니다</span><span class="sxs-lookup"><span data-stu-id="68cd9-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68cd9-150"><strong>플래그가</strong></span><span class="sxs-lookup"><span data-stu-id="68cd9-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="68cd9-151">smallint</span><span class="sxs-lookup"><span data-stu-id="68cd9-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="68cd9-p108">회의 특성을 포함하는 비트 마스크입니다. 사용할 수 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68cd9-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="68cd9-154">0X01 - 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="68cd9-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

