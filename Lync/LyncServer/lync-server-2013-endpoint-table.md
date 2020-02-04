---
title: 'Lync Server 2013: Endpoint 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11da225da1a8120f5de7ac21b3beb318326601f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a>Lync Server 2013의 Endpoint 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

끝점 테이블은 데이터베이스에 기록 된 세션에 참가 한 끝점에 대 한 정보를 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 끝점을 나타냅니다.


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
<th><strong>세부적인</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>EndpointKey</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p>이 끝점을 식별 하는 고유 번호입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>이름</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>독특한</p></td>
<td><p>끝점 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>변경할</strong></p></td>
<td><p>name</p></td>
<td><p> </p></td>
<td><p>끝점의 OS (운영 체제)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUName</strong></p></td>
<td><p>name</p></td>
<td></td>
<td><p>끝점의 CPU 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cpunum Of코어</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>끝점의 CPU 코어 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUProcessorSpeed</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>끝점의 CPU 프로세서 속도입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>VirtualizationFlag</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>시스템이 가상화 된 환경에서 실행 되 고 있는지를 나타내는 비트 플래그입니다.</p>
<ul>
<li><p>0x0000e-없음</p></li>
<li><p>0x0001 – HyperV</p></li>
<li><p>0x0002 – VMWare</p></li>
<li><p>0x0004-가상 PC</p></li>
<li><p>0x0008 – Xen PC</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

