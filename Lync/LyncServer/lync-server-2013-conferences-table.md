---
title: 'Lync Server 2013: 회의 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef5e8811ad4b0adaccd8964e2f0bca718ca531e2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529265"
---
# <a name="conferences-table-in-lync-server-2013"></a>Lync Server 2013의 회의 테이블

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

이 테이블의 각 레코드에는 하나의 회의에 대 한 통화 정보가 포함 되어 있습니다.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>전화 회의 요청이 CDR 에이전트에 의해 캡처된 시간입니다. 전화 회의 인스턴스를 고유 하 게 식별 하기 위한 기본 키로만 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>세션을 식별하기 위한 ID 번호입니다. <strong>Sessionidtime</strong> 과 함께 회의 인스턴스를 고유 하 게 식별 하는 데 사용 됩니다. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>전화 회의 URI입니다. 자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>인스턴스</strong></p></td>
<td><p>고유</p></td>
<td><p> </p></td>
<td><p>되풀이 회의에 유용 합니다. 되풀이 되는 회의의 각 인스턴스는 동일한 <strong>ConferenceUri</strong>을 갖고 있지만 서로 다른 <strong>인스턴스</strong>를 갖게 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>회의 시작 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>회의 시작 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>전화 회의를 캡처한 풀을 식별 하는 ID 번호입니다. 자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>임계값</p></td>
<td><p>외부</p></td>
<td><p>이 회의의 이끌이 URI를 식별 하는 ID 번호입니다. 자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>플래그가</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>전화 회의 특성을 포함 하는 비트 마스크입니다. 가능한 값은 다음과 같습니다.</p>
<ul>
<li><p>0X01</p></li>
<li><p>통합</p></li>
<li><p>트랜잭션</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>전처리</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>모니터링 서비스에서 사용 하는 내부 필드입니다.</p>
<p>이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
</tbody>
</table>


\* 대부분의 세션에서 SessionIdSeq는 값 1을 갖습니다. 두 세션을 정확히 동시에 시작 하는 경우에는 1을 위한 SessionIdSeq를 사용할 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

