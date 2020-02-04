---
title: 'Lync Server 2013: Devices 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 381b03fc5680276a64fc327f423f74c6773c2ed3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a>Lync Server 2013의 Devices 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-05-25_

장치 테이블은 지원 테이블입니다. 각 레코드는 한 장치 (일반 전화기)에 대 한 정보를 저장 합니다.


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
<th>세부적인</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p>이 하드웨어 버전을 식별 하는 고유 번호입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ManufacturerId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>이 장치에 대 한 제조업체입니다. 자세한 내용은 <a href="lync-server-2013-manufacturers-table.md">Lync Server 2013의 제조업체 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>HardwareVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>이 장치에 대 한 하드웨어 버전. 자세한 내용은 <a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013의 HardwareVersions 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>MacAddress</strong></p></td>
<td><p>bigint</p></td>
<td></td>
<td><p>MAC 주소</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

