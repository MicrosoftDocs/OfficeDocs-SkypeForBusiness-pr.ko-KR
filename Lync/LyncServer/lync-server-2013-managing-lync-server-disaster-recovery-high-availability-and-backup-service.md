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
ms.openlocfilehash: d7adc4086ac8ac6b8e5ad33c2e4c1dc131d357e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="5b6e7-102">Lync Server 2013 재해 복구, 고가용성 및 백업 서비스 관리</span><span class="sxs-lookup"><span data-stu-id="5b6e7-102">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b6e7-103">_**마지막으로 수정한 주제:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="5b6e7-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="5b6e7-104">이 섹션에는 장애 복구 작업에 대 한 절차가 포함 되어 있으며, 쌍으로 된 프런트 엔드 풀의 데이터를 동기화 하는 백업 서비스를 유지 관리 하는 절차도 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="5b6e7-105">재난 복구 절차 (장애 조치와 장애 복구)는 모두 수동입니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="5b6e7-106">재해가 발생 하는 경우 관리자가 장애 조치 절차를 수동으로 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="5b6e7-107">풀이 복구 된 후에도 장애 복구에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="5b6e7-108">이 섹션의 나머지 부분에 있는 재해 복구 절차는 다음과 같이 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-108">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="5b6e7-109">[Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)에 설명 된 바와 같이 서로 다른 사이트에 있는 쌍으로 이루어진 프런트 엔드 풀을 배포 하는 경우</span><span class="sxs-lookup"><span data-stu-id="5b6e7-109">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="5b6e7-110">동기화를 유지 하기 위해이 쌍의 풀에서 백업 서비스를 실행 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="5b6e7-111">중앙 관리 저장소가 풀에서 호스트 되는 경우 두 연결 된 풀에 설치 되 고 실행 되며, 활성 마스터를 호스트 하는 풀 중 하나를 사용 하 고 대기를 호스팅하는 다른 풀에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="5b6e7-112">다음 절차에서 <EM>poolfqdn</EM> 매개 변수는 영향을 받는 사용자가 리디렉션되는 풀이 아닌 재해의 영향을 받는 풀의 FQDN을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-112">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="5b6e7-113">동일한 영향을 받는 사용자 집합의 경우 장애 조치 및 장애 복구 cmdlet (즉, 장애 조치 전에 사용자를 먼저 홈으로 설정한 풀)에서 동일한 풀을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="5b6e7-114">예를 들어 풀 P1에 속한 모든 사용자가 백업 풀 (P2)로 장애 조치 되는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="5b6e7-115">관리자가 현재 P2에서 서비스를 제공 하는 모든 사용자를 P1에서 처리 하려는 경우 관리자는 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="5b6e7-116">장애 복구 cmdlet을 사용 하 여 P1에서 원래 홈으로 설정 된 모든 사용자를 P2에서 P1으로 다시 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="5b6e7-117">이 경우 <EM>Poolfqdn</EM> 은 P1's fqdn입니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-117">In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="5b6e7-118">P2에 원래 있는 모든 사용자가 장애 조치 cmdlet을 사용 하 여 P1으로 장애 조치 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="5b6e7-119">이 경우 <EM>Poolfqdn</EM> 은 P2's fqdn입니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-119">In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="5b6e7-120">나중에 관리자가 p2 사용자를 P2로 다시 장애 복구 하려는 경우 <EM>Poolfqdn</EM> 은 P2's fqdn입니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-120">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="5b6e7-121">풀 무결성을 유지 하려면 위의 1 단계를 2 단계 전에 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="5b6e7-122">1 단계 전에 2 단계를 수행 하면 2 단계 cmdlet이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b6e7-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5b6e7-123">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="5b6e7-123">In This Section</span></span>

  - [<span data-ttu-id="5b6e7-124">Lync Server 2013에서 백업 서비스 구성 및 모니터링</span><span class="sxs-lookup"><span data-stu-id="5b6e7-124">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="5b6e7-125">Lync Server 2013 에서 풀 장애 조치(failover)</span><span class="sxs-lookup"><span data-stu-id="5b6e7-125">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="5b6e7-126">Lync Server 2013에서 풀 장애 복구(failback)</span><span class="sxs-lookup"><span data-stu-id="5b6e7-126">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="5b6e7-127">Lync Server 2013에서 미러된 데이터베이스 장애 조치(failover)</span><span class="sxs-lookup"><span data-stu-id="5b6e7-127">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="5b6e7-128">Lync Server 2013에서 Lync Server 페더레이션에 사용되는 에지 풀 장애 조치(failover)</span><span class="sxs-lookup"><span data-stu-id="5b6e7-128">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="5b6e7-129">Lync Server 2013에서 XMPP 페더레이션에 사용되는 에지 풀 장애 조치(failover)</span><span class="sxs-lookup"><span data-stu-id="5b6e7-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="5b6e7-130">Lync Server 2013에서 Lync Server 페더레이션 또는 XMPP 페더레이션에 사용되는 에지 풀 장애 복구(failback)</span><span class="sxs-lookup"><span data-stu-id="5b6e7-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="5b6e7-131">Lync Server 2013에서 프런트 엔드 풀과 연결된 에지 풀 변경</span><span class="sxs-lookup"><span data-stu-id="5b6e7-131">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="5b6e7-132">Lync Server 2013에서 백업 서비스로 전화 회의 내용 복원</span><span class="sxs-lookup"><span data-stu-id="5b6e7-132">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5b6e7-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b6e7-133">See Also</span></span>


[<span data-ttu-id="5b6e7-134">Lync Server 2013의 고가용성 및 재해 복구 계획</span><span class="sxs-lookup"><span data-stu-id="5b6e7-134">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

