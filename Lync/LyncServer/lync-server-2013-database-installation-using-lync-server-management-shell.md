---
title: 'Lync Server 2013: Lync Server 관리 셸을 사용 하 여 데이터베이스 설치'
description: 'Lync Server 2013: Lync Server 관리 셸을 사용 하 여 데이터베이스 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d572984c94d280723b12c5343a92ddfaa12d4f0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558184"
---
# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a><span data-ttu-id="aad46-103">Lync Server 2013에서 Lync Server 관리 셸을 사용 하 여 데이터베이스 설치</span><span class="sxs-lookup"><span data-stu-id="aad46-103">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aad46-104">_**마지막으로 수정 된 항목:** 2016-06-16_</span><span class="sxs-lookup"><span data-stu-id="aad46-104">_**Topic Last Modified:** 2016-06-16_</span></span>

<span data-ttu-id="aad46-105">서버 관리자와 SQL Server 관리자의 역할 및 직무를 구분하면 구현이 지연될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-105">Separation of roles and responsibilities between server administrators and SQL Server administrators can result in delays in implementation.</span></span> <span data-ttu-id="aad46-106">Lync Server 2013에서는 RBAC (역할 기반 액세스 제어)를 사용 하 여 이러한 어려움을 완화 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-106">Lync Server 2013 uses role-based access control (RBAC) to mitigate these difficulties.</span></span> <span data-ttu-id="aad46-107">경우에 따라 SQL Server 관리자는 RBAC 외부의 SQL Server 기반 서버에서 데이터베이스 설치를 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-107">In some instances, the SQL Server administrator must manage the installation of databases on the SQL Server-based server outside RBAC.</span></span> <span data-ttu-id="aad46-108">Lync Server 2013 관리 셸을 사용 하면 SQL Server 관리자가 올바른 데이터 및 로그 파일로 데이터베이스를 구성 하기 위해 디자인 된 Windows PowerShell cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-108">The Lync Server 2013 Management Shell provides a way for the SQL Server administrator to run Windows PowerShell cmdlets designed to configure the databases with the correct data and log files.</span></span> <span data-ttu-id="aad46-109">자세한 내용은 [Lync server 2013의 SQL Server에 대 한 배포 권한을](lync-server-2013-deployment-permissions-for-sql-server.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aad46-109">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="aad46-110">다음 절차에서는 최소한 Lync Server 2013 OCSCore.msi SQL Server Native Client (sqlncli.msi) Microsoft SQL server 2012 Management Objects, Microsoft sql Server 2012 및 Microsoft SQL Server 2012 ADOMD.NET이 설치 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-110">The following procedure assumes that at a minimum the Lync Server 2013 OCSCore.msi, SQL Server Native Client (sqlncli.msi) Microsoft SQL Server 2012 Management Objects, CLR Types for Microsoft SQL Server 2012 and Microsoft SQL Server 2012 ADOMD.NET are installed.</span></span> <span data-ttu-id="aad46-111">OCSCore.msi는 \Setup\AMD64\Setup 디렉터리의 설치 미디어에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-111">The OCSCore.msi is located on the installation media in the \Setup\AMD64\Setup directory.</span></span> <span data-ttu-id="aad46-112">나머지 구성 요소는 \Setup\amd64.에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-112">The remaining components are located in \Setup\amd64.</span></span> <span data-ttu-id="aad46-113">또한 Lync Server 2013에 대 한 Active Directory 준비가 성공적으로 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-113">Additionally, Active Directory preparation for Lync Server 2013 has been successfully completed.</span></span>



</div>

<span data-ttu-id="aad46-114">**설치-CsDatabase** 는 데이터베이스를 설치 하는 데 사용 하는 Windows PowerShell cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-114">**Install-CsDatabase** is the Windows PowerShell cmdlet you use to install the databases.</span></span> <span data-ttu-id="aad46-115">**Install-CsDatabase** cmdlet는 수많은 매개 변수를 가지며 여기에서는 그 중 몇 가지만 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-115">The **Install-CsDatabase** cmdlet has a large number of parameters, only a few of which are discussed here.</span></span> <span data-ttu-id="aad46-116">가능한 매개 변수에 대 한 자세한 내용은 Lync Server 2013 Management Shell 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aad46-116">For details about the possible parameters, see the Lync Server 2013 Management Shell documentation.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="aad46-117">성능 및 가능한 시간 제한 문제를 피하려면 SQL Server 기반 서버를 참조할 때 항상 FQDN(정규화된 도메인 이름)을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="aad46-117">To avoid performance and possible time-out issues, always use fully qualified domain names (FQDNs) when referring to SQL Server-based servers.</span></span> <span data-ttu-id="aad46-118">호스트 이름 전용 참조는 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="aad46-118">Avoid using host name-only references.</span></span> <span data-ttu-id="aad46-119">예를 들어 sqlbe01.contoso.net를 사용 하 되 SQLBE01는 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="aad46-119">For example, use sqlbe01.contoso.net, but avoid using SQLBE01.</span></span>



</div>

<span data-ttu-id="aad46-120">데이터베이스를 설치 하는 경우에는 다음 세 가지 기본 **방법을 사용 하** 여 준비 된 SQL server 기반 서버에 데이터베이스를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-120">For installing databases, **Install-CsDatabase** uses three primary methods for placing the databases onto the prepared SQL Server-based server:</span></span>

  - <span data-ttu-id="aad46-121">**Install-CsDatabase**를 DatabasePaths 또는 UseDefaultSqlPath 없이 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-121">Run **Install-CsDatabase** without DatabasePaths or UseDefaultSqlPath.</span></span> <span data-ttu-id="aad46-122">cmdlet는 기본 제공 알고리즘을 사용하여 최적의 로그 및 데이터 파일 배치를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-122">The cmdlet uses a built in algorithm to determine the best placement for the log and data files.</span></span> <span data-ttu-id="aad46-123">이 알고리즘은 독립 실행형 SQL Server 구현에만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-123">The algorithm only works for stand-alone SQL Server implementations.</span></span>

  - <span data-ttu-id="aad46-124">**Install-CsDatabase**를 DatabasePaths 매개 변수와 함께 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-124">Run **Install-CsDatabase** with the DatabasePaths parameter.</span></span> <span data-ttu-id="aad46-125">DatabasePaths 매개 변수가 정의된 경우 로그 및 데이터 파일 위치를 최적화하는 기본 제공 알고리즘은 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-125">The built-in algorithm to optimize log and data file locations is not used if the DatabasePaths parameter is defined.</span></span> <span data-ttu-id="aad46-126">이 매개 변수를 사용하면 로그 및 데이터 파일을 배포할 위치를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-126">Using this parameter allows you to define the locations where log and data files will be deployed.</span></span>

  - <span data-ttu-id="aad46-127">**Install-CsDatabase**를 UseDefaultSqlPaths와 함께 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-127">Run **Install-CsDatabase** with UseDefaultSqlPaths.</span></span> <span data-ttu-id="aad46-128">이 옵션은 기본 제공 알고리즘을 사용하여 로그 및 데이터 파일 위치를 최적화하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-128">This option does not use the built-in algorithm to optimize the log and data file locations.</span></span> <span data-ttu-id="aad46-129">로그 및 데이터 파일은 SQL Server 관리자가 설정한 기본값에 따라 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-129">Log and data file are deployed according to the defaults set by the SQL Server administrator.</span></span> <span data-ttu-id="aad46-130">이러한 경로는 일반적으로 SQL Server에서 로그 및 데이터 파일을 자동으로 관리 하는 용도로 설정 되며, Lync Server 2013의 설정과는 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-130">These paths are typically set for the purpose of automatic administration of log and data files on the SQL Server in advance, and are not associated with the setup of Lync Server 2013.</span></span>

  - <span data-ttu-id="aad46-131">DatabasePathMap 매개 변수를 사용 하 여 각 데이터베이스 및 해당 로그 파일에 대 한 위치를 명시적으로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-131">The DatabasePathMap parameter can also be used to explicitly specify a location for each database and its respective log file.</span></span>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a><span data-ttu-id="aad46-132">Windows PowerShell cmdlet를 사용하여 SQL Server 중앙 관리 저장소를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="aad46-132">To use Windows PowerShell cmdlets to configure the SQL Server Central Management store</span></span>

1.  <span data-ttu-id="aad46-133">원하는 컴퓨터에서 SQL Server 기반 서버에 데이터베이스를 만들기 위해 관리 자격 증명을 사용하여 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-133">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="aad46-134">자세한 내용은 [Lync server 2013의 SQL Server에 대 한 배포 권한을](lync-server-2013-deployment-permissions-for-sql-server.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aad46-134">For details, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

2.  <span data-ttu-id="aad46-135">Lync Server 2013 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-135">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="aad46-136">Windows PowerShell에 대 한 실행 정책을 조정 하지 않은 경우 Windows PowerShell 스크립트 실행을 허용 하도록 정책을 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-136">If you have not adjusted the execution policy for Windows PowerShell, you must adjust the policy to allow Windows PowerShell scripts to run.</span></span> <span data-ttu-id="aad46-137">자세한 내용은에서 "실행 정책 검사"를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093) .</span><span class="sxs-lookup"><span data-stu-id="aad46-137">For details, see “Examining the Execution Policy” at [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093).</span></span>

