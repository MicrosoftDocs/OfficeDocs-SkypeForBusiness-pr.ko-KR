---
title: 'Lync Server 2013: tblServerIdentity'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7bdd939f838a9f72191d3aae27b9a4a56d26be3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblserveridentity-in-lync-server-2013"></a>Lync Server 2013의 tblServerIdentity

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-12_

tblServerIdentity는 영구 채팅 서버 풀의 활성 채팅 서버를 포함 합니다.

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
<td><p>serverID</p></td>
<td><p>int, null 아님</p></td>
<td><p>서버 ID입니다. 중앙 관리 저장소의 인스턴스 ID에 해당 합니다.</p></td>
</tr>
<tr class="even">
<td><p>serverAddress</p></td>
<td><p>nvarchar (256), null 아님</p></td>
<td><p>Windows Communication Foundation 주소를 사용 하는 서버 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p>Serverlast(Time)</p></td>
<td><p>dmtf</p></td>
<td><p>채널 서버가이 행을 업데이트 하 여 증거를 실행 하 고 있음을 제공 하는 최근 시간입니다.</p></td>
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
<td><p>serverID</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

