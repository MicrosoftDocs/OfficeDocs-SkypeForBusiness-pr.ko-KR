---
title: 프런트 엔드 풀 고가용성 및 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 두 개의 프런트 엔드 서버가 포함 된 풀에 대 한 풀, 쿼럼 손실 및 특수 단계 관리를 포함 하 여 비즈니스용 Skype 서버의 프런트 엔드 풀 관리에 대해 알아봅니다.
ms.openlocfilehash: 2982e2da0e7a103b5b598019baa7403a73da826d
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098436"
---
# <a name="front-end-pool-high-availability-and-management"></a><span data-ttu-id="bb856-103">프런트 엔드 풀 고가용성 및 관리</span><span class="sxs-lookup"><span data-stu-id="bb856-103">Front End Pool high availability and management</span></span>
 
<span data-ttu-id="bb856-104">두 개의 프런트 엔드 서버가 포함 된 풀에 대 한 풀, 쿼럼 손실 및 특수 단계 관리를 포함 하 여 비즈니스용 Skype 서버의 프런트 엔드 풀 관리에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-104">Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.</span></span>
  
<span data-ttu-id="bb856-105">비즈니스용 Skype 서버에서 프런트 엔드 풀의 아키텍처는 분산 시스템 모델을 사용 하며 각 사용자의 데이터는 풀의 프런트 엔드 서버 3 대까지 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-105">In Skype for Business Server, the architecture of Front End pools uses a distributed systems model, with each user's data kept on as many as three Front End Servers in the pool.</span></span> <span data-ttu-id="bb856-106">모든 Enterprise Edition 프런트 엔드 풀에는 세 개 이상의 프런트 엔드 서버가 포함 되는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-106">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span>

> [!NOTE]
> <span data-ttu-id="bb856-107">비즈니스용 Skype 서버 2019에서는 프런트 엔드 서버가 두 대 인 Enterprise Edition 프런트 엔드 풀을 지원 하지 않으며,이 시나리오에서 토폴로지를 게시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-107">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>
  
## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="bb856-108">프런트 엔드 풀 관리 계획</span><span class="sxs-lookup"><span data-stu-id="bb856-108">Planning for the management of Front End pools</span></span>

 <span data-ttu-id="bb856-109">비즈니스용 Skype 서버는 Windows Fabric을 기반으로 하는 분산 시스템 모델을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-109">Skype for Business Server uses a distributed systems model based on Windows Fabric.</span></span> <span data-ttu-id="bb856-110">이 모델에서는 각 사용자 및 전화 회의에 대 한 중요 한 데이터가 프런트 엔드 풀의 세 프런트 엔드 서버에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-110">In this model, important data for each user and conference is stored on three Front End Servers in a Front End pool.</span></span> <span data-ttu-id="bb856-111">특정 데이터 집합을 저장 하는이 세 서버는 calledreplicas입니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-111">These three servers storing a certain set of data are calledreplicas.</span></span>
  
<span data-ttu-id="bb856-112">프런트 엔드 풀에 대 한 분산 모델을 사용 하는 경우 풀이 작동 하려면 특정 그룹의 서버가 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-112">With the distributed model for Front End pools, a certain numbers of a pool's servers must be running for the pool to function.</span></span> <span data-ttu-id="bb856-113">풀에는 두 가지 손실 모드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-113">There are two loss modes for a pool.</span></span>
  
- <span data-ttu-id="bb856-114">특정 라우팅 그룹에 대 한 복제본 서버가 부족 하 여 라우팅 그룹 수준 쿼럼 손실이 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-114">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="bb856-115">라우팅 그룹은 풀에 속한 사용자 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-115">A routing group is a set of users homed in the pool.</span></span> <span data-ttu-id="bb856-116">각 라우팅 그룹에는 하나의 주 복제본과 두 개의 보조 복제본의 풀에 세 개의 복제본이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-116">Each routing group has three replicas in the pool: one primary replica and two secondary replicas.</span></span>
    
- <span data-ttu-id="bb856-117">풀 수준 쿼럼 손실 (풀에서 시드 서버가 충분히 실행 되지 않을 때 발생 하는 경우)</span><span class="sxs-lookup"><span data-stu-id="bb856-117">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span> 
    
