---
title: 'Lync Server 2013: McuJoinsAndLeaves view'
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
ms.openlocfilehash: d339df5b3b591cbf67376c36c5e0e4261c390851
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a>Lync Server 2013의 McuJoinsAndLeaves 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

McuJoinsAndLeaves 보기는 사용자가 1 회의 서버에 대 한 정보를 참가 및 탈퇴 하는 정보를 저장 합니다. 이 보기의 각 레코드에는 사용자 참가 또는 종료 및 회의 서버의 한 조합에 대 한 통화 정보가 포함 됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>컨퍼런스 인스턴스 시간. 회의 인스턴스를 고유 하 게 식별 하기 위해 SessionIdSeq와 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>회의 인스턴스를 식별 하는 ID 번호입니다. 회의 인스턴스를 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>사용자가 연결 된 회의 서버의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>사용자가 연결 된 회의 서버의 URI입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>회의 서버 참여/종료 정보를 캡처한 사용자의 URI입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>회의 서버 참여/종료 정보를 캡처한 사용자의 URI 유형입니다. 자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant 넌 트</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>회의 서버 참여/종료 정보를 캡처한 사용자의 테 넌 트입니다. 자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>회의 서버 참여/종료 정보를 캡처한 사용자가 사용 하는 클라이언트 버전입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>회의 서버 참여/종료 정보를 캡처한 사용자가 사용 하는 클라이언트입니다. 자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013에서 Useragentdef 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>회의 서버 참여/종료 정보를 캡처한 사용자가 사용 하는 클라이언트 범주의 이름입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>여러 장치에 동시에 로그온 한 사용자의 사용자/장치 조합을 고유 하 게 식별 합니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>Isuser찡그린 Mpstn</strong></p></td>
<td><p>다소</p></td>
<td><p>사용자가 내부 사용자 인지 여부를 나타내는 비트입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>세션의 SIP 대화 상자 ID입니다. 형식은 대화 상자, from 태그, to 태그입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>사용자가 회의 서버에 참가 한 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>사용자가 회의 서버를 남겨진 시간입니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

