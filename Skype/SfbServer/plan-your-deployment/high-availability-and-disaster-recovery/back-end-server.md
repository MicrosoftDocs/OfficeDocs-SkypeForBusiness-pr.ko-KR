---
title: 비즈니스용 Skype 서버의 백 엔드 서버 고가용성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: AlwaysOn 가용성 그룹, AlwaysOn 장애 조치 클러스터 인스턴스, 데이터베이스 미러링, SQL 장애 조치 클러스터링을 비롯 하 여 비즈니스용 Skype 서버에서 지원 되는 백 엔드 서버 고가용성 옵션에 대해 알아봅니다.
ms.openlocfilehash: 3a92c7ee8cbada8ce678e53e3aacff0aa562fca5
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991493"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a><span data-ttu-id="fe42f-103">비즈니스용 Skype 서버의 백 엔드 서버 고가용성</span><span class="sxs-lookup"><span data-stu-id="fe42f-103">Back End Server high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="fe42f-104">AlwaysOn 가용성 그룹, AlwaysOn 장애 조치 클러스터 인스턴스, 데이터베이스 미러링, SQL 장애 조치 클러스터링을 비롯 하 여 비즈니스용 Skype 서버에서 지원 되는 백 엔드 서버 고가용성 옵션에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-104">Learn about the Back End Server high availability options supported in Skype for Business Server, including AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances, database mirroring, and SQL failover clustering.</span></span>
  
<span data-ttu-id="fe42f-105">백 엔드 서버의 가용성을 높이기 위해 다음 네 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-105">To enhance high availability for your Back End Servers, you have four options:</span></span>
  
- <span data-ttu-id="fe42f-106">데이터베이스 미러링</span><span class="sxs-lookup"><span data-stu-id="fe42f-106">Database mirroring</span></span>
    
- <span data-ttu-id="fe42f-107">AlwaysOn 가용성 그룹</span><span class="sxs-lookup"><span data-stu-id="fe42f-107">AlwaysOn Availability Groups</span></span>
    
