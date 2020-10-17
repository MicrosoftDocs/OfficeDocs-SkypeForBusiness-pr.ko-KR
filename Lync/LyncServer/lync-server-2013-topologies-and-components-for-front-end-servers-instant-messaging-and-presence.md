---
title: 'Lync Server 2013: 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 토폴로지 및 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 103d03920df57023ae7dbb953beb0c426d0a43df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503755"
---
# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 토폴로지 및 구성 요소

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-10-24_

IM (인스턴트 메시징) 및 현재 상태에 필요한 구성 요소는 다음과 같습니다.

  - 조직의 프런트 엔드 서버 또는 Standard Edition 서버 이러한 서버에서 IM 및 현재 상태 기능을 항상 사용할 수 있습니다.

  - 부하 분산 장치 (Enterprise Edition 프런트 엔드 풀이 있는 경우) 자세한 내용은 [Lync Server 2013의 부하 분산 요구 사항](lync-server-2013-load-balancing-requirements.md)를 참조 하세요.

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>프런트 엔드 풀 배포 계획

Lync Server 2013에서는 프런트 엔드 풀 아키텍처가 변경 되었으며, 이러한 변경 사항에 따라 프런트 엔드 풀을 계획 하 고 유지 관리 하는 방법에 영향을 줍니다.

모든 Enterprise Edition 프런트 엔드 풀에는 세 개 이상의 프런트 엔드 서버가 포함 되는 것이 좋습니다. Lync Server에서 프런트 엔드 풀의 아키텍처는 분산 시스템 모델을 사용 하며 각 사용자의 데이터는 풀의 세 프런트 엔드 서버에 보관 됩니다. 이 새로운 아키텍처에 대 한 자세한 내용은 [Lync Server 2013의 토폴로지 변경 사항을](lync-server-2013-topology-changes.md)참조 하세요.

