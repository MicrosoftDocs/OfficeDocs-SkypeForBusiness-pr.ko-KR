---
title: 클라우드 커넥터의 새 버전으로 업그레이드
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Cloud Connector Edition 배포를 업그레이드하는 방법을 설명합니다.
ms.openlocfilehash: fea78c6b1b6ba3b2e644fef71d78b94aa3a244b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109134"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="bb322-103">클라우드 커넥터의 새 버전으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="bb322-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="bb322-104">Cloud Connector Edition은 비즈니스용 Skype Online과 함께 2021년 7월 31일부터 사용이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="bb322-105">조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="bb322-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="bb322-106">Cloud Connector Edition 배포를 업그레이드하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="bb322-107">온라인 관리 테넌트 계정을 설정하고 자동 업데이트를 사용하도록 설정한 경우 자동 업데이트 시간 창 구성에 따라 비즈니스용 Skype 클라우드 커넥터 버전의 기존 배포가 자동으로 최신 버전으로 업그레이드됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="bb322-108">수동 업그레이드를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="bb322-109">Cloud Connector Edition 버전 1.4.1 이상은 기본적으로 자동 업데이트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="bb322-110">최신 버전(2.1)으로 수동으로 업그레이드하려면 이 항목 의 부분에 있는 [Upgrade a single site to a new version을](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bb322-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="bb322-111">자동 업데이트를 사용하려면 클라우드 커넥터 서비스가 실행되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="bb322-112">다음 단계에서는 자동 업데이트 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="bb322-113">자동 업데이트 프로세스는 자동 업데이트에 대해 구성한 일정에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="bb322-114">운영 체제 업데이트 작업</span><span class="sxs-lookup"><span data-stu-id="bb322-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="bb322-115">운영 체제 업데이트를 확인하고 모든 클라우드 커넥터 VM에 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="bb322-116">모든 클라우드 커넥터 VM을 하나씩 설치 및 업데이트하고 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="bb322-117">클라우드 커넥터 VM을 다시 시작한 후 다른 다시 시작이 필요한지 확인해 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="bb322-118">클라우드 커넥터 VM이 성공적으로 패치된 후 클라우드 커넥터 호스트 컴퓨터의 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="bb322-119">클라우드 커넥터 호스트 시스템이 부팅된 후 미해결 운영 체제 업데이트 작업이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="bb322-120">클라우드 커넥터 업데이트 작업</span><span class="sxs-lookup"><span data-stu-id="bb322-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="bb322-121">다운로드 사이트에서 버전 파일을 다운로드하고 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="bb322-122">새 버전 .msi 파일을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="bb322-123">이전 msi 파일을 제거합니다. 새 msi 파일을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="bb322-124">새 버전의 비즈니스용 Skype 비트를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="bb322-125">Register-CcAppliance를 호출하여 어플라이언스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="bb322-126">새 클라우드 커넥터 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="bb322-127">이전 어플라이언스를 드레인하고 네트워크 연결을 새 어플라이언스로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="bb322-128">클라우드 커넥터가 새 빌드로 업데이트될 때 클라우드 커넥터 cmdlet이 업데이트되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="bb322-129">예를 들어 자동 업데이트가 수행되는 동안 PowerShell 창이 열려 있는 경우 이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="bb322-130">업데이트된 cmd > let을 로드하기 위해 Cloud Connector 어플라이언스에서 powerShell을 닫은 후 PowerShell.> 또는 CloudConnector -Force를 Import-Module 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="bb322-131">단일 사이트를 새 버전으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="bb322-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="bb322-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="bb322-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="bb322-133">사이트에 업그레이드할 어플라이언스가 하나뿐인 경우 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="bb322-134">제어판 프로그램 프로그램 및 기능에서 기존 클라우드 커넥터 **\> 버전을 \> 제거합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb322-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="bb322-135">에서 새 버전의 CloudConnector.msi [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="bb322-136">설치하는 버전에 CloudConnector.ini 파일이 있으며 환경에 필요한 모든 값을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="bb322-137">이전 릴리스의 .ini 파일은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="bb322-138">클라우드 커넥터를 업그레이드하는 경우 [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) 항목을 참조하고 SiteName 및 EnableReferSupport가 클라우드 커넥터 파일의 올바른 값으로 CloudConnector.ini 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="bb322-139">관리자 권한으로 PowerShell 콘솔을 시작하고 다음 cmdlet을 실행하여 현재 어플라이언스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="bb322-140">다음 cmdlet을 실행하여 최신 버전을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="bb322-141">다음 cmdlet을 실행하여 설치를 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="bb322-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="bb322-142">다음 cmdlet을 실행하여 새 배포를 활성화하고 이전 버전을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="bb322-143">사이트에 어플라이언스가 두 개 이상 있는 경우 위의 단계에 따라 각 어플라이언스를 하나씩 업그레이드하세요.</span><span class="sxs-lookup"><span data-stu-id="bb322-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="bb322-144">도메인 관리자, 가상 컴퓨터 관리자, 안전 모드 관리자 및 테넌트 관리자 자격 증명을 업데이트하려면  _UpdateAllCredentials_ 매개 변수를 사용하여 cmdlet을 실행하여 모든 자격 증명을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="bb322-145">그런 다음 새 버전으로 업그레이드를 시작하면 새 자격 증명을 입력할 수 있도록 승격됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="bb322-146">테넌트 관리자 자격 증명만 다시 설정하려는 경우 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="bb322-147">여러 사이트를 새 버전으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="bb322-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="bb322-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="bb322-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="bb322-149">배포의 각 사이트에 대해 한 번씩 한 사이트를 업그레이드하여 단일 사이트를 업그레이드하는 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="bb322-150">각 사이트를 업그레이드한 후 [클라우드](validate-your-cloud-connector-deployment.md) 커넥터 배포를 확인하고 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="bb322-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
