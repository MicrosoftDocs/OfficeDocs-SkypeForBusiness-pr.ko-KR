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
description: Cloud Connector Edition 배포를 업그레이드 하는 방법을 알아봅니다.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359294"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a><span data-ttu-id="52b65-103">클라우드 커넥터의 새 버전으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="52b65-103">Upgrade to a new version of Cloud Connector</span></span>

> [!Important]
> <span data-ttu-id="52b65-104">클라우드 커넥터 버전은 비즈니스용 Skype Online과 함께 2021 년 7 월 31 일에 사용 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="52b65-105">조직이 팀으로 업그레이드 된 후에는 [직접 라우팅을](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)사용 하 여 팀에 온-프레미스 전화 통신 네트워크를 연결 하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="52b65-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="52b65-106">Cloud Connector Edition 배포를 업그레이드 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-106">Learn about how to upgrade your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="52b65-107">온라인 관리 테 넌 트 계정을 설정 하 고 자동 업데이트를 사용 하도록 설정한 경우 자동 업데이트 시간 창 구성에 따라 비즈니스용 Skype 클라우드 커넥터 Edition의 기존 배포가 새 버전으로 자동으로 업그레이드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-107">If you have set up an online management tenant account and enabled automatic updates, your existing deployment of Skype for Business Cloud Connector Edition will be upgraded to the newer version automatically—according to your automatic update time window configuration.</span></span> <span data-ttu-id="52b65-108">수동 업그레이드를 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-108">You can also perform a manual upgrade.</span></span> 
  
<span data-ttu-id="52b65-109">Cloud Connector Edition 버전 1.4.1 이상에서는 기본적으로 자동 업데이트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-109">Cloud Connector Edition versions 1.4.1 and later perform automatic updates by default.</span></span> <span data-ttu-id="52b65-110">최신 버전 (2.1)으로 수동으로 업그레이드 하려면이 항목의 뒷부분에 나오는 [단일 사이트를 새 버전으로](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) 업그레이드를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="52b65-110">If you want to upgrade to the latest version (2.1) manually, see [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.</span></span>
  
<span data-ttu-id="52b65-111">자동 업데이트를 사용 하려면 클라우드 커넥터 서비스가 실행 되 고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-111">Automatic update requires that the Cloud Connector service is running.</span></span> <span data-ttu-id="52b65-112">다음 단계에서는 자동 업데이트에 대 한 프로세스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-112">The following steps describe the process for automatic updates:</span></span>
  
- <span data-ttu-id="52b65-113">자동 업데이트에 대해 구성한 일정에 따라 자동 업데이트 프로세스가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-113">The automatic update process will run according to the schedule you have configured for automatic updates.</span></span>
    
- <span data-ttu-id="52b65-114">운영 체제 업데이트 작업</span><span class="sxs-lookup"><span data-stu-id="52b65-114">Operating system update tasks</span></span>
    
  - <span data-ttu-id="52b65-115">모든 클라우드 커넥터 Vm에 대 한 운영 체제 업데이트를 확인 하 고 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-115">Check and download operating system updates to all Cloud Connector VMs.</span></span> 
    
  - <span data-ttu-id="52b65-116">모든 클라우드 커넥터 Vm을 하나씩 설치 및 업데이트 하 고 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-116">Install and update all Cloud Connector VMs one by one and restart.</span></span>
    
  - <span data-ttu-id="52b65-117">클라우드 커넥터 Vm이 다시 시작 된 후에 다른 다시 시작이 필요한 지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="52b65-117">After the Cloud Connector VMs restart, check to see if another restart is needed.</span></span>
    
  - <span data-ttu-id="52b65-118">클라우드 커넥터 Vm이 패치 된 후 클라우드 커넥터 호스트 컴퓨터에 대 한 프로세스를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-118">After the Cloud Connector VMs have been successfully patched, repeat the process for the Cloud Connector host machine.</span></span>
    
  - <span data-ttu-id="52b65-119">클라우드 커넥터 호스트 컴퓨터가 성공적으로 부팅 된 후에는 모든 처리 중인 운영 체제 업데이트 작업이 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-119">After the Cloud Connector host machine successfully boots up, any outstanding operating system update tasks are completed.</span></span>
    