세 개의 Enterprise Edition 프런트 엔드 서버를 배포 하 고 재해 복구를 수행 하지 않으려면 Lync Server Standard Edition을 사용 하 고 쌍으로 된 백업 관계로 두 개의 풀을 만드는 것이 좋습니다. 이렇게 하면 서버가 두 대 인 재해 복구 솔루션을 제공 합니다. 고가용성 및 재해 복구 토폴로지와 기능에 대 한 자세한 내용은 [Lync Server 2013에서 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하십시오.

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>프런트 엔드 풀 관리 계획

프런트 엔드 풀의 경우이 섹션의 지침을 따릅니다.

<div>

## <a name="ensuring-that-pools-are-functional"></a>풀이 작동 하는지 확인

프런트 엔드 풀에 대 한 새 분산 모델을 사용 하는 경우 풀이 작동 하려면 풀 서버의 특정 번호가 실행 중 이어야 합니다. 풀에는 두 가지 손실 모드를 사용할 수 있습니다.

  - 특정 라우팅 그룹에 대 한 복제본 서버가 부족 하 여 라우팅 그룹 수준 쿼럼 손실이 발생 했습니다. 라우팅 그룹은 풀에 속한 사용자 집합의 집합체입니다. 각 라우팅 그룹에는 하나의 기본 및 두 보조를 하나씩 포함 하 여 풀의 복제본이 세 개 있습니다.

  - 풀 수준 쿼럼 손실 (풀에서 시드 서버가 충분히 실행 되지 않을 때 발생 하는 경우)

<div>

## <a name="routing-group-level-quorum-loss"></a>라우팅 그룹 수준 쿼럼 손실

새 프런트 엔드 풀을 처음 시작 하는 경우에는 다음 표에 나와 있는 것과 같이 서버 중에서 1 ~ 85%가 작동 하는 것이 중요 합니다. 실행 중인 서버가 적으면 서비스가 시작 상태에 걸려 풀이 시작 되지 않을 수 있습니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>풀에 있는 총 서버 수</th>
<th>풀을 처음 시작할 때 실행 해야 하는 서버 수</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1 </p></td>
</tr>
<tr class="even">
<td><p>3(sp3)</p></td>
<td><p>3(sp3)</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>3(sp3)</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>4 </p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>5 </p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>5 </p></td>
</tr>
<tr class="odd">
<td><p>8 </p></td>
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>9 </p></td>
<td><p>7 </p></td>
</tr>
<tr class="odd">
<td><p>10  </p></td>
<td><p>8 </p></td>
</tr>
<tr class="even">
<td><p>11 </p></td>
<td><p>9 </p></td>
</tr>
<tr class="odd">
<td><p>12 </p></td>
<td><p>10  </p></td>
</tr>
</tbody>
</table>


그 다음에 풀을 시작할 때마다 서버의 85% (위 표에 표시 된 대로)가 시작 되어야 합니다. 이 서버 수를 시작할 수 없지만 풀 수준 쿼럼 손실에 해당 되지 않도록 충분 한 서버를 시작할 수 있으면 **Reset-reset-cspoolregistrarstate – ResetType QuorumLossRecovery** cmdlet을 사용 하 여 풀을이 라우팅 그룹 수준 쿼럼 손실에서 복구 하 고 작업을 진행할 수 있습니다. 이 cmdlet을 사용 하는 방법에 대 한 자세한 내용은 [Reset-reset-cspoolregistrarstate](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState)를 참조 하십시오.

<div>


> [!NOTE]  
> Lync Server에서는 기본 SQL 데이터베이스를 미러링 모니터로 사용 하기 때문에 기본 데이터베이스를 종료 하 고 미러 복사본으로 전환한 다음 충분 한 프런트 엔드 서버를 종료 하 여 앞의 표에 따라 충분히 실행 되지 않도록 하려면 전체 풀이 다운 됩니다. 자세한 내용은 <A href="https://go.microsoft.com/fwlink/?linkid=393672">데이터베이스 미러링 모니터 서버</A>를 참조 하세요.



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>풀 수준 쿼럼 손실

프런트 엔드 풀은 모두 작동 하기 위해 풀 수준의 쿼럼 손실 일 수 없습니다. 실행 중인 서버의 수가 다음 표에 나와 있는 것 처럼 기능 수준 아래로 떨어지면 풀의 나머지 서버가 모든 Lync Server 서비스를 중지 합니다. 다음 표의 숫자는 풀의 백 엔드 서버가 실행 되 고 있다고 가정 합니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>풀에 있는 총 프런트 엔드 서버 수</th>
<th>풀 작동을 위해 실행되어야 하는 서버 수</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1 </p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>모두 2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>모두 3</p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>모든 4</p></td>
</tr>
<tr class="odd">
<td><p>8-9</p></td>
<td><p>처음 7 개 서버 중 하나라도</p></td>
</tr>
<tr class="even">
<td><p>10-12</p></td>
<td><p>처음 9 대의 서버 5 개</p></td>
</tr>
</tbody>
</table>


위의 표에서 첫 번째 서버는 풀이 처음으로 시작 된 경우 시간순으로 나열 되는 서버입니다. 이러한 서버를 확인 하려면 **– Poolfqdn** 옵션을 사용 하 여 **Get cscomputer** cmdlet을 사용할 수 있습니다. 이 cmdlet은 토폴로지에 표시 되는 순서 대로 서버를 표시 하며, 목록 맨 위에 있는 서버가 첫 번째 서버입니다.

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>두 개의 프런트 엔드 서버를 포함 하는 프런트 엔드 풀

두 개의 프런트 엔드 서버만 포함 된 프런트 엔드 풀을 배포 하는 것은 권장 되지 않습니다. 이러한 풀을 배포 해야 하는 경우 다음 지침을 따릅니다.

  - 두 프런트 엔드 서버 중 하나가 다운 되 면 가능 하면 즉시 실패 한 서버를 백업 해 보십시오. 마찬가지로, 두 서버 중 하나를 업그레이드 해야 하는 경우 업그레이드가 완료 되는 즉시 다시 온라인 상태로 전환 합니다.

  - 어떤 이유로 두 서버를 동시에 가져오는 데 필요한 경우 풀에 대 한 가동 중지 시간이 완료 되 면 다음을 수행 합니다.
    
      - 가장 좋은 방법은 두 프런트 엔드 서버를 동시에 다시 시작 하는 것입니다.
    
      - 두 서버를 동시에 다시 시작할 수 없는 경우에는 다운 된 순서와 순서가 거꾸로 복원 되도록 해야 합니다.
    
      - 해당 순서 대로 백업할 수 없는 경우 풀을 백업 하기 전에 다음 cmdlet을 사용 합니다.
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>풀이 작동 하도록 확인 하기 위한 추가 단계

프런트 엔드 풀이 계속 작동 되도록 하려면 몇 가지 다른 요인을 살펴봐야 합니다.

  - 사용자를 처음으로 풀로 이동할 때는 프런트 엔드 서버 중 세 개 이상이 실행 되 고 있어야 합니다.

  - 이 풀과 재해 복구를 위해 다른 풀 간의 연결 관계를 설정 하는 경우 해당 관계를 설정한 후에는이 풀에 백업 풀과 데이터를 올바르게 동기화 하기 위해 일정 시간 동안 동시에 실행 되는 세 개의 프런트 엔드 서버가 있는지를 파악 해야 합니다. 풀 페어링 및 재해 복구 기능에 대 한 자세한 내용은 [Lync Server 2013에서 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요.

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>풀 업그레이드의 안정성 향상

프런트 엔드 풀에서 서버를 업그레이드 하거나 패치 해야 하는 경우에는 [Lync Server 2013의 프런트 엔드 서버 업그레이드 또는 업데이트](lync-server-2013-upgrade-or-update-front-end-servers.md)에 표시 된 워크플로를 따르고 다음 지침을 따릅니다.

  - 업그레이드를 위해 업그레이드를 수행 하는 경우 (예를 들어 [Lync Server 2013의 프런트 엔드 서버를 업데이트 하거나 업그레이드할](lync-server-2013-upgrade-or-update-front-end-servers.md)때의 워크플로를 팔 로우 하는 경우) **get-cspoolupgradereadinessstate** cmdlet을 사용 하 여 준비 상태를 확인 합니다. "Ready"에 도달 하면 각 업그레이드 도메인 사이에 20 분의 대기 시간을 추가 하면 업그레이드가 보다 안정적으로 수행 됩니다. 20 분 동안 **준비 되지** 않으면 20 분 타이머를 다시 시작 합니다. 또한 20 분 간격을 시작 하기 전이나 후에 **get-cspoolfabricstate** cmdlet을 실행 하 고 라우팅 그룹의 기본 및 보조가 변경 되지 않았는지 확인할 수 있습니다.

  - 마지막으로 패치 된 업그레이드 도메인에 있는 서버 중 하나라도 중지 되거나 다시 시작 되지 않으면 다음 업그레이드 도메인으로 이동 하지 마십시오. 이는 업그레이드 내에서 서버를 시작할 수 없는 경우에도 적용 됩니다. **Get-cspoolfabricstate** 를 실행 하 여 모든 라우팅 그룹에 기본 및 하나 이상의 보조가 있는지 확인 합니다. 이렇게 하면 모든 사용자에 게 서비스가 있는지 여부가 확인 됩니다.

  - 일부 사용자에 게 서비스가 있는 경우-Verbose 옵션을 사용 하 여 **get-cspoolfabricstate** 를 실행 하 여 복제본이 없는 라우팅 그룹을 확인 합니다. 전체 풀을 첫 번째 문제 해결 단계로 다시 시작 하지 마십시오. 이 cmdlet에 대 한 자세한 내용은 [get-cspoolfabricstate](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState)를 참조 하십시오.

  - 이벤트 뷰어 또는 성능 모니터 창의 모든 인스턴스가 windows fabric 설치/제거를 위해 닫혀 있는지 확인 합니다.

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>프런트 엔드 풀의 구성 변경

프런트 엔드 서버를 풀에 추가 하거나 풀에서 제거한 다음 새 토폴로지를 게시할 때마다 다음 지침을 따릅니다.

  - 새 토폴로지가 게시 된 후에 풀에서 각 프런트 엔드 서버를 다시 시작 해야 합니다. 한 번에 하나씩 다시 시작 합니다.

  - 구성 변경 중에 전체 풀이 다운 된 경우 새 토폴로지를 게시 한 후 다음 cmdlet을 실행 합니다.
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

프런트 엔드 서버에 오류가 발생 하 여 며칠 이상 교체 될 가능성이 없는 경우 토폴로지에서 해당 서버를 제거 합니다. 새 프런트 엔드 서버를 다시 사용할 수 있게 되 면 토폴로지에 추가 합니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

