---
title: 백 엔드 서버 고가용성을 위해 SQL 미러링 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a37c554faf81795363522378160abf5081084f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="26fa7-102">Lync Server 2013에서 백 엔드 서버 고가용성을 위해 SQL 미러링 배포</span><span class="sxs-lookup"><span data-stu-id="26fa7-102">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26fa7-103">_**마지막으로 수정한 주제:** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="26fa7-103">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="26fa7-104">SQL 미러링을 배포할 수 있으려면 서버에서 최소 SQL Server 2008 R2를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-104">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="26fa7-105">이 버전은 모든 관련 서버 (기본, 미러, 미러링 모니터)에서 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-105">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="26fa7-106">자세한 내용은을 참조 [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921)하세요.</span><span class="sxs-lookup"><span data-stu-id="26fa7-106">For details, see [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="26fa7-107">일반적으로 미러링 모니터로 두 백 엔드 서버 간에 SQL 미러링을 설정 하려면 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-107">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="26fa7-108">주 서버의 SQL Server 버전은 SQL 미러링을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-108">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="26fa7-109">기본, 미러, 미러링 모니터 (배포 된 경우)는 동일한 버전의 SQL Server를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-109">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="26fa7-110">기본 및 미러에는 동일한 버전의 SQL Server가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-110">The primary and the mirror must have the same edition of SQL Server.</span></span> <span data-ttu-id="26fa7-111">미러링 모니터 서버에 다른 버전이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-111">The witness may have a different edition.</span></span>

