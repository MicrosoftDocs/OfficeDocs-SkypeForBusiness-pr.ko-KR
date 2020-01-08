---
title: Lync Server 재해 복구, 고가용성 및 백업 서비스 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cada393fca28895ee5f23a12fdd55eabd211128e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a>Lync Server 2013 재해 복구, 고가용성 및 백업 서비스 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-11-12_

이 섹션에는 장애 복구 작업에 대 한 절차가 포함 되어 있으며, 쌍으로 된 프런트 엔드 풀의 데이터를 동기화 하는 백업 서비스를 유지 관리 하는 절차도 나와 있습니다.

재난 복구 절차 (장애 조치와 장애 복구)는 모두 수동입니다. 재해가 발생 하는 경우 관리자가 장애 조치 절차를 수동으로 호출 해야 합니다. 풀이 복구 된 후에도 장애 복구에 적용 됩니다.

이 섹션의 나머지 부분에 있는 재해 복구 절차는 다음과 같이 가정 합니다.

  - [Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)에 설명 된 바와 같이 서로 다른 사이트에 있는 쌍으로 이루어진 프런트 엔드 풀을 배포 하는 경우 동기화를 유지 하기 위해이 쌍의 풀에서 백업 서비스를 실행 하 고 있습니다.

  - 중앙 관리 저장소가 풀에서 호스트 되는 경우 두 연결 된 풀에 설치 되 고 실행 되며, 활성 마스터를 호스트 하는 풀 중 하나를 사용 하 고 대기를 호스팅하는 다른 풀에 연결 됩니다.

<div>


> [!IMPORTANT]
> 다음 절차에서 <EM>poolfqdn</EM> 매개 변수는 영향을 받는 사용자가 리디렉션되는 풀이 아닌 재해의 영향을 받는 풀의 FQDN을 나타냅니다. 동일한 영향을 받는 사용자 집합의 경우 장애 조치 및 장애 복구 cmdlet (즉, 장애 조치 전에 사용자를 먼저 홈으로 설정한 풀)에서 동일한 풀을 참조 합니다.<BR>예를 들어 풀 P1에 속한 모든 사용자가 백업 풀 (P2)로 장애 조치 되는 경우를 가정해 보겠습니다. 관리자가 현재 P2에서 서비스를 제공 하는 모든 사용자를 P1에서 처리 하려는 경우 관리자는 다음 단계를 수행 해야 합니다. 
> <OL>
> <LI>
> <P>장애 복구 cmdlet을 사용 하 여 P1에서 원래 홈으로 설정 된 모든 사용자를 P2에서 P1으로 다시 복구 합니다. 이 경우 <EM>Poolfqdn</EM> 은 P1's fqdn입니다.</P>
> <LI>
> <P>P2에 원래 있는 모든 사용자가 장애 조치 cmdlet을 사용 하 여 P1으로 장애 조치 합니다. 이 경우 <EM>Poolfqdn</EM> 은 P2's fqdn입니다.</P>
> <LI>
> <P>나중에 관리자가 p2 사용자를 P2로 다시 장애 복구 하려는 경우 <EM>Poolfqdn</EM> 은 P2's fqdn입니다.</P></LI></OL>풀 무결성을 유지 하려면 위의 1 단계를 2 단계 전에 수행 해야 합니다. 1 단계 전에 2 단계를 수행 하면 2 단계 cmdlet이 실패 합니다.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013에서 백업 서비스 구성 및 모니터링](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [Lync Server 2013 에서 풀 장애 조치(failover)](lync-server-2013-failing-over-a-pool.md)

  - [Lync Server 2013에서 풀 장애 복구(failback)](lync-server-2013-failing-back-a-pool.md)

  - [Lync Server 2013에서 미러된 데이터베이스 장애 조치(failover)](lync-server-2013-failing-over-a-mirrored-database.md)

  - [Lync Server 2013에서 Lync Server 페더레이션에 사용되는 에지 풀 장애 조치(failover)](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [Lync Server 2013에서 XMPP 페더레이션에 사용되는 에지 풀 장애 조치(failover)](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [Lync Server 2013에서 Lync Server 페더레이션 또는 XMPP 페더레이션에 사용되는 에지 풀 장애 복구(failback)](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [Lync Server 2013에서 프런트 엔드 풀과 연결된 에지 풀 변경](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [Lync Server 2013에서 백업 서비스로 전화 회의 내용 복원](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

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

