---
title: 'Lync Server 2013: ErrorCategory 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9bd9cebf26a147b00873c17372eca77f0a11f2d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a>Lync Server 2013의 ErrorCategory 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-08-20_

ErrorCategory 테이블에는 각 Microsoft Lync Server 2013 진단 분류에 대 한 친근 한 이름이 있습니다. 기본적으로 Lync Server 2013는 다음과 같은 분류를 사용 합니다.

  - 0--성공

  - 1--실패 예상

  - 2-예기치 않은 오류

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
<td><p><strong>CategoryId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>주요한</p></td>
<td><p>분류의 고유 식별자입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>이름</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>분류에 할당 된 값 및 식별 이름입니다. 사용 가능한 값은 다음과 같습니다.</p>
<ul>
<li><p>0--성공</p></li>
<li><p>1--실패 예상</p></li>
<li><p>2-예기치 않은 오류</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

