---
title: 프런트 엔드 풀 고가용성 및 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 풀 관리, 쿼럼 손실 및 프런트 엔드 서버가 2대뿐인 풀에 대한 특수 단계를 포함하여 비즈니스용 Skype 서버의 프런트 엔드 풀 관리에 대해 자세히 알아보십시오.
ms.openlocfilehash: 47e4b2157961a2856256e3d96a0676dd86d3f996
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093076"
---
# <a name="front-end-pool-high-availability-and-management"></a><span data-ttu-id="0f3b8-103">프런트 엔드 풀 고가용성 및 관리</span><span class="sxs-lookup"><span data-stu-id="0f3b8-103">Front End Pool high availability and management</span></span>
 
<span data-ttu-id="0f3b8-104">풀 관리, 쿼럼 손실 및 프런트 엔드 서버가 2대뿐인 풀에 대한 특수 단계를 포함하여 비즈니스용 Skype 서버의 프런트 엔드 풀 관리에 대해 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-104">Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.</span></span>
  
<span data-ttu-id="0f3b8-105">비즈니스용 Skype 서버에서 프런트 엔드 풀의 아키텍처는 분산 시스템 모델을 사용하 고, 각 사용자의 데이터는 풀에 있는 3대의 프런트 엔드 서버에 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-105">In Skype for Business Server, the architecture of Front End pools uses a distributed systems model, with each user's data kept on as many as three Front End Servers in the pool.</span></span> <span data-ttu-id="0f3b8-106">모든 Enterprise Edition 프런트 엔드 풀에는 3대 이상의 프런트 엔드 서버가 포함되어 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-106">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span>

> [!NOTE]
> <span data-ttu-id="0f3b8-107">비즈니스용 Skype 서버 2019는 프런트 엔드 서버가 두 대인 Enterprise Edition 프런트 엔드 풀을 지원하지 않습니다. 이 시나리오에서는 토폴로지가 게시될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-107">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>
  
## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="0f3b8-108">프런트 엔드 풀 관리 계획</span><span class="sxs-lookup"><span data-stu-id="0f3b8-108">Planning for the management of Front End pools</span></span>

 <span data-ttu-id="0f3b8-109">비즈니스용 Skype 서버는 Windows Fabric을 기반으로 하는 분산 시스템 모델을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-109">Skype for Business Server uses a distributed systems model based on Windows Fabric.</span></span> <span data-ttu-id="0f3b8-110">이 모델에서는 각 사용자 및 회의에 대한 중요한 데이터가 프런트 엔드 풀의 세 프런트 엔드 서버에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-110">In this model, important data for each user and conference is stored on three Front End Servers in a Front End pool.</span></span> <span data-ttu-id="0f3b8-111">이러한 세 서버는 특정 데이터 집합을 저장하는 데 사용할 수 있는 서버를replicas라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-111">These three servers storing a certain set of data are calledreplicas.</span></span>
  
<span data-ttu-id="0f3b8-112">프런트 엔드 풀에 대해 분산 모델을 사용할 경우 풀이 작동하려면 특정 수의 풀 서버를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-112">With the distributed model for Front End pools, a certain numbers of a pool's servers must be running for the pool to function.</span></span> <span data-ttu-id="0f3b8-113">풀에는 두 가지 손실 모드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-113">There are two loss modes for a pool.</span></span>
  
- <span data-ttu-id="0f3b8-114">특정 라우팅 그룹에 대한 복제본 서버가 부족하여 그룹 수준 쿼럼 손실이 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-114">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="0f3b8-115">라우팅 그룹은 풀에 있는 사용자 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-115">A routing group is a set of users homed in the pool.</span></span> <span data-ttu-id="0f3b8-116">각 라우팅 그룹에는 주 복제본 1개와 보조 복제본 2개 등 3개의 복제본이 풀에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-116">Each routing group has three replicas in the pool: one primary replica and two secondary replicas.</span></span>
    
