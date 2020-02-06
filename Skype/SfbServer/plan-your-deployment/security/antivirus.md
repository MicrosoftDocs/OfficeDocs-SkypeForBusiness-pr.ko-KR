---
title: 비즈니스용 Skype 서버에 대 한 바이러스 백신 검색 제외
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: 비즈니스용 Skype 서버와의 바이러스 검사 프로그램 상호 운용을 간략하게 설명 합니다.
ms.openlocfilehash: 10d296e36324fdbc8bca8f7da48370d619774501
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815696"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="89728-103">비즈니스용 Skype 서버에 대 한 바이러스 백신 검색 제외</span><span class="sxs-lookup"><span data-stu-id="89728-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="89728-104">비즈니스용 Skype 서버와의 바이러스 검사 프로그램 상호 운용을 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="89728-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="89728-105">바이러스 백신 스캐너가 비즈니스용 Skype 서버의 작동을 방해 하지 않도록 하려면 바이러스 검사 프로그램을 실행 하는 각 비즈니스용 Skype Server server 또는 서버 역할에 대 한 특정 프로세스 및 디렉터리를 제외 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89728-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="89728-106">다음 프로세스 및 디렉터리는 제외 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89728-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="89728-107">아래 나열 된 폴더 및 파일 위치는 비즈니스용 Skype 서버의 기본 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="89728-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="89728-108">기본값을 사용 하지 않은 위치의 경우이 항목에 지정 된 기본 위치 대신 조직에 대해 지정한 위치를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="89728-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89728-109">일부 바이러스 백신 프로그램에는 제외 목록에 대 한 상대 경로가 아닌 절대적인 필요이 있을 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="89728-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="89728-110">비즈니스용 Skype 서버 프로세스:</span><span class="sxs-lookup"><span data-stu-id="89728-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="89728-111">ABServer .exe</span><span class="sxs-lookup"><span data-stu-id="89728-111">ABServer.exe</span></span>

  - <span data-ttu-id="89728-112">ASMCUSvc .exe</span><span class="sxs-lookup"><span data-stu-id="89728-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="89728-113">AVMCUSvc .exe</span><span class="sxs-lookup"><span data-stu-id="89728-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="89728-114">ChannelService .exe</span><span class="sxs-lookup"><span data-stu-id="89728-114">ChannelService.exe</span></span>

  - <span data-ttu-id="89728-115">ClsAgent .exe</span><span class="sxs-lookup"><span data-stu-id="89728-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="89728-116">ComplianceService</span><span class="sxs-lookup"><span data-stu-id="89728-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="89728-117">DataMCUSvc</span><span class="sxs-lookup"><span data-stu-id="89728-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="89728-118">DataProxy</span><span class="sxs-lookup"><span data-stu-id="89728-118">DataProxy.exe</span></span>

  - <span data-ttu-id="89728-119">FileTransferAgent</span><span class="sxs-lookup"><span data-stu-id="89728-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="89728-120">HealthAgent</span><span class="sxs-lookup"><span data-stu-id="89728-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="89728-121">IMMCUSvc .exe</span><span class="sxs-lookup"><span data-stu-id="89728-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="89728-122">L<c13> Cbackupservices .exe</span><span class="sxs-lookup"><span data-stu-id="89728-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="89728-123">LysSvc</span><span class="sxs-lookup"><span data-stu-id="89728-123">LysSvc.exe</span></span>

  - <span data-ttu-id="89728-124">MasterReplicatorAgent</span><span class="sxs-lookup"><span data-stu-id="89728-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="89728-125">MediaRelaySvc</span><span class="sxs-lookup"><span data-stu-id="89728-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="89728-126">MediationServerSvc</span><span class="sxs-lookup"><span data-stu-id="89728-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="89728-127">MRASSvc</span><span class="sxs-lookup"><span data-stu-id="89728-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="89728-128">OcsAppServerHost</span><span class="sxs-lookup"><span data-stu-id="89728-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="89728-129">ReplicaReplicatorAgent</span><span class="sxs-lookup"><span data-stu-id="89728-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="89728-130">ReplicationApp</span><span class="sxs-lookup"><span data-stu-id="89728-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="89728-131">RtcHost</span><span class="sxs-lookup"><span data-stu-id="89728-131">RtcHost.exe</span></span>

  - <span data-ttu-id="89728-132">RTCSrv</span><span class="sxs-lookup"><span data-stu-id="89728-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="89728-133">XmppProxy</span><span class="sxs-lookup"><span data-stu-id="89728-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="89728-134">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="89728-134">XmppTGW.exe</span></span>

