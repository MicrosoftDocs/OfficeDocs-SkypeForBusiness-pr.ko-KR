---
title: 'Lync Server 2013: VoipDetails 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3d41021016d6d6e21e7112597bb6206dc46d95
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a>Lync Server 2013의 VoipDetails 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

각 레코드는 적어도 한 명의 사용자가 VoIP 사용자인 하나의 두 사용자 간 통화를 나타냅니다.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>세션 요청 시간입니다. <strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>세션을 식별하기 위한 ID 번호입니다. <strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>From번호 번호</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>발신자의 <strong>PhoneId</strong>입니다. 자세한 내용은 <a href="lync-server-2013-phones-table.md">Lync Server 2013의 phone 테이블</a> 을 참조 하십시오. NULL이 아니고 <strong>FromGatewayId</strong>가 NULL이 아니면 발신자가 PSTN 사용자입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectedNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화 수신자의 <strong>PhoneId</strong>입니다. 자세한 내용은 <a href="lync-server-2013-phones-table.md">Lync Server 2013의 phone 테이블</a> 을 참조 하십시오. NULL이 아니고 <strong>ToGatewayId</strong>가 NULL이 아니면 통화 수신자가 PSTN 사용자입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화의 발신측 중재 서버입니다. 자세한 내용은 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013에서 Mediationservers 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화의 수신측 중재 서버입니다. 자세한 내용은 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013에서 Mediationservers 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화의 발신측 게이트웨이입니다. 자세한 내용은 <a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화의 수신측 게이트웨이입니다. 자세한 내용은 <a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedbyURIId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>사용자가 URI를 갖고 있는 경우 통화 연결을 끊은 사용자의 URI입니다. 자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedbyPhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>전화에서 연결을 끊은 경우 통화 연결을 끊은 전화의 ID입니다. 자세한 내용은 <a href="lync-server-2013-phones-table.md">Lync Server 2013의 phone 테이블</a> 을 참조 하십시오.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