### <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="bb856-118">라우팅 그룹 수준 쿼럼 손실</span><span class="sxs-lookup"><span data-stu-id="bb856-118">Routing Group Level quorum loss</span></span>

<span data-ttu-id="bb856-119">새 프런트 엔드 풀을 처음 시작 하는 경우에는 다음 표에 나와 있는 것과 같이 서버 중에서 1 ~ 85%가 작동 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-119">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="bb856-120">실행 중인 서버가 적으면 서비스가 시작 상태에 걸려 풀이 시작 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-120">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>
  
|<span data-ttu-id="bb856-121">풀에 있는 총 서버 수</span><span class="sxs-lookup"><span data-stu-id="bb856-121">Total number of servers in the pool</span></span>  <br/> |<span data-ttu-id="bb856-122">풀을 처음 시작할 때 실행 해야 하는 서버 수</span><span class="sxs-lookup"><span data-stu-id="bb856-122">Number of servers that must be running for the pool to be started the first time</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="bb856-123">2 </span><span class="sxs-lookup"><span data-stu-id="bb856-123">2</span></span>  <br/> |<span data-ttu-id="bb856-124">1 </span><span class="sxs-lookup"><span data-stu-id="bb856-124">1</span></span>  <br/> |
|<span data-ttu-id="bb856-125">3 </span><span class="sxs-lookup"><span data-stu-id="bb856-125">3</span></span>  <br/> |<span data-ttu-id="bb856-126">3 </span><span class="sxs-lookup"><span data-stu-id="bb856-126">3</span></span>  <br/> |
|<span data-ttu-id="bb856-127">4 </span><span class="sxs-lookup"><span data-stu-id="bb856-127">4</span></span>  <br/> |<span data-ttu-id="bb856-128">3 </span><span class="sxs-lookup"><span data-stu-id="bb856-128">3</span></span>  <br/> |
|<span data-ttu-id="bb856-129">5 </span><span class="sxs-lookup"><span data-stu-id="bb856-129">5</span></span>  <br/> |<span data-ttu-id="bb856-130">4 </span><span class="sxs-lookup"><span data-stu-id="bb856-130">4</span></span>  <br/> |
|<span data-ttu-id="bb856-131">6 </span><span class="sxs-lookup"><span data-stu-id="bb856-131">6</span></span>  <br/> |<span data-ttu-id="bb856-132">5 </span><span class="sxs-lookup"><span data-stu-id="bb856-132">5</span></span>  <br/> |
|<span data-ttu-id="bb856-133">7 </span><span class="sxs-lookup"><span data-stu-id="bb856-133">7</span></span>  <br/> |<span data-ttu-id="bb856-134">5 </span><span class="sxs-lookup"><span data-stu-id="bb856-134">5</span></span>  <br/> |
|<span data-ttu-id="bb856-135">8 </span><span class="sxs-lookup"><span data-stu-id="bb856-135">8</span></span>  <br/> |<span data-ttu-id="bb856-136">6 </span><span class="sxs-lookup"><span data-stu-id="bb856-136">6</span></span>  <br/> |
|<span data-ttu-id="bb856-137">9 </span><span class="sxs-lookup"><span data-stu-id="bb856-137">9</span></span>  <br/> |<span data-ttu-id="bb856-138">7 </span><span class="sxs-lookup"><span data-stu-id="bb856-138">7</span></span>  <br/> |
|<span data-ttu-id="bb856-139">10 </span><span class="sxs-lookup"><span data-stu-id="bb856-139">10</span></span>  <br/> |<span data-ttu-id="bb856-140">8 </span><span class="sxs-lookup"><span data-stu-id="bb856-140">8</span></span>  <br/> |
|<span data-ttu-id="bb856-141">11 </span><span class="sxs-lookup"><span data-stu-id="bb856-141">11</span></span>  <br/> |<span data-ttu-id="bb856-142">9 </span><span class="sxs-lookup"><span data-stu-id="bb856-142">9</span></span>  <br/> |
|<span data-ttu-id="bb856-143">12 </span><span class="sxs-lookup"><span data-stu-id="bb856-143">12</span></span>  <br/> |<span data-ttu-id="bb856-144">10 </span><span class="sxs-lookup"><span data-stu-id="bb856-144">10</span></span>  <br/> |
|<span data-ttu-id="bb856-145">16 **비즈니스용 Skype 서버 2019**</span><span class="sxs-lookup"><span data-stu-id="bb856-145">16 **For Skype for Business Server 2019**</span></span> <br/> |<span data-ttu-id="bb856-146">12 </span><span class="sxs-lookup"><span data-stu-id="bb856-146">12</span></span>  <br/> |


   
<span data-ttu-id="bb856-147">그 다음에 풀을 시작할 때마다 서버의 85% (위 표에 표시 된 대로)가 시작 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-147">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="bb856-148">이 서버 수를 시작할 수 없지만 풀 수준 쿼럼 손실에 해당 하지 않도록 충분 한 서버를 시작할 수 있으면 cmdlet을 사용 `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` 하 여 풀에서이 라우팅 그룹 수준 쿼럼 손실을 복구 하 고 작업을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-148">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="bb856-149">이 cmdlet을 사용 하는 방법에 대 한 자세한 내용은 [Reset-reset-cspoolregistrarstate](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="bb856-149">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bb856-150">서버 수가 짝수 인 풀에서 비즈니스용 Skype 서버는 기본 SQL 데이터베이스를 미러링 모니터로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-150">In pools with an even number of servers, Skype for Business Server uses the Primary SQL database as Witness.</span></span> <span data-ttu-id="bb856-151">이와 같은 풀에서는 기본 데이터베이스를 종료 하 고 미러 복사본으로 전환한 다음, 앞의 표에 따라 충분히 실행 되지 않도록 충분 한 프런트 엔드 서버를 종료 하는 경우 전체 풀이 다운 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-151">In a pool like this, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="bb856-152">자세한 내용은 [데이터베이스 미러링 모니터 서버](https://go.microsoft.com/fwlink/?LinkId=393672)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb856-152">For more information, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/?LinkId=393672).</span></span> 
  
