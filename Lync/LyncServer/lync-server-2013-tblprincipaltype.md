---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4da3af65a20d13ce4d4f1078e5ef76cbc67f402c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a>Lync Server 2013의 tblPrincipalType

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-12_

tblPrincipalType에는 tblPrincipal 테이블에 있는 항목을 분류하기 위한 사용자 유형이 포함됩니다.

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
<td><p>Tblprincipaltype.ptypeid</p></td>
<td><p>smallint, null이 아님</p></td>
<td><p>사용자 유형 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>nvarchar(256), null이 아님</p></td>
<td><p>유형에 대한 설명입니다.</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>유형이 내부 용도로 사용되는 사용자에 해당하는 경우 True입니다.</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>유형이 사용자 유형인 경우 True입니다.</p></td>
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
<td><p>Tblprincipaltype.ptypeid</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a>사용자 값

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>역할</th>
<th>설명</th>
<th>사용자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1 </p></td>
<td><p>모두</p></td>
<td><p>유형이 알려지지 않은 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>2 </p></td>
<td><p>AnyUser</p></td>
<td><p>사용자 유형의 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.</p></td>
<td><p>예</p></td>
</tr>
<tr class="odd">
<td><p>3 </p></td>
<td><p>AnyGroup</p></td>
<td><p>그룹 체계를 포함하는 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>SystemUser</p></td>
<td><p>영구 채팅 서버에서 내부적으로 사용 되는 보안 주체입니다.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>5 </p></td>
<td><p>사용자</p></td>
<td><p>일반 사용자입니다.</p></td>
<td><p>예</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>AD</p></td>
<td><p>Active Directory 도메인 서비스 도메인 컨트롤러입니다.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>Group</p></td>
<td><p>Active Directory 보안 그룹입니다.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>편지함</p></td>
<td><p>Active Directory 컨테이너 또는 조직 단위입니다.</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 tblPrincipal](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

