---
title: 'Lync Server 2013: PurgeSettings 테이블'
description: 'Lync Server 2013: PurgeSettings 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table
ms:assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205121(v=OCS.15)
ms:contentKeyID: 48184932
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ec2d1508d8362988bddbab2fe7303a23a8ee2d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559184"
---
# <a name="purgesettings-table-in-lync-server-2013"></a><span data-ttu-id="ac381-103">Lync Server 2013의 PurgeSettings 테이블</span><span class="sxs-lookup"><span data-stu-id="ac381-103">PurgeSettings table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac381-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ac381-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ac381-105">PurgeSettings 테이블에는 오래된 통화 정보 기록을 CDR 데이터베이스에서 자동으로 삭제할지 여부 및 시기를 지정하는 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac381-105">The PurgeSettings table contains information that specifies if (and when) outdated call detail records will automatically be deleted from the CDR database.</span></span> <span data-ttu-id="ac381-106">다음 명령을 실행 하 여 Microsoft Lync Server 2013 관리 셸 내 에서도 제거 관련 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac381-106">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsCdrConfiguration

<span data-ttu-id="ac381-107">관리자는 PurgeSettings 테이블을 읽기 전용으로 취급 해야 합니다. 통화 정보 제거 설정에 대 한 변경 내용은 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) 또는 [get-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac381-107">Administrators should treat the PurgeSettings table as read-only: changes to the call detail purge settings should only be made using the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) or [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlets.</span></span>

<span data-ttu-id="ac381-108">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ac381-108">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ac381-109">열</span><span class="sxs-lookup"><span data-stu-id="ac381-109">Column</span></span></th>
<th><span data-ttu-id="ac381-110">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ac381-110">Data Type</span></span></th>
<th><span data-ttu-id="ac381-111">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="ac381-111">Key/Index</span></span></th>
<th><span data-ttu-id="ac381-112">세부 정보</span><span class="sxs-lookup"><span data-stu-id="ac381-112">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ac381-113"><strong>Id</strong></span><span class="sxs-lookup"><span data-stu-id="ac381-113"><strong>Id</strong></span></span></p></td>
<td><p><span data-ttu-id="ac381-114">int</span><span class="sxs-lookup"><span data-stu-id="ac381-114">int</span></span></p></td>
<td><p><span data-ttu-id="ac381-115">Primary</span><span class="sxs-lookup"><span data-stu-id="ac381-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="ac381-116">CDR 삭제 설정 컬렉션에 대한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ac381-116">Unique identifier for the collection of CDR purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac381-117"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="ac381-117"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="ac381-118">비트만</span><span class="sxs-lookup"><span data-stu-id="ac381-118">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ac381-119">True (1)로 설정 하면 Microsoft Lync Server 2013에서는 CDR 데이터베이스에서 오래 된 레코드를 주기적으로 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac381-119">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the CDR database.</span></span> <span data-ttu-id="ac381-120">삭제는 매일 PurgeHour 설정으로 지정된 시간에 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac381-120">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="ac381-121">False(0)로 설정하면 레코드가 데이터베이스에서 자동으로 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac381-121">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="ac381-122">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="ac381-122">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac381-123"><strong>Keepcalldetailfordays는</strong></span><span class="sxs-lookup"><span data-stu-id="ac381-123"><strong>KeepCallDetailForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="ac381-124">int</span><span class="sxs-lookup"><span data-stu-id="ac381-124">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ac381-p103">데이터베이스에서 삭제할 CDR 레코드의 기간(일)을 지정합니다. 삭제를 사용하도록 설정한 경우 이 값보다 오래된 CDR 레코드가 데이터베이스에서 삭제됩니다. 기본값은 60일입니다.</span><span class="sxs-lookup"><span data-stu-id="ac381-p103">Specifies the age of CDR records (in days) that will be purged from the database: if purging is enabled, CDR records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ac381-127"><strong>KeepErrorReportForDays</strong></span><span class="sxs-lookup"><span data-stu-id="ac381-127"><strong>KeepErrorReportForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="ac381-128">int</span><span class="sxs-lookup"><span data-stu-id="ac381-128">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ac381-p104">데이터베이스에서 삭제할 오류 보고서 레코드의 기간(일)을 지정합니다. 삭제를 사용하도록 설정한 경우 이 값보다 오래된 오류 보고서 레코드가 데이터베이스에서 삭제됩니다. 기본값은 60일입니다.</span><span class="sxs-lookup"><span data-stu-id="ac381-p104">Specifies the age of error report records (in days) that will be purged from the database: if purging is enabled, error report records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ac381-131"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="ac381-131"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="ac381-132">int</span><span class="sxs-lookup"><span data-stu-id="ac381-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ac381-p105">데이터베이스 삭제가 수행되는 현지 시간을 지정합니다. 시간은 24시간제를 사용하여 지정합니다. 0은 자정(오전 12:00)을 나타내고 23은 오후 11:00를 나타냅니다. 시간만 지정할 수 있습니다. 즉, 값으로 10(오전 10:00)은 사용할 수는 있지만, 10:30 또는 10.5(오전 10:30)는 사용할 수 없습니다. 기본값은 2(오전 2:00)입니다.</span><span class="sxs-lookup"><span data-stu-id="ac381-p105">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 2 (2:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

