---
title: 'Lync Server 2013: ProgressReport 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aae907981e04d8966bb7eac4229232056d1004e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049650"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a>Lync Server 2013의 ProgressReport 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

진행률 보고서는 통화 또는 세션이 완료된 후에 클라이언트가 데이터베이스에 업로드한 데이터를 기반으로 작성됩니다. 진행률 보고서는 Lync Server 2013에서 진단 목적에 따라 유용할 수 있는 통화 및 세션에 대해서만 기록 됩니다.

ErrorTime, ErrorReportSeq 및 ProgressReportSeq 필드가 반드시 오류를 참조할 필요는 없지만 통화 상태 또는 메시지를 나타내는 메시지를 참조합니다.


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>이 진행률 보고서를 포함하는 진행 상태 오류 보고서의 날짜 및 시간입니다. 자세한 내용은 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>ErrorTime, ProgressReportSeq와 함께 진행률 보고서를 고유하게 식별하기 위해 사용된 ID 번호입니다. 자세한 내용은 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>오류 보고서를 식별하는 ID 번호입니다. ErrorReporSeq는 ErrorTime과 함께 오류 보고서를 고유하게 식별하는 데 사용됩니다. 자세한 내용은 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 테이블</a> 을 참조 하십시오.</p>
<p>이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>진행률 보고서를 식별하기 위한 ID 번호입니다. ErrorTime 및 ErrorReportSeq와 함께 진행률 보고서를 고유하게 식별하기 위해 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>진행률 보고서의 진단 ID입니다.</p>
<p>이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>오류 보고서를 보낸 서버 (보고서가 서버 구성 요소에서 전송 된 경우)입니다. 자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a> 을 참조 하십시오. 이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보고서의 대상 Lync Server 프로세스입니다. 자세한 내용은 Application 테이블을 참조하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>사항은</strong></p></td>
<td><p>이미지나</p></td>
<td></td>
<td><p>공간 절약을 위해 이진 형식으로 저장된 진행률 보고서 세부 정보입니다. 다음 구문을 사용하여 이 데이터를 텍스트 형식으로 변환할 수 있습니다.</p>
<p>cast(cast(Detail as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>고유</p></td>
<td></td>
<td><p>전화 회의에 참가하는 각 구성 요소의 참가 시간 정보에 대해 상관 관계를 지정하는 고유 식별자입니다.</p>
<p>이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime 시간</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>특정 구성 요소가 전화 회의에 참가하는 시간(밀리초)입니다.</p>
<p>이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

