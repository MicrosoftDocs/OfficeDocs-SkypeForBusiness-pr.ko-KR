---
title: 'Lync Server 2013: ProgressReport 보기'
description: 'Lync Server 2013: ProgressReport 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b95086012f254499644e778e43cafdf70ffc8f9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579794"
---
# <a name="progressreport-view-in-lync-server-2013"></a>Lync Server 2013의 ProgressReport 보기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

ProgressReport 보기에는 완료 된 세션에 대 한 정보가 저장 됩니다. 진행률 보고서는 Lync Server 2013에서 진단 목적에 따라 유용할 수 있는 통화 및 세션에 대해서만 기록 됩니다. 이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.

<div>


> [!NOTE]  
> ErrorTime, ErrorReportSeq 및 ProgressReportSeq 필드가 반드시 오류를 참조할 필요는 없지만 통화 상태 또는 메시지를 나타내는 메시지를 참조합니다.



</div>


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
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>진행률 보고서를 식별 하는 ID입니다. 동일한 오류 보고서의 진행 상황 보고서를 구별 하는 데 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>오류 보고서의 진단 ID입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>원본</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류를 유발한 서버 이름입니다(보고서가 서버 구성 요소에서 전송된 경우).</p></td>
</tr>
<tr class="even">
<td><p><strong>응용 프로그램</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>오류를 유발한 응용 프로그램 이름입니다(보고서가 서버 구성 요소에서 전송된 경우).</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>고유</p></td>
<td><p>회의에 포함된 서로 다른 구성 요소의 참가 시간 정보와 연결된 고유 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime 시간</strong></p></td>
<td><p>int</p></td>
<td><p>회의에 참가하는 특정 구성 요소에 필요한 시간(밀리초)입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar (max)</p></td>
<td><p>추가 오류 정보입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

