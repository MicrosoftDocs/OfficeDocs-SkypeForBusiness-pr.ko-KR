---
title: 'Lync Server 2013: tblComplianceParticipant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 484948a01c82dc8ca256e3e50e484c94a9b81de4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a>Lync Server 2013의 tblComplianceParticipant

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-12_

tblComplianceParticipant에는 채널당 현재 참가자와 서버 별로 포함 됩니다.

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
<td><p>channelUri</p></td>
<td><p>nvarchar (255), null 아님</p></td>
<td><p>채널 URI (Uniform Resource Identifier)입니다.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, null 아님</p></td>
<td><p>참가자의 사용자 ID (tblPrincipal 테이블에 해당)</p></td>
</tr>
<tr class="odd">
<td><p>에서 joinedAt</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>참가 이벤트의 타임 스탬프입니다.</p></td>
</tr>
<tr class="even">
<td><p>partedAt</p></td>
<td><p>bigint</p></td>
<td><p>참가자가 아직 참가 한 경우 Null입니다. Null이 아닌 경우 이벤트를 종료 하는 채널의 타임 스탬프입니다.</p>
<p>이러한 항목은 모든 번역기가 이벤트를 처리할 때 결국 제거 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>userUri</p></td>
<td><p>nvarchar (255), null 아님</p></td>
<td><p>사용자 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p>serverID</p></td>
<td><p>int</p></td>
<td><p>서버 id (tblServerIdentity 테이블에 해당)</p></td>
</tr>
<tr class="odd">
<td><p>Session</p></td>
<td><p>bigint</p></td>
<td><p>서버 세션. 채팅 서비스를 시작할 때마다 생성 되는 난수입니다. 고아 참가자를 식별 하기 위해 세션을 구분 하는 데 사용 됩니다.</p></td>
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
<td><p>&lt;channelUri, userId, joinedAt&gt;</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

