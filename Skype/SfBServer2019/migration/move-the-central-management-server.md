---
title: 중앙 관리 서버 이동
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype 서버 2019로 마이그레이션한 후 레거시 서버를 제거하려면 먼저 중앙 관리 서버를 비즈니스용 Skype 서버 2019 프런트 엔드 서버 또는 풀로 이동해야 합니다.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752470"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="e77fe-103">레거시 중앙 관리 서버를 비즈니스용 Skype 서버로 이동</span><span class="sxs-lookup"><span data-stu-id="e77fe-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="e77fe-104">비즈니스용 Skype 서버 2019로 마이그레이션한 후 레거시 서버를 제거하려면 중앙 관리 서버를 비즈니스용 Skype 서버 2019 프런트 엔드 서버 또는 풀로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="e77fe-105">중앙 관리 서버는 데이터베이스의 읽기/쓰기 복사본이 중앙 관리 서버를 포함하는 프런트 엔드 서버에 의해 저장되는 단일 마스터/다중 복제본 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="e77fe-106">중앙 관리 서버가 포함된 프런트 엔드 서버를 포함하여 토폴로지의 각 컴퓨터에는 설치 및 배포 중에 컴퓨터에 설치된 SQL Server 데이터베이스(기본적으로 RTCLOCAL)의 중앙 관리 저장소 데이터의 읽기 전용 복사본이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="e77fe-107">로컬 데이터베이스는 모든 컴퓨터에서 서비스로 실행되는 비즈니스용 Skype 서버 복제본 복제자 에이전트를 통해 복제본 업데이트를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="e77fe-108">중앙 관리 서버 및 로컬 복제 데이터베이스의 실제 데이터베이스 이름은 xds.mdf 및 xds.ldf 파일로 구성되는 XDS입니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="e77fe-109">마스터 데이터베이스 위치는 Active Directory 도메인 서비스의 SCP(서비스 제어 지점)에서 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="e77fe-110">중앙 관리 서버를 사용하여 비즈니스용 Skype 서버를 관리 및 구성하는 모든 도구는 SCP를 사용하여 중앙 관리 저장소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="e77fe-111">중앙 관리 서버를 이동한 후 원래 프런트 엔드 서버에서 중앙 관리 서버 데이터베이스를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="e77fe-112">중앙 관리 서버 데이터베이스 제거에 대한 자세한 내용은 프런트 엔드 풀의 SQL Server 데이터베이스 [제거를 참조하십시오.](remove-the-sql-server-database-for-a-front-end-pool.md)</span><span class="sxs-lookup"><span data-stu-id="e77fe-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="e77fe-113">비즈니스용 Skype 서버 관리 셸의 Windows PowerShell cmdlet **Move-CsManagementServer를** 사용하여 레거시 설치 SQL Server 데이터베이스에서 비즈니스용 Skype 서버 2019 SQL Server 데이터베이스로 데이터베이스를 이동한 다음 비즈니스용 Skype 서버 2019 중앙 관리 서버 위치를 설정하도록 SCP를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="e77fe-114">중앙 관리 서버를 이동하기 전에 이 섹션의 절차에 따라 비즈니스용 Skype 서버 2019 프런트 엔드 서버를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="e77fe-115">Enterprise Edition 프런트 엔드 풀을 준비하는 경우</span><span class="sxs-lookup"><span data-stu-id="e77fe-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="e77fe-116">중앙 관리 서버를 재배치할 비즈니스용 Skype 서버 2019 Enterprise Edition 프런트 엔드 풀에서 **RTCUniversalServerAdmins** 그룹의 구성원으로 비즈니스용 Skype 서버 관리 셸이 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="e77fe-117">또한 중앙 관리 저장소를 SQL Server 데이터베이스에 대한 데이터베이스 sysadmin 사용자 권한 및 사용 권한도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="e77fe-118">비즈니스용 Skype 서버 관리 셸을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="e77fe-119">비즈니스용 Skype 서버 2019 데이터베이스에서 새 중앙 관리 저장소를 SQL Server 비즈니스용 Skype 서버 관리 셸에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="e77fe-120">비즈니스용 **Skype** 서버 프런트 엔드 서비스의 상태가 **시작된지 확인**</span><span class="sxs-lookup"><span data-stu-id="e77fe-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="e77fe-121">Standard Edition 프런트 엔드 서버를 준비하기 위해</span><span class="sxs-lookup"><span data-stu-id="e77fe-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="e77fe-122">중앙 관리 서버를 재배치하려는 비즈니스용 Skype 서버 2019 Standard Edition 프런트 엔드 서버에서 **RTCUniversalServerAdmins** 그룹의 구성원으로 비즈니스용 Skype 서버 관리 셸이 설치된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="e77fe-123">비즈니스용 Skype 서버 배포 마법사를 여는 경우</span><span class="sxs-lookup"><span data-stu-id="e77fe-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="e77fe-124">비즈니스용 Skype 서버 배포 마법사에서 첫 번째 Standard Edition 서버 **준비를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e77fe-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="e77fe-125">명령 **실행** 페이지에서 SQL Server Express가 중앙 관리 서버로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="e77fe-126">또한 필요한 방화벽 규칙이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="e77fe-127">데이터베이스 및 필수 구성 요소 소프트웨어 설치가 완료되면 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e77fe-128">초기 설치는 시간이 오래 걸릴 수 있으며 명령 출력 요약 화면에 업데이트가 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="e77fe-129">이는 Express를 설치하기 SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e77fe-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="e77fe-130">데이터베이스 설치를 모니터링해야 하는 경우 작업 관리자를 사용하여 설치를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="e77fe-131">비즈니스용 Skype 서버 2019 Standard Edition 프런트 엔드 서버에서 새 중앙 관리 저장소를 만들 경우 비즈니스용 Skype 서버 관리 셸에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="e77fe-132">비즈니스용 **Skype** 서버 프런트 엔드 서비스의 상태가 **시작된지 확인**</span><span class="sxs-lookup"><span data-stu-id="e77fe-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="e77fe-133">레거시를 이동하려면 중앙 관리 서버를 비즈니스용 Skype 서버 2019로 설치</span><span class="sxs-lookup"><span data-stu-id="e77fe-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="e77fe-134">중앙 관리 서버가 될 비즈니스용 Skype 서버 2019 서버에서 비즈니스용 Skype 서버 관리 셸이 설치된 컴퓨터에 **RTCUniversalServerAdmins** 그룹의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="e77fe-135">SQL Server 데이터베이스 관리자 사용자 권한 및 사용 권한도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="e77fe-136">비즈니스용 Skype 서버 관리 셸을 열고(관리자 권한으로 실행).</span><span class="sxs-lookup"><span data-stu-id="e77fe-136">Open Skype for Business Server Management Shell (run as administrator).</span></span>
    
