---
title: 'Lync Server 2013: PurgeSettings 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18b9fc0aa03596677cb73641ed46e86ea133f308
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="8cbe8-102">Lync Server 2013의 PurgeSettings 테이블</span><span class="sxs-lookup"><span data-stu-id="8cbe8-102">PurgeSettings table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cbe8-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8cbe8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8cbe8-104">PurgeSettings 테이블에는 CDR 데이터베이스에서 오래 된 통화 정보 레코드가 자동으로 삭제 되는지 여부를 지정 하는 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-104">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="8cbe8-105">다음 명령을 실행 하 여 Microsoft Lync Server 2013 관리 셸에서에서 제거 관련 정보를 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="8cbe8-106">관리자는 PurgeSettings 테이블을 읽기 전용으로 처리 해야 합니다. 통화 정보 제거 설정의 변경 사항은 [새로운-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) 또는 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet을 사용해 서만 이루어져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-106">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="8cbe8-107">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8cbe8-108">열</span><span class="sxs-lookup"><span data-stu-id="8cbe8-108">Column</span></span></th>
<th><span data-ttu-id="8cbe8-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8cbe8-109">Data Type</span></span></th>
<th><span data-ttu-id="8cbe8-110">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="8cbe8-110">Key/Index</span></span></th>
<th><span data-ttu-id="8cbe8-111">세부적인</span><span class="sxs-lookup"><span data-stu-id="8cbe8-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8cbe8-112"><strong>I</strong></span><span class="sxs-lookup"><span data-stu-id="8cbe8-112"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="8cbe8-113">int</span><span class="sxs-lookup"><span data-stu-id="8cbe8-113">int</span></span></p></td>
<td><p><span data-ttu-id="8cbe8-114">주요한</span><span class="sxs-lookup"><span data-stu-id="8cbe8-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="8cbe8-115">CDR 제거 설정 컬렉션의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-115">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cbe8-116"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="8cbe8-116"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="8cbe8-117">다소</span><span class="sxs-lookup"><span data-stu-id="8cbe8-117">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cbe8-118">True (1)로 설정 되 면 Microsoft Lync Server 2013이 CDR 데이터베이스에서 오래 된 레코드를 주기적으로 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-118">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="8cbe8-119">제거는 PurgeHour 설정으로 지정 된 상투메 매일 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-119">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="8cbe8-120">False로 설정 된 경우 레코드가 데이터베이스에서 자동으로 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-120">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="8cbe8-121">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-121">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cbe8-122"><strong>KeepCallDetailForDays</strong></span><span class="sxs-lookup"><span data-stu-id="8cbe8-122"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="8cbe8-123">int</span><span class="sxs-lookup"><span data-stu-id="8cbe8-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cbe8-124">데이터베이스에서 제거 되는 CDR 레코드의 보존 기간 (일)을 지정 합니다. 제거를 사용 하는 경우이 값 보다 오래 된 CDR 레코드가 데이터베이스에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-124">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database.</span></span> <span data-ttu-id="8cbe8-125">기본값은 60 일입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-125">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8cbe8-126"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="8cbe8-126"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="8cbe8-127">int</span><span class="sxs-lookup"><span data-stu-id="8cbe8-127">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cbe8-128">데이터베이스에서 삭제 되는 오류 보고서 레코드의 기간 (일)을 지정 합니다. 제거를 사용 하는 경우이 값 보다 오래 된 오류 보고서 레코드가 데이터베이스에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-128">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database.</span></span> <span data-ttu-id="8cbe8-129">기본값은 60 일입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-129">The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8cbe8-130"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="8cbe8-130"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="8cbe8-131">int</span><span class="sxs-lookup"><span data-stu-id="8cbe8-131">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8cbe8-132">데이터베이스 제거를 수행할 현지 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-132">Specifies the local time of day when database purging will take place.</span></span> <span data-ttu-id="8cbe8-133">시간은 24시간제를 사용하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-133">The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM.</span></span> <span data-ttu-id="8cbe8-134">일의 시간만 지정할 수 있음: 값 10 (10:00 AM)은 허용 되지만 10.5의 10:30의 값 (10:30 AM을 나타냄)은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-134">Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed.</span></span> <span data-ttu-id="8cbe8-135">기본값은 2(오전 2:00)입니다.</span><span class="sxs-lookup"><span data-stu-id="8cbe8-135">The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