3.  <span data-ttu-id="aad46-138">**설치-CsDatabase** cmdlet을 사용 하 여 중앙 관리 저장소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-138">Use the **Install-CsDatabase** cmdlet to install the Central Management store.</span></span>
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="aad46-139">Report 매개 변수는 선택적이지만 설치 프로세스를 문서화하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-139">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

4.  <span data-ttu-id="aad46-140">**설치-CsDatabase-databasepaths** 는 각각 SQL Server 데이터 및 로그 파일 배치에 정의 된 드라이브의 경로를 정의 하는 최대 6 개의 경로 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-140">**Install-CsDatabase –DatabasePaths** can use up to six path parameters, each defining the paths for the drives as defined in SQL Server Data and Log File Placement.</span></span> <span data-ttu-id="aad46-141">Lync Server 2013의 데이터베이스 구성에 대 한 논리적 규칙에 따라 드라이브는 2, 4 또는 6 개 버킷으로 구문 분석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-141">By the logical rules of the database configuration in Lync Server 2013, drives are parsed out into buckets of two, four, or six.</span></span> <span data-ttu-id="aad46-142">SQL Server 구성 및 버킷 수에 따라 두 개의 경로, 즉 4 개의 경로 또는 6 개의 경로를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-142">Depending on your SQL Server configuration and the number of buckets, you will supply two paths, four paths, or six paths.</span></span>
    
    <span data-ttu-id="aad46-143">드라이브가 세 개인 경우 로그가 우선 적용되며 데이터 파일은 이후에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-143">If you have three drives, the log gets priority and the data files are distributed after.</span></span> <span data-ttu-id="aad46-144">6 개의 드라이브로 구성 된 SQL Server 기반 서버에 대 한 예:</span><span class="sxs-lookup"><span data-stu-id="aad46-144">An example for a SQL Server-based server configured with six drives:</span></span>
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  <span data-ttu-id="aad46-145">데이터베이스 설치가 완료 되 면 Lync Server 2013 관리 셸을 닫거나 토폴로지 작성기에 정의 된 Lync Server 2013 구성 된 데이터베이스 설치로 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-145">When the database installation completes, you can close Lync Server 2013 Management Shell or proceed to the installation of the Lync Server 2013 configured databases defined in Topology Builder.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a><span data-ttu-id="aad46-146">Windows PowerShell cmdlet를 사용하여 SQL Server 토폴로지 구성 데이터베이스를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="aad46-146">To use Windows PowerShell cmdlets to configure the SQL Server topology configured databases</span></span>

