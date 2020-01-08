---
title: 'Lync Server 2013: FileTransfers view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4228bbe42f2e7bcf88b26f9147e514f09c106ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a>Lync Server 2013의 FileTransfers 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

FileTransfer 보기는 피어 투 피어 파일 전송 세션에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.

<div>


> [!NOTE]  
> FileTransfers 보기에는 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013의 Sessiondetails 보기</A> 에 아래 나열 된 열 외에 모든 열이 포함 되어 있습니다.



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
<th>세부적인</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>이름이</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>전송 된 파일의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>쿠키란</strong></p></td>
<td><p>name</p></td>
<td><p>모든 추가 작업 메시지를이 항목에 연결 된 것으로 식별 하는 데 사용 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>동일한 파일 이름을 포함 하는 파일 전송을 구분 하는 고유 식별자입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>사항</strong></p></td>
<td><p>다소</p></td>
<td><p>TRUE 또는 NULL 일 수 있습니다. TRUE 인 경우 거부 및 취소는 NULL입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>거부</strong></p></td>
<td><p>다소</p></td>
<td><p>TRUE 또는 NULL 일 수 있습니다. TRUE 이면 Accept와 Cancel은 NULL입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>취소</strong></p></td>
<td><p>다소</p></td>
<td><p>TRUE 또는 NULL 일 수 있습니다. TRUE 이면 Accept 및 Reject는 NULL입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