- <span data-ttu-id="fe42f-108">FCI (Failover) 클러스터 인스턴스 (AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="fe42f-108">AlwaysOn Failover Cluster Instances (FCI)</span></span>
    
- <span data-ttu-id="fe42f-109">SQL 장애 조치 클러스터링</span><span class="sxs-lookup"><span data-stu-id="fe42f-109">SQL failover clustering</span></span>
    
<span data-ttu-id="fe42f-110">이러한 솔루션 중 하나를 사용 하는 것은 선택 사항 이지만 조직의 비즈니스 연속성을 유지 관리 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-110">Using one of these solutions is optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="fe42f-111">그렇지 않으면 단일 데이터베이스 서버를 종료 하면 중요 한 비즈니스용 Skype 서버 데이터가 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-111">Otherwise, having a single database server go down could cause the loss of significant Skype for Business Server data.</span></span> 
  
<span data-ttu-id="fe42f-112">토폴로지 작성기만 사용 하 여 데이터베이스 미러링을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-112">You can set up database mirroring using only Topology Builder.</span></span> <span data-ttu-id="fe42f-113">AlwaysOn 가용성 그룹, AlwaysOn 장애 조치 클러스터 인스턴스 또는 SQL 장애 조치 (failover) 클러스터링의 경우 SQL Server를 사용 하 여 고가용성 솔루션을 만든 다음 토폴로지 작성기를 사용 하 여 프런트 엔드 풀과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-113">For AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances,or SQL failover clustering, you use SQL Server to create the high availability solution, then you can use Topology Builder to associate it with a Front End pool.</span></span>
  
<span data-ttu-id="fe42f-114">재해 복구를 위해 다른 프런트 엔드 풀과 쌍을 이루는 프런트 엔드 풀에서 백 엔드 서버 가용성을 사용 하는 경우 두 풀에서 동일한 백 엔드 고가용성 솔루션을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-114">If you use Back End Server high availability on a Front End pool that is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> 
  
## <a name="database-mirroring"></a><span data-ttu-id="fe42f-115">데이터베이스 미러링</span><span class="sxs-lookup"><span data-stu-id="fe42f-115">Database mirroring</span></span>

<span data-ttu-id="fe42f-116">비즈니스용 Skype 서버는 다음 데이터베이스 소프트웨어와의 미러링을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-116">Skype for Business Server supports mirroring with the following database software:</span></span>
  
- <span data-ttu-id="fe42f-117">SQL Server 2019 (Enterprise Edition 및 Standard Edition 모두)</span><span class="sxs-lookup"><span data-stu-id="fe42f-117">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="fe42f-118">SQL Server 2017 (Enterprise Edition 및 Standard Edition 모두)</span><span class="sxs-lookup"><span data-stu-id="fe42f-118">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="fe42f-119">SQL Server 2016 (Enterprise Edition 및 Standard Edition 모두)</span><span class="sxs-lookup"><span data-stu-id="fe42f-119">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="fe42f-120">SQL Server 2014 (Enterprise Edition 및 Standard Edition 모두)</span><span class="sxs-lookup"><span data-stu-id="fe42f-120">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="fe42f-121">SQL Server 2012 SP2 및 CU2 (Enterprise Edition 및 Standard Edition 모두 해당)</span><span class="sxs-lookup"><span data-stu-id="fe42f-121">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>
    

> [!NOTE]
> <span data-ttu-id="fe42f-122">SQL 미러링은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-122">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="fe42f-123">AlwaysOn 가용성 그룹,이 어 장애 조치 (Failover) 클러스터 인스턴스 (FCI) 및 SQL 장애 조치 (failover) 클러스터링 방법은 비즈니스용 Skype 서버 2019에서 선호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-123">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="fe42f-124">비즈니스용 Skype 서버에서 백 엔드 서버의 고가용성을 사용할 수 없는 경우 비동기 데이터베이스 미러링이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-124">Asynchronous database mirroring is not supported for Back End Server high availability in Skype for Business Server.</span></span> <span data-ttu-id="fe42f-125">이 문서의 나머지 부분에서 데이터베이스 미러링은 명시적으로 명시 되지 않은 경우 동기 데이터베이스 미러링을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-125">In the rest of this document, database mirroring means synchronous database mirroring, unless otherwise explicitly stated.</span></span> 
  
<span data-ttu-id="fe42f-126">프런트 엔드 풀에서 데이터베이스 미러링을 배포 하는 경우 중앙 관리 저장소를 포함 하 여 해당 풀에 있는 모든 비즈니스용 Skype 서버 데이터베이스가 미러링 되며 응답 그룹 응용 프로그램 데이터베이스 및 통화 대기 시간에도 해당 됩니다. 응용 프로그램이 풀에서 실행 되는 경우 해당 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="fe42f-126">When you deploy database mirroring in a Front End pool, all Skype for Business Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span> 
  
<span data-ttu-id="fe42f-127">데이터베이스 미러링에서는 서버에 공유 저장소를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-127">With database mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="fe42f-128">각 서버는 로컬 저장소에 데이터베이스 복사본을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-128">Each server keeps its copy of the databases in local storage.</span></span> 
  
<span data-ttu-id="fe42f-129">미러링 모니터 서버와 함께 데이터베이스 미러링을 배포 하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-129">You may choose to deploy database mirroring with or without a witness.</span></span> <span data-ttu-id="fe42f-130">미러링 모니터 서버를 사용 하 여 백 엔드 서버의 장애 조치를 자동으로 수행할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-130">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="fe42f-131">그렇지 않으면 관리자가 장애 조치를 수동으로 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-131">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="fe42f-132">미러링 모니터 서버가 배포 된 경우에도 관리자는 필요한 경우 백 엔드 서버 장애 조치를 수동으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-132">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>
  
<span data-ttu-id="fe42f-133">미러링 모니터 서버를 사용 하는 경우 백 엔드 서버의 여러 쌍에 단일 미러링 모니터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-133">If you use a witness, you can use a single witness for multiple pairs of Back End Servers.</span></span> <span data-ttu-id="fe42f-134">백 엔드 서버와 witnesses의 짝이 엄격한 1:1 대응 기능은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-134">There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers.</span></span> <span data-ttu-id="fe42f-135">여러 백 엔드 서버 쌍에 단일 미러링 모니터를 사용 하는 배포는 각 백 엔드 서버 쌍에 대해 별도의 감시가 있는 토폴로지로 탄력적으로 복구 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-135">Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span> 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a><span data-ttu-id="fe42f-136">백 엔드 서버 미러링 계획에 대 한 지침</span><span class="sxs-lookup"><span data-stu-id="fe42f-136">Guidelines for planning Back End Server mirroring</span></span>

<span data-ttu-id="fe42f-137">일반적으로 미러링 모니터로 두 백 엔드 서버 간에 SQL 미러링을 설정 하려면 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-137">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>
  
- <span data-ttu-id="fe42f-138">주 서버의 SQL Server 버전은 SQL 미러링을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-138">The primary server's version of SQL Server must support SQL mirroring.</span></span>
    
- <span data-ttu-id="fe42f-139">기본, 미러, 미러링 모니터 (배포 된 경우)는 동일한 버전의 SQL Server를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-139">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span> 
    
- <span data-ttu-id="fe42f-140">기본 및 미러에는 동일한 버전의 SQL Server가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-140">The primary and the mirror must have the same edition of SQL Server.</span></span> <span data-ttu-id="fe42f-141">미러링 모니터 서버에 다른 버전이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-141">The witness may have a different edition.</span></span>
    
<span data-ttu-id="fe42f-142">미러링 모니터 역할에 대해 지원 되는 SQL 버전에 대 한 SQL 모범 사례는 MSDN Library의 ["데이터베이스 미러링 감시"](https://go.microsoft.com/fwlink/p/?LinkId=247345) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe42f-142">For SQL best practices in terms of what SQL versions are supported for a Witness role, see  ["Database Mirroring Witness"](https://go.microsoft.com/fwlink/p/?LinkId=247345) in the MSDN Library.</span></span>
  
<span data-ttu-id="fe42f-143">서버 미러링을 구성 하기 전에 먼저 SQL 데이터베이스 사용 권한을 올바르게 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-143">Before configuring server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="fe42f-144">자세한 내용은 ["데이터베이스 미러링 또는 AlwaysOn 가용성 그룹에 대 한 로그인 계정 설정 (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe42f-144">For details, see  ["Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>
  
<span data-ttu-id="fe42f-145">SQL 미러링에서는 데이터베이스 복구 모드가 항상 **Full**로 설정 되며,이는 백 엔드 서버의 디스크 공간 부족을 방지 하기 위해 트랜잭션 로그 크기를 면밀 하 게 모니터링 하 고 트랜잭션 로그를 정기적으로 백업 해야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-145">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers.</span></span> <span data-ttu-id="fe42f-146">트랜잭션 로그 백업의 빈도는 로그 증가 속도에 따라 다르며,이는 프런트 엔드 풀의 사용자 활동에서 발생 하는 데이터베이스 트랜잭션에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-146">The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool.</span></span> <span data-ttu-id="fe42f-147">계획을 적절 하 게 수행할 수 있도록 Lync 배포 작업 부하에 예상 되는 트랜잭션 로그 성장이 얼마나 되는지 결정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-147">We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly.</span></span> <span data-ttu-id="fe42f-148">다음 문서는 SQL 백업 및 로그 관리에 대 한 추가 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-148">The following articles provide additional information on SQL backup and log management:</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fe42f-149">토폴로지 작성기 또는 cmdlet을 사용 하 여 SQL 미러링을 설정 및 제거 하는 것은 주, 미러, 미러링 모니터 (원하는 경우) 서버가 모두 동일한 도메인에 속해 있는 경우에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-149">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="fe42f-150">다른 도메인의 서버 간에 SQL 미러링을 설정 하려면 SQL Server 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe42f-150">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span> 

> [!NOTE]
> <span data-ttu-id="fe42f-151">SQL 미러링은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-151">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="fe42f-152">AlwaysOn 가용성 그룹,이 어 장애 조치 (Failover) 클러스터 인스턴스 (FCI) 및 SQL 장애 조치 (failover) 클러스터링 방법은 비즈니스용 Skype 서버 2019에서 선호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-152">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a><span data-ttu-id="fe42f-153">데이터베이스 미러링을 사용 하 여 자동 백 엔드 서버 장애 조치 복구 시간</span><span class="sxs-lookup"><span data-stu-id="fe42f-153">Recovery time for automatic Back End Server failover with database mirroring</span></span>

<span data-ttu-id="fe42f-154">데이터베이스 미러링으로 자동 백 엔드 장애 조치를 사용 하는 경우 RTO (복구 시간 목표)에 대 한 엔지니어링 대상은 5 분입니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-154">For automatic Back End failover with database mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="fe42f-155">동기 데이터베이스 미러링 때문에, 서버 간에 데이터를 이동 하는 동안 프런트 엔드 서버와 백 엔드 서버가 동시에 종료 되는 경우를 제외 하 고는 백 엔드 서버 오류 시 데이터 손실이 예상 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-155">Because of the synchronous database mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="fe42f-156">RPO (복구 시점 목표)에 대 한 엔지니어링 대상은 5 분입니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-156">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a><span data-ttu-id="fe42f-157">데이터베이스 미러링으로 백 엔드 서버 오류 발생 시 사용자 환경</span><span class="sxs-lookup"><span data-stu-id="fe42f-157">User experience during Back End Server failure with database mirroring</span></span>

<span data-ttu-id="fe42f-158">오류 발생 시 사용자 환경은 오류의 성격 및 토폴로지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-158">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>
  
<span data-ttu-id="fe42f-159">데이터베이스 미러링을 사용 하 고 미러링 모니터 서버가 구성 되어 있는 경우 주 서버가 실패 하면 백 엔드 서버 장애 조치는 자동으로 신속 하 게 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-159">If you use database mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="fe42f-160">활성 사용자는 진행 중인 세션을 크게 중단 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-160">Active users should not notice much interruption to their ongoing sessions.</span></span>
  
<span data-ttu-id="fe42f-161">미러링 모니터가 구성 되어 있지 않은 경우 관리자가 장애 조치를 수동으로 호출 하는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-161">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="fe42f-162">이 기간 동안에는 활성 사용자에 게 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-162">During that time, active users may be affected.</span></span> <span data-ttu-id="fe42f-163">약 30 분 동안에는 세션을 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-163">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="fe42f-164">기본 상태가 복원 되지 않거나 관리자가 백업으로 장애 조치 되지 않으면 사용자가 복원 모드로 전환 되어 Lync Server (예: 대화 상대 추가)에 영구적으로 변경 해야 하는 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-164">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>
  
<span data-ttu-id="fe42f-165">주 서버와 미러 백 엔드 서버가 둘 다 실패 하거나 이러한 서버와 미러링 모니터 서버가 실패 한 경우 백 엔드 서버를 사용할 수 없게 됩니다 (아직 작동 중인 주에 포함).</span><span class="sxs-lookup"><span data-stu-id="fe42f-165">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working).</span></span> <span data-ttu-id="fe42f-166">이 경우 활성 사용자는 잠시 후에 복원 모드로 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-166">In this case, active users are switched to Resiliency mode after some time.</span></span>
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a><span data-ttu-id="fe42f-167">AlwaysOn 가용성 그룹 및 AlwaysOn 장애 조치 (Failover) 클러스터 인스턴스</span><span class="sxs-lookup"><span data-stu-id="fe42f-167">AlwaysOn Availability Groups and AlwaysOn Failover Cluster Instances</span></span>

<span data-ttu-id="fe42f-168">비즈니스용 Skype 서버는 활성/passive 또는 액티브/액티브는 제외 하 고 AlwaysOn 가용성 그룹만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-168">Skype for Business Server supports AlwaysOn Availability Groups only as active/passive, not active/active.</span></span> 
  
<span data-ttu-id="fe42f-169">AlwaysOn 가용성 그룹 또는 AlwaysOn 장애 조치 (Failover) 클러스터 인스턴스를 사용 하려면 먼저 SQL Server를 사용 하 여 고가용성 솔루션을 설정 하 고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-169">To use AlwaysOn Availability Groups or AlwaysOn Failover Cluster Instances, you first use SQL Server to set up and configure the high availability solution.</span></span> <span data-ttu-id="fe42f-170">그런 다음 토폴로지 작성기를 사용 하 여 프런트 엔드 풀과 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-170">You can then use Topology Builder to associate it with a Front End pool.</span></span>

<span data-ttu-id="fe42f-171">비즈니스용 Skype 서버는 다음 데이터베이스 소프트웨어를 사용 하 여 AlwaysOn을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-171">Skype for Business Server supports AlwaysOn with the following database software:</span></span>

- <span data-ttu-id="fe42f-172">SQL Server 2019 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="fe42f-172">SQL Server 2019 Enterprise Edition</span></span>

- <span data-ttu-id="fe42f-173">제한 사항이 적용 되는 SQL Server 2019 Standard Edition의 아래 참고 자료를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe42f-173">SQL Server 2019 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="fe42f-174">SQL Server 2017 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="fe42f-174">SQL Server 2017 Enterprise Edition</span></span>

- <span data-ttu-id="fe42f-175">제한 사항이 적용 되는 SQL Server 2017 Standard Edition의 아래 참고 자료를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe42f-175">SQL Server 2017 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="fe42f-176">SQL Server 2016 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="fe42f-176">SQL Server 2016 Enterprise Edition</span></span>

- <span data-ttu-id="fe42f-177">제한 사항이 적용 되는 SQL Server 2016 Standard Edition의 아래 참고 자료를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe42f-177">SQL Server 2016 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="fe42f-178">SQL Server 2014 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="fe42f-178">SQL Server 2014 Enterprise Edition</span></span>
    
- <span data-ttu-id="fe42f-179">SQL Server 2012 SP2 및 CU2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="fe42f-179">SQL Server 2012 SP2 and CU2 Enterprise Edition</span></span>

> [!NOTE]
> <span data-ttu-id="fe42f-180">SQL Server 2019, 2017 및 2016은 비즈니스용 Skype Server 2019에서 지원 되는 유일한 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-180">SQL Server 2019, 2017, and 2016 are the only versions supported by Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="fe42f-181">SQL 2016, 2017 및 2019 Standard Edition에서는 always On 가용성 그룹이 지원 **되지** 않지만 항상 장애 조치 (Failover) 클러스터 인스턴스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-181">Always On Availability Groups is **not** supported in SQL 2016, 2017, and 2019 Standard Editions but you can use Always On Failover Cluster Instances.</span></span> <span data-ttu-id="fe42f-182">자세한 내용은 [SQL Server 2016의 버전 및 지원 되는 기능](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe42f-182">See [Editions and supported features of SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) to learn more.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fe42f-183">여러 AlwaysOn 가용성 그룹 인스턴스의 인스턴스 이름은 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-183">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
<span data-ttu-id="fe42f-184">AlwaysOn 가용성 그룹 배포 단계는 [비즈니스용 Skype 서버의 백 엔드 서버에서 AlwaysOn 가용성 그룹 배포](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe42f-184">For steps for deploying AlwaysOn Availability Groups, see [Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).</span></span>
  
## <a name="sql-server-failover-clustering"></a><span data-ttu-id="fe42f-185">SQL Server 장애 조치 클러스터링</span><span class="sxs-lookup"><span data-stu-id="fe42f-185">SQL Server Failover Clustering</span></span>

<span data-ttu-id="fe42f-186">비즈니스용 Skype 서버는 다음 데이터베이스 소프트웨어를 사용 하 여 SQL Server 장애 조치 (failover) 클러스터링을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-186">Skype for Business Server supports SQL Server failover clustering with the following database software:</span></span>
  
- <span data-ttu-id="fe42f-187">SQL Server 2019 (Enterprise Edition 및 Standard Edition 모두)</span><span class="sxs-lookup"><span data-stu-id="fe42f-187">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="fe42f-188">SQL Server 2017 (Enterprise Edition 및 Standard Edition 모두)</span><span class="sxs-lookup"><span data-stu-id="fe42f-188">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="fe42f-189">SQL Server 2016 (Enterprise Edition 및 Standard Edition 모두)</span><span class="sxs-lookup"><span data-stu-id="fe42f-189">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="fe42f-190">SQL Server 2014 (Enterprise Edition 및 Standard Edition 모두)</span><span class="sxs-lookup"><span data-stu-id="fe42f-190">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="fe42f-191">SQL Server 2012 SP2 및 CU2 (Enterprise Edition 및 Standard Edition 모두 해당)</span><span class="sxs-lookup"><span data-stu-id="fe42f-191">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>

<span data-ttu-id="fe42f-192">SQL 장애 조치 (failover) 클러스터링을 사용 하려면 먼저 프런트 엔드 풀을 배포 하기 전에 SQL Server 클러스터를 설정 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-192">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="fe42f-193">SQL Server 2012의 장애 조치 (failover) 클러스터링에 대 한 모범 사례 [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)및 설정 지침은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe42f-193">For best practices and setup instructions for failover clustering in SQL Server 2012, see [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="fe42f-194">SQL Server 2019, 2017 및 SQL Server 2016는 비즈니스용 Skype 서버 2019에서 지원 되는 유일한 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-194">SQL Server 2019, 2017, and SQL Server 2016 are the only versions supported by Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="fe42f-195">SQL 장애 조치 (failover) 클러스터링을 사용 하려면 먼저 프런트 엔드 풀을 배포 하기 전에 SQL Server 클러스터를 설정 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-195">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="fe42f-196">SQL Server 2014 및 2016의 장애 조치 (failover) 클러스터링에 대 한 모범 사례 [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)및 설정 지침은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe42f-196">For best practices and setup instructions for failover clustering in SQL Server 2014 and 2016, see [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx).</span></span> <span data-ttu-id="fe42f-197">SQL Server 2008의 장애 조치 (failover) [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)클러스터링에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe42f-197">For failover clustering in SQL Server 2008, see [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx).</span></span>
  
<span data-ttu-id="fe42f-198">SQL Server를 설치할 때 데이터베이스 및 로그 파일 위치의 위치를 관리 하려면 SQL Server Management Studio를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-198">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="fe42f-199">Sql server Management Studio는 SQL Server를 설치할 때 선택적 구성 요소로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe42f-199">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>
  
