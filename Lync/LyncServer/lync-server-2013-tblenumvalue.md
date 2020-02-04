---
title: 'Lync Server 2013: tblEnumValue'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c09c5e911dcd63f50d8b15343075c5b3e05e631
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a>Lync Server 2013의 tblEnumValue

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-28_

tblEnumValue는 노드 테이블에 사용 되는 특성의 Visibility 및 Behavior 값을 포함 하는 하드 코드 된 테이블입니다.

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
<td><p>고 대 Eid</p></td>
<td><p>smallint, null이 아님</p></td>
<td><p>값의 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>smallint, null이 아님</p></td>
<td><p>특성의 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p>attributeValue</p></td>
<td><p>nvarchar (256), null 아님</p></td>
<td><p>값의 이름입니다.</p></td>
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
<td><p>고 대 Eid</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>TblEnumAttribute의 조회가 포함 되어 있는 외래 키입니다.</p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a>테이블 값

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>고 대 Eid</th>
<th>attributeID</th>
<th>attributeValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
<td><p>개인용</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>1</p></td>
<td><p>범위도</p></td>
</tr>
<tr class="odd">
<td><p>4(tcp/ipv4)</p></td>
<td><p>2</p></td>
<td><p>크기로</p></td>
</tr>
<tr class="even">
<td><p>5mb</p></td>
<td><p>2</p></td>
<td><p>auditorium</p></td>
</tr>
<tr class="odd">
<td><p>26</p></td>
<td><p>1</p></td>
<td><p>열면</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 tblNode](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

