---
title: 백 엔드 서버 고가용성을 위해 SQL 미러링 배포
description: 백 엔드 서버 고가용성을 위해 SQL 미러링 배포
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
ms.openlocfilehash: 4a2ab2d598249c12231668a888b442f830c5d65f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566004"
---
# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="a77d0-103">Lync Server 2013에서 백 엔드 서버 고가용성을 위해 SQL 미러링 배포</span><span class="sxs-lookup"><span data-stu-id="a77d0-103">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a77d0-104">_**마지막으로 수정 된 항목:** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="a77d0-104">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="a77d0-105">SQL 미러링을 배포할 수 있으려면 서버에서 최소한 SQL Server 2008 R2를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-105">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="a77d0-106">이 버전은 기본, 미러 및 미러링 모니터 서버 등 모든 관련 서버에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-106">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="a77d0-107">자세한 내용은를 참조 [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921) 하세요.</span><span class="sxs-lookup"><span data-stu-id="a77d0-107">For details, see [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="a77d0-108">일반적으로 미러링 모니터 서버가 포함된 두 개의 백 엔드 서버 사이에 SQL 미러링을 설정하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-108">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="a77d0-109">기본 서버의 SQL Server 버전에서 SQL 미러링을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-109">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="a77d0-110">기본, 미러, 미러링 모니터 서버(배포된 경우)는 모두 SQL Server 버전이 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-110">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="a77d0-p102">기본 및 미러는 SQL Server의 에디션이 동일해야 합니다. 미러링 모니터 서버는 에디션이 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-p102">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="a77d0-113">감시 역할에 대해 지원 되는 SQL 버전에 대 한 SQL 모범 사례에 대 한 자세한 내용은 MSDN Library의 "데이터베이스 미러링 감시"를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345) .</span><span class="sxs-lookup"><span data-stu-id="a77d0-113">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="a77d0-114">토폴로지 작성기를 사용 하 여 SQL 미러링을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-114">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="a77d0-115">토폴로지 작성기에서 옵션을 선택 하 여 데이터베이스를 미러링 하 고 토폴로지 작성기는 토폴로지를 게시할 때 미러링 (원하는 경우 미러링 모니터 서버 설정 포함)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-115">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="a77d0-116">미러를 설정하거나 제거하는 것과 동시에 미러링 모니터 서버도 설정하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-116">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="a77d0-117">미러링 모니터 서버만 배포하거나 제거할 수 있는 별도의 명령은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-117">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="a77d0-118">서버 미러링을 구성하려면 먼저 SQL 데이터베이스 권한을 올바르게 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-118">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="a77d0-119">자세한 내용은에서 "데이터베이스 미러링 또는 AlwaysOn 가용성 그룹에 대 한 로그인 계정 설정 (SQL Server)"을 참조 하십시오 [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454) .</span><span class="sxs-lookup"><span data-stu-id="a77d0-119">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="a77d0-p105">SQL 미러링을 사용할 경우 데이터베이스 복구 모드는 항상 **전체**로 설정되므로 트랜잭션 로그 크기를 자세히 모니터링하고 백 엔드 서버의 디스크 공간이 부족해지지 않도록 정기적으로 트랜잭션 로그를 백업해야 합니다. 트랜잭션 로그 백업의 빈도는 로그 증가 속도에 따라 달라지며, 이는 다시 프런트 엔드 풀에서의 사용자 활동으로 인해 발생하는 데이터베이스 트랜잭션에 따라 달라집니다. 올바르게 계획할 수 있도록 Lync 배포 작업에 트랜잭션 로그 증가량이 얼마나 예상되는지 확인하는 것이 좋습니다. 다음 문서에서는 SQL 백업 및 로그 관리에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-p105">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="a77d0-124">데이터베이스 복구 모델: "복구 모델 (SQL Server)" [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="a77d0-124">Database recovery models: "Recovery Models (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="a77d0-125">백업 개요: "백업 개요 (SQL Server)" 위치 [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="a77d0-125">Backup overview: "Backup Overview (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="a77d0-126">백업 트랜잭션 로그: "트랜잭션 로그 백업 (SQL Server)" [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="a77d0-126">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="a77d0-127">SQL 미러링을 사용하면 풀을 만들 때 또는 풀이 이미 만들어진 후에 미러링에 대한 토폴로지를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-127">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="a77d0-128">토폴로지 작성기 또는 cmdlet을 사용 하 여 SQL 미러링을 설정 및 제거 하는 것은 기본, 미러 서버 및 미러링 모니터 서버가 모두 같은 도메인에 속하는 경우에만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-128">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="a77d0-129">다른 도메인에 있는 서버 간에 SQL 미러링을 설정하려는 경우에는 SQL Server 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a77d0-129">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="a77d0-130">백 엔드 데이터베이스 미러링 관계를 변경할 때마다 풀에서 모든 프런트 엔드 서버를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-130">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="a77d0-131">미러링 변경의 경우 (예: 미러 위치 변경) 토폴로지 작성기를 사용 하 여 다음 세 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-131">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="a77d0-132">이전 미러 서버에서 미러링을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-132">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="a77d0-133">새 미러 서버에 미러링을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-133">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="a77d0-134">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-134">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="a77d0-135">미러 파일을 쓰기 위해 파일 공유를 만들고, SQL Server 및 SQL 에이전트에서 실행 중인 서비스에 읽기/쓰기 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-135">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="a77d0-136">SQL Server 서비스가 네트워크 서비스의 컨텍스트에서 실행 중인 경우 &lt; &gt; 주 서버 &lt; &gt; 및 미러 SQL server 둘 다의 도메인&#92;sqlservername $을 공유 권한으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-136">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="a77d0-137">이는 컴퓨터 계정 임을 식별 하는 데 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-137">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="a77d0-138">토폴로지 작성기에서 풀을 만드는 동안 SQL 미러링을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="a77d0-138">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="a77d0-139">**SQL 저장소 정의** 페이지에서 **SQL 저장소** 상자 옆에 있는 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-139">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="a77d0-140">**새 SQL 저장소 정의** 페이지에서 기본 저장소를 지정하고 **이 SQL 인스턴스가 미러링 관계에 있음**을 선택하고, SQL 미러링 포트 번호(기본값 5022)를 지정한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-140">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="a77d0-141">다시 **SQL 저장소 정의** 페이지에서 **SQL 저장소 미러링 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-141">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="a77d0-p108">**새 SQL 저장소 정의** 페이지에서 미러로 사용할 SQL 저장소를 지정합니다. **이 SQL 인스턴스가 미러링 관계에 있음**을 선택하고 포트 번호(기본값 5022)를 지정한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-p108">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="a77d0-144">이 미러에 대해 미러링 모니터 서버를 사용하려는 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-144">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="a77d0-145">**SQL 미러링 모니터 서버를 사용하여 자동 장애 조치(Failover) 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-145">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="a77d0-146">**SQL 저장소 정의** 페이지에서 **SQL 미러링 모니터 서버를 사용하여 자동 장애 조치(Failover) 사용**을 선택하고 미러링 모니터 서버로 사용할 SQL 저장소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-146">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="a77d0-147">포트 번호(기본값 7022)를 지정하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-147">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="a77d0-148">프런트 엔드 풀 및 토폴로지에 있는 다른 모든 역할을 정의한 후 토폴로지 작성기를 사용 하 여 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-148">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="a77d0-149">토폴로지가 게시 되 면 중앙 관리 저장소를 호스트 하는 프런트 엔드 풀에 SQL 미러링이 사용 하도록 설정 된 경우 기본 및 미러 SQL 저장소 데이터베이스를 모두 만드는 옵션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-149">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="a77d0-150">**설정**을 클릭하고 미러링 백업에 대한 파일 공유로 사용할 경로를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-150">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="a77d0-p110">**확인**을 클릭한 후 **다음**을 클릭하여 데이터베이스를 만들고 토폴로지를 게시합니다. 미러링 및 미러링 모니터 서버(지정된 경우)가 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-p110">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="a77d0-153">토폴로지 작성기를 사용 하 여 기존 풀의 속성을 편집 하 여 SQL 미러링을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-153">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="a77d0-154">토폴로지 작성기에서 기존 프런트 엔드 풀에 SQL 미러링을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="a77d0-154">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="a77d0-155">토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-155">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="a77d0-156">**SQL 저장소 미러링 사용**을 선택한 후 **미러링 SQL 저장소** 옆에서 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-156">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="a77d0-157">미러로 사용하려는 SQL 저장소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-157">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="a77d0-158">**이 SQL 인스턴스가 미러링 관계에 있음**을 선택하고 SQL 미러링 포트 번호(기본 포트는 5022)를 지정한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-158">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="a77d0-159">미러링 모니터 서버를 구성하려면 **SQL 미러링 모니터 서버를 사용하여 자동 장애 조치(Failover) 사용**을 선택하고 **새로 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-159">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="a77d0-160">미러링 모니터 서버로 사용하려는 SQL 저장소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-160">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="a77d0-161">**이 SQL 인스턴스가 미러링 관계에 있음**을 선택하고 SQL 미러링 포트 번호(기본 포트는 7022)를 지정한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-161">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="a77d0-162">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-162">Click **OK**.</span></span>

