---
title: 풀 장애 극복 및 복구
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
description: .
ms.openlocfilehash: 547a71f44fa81f9ba12a1c661465c7b8604b3fa1
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278678"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="262cb-103">비즈니스용 Skype 서버에서 풀 장애 조치(fail over) 및 장애 조치(fail back)</span><span class="sxs-lookup"><span data-stu-id="262cb-103">Failing over and failing back a pool in Skype for Business Server</span></span>

<span data-ttu-id="262cb-104">단일 Front-End 풀이 실패하여 복구해야 하는 경우 또는 재해가 발생한 풀이 다시 온라인 상태가 되어 배포를 일반 작업 상태로 복원해야 하는 경우 다음 절차를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="262cb-104">Use the following procedures if a single Front-End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="262cb-105">비즈니스용 Skype 페더ation 또는 XMPP 페더ation에 사용되는 에지 풀을 장애 조치(fail over)한 후 장애 조치(fail back)하거나, Front-End 풀과 연결된 에지 풀을 변경하는 방법을 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="262cb-105">Learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front-End pool.</span></span>

- [<span data-ttu-id="262cb-106">프런트 엔드 풀 장애 조치(fail over)</span><span class="sxs-lookup"><span data-stu-id="262cb-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="262cb-107">풀 장애 조치(fail back)</span><span class="sxs-lookup"><span data-stu-id="262cb-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="262cb-108">비즈니스용 Skype 서버 페더전에 사용되는 에지 풀 장애 조치(fail over)</span><span class="sxs-lookup"><span data-stu-id="262cb-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="262cb-109">비즈니스용 Skype 서버에서 XMPP 페더전에 사용되는 에지 풀 장애 조치(fail over)</span><span class="sxs-lookup"><span data-stu-id="262cb-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="262cb-110">비즈니스용 Skype 서버 페더ation 또는 XMPP 페더ation에 사용되는 에지 풀 장애 조치(fail back)</span><span class="sxs-lookup"><span data-stu-id="262cb-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="262cb-111">프런트 엔드 풀과 연결된 에지 풀 변경</span><span class="sxs-lookup"><span data-stu-id="262cb-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="262cb-112">Front-End 풀 장애 조치(fail over)</span><span class="sxs-lookup"><span data-stu-id="262cb-112">Fail over a Front-End pool</span></span>

<span data-ttu-id="262cb-113">Datacenter1에 Pool1이 포함되어 있으며 Pool1이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-113">Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="262cb-114">Datacenter2에 있는 Pool2로 장애 조치(fail over)합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-114">You're failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="262cb-115">풀 장애 조치(failover)에 대한 대부분의 작업에서는 필요한 경우 중앙 관리 저장소를 장애 조치(failover)합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-115">Most of the work for the pool failover involves failing over the Central Management store, if it's required.</span></span> <span data-ttu-id="262cb-116">풀의 사용자가 실패할 때 중앙 관리 저장소가 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-116">The Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="262cb-117">Front-End 풀이 실패하지만 해당 사이트의 에지 풀이 계속 실행 중인 경우 에지 풀이 실패한 풀을 다음 홉 풀로 사용하는지 여부를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-117">If a Front-End pool fails, but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="262cb-118">이 경우 오류가 있는 모든 풀에 장애 조치(fail over)하기 전에 다른 Front-End 풀을 사용하려면 에지 풀을 Front-End 합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-118">If it does, you must change the Edge pool to use a different Front-End pool before failing over the failed Front-End pool.</span></span> <span data-ttu-id="262cb-119">다음 홉 설정을 변경하는 방법은 에지가 에지 풀과 같은 사이트의 풀을 사용하는지 아니면 다른 사이트의 풀을 사용하는지에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="262cb-120">**에지 풀이 동일한 사이트에서 다음 홉 풀을 사용하게 설정**</span><span class="sxs-lookup"><span data-stu-id="262cb-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1. <span data-ttu-id="262cb-121">토폴로지 작성기에서 변경해야 하는 에지 풀을 마우스 오른쪽 단추로 클릭한 다음 속성 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="262cb-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and select **Edit Properties**.</span></span>

2. <span data-ttu-id="262cb-122">다음 **홉을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="262cb-122">Select **Next Hop**.</span></span> <span data-ttu-id="262cb-123">다음 **홉 풀:** 목록에서 다음 홉 풀로 사용할 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-123">From the **Next hop pool:** list, select the pool that will now serve as the next hop pool.</span></span>

3. <span data-ttu-id="262cb-124">**확인을** 선택한 다음 변경 내용을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-124">Select **OK**, and then publish the changes.</span></span>

<span data-ttu-id="262cb-125">**다른 사이트에서 다음 홉 풀을 사용하기 위해 에지 풀을 설정**</span><span class="sxs-lookup"><span data-stu-id="262cb-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1. <span data-ttu-id="262cb-126">비즈니스용 Skype 서버 관리 셸 창을 열고 다음 cmdlet을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>

        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="262cb-127">**재해에서 풀을 장애 조치(fail over)를 위해**</span><span class="sxs-lookup"><span data-stu-id="262cb-127">**To fail over a pool in a disaster**</span></span>

1. <span data-ttu-id="262cb-128">Pool2의 Front-End 서버에서 다음 cmdlet을 입력하여 중앙 관리 서버의 호스트 풀을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-128">Find the host pool for the Central Management Server by typing the following cmdlet on a Front-End server in Pool2:</span></span>

        Invoke-CsManagementServerFailover -Whatif

    <span data-ttu-id="262cb-129">이 cmdlet의 결과에는 중앙 관리 서버를 현재 호스트하는 풀이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="262cb-130">이 절차의 나머지부분에서 이 풀을 CMS 풀로 \_ 지명합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2. <span data-ttu-id="262cb-131">토폴로지 작성기에서 CMS 풀에서 실행되는 비즈니스용 Skype 서버 버전을 찾을 수 \_ 있습니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="262cb-132">비즈니스용 Skype 서버를 실행하는 경우 다음 cmdlet을 사용하여 풀 1의 백업 풀을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-132">If it's running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>

        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>

    <span data-ttu-id="262cb-133">백업 \_ 풀을 백업 풀로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-133">Let Backup\_Pool be the backup pool.</span></span>

3. <span data-ttu-id="262cb-134">다음 cmdlet을 통해 중앙 관리 저장소의 상태를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-134">Check the status of the Central Management store with the following cmdlet:</span></span>

        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 

    <span data-ttu-id="262cb-135">이 cmdlet은 ActiveMasterFQDN과 ActiveFileTransferAgents가 모두 CMS 풀의 FQDN을 포인터로 표시하는지 표시해야 \_ 합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="262cb-136">이 서버가 비어 있는 경우 중앙 관리 서버를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="262cb-137">중앙 관리 저장소를 사용할 수 없는 경우 또는 Pool1에서 중앙 관리 저장소가 실행 중이던 경우(즉, 오류가 있는 풀) 풀을 장애 조치(fail over)하기 전에 중앙 관리 서버를 장애 조치(fail over)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="262cb-138">비즈니스용 Skype 서버를 실행하는 풀에서 호스트된 중앙 관리 서버를 장애 조치(fail over)해야 하는 경우 이 절차의 5단계에서 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="262cb-139">중앙 관리 서버를 장애 조치(fail over)할 필요가 없는 경우 이 절차의 7단계로 건너뜁니 다.</span><span class="sxs-lookup"><span data-stu-id="262cb-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="262cb-140">비즈니스용 Skype 서버를 실행하는 풀에서 중앙 관리 저장소를 장애 조치(fail over)를 실행하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>

      - <span data-ttu-id="262cb-141">먼저 다음을 Back-End 백업 풀의 서버가 중앙 관리 저장소의 주 인스턴스를 실행하는지 \_ 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-141">First, check which Back-End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>

            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="262cb-142">백업 풀의 Back-End 기본 서버가 주 서버인 경우 \_ 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-142">If the primary Back-End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="262cb-143">백업 풀의 Back-End 서버가 주 서버인 경우 \_ 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-143">If the mirror Back-End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="262cb-144">중앙 관리 서버 장애 조치(failover)가 완료된지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="262cb-145">다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-145">Type the following command:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="262cb-146">ActiveMasterFQDN과 ActiveFileTransferAgents가 모두 백업 풀의 FQDN을 지정하는지 \_ 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="262cb-147">마지막으로 다음을 입력하여 모든 Front-End 서버의 복제본 상태를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-147">Finally, check the replica status for all Front-End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="262cb-148">모든 복제본의 값이 True인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="262cb-149">이 절차의 7단계로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="262cb-150">백업 풀의 백 엔드 서버에 중앙 관리 저장소를 \_ 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="262cb-151">먼저 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="262cb-152">백업 풀의 프런트 엔드 서버 중 하나에서 다음 명령을 실행하여 중앙 관리 저장소를 \_ 강제로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="262cb-153">이동이 완료되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="262cb-154">ActiveMasterFQDN과 ActiveFileTransferAgents가 모두 백업 풀의 FQDN을 지정하는지 \_ 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="262cb-155">다음을 입력하여 모든 프런트 엔드 서버의 복제 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="262cb-156">모든 복제본의 값이 True인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="262cb-157">백업 풀의 나머지 프런트 엔드 서버에 중앙 관리 서버 서비스를 \_ 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="262cb-158">이렇게 하여 이 절차의 앞부분에서 중앙 관리 저장소를 이동하게 할 때 사용한 명령을 제외한 모든 프런트 엔드 서버에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="262cb-159">비즈니스용 Skype 서버 관리 셸 창에서 다음 cmdlet을 실행하여 Pool1에서 Pool2로 사용자를 장애 조치(fail over)합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="262cb-160">중앙 관리 저장소 상태를 확인하기 위해 이 절차의 이전 부분에서 수행한 단계는 범용이 아니기 때문에 중앙 관리 저장소가 아직 완전히 장애 조치(fail over)되지 않았기 때문에 이 cmdlet이 실패할 가능성이 여전히 있습니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="262cb-161">이 경우 표시하는 오류 메시지에 따라 중앙 관리 저장소를 수정한 다음 이 cmdlet을 다시 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="262cb-p113">다음 오류 메시지가 표시되는 경우에는 이 사이트의 에지 풀이 다음 홉으로 다른 풀을 사용하도록 변경한 후에 풀을 장애 조치(failover)해야 합니다. 자세한 내용은 이 항목 첫 부분의 절차를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="262cb-p113">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="262cb-164">풀 장애 조치(fail back)</span><span class="sxs-lookup"><span data-stu-id="262cb-164">Fail back a pool</span></span>

<span data-ttu-id="262cb-165">재해가 발생한 풀을 다시 온라인으로 전환한 후(이 예의 Pool1) 다음 단계에 따라 배포를 일반 작업 상태로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="262cb-166">장애 조치(failback) 프로세스를 완료하는 데 몇 분 정도 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-166">The failback process takes several minute to complete.</span></span> <span data-ttu-id="262cb-167">참조를 위해 20,000명인 풀의 경우 최대 60분이 소요될 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-167">For reference, it's expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="262cb-168">다음 cmdlet을 사용해서 원래 Pool1에 있다가 Pool2로 장애 조치(Failover)되었던 사용자를 복구(Failback)합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="262cb-169">다른 단계는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-169">No other steps are necessary.</span></span> <span data-ttu-id="262cb-170">중앙 관리 서버를 실패한 경우 Pool2에 그대로 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="262cb-171">비즈니스용 Skype 서버 페더전에 사용되는 에지 풀 장애 조치(fail over)</span><span class="sxs-lookup"><span data-stu-id="262cb-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="262cb-172">비즈니스용 Skype 서버 페더전을 구성한 에지 풀이 다운되면 페더전이 작동하려면 다른 에지 풀을 사용하도록 페더전을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="262cb-173">프런트 엔드 서버에서 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="262cb-174">**에지 풀을** 확장한 다음 현재 페더에 대해 구성된 에지 서버 또는 에지 서버 풀을 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="262cb-175">**속성 편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="262cb-176">**일반** 아래의 **속성 편집** 에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="262cb-177">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-177">Select **OK**.</span></span>

3.  <span data-ttu-id="262cb-178">**에지 풀을** 확장한 다음 이제 페더전에 사용할 에지 서버 또는 에지 서버 풀을 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="262cb-179">**에지 속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="262cb-180">**일반** 아래의 **속성 편집** 에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="262cb-181">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-181">Select **OK**.</span></span>

5.  <span data-ttu-id="262cb-182">작업 **선택,** **토폴로지 선택,** **게시를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="262cb-182">Select **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="262cb-183">토폴로지 게시 메시지가 **표시될 때** 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="262cb-183">When prompted on **Publish the topology**, select **Next**.</span></span> <span data-ttu-id="262cb-184">게시가 완료되면 **마쳤습니다.**</span><span class="sxs-lookup"><span data-stu-id="262cb-184">When the Publish is finished, select **Finish**.</span></span>

6.  <span data-ttu-id="262cb-185">에지 서버에서 비즈니스용 Skype 서버 배포 마법사를 여십시오.</span><span class="sxs-lookup"><span data-stu-id="262cb-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="262cb-186">비즈니스용 **Skype 서버** 시스템 설치 또는 업데이트를 선택한 다음 비즈니스용 Skype 서버 구성 요소를 설치 또는 **제거합니다.**</span><span class="sxs-lookup"><span data-stu-id="262cb-186">Select **Install or Update Skype for Business Server System**, and then select **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="262cb-187">다시 **실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="262cb-187">Select **Run Again**.</span></span>

7.  <span data-ttu-id="262cb-188">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-188">Select **Next**.</span></span> <span data-ttu-id="262cb-189">요약 화면에 실행되는 작업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="262cb-190">배포가 완료되면 로그 보기를 선택하여 **사용** 가능한 로그 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-190">Once the deployment is done, select **View Log** to view available log files.</span></span> <span data-ttu-id="262cb-191">**완료를** 선택하여 배포를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-191">Select **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="262cb-192">실패한 에지 풀이 포함된 사이트에 아직 실행 중인 프런트 엔드 서버가 포함되어 있는 경우 계속 실행 중인 원격 사이트의 에지 풀을 사용하려면 이러한 Front-End 풀에서 웹 회의 서비스 및 A/V 회의 서비스를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front-End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="262cb-193">비즈니스용 Skype 서버에서 XMPP 페더전에 사용되는 에지 풀 장애 조치(fail over)</span><span class="sxs-lookup"><span data-stu-id="262cb-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="262cb-p123">조직에는 XMPP 페더레이션에 사용할 풀로 하나의 에지 풀이 지정됩니다. 이 풀이 다운되면 XMPP 페더레이션이 다시 작동하기 전에 다른 에지 풀을 사용하도록 XMPP 페더레이션을 장애 조치(failover)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-p123">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="262cb-196">에지 풀을 처음 설치하고 XMPP 페더레이션을 사용하도록 설정할 때는 XMPP 페더레이션용으로 모든 에지 풀에 대해 하나가 아니라 여러 개의 외부 DNS SRV 레코드를 설정하여 재해 복구 프로세스를 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="262cb-197">이러한 각 SRV 레코드에는 우선 순위를 다르게 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="262cb-198">모든 XMPP 페더레이션 트래픽은 우선 순위가 가장 높은 SRV 레코드가 포함된 풀을 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="262cb-199">다음 절차에서 EdgePool1은 원래 XMPP 페더럴을 호스팅한 풀이고 EdgePool2는 이제 XMPP 페더전을 호스팅할 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-199">In the following procedure, EdgePool1 is the pool, which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>
### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="262cb-200">XMPP 페더럴에 사용되는 에지 풀을 장애 조치(fail over)를 사용</span><span class="sxs-lookup"><span data-stu-id="262cb-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="262cb-201">아직 다른 에지 풀이 배포되지 않은 경우(현재 다운된 에지 풀 외에) 해당 풀을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-201">If you don’t already have another Edge pool deployed (besides the one that is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="262cb-202">이제 XMPP 페더레이션을 호스팅할 새로운 에지 풀(EdgePool2)의 각 에지 서버에서 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="262cb-203">다음 cmdlet을 실행하여 XMPP 페더레이션 경로를 다시 EdgePool2로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="262cb-204">이 예에서 Site2는 XMPP 페더레이션 경로를 이제 호스팅할 에지 풀이 포함된 사이트입니다. EdgeServer2.contoso.com은 이 풀에 있는 에지 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="262cb-205">외부 DNS 서버에서 XMPP 페더레이션용 DNS A 레코드를 EdgeServer2.contoso.com을 가리키도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="262cb-p125">이제 XMPP 페더레이션을 호스팅할 에지 풀로 확인되는 XMPP 페더레이션용 DNS SRV 레코드가 없으면 다음 예에 표시된 것처럼 지금 추가해야 합니다. 이 SRV 레코드는 포트 값 5269를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-p125">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="262cb-208">이제 XMPP 페더레이션을 호스팅할 에지 풀의 포트 5269가 외부적으로 열려 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="262cb-209">이제 XMPP 페더레이션을 호스팅할 에지 풀의 모든 에지 서버에서 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="262cb-210">비즈니스용 Skype 서버 페더ation 또는 XMPP 페더ation에 사용되는 에지 풀 장애 조치(fail back)</span><span class="sxs-lookup"><span data-stu-id="262cb-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="262cb-211">페더럴을 호스팅하는 데 사용된 오류가 발생한 에지 풀이 다시 온라인으로 되돌아온 후 이 절차에 따라 비즈니스용 Skype 서버 페더ation 경로 및/또는 XMPP 페더임 경로를 장애 복구(fail back)하여 복원된 에지 풀을 다시 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="262cb-212">이제 다시 사용할 수 있는 에지 풀에서 에지 서비스를 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="262cb-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="262cb-213">복원된 에지 서버를 사용하기 위해 비즈니스용 Skype 서버 페더ation 경로를 장애 복구(fail back)하려는 경우 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="262cb-214">프런트 엔드 서버에서 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="262cb-215">**에지 풀을** 확장한 다음 현재 페더에 대해 구성된 에지 서버 또는 에지 서버 풀을 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-215">Expand **Edge pools**, then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="262cb-216">**속성 편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="262cb-217">**일반** 아래의 **속성 편집** 에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="262cb-218">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-218">Select **OK**.</span></span>
    
      - <span data-ttu-id="262cb-219">**에지 풀을** 확장한 다음 다시 연결에 사용할 원래 에지 서버 또는 에지 서버 풀을 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-219">Expand **Edge pools**, then right-click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="262cb-220">**에지 속성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="262cb-221">**일반** 아래의 **속성 편집** 에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="262cb-222">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-222">Select **OK**.</span></span>
    
      - <span data-ttu-id="262cb-223">작업 **선택,** **토폴로지 선택,** **게시를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="262cb-223">Select **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="262cb-224">토폴로지 게시 메시지가 **표시될 때** 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="262cb-224">When prompted on **Publish the topology**, select **Next**.</span></span> <span data-ttu-id="262cb-225">게시가 완료되면 **마쳤습니다.**</span><span class="sxs-lookup"><span data-stu-id="262cb-225">When the Publish is finished, select **Finish**.</span></span>
    
      - <span data-ttu-id="262cb-226">에지 서버에서 비즈니스용 Skype 서버 배포 마법사를 여십시오.</span><span class="sxs-lookup"><span data-stu-id="262cb-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="262cb-227">비즈니스용 **Skype** 서버 시스템 설치 또는 업데이트, 설치 또는 비즈니스용 Skype 서버 구성 요소 **제거를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="262cb-227">Select **Install or Update Skype for Business Server System**, then select **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="262cb-228">다시 **실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="262cb-228">Select **Run Again**.</span></span>
    
      - <span data-ttu-id="262cb-229">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-229">Select **Next**.</span></span> <span data-ttu-id="262cb-230">요약 화면에 실행되는 작업이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="262cb-231">배포가 완료되면 로그 보기를 선택하여 **사용** 가능한 로그 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-231">Once the deployment is done, select **View Log** to view available log files.</span></span> <span data-ttu-id="262cb-232">**완료를** 선택하여 배포를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-232">Select **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="262cb-233">복원된 에지 서버를 사용하기 위해 XMPP 페더ation 경로를 장애 복구(fail back)하려는 경우 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="262cb-234">다음 cmdlet을 실행하여 이제 XMPP 페더럴을 호스팅할 에지 풀(이 예에서는 EdgeServer1)으로 XMPP 페더ation 경로를 다시 점화합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="262cb-235">이 예제에서 Site1은 이제 XMPP 페더럴 경로를 호스팅할 에지 풀이 포함된 사이트로, EdgeServer1.contoso.com 풀에 있는 에지 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="262cb-p133">이제 XMPP 페더레이션을 호스팅할 에지 풀로 확인되는 XMPP 페더레이션용 DNS SRV 레코드가 없으면 다음 예에 표시된 것처럼 지금 추가해야 합니다. 이 SRV 레코드는 포트 값 5269를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-p133">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="262cb-238">외부 DNS 서버에서 XMPP 페더레이션용 DNS A 레코드를 EdgeServer2.contoso.com을 가리키도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="262cb-239">이제 XMPP 페더레이션을 호스팅할 에지 풀의 포트 5269가 외부적으로 열려 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="262cb-240">프런트 엔드 풀이 실패하여 복원된 에지 풀이 포함된 사이트에서 실행된 상태로 유지된 경우 이러한 프런트 엔드 풀에서 웹 회의 서비스 및 A/V 회의 서비스를 업데이트하여 로컬 사이트의 에지 풀을 다시 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="262cb-241">오류가 발생한 에지 풀과 동일한 사이트의 프런트 엔드 풀도 실패한 경우 이제 Invoke-CsPoolFailback을 사용하여 프런트 엔드 풀을 장애 조치(failback)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="262cb-242">프런트 엔드 풀과 연결된 에지 풀 변경</span><span class="sxs-lookup"><span data-stu-id="262cb-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="262cb-243">에지 풀이 다운되었는데 동일 사이트의 프런트 엔드 풀은 계속 실행되는 경우에는 오류가 발생한 에지 풀을 복원하는 동안 다른 사이트의 에지 풀을 사용하도록 프런트 엔드 풀을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="262cb-244">토폴로지 작성기에서 변경해야 하는 프런트 엔드 풀의 이름을 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="262cb-245">풀을 마우스 오른쪽 단추로 클릭한 다음 속성 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="262cb-245">Right-click the pool, and then select **Edit Properties**.</span></span>

3.  <span data-ttu-id="262cb-246">**연결** 섹션의 **에지 풀 연결(미디어 구성 요소)** 에서 드롭다운 상자를 사용하여 이 프런트 엔드 풀과 연결할 에지 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="262cb-247">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="262cb-247">Select **OK**.</span></span>
