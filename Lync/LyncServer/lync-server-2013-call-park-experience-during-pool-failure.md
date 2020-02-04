---
title: 'Lync Server 2013: 풀 오류 발생 시 통화 대기 환경'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park experience during pool failure
ms:assetid: f6303e69-8771-492a-9e8b-c3d7ba231309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205383(v=OCS.15)
ms:contentKeyID: 48185831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59de3b7cc7490c84536cfbc1457c6486af52c33a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>풀 오류 발생 시 Lync Server 2013의 통화 대기 환경

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-10_

계획 되지 않은 사고 때문에 프런트 엔드 풀을 사용할 수 없게 되 면 파킹 되었지만 아직 검색 되지 않은 통화는 연결이 끊깁니다. 백업 풀로 장애 조치 하는 동안 사용자는 백업 풀로 리디렉션되고 복원 모드에 있습니다. 복원 모드에서는 사용자가 통화를 보류할 수 없지만 통화를 대기 상태로 전환 하 고 전송할 수 있습니다. 장애 조치가 완료 되 면 통화가 다시 파킹 되 고 평소와 같이 검색 될 수 있습니다. 장애 복구 중에는 사용자가 복원 모드에서 끝날 때까지 통화를 파킹 해제할 수 없습니다.

재해 복구 중 장애 조치 (failover) 프로세스의 일부로 백업 풀로 리디렉션되는 사용자는 백업 풀에 배포 된 통화 대기 응용 프로그램을 사용 합니다. 따라서 백업 풀로 리디렉션되는 사용자는 백업 풀의 통화 공원 응용 프로그램에 대해 구성 된 통화 대기 설정을 사용 합니다.

다음 표에는 재해 복구의 단계를 통해 호출 공원 환경이 요약 되어 있습니다.

### <a name="user-experience-during-disaster-recovery"></a>재해 복구 중 사용자 환경

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>통화 상태</th>
<th>중단 발생 시기</th>
<th>장애 조치 동안</th>
<th>장애 복구 중</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>통화가 아직 파킹 되지 않음</p></td>
<td><p>통화는 계속 연결 되어 있지만 파킹 할 수는 없습니다.</p></td>
<td><ul>
<li><p>장애 조치 중에는 사용자가 복원 모드에 있는 동안에는 통화를 파킹 할 수 없지만 보류 하 고 전송할 수 있습니다.</p></li>
<li><p>장애 조치가 완료 되 면 통화를 파킹 하 여 검색할 수 있습니다.</p></li>
</ul></td>
<td><ul>
<li><p>장애 복구 중에는 사용자가 복원 모드에 있는 동안 통화를 파킹 할 수 없지만 보류 하 고 전송할 수 있습니다.</p></li>
<li><p>장애 복구를 완료 하면 통화를 파킹 하 여 검색할 수 있습니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>파킹 된 통화 (아직 검색 되지 않음)</p></td>
<td><p>통화가 끊겼습니다.</p></td>
<td><p>이 상태의 통화는 없습니다.</p></td>
<td><p>통화는 계속 파킹 됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>파킹 통화가 이미 검색 됨</p></td>
<td><p>통화는 연결 된 상태로 유지 됩니다.</p></td>
<td><p>통화는 연결 된 상태로 유지 됩니다.</p></td>
<td><p>통화는 연결 된 상태로 유지 됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

