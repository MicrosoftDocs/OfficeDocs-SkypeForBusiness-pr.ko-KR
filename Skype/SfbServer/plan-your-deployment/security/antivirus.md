---
title: 비즈니스용 Skype 서버에 대 한 바이러스 백신 검색 제외
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: 비즈니스용 Skype 서버와의 바이러스 검사 프로그램 상호 운용을 간략하게 설명 합니다.
ms.openlocfilehash: 9ec13b31328744bb154c9eb5e09dff7665c4b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196843"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a><span data-ttu-id="ce369-103">비즈니스용 Skype 서버에 대 한 바이러스 백신 검색 제외</span><span class="sxs-lookup"><span data-stu-id="ce369-103">Antivirus scanning exclusions for Skype for Business Server</span></span>

<span data-ttu-id="ce369-104">비즈니스용 Skype 서버와의 바이러스 검사 프로그램 상호 운용을 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce369-104">Overview of antivirus scanner interoperation with Skype for Business Server.</span></span>

<span data-ttu-id="ce369-105">이 문서에는 Active Directory 도메인에서 바이러스 백신 소프트웨어를 사용 하는 경우 지원 되는 버전의 Microsoft Windows를 실행 하는 컴퓨터에서 발생 가능한 불안정성의 원인을 확인 하는 데 도움이 되는 권장 사항이 포함 되어 있습니다. 환경 또는 관리 비즈니스 환경</span><span class="sxs-lookup"><span data-stu-id="ce369-105">This article contains recommendations that may help an administrator determine the cause of potential instability on a computer that is running a supported version of Microsoft Windows when it is used with antivirus software in an Active Directory domain environment or in a managed business environment.</span></span>

<span data-ttu-id="ce369-106">시스템을 평가 하기 위해 이러한 절차를 일시적으로 적용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ce369-106">We recommend that you temporarily apply these procedures to evaluate a system.</span></span> <span data-ttu-id="ce369-107">이 문서의 권장 사항에 따라 시스템 성능 또는 안정성이 향상 되는 경우 바이러스 백신 소프트웨어 공급 업체에 문의 하 여 지침을 참조 하거나 바이러스 백신 소프트웨어의 업데이트 된 버전을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce369-107">If your system performance or stability is improved by the recommendations that are made in this article, contact your antivirus software vendor for instructions or for an updated version of the antivirus software.</span></span>

<span data-ttu-id="ce369-108">이 문서에는 보안 설정을 낮추거나 컴퓨터에서 보안 기능을 일시적으로 해제 하는 방법을 보여 주는 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce369-108">This article contains information that shows how to help lower security settings or how to temporarily turn off security features on a computer.</span></span> <span data-ttu-id="ce369-109">특정 문제의 특성을 이해 하기 위해 이러한 변경 내용을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce369-109">You can make these changes to understand the nature of a specific problem.</span></span> <span data-ttu-id="ce369-110">이러한 변경 작업을 수행 하기 전에 특정 환경에서이 해결 방법을 구현 하는 것과 관련 된 위험을 평가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ce369-110">Before you make these changes, we recommend that you evaluate the risks that are associated with implementing this workaround in your particular environment.</span></span> <span data-ttu-id="ce369-111">이 해결 방법을 구현 하는 경우 바이러스 백신 소프트웨어로 더 이상 검색 하지 않는 파일에 대해 컴퓨터를 보호 하는 적절 한 추가 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce369-111">If you implement this workaround, take any appropriate additional steps to help protect the computer for the files that are no longer being scanned by your antivirus software.</span></span>

<span data-ttu-id="ce369-112">바이러스 백신 스캐너가 비즈니스용 Skype 서버의 작동을 방해 하지 않도록 하려면 바이러스 검사 프로그램을 실행 하는 각 비즈니스용 Skype Server server 또는 서버 역할에 대 한 특정 프로세스 및 디렉터리를 제외 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce369-112">To ensure that the antivirus scanner does not interfere with the operation of Skype for Business Server, you must exclude specific processes and directories for each Skype for Business Server server or server role on which you run an antivirus scanner.</span></span> <span data-ttu-id="ce369-113">다음 프로세스 및 디렉터리는 제외 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce369-113">The following processes and directories should be excluded:</span></span>

