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
# <a name="videometricsthreshold-table-in-lync-server-2013"></a>Lync Server 2013의 VideoMetricsThreshold 테이블

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-02_

VideoMetricsThreshold 테이블은 비디오 통화에 사용되는 체감 품질 메트릭에 대한 최적의 값과 적절한 값을 포함합니다.


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
<th><strong>세부 정보</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>건 전화의 유형입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLROptimal</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>기본값은 0.05입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPostFECPLRAcceptable</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>기본값은 0.10입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>기본값은 5.0입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>기본값은 10.0입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverageOptimal</strong></p></td>
<td><p>10 진수 (9, 4)</p></td>
<td></td>
<td><p>기본값은 12.0000입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvFramerateAverageAcceptable</strong></p></td>
<td><p>10 진수 (9, 4)</p></td>
<td></td>
<td><p>기본값은 7.0000입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercentOptimal</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>기본값은 5.0입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowFrameRateCallPercentAcceptable</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>기본값은 10.0입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>LowResolutionCallPercentOptimal</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>기본값은 5.0입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercentAcceptable</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>기본값은 10.0입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPacketLossRateOptimal</strong></p></td>
<td><p>at</p></td>
<td></td>
<td><p>기본값은 0.05입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPacketLossRateAcceptable</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>기본값은 0.10입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFrameRateAvgOptimal</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>기본값은 12입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameRateAvgAcceptable</strong></p></td>
<td><p>식</p></td>
<td></td>
<td><p>기본값은 7입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DynamicCapabilityPercentOptimal</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>기본값은 5.00입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercentAcceptable</strong></p></td>
<td><p>10 진수 (5, 2)</p></td>
<td></td>
<td><p>기본값은 10.00입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

