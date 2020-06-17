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
description: 비즈니스용 Skype 서버 2019로 마이그레이션한 후에는 레거시 서버를 제거 하기 전에 중앙 관리 서버를 비즈니스용 Skype 서버 2019 프런트 엔드 서버 또는 풀로 이동 해야 합니다.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752470"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="3e3f2-103">레거시 중앙 관리 서버를 비즈니스용 Skype 서버 2019로 이동</span><span class="sxs-lookup"><span data-stu-id="3e3f2-103">Move the legacy Central Management Server to Skype for Business Server 2019</span></span>

<span data-ttu-id="3e3f2-104">비즈니스용 Skype 서버 2019로 마이그레이션한 후, 레거시 서버를 제거 하기 전에 중앙 관리 서버를 비즈니스용 Skype 서버 2019 프런트 엔드 서버 또는 풀로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-104">After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool.</span></span> 
  
<span data-ttu-id="3e3f2-105">중앙 관리 서버는 단일 마스터/다중 복제본 시스템으로, 중앙 관리 서버를 포함 하는 프런트 엔드 서버에서 데이터베이스의 읽기/쓰기 복사본을 보유 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-105">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="3e3f2-106">중앙 관리 서버를 포함 하는 프런트 엔드 서버를 포함 하 여 토폴로지의 각 컴퓨터에는 설치 및 배포 중에 컴퓨터에 설치 된 SQL Server 데이터베이스 (기본적으로 RTCLOCAL 라는)의 중앙 관리 저장소 데이터에 대 한 읽기 전용 복사본이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-106">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="3e3f2-107">로컬 데이터베이스는 모든 컴퓨터에서 서비스로 실행 되는 비즈니스용 Skype 서버 복제본 복제기 에이전트를 통해 복제 데이터베이스 업데이트를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-107">The local database receives replica updates by way of the Skype for Business Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="3e3f2-108">중앙 관리 서버 및 로컬 복제본의 실제 데이터베이스 이름은 xds로, xds로, xds로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-108">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="3e3f2-109">Active Directory 도메인 서비스의 SCP (서비스 제어 지점)에서 마스터 데이터베이스 위치를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-109">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="3e3f2-110">중앙 관리 서버를 사용 하 여 비즈니스용 Skype 서버를 관리 및 구성 하는 모든 도구는 SCP를 사용 하 여 중앙 관리 저장소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-110">All tools that use the Central Management Server to manage and configure Skype for Business Server use the SCP to locate the Central Management store.</span></span>
  
<span data-ttu-id="3e3f2-111">중앙 관리 서버를 성공적으로 이동한 후에는 원래 프런트 엔드 서버에서 중앙 관리 서버 데이터베이스를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-111">After you have successfully moved the Central Management Server, you should remove the Central Management Server databases from the original Front End Server.</span></span> <span data-ttu-id="3e3f2-112">중앙 관리 서버 데이터베이스를 제거 하는 방법에 대 한 자세한 내용은 [Remove THE SQL Server database for a 프런트 End pool](remove-the-sql-server-database-for-a-front-end-pool.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-112">For information on removing the Central Management Server databases, see [Remove the SQL Server database for a Front End pool](remove-the-sql-server-database-for-a-front-end-pool.md).</span></span>
  
<span data-ttu-id="3e3f2-113">비즈니스용 Skype 서버 관리 셸에서 Windows PowerShell cmdlet **move-csmanagementserver** 를 사용 하 여 데이터베이스를 레거시 설치 SQL server 데이터베이스에서 비즈니스용 skype 서버 2019 SQL Server 데이터베이스로 이동한 다음, SCP가 비즈니스용 skype 서버 2019 중앙 관리 서버 위치를 가리키도록 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-113">You use the Windows PowerShell cmdlet **Move-CsManagementServer** in the Skype for Business Server Management Shell to move the database from the legacy install SQL Server database to the Skype for Business Server 2019 SQL Server database, and then update the SCP to point to the Skype for Business Server 2019 Central Management Server location.</span></span> 
  
<span data-ttu-id="3e3f2-114">중앙 관리 서버를 이동 하기 전에이 섹션의 절차를 사용 하 여 비즈니스용 Skype 서버 2019 프런트 엔드 서버를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-114">Use the procedures in this section to prepare the Skype for Business Server 2019 Front End Servers before you move the Central Management Server.</span></span>
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a><span data-ttu-id="3e3f2-115">Enterprise Edition 프런트 엔드 풀을 준비 하려면</span><span class="sxs-lookup"><span data-stu-id="3e3f2-115">To prepare an Enterprise Edition Front End pool</span></span>

1. <span data-ttu-id="3e3f2-116">중앙 관리 서버를 재배치할 비즈니스용 Skype 서버 2019 Enterprise Edition 프런트 엔드 풀에서 비즈니스용 Skype 서버 관리 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-116">On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="3e3f2-117">또한 중앙 관리 저장소를 설치 하려는 데이터베이스에 대 한 SQL Server 데이터베이스 sysadmin 사용자 권한 및 사용 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-117">You must also have SQL Server database sysadmin user rights and permissions on the database where you want to install the Central Management store.</span></span> 
    
