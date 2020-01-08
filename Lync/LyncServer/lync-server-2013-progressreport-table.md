---
title: 'Lync Server 2013: ProgressReport 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8ca0341cd5b85418ef5f71234870ae4171af27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a>Lync Server 2013의 ProgressReport 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-28_

진행률 보고서는 호출 또는 세션이 완료 된 후 클라이언트에서 데이터베이스에 업로드 한 데이터를 기반으로 합니다. 진행률 보고서는 Lync Server 2013이 진단 목적에 유용할 수 있는 통화 및 세션에 대해서만 기록 됩니다.

ErrorTime, ErrorReportSeq 및 ProgressReportSeq 필드는 반드시 오류를 의미 하지는 않으며 호출 상태를 나타내는 메시지에만 해당 됩니다.


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>기본, 외래</p></td>
<td><p>이 진행률 보고서가 포함 된 진행률 오류 보고서의 날짜 및 시간입니다. 자세한 내용은 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>기본, 외래</p></td>
<td><p>상태 보고서를 고유 하 게 식별 하는 ProgressReportSeq ErrorTime과 함께 사용 되는 ID 번호입니다. 자세한 내용은 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>기본, 외래</p></td>
<td><p>오류 보고서를 식별 하는 ID 번호입니다. ErrorReporSeq는 오류 보고서를 고유 하 게 식별 하는 ErrorTime과 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013의 ErrorReport 표</a> 를 참조 하세요.</p>
<p>이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p>진행률 보고서를 식별 하는 ID 번호입니다. 진행률 보고서를 고유 하 게 식별 하는 ErrorTime 및 Errortime Seq와 함께 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>진행률 보고서의 진단 ID입니다.</p>
<p>이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>오류 보고서를 보낸 서버 (보고서가 서버 구성 요소에서 전송 된 경우) 자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 서버 테이블</a> 을 참조 하세요. 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>보고서에 대 한 Lync Server 프로세스입니다. 자세한 내용은 응용 프로그램 테이블을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>도</strong></p></td>
<td><p>이미지</p></td>
<td></td>
<td><p>공간 절약을 위해 이진 형식으로 저장 된 진행률 보고서 세부 정보입니다. 이 구문을 사용 하 여이 데이터를 텍스트 형식으로 변환할 수 있습니다.</p>
<p>cast (cast (varbinary (max)로 Detail)를 varchar (max)로 캐스트)</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>컨퍼런스와 관련 된 다양 한 구성 요소에 대 한 조인 시간 정보를 연관 시키는 고유 식별자입니다.</p>
<p>이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime 시간</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>특정 구성 요소가 컨퍼런스에 참가 하는 데 걸리는 시간 (밀리초 단위)입니다.</p>
<p>이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