- <span data-ttu-id="89728-135">Windows Fabric Host 서비스 프로세스:</span><span class="sxs-lookup"><span data-stu-id="89728-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="89728-136">Printbrm.exe</span><span class="sxs-lookup"><span data-stu-id="89728-136">Fabric.exe</span></span>

  - <span data-ttu-id="89728-137">FabricDCA</span><span class="sxs-lookup"><span data-stu-id="89728-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="89728-138">FabricHost</span><span class="sxs-lookup"><span data-stu-id="89728-138">FabricHost.exe</span></span>

- <span data-ttu-id="89728-139">IIS 프로세스:</span><span class="sxs-lookup"><span data-stu-id="89728-139">IIS processes:</span></span>

  - <span data-ttu-id="89728-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="89728-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="89728-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="89728-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="89728-142">SQL Server 백 엔드 프로세스:</span><span class="sxs-lookup"><span data-stu-id="89728-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="89728-143">이러한 경로는 SQL Server 버전과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89728-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="89728-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11. MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="89728-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="89728-145">%ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="89728-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="89728-146">%ProgramFiles%\Microsoft SQL Server\MSAS11. MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="89728-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="89728-147">SQL Server 프런트 엔드 프로세스:</span><span class="sxs-lookup"><span data-stu-id="89728-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="89728-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12. LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="89728-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="89728-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12. RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="89728-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="89728-150">Standard Edition 설치 RTC 인스턴스</span><span class="sxs-lookup"><span data-stu-id="89728-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="89728-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12. RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="89728-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="89728-152">디렉터리 및 파일:</span><span class="sxs-lookup"><span data-stu-id="89728-152">Directories and files:</span></span>

  - <span data-ttu-id="89728-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="89728-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="89728-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="89728-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="89728-155">%systemroot%\Microsoft.NET\assembly\ GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="89728-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="89728-156">이러한 경로는 비즈니스용 Skype 서버 버전과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89728-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="89728-157">%programfiles%\Skype 비즈니스 서버 2015</span><span class="sxs-lookup"><span data-stu-id="89728-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="89728-158">%programfiles%\Common Files\Skype Business Server 2015 \ 감시자 노드</span><span class="sxs-lookup"><span data-stu-id="89728-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="89728-159">%programfiles%\Common Files\Skype for Business 서버 2015</span><span class="sxs-lookup"><span data-stu-id="89728-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="89728-160">비즈니스용%programfiles%\Common Files\Skype Online</span><span class="sxs-lookup"><span data-stu-id="89728-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="89728-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="89728-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="89728-162">파일 공유 저장소 (토폴로지 작성기에서 지정)</span><span class="sxs-lookup"><span data-stu-id="89728-162">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="89728-163">파일 저장소는 토폴로지 작성기에 지정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89728-163">File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="89728-164">백 엔드 데이터베이스, 사용자 저장소, 보관 저장소, 모니터링 저장소 및 응용 프로그램 저장소를 포함 하는 SQL Server 데이터 및 로그 파일</span><span class="sxs-lookup"><span data-stu-id="89728-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="89728-165">토폴로지 작성기에서 데이터베이스 및 로그 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89728-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="89728-166">기본 이름을 포함 하 여 각 데이터베이스의 데이터 및 로그 파일에 대 한 자세한 내용은 배포 설명서에서 [SQL Server 데이터 및 로그 파일 배치](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="89728-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="89728-167">프런트 엔드 데이터베이스, 비즈니스용 Skype 스토어, RtcDatabase 저장소 등의 SQL Server 데이터 및 로그 파일</span><span class="sxs-lookup"><span data-stu-id="89728-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="89728-168">일반적 으로%localdrive%\CSData. 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89728-168">They are normally under %localdrive%\CSData.</span></span>


