---
title: 비즈니스용 Skype 서버에 대 한 통화 품질 대시보드 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: '요약: 통화 품질 대시보드의 배포 프로세스에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버에 대 한 도구입니다.'
ms.openlocfilehash: 5879c4a99eec8471763e0fccc3a4886be660dbb6
ms.sourcegitcommit: 54cbcf917d9663e6aa9760d7399b36c00d66478c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2020
ms.locfileid: "42840162"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="1435a-104">비즈니스용 Skype 서버에 대 한 통화 품질 대시보드 배포</span><span class="sxs-lookup"><span data-stu-id="1435a-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="1435a-105">**요약:** 통화 품질 대시보드의 배포 프로세스에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="1435a-106">통화 품질 대시보드는 비즈니스용 Skype 서버에 대 한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="1435a-107">배포 개요</span><span class="sxs-lookup"><span data-stu-id="1435a-107">Deployment Overview</span></span>

<span data-ttu-id="1435a-108">CQD (통화 품질 대시보드)는 다음과 같은 세 가지 주요 구성 요소로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="1435a-109">**보관 데이터베이스**(QoE) 데이터를 복제 하 고 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="1435a-110">QoE 보관 데이터베이스의 데이터가 최적화 되 고 빠른 액세스를 위해 집계 되는 **큐브**</span><span class="sxs-lookup"><span data-stu-id="1435a-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="1435a-111">**포털**-사용자가 QoE 데이터를 쉽게 쿼리하고 시각화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![CQD 구성 요소](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="1435a-113">QoE 보관을 위한 설치 프로세스에는 QoE 보관 데이터베이스를 만들고, 원본 QoE 메트릭 데이터베이스의 데이터를 QoE 보관 데이터베이스로 이동 하 고, SQL Server 에이전트 작업을 설정 하 여 저장 된 데이터베이스를 실행 하는 SQL Server 저장 프로시저를 배포 하는 작업이 포함 됩니다. 정기적으로 프로시저를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="1435a-114">큐브 배포는 QoE 보관 사서함이 있는 사용자 로부터 정보를 가져오고, 큐브를 배포 하 고, 정기적으로 큐브를 새로 고치는 정기적인 SQL Server 에이전트 작업을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="1435a-115">Portal 설치 각 사용자의 보고서/쿼리에 CQD 사용자 매핑을 저장 하는 리포지토리 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="1435a-116">그런 다음 사용자 지정 및 직접 쿼리를 만들어 큐브의 데이터를 시각화 하는 대시보드 인 IIS 웹 응용 프로그램을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="1435a-117">Portal 설치 프로그램에서는 사용자가 리포지토리 및 큐브에 프로그래밍 방식으로 액세스할 수 있도록 Api를 제공 하는 두 개의 추가 웹 응용 프로그램이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="1435a-118">이러한 Api는 대시보드의 내부에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="1435a-119">**작업 단계**</span><span class="sxs-lookup"><span data-stu-id="1435a-119">**Phase**</span></span>|<span data-ttu-id="1435a-120">**단계**</span><span class="sxs-lookup"><span data-stu-id="1435a-120">**Steps**</span></span>|<span data-ttu-id="1435a-121">**역할 및 그룹 구성원**</span><span class="sxs-lookup"><span data-stu-id="1435a-121">**Roles and group membership**</span></span>|<span data-ttu-id="1435a-122">**설명서**</span><span class="sxs-lookup"><span data-stu-id="1435a-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1435a-123">하드웨어 및 소프트웨어 필수 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="1435a-124">CQD 구성을 결정 하 고 설치를 수행할 SQL Server를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="1435a-125">로컬 Administrators 그룹의 구성원인 도메인 사용자</span><span class="sxs-lookup"><span data-stu-id="1435a-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="1435a-126">배포 설명서의 "사전 설치 요구 사항" 섹션</span><span class="sxs-lookup"><span data-stu-id="1435a-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="1435a-127">CQD 설치</span><span class="sxs-lookup"><span data-stu-id="1435a-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="1435a-128">배포 문서 다음에 MSI를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="1435a-129">설치를 수행 하려면 설치 하는 계정은 로컬 administrators 그룹의 구성원 인 도메인 사용자 여야 하며 모니터링 서버의 QoE 메트릭 데이터베이스에 대 한 읽기 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="1435a-130">배포 설명서의 "계정 및 배포 단계" 섹션</span><span class="sxs-lookup"><span data-stu-id="1435a-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="1435a-131">사용자에 게 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="1435a-132">포털에 대 한 사용자 권한 부여를 관리 하려면 IIS 7.0에 도입 된 URL 권한 부여를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="1435a-133">자세한 내용은 [IIS 7.0 URL 권한 부여 이해](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)(영문)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1435a-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="1435a-134">로컬 Administrators 그룹의 구성원인 도메인 사용자</span><span class="sxs-lookup"><span data-stu-id="1435a-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="1435a-135">배포 설명서의 포털 섹션에 대 한 사용자 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="1435a-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="1435a-136">선택 사항: 서브넷 매핑 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="1435a-137">QoE 보관 데이터베이스에서 네트워크 및 건물 매핑 테이블을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="1435a-138">QoE 보관 데이터베이스에 대 한 쓰기 권한이 있는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="1435a-139">사용자 설명서의 "서브넷 정보 제공" 섹션</span><span class="sxs-lookup"><span data-stu-id="1435a-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="1435a-140">통화 품질 대시보드를 배포 하려면 인프라를 설정 하 고 소프트웨어를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="1435a-141">다음 절차에서는이 프로세스를 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="1435a-142">배포 단계</span><span class="sxs-lookup"><span data-stu-id="1435a-142">Deployment Steps</span></span>

