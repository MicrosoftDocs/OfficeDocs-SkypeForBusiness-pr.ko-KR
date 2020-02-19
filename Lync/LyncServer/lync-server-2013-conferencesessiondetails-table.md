---
title: 'Lync Server 2013: ConferenceSessionDetails 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7f0907b6c92d3ca5ed1adf7f1a991242d6ddeb1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a>Lync Server 2013의 ConferenceSessionDetails 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

각 레코드는 Focus를 가진 세션이거나, 특정 회의 서버를 가진 세션일 수 있는 하나의 회의 세션을 나타냅니다.


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
<td><p>Datetime</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>세션 요청 시간 <strong>Sessionidseq</strong> 와 함께 사용 되어 회의 세션을 고유 하 게 식별 합니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>세션을 식별하기 위한 ID 번호입니다. 회의 세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>이 세션과 관련된 회의 센터 회의 URI입니다. 자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하십시오. 이 URI는 회의 센터 기반 회의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>인스턴스</strong></p></td>
<td><p>고유</p></td>
<td></td>
<td><p>되풀이 회의 인스턴스 간에 구별하기 위한 식별자입니다. 각 되풀이 회의 인스턴스는 ConferenceURI 값이 같지만 ConfInstance 값은 다릅니다.</p>
<p>이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>이 세션과 관련된 회의 서버 회의 URI입니다. 자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하십시오. 이 URI는 회의 서버 기반 회의 URI입니다. 회의 센터 회의 세션의 경우 이 열은 Null입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>회의 세션에 있는 한 사용자의 ID입니다. 자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>고유</p></td>
<td></td>
<td><p>끝점 인스턴스를 식별하기 위한 GUID입니다. 예를 들어 한 사용자가 동일 계정을 사용하여 여러 컴퓨터에 로그온하면 각 컴퓨터가 서로 다른 끝점 ID를 갖습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>발신자가 역할을 대신 수행하고 있는 원래 사용자의 ID를 나타냅니다. 자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 참조한 사용자의 ID입니다. 자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>회의 사용자가 사용한 클라이언트 버전입니다. 자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>에이 Client합니다.</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>회의 서버가 사용한 클라이언트 버전입니다. 자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>외부</p></td>
<td><p>현재 세션으로 교체된 대화를 식별하기 위한 ID 번호입니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>세션을 식별하기 위한 ID 번호입니다. <strong>ReplacesDialogIdTime</strong>과 함께 이 세션으로 교체된 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>세션이 회의 서버에서 시작되었는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>세션이 회의 서버에서 종료되었는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>비트만</p></td>
<td></td>
<td><p>사용자가 내부로부터 로그온되었는지 여부입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>세션 초대에 대한 SIP(Session Initiation Protocol) 응답 코드입니다. 이 필드는 대개 세션의 초기 INVITE 메시지에서 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>SIP 헤더에서 캡처된 진단 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>이 세션에 사용된 프런트 엔드 서버의 ID입니다. 자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>세션이 캡처된 풀의 ID입니다. 자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 사용 중인 중재 서버입니다. 자세한 내용은 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013에서 Mediationservers 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>GatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 사용 중인 게이트웨이입니다. 자세한 내용은 <a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 사용 중인 에지 서버입니다. 자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>세션에 사용된 콘텐츠 형식입니다. 자세한 내용은 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013의 Contenttypes 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>첫 번째 INVITE 요청 시간입니다. 이 필드는 대개 세션의 초기 INVITE 메시지에서 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 이 필드가 첫 번째 해당 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜와 시간으로 채워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>첫 번째 SIP RESPONSE 시간입니다. 이 필드는 대개 세션의 초기 INVITE 메시지에서 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 이 필드가 첫 번째 해당 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜와 시간으로 채워집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>세션이 종료된 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>외부</p></td>
<td><p><a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a>에 있는 MCU URI 유형 값을 포함 합니다. 이 필드는 쿼리 성능을 높이기 위해 사용됩니다.</p>
<p>이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>사용자 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다.</p>
<ul>
<li><p>일반 전화기와 통합됨 - 1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>통화 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다.</p>
<ul>
<li><p>다시 시도된 세션 - 1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\*대부분의 세션에서 SessionIdSeq는 값 1을 갖습니다. 여러 세션이 정확히 동시에 시작될 경우 한 세션에 대한 SessionIdSeq가 1이 되고 다른 세션에 대해서는 2, 3, 4의 순서로 지정됩니다.

</div>

<span> </span>

</div>

</div>

</div>

