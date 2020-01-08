---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 725d097e1e2e75b6430974a4f133cb5fa4130346
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a>Lync Server 2013의 tblPrincipalType

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-12_

tblPrincipalType에는 tblPrincipal 테이블에 있는 항목을 분류 하는 principal 형식이 포함 되어 있습니다.

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
<td><p>ptypeID</p></td>
<td><p>smallint, null이 아님</p></td>
<td><p>Principal type ID.</p></td>
</tr>
<tr class="even">
<td><p>ptypeDesc</p></td>
<td><p>nvarchar (256), null 아님</p></td>
<td><p>형식에 대 한 설명입니다.</p></td>
</tr>
<tr class="odd">
<td><p>ptypeIsSystemUser</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>내부 용도에 사용 되는 주체에 해당 하는 형식인 경우 True입니다.</p></td>
</tr>
<tr class="even">
<td><p>ptypeIsUser</p></td>
<td><p>bit, null이 아님</p></td>
<td><p>형식이 사용자 형식인 경우 True입니다.</p></td>
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
<td><p>ptypeID</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a>Principal 값

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>I</th>
<th>역할</th>
<th>설명</th>
<th>사용자</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>이상</p></td>
<td><p>알려진 형식이 없는 일반 주체입니다. TblPrincipal 테이블에서 사용 되지 않습니다.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>AnyUser</p></td>
<td><p>사용자 유형의 일반 사용자입니다. TblPrincipal 테이블에서 사용 되지 않습니다.</p></td>
<td><p>예</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>AnyGroup</p></td>
<td><p>그룹 의미가 있는 일반 주체입니다. TblPrincipal 테이블에서 사용 되지 않습니다.</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>4(tcp/ipv4)</p></td>
<td><p>SystemUser</p></td>
<td><p>영구 채팅 서버에서 내부적으로 사용 하는 주체입니다.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>5mb</p></td>
<td><p>사용자</p></td>
<td><p>일반 사용자.</p></td>
<td><p>예</p></td>
</tr>
<tr class="even">
<td><p>20cm(8</p></td>
<td><p>DC</p></td>
<td><p>Active Directory 도메인 서비스 도메인 컨트롤러.</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>되었는지</p></td>
<td><p>그룹과</p></td>
<td><p>Active Directory 보안 그룹</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>1천만</p></td>
<td><p>폴더</p></td>
<td><p>Active Directory 컨테이너 또는 조직 구성 단위입니다.</p></td>
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

