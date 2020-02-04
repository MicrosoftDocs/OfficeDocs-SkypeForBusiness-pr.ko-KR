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

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a>Lync Server 2013의 AppSharingMetricsThreshold 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2015-12-08_

AppSharingMetricsThreshold 테이블에는 응용 프로그램 공유에 사용 되는 경험 메트릭의 품질 기준에 적합 한 값이 포함 되어 있습니다. 이러한 임계값은 응용 프로그램 공유 환경을 불량으로 분류 해야 하는지 결정 하는 데 사용 됩니다.

이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>열</strong></th>
<th><strong>데이터 형식</strong></th>
<th><strong>키/인덱스</strong></th>
<th><strong>세부적인</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p>배치 된 통화 유형입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimitOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>응용 프로그램 공유에 대 한 최적의 대역폭 제한. 기본값은 100만입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthLimitAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>응용 프로그램 공유에 허용 되는 대역폭 제한. 기본값은 50만입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotalOptimal</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>응용 프로그램 공유 품질을 분류 하기 위해 "spoiled" 타일에 대 한 최적 백분율 비율입니다. 이 값은 보기에 도달 하지 않은 공유자 콘텐츠의 백분율입니다. 공유자에서 그래픽 원본의 타일을 포기 하거나 ASMCU 타일이 공유자의 타일을 각각 삭제 하는 경우 콘텐츠가 취소 (또는 spoiled) 될 수 있습니다. 기본 값은 11%입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentTotalAcceptable</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>cceptable 응용 프로그램 공유 품질을 분류 하기 위한 "spoiled" 타일의 백분율 비율입니다. 이 값은 보기에 도달 하지 않은 공유자 콘텐츠의 백분율입니다. 공유자에서 그래픽 원본의 타일을 포기 하거나 ASMCU 타일이 공유자의 타일을 각각 삭제 하는 경우 콘텐츠가 취소 (또는 spoiled) 될 수 있습니다. 기본값은 36%입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensityOptimal</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensityAcceptable</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>이 열은 Microsoft Lync Server 2013에서 사용 되지 않습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverageOptimal</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>응용 프로그램 공유에 포함 된 두 미디어 끝점 간의 상대적 단방향 지연에 대 한 최적의 값입니다. 이것은 단일 홉 대기 시간 측정입니다. 기본값은 1.0 초입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverageAcceptable</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>응용 프로그램 공유에 포함 된 두 미디어 끝점 간의 상대적 단방향 지연에 대 한 최적의 값입니다. 이것은 단일 홉 대기 시간 측정입니다. 기본값은 1.75 초입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyAverageOptimal</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>보기 세션 중에 회의 서버의 평균 RDP 타일 처리 대기 시간에 대 한 최적의 값입니다. 대기 시간은 서버 (공유자 또는 해당 시나리오에 따라)에서 시작 프레임을 인코딩한 시간과 동일한 시작 프레임을 뷰어에 디코딩할 때의 차이입니다.</p>
<p>평균 높음은 보기 환경에서 더 오래 지연 됩니다. 오버 로드 된 회의 서버는 평균 지연 시간을 겪을 수 있습니다. 기본값은 200ms입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverageAcceptable</strong></p></td>
<td><p>o</p></td>
<td></td>
<td><p>보기 세션 중에 회의 서버의 평균 RDP 타일 처리 대기 시간을 허용 하는 값입니다. 대기 시간은 서버 (공유자 또는 해당 시나리오에 따라)에서 시작 프레임을 인코딩한 시간과 동일한 시작 프레임을 뷰어에 디코딩할 때의 차이입니다.</p>
<p>평균 높음은 보기 환경에서 더 오래 지연 됩니다. 오버 로드 된 회의 서버는 평균 지연 시간을 겪을 수 있습니다. 기본값은 200ms입니다.</p>
<p>이 열은 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