- <span data-ttu-id="52b65-120">클라우드 커넥터 업데이트 작업</span><span class="sxs-lookup"><span data-stu-id="52b65-120">Cloud Connector update tasks</span></span>
    
  - <span data-ttu-id="52b65-121">다운로드 사이트에서 버전 파일을 다운로드 하 여 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-121">Download and check the version file from the download site.</span></span>
    
  - <span data-ttu-id="52b65-122">새 버전의 .msi 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-122">Download the new version .msi file.</span></span> 
    
  - <span data-ttu-id="52b65-123">이전 msi 파일을 제거 합니다. 새 msi 파일을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-123">Uninstall the old msi file; install the new msi file.</span></span>
    
  - <span data-ttu-id="52b65-124">새 버전의 비즈니스용 Skype 비트를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-124">Download the new version of Skype for Business bits.</span></span>
    
  - <span data-ttu-id="52b65-125">Register-CcAppliance를 호출 하 여 기기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-125">Register the appliance by calling Register-CcAppliance.</span></span>
    
  - <span data-ttu-id="52b65-126">새 클라우드 커넥터 버전을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-126">Install the new Cloud Connector version.</span></span>
    
  - <span data-ttu-id="52b65-127">이전 기기를 방전 하 고 새 기기로 네트워크 연결을 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-127">Drain the old appliance and switch the network connection to the new appliance.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="52b65-128">클라우드 커넥터가 새 빌드로 업데이트 되 면 클라우드 커넥터 cmdlet이 업데이트 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-128">When Cloud Connector updates to a new build, Cloud Connector cmdlets might not be updated.</span></span> <span data-ttu-id="52b65-129">예를 들어 자동 업데이트를 수행 하는 동안 PowerShell 창을 열어 두면이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-129">This can happen, for example, if a PowerShell window is left open while automatic update occurs.</span></span> <span data-ttu-id="52b65-130">업데이트 된 cmdlet을 로드 하려면 > 다음 단계 중 하나를 수행 하면 됩니다. 클라우드 커넥터 기기에서 PowerShell을 닫고 PowerShell을 다시 엽니다. > 하거나 Import-Module CloudConnector-Force를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-130">To load the updated cmdlets, you can do either of the following steps:>  Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.>  Or, you can run Import-Module CloudConnector -Force.</span></span>
  
## <a name="upgrade-a-single-site-to-a-new-version"></a><span data-ttu-id="52b65-131">단일 사이트를 새 버전으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="52b65-131">Upgrade a single site to a new version</span></span>
<span data-ttu-id="52b65-132"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="52b65-132"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="52b65-133">업그레이드 하려는 사이트에 기기가 하나뿐인 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-133">If there is only one appliance in the site you want to upgrade, do the following:</span></span>
  
1. <span data-ttu-id="52b65-134">**제어판 프로그램의 프로그램 \> \> 및 기능**에서 기존 클라우드 커넥터 버전을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-134">Uninstall the existing Cloud Connector version in **Control Panel \> Programs \> Programs and Features**.</span></span>
    
2. <span data-ttu-id="52b65-135">에서 CloudConnector.msi의 새 버전을 설치 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-135">Install the new version of CloudConnector.msi from [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).</span></span>
    
