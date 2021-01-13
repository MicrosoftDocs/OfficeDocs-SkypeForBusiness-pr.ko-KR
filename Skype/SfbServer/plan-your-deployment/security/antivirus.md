---
title: 비즈니스용 Skype 서버에 대한 바이러스 백신 검사 제외
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: 비즈니스용 Skype 서버와의 바이러스 백신 스캐너 상호 작동 개요.
ms.openlocfilehash: b59a5c474a96d312ebe3a648536ebe827e684931
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832268"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="aeef7-103">비즈니스용 Skype 서버에 대한 바이러스 백신 검사 제외</span><span class="sxs-lookup"><span data-stu-id="aeef7-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="aeef7-104">비즈니스용 Skype 서버와의 바이러스 백신 스캐너 상호 작동 개요.</span><span class="sxs-lookup"><span data-stu-id="aeef7-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="aeef7-105">바이러스 백신 스캐너가 비즈니스용 Skype 서버의 작동을 방해하지 않도록 하기 위해 바이러스 백신 스캐너를 실행한 각 비즈니스용 Skype 서버 서버 또는 서버 역할에 대한 특정 프로세스 및 Directories를 제외해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeef7-105">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="aeef7-106">다음과 같은 프로세스 및 디렉터리를 제외해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aeef7-106">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="aeef7-107">아래에 나열된 폴더 및 파일 위치는 비즈니스용 Skype 서버의 기본 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="aeef7-107">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="aeef7-108">기본값을 그대로 사용하지 않은 위치의 경우 이 항목에 지정된 기본 위치 대신 조직에서 사용자가 지정한 위치를 제외하십시오.</span><span class="sxs-lookup"><span data-stu-id="aeef7-108">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aeef7-109">일부 바이러스 백신 프로그램은 제외 목록에 상대 경로가 아닌 절대 경로가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeef7-109">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="aeef7-110">비즈니스용 Skype 서버 프로세스:</span><span class="sxs-lookup"><span data-stu-id="aeef7-110">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="aeef7-111">ABServer.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-111">ABServer.exe</span></span>

  - <span data-ttu-id="aeef7-112">ASMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-112">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="aeef7-113">AVMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-113">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="aeef7-114">ChannelService.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-114">ChannelService.exe</span></span>

  - <span data-ttu-id="aeef7-115">ClsAgent.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-115">ClsAgent.exe</span></span>

  - <span data-ttu-id="aeef7-116">ComplianceService.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-116">ComplianceService.exe</span></span>

  - <span data-ttu-id="aeef7-117">DataMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-117">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="aeef7-118">DataProxy.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-118">DataProxy.exe</span></span>

  - <span data-ttu-id="aeef7-119">FileTransferAgent.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-119">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="aeef7-120">HealthAgent.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-120">HealthAgent.exe</span></span>

  - <span data-ttu-id="aeef7-121">IMMCUSvc.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-121">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="aeef7-122">LyncBackupService.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-122">LyncBackupService.exe</span></span>

  - <span data-ttu-id="aeef7-123">LysSvc.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-123">LysSvc.exe</span></span>

  - <span data-ttu-id="aeef7-124">MasterReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-124">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="aeef7-125">MediaRelaySvc.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-125">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="aeef7-126">MediationServerSvc.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-126">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="aeef7-127">MRASSvc.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-127">MRASSvc.exe</span></span>

  - <span data-ttu-id="aeef7-128">OcsAppServerHost.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-128">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="aeef7-129">ReplicaReplicatorAgent.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-129">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="aeef7-130">ReplicationApp.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-130">ReplicationApp.exe</span></span>

  - <span data-ttu-id="aeef7-131">RtcHost.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-131">RtcHost.exe</span></span>

  - <span data-ttu-id="aeef7-132">RTCSrv.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-132">RTCSrv.exe</span></span>

  - <span data-ttu-id="aeef7-133">XmppProxy.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-133">XmppProxy.exe</span></span>

  - <span data-ttu-id="aeef7-134">XmppTGW.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-134">XmppTGW.exe</span></span>

- <span data-ttu-id="aeef7-135">Windows Fabric 호스트 서비스 프로세스:</span><span class="sxs-lookup"><span data-stu-id="aeef7-135">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="aeef7-136">Fabric.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-136">Fabric.exe</span></span>

  - <span data-ttu-id="aeef7-137">FabricDCA.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-137">FabricDCA.exe</span></span>

  - <span data-ttu-id="aeef7-138">FabricHost.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-138">FabricHost.exe</span></span>

- <span data-ttu-id="aeef7-139">IIS 프로세스:</span><span class="sxs-lookup"><span data-stu-id="aeef7-139">IIS processes:</span></span>

  - <span data-ttu-id="aeef7-140">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-140">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="aeef7-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-141">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="aeef7-142">SQL Server Back-End 프로세스:</span><span class="sxs-lookup"><span data-stu-id="aeef7-142">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="aeef7-143">이러한 경로는 특정 버전과 SQL Server 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeef7-143">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="aeef7-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-144">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="aeef7-145">%ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-145">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="aeef7-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-146">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="aeef7-147">SQL Server Front-End 프로세스:</span><span class="sxs-lookup"><span data-stu-id="aeef7-147">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="aeef7-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-148">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="aeef7-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-149">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="aeef7-150">Standard Edition 설치 RTC 인스턴스</span><span class="sxs-lookup"><span data-stu-id="aeef7-150">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="aeef7-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="aeef7-151">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="aeef7-152">디렉터리 및 파일:</span><span class="sxs-lookup"><span data-stu-id="aeef7-152">Directories and files:</span></span>

  - <span data-ttu-id="aeef7-153">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="aeef7-153">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="aeef7-154">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="aeef7-154">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="aeef7-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="aeef7-155">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="aeef7-156">이러한 경로는 비즈니스용 Skype 서버 버전과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeef7-156">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="aeef7-157">%programfiles%\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="aeef7-157">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="aeef7-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span><span class="sxs-lookup"><span data-stu-id="aeef7-158">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="aeef7-159">%programfiles%\Common Files\Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="aeef7-159">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="aeef7-160">%programfiles%\Common Files\Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="aeef7-160">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="aeef7-161">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="aeef7-161">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="aeef7-p103">파일 공유 저장소(토폴로지 작성기에서 지정). 파일 저장소는 토폴로지 작성기에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="aeef7-p103">File share store (specified in Topology Builder). File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="aeef7-164">백 엔드 데이터베이스, 사용자 저장소, 보관 저장소, 모니터링 저장소 및 응용 프로그램 저장소에 대한 항목을 포함하는 SQL Server 데이터 및 로그 파일.</span><span class="sxs-lookup"><span data-stu-id="aeef7-164">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="aeef7-165">데이터베이스 및 로그 파일은 토폴로지 작성기에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeef7-165">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="aeef7-166">기본 이름을 포함하여 각 데이터베이스의 데이터 및 로그 파일에 대한 자세한 내용은 배포 설명서의 [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="aeef7-166">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="aeef7-167">SQL Server 데이터베이스, 비즈니스용 Skype 저장소 및 RtcDatabase 저장소를 비롯한 데이터 및 로그 파일을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeef7-167">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="aeef7-168">일반적으로 %localdrive%\CSData 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aeef7-168">They are normally under %localdrive%\CSData.</span></span>


