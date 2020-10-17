---
title: 'Lync Server 2013: ConferenceMessageCount 보기'
description: 'Lync Server 2013: ConferenceMessageCount 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 212d6e1a346253809fb70806424350cc7fc0dfe2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561614"
---
# <a name="conferencemessagecount-view-in-lync-server-2013"></a>Lync Server 2013의 ConferenceMessageCount 보기

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

ConferenceMessageCount 보기에는 사용자가 회의에 전송한 메시지 수에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.

<div>


> [!NOTE]  
> ConferenceMessageCount 보기에는 아래 나열 된 열 외에도 <A href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013의 ConferenceSessionDetails 보기</A> 에 있는 모든 열이 포함 되어 있습니다.



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
<td><p><strong>변수와 useruri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>메시지를 보낸 사용자의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Userurit<</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>메시지를 보낸 사용자 URI의 형식입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant 넌 트</strong></p></td>
<td><p>고유</p></td>
<td><p>메시지를 보낸 사용자의 테넌트입니다. 자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserMessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p>회의 세션 중 사용자가 보낸 메시지 수입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

