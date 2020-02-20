---
title: 'Lync Server 2013: 미디어 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92bd1abb28b74fe7f2c46ad89d713a9b6244f4c3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a>Lync Server 2013의 미디어 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

각 레코드는 피어-투-피어 세션에 사용된 하나의 미디어 유형을 나타냅니다. 둘 이상의 미디어 유형이 사용된 경우 하나의 세션이 테이블에 여러 레코드로 표시됩니다.

<div>


> [!NOTE]  
> Media 테이블을 사용하여 세션의 미디어 기간을 계산해서는 안 됩니다. 이 테이블에는 세션에 포함된 미디어 교환의 신호 세부 정보가 포함됩니다. 미디어 교환은 INVITE 요청에 의해 수행되며 StartTime은 INVITE가 전송된 시간을 나타냅니다. 미디어는 세션 참가자가 세션을 수락한 후에만 시작되므로 초대 시간이 반드시 미디어 시작 시간인 것은 아닙니다. EndTime은 일반적으로 이 세션의 종료 시간을 의미합니다.



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
<th>세부 정보</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>세션 요청 시간입니다. <strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>세션을 식별하기 위한 ID 번호입니다. <strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>이 미디어 유형을 식별하는 고유 번호입니다. 자세한 내용은 <a href="lync-server-2013-medialist-table.md">Lync Server 2013에서 Medialist 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>실제 미디어 시작 시간이 아니라 미디어 요청이 전송된 시간입니다. <strong>StartTime</strong>에는 세션 설정 시간이 포함됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>세션의 종료 시간입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

