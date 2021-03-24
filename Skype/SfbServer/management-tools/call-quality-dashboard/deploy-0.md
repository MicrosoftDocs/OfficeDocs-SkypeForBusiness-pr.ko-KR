---
title: 비즈니스용 Skype 서버용 통화 품질 대시보드 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: '요약: 통화 품질 대시보드의 배포 프로세스에 대해 설명합니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 1f59209575284035fcdca52e4f18220aa05337af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114114"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="93a8c-104">비즈니스용 Skype 서버용 통화 품질 대시보드 배포</span><span class="sxs-lookup"><span data-stu-id="93a8c-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="93a8c-105">**요약:** 통화 품질 대시보드의 배포 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="93a8c-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="93a8c-107">배포 개요</span><span class="sxs-lookup"><span data-stu-id="93a8c-107">Deployment Overview</span></span>

<span data-ttu-id="93a8c-108">CQD(통화 품질 대시보드)는 다음과 같은 세 가지 주요 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="93a8c-109">**보관 데이터베이스**. QoE(QoE) 데이터가 복제되고 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="93a8c-110">**큐브**- QoE 보관 데이터베이스의 데이터가 최적화 및 빠른 액세스를 위해 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="93a8c-111">**포털**- 사용자가 QoE 데이터를 쉽게 쿼리하고 시각화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![CQD 구성 요소](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="93a8c-113">QoE Archive 설치 프로세스에는 QoE 보관 데이터베이스를 만들고, 원본 QoE 메트릭 데이터베이스의 데이터를 QoE 보관 데이터베이스로 이동하는 SQL Server 저장 프로시저를 배포하고, 저장 프로시저를 정기적으로 실행하도록 SQL Server 에이전트 작업을 설정하는 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="93a8c-114">큐브 배포는 QoE 보관함이 있는 위치의 사용자 정보를 수집하고, 큐브를 배포하고, 정기적으로 큐브를 새로 고칠 정기적인 SQL Server 에이전트 작업을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="93a8c-115">포털 설치는 각 사용자의 보고서/쿼리에 대한 CQD 사용자 매핑을 저장하는 리포지토리 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="93a8c-116">그런 다음 사용자가 미리 정의된 보고서 집합을 볼 수 있으며 큐브에서 데이터를 시각화하는 자체 쿼리를 사용자 지정하고 만들 수 있는 대시보드인 IIS 웹 응용 프로그램을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="93a8c-117">포털 설치는 사용자가 리포지토리 및 큐브에 프로그래밍식으로 액세스할 수 있도록 API를 노출하는 두 개의 추가 웹 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="93a8c-118">이러한 API는 대시보드에서 내부적으로도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="93a8c-119">**작업 단계**</span><span class="sxs-lookup"><span data-stu-id="93a8c-119">**Phase**</span></span>|<span data-ttu-id="93a8c-120">**단계**</span><span class="sxs-lookup"><span data-stu-id="93a8c-120">**Steps**</span></span>|<span data-ttu-id="93a8c-121">**역할 및 그룹 구성원**</span><span class="sxs-lookup"><span data-stu-id="93a8c-121">**Roles and group membership**</span></span>|<span data-ttu-id="93a8c-122">**설명서**</span><span class="sxs-lookup"><span data-stu-id="93a8c-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="93a8c-123">필요한 하드웨어 및 소프트웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="93a8c-124">CQD 구성을 결정하고 설치를 SQL Server 구성을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="93a8c-125">로컬 Administrators 그룹의 구성원인 도메인 사용자</span><span class="sxs-lookup"><span data-stu-id="93a8c-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="93a8c-126">배포 설명서의 "사전 설치 요구 사항" 섹션</span><span class="sxs-lookup"><span data-stu-id="93a8c-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="93a8c-127">CQD를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="93a8c-128">배포 문서 다음에 MSI를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="93a8c-129">설치 계정을 설치하려면 설치 계정이 로컬 관리자 그룹의 구성원인 도메인 사용자로서 모니터링 서버의 QoE 메트릭 데이터베이스에 대한 읽기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="93a8c-130">배포 설명서의 "계정 및 배포 단계" 섹션</span><span class="sxs-lookup"><span data-stu-id="93a8c-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="93a8c-131">사용자에게 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="93a8c-132">포털에 대한 사용자 권한 부여를 관리하기 위해 IIS 7.0에 도입된 URL 권한 부여를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="93a8c-133">자세한 내용은 [UNDERSTANDING IIS 7.0 URL Authorization를 참조하십시오.](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)</span><span class="sxs-lookup"><span data-stu-id="93a8c-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="93a8c-134">로컬 Administrators 그룹의 구성원인 도메인 사용자</span><span class="sxs-lookup"><span data-stu-id="93a8c-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="93a8c-135">배포 설명서의 포털에 대한 사용자 액세스 관리 섹션</span><span class="sxs-lookup"><span data-stu-id="93a8c-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="93a8c-136">선택 사항: 서브넷 매핑 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="93a8c-137">QoE 보관 데이터베이스에서 네트워크 및 매핑 테이블을 채우고 매핑 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="93a8c-138">QoE 보관 데이터베이스에 대한 쓰기 권한이 있는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="93a8c-139">사용자 설명서의 "서브넷 정보 제공" 섹션</span><span class="sxs-lookup"><span data-stu-id="93a8c-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="93a8c-140">통화 품질 대시보드 배포에는 인프라 설정 및 소프트웨어 설치가 수반됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="93a8c-141">다음 절차에서는 프로세스를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="93a8c-142">배포 단계</span><span class="sxs-lookup"><span data-stu-id="93a8c-142">Deployment Steps</span></span>

1. <span data-ttu-id="93a8c-143">CQD의 CallQualityDashboard.msi 구성 요소를 설치할 컴퓨터(이 컴퓨터는 설치되지 않은 컴퓨터)에 SQL Server 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="93a8c-144">MSI를 실행합니다(Windows에서 관리자 권한으로 실행하라는 메시지가 표시될 경우 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="93a8c-145">EULA에 동의합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="93a8c-146">통화 품질 대시보드 구성 요소와 관련된 파일이 위치할 대상 폴더를 선택하거나 기본 위치를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="93a8c-147">모든 기능을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-147">Select all features.</span></span>
    
6. <span data-ttu-id="93a8c-148">QoE 보관 구성 페이지에서 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="93a8c-149">**QoE 메트릭은 SQL Server.** SQL Server 메트릭 DB가 있는 위치의 인스턴스 이름입니다(데이터 원본).</span><span class="sxs-lookup"><span data-stu-id="93a8c-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="93a8c-150">**QoE 보관 SQL Server 이름:** 이 필드는 읽기 전용 필드로, 로컬 컴퓨터의 정식 도메인 이름에 고정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="93a8c-151">보관 DB는 로컬 컴퓨터에만 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="93a8c-152">**QoE 보관 SQL Server 인스턴스:** 보관 SQL Server 만들 로컬 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="93a8c-153">기본 인스턴스를 SQL Server 이 필드를 비워 두십시오.</span><span class="sxs-lookup"><span data-stu-id="93a8c-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="93a8c-154">명명된 인스턴스를 SQL Server 인스턴스 이름(예: " 다음의 이름)을 \" 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="93a8c-155">**QoE 보관 데이터베이스:** 기본적으로 이 옵션은 "새 데이터베이스 만들기"로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="93a8c-156">보관 DB 업그레이드는 지원되지 않습니다. "기존 데이터베이스 사용" 옵션을 사용할 수 있는 유일한 상황은 기존 보관 데이터베이스에 설치할 빌드와 동일한 스마마가 있는 경우뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="93a8c-157">**데이터베이스 파일 디렉터리:** 보관 DB의 데이터베이스 파일(.mdf 및 .ldf)을 배치할 위치의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="93a8c-158">이는 OS와 별개인 드라이브(권장 하드웨어 구성의 HDD2)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="93a8c-159">파일 이름은 설치 시 수정되어 있을 수 있는 충돌을 방지하기 위해 파일이 없는 빈 디렉터리를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="93a8c-160">**여러 파티션 사용:** 기본값은 "다중 파티션"으로 설정되어 비즈니스 인텔리전스 에디션 또는 Enterprise 버전이 SQL Server.</span><span class="sxs-lookup"><span data-stu-id="93a8c-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="93a8c-161">Standard Edition의 경우 "단일 파티션" 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="93a8c-162">단일 파티션을 사용하는 경우 큐브 처리 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="93a8c-163">설치가 완료되면 여러 파티션 사용 옵션을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="93a8c-164">큐브 기능을 변경하기 위해서는 먼저 큐브 기능을 제거한 다음 제어판에서 "변경" 옵션을 사용하여 다시 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="93a8c-165">**파일 디렉터리 분할:** QoE 보관 데이터베이스의 파티션을 배치할 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="93a8c-166">이 드라이브는 OS 드라이브와 데이터베이스 로그 파일 드라이브와 별개인 드라이브(권장 하드웨어 구성의 HDD3)에 SQL 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="93a8c-167">파일 이름은 설치 시 수정되어 있을 수 있는 충돌을 방지하기 위해 파일이 없는 빈 디렉터리를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="93a8c-168">**SQL 에이전트 작업 사용자 - 사용자 이름 &amp; 암호:** SQL Server 에이전트 작업의 "QoE 보관 데이터" 단계를 실행하는 데 사용되는 도메인 서비스 계정 이름 및 암호(마스킹)입니다. 이 저장 프로시저를 실행하여 QoE 메트릭 DB에서 보관 DB로 데이터를 페치할 예정이기 때문에 이 계정에는 계정 섹션에 표시된 QoE 메트릭 DB에 대한 읽기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="93a8c-169">또한 이 계정은 QoE Archive SQL Server 인스턴스에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="93a8c-170">NT SERVICE\MSSQLSERVER와 같이 SQL Server 인스턴스가 실행되는 계정에는 설치가 성공하려면 위에 제공된 Director에 대한 액세스/권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="93a8c-171">자세한 내용은 [Configure File System Permissions for Database Engine Access을 참조합니다.](/previous-versions/sql/sql-server-2012/jj219062(v=sql.110))</span><span class="sxs-lookup"><span data-stu-id="93a8c-171">For details, see [Configure File System Permissions for Database Engine Access](/previous-versions/sql/sql-server-2012/jj219062(v=sql.110))</span></span>
  
7. <span data-ttu-id="93a8c-172">다음을 클릭하면 설치 관리자에서 선행 작업 확인을 수행하고 문제가 발생하는 경우 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="93a8c-173">모든 선행 구성 검사가 통과하면 설치 관리자에서 큐브 구성 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="93a8c-174">설치 관리자에 QoE Archive SQL Server 인스턴스에 대한 SQL Server 에이전트 서비스가 현재 실행되고 있지 않다는 경고 메시지가 표시될 경우 설치를 계속할 수 있지만 설치 후를 수행하려면 SQL Agent Service가 실행되고 있는지 확인하여 시작 유형을 자동으로 설정하여 예약된 작업이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="93a8c-175">큐브 구성 페이지에서 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="93a8c-176">**QoE 보관 SQL Server 이름:** 이 필드는 읽기 전용 필드로, 로컬 컴퓨터의 정식 도메인 이름에 고정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="93a8c-177">큐브는 QoE 보관 데이터베이스가 있는 컴퓨터(참고)에서만 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="93a8c-178">큐브 자체가 원격 컴퓨터에 설치될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="93a8c-179">아래 참조)</span><span class="sxs-lookup"><span data-stu-id="93a8c-179">See below)</span></span>
    
   - <span data-ttu-id="93a8c-180">**QoE 보관 SQL Server 인스턴스:** SQL Server 보관 DB가 있는 위치의 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="93a8c-181">기본 SQL Server 지정하기 위해 이 필드를 비워 두십시오.</span><span class="sxs-lookup"><span data-stu-id="93a8c-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="93a8c-182">명명된 SQL Server 인스턴스를 지정하기 위해 인스턴스 이름(예: " 다음의 이름)을 \" 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="93a8c-183">설치를 위해 QoE 보관 구성 요소를 선택한 경우 이 필드는 QoE 보관 구성 페이지에 제공된 값으로 미리 채워지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="93a8c-184">**큐브 분석 서버:** SQL Server 만들 Analysis Service 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="93a8c-185">이 컴퓨터는 다른 컴퓨터일 수 있지만 설치하는 사용자는 Analysis Service 인스턴스의 대상 서버 관리자 SQL Server 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="93a8c-186">Analysis Services 서버 관리자 권한을 구성하는 데 대한 자세한 내용은 [Grant Server Administrator Permissions (Analysis Services)을 참조하십시오.](/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance?viewFallbackFrom=sql-server-ver15)</span><span class="sxs-lookup"><span data-stu-id="93a8c-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance?viewFallbackFrom=sql-server-ver15)</span></span>
  
   - <span data-ttu-id="93a8c-187">**여러 파티션 사용:** 기본값은 "다중 파티션"으로 설정되어 비즈니스 인텔리전스 에디션 또는 Enterprise 버전이 SQL Server.</span><span class="sxs-lookup"><span data-stu-id="93a8c-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="93a8c-188">Standard Edition의 경우 "단일 파티션" 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="93a8c-189">단일 파티션을 사용하는 경우 큐브 처리 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="93a8c-190">설치가 완료되면 여러 파티션 사용 옵션을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="93a8c-191">큐브 기능을 변경하기 위해서는 먼저 큐브 기능을 제거한 다음 제어판에서 "변경" 옵션을 사용하여 다시 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="93a8c-192">**큐브 사용자 - 사용자 이름 &amp; 암호:** 큐브 처리를 트리거하는 도메인 서비스 계정 이름 및 암호(마스킹)입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="93a8c-193">설치를 위해 QoE 보관 구성 요소를 선택한 경우 이 필드는 SQL 에이전트 작업 사용자에 대한 보관 구성 페이지에 제공된 값으로 미리 채워지지만 설치 프로그램이 최소 필수 권한을 부여할 수 있도록 다른 도메인 서비스 계정을 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="93a8c-194">다음을 클릭하면 다른 유효성 검사 라운드가 수행되는 것이고 모든 문제가 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="93a8c-195">유효성 검사가 성공적으로 완료된 후 설치 관리자에서 포털 구성 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="93a8c-196">포털 구성 페이지에서 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="93a8c-197">**QoE 보관 SQL Server:** SQL Server 데이터베이스가 있는 위치의 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="93a8c-198">QoE 보관 구성 페이지 및 큐브 구성 페이지와 달리 컴퓨터 이름은 고정되지 않고 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="93a8c-199">설치를 위해 QoE 보관 구성 요소를 선택한 경우 이 필드는 QoE 보관 구성 페이지에 제공된 값으로 미리 채워지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="93a8c-200">**큐브 분석 서버:** SQL Server 위치의 Analysis Service 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="93a8c-201">설치를 위해 큐브 구성 요소를 선택한 경우 큐브 구성 페이지에 제공된 값으로 이 필드가 미리 채워지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="93a8c-202">**리포지토리 SQL Server:** SQL Server 데이터베이스를 만들 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="93a8c-203">설치 SQL Server QoE 보관 데이터베이스가 있는 위치의 SQL Server 인스턴스 이름이 다른 구성 요소에서 제공된 경우 이 필드는 QoE Archive DB 및 SQL Server 인스턴스 이름으로 미리 채워지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="93a8c-204">이 인스턴스는 모든 SQL Server 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="93a8c-205">**리포지토리 데이터베이스:** 기본적으로 옵션은 "새 데이터베이스 만들기"로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="93a8c-206">리포지토리 DB 업그레이드는 지원되지 않습니다. "기존 데이터베이스 사용" 옵션을 사용할 수 있는 유일한 상황은 기존 Repository DB에 설치할 빌드와 동일한 스마마가 있는 경우뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="93a8c-207">**IIS 앱 풀 사용자 - 사용자 이름 &amp; 암호:** IIS 응용 프로그램 풀이 실행해야 하는 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="93a8c-208">기본 제공 시스템 계정을 선택하면 사용자 이름 및 암호 필드가 회색으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="93a8c-209">이러한 필드는 사용자가 도메인 서비스 계정 정보를 입력할 수 있도록 드롭다운 상자에서 "기타"를 선택한 경우만 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="93a8c-210">다음을 클릭하면 최종 유효성 검사 라운드가 수행되어 제공된 자격 증명을 사용하여 SQL Server 인스턴스에 액세스할 수 있으며 컴퓨터의 IIS를 사용할 수 있는지를 확인하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="93a8c-211">유효성 검사가 성공적으로 완료된 후 설치 프로그램이 설치를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="93a8c-212">설치 관리자를 완료하면 QoE SQL Server 큐브 처리의 초기 로드를 수행하여 SQL Server 에이전트 작업이 진행될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="93a8c-213">QoE의 데이터 양에 따라 포털에 아직 데이터를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="93a8c-214">데이터 로드 및 큐브 처리 상태를 확인한 후 로  `http://<machinename>/CQD/#/Health` 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="93a8c-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="93a8c-215">다운로드 큐브 처리의 상태를 확인할 URL은 대/중입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="93a8c-216">'health'를 입력하면 URL이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="93a8c-217">URL 끝에 대문자 H를 사용하여 'Health'를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="93a8c-218">디버그 모드를 사용하는 경우 자세한 로그 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="93a8c-219">디버그 모드를 사용하도록 설정하려면 **%SYSTEMDRIVE%\Program Files\Skype for Business 2015** CQD\QoEDataService\web.config로 이동하여 값을 **True로** 설정하도록 다음 줄을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="93a8c-220">기본 포털 페이지는 를 통해 액세스할 수  `http://<machinename>/CQD` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="93a8c-221">포털에 대한 사용자 액세스 관리</span><span class="sxs-lookup"><span data-stu-id="93a8c-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="93a8c-222">포털에 대한 사용자 권한 부여를 관리하기 위해 IIS 7.0에 도입된 URL 권한 부여를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="93a8c-223">IIS 보안에 대한 자세한 내용은 [UNDERSTANDING IIS 7.0 URL Authorization를 참조하십시오.](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)</span><span class="sxs-lookup"><span data-stu-id="93a8c-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="93a8c-224">모든 웹 사이트 또는 웹 응용 프로그램은 일반적으로 "모든 사용자 허용"인 전체 IIS에 대해 구성된 기본 URL 권한 부여를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="93a8c-225">포털에 대한 액세스가 보다 제한적인 경우 관리자는 "권한 부여 규칙"을 편집하여 특정 사용자 그룹에만 액세스 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![통화 품질 배포 - IIS에서 권한 부여 규칙](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="93a8c-227">권한 부여 규칙 아이콘은 다른 권한 부여 메커니즘인 ASP.NET 섹션에서 ".NET 권한 부여"와 혼동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="93a8c-228">관리자는 먼저 상속된 "모든 사용자 허용" 규칙을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="93a8c-229">이렇게 하면 권한이 없는 사용자가 포털에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![CQD 배포](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="93a8c-231">다음으로 관리자는 새 허용 규칙을 추가하고 특정 사용자에게 포털 액세스 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="93a8c-232">사용자를 관리하기 위해 "CQDPortalUsers"라는 로컬 그룹을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![통화 품질 대시보드 배포](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="93a8c-234">구성 세부 정보는 포털의 web.config 디렉터리에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="93a8c-235">다음 단계는 CQD의 대시보드를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="93a8c-236">IIS에서 사용자를 인증한 후 웹 포털 콘텐츠에 액세스하려면 CQD 디렉터리에 대한 파일 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="93a8c-237">CQD 디렉터리 속성의 보안 탭을 통해 ACL을 변경하여 개별 사용자 또는 그룹을 추가할 수 있습니다. 그러나 권장되는 방법은 파일 사용 권한을 그대로 두는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="93a8c-238">대신 인증된 사용자에 상관없이 IIS Worker 프로세스를 사용하여 CQD 디렉터리에 액세스하도록 IIS 설정을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="93a8c-239">CQD 응용 프로그램에 대해 이 설정만 변경해야 합니다. 단, 두 API 응용 프로그램인 QoEDataService 및 QoERepositoryService는 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="93a8c-240">CQD에 대한 파일 액세스 구성(대시보드)</span><span class="sxs-lookup"><span data-stu-id="93a8c-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="93a8c-241">CQD에 대한 구성 편집기를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-241">Open the Configuration Editor for CQD.</span></span>
    
     ![통화 품질 대시보드 배포](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="93a8c-243">섹션에서 **system.webServer/serverRuntime 을 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="93a8c-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![통화 품질 대시보드 배포](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="93a8c-245">authenticatedUserOverride를 **UseWorkerProcessUser로 변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="93a8c-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![통화 품질 대시보드 배포 - 구성 편집기](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="93a8c-247">페이지 **오른쪽에서** 적용을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="93a8c-248">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="93a8c-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="93a8c-249">배포 후 CQD에 데이터가 없음</span><span class="sxs-lookup"><span data-stu-id="93a8c-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="93a8c-250">다음과 같은 오류가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-250">You may receive the following error:</span></span>

<span data-ttu-id="93a8c-251">*큐브에서 쿼리를 실행하는 동안 쿼리를 수행할 수 없습니다. 쿼리 편집기를 사용하여 쿼리를 수정하고 문제를 해결합니다. 큐브에 액세스할 수 있는지도 확인 합니다.*</span><span class="sxs-lookup"><span data-stu-id="93a8c-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="93a8c-252">즉, CQD에서 사용하려면 SQL Server Analysis Services에서 큐브를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="93a8c-253">다음 단계에 따라 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="93a8c-254">새 SQL Management Studio **를 열고 Analysis Services 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="93a8c-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="93a8c-255">**QoECube** 개체를 확장하고 **QoE 메트릭을 선택하고** 마우스 오른쪽 단추를 클릭한 다음 **찾아보기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="93a8c-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="93a8c-256">이 경우 빈 브라우저가 반환될 경우 큐브가 아직 진행되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="93a8c-257">**QoE 메트릭을 마우스 오른쪽 단추로** 클릭하고 프로세스를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="93a8c-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="93a8c-258">처리가 완료되면 개체를 마우스 오른쪽 단추로  다시 클릭하고 찾아보기를 클릭하여 브라우저 페이지에 데이터가 표시되어 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="93a8c-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="93a8c-259">설치 관리자에서 IIS에서 올바른 설정을 만들지 못하기 때문에 로그인하는 데 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="93a8c-260">드문 경우지만 설치 관리자에서 IIS에서 올바른 설정을 만들지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="93a8c-261">사용자가 CQD에 로그인할 수 있도록 수동으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="93a8c-262">사용자가 로그인하는 데 문제가 있는 경우 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="93a8c-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="93a8c-263">IIS 관리자를 열고 기본 웹 사이트로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![통화 품질 대시보드 배포](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="93a8c-265">"인증"을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-265">Click on "Authentication".</span></span> <span data-ttu-id="93a8c-266">"익명 인증", "ASP.NET 가장", "양식 인증" 및 "Windows 인증"이 아래 표시된 설정과 일치하지 않는 경우 아래 설정과 일치하도록 수동으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="93a8c-267">다른 모든 인증 메커니즘은 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![통화 품질 대시보드 배포](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="93a8c-269">"Windows 인증"의 경우 오른쪽의 고급 설정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![통화 품질 대시보드 배포](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="93a8c-271">"확장된 보호"를 수락으로 설정하고 "커널 모드 인증 사용" 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![통화 품질 대시보드 배포](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="93a8c-273">"기본 웹 사이트" 아래의 각 "CQD", "QoEDataService" 및 "QoERepositoryService" 항목에 대해 위의 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="93a8c-274">HTTP 및 HTTPS 포트 바인딩의 경우 설치 관리자에서 기본 포트 번호(HTTP의 경우 포트 80, HTTPS의 경우 포트 443)에 포트 바인딩을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="93a8c-275">이러한 바인딩을 사용하는 다른 웹 사이트가 있는 경우 충돌이 있으며 IIS 동작을 예측할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="93a8c-276">이 문제를 방지하는 가장 좋은 방법은 CQD를 설치하기 전에 다른 웹 사이트가 포트 80 및 443에 매핑되어 있는지 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="93a8c-277">IIS에서 SSL/TLS를 사용하도록 설정하고 사용자가 HTTP 대신 보안 HTTPS를 통해 연결하도록 강제하려면</span><span class="sxs-lookup"><span data-stu-id="93a8c-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="93a8c-278">IIS에서 Secure Sockets Layer 구성은 [IIS 7에서 Secure Sockets Layer 구성을 참조합니다.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="93a8c-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771438(v=ws.10)).</span></span> <span data-ttu-id="93a8c-279">완료되면 으로  `http` `https` 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="93a8c-280">SQL Server 연결에서 TLS를 사용하도록 설정하는 방법에 대한 자세한 내용은 Microsoft Management Console을 사용하여 SQL Server 인스턴스에 [대해 SSL 암호화를 사용하도록 설정하는 방법을 참조하세요.](https://support.microsoft.com/kb/316898/)</span><span class="sxs-lookup"><span data-stu-id="93a8c-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="93a8c-281">큐브 동기화 실패</span><span class="sxs-lookup"><span data-stu-id="93a8c-281">Cube Sync Fails</span></span>

<span data-ttu-id="93a8c-282">QoEMetrics에는 최종 사용자 시계에 따라 일부 잘못된 레코드가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="93a8c-283">시간이 60yrs보다 크면 큐브 가져오기에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="93a8c-284">아래 선택을 사용하여 Min 및 Max StartTime/EndTime을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="93a8c-285">먼 미래에 레코드를 찾아 삭제하면 무시될 수 있으며 동기화 프로세스가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="93a8c-286">MIN(StartTime) FROM CqdPartitionedStreamView를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="93a8c-287">MAX(StartTime) FROM CqdPartitionedStreamView를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="93a8c-288">MIN(EndTime) FROM CqdPartitionedStreamView를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="93a8c-289">MAX(EndTime) FROM CqdPartitionedStreamView를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="93a8c-290">설치 후 작업</span><span class="sxs-lookup"><span data-stu-id="93a8c-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="93a8c-291">건물 및 네트워크 가져오기</span><span class="sxs-lookup"><span data-stu-id="93a8c-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="93a8c-292">CQD를 설치한 후 다음 구성 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="93a8c-293">구축 유형 정의(권장)</span><span class="sxs-lookup"><span data-stu-id="93a8c-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="93a8c-294">소유권 유형 정의(권장)</span><span class="sxs-lookup"><span data-stu-id="93a8c-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="93a8c-295">네트워크 유형 정의(권장)</span><span class="sxs-lookup"><span data-stu-id="93a8c-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="93a8c-296">건물 가져오기(권장)</span><span class="sxs-lookup"><span data-stu-id="93a8c-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="93a8c-297">서브넷 가져오기(권장)</span><span class="sxs-lookup"><span data-stu-id="93a8c-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="93a8c-298">건물 유형 정의</span><span class="sxs-lookup"><span data-stu-id="93a8c-298">Define Building Types</span></span>

<span data-ttu-id="93a8c-299">건물 유형은 조직 내의 다양한 건물 정의 또는 유형을 설명하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="93a8c-300">이 단계는 선택 사항이지만 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="93a8c-301">예</span><span class="sxs-lookup"><span data-stu-id="93a8c-301">Examples</span></span>
  
- <span data-ttu-id="93a8c-302">본사</span><span class="sxs-lookup"><span data-stu-id="93a8c-302">Headquarters</span></span>
    
- <span data-ttu-id="93a8c-303">원격 Office</span><span class="sxs-lookup"><span data-stu-id="93a8c-303">Remote Office</span></span>
    
- <span data-ttu-id="93a8c-304">공동 위치</span><span class="sxs-lookup"><span data-stu-id="93a8c-304">Joint-venture location</span></span>
    
  <span data-ttu-id="93a8c-305">**샘플 SQL 구문**</span><span class="sxs-lookup"><span data-stu-id="93a8c-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="93a8c-306">BuildingTypeId 및 BuildingTypeDesc 매개 변수는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="93a8c-307">소유권 유형 정의</span><span class="sxs-lookup"><span data-stu-id="93a8c-307">Define Building Ownership Types</span></span>

<span data-ttu-id="93a8c-308">소유권 유형은 소유 자산과 임대 자산을 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="93a8c-309">이 단계는 선택 사항이지만 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="93a8c-310">예</span><span class="sxs-lookup"><span data-stu-id="93a8c-310">Examples</span></span>
  
- <span data-ttu-id="93a8c-311">Contoso Leased non-RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="93a8c-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="93a8c-312">Contoso Leased RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="93a8c-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="93a8c-313">Contoso Owned</span><span class="sxs-lookup"><span data-stu-id="93a8c-313">Contoso Owned</span></span>
    
- <span data-ttu-id="93a8c-314">자회사 임대</span><span class="sxs-lookup"><span data-stu-id="93a8c-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="93a8c-315">**샘플 SQL 구문**</span><span class="sxs-lookup"><span data-stu-id="93a8c-315">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="93a8c-316">OwnershipTypeId 및 OwnershipTypeDesc 매개 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="93a8c-317">네트워크 이름 정의</span><span class="sxs-lookup"><span data-stu-id="93a8c-317">Define Network Names</span></span>

<span data-ttu-id="93a8c-318">네트워크 유형은 조직 내에서 다양한 유형의 네트워크를 설명하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="93a8c-319">이렇게 하면 특정 네트워크 유형을 필터링(또는 필터링)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="93a8c-320">네트워크 이름을 정의하는 것이 되지만 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="93a8c-321">네트워크 이름을 정의하지 않도록 결정한 경우 각 CqdNetwork 항목에 BuildingId가 0인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="93a8c-322">예</span><span class="sxs-lookup"><span data-stu-id="93a8c-322">Examples</span></span>
  
- <span data-ttu-id="93a8c-323">VPN</span><span class="sxs-lookup"><span data-stu-id="93a8c-323">VPN</span></span>
    
- <span data-ttu-id="93a8c-324">랩</span><span class="sxs-lookup"><span data-stu-id="93a8c-324">LAB</span></span>
    
  <span data-ttu-id="93a8c-325">**샘플 SQL 구문**</span><span class="sxs-lookup"><span data-stu-id="93a8c-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="93a8c-326">NetworkNameID 및 NetworkName 매개 변수는 필수이며 NetworkType 매개 변수는 선택 사항이지만 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="93a8c-327">건물 가져오기</span><span class="sxs-lookup"><span data-stu-id="93a8c-327">Import Buildings</span></span>

<span data-ttu-id="93a8c-328">건물을 가져오면 특정 정보(WiFi/유선 등에서 건물당 불량 통화 수)를 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="93a8c-329">이 단계는 선택 사항이지만 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="93a8c-330">새 건물을 가져오기 전에 미리 정의한 BuildingKey가 이미 식별되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="93a8c-331">이를 위해 "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL 명령을 실행하여 현재 값을 식별하고 결과에 1을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="93a8c-332">**샘플 SQL 구문**</span><span class="sxs-lookup"><span data-stu-id="93a8c-332">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="93a8c-333">BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId 매개 변수는 필수이며 다른 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="93a8c-334">서브넷 가져오기</span><span class="sxs-lookup"><span data-stu-id="93a8c-334">Import Subnets</span></span>

<span data-ttu-id="93a8c-335">건물을 가져오면 특정 정보(WiFi/유선 등에서 건물당 불량 통화 수)를 구축할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="93a8c-336">이 단계는 선택 사항이지만 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-336">This step is optional, but recommended.</span></span>
  
<span data-ttu-id="93a8c-337">서브넷을 가져와서 마지막 단계에서 가져온 건물에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="93a8c-338">NetworkName을 채우지 않도록 결정한 경우 이 표의 각 항목이 NetworkNameID 0을 사용하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span> <span data-ttu-id="93a8c-339">통화 품질 SQL 구문과 매개 변수에 대한 자세한 내용은 [Use Call Quality Dashboard for Skype for Business Server을 참조하십시오.](./use.md)</span><span class="sxs-lookup"><span data-stu-id="93a8c-339">For more information on SQL syntax and parameters for the Call Quality Dashboard, see [Use Call Quality Dashboard for Skype for Business Server](./use.md).</span></span>
  
 <span data-ttu-id="93a8c-340">**샘플 SQL 구문**</span><span class="sxs-lookup"><span data-stu-id="93a8c-340">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="93a8c-341">Network 및 UpdatedDate 매개 변수는 필수이며 다른 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-341">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="93a8c-342">선택 사항: BSSID</span><span class="sxs-lookup"><span data-stu-id="93a8c-342">Optional: BSSID</span></span>

<span data-ttu-id="93a8c-343">BSSID 정보를 채우면 컨트롤러 또는 라디오에 대한 추가 WiFi 스트림 상관 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-343">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="93a8c-344">이는 구성 또는 서브넷을 사용하여 필터링하는 것 외에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-344">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="93a8c-345">**샘플 SQL 구문**</span><span class="sxs-lookup"><span data-stu-id="93a8c-345">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="93a8c-346">**CqdBssidTable 세부 정보**</span><span class="sxs-lookup"><span data-stu-id="93a8c-346">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="93a8c-347">**CQD에 표시된 것**</span><span class="sxs-lookup"><span data-stu-id="93a8c-347">**As shown in CQD**</span></span>|<span data-ttu-id="93a8c-348">**CQDBssid 테이블**</span><span class="sxs-lookup"><span data-stu-id="93a8c-348">**CQDBssid Table**</span></span>|<span data-ttu-id="93a8c-349">**예제 입력**</span><span class="sxs-lookup"><span data-stu-id="93a8c-349">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="93a8c-350">Ap NName</span><span class="sxs-lookup"><span data-stu-id="93a8c-350">Ap NName</span></span>  <br/> |<span data-ttu-id="93a8c-351">AP</span><span class="sxs-lookup"><span data-stu-id="93a8c-351">AP</span></span>  <br/> |<span data-ttu-id="93a8c-352">AP1</span><span class="sxs-lookup"><span data-stu-id="93a8c-352">AP1</span></span>  <br/> |
|<span data-ttu-id="93a8c-353">BBssid</span><span class="sxs-lookup"><span data-stu-id="93a8c-353">BBssid</span></span>  <br/> |<span data-ttu-id="93a8c-354">BSS</span><span class="sxs-lookup"><span data-stu-id="93a8c-354">BSS</span></span>  <br/> |<span data-ttu-id="93a8c-355">00-00-00-00-00-00(나만의 fformat 사용)</span><span class="sxs-lookup"><span data-stu-id="93a8c-355">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="93a8c-356">컨트롤러</span><span class="sxs-lookup"><span data-stu-id="93a8c-356">Controller</span></span>  <br/> |<span data-ttu-id="93a8c-357">건물</span><span class="sxs-lookup"><span data-stu-id="93a8c-357">Building</span></span>  <br/> |<span data-ttu-id="93a8c-358">아루바 AP 7</span><span class="sxs-lookup"><span data-stu-id="93a8c-358">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="93a8c-359">장치</span><span class="sxs-lookup"><span data-stu-id="93a8c-359">Device</span></span>  <br/> |<span data-ttu-id="93a8c-360">ess</span><span class="sxs-lookup"><span data-stu-id="93a8c-360">ess</span></span>  <br/> |<span data-ttu-id="93a8c-361">Controller1</span><span class="sxs-lookup"><span data-stu-id="93a8c-361">Controller1</span></span>  <br/> |
|<span data-ttu-id="93a8c-362">라디오</span><span class="sxs-lookup"><span data-stu-id="93a8c-362">Radio</span></span>  <br/> |<span data-ttu-id="93a8c-363">phy</span><span class="sxs-lookup"><span data-stu-id="93a8c-363">phy</span></span>  <br/> |<span data-ttu-id="93a8c-364">bgn</span><span class="sxs-lookup"><span data-stu-id="93a8c-364">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="93a8c-365">가져온 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="93a8c-365">Processing the imported data</span></span>

<span data-ttu-id="93a8c-366">기본적으로 건물/네트워크 데이터를 가져온 후 해당 시점 이후에 생성된 레코드에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-366">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="93a8c-367">이 새 데이터를 사용하여 이전 레코드에 태그를 지정하려면 아래와 같이 CqdUpdateBuilding 저장 프로시저를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-367">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="93a8c-368">첫 번째 레코드의 날짜를 제공합니다(SELECT MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of my last two values, then NULL.</span><span class="sxs-lookup"><span data-stu-id="93a8c-368">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="93a8c-369">데이터가 스트림 데이터와 연결된 후 SSIS 큐브는 모든 레코드를 다시 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-369">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="93a8c-370">이는 BSSID/ISP 데이터를 대량으로 추가할 때도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-370">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="93a8c-371">"전체 프로세스"가 선택되어 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="93a8c-371">Ensure that "Process Full" is selected.</span></span>
