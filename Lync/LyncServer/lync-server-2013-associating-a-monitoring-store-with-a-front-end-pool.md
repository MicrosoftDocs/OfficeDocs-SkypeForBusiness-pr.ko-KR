---
title: 'Lync Server 2013: 모니터링 저장소를 프런트 엔드 풀에 연결'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c1153d0d20cf5a3855a36f8d7aa24a8d9d4680b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="bcb4d-102">Lync Server 2013의 프런트 엔드 풀에 모니터링 저장소 연결</span><span class="sxs-lookup"><span data-stu-id="bcb4d-102">Associating a monitoring store with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcb4d-103">_**마지막으로 수정한 주제:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="bcb4d-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="bcb4d-104">Microsoft Lync Server 2013 모니터링 저장소와 연결 된 프런트 엔드 풀 에서만 데이터를 수집할 수 있으며, 일반적으로 토폴로지 작성기에서 프런트 엔드 풀을 정의 하는 작업이 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-104">In Microsoft Lync Server 2013 monitoring data can only be collected on Front End pools that have been associated with a monitoring store, a task typically carried out you define a Front End pool in Topology Builder.</span></span> <span data-ttu-id="bcb4d-105">모니터링 저장소와 새 프런트 엔드 풀을 연결 하려면 새 프런트 엔드 풀 정의 마법사의 **기능 선택** 페이지에서 **경험 치 메트릭의 자세한 기록 및 로깅** 옵션을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-105">To associate a monitoring store with a new Front End pool, make sure that you select the option **Monitoring (call detail recording and logging of quality of experience metrics)** on the **Select Features** page of the Define New Front End Pool wizard.</span></span> <span data-ttu-id="bcb4d-106">이 옵션을 선택 하는 경우 마법사를 완료 하기 위해 SQL 저장소도 지정 해야 합니다. 그러나이 저장소는 마법사를 실행할 때 존재 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-106">Note that, if you select this option, you must also specify a SQL store in order to complete the wizard; however, this store does not have to exist at the time you run the wizard.</span></span> <span data-ttu-id="bcb4d-107">즉, 먼저 풀을 모니터링 저장소와 연결한 다음 나중에 설치 하 고 해당 저장소를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-107">That means that you can first associate a pool with a monitoring store, then later setup and configure that store.</span></span>

<span data-ttu-id="bcb4d-108">또는 다음 절차를 완료 하 여 기존 프런트 엔드 풀을 새 모니터링 저장소나 다른 모니터링 저장소와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-108">Alternatively, you can associate an existing Front End pool with a new or different monitoring store by completing the following procedure:</span></span>

1.  <span data-ttu-id="bcb4d-109">**시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="bcb4d-110">**토폴로지 작성기** 대화 상자에서 **기존 배포의 토폴로지 다운로드** 를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-110">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="bcb4d-111">**다른 이름으로 저장** 대화 상자에서 현재 토폴로지의 파일 이름을 입력 한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-111">In the **Save As** dialog box, enter a file name for your current topology and then click **Save**.</span></span> <span data-ttu-id="bcb4d-112">새 토폴로지에 문제가 있는 경우 나중에 저장 된 토폴로지가 검색 되 고 다시 게시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-112">The saved topology can later be retrieved and re-published in case there are problems with the new topology.</span></span>

4.  <span data-ttu-id="bcb4d-113">토폴로지 작성기에서 **Lync Server 2013**을 확장 하 고 프런트 엔드 풀을 포함 하는 사이트의 이름을 확장 한 다음 **Enterprise Edition 프런트 엔드 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-113">In Topology Builder, expand **Lync Server 2013**, expand the name of the site containing the Front End pool, then click expand **Enterprise Edition Front End pools**.</span></span>

