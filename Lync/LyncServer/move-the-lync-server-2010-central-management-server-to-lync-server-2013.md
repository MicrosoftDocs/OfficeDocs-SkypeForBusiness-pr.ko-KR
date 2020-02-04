---
title: Lync Server 2010 중앙 관리 서버를 Lync Server 2013로 이동
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
ms.openlocfilehash: 5f301c8f6e11ca3c8f19ed167489bb3fbf51fc63
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a><span data-ttu-id="5ae9c-102">Lync Server 2010 중앙 관리 서버를 Lync Server 2013로 이동</span><span class="sxs-lookup"><span data-stu-id="5ae9c-102">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ae9c-103">_**마지막으로 수정한 주제:** 2013-11-25_</span><span class="sxs-lookup"><span data-stu-id="5ae9c-103">_**Topic Last Modified:** 2013-11-25_</span></span>

<span data-ttu-id="5ae9c-104">Lync Server 2010에서 Lync Server 2013으로 마이그레이션한 후에는 lync server 2010 중앙 관리 서버를 Lync Server 2013 프런트 엔드 서버 또는 풀로 이동 해야 레거시 Lync Server 2010 서버를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-104">After migrating from Lync Server 2010 to Lync Server 2013, you need to move the Lync Server 2010 Central Management Server to the Lync Server 2013 Front End Server or pool, before you can remove the legacy Lync Server 2010 server.</span></span>

<span data-ttu-id="5ae9c-105">중앙 관리 서버는 중앙 관리 서버를 포함 하는 프런트 엔드 서버에서 데이터베이스의 읽기/쓰기 복사본을 보유 하 고 있는 단일 마스터/다중 복제 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="5ae9c-106">중앙 관리 서버를 포함 하는 프런트 엔드 서버를 포함 하 여 토폴로지의 각 컴퓨터에는 설치 하는 동안 컴퓨터에 설치 된 SQL Server 데이터베이스 (기본적으로 RTCLOCAL 이라는)의 중앙 관리 저장소 데이터에 대 한 읽기 전용 복사본이 있습니다. 배포가.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="5ae9c-107">로컬 데이터베이스는 모든 컴퓨터에서 서비스로 실행 되는 Lync Server 복제본 복제기 에이전트를 통해 복제본 업데이트를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-107">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="5ae9c-108">중앙 관리 서버 및 로컬 복제본의 실제 데이터베이스 이름은 xds, xds .mdf 파일로 구성 되는 XDS입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="5ae9c-109">Active Directory 도메인 서비스의 SCP (서비스 제어 지점)에서 마스터 데이터베이스 위치를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="5ae9c-110">중앙 관리 서버를 사용 하 여 Lync Server를 관리 하 고 구성 하는 모든 도구는 SCP를 사용 하 여 중앙 관리 저장소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-110">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>

