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
ms.openlocfilehash: a89acc193f70ba5047a2f1c6362b957d182afdb5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-experience-in-lync-server-2013-during-pool-failure"></a>풀 오류 발생 시 Lync Server 2013의 통화 대기 환경

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-10_

계획 되지 않은 문제로 인해 프런트 엔드 풀을 사용할 수 없는 경우 파킹 되었지만 아직 검색 되지 않은 통화는 끊어집니다. 백업 풀로 장애 조치(failover)하는 중에는 사용자가 백업 풀로 리디렉션되고 복구 모드에 있게 됩니다. 복구 모드에서는 사용자가 통화를 대기시킬 수는 없지만 대기 상태로 설정하고 전송할 수는 있습니다. 장애 조치(failover)가 완료되면 통화가 보통 때처럼 다시 대기되었다고 재개될 수 있습니다. 장애 복구(failback) 중에는 사용자가 복구 모드가 끝날 때까지 통화를 대기시킬 수 없습니다.

재해 복구를 수행 하는 동안 장애 조치 (failover) 프로세스의 일부로 백업 풀로 리디렉션되는 사용자는 백업 풀에 배포 된 통화 대기 응용 프로그램을 사용 합니다. 따라서 백업 풀로 리디렉션되는 사용자는 백업 풀의 통화 대기 응용 프로그램에 대해 구성 된 통화 대기 설정을 사용 합니다.

다음 표에는 재해 복구 단계를 통해 제공 되는 통화 대기 환경이 요약 되어 있습니다.

### <a name="user-experience-during-disaster-recovery"></a>재해 복구 시 사용자 환경

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
<th>중단이 발생하는 경우</th>
<th>장애 조치(failover) 시</th>
<th>장애 복구(failback) 시</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>통화가 아직 대기되지 않았음</p></td>
<td><p>통화가 연결되었지만 대기될 수 없습니다.</p></td>
<td><ul>
<li><p>장애 조치(failover) 중에는 사용자가 복구 모드에 있는 동안 통화를 대기할 수 없지만 대기 상태로 설정하고 전송할 수 있습니다.</p></li>
<li><p>장애 조치(failover)가 완료되면 통화를 대기하고 재개할 수 있습니다.</p></li>
</ul></td>
<td><ul>
<li><p>장애 복구(failback) 중에는 사용자가 복구 모드에 있는 동안 통화를 대기할 수 없지만, 대기 상태로 설정하고 전송할 수 있습니다.</p></li>
<li><p>장애 복구(failback)가 완료되면 통화를 대기하고 재개할 수 있습니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>통화가 대기되었지만 아직 재개되지 않았음</p></td>
<td><p>통화가 끊어졌습니다.</p></td>
<td><p>이 상태의 통화가 없습니다.</p></td>
<td><p>통화가 대기 상태로 유지됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>대기된 통화가 이미 재개됨</p></td>
<td><p>통화가 연결된 상태로 유지됩니다.</p></td>
<td><p>통화가 연결된 상태로 유지됩니다.</p></td>
<td><p>통화가 연결된 상태로 유지됩니다.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