#### <a name="pool-level-quorum-loss"></a><span data-ttu-id="bb856-153">풀 수준 쿼럼 손실</span><span class="sxs-lookup"><span data-stu-id="bb856-153">Pool-level quorum loss</span></span>

<span data-ttu-id="bb856-154">프런트 엔드 풀은 모두 작동 하기 위해 풀 수준의 쿼럼 손실 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-154">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="bb856-155">실행 중인 서버의 수가 다음 표에 나와 있는 것 처럼 기능 수준 아래로 떨어지면 풀의 나머지 서버가 모든 비즈니스용 Skype 서버 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-155">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Skype for Business Server services.</span></span> <span data-ttu-id="bb856-156">다음 표의 숫자는 풀의 백 엔드 서버가 실행 되 고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-156">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>
  
|<span data-ttu-id="bb856-157">풀에 있는 총 프런트 엔드 서버 수</span><span class="sxs-lookup"><span data-stu-id="bb856-157">Total number of Front End Servers in the pool</span></span>  <br/> |<span data-ttu-id="bb856-158">풀 작동을 위해 실행되어야 하는 서버 수</span><span class="sxs-lookup"><span data-stu-id="bb856-158">Number of servers that must be running for pool to be functional</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="bb856-159">2 </span><span class="sxs-lookup"><span data-stu-id="bb856-159">2</span></span>  <br/> |<span data-ttu-id="bb856-160">1 </span><span class="sxs-lookup"><span data-stu-id="bb856-160">1</span></span>  <br/> |
|<span data-ttu-id="bb856-161">3-4</span><span class="sxs-lookup"><span data-stu-id="bb856-161">3-4</span></span>  <br/> |<span data-ttu-id="bb856-162">모두 2</span><span class="sxs-lookup"><span data-stu-id="bb856-162">Any 2</span></span>  <br/> |
|<span data-ttu-id="bb856-163">5-6</span><span class="sxs-lookup"><span data-stu-id="bb856-163">5-6</span></span>  <br/> |<span data-ttu-id="bb856-164">모두 3</span><span class="sxs-lookup"><span data-stu-id="bb856-164">Any 3</span></span>  <br/> |
|<span data-ttu-id="bb856-165">7 </span><span class="sxs-lookup"><span data-stu-id="bb856-165">7</span></span>  <br/> |<span data-ttu-id="bb856-166">모든 4</span><span class="sxs-lookup"><span data-stu-id="bb856-166">Any 4</span></span>  <br/> |
|<span data-ttu-id="bb856-167">8-9</span><span class="sxs-lookup"><span data-stu-id="bb856-167">8-9</span></span>  <br/> |<span data-ttu-id="bb856-168">처음 7 개 서버 중 하나라도</span><span class="sxs-lookup"><span data-stu-id="bb856-168">Any 4 of the first 7 servers</span></span>  <br/> |
|<span data-ttu-id="bb856-169">10-12</span><span class="sxs-lookup"><span data-stu-id="bb856-169">10-12</span></span>  <br/> |<span data-ttu-id="bb856-170">처음 9 대의 서버 5 개</span><span class="sxs-lookup"><span data-stu-id="bb856-170">Any 5 of the first 9 servers</span></span>  <br/> |
|<span data-ttu-id="bb856-171">**비즈니스용 Skype 서버 2019** 12-16</span><span class="sxs-lookup"><span data-stu-id="bb856-171">12-16  **For Skype for Business Server 2019**</span></span>  <br/> |<span data-ttu-id="bb856-172">처음 12 개 서버 중 7 개</span><span class="sxs-lookup"><span data-stu-id="bb856-172">Any 7 of the first 12 servers</span></span>  <br/> |
   
