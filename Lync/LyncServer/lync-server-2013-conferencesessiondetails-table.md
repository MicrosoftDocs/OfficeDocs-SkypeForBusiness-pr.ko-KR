---
title: 'Lync Server 2013: ConferenceSessionDetails 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c5aaa3ec022be18ad54cc8a24b8410c23faf799
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a>Lync Server 2013의 ConferenceSessionDetails 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-28_

각 레코드는 하나의 회의 세션을 나타내며,이는 포커스가 있는 세션 또는 특정 회의 서버 세션 중 하나가 될 수 있습니다.


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
<td><p>Dmtf</p></td>
<td><p>기본, 외래</p></td>
<td><p>세션 요청 시간 회의 세션을 고유 하 게 식별 하는 <strong>Sessionidseq</strong> 와 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>기본, 외래</p></td>
<td><p>세션을 식별 하는 ID 번호입니다. 회의 세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요. *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>이 세션과 관련 된 포커스 회의 URI입니다. 자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하세요. 이 URI는 포커스 기반 전화 회의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>인스턴스</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>되풀이 회의의 인스턴스를 구별 하는 식별자입니다. 각 되풀이 회의 인스턴스에는 동일한 ConferenceURI 있지만 다른 지 인 인스턴스 값이 있습니다.</p>
<p>이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>이 세션과 관련 된 회의 서버 컨퍼런스 URI입니다. 자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하세요. 이 URI는 회의 서버 기반 전화 회의 URI입니다. 포커스 회의 세션의 경우이 열은 null입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>회의 세션의 한 사용자의 ID입니다. 자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td></td>
<td><p>끝점의 인스턴스를 식별 하는 GUID입니다. 예를 들어 한 사용자가 동일한 계정을 사용 하 여 다른 컴퓨터에 로그온 하는 경우 각 컴퓨터에는 서로 다른 끝점 ID가 부여 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>호출자가 대신 하는 사용자의 ID를 나타냅니다. 자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화를 참조 하는 사용자의 ID입니다. 자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>컨퍼런스 사용자가 클라이언트 버전을 사용 합니다. 자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 Clientversions 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>해당 클라이언트</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>회의 서버에서 사용 하는 클라이언트 버전. 자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 Clientversions 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>외부</p></td>
<td><p>현재 세션으로 대체 된 대화 상자를 식별 하는 ID 번호입니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>세션을 식별 하는 ID 번호입니다. <strong>ReplacesDialogIdTime</strong> 와 함께 사용 하 여이 세션으로 대체 되는 세션을 고유 하 게 식별 합니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>회의 서버에서 세션을 시작 했음을 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Isen이상 By참여 서버</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>회의 서버에서 세션을 종료 했음을 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>사용자가 내부에서 로그온 되었는지 여부</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>세션 초대에 대 한 SIP (세션 초기화 프로토콜) 응답 코드 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>SIP 헤더에서 진단 ID를 캡처 했습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>이 세션에 사용 되는 프런트 엔드 서버의 ID입니다. 자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 서버 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>세션이 캡처된 풀의 ID입니다. 자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화에서 사용 중인 중재 서버입니다. 자세한 내용은 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013의 Mediationservers 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>GatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화에서 사용 중인 게이트웨이 자세한 내용은 <a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>통화에서 사용 중인 Edge 서버입니다. 자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>세션에 사용 되는 콘텐츠 형식입니다. 자세한 내용은 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013의 Contenttypes 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>dmtf</p></td>
<td></td>
<td><p>첫 번째 초대 요청 시간입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>dmtf</p></td>
<td></td>
<td><p>첫 번째 SIP 응답의 시간입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>dmtf</p></td>
<td></td>
<td><p>세션이 종료 된 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>외부</p></td>
<td><p><a href="lync-server-2013-uritypes-table.md">Lync Server 2013에서 UriTypes 테이블</a>의 MCU URI 유형 값을 포함 합니다. 이 필드는 쿼리 성능을 개선 하는 데 사용 됩니다.</p>
<p>이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>사용자 특성을 나타내는 비트 집합입니다. 다음과 같은 특성 정의가 나열 됩니다.</p>
<ul>
<li><p>데스크톱 전화번호와 통합-1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>통화 특성을 나타내는 비트 집합입니다. 다음과 같은 특성 정의가 나열 됩니다.</p>
<ul>
<li><p>다시 시도 된 세션-1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\*대부분의 세션에서 SessionIdSeq에는 값 1이 사용 됩니다. 정확히 동시에 여러 세션을 시작 하는 경우 1에 대 한 SessionIdSeq는 1이 되 고 다른 하나는 2가 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

