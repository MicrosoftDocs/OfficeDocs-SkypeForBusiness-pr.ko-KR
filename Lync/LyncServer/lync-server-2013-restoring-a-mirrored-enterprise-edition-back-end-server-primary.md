---
title: 미러된 Enterprise Edition 백 엔드 서버 복원-기본
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbf0c8562ed4180fb14bf0bda74a03dd4ee8f746
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a><span data-ttu-id="0c4fa-102">Lync Server 2013에서 미러된 Enterprise Edition 백 엔드 서버 복원-기본</span><span class="sxs-lookup"><span data-stu-id="0c4fa-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c4fa-103">_**마지막으로 수정한 주제:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="0c4fa-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="0c4fa-104">미러된 구성에 Enterprise Edition 백 엔드 서버가 있고 주 데이터베이스에만 오류가 있는 경우이 섹션의 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the primary database fails, follow the procedures in this section.</span></span> <span data-ttu-id="0c4fa-105">주 데이터베이스와 미러 서버 모두에 오류가 발생 하는 경우 [에는 Lync server 2013에서 Enterprise Edition 백 엔드 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="0c4fa-106">미러만 실패 하는 경우 [Lync server 2013-미러에서 미러된 Enterprise Edition 백 엔드 서버 복원을](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-106">If only the mirror fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span></span> <span data-ttu-id="0c4fa-107">중앙 관리 저장소를 호스팅하는 데이터베이스에 오류가 발생 하는 경우 [Lync server 2013에서 중앙 관리 저장소를 호스팅하는 서버 복원을](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="0c4fa-108">백 엔드 서버가 아닌 Enterprise Edition 구성원 서버가 실패 하는 경우 [Lync server 2013에서 Enterprise edition 구성원 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-member-server.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="0c4fa-109">복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="0c4fa-110">복원 중에 문제가 발생 하는 경우이 이미지를 롤백 시점으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="0c4fa-111">운영 체제 및 SQL Server를 설치 하 고 인증서를 복원 하거나 reenroll 이미지 복사본을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<span data-ttu-id="0c4fa-112">이 항목의 예제 기본 데이터베이스는 BE1.contoso.com의 FQDN (정규화 된 도메인 이름)을 사용 하 고 미러 데이터베이스의 FQDN은 BE2.contoso.com입니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-112">In this topic, the example primary database will have a fully qualified domain name (FQDN) of BE1.contoso.com, and the mirror database will have an FQDN of BE2.contoso.com.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a><span data-ttu-id="0c4fa-113">Enterprise Edition 백 엔드 서버 기본 데이터베이스를 복원 하려면</span><span class="sxs-lookup"><span data-stu-id="0c4fa-113">To restore an Enterprise Edition Back End Server Primary Database</span></span>

1.  <span data-ttu-id="0c4fa-114">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 프런트 엔드 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-114">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="0c4fa-115">Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0c4fa-116">구성 된 모든 데이터베이스를 강제로 미러에서 장애 조치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-116">Force all of the configured databases to fail over to the Mirror.</span></span> <span data-ttu-id="0c4fa-117">이 서버에 구성한 각 데이터베이스 유형에 대해 다음 cmdlet을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-117">For each of the database types that you have configured on this server, type the following cmdlet:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    <span data-ttu-id="0c4fa-118">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-118">For example:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="0c4fa-119">미러링 모니터 서버와 동기화 된 미러링을 사용 하도록 백 엔드 데이터베이스를 구성한 경우 장애 조치는 자동으로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-119">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span>

    
    </div>

4.  <span data-ttu-id="0c4fa-120">장애 조치 (failover)를 완료 한 후 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-120">After completing failover, perform the following:</span></span>
    
      - <span data-ttu-id="0c4fa-121">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="0c4fa-122">백 엔드 서버의 미러링 사용 안 함: **Enterprise Edition 프런트 엔드 풀** 에서 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-122">Disable mirroring on the Back End Server: Right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="0c4fa-123">**일반** 탭의 **연결**에서 **SQL Server 스토어 미러링 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-123">On the **General** tab, under **Associations**, clear the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="0c4fa-124">필요에 따라 보관 및 모니터링에이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-124">Do this for Archiving and Monitoring as necessary.</span></span> <span data-ttu-id="0c4fa-125">그런 다음 **확인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-125">Then click **OK**.</span></span>
    
      - <span data-ttu-id="0c4fa-126">Lync Server 2013 노드를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-126">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="0c4fa-127">계속 해 서 작동 하는 백 엔드 (BE2.contoso.com)를 새 SQL 저장소로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-127">Select the still functioning backend (BE2.contoso.com) to be the new SQL store.</span></span> <span data-ttu-id="0c4fa-128">이렇게 하려면 **Enterprise Edition 프런트 엔드 풀** 에서 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-128">To do this, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="0c4fa-129">**일반** 탭의 **연결**에서 **SQL Server store** 필드에 작동 하는 백 엔드의 FQDN (이 예제에서는 BE2.contoso.com)을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-129">On the **General** tab, under **Associations**, type the FQDN of the functioning backend in the **SQL Server store** field (in our example, BE2.contoso.com).</span></span>
    
      - <span data-ttu-id="0c4fa-130">Lync Server 2013 노드를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-130">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="0c4fa-131">각 서버가 새 토폴로지를 읽을 수 있도록 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-131">Restart services so that each server can read the new topology.</span></span> <span data-ttu-id="0c4fa-132">Lync Server Management 셸에서이 풀에 속하는 각 프런트 엔드 서버에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-132">From a Lync Server Management Shell, run the following cmdlets on each Front End Server that belongs to this pool:</span></span>
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  <span data-ttu-id="0c4fa-133">미러링 제거.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-133">Uninstall mirroring.</span></span> <span data-ttu-id="0c4fa-134">Lync Server Management Shell에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-134">From a Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="0c4fa-135">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-135">For example:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    <span data-ttu-id="0c4fa-136">이 서버의 모든 데이터베이스 유형에 대해이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-136">Do this for all database types on this server.</span></span>

6.  <span data-ttu-id="0c4fa-137">실패 한 컴퓨터와 동일한 FQDN (이 예제에서는 DB1.contoso.com)을가지고 있는 새 서버를 만들거나, 운영 체제를 설치한 다음, 인증서를 복원 하거나 reenroll.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-137">Create a clean or new server that has the same FQDN (in this example, DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="0c4fa-138">이 서버는 새 미러에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-138">This server will function as the new mirror.</span></span>

7.  <span data-ttu-id="0c4fa-139">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 새 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-139">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

8.  <span data-ttu-id="0c4fa-140">SQL Server 2012 또는 SQL Server 2008 R2를 설치 하 고 인스턴스 이름을 오류 전과 동일 하 게 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-140">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

9.  <span data-ttu-id="0c4fa-141">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 프런트 엔드 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-141">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

10. <span data-ttu-id="0c4fa-142">토폴로지 작성기를 사용 하 여 미러 DB를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-142">Use Topology Builder to install mirror DB.</span></span> <span data-ttu-id="0c4fa-143">다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-143">Perform the following steps:</span></span>
    
      - <span data-ttu-id="0c4fa-144">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-144">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="0c4fa-145">백 엔드 서버에서 미러링을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-145">Enable mirroring on the Back End Server.</span></span> <span data-ttu-id="0c4fa-146">이렇게 하려면 **Enterprise Edition 프런트 엔드 풀** 에서 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-146">To do so, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="0c4fa-147">**일반** 탭의 **연결**에서 **SQL Server 스토어 미러링 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-147">On the **General** tab, under **Associations**, select the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="0c4fa-148">필요에 따라 보관 및 모니터링에도이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-148">Also do this for Archiving and Monitoring, if necessary.</span></span>
        
        <span data-ttu-id="0c4fa-149">그런 다음 **SQL server 저장소 미러링** 필드에 새 서버의 FQDN을 입력 합니다 (이 예에서는 BE1.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0c4fa-149">Then, in the **Mirroring SQL Server store** field, type the FQDN of the new server (n this example, BE1.contoso.com).</span></span> <span data-ttu-id="0c4fa-150">그런 다음 **확인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-150">Then click **OK**.</span></span>
    
      - <span data-ttu-id="0c4fa-151">Lync Server 2013 노드를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **데이터베이스 설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-151">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="0c4fa-152">**데이터베이스 설치** 마법사를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-152">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="0c4fa-153">**데이터베이스 만들기** 페이지에서 다시 만들려는 데이터베이스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-153">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="0c4fa-154">메시지가 나타날 때까지 마법사의 지시에 따라 **미러 데이터베이스를 만듭니다**.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-154">Follow the wizard until you come to the prompt, **Create Mirror Database**.</span></span> <span data-ttu-id="0c4fa-155">설치 하려는 데이터베이스를 선택 하 고이 프로세스를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c4fa-155">Select the database that you want to install, and complete this process.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

