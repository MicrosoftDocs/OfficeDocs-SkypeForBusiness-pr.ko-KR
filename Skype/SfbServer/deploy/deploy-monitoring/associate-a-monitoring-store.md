---
title: 비즈니스용 Skype 서버에서 모니터링 저장소를 프런트 엔드 풀과 연결
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
description: '요약: 프런트 엔드 풀을 비즈니스용 Skype 서버에서 사용하는 모니터링 저장소와 연결하는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 4ec48e99da9a827cdc40d87c42ec764bda66a416
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830548"
---
# <a name="associate-a-monitoring-store-with-a-front-end-pool-in-skype-for-business-server"></a><span data-ttu-id="ac264-103">비즈니스용 Skype 서버에서 모니터링 저장소를 프런트 엔드 풀과 연결</span><span class="sxs-lookup"><span data-stu-id="ac264-103">Associate a monitoring store with a Front End pool in Skype for Business Server</span></span> 
<span data-ttu-id="ac264-104">**요약:** 프런트 엔드 풀을 비즈니스용 Skype 서버에서 사용하는 모니터링 저장소와 연결하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-104">**Summary:** Learn how to associate Front End pools with a monitoring store used by Skype for Business Server.</span></span>
  
<span data-ttu-id="ac264-105">비즈니스용 Skype 서버에서는 모니터링 저장소와 연결된 프런트 엔드 풀에서만 모니터링 데이터를 수집할 수 있으며, 작업은 일반적으로 토폴로지 작성기에서 프런트 엔드 풀을 정의할 때 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-105">In Skype for Business Server, monitoring data can only be collected on Front End pools that have been associated with a monitoring store, a task typically carried out when you define a Front End pool in Topology Builder.</span></span>
  
## <a name="associate-a-monitoring-store-with-a-front-end-pool"></a><span data-ttu-id="ac264-106">모니터링 저장소를 프런트 엔드 풀과 연결</span><span class="sxs-lookup"><span data-stu-id="ac264-106">Associate a monitoring store with a Front End pool</span></span>

 <span data-ttu-id="ac264-107">모니터링 저장소를 새 프런트 엔드 풀과 연결하려면 새 프런트  엔드 풀 정의 마법사의 기능 선택 페이지에서 옵션 모니터링(통화 정보 기록 및 환경 품질 메트릭 로깅)을 선택해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="ac264-107">To associate a monitoring store with a new Front End pool, make sure that you select the option **Monitoring (call detail recording and logging of quality of experience metrics)** on the **Select Features** page of the Define New Front End Pool wizard.</span></span> <span data-ttu-id="ac264-108">이 옵션을 선택하는 경우 마법사를 완료하려면 SQL 저장소도 지정해야 합니다. 그러나 이 저장소는 마법사를 실행할 때 존재하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-108">Note that, if you select this option, you must also specify a SQL store in order to complete the wizard; however, this store does not have to exist at the time you run the wizard.</span></span> <span data-ttu-id="ac264-109">즉, 먼저 풀을 모니터링 저장소와 연결한 다음 나중에 해당 저장소를 설정하고 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-109">That means that you can first associate a pool with a monitoring store, then later setup and configure that store.</span></span>
  
<span data-ttu-id="ac264-110">또는 다음 절차를 완료하여 기존 프런트 엔드 풀을 새 모니터링 저장소 또는 다른 모니터링 저장소와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-110">Alternatively, you can associate an existing Front End pool with a new or different monitoring store by completing the following procedure:</span></span>
  
1. <span data-ttu-id="ac264-111">**시작,** 모든 **프로그램,** 비즈니스용 **Skype 서버 2015를** 클릭한 다음 비즈니스용 Skype 서버 토폴로지 작성기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac264-111">Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Topology Builder**.</span></span>
    
2. <span data-ttu-id="ac264-112">**토폴로지 작성기** 대화 상자에서 **기존 배포에서 토폴로지 다운로드** 를 선택한 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-112">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>
    
3. <span data-ttu-id="ac264-113">다른 **이름으로** 저장 대화 상자에서 현재 토폴로지의 파일 이름을 입력한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac264-113">In the **Save As** dialog box, enter a file name for your current topology and then click **Save**.</span></span> <span data-ttu-id="ac264-114">새 토폴로지에서 문제가 발생할 경우 저장된 토폴로지가 나중에 검색되고 다시 게시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-114">The saved topology can later be retrieved and re-published in case there are problems with the new topology.</span></span>
    
4. <span data-ttu-id="ac264-115">토폴로지 작성기에서 비즈니스용 **Skype** 서버를 확장하고 프런트 엔드 풀이 포함된 사이트의 이름을 확장한 다음 Enterprise Edition 프런트 엔드 풀을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac264-115">In Topology Builder, expand **Skype for Business Server**, expand the name of the site containing the Front End pool, then click expand **Enterprise Edition Front End pools**.</span></span>
    
