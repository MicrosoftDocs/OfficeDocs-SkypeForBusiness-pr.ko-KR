---
title: 'Lync Server 2013: tblScopePrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece5ae542060835aefa05edb6e08b766293e2ac1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblscopeprincipal-in-lync-server-2013"></a>Lync Server 2013의 tblScopePrincipal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-12_

tblScopePrincipal에는 노드에 할당 된 범위가 포함 됩니다.

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
<td><p>scopeNodeID</p></td>
<td><p>int, null 아님</p></td>
<td><p>범위가 적용 되는 노드 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>scopePrinID</p></td>
<td><p>int, null 아님</p></td>
<td><p>Principal ID.</p></td>
</tr>
<tr class="odd">
<td><p>scopeIsDenied</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>범위 형식이 Deny 이면 True이 고, 그렇지 않으면 false입니다. 허용 하는 경우 False</p></td>
</tr>
<tr class="even">
<td><p>scopeUpdatedBy</p></td>
<td><p>int, null 아님</p></td>
<td><p>이 항목을 마지막으로 업데이트 한 사용자의 ID입니다.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>핵심

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
<td><p>&lt;scopeNodeID, scopePrinID&gt;</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
<tr class="even">
<td><p>scopeNodeID</p></td>
<td><p>NodeID 테이블에 조회를 포함 하는 외래 키입니다.</p></td>
</tr>
<tr class="odd">
<td><p>scopePrinID</p></td>
<td><p>TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

