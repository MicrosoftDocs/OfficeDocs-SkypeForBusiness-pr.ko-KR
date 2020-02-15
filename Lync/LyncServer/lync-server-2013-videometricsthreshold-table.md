---
title: 'Lync Server 2013: VideoMetricsThreshold 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ffd2c289917c5ccf0ec3a484284fecca3323810
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="e52bc-102">Lync Server 2013의 VideoMetricsThreshold 테이블</span><span class="sxs-lookup"><span data-stu-id="e52bc-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e52bc-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e52bc-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e52bc-104">VideoMetricsThreshold 테이블은 비디오 통화에 사용되는 체감 품질 메트릭에 대한 최적의 값과 적절한 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e52bc-105"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e52bc-106"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e52bc-107"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e52bc-108"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e52bc-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-110">int</span><span class="sxs-lookup"><span data-stu-id="e52bc-110">int</span></span></p></td>
<td><p><span data-ttu-id="e52bc-111">Primary</span><span class="sxs-lookup"><span data-stu-id="e52bc-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="e52bc-112">건 전화의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52bc-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-114">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e52bc-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e52bc-115">기본값은 0.05입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52bc-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-117">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e52bc-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e52bc-118">기본값은 0.10입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52bc-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-120">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e52bc-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e52bc-121">기본값은 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52bc-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-123">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e52bc-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e52bc-124">기본값은 10.0입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52bc-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-126">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e52bc-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e52bc-127">기본값은 12.0000입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52bc-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-129">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="e52bc-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e52bc-130">기본값은 7.0000입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52bc-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-132">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e52bc-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e52bc-133">기본값은 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52bc-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-135">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e52bc-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e52bc-136">기본값은 10.0입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52bc-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-138">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e52bc-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e52bc-139">기본값은 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52bc-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-141">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e52bc-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e52bc-142">기본값은 10.0입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52bc-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-144">at</span><span class="sxs-lookup"><span data-stu-id="e52bc-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e52bc-145">기본값은 0.05입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52bc-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-147">식</span><span class="sxs-lookup"><span data-stu-id="e52bc-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e52bc-148">기본값은 0.10입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52bc-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-150">식</span><span class="sxs-lookup"><span data-stu-id="e52bc-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e52bc-151">기본값은 12입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52bc-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-153">식</span><span class="sxs-lookup"><span data-stu-id="e52bc-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e52bc-154">기본값은 7입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e52bc-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-156">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e52bc-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e52bc-157">기본값은 5.00입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e52bc-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="e52bc-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="e52bc-159">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="e52bc-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e52bc-160">기본값은 10.00입니다.</span><span class="sxs-lookup"><span data-stu-id="e52bc-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

