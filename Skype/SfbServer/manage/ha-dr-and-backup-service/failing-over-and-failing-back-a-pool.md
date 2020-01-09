---
title: 풀 장애 극복 및 복구
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: f2a1970df43aa2fb7becb03319ee6ff5934afe0a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991803"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="0bea2-103">비즈니스용 Skype 서버에서 풀 장애 조치 및 장애 복구</span><span class="sxs-lookup"><span data-stu-id="0bea2-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="0bea2-104">단일 프런트 엔드 풀에 실패 하 여 장애 조치를 수행 해야 하거나 재해가 발생 한 풀이 온라인 상태가 되는 경우 배포를 정상 작업 상태로 복원 해야 하는 경우 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="0bea2-105">또한 비즈니스용 Skype 페더레이션 또는 XMPP 페더레이션에 사용 되는 Edge 풀을 장애 조치 및 장애 복구 하는 방법과 프런트 엔드 풀에 연결 된 Edge 풀을 변경 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="0bea2-106">프런트 엔드 풀을 통해 장애 조치</span><span class="sxs-lookup"><span data-stu-id="0bea2-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="0bea2-107">풀 장애 복구</span><span class="sxs-lookup"><span data-stu-id="0bea2-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="0bea2-108">비즈니스용 Skype Server federation에 사용 되는 Edge 풀을 통해 장애 조치</span><span class="sxs-lookup"><span data-stu-id="0bea2-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="0bea2-109">비즈니스용 Skype 서버에서 XMPP 페더레이션에 사용 되는 Edge 풀을 통해 장애 조치</span><span class="sxs-lookup"><span data-stu-id="0bea2-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="0bea2-110">비즈니스용 Skype Server federation 또는 XMPP 페더레이션에 사용 되는 Edge 풀을 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="0bea2-111">프런트 엔드 풀에 연결 된 Edge 풀 변경</span><span class="sxs-lookup"><span data-stu-id="0bea2-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="0bea2-112">프런트 엔드 풀을 통해 장애 조치</span><span class="sxs-lookup"><span data-stu-id="0bea2-112">Fail over a Front End pool</span></span>