5.  <span data-ttu-id="bcb4d-114">모니터링 저장소와 연결할 풀의 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-114">Right-click the name of the pool to be associated with the monitoring store and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="bcb4d-115">**속성 편집** 대화 상자의 **일반** 탭에서 **모니터링 옵션 (CDR 및 체감 품질 메트릭스)** 을 선택한 다음 **sql SERVER Store 모니터링** 드롭다운 목록에서 기존 SQL Server 데이터베이스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-115">In the **Edit Properties** dialog box, on the **General** tab, select the option **Monitoring (CDR and QoE metrics)** and then select an existing SQL Server database from the **Monitoring SQL Server store** dropdown list.</span></span> <span data-ttu-id="bcb4d-116">(또는 **새로 만들기** 를 클릭 하 여 풀을 새 데이터베이스 저장소와 연결 합니다.) 새 데이터베이스 저장소를 사용 하도록 선택한 경우 **새 Sql 저장소 정의** 대화 상자에서 sql SERVER의 **FQDN** (정규화 된 도메인 이름) 확인란</span><span class="sxs-lookup"><span data-stu-id="bcb4d-116">(Or, click **New** to associate the pool with a new database store.) If you choose to use a new database store then, in the **Define New SQL Store** dialog box, enter the fully qualified domain name of the SQL Server computer in the **Sql Server FQDN** box.</span></span> <span data-ttu-id="bcb4d-117">해당 저장소에 대 한 기본 SQL Server 인스턴스를 사용 하려는 경우 **기본 인스턴스**를 선택 합니다. 그렇지 않으면 **명명 된 인스턴스** 를 선택 하 고 명명 된 **인스턴스** 상자에 인스턴스 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-117">If you want to use the default SQL Server instance for that store select **Default Instance**; otherwise select **Named Instance** and enter the instance name in the **Named Instance** box.</span></span>
    
    <span data-ttu-id="bcb4d-118">**속성 편집** 대화 상자에는 모니터링 데이터베이스에 대 한 sql 미러를 만들 수 있는 옵션이 제공 됩니다 (SQL 미러를 통해 모니터링 데이터베이스의 복사본 두 개, 모니터링 저장소 컴퓨터에 저장 된 복사본 한 개, SQL 미러 컴퓨터에는 한 부만 유지 관리) 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-118">The **Edit Properties** dialog box also gives you the option of creating a SQL mirror for your monitoring database (a SQL mirror enables you to maintain two copies of your monitoring database, one copy stored on the monitoring store computer and the other on the SQL mirror computer).</span></span> <span data-ttu-id="bcb4d-119">미러링 기능을 사용 하도록 설정 하려면 해당**SQL 인스턴스가 미러링 관계에 있는** T를 선택 하 고 **미러링 포트 번호** 상자에 미러 서버의 포트 번호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-119">To enable mirroring, select T**his SQL instance is in mirroring relation** and enter the port number for the mirror server in the **Mirroring port number** box.</span></span>

7.  <span data-ttu-id="bcb4d-120">**속성 편집** 대화 상자에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-120">In the **Edit Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="bcb4d-121">모니터링 저장소를 프런트 엔드 풀에 연결한 후에는 변경 내용이 적용 되기 전에 새 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-121">After associating the monitoring store with a Front End pool you must publish the new topology before the changes take effect.</span></span> <span data-ttu-id="bcb4d-122">새 토폴로지를 게시 하려면 토폴로지 작성기에서 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-122">To publish your new topology, complete the following steps in Topology Builder:</span></span>

1.  <span data-ttu-id="bcb4d-123">**동작**을 클릭 하 고 **토폴로지**를 가리킨 다음 **게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-123">Click **Action**, point to **Topology**, and then click **Publish**.</span></span>

2.  <span data-ttu-id="bcb4d-124">토폴로지 게시 마법사의 **토폴로지 게시** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-124">In the Publish Topology wizard, on the **Publish the topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="bcb4d-125">**게시 마법사 완료** 페이지에서 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-125">On the **Publishing wizard complete** page, click **Finish**.</span></span>

<span data-ttu-id="bcb4d-126">토폴로지가 게시 된 후 모니터링 저장소를 호스팅할 컴퓨터에 모니터링 데이터베이스를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-126">After the topology has been published you can then install the monitoring database on the computer that will host the monitoring store.</span></span> <span data-ttu-id="bcb4d-127">모니터링 데이터베이스는 Lync Server 관리 셸 및 Windows PowerShell을 사용 하 여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-127">The monitoring database can be installed by using the Lync Server Management Shell and Windows PowerShell.</span></span> <span data-ttu-id="bcb4d-128">로컬에서 데이터베이스를 설치 하려면 (즉, Lync Server Management Shell을 실행 중인 컴퓨터에 데이터베이스를 설치 하려면) 해당 컴퓨터에서 관리 셸을 시작 하 고 다음 명령을 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-128">To install the database locally (that is, to install the database on the same computer where you are running the Lync Server Management Shell), start the Management Shell on the appropriate computer, then type in the following command and press ENTER:</span></span>

    Install-CsDatabase -LocalDatabases

