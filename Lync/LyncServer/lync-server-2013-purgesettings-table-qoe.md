---
title: 'Lync Server 2013: PurgeSettings 테이블 (QoE)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PurgeSettings table (QoE)
ms:assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204788(v=OCS.15)
ms:contentKeyID: 48183777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 622a807e9b41487408a62863e4c46149c63bbe8a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="purgesettings-table-qoe-in-lync-server-2013"></a><span data-ttu-id="8941b-102">Lync Server 2013의 PurgeSettings 테이블 (QoE)</span><span class="sxs-lookup"><span data-stu-id="8941b-102">PurgeSettings table (QoE) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8941b-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8941b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8941b-104">PurgeSettings 테이블은 오래된 체감 품질 레코드가 QoE 데이터베이스에서 자동으로 삭제되는지 여부 및 삭제되는 시간을 지정하는 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8941b-104">The PurgeSettings table contains information that specifies if (and when) outdated Quality of Experience records will automatically be deleted from the QoE database.</span></span> <span data-ttu-id="8941b-105">다음 명령을 실행 하 여 Microsoft Lync Server 2013 관리 셸 내 에서도 제거 관련 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8941b-105">Note that purging-related information can also be obtained from within the Microsoft Lync Server 2013 Management Shell by running the following command:</span></span>

    Get-CsQoEConfiguration

<span data-ttu-id="8941b-106">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8941b-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8941b-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="8941b-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8941b-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="8941b-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8941b-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="8941b-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8941b-110"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="8941b-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8941b-111"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="8941b-111"><strong>ID</strong></span></span></p></td>
<td><p><span data-ttu-id="8941b-112">int</span><span class="sxs-lookup"><span data-stu-id="8941b-112">int</span></span></p></td>
<td><p><span data-ttu-id="8941b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8941b-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="8941b-114">QoE 삭제 설정 컬렉션의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8941b-114">Unique identifier for the collection of QoE purge settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8941b-115"><strong>EnablePurge</strong></span><span class="sxs-lookup"><span data-stu-id="8941b-115"><strong>EnablePurge</strong></span></span></p></td>
<td><p><span data-ttu-id="8941b-116">비트만</span><span class="sxs-lookup"><span data-stu-id="8941b-116">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8941b-117">True (1)로 설정 하면 Microsoft Lync Server 2013이 QoE 데이터베이스에서 오래 된 레코드를 주기적으로 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="8941b-117">When set to True (1) Microsoft Lync Server 2013 will periodically purge outdated records from the QoE database.</span></span> <span data-ttu-id="8941b-118">삭제는 매일 PurgeHour 설정으로 지정된 시간에 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8941b-118">Purging will take place each day at the tome specified by the PurgeHour setting.</span></span> <span data-ttu-id="8941b-119">False(0)로 설정하면 레코드가 데이터베이스에서 자동으로 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8941b-119">If set to False (0) then records will not be automatically purged from the database.</span></span> <span data-ttu-id="8941b-120">기본값은 True입니다.</span><span class="sxs-lookup"><span data-stu-id="8941b-120">The default value is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8941b-121"><strong>KeepQoEDataForDays</strong></span><span class="sxs-lookup"><span data-stu-id="8941b-121"><strong>KeepQoEDataForDays</strong></span></span></p></td>
<td><p><span data-ttu-id="8941b-122">int</span><span class="sxs-lookup"><span data-stu-id="8941b-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8941b-p103">QoE 레코드가 데이터베이스에서 삭제되는 기간(일)을 지정합니다. 삭제가 사용하도록 설정된 경우 이 값보다 오래된 QoE 레코드가 데이터베이스에서 제거됩니다. 기본값은 60일입니다.</span><span class="sxs-lookup"><span data-stu-id="8941b-p103">Specifies the age of QoE records (in days) that will be purged from the database: if purging is enabled, QoE records older than this value will be removed from the database. The default value is 60 days.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8941b-125"><strong>PurgeHour</strong></span><span class="sxs-lookup"><span data-stu-id="8941b-125"><strong>PurgeHour</strong></span></span></p></td>
<td><p><span data-ttu-id="8941b-126">int</span><span class="sxs-lookup"><span data-stu-id="8941b-126">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8941b-p104">데이터베이스 삭제가 수행되는 로컬 시간을 지정합니다. 시간은 24시간제를 사용하여 지정되며 0이 자정(오전 12시)을, 23이 오후 11시를 나타냅니다. 시간 단위만 지정할 수 있습니다. 즉, 오전 10시를 나타내는 10은 값으로 허용되지만 오전 10시 30분을 나타내는 10:30 또는 10.5는 값으로 허용되지 않습니다. 기본값은 1(오전 1시)입니다.</span><span class="sxs-lookup"><span data-stu-id="8941b-p104">Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM). Specifies the local time of day when database purging will take place. The time of day is specified using a 24-hour clock, with 0 representing midnight (12:00 AM) and 23 representing 11:00 PM. Note that you can only specify the hour of the day: a value of 10 (indicating 10:00 AM) is allowed, but a value of 10:30 of 10.5 (indicating 10:30 AM) is not allowed. The default value is 1 (1:00 AM).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