2. <span data-ttu-id="3e3f2-118">비즈니스용 Skype 서버 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-118">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="3e3f2-119">비즈니스용 skype 서버 2019 SQL Server 데이터베이스에서 새 중앙 관리 저장소를 만들려면 lync for Business Server Management Shell에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-119">To create the new Central Management store in the Skype for Business Server 2019 SQL Server database, in the Skype for Business Server Management Shell, type:</span></span>
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. <span data-ttu-id="3e3f2-120">**비즈니스용 Skype 서버 프런트 엔드** 서비스의 상태가 **시작**되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-120">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a><span data-ttu-id="3e3f2-121">Standard Edition 프런트 엔드 서버를 준비 하려면</span><span class="sxs-lookup"><span data-stu-id="3e3f2-121">To prepare a Standard Edition Front End Server</span></span>

1. <span data-ttu-id="3e3f2-122">중앙 관리 서버를 재배치할 비즈니스용 Skype 서버 2019 Standard Edition 프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-122">On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> 
    
2. <span data-ttu-id="3e3f2-123">비즈니스용 Skype 서버 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-123">Open the Skype for Business Server Deployment Wizard.</span></span>
    
3. <span data-ttu-id="3e3f2-124">비즈니스용 Skype 서버 배포 마법사에서 **첫 번째 Standard Edition Server 준비**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-124">In the Skype for Business Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>
    
4. <span data-ttu-id="3e3f2-125">**명령 실행** 페이지에서 SQL Server Express는 중앙 관리 서버로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-125">On the **Executing Commands** page, SQL Server Express is installed as the Central Management Server.</span></span> <span data-ttu-id="3e3f2-126">또한 필요한 방화벽 규칙이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-126">Necessary firewall rules are created.</span></span> <span data-ttu-id="3e3f2-127">데이터베이스 및 필수 구성 요소 소프트웨어 설치가 완료되면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-127">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3e3f2-128">초기 설치는 시간이 오래 걸릴 수 있으며 명령 출력 요약 화면에 업데이트가 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-128">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="3e3f2-129">SQL Server Express 설치 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-129">This is due to the installation of SQL Server Express.</span></span> <span data-ttu-id="3e3f2-130">데이터베이스 설치를 모니터링해야 하는 경우 작업 관리자를 사용하여 설치를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-130">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span> 
  
5. <span data-ttu-id="3e3f2-131">비즈니스용 skype 서버 2019 Standard Edition 프런트 엔드 서버에서 새 중앙 관리 저장소를 만들려면 lync for Business Server Management Shell에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-131">To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. <span data-ttu-id="3e3f2-132">**비즈니스용 Skype 서버 프런트 엔드** 서비스의 상태가 **시작**되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-132">Confirm that the status of the **Skype for Business Server Front-End** service is **Started**.</span></span>
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a><span data-ttu-id="3e3f2-133">레거시 설치 중앙 관리 서버를 비즈니스용 Skype 서버 2019로 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="3e3f2-133">To move the legacy installs Central Management Server to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="3e3f2-134">중앙 관리 서버가 되는 비즈니스용 Skype 서버 2019 서버에서 비즈니스용 Skype 서버 관리 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-134">On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="3e3f2-135">SQL Server 데이터베이스 관리자 사용자 권한 및 사용 권한도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-135">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="3e3f2-136">비즈니스용 Skype 서버 관리 셸을 엽니다 (관리자 권한으로 실행).</span><span class="sxs-lookup"><span data-stu-id="3e3f2-136">Open Skype for Business Server Management Shell (run as administrator).</span></span>
    
3. <span data-ttu-id="3e3f2-137">비즈니스용 Skype 서버 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-137">In the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > <span data-ttu-id="3e3f2-138">`Enable-CsTopology`이 실패할 경우 계속 하기 전에 명령을 완료 하지 못하게 하는 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-138">If `Enable-CsTopology` is not successful, resolve the problem preventing the command from completing before continuing.</span></span> <span data-ttu-id="3e3f2-139">**Enable-enable-cstopology** 가 실패 하면 이동이 실패 하 고 중앙 관리 저장소가 없는 상태로 토폴로지가 나갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-139">If **Enable-CsTopology** is not successful, the move will fail and it may leave your topology in a state where there is no Central Management store.</span></span> 
  
4. <span data-ttu-id="3e3f2-140">비즈니스용 skype 서버 2019 프런트 엔드 서버 또는 프런트 엔드 풀의 Wmi for Business Server 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-140">On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type:</span></span> 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. <span data-ttu-id="3e3f2-141">비즈니스용 Skype 서버 관리 셸에서는 서버, 파일 저장소, 데이터베이스 저장소 및 현재 상태와 제안 된 상태의 서비스 연결 지점을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-141">Skype for Business Server Management Shell displays the servers, file stores, database stores, and the service connection points of the Current State and the Proposed State.</span></span> <span data-ttu-id="3e3f2-142">정보를 주의해서 읽고 원래 의도된 원본과 대상인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-142">Read the information carefully and confirm that this is the intended source and destination.</span></span> <span data-ttu-id="3e3f2-143">계속하려면 **Y**를 입력하고 이동을 중지하려면 **N**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-143">Type **Y** to continue, or **N** to stop the move.</span></span> 
    