> [!NOTE]
> <span data-ttu-id="ce369-114">아래 나열 된 폴더 및 파일 위치는 비즈니스용 Skype 서버의 기본 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="ce369-114">Folder and file locations listed below are the default locations for Skype for Business Server.</span></span> <span data-ttu-id="ce369-115">기본값을 사용 하지 않은 위치의 경우이 항목에 지정 된 기본 위치 대신 조직에 대해 지정한 위치를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce369-115">For any locations for which you did not use the default, exclude the locations you specified for your organization instead of the default locations specified in this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce369-116">일부 바이러스 백신 프로그램에는 제외 목록에 대 한 상대 경로가 아닌 절대적인 필요이 있을 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce369-116">Please note that some antivirus programs may need absolute, not relative paths, for their exclusion list.</span></span>

- <span data-ttu-id="ce369-117">비즈니스용 Skype 서버 프로세스:</span><span class="sxs-lookup"><span data-stu-id="ce369-117">Skype for Business Server processes:</span></span>

  - <span data-ttu-id="ce369-118">ABServer .exe</span><span class="sxs-lookup"><span data-stu-id="ce369-118">ABServer.exe</span></span>

  - <span data-ttu-id="ce369-119">ASMCUSvc .exe</span><span class="sxs-lookup"><span data-stu-id="ce369-119">ASMCUSvc.exe</span></span>

  - <span data-ttu-id="ce369-120">AVMCUSvc .exe</span><span class="sxs-lookup"><span data-stu-id="ce369-120">AVMCUSvc.exe</span></span>

  - <span data-ttu-id="ce369-121">ChannelService .exe</span><span class="sxs-lookup"><span data-stu-id="ce369-121">ChannelService.exe</span></span>

  - <span data-ttu-id="ce369-122">ClsAgent .exe</span><span class="sxs-lookup"><span data-stu-id="ce369-122">ClsAgent.exe</span></span>

  - <span data-ttu-id="ce369-123">ComplianceService</span><span class="sxs-lookup"><span data-stu-id="ce369-123">ComplianceService.exe</span></span>

  - <span data-ttu-id="ce369-124">DataMCUSvc</span><span class="sxs-lookup"><span data-stu-id="ce369-124">DataMCUSvc.exe</span></span>

  - <span data-ttu-id="ce369-125">DataProxy</span><span class="sxs-lookup"><span data-stu-id="ce369-125">DataProxy.exe</span></span>

  - <span data-ttu-id="ce369-126">FileTransferAgent</span><span class="sxs-lookup"><span data-stu-id="ce369-126">FileTransferAgent.exe</span></span>

  - <span data-ttu-id="ce369-127">HealthAgent</span><span class="sxs-lookup"><span data-stu-id="ce369-127">HealthAgent.exe</span></span>

  - <span data-ttu-id="ce369-128">IMMCUSvc .exe</span><span class="sxs-lookup"><span data-stu-id="ce369-128">IMMCUSvc.exe</span></span>
  
  - <span data-ttu-id="ce369-129">L<c13> Cbackupservices .exe</span><span class="sxs-lookup"><span data-stu-id="ce369-129">LyncBackupService.exe</span></span>

  - <span data-ttu-id="ce369-130">LysSvc</span><span class="sxs-lookup"><span data-stu-id="ce369-130">LysSvc.exe</span></span>

  - <span data-ttu-id="ce369-131">MasterReplicatorAgent</span><span class="sxs-lookup"><span data-stu-id="ce369-131">MasterReplicatorAgent.exe</span></span>

  - <span data-ttu-id="ce369-132">MediaRelaySvc</span><span class="sxs-lookup"><span data-stu-id="ce369-132">MediaRelaySvc.exe</span></span>

  - <span data-ttu-id="ce369-133">MediationServerSvc</span><span class="sxs-lookup"><span data-stu-id="ce369-133">MediationServerSvc.exe</span></span>

  - <span data-ttu-id="ce369-134">MRASSvc</span><span class="sxs-lookup"><span data-stu-id="ce369-134">MRASSvc.exe</span></span>

  - <span data-ttu-id="ce369-135">OcsAppServerHost</span><span class="sxs-lookup"><span data-stu-id="ce369-135">OcsAppServerHost.exe</span></span>

  - <span data-ttu-id="ce369-136">ReplicaReplicatorAgent</span><span class="sxs-lookup"><span data-stu-id="ce369-136">ReplicaReplicatorAgent.exe</span></span>

  - <span data-ttu-id="ce369-137">ReplicationApp</span><span class="sxs-lookup"><span data-stu-id="ce369-137">ReplicationApp.exe</span></span>

  - <span data-ttu-id="ce369-138">RtcHost</span><span class="sxs-lookup"><span data-stu-id="ce369-138">RtcHost.exe</span></span>

  - <span data-ttu-id="ce369-139">RTCSrv</span><span class="sxs-lookup"><span data-stu-id="ce369-139">RTCSrv.exe</span></span>

  - <span data-ttu-id="ce369-140">XmppProxy</span><span class="sxs-lookup"><span data-stu-id="ce369-140">XmppProxy.exe</span></span>

  - <span data-ttu-id="ce369-141">XmppTGW</span><span class="sxs-lookup"><span data-stu-id="ce369-141">XmppTGW.exe</span></span>

