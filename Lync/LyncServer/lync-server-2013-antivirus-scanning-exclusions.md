---
title: 'Lync Server 2013: 바이러스 백신 검사 제외'
description: 'Lync Server 2013: 바이러스 백신 검사 제외'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20c395f529cad91993d003efdeb231bd66f4b9bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561914"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a><span data-ttu-id="e424b-103">Lync Server 2013에 대 한 바이러스 백신 검사 제외</span><span class="sxs-lookup"><span data-stu-id="e424b-103">Antivirus scanning exclusions for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e424b-104">_**마지막으로 수정 된 항목:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="e424b-104">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="e424b-105">바이러스 백신 스캐너가 Lync Server 2013의 작업을 방해 하지 않도록 하려면 바이러스 검사 프로그램을 실행 하는 각 Lync Server 2013 서버 또는 서버 역할에 대해 특정 프로세스 및 디렉터리를 제외 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e424b-105">To ensure that the antivirus scanner does not interfere with the operation of Lync Server 2013, you must exclude specific processes and directories for each Lync Server 2013 server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="e424b-106">다음과 같은 프로세스 및 디렉터리를 제외해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e424b-106">The following processes and directories should be excluded:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e424b-107">아래에 나열 된 폴더 및 파일 위치는 Lync Server 2013의 기본 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="e424b-107">Folder and file locations listed below are the default locations for Lync Server 2013.</span></span> <span data-ttu-id="e424b-108">기본값을 그대로 사용하지 않은 위치의 경우 이 항목에 지정된 기본 위치 대신 조직에서 사용자가 지정한 위치를 제외하십시오.</span><span class="sxs-lookup"><span data-stu-id="e424b-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e424b-109">일부 바이러스 백신 프로그램은 제외 목록에 대 한 절대 상대 경로가 필요 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e424b-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>



