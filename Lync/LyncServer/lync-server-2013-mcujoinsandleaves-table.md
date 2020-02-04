---
title: 'Lync Server 2013: McuJoinsAndLeaves 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 204906deb88a2067b7304088515b25fee2da0350
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a>Lync Server 2013의 McuJoinsAndLeaves 테이블

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-28_

이 테이블의 각 레코드에는 사용자 참가 또는 종료 및 회의 서버의 한 조합에 대 한 통화 정보가 포함 되어 있습니다. 예를 들어 사용자가 웹 회의 및 오디오/비디오 요소를 포함 하는 회의에 참가 하는 경우 해당 사용자의 웹 회의 참가에 대해 하나의 레코드가 만들어지고 사용자의 오디오/비디오 회의 참가에 대해 다른 레코드가 만들어집니다.


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
<td><p>컨퍼런스 인스턴스 시간. 회의 인스턴스를 고유 하 게 식별 하기 위해 <strong>Sessionidseq</strong> 와 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>기본, 외래</p></td>
<td><p>회의 인스턴스를 식별 하는 ID 번호입니다. 회의 인스턴스를 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>기본, 외래</p></td>
<td><p>이 사용자를 식별 하는 고유 번호입니다. 자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>주요한</p></td>
<td><p>사용자가 한 번에 여러 컴퓨터 또는 장치에 로그온 한 경우 McuUserInstance는 사용자/장치 조합을 고유 하 게 식별 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Is찡그린 Mpstn</strong></p></td>
<td><p>다소</p></td>
<td><p> </p></td>
<td><p>사용자가 PSTN에서 가입 하 고 있는지 여부.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuId</strong></p></td>
<td><p>int</p></td>
<td><p>기본, 외래</p></td>
<td><p>이 회의 서버를 식별 하는 고유 번호입니다. 자세한 내용은 <a href="lync-server-2013-mcus-table.md">Lync Server 2013의 Mcus 테이블</a> 을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p>외부</p></td>
<td><p>세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 <strong>Sessionidseq</strong> 와 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p> </p></td>
<td><p>이 사용자가 회의 서버에 참가 한 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>dmtf</p></td>
<td><p> </p></td>
<td><p>이 사용자가 회의 서버를 나간 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>회의에서 클라이언트 소프트웨어 사용의 버전 번호를 지정 하는 식별자입니다. 자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 Clientversions 테이블</a> 을 참조 하세요.</p>
<p>이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

