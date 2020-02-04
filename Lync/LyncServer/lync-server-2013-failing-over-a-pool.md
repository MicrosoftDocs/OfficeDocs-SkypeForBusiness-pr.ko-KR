---
title: 'Lync Server 2013: 풀 장애 조치(failover)'
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
ms.openlocfilehash: ea66ae4a224d78e40a9fdb9de867d4738a5e3714
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="e2107-102">Lync Server 2013 에서 풀 장애 조치(failover)</span><span class="sxs-lookup"><span data-stu-id="e2107-102">Failing over a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2107-103">_**마지막으로 수정한 주제:** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="e2107-103">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="e2107-104">단일 프런트 엔드 풀에 오류가 발생 하 여 장애 조치 해야 하는 경우 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-104">If a single Front End pool has failed and needs to be failed over, use the following procedure.</span></span> <span data-ttu-id="e2107-105">이 절차에서는 Datacenter1에 Pool1이 포함 되어 있고 Pool1에 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-105">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="e2107-106">Datacenter2에 위치한 Pool2로 장애 조치 (failover) 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-106">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="e2107-107">필요한 경우 풀 장애 조치 (failover)에 대 한 대부분의 작업은 중앙 관리 저장소를 통해 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-107">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="e2107-108">이는 풀의 사용자가 장애 조치를 할 때 중앙 관리 저장소가 작동 해야 하기 때문에 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-108">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="e2107-109">또한 프런트 엔드 풀에는 실패 하지만 해당 사이트의 Edge 풀은 계속 실행 되는 경우에는 Edge 풀이 다음 홉 풀로 실패 한 풀을 사용 하는지 여부를 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-109">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="e2107-110">이 경우 실패 한 프런트 엔드 풀을 장애 조치 (failover) 하기 전에 다른 프런트 엔드 풀을 사용 하도록 Edge 풀을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-110">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="e2107-111">다음 홉 설정을 변경 하는 방법은 Edge가 Edge 풀과 동일한 사이트의 풀을 사용할지 아니면 다른 사이트에 있는지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-111">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="e2107-112">**같은 사이트에서 다음 홉 풀을 사용 하도록 Edge 풀 설정**</span><span class="sxs-lookup"><span data-stu-id="e2107-112">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="e2107-113">토폴로지 작성기를 열고 변경 해야 하는 Edge 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-113">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="e2107-114">**다음 홉**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-114">Click **Next Hop**.</span></span> <span data-ttu-id="e2107-115">**다음 홉 풀:** 목록에서 이제 다음 홉 풀 역할을 할 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-115">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="e2107-116">**확인**을 클릭 한 다음 변경 내용을 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-116">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="e2107-117">**다른 사이트에서 다음 홉 풀을 사용 하도록 Edge 풀을 설정 하려면**</span><span class="sxs-lookup"><span data-stu-id="e2107-117">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="e2107-118">Lync Server Management Shell 창을 열고 다음 cmdlet을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-118">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="e2107-119">**재해에 따라 풀을 장애 조치**</span><span class="sxs-lookup"><span data-stu-id="e2107-119">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="e2107-120">Pool2의 프런트 엔드 서버에 다음 cmdlet을 입력 하 여 중앙 관리 서버의 호스트인 풀을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-120">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="e2107-121">이 cmdlet의 결과에는 현재 중앙 관리 서버를 호스트 하는 풀이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-121">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="e2107-122">이 절차의 나머지 부분에서는이 풀을 CMS\_풀 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-122">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="e2107-123">토폴로지 작성기를 사용 하 여 CMS\_풀에서 실행 되는 Lync Server 버전을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-123">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="e2107-124">Lync Server 2013을 실행 하는 경우 다음 cmdlet을 사용 하 여 풀 1의 백업 풀을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-124">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="e2107-125">\_백업 풀을 백업 풀로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-125">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="e2107-126">다음 cmdlet을 사용 하 여 중앙 관리 저장소의 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-126">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="e2107-127">이 cmdlet은 ActiveMasterFQDN 및 ActiveFileTransferAgents 모두 CMS\_풀의 FQDN을 가리키지만을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-127">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="e2107-128">비어 있는 경우 중앙 관리 서버를 사용할 수 없으며 장애 조치를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-128">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="e2107-129">중앙 관리 저장소를 사용할 수 없거나 중앙 관리 저장소가 Pool1 (즉, 실패 한 풀)에서 실행 되는 경우에는 풀을 통해 실패 하기 전에 중앙 관리 서버를 장애 조치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-129">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="e2107-130">Lync Server 2013를 실행 하는 풀에 호스트 된 중앙 관리 서버를 장애 조치 해야 하는 경우이 절차의 5 단계에서 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-130">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="e2107-131">Lync Server 2010를 실행 하는 풀에 호스트 된 중앙 관리 서버를 장애 조치 해야 하는 경우이 절차의 6 단계에서 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="e2107-132">중앙 관리 서버를 장애 조치할 필요가 없는 경우에는이 절차의 7 단계로 건너뛰십시오.</span><span class="sxs-lookup"><span data-stu-id="e2107-132">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="e2107-133">Lync Server 2013를 실행 하는 풀의 중앙 관리 저장소를 장애 조치 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-133">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="e2107-134">먼저 다음을 입력 하 여 백업\_풀의 백 엔드 서버가 중앙 관리 저장소의 principal 인스턴스를 실행 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-134">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="e2107-135">백업\_풀의 주 백 엔드 서버가 주 서버 이면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-135">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="e2107-136">백업\_풀의 미러 백 엔드 서버가 주 서버 이면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-136">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="e2107-137">중앙 관리 서버 장애 조치 (failover)가 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-137">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="e2107-138">다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-138">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="e2107-139">ActiveMasterFQDN와 ActiveFileTransferAgents 모두 백업\_풀의 FQDN을 가리키고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-139">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="e2107-140">마지막으로, 다음을 입력 하 여 모든 프런트 엔드 서버의 복제 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-140">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="e2107-141">모든 복제본에 True 값이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-141">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="e2107-142">이 절차의 7 단계로 건너뛰십시오.</span><span class="sxs-lookup"><span data-stu-id="e2107-142">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="e2107-143">백업\_풀의 백 엔드 서버에 중앙 관리 저장소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-143">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="e2107-144">먼저 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-144">First, run the following command:</span></span>
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="e2107-145">백업\_풀의 프런트 엔드 서버 중 하나에서 다음 명령을 실행 하 여 중앙 관리 저장소의 이동을 강제로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-145">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="e2107-146">이동이 완료 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-146">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="e2107-147">ActiveMasterFQDN와 ActiveFileTransferAgents 모두 백업\_풀의 FQDN을 가리키고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-147">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="e2107-148">다음을 입력 하 여 모든 프런트 엔드 서버의 복제 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-148">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="e2107-149">모든 복제본에 True 값이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-149">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="e2107-150">백업\_풀의 프런트 엔드 서버 나머지 부분에 중앙 관리 서버 서비스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-150">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="e2107-151">이렇게 하려면이 절차의 앞부분에서 중앙 관리 저장소를 강제로 이동할 때 사용한 것을 제외 하 고 모든 프런트 엔드 서버에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-151">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="e2107-152">Lync Server Management Shell 창에서 다음 cmdlet을 실행 하 여 Pool1에서 Pool2로 사용자를 장애 조치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-152">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="e2107-153">중앙 관리 저장소 상태를 검사 하는이 절차의 이전 부분에서 수행 된 단계는 유니버설 하지 않기 때문에 중앙 관리 저장소가 아직 완전히 장애 조치 되지 않아이 cmdlet이 실패할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-153">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="e2107-154">이 경우 표시 되는 오류 메시지를 기반으로 중앙 관리 저장소를 수정한 다음이 cmdlet을 다시 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-154">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="e2107-155">다음 오류 메시지가 표시 되는 경우 풀을 장애 인하기 전에 다음 홉으로 다른 풀을 사용 하도록이 사이트에서 Edge 풀을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2107-155">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="e2107-156">자세한 내용은이 항목의 시작 부분에 나오는 절차를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e2107-156">For details, see the procedures at the beginning of this topic.</span></span>
    
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

