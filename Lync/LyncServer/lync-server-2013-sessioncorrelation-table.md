---
title: 'Lync Server 2013: SessionCorrelation 관계 테이블'
description: 'Lync Server 2013: SessionCorrelation 관계 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionCorrelation table
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398091(v=OCS.15)
ms:contentKeyID: 48183267
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 814b7e8539d89f87e7df60ceb03e70800553fb55
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579664"
---
# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="719f4-103">Lync Server 2013의 SessionCorrelation 관계 테이블</span><span class="sxs-lookup"><span data-stu-id="719f4-103">SessionCorrelation table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="719f4-104">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="719f4-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="719f4-105">SessionCorrelation 관계 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="719f4-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="719f4-106">각 레코드는 여러 세션을 상호 연결 하는 데 사용 되는 하나의 CorrelationID를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="719f4-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="719f4-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="719f4-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="719f4-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="719f4-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="719f4-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="719f4-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="719f4-110"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="719f4-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="719f4-111"><strong>제외</strong></span><span class="sxs-lookup"><span data-stu-id="719f4-111"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="719f4-112">int</span><span class="sxs-lookup"><span data-stu-id="719f4-112">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719f4-113"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="719f4-113"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="719f4-114">int</span><span class="sxs-lookup"><span data-stu-id="719f4-114">int</span></span></p></td>
<td><p><span data-ttu-id="719f4-115">Primary</span><span class="sxs-lookup"><span data-stu-id="719f4-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="719f4-116">이 A/V 회의 서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="719f4-116">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="719f4-117"><strong>관계</strong></span><span class="sxs-lookup"><span data-stu-id="719f4-117"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="719f4-118">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="719f4-118">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="719f4-119">고유한</span><span class="sxs-lookup"><span data-stu-id="719f4-119">Unique</span></span></p></td>
<td><p><span data-ttu-id="719f4-120">상호 연관 된 세션은 상관 ID가 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="719f4-120">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="719f4-121"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="719f4-121"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="719f4-122">datetime</span><span class="sxs-lookup"><span data-stu-id="719f4-122">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="719f4-123">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="719f4-123">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

