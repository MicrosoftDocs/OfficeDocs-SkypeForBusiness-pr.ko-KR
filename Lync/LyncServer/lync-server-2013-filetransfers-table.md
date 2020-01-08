---
title: 'Lync Server 2013: FileTransfers 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71e53e59e3ed1391adebff8b7c4046ef3c23aa21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a>Lync Server 2013의 FileTransfers 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-28_

각 레코드는 하나의 파일 전송 세션을 나타냅니다.


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
<td><p>dmtf</p></td>
<td><p>기본, 외래</p></td>
<td><p>세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 <strong>Sessionidseq</strong> 와 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>기본, 외래</p></td>
<td><p>세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>파일 이름</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>파일의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td></td>
<td><p>동일한 파일 이름을 포함 하는 파일 전송을 구분 하는 고유 식별자입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>쿠키란</strong></p></td>
<td><p>name</p></td>
<td><p>주요한</p></td>
<td><p>모든 추가 작업 메시지를이 항목에 연결 된 것으로 식별 하는 데 사용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>사항</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>TRUE 또는 NULL 일 수 있습니다. TRUE 인 경우 거부 및 취소는 NULL입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>거부</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>TRUE 또는 NULL 일 수 있습니다. TRUE 이면 Accept와 Cancel은 NULL입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>취소</strong></p></td>
<td><p>다소</p></td>
<td></td>
<td><p>TRUE 또는 NULL 일 수 있습니다. TRUE 이면 Accept 및 Reject는 NULL입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

