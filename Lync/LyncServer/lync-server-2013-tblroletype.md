---
title: 'Lync Server 2013: tblRoleType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba6b5041453b0965fafc12ada2be62ec42316f89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a>Lync Server 2013의 tblRoleType

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-25_

tblRoleType는 역할 유형 및 연결 된 사용 권한 집합을 포함 하는 정적 조회 테이블입니다.

### <a name="columns"></a>열

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>열</th>
<th>유형</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>rtypeID</p></td>
<td><p>int, null 아님</p></td>
<td><p>역할 유형 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>nvarchar (256), null 아님</p></td>
<td><p>역할 유형 설명입니다. 사용할 수 있는 역할은 네 가지가 있습니다.</p>
<ul>
<li><p>회원: 채팅방 구성원</p></li>
<li><p>관리자: 채팅방 관리자</p></li>
<li><p>않지만: auditorium 채팅방의 발표자</p></li>
<li><p>작성자: 채팅방을 만들 수 있습니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>역할에 대 한 사용 권한 집합입니다. 사용 되는 비트는 다음과 같습니다.</p>
<ul>
<li><p>2: 역할이 노드를 관리할 수 있는 경우 True입니다.</p></li>
<li><p>4: 역할이 자식 노드를 만들 수 있는 경우 True입니다.</p></li>
<li><p>7: 역할이 채팅방에 참가할 수 있으면 True이 고, 그렇지 않은 경우에는 범주에 있는 채팅방을 어린이에 게 보세요.</p></li>
<li><p>8: 역할이 채팅방에서 채팅을 할 수 있으면 True이 고, 그렇지 않은 경우에는 범주의 채팅방을 어린이에 게 보세요.</p></li>
<li><p>10: 채팅방에 참가 하지 않은 경우에도 역할이 채팅 기록을 읽을 수 있는 경우 True입니다.</p></li>
<li><p>11: 역할이 채팅방을 볼 수 있으면 True입니다. (범위 및 표시 유형 등의 요인에 따라 구체화 됩니다.)</p></li>
<li><p>12: 역할이 auditorium 채팅방에서 채팅을 할 수 있는 경우 True입니다.</p></li>
<li><p>13: 역할이 노드를 볼 때 표시 규칙을 무시할 수 있는 경우 True입니다.</p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a>키

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>열</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>rtypeID</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