<span data-ttu-id="bb856-173">위의 표에서 첫 번째 서버는 풀이 처음으로 시작 된 경우 시간순으로 나열 되는 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-173">In the preceding table, the "first servers" are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="bb856-174">이러한 서버를 확인 하기 위해 옵션과 함께 cmdlet을 사용할 수 있습니다 `Get-CsComputer` `-PoolFqdn` .</span><span class="sxs-lookup"><span data-stu-id="bb856-174">To determine these servers, you can use the  `Get-CsComputer` cmdlet with the `-PoolFqdn` option.</span></span> <span data-ttu-id="bb856-175">이 cmdlet은 토폴로지에 표시 되는 순서 대로 서버를 표시 하며, 목록 맨 위에 있는 서버가 첫 번째 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-175">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bb856-176">[비즈니스용 Skype 서버 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019) 에서 최대 프런트 엔드 서버 수가 16 개로 늘어났습니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-176">The maximum number of front end servers has been increased to 16 in [Skype for Business Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)</span></span>
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="bb856-177">풀이 작동 하도록 확인 하기 위한 추가 단계</span><span class="sxs-lookup"><span data-stu-id="bb856-177">Additional steps to ensure pools are functional</span></span>

<span data-ttu-id="bb856-178">프런트 엔드 풀이 계속 작동 되도록 하려면 몇 가지 다른 요인을 살펴봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-178">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>
  
- <span data-ttu-id="bb856-179">사용자를 처음으로 풀로 이동할 때는 프런트 엔드 서버 중 세 개 이상이 실행 되 고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-179">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>
    
- <span data-ttu-id="bb856-180">이 풀과 재해 복구를 위해 다른 풀 간의 연결 관계를 설정 하는 경우 해당 관계를 설정한 후에는이 풀에 백업 풀과 데이터를 올바르게 동기화 하기 위해 일정 시간 동안 동시에 실행 되는 세 개의 프런트 엔드 서버가 있는지를 파악 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-180">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="bb856-181">풀 페어링 및 재해 복구 기능에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 고가용성 및 재해 복구 계획](high-availability-and-disaster-recovery.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb856-181">For more information on pool pairing and disaster recovery features, see [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md).</span></span> 
    
## <a name="front-end-pool-with-two-front-end-servers"></a><span data-ttu-id="bb856-182">두 개의 프런트 엔드 서버가 있는 프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="bb856-182">Front End pool with two Front End servers</span></span>

