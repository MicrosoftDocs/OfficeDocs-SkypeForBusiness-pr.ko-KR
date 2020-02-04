---
title: 'Lync Server 2013: Session 테이블'
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
ms.openlocfilehash: 81b97d6a7521add62817147ae87995508b841f2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a>Lync Server 2013의 Session 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-09-09_

각 레코드는 오디오 또는 오디오 및 비디오를 포함 하는 하나의 세션을 나타냅니다. 세션에 대 한 전반적인 정보를 포함 합니다. 세션은 두 끝점 간에 오디오 또는 SIP (비디오 세션 초기화 프로토콜) 대화 상자로 정의 됩니다.


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
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>주요한</p></td>
<td><p><a href="lync-server-2013-dialog-table.md">Lync Server 2013의 대화 상자 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p><a href="lync-server-2013-dialog-table.md">Lync Server 2013의 대화 상자 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>회의 키입니다. <a href="lync-server-2013-conference-table.md">Lync Server 2013의 컨퍼런스 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>상관 관계 키입니다. <a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013의 Sessioncorrelation 관계 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>다소</p></td>
<td><p> </p></td>
<td><p>대화 상자 범주 0은 서버 레그 조정을 위한 Lync Server입니다. 1이 (가) PSTN 게이트웨이 레그로 서버를 중재 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>통화가 바이패스 되었는지 여부를 나타내는 플래그입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>이 필드에는 바이패스 Id가 일치 하는 경우에도 통화가 무시 되지 않은 이유가 표시 됩니다. Lync Server의 경우 하나의 값만 정의 됩니다.</p>
<p>0x0001-기본 네트워크 어댑터에 대 한 알 수 없는 바이패스 ID.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p> </p></td>
<td><p>통화 시작 시간.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p> </p></td>
<td><p>통화 종료 시간.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>호출자의 풀입니다. <a href="lync-server-2013-pool-table.md">Lync Server 2013의 풀 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화 수신기 풀입니다. <a href="lync-server-2013-pool-table.md">Lync Server 2013의 풀 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>수신 끝점의 SIP p-어설션된 id (PAI)의 SIP URI입니다. <a href="lync-server-2013-user-table.md">Lync Server 2013의 사용자 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>호출자의 URI입니다. <a href="lync-server-2013-user-table.md">Lync Server 2013의 사용자 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>호출자의 끝점입니다. <a href="lync-server-2013-endpoint-table.md">Lync Server 2013의 끝점 테이블</a>에서 참조 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>다소</p></td>
<td><p>외부</p></td>
<td><p>발신자의 사용자 에이전트. <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a>에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>이 통화의 우선 순위입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>이 열은 더 이상 사용 되지 않으며 Microsoft Lync Server 2013에서 사용 되지 않습니다. 대신이 정보는 미디어 단위 회선 기반에 보고 됩니다. 자세한 내용은 <a href="lync-server-2013-medialine-table.md">Lync Server 2013의 Medialine 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>P-어설션 됨-통화를 놓은 사용자의 Id입니다. P-어설션된-Id (PAI)는 통화를 설정한 사용자의 실제 id를 전달 하는 데 사용 됩니다.</p></td>
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

