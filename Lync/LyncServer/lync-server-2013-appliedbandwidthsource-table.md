---
title: 'Lync Server 2013: AppliedBandwidthSource 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppliedBandwidthSource table
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425725(v=OCS.15)
ms:contentKeyID: 48183638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ffc7104024c3d4d8fd0aa409fa965d6a426cd34
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appliedbandwidthsource-table-in-lync-server-2013"></a><span data-ttu-id="ad337-102">Lync Server 2013의 AppliedBandwidthSource 테이블</span><span class="sxs-lookup"><span data-stu-id="ad337-102">AppliedBandwidthSource table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad337-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ad337-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ad337-104">AppliedBandwidthSource 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="ad337-104">The AppliedBandwidthSource table is a supporting table.</span></span> <span data-ttu-id="ad337-105">각 레코드는 하나의 소스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad337-105">Each record represents one source.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad337-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="ad337-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ad337-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="ad337-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ad337-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="ad337-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ad337-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="ad337-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad337-110"><strong>AppliedBandwidthSourceKey</strong></span><span class="sxs-lookup"><span data-stu-id="ad337-110"><strong>AppliedBandwidthSourceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ad337-111">int</span><span class="sxs-lookup"><span data-stu-id="ad337-111">int</span></span></p></td>
<td><p><span data-ttu-id="ad337-112">Primary</span><span class="sxs-lookup"><span data-stu-id="ad337-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="ad337-113">원본을 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ad337-113">Unique number identifying the source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad337-114"><strong>AppliedBandwidthSource</strong></span><span class="sxs-lookup"><span data-stu-id="ad337-114"><strong>AppliedBandwidthSource</strong></span></span></p></td>
<td><p><span data-ttu-id="ad337-115">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="ad337-115">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ad337-116">고유한</span><span class="sxs-lookup"><span data-stu-id="ad337-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="ad337-117">적용 되는 대역폭 캡의 출처입니다.</span><span class="sxs-lookup"><span data-stu-id="ad337-117">This is the source of the bandwidth cap being imposed.</span></span> <span data-ttu-id="ad337-118">이 원본은 대역폭 제한이 시작되는 위치(예: "정책 서버", "TURN 서버" 또는 "형식")를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ad337-118">It describes where the bandwidth limit is coming from (for example, “Policy Server”, “TURN Server”, or “Modality”).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