<span data-ttu-id="0bea2-113">이 절차에서는 Datacenter1에 Pool1이 포함 되어 있고 Pool1에 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="0bea2-114">Datacenter2에 위치한 Pool2로 장애 조치 (failover) 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="0bea2-115">필요한 경우 풀 장애 조치 (failover)에 대 한 대부분의 작업은 중앙 관리 저장소를 통해 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="0bea2-116">이는 풀의 사용자가 장애 조치를 할 때 중앙 관리 저장소가 작동 해야 하기 때문에 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="0bea2-117">또한 프런트 엔드 풀에는 실패 하지만 해당 사이트의 Edge 풀은 계속 실행 되는 경우에는 Edge 풀이 다음 홉 풀로 실패 한 풀을 사용 하는지 여부를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-117">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="0bea2-118">이 경우 실패 한 프런트 엔드 풀을 장애 조치 (failover) 하기 전에 다른 프런트 엔드 풀을 사용 하도록 Edge 풀을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-118">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="0bea2-119">다음 홉 설정을 변경 하는 방법은 Edge가 Edge 풀과 동일한 사이트의 풀을 사용할지 아니면 다른 사이트에 있는지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="0bea2-120">**같은 사이트에서 다음 홉 풀을 사용 하도록 Edge 풀 설정**</span><span class="sxs-lookup"><span data-stu-id="0bea2-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="0bea2-121">토폴로지 작성기를 열고 변경 해야 하는 Edge 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="0bea2-122">**다음 홉**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-122">Click **Next Hop**.</span></span> <span data-ttu-id="0bea2-123">**다음 홉 풀:** 목록에서 이제 다음 홉 풀 역할을 할 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-123">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="0bea2-124">**확인**을 클릭 한 다음 변경 내용을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="0bea2-125">**다른 사이트에서 다음 홉 풀을 사용 하도록 Edge 풀을 설정 하려면**</span><span class="sxs-lookup"><span data-stu-id="0bea2-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="0bea2-126">비즈니스용 Skype Server Management Shell 창을 열고 다음 cmdlet을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="0bea2-127">**재해에 따라 풀을 장애 조치**</span><span class="sxs-lookup"><span data-stu-id="0bea2-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="0bea2-128">Pool2의 프런트 엔드 서버에 다음 cmdlet을 입력 하 여 중앙 관리 서버의 호스트인 풀을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="0bea2-129">이 cmdlet의 결과에는 현재 중앙 관리 서버를 호스트 하는 풀이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="0bea2-130">이 절차의 나머지 부분에서는이 풀을 CMS\_풀 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="0bea2-131">토폴로지 작성기를 사용 하 여 CMS\_풀에서 실행 되는 비즈니스용 Skype 서버의 버전을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="0bea2-132">비즈니스용 Skype 서버를 실행 하는 경우 다음 cmdlet을 사용 하 여 풀 1의 백업 풀을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="0bea2-133">\_백업 풀을 백업 풀로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="0bea2-134">다음 cmdlet을 사용 하 여 중앙 관리 저장소의 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="0bea2-135">이 cmdlet은 ActiveMasterFQDN 및 ActiveFileTransferAgents 모두 CMS\_풀의 FQDN을 가리키지만을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="0bea2-136">비어 있는 경우 중앙 관리 서버를 사용할 수 없으며 장애 조치를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="0bea2-137">중앙 관리 저장소를 사용할 수 없거나 중앙 관리 저장소가 Pool1 (즉, 실패 한 풀)에서 실행 되는 경우에는 풀을 통해 실패 하기 전에 중앙 관리 서버를 장애 조치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="0bea2-138">비즈니스용 Skype Server를 실행 하는 풀에 호스트 된 중앙 관리 서버를 장애 조치 해야 하는 경우이 절차의 5 단계에서 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="0bea2-139">중앙 관리 서버를 장애 조치할 필요가 없는 경우에는이 절차의 7 단계로 건너뛰십시오.</span><span class="sxs-lookup"><span data-stu-id="0bea2-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="0bea2-140">비즈니스용 Skype Server를 실행 하는 풀의 중앙 관리 저장소를 장애 조치 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="0bea2-141">먼저 다음을 입력 하 여 백업\_풀의 백 엔드 서버가 중앙 관리 저장소의 principal 인스턴스를 실행 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="0bea2-142">백업\_풀의 주 백 엔드 서버가 주 서버 이면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="0bea2-143">백업\_풀의 미러 백 엔드 서버가 주 서버 이면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="0bea2-144">중앙 관리 서버 장애 조치 (failover)가 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="0bea2-145">다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="0bea2-146">ActiveMasterFQDN와 ActiveFileTransferAgents 모두 백업\_풀의 FQDN을 가리키고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="0bea2-147">마지막으로, 다음을 입력 하 여 모든 프런트 엔드 서버의 복제 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="0bea2-148">모든 복제본에 True 값이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="0bea2-149">이 절차의 7 단계로 건너뛰십시오.</span><span class="sxs-lookup"><span data-stu-id="0bea2-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="0bea2-150">백업\_풀의 백 엔드 서버에 중앙 관리 저장소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="0bea2-151">먼저 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="0bea2-152">백업\_풀의 프런트 엔드 서버 중 하나에서 다음 명령을 실행 하 여 중앙 관리 저장소의 이동을 강제로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="0bea2-153">이동이 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="0bea2-154">ActiveMasterFQDN와 ActiveFileTransferAgents 모두 백업\_풀의 FQDN을 가리키고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="0bea2-155">다음을 입력 하 여 모든 프런트 엔드 서버의 복제 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="0bea2-156">모든 복제본에 True 값이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="0bea2-157">백업\_풀의 프런트 엔드 서버 나머지 부분에 중앙 관리 서버 서비스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="0bea2-158">이렇게 하려면이 절차의 앞부분에서 중앙 관리 저장소를 강제로 이동할 때 사용한 것을 제외 하 고 모든 프런트 엔드 서버에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="0bea2-159">비즈니스용 Skype 서버 관리 셸 창에서 다음 cmdlet을 실행 하 여 Pool1에서 Pool2로 사용자를 장애 조치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="0bea2-160">중앙 관리 저장소 상태를 검사 하는이 절차의 이전 부분에서 수행 된 단계는 유니버설 하지 않기 때문에 중앙 관리 저장소가 아직 완전히 장애 조치 되지 않아이 cmdlet이 실패할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="0bea2-161">이 경우 표시 되는 오류 메시지를 기반으로 중앙 관리 저장소를 수정한 다음이 cmdlet을 다시 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="0bea2-162">다음 오류 메시지가 표시 되는 경우 풀을 장애 인하기 전에 다음 홉으로 다른 풀을 사용 하도록이 사이트에서 Edge 풀을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-162">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="0bea2-163">자세한 내용은이 항목의 시작 부분에 나오는 절차를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bea2-163">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="0bea2-164">풀 장애 복구</span><span class="sxs-lookup"><span data-stu-id="0bea2-164">Fail back a pool</span></span>

