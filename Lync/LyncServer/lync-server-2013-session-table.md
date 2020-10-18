---
title: 'Lync Server 2013: Session 테이블'
description: 'Lync Server 2013: Session 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1a52813dfea808253cc934f71a9d4c846c2dbbd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576454"
---
# <a name="session-table-in-lync-server-2013"></a>Lync Server 2013의 Session 테이블

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-09-09_

각 레코드는 오디오 또는 오디오/비디오를 포함 하는 하나의 세션을 나타냅니다. 세션에 대 한 전체 정보를 포함 합니다. 세션은 두 끝점 간에 오디오 또는 비디오 세션 시작 프로토콜 (SIP) 대화 상자로 정의 됩니다.


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
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-dialog-table.md">Lync Server 2013의 Dialog 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-dialog-table.md">Lync Server 2013의 Dialog 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>전화 회의 키 <a href="lync-server-2013-conference-table.md">Lync Server 2013의 회의 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>상관 관계 키입니다. <a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013의 Sessioncorrelation 관계 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>비트만</p></td>
<td><p> </p></td>
<td><p>대화 상자 범주 0은 중재 서버 레그에 대 한 Lync Server입니다. 1은 PSTN 게이트웨이 레그에 대 한 중재 서버입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>통화가 바이패스되었는지 여부를 나타내는 플래그입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>이 필드(제공된 경우)는 우회 ID가 일치했어도 통화가 우회되지 않은 이유를 나타냅니다. Lync Server의 경우 한 가지 값만 정의 됩니다.</p>
<p>0x0001 -  기본 네트워크 어댑터에 대한 알 수 없는 바이패스 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>통화 시작 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>통화 종료 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>발신자의 풀입니다. <a href="lync-server-2013-pool-table.md">Lync Server 2013의 Pool 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화 수신기 풀입니다. <a href="lync-server-2013-pool-table.md">Lync Server 2013의 Pool 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>수신 끝점의 SIP p-어설션된 id (PAI)에 있는 SIP URI입니다. <a href="lync-server-2013-user-table.md">Lync Server 2013의 User 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>발신자의 URI입니다. <a href="lync-server-2013-user-table.md">Lync Server 2013의 User 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>발신자의 끝점입니다. <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 끝점 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>비트만</p></td>
<td><p>외부</p></td>
<td><p>발신자의 사용자 에이전트 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>이 통화의 우선 순위입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>이 열은 더 이상 사용 되지 않으며 Microsoft Lync Server 2013에서 사용 되지 않습니다. 대신이 정보는 미디어 단위 회선 기반에 보고 됩니다. 자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialofftable</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>P-어설션된-통화를 시작한 사용자의 Id입니다. P-어설션된-Identity (PAI)는 통화를 시작한 사용자의 실제 id를 전달 하는 데 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 받은 끝점입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 받은 사용자가 사용 하는 사용자 에이전트입니다. 사용자 에이전트는 클라이언트 끝점 장치를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 받은 사용자의 SIP URI입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

