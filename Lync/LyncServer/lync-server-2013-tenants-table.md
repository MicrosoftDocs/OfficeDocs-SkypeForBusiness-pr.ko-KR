---
title: 'Lync Server 2013: Tenants 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de776adeb8c280c5216b35cc8236a0834c14aa13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tenants-table-in-lync-server-2013"></a>Lync Server 2013의 Tenants 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-28_

테 넌 트 테이블은 다양 한 테 넌 트 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 테 넌 트를 나타냅니다.

<div>


> [!NOTE]  
> 온-프레미스 배포에서 CDR는 빌드에 테 넌 트 ID를 사용 하 여 공용 IM 연결, 페더레이션 및 익명 등의 다른 인증 유형을 나타냅니다.



</div>


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
<td><p><strong>TenantId</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p>이 테 넌 트 ID를 식별 하는 고유 번호입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>허용 되는 값:</p>
<ul>
<li><p>00000000-0000-0000-0000-000000000000 – 엔터프라이즈</p></li>
<li><p>00000000-0000-0000-0000-000000000001-페더레이션</p></li>
<li><p>00000000-0000-0000-0000-000000000002 – 익명</p></li>
<li><p>00000000-0000-0000-0000-000000000003-공용 메신저 연결</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

