---
title: 'Lync Server 2013: SIPResponseMetaData 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 164c6e1541869a2976f283443f2fae9246f28007
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Lync Server 2013의 SIPResponseMetaData 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

SIPResponseMetaDataTable에는 SIP 응답 코드 목록과 이러한 각 코드의 분류 및 정의가 포함 되어 있습니다. 이러한 코드는 SIP 장치 및 SIP 통신 세션에 영향을 주는 이벤트에 대 한 응답으로 생성 됩니다. 예를 들어 응답 코드 403는 SIP 장치에서 요청을 할 때 생성 되지만 서버에서 해당 요청을 사용 하는 것을 거절 합니다.

이 표는 Microsoft Lync Server 2013에 도입 되었습니다.


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
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>SIP 응답 코드를 나타내는 숫자 값입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>클래스</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>응답 코드에 대 한 일반 분류입니다. 분류에는 다음이 포함 됩니다.</p>
<ul>
<li><p>1 – 정보 응답</p></li>
<li><p>2-성공적인 응답</p></li>
<li><p>3 – 리디렉션 응답</p></li>
<li><p>4-클라이언트 오류 응답</p></li>
<li><p>5--서버 오류 응답</p></li>
<li><p>6 – 전역 오류 응답</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>설명</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>SIP 응답 코드에 대 한 설명입니다. 예를 들어, 응답 코드 181에는 다음 설명이 포함 됩니다.</p>
<p>착신 전환 중</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

