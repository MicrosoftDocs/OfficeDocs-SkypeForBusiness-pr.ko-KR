---
title: 기존 클라우드 커넥터 배포의 구성 수정
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: 기존 비즈니스용 Skype 클라우드 Connector Edition 1.4.1 이상 배포의 구성을 수정 하려면이 항목의 단계를 수행 합니다.
ms.openlocfilehash: 77e9940e10cc356afbade5592bf41a0cdba66b0f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779384"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="a726b-103">기존 클라우드 커넥터 배포의 구성 수정</span><span class="sxs-lookup"><span data-stu-id="a726b-103">Modify the configuration of an existing Cloud Connector deployment</span></span>
 
<span data-ttu-id="a726b-104">기존 비즈니스용 Skype 클라우드 Connector Edition 1.4.1 이상 배포의 구성을 수정 하려면이 항목의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-104">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="a726b-105">단일 사이트의 구성 수정</span><span class="sxs-lookup"><span data-stu-id="a726b-105">Modify the configuration of a single site</span></span>
<span data-ttu-id="a726b-106"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="a726b-106"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="a726b-107">사이트에 기기가 하나뿐인 경우 기기를 배포한 후 구성 설정을 변경 하려는 경우에는 CloudConnector .ini 파일을 수정 하 고 배포를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-107">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="a726b-108">다음 cmdlet를 실행 하 여 호스트 서버에서 기존 가상 컴퓨터를 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-108">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="a726b-109">다음 cmdlet를 실행 하 여 기기 등록을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-109">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="a726b-110">기기 디렉터리에서 CloudConnector .ini 파일을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-110">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="a726b-111">다음 cmdlet을 실행 하 여 구성을 업데이트 합니다. (이 단계는 버전 2, 이전 버전의 경우에만 적용 되며, 다음 단계로 건너뜁니다.)</span><span class="sxs-lookup"><span data-stu-id="a726b-111">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="a726b-112">다음 cmdlet를 실행 하 여 기기를 다시 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-112">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="a726b-113">다음 cmdlet를 실행 하 여 비즈니스용 Skype 클라우드 Connector Edition을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-113">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="a726b-114">사이트에 둘 이상의 기기가 있는 경우 다음 단계를 수행 하 고 CloudConnector .ini 파일을 수정한 다음 기기를 하나씩 다시 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-114">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="a726b-115">다음 cmdlet를 실행 하 여 현재 기기에 있는 기존 가상 컴퓨터를 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-115">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="a726b-116">다음 cmdlet를 실행 하 여 기기 등록을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-116">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="a726b-117">기기 디렉터리에서 CloudConnector .ini 파일을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-117">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="a726b-118">다음 cmdlet을 실행 하 여 구성을 업데이트 합니다. (이 단계는 버전 2, 이전 버전의 경우에만 적용 되며, 다음 단계로 건너뜁니다.)</span><span class="sxs-lookup"><span data-stu-id="a726b-118">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="a726b-119">다음 cmdlet를 실행 하 여 기기를 다시 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-119">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="a726b-120">사이트의 다른 모든 기기에서 다음 cmdlet을 실행 하 여 최신 구성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-120">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="a726b-121">다음 cmdlet를 실행 하 여 현재 기기에 클라우드 커넥터를 다시 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-121">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="a726b-122">여러 사이트의 구성 수정</span><span class="sxs-lookup"><span data-stu-id="a726b-122">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="a726b-123"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="a726b-123"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="a726b-124">배포의 여러 사이트에 대 한 구성을 수정 하려면 단일 사이트에 대 한 단계를 수행 하 고 한 번에 한 사이트를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-124">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="a726b-125">자동 업데이트를 사용 하도록 Office 365 조직의 구성 수정</span><span class="sxs-lookup"><span data-stu-id="a726b-125">Modify the configuration of your Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="a726b-126"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="a726b-126"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="a726b-127">운영 체제 자동 업데이트 및 Bits 자동 업데이트를 사용 하도록 설정 하려면 온라인 관리에 비즈니스용 Skype 테 넌 트 관리자 계정을 사용 하 고 다음과 같이 테 넌 트 원격 PowerShell을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-127">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="a726b-128">운영 체제 자동 업데이트 또는 Bits 자동 업데이트를 사용 하지 않도록 설정한 경우 호스트 및 가상 컴퓨터에서 중요 한 Windows 업데이트를 놓칠 수 있으며 클라우드 커넥터가 새 버전으로 자동으로 업그레이드 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-128">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="a726b-129">자동 업데이트를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-129">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="a726b-130">사이트의 EnableAutoUpdate 업데이트 속성을 true (기본값)로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-130">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="a726b-131">다음 cmdlet을 실행 하 여 EnableAutoUpdate 업데이트가 true로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-131">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="a726b-132">테 넌 트에 대 한 자동 업데이트 시간 창을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-132">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="a726b-133">기간은 매일, 매주 및 매월 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-133">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="a726b-134">모든 기간에 시작 시간과 기간이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-134">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="a726b-135">일 단위 기간에는 시작 시간 및 시간만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-135">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="a726b-136">주간 기간에 대해 요일이 1 일 또는 여러 일인 작업일이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-136">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="a726b-137">월별 시간대에는 두 가지 유형이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-137">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="a726b-138">첫 번째 형식은 일을 지정 하는 것 이며 1 일이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-138">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="a726b-139">두 번째 유형은 월의 주와 요일을 지정 하 고, 둘 다 단일 항목 또는 여러 항목 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-139">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="a726b-140">각 테 넌 트에는 20 개의 windows 시간을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-140">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="a726b-141">새 테 넌 트에 대 한 기본 시간대가 운영 체제 업데이트 및 Bits 업데이트를 위한 기본 시간 창으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-141">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="a726b-142">다음 cmdlet을 실행 하 여 일별, 주별 또는 월별 시간 기간을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-142">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - <span data-ttu-id="a726b-143">사이트에 업데이트 시간 창을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-143">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="a726b-144">Bits 업데이트 시간 및 OS 업데이트 시간 창은 별도로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-144">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="a726b-145">두 사용자 모두에 게는 한 번 또는 여러 시간 창에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-145">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="a726b-146">각 시간 창은 서로 다른 사이트에 할당 될 수 있으며 각 시간대에는 다른 용도가 있습니다 (Bits 업데이트 및 OS 업데이트).</span><span class="sxs-lookup"><span data-stu-id="a726b-146">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="a726b-147">다음 cmdlet를 실행 하 여 사이트에 대 한 시간 창을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-147">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="a726b-148">전용 테 넌 트 관리자 자격 증명 업데이트</span><span class="sxs-lookup"><span data-stu-id="a726b-148">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="a726b-149"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="a726b-149"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="a726b-150">클라우드 커넥터에 대 한 Office 365 조 직의 관리 변경 사항은 필요한 사용 권한이 있는 계정에서 만든 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-150">Administrative changes in the Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="a726b-151">2.0 이전 클라우드 커넥터 버전에서 해당 계정은 전용 전역 테 넌 트 관리자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-151">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="a726b-152">클라우드 커넥터 버전 2.0 이상에서는 해당 계정이 비즈니스용 Skype 관리자 권한을 가진 Office 365 계정일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-152">In Cloud Connector versions 2.0 and later, that account can be an Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="a726b-153">Office 365에서 관리자 계정 자격 증명이 변경 되는 경우 배포 된 각 클라우드 커넥터 기기에서 다음 관리자 PowerShell 명령을 실행 하 여 클라우드 커넥터의 로컬로 캐시 된 자격 증명도 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-153">If your admin account credentials change in Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="a726b-154">호스트 서버에 대 한 암호 업데이트</span><span class="sxs-lookup"><span data-stu-id="a726b-154">Update the password for the host server</span></span>
<span data-ttu-id="a726b-155"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a726b-155"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="a726b-156">이 섹션은 클라우드 커넥터 버전 2.0 이상에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-156">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="a726b-157">모든 클라우드 커넥터 자격 증명은 "%SystemDrive%\Programdata\Cloudconnector\credentials." 파일에 저장 됩니다. \<CurrentUser\>"가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-157">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="a726b-158">호스트 서버의 암호가 변경 되 면 로컬로 저장 된 자격 증명을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-158">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="a726b-159">클라우드 커넥터 기기에서 로컬로 저장 된 자격 증명을 업데이트 하려면 [Get-cccredential](get-cccredential.md) 및 [-cccredential](set-cccredential.md) cmdlet을 사용 하 고 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-159">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="a726b-160">나중에 필요한 암호를 검색 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-160">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="a726b-161">Get-CcCredential-AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="a726b-161">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="a726b-162">Get-CcCredential-AccountType VMAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="a726b-162">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="a726b-163">Get-CcCredential-AccountType CceService-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="a726b-163">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="a726b-164">호스트 서버에서 계정의 암호를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-164">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="a726b-165">호스트 서버를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-165">Restart the host server.</span></span>
    
