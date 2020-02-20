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
ms.openlocfilehash: 80b9c7c9b54deb28b70c8ee2386359bec37d5a69
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a>Lync Server 2013의 세션 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-03_

세션 보기에는 데이터베이스의 레코드가 포함된 세션에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.


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
<th>세부 정보</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Conferencedatetime이 동일할</p></td>
<td><p>datetime</p></td>
<td><p>MediaLine 테이블에서 참조됩니다.</p></td>
</tr>
<tr class="even">
<td><p>ConferenceURI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>항목이 회의인 경우 회의 URI이고 피어 투 피어 세션인 경우에는 DialogID입니다.</p></td>
</tr>
<tr class="odd">
<td><p>Correlation</p></td>
<td><p>varchar (max)</p></td>
<td><p>세션의 상관 관계 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>비트만</p></td>
<td><p>대화 상자 범주 0은 중재 서버 레그에 대 한 Lync Server입니다. 1은 PSTN 게이트웨이 레그에 대 한 중재 서버입니다.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>비트만</p></td>
<td><p>통화가 우회되었는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>이 필드(제공된 경우)는 우회 ID가 일치했어도 통화가 우회되지 않은 이유를 나타냅니다. Lync Server의 경우 한 가지 값만 정의 됩니다.</p>
<p>0x0001 -  기본 네트워크 어댑터에 대한 알 수 없는 바이패스 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>통화 시작 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>통화 종료 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>발신자 풀 FQDN입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleePool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>수신자 풀 FQDN입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPAI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>발신자의 P-Asserted Identity URI입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleePAI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>발신자의 P-Asserted Identity URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>발신자의 끝점 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>발신자의 끝점 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>발신자의 사용자 에이전트 문자열입니다.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>발신자의 사용자 에이전트 형식입니다. 자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>발신자의 사용자 에이전트 범주입니다. 자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>수신자의 사용자 에이전트 문자열입니다.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>수신자의 사용자 에이전트 유형입니다. 자세한 내용은 <a href="lync-server-2013-useragent-table.md">Lync Server 2013의 UserAgent 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>수신자의 사용자 에이전트 범주입니다. 자세한 내용은 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013의 Useragentdef 테이블 (QoE)</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p>CallerURI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>발신자의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p>CalleeURI</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>수신자의 URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p>Call Oirty</p></td>
<td><p>int</p></td>
<td><p>통화 우선 순위입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

