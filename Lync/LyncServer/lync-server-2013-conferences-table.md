---
title: 'Lync Server 2013: Conferences 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17cbadaf18fa36ca55f7755b5e679e564163a207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a>Lync Server 2013의 Conferences 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-28_

이 테이블의 각 레코드에는 한 회의에 대 한 통화 정보가 포함 됩니다.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>주요한</p></td>
<td><p>전화 회의 요청이 CDR 에이전트에 의해 캡처 된 시간입니다. 회의 인스턴스를 고유 하 게 식별 하는 기본 키로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p>세션을 식별 하는 ID 번호입니다. 회의 인스턴스를 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>회의 URI. 자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>인스턴스</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p> </p></td>
<td><p>되풀이 회의에 유용 합니다. 각 되풀이 회의의 각 인스턴스는 동일한 <strong>ConferenceUri</strong>를 가지 지만 다양 한 다른 <strong>인스턴스</strong>를 보유 하 게 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p> </p></td>
<td><p>회의 시작 시간.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p> </p></td>
<td><p>회의 시작 시간.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>회의를 캡처한 풀을 식별 하는 ID 번호입니다. 자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>Int</p></td>
<td><p>외부</p></td>
<td><p>이 컨퍼런스의 이끌이 URI를 식별 하는 ID 번호입니다. 자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>플래그</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>컨퍼런스 특성을 포함 하는 비트 마스크입니다. 사용할 수 있는 값은 다음과 같습니다.</p>
<ul>
<li><p>0X01</p></li>
<li><p>종합적인</p></li>
<li><p>트랜잭션과</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>처리</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>모니터링 서비스에서 사용 하는 내부 필드입니다.</p>
<p>이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
</tbody>
</table>


\*대부분의 세션에서 SessionIdSeq에는 값 1이 사용 됩니다. 두 세션이 정확히 동시에 시작 되 면 1에 대 한 SessionIdSeq는 1이 되 고 다른 하나는 2가 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

