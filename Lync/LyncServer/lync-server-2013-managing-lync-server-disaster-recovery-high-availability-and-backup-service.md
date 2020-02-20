---
title: Lync Server 재해 복구, 고가용성 및 백업 서비스 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7ee9bd75ce0f9326c06ffda28a48193749a950c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>Lync Server 2013 재해 복구, 고가용성 및 백업 서비스 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-11-12_

이 섹션에는 연결된 프런트 엔드 풀의 데이터를 동기화하는 백업 서비스를 백업 서비스를 유지 관리하는 작업과 재해 복구 작업에 대한 절차가 포함되어 있습니다.

장애 조치(failover)와 장애 복구(failback)라는 재해 복구 절차는 둘 다 수동 절차입니다. 따라서 재해가 발생한 경우 관리자는 장애 조치(failover) 절차를 직접 호출해야 합니다. 풀이 복구된 이후의 장애 복구(failback)에도 동일한 절차가 적용됩니다.

이 섹션의 나머지 부분에 나오는 재해 복구 절차는 다음을 전제로 합니다.

  - [Lync Server 2013에서 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)에 설명 된 대로 서로 다른 사이트에 있는 쌍으로 된 프런트 엔드 풀을 사용 하 여 배포를 진행 하 고 있습니다. 백업 서비스가 이러한 연결된 풀에서 실행되어 이들 풀을 동기화 상태로 유지하고 있습니다.

  - 중앙 관리 저장소를 두 풀에서 호스트 하는 경우 연결 된 모든 풀에 설치 되 고 실행 되며, 활성 마스터를 호스트 하는 풀과 대기를 호스트 하는 풀 중 하나가 사용 됩니다.

<div>


> [!IMPORTANT]
> 다음 절차에서 <EM>PoolFQDN</EM> 매개 변수는 영향을 받는 사용자가 리디렉션되는 풀이 아니라 재해에 영향을 받는 풀의 FQDN을 나타냅니다. 영향을 받는 일부 사용자의 경우 장애 조치(failover) 및 장애 복구(failback) cmdlet에서 동일한 풀(즉 장애 조치(failover) 전에 사용자가 있던 풀)을 참조합니다.<BR>예를 들어, 풀 P1에 있는 모든 사용자가 백업 풀 P2로 장애 조치(failover)된다고 가정해 보겠습니다. 관리자가 현재 P2에서 서비스를 받는 모든 사용자를 P1에서 서비스를 받도록 옮기려는 경우 관리자는 다음 단계를 수행해야 합니다. 
> <OL>
> <LI>
> <P>장애 복구(failback) cmdlet을 사용하여 원래 P1에 있던 모든 사용자를 P2에서 P1으로 장애 복구(failback)합니다. 이 경우 <EM>PoolFQDN</EM>이 P1의 FQDN입니다.</P>
> <LI>
> <P>장애 조치(failover) cmdlet을 사용하여 원래 P2에 있던 모든 사용자를 P1으로 장애 조치(failover)합니다. 이 경우 <EM>PoolFQDN</EM>은 P2의 FQDN입니다.</P>
> <LI>
> <P>관리자가 나중에 이러한 P2 사용자를 다시 P2로 장애 복구(failback)하려는 경우 <EM>PoolFQDN</EM>이 P2의 FQDN입니다.</P></LI></OL>풀 무결성을 유지하려면 위의 1단계를 2단계 전에 수행해야 합니다. 1단계 전에 2단계를 시도하면 2단계 cmdlet이 실패합니다.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 백업 서비스 구성 및 모니터링](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Lync Server 2013에서 풀 장애 조치 (failover)](lync-server-2013-failing-over-a-pool.md)

  - [Lync Server 2013에서 풀 장애 복구 (failback)](lync-server-2013-failing-back-a-pool.md)

  - [Lync Server 2013에서 미러된 데이터베이스 장애 조치 (failover)](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Lync Server 2013의 Lync Server federation에 사용 되는에 지 풀 장애 조치 (failover)](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Lync Server 2013의 XMPP 페더레이션에 사용 되는에 지 풀 장애 조치 (failover)](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Lync Server 2013에서 Lync Server 페더레이션 또는 XMPP 페더레이션에 사용 되는에 지 풀 장애 복구 (failback)](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Lync Server 2013의 프런트 엔드 풀과 연결 된에 지 풀 변경](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Lync Server 2013에서 백업 서비스를 사용 하 여 전화 회의 내용 복원](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