6. <span data-ttu-id="3e3f2-144">**Move-CsManagementServer** 명령으로 생성된 경고 또는 오류를 검토하고 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-144">Review any warnings or errors generated by the **Move-CsManagementServer** command and resolve them.</span></span> 
    
7. <span data-ttu-id="3e3f2-145">비즈니스용 Skype 서버 2019 서버에서 비즈니스용 Skype 서버 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-145">On the Skype for Business Server 2019 server, open the Skype for Business Server Deployment Wizard.</span></span> 
    
8. <span data-ttu-id="3e3f2-146">비즈니스용 Skype 서버 배포 마법사에서 비즈니스용 skype 서버 **시스템 설치 또는 업데이트**를 클릭 하 고 **2 단계: 비즈니스용 Skype 서버 구성 요소 설치 또는 제거**를 클릭 한 다음 요약을 **검토 하 고** **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-146">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
9. <span data-ttu-id="3e3f2-147">레거시 설치 서버에서 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-147">On the legacy install server, open the Deployment Wizard.</span></span> 
    
10. <span data-ttu-id="3e3f2-148">비즈니스용 Skype 서버 배포 마법사에서 비즈니스용 skype 서버 **시스템 설치 또는 업데이트**를 클릭 하 고 **2 단계: 비즈니스용 Skype 서버 구성 요소 설치 또는 제거**를 클릭 한 다음 요약을 **검토 하 고** **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-148">In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click **Step 2: Setup or Remove Skype for Business Server Components**, click **Next**, review the summary, and then click **Finish**.</span></span> 
    
11. <span data-ttu-id="3e3f2-149">비즈니스용 Skype 서버 2019 서버를 다시 부팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-149">Reboot the Skype for Business Server 2019 server.</span></span> <span data-ttu-id="3e3f2-150">이는 액세스 중앙 관리 서버 데이터베이스에 대 한 그룹 구성원 자격을 변경 했기 때문에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-150">This is required because of a group membership change to access Central Management Server database.</span></span>
    
12. <span data-ttu-id="3e3f2-151">새 중앙 관리 저장소를 사용한 복제가 진행 되 고 있는지 확인 하려면 비즈니스용 Skype 서버 관리 셸에서 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-151">To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type:</span></span> 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > <span data-ttu-id="3e3f2-152">복제로 모든 현재 복제본을 업데이트하려면 시간이 다소 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-152">The replication may take some time to update all current replicas.</span></span> 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a><span data-ttu-id="3e3f2-153">이동 후 레거시 설치 중앙 관리 저장소 파일을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="3e3f2-153">To remove legacy install Central Management store files after a move</span></span>

1. <span data-ttu-id="3e3f2-154">레거시 설치 서버에서 비즈니스용 Skype 서버 관리 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-154">On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group.</span></span> <span data-ttu-id="3e3f2-155">SQL Server 데이터베이스 관리자 사용자 권한 및 사용 권한도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-155">You must also have the SQL Server database administrator user rights and permissions.</span></span> 
    
2. <span data-ttu-id="3e3f2-156">비즈니스용 Skype 서버 관리 셸 열기</span><span class="sxs-lookup"><span data-stu-id="3e3f2-156">Open Skype for Business Server Management Shell</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="3e3f2-157">복제가 완료되고 안정화되기 전까지는 이전 데이터베이스 파일의 제거를 진행하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-157">Do not proceed with the removal of the previous database files until replication is complete and is stable.</span></span> <span data-ttu-id="3e3f2-158">복제를 완료 하기 전에 파일을 제거 하면 복제 프로세스를 중단 하 고 새로 이동한 중앙 관리 서버를 알 수 없는 상태로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-158">If you remove the files prior to completing replication, you will disrupt the replication process and leave the newly moved Central Management Server in an unknown state.</span></span> <span data-ttu-id="3e3f2-159">**Get-CsManagementStoreReplicationStatus** cmdlet을 사용하여 복제 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-159">Use the cmdlet **Get-CsManagementStoreReplicationStatus** to confirm the replication status.</span></span> 
  
3. <span data-ttu-id="3e3f2-160">레거시 설치 중앙 관리 서버에서 중앙 관리 저장소 데이터베이스 파일을 제거 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-160">To remove the Central Management store database files from the legacy install Central Management Server, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    <span data-ttu-id="3e3f2-161">예시:</span><span class="sxs-lookup"><span data-stu-id="3e3f2-161">For example:</span></span>
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    <span data-ttu-id="3e3f2-162">여기서은 _\<FQDN of SQL Server\>_ 엔터프라이즈 버전 배포의 레거시 설치 백 엔드 서버 또는 Standard edition Server의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="3e3f2-162">Where the  _\<FQDN of SQL Server\>_ is either the legacy install Back End Server in an Enterprise Edition deployment or the FQDN of the Standard Edition server.</span></span> 
    

