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
description: 클라우드 커넥터 에디션에 단일 PSTN 사이트를 배포 하는 방법에 대해 알아보세요.
ms.openlocfilehash: 09aa2e2a7417539757c70368e4f7a508de57bc7f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799708"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a><span data-ttu-id="d35ef-103">클라우드 커넥터에서 단일 사이트 배포</span><span class="sxs-lookup"><span data-stu-id="d35ef-103">Deploy a single site in Cloud Connector</span></span>
 
<span data-ttu-id="d35ef-104">클라우드 커넥터 에디션에 단일 PSTN 사이트를 배포 하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="d35ef-104">Learn about deploying a single PSTN site in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="d35ef-105">HA (고가용성) 지원 여부에 관계 없이 비즈니스용 Skype 클라우드 커넥터 에디션을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-105">You can deploy Skype for Business Cloud Connector Edition with or without High Availability (HA) support.</span></span> <span data-ttu-id="d35ef-106">HA를 사용 하도록 설정 하려면 사이트 내에 두 개 이상의 기기를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-106">If you want to enable HA, you'll need to deploy two or more appliances within a site.</span></span> <span data-ttu-id="d35ef-107">또한 기존 기기를 배포 후 HA를 지원 하도록 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-107">You can also convert an existing appliance to support HA after it is deployed.</span></span>
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a><span data-ttu-id="d35ef-108">첫 번째 비즈니스용 Skype 클라우드 커넥터 에디션 기기 배포</span><span class="sxs-lookup"><span data-stu-id="d35ef-108">Deploy the first Skype for Business Cloud Connector Edition appliance</span></span>

<span data-ttu-id="d35ef-109">사이트에 첫 번째 기기를 배포 하려면 관리자로 PowerShell 콘솔을 열고 다음 cmdlet을 실행 하 여 기기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-109">To deploy the first appliance in a site, open a PowerShell console as administrator and run the following cmdlet to register the appliance:</span></span>
  
```powershell
Register-CcAppliance
```

<span data-ttu-id="d35ef-110">지침에 따라 테 넌 트 관리자 계정 이름 및 암호를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-110">Follow the instructions to provide the tenant admin account name and password.</span></span> <span data-ttu-id="d35ef-111">클라우드 커넥터 온라인 관리에 대해 만든 계정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-111">Use the account you have created for Cloud Connector online management.</span></span> <span data-ttu-id="d35ef-112">또한 지침에 따라 외부 인증서 암호, 안전 모드 관리자 암호, 도메인 관리자 암호 및 VM 관리자 암호를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-112">Also, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="d35ef-113">릴리스 1.4.2 및 이전 버전에서는 외부 인증서 암호, 안전 모드 관리자 암호, 도메인 관리자 암호, VM 관리자 암호를 제공 하는 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-113">In release 1.4.2 and earlier, also follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="d35ef-114">릴리스 2.0 이상에서는 지침에 따라 외부 인증서 암호, CceService password 및 CABackupFile 암호를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-114">In release 2.0 and later, also follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="d35ef-115">설치를 시작 하려면 관리자로 PowerShell 콘솔을 열고 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-115">To start the installation, open a PowerShell console as administrator and run the following cmdlet:</span></span>
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a><span data-ttu-id="d35ef-116">기존 사이트에 기기 추가</span><span class="sxs-lookup"><span data-stu-id="d35ef-116">Add an appliance to an existing site</span></span>

<span data-ttu-id="d35ef-117">사이트에 추가 기기를 추가 하 여 HA를 지원 하도록 기존 클라우드 커넥터 사이트를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-117">You can extend an existing Cloud Connector site to support HA by adding additional appliances to the site.</span></span> 
  
1. <span data-ttu-id="d35ef-118">[클라우드 커넥터 기기 준비](prepare-your-cloud-connector-appliance.md)의 설명 대로 단계에 따라 클라우드 커넥터 기기를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-118">Follow the steps to prepare your Cloud Connector appliance as described in [Prepare your Cloud Connector appliance](prepare-your-cloud-connector-appliance.md).</span></span> <span data-ttu-id="d35ef-119">일부 단계는 배포의 첫 번째 기기에만 필요 함을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="d35ef-119">Note that some steps are required only for the first appliance in your deployment.</span></span> <span data-ttu-id="d35ef-120">사이트 디렉터리가 있고 HA 지원에 맞게 올바르게 구성 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-120">Confirm that the site directory exists and is correctly configured for HA support.</span></span>
    