4. <span data-ttu-id="a726b-166">다음 파일을 삭제 합니다. "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>"가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-166">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="a726b-167">PowerShell 콘솔을 관리자 권한으로 시작한 다음 "레지스터-CcAppliance-Local"을 실행 하 여 설명에 해당 하는 암호를 다시 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-167">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="a726b-168">클라우드 커넥터 배포 전에 입력 한 것과 동일한 암호를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-168">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="a726b-169">기본적으로 VmAdmin 및 DomainAdmin은 CceService와 동일한 암호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-169">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="a726b-170">1 단계에서 반환 된 DomainAdmin, VMAdmin 및 CceService 암호가 서로 다르면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-170">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="a726b-171">Set-CcCredential-AccountType DomainAdmin을 다음과 같이 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-171">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="a726b-172">이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-172">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="a726b-173">새 계정 자격 증명을 묻는 메시지가 표시 되 면 1 단계에서 반환 된 DomainAdmin 암호의 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-173">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="a726b-174">다음과 같이 Set-CcCredential-AccountType VmAdmin을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-174">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="a726b-175">이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-175">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="a726b-176">새 계정 자격 증명을 묻는 메시지가 표시 되 면 1 단계에서 반환 된 VmAdmin 암호의 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-176">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="a726b-177">CceService 계정의 암호를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-177">Update the password for the CceService account</span></span>
<span data-ttu-id="a726b-178"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a726b-178"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="a726b-179">이 섹션은 클라우드 커넥터 버전 2.0.1 이상에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-179">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="a726b-180">클라우드 커넥터 서비스가 클라우드 커넥터 관리 서비스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-180">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="a726b-181">CceService 계정은 클라우드 커넥터 에디션 배포 중에 만들어지고 다음 파일에 저장 됩니다. "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>"및"%SystemDrive%\Programdata\Cloudconnector\credentials.. CceService ".</span><span class="sxs-lookup"><span data-stu-id="a726b-181">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="a726b-182">모든 기기가 사이트 디렉터리 공유에 액세스할 수 있도록 하려면 CceService 계정의 암호가 사이트 내에 배포 된 모든 기기에서 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-182">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="a726b-183">다음 사항에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-183">Keep the following in mind:</span></span>
  
