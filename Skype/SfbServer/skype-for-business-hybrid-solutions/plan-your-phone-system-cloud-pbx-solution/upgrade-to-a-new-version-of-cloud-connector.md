---
title: 새 버전의 클라우드 커넥터로 업그레이드
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: 클라우드 커넥터 에디션 배포를 업그레이드 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: c2613069f1626f8fc7e28b4fb5a246fc7647cf98
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190572"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="2caae-103">새 버전의 클라우드 커넥터로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="2caae-103">Upgrade to a new version of Cloud Connector</span></span>
 
<span data-ttu-id="2caae-104">클라우드 커넥터 에디션 배포를 업그레이드 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-104">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="2caae-105">온라인 관리 테 넌 트 계정을 설정 하 고 자동 업데이트를 사용 하는 경우 자동 업데이트 시간 창에 따라 비즈니스용 Skype 클라우드 커넥터 에디션에 대 한 기존 배포가 자동으로 최신 버전으로 업그레이드 됩니다. 구성.</span><span class="sxs-lookup"><span data-stu-id="2caae-105">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="2caae-106">수동 업그레이드를 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-106">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="2caae-107">Cloud Connector Edition 버전 1.4.1 이상에서는 기본적으로 자동 업데이트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-107">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="2caae-108">최신 버전 (2.1)으로 수동으로 업그레이드 하려는 경우이 항목의 뒷부분에 나오는 [단일 사이트를 새 버전으로 업그레이드](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2caae-108">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="2caae-109">자동 업데이트를 사용 하려면 클라우드 커넥터 서비스가 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-109">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="2caae-110">다음 단계에서는 자동 업데이트에 대 한 프로세스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-110">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="2caae-111">자동 업데이트 프로세스는 자동 업데이트를 위해 구성한 일정에 따라 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-111">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="2caae-112">운영 체제 업데이트 작업</span><span class="sxs-lookup"><span data-stu-id="2caae-112">Operating system update tasks</span></span>
    
  - <span data-ttu-id="2caae-113">모든 클라우드 커넥터 Vm에 대 한 운영 체제 업데이트를 확인 하 고 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-113">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="2caae-114">모든 클라우드 커넥터 Vm을 하나씩 설치 하 고 업데이트 한 후 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-114">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="2caae-115">클라우드 커넥터 Vm을 다시 시작한 후에 다른 다시 시작이 필요한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-115">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="2caae-116">클라우드 커넥터 Vm이 성공적으로 패치 된 후 클라우드 커넥터 호스트 컴퓨터에 대 한 프로세스를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-116">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="2caae-117">클라우드 커넥터 호스트 컴퓨터를 성공적으로 부팅 한 후에는 처리 중인 운영 체제 업데이트 작업이 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-117">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="2caae-118">클라우드 커넥터 업데이트 작업</span><span class="sxs-lookup"><span data-stu-id="2caae-118">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="2caae-119">다운로드 사이트에서 버전 파일을 다운로드 하 여 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-119">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="2caae-120">새 버전의 .msi 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-120">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="2caae-121">이전 msi 파일을 제거 합니다. 새 msi 파일을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-121">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="2caae-122">새 버전의 비즈니스용 Skype 비트를 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="2caae-122">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="2caae-123">등록-CcAppliance를 호출 하 여 기기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-123">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="2caae-124">새 클라우드 커넥터 버전을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-124">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="2caae-125">이전 기기를 방전 하 고 새 기기로 네트워크 연결을 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-125">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="2caae-126">클라우드 커넥터가 새 빌드로 업데이트 되 면 클라우드 커넥터 cmdlet이 업데이트 되지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-126">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="2caae-127">예를 들어 자동 업데이트가 발생 하는 동안 PowerShell 창이 열려 있는 경우이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-127">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="2caae-128">업데이트 된 cmdlet을 로드 하려면 다음 단계 중 하나를 수행 합니다. 클라우드 커넥터 기기에서 PowerShell을 > 다음 PowerShell을 다시 엽니다. > 또는 가져오기-모듈 CloudConnector-Force를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-128">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="2caae-129">단일 사이트를 새 버전으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="2caae-129">Upgrade a single site to a new version</span></span>
<span data-ttu-id="2caae-130"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="2caae-130"></span></span>

<span data-ttu-id="2caae-131">업그레이드 하려는 사이트에 하나의 기기만 있는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-131">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="2caae-132">**제어판 \> 프로그램 \> 의 프로그램 및 기능**에서 기존 클라우드 커넥터 버전을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-132">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="2caae-133">에서 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)새 버전의 cloudconnector의 msi를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-133">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="2caae-134">설치 하려는 버전에 대 한 CloudConnector .ini 파일이 있고 환경에 필요한 모든 값을 업데이트 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-134">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="2caae-135">이전 릴리스에서는 .ini 파일을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-135">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="2caae-136">클라우드 커넥터를 업그레이드 하는 경우 [클라우드 커넥터 기기 준비](prepare-your-cloud-connector-appliance.md) 항목을 참조 하 고 다음을 사용 하 여 SiteName 및 EnableReferSupport가 cloudconnector .ini 파일에서 올바른 값으로 설정 되어 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="2caae-136">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="2caae-137">PowerShell 콘솔을 관리자로 시작 하 고 다음 cmdlet을 실행 하 여 현재 기기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-137">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```
   Register-CcAppliance
   ```

5. <span data-ttu-id="2caae-138">다음 cmdlet을 실행 하 여 최신 버전을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-138">Run the following cmdlet to download the latest version:</span></span>
    
   ```
   Start-CcDownload
   ```

6. <span data-ttu-id="2caae-139">다음 cmdlet을 실행 하 여 설치를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-139">Run the following cmdlet to start the installation:</span></span> 
    
   ```
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="2caae-140">다음 cmdlet을 실행 하 여 새 배포를 활성화 하 고 이전 버전을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-140">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```
   Switch-CcVersion
   ```

<span data-ttu-id="2caae-141">사이트에 둘 이상의 기기가 있는 경우 앞의 단계를 따라 각 기기를 하나씩 업그레이드 하세요.</span><span class="sxs-lookup"><span data-stu-id="2caae-141">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="2caae-142">도메인 관리자, 가상 컴퓨터 관리자, 안전 모드 관리자 및 테 넌 트 관리자 자격 증명을 업데이트 하려는 경우 _Updateallcredentials_ 매개 변수를 사용 하 여 cmdlet을 실행 하 여 모든 자격 증명을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-142">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="2caae-143">그런 다음 새 버전으로 업그레이드 하기 시작 하면 새 자격 증명을 입력 하도록 승격 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-143">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="2caae-144">테 넌 트 관리자 자격 증명만을 다시 설정 하려는 경우 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-144">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="2caae-145">여러 사이트를 새 버전으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="2caae-145">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="2caae-146"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="2caae-146"></span></span>

<span data-ttu-id="2caae-147">배포의 각 사이트에 대해 한 번에 한 사이트를 업그레이드 하 여 단일 사이트를 업그레이드 하는 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-147">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="2caae-148">각 사이트를 업그레이드 한 후 [클라우드 커넥터 배포를 확인 하 고 유효성을 검사](validate-your-cloud-connector-deployment.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="2caae-148">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

