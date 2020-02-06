---
title: 비즈니스용 Skype 서버 2015에서 백 엔드 서버에 대 한 SQL 미러링 배포 높은 가용성을 제공 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: SQL 미러링을 배포할 수 있으려면 서버에서 최소 SQL Server 2008 R2를 실행 해야 합니다. 이 버전은 모든 관련 서버 (기본, 미러, 미러링 모니터)에서 실행 되어야 합니다. 자세한 내용은 SQL Server 2008 서비스 팩 1에 대 한 누적 업데이트 패키지 9를 참조 하세요.
ms.openlocfilehash: 2be6b59d294db6a74ffe902648511658a07242ca
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790066"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="6e0e9-105">비즈니스용 Skype 서버 2015에서 백 엔드 서버에 대 한 SQL 미러링 배포 높은 가용성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-105">Deploy SQL mirroring for Back End Server high availability in Skype for Business server 2015</span></span>


<span data-ttu-id="6e0e9-106">SQL 미러링을 배포할 수 있으려면 서버에서 최소 SQL Server 2008 R2를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-106">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="6e0e9-107">이 버전은 모든 관련 서버 (기본, 미러, 미러링 모니터)에서 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-107">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="6e0e9-108">자세한 내용은 [SQL Server 2008 서비스 팩 1에 대 한 누적 업데이트 패키지 9](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-108">For details, see [Cumulative update package 9 for SQL Server 2008 Service Pack 1](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span></span>

<span data-ttu-id="6e0e9-109">일반적으로 미러링 모니터로 두 백 엔드 서버 간에 SQL 미러링을 설정 하려면 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-109">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

- <span data-ttu-id="6e0e9-110">주 서버의 SQL Server 버전은 SQL 미러링을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-110">The primary server's version of SQL Server must support SQL mirroring.</span></span>

- <span data-ttu-id="6e0e9-111">기본, 미러, 미러링 모니터 (배포 된 경우)는 동일한 버전의 SQL Server를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-111">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

- <span data-ttu-id="6e0e9-112">기본 및 미러에는 동일한 버전의 SQL Server가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-112">The primary and the mirror must have the same edition of SQL Server.</span></span> <span data-ttu-id="6e0e9-113">미러링 모니터 서버에 다른 버전이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-113">The witness may have a different edition.</span></span>

<span data-ttu-id="6e0e9-114">미러링 모니터 역할에 대해 지원 되는 SQL 버전에 대 한 SQL 모범 사례는 [데이터베이스 미러링 감시](https://go.microsoft.com/fwlink/p/?LinkId=247345)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-114">For SQL best practices in terms of what SQL versions are supported for a Witness role, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span></span>

<span data-ttu-id="6e0e9-115">토폴로지 작성기를 사용 하 여 SQL 미러링을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-115">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="6e0e9-116">토폴로지 작성기에서 데이터베이스를 미러링 하는 옵션을 선택 하면 토폴로지를 게시할 때 토폴로지 작성기에서 미러링 (미러링 모니터 서버 설정 포함)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-116">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="6e0e9-117">미러를 설정 하거나 제거할 때와 동시에 미러링 모니터를 설정 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-117">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="6e0e9-118">미러링 모니터만 배포 하거나 제거 하는 별도의 명령은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-118">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="6e0e9-119">서버 미러링을 구성 하려면 먼저 SQL 데이터베이스 권한을 올바르게 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-119">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="6e0e9-120">자세한 내용은 [데이터베이스 미러링 또는 AlwaysOn 가용성 그룹 (SQL Server)에 대 한 로그인 계정 설정을](https://go.microsoft.com/fwlink/p/?LinkId=268454)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-120">For details, see [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>

<span data-ttu-id="6e0e9-121">SQL 미러링에서는 데이터베이스 복구 모드가 항상 **Full**로 설정 되며,이는 백 엔드 서버의 디스크 공간 부족을 방지 하기 위해 트랜잭션 로그 크기를 면밀 하 게 모니터링 하 고 트랜잭션 로그를 정기적으로 백업 해야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-121">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers.</span></span> <span data-ttu-id="6e0e9-122">트랜잭션 로그 백업의 빈도는 로그 증가 속도에 따라 다르며,이는 프런트 엔드 풀의 사용자 활동에서 발생 하는 데이터베이스 트랜잭션에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-122">The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool.</span></span> <span data-ttu-id="6e0e9-123">계획을 적절 하 게 수행할 수 있도록 배포 작업 부하에 예상 되는 트랜잭션 로그 성장이 얼마나 되는지 결정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-123">We recommend that you determine how much transaction log growth is expected for your deployment workload so that you can do the planning accordingly.</span></span> <span data-ttu-id="6e0e9-124">다음 문서는 SQL 백업 및 로그 관리에 대 한 추가 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-124">The following articles provide additional information on SQL backup and log management:</span></span>

- [<span data-ttu-id="6e0e9-125">데이터베이스 복구 모델</span><span class="sxs-lookup"><span data-stu-id="6e0e9-125">Database recovery models</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [<span data-ttu-id="6e0e9-126">백업 개요</span><span class="sxs-lookup"><span data-stu-id="6e0e9-126">Backup overview</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [<span data-ttu-id="6e0e9-127">트랜잭션 로그 백업</span><span class="sxs-lookup"><span data-stu-id="6e0e9-127">Backup transaction log</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268452)

<span data-ttu-id="6e0e9-128">SQL 미러링을 사용 하면 풀을 만들 때 또는 풀이 이미 만들어진 후에 미러링에 대 한 토폴로지를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-128">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e0e9-129">토폴로지 작성기 또는 cmdlet을 사용 하 여 SQL 미러링을 설정 및 제거 하는 것은 주, 미러, 미러링 모니터 (원하는 경우) 서버가 모두 동일한 도메인에 속해 있는 경우에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-129">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="6e0e9-130">다른 도메인의 서버 간에 SQL 미러링을 설정 하려면 SQL Server 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-130">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e0e9-131">백 엔드 데이터베이스 미러링 관계를 변경할 때마다 풀의 모든 프런트 엔드 서버를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-131">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span> <span data-ttu-id="6e0e9-132">미러링 변경 내용에 대 한 > (예: 미러 위치 변경) 토폴로지 작성기를 사용 하 여 다음 세 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-132">> For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span>

1. <span data-ttu-id="6e0e9-133">이전 미러 서버에서 미러링을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-133">Remove mirroring from the old mirror server.</span></span>

2. <span data-ttu-id="6e0e9-134">새 미러 서버에 미러링을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-134">Add mirroring to the new mirror server.</span></span>

3. <span data-ttu-id="6e0e9-135">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-135">Publish the topology.</span></span>

> [!NOTE]
> <span data-ttu-id="6e0e9-136">쓰기 파일에 대 한 파일 공유를 만들어야 하며, SQL Server 및 SQL 에이전트에서 실행 중인 서비스에 읽기/쓰기 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-136">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="6e0e9-137">Sql Server 서비스가 네트워크 서비스의 컨텍스트에서 실행 되는 경우 주 서버와 미러 SQL server \<의\> \\ 도메인<sqlservername\>$을 공유 사용 권한으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-137">If the SQL Server service is running under the context of Network Service, you can add \<Domain\>\\<SQLSERVERNAME\>$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="6e0e9-138">$는 컴퓨터 계정 임을 식별 하는 데 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-138">The $ is important to identify that this is a computer account.</span></span>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="6e0e9-139">토폴로지 작성기에서 풀을 만드는 동안 SQL 미러링을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="6e0e9-139">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1. <span data-ttu-id="6e0e9-140">**Sql 저장소 정의** 페이지에서 **sql 스토어** 상자 옆에 있는 **새로 만들기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-140">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2. <span data-ttu-id="6e0e9-141">**새 SQL Store 정의** 페이지에서 기본 저장소를 지정 하 고, **이 sql 인스턴스가 미러링 관계에 있는 경우**를 선택 하 고, sql 미러링 포트 번호 (기본값 5022)를 지정한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-141">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3. <span data-ttu-id="6e0e9-142">다시 **sql 저장소 정의** 페이지에서 **Sql 저장소 미러링 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-142">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4. <span data-ttu-id="6e0e9-143">**새 Sql 저장소 정의** 페이지에서 미러로 사용할 SQL 저장소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-143">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror.</span></span> <span data-ttu-id="6e0e9-144">**이 SQL 인스턴스는 미러링 관계에 있으며**, 포트 번호 (기본값 5022)를 지정한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-144">Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="6e0e9-145">이 미러에 미러링 모니터를 원하는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-145">If you want a witness for this mirror, do the following:</span></span>

    <span data-ttu-id="6e0e9-146">에서.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-146">a.</span></span> <span data-ttu-id="6e0e9-147">**SQL 미러링 감시 사용을 선택 하 여 자동 장애 조치를 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-147">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>

    <span data-ttu-id="6e0e9-148">b.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-148">b.</span></span> <span data-ttu-id="6e0e9-149">**Sql Store 정의** 페이지에서 **sql 미러링 미러링 모니터 사용을 선택 하 여 자동 장애 조치 (failover)를 설정 하**고 미러링 모니터로 사용할 sql 저장소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-149">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>

    <span data-ttu-id="6e0e9-150">c.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-150">c.</span></span> <span data-ttu-id="6e0e9-151">포트 번호 (기본값 7022)를 지정 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-151">Specify the port number (the default is 7022) and click **OK**.</span></span>

6. <span data-ttu-id="6e0e9-152">프런트 엔드 풀 및 다른 모든 역할을 토폴로지에 대해 정의한 후 토폴로지 작성기를 사용 하 여 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-152">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="6e0e9-153">토폴로지가 게시 되 면 중앙 관리 저장소를 호스트 하는 프런트 엔드 풀에 SQL 미러링이 설정 되어 있는 경우 기본 및 미러 SQL 저장소 데이터베이스를 모두 만드는 옵션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-153">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>

    <span data-ttu-id="6e0e9-154">**설정을**클릭 하 고 미러링 백업에 대 한 파일 공유로 사용할 경로를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-154">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>

    <span data-ttu-id="6e0e9-155">**확인** 을 클릭 한 후 **다음** 을 클릭 하 여 데이터베이스를 만들고 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-155">Click **OK** and then **Next** to create the databases and publish the topology.</span></span> <span data-ttu-id="6e0e9-156">미러링과 미러링 모니터 (지정 된 경우)가 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-156">The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="6e0e9-157">토폴로지 작성기를 사용 하 여 이미 존재 하는 풀의 속성을 편집 하 여 SQL 미러링을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-157">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="6e0e9-158">토폴로지 작성기에서 기존 프런트 엔드 풀에 SQL 미러링을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="6e0e9-158">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1. <span data-ttu-id="6e0e9-159">토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-159">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2. <span data-ttu-id="6e0e9-160">**Sql 저장소 미러링 사용**을 선택 하 고 **sql 저장소 미러링**옆에 있는 **새로 만들기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-160">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3. <span data-ttu-id="6e0e9-161">미러로 사용할 SQL 저장소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-161">Specify the SQL store that you want to use as the mirror.</span></span>

4. <span data-ttu-id="6e0e9-162">**이 sql 인스턴스는 미러링 관계에 있으며**, 기본 포트가 5022 인 sql 미러링 포트 번호를 지정한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-162">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="6e0e9-163">미러링 모니터를 구성 하려면 **SQL 미러링 미러링 모니터 사용을 선택 하 여 자동 장애 조치 (failover)를 사용 하도록 설정**하 고 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-163">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6. <span data-ttu-id="6e0e9-164">미러링 모니터로 사용할 SQL 저장소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-164">Specify the SQL store that you want to use as the witness.</span></span>

7. <span data-ttu-id="6e0e9-165">**이 sql 인스턴스는 미러링 관계에 있으며**, sql 미러링 포트 번호 (기본 포트는 7022)를 지정한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-165">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8. <span data-ttu-id="6e0e9-166">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-166">Click **OK**.</span></span>

9. <span data-ttu-id="6e0e9-167">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-167">Publish the topology.</span></span> <span data-ttu-id="6e0e9-168">이렇게 하면 데이터베이스를 설치 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-168">When you do so, you will be prompted to install the database.</span></span>

    <span data-ttu-id="6e0e9-169">토폴로지 게시 프로세스 중에 파일 공유 경로를 정의 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-169">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="6e0e9-170">미러링에 참여 하는 SQL 서버는 미러를 설정 하기 위해이 파일 공유에 대 한 읽기/쓰기 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-170">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="6e0e9-171">다음 절차를 진행 하기 전에 데이터베이스를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-171">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="6e0e9-172">SQL 미러링을 설정할 때 다음 사항에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-172">You should keep the following in mind when setting up SQL mirroring:</span></span>

- <span data-ttu-id="6e0e9-173">미러링 끝점이 이미 있으면이 끝점을 정의한 포트를 사용 하 여 다시 사용할 수 있으며 토폴로지에 지정 된 것을 무시 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-173">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

- <span data-ttu-id="6e0e9-174">다른 SQL 인스턴스에 대 한 다른 응용 프로그램에 이미 할당 된 모든 포트는 설치 된 SQL 인스턴스에 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-174">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand.</span></span> <span data-ttu-id="6e0e9-175">이는 같은 서버에 둘 이상의 SQL 인스턴스가 설치 되어 있는 경우 미러링에 동일한 포트를 사용 하지 않아야 한다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-175">This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring.</span></span> <span data-ttu-id="6e0e9-176">자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-176">For details, see the following articles:</span></span>

  - [<span data-ttu-id="6e0e9-177">서버 네트워크 주소 (데이터베이스 미러링) 지정</span><span class="sxs-lookup"><span data-stu-id="6e0e9-177">Specify a Server Network Address (Database Mirroring)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [<span data-ttu-id="6e0e9-178">데이터베이스 미러링 끝점 (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6e0e9-178">The Database Mirroring Endpoint (SQL Server)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="6e0e9-179">비즈니스용 Skype Server 2015 관리 셸 Cmdlet을 사용 하 여 SQL 미러링 설정</span><span class="sxs-lookup"><span data-stu-id="6e0e9-179">Using Skype for Business Server 2015 Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="6e0e9-180">미러링을 설정 하는 가장 쉬운 방법은 토폴로지 작성기를 사용 하는 것 이지만, 이렇게 하면 cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-180">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1. <span data-ttu-id="6e0e9-181">비즈니스용 Skype Server 2015 관리 셸 창을 열고 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-181">Open a Skype for Business Server 2015 Management Shell window and run the following cmdlet:</span></span>

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    <span data-ttu-id="6e0e9-182">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-182">For example:</span></span>

   ```powershell
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    <span data-ttu-id="6e0e9-183">다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-183">You will see the following:</span></span>

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

2. <span data-ttu-id="6e0e9-184">다음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-184">Verify the following:</span></span>

    - <span data-ttu-id="6e0e9-185">기본 SQL Server los_a e04에서 Windows 방화벽을 사용 하는 경우 방화벽을 통해 포트 5022에 액세스할 수 있습니다. local\rtc.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-185">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="6e0e9-186">미러 SQL Server K16에서 Windows 방화벽을 사용 하는 경우 방화벽을 통해 포트 5022에 액세스할 수 있습니다. local\rtc.. los_a</span><span class="sxs-lookup"><span data-stu-id="6e0e9-186">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="6e0e9-187">Los_a AB14에서 Windows 방화벽을 사용 하는 경우 방화벽을 통해 포트 7022에 액세스할 수 있습니다. local\rtc.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-187">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los_a.lsipt.local\rtc.</span></span>

   - <span data-ttu-id="6e0e9-188">모든 기본 및 미러 SQL server에서 SQL Server를 실행 하는 계정에는 파일 공유 \\E04-OCS\csdatabackup에 대 한 읽기/쓰기 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-188">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\E04-OCS\csdatabackup</span></span>

   - <span data-ttu-id="6e0e9-189">이러한 모든 서버에서 WMI (Windows Management Instrumentation) 공급자가 실행 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-189">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers.</span></span> <span data-ttu-id="6e0e9-190">Cmdlet은이 공급자를 사용 하 여 모든 주 미러 및 미러링 모니터 서버에서 실행 되는 SQL Server 서비스에 대 한 계정 정보를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-190">The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>

   - <span data-ttu-id="6e0e9-191">이 cmdlet을 실행 하는 계정에 모든 미러 서버의 데이터 및 로그 파일에 대 한 폴더를 만들 수 있는 권한이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-191">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>

   - <span data-ttu-id="6e0e9-192">SQL 인스턴스에서 실행 하는 데 사용 하는 사용자 계정에는 파일 공유에 대 한 읽기/쓰기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-192">Note that the user account that the SQL instance uses to run must have read/write permission to the file share.</span></span> <span data-ttu-id="6e0e9-193">파일 공유가 다른 서버에 있고 SQL 인스턴스가 로컬 시스템 계정을 실행 하는 경우에는 SQL 인스턴스를 호스트 하는 서버에 파일 공유 권한을 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-193">If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3. <span data-ttu-id="6e0e9-194">A를 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-194">Type A and press ENTER.</span></span>

    <span data-ttu-id="6e0e9-195">미러링이 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-195">The mirroring will be configured.</span></span>

    <span data-ttu-id="6e0e9-196">**설치-CsMirrorDatabase** 는 미러를 설치 하 고 기본 SQL 저장소에 있는 모든 데이터베이스에 대해 미러링을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-196">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="6e0e9-197">특정 데이터베이스에 대해서만 미러링을 구성 하려는 경우-DatabaseType 옵션을 사용 하거나, 몇 개를 제외한 모든 데이터베이스에 대 한 미러링을 구성 하려는 경우 쉼표로 구분 된 데이터베이스 목록과 함께-ExcludeDatabaseList 옵션을 사용할 수 있습니다. 제외할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-197">If you want to configure mirroring for only specific databases, you can use the -DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

    <span data-ttu-id="6e0e9-198">예를 들어, **설치-CsMirrorDatabase**에 다음 옵션을 추가 하는 경우 rtcab 및 rtcxds를 제외한 모든 데이터베이스가 미러 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-198">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

    `-ExcludeDatabaseList rtcab,rtcxds`

   <span data-ttu-id="6e0e9-199">예를 들어, **설치-CsMirrorDatabase**에 다음 옵션을 추가 하면 rtcab, rtcshared 및 rtcxds 데이터베이스만 미러링됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-199">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="6e0e9-200">SQL 미러링 제거 또는 변경</span><span class="sxs-lookup"><span data-stu-id="6e0e9-200">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="6e0e9-201">토폴로지 작성기에서 풀의 SQL 미러링을 제거 하려면 먼저 cmdlet을 사용 하 여 SQL Server에서 미러를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-201">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="6e0e9-202">그런 다음 토폴로지 작성기를 사용 하 여 토폴로지에서 미러를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-202">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="6e0e9-203">SQL Server에서 미러를 제거 하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-203">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

<span data-ttu-id="6e0e9-204">예를 들어 미러링을 제거 하 고 사용자 데이터베이스용 데이터베이스를 삭제 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-204">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

<span data-ttu-id="6e0e9-205">이 `-DropExistingDatabasesOnMirror` 옵션을 선택 하면 해당 데이터베이스가 미러에서 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-205">The  `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="6e0e9-206">그런 다음 토폴로지에서 미러를 제거 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-206">Then, to remove the mirror from the topology, do the following:</span></span>

1. <span data-ttu-id="6e0e9-207">토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="6e0e9-208">**SQL 저장소 미러링 사용** 을 선택 취소 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-208">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3. <span data-ttu-id="6e0e9-209">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-209">Publish the topology.</span></span>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="6e0e9-210">미러링 모니터 제거</span><span class="sxs-lookup"><span data-stu-id="6e0e9-210">Removing a Mirroring Witness</span></span>

<span data-ttu-id="6e0e9-211">백 엔드 서버 미러링 구성에서 미러링 모니터를 제거 해야 하는 경우이 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-211">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1. <span data-ttu-id="6e0e9-212">토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-212">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="6e0e9-213">**SQL Server 미러링 모니터 사용을 선택 취소 하 여 자동 장애 조치를 활성화 하** 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-213">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3. <span data-ttu-id="6e0e9-214">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-214">Publish the topology.</span></span>

    <span data-ttu-id="6e0e9-215">토폴로지를 게시 한 후 토폴로지 작성기에는 다음이 포함 된 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-215">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    <span data-ttu-id="6e0e9-216">그러나이 단계를 따르지 말고 전체 미러링 구성을 제거 하는 `Uninstall-CsMirrorDatabase` 것으로 입력 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-216">However, do not follow that step, and do not type  `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4. <span data-ttu-id="6e0e9-217">SQL Server 구성에서 미러링 모니터만 제거 하려면 [데이터베이스 미러링 세션 (SQL Server)에서 미러링 모니터 제거](https://go.microsoft.com/fwlink/p/?LinkId=268456)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6e0e9-217">To remove just the witness from the SQL Server configuration, follow the instructions in [Remove the Witness from a Database Mirroring Session (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span></span>


