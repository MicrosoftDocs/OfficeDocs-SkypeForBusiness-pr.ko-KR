---
title: 'Lync Server 2013: 재해 복구 중의 그룹 통화 픽업 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45ebe93ebc1711f49d4578a2a5d908104ca2a411
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013에서 재해 복구를 수행 하는 동안 그룹 통화 픽업 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-01-30_

계획 되지 않은 사고 때문에 프런트 엔드 풀을 사용할 수 없게 되 면 서비스가 백업 풀로 장애 조치 됩니다. 백업 풀로 장애 조치 (failover) 하는 동안 사용자가 복원 모드에 있는 백업 풀로 리디렉션됩니다. 복원 모드에서는 사용자가 다른 사용자의 통화를 선택 하거나 다른 사용자가 통화를 선택할 수 없습니다. 장애 조치가 완료 되 면 사용자는 평소 대로 그룹 통화 픽업을 사용할 수 있습니다.

기본 풀로 장애 복구 하는 동안 사용자는 기본 풀로 리디렉션되고 복원 모드에 다시 있습니다. 사용자가 복원 모드를 벗어나면 그룹 통화 픽업 기능을 사용할 수 없습니다.

이 섹션에서는 장애 복구 중 그룹 통화 픽업에 대 한 몇 가지 고려 사항에 대해 설명 하 고 사용자 환경에 대해서도 설명 합니다.

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>재해 복구 중 그룹 통화 픽업 고려 사항

재해 복구 중 장애 조치 (failover) 프로세스의 일부로 백업 풀로 리디렉션되는 사용자는 통화 픽업 그룹 번호에 대 한 백업 풀에서 실행 되는 통화 공원 응용 프로그램을 사용 합니다. 따라서 재해 복구 중 그룹 통화 픽업 지원에는 기본 풀과 백업 풀 모두에서 통화 대기 응용 프로그램을 배포 하 고 사용 하도록 설정 해야 합니다.

통화 공원 표 내의 그룹 통화 픽업 번호 범위는 백업 풀에 대 한 장애 조치 프로세스가 완료 된 후 백업 풀로 리디렉션되어야 합니다. 주 풀에 대 한 장애 복구 프로세스가 완료 되 면 번호 범위를 기본 풀로 다시 리디렉션 해야 합니다. 그룹 통화 픽업 범위를 리디렉션하려면 **Set-CsCallParkOrbit** cmdlet을 사용 합니다.

다른 FQDN (정규화 된 도메인 이름)으로 새 풀을 배포 하 여 기본 풀을 바꾸려면 기본 풀과 연결 된 모든 그룹 통화 픽업 번호 범위를 새 풀의 FQDN으로 다시 할당 해야 합니다. 숫자 범위를 새 풀에 다시 할당 하려면 **CsCallParkOrbit** cmdlet을 사용 하면 됩니다. **Set-CsCallParkOrbit** cmdlet에 대 한 자세한 내용은 [set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)를 참조 하세요.

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>풀 오류 중 그룹 통화 픽업 경험

다음 표에는 재해 복구의 단계를 통해 그룹 통화 픽업 환경이 요약 되어 있습니다.

### <a name="user-experience-during-disaster-recovery"></a>재해 복구 중 사용자 환경

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>통화 상태</th>
<th>백업 풀에 대 한 장애 조치</th>
<th>주 풀 장애 복구</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>새로운 통화</p></td>
<td><p><strong>장애 조치 프로세스 중:</strong></p>
<ul>
<li><p>복원 모드의 사용자는 그룹 통화 픽업을 사용할 수 없음</p></li>
</ul>
<p><strong>장애 조치 완료 후:</strong></p>
<ul>
<li><p>회복성 있지 않은 사용자 및 그룹 통화 픽업 번호 범위가 백업 풀로 리디렉션되는 경우 사용할 수 있는 그룹 통화 픽업</p></li>
</ul></td>
<td><p><strong>장애 복구 프로세스가 진행 되는 동안:</strong></p>
<ul>
<li><p>복원 모드의 사용자는 그룹 통화 픽업을 사용할 수 없음</p></li>
</ul>
<p><strong>장애 복구 완료 후:</strong></p>
<ul>
<li><p>회복성 있지 않은 사용자 및 그룹 통화 픽업 번호 범위가 기본 풀로 다시 리디렉션되는 경우 사용할 수 있는 그룹 통화 픽업</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>그룹 통화 픽업 대기열의 통화</p></td>
<td><p><strong>장애 조치 프로세스 중:</strong></p>
<ul>
<li><p>큐의 통화는 그룹 통화 픽업을 통해 응답할 수 없습니다.</p></li>
</ul>
<p><strong>장애 조치 완료 후:</strong></p>
<ul>
<li><p>이 상태의 통화 없음</p></li>
</ul></td>
<td><p><strong>장애 복구 프로세스가 진행 되는 동안:</strong></p>
<ul>
<li><p>큐의 통화는 그룹 통화 픽업을 통해 응답할 수 없습니다.</p></li>
</ul>
<p><strong>장애 복구 완료 후:</strong></p>
<ul>
<li><p>큐의 통화는 그룹 통화 픽업을 통해 응답할 수 없습니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>통화 설정</p></td>
<td><p><strong>장애 조치 프로세스 중:</strong></p>
<ul>
<li><p>통화 연결 유지</p></li>
</ul>
<p><strong>장애 조치 완료 후:</strong></p>
<ul>
<li><p>통화 연결 유지</p></li>
</ul></td>
<td><p><strong>장애 복구 프로세스가 진행 되는 동안:</strong></p>
<ul>
<li><p>통화 연결 유지</p></li>
</ul>
<p><strong>장애 복구 완료 후:</strong></p>
<ul>
<li><p>통화 연결 유지</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

