---
title: 'Lync Server 2013: 재해 복구 중 그룹 통화 픽업 관리'
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
ms.openlocfilehash: f58894a00c853f04d5d4c6f995edc17683b12e9f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013에서 재해 복구를 수행 하는 동안 그룹 통화 픽업 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-01-30_

계획 되지 않은 문제로 인해 프런트 엔드 풀을 사용할 수 없게 되 면 서비스가 백업 풀로 장애 조치 (failover) 됩니다. 백업 풀로 장애 조치 (failover) 중에 사용자가 백업 풀로 리디렉션되어 복원 모드에 있습니다. 복구 모드에서는 사용자가 다른 사용자의 통화를 선택 하거나 전화를 다른 사용자가 선택할 수 없습니다. 장애 조치 (failover)가 완료 되 면 사용자는 평소와 같이 그룹 통화 픽업을 다시 사용할 수 있습니다.

기본 풀로의 장애 복구 (failback) 중에는 사용자가 기본 풀로 리디렉션되어 복원 모드에서 다시 수행 됩니다. 사용자가 복구 모드를 해제할 때 까지는 그룹 통화 픽업 기능을 사용할 수 없습니다.

이 섹션에서는 재해 복구 중에 그룹 통화 픽업에 대 한 몇 가지 고려 사항을 설명 하 고 사용자 환경에 대해서도 설명 합니다.

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a>재해 복구 시 그룹 통화 픽업 고려 사항

재해 복구 중에 장애 조치 (failover) 프로세스의 일부로 백업 풀로 리디렉션된 사용자는 통화 픽업 그룹 번호에 대해 백업 풀에서 실행 되는 통화 대기 응용 프로그램을 사용 합니다. 따라서 재해 복구 중에 그룹 통화 픽업 지원을 사용 하려면 기본 풀과 백업 풀에서 모두 통화 대기 응용 프로그램을 배포 하 고 사용 하도록 설정 해야 합니다.

통화 대기 번호 테이블의 그룹 통화 픽업 수 범위는 백업 풀에 대 한 장애 조치 (failover) 프로세스가 완료 된 후 백업 풀로 리디렉션해야 합니다. 기본 풀에 대 한 장애 복구 프로세스가 완료 된 후 번호 범위를 주 풀로 다시 리디렉션해야 합니다. 그룹 통화 픽업 범위를 리디렉션하려면 **get-cscallparkorbit** cmdlet을 사용 합니다.

기본 풀을 대체 하기 위해 다른 FQDN (정규화 된 도메인 이름)을 사용 하 여 새 풀을 배포 하는 경우 기본 풀과 연결 된 모든 그룹 통화 픽업 번호 범위를 새 풀의 FQDN으로 다시 할당 해야 합니다. 번호 범위를 새 풀에 다시 할당 하려면 **get-cscallparkorbit** cmdlet을 사용 하면 됩니다. **Get-cscallparkorbit** cmdlet에 대 한 자세한 내용은 [get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)를 참조 하십시오.

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a>풀 오류 발생 시 그룹 통화 픽업 환경

다음 표에서는 재해 복구 단계를 통해 그룹 통화 픽업 경험을 요약 하 여 보여 줍니다.

### <a name="user-experience-during-disaster-recovery"></a>재해 복구 시 사용자 환경

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>통화 상태</th>
<th>백업 풀에 대 한 장애 조치 (Failover)</th>
<th>기본 풀 장애 복구 (Failback)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>새 통화</p></td>
<td><p><strong>장애 조치 (failover) 프로세스 중:</strong></p>
<ul>
<li><p>복원 모드의 사용자는 그룹 통화 픽업을 사용할 수 없음</p></li>
</ul>
<p><strong>장애 조치 (failover) 완료 후:</strong></p>
<ul>
<li><p>그룹 통화 픽업 사용자 복구 및 그룹 통화 픽업 번호 범위가 백업 풀로 리디렉션될 때 사용할 수 있습니다.</p></li>
</ul></td>
<td><p><strong>장애 복구 프로세스 중:</strong></p>
<ul>
<li><p>복원 모드의 사용자는 그룹 통화 픽업을 사용할 수 없음</p></li>
</ul>
<p><strong>장애 복구 (failback) 완료 후:</strong></p>
<ul>
<li><p>그룹 통화 픽업 사용자 복구 및 그룹 통화 픽업 번호 범위가 기본 풀로 다시 리디렉션될 때 사용할 수 있습니다.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>그룹 통화 픽업 큐의 통화</p></td>
<td><p><strong>장애 조치 (failover) 프로세스 중:</strong></p>
<ul>
<li><p>그룹 통화 픽업를 통해 큐의 통화에 응답할 수 없습니다.</p></li>
</ul>
<p><strong>장애 조치 (failover) 완료 후:</strong></p>
<ul>
<li><p>이 상태의 통화 없음</p></li>
</ul></td>
<td><p><strong>장애 복구 프로세스 중:</strong></p>
<ul>
<li><p>그룹 통화 픽업를 통해 큐의 통화에 응답할 수 없습니다.</p></li>
</ul>
<p><strong>장애 복구 (failback) 완료 후:</strong></p>
<ul>
<li><p>그룹 통화 픽업를 통해 큐의 통화에 응답할 수 없습니다.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>통화 설정</p></td>
<td><p><strong>장애 조치 (failover) 프로세스 중:</strong></p>
<ul>
<li><p>통화를 계속 연결</p></li>
</ul>
<p><strong>장애 조치 (failover) 완료 후:</strong></p>
<ul>
<li><p>통화를 계속 연결</p></li>
</ul></td>
<td><p><strong>장애 복구 프로세스 중:</strong></p>
<ul>
<li><p>통화를 계속 연결</p></li>
</ul>
<p><strong>장애 복구 (failback) 완료 후:</strong></p>
<ul>
<li><p>통화를 계속 연결</p></li>
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