- <span data-ttu-id="a726b-184">기본적으로 CceService 계정은 "암호 사용 기간 제한 없음"으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-184">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="a726b-185">암호를 업데이트할 때이 구성을 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-185">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="a726b-186">Bits 또는 Windows 업데이트에 대해 사용량이 많지 않은 기간 동안 및 자동 업데이트 시간 창 외부에서 암호를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-186">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="a726b-187">암호를 업데이트할 때 기기를 다시 시작 하 고 약간의 시간을 소요 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-187">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="a726b-188">기기를 다시 시작 하면 자동 업데이트 작업이 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-188">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="a726b-189">CceService 계정 암호를 변경 하는 경우 모든 자격 증명을 지정 하 고 로컬로 저장 된 파일에 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-189">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="a726b-190">동일한 PSTN 사이트에 속하는 각 기기에 대해 다음을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-190">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="a726b-191">나중에 사용할 계정 이름 및 암호를 검색 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-191">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. <span data-ttu-id="a726b-192">Enter-CcUpdate cmdlet을 실행 하 여 기기를 드레이닝 하 고 수동 유지 관리 모드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-192">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="a726b-193">호스트 서버에서 CceService 계정의 암호를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-193">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="a726b-194">호스트 서버를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-194">Restart the host server.</span></span>
    
5. <span data-ttu-id="a726b-195">복원-CcCredentials cmdlet을 실행 하 여 설명 다음에 암호를 다시 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-195">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="a726b-196">CceService 계정을 제외 하 고 클라우드 커넥터 배포 전에 입력 한 것과 동일한 암호를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-196">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="a726b-197">CceService 계정에 대해 새 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-197">For the CceService account, enter your new password.</span></span> <span data-ttu-id="a726b-198">CceService 계정의 새 암호가 PSTN 사이트의 모든 기기에서 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-198">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="a726b-199">기본적으로 VmAdmin 및 DomainAdmin은 CceService와 동일한 암호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-199">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="a726b-200">1 단계에서 반환 된 DomainAdmin, VMAdmin 및 CceService 암호가 서로 다르면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-200">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="a726b-201">Set-CcCredential-AccountType DomainAdmin을 다음과 같이 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-201">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="a726b-202">이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-202">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="a726b-203">새 계정 자격 증명을 묻는 메시지가 표시 되 면 1 단계에서 반환 된 DomainAdmin 암호의 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-203">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="a726b-204">다음과 같이 Set-CcCredential-AccountType VmAdmin을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-204">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="a726b-205">이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-205">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="a726b-206">새 계정 자격 증명을 묻는 메시지가 표시 되 면 1 단계에서 반환 된 VmAdmin 암호의 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-206">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="a726b-207">수동 유지 관리 모드에서 기기를 이동 하려면 엑시트-CcUpdate cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-207">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="a726b-208">동일한 PSTN 사이트의 모든 기기에서 이러한 단계를 완료 한 후에는 사이트 루트 디렉터리에서 다음 파일을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-208">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="a726b-209">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="a726b-209">CcLockFile</span></span>
    
    - <span data-ttu-id="a726b-210">Site_\<에 지 외부 Sip 풀 fqdn\></span><span class="sxs-lookup"><span data-stu-id="a726b-210">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="a726b-211">Tenant_\<에 지 외부 Sip 풀 fqdn\></span><span class="sxs-lookup"><span data-stu-id="a726b-211">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="a726b-212">TenantConfigLock_\<에 지 외부 Sip 풀 fqdn\></span><span class="sxs-lookup"><span data-stu-id="a726b-212">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="a726b-213">새 SIP 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="a726b-213">Add a new SIP domain</span></span>
