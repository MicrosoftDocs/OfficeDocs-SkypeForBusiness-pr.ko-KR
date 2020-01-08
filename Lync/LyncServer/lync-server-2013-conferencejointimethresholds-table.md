---
title: 'Lync Server 2013: ConferenceJoinTimeThresholds 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66793cc3bd545d343198d00f7fb477c1f9b88fac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="08a6d-102">Lync Server 2013의 ConferenceJoinTimeThresholds 테이블</span><span class="sxs-lookup"><span data-stu-id="08a6d-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08a6d-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="08a6d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="08a6d-104">ConferenceJoinTimeThresholds 테이블에는 컨퍼런스 참가 시간 요약 보고서에 사용 되는 분류 경계가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08a6d-104">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="08a6d-105">컨퍼런스 참가 시간 요약 보고서에는 사용자가 회의에 참가 하는 데 필요한 시간 시간이 요약 되어 있습니다. 이러한 시간 값은 다음 범주 중 하 나와 평균으로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08a6d-105">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="08a6d-106">2 초 미만.</span><span class="sxs-lookup"><span data-stu-id="08a6d-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="08a6d-107">2 초에서 5 초 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="08a6d-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="08a6d-108">5 초에서 10 초 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="08a6d-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="08a6d-109">10 초 이상</span><span class="sxs-lookup"><span data-stu-id="08a6d-109">More than 10 seconds.</span></span>

<span data-ttu-id="08a6d-110">ConferenceJoinTimeThresholds 테이블에는 2 초, 5 초 및 10 초의 분류 값이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08a6d-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="08a6d-111">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="08a6d-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08a6d-112">열</span><span class="sxs-lookup"><span data-stu-id="08a6d-112">Column</span></span></th>
<th><span data-ttu-id="08a6d-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="08a6d-113">Data Type</span></span></th>
<th><span data-ttu-id="08a6d-114">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="08a6d-114">Key/Index</span></span></th>
<th><span data-ttu-id="08a6d-115">세부적인</span><span class="sxs-lookup"><span data-stu-id="08a6d-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08a6d-116"><strong>ThresholdId</strong></span><span class="sxs-lookup"><span data-stu-id="08a6d-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="08a6d-117">int</span><span class="sxs-lookup"><span data-stu-id="08a6d-117">int</span></span></p></td>
<td><p><span data-ttu-id="08a6d-118">주요한</span><span class="sxs-lookup"><span data-stu-id="08a6d-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="08a6d-119">분류의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="08a6d-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08a6d-120"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="08a6d-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="08a6d-121">int</span><span class="sxs-lookup"><span data-stu-id="08a6d-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="08a6d-122">분류에 대 한 상한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="08a6d-122">Upper limit for the classification.</span></span> <span data-ttu-id="08a6d-123">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="08a6d-123">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="08a6d-124">2</span><span class="sxs-lookup"><span data-stu-id="08a6d-124">2</span></span></p></li>
<li><p><span data-ttu-id="08a6d-125">5mb</span><span class="sxs-lookup"><span data-stu-id="08a6d-125">5</span></span></p></li>
<li><p><span data-ttu-id="08a6d-126">1천만</span><span class="sxs-lookup"><span data-stu-id="08a6d-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