1.  <span data-ttu-id="aad46-147">Lync Server 2013에 대해 토폴로지 작성기 구성 데이터베이스를 설치 하려면 Lync Server 2013 관리자가 토폴로지를 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-147">To install the Topology Builder configured databases for Lync Server 2013, the Lync Server 2013 administrator must publish the topology.</span></span> <span data-ttu-id="aad46-148">자세한 내용은 배포 설명서에서 [Lync Server 2013의 토폴로지 게시](lync-server-2013-publish-the-topology.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aad46-148">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation.</span></span>

2.  <span data-ttu-id="aad46-149">원하는 컴퓨터에서 SQL Server 기반 서버에 데이터베이스를 만들기 위해 관리 자격 증명을 사용하여 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-149">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="aad46-150">[Lync server 2013의 SQL Server에 대 한 배포 권한](lync-server-2013-deployment-permissions-for-sql-server.md)항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aad46-150">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="aad46-151">SQL Server 기반 데이터베이스를 구성 하려면 여기에 설명 된 단계를 실행 하는 데 사용 되는 SQL Server 관리자 계정이 SQL Server를 실행 하는 서버에서 중앙 관리 서버 역할을 수행 하는 서버의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-151">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="aad46-152">특히 SQL Server 데이터베이스를 설치 하거나 구성 해야 하는 추가 Lync Server 2013 풀을 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-152">This is especially important to check for any additional Lync Server 2013 pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="aad46-153">예를 들어 두 번째 풀 (pool02)을 배포 하는 경우 중앙 관리 서버 역할은 pool01에서 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-153">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="aad46-154">SQL Server sysadmin 그룹에는 두 SQL Server 기반 데이터베이스에 대 한 사용 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-154">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="aad46-155">Lync Server 2013 관리 셸을 아직 열려 있지 않은 경우 엽니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-155">Open Lync Server 2013 Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="aad46-156">**설치-CsDatabase** cmdlet을 사용 하 여 토폴로지 작성기 구성 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-156">Use the **Install-CsDatabase** cmdlet to install the Topology Builder configured databases.</span></span>
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="aad46-157">Report 매개 변수는 선택적이지만 설치 프로세스를 문서화하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-157">The Report parameter is optional but is useful if you are documenting the installation process.</span></span>

    
    </div>

