---
title: 'Lync Server 2013: 장애 조치(failover) 경로 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e65070326c82e3a30977b3512bd2785d6bb4bd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a>Lync Server 2013에서 장애 조치(failover) 경로 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

다음 예에서는 관리자가 GW1에서 유지 관리를 위해 중단 되거나 사용할 수 없는 경우에 사용할 장애 조치 경로를 정의 하는 방법을 보여 줍니다. 다음 표에는 필요한 구성 변경 내용이 설명 되어 있습니다.

### <a name="table-1-user-policy"></a>표 1 사용자 정책

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>사용자 정책</th>
<th>전화 사용</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>기본 통화 정책</p></td>
<td><p>로컬</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
<tr class="even">
<td><p>Redmond 로컬 정책</p></td>
<td><p>RedmondLocal</p></td>
</tr>
<tr class="odd">
<td><p>달라스 호출 정책</p></td>
<td><p>DallasUsers</p>
<p>GlobalPSTNHopoff</p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a>표 2. 경로도

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>경로 이름</th>
<th>번호 패턴</th>
<th>전화 사용</th>
<th>트렁크</th>
<th>게이트웨이와</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Redmond 로컬 경로</p></td>
<td><p>^\+1 (425 | 206 | 253) (\d{7}) $</p></td>
<td><p>로컬</p>
<p>RedmondLocal</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p></td>
<td><p>빨강-GW1</p>
<p>빨강-GW2</p></td>
</tr>
<tr class="even">
<td><p>달라스 로컬 경로</p></td>
<td><p>^\+1 (972 | 214 | 469) (\d{7}) $</p></td>
<td><p>로컬</p></td>
<td><p>Trunk3</p></td>
<td><p>달라스-GW1</p></td>
</tr>
<tr class="odd">
<td><p>유니버설 경로</p></td>
<td><p>^\+? (\d *) $</p></td>
<td><p>GlobalPSTNHopoff</p></td>
<td><p>Trunk1</p>
<p>Trunk2</p>
<p>Trunk3</p></td>
<td><p>빨강-GW1</p>
<p>빨강-GW2</p>
<p>달라스-GW1</p></td>
</tr>
<tr class="even">
<td><p>달라스 사용자 라우팅</p></td>
<td><p>^\+? (\d *) $</p></td>
<td><p>DallasUsers</p></td>
<td><p>Trunk3</p></td>
<td><p>달라스-GW1</p></td>
</tr>
</tbody>
</table>


표 1에서 GlobalPSTNHopoff의 전화 사용은 달라스 호출 정책의 DallasUsers 전화 사용 후에 추가 됩니다. 이렇게 하면 DallasUsers 전화 사용에 대 한 경로를 사용할 수 없는 경우 달라스 호출 정책으로 전화를 걸 때 GlobalPSTNHopoff 전화 사용에 대해 구성 된 경로를 사용할 수 있습니다.

</div>

<span> </span>

</div>

</div>

</div>