<span data-ttu-id="5ae9c-111">중앙 관리 서버를 성공적으로 이동한 후에는 원래 프런트 엔드 서버에서 중앙 관리 서버 데이터베이스를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="5ae9c-112">중앙 관리 서버 데이터베이스를 제거 하는 방법에 대 한 자세한 내용은 [프런트 엔드 풀의 SQL Server 데이터베이스 제거](remove-the-sql-server-database-for-a-front-end-pool.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>

<span data-ttu-id="5ae9c-113">Lync server 관리 셸에서 Windows PowerShell cmdlet **CsManagementServer** 을 사용 하 여 lync SERVER 2010 sql server 데이터베이스에서 lync SERVER 2013 sql server 데이터베이스로 데이터베이스를 이동한 다음 lync Server 2013 중앙 관리 서버 위치를 가리키도록 SCP를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Lync Server Management Shell to move the database from the Lync Server 2010 SQL Server database to the Lync Server 2013 SQL Server database, and then update the SCP to point to the Lync Server 2013 Central Management Server location.</span></span>

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a><span data-ttu-id="5ae9c-114">중앙 관리 서버를 이동 하기 전에 Lync Server 2013 프런트 엔드 서버 준비</span><span class="sxs-lookup"><span data-stu-id="5ae9c-114">Preparing Lync Server 2013 Front End Servers before moving the Central Management Server</span></span>

<span data-ttu-id="5ae9c-115">Lync server 2010 중앙 관리 서버를 이동 하기 전에이 섹션의 절차를 사용 하 여 Lync Server 2013 프런트 엔드 서버를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-115">Use the procedures in this section to prepare the Lync Server 2013 Front End Servers before you move the Lync Server 2010 Central Management Server.</span></span>

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="5ae9c-116">Enterprise Edition 프런트 엔드 풀을 준비 하려면</span><span class="sxs-lookup"><span data-stu-id="5ae9c-116">To prepare an Enterprise Edition Front End pool</span></span>

1.  <span data-ttu-id="5ae9c-117">중앙 관리 서버를 재배치할 Lync Server 2013 Enterprise Edition 프런트 엔드 풀에서 Lync Server 관리 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-117">On the Lync Server 2013 Enterprise Edition Front End pool where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="5ae9c-118">또한 중앙 관리 저장소를 설치 하려는 데이터베이스에 대 한 SQL Server 데이터베이스 sysadmin 사용자 권한 및 사용 권한도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-118">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span>

2.  <span data-ttu-id="5ae9c-119">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-119">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="5ae9c-120">Lync server 2013 SQL Server 데이터베이스에서 새 중앙 관리 저장소를 만들려면 Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-120">To create the new Central Management store in the Lync Server 2013 SQL Server database, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  <span data-ttu-id="5ae9c-121">**Lync Server 프런트 엔드** 서비스의 상태가 **시작**되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-121">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="5ae9c-122">Standard Edition 프런트 엔드 서버를 준비 하려면</span><span class="sxs-lookup"><span data-stu-id="5ae9c-122">To prepare a Standard Edition Front End Server</span></span>

1.  <span data-ttu-id="5ae9c-123">중앙 관리 서버를 재배치할 Lync Server 2013 Standard Edition 프런트 엔드 서버: Lync Server 관리 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-123">On the Lync Server 2013 Standard Edition Front End Server where you want to relocate the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span>

2.  <span data-ttu-id="5ae9c-124">Lync 서버 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-124">Open the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="5ae9c-125">Lync Server 배포 마법사에서 **첫 번째 Standard Edition Server 준비**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-125">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="5ae9c-126">**명령 실행** 페이지에서 SQL Server Express가 중앙 관리 서버로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-126">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="5ae9c-127">필요한 방화벽 규칙이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-127">Necessary firewall rules are created.</span></span> <span data-ttu-id="5ae9c-128">데이터베이스 설치 및 필수 소프트웨어 소프트웨어가 완료 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-128">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ae9c-129">초기 설치에는 명령 출력 요약 화면에 표시 되는 업데이트 없이 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-129">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="5ae9c-130">이는 SQL Server Express의 설치 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-130">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="5ae9c-131">데이터베이스 설치를 모니터링 해야 하는 경우 작업 관리자를 사용 하 여 설정을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-131">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

5.  <span data-ttu-id="5ae9c-132">Lync server 2013 Standard Edition 프런트 엔드 서버에서 새 중앙 관리 저장소를 만들려면 Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-132">To create the new Central Management store on the Lync Server 2013 Standard Edition Front End Server, in the Lync Server Management Shell, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  <span data-ttu-id="5ae9c-133">**Lync Server 프런트 엔드** 서비스의 상태가 **시작**되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-133">Confirm that the status of the **Lync Server Front-End** service is **Started**.</span></span>

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a><span data-ttu-id="5ae9c-134">Lync Server 2010 중앙 관리 서버를 Lync Server 2013로 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="5ae9c-134">To move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>

1.  <span data-ttu-id="5ae9c-135">중앙 관리 서버가 되는 Lync Server 2013 서버에서 Lync Server Management 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-135">On the Lync Server 2013 server that will be the Central Management Server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="5ae9c-136">또한 SQL Server 데이터베이스 관리자의 사용자 권한 및 권한도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-136">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="5ae9c-137">Lync Server Management Shell을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-137">Open Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="5ae9c-138">Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-138">In the Lync Server Management Shell, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="5ae9c-139">이 <CODE>Enable-CsTopology</CODE> 실패할 경우, 계속 하기 전에 명령이 완료 되지 않도록 하는 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-139">If <CODE>Enable-CsTopology</CODE> is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="5ae9c-140"><STRONG>Enable-CsTopology</STRONG> 가 실패 하면 이동이 실패 하 고 중앙 관리 저장소가 없는 상태로 토폴로지가 유지 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-140">If <STRONG>Enable-CsTopology</STRONG> is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span>

    
    </div>

4.  <span data-ttu-id="5ae9c-141">Lync server 2013 프런트 엔드 서버 또는 프런트 엔드 풀의 Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-141">On the Lync Server 2013 Front End Server or Front End pool, in the Lync Server Management Shell, type:</span></span>
    
        Move-CsManagementServer

5.  <span data-ttu-id="5ae9c-142">Lync Server 관리 셸에서는 서버, 파일 저장소, 데이터베이스 저장소, 현재 상태의 서비스 연결 지점 및 제안 된 상태를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-142">Lync Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="5ae9c-143">이 정보를 주의깊게 읽고이 대상이 의도 한 원본 및 대상 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-143">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="5ae9c-144">계속 하려면 **Y** 를 입력 하 고, 이동을 중지 하려면 **N을 누르십시오** .</span><span class="sxs-lookup"><span data-stu-id="5ae9c-144">Type **Y** to continue, or **N** to stop the move.</span></span>

6.  <span data-ttu-id="5ae9c-145">**이동-CsManagementServer** 명령으로 생성 된 경고나 오류를 검토 하 고이를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-145">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span>

7.  <span data-ttu-id="5ae9c-146">Lync Server 2013 서버에서 Lync Server 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-146">On the Lync Server 2013 server, open the Lync Server Deployment Wizard.</span></span>

8.  <span data-ttu-id="5ae9c-147">Lync Server 배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭 하 고 **2 단계: Lync Server 구성 요소 설정 또는 제거**에서 **다음**을 클릭 하 고 요약을 검토 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-147">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

9.  <span data-ttu-id="5ae9c-148">Lync Server 2010 서버에서 Lync Server 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-148">On the Lync Server 2010 server, open the Lync Server Deployment Wizard.</span></span>

10. <span data-ttu-id="5ae9c-149">Lync Server 배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭 하 고 **2 단계: Lync Server 구성 요소 설정 또는 제거**에서 **다음**을 클릭 하 고 요약을 검토 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-149">In Lync Server Deployment Wizard, click **Install or Update Lync Server System**, click **Step 2: Setup or Remove Lync Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span>

11. <span data-ttu-id="5ae9c-150">Lync Server 2013 서버를 다시 부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-150">Reboot the Lync Server 2013 server.</span></span> <span data-ttu-id="5ae9c-151">이는 그룹 구성원 자격이 access 중앙 관리 서버 데이터베이스로 변경 되었기 때문에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-151">This is required because of a group membership change to access Central Management Server database.</span></span>

12. <span data-ttu-id="5ae9c-152">새 중앙 관리 저장소와의 복제가 진행 중인지 확인 하려면 Lync Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-152">To confirm that replication with the new Central Management store is occurring, in the Lync Server Management Shell, type:</span></span>
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ae9c-153">복제는 현재 모든 복제본을 업데이트 하는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-153">The replication may take some time to update all current replicas.</span></span>

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a><span data-ttu-id="5ae9c-154">이동 후 Lync Server 2010 중앙 관리 저장소 파일을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="5ae9c-154">To remove Lync Server 2010 Central Management store files after a move</span></span>

1.  <span data-ttu-id="5ae9c-155">Lync Server 2010 서버: Lync Server Management 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-155">On the Lync Server 2010 server: Log on to the computer where the Lync Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="5ae9c-156">또한 SQL Server 데이터베이스 관리자의 사용자 권한 및 권한도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-156">You must also have the SQL Server database administrator user rights and permissions.</span></span>

2.  <span data-ttu-id="5ae9c-157">Lync Server 관리 셸 열기</span><span class="sxs-lookup"><span data-stu-id="5ae9c-157">Open Lync Server Management Shell</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="5ae9c-158">복제가 완료 되 고 안정적이 지 않아도 이전 데이터베이스 파일을 제거 하는 것을 진행 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-158">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="5ae9c-159">복제를 완료 하기 전에 파일을 제거 하면 복제 프로세스가 중단 되 고 새로 이동한 중앙 관리 서버가 알 수 없는 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-159">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="5ae9c-160">Cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> 을 사용 하 여 복제 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-160">Use the cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> to confirm the replication status.</span></span>

    
    </div>

3.  <span data-ttu-id="5ae9c-161">Lync Server 2010 중앙 관리 서버에서 중앙 관리 저장소 데이터베이스 파일을 제거 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-161">To remove the Central Management store database files from the Lync Server 2010 Central Management Server, type:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    <span data-ttu-id="5ae9c-162">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-162">For example:</span></span>
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    <span data-ttu-id="5ae9c-163">여기서 SQL \<Server\> 의 fqdn은 엔터프라이즈 버전 배포의 Lync Server 2010 백 엔드 서버 이거나 STANDARD edition Server의 fqdn입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae9c-163">Where the \<FQDN of SQL Server\> is either the Lync Server 2010 Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

