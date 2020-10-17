---
title: 'Lync Server 2013: 회의 표'
description: 'Lync Server 2013: 회의 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference table
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425762(v=OCS.15)
ms:contentKeyID: 48183700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 565725b527399cb3be55c649dfd74d8bcb5f13a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550664"
---
# <a name="conference-table-in-lync-server-2013"></a>Lync Server 2013의 회의 테이블

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-02_

Conference 테이블은 지원 테이블입니다. 각 레코드는 하나의 회의 또는 피어-투-피어 세션을 나타냅니다.


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
<th><strong>세부 정보</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>이 회의 레코드를 식별하는 고유 번호입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfURI</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>고유한</p></td>
<td><p>항목이 회의인 경우 회의 URI이고 피어 투 피어 세션인 경우에는 DialogID입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>제외</strong></p></td>
<td><p>int</p></td>
<td><p>인덱스</p></td>
<td><p>회의 URI의 체크섬입니다. 내부적으로 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>내부 용도로만 사용됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