- <span data-ttu-id="ce369-142">Windows Fabric Host 서비스 프로세스:</span><span class="sxs-lookup"><span data-stu-id="ce369-142">Windows Fabric Host Service processes:</span></span>

  - <span data-ttu-id="ce369-143">Printbrm.exe</span><span class="sxs-lookup"><span data-stu-id="ce369-143">Fabric.exe</span></span>

  - <span data-ttu-id="ce369-144">FabricDCA</span><span class="sxs-lookup"><span data-stu-id="ce369-144">FabricDCA.exe</span></span>

  - <span data-ttu-id="ce369-145">FabricHost</span><span class="sxs-lookup"><span data-stu-id="ce369-145">FabricHost.exe</span></span>

- <span data-ttu-id="ce369-146">IIS 프로세스:</span><span class="sxs-lookup"><span data-stu-id="ce369-146">IIS processes:</span></span>

  - <span data-ttu-id="ce369-147">%systemroot%\system32\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="ce369-147">%systemroot%\system32\inetsrv\w3wp.exe</span></span>

  - <span data-ttu-id="ce369-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span><span class="sxs-lookup"><span data-stu-id="ce369-148">%systemroot%\SysWOW64\inetsrv\w3wp.exe</span></span>

- <span data-ttu-id="ce369-149">SQL Server 백 엔드 프로세스:</span><span class="sxs-lookup"><span data-stu-id="ce369-149">SQL Server Back-End processes:</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce369-150">이러한 경로는 SQL Server 버전과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce369-150">Note that these paths are specific to SQL Server version.</span></span>

  - <span data-ttu-id="ce369-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11. MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="ce369-151">%ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="ce369-152">%ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span><span class="sxs-lookup"><span data-stu-id="ce369-152">%ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe</span></span>

  - <span data-ttu-id="ce369-153">%ProgramFiles%\Microsoft SQL Server\MSAS11. MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span><span class="sxs-lookup"><span data-stu-id="ce369-153">%ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe</span></span>

- <span data-ttu-id="ce369-154">SQL Server 프런트 엔드 프로세스:</span><span class="sxs-lookup"><span data-stu-id="ce369-154">SQL Server Front-End processes:</span></span>

  - <span data-ttu-id="ce369-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12. LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="ce369-155">%ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="ce369-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12. RTCLOCAL\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="ce369-156">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe</span></span>

  - <span data-ttu-id="ce369-157">Standard Edition 설치 RTC 인스턴스</span><span class="sxs-lookup"><span data-stu-id="ce369-157">Standard Edition Installation RTC Instance</span></span>

  - <span data-ttu-id="ce369-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12. RTC\MSSQL\Binn\SQLServr.exe</span><span class="sxs-lookup"><span data-stu-id="ce369-158">%ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe</span></span>

