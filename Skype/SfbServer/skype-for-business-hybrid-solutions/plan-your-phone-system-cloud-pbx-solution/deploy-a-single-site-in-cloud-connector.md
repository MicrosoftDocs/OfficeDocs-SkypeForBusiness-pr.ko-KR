---
title: 클라우드 커넥터에서 단일 사이트 배포
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Cloud Connector Edition에서 단일 PSTN 사이트 배포에 대해 자세히 알아보습니다.
ms.openlocfilehash: 32c981b0f7de3d596dc25c3336000871db9fee65
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094836"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="9601a-103">클라우드 커넥터에서 단일 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="9601a-103">Deploy a single site in Cloud Connector</span></span>
 
> [!Important]
> <span data-ttu-id="9601a-104">Cloud Connector Edition은 비즈니스용 Skype Online과 함께 2021년 7월 31일부터 사용이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="9601a-105">조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="9601a-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="9601a-106">Cloud Connector Edition에서 단일 PSTN 사이트 배포에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-106">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="9601a-107">HA(고가용성) 지원 여부에 따라 비즈니스용 Skype 클라우드 커넥터 Edition을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-107">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="9601a-108">HA를 사용하도록 설정하려면 사이트 내에 두 개 이상의 어플라이언스를 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-108">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="9601a-109">기존 어플라이언스가 배포된 후 HA를 지원하기 위해 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-109">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="9601a-110">첫 번째 비즈니스용 Skype 클라우드 커넥터 버전 어플라이언스 배포</span><span class="sxs-lookup"><span data-stu-id="9601a-110">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="9601a-111">사이트에 첫 번째 어플라이언스를 배포하기 위해 관리자 권한으로 PowerShell 콘솔을 열고 다음 cmdlet을 실행하여 어플라이언스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-111">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="9601a-112">지침에 따라 테넌트 관리자 계정 이름과 암호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-112">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="9601a-113">클라우드 커넥터 온라인 관리를 위해 만든 계정을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="9601a-113">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="9601a-114">또한 지침에 따라 외부 인증서 암호, 안전 모드 관리자 암호, 도메인 관리자 암호 및 VM 관리자 암호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-114">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="9601a-115">1.4.2 이전 버전에서는 지침에 따라 외부 인증서 암호, 안전 모드 관리자 암호, 도메인 관리자 암호 및 VM 관리자 암호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-115">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="9601a-116">릴리스 2.0 이상에서도 지침에 따라 외부 인증서 암호, CceService 암호 및 CABackupFile 암호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-116">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="9601a-117">설치를 시작하기 위해 관리자 권한으로 PowerShell 콘솔을 열고 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-117">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="9601a-118">기존 사이트에 어플라이언스 추가</span><span class="sxs-lookup"><span data-stu-id="9601a-118">Add an appliance to an existing site</span></span>

<span data-ttu-id="9601a-119">사이트에 어플라이언스를 추가하여 기존 클라우드 커넥터 사이트를 확장하여 HA를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-119">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="9601a-120">Prepare your Cloud Connector appliance에 설명된 바와 같이 단계에 따라 클라우드 커넥터 [어플라이언스를 준비합니다.](prepare-your-cloud-connector-appliance.md)</span><span class="sxs-lookup"><span data-stu-id="9601a-120">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="9601a-121">일부 단계는 배포의 첫 번째 어플라이언스에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-121">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="9601a-122">사이트 디렉터리가 있으며 HA 지원에 맞게 올바르게 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-122">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="9601a-123">새로 추가된 호스트 서버에서만 다음 cmdlet을 실행하여 Microsoft 365 또는 Office 365 조직 구성의 토폴로지 정보를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-123">Run the following cmdlet only on the newly added host server to update topology information in your Microsoft 365 or Office 365 organization configuration.</span></span> <span data-ttu-id="9601a-124">여러 어플라이언스를 동시에 추가하려는 경우 새로 추가된 각 호스트 서버에서 하나씩 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-124">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="9601a-125">각 호스트 서버에서 다음 cmdlet을 실행하여 기존 어플라이언스에서 토폴로지 업데이트</span><span class="sxs-lookup"><span data-stu-id="9601a-125">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="9601a-126">기존 어플라이언스에서만 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-126">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="9601a-127">새로 추가된 호스트 서버에서만 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-127">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="9601a-128">기존 어플라이언스에서 이 cmdlet을 실행하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="9601a-128">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="9601a-129">여러 어플라이언스를 동시에 추가하려는 경우 새로 추가된 각 호스트 서버에서 cmdlet을 하나씩 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-129">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="9601a-130">사이트 디렉터리가 로컬 폴더 경로로 설정된 경우 이 폴더에 대한 파일 공유를 정의하고 새 어플라이언스의 사이트 디렉터리에 대해 UNC 경로를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-130">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="9601a-131">로컬 경로가 있는 첫 번째 어플라이언스 사이트 디렉터리를 그대로 두거나 공유의 UNC 경로를 동일한 폴더로 사용하기 위해 이를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-131">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="9601a-132">공유 사이트 디렉터리의 위치가 변경되면 이전에 설치된 모든 어플라이언스를 제거한 다음 다시 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-132">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="9601a-133">> 중요: 어플라이언스가 사이트 디렉터리 공유 및 사이트 디렉터리의 암호화된 CA 백업 파일에 액세스할 수 있도록 CceService 계정과 CABackupFile 계정의 암호는 사이트 내에 배포된 모든 어플라이언스에서 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-133">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="9601a-134">기존 사이트에서 어플라이언스 제거</span><span class="sxs-lookup"><span data-stu-id="9601a-134">Remove an appliance from an existing site</span></span>

<span data-ttu-id="9601a-135">기존 사이트에서 어플라이언스를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="9601a-135">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="9601a-136">사이트에서 제거할 호스트 서버에서만 다음 cmdlet을 실행하여 Microsoft 365 또는 Office 365 조직 구성의 토폴로지 정보를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-136">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Microsoft 365 or Office 365 organization configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="9601a-137">다음 cmdlet은 어플라이언스의 모든 가상 컴퓨터를 제거할 호스트 서버에서만 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9601a-137">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```