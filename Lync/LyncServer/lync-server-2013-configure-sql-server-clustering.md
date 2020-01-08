---
title: 'Lync Server 2013: SQL Server 클러스터링 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279c6581d0a56193c094c3dd7b9638fd74e2e60c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="68f95-102">Lync Server 2013 용 SQL Server 클러스터링 구성</span><span class="sxs-lookup"><span data-stu-id="68f95-102">Configure SQL Server clustering for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68f95-103">_**마지막으로 수정한 주제:** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="68f95-103">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="68f95-104">Microsoft Lync Server 2013는 SQL Server 2012 및 SQL Server 2008 R2에 대 한 클러스터링을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-104">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="68f95-105">지원 되는 기능에 대 한 자세한 내용은 [Lync Server 2013에서 데이터베이스 소프트웨어 지원을](lync-server-2013-database-software-support.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68f95-105">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="68f95-106">Enterprise Edition 프런트 엔드 서버 및 백 엔드 데이터베이스를 설치 하 고 배포 하기 전에 SQL Server 클러스터를 설정 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-106">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="68f95-107">SQL Server 2012의 장애 조치 (failover) 클러스터링에 대 한 모범 사례 <http://technet.microsoft.com/en-us/library/hh231721.aspx>및 설정 지침은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68f95-107">For best practices and setup instructions for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span></span> <span data-ttu-id="68f95-108">SQL Server 2008의 장애 조치 (failover) <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>클러스터링에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68f95-108">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="68f95-109">SQL Server를 설치할 때 데이터베이스 및 로그 파일 위치의 위치를 관리 하려면 SQL Server Management Studio를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-109">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="68f95-110">Sql server Management Studio는 SQL Server를 설치할 때 선택적 구성 요소로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-110">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="68f95-111">SQL Server 기반 서버에 데이터베이스를 설치 하 고 배포 하려면 데이터베이스 파일을 설치 하는 SQL Server 기반 서버에 대 한 SQL Server sysadmin 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-111">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="68f95-112">SQL Server sysadmin 그룹의 구성원이 아닌 경우 데이터베이스 파일이 배포 될 때까지 그룹에 추가 되도록 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-112">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="68f95-113">Sysadmin 그룹의 구성원을 만들 수 없는 경우에는 데이터베이스를 구성 하 고 배포 하는 스크립트를 사용 하 여 SQL Server 데이터베이스 관리자를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-113">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="68f95-114">절차를 수행 하는 데 필요한 적절 한 사용자 권한 및 권한에 대 한 자세한 내용은 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013에서 SQL Server에 대 한 배포 권한을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68f95-114">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="68f95-115">SQL Server 클러스터링을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="68f95-115">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="68f95-116">SQL Server 클러스터링의 설치 및 구성을 완료 한 후 sql server 인스턴스 가상 클러스터 이름 (SQL Server 클러스터링용 설정에서 구성 됨) 및 인스턴스를 사용 하 여 토폴로지 작성기에서 SQL Server 저장소를 정의 합니다. SQL Server 데이터베이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-116">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="68f95-117">단일 SQL Server 기반 서버와 달리 클러스터 된 SQL Server 기반 서버에 대 한 가상 노드의 정규화 된 도메인 이름 (FQDN)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-117">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68f95-118">토폴로지 작성기에 대해 개별 Windows Server 클러스터 노드를 구성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-118">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="68f95-119">가상 SQL Server 클러스터 이름만 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-119">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="68f95-120">토폴로지 작성기를 사용 하 여 데이터베이스를 배포 하는 경우에는 SQL Server sysadmin 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-120">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="68f95-121">SQL Server sysadmin 그룹의 구성원 이지만 도메인에 대 한 권한이 없는 경우 (예: SQL Server 데이터베이스 관리자 역할), Lync Server에서 데이터베이스를 만들 수 있지만 필요한 정보를 읽을 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-121">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="68f95-122">Lync Server를 배포 하는 데 필요한 사용자 권한 및 권한에 대 한 자세한 내용은 [Lync server 2013에서 SQL Server에 대 한 배포 권한을](lync-server-2013-deployment-permissions-for-sql-server.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68f95-122">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="68f95-123">SQL Server Management Studio를 사용 하 여 데이터베이스 폴더 및 로그 파일 폴더 기본값이 SQL Server 클러스터의 공유 디스크에 올바르게 매핑 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-123">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio.</span></span> <span data-ttu-id="68f95-124">토폴로지 작성기를 사용 하 여 데이터베이스를 만들 경우이 절차를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-124">This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68f95-125">SQL Server Management Studio를 설치 하지 않은 경우 SQL Server 설치를 다시 실행 한 다음 기존 SQL Server 배포에 대 한 추가 기능으로 관리 도구를 선택 하 여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-125">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="68f95-126">토폴로지 작성기 또는 Windows PowerShell cmdlet 중 하나를 사용 하 여 SQL Server 기반 서버에 대 한 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-126">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="68f95-127">토폴로지 작성기를 사용 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-127">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="68f95-128">Windows PowerShell cmdlet을 사용 하려면 [lync server 2013에서 Lync Server 관리 셸을 사용 하 여 데이터베이스 설치](lync-server-2013-database-installation-using-lync-server-management-shell.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68f95-128">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="68f95-129">토폴로지 작성기를 사용 하 여 데이터베이스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="68f95-129">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="68f95-130">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-130">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="68f95-131">다음 절차에서는 토폴로지 작성기에서 토폴로지를 정의 하 고 구성한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-131">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="68f95-132">토폴로지를 정의 하는 방법에 대 한 자세한 내용은<A href="lync-server-2013-defining-and-configuring-the-topology.md">Lync Server 2013에서 토폴로지 정의 및 구성을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68f95-132">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="68f95-133">토폴로지 작성기를 사용 하 여 토폴로지를 게시 하 고 데이터베이스를 구성 하려면 올바른 사용자 권한 및 그룹 구성원 자격으로 사용자로 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-133">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="68f95-134">필요한 권한 및 그룹 구성원에 대 한 자세한 내용은 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013에서 SQL Server에 대 한 배포 권한을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="68f95-134">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="68f95-135">토폴로지 작성기에서 토폴로지를 게시할 때 **데이터베이스 만들기** 페이지에서 **고급**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-135">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="68f95-136">**데이터베이스 파일 위치 선택** 페이지에는 SQL Server 클러스터에 데이터베이스 파일을 배포 하는 방법을 결정 하는 두 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-136">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster.</span></span> <span data-ttu-id="68f95-137">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-137">Select one of the following:</span></span>
    
      - <span data-ttu-id="68f95-138">**자동으로 데이터베이스 파일 위치를 결정 합니다.**</span><span class="sxs-lookup"><span data-stu-id="68f95-138">**Automatically determine the database file location.**</span></span> <span data-ttu-id="68f95-139">이 선택 항목은 알고리즘을 사용 하 여 SQL Server 기반 서버의 드라이브 구성에 따라 데이터베이스 로그 및 데이터 파일 위치를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-139">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="68f95-140">파일은 최적의 성능을 제공 하는 방식으로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-140">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="68f95-141">SQL Server 인스턴스 기본값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-141">Use SQL Server instance defaults.</span></span> <span data-ttu-id="68f95-142">이 옵션을 선택 하면 SQL Server 인스턴스 설정에 따라 로그 및 데이터 파일이 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-142">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="68f95-143">Sql server에 데이터베이스 파일을 배포한 후 SQL Server 데이터베이스 관리자가 파일을 재배치 하 여 특정 SQL Server 구성 요구 사항에 대 한 성능을 최적화 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-143">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="68f95-144">토폴로지 게시를 완료 하 고 작업 중에 오류가 발생 하지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="68f95-144">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

