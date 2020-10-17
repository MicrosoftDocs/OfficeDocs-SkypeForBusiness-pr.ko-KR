---
title: 'Lync Server 2013: 회의 보기'
description: 'Lync Server 2013: 회의 보기입니다.'
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
ms.openlocfilehash: dee7fbb7c839c351fc9c81716a5800a678980549
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561584"
---
# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="cfe33-103">Lync Server 2013의 회의 보기</span><span class="sxs-lookup"><span data-stu-id="cfe33-103">Conferences view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfe33-104">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="cfe33-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="cfe33-105">회의 보기에는 회의에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfe33-105">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="cfe33-106">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cfe33-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cfe33-107">열</span><span class="sxs-lookup"><span data-stu-id="cfe33-107">Column</span></span></th>
<th><span data-ttu-id="cfe33-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="cfe33-108">Data Type</span></span></th>
<th><span data-ttu-id="cfe33-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="cfe33-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cfe33-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="cfe33-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe33-111">datetime</span><span class="sxs-lookup"><span data-stu-id="cfe33-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="cfe33-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="cfe33-112">Time of session request.</span></span> <span data-ttu-id="cfe33-113">SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfe33-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="cfe33-114">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cfe33-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe33-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cfe33-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe33-116">int</span><span class="sxs-lookup"><span data-stu-id="cfe33-116">int</span></span></p></td>
<td><p><span data-ttu-id="cfe33-117">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="cfe33-117">ID number to identify the session.</span></span> <span data-ttu-id="cfe33-118">SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfe33-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="cfe33-119">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cfe33-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfe33-120"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="cfe33-120"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe33-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cfe33-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cfe33-122">회의의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="cfe33-122">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe33-123"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="cfe33-123"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe33-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cfe33-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cfe33-125">회의 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cfe33-125">Type of the conference URI.</span></span> <span data-ttu-id="cfe33-126">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cfe33-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfe33-127"><strong>인스턴스</strong></span><span class="sxs-lookup"><span data-stu-id="cfe33-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe33-128">고유</span><span class="sxs-lookup"><span data-stu-id="cfe33-128">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="cfe33-p105">되풀이 회의에 유용합니다. 되풀이 회의의 각 인스턴스에는 동일한 ConferenceUri가 포함되지만 ConfInstance가 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="cfe33-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe33-131"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="cfe33-131"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe33-132">datetime</span><span class="sxs-lookup"><span data-stu-id="cfe33-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="cfe33-133">회의의 시작 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="cfe33-133">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfe33-134"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="cfe33-134"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe33-135">datetime</span><span class="sxs-lookup"><span data-stu-id="cfe33-135">datetime</span></span></p></td>
<td><p><span data-ttu-id="cfe33-136">회의의 종료 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="cfe33-136">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe33-137"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="cfe33-137"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe33-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cfe33-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cfe33-139">회의를 구성한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="cfe33-139">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfe33-140"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="cfe33-140"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe33-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cfe33-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cfe33-142">회의를 구성한 사용자의 URI 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cfe33-142">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="cfe33-143">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cfe33-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe33-144"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="cfe33-144"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe33-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cfe33-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cfe33-146">회의를 구성한사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="cfe33-146">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="cfe33-147">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cfe33-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cfe33-148"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="cfe33-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe33-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cfe33-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cfe33-150">회의를 호스팅한 풀의 정규화된 도메인 이름입니다</span><span class="sxs-lookup"><span data-stu-id="cfe33-150">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cfe33-151"><strong>플래그가</strong></span><span class="sxs-lookup"><span data-stu-id="cfe33-151"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="cfe33-152">smallint</span><span class="sxs-lookup"><span data-stu-id="cfe33-152">smallint</span></span></p></td>
<td><p><span data-ttu-id="cfe33-p108">회의 특성을 포함하는 비트 마스크입니다. 사용할 수 있는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cfe33-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="cfe33-155">0X01 - 가상 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="cfe33-155">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

