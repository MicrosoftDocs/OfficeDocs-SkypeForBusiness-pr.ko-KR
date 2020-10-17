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
ms.openlocfilehash: c935a27f737d8ec7fdb012f4e0c13930d20a1319
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498155"
---
# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="6b675-102">Lync Server 2013 재해 복구, 고가용성 및 백업 서비스 관리</span><span class="sxs-lookup"><span data-stu-id="6b675-102">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b675-103">_**마지막으로 수정 된 항목:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="6b675-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="6b675-104">이 섹션에는 연결된 프런트 엔드 풀의 데이터를 동기화하는 백업 서비스를 백업 서비스를 유지 관리하는 작업과 재해 복구 작업에 대한 절차가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b675-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="6b675-p101">장애 조치(failover)와 장애 복구(failback)라는 재해 복구 절차는 둘 다 수동 절차입니다. 따라서 재해가 발생한 경우 관리자는 장애 조치(failover) 절차를 직접 호출해야 합니다. 풀이 복구된 이후의 장애 복구(failback)에도 동일한 절차가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b675-p101">Disaster recovery procedures, both failover and failback, are manual. If there is a disaster, the administrator must manually invoke the failover procedures. The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="6b675-108">이 섹션의 나머지 부분에 나오는 재해 복구 절차는 다음을 전제로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b675-108">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="6b675-109">[Lync Server 2013에서 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)에 설명 된 대로 서로 다른 사이트에 있는 쌍으로 된 프런트 엔드 풀을 사용 하 여 배포를 진행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b675-109">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="6b675-110">백업 서비스가 이러한 연결된 풀에서 실행되어 이들 풀을 동기화 상태로 유지하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b675-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="6b675-111">중앙 관리 저장소를 두 풀에서 호스트 하는 경우 연결 된 모든 풀에 설치 되 고 실행 되며, 활성 마스터를 호스트 하는 풀과 대기를 호스트 하는 풀 중 하나가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b675-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="6b675-p103">다음 절차에서 <EM>PoolFQDN</EM> 매개 변수는 영향을 받는 사용자가 리디렉션되는 풀이 아니라 재해에 영향을 받는 풀의 FQDN을 나타냅니다. 영향을 받는 일부 사용자의 경우 장애 조치(failover) 및 장애 복구(failback) cmdlet에서 동일한 풀(즉 장애 조치(failover) 전에 사용자가 있던 풀)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6b675-p103">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from. For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="6b675-p104">예를 들어, 풀 P1에 있는 모든 사용자가 백업 풀 P2로 장애 조치(failover)된다고 가정해 보겠습니다. 관리자가 현재 P2에서 서비스를 받는 모든 사용자를 P1에서 서비스를 받도록 옮기려는 경우 관리자는 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b675-p104">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2. If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="6b675-p105">장애 복구(failback) cmdlet을 사용하여 원래 P1에 있던 모든 사용자를 P2에서 P1으로 장애 복구(failback)합니다. 이 경우 <EM>PoolFQDN</EM>이 P1의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="6b675-p105">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet. In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="6b675-p106">장애 조치(failover) cmdlet을 사용하여 원래 P2에 있던 모든 사용자를 P1으로 장애 조치(failover)합니다. 이 경우 <EM>PoolFQDN</EM>은 P2의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="6b675-p106">Fail over all the users originally homed on P2 to P1 using the failover cmdlet. In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="6b675-120">관리자가 나중에 이러한 P2 사용자를 다시 P2로 장애 복구(failback)하려는 경우 <EM>PoolFQDN</EM>이 P2의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="6b675-120">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="6b675-121">풀 무결성을 유지하려면 위의 1단계를 2단계 전에 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b675-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="6b675-122">1단계 전에 2단계를 시도하면 2단계 cmdlet이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="6b675-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6b675-123">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="6b675-123">In This Section</span></span>

  - [<span data-ttu-id="6b675-124">Lync Server 2013에서 백업 서비스 구성 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="6b675-124">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="6b675-125">Lync Server 2013에서 풀 장애 조치 (failover)</span><span class="sxs-lookup"><span data-stu-id="6b675-125">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="6b675-126">Lync Server 2013에서 풀 장애 복구 (failback)</span><span class="sxs-lookup"><span data-stu-id="6b675-126">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="6b675-127">Lync Server 2013에서 미러된 데이터베이스 장애 조치 (failover)</span><span class="sxs-lookup"><span data-stu-id="6b675-127">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="6b675-128">Lync Server 2013의 Lync Server federation에 사용 되는에 지 풀 장애 조치 (failover)</span><span class="sxs-lookup"><span data-stu-id="6b675-128">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="6b675-129">Lync Server 2013의 XMPP 페더레이션에 사용 되는에 지 풀 장애 조치 (failover)</span><span class="sxs-lookup"><span data-stu-id="6b675-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="6b675-130">Lync Server 2013에서 Lync Server 페더레이션 또는 XMPP 페더레이션에 사용 되는에 지 풀 장애 복구 (failback)</span><span class="sxs-lookup"><span data-stu-id="6b675-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="6b675-131">Lync Server 2013의 프런트 엔드 풀과 연결 된에 지 풀 변경</span><span class="sxs-lookup"><span data-stu-id="6b675-131">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="6b675-132">Lync Server 2013에서 백업 서비스를 사용 하 여 전화 회의 내용 복원</span><span class="sxs-lookup"><span data-stu-id="6b675-132">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6b675-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b675-133">See Also</span></span>


[<span data-ttu-id="6b675-134">Lync Server 2013의 고가용성 및 재해 복구 계획</span><span class="sxs-lookup"><span data-stu-id="6b675-134">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

