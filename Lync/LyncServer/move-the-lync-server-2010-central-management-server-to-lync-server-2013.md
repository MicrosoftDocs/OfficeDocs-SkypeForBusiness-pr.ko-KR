---
title: Lync server 2010 중앙 관리 서버를 Lync Server 2013로 이동
description: Lync server 2010 중앙 관리 서버를 Lync Server 2013로 이동 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19d53d797375b1eb8fde72f6b999e509b97f85ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571284"
---
# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="e92dc-103">Lync server 2010 중앙 관리 서버를 Lync Server 2013로 이동</span><span class="sxs-lookup"><span data-stu-id="e92dc-103">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e92dc-104">_**마지막으로 수정 된 항목:** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="e92dc-104">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="e92dc-105">Lync Server 2010에서 Lync Server 2013로 마이그레이션한 후에는 레거시 Lync Server 2010 서버를 제거 하기 전에 Lync server 2010 중앙 관리 서버를 Lync Server 2013 프런트 엔드 서버 또는 풀로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-105">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="e92dc-106">중앙 관리 서버는 단일 마스터/다중 복제본 시스템으로, 중앙 관리 서버를 포함 하는 프런트 엔드 서버에서 데이터베이스의 읽기/쓰기 복사본을 보유 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-106">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="e92dc-107">중앙 관리 서버를 포함 하는 프런트 엔드 서버를 포함 하 여 토폴로지의 각 컴퓨터에는 설치 및 배포 중에 컴퓨터에 설치 된 SQL Server 데이터베이스 (기본적으로 RTCLOCAL 라는)의 중앙 관리 저장소 데이터에 대 한 읽기 전용 복사본이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-107">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="e92dc-108">로컬 데이터베이스는 모든 컴퓨터에서 서비스로 실행 되는 Lync Server 복제본 복제기 에이전트를 통해 복제 데이터베이스 업데이트를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-108">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="e92dc-109">중앙 관리 서버 및 로컬 복제본의 실제 데이터베이스 이름은 xds로, xds로, xds로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-109">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="e92dc-110">Active Directory 도메인 서비스의 SCP (서비스 제어 지점)에서 마스터 데이터베이스 위치를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-110">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="e92dc-111">중앙 관리 서버를 사용 하 여 Lync Server를 관리 및 구성 하는 모든 도구는 SCP를 사용 하 여 중앙 관리 저장소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-111">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="e92dc-112">중앙 관리 서버를 성공적으로 이동한 후에는 원래 프런트 엔드 서버에서 중앙 관리 서버 데이터베이스를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-112">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="e92dc-113">중앙 관리 서버 데이터베이스를 제거 하는 방법에 대 한 자세한 내용은 [Remove THE SQL Server database for a 프런트 End pool](remove-the-sql-server-database-for-a-front-end-pool.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e92dc-113">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="e92dc-114">Lync server 관리 셸에서 Windows PowerShell cmdlet **move-csmanagementserver** 를 사용 하 여 lync SERVER 2010 sql server 데이터베이스에서 lync SERVER 2013 sql server 데이터베이스로 데이터베이스를 이동한 다음 lync Server 2013 중앙 관리 서버 위치를 가리키도록 SCP를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-114">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="e92dc-115">중앙 관리 서버를 이동 하기 전에 Lync Server 2013 프런트 엔드 서버 준비</span><span class="sxs-lookup"><span data-stu-id="e92dc-115">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="e92dc-116">Lync server 2010 중앙 관리 서버를 이동 하기 전에이 섹션의 절차를 사용 하 여 Lync Server 2013 프런트 엔드 서버를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-116">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="e92dc-117">Enterprise Edition 프런트 엔드 풀을 준비 하려면</span><span class="sxs-lookup"><span data-stu-id="e92dc-117">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="e92dc-118">중앙 관리 서버를 재배치할 Lync Server 2013 Enterprise Edition 프런트 엔드 풀에서 Lync Server 관리 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-118">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="e92dc-119">또한 중앙 관리 저장소를 설치 하려는 데이터베이스에 대 한 SQL Server 데이터베이스 sysadmin 사용자 권한 및 사용 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-119">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="e92dc-120">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-120">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="e92dc-121">Lync server 2013 SQL Server 데이터베이스에서 새 중앙 관리 저장소를 만들려면 Lync 서버 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-121">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="e92dc-122">**Lync Server 프런트 엔드** 서비스의 상태가 **시작됨**인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-122">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="e92dc-123">Standard Edition 프런트 엔드 서버를 준비 하려면</span><span class="sxs-lookup"><span data-stu-id="e92dc-123">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="e92dc-124">중앙 관리 서버를 재배치할 Lync Server 2013 Standard Edition 프런트 엔드 서버에서 Lync Server 관리 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-124">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="e92dc-125">Lync Server 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-125">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="e92dc-126">Lync Server 배포 마법사에서 **첫 번째 Standard Edition Server 준비**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-126">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="e92dc-127">**명령 실행** 페이지에서 SQL Server Express는 중앙 관리 서버로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-127">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="e92dc-128">또한 필요한 방화벽 규칙이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-128">Necessary firewall rules are created.</span></span> <span data-ttu-id="e92dc-129">데이터베이스 및 필수 구성 요소 소프트웨어 설치가 완료되면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-129">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e92dc-130">초기 설치는 시간이 오래 걸릴 수 있으며 명령 출력 요약 화면에 업데이트가 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-130">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="e92dc-131">SQL Server Express가 설치 되었기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-131">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="e92dc-132">데이터베이스 설치를 모니터링해야 하는 경우 작업 관리자를 사용하여 설치를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-132">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="e92dc-133">Lync server 2013 Standard Edition 프런트 엔드 서버에서 새 중앙 관리 저장소를 만들려면 Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-133">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="e92dc-134">**Lync Server 프런트 엔드** 서비스의 상태가 **시작됨**인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-134">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="e92dc-135">Lync server 2010 중앙 관리 서버를 Lync Server 2013로 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="e92dc-135">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="e92dc-136">중앙 관리 서버가 되는 Lync Server 2013 서버에서 Lync Server 관리 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-136">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="e92dc-137">SQL Server 데이터베이스 관리자 사용자 권한 및 사용 권한도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-137">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="e92dc-138">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-138">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="e92dc-139">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-139">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e92dc-140"><CODE>Enable-CsTopology</CODE>이 실패할 경우 계속 하기 전에 명령을 완료 하지 못하게 하는 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-140">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="e92dc-141"><STRONG>Enable-enable-cstopology</STRONG> 가 실패 하면 이동이 실패 하 고 중앙 관리 저장소가 없는 상태로 토폴로지가 나갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-141">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="e92dc-142">Lync server 2013 프런트 엔드 서버 또는 프런트 엔드 풀의 Lync 서버 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-142">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="e92dc-143">Lync Server 관리 셸에서는 현재 상태와 제안 된 상태의 서버, 파일 저장소, 데이터베이스 저장소 및 서비스 연결 지점을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-143">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="e92dc-144">정보를 주의해서 읽고 원래 의도된 원본과 대상인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-144">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="e92dc-145">계속하려면 **Y**를 입력하고 이동을 중지하려면 **N**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-145">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="e92dc-146">**Move-CsManagementServer** 명령으로 생성된 경고 또는 오류를 검토하고 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-146">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="e92dc-147">Lync Server 2013 서버에서 Lync Server 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-147">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="e92dc-148">Lync Server 배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭 하 고 **2 단계: Lync Server 구성 요소 설치 또는 제거**를 클릭 한 후 **다음**을 클릭 하 고 요약을 검토 한 후 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-148">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="e92dc-149">Lync Server 2010 서버에서 Lync Server 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-149">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="e92dc-150">Lync Server 배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭 하 고 **2 단계: Lync Server 구성 요소 설치 또는 제거**를 클릭 한 후 **다음**을 클릭 하 고 요약을 검토 한 후 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-150">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="e92dc-151">Lync Server 2013 서버를 다시 부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-151">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="e92dc-152">이는 액세스 중앙 관리 서버 데이터베이스에 대 한 그룹 구성원 자격을 변경 했기 때문에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-152">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="e92dc-153">새 중앙 관리 저장소를 사용한 복제가 진행 되 고 있는지 확인 하려면 Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-153">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e92dc-154">복제로 모든 현재 복제본을 업데이트하려면 시간이 다소 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-154">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="e92dc-155">이동 후 Lync Server 2010 중앙 관리 저장소 파일을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="e92dc-155">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="e92dc-156">Lync Server 2010 서버: Lync Server 관리 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-156">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="e92dc-157">SQL Server 데이터베이스 관리자 사용자 권한 및 사용 권한도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-157">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="e92dc-158">Lync Server 관리 셸 열기</span><span class="sxs-lookup"><span data-stu-id="e92dc-158">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e92dc-159">복제가 완료되고 안정화되기 전까지는 이전 데이터베이스 파일의 제거를 진행하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="e92dc-159">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="e92dc-160">복제를 완료 하기 전에 파일을 제거 하면 복제 프로세스를 중단 하 고 새로 이동한 중앙 관리 서버를 알 수 없는 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-160">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="e92dc-161"><STRONG>Get-CsManagementStoreReplicationStatus</STRONG> cmdlet을 사용하여 복제 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-161">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="e92dc-162">Lync Server 2010 중앙 관리 서버에서 중앙 관리 저장소 데이터베이스 파일을 제거 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-162">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="e92dc-163">예제:</span><span class="sxs-lookup"><span data-stu-id="e92dc-163">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="e92dc-164">여기서는 \<FQDN of SQL Server\> 엔터프라이즈 버전 배포의 Lync server 2010 백 엔드 서버 또는 Standard edition Server의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="e92dc-164">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

