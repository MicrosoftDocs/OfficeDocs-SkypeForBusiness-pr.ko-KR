---
title: 'Lync Server 2013: AppSharingMetricsThreshold 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e247f83b00d226024f9fc671f2d744f1ee7fdf0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="ab59d-102">Lync Server 2013의 AppSharingMetricsThreshold 테이블</span><span class="sxs-lookup"><span data-stu-id="ab59d-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab59d-103">_**마지막으로 수정한 주제:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="ab59d-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="ab59d-104">AppSharingMetricsThreshold 테이블에는 응용 프로그램 공유에 사용 되는 경험 메트릭의 품질 기준에 적합 한 값이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-104">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span> <span data-ttu-id="ab59d-105">이러한 임계값은 응용 프로그램 공유 환경을 불량으로 분류 해야 하는지 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-105">These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="ab59d-106">이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab59d-107"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ab59d-108"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ab59d-109"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ab59d-110"><strong>세부적인</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab59d-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="ab59d-112">int</span><span class="sxs-lookup"><span data-stu-id="ab59d-112">int</span></span></p></td>
<td><p><span data-ttu-id="ab59d-113">주요한</span><span class="sxs-lookup"><span data-stu-id="ab59d-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="ab59d-114">배치 된 통화 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab59d-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab59d-116">int</span><span class="sxs-lookup"><span data-stu-id="ab59d-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab59d-117">응용 프로그램 공유에 대 한 최적의 대역폭 제한.</span><span class="sxs-lookup"><span data-stu-id="ab59d-117">Optimal bandwidth limitation for application sharing.</span></span> <span data-ttu-id="ab59d-118">기본값은 100만입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-118">The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab59d-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ab59d-120">int</span><span class="sxs-lookup"><span data-stu-id="ab59d-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab59d-121">응용 프로그램 공유에 허용 되는 대역폭 제한.</span><span class="sxs-lookup"><span data-stu-id="ab59d-121">Acceptable bandwidth limitation for application sharing.</span></span> <span data-ttu-id="ab59d-122">기본값은 50만입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-122">The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab59d-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab59d-124">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ab59d-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab59d-125">응용 프로그램 공유 품질을 분류 하기 위해 "spoiled" 타일에 대 한 최적 백분율 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-125">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="ab59d-126">이 값은 보기에 도달 하지 않은 공유자 콘텐츠의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-126">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="ab59d-127">공유자에서 그래픽 원본의 타일을 포기 하거나 ASMCU 타일이 공유자의 타일을 각각 삭제 하는 경우 콘텐츠가 취소 (또는 spoiled) 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-127">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="ab59d-128">기본 값은 11%입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-128">The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab59d-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ab59d-130">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="ab59d-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab59d-131">cceptable 응용 프로그램 공유 품질을 분류 하기 위한 "spoiled" 타일의 백분율 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-131">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="ab59d-132">이 값은 보기에 도달 하지 않은 공유자 콘텐츠의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-132">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="ab59d-133">공유자에서 그래픽 원본의 타일을 포기 하거나 ASMCU 타일이 공유자의 타일을 각각 삭제 하는 경우 콘텐츠가 취소 (또는 spoiled) 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-133">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="ab59d-134">기본값은 36%입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-134">The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab59d-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab59d-136">int</span><span class="sxs-lookup"><span data-stu-id="ab59d-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab59d-137">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab59d-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ab59d-139">int</span><span class="sxs-lookup"><span data-stu-id="ab59d-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab59d-140">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab59d-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab59d-142">o</span><span class="sxs-lookup"><span data-stu-id="ab59d-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab59d-143">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab59d-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ab59d-145">o</span><span class="sxs-lookup"><span data-stu-id="ab59d-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab59d-146">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab59d-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab59d-148">o</span><span class="sxs-lookup"><span data-stu-id="ab59d-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab59d-149">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab59d-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ab59d-151">o</span><span class="sxs-lookup"><span data-stu-id="ab59d-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab59d-152">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab59d-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab59d-154">o</span><span class="sxs-lookup"><span data-stu-id="ab59d-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab59d-155">응용 프로그램 공유에 포함 된 두 미디어 끝점 간의 상대적 단방향 지연에 대 한 최적의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-155">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="ab59d-156">이것은 단일 홉 대기 시간 측정입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-156">This is a single-hop latency measure.</span></span> <span data-ttu-id="ab59d-157">기본값은 1.0 초입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-157">The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="ab59d-158">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab59d-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ab59d-160">o</span><span class="sxs-lookup"><span data-stu-id="ab59d-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab59d-161">응용 프로그램 공유에 포함 된 두 미디어 끝점 간의 상대적 단방향 지연에 대 한 최적의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-161">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="ab59d-162">이것은 단일 홉 대기 시간 측정입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-162">This is a single-hop latency measure.</span></span> <span data-ttu-id="ab59d-163">기본값은 1.75 초입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-163">The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="ab59d-164">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab59d-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab59d-166">o</span><span class="sxs-lookup"><span data-stu-id="ab59d-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab59d-167">보기 세션 중에 회의 서버의 평균 RDP 타일 처리 대기 시간에 대 한 최적의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="ab59d-168">대기 시간은 서버 (공유자 또는 해당 시나리오에 따라)에서 시작 프레임을 인코딩한 시간과 동일한 시작 프레임을 뷰어에 디코딩할 때의 차이입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="ab59d-169">평균 높음은 보기 환경에서 더 오래 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-169">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="ab59d-170">오버 로드 된 회의 서버는 평균 지연 시간을 겪을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-170">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="ab59d-171">기본값은 200ms입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-171">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="ab59d-172">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab59d-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ab59d-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ab59d-174">o</span><span class="sxs-lookup"><span data-stu-id="ab59d-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab59d-175">보기 세션 중에 회의 서버의 평균 RDP 타일 처리 대기 시간을 허용 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="ab59d-176">대기 시간은 서버 (공유자 또는 해당 시나리오에 따라)에서 시작 프레임을 인코딩한 시간과 동일한 시작 프레임을 뷰어에 디코딩할 때의 차이입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="ab59d-177">평균 높음은 보기 환경에서 더 오래 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-177">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="ab59d-178">오버 로드 된 회의 서버는 평균 지연 시간을 겪을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-178">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="ab59d-179">기본값은 200ms입니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-179">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="ab59d-180">이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab59d-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

