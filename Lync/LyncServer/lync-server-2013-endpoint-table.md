---
title: 'Lync Server 2013: 끝점 테이블'
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
ms.openlocfilehash: 3a71e59b6cf9b4143a5b984cc7b169279aa2cb57
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533325"
---
# <a name="endpoint-table-in-lync-server-2013"></a>Lync Server 2013의 끝점 테이블

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-02_

끝점 테이블은 데이터베이스에 기록 된 세션에 참여 한 끝점에 대 한 정보를 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 끝점을 나타냅니다.


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
<td><p><strong>EndpointKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>이 끝점을 식별 하는 고유 번호입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>이름</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>고유한</p></td>
<td><p>끝점 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>르</strong></p></td>
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
<td><p><strong>CPUNumberOfCores</strong></p></td>
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
<li><p>에이 – 없음</p></li>
<li><p>0x0001 – HyperV</p></li>
<li><p>0x0002 – VMWare</p></li>
<li><p>0x0004-가상 PC</p></li>
<li><p>0x0008-Xen PC</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