5.  <span data-ttu-id="aad46-158">데이터베이스 설치가 완료 되 면 Lync Server 2013 관리 셸을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-158">When the database installation completes, close Lync Server 2013 Management Shell.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a><span data-ttu-id="aad46-159">Windows PowerShell cmdlet을 사용 하 여 DatabasePathMap 매개 변수를 사용 하 여 SQL Server 토폴로지를 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-159">To use Windows PowerShell cmdlets to configure the SQL Server topology using the DatabasePathMap parameter</span></span>

1.  <span data-ttu-id="aad46-160">Lync Server 2013에 대 한 데이터베이스를 설치 하려면 Lync Server 관리자가 경로를 만들고 미리 정의 된 규칙 집합에 따라 데이터베이스 파일 및 로그 파일을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-160">To install databases for Lync Server 2013, the Lync Server administrator must create the paths and deploy the databases files and log files according to a predefined set of rules.</span></span>

2.  <span data-ttu-id="aad46-161">원하는 컴퓨터에서 SQL Server 기반 서버에 데이터베이스를 만들기 위해 관리 자격 증명을 사용하여 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-161">On any computer, log on with administrative credentials for creating the databases on the SQL Server-based server.</span></span> <span data-ttu-id="aad46-162">[Lync server 2013의 SQL Server에 대 한 배포 권한](lync-server-2013-deployment-permissions-for-sql-server.md)항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="aad46-162">See the topic, [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="aad46-163">SQL Server 기반 데이터베이스를 구성 하려면 여기에 설명 된 단계를 실행 하는 데 사용 되는 SQL Server 관리자 계정이 SQL Server를 실행 하는 서버에서 중앙 관리 서버 역할을 수행 하는 서버의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-163">To be able to configure the SQL Server-based databases, make sure the SQL Server administrator account used to run the steps described here is also a member of the sysadmins group (or equivalent) on the server running SQL Server and holding the Central Management Server role.</span></span> <span data-ttu-id="aad46-164">특히 SQL Server 데이터베이스를 설치 하거나 구성 해야 하는 추가 Lync Server 풀이 있는지 확인 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-164">This is especially important to check for any additional Lync Server pools which require SQL Server database installation or configuration.</span></span> <span data-ttu-id="aad46-165">예를 들어 두 번째 풀 (pool02)을 배포 하는 경우 중앙 관리 서버 역할은 pool01에서 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-165">For example, if you are deploying a second pool (pool02) but the Central Management Server role is held by pool01.</span></span> <span data-ttu-id="aad46-166">SQL Server sysadmin 그룹에는 두 SQL Server 기반 데이터베이스에 대 한 사용 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-166">The SQL Server sysadmin group (or equivalent) must have permissions on both SQL Server-based databases.</span></span>

    
    </div>