- <span data-ttu-id="0f3b8-117">풀 수준 쿼럼 손실( 풀에서 시드 서버가 충분하지 않은 경우 발생)</span><span class="sxs-lookup"><span data-stu-id="0f3b8-117">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span> 
    
### <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="0f3b8-118">라우팅 그룹 수준 쿼럼 손실</span><span class="sxs-lookup"><span data-stu-id="0f3b8-118">Routing Group Level quorum loss</span></span>

<span data-ttu-id="0f3b8-119">새 프런트 엔드 풀을 처음 시작할 때 다음 표와 같이 서버의 85%가 실행 중임이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-119">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="0f3b8-120">실행 중인 서버 수가 적은 경우 서비스가 시작 상태가 되지 않을 수 있으며 풀이 시작되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-120">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>
  
|<span data-ttu-id="0f3b8-121">풀의 총 서버 수</span><span class="sxs-lookup"><span data-stu-id="0f3b8-121">Total number of servers in the pool</span></span>  <br/> |<span data-ttu-id="0f3b8-122">풀을 처음 시작하려면 실행해야 하는 서버 수</span><span class="sxs-lookup"><span data-stu-id="0f3b8-122">Number of servers that must be running for the pool to be started the first time</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="0f3b8-123">2 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-123">2</span></span>  <br/> |<span data-ttu-id="0f3b8-124">1</span><span class="sxs-lookup"><span data-stu-id="0f3b8-124">1</span></span>  <br/> |
|<span data-ttu-id="0f3b8-125">3 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-125">3</span></span>  <br/> |<span data-ttu-id="0f3b8-126">3 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-126">3</span></span>  <br/> |
|<span data-ttu-id="0f3b8-127">4 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-127">4</span></span>  <br/> |<span data-ttu-id="0f3b8-128">3 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-128">3</span></span>  <br/> |
|<span data-ttu-id="0f3b8-129">5 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-129">5</span></span>  <br/> |<span data-ttu-id="0f3b8-130">4 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-130">4</span></span>  <br/> |
|<span data-ttu-id="0f3b8-131">6 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-131">6</span></span>  <br/> |<span data-ttu-id="0f3b8-132">5 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-132">5</span></span>  <br/> |
|<span data-ttu-id="0f3b8-133">7 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-133">7</span></span>  <br/> |<span data-ttu-id="0f3b8-134">5 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-134">5</span></span>  <br/> |
|<span data-ttu-id="0f3b8-135">8 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-135">8</span></span>  <br/> |<span data-ttu-id="0f3b8-136">6 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-136">6</span></span>  <br/> |
|<span data-ttu-id="0f3b8-137">9 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-137">9</span></span>  <br/> |<span data-ttu-id="0f3b8-138">7 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-138">7</span></span>  <br/> |
|<span data-ttu-id="0f3b8-139">10  </span><span class="sxs-lookup"><span data-stu-id="0f3b8-139">10</span></span>  <br/> |<span data-ttu-id="0f3b8-140">8 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-140">8</span></span>  <br/> |
|<span data-ttu-id="0f3b8-141">11 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-141">11</span></span>  <br/> |<span data-ttu-id="0f3b8-142">9 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-142">9</span></span>  <br/> |
|<span data-ttu-id="0f3b8-143">12 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-143">12</span></span>  <br/> |<span data-ttu-id="0f3b8-144">10  </span><span class="sxs-lookup"><span data-stu-id="0f3b8-144">10</span></span>  <br/> |
|<span data-ttu-id="0f3b8-145">16 **For Skype for Business Server 2019**</span><span class="sxs-lookup"><span data-stu-id="0f3b8-145">16 **For Skype for Business Server 2019**</span></span> <br/> |<span data-ttu-id="0f3b8-146">12 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-146">12</span></span>  <br/> |


   
<span data-ttu-id="0f3b8-147">이후 풀이 시작될 때마다 서버의 85%가 시작되어야 합니다(위의 표에 나와 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="0f3b8-147">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="0f3b8-148">이 서버 수를 시작할 수 없는 경우(하지만 풀 수준 쿼럼 손실이 되지 않을 수 있도록 충분한 서버를 시작할 수 있는 경우) cmdlet을 사용하여 이 라우팅 그룹 수준 쿼럼 손실에서 풀을 복구하고 진행할 수  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-148">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="0f3b8-149">이 cmdlet을 사용하는 방법에 대한 자세한 내용은 [Reset-CsPoolRegistrarState를 참조하십시오.](/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0f3b8-149">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0f3b8-150">서버 수가 온라인인 풀에서 비즈니스용 Skype 서버는 기본 SQL 미러링크로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-150">In pools with an even number of servers, Skype for Business Server uses the Primary SQL database as Witness.</span></span> <span data-ttu-id="0f3b8-151">이와 같은 풀에서 기본 데이터베이스를 종료하고 미러 복사본으로 전환하고 앞의 표에 따라 충분히 실행되지 않는 충분한 프런트 엔드 서버를 종료하면 전체 풀이 다운됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-151">In a pool like this, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="0f3b8-152">자세한 내용은 데이터베이스 [미러링 서버 를 참조하세요.](/sql/database-engine/database-mirroring/database-mirroring-witness)</span><span class="sxs-lookup"><span data-stu-id="0f3b8-152">For more information, see [Database Mirroring Witness](/sql/database-engine/database-mirroring/database-mirroring-witness).</span></span> 
  
#### <a name="pool-level-quorum-loss"></a><span data-ttu-id="0f3b8-153">풀 수준 쿼럼 손실</span><span class="sxs-lookup"><span data-stu-id="0f3b8-153">Pool-level quorum loss</span></span>

<span data-ttu-id="0f3b8-154">프런트 엔드 풀이 작동하기 위해 풀 수준 쿼럼 손실에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-154">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="0f3b8-155">실행 중인 서버 수가 다음 표에 나와 있는 기능 수준 미만으로 떨어지면 풀의 나머지 서버가 모든 비즈니스용 Skype 서버 서비스를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-155">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Skype for Business Server services.</span></span> <span data-ttu-id="0f3b8-156">다음 표의 숫자는 풀의 백 엔드 서버가 실행되고 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-156">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>
  
|<span data-ttu-id="0f3b8-157">풀에 있는 총 프런트 엔드 서버 수</span><span class="sxs-lookup"><span data-stu-id="0f3b8-157">Total number of Front End Servers in the pool</span></span>  <br/> |<span data-ttu-id="0f3b8-158">풀 작동을 위해 실행되어야 하는 서버 수</span><span class="sxs-lookup"><span data-stu-id="0f3b8-158">Number of servers that must be running for pool to be functional</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="0f3b8-159">2 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-159">2</span></span>  <br/> |<span data-ttu-id="0f3b8-160">1</span><span class="sxs-lookup"><span data-stu-id="0f3b8-160">1</span></span>  <br/> |
|<span data-ttu-id="0f3b8-161">3-4</span><span class="sxs-lookup"><span data-stu-id="0f3b8-161">3-4</span></span>  <br/> |<span data-ttu-id="0f3b8-162">모든 2</span><span class="sxs-lookup"><span data-stu-id="0f3b8-162">Any 2</span></span>  <br/> |
|<span data-ttu-id="0f3b8-163">5-6</span><span class="sxs-lookup"><span data-stu-id="0f3b8-163">5-6</span></span>  <br/> |<span data-ttu-id="0f3b8-164">모든 3</span><span class="sxs-lookup"><span data-stu-id="0f3b8-164">Any 3</span></span>  <br/> |
|<span data-ttu-id="0f3b8-165">7 </span><span class="sxs-lookup"><span data-stu-id="0f3b8-165">7</span></span>  <br/> |<span data-ttu-id="0f3b8-166">모든 4</span><span class="sxs-lookup"><span data-stu-id="0f3b8-166">Any 4</span></span>  <br/> |
|<span data-ttu-id="0f3b8-167">8-9</span><span class="sxs-lookup"><span data-stu-id="0f3b8-167">8-9</span></span>  <br/> |<span data-ttu-id="0f3b8-168">처음 7개 서버 중 4개</span><span class="sxs-lookup"><span data-stu-id="0f3b8-168">Any 4 of the first 7 servers</span></span>  <br/> |
|<span data-ttu-id="0f3b8-169">10-12</span><span class="sxs-lookup"><span data-stu-id="0f3b8-169">10-12</span></span>  <br/> |<span data-ttu-id="0f3b8-170">처음 9개 서버 중 5개</span><span class="sxs-lookup"><span data-stu-id="0f3b8-170">Any 5 of the first 9 servers</span></span>  <br/> |
|<span data-ttu-id="0f3b8-171">비즈니스용 Skype 서버  **2019의 경우 12-16**</span><span class="sxs-lookup"><span data-stu-id="0f3b8-171">12-16  **For Skype for Business Server 2019**</span></span>  <br/> |<span data-ttu-id="0f3b8-172">처음 12개 서버 중 7개</span><span class="sxs-lookup"><span data-stu-id="0f3b8-172">Any 7 of the first 12 servers</span></span>  <br/> |
   
<span data-ttu-id="0f3b8-173">위의 표에서 "첫 번째 서버"는 풀이 처음 시작된 시간부터 가장 먼저 시작된 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-173">In the preceding table, the "first servers" are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="0f3b8-174">이러한 서버를 확인하기 위해  `Get-CsComputer` 이 cmdlet을 옵션과 함께 사용할 수 `-PoolFqdn` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-174">To determine these servers, you can use the  `Get-CsComputer` cmdlet with the `-PoolFqdn` option.</span></span> <span data-ttu-id="0f3b8-175">이 cmdlet은 서버가 토폴로지에 나타나는 순서대로 표시하며 목록 맨 위에 있는 서버가 첫 번째 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-175">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0f3b8-176">최대 프런트 엔드 서버 수가 비즈니스용 [Skype 서버 2019에서 16으로 증가했습니다.](../../../SfBServer2019/plan/user-model-2019.md)</span><span class="sxs-lookup"><span data-stu-id="0f3b8-176">The maximum number of front end servers has been increased to 16 in [Skype for Business Server 2019](../../../SfBServer2019/plan/user-model-2019.md)</span></span>
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="0f3b8-177">풀이 작동하도록 하는 추가 단계</span><span class="sxs-lookup"><span data-stu-id="0f3b8-177">Additional steps to ensure pools are functional</span></span>

<span data-ttu-id="0f3b8-178">프런트 엔드 풀이 계속 작동하도록 보장하기 위해 몇 가지 다른 요소를 감시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-178">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>
  
- <span data-ttu-id="0f3b8-179">사용자를 풀로 처음 이동할 때 적어도 세 개의 프런트 엔드 서버가 실행되고 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-179">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>
    
- <span data-ttu-id="0f3b8-180">재해 복구를 위해 이 풀과 다른 풀 간에 페어링 관계를 설정하는 경우 해당 관계를 설정한 후 백업 풀과 데이터를 올바르게 동기화하려면 이 풀에 동시에 실행되는 프런트 엔드 서버 3개가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-180">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="0f3b8-181">풀 페어링 및 재해 복구 기능에 대한 자세한 내용은 [Plan for high availability and disaster recovery in Skype for Business Server을 참조하십시오.](high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="0f3b8-181">For more information on pool pairing and disaster recovery features, see [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md).</span></span> 
    
## <a name="front-end-pool-with-two-front-end-servers"></a><span data-ttu-id="0f3b8-182">프런트 엔드 서버가 2대인 프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="0f3b8-182">Front End pool with two Front End servers</span></span>

<span data-ttu-id="0f3b8-183">프런트 엔드 서버가 두 대만 포함된 프런트 엔드 풀은 배포하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-183">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="0f3b8-184">이 소규모 풀은 더 큰 풀과 같은 강력한 고가용성 솔루션을 제공하지는 못하며 관리에 특히 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-184">This small pool will not provide a robust high-availability solution like a larger pool would, and needs extra care in managing.</span></span> <span data-ttu-id="0f3b8-185">또한 두 서버 풀의 백 엔드 서버가 다운된 경우 전체 풀 자체도 곧 다운될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-185">Additionally, if the Back End Server of a two-server pool went down, the whole pool itself would likely soon go down as well.</span></span> <span data-ttu-id="0f3b8-186">비즈니스용 Skype 서버를 실행하는 한 두 대의 서버만 배포하려는 경우 Standard Edition 서버로 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-186">If you want to deploy just one or two servers running Skype for Business Server, we recommend you deploy them as Standard Edition servers.</span></span>
  
<span data-ttu-id="0f3b8-187">프런트 엔드 서버가 두 대인 풀을 배포해야 하는 경우 다음 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-187">If you do ever need to deploy a pool with two Front End Servers, follow these guidelines:</span></span>
  
- <span data-ttu-id="0f3b8-188">두 프런트 엔드 서버 중 한 대가 다운되는 경우 가능한 한 빨리 실패한 서버를 백업해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-188">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="0f3b8-189">마찬가지로, 두 서버 중 하나를 업그레이드해야 하는 경우 업그레이드가 완료되는 즉시 다시 온라인으로 되돌려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-189">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>
    
- <span data-ttu-id="0f3b8-190">어떤 이유로 인해 두 서버를 동시에 다운해야 하는 경우 풀의 다운타임이 완료되면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-190">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
  - <span data-ttu-id="0f3b8-191">최상의 방법은 두 프런트 엔드 서버를 동시에 다시 시작하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-191">The best practice is to restart both Front End Servers at the same time.</span></span> 
    
  - <span data-ttu-id="0f3b8-192">두 서버를 동시에 다시 시작할 수 없는 경우 서버가 다운된 순서의 역순으로 백업해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-192">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
  - <span data-ttu-id="0f3b8-193">해당 순서대로 백업할 수 없는 경우 풀을 백업하기 전에 다음 cmdlet을 사용 합니다.  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span><span class="sxs-lookup"><span data-stu-id="0f3b8-193">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span></span>
    
## <a name="front-end-pool-configuration-failures-and-changes"></a><span data-ttu-id="0f3b8-194">프런트 엔드 풀 구성 오류 및 변경 사항</span><span class="sxs-lookup"><span data-stu-id="0f3b8-194">Front End pool configuration failures and changes</span></span>

<span data-ttu-id="0f3b8-195">프런트 엔드 서버가 실패하여 며칠 이상 교체되지 않을 경우 토폴로지에서 서버를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-195">If a Front End server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="0f3b8-196">토폴로지에서 새 프런트 엔드 서버를 다시 사용할 수 있는 경우 토폴로지에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-196">Add the new Front End server to the topology when it is available again.</span></span>
  
<span data-ttu-id="0f3b8-197">서버 추가 또는 제거와 같이 프런트 엔드 풀의 구성을 변경할 때마다 다음 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-197">Whenever you make a configuration change to a Front End pool, such as adding or removing servers, you must follow these guidelines:</span></span>
  
- <span data-ttu-id="0f3b8-198">새 토폴로지가 게시된 후 풀의 각 프런트 엔드 서버를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-198">After the new topology has been published, you must restart each Front End server in the pool.</span></span> <span data-ttu-id="0f3b8-199">한 번씩 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3b8-199">Restart them one at a time.</span></span>
    
- <span data-ttu-id="0f3b8-200">구성 변경 중에 전체 풀이 다운된 경우 새 토폴로지가 게시된 후 다음 cmdlet을 실행합니다.  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span><span class="sxs-lookup"><span data-stu-id="0f3b8-200">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span></span>
