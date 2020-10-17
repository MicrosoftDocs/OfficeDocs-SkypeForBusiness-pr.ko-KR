---
title: 'Lync Server 2013: CallType 테이블'
description: 'Lync Server 2013: CallType 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallType table
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412752(v=OCS.15)
ms:contentKeyID: 48185019
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af9c40396b993893f5157b89bedff0d80d87eb0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565174"
---
# <a name="calltype-table-in-lync-server-2013"></a>Lync Server 2013의 CallType 테이블

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

CallType 테이블은 사용 가능한 통화 유형 목록이 저장된 정적 테이블입니다.


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
<td><p><strong>CallTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>CallType</strong></p></td>
<td><p>varchar</p></td>
<td></td>
<td><p>허용되는 값은 다음과 같습니다.</p>
<ul>
<li><p>0 -- 알 수 없음</p></li>
<li><p>1 -- 인스턴트 메시징</p></li>
<li><p>2--응용 프로그램 공유</p></li>
<li><p>3 -- 오디오</p></li>
<li><p>4 -- 오디오 및 비디오</p></li>
<li><p>5 -- 파일 전송</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

