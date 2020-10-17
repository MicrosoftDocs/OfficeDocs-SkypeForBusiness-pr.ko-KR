---
title: 'Lync Server 2013: TraceRoute 테이블'
description: 'Lync Server 2013: TraceRoute 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af33e572065fbab1eaaaef684997e7f95edaed9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549064"
---
# <a name="traceroute-table-in-lync-server-2013"></a>Lync Server 2013의 TraceRoute 테이블

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-21_

TraceRoute 테이블에는 통화의 라우팅 정보가 포함 됩니다. 이 표는 Microsoft Lync Server 2013에 도입 되었습니다.


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
<td><p><strong>Conferencedatetime이 동일할</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>통화가 시작 된 날짜 및 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>같은 날짜와 시간에 시작 되었을 수 있는 여러 통화를 구분 하는 데 사용 되는 고유 식별자입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>통화에서 사용되는 비디오 라인의 유형을 나타냅니다. 허용되는 값은 다음과 같습니다.</p>
<ul>
<li><p>0-오디오</p></li>
<li><p>1-비디오</p></li>
<li><p>2 -- 파노라마 비디오</p></li>
<li><p>3-응용 프로그램/데스크톱 공유</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>비트만</p></td>
<td><p>Primary</p></td>
<td><p>통화를 시작한 끝점입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>통과할</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>네트워크 홉/</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>IP 주소에 대 한 고유 식별자입니다. IP 주소 정보는 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013의 IPAddress 테이블</a>에 저장 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RTT</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>왕복 시간입니다. 왕복 시간은 음성 패킷이 대상에 도달 하는 데 걸리는 시간을 측정 한 다음 수신 된 알림을 다시 전송 합니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

