---
title: 'Lync Server 2013: VoipDetails 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7879f5dc7d5b884dfc2d3777ed4fa800978a3cff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a>Lync Server 2013의 VoipDetails 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-28_

각 레코드는 하나 이상의 사용자가 VoIP 사용자 인 1 2-파티 통화를 나타냅니다.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>주요한</p></td>
<td><p>세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 <strong>Sessionidseq</strong> 와 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p>세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>From번호 번호</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>발신자의 <strong>PhoneId</strong> . 자세한 내용은 <a href="lync-server-2013-phones-table.md">Lync Server 2013의 전화 테이블</a> 을 참조 하세요. NULL이 아니고 <strong>FromGatewayId</strong> 가 null이 아니면 호출자는 PSTN 사용자입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectedNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화 수신기의 <strong>PhoneId</strong> . 자세한 내용은 <a href="lync-server-2013-phones-table.md">Lync Server 2013의 전화 테이블</a> 을 참조 하세요. NULL이 아니고 <strong>ToGatewayId</strong> 가 null이 아니면 통화 수신기는 PSTN 사용자입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 보내는 중재 서버입니다. 자세한 내용은 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013의 Mediationservers 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>호출 되는 중재 서버. 자세한 내용은 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013의 Mediationservers 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 보내는 게이트웨이. 자세한 내용은 <a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>전화를 받는 게이트웨이 자세한 내용은 <a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedbyURIId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>사용자에 게 URI가 있는 경우 전화를 끊은 사용자의 URI입니다. 자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedbyPhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 끊은 전화의 ID가 휴대폰에서 연결이 끊어졌습니다. 자세한 내용은 <a href="lync-server-2013-phones-table.md">Lync Server 2013의 전화 테이블</a> 을 참조 하세요.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