</div>

  - <span data-ttu-id="e424b-110">Lync Server 2013 프로세스:</span><span class="sxs-lookup"><span data-stu-id="e424b-110">Lync Server 2013 processes:</span></span>
    
      - <span data-ttu-id="e424b-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-111">ABServer.exe</span></span>
    
      - <span data-ttu-id="e424b-112">AcpMcuSvc.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-112">AcpMcuSvc.exe</span></span>
    
      - <span data-ttu-id="e424b-113">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-113">ASMCUSvc.exe</span></span>
    
      - <span data-ttu-id="e424b-114">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-114">AVMCUSvc.exe</span></span>
    
      - <span data-ttu-id="e424b-115">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-115">ChannelService.exe</span></span>
    
      - <span data-ttu-id="e424b-116">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-116">ClsAgent.exe</span></span>
    
      - <span data-ttu-id="e424b-117">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-117">ComplianceService.exe</span></span>
    
      - <span data-ttu-id="e424b-118">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-118">DataMCUSvc.exe</span></span>
    
      - <span data-ttu-id="e424b-119">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-119">DataProxy.exe</span></span>
    
      - <span data-ttu-id="e424b-120">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-120">FileTransferAgent.exe</span></span>
    
      - <span data-ttu-id="e424b-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-121">IMMCUSvc.exe</span></span>
    
      - <span data-ttu-id="e424b-122">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-122">LysSvc.exe</span></span>
    
      - <span data-ttu-id="e424b-123">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-123">MasterReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="e424b-124">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-124">MediaRelaySvc.exe</span></span>
    
      - <span data-ttu-id="e424b-125">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-125">MediationServerSvc.exe</span></span>
    
      - <span data-ttu-id="e424b-126">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-126">MRASSvc.exe</span></span>
    
      - <span data-ttu-id="e424b-127">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-127">OcsAppServerHost.exe</span></span>
    
      - <span data-ttu-id="e424b-128">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-128">ReplicaReplicatorAgent.exe</span></span>
    
      - <span data-ttu-id="e424b-129">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-129">ReplicationApp.exe</span></span>
    
      - <span data-ttu-id="e424b-130">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-130">RtcHost.exe</span></span>
    
      - <span data-ttu-id="e424b-131">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-131">RTCSrv.exe</span></span>
    
      - <span data-ttu-id="e424b-132">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-132">XmppProxy.exe</span></span>
    
      - <span data-ttu-id="e424b-133">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-133">XmppTGW.exe</span></span>

  - <span data-ttu-id="e424b-134">Windows Fabric 호스트 서비스 프로세스:</span><span class="sxs-lookup"><span data-stu-id="e424b-134">Windows Fabric Host Service processes:</span></span>
    
      - <span data-ttu-id="e424b-135">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-135">Fabric.exe</span></span>
    
      - <span data-ttu-id="e424b-136">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-136">FabricDCA.exe</span></span>
    
      - <span data-ttu-id="e424b-137">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-137">FabricHost.exe</span></span>

  - <span data-ttu-id="e424b-138">IIS 프로세스:</span><span class="sxs-lookup"><span data-stu-id="e424b-138">IIS processes:</span></span>
    
      - <span data-ttu-id="e424b-139">% systemroot% \\ system32 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-139">%systemroot%\\system32\\inetsrv\\w3wp.exe</span></span>
    
      - <span data-ttu-id="e424b-140">% systemroot% \\ SysWOW64 \\ inetsrv \\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-140">%systemroot%\\SysWOW64\\inetsrv\\w3wp.exe</span></span>

  - <span data-ttu-id="e424b-141">SQL Server Back-End 프로세스:</span><span class="sxs-lookup"><span data-stu-id="e424b-141">SQL Server Back-End processes:</span></span>
    
      - <span data-ttu-id="e424b-142">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11. MSSQLSERVER \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-142">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.MSSQLSERVER\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="e424b-143">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSRS11. MSSQLSERVER \\ Reporting Services \\ ReportServer \\ Bin \\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-143">%ProgramFiles%\\Microsoft SQL Server\\MSRS11.MSSQLSERVER\\Reporting Services\\ReportServer\\Bin\\ReportingServicesService.exe</span></span>
    
      - <span data-ttu-id="e424b-144">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSAS11. MSSQLSERVER \\ OLAP \\ Bin \\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-144">%ProgramFiles%\\Microsoft SQL Server\\MSAS11.MSSQLSERVER\\OLAP\\Bin\\MSMDSrv.exe</span></span>

  - <span data-ttu-id="e424b-145">SQL Server Front-End 프로세스:</span><span class="sxs-lookup"><span data-stu-id="e424b-145">SQL Server Front-End processes:</span></span>
    
      - <span data-ttu-id="e424b-146">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11. LYNCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-146">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.LYNCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>
    
      - <span data-ttu-id="e424b-147">% ProgramFiles% \\ MICROSOFT SQL Server \\ MSSQL11. RTCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="e424b-147">%ProgramFiles%\\Microsoft SQL Server\\MSSQL11.RTCLOCAL\\MSSQL\\Binn\\SQLServr.exe</span></span>

  - <span data-ttu-id="e424b-148">디렉터리 및 파일:</span><span class="sxs-lookup"><span data-stu-id="e424b-148">Directories and files:</span></span>
    
      - <span data-ttu-id="e424b-149">% systemroot% \\ System32 \\ LogFiles</span><span class="sxs-lookup"><span data-stu-id="e424b-149">%systemroot%\\System32\\LogFiles</span></span>
    
      - <span data-ttu-id="e424b-150">% systemroot% \\ SysWow64 \\ LogFiles</span><span class="sxs-lookup"><span data-stu-id="e424b-150">%systemroot%\\SysWow64\\LogFiles</span></span>
    
      - <span data-ttu-id="e424b-151">% systemroot% \\ Microsoft.NET \\ 어셈블리 \\ GAC \_ MSIL</span><span class="sxs-lookup"><span data-stu-id="e424b-151">%systemroot%\\Microsoft.NET\\assembly\\GAC\_MSIL</span></span>
    
      - <span data-ttu-id="e424b-152">% programfiles% \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e424b-152">%programfiles%\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="e424b-153">% programfiles% \\ Common Files \\ Microsoft Lync Server 2013 \\ 감시자 노드</span><span class="sxs-lookup"><span data-stu-id="e424b-153">%programfiles%\\Common Files\\Microsoft Lync Server 2013\\Watcher Node</span></span>
    
      - <span data-ttu-id="e424b-154">% programfiles% \\ Common Files \\ Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e424b-154">%programfiles%\\Common Files\\Microsoft Lync Server 2013</span></span>
    
      - <span data-ttu-id="e424b-155">% RtcReplicaRoot (%) \\</span><span class="sxs-lookup"><span data-stu-id="e424b-155">%SystemDrive%\\RtcReplicaRoot</span></span>
    
      - <span data-ttu-id="e424b-156">파일 공유 저장소(토폴로지 작성기에서 지정).</span><span class="sxs-lookup"><span data-stu-id="e424b-156">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="e424b-157">파일 저장소는 토폴로지 작성기에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e424b-157">File stores are specified in Topology Builder.</span></span>
    
      - <span data-ttu-id="e424b-158">백 엔드 데이터베이스, 사용자 저장소, 보관 저장소, 모니터링 저장소 및 응용 프로그램 저장소에 대한 항목을 포함하는 SQL Server 데이터 및 로그 파일.</span><span class="sxs-lookup"><span data-stu-id="e424b-158">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="e424b-159">데이터베이스 및 로그 파일은 토폴로지 작성기에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e424b-159">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="e424b-160">기본 이름을 비롯 하 여 각 데이터베이스의 데이터 및 로그 파일에 대 한 자세한 내용은 배포 설명서에서 [SQL Server 데이터 및 Lync Server 2013에 대 한 로그 파일 배치](lync-server-2013-sql-server-data-and-log-file-placement.md) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e424b-160">For details about the data and log files for each database, including default names, see [SQL Server data and log file placement for Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="e424b-161">SQL Server 데이터 및 로그 파일 (프런트 엔드 데이터베이스, Lync store 및 RtcDatabase 저장소 포함)</span><span class="sxs-lookup"><span data-stu-id="e424b-161">SQL Server data and log files, including those for the Front-end database, Lync store, and RtcDatabase store.</span></span> <span data-ttu-id="e424b-162">일반적 으로% localdrive% \\ csdata에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e424b-162">They are normally under %localdrive%\\CSData.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

