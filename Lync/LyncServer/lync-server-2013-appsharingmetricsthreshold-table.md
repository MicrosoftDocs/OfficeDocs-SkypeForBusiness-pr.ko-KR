---
title: 'Lync Server 2013: AppSharingMetricsThreshold 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0f8dc1dac3dc7a9ec362473221d36191dd7dd0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="9b89e-102">Lync Server 2013의 AppSharingMetricsThreshold 테이블</span><span class="sxs-lookup"><span data-stu-id="9b89e-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b89e-103">_**마지막으로 수정한 주제:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="9b89e-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="9b89e-104">AppSharingMetricsThreshold 테이블에는 응용 프로그램 공유에 사용 되는 경험 메트릭의 품질 기준에 적합 한 값이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-104">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span> <span data-ttu-id="9b89e-105">이러한 임계값은 응용 프로그램 공유 환경을 불량으로 분류 해야 하는지 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-105">These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="9b89e-106">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b89e-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9b89e-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9b89e-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9b89e-110"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b89e-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="9b89e-112">int</span><span class="sxs-lookup"><span data-stu-id="9b89e-112">int</span></span></p></td>
<td><p><span data-ttu-id="9b89e-113">주요한</span><span class="sxs-lookup"><span data-stu-id="9b89e-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="9b89e-114">배치 된 통화 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b89e-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9b89e-116">int</span><span class="sxs-lookup"><span data-stu-id="9b89e-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b89e-117">응용 프로그램 공유에 대 한 최적의 대역폭 제한.</span><span class="sxs-lookup"><span data-stu-id="9b89e-117">Optimal bandwidth limitation for application sharing.</span></span> <span data-ttu-id="9b89e-118">기본값은 100만입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-118">The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b89e-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9b89e-120">int</span><span class="sxs-lookup"><span data-stu-id="9b89e-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b89e-121">응용 프로그램 공유에 허용 되는 대역폭 제한.</span><span class="sxs-lookup"><span data-stu-id="9b89e-121">Acceptable bandwidth limitation for application sharing.</span></span> <span data-ttu-id="9b89e-122">기본값은 50만입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-122">The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b89e-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9b89e-124">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="9b89e-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b89e-125">응용 프로그램 공유 품질을 분류 하기 위해 "spoiled" 타일에 대 한 최적 백분율 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-125">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="9b89e-126">이 값은 보기에 도달 하지 않은 공유자 콘텐츠의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-126">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="9b89e-127">공유자에서 그래픽 원본의 타일을 포기 하거나 ASMCU 타일이 공유자의 타일을 각각 삭제 하는 경우 콘텐츠가 취소 (또는 spoiled) 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-127">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="9b89e-128">기본 값은 11%입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-128">The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b89e-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9b89e-130">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="9b89e-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b89e-131">cceptable 응용 프로그램 공유 품질을 분류 하기 위한 "spoiled" 타일의 백분율 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-131">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="9b89e-132">이 값은 보기에 도달 하지 않은 공유자 콘텐츠의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-132">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="9b89e-133">공유자에서 그래픽 원본의 타일을 포기 하거나 ASMCU 타일이 공유자의 타일을 각각 삭제 하는 경우 콘텐츠가 취소 (또는 spoiled) 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-133">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="9b89e-134">기본값은 36%입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-134">The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b89e-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9b89e-136">int</span><span class="sxs-lookup"><span data-stu-id="9b89e-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b89e-137">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b89e-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9b89e-139">int</span><span class="sxs-lookup"><span data-stu-id="9b89e-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b89e-140">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b89e-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9b89e-142">o</span><span class="sxs-lookup"><span data-stu-id="9b89e-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b89e-143">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b89e-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9b89e-145">o</span><span class="sxs-lookup"><span data-stu-id="9b89e-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b89e-146">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b89e-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9b89e-148">o</span><span class="sxs-lookup"><span data-stu-id="9b89e-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b89e-149">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b89e-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9b89e-151">o</span><span class="sxs-lookup"><span data-stu-id="9b89e-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b89e-152">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b89e-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9b89e-154">o</span><span class="sxs-lookup"><span data-stu-id="9b89e-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b89e-155">응용 프로그램 공유에 포함 된 두 미디어 끝점 간의 상대적 단방향 지연에 대 한 최적의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-155">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="9b89e-156">이것은 단일 홉 대기 시간 측정입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-156">This is a single-hop latency measure.</span></span> <span data-ttu-id="9b89e-157">기본값은 1.0 초입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-157">The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="9b89e-158">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b89e-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9b89e-160">o</span><span class="sxs-lookup"><span data-stu-id="9b89e-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b89e-161">응용 프로그램 공유에 포함 된 두 미디어 끝점 간의 상대적 단방향 지연에 대 한 최적의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-161">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="9b89e-162">이것은 단일 홉 대기 시간 측정입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-162">This is a single-hop latency measure.</span></span> <span data-ttu-id="9b89e-163">기본값은 1.75 초입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-163">The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="9b89e-164">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b89e-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9b89e-166">o</span><span class="sxs-lookup"><span data-stu-id="9b89e-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b89e-167">보기 세션 중에 회의 서버의 평균 RDP 타일 처리 대기 시간에 대 한 최적의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="9b89e-168">대기 시간은 서버 (공유자 또는 해당 시나리오에 따라)에서 시작 프레임을 인코딩한 시간과 동일한 시작 프레임을 뷰어에 디코딩할 때의 차이입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="9b89e-169">평균 높음은 보기 환경에서 더 오래 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-169">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="9b89e-170">오버 로드 된 회의 서버는 평균 지연 시간을 겪을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-170">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="9b89e-171">기본값은 200ms입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-171">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="9b89e-172">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b89e-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9b89e-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9b89e-174">o</span><span class="sxs-lookup"><span data-stu-id="9b89e-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9b89e-175">보기 세션 중에 회의 서버의 평균 RDP 타일 처리 대기 시간을 허용 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="9b89e-176">대기 시간은 서버 (공유자 또는 해당 시나리오에 따라)에서 시작 프레임을 인코딩한 시간과 동일한 시작 프레임을 뷰어에 디코딩할 때의 차이입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="9b89e-177">평균 높음은 보기 환경에서 더 오래 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-177">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="9b89e-178">오버 로드 된 회의 서버는 평균 지연 시간을 겪을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-178">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="9b89e-179">기본값은 200ms입니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-179">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="9b89e-180">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9b89e-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

