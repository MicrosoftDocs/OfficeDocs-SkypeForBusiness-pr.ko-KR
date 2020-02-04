---
title: 'Lync Server 2013: UserAgent 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25d1cd6b48b09ad3083499ec3f173772d242ba6b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a>Lync Server 2013의 UserAgent 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-05-25_

UserAgent 테이블은 데이터베이스에 기록 된 세션에 참가 한 다양 한 사용자 에이전트의 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 한 명의 사용자 에이전트를 나타냅니다.


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
<td><p><strong>UserAgentKey</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p>이 사용자 에이전트를 식별 하는 고유 번호입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserAgent</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>독특한</p></td>
<td><p>사용자 에이전트 문자열입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UAType</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>1은 중재 서버입니다.</p>
<p>2는 A/V 회의 서버입니다.</p>
<p>4 님이 Lync입니다.</p>
<p>8은 IP 전화입니다.</p>
<p>16 개는 Live Meeting Console입니다.</p>
<p>32는 DVT (배포 유효성 검사 도구)입니다.</p>
<p>64는 Macintosh 컴퓨터의 Lync입니다.</p>
<p>128는 Office Communications Server 2007 R2 수행자입니다.</p>
<p>256는 회의 알림 서비스입니다.</p>
<p>512는 회의 자동 전화 교환입니다.</p>
<p>1024는 응답 그룹 응용 프로그램입니다.</p>
<p>2048는 음성 제어를 벗어납니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

