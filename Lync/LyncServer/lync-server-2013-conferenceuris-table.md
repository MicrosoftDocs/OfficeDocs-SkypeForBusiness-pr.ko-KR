---
title: 'Lync Server 2013: ConferenceUris 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9142be1b2d46a7d7634394970d07dfa450a22e1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529175"
---
# <a name="conferenceuris-table-in-lync-server-2013"></a>Lync Server 2013의 ConferenceUris 테이블

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-05-25_

ConfereneUris 테이블은 데이터베이스에 기록 된 전화 회의 세션에 참가 한 다양 한 전화 회의 Uri 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 회의 URI를 나타냅니다.


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
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>내부 사용 시간 스탬프입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>이 회의 URI를 식별 하는 고유 번호입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td></td>
<td><p>전화 회의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>제외</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ConferenceUri의 체크섬입니다. 데이터베이스 검색 속도를 향상 시키는 데 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>오디오/비디오 회의에 대 한 회의: 음성 채팅에 대 한 대화 또는 전화: 오디오와 같은 URI 유형입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 테이블의 UriTypes 테이블</a> 을 참조 하십시오.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

