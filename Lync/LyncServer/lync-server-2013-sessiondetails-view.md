---
title: 'Lync Server 2013: SessionDetails 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fabf7ae963240f6a2b14ac8c3db272e0cb06091c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a>Lync Server 2013의 SessionDetails 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

SessionDetails view는 피어 투 피어 세션에 대 한 정보를 저장 하는데,이는 VoIP 전화 통화, 2-파티 IM 세션 또는 기타 세션 유형이 될 수 있습니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 테이블의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>첫 번째 초대 요청의 시간입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>세션을 시작한 사용자의 URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>세션에 참가 한 사용자의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fromurit</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션을 시작한 사용자의 URI 유형입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션에 참가 한 사용자의 URI 유형입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>세션을 시작한 사용자의 테 넌 트입니다. 자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant 넌 트</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션에 참가 한 사용자의 테 넌 트입니다. 자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>세션을 시작한 사용자의 끝점에 대 한 고유 식별자입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>세션에 참가 한 사용자의 끝점에 대 한 고유 식별자입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>세션 종료 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMessageCount</strong></p></td>
<td><p>int</p></td>
<td><p>세션을 시작한 사용자가 보낸 메시지 수입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMessageCount</strong></p></td>
<td><p>int</p></td>
<td><p>세션에 참가 한 사용자가 보낸 메시지 수입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션을 시작한 사용자가 사용 하는 클라이언트 버전입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromClientType</strong></p></td>
<td><p>int</p></td>
<td><p>세션을 시작한 사용자가 사용 하는 클라이언트입니다. 자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013에서 Useragentdef 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>세션을 시작한 사용자가 사용 하는 클라이언트 범주의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션에 참가 한 사용자가 사용 하는 클라이언트 버전</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToClientType</strong></p></td>
<td><p>int</p></td>
<td><p>세션에 참가 한 사용자가 사용 하는 클라이언트입니다. 자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013에서 Useragentdef 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>세션에 참가 한 사용자가 사용 하는 클라이언트 범주의 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TargetUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>세션의 대상 사용자의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>TargetUriType</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>세션에 대 한 대상 사용자의 URI 유형입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>해당 세션이 시작 된 사용자의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>OnnnBehalfOfUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션이 시작 된 사용자의 URI 유형입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>OnBehalfOfTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션이 시작 된 사용자를 대신해 서의 테 넌 트입니다. 자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>세션을 참조 한 사용자의 URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredByUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션을 참조 한 사용자의 URI 유형입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReferredByTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션을 참조 한 사용자의 테 넌 트입니다. 자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>SIP 대화 상자 ID입니다. 형식은 다음과 같습니다.</p>
<p>대화 상자; from 태그; 태그</p></td>
</tr>
<tr class="even">
<td><p><strong>Legredir</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>여러 세션의 연관성을 위해 사용 되는 GUID입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>세션으로 대체 된 대화의 시간입니다. ReplaceDialogIdSeq와 함께 사용 하 여 세션으로 대체 되는 대화를 고유 하 게 식별 합니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>세션을 식별 하는 ID 번호입니다. ReplaceDialogIdTime와 함께 사용 하 여 세션으로 대체 되는 대화를 고유 하 게 식별 합니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplacesDialogId</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>세션에서 대체 하는 SIP 대화 상자 ID입니다. 형식은 다음과 같습니다.</p>
<p>대화 상자; from 태그; 태그</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>첫 번째 초대 메시지에 대 한 응답 시간입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>세션 초대에 대 한 SIP 응답 코드입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>SIP 헤더에서 진단 ID를 캡처 했습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션의 콘텐츠 유형입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션에 대 한 데이터를 캡처한 프런트 엔드 서버의 FQDN입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>풀</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션에 대 한 데이터를 캡처한 풀의 FQDN입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromEdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션을 시작한 사용자가 사용 하는 Edge 서버의 FQDN입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToEdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션을 시작한 사용자가 사용 하는 Edge 서버의 FQDN</p></td>
</tr>
<tr class="even">
<td><p><strong>IsFromInternal</strong></p></td>
<td><p>다소</p></td>
<td><p>세션을 시작한 사용자가 내부 네트워크에서 로그온 했는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsToInternal</strong></p></td>
<td><p>다소</p></td>
<td><p>세션에 참가 한 사용자가 내부 네트워크에서 로그온 되었는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션의 호출 우선 순위입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>세션을 시작한 사용자의 특성을 나타냅니다. 다음과 같은 특성 정의가 허용 됩니다.</p>
<p>0x01-데스크톱 전화와 통합</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>세션을 시작한 사용자의 특성을 나타냅니다. 다음과 같은 특성 정의가 허용 됩니다.</p>
<p>0x01-데스크톱 전화와 통합</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p>통화 특성을 나타냅니다. 다음과 같은 특성 정의가 허용 됩니다.</p>
<p>0x01-재시도 하는 세션</p>
<p>0x02-응답 그룹을 대신 하 여 상담원이 수행한 A 통화</p></td>
</tr>
<tr class="even">
<td><p><strong>위치</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>비상 전화의 위치입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

