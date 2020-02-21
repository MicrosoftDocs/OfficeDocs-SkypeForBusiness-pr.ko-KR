---
title: 'Lync Server 2013: FileTransfers 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2bf6f78a564ef1fd526ba8d265bedf81c845810
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a>Lync Server 2013의 FileTransfers 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

FileTransfer 보기에는 피어 투 피어 파일 전송 세션에 대 한 정보가 저장 됩니다. 이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.

<div>


> [!NOTE]  
> FileTransfers 보기에는 아래 나열 된 열 외에도 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013의 Sessiondetails view</A> 의 모든 열이 포함 되어 있습니다.



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
<td><p><strong>이름을</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>전송 된 파일의 이름입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>쿠키나</strong></p></td>
<td><p>name</p></td>
<td><p>이 항목과 연결 중인 모든 후속 작업 메시지를 식별하기 위해 사용됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>고유</p></td>
<td><p>동일한 파일 이름을 포함하는 각 전송 작업을 구분하기 위한 고유 식별자입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>수락</strong></p></td>
<td><p>비트만</p></td>
<td><p>TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Reject 및 Cancel이 NULL이 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>거부</strong></p></td>
<td><p>비트만</p></td>
<td><p>TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Accept 및 Cancel이 NULL이 됩니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>취소</strong></p></td>
<td><p>비트만</p></td>
<td><p>TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Accept 및 Reject가 NULL이 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