3.  <span data-ttu-id="aad46-167">Lync Server Management Shell (아직 열려 있지 않은 경우)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-167">Open Lync Server Management Shell, if it’s not already open.</span></span>

4.  <span data-ttu-id="aad46-168">DatabasePathMap 매개 변수와 PowerShell 해시 테이블을 포함 하는 **csdatabase** cmdlet을 사용 하 여 토폴로지 작성기 구성 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-168">Use the **Install-CsDatabase** cmdlet with the DatabasePathMap parameter and a PowerShell hash table to install the Topology Builder configured databases.</span></span>

5.  <span data-ttu-id="aad46-169">예제 코드에서 데이터베이스에 대해 정의 된 경로는 다음과 같이 – DatabasePathMap 매개 변수 및 정의 된 해시 테이블을 사용 하 여 세부적으로 결정할 수 있으며,이 예에서는 \\ 모든 데이터베이스 (.mdf) 파일에 "c: csdata"를 사용 하 고 \\ 모든 로그 파일 (.ldf)을 "c: csdata"로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-169">In the example code, the paths defined for the databases can be determined in a granular manner by using the –DatabasePathMap parameter and a defined hash table as follows (the example uses “C:\\CSData” for all database (.mdf) files, and “C:\\CSLogFiles” for all log (.ldf) files.</span></span> <span data-ttu-id="aad46-170">설치-CsDatabase에서 필요에 따라 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-170">Folder will be created as needed by Install-CsDatabase):</span></span>
    ```powershell
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
    "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
    "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
    }
    Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
6.  <span data-ttu-id="aad46-171">데이터베이스와 로그 파일은 대상 데이터베이스 서버에서 해당 위치를 사용 하 여 명시적으로 이름이 지정 되므로 각 서비스 유형의 실제 데이터베이스 및 로그 위치에 대해 특정 위치를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-171">Because the database and log files are explicitly named with their location on the destination database server, you can define specific locations for each service type’s actual database and log location.</span></span> <span data-ttu-id="aad46-172">다음 예에서는 각 특정 서비스 종류에 대 한 데이터베이스를 별도의 디스크에 배치 하 고 관련 로그 파일을 서로 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-172">The following example puts databases for each specific service type on separate disks, and associated log files on another.</span></span> <span data-ttu-id="aad46-173">예제:</span><span class="sxs-lookup"><span data-stu-id="aad46-173">For example:</span></span>
    
      - <span data-ttu-id="aad46-174">"D: rtcdatabase"에 대 한 모든 RTC 데이터베이스 \\</span><span class="sxs-lookup"><span data-stu-id="aad46-174">All RTC databases to “D:\\RTCDatabase”</span></span>
    
      - <span data-ttu-id="aad46-175">"E: RTCLogs"에 대 한 모든 RTC 로그 파일 \\</span><span class="sxs-lookup"><span data-stu-id="aad46-175">All RTC log files to “E:\\RTCLogs”</span></span>
    
      - <span data-ttu-id="aad46-176">모든 응용 프로그램 저장소 데이터베이스를 "F: \\ cpsdatabases"로</span><span class="sxs-lookup"><span data-stu-id="aad46-176">All application store databases to “F:\\CPSDatabases”</span></span>
    
      - <span data-ttu-id="aad46-177">모든 응용 프로그램 저장소는 "G: \\ cpslogs"에 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-177">All application store logs to “G:\\CPSLogs”</span></span>
    
      - <span data-ttu-id="aad46-178">모든 응답 그룹 저장소 데이터베이스를 "H: \\ RGSDatabases"로 저장</span><span class="sxs-lookup"><span data-stu-id="aad46-178">All response group store databases to “H:\\RGSDatabases”</span></span>
    
      - <span data-ttu-id="aad46-179">모든 응답 그룹 저장소가 "I: RGSLogs"에 기록 됩니다. \\</span><span class="sxs-lookup"><span data-stu-id="aad46-179">All response group store logs to “I:\\RGSLogs”</span></span>
    
      - <span data-ttu-id="aad46-180">모든 주소록 저장소 데이터베이스를 "J: \\ ABSDatabases"로</span><span class="sxs-lookup"><span data-stu-id="aad46-180">All address book store databases to “J:\\ABSDatabases”</span></span>
    
      - <span data-ttu-id="aad46-181">모든 주소록 저장소 로그 파일을 "K: \\ ABSLogs"에 저장</span><span class="sxs-lookup"><span data-stu-id="aad46-181">All address book store log files to “K:\\ABSLogs”</span></span>
    
      - <span data-ttu-id="aad46-182">모든 보관 저장소 데이터베이스를 "L: \\ ArchivingDatabases"로</span><span class="sxs-lookup"><span data-stu-id="aad46-182">All archiving store databases to “L:\\ArchivingDatabases”</span></span>
    
      - <span data-ttu-id="aad46-183">모든 보관 저장소는 "M: ArchivingLogs"에 기록 됩니다. \\</span><span class="sxs-lookup"><span data-stu-id="aad46-183">All archiving store logs to “M:\\ArchivingLogs”</span></span>
    
      - <span data-ttu-id="aad46-184">"N: MonitoringDatabases"에 대 한 모든 모니터링 저장소 데이터베이스 \\</span><span class="sxs-lookup"><span data-stu-id="aad46-184">All monitoring store databases to “N:\\MonitoringDatabases”</span></span>
    
      - <span data-ttu-id="aad46-185">모든 모니터링 저장소 로그 파일을 "O: \\ MonitoringLogfiles"로</span><span class="sxs-lookup"><span data-stu-id="aad46-185">All monitoring store log files to “O:\\MonitoringLogfiles”</span></span>
    
    <!-- end list -->
    
    ```powershell    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    <span data-ttu-id="aad46-186">– DatabasePathMap 매개 변수를 사용 하면 SQL Server 성능 및 배치 요구 사항에 가장 적합 한 솔루션을 제공 하는 논리적 드라이브 문자 매핑 조합을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-186">Using the –DatabasePathMap parameter, you can define any logical drive letter mapping combination that provides the best solution for your SQL Server performance and placement requirements.</span></span>

