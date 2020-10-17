---
title: 'Lync Server 2013: AppSharingMetricsThreshold 테이블'
description: 'Lync Server 2013: AppSharingMetricsThreshold 테이블'
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
ms.openlocfilehash: 092c7d08026e6b736b81043a71b4ecaabc4d5f1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546814"
---
# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="bac96-103">Lync Server 2013의 AppSharingMetricsThreshold 테이블</span><span class="sxs-lookup"><span data-stu-id="bac96-103">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bac96-104">_**마지막으로 수정 된 항목:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="bac96-104">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="bac96-p101">AppSharingMetricsThreshold 테이블에는 응용 프로그램 공유에 사용되는 QoE(체감 품질) 메트릭에 대한 최적값 및 허용 가능한 값이 포함되어 있습니다. 이러한 임계값은 응용 프로그램 공유 환경을 불량으로 분류해야 하는지 여부를 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-p101">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing. These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="bac96-107">이 표는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bac96-108"><strong>열</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="bac96-109"><strong>데이터 형식</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="bac96-110"><strong>키/인덱스</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="bac96-111"><strong>세부 정보</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bac96-112"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-112"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="bac96-113">int</span><span class="sxs-lookup"><span data-stu-id="bac96-113">int</span></span></p></td>
<td><p><span data-ttu-id="bac96-114">Primary</span><span class="sxs-lookup"><span data-stu-id="bac96-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="bac96-115">수행된 통화 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-115">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bac96-116"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-116"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="bac96-117">int</span><span class="sxs-lookup"><span data-stu-id="bac96-117">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bac96-p102">응용 프로그램 공유에 대한 최적의 대역폭 제한입니다. 기본값은 1000000입니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-p102">Optimal bandwidth limitation for application sharing. The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bac96-120"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-120"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="bac96-121">int</span><span class="sxs-lookup"><span data-stu-id="bac96-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bac96-p103">응용 프로그램 공유에 대한 허용 가능한 대역폭 제한입니다. 기본값은 500000입니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-p103">Acceptable bandwidth limitation for application sharing. The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bac96-124"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-124"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="bac96-125">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="bac96-125">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bac96-p104">응용 프로그램 공유 품질을 분류하기 위한 "잘못된" 타일에 대한 최적 비율입니다. 이 값은 공유자의 콘텐츠 중 뷰어에 도달하지 못한 비율입니다. 공유자가 그래픽 원본에서 타일을 삭제하거나 ASMCU 타일이 각각의 공유자에서 타일을 삭제하면 콘텐츠가 삭제(또는 잘못됨)될 수 있습니다. 기본값은 11%입니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-p104">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bac96-130"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-130"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="bac96-131">10 진수 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="bac96-131">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bac96-p105">응용 프로그램 공유 품질을 분류하기 위한 "잘못된" 타일에 대한 허용 가능한 비율입니다. 이 값은 공유자의 콘텐츠 중 뷰어에 도달하지 못한 비율입니다. 공유자가 그래픽 원본에서 타일을 삭제하거나 ASMCU 타일이 각각의 공유자에서 타일을 삭제하면 콘텐츠가 삭제(또는 잘못됨)될 수 있습니다. 기본값은 36%입니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-p105">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bac96-136"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-136"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="bac96-137">int</span><span class="sxs-lookup"><span data-stu-id="bac96-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bac96-138">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-138">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bac96-139"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-139"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="bac96-140">int</span><span class="sxs-lookup"><span data-stu-id="bac96-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bac96-141">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-141">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bac96-142"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-142"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="bac96-143">식</span><span class="sxs-lookup"><span data-stu-id="bac96-143">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bac96-144">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-144">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bac96-145"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-145"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="bac96-146">식</span><span class="sxs-lookup"><span data-stu-id="bac96-146">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bac96-147">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-147">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bac96-148"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-148"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="bac96-149">식</span><span class="sxs-lookup"><span data-stu-id="bac96-149">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bac96-150">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-150">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bac96-151"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-151"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="bac96-152">식</span><span class="sxs-lookup"><span data-stu-id="bac96-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bac96-153">이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-153">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bac96-154"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-154"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="bac96-155">식</span><span class="sxs-lookup"><span data-stu-id="bac96-155">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bac96-p106">응용 프로그램 공유에 포함된 두 개의 미디어 끝점 사이의 상대적 단방향 지연 시간에 대한 최적 값입니다. 이 값은 단일 홉 지연 시간 측정값입니다. 기본값은 1.0초입니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-p106">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="bac96-159">이 열은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-159">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bac96-160"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-160"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="bac96-161">식</span><span class="sxs-lookup"><span data-stu-id="bac96-161">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bac96-p107">응용 프로그램 공유에 포함된 두 개의 미디어 끝점 사이의 상대적 단방향 지연 시간에 대한 최적 값입니다. 이 값은 단일 홉 지연 시간 측정값입니다. 기본값은 1.75초입니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-p107">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="bac96-165">이 열은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-165">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bac96-166"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-166"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="bac96-167">식</span><span class="sxs-lookup"><span data-stu-id="bac96-167">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bac96-168">보기 세션 기간 중 AS 회의 서버의 평균 RDP 타일 처리 지연 시간에 대한 최적 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-168">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="bac96-169">대기 시간은 서버에서 시작 프레임이 인코딩 되는 시기와 (시나리오에 따라 공유자 또는 MCU) 같은 시작 프레임이 뷰어에 디코딩되는 시간 차이입니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-169">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="bac96-p109">평균 값이 높으면 보기 환경의 지연 시간이 길다는 것을 나타냅니다. 부하가 높은 회의 서버는 평균 대기 시간이 높을 수 있습니다. 기본값은 200ms입니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-p109">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="bac96-173">이 열은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-173">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bac96-174"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="bac96-174"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="bac96-175">식</span><span class="sxs-lookup"><span data-stu-id="bac96-175">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bac96-176">보기 세션 기간 중 AS 회의 서버의 평균 RDP 타일 처리 지연 시간에 대한 허용 가능한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-176">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="bac96-177">대기 시간은 서버에서 시작 프레임이 인코딩 되는 시기와 (시나리오에 따라 공유자 또는 MCU) 같은 시작 프레임이 뷰어에 디코딩되는 시간 차이입니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-177">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="bac96-p111">평균 값이 높으면 보기 환경의 지연 시간이 길다는 것을 나타냅니다. 부하가 높은 회의 서버는 평균 대기 시간이 높을 수 있습니다. 기본값은 200ms입니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-p111">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="bac96-181">이 열은 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bac96-181">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