<span data-ttu-id="a726b-214"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a726b-214"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="a726b-215">새 SIP 도메인 (또는 여러 SIP 도메인)을 기존 클라우드 커넥터 배포에 추가 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-215">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="a726b-216">Office 365에서 도메인을 업데이트 하는 단계를 완료 했으며 DNS 레코드를 추가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-216">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="a726b-217">Office 365에서 도메인을 설정 하는 방법에 대 한 자세한 내용은 [Add a domain To office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a726b-217">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="a726b-218">새 SIP 도메인 또는 도메인을 사용 하 여 클라우드 커넥터 구성 파일을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-218">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="a726b-219">클라우드 커넥터 구성에 정의 된 각 SIP 도메인에 대해 추가 SAN 이름을 사용 하 여 새에 지 외부 인증서를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-219">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="a726b-220">새에 지 외부 인증서의 경로를 다음과 같이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-220">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="a726b-221">지침에 따라 [단일 사이트의 구성을 수정](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) 하거나 [여러 사이트의 구성을 수정](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-221">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="a726b-222">기본 SIP 도메인 수정</span><span class="sxs-lookup"><span data-stu-id="a726b-222">Modify the primary SIP domain</span></span>
<span data-ttu-id="a726b-223"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a726b-223"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="a726b-224">클라우드 커넥터 배포에서 기본 SIP 도메인을 변경 해야 하는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-224">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="a726b-225">Office 365에서 도메인을 업데이트 하는 단계를 완료 했으며 DNS 레코드를 추가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-225">Make sure you've completed the steps to update your domain in Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="a726b-226">Office 365에서 도메인을 설정 하는 방법에 대 한 자세한 내용은 [Add a domain To office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a726b-226">For more information about how to set up your domain in Office 365, see [Add a domain to Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="a726b-227">새 SIP 도메인을 사용 하 여 클라우드 커넥터 구성 파일을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-227">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="a726b-228">클라우드 커넥터 구성에 정의 된 각 SIP 도메인에 대해 추가 SAN 이름을 사용 하 여 새에 지 외부 인증서를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-228">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="a726b-229">새에 지 외부 인증서의 경로를 다음과 같이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-229">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="a726b-230">클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행 하 여 사이트의 각 기기에 대 한 테 넌 트 등록을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-230">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="a726b-231">비즈니스용 Skype Online PowerShell에서 다음 cmdlet을 실행 하 여 각 사이트에 대 한 사이트 등록을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-231">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="a726b-232">클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행 하 여 각 기기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-232">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="a726b-233">클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행 하 여 각 기기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-233">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="a726b-234">클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행 하 여 각 기기를 하나씩 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-234">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="a726b-235">외부에 지 인증서를 새 인증서로 바꾸기</span><span class="sxs-lookup"><span data-stu-id="a726b-235">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="a726b-236"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a726b-236"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="a726b-237">클라우드 커넥터 기기에서 외부에 지 인증서를 교체 해야 하는 경우에는 새에 지 인증서를 획득 하 고, 개인 키 및 전체 인증서 체인이 포함 된 PFX 파일을 준비 하 고, 각 기기에서 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-237">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="a726b-238">Enter-CcUpdate cmdlet을 사용 하 여 기기를 유지 관리 모드로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-238">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="a726b-239">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-239">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="a726b-240">새 인증서의 암호가 이전 암호와 동일 하면 가져오기가 정상적으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-240">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="a726b-241">암호가 다르면 암호가 잘못 되었다는 오류가 표시 되며,-Local 매개 변수를 사용 하 여 Register-CcAppliance cmdlet을 실행 하 고 2 단계를 반복 하 여 암호를 다시 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-241">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="a726b-242">Exit-CcUpdate cmdlet을 사용 하 여 기기를 유지 관리 모드에서 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="a726b-242">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

