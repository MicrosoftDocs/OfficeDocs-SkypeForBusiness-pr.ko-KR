---
title: 'Lync Server 2013: tblServerIdentity'
description: 'Lync Server 2013: tblServerIdentity'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e954618cb373f2cf4f1b7ed929c3aaf6d8875e92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564534"
---
# <a name="tblserveridentity-in-lync-server-2013"></a>Lync Server 2013의 tblServerIdentity

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-12_

tblServerIdentity에는 영구 채팅 서버 풀의 활성 채팅 서버가 포함 되어 있습니다.

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
<th>유형</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>serverID</p></td>
<td><p>int, null이 아님</p></td>
<td><p>서버 ID입니다. 중앙 관리 저장소의 인스턴스 ID에 해당 합니다.</p></td>
</tr>
<tr class="even">
<td><p>serverAddress</p></td>
<td><p>nvarchar(256), null이 아님</p></td>
<td><p>Windows Communication Foundation 주소를 사용 중인 서버 주소입니다.</p></td>
</tr>
<tr class="odd">
<td><p>Serverlast(Time)</p></td>
<td><p>datetime</p></td>
<td><p>실행 중임에 대한 증거를 제공하기 위해 채널 서버가 이 행을 마지막으로 업데이트한 시간입니다.</p></td>
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

