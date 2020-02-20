---
title: 'Lync Server 2013: McuJoinsAndLeaves 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a217ddc3ef362c99e5cb7686594e5f9068ce4970
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a>Lync Server 2013의 McuJoinsAndLeaves 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

McuJoinsAndLeaves 보기에는 사용자에 대 한 정보를 저장 하 고 회의 서버 한 대에 대 한 정보를 탈퇴 합니다. 이 보기의 각 레코드에는 사용자 참가 또는 나가기 및 회의 서버의 한 조합에 대 한 통화 정보가 포함 되어 있습니다. 이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>전화 회의 시간입니다. 이를 SessionIdSeq와 함께 사용 하 여 전화 회의 인스턴스를 고유 하 게 식별 합니다. 자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>전화 회의 인스턴스를 식별 하기 위한 ID 번호입니다. SessionIdTime과 함께 회의 인스턴스를 고유 하 게 식별 하는 데 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>사용자가 연결 된 회의 서버의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>M메이 urit3</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>사용자가 연결 된 회의 서버의 URI입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>변수와 useruri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>회의 서버 참가/나가기 정보가 캡처된 사용자의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Userurit<</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>회의 서버 참가/나가기 정보가 캡처된 사용자의 URI 유형입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant 넌 트</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>회의 서버 참가/탈퇴 정보를 캡처한 사용자의 테 넌 트입니다. 자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>회의 서버 참가/탈퇴 정보를 캡처한 사용자가 사용 하는 클라이언트의 버전입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>회의 서버 참가/탈퇴 정보를 캡처한 사용자가 사용 하는 클라이언트입니다. 자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>회의 서버 참가/탈퇴 정보를 캡처한 사용자가 사용 하는 클라이언트의 범주 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>여러 장치에 동시에 로그온 한 사용자의 사용자/장치 조합을 고유 하 게 식별 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserFromPstn</strong></p></td>
<td><p>비트만</p></td>
<td><p>사용자가 내부 사용자 인지 여부를 나타내는 비트입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>세션 요청 시간입니다. SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>세션을 식별하기 위한 ID 번호입니다. SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>세션의 SIP 대화 ID입니다. 형식은 dialog, from-tag; to 태그입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>사용자가 회의 서버에 참가 한 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>사용자가 회의 서버를 떠난 시간입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

