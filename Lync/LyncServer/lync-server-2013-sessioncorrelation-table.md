---
title: 'Lync Server 2013: SessionCorrelation 관계 테이블'
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
ms.openlocfilehash: a47e8d3bfcac06aed0ce76616208d0ead018ccbf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessioncorrelation-table-in-lync-server-2013"></a><span data-ttu-id="bee9e-102">Lync Server 2013의 SessionCorrelation 관계 테이블</span><span class="sxs-lookup"><span data-stu-id="bee9e-102">SessionCorrelation table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bee9e-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="bee9e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="bee9e-104">SessionCorrelation 관계 테이블은 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="bee9e-104">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="bee9e-105">각 레코드는 여러 세션을 상호 연결 하는 데 사용 되는 하나의 CorrelationID를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bee9e-105">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bee9e-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="bee9e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="bee9e-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="bee9e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="bee9e-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="bee9e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="bee9e-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="bee9e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bee9e-110"><strong>제외</strong></span><span class="sxs-lookup"><span data-stu-id="bee9e-110"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="bee9e-111">int</span><span class="sxs-lookup"><span data-stu-id="bee9e-111">int</span></span></p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bee9e-112"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="bee9e-112"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="bee9e-113">int</span><span class="sxs-lookup"><span data-stu-id="bee9e-113">int</span></span></p></td>
<td><p><span data-ttu-id="bee9e-114">Primary</span><span class="sxs-lookup"><span data-stu-id="bee9e-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="bee9e-115">이 A/V 회의 서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="bee9e-115">Unique number identifying this A/V Conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bee9e-116"><strong>관계</strong></span><span class="sxs-lookup"><span data-stu-id="bee9e-116"><strong>CorrelationID</strong></span></span></p></td>
<td><p><span data-ttu-id="bee9e-117">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="bee9e-117">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="bee9e-118">고유한</span><span class="sxs-lookup"><span data-stu-id="bee9e-118">Unique</span></span></p></td>
<td><p><span data-ttu-id="bee9e-119">상호 연관 된 세션은 상관 ID가 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="bee9e-119">Sessions that are correlated will have the same correlation ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bee9e-120"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="bee9e-120"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="bee9e-121">datetime</span><span class="sxs-lookup"><span data-stu-id="bee9e-121">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="bee9e-122">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bee9e-122">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

