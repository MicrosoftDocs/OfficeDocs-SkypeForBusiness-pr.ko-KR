---
title: 'Lync Server 2013: VideoMetricsThreshold 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c15910f6478f3df12bf906f04aee82c89a822de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="7c05e-102">Lync Server 2013의 VideoMetricsThreshold 테이블</span><span class="sxs-lookup"><span data-stu-id="7c05e-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c05e-103">_**마지막으로 수정한 주제:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7c05e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7c05e-104">VideoMetricsThreshold 테이블에는 영상 통화에 사용 되는 경력 메트릭의 품질에 적합 한 값이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c05e-105"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7c05e-106"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7c05e-107"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7c05e-108"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c05e-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-110">int</span><span class="sxs-lookup"><span data-stu-id="7c05e-110">int</span></span></p></td>
<td><p><span data-ttu-id="7c05e-111">주요한</span><span class="sxs-lookup"><span data-stu-id="7c05e-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="7c05e-112">배치 된 통화 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c05e-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-114">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7c05e-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c05e-115">기본값은 0.05입니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c05e-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-117">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7c05e-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c05e-118">기본값은 0.10입니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c05e-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-120">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7c05e-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c05e-121">기본값은 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c05e-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-123">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7c05e-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c05e-124">기본값은 10.0입니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c05e-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-126">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7c05e-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c05e-127">기본값은 12.0000입니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c05e-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-129">10 진수 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="7c05e-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c05e-130">기본값은 7.0000입니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c05e-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-132">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7c05e-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c05e-133">기본값은 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c05e-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-135">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7c05e-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c05e-136">기본값은 10.0/</span><span class="sxs-lookup"><span data-stu-id="7c05e-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c05e-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-138">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7c05e-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c05e-139">기본값은 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c05e-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-141">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7c05e-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c05e-142">기본값은 10.0입니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c05e-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-144">에</span><span class="sxs-lookup"><span data-stu-id="7c05e-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c05e-145">기본값은 0.05입니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c05e-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-147">o</span><span class="sxs-lookup"><span data-stu-id="7c05e-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c05e-148">기본값은 0.10입니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c05e-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-150">o</span><span class="sxs-lookup"><span data-stu-id="7c05e-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c05e-151">기본값은 12입니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c05e-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-153">o</span><span class="sxs-lookup"><span data-stu-id="7c05e-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c05e-154">기본값은 7입니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c05e-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-156">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7c05e-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c05e-157">기본값은 5.00입니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c05e-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="7c05e-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="7c05e-159">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="7c05e-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7c05e-160">기본값은 10.00입니다.</span><span class="sxs-lookup"><span data-stu-id="7c05e-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

