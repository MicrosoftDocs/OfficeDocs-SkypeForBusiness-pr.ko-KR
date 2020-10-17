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
# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="f04fc-102">Lync Server 2013의 프런트 엔드 서버, 인스턴트 메시징 및 현재 상태에 대 한 토폴로지 및 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f04fc-102">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f04fc-103">_**마지막으로 수정 된 항목:** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="f04fc-103">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="f04fc-104">IM (인스턴트 메시징) 및 현재 상태에 필요한 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-104">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="f04fc-105">조직의 프런트 엔드 서버 또는 Standard Edition 서버</span><span class="sxs-lookup"><span data-stu-id="f04fc-105">Your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="f04fc-106">이러한 서버에서 IM 및 현재 상태 기능을 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-106">IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="f04fc-107">부하 분산 장치 (Enterprise Edition 프런트 엔드 풀이 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="f04fc-107">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="f04fc-108">자세한 내용은 [Lync Server 2013의 부하 분산 요구 사항](lync-server-2013-load-balancing-requirements.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f04fc-108">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="f04fc-109">프런트 엔드 풀 배포 계획</span><span class="sxs-lookup"><span data-stu-id="f04fc-109">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="f04fc-110">Lync Server 2013에서는 프런트 엔드 풀 아키텍처가 변경 되었으며, 이러한 변경 사항에 따라 프런트 엔드 풀을 계획 하 고 유지 관리 하는 방법에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-110">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="f04fc-111">모든 Enterprise Edition 프런트 엔드 풀에는 세 개 이상의 프런트 엔드 서버가 포함 되는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-111">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="f04fc-112">Lync Server에서 프런트 엔드 풀의 아키텍처는 분산 시스템 모델을 사용 하며 각 사용자의 데이터는 풀의 세 프런트 엔드 서버에 보관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-112">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="f04fc-113">이 새로운 아키텍처에 대 한 자세한 내용은 [Lync Server 2013의 토폴로지 변경 사항을](lync-server-2013-topology-changes.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f04fc-113">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="f04fc-114">세 개의 Enterprise Edition 프런트 엔드 서버를 배포 하 고 재해 복구를 수행 하지 않으려면 Lync Server Standard Edition을 사용 하 고 쌍으로 된 백업 관계로 두 개의 풀을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-114">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="f04fc-115">이렇게 하면 서버가 두 대 인 재해 복구 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-115">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="f04fc-116">고가용성 및 재해 복구 토폴로지와 기능에 대 한 자세한 내용은 [Lync Server 2013에서 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f04fc-116">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="f04fc-117">프런트 엔드 풀 관리 계획</span><span class="sxs-lookup"><span data-stu-id="f04fc-117">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="f04fc-118">프런트 엔드 풀의 경우이 섹션의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-118">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="f04fc-119">풀이 작동 하는지 확인</span><span class="sxs-lookup"><span data-stu-id="f04fc-119">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="f04fc-120">프런트 엔드 풀에 대 한 새 분산 모델을 사용 하는 경우 풀이 작동 하려면 풀 서버의 특정 번호가 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-120">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="f04fc-121">풀에는 두 가지 손실 모드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-121">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="f04fc-122">특정 라우팅 그룹에 대 한 복제본 서버가 부족 하 여 라우팅 그룹 수준 쿼럼 손실이 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-122">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="f04fc-123">라우팅 그룹은 풀에 속한 사용자 집합의 집합체입니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-123">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="f04fc-124">각 라우팅 그룹에는 하나의 기본 및 두 보조를 하나씩 포함 하 여 풀의 복제본이 세 개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-124">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="f04fc-125">풀 수준 쿼럼 손실 (풀에서 시드 서버가 충분히 실행 되지 않을 때 발생 하는 경우)</span><span class="sxs-lookup"><span data-stu-id="f04fc-125">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="f04fc-126">라우팅 그룹 수준 쿼럼 손실</span><span class="sxs-lookup"><span data-stu-id="f04fc-126">Routing Group Level quorum loss</span></span>

