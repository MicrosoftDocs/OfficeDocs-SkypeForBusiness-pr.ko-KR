---
title: 'Lync Server 2013: McuJoinsAndLeaves 테이블'
description: 'Lync Server 2013: McuJoinsAndLeaves 테이블'
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
ms.openlocfilehash: ee7d9473892ac357dcefd80b0d52382c5dd7d930
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556504"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a>Lync Server 2013의 McuJoinsAndLeaves 테이블

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

이 테이블의 각 레코드에는 사용자 참가 또는 나가기 및 회의 서버의 한 조합에 대 한 통화 정보가 포함 되어 있습니다. 예를 들어 사용자가 웹 회의 및 오디오/비디오 요소를 포함 하는 회의에 참가 하는 경우 해당 사용자의 웹 회의 참가에 대해 하나의 레코드가 생성 되 고 사용자의 오디오/비디오 회의 참가에 대 한 다른 레코드가 생성 됩니다.


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>전화 회의 시간입니다. 이를 <strong>Sessionidseq</strong> 와 함께 사용 하 여 전화 회의 인스턴스를 고유 하 게 식별 합니다. 자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>전화 회의 인스턴스를 식별 하기 위한 ID 번호입니다. <strong>Sessionidtime</strong> 과 함께 회의 인스턴스를 고유 하 게 식별 하는 데 사용 됩니다. 자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>이 사용자를 식별하는 고유 번호입니다. 자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>사용자가 한 번에 여러 컴퓨터 또는 장치에 로그온 되어 있는 경우 McuUserInstance는 사용자/장치 조합을 고유 하 게 식별 합니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Is고 Mpstn</strong></p></td>
<td><p>비트만</p></td>
<td><p> </p></td>
<td><p>사용자가 PSTN에서 가입 하 고 있는지 여부입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>McuId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary, Foreign</p></td>
<td><p>이 회의 서버를 식별 하는 고유 번호입니다. 자세한 내용은 <a href="lync-server-2013-mcus-table.md">Lync Server 2013의 Mcus 테이블</a> 을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>외부</p></td>
<td><p>세션 요청 시간입니다. <strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>세션을 식별하기 위한 ID 번호입니다. <strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>이 사용자가이 회의 서버에 참가 하는 시간입니다.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>이 사용자가이 회의 서버를 떠나는 시간입니다.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>외부</p></td>
<td><p>회의에서 클라이언트 소프트웨어를 사용 하는 경우의 버전 번호를 지정 하는 식별자입니다. 자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</p>
<p>이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