5. <span data-ttu-id="ac264-116">모니터링 저장소와 연결될 풀의 이름을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac264-116">Right-click the name of the pool to be associated with the monitoring store and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="ac264-117">속성  편집 대화 상자의  일반 탭에서 옵션 모니터링(CDR 및 **QoE** 메트릭)을 선택한 다음 모니터링  SQL Server 저장소 드롭다운 목록에서 기존 SQL Server 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-117">In the **Edit Properties** dialog box, on the **General** tab, select the option **Monitoring (CDR and QoE metrics)** and then select an existing SQL Server database from the **Monitoring SQL Server store** dropdown list.</span></span> <span data-ttu-id="ac264-118">또는 새로 **고침을** 클릭하여 풀을 새 데이터베이스 저장소와 연결합니다. 새 데이터베이스 저장소를 사용하기로 선택한 경우 새 SQL **저장소** 정의 대화 상자에서 **Sql Server FQDN** 상자에 SQL Server 컴퓨터의 SQL Server 도메인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-118">(Or, click **New** to associate the pool with a new database store.) If you choose to use a new database store then, in the **Define New SQL Store** dialog box, enter the fully qualified domain name of the SQL Server computer in the **Sql Server FQDN** box.</span></span> <span data-ttu-id="ac264-119">해당 저장소에 대해 기본 SQL Server 인스턴스를 사용하려면 기본 **인스턴스를 선택합니다.** 그렇지 않으면 **명명된 인스턴스를** 선택하고 명명된 인스턴스 상자에 인스턴스 **이름을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac264-119">If you want to use the default SQL Server instance for that store select **Default Instance**; otherwise select **Named Instance** and enter the instance name in the **Named Instance** box.</span></span>
    
    <span data-ttu-id="ac264-120">또한  속성 편집 대화 상자에서는 모니터링 데이터베이스에 대한 SQL 미러를 만들 수 있는 옵션도 제공합니다(SQL 미러를 사용하면 모니터링 데이터베이스의 복사본 두 개, 모니터링 저장소 컴퓨터에 저장된 복사본 1개, SQL 미러 컴퓨터에 저장되는 복사본을 유지 관리하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-120">The **Edit Properties** dialog box also gives you the option of creating a SQL mirror for your monitoring database (a SQL mirror enables you to maintain two copies of your monitoring database, one copy stored on the monitoring store computer and the other on the SQL mirror computer).</span></span> <span data-ttu-id="ac264-121">미러링을 사용하도록  설정하려면 해당 SQL 인스턴스가 미러링 관계에 있는 T를 선택하고 미러링 포트 번호 상자에 미러 서버의 포트 번호를 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac264-121">To enable mirroring, select T **his SQL instance is in mirroring relation** and enter the port number for the mirror server in the **Mirroring port number** box.</span></span>
    
7. <span data-ttu-id="ac264-122">속성 **편집 대화** 상자에서 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac264-122">In the **Edit Properties** dialog box, click **OK**.</span></span>
    
<span data-ttu-id="ac264-123">모니터링 저장소를 프런트 엔드 풀과 연결한 후 변경 내용을 적용하려면 새 토폴로지가 게시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-123">After associating the monitoring store with a Front End pool you must publish the new topology before the changes take effect.</span></span> <span data-ttu-id="ac264-124">새 토폴로지 게시를 위해 토폴로지 작성기에서 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-124">To publish your new topology, complete the following steps in Topology Builder:</span></span>
  
1. <span data-ttu-id="ac264-125">작업을 **클릭하고** **토폴로지,** 게시를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac264-125">Click **Action**, point to **Topology**, and then click **Publish**.</span></span>
    
2. <span data-ttu-id="ac264-126">토폴로지 게시 마법사의  토폴로지 게시 페이지에서 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac264-126">In the Publish Topology wizard, on the **Publish the topology** page, click **Next**.</span></span>
    
3. <span data-ttu-id="ac264-127">**게시 마법사 완료** 페이지에서 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-127">On the **Publishing wizard complete** page, click **Finish**.</span></span>
    
<span data-ttu-id="ac264-128">토폴로지가 게시된 후 모니터링 저장소를 호스팅할 컴퓨터에 모니터링 데이터베이스를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-128">After the topology has been published you can then install the monitoring database on the computer that will host the monitoring store.</span></span> <span data-ttu-id="ac264-129">모니터링 데이터베이스는 비즈니스용 Skype 서버 관리 셸 및 셸을 사용하여 설치할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac264-129">The monitoring database can be installed by using the Skype for Business Server Management Shell and Windows PowerShell.</span></span> <span data-ttu-id="ac264-130">데이터베이스를 로컬로 설치하려면(즉, 비즈니스용 Skype 서버 관리 셸을 실행하는 동일한 컴퓨터에 데이터베이스를 설치하려면 해당 컴퓨터에서 관리 셸을 시작한 후 다음 명령을 입력하고 Enter 누르기)</span><span class="sxs-lookup"><span data-stu-id="ac264-130">To install the database locally (that is, to install the database on the same computer where you are running the Skype for Business Server Management Shell), start the Management Shell on the appropriate computer, then type in the following command and press ENTER:</span></span>
  
```powershell
Install-CsDatabase -LocalDatabases
```

<span data-ttu-id="ac264-131">위의 명령을 실행하면 Install-CsDatabase 현재 비즈니스용 Skype 서버 토폴로지가 읽고 로컬 컴퓨터에 설치해야 하는 데이터베이스를 확인한 다음 이러한 각 데이터베이스를 자동으로 설치 및 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-131">When you run the preceding command, Install-CsDatabase will read the current Skype for Business Server topology, determine which databases need to be installed on the local computer, and then automatically install and configure each of those databases.</span></span>
  
<span data-ttu-id="ac264-132">원격 컴퓨터(즉, 관리 셸이 실행 중인 컴퓨터가 아닌 다른 컴퓨터)에 데이터베이스를 설치하려면 ConfiguredDatabases 매개 변수와 SqlServerFqdn 매개 변수의 두 개 이상의 매개 변수를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-132">To install the database on a remote computer (that is, a computer other than the computer where the Management Shell is running) you must include at least two parameters: the ConfiguredDatabases parameter and the SqlServerFqdn parameter.</span></span> <span data-ttu-id="ac264-133">이러한 매개 변수는 Install-CsDatabase cmdlet에 비즈니스용 Skype 서버 토폴로지 검색을 한 다음 SqlServerFqdn 매개 변수로 지정된 컴퓨터에 필요한 데이터베이스를 설치 및 구성하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-133">These parameters tell the Install-CsDatabase cmdlet to retrieve the Skype for Business Server topology and then install and configure the required databases on the computer specified by the SqlServerFqdn parameter.</span></span> <span data-ttu-id="ac264-134">SqlServerFqdn 매개 변수는 데이터베이스를 설치할 컴퓨터의 정식 도메인 이름을 나타내는 매개 변수 값을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-134">The SqlServerFqdn parameter must use a parameter value representing the fully qualified domain name of the computer where the databases are to be installed.</span></span>
  
<span data-ttu-id="ac264-135">예를 들어 다음 명령은 다음과 같은 컴퓨터에 모니터링 데이터베이스를 atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ac264-135">For example, this command installs the monitoring database on the computer atl-sql-001.litwareinc.com:</span></span>
  
```powershell
Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com
```

<span data-ttu-id="ac264-136">또는 모니터링 저장소를 호스팅할 컴퓨터에서 비즈니스용 Skype 서버 배포 마법사를 실행하여 모니터링 데이터베이스를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-136">Alternatively, you can install the monitoring database by running the Skype for Business Server Deployment Wizard on the computer that will host the monitoring store.</span></span> <span data-ttu-id="ac264-137">이렇게하려면 해당 컴퓨터에 로그온하고 다음 절차를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-137">To do this, log on to the appropriate computer and complete the following procedure:</span></span>
  
1. <span data-ttu-id="ac264-138">**시작,** 모든 **프로그램,** 비즈니스용 **Skype 서버 2015를** 클릭한 다음 비즈니스용 Skype 서버 배포 마법사를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac264-138">Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="ac264-139">배포 마법사에서 **비즈니스용 Skype** 서버 시스템 설치 또는 업데이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-139">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="ac264-140">배포 **페이지의** **2단계: 비즈니스용 Skype** 서버 구성 요소 설치 또는 제거에서 다시 **실행을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac264-140">On the **Deploy** page, under **Step 2: Setup or Remove Skype for Business Server Components**, click **Run Again**.</span></span>
    
4. <span data-ttu-id="ac264-141">비즈니스용 Skype 서버 구성 요소 설치 마법사의 비즈니스용 **Skype 서버** 구성 요소 설치 페이지에서 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac264-141">In the Setup Skype for Business Server components wizard, on the **Setup Skype for Business Server components** page, click **Next**.</span></span>
    
5. <span data-ttu-id="ac264-142">**MSIS** 경로 지정 페이지에서 파일 경로(Ocscore.msi 비즈니스용 Skype 서버 설치 미디어에 포함된 파일)를 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac264-142">On the **Specify path to MSIs** page, type the path to the file Ocscore.msi (a file included with your Skype for Business Server installation media) and then click **Next**.</span></span>
    
6. <span data-ttu-id="ac264-143">**명령 실행** 페이지에서 **마침** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac264-143">On the **Executing Commands** page, click **Finish**.</span></span>
    
<span data-ttu-id="ac264-144">필요한 모든 비즈니스용 Skype 서버 서비스가 시작되도록  확인하려면 배포 페이지에서 **4단계:** 서비스 시작 페이지의 실행을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac264-144">To ensure that all the required Skype for Business Server services have started, click **Run** under the heading **Step 4: Start Services** on the **Deploy** page</span></span>
  

