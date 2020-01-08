---
title: 'Lync Server 2013: 바이러스 백신 검사 제외'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f354b93bf21f054e9b5b24e3befd1787279bbe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="f3b16-102">Lync Server 2013을 위한 바이러스 백신 검사 제외</span><span class="sxs-lookup"><span data-stu-id="f3b16-102">Antivirus scanning exclusions for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3b16-103">_**마지막으로 수정한 주제:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="f3b16-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="f3b16-104">바이러스 백신 스캐너가 Lync Server 2013의 작동을 방해 하지 않도록 하려면 바이러스 검사 프로그램을 실행 하는 각 Lync Server 2013 서버 또는 서버 역할에 대해 특정 프로세스 및 디렉터리를 제외 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3b16-104">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="f3b16-105">다음 프로세스 및 디렉터리는 제외 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3b16-105">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f3b16-106">아래 나열 된 폴더 및 파일 위치는 Lync Server 2013의 기본 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="f3b16-106">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="f3b16-107">기본값을 사용 하지 않은 위치의 경우이 항목에 지정 된 기본 위치 대신 조직에 대해 지정한 위치를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3b16-107">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f3b16-108">일부 바이러스 백신 프로그램에는 제외 목록에 대 한 상대 경로가 아닌 절대적인 필요이 있을 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3b16-108">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="f3b16-109">Lync Server 2013 프로세스:</span><span class="sxs-lookup"><span data-stu-id="f3b16-109">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="f3b16-110">ABServer .exe</span><span class="sxs-lookup"><span data-stu-id="f3b16-110">ABServer.exe</span></span>
    
      - <span data-ttu-id="f3b16-111">AcpMcuSvc .exe</span><span class="sxs-lookup"><span data-stu-id="f3b16-111">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="f3b16-112">ASMCUSvc .exe</span><span class="sxs-lookup"><span data-stu-id="f3b16-112">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="f3b16-113">AVMCUSvc .exe</span><span class="sxs-lookup"><span data-stu-id="f3b16-113">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="f3b16-114">ChannelService .exe</span><span class="sxs-lookup"><span data-stu-id="f3b16-114">ChannelService.exe</span></span>
    
      - <span data-ttu-id="f3b16-115">ClsAgent .exe</span><span class="sxs-lookup"><span data-stu-id="f3b16-115">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="f3b16-116">ComplianceService</span><span class="sxs-lookup"><span data-stu-id="f3b16-116">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="f3b16-117">DataMCUSvc</span><span class="sxs-lookup"><span data-stu-id="f3b16-117">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="f3b16-118">DataProxy</span><span class="sxs-lookup"><span data-stu-id="f3b16-118">DataProxy.exe</span></span>
    
      - <span data-ttu-id="f3b16-119">FileTransferAgent</span><span class="sxs-lookup"><span data-stu-id="f3b16-119">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="f3b16-120">IMMCUSvc .exe</span><span class="sxs-lookup"><span data-stu-id="f3b16-120">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="f3b16-121">LysSvc</span><span class="sxs-lookup"><span data-stu-id="f3b16-121">LysSvc.exe</span></span>
    
      - <span data-ttu-id="f3b16-122">MasterReplicatorAgent</span><span class="sxs-lookup"><span data-stu-id="f3b16-122">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="f3b16-123">MediaRelaySvc</span><span class="sxs-lookup"><span data-stu-id="f3b16-123">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="f3b16-124">MediationServerSvc</span><span class="sxs-lookup"><span data-stu-id="f3b16-124">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="f3b16-125">MRASSvc</span><span class="sxs-lookup"><span data-stu-id="f3b16-125">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="f3b16-126">OcsAppServerHost</span><span class="sxs-lookup"><span data-stu-id="f3b16-126">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="f3b16-127">ReplicaReplicatorAgent</span><span class="sxs-lookup"><span data-stu-id="f3b16-127">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="f3b16-128">ReplicationApp</span><span class="sxs-lookup"><span data-stu-id="f3b16-128">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="f3b16-129">RtcHost</span><span class="sxs-lookup"><span data-stu-id="f3b16-129">RtcHost.exe</span></span>
    
      - <span data-ttu-id="f3b16-130">RTCSrv</span><span class="sxs-lookup"><span data-stu-id="f3b16-130">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="f3b16-131">XmppProxy</span><span class="sxs-lookup"><span data-stu-id="f3b16-131">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="f3b16-132">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="f3b16-132">XmppTGW.exe</span></span>

  - <span data-ttu-id="f3b16-133">Windows Fabric Host 서비스 프로세스:</span><span class="sxs-lookup"><span data-stu-id="f3b16-133">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="f3b16-134">Printbrm.exe</span><span class="sxs-lookup"><span data-stu-id="f3b16-134">Fabric.exe</span></span>
    
      - <span data-ttu-id="f3b16-135">FabricDCA</span><span class="sxs-lookup"><span data-stu-id="f3b16-135">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="f3b16-136">FabricHost</span><span class="sxs-lookup"><span data-stu-id="f3b16-136">FabricHost.exe</span></span>

  - <span data-ttu-id="f3b16-137">IIS 프로세스:</span><span class="sxs-lookup"><span data-stu-id="f3b16-137">IIS processes:</span></span>
    
      - <span data-ttu-id="f3b16-138">% systemroot%\\system32\\inetsrv\\w3wp</span><span class="sxs-lookup"><span data-stu-id="f3b16-138">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="f3b16-139">% systemroot%\\SysWOW64\\inetsrv\\w3wp</span><span class="sxs-lookup"><span data-stu-id="f3b16-139">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="f3b16-140">SQL Server 백 엔드 프로세스:</span><span class="sxs-lookup"><span data-stu-id="f3b16-140">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="f3b16-141">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. MSSQLSERVER\\MSSQL\\Binn\\sqlservr.exe</span><span class="sxs-lookup"><span data-stu-id="f3b16-141">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="f3b16-142">% ProgramFiles%\\Microsoft SQL Server\\MSRS11. MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService</span><span class="sxs-lookup"><span data-stu-id="f3b16-142">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="f3b16-143">% ProgramFiles%\\Microsoft SQL Server\\MSAS11. MSSQLSERVER\\OLAP\\Bin\\MSMDSrv</span><span class="sxs-lookup"><span data-stu-id="f3b16-143">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="f3b16-144">SQL Server 프런트 엔드 프로세스:</span><span class="sxs-lookup"><span data-stu-id="f3b16-144">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="f3b16-145">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. L CLOCAL\\MSSQL\\Binn\\sqlservr.exe</span><span class="sxs-lookup"><span data-stu-id="f3b16-145">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="f3b16-146">% ProgramFiles%\\Microsoft SQL Server\\MSSQL11. RTCLOCAL\\MSSQL\\Binn\\sqlservr.exe</span><span class="sxs-lookup"><span data-stu-id="f3b16-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="f3b16-147">디렉터리 및 파일:</span><span class="sxs-lookup"><span data-stu-id="f3b16-147">Directories and files:</span></span>
    
      - <span data-ttu-id="f3b16-148">% systemroot%\\System32\\로그 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3b16-148">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="f3b16-149">% systemroot%\\SysWow64\\로그 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3b16-149">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="f3b16-150">% systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span><span class="sxs-lookup"><span data-stu-id="f3b16-150">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="f3b16-151">% programfiles%\\Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3b16-151">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="f3b16-152">% programfiles%\\공용 파일\\Microsoft Lync Server 2013\\감시자 노드</span><span class="sxs-lookup"><span data-stu-id="f3b16-152">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="f3b16-153">% programfiles%\\공용 파일\\Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3b16-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="f3b16-154">%\\RtcReplicaRoot%</span><span class="sxs-lookup"><span data-stu-id="f3b16-154">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="f3b16-155">파일 공유 저장소 (토폴로지 작성기에서 지정)</span><span class="sxs-lookup"><span data-stu-id="f3b16-155">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="f3b16-156">파일 저장소는 토폴로지 작성기에 지정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3b16-156">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="f3b16-157">백 엔드 데이터베이스, 사용자 저장소, 보관 저장소, 모니터링 저장소 및 응용 프로그램 저장소를 포함 하는 SQL Server 데이터 및 로그 파일</span><span class="sxs-lookup"><span data-stu-id="f3b16-157">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="f3b16-158">토폴로지 작성기에서 데이터베이스 및 로그 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3b16-158">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="f3b16-159">기본 이름을 포함 하 여 각 데이터베이스의 데이터 및 로그 파일에 대 한 자세한 내용은 배포 설명서의 [Lync server 2013에 대 한 SQL Server 데이터 및 로그 파일 배치](lync-server-2013-sql-server-data-and-log-file-placement.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f3b16-159">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="f3b16-160">프런트 엔드 데이터베이스, Lync 스토어, RtcDatabase 저장소 등의 SQL Server 데이터 및 로그 파일</span><span class="sxs-lookup"><span data-stu-id="f3b16-160">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="f3b16-161">일반적 으로% localdrive%\\csdata 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3b16-161">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

