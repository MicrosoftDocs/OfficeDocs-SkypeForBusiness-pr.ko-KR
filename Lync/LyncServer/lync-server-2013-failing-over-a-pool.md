---
title: 'Lync Server 2013: 풀을 장애 조치 (failover)'
description: 'Lync Server 2013: 풀을 장애 조치 (failover) 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 819137c1277c5058f4e5d36ef5dbe71e672e8641
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554984"
---
# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="e0c89-103">Lync Server 2013에서 풀 장애 조치 (failover)</span><span class="sxs-lookup"><span data-stu-id="e0c89-103">Failing over a pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0c89-104">_**마지막으로 수정 된 항목:** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="e0c89-104">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="e0c89-p101">단일 프런트 엔드 풀에 오류가 발생하여 장애 조치(failover)를 수행해야 하는 경우 다음 절차를 따릅니다. 이 절차에서 Datacenter1은 Pool1을 포함하며 Pool1에서 오류가 발생한 상태입니다. Pool1을 Datacenter2에 있는 Pool2로 장애 조치(failover)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-p101">If a single Front End pool has failed and needs to be failed over, use the following procedure. In this procedure, Datacenter1 contains Pool1, and Pool1 has failed. You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="e0c89-108">풀 장애 조치 (failover)를 수행 하는 대부분의 작업은 중앙 관리 저장소 (필요한 경우)를 통과 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-108">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="e0c89-109">이는 해당 풀의 사용자가 장애 조치 (failover) 될 때 중앙 관리 저장소가 정상적으로 작동 하기 때문에 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-109">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="e0c89-p103">또한 프런트 엔드 풀에 오류가 발생했는데 해당 사이트의 에지 풀은 계속 실행되는 경우에는 에지 풀이 오류가 발생한 풀을 다음 홉 풀로 사용하는지 여부를 확인해야 합니다. 오류가 발생한 풀이 다음 홉 풀로 사용되는 경우에는 해당 프런트 엔드 풀을 장애 조치(failover)하기 전에 다른 프런트 엔드 풀을 사용하도록 에지 풀을 변경해야 합니다. 다음 홉 설정을 변경하는 방법은 에지가 에지 풀과 같은 사이트의 풀을 사용하는지 아니면 다른 사이트의 풀을 사용하는지에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-p103">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="e0c89-113">**에지 풀이 같은 사이트의 다음 홉 풀을 사용하도록 설정하려면**</span><span class="sxs-lookup"><span data-stu-id="e0c89-113">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="e0c89-114">토폴로지 작성기를 열고 변경 해야 하는에 지 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-114">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="e0c89-p104">**다음 홉**을 클릭합니다. **다음 홉 풀:** 목록에서 다음 홉 풀로 사용할 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-p104">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="e0c89-117">**확인**을 클릭하고 변경 내용을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-117">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="e0c89-118">**에지 풀이 다른 사이트의 다음 홉 풀을 사용하도록 설정하려면**</span><span class="sxs-lookup"><span data-stu-id="e0c89-118">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="e0c89-119">Lync Server 관리 셸 창을 열고 다음 cmdlet을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-119">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="e0c89-120">**재해 발생 시 풀을 장애 조치(failover)하려면**</span><span class="sxs-lookup"><span data-stu-id="e0c89-120">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="e0c89-121">호스트인의 프런트 엔드 서버에 다음 cmdlet을 입력 하 여 중앙 관리 서버에 대 한 호스트인 풀을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-121">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="e0c89-122">이 cmdlet의 결과는 현재 중앙 관리 서버를 호스트 하는 풀을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-122">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="e0c89-123">이 절차의 나머지 부분에서이 풀을 CMS 풀 이라고 합니다 \_ .</span><span class="sxs-lookup"><span data-stu-id="e0c89-123">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="e0c89-124">토폴로지 작성기를 사용 하 여 CMS 풀에서 실행 되는 Lync Server의 버전을 찾습니다 \_ .</span><span class="sxs-lookup"><span data-stu-id="e0c89-124">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="e0c89-125">Lync Server 2013를 실행 하는 경우 다음 cmdlet을 사용 하 여 풀 1의 백업 풀을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-125">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="e0c89-126">백업 풀 \_ 을 백업 풀로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-126">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="e0c89-127">다음 cmdlet을 사용 하 여 중앙 관리 저장소의 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-127">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="e0c89-128">이 cmdlet은 ActiveMasterFQDN 및 Activefiletransferagents가 둘 다 CMS 풀의 FQDN을 가리키고 있음을 보여 줍니다 \_ .</span><span class="sxs-lookup"><span data-stu-id="e0c89-128">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="e0c89-129">비어 있는 경우에는 중앙 관리 서버를 사용할 수 없으며 장애 조치 (failover)를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-129">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="e0c89-130">중앙 관리 저장소를 사용할 수 없거나 중앙 관리 저장소가 Pool1) (즉, 오류가 발생 한 풀)에서 실행 되 고 있는 경우에는 해당 풀을 장애 조치 (failover) 하기 전에 중앙 관리 서버를 장애 조치 (failover) 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-130">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="e0c89-131">Lync Server 2013을 실행 하는 풀에 호스트 된 중앙 관리 서버를 장애 조치 (failover) 해야 하는 경우에는이 절차의 5 단계에서 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="e0c89-132">Lync Server 2010을 실행 하는 풀에 호스트 된 중앙 관리 서버를 장애 조치 (failover) 해야 하는 경우이 절차의 6 단계에 나오는 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-132">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="e0c89-133">중앙 관리 서버를 장애 조치할 필요가 없으면이 절차의 7 단계로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-133">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="e0c89-134">Lync Server 2013을 실행 하는 풀에서 중앙 관리 저장소를 장애 조치 (failover) 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-134">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="e0c89-135">먼저 \_ 다음을 입력 하 여 백업 풀의 백 엔드 서버가 중앙 관리 저장소의 보안 주체 인스턴스를 실행 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-135">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="e0c89-136">백업 풀의 주 백 엔드 서버가 주 서버인 경우 \_ 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-136">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="e0c89-137">백업 풀의 미러 백 엔드 서버가 \_ 보안 주체 인 경우 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-137">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="e0c89-138">중앙 관리 서버 장애 조치 (failover)가 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-138">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="e0c89-139">다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-139">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="e0c89-140">ActiveMasterFQDN 및 Activefiletransferagents가 모두 백업 풀의 FQDN을 가리키는지 확인 \_ 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-140">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="e0c89-141">마지막으로 다음을 입력 하 여 모든 프런트 엔드 서버의 복제 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-141">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="e0c89-142">모든 복제본의 값이 True인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-142">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="e0c89-143">이 절차의 7단계로 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-143">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="e0c89-144">백업 풀의 백 엔드 서버에 중앙 관리 저장소를 설치 \_ 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-144">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="e0c89-145">먼저 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-145">First, run the following command:</span></span>
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="e0c89-146">백업 풀의 프런트 엔드 서버 중 하나에서 다음 명령을 실행 \_ 하 여 중앙 관리 저장소를 강제로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-146">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="e0c89-147">이동이 완료되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-147">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="e0c89-148">ActiveMasterFQDN 및 Activefiletransferagents가 모두 백업 풀의 FQDN을 가리키는지 확인 \_ 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-148">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="e0c89-149">다음을 입력하여 모든 프런트 엔드 서버의 복제 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-149">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="e0c89-150">모든 복제본의 값이 True인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-150">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="e0c89-151">백업 풀의 나머지 프런트 엔드 서버에 중앙 관리 서버 서비스를 설치 \_ 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-151">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="e0c89-152">이렇게 하려면이 절차의 앞부분에서 중앙 관리 저장소를 이동할 때 사용한 것을 제외 하 고 모든 프런트 엔드 서버에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-152">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="e0c89-153">Lync Server 관리 셸 창에서 다음 cmdlet을 실행 하 여 Pool1)에서 호스트인로 사용자를 장애 조치 (failover) 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-153">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="e0c89-154">이 절차의 이전 부분에서 설명한 것 처럼 중앙 관리 저장소 상태를 확인 하기 위해 수행 하는 단계는 universal이 아니므로 중앙 관리 저장소에서 아직 완전히 장애 조치 (failover) 되지 않았으므로이 cmdlet이 실패할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-154">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="e0c89-155">이 경우 표시 되는 오류 메시지를 기반으로 중앙 관리 저장소를 수정한 다음이 cmdlet을 다시 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c89-155">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="e0c89-p112">다음 오류 메시지가 표시되는 경우에는 이 사이트의 에지 풀이 다음 홉으로 다른 풀을 사용하도록 변경한 후에 풀을 장애 조치(failover)해야 합니다. 자세한 내용은 이 항목 첫 부분의 절차를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0c89-p112">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