<span data-ttu-id="bb856-183">두 개의 프런트 엔드 서버만 포함 된 프런트 엔드 풀을 배포 하는 것은 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-183">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="bb856-184">이 소규모 풀은 대규모 그룹과 같은 강력한 고가용성 솔루션을 제공 하지 않으며 관리 하는 경우 추가 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-184">This small pool will not provide a robust high-availability solution like a larger pool would, and needs extra care in managing.</span></span> <span data-ttu-id="bb856-185">또한 두 서버 풀의 백 엔드 서버가 다운 되 면 전체 풀도 곧 다운 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-185">Additionally, if the Back End Server of a two-server pool went down, the whole pool itself would likely soon go down as well.</span></span> <span data-ttu-id="bb856-186">비즈니스용 Skype 서버를 실행 하는 서버를 한 두 대만 배포 하려면 Standard Edition 서버로 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-186">If you want to deploy just one or two servers running Skype for Business Server, we recommend you deploy them as Standard Edition servers.</span></span>
  
<span data-ttu-id="bb856-187">두 개의 프런트 엔드 서버를 사용 하 여 풀을 배포 해야 하는 경우 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-187">If you do ever need to deploy a pool with two Front End Servers, follow these guidelines:</span></span>
  
- <span data-ttu-id="bb856-188">두 프런트 엔드 서버 중 하나가 다운 되 면 가능 하면 즉시 실패 한 서버를 백업 해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="bb856-188">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="bb856-189">마찬가지로, 두 서버 중 하나를 업그레이드 해야 하는 경우 업그레이드가 완료 되는 즉시 다시 온라인 상태로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-189">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>
    
- <span data-ttu-id="bb856-190">어떤 이유로 두 서버를 동시에 가져오는 데 필요한 경우 풀에 대 한 가동 중지 시간이 완료 되 면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-190">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
  - <span data-ttu-id="bb856-191">가장 좋은 방법은 두 프런트 엔드 서버를 동시에 다시 시작 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-191">The best practice is to restart both Front End Servers at the same time.</span></span> 
    
  - <span data-ttu-id="bb856-192">두 서버를 동시에 다시 시작할 수 없는 경우에는 다운 된 순서와 순서가 거꾸로 복원 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-192">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
  - <span data-ttu-id="bb856-193">해당 순서 대로 백업할 수 없는 경우 풀을 백업 하기 전에 다음 cmdlet을 사용 합니다.`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span><span class="sxs-lookup"><span data-stu-id="bb856-193">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span></span>
    
## <a name="front-end-pool-configuration-failures-and-changes"></a><span data-ttu-id="bb856-194">프런트 엔드 풀 구성 오류 및 변경 사항</span><span class="sxs-lookup"><span data-stu-id="bb856-194">Front End pool configuration failures and changes</span></span>

<span data-ttu-id="bb856-195">프런트 엔드 서버에 오류가 발생 하 여 며칠 이상 교체 될 가능성이 없는 경우 토폴로지에서 해당 서버를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-195">If a Front End server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="bb856-196">새 프런트 엔드 서버를 다시 사용할 수 있게 되 면 토폴로지에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-196">Add the new Front End server to the topology when it is available again.</span></span>
  
<span data-ttu-id="bb856-197">서버를 추가 하거나 제거 하는 등 프런트 엔드 풀의 구성을 변경할 때마다 다음 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-197">Whenever you make a configuration change to a Front End pool, such as adding or removing servers, you must follow these guidelines:</span></span>
  
- <span data-ttu-id="bb856-198">새 토폴로지가 게시 된 후에 풀에서 각 프런트 엔드 서버를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-198">After the new topology has been published, you must restart each Front End server in the pool.</span></span> <span data-ttu-id="bb856-199">한 번에 하나씩 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb856-199">Restart them one at a time.</span></span>
    
- <span data-ttu-id="bb856-200">구성 변경 중에 전체 풀이 다운 된 경우 새 토폴로지를 게시 한 후 다음 cmdlet을 실행 합니다.`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span><span class="sxs-lookup"><span data-stu-id="bb856-200">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span></span>
    

