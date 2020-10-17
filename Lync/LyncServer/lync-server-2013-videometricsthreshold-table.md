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
ms.openlocfilehash: 2f1f1fc7ca86c10fa9c409c73c2f4b54ee2777a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508515"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="769ba-102">Lync Server 2013의 VideoMetricsThreshold 테이블</span><span class="sxs-lookup"><span data-stu-id="769ba-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="769ba-103">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="769ba-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="769ba-104">VideoMetricsThreshold 테이블은 비디오 통화에 사용되는 체감 품질 메트릭에 대한 최적의 값과 적절한 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="769ba-105"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="769ba-106"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="769ba-107"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="769ba-108"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="769ba-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-110">int</span><span class="sxs-lookup"><span data-stu-id="769ba-110">int</span></span></p></td>
<td><p><span data-ttu-id="769ba-111">Primary</span><span class="sxs-lookup"><span data-stu-id="769ba-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="769ba-112">건 전화의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="769ba-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-114">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="769ba-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="769ba-115">기본값은 0.05입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="769ba-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-117">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="769ba-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="769ba-118">기본값은 0.10입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="769ba-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-120">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="769ba-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="769ba-121">기본값은 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="769ba-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-123">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="769ba-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="769ba-124">기본값은 10.0입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="769ba-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-126">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="769ba-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="769ba-127">기본값은 12.0000입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="769ba-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-129">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="769ba-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="769ba-130">기본값은 7.0000입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="769ba-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-132">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="769ba-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="769ba-133">기본값은 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="769ba-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-135">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="769ba-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="769ba-136">기본값은 10.0입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="769ba-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-138">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="769ba-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="769ba-139">기본값은 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="769ba-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-141">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="769ba-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="769ba-142">기본값은 10.0입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="769ba-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-144">at</span><span class="sxs-lookup"><span data-stu-id="769ba-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="769ba-145">기본값은 0.05입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="769ba-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-147">식</span><span class="sxs-lookup"><span data-stu-id="769ba-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="769ba-148">기본값은 0.10입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="769ba-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-150">식</span><span class="sxs-lookup"><span data-stu-id="769ba-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="769ba-151">기본값은 12입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="769ba-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-153">식</span><span class="sxs-lookup"><span data-stu-id="769ba-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="769ba-154">기본값은 7입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="769ba-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-156">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="769ba-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="769ba-157">기본값은 5.00입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="769ba-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="769ba-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="769ba-159">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="769ba-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="769ba-160">기본값은 10.00입니다.</span><span class="sxs-lookup"><span data-stu-id="769ba-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

