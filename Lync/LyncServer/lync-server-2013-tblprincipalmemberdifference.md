---
title: 'Lync Server 2013: tblPrincipalMemberDifference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cfdd2ff1ca0c288738005c8d0740770e7c43319f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a>Lync Server 2013의 tblPrincipalMemberDifference

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-12_

tblPrincipalMemberDifference에는 이후 Active Directory 도메인 서비스 동기화 단계에서 아직 처리 되지 않은 그룹 구성원 자격 변경 내용 (추가 및 제거 된 구성원 모두)이 포함 됩니다.

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
<td><p>Principal.pringuid</p></td>
<td><p>GUID, null이 아님</p></td>
<td><p>변경된 그룹의 사용자 GUID입니다.</p></td>
</tr>
<tr class="even">
<td><p>memberADPath</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>구성원의 고유 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>memberRemoved 됨</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>구성원이 추가된 경우 False입니다. 구성원이 제거된 경우 True입니다.</p></td>
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
<td><p>&lt;Principal.pringuid, memberADPath&gt;</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