3. <span data-ttu-id="52b65-136">설치 하려는 버전의 CloudConnector.ini 파일이 있으며 환경에 필요한 모든 값을 업데이트 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-136">Confirm that you have the CloudConnector.ini file for the version you are installing, and that you have updated all of the required values for your environment.</span></span> <span data-ttu-id="52b65-137">이전 릴리스의 .ini 파일은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-137">You cannot use the .ini file from a previous release.</span></span> <span data-ttu-id="52b65-138">클라우드 커넥터를 업그레이드 하는 경우 [클라우드 커넥터 기기 준비](prepare-your-cloud-connector-appliance.md) 항목을 참조 하 고 CloudConnector.ini 파일에서 SiteName 및 EnableReferSupport가 올바른 값으로 설정 되어 있는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="52b65-138">If you are upgrading Cloud Connector, please refer to the topic [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md) and make sure SiteName and EnableReferSupport are set to the correct value in the CloudConnector.ini file.</span></span>
    
4. <span data-ttu-id="52b65-139">관리자로 PowerShell 콘솔을 시작 하 고 다음 cmdlet을 실행 하 여 현재 기기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-139">Start a PowerShell console as administrator and run the following cmdlet to register the current appliance:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

5. <span data-ttu-id="52b65-140">다음 cmdlet를 실행 하 여 최신 버전을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-140">Run the following cmdlet to download the latest version:</span></span>
    
   ```powershell
   Start-CcDownload
   ```

6. <span data-ttu-id="52b65-141">다음 cmdlet를 실행 하 여 설치를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-141">Run the following cmdlet to start the installation:</span></span> 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. <span data-ttu-id="52b65-142">다음 cmdlet를 실행 하 여 새 배포를 활성화 하 고 이전 버전을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-142">Run the following cmdlet to activate the new deployment and turn off the previous version:</span></span>
    
   ```powershell
   Switch-CcVersion
   ```

<span data-ttu-id="52b65-143">사이트에 둘 이상의 기기가 있으면 앞의 단계에 따라 각 기기를 하나씩 업그레이드 하십시오.</span><span class="sxs-lookup"><span data-stu-id="52b65-143">If there is more than one appliance in the site, please follow the preceding steps to upgrade each appliance one by one.</span></span>
  
<span data-ttu-id="52b65-144">도메인 관리자, 가상 컴퓨터 관리자, 안전 모드 관리자 및 테 넌 트 관리자 자격 증명을 업데이트 하려는 경우  _Updateallcredentials_ 매개 변수를 사용 하 여 cmdlet을 실행 하 여 모든 자격 증명을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-144">If you want to update Domain administrator, Virtual machine administrator, Safe Mode administrator and Tenant administrator credentials, you can run the cmdlet with the  _UpdateAllCredentials_ parameter to reset all credentials:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

<span data-ttu-id="52b65-145">그런 다음 새 버전으로 업그레이드 하기 시작 하면 새 자격 증명을 입력 하도록 승격 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-145">Then, when you start to upgrade to a new version, you will be promoted to input the new credentials.</span></span> 
  
<span data-ttu-id="52b65-146">테 넌 트 관리자 자격 증명만 다시 설정 하려면 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-146">If you only want to reset your Tenant administrator credentials, run the following cmdlet:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a><span data-ttu-id="52b65-147">여러 사이트를 새 버전으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="52b65-147">Upgrade multiple sites to a new version</span></span>
<span data-ttu-id="52b65-148"><a name="BKMK_Upgrade"> </a></span><span class="sxs-lookup"><span data-stu-id="52b65-148"><a name="BKMK_Upgrade"> </a></span></span>

<span data-ttu-id="52b65-149">배포의 각 사이트에 대해 한 번에 한 사이트를 업그레이드 하는 단계를 수행 하 여 단일 사이트를 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-149">Follow the steps for upgrading a single site, upgrading one site at a time for each site in your deployment.</span></span> <span data-ttu-id="52b65-150">각 사이트를 업그레이드 한 후 [에 클라우드 커넥터 배포를 확인 하 고 유효성을 검사](validate-your-cloud-connector-deployment.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="52b65-150">Make sure and [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) after upgrading each site.</span></span>
  