<span data-ttu-id="aad46-187">**Databasepathmap** 메서드를 사용 하 여 데이터베이스 데이터 파일 및 로그 파일을 구성 하는 경우에는 토폴로지 작성기를 사용할 때 일반 프로세스를 약간 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-187">If you configure your database data files and log files by using the **DatabasePathMap** method, you will need to make a slight change to your normal process when using Topology Builder.</span></span> <span data-ttu-id="aad46-188">일반적으로 토폴로지 선택 사항을 정의 하 고, 토폴로지를 게시 하 고, 데이터베이스 선택을 배포 하도록 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-188">Typically, you would define your topology choices, publish the topology, and choose to deploy the database selections.</span></span>

<span data-ttu-id="aad46-189">**Databasepathmap** 을 사용한 경우 토폴로지 작성기 프로세스의 세 번째 부분을 이미 완료 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-189">If you have used **DatabasePathMap** you have already accomplished the third part of the Topology Builder process.</span></span> <span data-ttu-id="aad46-190">토폴로지 작성기를 실행 하기 전에 전체적으로 데이터베이스 서버를 구성 하는 경우에도 모든 서버 역할 및 옵션을 정의 하 되, 데이터베이스 만들기 옵션은 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad46-190">In the case of having a completely configured database server in advance of running Topology Builder, you would still define all of your server roles and options, but deselect the option to create the databases.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