<span data-ttu-id="26fa7-112">미러링 모니터 역할에 대해 지원 되는 SQL 버전에 대 한 SQL 모범 사례는의 MSDN Library에서 "데이터베이스 미러링 감시"를 참조 [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345)하세요.</span><span class="sxs-lookup"><span data-stu-id="26fa7-112">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [http://go.microsoft.com/fwlink/p/?LinkId=247345](http://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="26fa7-113">토폴로지 작성기를 사용 하 여 SQL 미러링을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-113">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="26fa7-114">토폴로지 작성기에서 데이터베이스를 미러링 하는 옵션을 선택 하면 토폴로지를 게시할 때 토폴로지 작성기에서 미러링 (미러링 모니터 서버 설정 포함)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-114">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="26fa7-115">미러를 설정 하거나 제거할 때와 동시에 미러링 모니터를 설정 하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-115">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="26fa7-116">미러링 모니터만 배포 하거나 제거 하는 별도의 명령은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-116">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="26fa7-117">서버 미러링을 구성 하려면 먼저 SQL 데이터베이스 권한을 올바르게 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-117">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="26fa7-118">자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454)"데이터베이스 미러링 또는 AlwaysOn 가용성 그룹에 대 한 로그인 계정 설정 (SQL Server)"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26fa7-118">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268454](http://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="26fa7-119">SQL 미러링에서는 데이터베이스 복구 모드가 항상 **Full**로 설정 되며,이는 백 엔드 서버의 디스크 공간 부족을 방지 하기 위해 트랜잭션 로그 크기를 면밀 하 게 모니터링 하 고 트랜잭션 로그를 정기적으로 백업 해야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-119">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers.</span></span> <span data-ttu-id="26fa7-120">트랜잭션 로그 백업의 빈도는 로그 증가 속도에 따라 다르며,이는 프런트 엔드 풀의 사용자 활동에서 발생 하는 데이터베이스 트랜잭션에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-120">The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool.</span></span> <span data-ttu-id="26fa7-121">계획을 적절 하 게 수행할 수 있도록 Lync 배포 작업 부하에 예상 되는 트랜잭션 로그 성장이 얼마나 되는지 결정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-121">We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly.</span></span> <span data-ttu-id="26fa7-122">다음 문서는 SQL 백업 및 로그 관리에 대 한 추가 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-122">The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="26fa7-123">데이터베이스 복구 모델: 다음 위치의 "복구 모델 (SQL Server)"[http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="26fa7-123">Database recovery models: "Recovery Models (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268446](http://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="26fa7-124">백업 개요: 다음 위치의 "백업 개요 (SQL Server)"[http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="26fa7-124">Backup overview: "Backup Overview (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268449](http://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="26fa7-125">백업 트랜잭션 로그: "트랜잭션 로그 백업 (SQL Server)"[http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="26fa7-125">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268452](http://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="26fa7-126">SQL 미러링을 사용 하면 풀을 만들 때 또는 풀이 이미 만들어진 후에 미러링에 대 한 토폴로지를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-126">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="26fa7-127">토폴로지 작성기 또는 cmdlet을 사용 하 여 SQL 미러링을 설정 및 제거 하는 것은 주, 미러, 미러링 모니터 (원하는 경우) 서버가 모두 동일한 도메인에 속해 있는 경우에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-127">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="26fa7-128">다른 도메인의 서버 간에 SQL 미러링을 설정 하려면 SQL Server 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26fa7-128">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="26fa7-129">백 엔드 데이터베이스 미러링 관계를 변경할 때마다 풀의 모든 프런트 엔드 서버를 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-129">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="26fa7-130">미러링 변경 사항 (예: 미러 위치 변경)의 경우 토폴로지 작성기를 사용 하 여 다음 세 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-130">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="26fa7-131">이전 미러 서버에서 미러링을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-131">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="26fa7-132">새 미러 서버에 미러링을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-132">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="26fa7-133">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-133">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="26fa7-134">쓰기 파일에 대 한 파일 공유를 만들어야 하며, SQL Server 및 SQL 에이전트에서 실행 중인 서비스에 읽기/쓰기 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-134">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="26fa7-135">SQL Server 서비스가 네트워크 서비스의 컨텍스트에서 실행 되는 경우 주 서버와 미러 SQL server &lt;의&gt; 도메인 &lt;&#92;sqlservername&gt;$을 공유 사용 권한으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-135">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="26fa7-136">$는 컴퓨터 계정 임을 식별 하는 데 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-136">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="26fa7-137">토폴로지 작성기에서 풀을 만드는 동안 SQL 미러링을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="26fa7-137">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="26fa7-138">**Sql 저장소 정의** 페이지에서 **sql 스토어** 상자 옆에 있는 **새로 만들기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-138">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="26fa7-139">**새 SQL Store 정의** 페이지에서 기본 저장소를 지정 하 고, **이 sql 인스턴스가 미러링 관계에 있는 경우**를 선택 하 고, sql 미러링 포트 번호 (기본값 5022)를 지정한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-139">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="26fa7-140">다시 **sql 저장소 정의** 페이지에서 **Sql 저장소 미러링 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-140">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="26fa7-141">**새 Sql 저장소 정의** 페이지에서 미러로 사용할 SQL 저장소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-141">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror.</span></span> <span data-ttu-id="26fa7-142">**이 SQL 인스턴스는 미러링 관계에 있으며**, 포트 번호 (기본값 5022)를 지정한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-142">Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="26fa7-143">이 미러에 미러링 모니터를 원하는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-143">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="26fa7-144">**SQL 미러링 감시 사용을 선택 하 여 자동 장애 조치를 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-144">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="26fa7-145">**Sql Store 정의** 페이지에서 **sql 미러링 미러링 모니터 사용을 선택 하 여 자동 장애 조치 (failover)를 설정 하**고 미러링 모니터로 사용할 sql 저장소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-145">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="26fa7-146">포트 번호 (기본값 7022)를 지정 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-146">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="26fa7-147">프런트 엔드 풀 및 다른 모든 역할을 토폴로지에 대해 정의한 후 토폴로지 작성기를 사용 하 여 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-147">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="26fa7-148">토폴로지가 게시 되 면 중앙 관리 저장소를 호스트 하는 프런트 엔드 풀에 SQL 미러링이 설정 되어 있는 경우 기본 및 미러 SQL 저장소 데이터베이스를 모두 만드는 옵션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-148">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="26fa7-149">**설정을**클릭 하 고 미러링 백업에 대 한 파일 공유로 사용할 경로를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-149">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="26fa7-150">**확인** 을 클릭 한 후 **다음** 을 클릭 하 여 데이터베이스를 만들고 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-150">Click **OK** and then **Next** to create the databases and publish the topology.</span></span> <span data-ttu-id="26fa7-151">미러링과 미러링 모니터 (지정 된 경우)가 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-151">The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="26fa7-152">토폴로지 작성기를 사용 하 여 이미 존재 하는 풀의 속성을 편집 하 여 SQL 미러링을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-152">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="26fa7-153">토폴로지 작성기에서 기존 프런트 엔드 풀에 SQL 미러링을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="26fa7-153">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="26fa7-154">토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-154">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="26fa7-155">**Sql 저장소 미러링 사용**을 선택 하 고 **sql 저장소 미러링**옆에 있는 **새로 만들기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-155">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="26fa7-156">미러로 사용할 SQL 저장소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-156">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="26fa7-157">**이 sql 인스턴스는 미러링 관계에 있으며**, 기본 포트가 5022 인 sql 미러링 포트 번호를 지정한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-157">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="26fa7-158">미러링 모니터를 구성 하려면 **SQL 미러링 미러링 모니터 사용을 선택 하 여 자동 장애 조치 (failover)를 사용 하도록 설정**하 고 **새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-158">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="26fa7-159">미러링 모니터로 사용할 SQL 저장소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-159">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="26fa7-160">**이 sql 인스턴스는 미러링 관계에 있으며**, sql 미러링 포트 번호 (기본 포트는 7022)를 지정한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-160">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="26fa7-161">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-161">Click **OK**.</span></span>

9.  <span data-ttu-id="26fa7-162">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-162">Publish the topology.</span></span> <span data-ttu-id="26fa7-163">이렇게 하면 데이터베이스를 설치 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-163">When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="26fa7-164">토폴로지 게시 프로세스 중에 파일 공유 경로를 정의 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-164">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="26fa7-165">미러링에 참여 하는 SQL 서버는 미러를 설정 하기 위해이 파일 공유에 대 한 읽기/쓰기 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-165">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="26fa7-166">다음 절차를 진행 하기 전에 데이터베이스를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-166">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="26fa7-167">SQL 미러링을 설정할 때 다음 사항에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-167">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="26fa7-168">미러링 끝점이 이미 있으면이 끝점을 정의한 포트를 사용 하 여 다시 사용할 수 있으며 토폴로지에 지정 된 것을 무시 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-168">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="26fa7-169">다른 SQL 인스턴스에 대 한 다른 응용 프로그램에 이미 할당 된 모든 포트는 설치 된 SQL 인스턴스에 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-169">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand.</span></span> <span data-ttu-id="26fa7-170">이는 같은 서버에 둘 이상의 SQL 인스턴스가 설치 되어 있는 경우 미러링에 동일한 포트를 사용 하지 않아야 한다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-170">This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring.</span></span> <span data-ttu-id="26fa7-171">자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26fa7-171">For details, see the following articles:</span></span>
    
      - <span data-ttu-id="26fa7-172">MSDN Library에서 "서버 네트워크 주소 (데이터베이스 미러링)"를 지정 합니다.[http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="26fa7-172">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [http://go.microsoft.com/fwlink/p/?LinkId=247346](http://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="26fa7-173">"데이터베이스 미러링 끝점 (SQL Server)"[http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="26fa7-173">"The Database Mirroring Endpoint (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=247347](http://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="26fa7-174">Lync Server Management Shell Cmdlet을 사용 하 여 SQL 미러링 설정</span><span class="sxs-lookup"><span data-stu-id="26fa7-174">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="26fa7-175">미러링을 설정 하는 가장 쉬운 방법은 토폴로지 작성기를 사용 하는 것 이지만, 이렇게 하면 cmdlet을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-175">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="26fa7-176">Lync Server Management Shell 창을 열고 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-176">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="26fa7-177">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-177">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="26fa7-178">다음이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-178">You will see the following:</span></span>
    
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

2.  <span data-ttu-id="26fa7-179">다음을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-179">Verify the following:</span></span>
    
      - <span data-ttu-id="26fa7-180">기본 SQL Server e04-ocs\_\\에서 Windows 방화벽을 사용 하도록 설정한 경우 방화벽을 통해 포트 5022에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-180">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="26fa7-181">포트 5022은 미러 SQL Server K16-ocs\_\\에서 Windows 방화벽을 사용 하도록 설정한 경우 방화벽을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-181">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="26fa7-182">포트 7022은 감시 SQL Server AB14-lct\_\\에서 Windows 방화벽을 사용 하도록 설정 된 경우 방화벽을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-182">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="26fa7-183">모든 기본 및 미러 sql server에서 sql server를 실행 하는 계정은 파일 공유 \\ \\E04에 대 한 읽기/쓰기 권한을\\가집니다 (OCS csdatabackup).</span><span class="sxs-lookup"><span data-stu-id="26fa7-183">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="26fa7-184">이러한 모든 서버에서 WMI (Windows Management Instrumentation) 공급자가 실행 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-184">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers.</span></span> <span data-ttu-id="26fa7-185">Cmdlet은이 공급자를 사용 하 여 모든 주 미러 및 미러링 모니터 서버에서 실행 되는 SQL Server 서비스에 대 한 계정 정보를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-185">The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="26fa7-186">이 cmdlet을 실행 하는 계정에 모든 미러 서버의 데이터 및 로그 파일에 대 한 폴더를 만들 수 있는 권한이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-186">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="26fa7-187">SQL 인스턴스에서 실행 하는 데 사용 하는 사용자 계정에는 파일 공유에 대 한 읽기/쓰기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-187">Note that the user account that the SQL instance uses to run must have read/write permission to the file share.</span></span> <span data-ttu-id="26fa7-188">파일 공유가 다른 서버에 있고 SQL 인스턴스가 로컬 시스템 계정을 실행 하는 경우에는 SQL 인스턴스를 호스트 하는 서버에 파일 공유 권한을 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-188">If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="26fa7-189">A를 입력 하 고 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-189">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="26fa7-190">미러링이 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-190">The mirroring will be configured.</span></span>

<span data-ttu-id="26fa7-191">**설치-CsMirrorDatabase** 는 미러를 설치 하 고 기본 SQL 저장소에 있는 모든 데이터베이스에 대해 미러링을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-191">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="26fa7-192">특정 데이터베이스에 대해서만 미러링을 구성 하려면 – DatabaseType 옵션을 사용 하거나, 몇 개를 제외한 모든 데이터베이스에 대해 미러링을 구성 하려는 경우 쉼표로 구분 된 데이터베이스 목록과 함께-ExcludeDatabaseList 옵션을 사용할 수 있습니다. 제외할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-192">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="26fa7-193">예를 들어, **설치-CsMirrorDatabase**에 다음 옵션을 추가 하는 경우 rtcab 및 rtcxds를 제외한 모든 데이터베이스가 미러 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-193">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="26fa7-194">예를 들어, **설치-CsMirrorDatabase**에 다음 옵션을 추가 하면 rtcab, rtcshared 및 rtcxds 데이터베이스만 미러링됩니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-194">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="26fa7-195">SQL 미러링 제거 또는 변경</span><span class="sxs-lookup"><span data-stu-id="26fa7-195">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="26fa7-196">토폴로지 작성기에서 풀의 SQL 미러링을 제거 하려면 먼저 cmdlet을 사용 하 여 SQL Server에서 미러를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-196">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="26fa7-197">그런 다음 토폴로지 작성기를 사용 하 여 토폴로지에서 미러를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-197">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="26fa7-198">SQL Server에서 미러를 제거 하려면 다음 cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-198">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="26fa7-199">예를 들어 미러링을 제거 하 고 사용자 데이터베이스용 데이터베이스를 삭제 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-199">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="26fa7-200">이 `-DropExistingDatabasesOnMirror` 옵션을 선택 하면 해당 데이터베이스가 미러에서 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-200">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="26fa7-201">그런 다음 토폴로지에서 미러를 제거 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-201">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="26fa7-202">토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-202">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="26fa7-203">**SQL 저장소 미러링 사용** 을 선택 취소 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-203">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="26fa7-204">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-204">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="26fa7-205">미러링 모니터 제거</span><span class="sxs-lookup"><span data-stu-id="26fa7-205">Removing a Mirroring Witness</span></span>

<span data-ttu-id="26fa7-206">백 엔드 서버 미러링 구성에서 미러링 모니터를 제거 해야 하는 경우이 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-206">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="26fa7-207">토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="26fa7-208">**SQL Server 미러링 모니터 사용을 선택 취소 하 여 자동 장애 조치를 활성화 하** 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-208">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="26fa7-209">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-209">Publish the topology.</span></span>
    
    <span data-ttu-id="26fa7-210">토폴로지를 게시 한 후 토폴로지 작성기에는 다음이 포함 된 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26fa7-210">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="26fa7-211">그러나이 단계를 따르지 말고 전체 미러링 구성을 제거 하는 `Uninstall-CsMirrorDatabase` 것으로 입력 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="26fa7-211">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="26fa7-212">SQL Server 구성에서 미러링 모니터만 제거 하려면 "데이터베이스 미러링 세션에서 미러링 모니터 제거 (SQL Server)"의 지침을 따릅니다 [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456).</span><span class="sxs-lookup"><span data-stu-id="26fa7-212">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [http://go.microsoft.com/fwlink/p/?LinkId=268456](http://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

