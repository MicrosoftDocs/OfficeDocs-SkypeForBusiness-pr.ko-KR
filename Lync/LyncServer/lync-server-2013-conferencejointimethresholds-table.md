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
ms.openlocfilehash: baf29af4b9d1f2b026271b84cb54436e8f4b233f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a>Lync Server 2013의 ConferenceJoinTimeThresholds 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-28_

ConferenceJoinTimeThresholds 테이블에는 컨퍼런스 참가 시간 요약 보고서에 사용 되는 분류 경계가 포함 되어 있습니다. 컨퍼런스 참가 시간 요약 보고서에는 사용자가 회의에 참가 하는 데 필요한 시간 시간이 요약 되어 있습니다. 이러한 시간 값은 다음 범주 중 하 나와 평균으로 보고 됩니다.

  - 2 초 미만.

  - 2 초에서 5 초 사이입니다.

  - 5 초에서 10 초 사이입니다.

  - 10 초 이상

ConferenceJoinTimeThresholds 테이블에는 2 초, 5 초 및 10 초의 분류 값이 포함 됩니다.

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
<th>열</th>
<th>데이터 형식</th>
<th>키/인덱스</th>
<th>세부적인</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ThresholdId</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p>분류의 고유 식별자입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ThresholdValue</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>분류에 대 한 상한 값입니다. 사용 가능한 값은 다음과 같습니다.</p>
<ol>
<li><p>2</p></li>
<li><p>5mb</p></li>
<li><p>1천만</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

