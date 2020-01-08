---
title: 'Lync Server 2013: PurgeSettings table (체감 품질)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3cc227d11ee723acb5a49c50d5b8d4d7e819062
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="ac29a-102">Lync Server 2013의 PurgeSettings 테이블 (체감 품질)</span><span class="sxs-lookup"><span data-stu-id="ac29a-102">PurgeSettings table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac29a-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ac29a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ac29a-104">PurgeSettings 테이블에는 체감 품질 데이터베이스에서 오래 된 경력 품질 레코드가 자동으로 삭제 되는지 여부를 지정 하는 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-104">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="ac29a-105">다음 명령을 실행 하 여 Microsoft Lync Server 2013 관리 셸에서에서 제거 관련 정보를 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="ac29a-106">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac29a-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="ac29a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ac29a-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="ac29a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ac29a-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="ac29a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ac29a-110"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="ac29a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac29a-111"><strong>I</strong></span><span class="sxs-lookup"><span data-stu-id="ac29a-111"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="ac29a-112">int</span><span class="sxs-lookup"><span data-stu-id="ac29a-112">int</span></span></p></td>
<td><p><span data-ttu-id="ac29a-113">주요한</span><span class="sxs-lookup"><span data-stu-id="ac29a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ac29a-114">체감 품질 purge 설정 컬렉션의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-114">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac29a-115"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="ac29a-115"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="ac29a-116">다소</span><span class="sxs-lookup"><span data-stu-id="ac29a-116">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ac29a-117">True (1)로 설정 하면 Microsoft Lync Server 2013 체감 품질 데이터베이스에서 오래 된 레코드가 주기적으로 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-117">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="ac29a-118">제거는 PurgeHour 설정으로 지정 된 상투메 매일 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-118">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="ac29a-119">False로 설정 된 경우 레코드가 데이터베이스에서 자동으로 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-119">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="ac29a-120">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-120">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac29a-121"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="ac29a-121"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="ac29a-122">int</span><span class="sxs-lookup"><span data-stu-id="ac29a-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ac29a-123">데이터베이스에서 삭제 되는 체감 품질 레코드의 기간 (일)을 지정 합니다. 제거를 사용 하는 경우이 값 보다 오래 된 체감 품질 레코드는 데이터베이스에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-123">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database.</span></span> <span data-ttu-id="ac29a-124">기본값은 60 일입니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-124">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac29a-125"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="ac29a-125"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="ac29a-126">int</span><span class="sxs-lookup"><span data-stu-id="ac29a-126">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ac29a-127">데이터베이스 제거를 수행할 현지 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-127">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="ac29a-128">시간은 24시간제를 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-128">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="ac29a-129">일의 시간만 지정할 수 있음: 값 10 (10:00 AM)은 허용 되지만 10.5의 10:30의 값 (10:30 AM을 나타냄)은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-129">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="ac29a-130">기본값은 1 (1:00 AM)입니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-130">The default value is 1 (1:00 AM).</span></span> <span data-ttu-id="ac29a-131">데이터베이스 제거를 수행할 현지 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-131">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="ac29a-132">시간은 24시간제를 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-132">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="ac29a-133">일의 시간만 지정할 수 있음: 값 10 (10:00 AM)은 허용 되지만 10.5의 10:30의 값 (10:30 AM을 나타냄)은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-133">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="ac29a-134">기본값은 1 (1:00 AM)입니다.</span><span class="sxs-lookup"><span data-stu-id="ac29a-134">The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

