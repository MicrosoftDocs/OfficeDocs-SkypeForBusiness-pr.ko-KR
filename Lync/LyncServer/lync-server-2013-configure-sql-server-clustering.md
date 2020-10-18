---
title: 'Lync Server 2013: SQL Server 클러스터링 구성'
description: 'Lync Server 2013: SQL Server 클러스터링을 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f4b81b62d086de27659f564427ad6adde99ecac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576754"
---
# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="5f487-103">Lync Server 2013에 대해 SQL Server 클러스터링 구성</span><span class="sxs-lookup"><span data-stu-id="5f487-103">Configure SQL Server clustering for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f487-104">_**마지막으로 수정 된 항목:** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="5f487-104">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="5f487-105">Microsoft Lync Server 2013는 SQL Server 2012 및 SQL Server 2008 r 2에 대 한 클러스터링을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-105">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="5f487-106">지원 되는 기능에 대 한 자세한 내용은 [Lync Server 2013에서 데이터베이스 소프트웨어 지원을](lync-server-2013-database-software-support.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f487-106">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="5f487-107">Enterprise Edition 프런트 엔드 서버 및 백 엔드 데이터베이스를 설치 및 배포 하기 전에 SQL Server 클러스터를 설정 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-107">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="5f487-108">SQL Server 2012의 장애 조치 (failover) 클러스터링에 대 한 모범 사례 및 설정 지침은를 참조 하세요 <https://technet.microsoft.com/library/hh231721.aspx> .</span><span class="sxs-lookup"><span data-stu-id="5f487-108">For best practices and setup instructions for failover clustering in SQL Server 2012, see <https://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="5f487-109">SQL Server 2008의 장애 조치 (failover) 클러스터링의 경우를 참조 하세요 <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> .</span><span class="sxs-lookup"><span data-stu-id="5f487-109">For failover clustering in SQL Server 2008, see <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="5f487-110">SQL Server를 설치하는 경우 데이터베이스 위치 및 로그 파일 위치를 관리할 SQL Server Management Studio를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-110">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="5f487-111">SQL Server Management Studio는 SQL Server를 설치할 때 선택적 구성 요소로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-111">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5f487-112">SQL Server 기반 서버에 데이터베이스를 설치하고 배포하려면 데이터베이스 파일을 설치할 SQL Server 기반 서버에 대한 SQL Server sysadmin 그룹의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-112">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="5f487-113">SQL Server sysadmin 그룹의 구성원이 아닌 경우에는 데이터베이스 파일이 배포될 때까지 그룹에 추가되도록 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-113">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="5f487-114">sysadmin 그룹의 구성원으로 지정될 수 없으면 SQL Server 데이터베이스 관리자에게 데이터베이스를 구성하고 배포할 스크립트를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-114">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="5f487-115">절차를 수행 하는 데 필요한 적절 한 사용자 권한 및 권한에 대 한 자세한 내용은 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013에서 SQL Server에 대 한 배포 권한을</A>참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f487-115">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="5f487-116">SQL Server 클러스터링을 구성하려면</span><span class="sxs-lookup"><span data-stu-id="5f487-116">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="5f487-117">SQL Server 클러스터링의 설치 및 구성을 완료 했으면 sql server 인스턴스 가상 클러스터 이름 (SQL Server 클러스터링용 설정에 구성 됨) 및 SQL Server 데이터베이스의 인스턴스 이름을 사용 하 여 토폴로지 작성기에서 SQL Server 저장소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-117">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="5f487-118">단일 SQL Server 기반 서버와 달리 클러스터형 SQL Server 기반 서버에는 가상 노드 FQDN(정규화된 도메인 이름)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-118">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5f487-119">개별 Windows Server 클러스터 노드를 토폴로지 작성기에 대해 구성할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-119">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="5f487-120">가상 SQL Server 클러스터 이름만 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-120">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="5f487-121">토폴로지 작성기를 사용 하 여 데이터베이스를 배포 하는 경우에는 SQL Server sysadmin 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-121">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="5f487-122">SQL Server sysadmin 그룹의 구성원 이지만 도메인 (예: SQL Server 데이터베이스 관리자 역할)에 해당 하는 권한이 없는 경우에는 Lync Server에서 데이터베이스를 만들 수는 있지만 필요한 정보를 읽지 못하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-122">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="5f487-123">Lync Server를 배포 하는 데 필요한 사용자 권한 및 사용 권한에 대 한 자세한 내용은 [Lync server 2013에서 SQL Server에 대 한 배포 권한을](lync-server-2013-deployment-permissions-for-sql-server.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f487-123">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="5f487-p108">SQL Server Management Studio를 사용하여 데이터베이스 폴더 및 로그 파일 폴더 기본값이 SQL Server 클러스터의 공유 디스크에 제대로 매핑되어 있는지 확인합니다. 이는 Topology Builder를 사용하여 데이터베이스를 만들려는 경우에 필요한 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-p108">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio. This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5f487-126">SQL Server Management Studio를 설치하지 않은 경우 SQL Server 설치를 다시 실행한 다음 기존 SQL Server 배포에 대한 추가 기능으로 관리 도구를 선택하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-126">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="5f487-127">토폴로지 작성기 또는 Windows PowerShell cmdlet을 사용 하 여 SQL Server 기반 서버에 대 한 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-127">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="5f487-128">토폴로지 작성기를 사용 하려면 다음 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-128">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="5f487-129">Windows PowerShell cmdlet을 사용 하려면 [Lync server 2013에서 Lync Server 관리 셸을 사용 하 여 데이터베이스 설치](lync-server-2013-database-installation-using-lync-server-management-shell.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f487-129">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="5f487-130">토폴로지 작성기를 사용 하 여 데이터베이스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="5f487-130">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="5f487-131">토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-131">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="5f487-132">다음 절차에서는 토폴로지 작성기에서 토폴로지를 정의 하 고 구성한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-132">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="5f487-133">토폴로지를 정의 하는 방법에 대 한 자세한 내용은<A href="lync-server-2013-defining-and-configuring-the-topology.md">Lync Server 2013에서 토폴로지 정의 및 구성을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f487-133">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="5f487-134">Topology Builder를 사용하여 토폴로지를 게시하고 데이터베이스를 구성하려면 올바른 사용자 권한 및 그룹 구성원 자격이 있는 사용자로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-134">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="5f487-135">필요한 권한 및 그룹 멤버 자격에 대 한 자세한 내용은 <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Lync server 2013에서 SQL Server에 대 한 배포 권한을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5f487-135">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="5f487-136">토폴로지 작성기에서 토폴로지를 게시할 때 **데이터베이스 만들기** 페이지에서 **고급**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-136">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="5f487-p111">**데이터베이스 파일 위치 선택** 페이지에는 데이터베이스 파일을 SQL Server 클러스터에 배포할 방법을 결정하는 두 가지 옵션이 있습니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-p111">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster. Select one of the following:</span></span>
    
      - <span data-ttu-id="5f487-139">**데이터베이스 파일 위치를 자동으로 결정 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5f487-139">**Automatically determine the database file location.**</span></span> <span data-ttu-id="5f487-140">이 옵션은 SQL Server 기반 서버의 드라이브 구성을 기반으로 데이터베이스 로그 및 데이터 파일 위치를 결정하는 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-140">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="5f487-141">파일은 최적의 성능을 제공할 수 있도록 분산됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-141">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="5f487-142">SQL Server 인스턴스 기본값 사용.</span><span class="sxs-lookup"><span data-stu-id="5f487-142">Use SQL Server instance defaults.</span></span> <span data-ttu-id="5f487-143">이 옵션을 선택하면 SQL Server 인스턴스 설정에 따라 로그 및 데이터 파일이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-143">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="5f487-144">SQL Server에 데이터베이스 파일을 배포한 후 SQL Server 데이터베이스 관리자는 특정 SQL Server 구성 요구 사항에 맞게 성능을 최적화하기 위해 파일 위치를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-144">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="5f487-145">토폴로지 게시를 완료하고 작업 중에 오류가 없었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5f487-145">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

