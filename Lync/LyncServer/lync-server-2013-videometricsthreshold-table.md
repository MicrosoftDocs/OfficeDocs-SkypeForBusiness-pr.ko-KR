---
title: 'Lync Server 2013: VideoMetricsThreshold 테이블'
description: 'Lync Server 2013: VideoMetricsThreshold 테이블'
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
ms.openlocfilehash: 93cdd6fb4c3c54ac1470499490f36fee87ba283d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568004"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="04af1-103">Lync Server 2013의 VideoMetricsThreshold 테이블</span><span class="sxs-lookup"><span data-stu-id="04af1-103">VideoMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04af1-104">_**마지막으로 수정 된 항목:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="04af1-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="04af1-105">VideoMetricsThreshold 테이블은 비디오 통화에 사용되는 체감 품질 메트릭에 대한 최적의 값과 적절한 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-105">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="04af1-106"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="04af1-107"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="04af1-108"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="04af1-109"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04af1-110"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-110"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-111">int</span><span class="sxs-lookup"><span data-stu-id="04af1-111">int</span></span></p></td>
<td><p><span data-ttu-id="04af1-112">Primary</span><span class="sxs-lookup"><span data-stu-id="04af1-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="04af1-113">건 전화의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-113">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04af1-114"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-114"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-115">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="04af1-115">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04af1-116">기본값은 0.05입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-116">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04af1-117"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-117"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-118">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="04af1-118">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04af1-119">기본값은 0.10입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-119">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04af1-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-121">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="04af1-121">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04af1-122">기본값은 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-122">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04af1-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-124">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="04af1-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04af1-125">기본값은 10.0입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-125">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04af1-126"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-126"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-127">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="04af1-127">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04af1-128">기본값은 12.0000입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-128">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04af1-129"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-129"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-130">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="04af1-130">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04af1-131">기본값은 7.0000입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-131">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04af1-132"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-132"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-133">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="04af1-133">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04af1-134">기본값은 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-134">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04af1-135"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-135"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-136">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="04af1-136">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04af1-137">기본값은 10.0입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-137">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04af1-138"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-138"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-139">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="04af1-139">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04af1-140">기본값은 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-140">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04af1-141"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-141"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-142">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="04af1-142">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04af1-143">기본값은 10.0입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-143">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04af1-144"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-144"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-145">at</span><span class="sxs-lookup"><span data-stu-id="04af1-145">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04af1-146">기본값은 0.05입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-146">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04af1-147"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-147"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-148">식</span><span class="sxs-lookup"><span data-stu-id="04af1-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04af1-149">기본값은 0.10입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-149">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04af1-150"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-150"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-151">식</span><span class="sxs-lookup"><span data-stu-id="04af1-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04af1-152">기본값은 12입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-152">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04af1-153"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-153"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-154">식</span><span class="sxs-lookup"><span data-stu-id="04af1-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04af1-155">기본값은 7입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-155">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04af1-156"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-156"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-157">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="04af1-157">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04af1-158">기본값은 5.00입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-158">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="04af1-159"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="04af1-159"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="04af1-160">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="04af1-160">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="04af1-161">기본값은 10.00입니다.</span><span class="sxs-lookup"><span data-stu-id="04af1-161">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

