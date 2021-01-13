---
title: 비즈니스용 Skype 서버의 백 엔드 서버 고가용성
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
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: AlwaysOn 가용성 그룹, AlwaysOn 장애 조치(failover) 클러스터 인스턴스, 데이터베이스 미러링 및 장애 조치(failover) 클러스터링을 포함하여 비즈니스용 Skype 서버에서 지원되는 SQL 대해 자세히 알아보습니다.
ms.openlocfilehash: bbb55ded0d5ce1127f5dcab829907c533cc6316e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802928"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a><span data-ttu-id="09bcb-103">비즈니스용 Skype 서버의 백 엔드 서버 고가용성</span><span class="sxs-lookup"><span data-stu-id="09bcb-103">Back End Server high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="09bcb-104">AlwaysOn 가용성 그룹, AlwaysOn 장애 조치(failover) 클러스터 인스턴스, 데이터베이스 미러링 및 장애 조치(failover) 클러스터링을 포함하여 비즈니스용 Skype 서버에서 지원되는 SQL 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-104">Learn about the Back End Server high availability options supported in Skype for Business Server, including AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances, database mirroring, and SQL failover clustering.</span></span>
  
<span data-ttu-id="09bcb-105">백 엔드 서버의 고가용성을 향상하기 위해 다음과 같은 네 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-105">To enhance high availability for your Back End Servers, you have four options:</span></span>
  
- <span data-ttu-id="09bcb-106">데이터베이스 미러링</span><span class="sxs-lookup"><span data-stu-id="09bcb-106">Database mirroring</span></span>
    
- <span data-ttu-id="09bcb-107">AlwaysOn 가용성 그룹</span><span class="sxs-lookup"><span data-stu-id="09bcb-107">AlwaysOn Availability Groups</span></span>
    
- <span data-ttu-id="09bcb-108">AlwaysOn FCI(장애 조치(Failover) 클러스터 인스턴스)</span><span class="sxs-lookup"><span data-stu-id="09bcb-108">AlwaysOn Failover Cluster Instances (FCI)</span></span>
    
- <span data-ttu-id="09bcb-109">SQL 클러스터링</span><span class="sxs-lookup"><span data-stu-id="09bcb-109">SQL failover clustering</span></span>
    
<span data-ttu-id="09bcb-110">이러한 솔루션 중 하나를 사용하는 것은 선택 사항이지만 조직의 비즈니스 연속성을 유지 관리하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-110">Using one of these solutions is optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="09bcb-111">그렇지 않으면 데이터베이스 서버가 하나만 다운된 경우 비즈니스용 Skype 서버 데이터가 손실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-111">Otherwise, having a single database server go down could cause the loss of significant Skype for Business Server data.</span></span> 
  
<span data-ttu-id="09bcb-112">토폴로지 작성기만 사용하여 데이터베이스 미러링을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-112">You can set up database mirroring using only Topology Builder.</span></span> <span data-ttu-id="09bcb-113">AlwaysOn 가용성 그룹, AlwaysOn 장애 조치(failover) 클러스터 인스턴스 또는 SQL 장애 조치(failover) 클러스터링의 경우 SQL Server 사용하여 고가용성 솔루션을 만든 다음 토폴로지 작성기에서 이를 프런트 엔드 풀과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-113">For AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances,or SQL failover clustering, you use SQL Server to create the high availability solution, then you can use Topology Builder to associate it with a Front End pool.</span></span>
  
<span data-ttu-id="09bcb-114">재해 복구를 위해 다른 프런트 엔드 풀과 페어링된 프런트 엔드 풀에서 백 엔드 서버 고가용성을 사용하는 경우 두 풀에서 동일한 백 엔드 고가용성 솔루션을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-114">If you use Back End Server high availability on a Front End pool that is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> 
  
## <a name="database-mirroring"></a><span data-ttu-id="09bcb-115">데이터베이스 미러링</span><span class="sxs-lookup"><span data-stu-id="09bcb-115">Database mirroring</span></span>

<span data-ttu-id="09bcb-116">비즈니스용 Skype 서버는 다음 데이터베이스 소프트웨어를 사용하여 미러링을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-116">Skype for Business Server supports mirroring with the following database software:</span></span>
  
