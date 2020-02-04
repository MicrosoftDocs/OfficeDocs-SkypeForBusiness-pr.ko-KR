---
title: 'Lync Server 2013: 프런트 엔드 서버, 메신저 및 현재 상태에 대한 토폴로지 및 구성 요소'
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
ms.openlocfilehash: 181ae682ec5ee1352c5d4f4280b4164fbbcd91f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Lync Server 2013 의 프런트 엔드 서버, 메신저 및 현재 상태에 대한 토폴로지 및 구성 요소

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-10-24_

인스턴트 메시징 (IM) 및 현재 상태에 필요한 유일한 구성 요소는 다음과 같습니다.

  - 조직의 프런트 엔드 서버 또는 Standard Edition 서버 이러한 서버에서 IM 및 현재 상태 접근 권한 값을 항상 사용할 수 있습니다.

  - 부하 분산 장치 (Enterprise Edition 프런트 엔드 풀을 사용 하는 경우) 자세한 내용은 [Lync Server 2013의 부하 분산 요구 사항](lync-server-2013-load-balancing-requirements.md)을 참조 하세요.

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>프런트 엔드 풀 배포 계획

Lync Server 2013에서는 프런트 엔드 풀 아키텍처가 변경 되었으며, 이러한 변경 사항은 프런트 엔드 풀을 계획 하 고 유지 관리 하는 방법에 영향을 줍니다.

모든 Enterprise Edition 프런트 엔드 풀에는 프런트 엔드 서버가 세 대 이상 포함 되는 것이 좋습니다. Lync Server에서 프런트 엔드 풀의 아키텍처는 분산 시스템 모델을 사용 하 고 각 사용자의 데이터는 풀의 프런트 엔드 서버 세 대로 유지 됩니다. 이 새로운 아키텍처에 대 한 자세한 내용은 [Lync Server 2013의 토폴로지 변경 사항을](lync-server-2013-topology-changes.md)참조 하세요.