<span data-ttu-id="f04fc-127">새 프런트 엔드 풀을 처음 시작 하는 경우에는 다음 표에 나와 있는 것과 같이 서버 중에서 1 ~ 85%가 작동 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-127">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="f04fc-128">실행 중인 서버가 적으면 서비스가 시작 상태에 걸려 풀이 시작 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-128">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f04fc-129">풀에 있는 총 서버 수</span><span class="sxs-lookup"><span data-stu-id="f04fc-129">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="f04fc-130">풀을 처음 시작할 때 실행 해야 하는 서버 수</span><span class="sxs-lookup"><span data-stu-id="f04fc-130">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f04fc-131">2</span><span class="sxs-lookup"><span data-stu-id="f04fc-131">2</span></span></p></td>
<td><p><span data-ttu-id="f04fc-132">1 </span><span class="sxs-lookup"><span data-stu-id="f04fc-132">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f04fc-133">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="f04fc-133">3</span></span></p></td>
<td><p><span data-ttu-id="f04fc-134">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="f04fc-134">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f04fc-135">4 </span><span class="sxs-lookup"><span data-stu-id="f04fc-135">4</span></span></p></td>
<td><p><span data-ttu-id="f04fc-136">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="f04fc-136">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f04fc-137">5 </span><span class="sxs-lookup"><span data-stu-id="f04fc-137">5</span></span></p></td>
<td><p><span data-ttu-id="f04fc-138">4 </span><span class="sxs-lookup"><span data-stu-id="f04fc-138">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f04fc-139">6 </span><span class="sxs-lookup"><span data-stu-id="f04fc-139">6</span></span></p></td>
<td><p><span data-ttu-id="f04fc-140">5 </span><span class="sxs-lookup"><span data-stu-id="f04fc-140">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f04fc-141">7 </span><span class="sxs-lookup"><span data-stu-id="f04fc-141">7</span></span></p></td>
<td><p><span data-ttu-id="f04fc-142">5 </span><span class="sxs-lookup"><span data-stu-id="f04fc-142">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f04fc-143">8 </span><span class="sxs-lookup"><span data-stu-id="f04fc-143">8</span></span></p></td>
<td><p><span data-ttu-id="f04fc-144">6 </span><span class="sxs-lookup"><span data-stu-id="f04fc-144">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f04fc-145">9 </span><span class="sxs-lookup"><span data-stu-id="f04fc-145">9</span></span></p></td>
<td><p><span data-ttu-id="f04fc-146">7 </span><span class="sxs-lookup"><span data-stu-id="f04fc-146">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f04fc-147">10  </span><span class="sxs-lookup"><span data-stu-id="f04fc-147">10</span></span></p></td>
<td><p><span data-ttu-id="f04fc-148">8 </span><span class="sxs-lookup"><span data-stu-id="f04fc-148">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f04fc-149">11 </span><span class="sxs-lookup"><span data-stu-id="f04fc-149">11</span></span></p></td>
<td><p><span data-ttu-id="f04fc-150">9 </span><span class="sxs-lookup"><span data-stu-id="f04fc-150">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f04fc-151">12 </span><span class="sxs-lookup"><span data-stu-id="f04fc-151">12</span></span></p></td>
<td><p><span data-ttu-id="f04fc-152">10  </span><span class="sxs-lookup"><span data-stu-id="f04fc-152">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f04fc-153">그 다음에 풀을 시작할 때마다 서버의 85% (위 표에 표시 된 대로)가 시작 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-153">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="f04fc-154">이 서버 수를 시작할 수 없지만 풀 수준 쿼럼 손실에 해당 되지 않도록 충분 한 서버를 시작할 수 있으면 **Reset-reset-cspoolregistrarstate – ResetType QuorumLossRecovery** cmdlet을 사용 하 여 풀을이 라우팅 그룹 수준 쿼럼 손실에서 복구 하 고 작업을 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-154">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="f04fc-155">이 cmdlet을 사용 하는 방법에 대 한 자세한 내용은 [Reset-reset-cspoolregistrarstate](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f04fc-155">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f04fc-156">Lync Server에서는 기본 SQL 데이터베이스를 미러링 모니터로 사용 하기 때문에 기본 데이터베이스를 종료 하 고 미러 복사본으로 전환한 다음 충분 한 프런트 엔드 서버를 종료 하 여 앞의 표에 따라 충분히 실행 되지 않도록 하려면 전체 풀이 다운 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-156">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="f04fc-157">자세한 내용은 <A href="https://go.microsoft.com/fwlink/?linkid=393672">데이터베이스 미러링 모니터 서버</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f04fc-157">For more information, see <A href="https://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="f04fc-158">풀 수준 쿼럼 손실</span><span class="sxs-lookup"><span data-stu-id="f04fc-158">Pool-level quorum loss</span></span>

