---
title: 'Lync Server 2013: ErrorReport 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1430ab1cc00b29ed834ff078cbe70a1265a2162
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a>Lync Server 2013의 ErrorReport 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-22_

ErrorReport 보기에는 보고된 오류에 대한 정보가 저장됩니다. 각 레코드는 발생한 한 가지 오류를 나타냅니다. 오류는 프런트 엔드 서버에서 실행하는 CDR 에이전트로 캡처되거나 클라이언트로 전송됩니다. 이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>오류가 발생한 시간입니다. ErrorReportSeq와 함께 오류를 고유하게 식별하기 위해 사용됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>오류를 식별하기 위한 ID 번호입니다. ErrorTime과 함께 오류를 고유하게 식별하기 위해 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>오류 보고서의 진단 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>오류가 유발된 사용자의 URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류가 유발된 사용자의 URI 형식입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류가 유발된 사용자의 테넌트입니다. 자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>오류 보고서의 대상인 사용자의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류 보고서의 대상인 사용자의 URI 형식입니다. 자세한 내용은 UriTypes Table을 참조하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant 넌 트</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류 보고서의 대상인 사용자의 테넌트입니다. 자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>오류 보고서의 대상인 회의의 URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류 보고서의 대상인 회의의 URI 형식입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>오류 보고서를 시작한 세션 요청의 시간입니다. SessionIdSeq과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>오류 보고서를 시작한 세션 요청을 식별하는 ID 번호입니다. SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>오류가 유발된 세션의 SIP 대화 ID입니다. 형식:</p>
<p>대화 상자, from 태그; to 태그</p>
<p>이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.</p>
<p>cast(cast(ExternalId as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>Microsoft.rtc.management.writableconfig.policy.clientversion.clientversion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류를 유발한 사용자가 사용하는 클라이언트 버전입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>오류를 유발한 사용자가 사용한 클라이언트입니다. 자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>오류를 유발한 사용자가 사용한 클라이언트 범주 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>원본</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류를 유발한 서버 이름입니다(보고서가 서버 구성 요소에서 전송된 경우).</p></td>
</tr>
<tr class="odd">
<td><p><strong>응용 프로그램</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류를 유발한 응용 프로그램 이름입니다(보고서가 서버 구성 요소에서 전송된 경우).</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>오류 보고서를 포함하는 SIP 메시지 세션에 대한 SIP 응답 코드입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>실패한 요청 유형입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>실패한 요청의 콘텐츠 유형입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>세션 유형입니다. 자세한 내용은 <a href="lync-server-2013-calltype-table.md">Lync Server 2013의 Calltype table</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>고유</p></td>
<td><p>회의에 포함된 서로 다른 구성 요소의 참가 시간 정보와 연결된 고유 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SetupTime 시간</strong></p></td>
<td><p>int</p></td>
<td><p>회의에 참가하는 특정 구성 요소에 필요한 시간(밀리초)입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>비트만</p></td>
<td><p>프런트 엔드 서버에서 실행하는 CDR 에이전트에 의해 캡처되었는지, 아니면 클라이언트에 의해 전송되었는지를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>플래그가</strong></p></td>
<td><p>smallint</p></td>
<td><p>나중에 사용하도록 예약됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>오류에 대한 추가 정보입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>프런트</strong></p></td>
<td><p>varchar</p></td>
<td><p>보고서를 전송한 프런트 엔드 서버의 정규화 된 도메인 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>그룹</strong></p></td>
<td><p>varchar</p></td>
<td><p>보고서를 전송한 프런트 엔드 서버가 포함 된 풀의 정규화 된 도메인 이름입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