3. <span data-ttu-id="e77fe-137">비즈니스용 Skype 서버 관리 셸에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="e77fe-138">성공하지 못하면 계속하기 전에 명령을 완료하지 못하게 하는 문제를 `Enable-CsTopology` 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="e77fe-139">**Enable-CsTopology가** 실패하면 이동이 실패하고 중앙 관리 저장소가 없는 상태로 토폴로지가 남을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="e77fe-140">비즈니스용 Skype 서버 2019 프런트 엔드 서버 또는 프런트 엔드 풀의 비즈니스용 Skype 서버 관리 셸에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. <span data-ttu-id="e77fe-141">비즈니스용 Skype 서버 관리 셸에는 현재 상태 및 제안된 상태의 서버, 파일 저장소, 데이터베이스 저장소 및 서비스 연결 지점이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="e77fe-142">정보를 주의해서 읽고 원래 의도된 원본과 대상인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="e77fe-143">계속하려면 **Y** 를 입력하고 이동을 중지하려면 **N** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="e77fe-144">**Move-CsManagementServer** 명령으로 생성된 경고 또는 오류를 검토하고 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="e77fe-145">비즈니스용 Skype 서버 2019 서버에서 비즈니스용 Skype 서버 배포 마법사를 니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="e77fe-146">비즈니스용 Skype 서버 배포 마법사에서 비즈니스용 **Skype** 서버 시스템 설치 또는 업데이트를 클릭하고, **2단계:** 비즈니스용 Skype 서버 구성 요소 설치 또는 제거, **다음,** 요약 검토 및 완료를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e77fe-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="e77fe-147">레거시 설치 서버에서 배포 마법사를 여는 경우</span><span class="sxs-lookup"><span data-stu-id="e77fe-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="e77fe-148">비즈니스용 Skype 서버 배포 마법사에서 비즈니스용 **Skype** 서버 시스템 설치 또는 업데이트를 클릭하고, **2단계:** 비즈니스용 Skype 서버 구성 요소 설치 또는 제거, **다음,** 요약 검토 및 완료를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e77fe-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="e77fe-149">비즈니스용 Skype 서버 2019 서버를 다시 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="e77fe-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="e77fe-150">이 설정은 중앙 관리 서버 데이터베이스에 액세스하기 위한 그룹 구성원 변경 때문에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="e77fe-151">새 중앙 관리 저장소와의 복제가 발생하는지 확인하기 위해 비즈니스용 Skype 서버 관리 셸에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="e77fe-152">복제로 모든 현재 복제본을 업데이트하려면 시간이 다소 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="e77fe-153">이동 후 레거시 중앙 관리 저장소 파일을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="e77fe-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="e77fe-154">레거시 설치 서버에서 비즈니스용 Skype 서버 관리 셸이 설치된 컴퓨터에 **RTCUniversalServerAdmins** 그룹의 구성원으로 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="e77fe-155">SQL Server 데이터베이스 관리자 사용자 권한 및 사용 권한도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="e77fe-156">비즈니스용 Skype 서버 관리 셸 열기</span><span class="sxs-lookup"><span data-stu-id="e77fe-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="e77fe-157">복제가 완료되고 안정화되기 전까지는 이전 데이터베이스 파일의 제거를 진행하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="e77fe-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="e77fe-158">복제를 완료하기 전에 파일을 제거하면 복제 프로세스가 중단된 후 새로 이동된 중앙 관리 서버가 알 수 없는 상태로 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="e77fe-159">**Get-CsManagementStoreReplicationStatus** cmdlet을 사용하여 복제 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="e77fe-160">레거시 설치 중앙 관리 서버에서 중앙 관리 저장소 데이터베이스 파일을 제거하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="e77fe-161">예시:</span><span class="sxs-lookup"><span data-stu-id="e77fe-161">For example:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="e77fe-162">여기서 레거시는 Enterprise Edition 배포에 백 엔드 서버를 설치하거나  _\<FQDN of SQL Server\>_ Standard Edition 서버의 FQDN을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e77fe-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