세 개의 Enterprise Edition 프런트 엔드 서버를 배포 하지 않고 재해 복구를 수행 하려는 경우 Lync Server Standard Edition을 사용 하 고 두 개의 풀을 연결 하 여 쌍을 이루는 백업 관계로 만드는 것이 좋습니다. 이렇게 하면 서버가 두 대 인 재난 복구 솔루션을 제공 합니다. 고가용성 및 재해 복구 토폴로지와 기능에 대 한 자세한 내용은 [Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요.

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>프런트 엔드 풀 관리 계획

프런트 엔드 풀의 경우이 섹션의 지침을 따릅니다.

<div>

## <a name="ensuring-that-pools-are-functional"></a>풀이 작동 하는지 확인

프런트 엔드 풀에 대 한 새 분산 모델을 사용 하는 경우 풀이 작동 하려면 풀 서버의 특정 번호가 실행 중 이어야 합니다. 풀에는 두 가지 손실 모드가 있습니다.

  - 라우팅 그룹 수준 쿼럼 손실, 특정 라우팅 그룹에 대 한 복제본 서버가 부족 하 여 발생 합니다. 라우팅 그룹은 풀에 속한 사용자 집합의 집합체입니다. 각 라우팅 그룹에는 풀에 세 개의 복제본 (주 1 개와 보조 2 개)이 있습니다.

  - 풀에 시드 서버가 충분히 실행 되 고 있지 않은 경우 발생 하는 풀 수준 쿼럼 손실.

<div>

## <a name="routing-group-level-quorum-loss"></a>라우팅 그룹 수준 쿼럼 손실

새 프런트 엔드 풀을 처음 시작 하는 경우에는 다음 표에 표시 된 대로 서버의 85%가 작동 하 고 실행 되 고 있어야 합니다. 실행 중인 서버 수가 적은 경우 서비스는 시작 상태에 멈춰 있을 수 있으며 풀이 시작 되지 않을 수 있습니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>풀의 총 서버 수</th>
<th>풀이 처음 시작 될 때 실행 되어야 하는 서버 수</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
</tr>
<tr class="odd">
<td><p>4(tcp/ipv4)</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>5mb</p></td>
<td><p>4(tcp/ipv4)</p></td>
</tr>
<tr class="odd">
<td><p>26</p></td>
<td><p>5mb</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>5mb</p></td>
</tr>
<tr class="odd">
<td><p>20cm(8</p></td>
<td><p>26</p></td>
</tr>
<tr class="even">
<td><p>되었는지</p></td>
<td><p>7</p></td>
</tr>
<tr class="odd">
<td><p>1천만</p></td>
<td><p>20cm(8</p></td>
</tr>
<tr class="even">
<td><p>mb</p></td>
<td><p>되었는지</p></td>
</tr>
<tr class="odd">
<td><p>까지</p></td>
<td><p>1천만</p></td>
</tr>
</tbody>
</table>


이후 풀이 시작 될 때마다 서버의 85%가 시작 되어야 합니다 (앞의 표에 표시 된 대로). 이 서버 수를 시작할 수 없는 경우 (풀 수준의 쿼럼 손실에 해당 되지 않도록 충분 한 서버를 시작할 수 있음) **Reset-CsPoolRegistrarState – ResetType QuorumLossRecovery** cmdlet을 사용 하 여 풀을이 라우팅 그룹 수준 쿼럼 손실에서 복구 하 고 진행을 진행할 수 있습니다. 이 cmdlet을 사용 하는 방법에 대 한 자세한 내용은 [-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState)을 참조 하세요.

<div>


> [!NOTE]  
> Lync Server는 기본 SQL 데이터베이스를 미러링 모니터로 사용 하기 때문에 기본 데이터베이스를 종료 하 고 미러 복사본으로 전환 하 여 앞의 표에 따라 실행 되지 않도록 충분 한 프런트 엔드 서버를 종료 하면 전체 풀이 중단 됩니다. 자세한 내용은 <A href="http://go.microsoft.com/fwlink/?linkid=393672">데이터베이스 미러링 감시</A>를 참조 하세요.



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>풀 수준 쿼럼 손실

프런트 엔드 풀은 전혀 작동 하기 위해 풀 수준의 쿼럼 손실 일 수 없습니다. 실행 중인 서버 수가 다음 표에 나와 있는 것 처럼 기능 수준 아래로 떨어지면 풀의 나머지 서버가 모든 Lync Server 서비스를 중지 합니다. 다음 표의 숫자는 풀의 백 엔드 서버가 실행 되 고 있는 것으로 가정 합니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>풀의 총 프런트 엔드 서버 수</th>
<th>풀을 작동 하기 위해 실행 해야 하는 서버 수</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>모든 2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>모든 3</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>모든 4</p></td>
</tr>
<tr class="odd">
<td><p>8-9</p></td>
<td><p>처음 7 대의 서버 중 4 대</p></td>
</tr>
<tr class="even">
<td><p>10-12</p></td>
<td><p>처음 9 대의 서버 5 대</p></td>
</tr>
</tbody>
</table>


앞의 표에서 "첫 번째 서버"는 풀이 처음으로 시작 된 시점에 시간순으로 나열 된 서버입니다. 이러한 서버를 확인 하기 위해 **– Poolfqdn** 옵션으로 **Get-cscomputer** cmdlet을 사용할 수 있습니다. 이 cmdlet은 토폴로지에 표시 되는 순서 대로 서버를 표시 하 고 목록의 맨 위에는 첫 번째 서버가 됩니다.

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>두 개의 프런트 엔드 서버가 있는 프런트 엔드 풀

프런트 엔드 서버를 두 대만 포함 하는 프런트 엔드 풀은 배포 하지 않는 것이 좋습니다. 이러한 풀을 배포 해야 하는 경우 다음 지침을 따릅니다.

  - 두 프런트 엔드 서버 중 하나가 중단 되 면 가능한 한 빨리 실패 한 서버를 다시 온라인 상태로 만들어야 합니다. 마찬가지로, 두 서버 중 하나를 업그레이드 해야 하는 경우 업그레이드가 완료 되는 즉시 다시 온라인 상태로 전환 합니다.

  - 어떤 이유로 두 서버를 동시에 종료 해야 하는 경우 풀의 가동 중지 시간이 완료 되 면 다음을 수행 합니다.
    
      - 가장 좋은 방법은 프런트 엔드 서버를 동시에 다시 시작 하는 것입니다.
    
      - 두 서버를 동시에 다시 시작할 수 없는 경우에는 그 순서의 역순으로 백업 해야 합니다.
    
      - 해당 순서 대로 백업할 수 없는 경우 풀을 다시 가져오려면 다음 cmdlet을 사용 합니다.
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>풀이 작동 하도록 하는 추가 단계

프런트 엔드 풀이 작동 하는 것을 방지 하기 위해 몇 가지 다른 요인에 유의 해야 합니다.

  - 사용자를 처음으로 풀로 이동 하는 경우 프런트 엔드 서버가 세 개 이상 실행 되 고 있는지 확인 합니다.

  - 이 풀과 재해 복구용에 대 한 다른 풀 간의 페어링 관계를 설정 하는 경우 해당 관계를 설정한 후에는이 풀에 동시에 실행 되는 세 개의 프런트 엔드 서버가 있어야 올바르게 동기화 할 수 있습니다. 백업 풀을 사용 하 여 데이터 풀 페어링 및 재해 복구 기능에 대 한 자세한 내용은 [Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요.

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>풀 업그레이드의 안정성 개선

프런트 엔드 풀에서 서버를 업그레이드 하거나 패치 해야 하는 경우에는 [Lync Server 2013의 프런트 엔드 서버 업그레이드 또는 업데이트](lync-server-2013-upgrade-or-update-front-end-servers.md)에 표시 된 워크플로를 따르고 다음 지침을 참조 하세요.

  - 업그레이드에 대 한 업그레이드 도메인 간에 이동 하는 경우 (예를 들어 [Lync Server 2013의 프런트 엔드 서버 업데이트](lync-server-2013-upgrade-or-update-front-end-servers.md)에서 워크플로를 팔 로우) **CsPoolUpgradeReadinessState** cmdlet을 사용 하 고 준비 상태를 확인 합니다. 각 업그레이드 도메인 사이에 20 분의 대기 시간을 추가 하면 "준비"에 도달한 후에는 업그레이드를 더욱 안정적으로 만들 수 있습니다. 20 분 동안 **준비 되지** 않으면 20 분 타이머를 다시 시작 합니다. 또한 20 분 간격을 시작 하기 전과 후에 **CsPoolFabricState** cmdlet을 실행 하 고 라우팅 그룹의 일부 및 보조 항목이 변경 되지 않도록 할 수 있습니다.

  - 마지막으로 패치가 적용 된 업그레이드 도메인의 서버 중 하나가 중지 되거나 다시 시작 되지 않는 경우 다음 업그레이드 도메인으로 이동 하지 마세요. 이는 업그레이드 내의 모든 서버를 시작할 수 없는 경우에도 적용 됩니다. **CsPoolFabricState** 를 실행 하 여 모든 라우팅 그룹에 기본 및 하나 이상의 보조 권한이 있는지 확인 합니다. 이렇게 하면 모든 사용자가 서비스를 보유 하 고 있는지 확인 합니다.

  - 일부 사용자가 서비스를 보유 하 고 있지 않은 경우 – Verbose 옵션을 사용 하 여 **CsPoolFabricState** 를 실행 하 여 복제본이 없는 라우팅 그룹을 확인 합니다. 첫 번째 문제 해결 단계로 전체 풀을 다시 시작 하지 마세요. 이 cmdlet에 대 한 자세한 내용은 Get-help를 참조 하세요 [CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).

  - Windows fabric 설치/제거에 대해 이벤트 뷰어 또는 성능 모니터 창의 모든 인스턴스가 닫혀 있는지 확인 합니다.

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>프런트 엔드 풀의 구성 변경

프런트 엔드 서버를 풀에 추가 하거나 풀에서 제거한 다음 새 토폴로지를 게시 하는 경우 다음 지침을 따릅니다.

  - 새 토폴로지가 게시 된 후에 풀에서 각 프런트 엔드 서버를 다시 시작 해야 합니다. 한 번에 하나씩 다시 시작 합니다.

  - 구성 변경 중 전체 풀이 중단 되 면 새 토폴로지가 게시 된 후 다음 cmdlet을 실행 합니다.
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

프런트 엔드 서버에 오류가 발생 하 여 며칠 이상 교체할 수 없는 경우 토폴로지에서 서버를 제거 합니다. 다시 사용할 수 있게 되 면 토폴로지에 새 프런트 엔드 서버를 추가 합니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