- <span data-ttu-id="ce369-159">디렉터리 및 파일:</span><span class="sxs-lookup"><span data-stu-id="ce369-159">Directories and files:</span></span>

  - <span data-ttu-id="ce369-160">%systemroot%\System32\LogFiles</span><span class="sxs-lookup"><span data-stu-id="ce369-160">%systemroot%\System32\LogFiles</span></span>

  - <span data-ttu-id="ce369-161">%systemroot%\SysWow64\LogFiles</span><span class="sxs-lookup"><span data-stu-id="ce369-161">%systemroot%\SysWow64\LogFiles</span></span>

  - <span data-ttu-id="ce369-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span><span class="sxs-lookup"><span data-stu-id="ce369-162">%systemroot%\Microsoft.NET\assembly\GAC_MSIL</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce369-163">이러한 경로는 비즈니스용 Skype 서버 버전과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce369-163">Note that these paths are specific to Skype for Business Server version.</span></span>

  - <span data-ttu-id="ce369-164">%programfiles%\Skype 비즈니스 서버 2015</span><span class="sxs-lookup"><span data-stu-id="ce369-164">%programfiles%\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="ce369-165">%programfiles%\Common Files\Skype Business Server 2015 \ 감시자 노드</span><span class="sxs-lookup"><span data-stu-id="ce369-165">%programfiles%\Common Files\Skype for Business Server 2015\Watcher Node</span></span>

  - <span data-ttu-id="ce369-166">%programfiles%\Common Files\Skype for Business 서버 2015</span><span class="sxs-lookup"><span data-stu-id="ce369-166">%programfiles%\Common Files\Skype for Business Server 2015</span></span>

  - <span data-ttu-id="ce369-167">비즈니스용%programfiles%\Common Files\Skype Online</span><span class="sxs-lookup"><span data-stu-id="ce369-167">%programfiles%\Common Files\Skype for Business Online</span></span>

  - <span data-ttu-id="ce369-168">%SystemDrive%\RtcReplicaRoot</span><span class="sxs-lookup"><span data-stu-id="ce369-168">%SystemDrive%\RtcReplicaRoot</span></span>

  - <span data-ttu-id="ce369-169">파일 공유 저장소 (토폴로지 작성기에서 지정)</span><span class="sxs-lookup"><span data-stu-id="ce369-169">File share store (specified in Topology Builder).</span></span> <span data-ttu-id="ce369-170">파일 저장소는 토폴로지 작성기에 지정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce369-170">File stores are specified in Topology Builder.</span></span>

  - <span data-ttu-id="ce369-171">백 엔드 데이터베이스, 사용자 저장소, 보관 저장소, 모니터링 저장소 및 응용 프로그램 저장소를 포함 하는 SQL Server 데이터 및 로그 파일</span><span class="sxs-lookup"><span data-stu-id="ce369-171">SQL Server data and log files, including those for the back-end database, user store, archiving store, monitoring store, and application store.</span></span> <span data-ttu-id="ce369-172">토폴로지 작성기에서 데이터베이스 및 로그 파일을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce369-172">Database and log files can be specified in Topology Builder.</span></span> <span data-ttu-id="ce369-173">기본 이름을 포함 하 여 각 데이터베이스의 데이터 및 로그 파일에 대 한 자세한 내용은 배포 설명서에서 [SQL Server 데이터 및 로그 파일 배치](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce369-173">For details about the data and log files for each database, including default names, see [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span>

  - <span data-ttu-id="ce369-174">프런트 엔드 데이터베이스, 비즈니스용 Skype 스토어, RtcDatabase 저장소 등의 SQL Server 데이터 및 로그 파일</span><span class="sxs-lookup"><span data-stu-id="ce369-174">SQL Server data and log files, including those for the Front-end database, Skype for Business store, and RtcDatabase store.</span></span> <span data-ttu-id="ce369-175">일반적으로%localdrive%\CSData. 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce369-175">They are normally under %localdrive%\CSData.</span></span>


