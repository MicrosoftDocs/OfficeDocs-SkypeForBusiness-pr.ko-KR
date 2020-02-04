---
title: 'Lync Server 2013: 세션 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a153899fd484da861088a8e7672a69707e46a59
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a>Lync Server 2013의 세션 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-03_

세션 보기는 데이터베이스에 레코드가 있는 세션에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>열</th>
<th>데이터 형식</th>
<th>세부적인</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceDateTime</p></td>
<td><p>dmtf</p></td>
<td><p>MediaLine 테이블에서 참조 합니다.</p></td>
</tr>
<tr class="even">
<td><p>ConferenceURI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>회의가 면 회의 URI이 고 피어 투 피어 세션 인 경우 DialogID입니다.</p></td>
</tr>
<tr class="odd">
<td><p>상관이</p></td>
<td><p>varchar (max)</p></td>
<td><p>세션의 상관 관계 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>다소</p></td>
<td><p>대화 상자 범주 0은 서버 레그 조정을 위한 Lync Server입니다. 1이 (가) PSTN 게이트웨이 레그로 서버를 중재 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>다소</p></td>
<td><p>통화가 생략 되었는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>이 필드에는 바이패스 Id가 일치 하는 경우에도 통화가 무시 되지 않은 이유가 표시 됩니다. Lync Server의 경우 하나의 값만 정의 됩니다.</p>
<p>0x0001-기본 네트워크 어댑터에 대 한 알 수 없는 바이패스 ID</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>dmtf</p></td>
<td><p>통화 시작 시간.</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>dmtf</p></td>
<td><p>통화 종료 시간.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>발신자 풀 FQDN.</p></td>
</tr>
<tr class="even">
<td><p>CalleePool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>호출 수신자 풀 FQDN입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPAI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>호출자의 p-어설션된 id URI입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleePAI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>피호출자의 p-어설션된 id URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>호출자의 끝점 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>호출자의 끝점 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>호출자의 사용자 에이전트 문자열입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>호출자의 사용자 에이전트 유형입니다. 자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>호출자의 사용자 에이전트 범주입니다. 자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (체감 품질)</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>호출 수신자의 사용자 에이전트 문자열입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>호출 수신자의 사용자 에이전트 유형입니다. 자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>호출 수신자의 사용자 에이전트 범주입니다. 자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (체감 품질)</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>CallerURI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>호출자의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeURI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>호출 수신자의 URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p>Callto Oirty</p></td>
<td><p>int</p></td>
<td><p>통화의 우선 순위입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