- <span data-ttu-id="09bcb-117">SQL Server Enterprise Edition 및 Standard Edition의 2019</span><span class="sxs-lookup"><span data-stu-id="09bcb-117">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="09bcb-118">SQL Server Enterprise Edition 및 Standard Edition 2017</span><span class="sxs-lookup"><span data-stu-id="09bcb-118">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="09bcb-119">SQL Server 2016, Enterprise Edition 및 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="09bcb-119">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="09bcb-120">SQL Server Enterprise Edition 및 Standard Edition 2014</span><span class="sxs-lookup"><span data-stu-id="09bcb-120">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="09bcb-121">SQL Server 2012 SP2 및 CU2, Enterprise Edition 및 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="09bcb-121">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>
    

> [!NOTE]
> <span data-ttu-id="09bcb-122">SQL 미러링은 비즈니스용 Skype 서버에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-122">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="09bcb-123">AlwaysOn 가용성 그룹, AlwaysOn FCI(장애 조치(failover) 클러스터 인스턴스) 및 SQL 장애 조치(failover) 클러스터링 방법은 비즈니스용 Skype 서버 2019에서 지원되는 유일한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-123">The AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are the only supported options with Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="09bcb-124">비즈니스용 Skype 서버의 백 엔드 서버 고가용성에는 비동기 데이터베이스 미러링이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-124">Asynchronous database mirroring is not supported for Back End Server high availability in Skype for Business Server.</span></span> <span data-ttu-id="09bcb-125">이 문서의 나머지에서 데이터베이스 미러링은 다른 명시적 설명이 없는 한 동기 데이터베이스 미러링을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-125">In the rest of this document, database mirroring means synchronous database mirroring, unless otherwise explicitly stated.</span></span> 
  
<span data-ttu-id="09bcb-126">프런트 엔드 풀에 데이터베이스 미러링을 배포하면 중앙 관리 저장소(이 풀에 있는 경우) 및 응답 그룹 응용 프로그램 데이터베이스 및 통화 파킹 응용 프로그램 데이터베이스(해당 응용 프로그램이 풀에서 실행되는 경우)를 포함하여 풀의 모든 비즈니스용 Skype 서버 데이터베이스가 미러링됩니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-126">When you deploy database mirroring in a Front End pool, all Skype for Business Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span> 
  
<span data-ttu-id="09bcb-127">데이터베이스 미러링을 사용하는 경우 서버에 대해 공유 저장소를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-127">With database mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="09bcb-128">각 서버는 로컬 저장소에 데이터베이스 복사본을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-128">Each server keeps its copy of the databases in local storage.</span></span> 
  
<span data-ttu-id="09bcb-129">미러링된 데이터베이스 미러링을 배포할지 또는 미러링되지 않은 데이터베이스 미러링을 배포할지 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-129">You may choose to deploy database mirroring with or without a witness.</span></span> <span data-ttu-id="09bcb-130">하지만 벡 엔드 서버의 장애 조치(failover)를 자동화할 수 있도록 미러링 모니터를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-130">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="09bcb-131">그렇지 않으면 관리자가 수동으로 장애 조치를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-131">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="09bcb-132">참고로, 미러링 모니터가 구축된 경우라도 필요하면 관리자가 수동으로 백 엔드 서버의 장애 조치를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-132">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>
  
<span data-ttu-id="09bcb-p107">미러링 모니터를 사용하는 경우 여러 쌍의 백 엔드 서버에 대해 단일 미러링 모니터를 사용할 수 있습니다. 미러링 모니터와 백 엔드 서버 쌍 간을 엄격하게 1:1로 일치시킬 필요는 없습니다. 여러 백 엔드 서버 쌍에 단일 미러링 모니터를 사용하는 구축의 경우 각 백 엔드 서버 쌍에 별도의 미러링 모니터를 사용하는 토폴로지보다 복원력은 다소 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-p107">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span> 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a><span data-ttu-id="09bcb-136">백 엔드 서버 미러링 계획 지침</span><span class="sxs-lookup"><span data-stu-id="09bcb-136">Guidelines for planning Back End Server mirroring</span></span>

<span data-ttu-id="09bcb-137">일반적으로 미러링 모니터 서버가 포함된 두 개의 백 엔드 서버 사이에 SQL 미러링을 설정하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-137">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>
  
- <span data-ttu-id="09bcb-138">기본 서버의 버전은 SQL Server 미러링을 SQL 합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-138">The primary server's version of SQL Server must support SQL mirroring.</span></span>
    