<span data-ttu-id="0bea2-165">재해가 발생 한 풀이 온라인 상태가 된 후 (즉,이 예제에서 Pool1) 다음 단계를 수행 하 여 배포를 정상 작업 상태로 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="0bea2-166">장애 복구 프로세스가 완료 되기까지 몇 분이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-166">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="0bea2-167">참조용으로 2만 사용자 풀에 대해 최대 60 분이 소요 될 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-167">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="0bea2-168">Pool1에서 원래 홈 이었던 사용자와 다음 cmdlet을 입력 하 여 Pool2에 장애 조치 (Fail over)를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="0bea2-169">다른 단계는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-169">No other steps are necessary.</span></span> <span data-ttu-id="0bea2-170">중앙 관리 서버를 장애 조치 (Pool2) 한 경우에는 그대로 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="0bea2-171">비즈니스용 Skype Server federation에 사용 되는 Edge 풀을 통해 장애 조치</span><span class="sxs-lookup"><span data-stu-id="0bea2-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="0bea2-172">비즈니스용 Skype 서버 페더레이션이 구성 된 Edge 풀을 사용할 수 없는 경우 페더레이션에서 다른 Edge 풀을 사용 하도록 페더레이션을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="0bea2-173">프런트 엔드 서버에서 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="0bea2-174">**Edge 풀**을 확장 한 다음 현재 페더레이션에 대해 구성 되어 있는 edge 서버 또는 edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="0bea2-175">**속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="0bea2-176">**일반**아래의 **속성 편집** 에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 을 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="0bea2-177">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-177">Click **OK**.</span></span>

3.  <span data-ttu-id="0bea2-178">**Edge 풀**을 확장 한 다음 현재 페더레이션에 사용할 edge 서버 또는 edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="0bea2-179">**속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="0bea2-180">**일반**아래에서 **속성 편집** 에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="0bea2-181">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-181">Click **OK**.</span></span>

