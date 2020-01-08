---
title: 'Lync Server 2013: ErrorReport view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b50a2615fe83ed481d9642ac6895120f20b9fd0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a>Lync Server 2013의 ErrorReport 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-01-22_

ErrorReport 보기는 보고 된 오류에 대 한 정보를 저장 합니다. 각 레코드는 오류 발생 중 하나입니다. 이 오류는 프런트 엔드 서버에서 실행 되는 CDR 에이전트에서 또는 클라이언트에서 전송 된에 의해 캡처됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>오류가 발생 한 시간입니다. 오류를 고유 하 게 식별 하는 ErrorReportSeq와 함께 사용 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>오류를 식별 하는 ID 번호입니다. 오류를 고유 하 게 식별 하는 ErrorTime과 함께 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>오류 보고서의 진단 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>오류를 발생 시킨 사용자의 URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fromurit</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류를 발생 시킨 사용자의 URI 유형입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류를 발생 시킨 사용자의 테 넌 트입니다. 자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>오류 보고서를 대상으로 하는 사용자의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류 보고서를 대상으로 하는 사용자의 URI 유형입니다. 자세한 내용은 UriTypes 테이블을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant 넌 트</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류 보고서를 대상으로 하는 사용자의 테 넌 트입니다. 자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>오류 보고서의 대상인 컨퍼런스의 URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류 보고서의 대상에 해당 하는 회의의 URI 형식입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>오류 보고를 시작 하는 세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>오류 보고서를 시작 하는 세션 요청을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>오류를 발생 시킨 세션의 SIP 대화 상자 ID입니다. 형식은 다음과 같습니다.</p>
<p>대화 상자; from 태그; 태그</p>
<p>이 구문을 사용 하 여이 데이터를 텍스트 형식으로 변환할 수 있습니다.</p>
<p>캐스트 (cast (max) as varchar (max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류를 발생 시킨 사용자가 사용 하는 클라이언트 버전입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>오류를 발생 시킨 사용자가 사용 하는 클라이언트입니다. 자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013에서 Useragentdef 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>오류를 발생 시킨 사용자가 사용 하는 클라이언트 범주의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류를 발생 시킨 서버의 이름입니다 (보고서가 서버 구성 요소에서 전송 된 경우).</p></td>
</tr>
<tr class="odd">
<td><p><strong>응용 프로그램</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류를 발생 시킨 응용 프로그램의 이름입니다 (보고서가 서버 구성 요소에서 전송 된 경우).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>오류 보고서를 포함 하는 SIP 메시지의 세션에 대 한 SIP 응답 코드</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>실패 한 요청의 유형입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>실패 한 요청의 콘텐츠 형식입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션의 유형입니다. 자세한 내용은 <a href="lync-server-2013-calltype-table.md">Lync Server 2013의 Calltype 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>고유한 식별자는 회의에 관련 된 다양 한 구성 요소에 대 한 조인 시간 정보를 연결 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SetupTime 시간</strong></p></td>
<td><p>int</p></td>
<td><p>특정 구성 요소가 컨퍼런스에 참가 하는 데 필요한 시간 (밀리초 단위)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>다소</p></td>
<td><p>프런트 엔드 서버에서 실행 중이거나 클라이언트가 보낸 CDR 에이전트에 의해 오류 보고서가 캡처 되었는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>플래그</strong></p></td>
<td><p>smallint</p></td>
<td><p>나중에 사용 하기 위해 예약 되어 있습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>오류에 대 한 추가 정보입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FrontEnd</strong></p></td>
<td><p>varchar</p></td>
<td><p>보고서를 제출한 프런트 엔드 서버의 정규화 된 도메인 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>풀</strong></p></td>
<td><p>varchar</p></td>
<td><p>보고서를 제출한 프런트 엔드 서버를 포함 하는 풀의 정규화 된 도메인 이름입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

