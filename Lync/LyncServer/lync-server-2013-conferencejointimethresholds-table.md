---
title: 'Lync Server 2013: ConferenceJoinTimeThresholds 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d8dcf3d8b5f74abe6e145d7ac25e43411ca085c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502315"
---
# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a>Lync Server 2013의 ConferenceJoinTimeThresholds 테이블

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

ConferenceJoinTimeThresholds 테이블에는 회의 참가 시간 요약 보고서에서 사용하는 분류 경계가 포함됩니다. 회의 참가 시간 요약 보고서에는 사용자가 회의에 정상적으로 참가하는 데 걸리는 시간이 요약되어 있습니다. 이러한 시간 값은 평균 및 다음 범주 중 하나로 보고됩니다.

  - 2초 미만

  - 2~5초

  - 5~10초

  - 10초 초과

ConferenceJoinTimeThresholds 테이블에는 분류 값 2초, 5초, 10초가 포함됩니다.

이 표는 Microsoft Lync Server 2013에 도입 되었습니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>열</th>
<th>데이터 형식</th>
<th>키/인덱스</th>
<th>세부 정보</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ThresholdId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>분류의 고유한 식별자입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ThresholdValue</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>분류의 상한입니다. 허용되는 값은 다음과 같습니다.</p>
<ol>
<li><p>2</p></li>
<li><p>5 </p></li>
<li><p>10  </p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