<span data-ttu-id="bcb4d-129">앞의 명령을 실행 하는 경우, 설치-CsDatabase는 현재 Lync Server 토폴로지를 읽고, 로컬 컴퓨터에 설치 해야 할 데이터베이스를 결정 한 다음 해당 데이터베이스를 자동으로 설치 및 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-129">When you run the preceding command, Install-CsDatabase will read the current Lync Server topology, determine which databases need to be installed on the local computer, and then automatically install and configure each of those databases.</span></span>

<span data-ttu-id="bcb4d-130">원격 컴퓨터 (즉, 관리 셸이 실행 되는 컴퓨터가 아닌 컴퓨터)에 데이터베이스를 설치 하려면 최소 두 개의 매개 변수, ConfiguredDatabases 매개 변수 및 SqlServerFqdn 매개 변수를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-130">To install the database on a remote computer (that is, a computer other than the computer where the Management Shell is running) you must include at least two parameters: the ConfiguredDatabases parameter and the SqlServerFqdn parameter.</span></span> <span data-ttu-id="bcb4d-131">이러한 매개 변수는 Lync Server 토폴로지를 검색 하 고 SqlServerFqdn 매개 변수로 지정 된 컴퓨터에 필요한 데이터베이스를 설치 및 구성 하는 데 설치-CsDatabase cmdlet에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-131">These parameters tell the Install-CsDatabase cmdlet to retrieve the Lync Server topology and then install and configure the required databases on the computer specified by the SqlServerFqdn parameter.</span></span> <span data-ttu-id="bcb4d-132">SqlServerFqdn 매개 변수는 데이터베이스를 설치할 컴퓨터의 정규화 된 도메인 이름을 나타내는 매개 변수 값을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-132">The SqlServerFqdn parameter must use a parameter value representing the fully qualified domain name of the computer where the databases are to be installed.</span></span>

<span data-ttu-id="bcb4d-133">예를 들어이 명령은 컴퓨터 atl-sql-001.litwareinc.com에 모니터링 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-133">For example, this command installs the monitoring database on the computer atl-sql-001.litwareinc.com:</span></span>

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

<span data-ttu-id="bcb4d-134">또는 모니터링 저장소를 호스트 하는 컴퓨터에서 Lync Server 배포 마법사를 실행 하 여 모니터링 데이터베이스를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-134">Alternatively, you can install the monitoring database by running the Lync Server Deployment Wizard on the computer that will host the monitoring store.</span></span> <span data-ttu-id="bcb4d-135">이렇게 하려면 해당 컴퓨터에 로그온 하 고 다음 절차를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-135">To do this, log on to the appropriate computer and complete the following procedure:</span></span>

1.  <span data-ttu-id="bcb4d-136">**시작**을 클릭 하 고 **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 배포 마법사**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-136">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="bcb4d-137">배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-137">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="bcb4d-138">**배포** 페이지의 **2 단계: Lync Server 구성 요소 설정 또는 제거**에서 **다시 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-138">On the **Deploy** page, under **Step 2: Setup or Remove Lync Server Components**, click **Run Again**.</span></span>

4.  <span data-ttu-id="bcb4d-139">Lync Server 구성 요소 설정 마법사의 **Lync server 구성 요소 설정** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-139">In the Setup Lync Server components wizard, on the **Setup Lync Server components** page, click **Next**.</span></span>

5.  <span data-ttu-id="bcb4d-140">**MSIs에 경로 지정** 페이지에서 파일 ocx의 경로를 입력 합니다. Msi (Lync Server 설치 미디어에 포함 된 파일)로 이동한 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-140">On the **Specify path to MSIs** page, type the path to the file Ocscore.msi (a file included with your Lync Server installation media) and then click **Next**.</span></span>

6.  <span data-ttu-id="bcb4d-141">**명령 실행** 페이지에서 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcb4d-141">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="bcb4d-142">필요한 모든 Lync Server 서비스가 시작 되었는지 확인 하려면 제목 아래에서 **실행** 을 클릭 합니다 **. 4 단계:** **배포** 페이지에서 서비스 시작</span><span class="sxs-lookup"><span data-stu-id="bcb4d-142">To ensure that all the required Lync Server services have started, click **Run** under the heading **Step 4: Start Services** on the **Deploy** page</span></span>

</div>

<span> </span>

</div>

</div>

</div>

