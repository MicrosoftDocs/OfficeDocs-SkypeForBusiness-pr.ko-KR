---
title: 재해 복구, 고가용성 및 백업 서비스 관리
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 재해 복구 작업에 대한 절차와 페어링된 프런트 엔드 풀의 데이터를 동기화하는 백업 서비스 유지 관리 절차에 대해 자세히 알아보습니다.
ms.openlocfilehash: e486a71203b64b4fc351888869ac64a24689ba7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817158"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="a675f-103">비즈니스용 Skype 서버 재해 복구, 고가용성 및 백업 서비스 관리</span><span class="sxs-lookup"><span data-stu-id="a675f-103">Managing Skype for Business Server disaster recovery, high availability, and Backup Service</span></span>

<span data-ttu-id="a675f-104">이 섹션에는 재해 복구 작업에 대한 절차와 페어링된 프런트 엔드 풀의 데이터를 동기화하는 백업 서비스 유지 관리 절차가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a675f-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service, which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="a675f-p101">장애 조치(failover)와 장애 복구(failback)라는 재해 복구 절차는 둘 다 수동 절차입니다. 따라서 재해가 발생한 경우 관리자는 장애 조치(failover) 절차를 직접 호출해야 합니다. 풀이 복구된 이후의 장애 복구(failback)에도 동일한 절차가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a675f-p101">Disaster recovery procedures, both failover and failback, are manual. If there is a disaster, the administrator must manually invoke the failover procedures. The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="a675f-108">이 섹션의 재해 복구 절차에서는 다음을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a675f-108">The disaster recovery procedures in this section assume the following:</span></span>

  - <span data-ttu-id="a675f-109">고가용성 및 재해 복구 계획에 설명된 바와 같이 서로 다른 사이트에 쌍으로 된 프런트 엔드 풀이 있는 [배포가 있습니다.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="a675f-109">You have a deployment with paired Front End pools, located in different sites, as described in [Plan for high availability and disaster recovery](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="a675f-110">백업 서비스가 이러한 연결된 풀에서 실행되어 이들 풀을 동기화 상태로 유지하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a675f-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="a675f-111">중앙 관리 저장소가 두 풀 중 하나에서 호스팅되는 경우 이 저장소는 활성 마스터를 호스팅하는 풀 중 하나와 대기 중인 다른 풀과 함께 페어링된 두 풀 모두에서 설치 및 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a675f-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a675f-p103">다음 절차에서 *PoolFQDN* 매개 변수는 영향을 받는 사용자가 리디렉션되는 풀이 아니라 재해에 영향을 받는 풀의 FQDN을 나타냅니다. 영향을 받는 일부 사용자의 경우 장애 조치(failover) 및 장애 복구(failback) cmdlet에서 동일한 풀(즉 장애 조치(failover) 전에 사용자가 있던 풀)을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a675f-p103">In the following procedures, the *PoolFQDN* parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from. For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><br><span data-ttu-id="a675f-p104">예를 들어, 풀 P1에 있는 모든 사용자가 백업 풀 P2로 장애 조치(failover)된다고 가정해 보겠습니다. 관리자가 현재 P2에서 서비스를 받는 모든 사용자를 P1에서 서비스를 받도록 옮기려는 경우 관리자는 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a675f-p104">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2. If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="a675f-p105">장애 복구(failback) cmdlet을 사용하여 원래 P1에 있던 모든 사용자를 P2에서 P1으로 장애 복구(failback)합니다. 이 경우 *PoolFQDN* 이 P1의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="a675f-p105">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet. In this case, the *PoolFQDN* is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="a675f-118">장애 조치(failover) cmdlet을 사용하여 원래 P2에 있던 모든 사용자를 P1으로 장애 조치(failover)합니다.</span><span class="sxs-lookup"><span data-stu-id="a675f-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="a675f-119">이 경우 PoolFQDN은 P2의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="a675f-119">In this case, the PoolFQDN is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="a675f-120">관리자가 나중에 이러한 P2 사용자를 다시 P2로 장애 복구(failback)하려는 경우 PoolFQDN이 P2의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="a675f-120">If the administrator later wants to fail back those P2 users back to P2, the PoolFQDN is P2’s FQDN.</span></span></P></LI></OL><br><span data-ttu-id="a675f-p107">풀 무결성을 유지하려면 위의 1단계를 2단계 전에 수행해야 합니다. 1단계 전에 2단계를 시도하면 2단계 cmdlet이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="a675f-p107">Note that step 1 above must be performed before step 2 to preserve pool integrity. If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>


## <a name="see-also"></a><span data-ttu-id="a675f-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a675f-123">See Also</span></span>

[<span data-ttu-id="a675f-124">고가용성 및 재해 복구 계획</span><span class="sxs-lookup"><span data-stu-id="a675f-124">Plan for high availability and disaster recovery</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