9.  <span data-ttu-id="a77d0-p111">토폴로지를 게시합니다. 이렇게 하면 데이터베이스를 설치하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-p111">Publish the topology. When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="a77d0-165">토폴로지 게시 프로세스 중에 파일 공유 경로를 정의 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-165">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="a77d0-166">미러링에 참여 하는 SQL 서버에는 미러를 설정 하기 위해이 파일 공유에 대 한 읽기/쓰기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-166">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="a77d0-167">그런 후 다음 절차로 이동하려면 먼저 데이터베이스를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-167">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="a77d0-168">SQL 미러링을 설정할 때는 다음 사항에 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-168">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="a77d0-169">미러링 끝점이 존재하는 경우 해당 위치에 정의된 포트를 사용하여 다시 사용되며, 사용자가 토폴로지에 지정한 포트는 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-169">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="a77d0-p113">다른 SQL 인스턴스에 대한 포트를 포함하여 동일 서버의 다른 응용 프로그램에 이미 할당된 포트는 설치된 현재 SQL 인스턴스에 대해 사용하지 않아야 합니다. 이러한 제한은 동일한 서버에 SQL 인스턴스를 두 개 이상 설치한 경우 이러한 인스턴스가 미러링에 대해 동일한 포트를 사용하지 않아야 함을 의미합니다. 자세한 내용은 다음 문서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a77d0-p113">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>
    
      - <span data-ttu-id="a77d0-173">MSDN Library의 "서버 네트워크 주소 (데이터베이스 미러링) 지정" [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="a77d0-173">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="a77d0-174">"데이터베이스 미러링 끝점 (SQL Server)" [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="a77d0-174">"The Database Mirroring Endpoint (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="a77d0-175">Lync Server 관리 셸 Cmdlet을 사용 하 여 SQL 미러링 설정</span><span class="sxs-lookup"><span data-stu-id="a77d0-175">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="a77d0-176">미러링을 설정 하는 가장 쉬운 방법은 토폴로지 작성기를 사용 하는 것 이지만 cmdlet을 사용 하 여이 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-176">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="a77d0-177">Lync Server 관리 셸 창을 열고 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-177">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="a77d0-178">예:</span><span class="sxs-lookup"><span data-stu-id="a77d0-178">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="a77d0-179">다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-179">You will see the following:</span></span>
    
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

2.  <span data-ttu-id="a77d0-180">다음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-180">Verify the following:</span></span>
    
      - <span data-ttu-id="a77d0-181">기본 SQL Server e04-ocs에 있는 Windows 방화벽이 사용 하도록 설정 된 경우 포트 5022은 방화벽을 통해 액세스할 \_ 수 있습니다. \\</span><span class="sxs-lookup"><span data-stu-id="a77d0-181">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="a77d0-182">Windows 방화벽이 미러 SQL Server K16-ocs에서 사용 하도록 설정 된 경우 포트 5022은 방화벽을 통해 액세스할 수 \_ 있습니다. \\</span><span class="sxs-lookup"><span data-stu-id="a77d0-182">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="a77d0-183">Windows 방화벽이 미러링 모니터 SQL Server AB14-lct에서 사용 하도록 설정 된 경우 포트 7022은 방화벽을 통해 액세스할 \_ 수 있습니다. \\</span><span class="sxs-lookup"><span data-stu-id="a77d0-183">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="a77d0-184">모든 기본 및 미러 SQL server에서 SQL Server를 실행 하는 계정에는 파일 공유 \\ \\ E04-OCS \\ csdatabackup에 대 한 읽기/쓰기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-184">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="a77d0-p114">WMI(Windows Management Instrumentation) 공급자가 이러한 모든 서버에서 실행되고 있는지 확인합니다. 이 cmdlet은 이 공급자를 사용해서 모든 기본, 미러 및 미러링 모니터 서버에서 실행되는 SQL Server 서비스에 대한 계정 정보를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-p114">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="a77d0-187">이 cmdlet을 실행 중인 계정에 모든 미러 서버에 대한 데이터 및 로그 파일의 폴더를 만들 수 있는 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-187">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="a77d0-p115">SQL 인스턴스가 실행을 위해 사용하는 사용자 계정에 파일 공유에 대한 읽기/쓰기 권한이 있어야 합니다. 파일 공유가 다른 서버에 있고 SQL 인스턴스가 로컬 시스템 계정으로 실행되는 경우에는 해당 SQL 인스턴스를 호스팅하는 서버에 파일 공유 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-p115">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="a77d0-190">A를 입력한 후 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-190">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="a77d0-191">미러링이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-191">The mirroring will be configured.</span></span>

<span data-ttu-id="a77d0-192">**CsMirrorDatabase** 를 설치 하면 미러를 설치 하 고 기본 SQL 저장소에 있는 모든 데이터베이스에 대해 미러링을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-192">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="a77d0-193">특정 데이터베이스에 대해서만 미러링을 구성 하려면 – DatabaseType 옵션을 사용 하거나, 몇 개를 제외한 모든 데이터베이스에 대해 미러링을 구성 하려는 경우에는-ExcludeDatabaseList 옵션을 사용 하 여 제외할 데이터베이스 이름 목록을 쉼표로 구분 된 목록과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-193">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="a77d0-194">예를 들어 **Install-CsMirrorDatabase**에 다음 옵션을 추가하면 rtcab 및 rtcxds를 제외한 모든 데이터베이스가 미러링됩니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-194">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="a77d0-195">예를 들어 **Install-CsMirrorDatabase**에 다음 옵션을 추가하면 rtcab, rtcshared 및 rtcxds 데이터베이스만 미러링됩니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-195">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="a77d0-196">SQL 미러링 제거 또는 변경</span><span class="sxs-lookup"><span data-stu-id="a77d0-196">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="a77d0-p117">토폴로지 작성기에서 풀에 대한 SQL 미러링을 제거하려면 먼저 SQL Server에서 미러를 제거하는 cmdlet을 사용해야 합니다. 그런 후 토폴로지 작성기를 사용해서 토폴로지에서 미러를 제거할 수 있습니다. SQL Server에서 미러를 제거하려면 다음 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-p117">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="a77d0-200">예를 들어 User 데이터베이스에 대한 미러링을 제거하고 데이터베이스를 삭제하려면 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-200">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="a77d0-201">이 `-DropExistingDatabasesOnMirror` 옵션을 선택 하면 해당 데이터베이스가 미러에서 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-201">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="a77d0-202">그런 후 토폴로지에서 미러를 제거하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-202">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="a77d0-203">토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭하고 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-203">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="a77d0-204">**SQL 저장소 미러링 사용**의 선택을 취소하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-204">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="a77d0-205">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-205">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="a77d0-206">미러링 모니터 서버 제거</span><span class="sxs-lookup"><span data-stu-id="a77d0-206">Removing a Mirroring Witness</span></span>

<span data-ttu-id="a77d0-207">이 절차는 백 엔드 서버 미러링 구성에서 미러링 모니터 서버를 제거 해야 하는 경우에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-207">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="a77d0-208">토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭하고 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-208">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="a77d0-209">**SQL Server 미러링 모니터 서버를 사용하여 자동 장애 조치(Failover) 사용**의 선택을 취소하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-209">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="a77d0-210">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-210">Publish the topology.</span></span>
    
    <span data-ttu-id="a77d0-211">토폴로지를 게시 한 후 토폴로지 작성기에는 다음 항목을 포함 하는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a77d0-211">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="a77d0-212">그러나이 단계를 따르지 말고 `Uninstall-CsMirrorDatabase` 전체 미러링 구성을 제거 하는 것으로 입력 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="a77d0-212">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="a77d0-213">SQL Server 구성에서 미러링 모니터 서버를 제거 하려면 "데이터베이스 미러링 세션에서 감시 제거 (SQL Server)"의 지침을 따르세요 [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456) .</span><span class="sxs-lookup"><span data-stu-id="a77d0-213">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