5.  <span data-ttu-id="0bea2-182">**작업**을 클릭 하 고 **토폴로지**를 선택한 다음 **게시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-182">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="0bea2-183">**토폴로지를 게시할**것인지 묻는 메시지가 표시 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-183">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="0bea2-184">게시가 완료 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-184">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="0bea2-185">Edge 서버에서 비즈니스용 Skype 서버 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="0bea2-186">**비즈니스용 Skype 서버 시스템 설치 또는 업데이트**를 클릭 한 다음 설정을 클릭 **하거나 비즈니스용 Skype 서버 구성 요소를 제거**합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="0bea2-187">**다시 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="0bea2-188">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-188">Click **Next**.</span></span> <span data-ttu-id="0bea2-189">요약 화면에 실행 되는 작업이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="0bea2-190">배포가 완료 되 면 **로그 보기** 를 클릭 하 여 사용 가능한 로그 파일을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="0bea2-191">**마침을** 클릭 하 여 배포를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="0bea2-192">실행 중인 프런트 엔드 서버가 실패 한 Edge 풀을 포함 하는 사이트에 포함 되어 있는 경우, 현재 실행 중인 원격 사이트의 Edge 풀을 사용 하도록 이러한 프런트 엔드 풀의 웹 회의 서비스와 A/V 회의 서비스를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="0bea2-193">비즈니스용 Skype 서버에서 XMPP 페더레이션에 사용 되는 Edge 풀을 통해 장애 조치</span><span class="sxs-lookup"><span data-stu-id="0bea2-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="0bea2-194">조직에서 XMPP 페더레이션에 사용할 풀로 지정 된 하나의 Edge 풀이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-194">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="0bea2-195">이 풀이 중단 되 면 xmpp federation에서 다시 작동할 수 있도록 XMPP federation를 장애 조치 하 여 다른 Edge 풀을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-195">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="0bea2-196">Edge 풀을 처음 설치 하 고 XMPP 페더레이션을 사용 하면 XMPP 페더레이션의 모든 Edge 풀에 대해 외부 DNS SRV 레코드를 하나만 설정 하는 것이 아니라 장애 복구 프로세스를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="0bea2-197">이러한 각각의 SRV 레코드에는 다른 우선 순위가 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="0bea2-198">모든 XMPP 페더레이션 트래픽은 우선 순위가 가장 높은 SRV 레코드를 사용 하 여 풀을 거칩니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="0bea2-199">다음 절차에서는 EdgePool1가 원래 XMPP 페더레이션을 호스팅하는 풀 이며, EdgePool2는 이제 XMPP federation를 호스트 하는 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="0bea2-200">XMPP 페더레이션에 사용 되는 Edge 풀을 장애 조치</span><span class="sxs-lookup"><span data-stu-id="0bea2-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="0bea2-201">현재 사용 중인 다른 Edge 풀을 아직 배포 하지 않은 경우에는 해당 풀을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="0bea2-202">이제 XMPP 페더레이션 (EdgePool2)을 호스트 하는 새 Edge 풀의 각 Edge 서버에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="0bea2-203">XMPP 페더레이션 경로를 EdgePool2로 다시 가리키도록 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="0bea2-204">이 예제에서 Site2는 이제 XMPP 페더레이션 경로를 호스팅하는 Edge 풀을 포함 하는 사이트 이며, EdgeServer2.contoso.com는 해당 풀에 있는 Edge 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="0bea2-205">외부 DNS 서버에서 XMPP 페더레이션의 DNS A 레코드를 EdgeServer2.contoso.com를 가리키도록 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="0bea2-206">이제 XMPP 페더레이션을 호스트 하는 Edge 풀로 확인 되는 DNS SRV 레코드가 아직 없는 경우 다음 예제와 같이 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-206">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="0bea2-207">이 SRV 레코드의 포트 값은 5269 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-207">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="0bea2-208">이제 XMPP federation host에 호스트 되는 Edge 풀에 포트 5269이 외부적으로 열려 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="0bea2-209">이제 Edge 풀에서 XMPP 페더레이션을 호스트 하는 모든 Edge 서버에서 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="0bea2-210">비즈니스용 Skype Server federation 또는 XMPP 페더레이션에 사용 되는 Edge 풀을 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="0bea2-211">페더레이션을 호스트 하는 데 사용 된 실패 한도 풀이 온라인 상태가 되 면이 절차를 사용 하 여 비즈니스용 Skype Server federation route 및/또는 XMPP 페더레이션 경로를 다시 실행 하 여 복원 된이 Edge 풀을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="0bea2-212">지금 다시 사용할 수 있는 Edge 풀에서 Edge 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="0bea2-213">복원 된 Edge 서버를 사용 하기 위해 비즈니스용 Skype 서버 페더레이션 경로를 장애 복구 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="0bea2-214">프런트 엔드 서버에서 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="0bea2-215">**Edge 풀**을 확장 한 다음, 현재 페더레이션에 대해 구성 된 edge 서버 또는 edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-215">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="0bea2-216">**속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="0bea2-217">**일반**아래의 **속성 편집** 에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 을 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="0bea2-218">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-218">Click **OK**.</span></span>
    
      - <span data-ttu-id="0bea2-219">**Edge 풀**을 확장 한 다음 페더레이션에 사용할 원본 edge 서버 또는 edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="0bea2-220">**속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="0bea2-221">**일반**아래에서 **속성 편집** 에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="0bea2-222">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-222">Click **OK**.</span></span>
    
      - <span data-ttu-id="0bea2-223">**작업**을 클릭 하 고 **토폴로지**를 선택한 다음 **게시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-223">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="0bea2-224">**토폴로지를 게시할**것인지 묻는 메시지가 표시 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-224">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="0bea2-225">게시가 완료 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-225">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="0bea2-226">Edge 서버에서 비즈니스용 Skype 서버 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="0bea2-227">**비즈니스용 Skype 서버 시스템 설치 또는 업데이트**를 클릭 한 다음 **설정 또는 비즈니스용 Skype 서버 구성 요소 제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="0bea2-228">**다시 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="0bea2-229">**다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-229">Click **Next**.</span></span> <span data-ttu-id="0bea2-230">요약 화면에 실행 되는 작업이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="0bea2-231">배포가 완료 되 면 **로그 보기** 를 클릭 하 여 사용 가능한 로그 파일을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="0bea2-232">**마침을** 클릭 하 여 배포를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="0bea2-233">XMPP 페더레이션 경로를 장애 복구 하 여 복원 된 Edge 서버를 사용 하려는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="0bea2-234">다음 cmdlet을 실행 하 여 XMPP 페더레이션 경로를 다시 지정 합니다. 이제 XMPP 페더레이션 (이 예제에서는 EdgeServer1)을 호스트 하는 Edge 풀을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="0bea2-235">이 예제에서 Site1는 이제 XMPP 페더레이션 경로를 호스팅하는 Edge 풀을 포함 하는 사이트 이며, EdgeServer1.contoso.com는 해당 풀에 있는 Edge 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="0bea2-236">이제 XMPP 페더레이션을 호스트 하는 Edge 풀로 확인 되는 DNS SRV 레코드가 아직 없는 경우 다음 예제와 같이 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-236">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="0bea2-237">이 SRV 레코드의 포트 값은 5269 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-237">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="0bea2-238">외부 DNS 서버에서 XMPP 페더레이션의 DNS A 레코드를 EdgeServer2.contoso.com를 가리키도록 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="0bea2-239">이제 XMPP federation host에 호스트 되는 Edge 풀에 포트 5269이 외부적으로 열려 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="0bea2-240">실패 한 Edge 풀을 포함 하는 사이트에서 프런트 엔드 풀이 계속 실행 되 고 있는 경우에는 이러한 프런트 엔드 풀의 웹 회의 서비스와 A/V 회의 서비스를 업데이트 하 여 로컬 사이트의 Edge 풀을 다시 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="0bea2-241">실패 한 Edge 풀과 동일한 사이트의 프런트 엔드 풀에도 실패 한 경우에는 Invoke – CsPoolFailback를 사용 하 여 프런트 엔드 풀을 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="0bea2-242">프런트 엔드 풀에 연결 된 Edge 풀 변경</span><span class="sxs-lookup"><span data-stu-id="0bea2-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="0bea2-243">Edge 풀이 작동 하지 않지만 같은 사이트의 프런트 엔드 풀은 계속 실행 되는 경우에는 프런트 엔드 풀을 설정 하 여 실패 한도 풀이 복원 될 때까지 다른 사이트의 Edge 풀을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="0bea2-244">토폴로지 작성기에서 변경 해야 하는 프런트 엔드 풀의 이름으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="0bea2-245">풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="0bea2-246">**연결** 섹션의 **Edge 풀 연결 (미디어 구성 요소)** 에서 드롭다운 상자를 사용 하 여이 프론트 엔드 풀을 연결할 edge 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="0bea2-247">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0bea2-247">Click **OK**.</span></span>
