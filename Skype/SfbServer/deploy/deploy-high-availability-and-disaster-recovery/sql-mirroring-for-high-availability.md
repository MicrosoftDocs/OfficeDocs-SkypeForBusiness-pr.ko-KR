---
title: 비즈니스 SQL 2015에서 백 엔드 서버 고가용성을 위한 미러링 배포
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
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: SQL 미러링을 배포할 수 있으려면 서버에서 최소한 SQL Server 2008 R2를 실행해야 합니다. 이 버전은 기본, 미러 및 미러링 모니터 서버 등 모든 관련 서버에서 실행해야 합니다. 자세한 내용은 SQL Server 2008 서비스 팩 1용 누적 업데이트 패키지 9를 참조합니다.
ms.openlocfilehash: 38c3e749b39cd510623232e9f29ace03a1c19f6c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100724"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="6d422-105">비즈니스 SQL 2015에서 백 엔드 서버 고가용성을 위한 미러링 배포</span><span class="sxs-lookup"><span data-stu-id="6d422-105">Deploy SQL mirroring for Back End Server high availability in Skype for Business server 2015</span></span>


<span data-ttu-id="6d422-106">SQL 미러링을 배포할 수 있으려면 서버에서 최소한 SQL Server 2008 R2를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-106">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="6d422-107">이 버전은 기본, 미러 및 미러링 모니터 서버 등 모든 관련 서버에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-107">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="6d422-108">자세한 내용은 [SQL Server 2008 서비스 팩 1용 누적 업데이트 패키지 9를 참조합니다.](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921)</span><span class="sxs-lookup"><span data-stu-id="6d422-108">For details, see [Cumulative update package 9 for SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span></span>

<span data-ttu-id="6d422-109">일반적으로 미러링 모니터 서버가 포함된 두 개의 백 엔드 서버 사이에 SQL 미러링을 설정하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-109">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

- <span data-ttu-id="6d422-110">기본 서버의 서버 버전은 SQL Server 미러링을 SQL 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-110">The primary server's version of SQL Server must support SQL mirroring.</span></span>

- <span data-ttu-id="6d422-111">기본, 미러, 미러링 모니터 서버(배포된 경우)는 모두 SQL Server 버전이 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-111">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

- <span data-ttu-id="6d422-p103">기본 및 미러는 SQL Server의 에디션이 동일해야 합니다. 미러링 모니터 서버는 에디션이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-p103">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="6d422-114">미러링 SQL 지원되는 버전과 SQL 모범 사례에 대한 자세한 내용은 데이터베이스 미러링 미러링 [목차를 참조합니다.](/sql/database-engine/database-mirroring/database-mirroring-witness)</span><span class="sxs-lookup"><span data-stu-id="6d422-114">For SQL best practices in terms of what SQL versions are supported for a Witness role, see [Database Mirroring Witness](/sql/database-engine/database-mirroring/database-mirroring-witness).</span></span>

<span data-ttu-id="6d422-115">토폴로지 작성기에서 토폴로지 SQL 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-115">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="6d422-116">토폴로지 작성기에서 데이터베이스를 미러링할 옵션을 선택하고, 토폴로지 작성기에서 토폴로지 게시 시 미러링(원하는 경우 미러링 보기 설정 포함)을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-116">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="6d422-117">미러를 설정하거나 제거하는 것과 동시에 미러링 모니터 서버도 설정하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-117">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="6d422-118">미러링 모니터 서버만 배포하거나 제거할 수 있는 별도의 명령은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-118">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="6d422-119">서버 미러링을 구성하려면 먼저 SQL 데이터베이스 권한을 올바르게 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-119">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="6d422-120">자세한 내용은 Set Up Login Accounts for Database Mirroring or [AlwaysOn Availability Groups (SQL Server)을 참조합니다.](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability)</span><span class="sxs-lookup"><span data-stu-id="6d422-120">For details, see [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability).</span></span>

<span data-ttu-id="6d422-121">SQL 미러링을 사용할 경우 데이터베이스 복구 모드는 항상 **전체** 로 설정되므로 트랜잭션 로그 크기를 자세히 모니터링하고 백 엔드 서버의 디스크 공간이 부족해지지 않도록 정기적으로 트랜잭션 로그를 백업해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-121">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers.</span></span> <span data-ttu-id="6d422-122">트랜잭션 로그 백업의 빈도는 로그 증가 속도에 따라 달라지며, 이는 다시 프런트 엔드 풀에서의 사용자 활동으로 인해 발생하는 데이터베이스 트랜잭션에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-122">The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool.</span></span> <span data-ttu-id="6d422-123">그에 따라 계획을 수립할 수 있도록 배포 작업 부하에 대해 트랜잭션 로그 증가가 예상되는 정도를 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-123">We recommend that you determine how much transaction log growth is expected for your deployment workload so that you can do the planning accordingly.</span></span> <span data-ttu-id="6d422-124">다음 문서에서는 SQL 백업 및 로그 관리에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-124">The following articles provide additional information on SQL backup and log management:</span></span>

- [<span data-ttu-id="6d422-125">데이터베이스 복구 모델</span><span class="sxs-lookup"><span data-stu-id="6d422-125">Database recovery models</span></span>](/sql/relational-databases/backup-restore/recovery-models-sql-server)

- [<span data-ttu-id="6d422-126">백업 개요</span><span class="sxs-lookup"><span data-stu-id="6d422-126">Backup overview</span></span>](/sql/relational-databases/backup-restore/backup-overview-sql-server)

- [<span data-ttu-id="6d422-127">백업 트랜잭션 로그</span><span class="sxs-lookup"><span data-stu-id="6d422-127">Backup transaction log</span></span>](/sql/relational-databases/backup-restore/back-up-a-transaction-log-sql-server)

<span data-ttu-id="6d422-128">SQL 미러링을 사용하면 풀을 만들 때 또는 풀이 이미 만들어진 후에 미러링에 대한 토폴로지를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-128">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d422-129">토폴로지 작성기 또는 cmdlet을 사용하여 SQL 미러링을 설정 및 제거하는 것은 기본 서버, 미러 및 미러링 카메라(필요한 경우) 서버가 모두 동일한 도메인에 속하는 경우만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-129">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="6d422-130">다른 도메인에 있는 서버 간에 SQL 미러링을 설정하려는 경우에는 SQL Server 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6d422-130">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d422-131">백 엔드 데이터베이스 미러링 관계를 변경할 때마다 풀에서 모든 프런트 엔드 서버를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-131">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span> <span data-ttu-id="6d422-132">> 미러의 위치 변경과 같은 미러링 변경의 경우 토폴로지 작성기에서 다음 세 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-132">> For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span>

1. <span data-ttu-id="6d422-133">이전 미러 서버에서 미러링을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-133">Remove mirroring from the old mirror server.</span></span>

2. <span data-ttu-id="6d422-134">새 미러 서버에 미러링을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-134">Add mirroring to the new mirror server.</span></span>

3. <span data-ttu-id="6d422-135">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-135">Publish the topology.</span></span>

> [!NOTE]
> <span data-ttu-id="6d422-136">미러 파일을 기록하려면 파일 공유를 만들어야 합니다. 에이전트 및 SQL Server SQL 실행 중인 서비스는 읽기/쓰기 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-136">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="6d422-137">SQL Server 서비스가 네트워크 서비스의 컨텍스트에서 실행되는 경우 주 서버와 미러 서버의 \<Domain\> \\<SQLSERVERNAME $을 공유 권한에 SQL 수 \> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-137">If the SQL Server service is running under the context of Network Service, you can add \<Domain\>\\<SQLSERVERNAME\>$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="6d422-138">$는 컴퓨터 계정으로 식별하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-138">The $ is important to identify that this is a computer account.</span></span>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="6d422-139">토폴로지 SQL 풀을 만드는 동안 미러링을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-139">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1. <span data-ttu-id="6d422-140">**SQL 저장소 정의** 페이지에서 **SQL 저장소** 상자 옆에 있는 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-140">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2. <span data-ttu-id="6d422-141">**새 SQL 저장소 정의** 페이지에서 기본 저장소를 지정하고 **이 SQL 인스턴스가 미러링 관계에 있음** 을 선택하고, SQL 미러링 포트 번호(기본값 5022)를 지정한 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-141">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3. <span data-ttu-id="6d422-142">다시 **SQL 저장소 정의** 페이지에서 **SQL 저장소 미러링 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-142">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4. <span data-ttu-id="6d422-p110">**새 SQL 저장소 정의** 페이지에서 미러로 사용할 SQL 저장소를 지정합니다. **이 SQL 인스턴스가 미러링 관계에 있음** 을 선택하고 포트 번호(기본값 5022)를 지정한 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-p110">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="6d422-145">이 미러에 대해 미러링 모니터 서버를 사용하려는 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-145">If you want a witness for this mirror, do the following:</span></span>

    <span data-ttu-id="6d422-146">a.</span><span class="sxs-lookup"><span data-stu-id="6d422-146">a.</span></span> <span data-ttu-id="6d422-147">**SQL 미러링 모니터 서버를 사용하여 자동 장애 조치(Failover) 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-147">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>

    <span data-ttu-id="6d422-148">b.</span><span class="sxs-lookup"><span data-stu-id="6d422-148">b.</span></span> <span data-ttu-id="6d422-149">**SQL 저장소 정의** 페이지에서 **SQL 미러링 모니터 서버를 사용하여 자동 장애 조치(Failover) 사용** 을 선택하고 미러링 모니터 서버로 사용할 SQL 저장소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-149">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>

    <span data-ttu-id="6d422-150">c.</span><span class="sxs-lookup"><span data-stu-id="6d422-150">c.</span></span> <span data-ttu-id="6d422-151">포트 번호(기본값 7022)를 지정하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-151">Specify the port number (the default is 7022) and click **OK**.</span></span>

6. <span data-ttu-id="6d422-152">프런트 엔드 풀 및 토폴로지의 다른 모든 역할 정의를 완료한 후 토폴로지 작성기에서 토폴로지 게시를 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-152">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="6d422-153">토폴로지가 게시되면 중앙 관리 저장소를 호스팅하는 프런트 엔드 풀에 SQL 미러링을 사용하도록 설정한 경우 기본 및 미러 저장소 데이터베이스를 SQL 옵션이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-153">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>

    <span data-ttu-id="6d422-154">**설정** 을 클릭하고 미러링 백업에 대한 파일 공유로 사용할 경로를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-154">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>

    <span data-ttu-id="6d422-p115">**확인** 을 클릭한 후 **다음** 을 클릭하여 데이터베이스를 만들고 토폴로지를 게시합니다. 미러링 및 미러링 모니터 서버(지정된 경우)가 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-p115">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="6d422-157">토폴로지 작성기에서 기존 풀의 속성을 편집하여 토폴로지 SQL 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-157">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="6d422-158">토폴로지 SQL 기존 프런트 엔드 풀에 미러링을 추가하는 방법</span><span class="sxs-lookup"><span data-stu-id="6d422-158">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1. <span data-ttu-id="6d422-159">토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭한 다음 속성 **편집 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6d422-159">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2. <span data-ttu-id="6d422-160">**SQL 저장소 미러링 사용** 을 선택한 후 **미러링 SQL 저장소** 옆에서 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-160">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3. <span data-ttu-id="6d422-161">미러로 사용하려는 SQL 저장소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-161">Specify the SQL store that you want to use as the mirror.</span></span>

4. <span data-ttu-id="6d422-162">**이 SQL 인스턴스가 미러링 관계에 있음** 을 선택하고 SQL 미러링 포트 번호(기본 포트는 5022)를 지정한 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-162">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="6d422-163">미러링 모니터 서버를 구성하려면 **SQL 미러링 모니터 서버를 사용하여 자동 장애 조치(Failover) 사용** 을 선택하고 **새로 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-163">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6. <span data-ttu-id="6d422-164">미러링 모니터 서버로 사용하려는 SQL 저장소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-164">Specify the SQL store that you want to use as the witness.</span></span>

7. <span data-ttu-id="6d422-165">**이 SQL 인스턴스가 미러링 관계에 있음** 을 선택하고 SQL 미러링 포트 번호(기본 포트는 7022)를 지정한 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-165">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8. <span data-ttu-id="6d422-166">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-166">Click **OK**.</span></span>

9. <span data-ttu-id="6d422-p116">토폴로지를 게시합니다. 이렇게 하면 데이터베이스를 설치하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-p116">Publish the topology. When you do so, you will be prompted to install the database.</span></span>

    <span data-ttu-id="6d422-169">토폴로지 게시 프로세스 중에 파일 공유 경로를 정의할지 묻는 요청이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-169">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="6d422-170">SQL 미러링에 참여하는 서버는 미러를 설정하려면 이 파일 공유에 대한 읽기/쓰기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-170">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="6d422-171">그런 후 다음 절차로 이동하려면 먼저 데이터베이스를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-171">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="6d422-172">SQL 미러링을 설정할 때는 다음 사항에 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-172">You should keep the following in mind when setting up SQL mirroring:</span></span>

- <span data-ttu-id="6d422-173">미러링 끝점이 존재하는 경우 해당 위치에 정의된 포트를 사용하여 다시 사용되며, 사용자가 토폴로지에 지정한 포트는 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-173">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

- <span data-ttu-id="6d422-p118">다른 SQL 인스턴스에 대한 포트를 포함하여 동일 서버의 다른 응용 프로그램에 이미 할당된 포트는 설치된 현재 SQL 인스턴스에 대해 사용하지 않아야 합니다. 이러한 제한은 동일한 서버에 SQL 인스턴스를 두 개 이상 설치한 경우 이러한 인스턴스가 미러링에 대해 동일한 포트를 사용하지 않아야 함을 의미합니다. 자세한 내용은 다음 문서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6d422-p118">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>

  - [<span data-ttu-id="6d422-177">서버 네트워크 주소 지정(데이터베이스 미러링)</span><span class="sxs-lookup"><span data-stu-id="6d422-177">Specify a Server Network Address (Database Mirroring)</span></span>](/sql/database-engine/database-mirroring/specify-a-server-network-address-database-mirroring)

  - [<span data-ttu-id="6d422-178">데이터베이스 미러링 끝점(SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6d422-178">The Database Mirroring Endpoint (SQL Server)</span></span>](/sql/database-engine/database-mirroring/the-database-mirroring-endpoint-sql-server)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="6d422-179">비즈니스용 Skype 서버 2015 관리 셸 cmdlet을 사용하여 미러링 SQL 설정</span><span class="sxs-lookup"><span data-stu-id="6d422-179">Using Skype for Business Server 2015 Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="6d422-180">미러링을 설정하는 가장 쉬운 방법은 토폴로지 작성기 사용이지만 cmdlet을 사용하여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-180">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1. <span data-ttu-id="6d422-181">비즈니스용 Skype 서버 2015 관리 셸 창을 열고 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-181">Open a Skype for Business Server 2015 Management Shell window and run the following cmdlet:</span></span>

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    <span data-ttu-id="6d422-182">예:</span><span class="sxs-lookup"><span data-stu-id="6d422-182">For example:</span></span>

   ```powershell
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    <span data-ttu-id="6d422-183">다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-183">You will see the following:</span></span>

   <pre>
   Database Name:rtcxds
        Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf
         Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:rtcshared
        Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf
         Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:rtcab
        Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf
         Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:rgsconfig
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:rgsdyn
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:cpsdyn
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:xds
        Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf
         Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:lis
        Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf
         Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
   [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
   </pre>

2. <span data-ttu-id="6d422-184">다음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-184">Verify the following:</span></span>

    - <span data-ttu-id="6d422-185">Windows 방화벽이 기본 SQL Server e04-ocs.los_a.lsipt.local\rtc에서 사용하도록 설정된 경우 방화벽을 통해 포트 5022에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-185">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="6d422-186">Windows 방화벽이 미러 SQL Server K16-ocs.los_a.lsipt.local\rtc에서 사용하도록 설정된 경우 방화벽을 통해 포트 5022에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-186">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="6d422-187">Windows 방화벽이 미러링 모니터 서버 AB14-lct.los_a.lsipt.local\rtc에서 사용하도록 설정된 경우 방화벽을 통해 포트 7022에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-187">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los_a.lsipt.local\rtc.</span></span>

   - <span data-ttu-id="6d422-188">모든 SQL 및 미러 SQL 서버에서 SQL 서버를 실행하는 계정에 파일 공유 \\ E04-OCS\csdatabackup에 대한 읽기/쓰기 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-188">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\E04-OCS\csdatabackup</span></span>

   - <span data-ttu-id="6d422-p119">WMI(Windows Management Instrumentation) 공급자가 이러한 모든 서버에서 실행되고 있는지 확인합니다. 이 cmdlet은 이 공급자를 사용해서 모든 기본, 미러 및 미러링 모니터 서버에서 실행되는 SQL Server 서비스에 대한 계정 정보를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-p119">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>

   - <span data-ttu-id="6d422-191">이 cmdlet을 실행 중인 계정에 모든 미러 서버에 대한 데이터 및 로그 파일의 폴더를 만들 수 있는 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-191">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>

   - <span data-ttu-id="6d422-p120">SQL 인스턴스가 실행을 위해 사용하는 사용자 계정에 파일 공유에 대한 읽기/쓰기 권한이 있어야 합니다. 파일 공유가 다른 서버에 있고 SQL 인스턴스가 로컬 시스템 계정으로 실행되는 경우에는 해당 SQL 인스턴스를 호스팅하는 서버에 파일 공유 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-p120">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3. <span data-ttu-id="6d422-194">A를 입력한 후 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-194">Type A and press ENTER.</span></span>

    <span data-ttu-id="6d422-195">미러링이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-195">The mirroring will be configured.</span></span>

    <span data-ttu-id="6d422-196">**Install-CsMirrorDatabase는** 미러를 설치하고 기본 데이터베이스 저장소에 있는 모든 데이터베이스에 SQL 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-196">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="6d422-197">특정 데이터베이스에 대한 미러링을 구성하려는 경우 -DatabaseType 옵션을 사용할 수도 있습니다. 또는 일부를 제외한 모든 데이터베이스에 대해 미러링을 구성하려는 경우 제외할 데이터베이스 이름 목록과 함께 -ExcludeDatabaseList 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-197">If you want to configure mirroring for only specific databases, you can use the -DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

    <span data-ttu-id="6d422-198">예를 들어 **Install-CsMirrorDatabase** 에 다음 옵션을 추가하면 rtcab 및 rtcxds를 제외한 모든 데이터베이스가 미러링됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-198">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

    `-ExcludeDatabaseList rtcab,rtcxds`

   <span data-ttu-id="6d422-199">예를 들어 **Install-CsMirrorDatabase** 에 다음 옵션을 추가하면 rtcab, rtcshared 및 rtcxds 데이터베이스만 미러링됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-199">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="6d422-200">SQL 미러링 제거 또는 변경</span><span class="sxs-lookup"><span data-stu-id="6d422-200">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="6d422-p122">토폴로지 작성기에서 풀에 대한 SQL 미러링을 제거하려면 먼저 SQL Server에서 미러를 제거하는 cmdlet을 사용해야 합니다. 그런 후 토폴로지 작성기를 사용해서 토폴로지에서 미러를 제거할 수 있습니다. SQL Server에서 미러를 제거하려면 다음 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-p122">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

<span data-ttu-id="6d422-204">예를 들어 User 데이터베이스에 대한 미러링을 제거하고 데이터베이스를 삭제하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-204">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

<span data-ttu-id="6d422-205">이 옵션을 사용하면 영향을 받는 데이터베이스가 미러에서  `-DropExistingDatabasesOnMirror` 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-205">The  `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="6d422-206">그런 후 토폴로지에서 미러를 제거하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-206">Then, to remove the mirror from the topology, do the following:</span></span>

1. <span data-ttu-id="6d422-207">토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭하고 **속성 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="6d422-208">**SQL 저장소 미러링 사용** 의 선택을 취소하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-208">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3. <span data-ttu-id="6d422-209">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-209">Publish the topology.</span></span>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="6d422-210">미러링 모니터 서버 제거</span><span class="sxs-lookup"><span data-stu-id="6d422-210">Removing a Mirroring Witness</span></span>

<span data-ttu-id="6d422-211">백 엔드 서버 미러링 구성에서 미러링을 제거해야 하는 경우 이 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-211">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1. <span data-ttu-id="6d422-212">토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭하고 **속성 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-212">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="6d422-213">**SQL Server 미러링 모니터 서버를 사용하여 자동 장애 조치(Failover) 사용** 의 선택을 취소하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-213">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3. <span data-ttu-id="6d422-214">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-214">Publish the topology.</span></span>

    <span data-ttu-id="6d422-215">토폴로지 게시 후 토폴로지 작성기에서 다음을 포함하는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-215">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    <span data-ttu-id="6d422-216">그러나 이 단계를 따르지 말고 전체 미러링 구성을 제거하기 위해  `Uninstall-CsMirrorDatabase` 입력하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d422-216">However, do not follow that step, and do not type  `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4. <span data-ttu-id="6d422-217">서버 구성에서 미러링 SQL Server 제거하려면 [Remove the Witness from a Database Mirroring Session (SQL Server)의 지침을 따릅니다.](/sql/database-engine/database-mirroring/remove-the-witness-from-a-database-mirroring-session-sql-server)</span><span class="sxs-lookup"><span data-stu-id="6d422-217">To remove just the witness from the SQL Server configuration, follow the instructions in [Remove the Witness from a Database Mirroring Session (SQL Server)](/sql/database-engine/database-mirroring/remove-the-witness-from-a-database-mirroring-session-sql-server).</span></span>