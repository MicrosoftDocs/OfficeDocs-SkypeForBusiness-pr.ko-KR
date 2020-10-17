---
title: 'Lync Server 2013: ConferenceJoinTimeThresholds 테이블'
description: 'Lync Server 2013: ConferenceJoinTimeThresholds 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e38c8b99f444e16309882b6a8885d166fdceb9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561674"
---
# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="d435c-103">Lync Server 2013의 ConferenceJoinTimeThresholds 테이블</span><span class="sxs-lookup"><span data-stu-id="d435c-103">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d435c-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d435c-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d435c-p101">ConferenceJoinTimeThresholds 테이블에는 회의 참가 시간 요약 보고서에서 사용하는 분류 경계가 포함됩니다. 회의 참가 시간 요약 보고서에는 사용자가 회의에 정상적으로 참가하는 데 걸리는 시간이 요약되어 있습니다. 이러한 시간 값은 평균 및 다음 범주 중 하나로 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="d435c-p101">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="d435c-107">2초 미만</span><span class="sxs-lookup"><span data-stu-id="d435c-107">Less than 2 seconds.</span></span>

  - <span data-ttu-id="d435c-108">2~5초</span><span class="sxs-lookup"><span data-stu-id="d435c-108">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="d435c-109">5~10초</span><span class="sxs-lookup"><span data-stu-id="d435c-109">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="d435c-110">10초 초과</span><span class="sxs-lookup"><span data-stu-id="d435c-110">More than 10 seconds.</span></span>

<span data-ttu-id="d435c-111">ConferenceJoinTimeThresholds 테이블에는 분류 값 2초, 5초, 10초가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d435c-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="d435c-112">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d435c-112">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d435c-113">열</span><span class="sxs-lookup"><span data-stu-id="d435c-113">Column</span></span></th>
<th><span data-ttu-id="d435c-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d435c-114">Data Type</span></span></th>
<th><span data-ttu-id="d435c-115">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="d435c-115">Key/Index</span></span></th>
<th><span data-ttu-id="d435c-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d435c-116">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d435c-117"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="d435c-117"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="d435c-118">int</span><span class="sxs-lookup"><span data-stu-id="d435c-118">int</span></span></p></td>
<td><p><span data-ttu-id="d435c-119">Primary</span><span class="sxs-lookup"><span data-stu-id="d435c-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="d435c-120">분류의 고유한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d435c-120">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d435c-121"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="d435c-121"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="d435c-122">int</span><span class="sxs-lookup"><span data-stu-id="d435c-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d435c-p102">분류의 상한입니다. 허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d435c-p102">Upper limit for the classification. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="d435c-125">2</span><span class="sxs-lookup"><span data-stu-id="d435c-125">2</span></span></p></li>
<li><p><span data-ttu-id="d435c-126">5 </span><span class="sxs-lookup"><span data-stu-id="d435c-126">5</span></span></p></li>
<li><p><span data-ttu-id="d435c-127">10  </span><span class="sxs-lookup"><span data-stu-id="d435c-127">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