<span data-ttu-id="f04fc-159">프런트 엔드 풀은 모두 작동 하기 위해 풀 수준의 쿼럼 손실 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-159">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="f04fc-160">실행 중인 서버의 수가 다음 표에 나와 있는 것 처럼 기능 수준 아래로 떨어지면 풀의 나머지 서버가 모든 Lync Server 서비스를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-160">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="f04fc-161">다음 표의 숫자는 풀의 백 엔드 서버가 실행 되 고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-161">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f04fc-162">풀에 있는 총 프런트 엔드 서버 수</span><span class="sxs-lookup"><span data-stu-id="f04fc-162">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="f04fc-163">풀 작동을 위해 실행되어야 하는 서버 수</span><span class="sxs-lookup"><span data-stu-id="f04fc-163">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f04fc-164">2</span><span class="sxs-lookup"><span data-stu-id="f04fc-164">2</span></span></p></td>
<td><p><span data-ttu-id="f04fc-165">1 </span><span class="sxs-lookup"><span data-stu-id="f04fc-165">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f04fc-166">3-4</span><span class="sxs-lookup"><span data-stu-id="f04fc-166">3-4</span></span></p></td>
<td><p><span data-ttu-id="f04fc-167">모두 2</span><span class="sxs-lookup"><span data-stu-id="f04fc-167">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f04fc-168">5-6</span><span class="sxs-lookup"><span data-stu-id="f04fc-168">5-6</span></span></p></td>
<td><p><span data-ttu-id="f04fc-169">모두 3</span><span class="sxs-lookup"><span data-stu-id="f04fc-169">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f04fc-170">7 </span><span class="sxs-lookup"><span data-stu-id="f04fc-170">7</span></span></p></td>
<td><p><span data-ttu-id="f04fc-171">모든 4</span><span class="sxs-lookup"><span data-stu-id="f04fc-171">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f04fc-172">8-9</span><span class="sxs-lookup"><span data-stu-id="f04fc-172">8-9</span></span></p></td>
<td><p><span data-ttu-id="f04fc-173">처음 7 개 서버 중 하나라도</span><span class="sxs-lookup"><span data-stu-id="f04fc-173">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f04fc-174">10-12</span><span class="sxs-lookup"><span data-stu-id="f04fc-174">10-12</span></span></p></td>
<td><p><span data-ttu-id="f04fc-175">처음 9 대의 서버 5 개</span><span class="sxs-lookup"><span data-stu-id="f04fc-175">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f04fc-176">위의 표에서 첫 번째 서버는 풀이 처음으로 시작 된 경우 시간순으로 나열 되는 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-176">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="f04fc-177">이러한 서버를 확인 하려면 **– Poolfqdn** 옵션을 사용 하 여 **Get cscomputer** cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-177">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="f04fc-178">이 cmdlet은 토폴로지에 표시 되는 순서 대로 서버를 표시 하며, 목록 맨 위에 있는 서버가 첫 번째 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-178">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="f04fc-179">두 개의 프런트 엔드 서버를 포함 하는 프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="f04fc-179">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="f04fc-180">두 개의 프런트 엔드 서버만 포함 된 프런트 엔드 풀을 배포 하는 것은 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-180">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="f04fc-181">이러한 풀을 배포 해야 하는 경우 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-181">If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="f04fc-182">두 프런트 엔드 서버 중 하나가 다운 되 면 가능 하면 즉시 실패 한 서버를 백업 해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="f04fc-182">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="f04fc-183">마찬가지로, 두 서버 중 하나를 업그레이드 해야 하는 경우 업그레이드가 완료 되는 즉시 다시 온라인 상태로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-183">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="f04fc-184">어떤 이유로 두 서버를 동시에 가져오는 데 필요한 경우 풀에 대 한 가동 중지 시간이 완료 되 면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="f04fc-185">가장 좋은 방법은 두 프런트 엔드 서버를 동시에 다시 시작 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-185">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="f04fc-186">두 서버를 동시에 다시 시작할 수 없는 경우에는 다운 된 순서와 순서가 거꾸로 복원 되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="f04fc-187">해당 순서 대로 백업할 수 없는 경우 풀을 백업 하기 전에 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="f04fc-188">풀이 작동 하도록 확인 하기 위한 추가 단계</span><span class="sxs-lookup"><span data-stu-id="f04fc-188">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="f04fc-189">프런트 엔드 풀이 계속 작동 되도록 하려면 몇 가지 다른 요인을 살펴봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-189">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="f04fc-190">사용자를 처음으로 풀로 이동할 때는 프런트 엔드 서버 중 세 개 이상이 실행 되 고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-190">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="f04fc-191">이 풀과 재해 복구를 위해 다른 풀 간의 연결 관계를 설정 하는 경우 해당 관계를 설정한 후에는이 풀에 백업 풀과 데이터를 올바르게 동기화 하기 위해 일정 시간 동안 동시에 실행 되는 세 개의 프런트 엔드 서버가 있는지를 파악 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-191">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="f04fc-192">풀 페어링 및 재해 복구 기능에 대 한 자세한 내용은 [Lync Server 2013에서 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f04fc-192">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="f04fc-193">풀 업그레이드의 안정성 향상</span><span class="sxs-lookup"><span data-stu-id="f04fc-193">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="f04fc-194">프런트 엔드 풀에서 서버를 업그레이드 하거나 패치 해야 하는 경우에는 [Lync Server 2013의 프런트 엔드 서버 업그레이드 또는 업데이트](lync-server-2013-upgrade-or-update-front-end-servers.md)에 표시 된 워크플로를 따르고 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-194">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="f04fc-195">업그레이드를 위해 업그레이드를 수행 하는 경우 (예를 들어 [Lync Server 2013의 프런트 엔드 서버를 업데이트 하거나 업그레이드할](lync-server-2013-upgrade-or-update-front-end-servers.md)때의 워크플로를 팔 로우 하는 경우) **get-cspoolupgradereadinessstate** cmdlet을 사용 하 여 준비 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-195">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="f04fc-196">"Ready"에 도달 하면 각 업그레이드 도메인 사이에 20 분의 대기 시간을 추가 하면 업그레이드가 보다 안정적으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-196">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="f04fc-197">20 분 동안 **준비 되지** 않으면 20 분 타이머를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-197">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="f04fc-198">또한 20 분 간격을 시작 하기 전이나 후에 **get-cspoolfabricstate** cmdlet을 실행 하 고 라우팅 그룹의 기본 및 보조가 변경 되지 않았는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-198">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="f04fc-199">마지막으로 패치 된 업그레이드 도메인에 있는 서버 중 하나라도 중지 되거나 다시 시작 되지 않으면 다음 업그레이드 도메인으로 이동 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="f04fc-199">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="f04fc-200">이는 업그레이드 내에서 서버를 시작할 수 없는 경우에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-200">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="f04fc-201">**Get-cspoolfabricstate** 를 실행 하 여 모든 라우팅 그룹에 기본 및 하나 이상의 보조가 있는지 확인 합니다. 이렇게 하면 모든 사용자에 게 서비스가 있는지 여부가 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-201">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="f04fc-202">일부 사용자에 게 서비스가 있는 경우-Verbose 옵션을 사용 하 여 **get-cspoolfabricstate** 를 실행 하 여 복제본이 없는 라우팅 그룹을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-202">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="f04fc-203">전체 풀을 첫 번째 문제 해결 단계로 다시 시작 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="f04fc-203">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="f04fc-204">이 cmdlet에 대 한 자세한 내용은 [get-cspoolfabricstate](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="f04fc-204">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="f04fc-205">이벤트 뷰어 또는 성능 모니터 창의 모든 인스턴스가 windows fabric 설치/제거를 위해 닫혀 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-205">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="f04fc-206">프런트 엔드 풀의 구성 변경</span><span class="sxs-lookup"><span data-stu-id="f04fc-206">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="f04fc-207">프런트 엔드 서버를 풀에 추가 하거나 풀에서 제거한 다음 새 토폴로지를 게시할 때마다 다음 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-207">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="f04fc-208">새 토폴로지가 게시 된 후에 풀에서 각 프런트 엔드 서버를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-208">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="f04fc-209">한 번에 하나씩 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-209">Restart them one at a time.</span></span>

  - <span data-ttu-id="f04fc-210">구성 변경 중에 전체 풀이 다운 된 경우 새 토폴로지를 게시 한 후 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-210">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="f04fc-211">프런트 엔드 서버에 오류가 발생 하 여 며칠 이상 교체 될 가능성이 없는 경우 토폴로지에서 해당 서버를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-211">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="f04fc-212">새 프런트 엔드 서버를 다시 사용할 수 있게 되 면 토폴로지에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f04fc-212">Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

