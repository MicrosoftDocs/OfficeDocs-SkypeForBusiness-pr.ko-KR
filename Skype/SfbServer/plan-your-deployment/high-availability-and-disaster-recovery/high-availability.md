---
title: 프런트 엔드 풀 고가용성 및 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 2 개의 프런트 엔드 서버만 사용 하는 풀에 대 한 풀 관리, 쿼럼 손실, 특별 단계를 포함 하 여 비즈니스용 Skype 서버의 프론트 엔드 풀 관리에 대해 알아봅니다.
ms.openlocfilehash: 719a6099ac4bd54d82a833548b2438d0e9d8cc2d
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "36197849"
---
# <a name="front-end-pool-high-availability-and-management"></a><span data-ttu-id="aa3f3-103">프런트 엔드 풀 고가용성 및 관리</span><span class="sxs-lookup"><span data-stu-id="aa3f3-103">Front End Pool high availability and management</span></span>
 
<span data-ttu-id="aa3f3-104">2 개의 프런트 엔드 서버만 사용 하는 풀에 대 한 풀 관리, 쿼럼 손실, 특별 단계를 포함 하 여 비즈니스용 Skype 서버의 프론트 엔드 풀 관리에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-104">Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.</span></span>
  
<span data-ttu-id="aa3f3-105">비즈니스용 Skype 서버에서 프런트 엔드 풀의 아키텍처는 분산 시스템 모델을 사용 하 고 각 사용자의 데이터는 풀의 프런트 엔드 서버 3 대까지 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-105">In Skype for Business Server, the architecture of Front End pools uses a distributed systems model, with each user's data kept on as many as three Front End servers in the pool.</span></span> <span data-ttu-id="aa3f3-106">모든 Enterprise Edition 프런트 엔드 풀에는 프런트 엔드 서버가 세 대 이상 포함 되는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-106">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> 
  
## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="aa3f3-107">프런트 엔드 풀 관리 계획</span><span class="sxs-lookup"><span data-stu-id="aa3f3-107">Planning for the management of Front End pools</span></span>

 <span data-ttu-id="aa3f3-108">비즈니스용 Skype Server는 Windows Fabric 기반의 분산 시스템 모델을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-108">Skype for Business Server uses a distributed systems model based on Windows Fabric.</span></span> <span data-ttu-id="aa3f3-109">이 모델에서 각 사용자 및 회의에 대 한 중요 한 데이터는 프런트 엔드 풀에 있는 세 개의 프런트 엔드 서버에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-109">In this model, important data for each user and conference is stored on three Front End Servers in a Front End pool.</span></span> <span data-ttu-id="aa3f3-110">특정 데이터 집합을 저장 하는 세 개의 서버는 calledreplicas.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-110">These three servers storing a certain set of data are calledreplicas.</span></span>
  
<span data-ttu-id="aa3f3-111">프런트 엔드 풀에 대 한 분산 모델을 사용 하는 경우 풀이 작동 하려면 풀 서버의 특정 번호가 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-111">With the distributed model for Front End pools, a certain numbers of a pool's servers must be running for the pool to function.</span></span> <span data-ttu-id="aa3f3-112">풀에는 두 가지 손실 모드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-112">There are two loss modes for a pool.</span></span>
  
- <span data-ttu-id="aa3f3-113">라우팅 그룹 수준 쿼럼 손실, 특정 라우팅 그룹에 대 한 복제본 서버가 부족 하 여 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-113">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="aa3f3-114">라우팅 그룹은 풀에 속한 사용자 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-114">A routing group is a set of users homed in the pool.</span></span> <span data-ttu-id="aa3f3-115">각 라우팅 그룹에는 하나의 주 복제본과 두 개의 보조 복제본 이라는 세 가지 풀의 복제본이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-115">Each routing group has three replicas in the pool: one primary replica and two secondary replicas.</span></span>
    
- <span data-ttu-id="aa3f3-116">풀에 시드 서버가 충분히 실행 되 고 있지 않은 경우 발생 하는 풀 수준 쿼럼 손실.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-116">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span> 
    
