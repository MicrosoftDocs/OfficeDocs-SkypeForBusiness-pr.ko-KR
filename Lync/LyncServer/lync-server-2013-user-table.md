---
title: 'Lync Server 2013: User 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4baaf8b8dea0f9e5aa77986791c82051fc00e90b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a>Lync Server 2013의 User 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

사용자 테이블은 데이터베이스에 기록 된 세션에 참가 한 다양 한 사용자의 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 한 명의 사용자를 나타냅니다.


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
<td><p><strong>UserKey</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p>이 사용자를 식별 하는 고유 번호입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>URL</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>독특한</p></td>
<td><p>URI 문자열입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URIType</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>1은 알 수 없는 URI 형식입니다.</p>
<p>2는 사용자 URI입니다.</p>
<p>4는 회의 URI입니다.</p>
<p>8은 phone URI입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>테 넌 트 테이블에서 참조 하는 사용자의 테 넌 트입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LastPoorCallTime</strong></p></td>
<td><p>dmtf</p></td>
<td></td>
<td><p>사용자가 음성 통화에 좋지 않은 경우의 최신 타임 스탬프입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>dmtf</p></td>
<td></td>
<td><p>내부용 으로만 사용 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

