---
title: 'Lync Server 2013: Pool 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Pool table
ms:assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398746(v=OCS.15)
ms:contentKeyID: 48184803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08f878b9eefef86fba0fed4dd039b9a60b6f035d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pool-table-in-lync-server-2013"></a>Lync Server 2013의 Pool 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

풀 테이블은 다양 한 프런트 엔드 풀에 대 한 정보를 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 풀을 나타냅니다.


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
<td><p><strong>PoolKey</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p>이 풀을 식별 하는 고유 번호입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolName</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>독특한 </p></td>
<td><p>풀 FQDN.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