### <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="aa3f3-117">라우팅 그룹 수준 쿼럼 손실</span><span class="sxs-lookup"><span data-stu-id="aa3f3-117">Routing Group Level quorum loss</span></span>

<span data-ttu-id="aa3f3-118">새 프런트 엔드 풀을 처음 시작 하는 경우에는 다음 표에 표시 된 대로 서버의 85%가 작동 하 고 실행 되 고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-118">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="aa3f3-119">실행 중인 서버 수가 적은 경우 서비스는 시작 상태에 멈춰 있을 수 있으며 풀이 시작 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-119">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>
  
|<span data-ttu-id="aa3f3-120">풀의 총 서버 수</span><span class="sxs-lookup"><span data-stu-id="aa3f3-120">Total number of servers in the pool</span></span>  <br/> |<span data-ttu-id="aa3f3-121">풀이 처음 시작 될 때 실행 되어야 하는 서버 수</span><span class="sxs-lookup"><span data-stu-id="aa3f3-121">Number of servers that must be running for the pool to be started the first time</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="aa3f3-122">2</span><span class="sxs-lookup"><span data-stu-id="aa3f3-122">2</span></span>  <br/> |<span data-ttu-id="aa3f3-123">raid-1</span><span class="sxs-lookup"><span data-stu-id="aa3f3-123">1</span></span>  <br/> |
|<span data-ttu-id="aa3f3-124">3-4</span><span class="sxs-lookup"><span data-stu-id="aa3f3-124">3</span></span>  <br/> |<span data-ttu-id="aa3f3-125">3-4</span><span class="sxs-lookup"><span data-stu-id="aa3f3-125">3</span></span>  <br/> |
|<span data-ttu-id="aa3f3-126">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="aa3f3-126">4</span></span>  <br/> |<span data-ttu-id="aa3f3-127">3-4</span><span class="sxs-lookup"><span data-stu-id="aa3f3-127">3</span></span>  <br/> |
|<span data-ttu-id="aa3f3-128">5mb</span><span class="sxs-lookup"><span data-stu-id="aa3f3-128">5</span></span>  <br/> |<span data-ttu-id="aa3f3-129">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="aa3f3-129">4</span></span>  <br/> |
|<span data-ttu-id="aa3f3-130">26</span><span class="sxs-lookup"><span data-stu-id="aa3f3-130">6</span></span>  <br/> |<span data-ttu-id="aa3f3-131">5mb</span><span class="sxs-lookup"><span data-stu-id="aa3f3-131">5</span></span>  <br/> |
|<span data-ttu-id="aa3f3-132">7</span><span class="sxs-lookup"><span data-stu-id="aa3f3-132">7</span></span>  <br/> |<span data-ttu-id="aa3f3-133">5mb</span><span class="sxs-lookup"><span data-stu-id="aa3f3-133">5</span></span>  <br/> |
|<span data-ttu-id="aa3f3-134">20cm(8</span><span class="sxs-lookup"><span data-stu-id="aa3f3-134">8</span></span>  <br/> |<span data-ttu-id="aa3f3-135">26</span><span class="sxs-lookup"><span data-stu-id="aa3f3-135">6</span></span>  <br/> |
|<span data-ttu-id="aa3f3-136">되었는지</span><span class="sxs-lookup"><span data-stu-id="aa3f3-136">9</span></span>  <br/> |<span data-ttu-id="aa3f3-137">7</span><span class="sxs-lookup"><span data-stu-id="aa3f3-137">7</span></span>  <br/> |
|<span data-ttu-id="aa3f3-138">1천만</span><span class="sxs-lookup"><span data-stu-id="aa3f3-138">10</span></span>  <br/> |<span data-ttu-id="aa3f3-139">20cm(8</span><span class="sxs-lookup"><span data-stu-id="aa3f3-139">8</span></span>  <br/> |
|<span data-ttu-id="aa3f3-140">mb</span><span class="sxs-lookup"><span data-stu-id="aa3f3-140">11</span></span>  <br/> |<span data-ttu-id="aa3f3-141">되었는지</span><span class="sxs-lookup"><span data-stu-id="aa3f3-141">9</span></span>  <br/> |
|<span data-ttu-id="aa3f3-142">까지</span><span class="sxs-lookup"><span data-stu-id="aa3f3-142">12</span></span>  <br/> |<span data-ttu-id="aa3f3-143">1천만</span><span class="sxs-lookup"><span data-stu-id="aa3f3-143">10</span></span>  <br/> |
   
<span data-ttu-id="aa3f3-144">이후 풀이 시작 될 때마다 서버의 85%가 시작 되어야 합니다 (앞의 표에 표시 된 대로).</span><span class="sxs-lookup"><span data-stu-id="aa3f3-144">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="aa3f3-145">이 서버 수를 시작할 수 없는 경우 (풀 수준의 쿼럼 손실에 해당 되지 않도록 충분 한 서버를 시작할 수 있음) `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet을 사용 하 여이 라우팅 그룹 수준 쿼럼 손실에서 복구 하 고 진행률을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-145">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="aa3f3-146">이 cmdlet을 사용 하는 방법에 대 한 자세한 <link Reset-CsPoolRegistrarState>내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-146">For more information about how to use this cmdlet, see <link Reset-CsPoolRegistrarState>.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aa3f3-147">서버 수가 짝수 인 풀에서 비즈니스용 Skype Server는 기본 SQL 데이터베이스를 미러링 모니터로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-147">In pools with an even number of servers, Skype for Business Server uses the Primary SQL database as Witness.</span></span> <span data-ttu-id="aa3f3-148">이와 같은 풀에서 기본 데이터베이스를 종료 하 고 미러 복사본으로 전환 하 여 앞의 표에 따라 실행 되지 않도록 충분 한 프런트 엔드 서버를 종료 하면 전체 풀이 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-148">In a pool like this, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="aa3f3-149">자세한 내용은 [데이터베이스 미러링 감시](https://go.microsoft.com/fwlink/?LinkId=393672)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-149">For more information, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/?LinkId=393672).</span></span> 
  
#### <a name="pool-level-quorum-loss"></a><span data-ttu-id="aa3f3-150">풀 수준 쿼럼 손실</span><span class="sxs-lookup"><span data-stu-id="aa3f3-150">Pool-level quorum loss</span></span>

<span data-ttu-id="aa3f3-151">프런트 엔드 풀은 전혀 작동 하기 위해 풀 수준의 쿼럼 손실 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-151">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="aa3f3-152">실행 중인 서버 수가 다음 표에 나와 있는 것 처럼 기능 수준 아래로 떨어지면 풀의 나머지 서버가 모든 비즈니스용 Skype 서버 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-152">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Skype for Business Server services.</span></span> <span data-ttu-id="aa3f3-153">다음 표의 숫자는 풀의 백 엔드 서버가 실행 되 고 있는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-153">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>
  
|<span data-ttu-id="aa3f3-154">풀의 총 프런트 엔드 서버 수</span><span class="sxs-lookup"><span data-stu-id="aa3f3-154">Total number of Front End Servers in the pool</span></span>  <br/> |<span data-ttu-id="aa3f3-155">풀을 작동 하기 위해 실행 해야 하는 서버 수</span><span class="sxs-lookup"><span data-stu-id="aa3f3-155">Number of servers that must be running for pool to be functional</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="aa3f3-156">2</span><span class="sxs-lookup"><span data-stu-id="aa3f3-156">2</span></span>  <br/> |<span data-ttu-id="aa3f3-157">raid-1</span><span class="sxs-lookup"><span data-stu-id="aa3f3-157">1</span></span>  <br/> |
|<span data-ttu-id="aa3f3-158">3-4</span><span class="sxs-lookup"><span data-stu-id="aa3f3-158">3-4</span></span>  <br/> |<span data-ttu-id="aa3f3-159">모든 2</span><span class="sxs-lookup"><span data-stu-id="aa3f3-159">Any 2</span></span>  <br/> |
|<span data-ttu-id="aa3f3-160">5-6</span><span class="sxs-lookup"><span data-stu-id="aa3f3-160">5-6</span></span>  <br/> |<span data-ttu-id="aa3f3-161">모든 3</span><span class="sxs-lookup"><span data-stu-id="aa3f3-161">Any 3</span></span>  <br/> |
|<span data-ttu-id="aa3f3-162">7</span><span class="sxs-lookup"><span data-stu-id="aa3f3-162">7</span></span>  <br/> |<span data-ttu-id="aa3f3-163">모든 4</span><span class="sxs-lookup"><span data-stu-id="aa3f3-163">Any 4</span></span>  <br/> |
|<span data-ttu-id="aa3f3-164">8-9</span><span class="sxs-lookup"><span data-stu-id="aa3f3-164">8-9</span></span>  <br/> |<span data-ttu-id="aa3f3-165">처음 7 대의 서버 중 4 대</span><span class="sxs-lookup"><span data-stu-id="aa3f3-165">Any 4 of the first 7 servers</span></span>  <br/> |
|<span data-ttu-id="aa3f3-166">10-12</span><span class="sxs-lookup"><span data-stu-id="aa3f3-166">10-12</span></span>  <br/> |<span data-ttu-id="aa3f3-167">처음 9 대의 서버 5 대</span><span class="sxs-lookup"><span data-stu-id="aa3f3-167">Any 5 of the first 9 servers</span></span>  <br/> |
   
<span data-ttu-id="aa3f3-168">앞의 표에서 "첫 번째 서버"는 풀이 처음으로 시작 된 시점에 시간순으로 나열 된 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-168">In the preceding table, the "first servers" are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="aa3f3-169">이러한 서버를 확인 하려면 `Get-CsComputer` `-PoolFqdn` 옵션에 cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-169">To determine these servers, you can use the  `Get-CsComputer` cmdlet with the `-PoolFqdn` option.</span></span> <span data-ttu-id="aa3f3-170">이 cmdlet은 토폴로지에 표시 되는 순서 대로 서버를 표시 하 고 목록의 맨 위에는 첫 번째 서버가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-170">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="aa3f3-171">풀이 작동 하도록 하는 추가 단계</span><span class="sxs-lookup"><span data-stu-id="aa3f3-171">Additional steps to ensure pools are functional</span></span>

<span data-ttu-id="aa3f3-172">프런트 엔드 풀이 작동 하는 것을 방지 하기 위해 몇 가지 다른 요인에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-172">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>
  
- <span data-ttu-id="aa3f3-173">사용자를 처음으로 풀로 이동 하는 경우 프런트 엔드 서버가 세 개 이상 실행 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-173">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>
    
- <span data-ttu-id="aa3f3-174">이 풀과 재해 복구용에 대 한 다른 풀 간의 페어링 관계를 설정 하는 경우 해당 관계를 설정한 후에는이 풀에 동시에 실행 되는 세 개의 프런트 엔드 서버가 있어야 올바르게 동기화 할 수 있습니다. 백업 풀을 사용 하 여 데이터</span><span class="sxs-lookup"><span data-stu-id="aa3f3-174">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="aa3f3-175">풀 페어링 및 재해 복구 기능에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 고가용성 및 재해 복구 계획](high-availability-and-disaster-recovery.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-175">For more information on pool pairing and disaster recovery features, see [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md).</span></span> 
    
## <a name="front-end-pool-with-two-front-end-servers"></a><span data-ttu-id="aa3f3-176">두 개의 프런트 엔드 서버가 있는 프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="aa3f3-176">Front End pool with two Front End servers</span></span>

<span data-ttu-id="aa3f3-177">프런트 엔드 서버를 두 대만 포함 하는 프런트 엔드 풀은 배포 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-177">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="aa3f3-178">이 작은 풀은 대규모 그룹과 같은 강력한 고가용성 솔루션을 제공 하지 않으며, 관리에 추가 주의가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-178">This small pool will not provide a robust high-availability solution like a larger pool would, and needs extra care in managing.</span></span> <span data-ttu-id="aa3f3-179">또한, 두 서버 풀의 백 엔드 서버가 종료 된 경우에도 전체 풀 자체는 곧 다운 될 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-179">Additionally, if the Back End Server of a two-server pool went down, the whole pool itself would likely soon go down as well.</span></span> <span data-ttu-id="aa3f3-180">비즈니스용 Skype 서버를 실행 하는 서버를 하나 또는 두 개 배포 하려는 경우 표준 버전 서버로 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-180">If you want to deploy just one or two servers running Skype for Business Server, we recommend you deploy them as Standard Edition servers.</span></span>
  
<span data-ttu-id="aa3f3-181">프런트 엔드 서버 두 대를 사용 하 여 풀을 배포 해야 하는 경우 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-181">If you do ever need to deploy a pool with two Front End Servers, follow these guidelines:</span></span>
  
- <span data-ttu-id="aa3f3-182">두 프런트 엔드 서버 중 하나가 중단 되 면 가능한 한 빨리 실패 한 서버를 다시 온라인 상태로 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-182">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="aa3f3-183">마찬가지로, 두 서버 중 하나를 업그레이드 해야 하는 경우 업그레이드가 완료 되는 즉시 다시 온라인 상태로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-183">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>
    
- <span data-ttu-id="aa3f3-184">어떤 이유로 두 서버를 동시에 종료 해야 하는 경우 풀의 가동 중지 시간이 완료 되 면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
  - <span data-ttu-id="aa3f3-185">가장 좋은 방법은 프런트 엔드 서버를 동시에 다시 시작 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-185">The best practice is to restart both Front End Servers at the same time.</span></span> 
    
  - <span data-ttu-id="aa3f3-186">두 서버를 동시에 다시 시작할 수 없는 경우에는 그 순서의 역순으로 백업 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
  - <span data-ttu-id="aa3f3-187">이 순서 대로 백업할 수 없는 경우 풀을 다시 가져오기 전에 다음 cmdlet을 사용 합니다.`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span><span class="sxs-lookup"><span data-stu-id="aa3f3-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span></span>
    
## <a name="front-end-pool-configuration-failures-and-changes"></a><span data-ttu-id="aa3f3-188">프런트 엔드 풀 구성 오류 및 변경</span><span class="sxs-lookup"><span data-stu-id="aa3f3-188">Front End pool configuration failures and changes</span></span>

<span data-ttu-id="aa3f3-189">프런트 엔드 서버에 오류가 발생 하 여 며칠 이상 교체할 수 없는 경우 토폴로지에서 서버를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-189">If a Front End server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="aa3f3-190">다시 사용할 수 있게 되 면 토폴로지에 새 프런트 엔드 서버를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-190">Add the new Front End server to the topology when it is available again.</span></span>
  
<span data-ttu-id="aa3f3-191">서버를 추가 하거나 제거 하는 등 프런트 엔드 풀의 구성을 변경할 때마다 다음 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-191">Whenever you make a configuration change to a Front End pool, such as adding or removing servers, you must follow these guidelines:</span></span>
  
- <span data-ttu-id="aa3f3-192">새 토폴로지가 게시 된 후에 풀에서 각 프런트 엔드 서버를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-192">After the new topology has been published, you must restart each Front End server in the pool.</span></span> <span data-ttu-id="aa3f3-193">한 번에 하나씩 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa3f3-193">Restart them one at a time.</span></span>
    
- <span data-ttu-id="aa3f3-194">구성 변경 중 전체 풀이 중단 되 면 새 토폴로지가 게시 된 후 다음 cmdlet을 실행 합니다.`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span><span class="sxs-lookup"><span data-stu-id="aa3f3-194">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span></span>
    

