---
title: 'Lync Server 2013: tblPrincipalRole'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4da9525e81856989c5d5046e43b2277ca6a8b2a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a>Lync Server 2013의 tblPrincipalRole

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-12_

tblPrincipalRole 테이블에는 노드에 할당된 명시적 역할이 포함됩니다.

### <a name="columns"></a>단

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>열</th>
<th>형식</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Principalrole.prinrolenodeid</p></td>
<td><p>int, null이 아님</p></td>
<td><p>해당 역할이 적용되는 노드 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>Principalrole.prinroleprinid</p></td>
<td><p>int, null이 아님</p></td>
<td><p>사용자 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p>Principalrole.prinroletypeid</p></td>
<td><p>int, null이 아님</p></td>
<td><p>역할 유형 ID(tblRoleType)입니다.</p></td>
</tr>
<tr class="even">
<td><p>prinRoleUpdatedBy</p></td>
<td><p>int, null이 아님</p></td>
<td><p>이 항목을 마지막으로 업데이트한 사용자의 ID입니다.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>키

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
<td><p>&lt;Principalrole.prinrolenodeid, Principalrole.prinroleprinid, Principalrole.prinroletypeid&gt;</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
<tr class="even">
<td><p>Principalrole.prinrolenodeid</p></td>
<td><p>tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</p></td>
</tr>
<tr class="odd">
<td><p>Principalrole.prinroleprinid</p></td>
<td><p>tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</p></td>
</tr>
<tr class="even">
<td><p>Principalrole.prinroletypeid</p></td>
<td><p>tblRoleType.rtypeID 테이블에서 조회 기능이 있는 외래 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