1. <span data-ttu-id="1435a-143">CQD의 보관 데이터베이스 구성 요소가 설치 될 컴퓨터 (SQL Server가 설치 된 컴퓨터)에 CallQualityDashboard를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="1435a-144">MSI를 실행 합니다 (Windows에서 관리자 권한으로 실행 하 라는 메시지가 표시 됨).</span><span class="sxs-lookup"><span data-stu-id="1435a-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="1435a-145">사용권 계약서에 동의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="1435a-146">통화 품질 대시보드 구성 요소와 관련 된 파일을 찾을 대상 폴더를 선택 하거나 기본 위치를 그대로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="1435a-147">모든 기능을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-147">Select all features.</span></span>
    
6. <span data-ttu-id="1435a-148">QoE 보관 구성 페이지에서 다음 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="1435a-149">**QoE 메트릭 SQL Server:** QoE 메트릭 DB가 있는 (데이터 원본이 됨) SQL Server 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="1435a-150">**QoE 보관 SQL Server 이름:** 이 필드는 읽기 전용으로 로컬 컴퓨터의 정규화 된 도메인 이름으로 고정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="1435a-151">보관 데이터베이스는 로컬 컴퓨터에만 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="1435a-152">**QoE ARCHIVE SQL Server 인스턴스:** 보관 데이터베이스를 만들 로컬 SQL Server 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="1435a-153">기본 SQL Server 인스턴스를 사용 하려면이 필드를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="1435a-154">명명 된 SQL Server 인스턴스를 사용 하려면 인스턴스 이름 (예: 이름 뒤에 "\")을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="1435a-155">**QoE 보관 데이터베이스:** 기본적으로이 옵션은 "새 데이터베이스 만들기"로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="1435a-156">보관 DB 업그레이드는 지원 되지 않으므로 "기존 데이터베이스 사용" 옵션을 사용할 수 있는 유일한 경우는 기존 보관 데이터베이스에 설치할 빌드와 같은 스키마가 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="1435a-157">**데이터베이스 파일 디렉터리:** 보관 DB 데이터베이스 파일 (.mdf 및 .ldf)이 위치할 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="1435a-158">이는 OS와 별개인 드라이브 (권장 하드웨어 구성의 HDD2)에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="1435a-159">파일 이름이 설치 중에 수정 되므로 잠재적인 충돌을 방지 하기 위해 파일이 없는 빈 디렉터리를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="1435a-160">**여러 파티션 사용:** 기본값은 Business Intelligence edition 또는 Enterprise edition SQL Server가 필요한 "여러 파티션"으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="1435a-161">Standard edition의 경우 "단일 파티션" 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="1435a-162">단일 파티션을 사용 하는 경우에는 큐브 처리 성능이 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="1435a-163">설치가 완료 되 면 여러 파티션 사용 옵션을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="1435a-164">이를 변경 하려면 먼저 큐브 기능을 제거한 다음 제어판의 "변경" 옵션을 사용 하 여 다시 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="1435a-165">**파티션 파일 디렉터리:** QoE 보관 데이터베이스에 대 한 파티션을 배치할 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="1435a-166">이는 OS 드라이브 및 SQL 데이터베이스 로그 파일 드라이브와는 별개의 드라이브 (권장 하드웨어 구성의 HDD3)에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="1435a-167">파일 이름이 설치 중에 수정 되므로 잠재적인 충돌을 방지 하기 위해 파일이 없는 빈 디렉터리를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="1435a-168">**SQL 에이전트 작업 사용자-사용자 이름 &amp; 암호:** SQL Server 에이전트 작업의 "QoE 보관 데이터" 단계 (저장 프로시저를 실행 하 여 QoE 메트릭 DB에서 보관 DB로 데이터를 페치 함)를 실행 하는 데 사용 되는,이 계정에는 Accounts 섹션에 나와 있는 것 처럼 QoE 메트릭 DB에 대 한 읽기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="1435a-169">또한이 계정에는 QoE Archive SQL Server 인스턴스에 로그인이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="1435a-170">SQL Server 인스턴스가 실행 중인 계정 (예: NT SERVICE\MSSQLSERVER)에는 설치에 성공 하기 위해 위에 지정 된 디렉터리에 대 한 액세스/권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="1435a-171">자세한 내용은 [데이터베이스 엔진 액세스에 대 한 파일 시스템 권한 구성](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1435a-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="1435a-172">다음을 클릭 하면 설치 관리자가 필수 구성 요소 검사를 수행 하 고 문제가 발생 한 경우 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="1435a-173">모든 필수 구성 요소 확인이 통과 되 면 설치 관리자는 큐브 구성 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1435a-174">설치 관리자에 QoE Archive SQL Server 인스턴스에 대 한 SQL Server 에이전트 서비스가 현재 실행 되 고 있지 않은 경고 메시지가 표시 되 면 설치를 계속할 수 있지만 설치 후에는 SQL 에이전트 서비스가 실행 되 고 있는지 확인 하 고 시작 유형을 다음으로 설정 해야 합니다. 자동으로 예약 된 작업을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="1435a-175">큐브 구성 페이지에서 다음 정보를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="1435a-176">**QoE 보관 SQL Server 이름:** 이 필드는 읽기 전용으로 로컬 컴퓨터의 정규화 된 도메인 이름으로 고정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="1435a-177">QoE 보관 데이터베이스가 있는 컴퓨터 에서만 큐브를 설치할 수 있습니다 (참고).</span><span class="sxs-lookup"><span data-stu-id="1435a-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="1435a-178">큐브 자체가 원격 컴퓨터에 설치 되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="1435a-179">아래 참조)</span><span class="sxs-lookup"><span data-stu-id="1435a-179">See below)</span></span>
    
   - <span data-ttu-id="1435a-180">**QoE ARCHIVE SQL Server 인스턴스:** QoE 보관 데이터베이스를 배치할 SQL Server 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="1435a-181">기본 SQL Server 인스턴스를 지정 하려면이 필드를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="1435a-182">명명 된 SQL Server 인스턴스를 지정 하려면 인스턴스 이름 (예: 이름 뒤에 name\")을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="1435a-183">설치를 위해 QoE 보관 구성 요소를 선택한 경우이 필드는 QoE 보관 구성 페이지에 제공 된 값으로 미리 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="1435a-184">**큐브 분석 서버:** 큐브를 만들 SQL Server Analysis Service 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="1435a-185">이는 다른 컴퓨터 일 수 있지만 설치 사용자는 대상 SQL Server Analysis Services 인스턴스의 서버 관리자 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="1435a-186">Analysis Services 서버 관리자 권한을 구성 하는 방법에 대 한 자세한 내용은 [Grant Server Administrator permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1435a-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="1435a-187">**여러 파티션 사용:** 기본값은 Business Intelligence edition 또는 Enterprise edition SQL Server가 필요한 "여러 파티션"으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="1435a-188">Standard edition의 경우 "단일 파티션" 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="1435a-189">단일 파티션을 사용 하는 경우에는 큐브 처리 성능이 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="1435a-190">설치가 완료 되 면 여러 파티션 사용 옵션을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="1435a-191">이를 변경 하려면 먼저 큐브 기능을 제거한 다음 제어판의 "변경" 옵션을 사용 하 여 다시 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="1435a-192">**큐브 사용자-사용자 이름 &amp; 암호:** 큐브 처리를 시작할 도메인 서비스 계정 이름 및 암호 (마스크 됨)입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="1435a-193">QoE 보관 구성 요소를 설치 하도록 선택한 경우이 필드는 SQL 에이전트 작업 사용자의 보관 구성 페이지에 제공 된 값으로 미리 채워지고, 설치 프로그램에서 다음을 허용 하도록 다른 도메인 서비스 계정을 지정 하는 것이 좋습니다. 최소 필요한 권한</span><span class="sxs-lookup"><span data-stu-id="1435a-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="1435a-194">다음을 클릭 하면 다른 유효성 검사 라운드를 수행 하 고 문제가 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="1435a-195">유효성 검사가 성공적으로 완료 되 면 설치 관리자가 포털 구성 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="1435a-196">포털 구성 페이지에서 다음 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="1435a-197">**QoE 보관 SQL Server:** QoE 보관 데이터베이스가 있는 위치에 대 한 SQL Server 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="1435a-198">QoE 보관 구성 페이지와 큐브 구성 페이지와 달리 컴퓨터 이름은 고정 되어 있지 않으므로 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="1435a-199">설치를 위해 QoE 보관 구성 요소를 선택한 경우이 필드는 QoE 보관 구성 페이지에 제공 된 값으로 미리 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="1435a-200">**큐브 분석 서버:** 큐브가 있는 SQL Server Analysis Service 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="1435a-201">설치를 위해 큐브 구성 요소를 선택한 경우이 필드는 큐브 구성 페이지에서 제공 되는 값으로 미리 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="1435a-202">**리포지토리 SQL Server:** 리포지토리 데이터베이스를 만들 SQL Server 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="1435a-203">QoE 보관 데이터베이스가 있는 위치에 대 한 SQL Server 인스턴스 이름이 설치 프로그램에서 이전에 제공 된 경우 (기타 구성 요소)이 필드는 QoE 보관 DB SQL Server 인스턴스 이름으로 미리 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="1435a-204">모든 SQL Server 인스턴스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="1435a-205">**리포지토리 데이터베이스:** 기본적으로이 옵션은 "새 데이터베이스 만들기"로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="1435a-206">리포지토리 DB 업그레이드는 지원 되지 않으므로 "기존 데이터베이스 사용" 옵션을 사용할 수 있는 유일한 경우는 기존 리포지토리 DB에 설치할 빌드와 같은 스키마가 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="1435a-207">**IIS 응용 프로그램 풀 사용자-사용자 &amp; 이름 암호:** IIS 응용 프로그램 풀을 실행 해야 하는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="1435a-208">기본 제공 시스템 계정을 선택한 경우 사용자 이름 및 암호 필드가 회색으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="1435a-209">사용자가 도메인 서비스 계정 정보를 입력할 수 있도록 드롭다운 상자에서 "기타"를 선택한 경우에만 이러한 필드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="1435a-210">다음을 클릭 하면 마지막으로 유효성 검사를 수행 하 여 제공 된 자격 증명을 사용 하 여 SQL Server 인스턴스에 액세스할 수 있고 해당 컴퓨터에서 IIS를 사용할 수 있는지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="1435a-211">유효성 검사가 성공적으로 완료 되 면 설치 관리자는 설정을 계속 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="1435a-212">설치 관리자가 완료 되 면 SQL Server 에이전트 작업이 진행 중인 것 이며,이는 QoE 데이터의 초기 로드와 큐브 처리를 수행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="1435a-213">QoE의 데이터 양에 따라 포털에는 아직 볼 수 있는 데이터가 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="1435a-214">데이터 로드 및 큐브 처리 상태를 확인 하려면로 `http://<machinename>/CQD/#/Health`이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="1435a-215">다운로드 큐브 처리의 상태를 확인 하는 URL은 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="1435a-216">' Health '를 입력 하면 URL이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="1435a-217">대문자 H를 사용 하 여 URL의 끝에 ' Health '를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="1435a-218">디버그 모드를 사용 하는 경우 자세한 로그 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="1435a-219">디버그 모드를 사용 하도록 설정 하려면 **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**으로 이동 하 고 다음 줄을 업데이트 하 여 값을 **True**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="1435a-220">기본 포털 페이지는을 통해 `http://<machinename>/CQD`액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="1435a-221">포털에 대 한 사용자 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="1435a-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="1435a-222">포털에 대 한 사용자 권한 부여를 관리 하려면 IIS 7.0에 도입 된 URL 권한 부여를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="1435a-223">IIS 보안에 대 한 자세한 내용은 [iis 7.0 URL 권한 부여 이해](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)(영문)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1435a-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="1435a-224">모든 웹 사이트 또는 웹 응용 프로그램은 전체 IIS에 대해 구성 된 기본 URL 권한 부여 (일반적으로 "모든 사용자 허용")를 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="1435a-225">포털에 대 한 액세스를 보다 엄격 하 게 제한 해야 하는 경우 관리자는 "권한 부여 규칙"을 편집 하 여 특정 사용자 그룹 에게만 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![IIS에서 통화 품질-권한 부여 규칙 배포](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="1435a-227">권한 부여 규칙 아이콘은 서로 다른 인증 메커니즘인 ASP.NET 섹션에 있는 ".NET 인증"과 혼동 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="1435a-228">관리자는 먼저 상속 된 "모든 사용자에 게 허용" 규칙을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="1435a-229">이렇게 하면 권한이 없는 사용자가 포털에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![CQD 배포](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="1435a-231">다음으로, 관리자는 새 허용 규칙을 추가 하 고 특정 사용자에 게 포털 액세스 권한을 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="1435a-232">사용자를 관리 하기 위해 "CQDPortalUsers" 라는 로컬 그룹을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![통화 품질 대시보드 배포](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="1435a-234">구성 세부 정보는 포털의 실제 디렉터리에 있는 web.config에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="1435a-235">다음 단계에서는 CQD의 대시보드를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="1435a-236">사용자가 IIS에서 인증 된 후에는 웹 포털 콘텐츠에 액세스 하기 위해 CQD 디렉터리에 대 한 파일 사용 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="1435a-237">CQD 디렉터리 속성의 보안 탭을 통해 Acl을 변경 하 여 개별 사용자 또는 그룹을 추가할 수 있습니다. 그러나 권장 되는 방법은 파일 사용 권한을 그대로 유지 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="1435a-238">대신 IIS 작업자 프로세스를 사용 하 여 인증 된 사용자에 관계 없이 CQD 디렉터리에 액세스 하도록 IIS 설정을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1435a-239">두 가지 API 응용 프로그램 인 QoEDataService 및 QoERepositoryService에 대 한 것이 아니라 CQD 응용 프로그램에 대해서만이 설정을 변경 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="1435a-240">CQD (대시보드)에 대 한 파일 액세스 구성</span><span class="sxs-lookup"><span data-stu-id="1435a-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="1435a-241">CQD 용 구성 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-241">Open the Configuration Editor for CQD.</span></span>
    
     ![통화 품질 대시보드 배포](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="1435a-243">섹션에서 **system.webserver/serverRuntime**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![통화 품질 대시보드 배포](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="1435a-245">AuthenticatedUserOverride를 **Use2| Processuser**로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![통화 품질 대시보드 배포-구성 편집기](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="1435a-247">페이지 오른쪽에서 **적용** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="1435a-248">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="1435a-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="1435a-249">배포 후 CQD에 데이터가 표시 되지 않음</span><span class="sxs-lookup"><span data-stu-id="1435a-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="1435a-250">다음 오류가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-250">You may receive the following error:</span></span>

<span data-ttu-id="1435a-251">*큐브를 실행 하는 동안 쿼리를 수행할 수 없습니다. 쿼리 편집기를 사용 하 여 쿼리를 수정 하 고 문제를 수정 합니다. 또한 큐브에 액세스할 수 있는지 확인 합니다.*</span><span class="sxs-lookup"><span data-stu-id="1435a-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="1435a-252">즉, 큐브가 CQD에서 사용 되기 전에 SQL Server Analysis Services에서 처리 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="1435a-253">다음 단계를 수행 하 여이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="1435a-254">SQL Management Studio를 열고 **Analysis Services**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="1435a-255">**QoECube** 개체를 확장 하 고, **QoE Metric**을 선택한 다음, 마우스 오른쪽 단추를 클릭 하 고 **찾아보기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="1435a-256">이 경우 빈 브라우저가 반환 되 면 큐브가 아직 처리 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="1435a-257">**QoE Metric** angain을 마우스 오른쪽 단추로 클릭 하 고 **프로세스**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="1435a-258">처리가 완료 되 면 개체를 다시 마우스 오른쪽 단추로 클릭 하 고 **찾아보기를** 선택 하 여 브라우저 페이지에 데이터가 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="1435a-259">설치 관리자가 IIS에서 올바른 설정을 만들지 못했으므로 로그인 하는 데 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="1435a-260">드문 경우 지만 설치 관리자가 IIS에서 올바른 설정을 만들지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="1435a-261">수동 변경은 사용자가 CQD에 로그인 할 수 있도록 하기 위해 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="1435a-262">사용자가 로그인 하는 데 문제가 있는 경우 다음 단계를 수행 하세요.</span><span class="sxs-lookup"><span data-stu-id="1435a-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="1435a-263">IIS 관리자를 열고 기본 웹 사이트로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![통화 품질 대시보드 배포](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="1435a-265">"인증"을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-265">Click on "Authentication".</span></span> <span data-ttu-id="1435a-266">"익명 인증", "ASP.NET 가장", "폼 인증" 및 "Windows 인증"이 아래 표시 된 설정과 일치 하지 않으면 아래 설정과 일치 하도록 수동으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="1435a-267">다른 모든 인증 메커니즘을 사용 하지 않도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![통화 품질 대시보드 배포](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="1435a-269">"Windows 인증"의 경우 오른쪽의 고급 설정을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![통화 품질 대시보드 배포](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="1435a-271">"확장 된 보호"를 설정 하 여 수락 하 고 "커널 모드 인증 사용" 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![통화 품질 대시보드 배포](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="1435a-273">각 "CQD", "QoEDataService" 및 "QoERepositoryService" 항목 아래에 있는 "기본 웹 사이트" 아래에서 위의 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="1435a-274">HTTP 및 HTTPS 포트 바인딩의 경우 설치 관리자가 기본 포트 번호 (HTTP의 경우 포트 80, HTTPS의 경우 포트 443)에 포트 바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="1435a-275">컴퓨터에 이러한 바인딩을 사용 하는 다른 웹 사이트가 있으면 충돌이 발생 하 고 IIS 동작을 예측할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="1435a-276">이 문제를 방지 하는 가장 좋은 방법은 CQD를 설치 하기 전에 포트 80 및 443에 다른 웹 사이트가 매핑되어 있지 않은지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="1435a-277">IIS에서 SSL/TLS를 사용 하도록 설정 하 고 사용자가 HTTP 대신 보안 HTTPS를 통해 연결 하도록 강제 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="1435a-278">Secure Sockets layer 구성 IIS에서 [iis 7의 Secure sockets Layer 구성을](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1435a-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="1435a-279">작업이 완료 되 면 `http` 로 `https`대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="1435a-280">SQL Server 연결에서 TLS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [Microsoft Management Console을 사용 하 여 Sql server 인스턴스에 대해 SSL 암호화를 사용 하도록 설정 하는 방법을](https://support.microsoft.com/kb/316898/)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1435a-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="1435a-281">큐브 동기화 실패</span><span class="sxs-lookup"><span data-stu-id="1435a-281">Cube Sync Fails</span></span>

<span data-ttu-id="1435a-282">QoEMetrics에는 최종 사용자 시계를 기반으로 하는 일부 잘못 된 레코드가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="1435a-283">시간 기울이기를 60 yrs 보다 크면 큐브 가져오기가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="1435a-284">아래 선택을 사용 하 여 Min and Max StartTime/EndTime을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="1435a-285">레코드를 찾아서 삭제 하는 것이 가장 멀리, 그 이후에는 무시 하 고 동기화 프로세스를 중단 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="1435a-286">Cqdpartition Edstreamview에서 MIN (StartTime)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="1435a-287">Cqdpartition Edstreamview에서 MAX (StartTime) 선택</span><span class="sxs-lookup"><span data-stu-id="1435a-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="1435a-288">Cqdpartition Edstreamview에서 최소 (EndTime)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="1435a-289">Cqdpartition Edstreamview에서 MAX (EndTime)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="1435a-290">설치 후 작업</span><span class="sxs-lookup"><span data-stu-id="1435a-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="1435a-291">건물 및 네트워크 가져오기</span><span class="sxs-lookup"><span data-stu-id="1435a-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="1435a-292">CQD를 설치한 후에는 다음 구성 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="1435a-293">건물 유형 정의 (권장)</span><span class="sxs-lookup"><span data-stu-id="1435a-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="1435a-294">건물 소유권 유형 정의 (권장)</span><span class="sxs-lookup"><span data-stu-id="1435a-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="1435a-295">네트워크 유형 정의 (권장)</span><span class="sxs-lookup"><span data-stu-id="1435a-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="1435a-296">건물 가져오기 (권장)</span><span class="sxs-lookup"><span data-stu-id="1435a-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="1435a-297">가져오기 서브넷 (권장)</span><span class="sxs-lookup"><span data-stu-id="1435a-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="1435a-298">건물 유형 정의</span><span class="sxs-lookup"><span data-stu-id="1435a-298">Define Building Types</span></span>

<span data-ttu-id="1435a-299">건물 유형은 조직 내의 다양 한 건물 정의 또는 유형을 설명 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1435a-300">이 단계는 선택 사항 이지만 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="1435a-301">예제</span><span class="sxs-lookup"><span data-stu-id="1435a-301">Examples</span></span>
  
- <span data-ttu-id="1435a-302">본사</span><span class="sxs-lookup"><span data-stu-id="1435a-302">Headquarters</span></span>
    
- <span data-ttu-id="1435a-303">원격 Office</span><span class="sxs-lookup"><span data-stu-id="1435a-303">Remote Office</span></span>
    
- <span data-ttu-id="1435a-304">공동으로 사용 하는 위치</span><span class="sxs-lookup"><span data-stu-id="1435a-304">Joint-venture location</span></span>
    
  <span data-ttu-id="1435a-305">**예제 SQL 구문**</span><span class="sxs-lookup"><span data-stu-id="1435a-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="1435a-306">BuildingTypeId 및 BuildingTypeDesc 매개 변수는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="1435a-307">건물 소유권 유형 정의</span><span class="sxs-lookup"><span data-stu-id="1435a-307">Define Building Ownership Types</span></span>

<span data-ttu-id="1435a-308">소유권 유형은 소유한 vs 임대 자산을 구분 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1435a-309">이 단계는 선택 사항 이지만 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="1435a-310">예제</span><span class="sxs-lookup"><span data-stu-id="1435a-310">Examples</span></span>
  
- <span data-ttu-id="1435a-311">Contoso 온-서 비&amp;F 임대</span><span class="sxs-lookup"><span data-stu-id="1435a-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="1435a-312">Contoso 임대 다시&amp;F</span><span class="sxs-lookup"><span data-stu-id="1435a-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="1435a-313">Contoso 소유</span><span class="sxs-lookup"><span data-stu-id="1435a-313">Contoso Owned</span></span>
    
- <span data-ttu-id="1435a-314">자회사 임대</span><span class="sxs-lookup"><span data-stu-id="1435a-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="1435a-315">**예제 SQL 구문**</span><span class="sxs-lookup"><span data-stu-id="1435a-315">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

<span data-ttu-id="1435a-316">소유자 \ Typeid 및 소유자 배송 매개 변수는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="1435a-317">네트워크 이름 정의</span><span class="sxs-lookup"><span data-stu-id="1435a-317">Define Network Names</span></span>

<span data-ttu-id="1435a-318">네트워크 유형은 조직 내에서 다양 한 유형의 네트워크를 설명 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="1435a-319">이렇게 하면 특정 네트워크 형식을 필터링 하거나 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1435a-320">네트워크 이름은 정의 하는 것이 좋지만 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="1435a-321">네트워크 이름을 정의 하지 않기로 결정 한 경우 각 CqdNetwork 항목에 BuildingId 0이 지정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="1435a-322">예제</span><span class="sxs-lookup"><span data-stu-id="1435a-322">Examples</span></span>
  
- <span data-ttu-id="1435a-323">VPN</span><span class="sxs-lookup"><span data-stu-id="1435a-323">VPN</span></span>
    
- <span data-ttu-id="1435a-324">연구원</span><span class="sxs-lookup"><span data-stu-id="1435a-324">LAB</span></span>
    
  <span data-ttu-id="1435a-325">**예제 SQL 구문**</span><span class="sxs-lookup"><span data-stu-id="1435a-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="1435a-326">NetworkNameID 및 Networknameid 매개 변수는 필수 이며 NetworkType 매개 변수는 선택 사항 이지만 권장 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="1435a-327">건물 가져오기</span><span class="sxs-lookup"><span data-stu-id="1435a-327">Import Buildings</span></span>

<span data-ttu-id="1435a-328">건물을 가져오면 특정 정보를 작성할 수 있는 기능 (WiFi/유선을 사용 하는 경우에는 제작 별 통화 불량 등)이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1435a-329">이 단계는 선택 사항 이지만 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="1435a-330">새 건물을 가져오기 전에 미리 정의 된 BuildingKey를 이미 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="1435a-331">이 작업을 수행 하려면 현재 값을 식별 하는 "MAX (BuildingKey)를 선택 합니다." SQL 명령을 실행 하 고 결과에 1을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="1435a-332">**예제 SQL 구문**</span><span class="sxs-lookup"><span data-stu-id="1435a-332">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

<span data-ttu-id="1435a-333">BuildingKey, BuildingName, BuildingShortName, 소유자, BuildingTypeId 매개 변수가 필요한 경우 다른 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="1435a-334">가져오기 서브넷</span><span class="sxs-lookup"><span data-stu-id="1435a-334">Import Subnets</span></span>

<span data-ttu-id="1435a-335">건물을 가져오면 특정 정보를 작성할 수 있는 기능 (WiFi/유선을 사용 하는 경우에는 제작 별 통화 불량 등)이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1435a-336">이 단계는 선택 사항 이지만 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-336">This step is optional, but recommended.</span></span>
  
<span data-ttu-id="1435a-337">서브넷을 가져와서 마지막 단계에서 가져온 건물에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="1435a-338">NetworkName을 채우지 않기로 결정 한 경우이 테이블의 각 항목은 Networkname 0을 사용 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span> <span data-ttu-id="1435a-339">통화 품질 대시보드의 SQL 구문 및 매개 변수에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 통화 품질 대시보드 사용](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1435a-339">For more information on SQL syntax and parameters for the Call Quality Dashboard, see [Use Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use).</span></span>
  
 <span data-ttu-id="1435a-340">**예제 SQL 구문**</span><span class="sxs-lookup"><span data-stu-id="1435a-340">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkRange]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',32,0,1,'2015-11-11')
```

<span data-ttu-id="1435a-341">Network 및 UpdatedDate 매개 변수가 필요한 경우 다른 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-341">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="1435a-342">선택 사항: BSSID</span><span class="sxs-lookup"><span data-stu-id="1435a-342">Optional: BSSID</span></span>

<span data-ttu-id="1435a-343">BSSID 정보를 채우면 컨트롤러 또는 라디오에 의해 추가 WiFi stream 상관 관계가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-343">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="1435a-344">이는 건물이 나 subnet을 기준으로 필터링 하는 것 외에도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-344">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="1435a-345">**예제 SQL 구문**</span><span class="sxs-lookup"><span data-stu-id="1435a-345">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

<span data-ttu-id="1435a-346">**CqdBssidTable 세부 정보**</span><span class="sxs-lookup"><span data-stu-id="1435a-346">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="1435a-347">**CQD와 같이**</span><span class="sxs-lookup"><span data-stu-id="1435a-347">**As shown in CQD**</span></span>|<span data-ttu-id="1435a-348">**CQDBssid 테이블**</span><span class="sxs-lookup"><span data-stu-id="1435a-348">**CQDBssid Table**</span></span>|<span data-ttu-id="1435a-349">**예제 입력**</span><span class="sxs-lookup"><span data-stu-id="1435a-349">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1435a-350">Ap NName</span><span class="sxs-lookup"><span data-stu-id="1435a-350">Ap NName</span></span>  <br/> |<span data-ttu-id="1435a-351">MUX</span><span class="sxs-lookup"><span data-stu-id="1435a-351">AP</span></span>  <br/> |<span data-ttu-id="1435a-352">AP1</span><span class="sxs-lookup"><span data-stu-id="1435a-352">AP1</span></span>  <br/> |
|<span data-ttu-id="1435a-353">BBssid</span><span class="sxs-lookup"><span data-stu-id="1435a-353">BBssid</span></span>  <br/> |<span data-ttu-id="1435a-354">유형이</span><span class="sxs-lookup"><span data-stu-id="1435a-354">BSS</span></span>  <br/> |<span data-ttu-id="1435a-355">00-00-00-00-00-00 (구분 된 fformat을 사용 해야 함)</span><span class="sxs-lookup"><span data-stu-id="1435a-355">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="1435a-356">컨트롤러</span><span class="sxs-lookup"><span data-stu-id="1435a-356">Controller</span></span>  <br/> |<span data-ttu-id="1435a-357">건설</span><span class="sxs-lookup"><span data-stu-id="1435a-357">Building</span></span>  <br/> |<span data-ttu-id="1435a-358">아루바 AP 7</span><span class="sxs-lookup"><span data-stu-id="1435a-358">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="1435a-359">디바이스</span><span class="sxs-lookup"><span data-stu-id="1435a-359">Device</span></span>  <br/> |<span data-ttu-id="1435a-360">ess</span><span class="sxs-lookup"><span data-stu-id="1435a-360">ess</span></span>  <br/> |<span data-ttu-id="1435a-361">Controller1</span><span class="sxs-lookup"><span data-stu-id="1435a-361">Controller1</span></span>  <br/> |
|<span data-ttu-id="1435a-362">휴대폰</span><span class="sxs-lookup"><span data-stu-id="1435a-362">Radio</span></span>  <br/> |<span data-ttu-id="1435a-363">phy</span><span class="sxs-lookup"><span data-stu-id="1435a-363">phy</span></span>  <br/> |<span data-ttu-id="1435a-364">bgn</span><span class="sxs-lookup"><span data-stu-id="1435a-364">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="1435a-365">가져온 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="1435a-365">Processing the imported data</span></span>

<span data-ttu-id="1435a-366">기본적으로 건물/네트워크 데이터를 가져온 후에는 해당 시점 이후에 생성 된 레코드에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-366">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="1435a-367">위의 모든 레코드에이 새 데이터로 태그를 표시 하려면 아래와 같이 CqdUpdateBuilding 저장 프로시저를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-367">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="1435a-368">첫 번째 레코드의 날짜를 지정 합니다 (Select MIN (StartTime) FROM Cqdpartition Edstreamview SQL 명령을 사용 하는 경우), 내일 EndDate, 마지막 두 값에 대해 NULL을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-368">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="1435a-369">데이터가 stream 데이터와 연결 되 면 SSIS 큐브가 모든 레코드를 다시 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-369">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="1435a-370">이는 BSSID/ISP 데이터를 대량 추가할 때에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-370">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="1435a-371">"전체 처리"가 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1435a-371">Ensure that "Process Full" is selected.</span></span>
  