2. <span data-ttu-id="d35ef-121">새로 추가한 호스트 서버 에서만 다음 cmdlet을 실행 하 여 Office 365 테 넌 트 구성의 토폴로지 정보를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-121">Run the following cmdlet only on the newly added host server to update topology information in your Office 365 tenant configuration.</span></span> <span data-ttu-id="d35ef-122">동시에 여러 기기를 추가 하려는 경우 새로 추가 된 각 호스트 서버에서 cmdlet을 하나씩 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-122">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

3. <span data-ttu-id="d35ef-123">각 호스트 서버에서 다음 cmdlet을 실행 하 여 기존 기기의 토폴로지를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-123">Update the topology on existing appliances by running the following cmdlet on each host server.</span></span> <span data-ttu-id="d35ef-124">기존 기기 에서만 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-124">Only run the cmdlet on the existing appliances.</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

4. <span data-ttu-id="d35ef-125">새로 추가 된 호스트 서버 에서만 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-125">Run the following cmdlet only on newly added host servers.</span></span> <span data-ttu-id="d35ef-126">기존 기기에서이 cmdlet을 실행 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d35ef-126">Do not run this cmdlet on the existing appliance.</span></span> <span data-ttu-id="d35ef-127">동시에 여러 기기를 추가 하려는 경우 새로 추가 된 각 호스트 서버에서 cmdlet을 하나씩 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-127">If you want to add multiple appliances at the same time, run the cmdlet on each newly added host server one by one.</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> <span data-ttu-id="d35ef-128">사이트 디렉터리가 로컬 폴더 경로로 설정 된 경우이 폴더에 대 한 파일 공유를 정의 하 고 새 기기의 site directory에 대 한 UNC 경로를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-128">If the site directory was set to a local folder path, you need to define a file share for this folder and use a UNC path for the site directory on the new appliance.</span></span> <span data-ttu-id="d35ef-129">첫 번째 기기 사이트 디렉토리를 로컬 경로로 유지 하거나 공유에 대 한 UNC 경로를 같은 폴더에 사용 하도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-129">You may leave the first appliance site directory with the local path or modify it to use the UNC path for the share to the same folder.</span></span> <span data-ttu-id="d35ef-130">공유 사이트 디렉터리의 위치가 변경 되 면 이전에 설치 된 모든 기기를 제거 하 고 다시 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-130">If the location for the shared site directory changes, any previously-installed appliances need to be uninstalled and then reinstalled.</span></span> <span data-ttu-id="d35ef-131">> 중요: CceService account 및 CABackupFile 계정에 대 한 암호는 해당 사이트 내에 배포 된 모든 기기에서 동일 해야 기기에서 사이트 디렉터리 공유와 암호화 된 CA 백업 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-131">> Important: The password for both the CceService account and the CABackupFile account must be the same on all appliances deployed within the site, so that the appliances can access the site directory share and the encrypted CA backup file in the site directory.</span></span> 
  
## <a name="remove-an-appliance-from-an-existing-site"></a><span data-ttu-id="d35ef-132">기존 사이트에서 기기 제거</span><span class="sxs-lookup"><span data-stu-id="d35ef-132">Remove an appliance from an existing site</span></span>

<span data-ttu-id="d35ef-133">기존 사이트에서 기기를 제거 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-133">If you want to remove an appliance from an existing site:</span></span>
  
1. <span data-ttu-id="d35ef-134">사이트에서 제거 하려는 호스트 서버 에서만 다음 cmdlet을 실행 하 여 Office 365 테 넌 트 구성의 토폴로지 정보를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-134">Run the following cmdlet only on the host servers you want to remove from the site to update the topology information in your Office 365 tenant configuration.</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

2. <span data-ttu-id="d35ef-135">기기의 모든 가상 머신을 제거 하려는 호스트 서버 에서만 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d35ef-135">Run the following cmdlet only on the host servers from which you want to remove all the virtual machines of the appliance.</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```