- <span data-ttu-id="09bcb-139">기본, 미러, 미러링 모니터 서버(배포된 경우)는 모두 SQL Server 버전이 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-139">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span> 
    
- <span data-ttu-id="09bcb-p108">기본 및 미러는 SQL Server의 에디션이 동일해야 합니다. 미러링 모니터 서버는 에디션이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-p108">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>
    
<span data-ttu-id="09bcb-142">미러링 SQL 지원되는 SQL 모범 사례에 대한 자세한 내용은 MSDN 라이브러리의 "데이터베이스 미러링 미러링  [지원"을](https://go.microsoft.com/fwlink/p/?LinkId=247345) 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-142">For SQL best practices in terms of what SQL versions are supported for a Witness role, see  ["Database Mirroring Witness"](https://go.microsoft.com/fwlink/p/?LinkId=247345) in the MSDN Library.</span></span>
  
<span data-ttu-id="09bcb-143">서버 미러링을 구성하기 전에 먼저 데이터베이스 SQL 올바르게 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-143">Before configuring server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="09bcb-144">자세한 내용은 "데이터베이스 미러링 또는 AlwaysOn 가용성 그룹에 대한 로그인 [계정 설정(SQL Server)"을 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkId=268454)</span><span class="sxs-lookup"><span data-stu-id="09bcb-144">For details, see  ["Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>
  
<span data-ttu-id="09bcb-p110">SQL 미러링을 사용할 경우 데이터베이스 복구 모드는 항상 **전체** 로 설정되므로 트랜잭션 로그 크기를 자세히 모니터링하고 백 엔드 서버의 디스크 공간이 부족해지지 않도록 정기적으로 트랜잭션 로그를 백업해야 합니다. 트랜잭션 로그 백업의 빈도는 로그 증가 속도에 따라 달라지며, 이는 다시 프런트 엔드 풀에서의 사용자 활동으로 인해 발생하는 데이터베이스 트랜잭션에 따라 달라집니다. 올바르게 계획할 수 있도록 Lync 배포 작업에 트랜잭션 로그 증가량이 얼마나 예상되는지 확인하는 것이 좋습니다. 다음 문서에서는 SQL 백업 및 로그 관리에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-p110">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="09bcb-149">토폴로지 작성기 또는 cmdlet을 사용하여 SQL 미러링을 설정 및 제거하는 것은 기본 서버, 미러 및 미러링 서버(필요한 경우)가 모두 동일한 도메인에 속하는 경우만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-149">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="09bcb-150">다른 도메인에 있는 서버 간에 SQL 미러링을 설정하려는 경우에는 SQL Server 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="09bcb-150">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span> 

> [!NOTE]
> <span data-ttu-id="09bcb-151">SQL 미러링은 비즈니스용 Skype 서버에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-151">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="09bcb-152">AlwaysOn 가용성 그룹, AlwaysOn FCI(장애 조치(failover) 클러스터 인스턴스) 및 SQL 장애 조치(failover) 클러스터링 방법은 비즈니스용 Skype 서버 2019에서 선호됩니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-152">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a><span data-ttu-id="09bcb-153">데이터베이스 미러링을 통해 자동 백 엔드 서버 장애 조치(failover)에 대한 복구 시간</span><span class="sxs-lookup"><span data-stu-id="09bcb-153">Recovery time for automatic Back End Server failover with database mirroring</span></span>

<span data-ttu-id="09bcb-154">데이터베이스 미러링을 통해 자동 백 엔드 장애 조치(failover)의 경우 RTO(복구 시간 목표)에 대한 엔지니어링 대상은 5분입니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-154">For automatic Back End failover with database mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="09bcb-155">동기 데이터베이스 미러링 때문에 프런트 엔드 서버와 백 엔드 서버가 동시에 다운되는 경우를 제외하고는 백 엔드 서버 오류 시 데이터 손실이 예상되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-155">Because of the synchronous database mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="09bcb-156">RPO(복구 지점 목표)에 대한 엔지니어링 대상은 5분입니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-156">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a><span data-ttu-id="09bcb-157">데이터베이스 미러링을 통해 백 엔드 서버 오류 시 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="09bcb-157">User experience during Back End Server failure with database mirroring</span></span>

<span data-ttu-id="09bcb-158">오류가 발생한 동안 사용자 환경에 미치는 영향은 오류의 특성과 토폴로지에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-158">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>
  
<span data-ttu-id="09bcb-159">데이터베이스 미러링을 사용하여 미러링을 구성한 경우 보안 주체가 실패하면 백 엔드 서버 장애 조치(failover)가 자동으로 빠르게 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-159">If you use database mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="09bcb-160">활성 사용자는 진행 중인 세션에서 중단이 발생했는지조차 알아채지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-160">Active users should not notice much interruption to their ongoing sessions.</span></span>
  
<span data-ttu-id="09bcb-161">미러링크가 구성되어 있는 경우 관리자가 장애 조치(failover)를 수동으로 호출하는 데 시간이 다소 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-161">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="09bcb-162">이 시간 동안 활성 사용자가 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-162">During that time, active users may be affected.</span></span> <span data-ttu-id="09bcb-163">약 30분 동안 세션을 정상으로 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-163">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="09bcb-164">기본이 복원되지 않은 경우 또는 관리자가 백업으로 전환하지 않은 경우 사용자는 복구 모드로 전환됩니다. 즉, Lync Server에서 연락처 추가와 같은 영구 변경이 필요한 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-164">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>
  
<span data-ttu-id="09bcb-p116">기본 서버와 미러 백 엔드 서버에 모두 오류가 발생하는 경우 또는 이러한 서버 중 하나와 미러링 모니터에 오류가 발생하는 경우 기본 서버가 실행 중이더라도 백 엔드 서버를 사용할 수 없습니다. 이러한 경우 활성 사용자는 일정 시간이 지난 후 복원 모드로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-p116">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a><span data-ttu-id="09bcb-167">AlwaysOn 가용성 그룹 및 AlwaysOn 장애 조치(failover) 클러스터 인스턴스</span><span class="sxs-lookup"><span data-stu-id="09bcb-167">AlwaysOn Availability Groups and AlwaysOn Failover Cluster Instances</span></span>

<span data-ttu-id="09bcb-168">비즈니스용 Skype 서버는 AlwaysOn 가용성 그룹을 활성/활성이 아닌 활성/수동으로만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-168">Skype for Business Server supports AlwaysOn Availability Groups only as active/passive, not active/active.</span></span> 
  
<span data-ttu-id="09bcb-169">AlwaysOn 가용성 그룹 또는 AlwaysOn 장애 조치(Failover) 클러스터 인스턴스를 사용하기 위해 먼저 SQL Server 사용하여 고가용성 솔루션을 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-169">To use AlwaysOn Availability Groups or AlwaysOn Failover Cluster Instances, you first use SQL Server to set up and configure the high availability solution.</span></span> <span data-ttu-id="09bcb-170">그런 다음 토폴로지 작성기에서 프런트 엔드 풀에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-170">You can then use Topology Builder to associate it with a Front End pool.</span></span>

<span data-ttu-id="09bcb-171">비즈니스용 Skype 서버는 다음 데이터베이스 소프트웨어를 사용하여 AlwaysOn을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-171">Skype for Business Server supports AlwaysOn with the following database software:</span></span>

- <span data-ttu-id="09bcb-172">SQL Server 2019 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="09bcb-172">SQL Server 2019 Enterprise Edition</span></span>

- <span data-ttu-id="09bcb-173">SQL Server 2019 Standard Edition에 제한이 있는 경우 아래 참고 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09bcb-173">SQL Server 2019 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="09bcb-174">SQL Server 2017 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="09bcb-174">SQL Server 2017 Enterprise Edition</span></span>

- <span data-ttu-id="09bcb-175">SQL Server 2017 Standard Edition에 제한이 있는 경우 아래 참고를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09bcb-175">SQL Server 2017 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="09bcb-176">SQL Server 2016 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="09bcb-176">SQL Server 2016 Enterprise Edition</span></span>

- <span data-ttu-id="09bcb-177">SQL Server 2016 Standard Edition에 제한이 있는 경우 아래 참고를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09bcb-177">SQL Server 2016 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="09bcb-178">SQL Server 2014 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="09bcb-178">SQL Server 2014 Enterprise Edition</span></span>
    
- <span data-ttu-id="09bcb-179">SQL Server 2012 SP2 및 CU2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="09bcb-179">SQL Server 2012 SP2 and CU2 Enterprise Edition</span></span>

> [!NOTE]
> <span data-ttu-id="09bcb-180">SQL Server 2019, 2017 및 2016은 비즈니스용 Skype 서버 2019에서 지원되는 유일한 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-180">SQL Server 2019, 2017, and 2016 are the only versions supported by Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="09bcb-181">Always On 가용성  그룹은 SQL 2016, 2017 및 2019 Standard Edition에서 지원되지 않지만 Always On 장애 조치(Failover) 클러스터 인스턴스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-181">Always On Availability Groups is **not** supported in SQL 2016, 2017, and 2019 Standard Editions but you can use Always On Failover Cluster Instances.</span></span> <span data-ttu-id="09bcb-182">자세한 내용은 SQL Server [2016의 버전](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) 및 지원되는 기능을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-182">See [Editions and supported features of SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) to learn more.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="09bcb-183">여러 AlwaysOn 가용성 그룹 인스턴스의 인스턴스 이름은 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-183">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
<span data-ttu-id="09bcb-184">AlwaysOn 가용성 그룹을 배포하는 단계는 비즈니스용 Skype 서버의 백 엔드 서버에 AlwaysOn 가용성 그룹 [배포를 참조하세요.](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)</span><span class="sxs-lookup"><span data-stu-id="09bcb-184">For steps for deploying AlwaysOn Availability Groups, see [Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).</span></span>
  
## <a name="sql-server-failover-clustering"></a><span data-ttu-id="09bcb-185">SQL Server 장애 조치(failover) 클러스터링</span><span class="sxs-lookup"><span data-stu-id="09bcb-185">SQL Server Failover Clustering</span></span>

<span data-ttu-id="09bcb-186">비즈니스용 Skype 서버는 다음 SQL Server 소프트웨어로 장애 조치(failover) 클러스터링을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-186">Skype for Business Server supports SQL Server failover clustering with the following database software:</span></span>
  
- <span data-ttu-id="09bcb-187">SQL Server Enterprise Edition 및 Standard Edition의 2019</span><span class="sxs-lookup"><span data-stu-id="09bcb-187">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="09bcb-188">SQL Server Enterprise Edition 및 Standard Edition 2017</span><span class="sxs-lookup"><span data-stu-id="09bcb-188">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="09bcb-189">SQL Server 2016, Enterprise Edition 및 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="09bcb-189">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="09bcb-190">SQL Server Enterprise Edition 및 Standard Edition 2014</span><span class="sxs-lookup"><span data-stu-id="09bcb-190">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="09bcb-191">SQL Server 2012 SP2 및 CU2, Enterprise Edition 및 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="09bcb-191">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>

<span data-ttu-id="09bcb-192">장애 조치(failover) 클러스터링을 SQL 프런트 엔드 풀을 배포하기 전에 먼저 SQL Server 클러스터를 설정하고 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-192">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="09bcb-193">2012년 2012의 장애 조치(failover) 클러스터링에 대한 SQL Server 지침은 [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx) 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09bcb-193">For best practices and setup instructions for failover clustering in SQL Server 2012, see [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="09bcb-194">SQL Server 2019, 2017 및 SQL Server 2016은 비즈니스용 Skype 서버 2019에서 지원되는 유일한 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-194">SQL Server 2019, 2017, and SQL Server 2016 are the only versions supported by Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="09bcb-195">장애 조치(failover) 클러스터링을 SQL 프런트 엔드 풀을 배포하기 전에 먼저 SQL Server 클러스터를 설정하고 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-195">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="09bcb-196">2014 및 2016의 장애 조치(failover) 클러스터링에 대한 SQL Server 지침은 [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx) 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09bcb-196">For best practices and setup instructions for failover clustering in SQL Server 2014 and 2016, see [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx).</span></span> <span data-ttu-id="09bcb-197">2008 SQL Server 장애 조치(failover) 클러스터링에 대한 자세한 내용은 [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx) 다음을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-197">For failover clustering in SQL Server 2008, see [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx).</span></span>
  
<span data-ttu-id="09bcb-198">SQL Server를 설치하는 경우 데이터베이스 위치 및 로그 파일 위치를 관리할 SQL Server Management Studio를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-198">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="09bcb-199">SQL Server Management Studio는 SQL Server를 설치할 때 선택적 구성 요소로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="09bcb-199">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>
  
