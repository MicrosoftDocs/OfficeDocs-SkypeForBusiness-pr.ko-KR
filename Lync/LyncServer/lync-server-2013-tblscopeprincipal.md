---
title: 'Lync Server 2013: tblScopePrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558639(v=OCS.15)
ms:contentKeyID: 48184009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8263369e9224c4a3aeb20bbb664392fbe3ba7c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536285"
---
# <a name="tblscopeprincipal-in-lync-server-2013"></a>Lync Server 2013의 tblScopePrincipal

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-12_

tblScopePrincipal에는 노드에 지정된 범위가 포함됩니다.

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
<th>유형</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Scopeprincipal.scopenodeid</p></td>
<td><p>int, null이 아님</p></td>
<td><p>해당 범위가 적용되는 노드 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>Scopeprincipal.scopeprinid</p></td>
<td><p>int, null이 아님</p></td>
<td><p>사용자 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p>scopeIsDenied</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>범위 유형이 Deny인 경우 True이고 Allow이면 False입니다.</p></td>
</tr>
<tr class="even">
<td><p>scopeUpdatedBy</p></td>
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
<td><p>&lt;Scopeprincipal.scopenodeid, Scopeprincipal.scopeprinid&gt;</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
<tr class="even">
<td><p>Scopeprincipal.scopenodeid</p></td>
<td><p>tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</p></td>
</tr>
<tr class="odd">
<td><p>Scopeprincipal.scopeprinid</p></td>
<td><p>tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

