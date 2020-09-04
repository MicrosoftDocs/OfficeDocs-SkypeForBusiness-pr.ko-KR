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
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359114"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="a1c46-103">기존 클라우드 커넥터 배포의 구성 수정</span><span class="sxs-lookup"><span data-stu-id="a1c46-103">Modify the configuration of an existing Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="a1c46-104">클라우드 커넥터 버전은 비즈니스용 Skype Online과 함께 2021 년 7 월 31 일에 사용 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="a1c46-105">조직이 팀으로 업그레이드 된 후에는 [직접 라우팅을](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)사용 하 여 팀에 온-프레미스 전화 통신 네트워크를 연결 하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="a1c46-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="a1c46-106">기존 비즈니스용 Skype 클라우드 Connector Edition 1.4.1 이상 배포의 구성을 수정 하려면이 항목의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-106">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="a1c46-107">단일 사이트의 구성 수정</span><span class="sxs-lookup"><span data-stu-id="a1c46-107">Modify the configuration of a single site</span></span>
<span data-ttu-id="a1c46-108"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="a1c46-108"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="a1c46-109">사이트에 기기가 하나뿐인 경우 기기를 배포한 후 구성 설정을 변경 하려는 경우에는 CloudConnector.ini 파일을 수정 하 고 배포를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-109">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="a1c46-110">다음 cmdlet를 실행 하 여 호스트 서버에서 기존 가상 컴퓨터를 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-110">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="a1c46-111">다음 cmdlet를 실행 하 여 기기 등록을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-111">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="a1c46-112">기기 디렉터리에서 CloudConnector.ini 파일을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-112">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="a1c46-113">다음 cmdlet을 실행 하 여 구성을 업데이트 합니다. (이 단계는 버전 2, 이전 버전의 경우에만 적용 되며, 다음 단계로 건너뜁니다.)</span><span class="sxs-lookup"><span data-stu-id="a1c46-113">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="a1c46-114">다음 cmdlet를 실행 하 여 기기를 다시 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-114">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="a1c46-115">다음 cmdlet를 실행 하 여 비즈니스용 Skype 클라우드 Connector Edition을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-115">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="a1c46-116">사이트에 둘 이상의 기기가 있는 경우 다음 단계를 수행 하 고 CloudConnector.ini 파일을 수정한 다음 기기를 하나씩 다시 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-116">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="a1c46-117">다음 cmdlet를 실행 하 여 현재 기기에 있는 기존 가상 컴퓨터를 모두 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-117">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="a1c46-118">다음 cmdlet를 실행 하 여 기기 등록을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-118">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="a1c46-119">기기 디렉터리에서 CloudConnector.ini 파일을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-119">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="a1c46-120">다음 cmdlet을 실행 하 여 구성을 업데이트 합니다. (이 단계는 버전 2, 이전 버전의 경우에만 적용 되며, 다음 단계로 건너뜁니다.)</span><span class="sxs-lookup"><span data-stu-id="a1c46-120">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="a1c46-121">다음 cmdlet를 실행 하 여 기기를 다시 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-121">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="a1c46-122">사이트의 다른 모든 기기에서 다음 cmdlet을 실행 하 여 최신 구성을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-122">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="a1c46-123">다음 cmdlet를 실행 하 여 현재 기기에 클라우드 커넥터를 다시 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-123">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="a1c46-124">여러 사이트의 구성 수정</span><span class="sxs-lookup"><span data-stu-id="a1c46-124">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="a1c46-125"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="a1c46-125"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="a1c46-126">배포의 여러 사이트에 대 한 구성을 수정 하려면 단일 사이트에 대 한 단계를 수행 하 고 한 번에 한 사이트를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-126">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="a1c46-127">자동 업데이트를 사용 하도록 Microsoft 365 또는 Office 365 조직의 구성 수정</span><span class="sxs-lookup"><span data-stu-id="a1c46-127">Modify the configuration of your Microsoft 365 or Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="a1c46-128"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="a1c46-128"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="a1c46-129">운영 체제 자동 업데이트 및 Bits 자동 업데이트를 사용 하도록 설정 하려면 온라인 관리에 비즈니스용 Skype 테 넌 트 관리자 계정을 사용 하 고 다음과 같이 테 넌 트 원격 PowerShell을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-129">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="a1c46-130">운영 체제 자동 업데이트 또는 Bits 자동 업데이트를 사용 하지 않도록 설정한 경우 호스트 및 가상 컴퓨터에서 중요 한 Windows 업데이트를 놓칠 수 있으며 클라우드 커넥터가 새 버전으로 자동으로 업그레이드 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-130">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="a1c46-131">자동 업데이트를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-131">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="a1c46-132">사이트의 EnableAutoUpdate 업데이트 속성을 true (기본값)로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-132">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="a1c46-133">다음 cmdlet을 실행 하 여 EnableAutoUpdate 업데이트가 true로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-133">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="a1c46-134">테 넌 트에 대 한 자동 업데이트 시간 창을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-134">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="a1c46-135">기간은 매일, 매주 및 매월 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-135">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="a1c46-136">모든 기간에 시작 시간과 기간이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-136">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="a1c46-137">일 단위 기간에는 시작 시간 및 시간만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-137">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="a1c46-138">주간 기간에 대해 요일이 1 일 또는 여러 일인 작업일이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-138">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="a1c46-139">월별 시간대에는 두 가지 유형이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-139">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="a1c46-140">첫 번째 형식은 일을 지정 하는 것 이며 1 일이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-140">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="a1c46-141">두 번째 유형은 월의 주와 요일을 지정 하 고, 둘 다 단일 항목 또는 여러 항목 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-141">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="a1c46-142">각 테 넌 트에는 20 개의 windows 시간을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-142">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="a1c46-143">새 테 넌 트에 대 한 기본 시간대가 운영 체제 업데이트 및 Bits 업데이트를 위한 기본 시간 창으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-143">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="a1c46-144">다음 cmdlet을 실행 하 여 일별, 주별 또는 월별 시간 기간을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-144">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="a1c46-145">사이트에 업데이트 시간 창을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-145">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="a1c46-146">Bits 업데이트 시간 및 OS 업데이트 시간 창은 별도로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-146">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="a1c46-147">두 사용자 모두에 게는 한 번 또는 여러 시간 창에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-147">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="a1c46-148">각 시간 창은 서로 다른 사이트에 할당 될 수 있으며 각 시간대에는 다른 용도가 있습니다 (Bits 업데이트 및 OS 업데이트).</span><span class="sxs-lookup"><span data-stu-id="a1c46-148">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="a1c46-149">다음 cmdlet를 실행 하 여 사이트에 대 한 시간 창을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-149">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="a1c46-150">전용 테 넌 트 관리자 자격 증명 업데이트</span><span class="sxs-lookup"><span data-stu-id="a1c46-150">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="a1c46-151"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="a1c46-151"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="a1c46-152">클라우드 커넥터에 대 한 Microsoft 365 또는 Office 365 조 직의 관리 변경 내용은 필요한 권한을 가진 계정에서 만든 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-152">Administrative changes in the Microsoft 365 or Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="a1c46-153">2.0 이전 클라우드 커넥터 버전에서 해당 계정은 전용 전역 테 넌 트 관리자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-153">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="a1c46-154">클라우드 커넥터 버전 2.0 이상에서는 해당 계정이 비즈니스용 Skype 관리자 권한을 가진 Microsoft 365 또는 Office 365 계정일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-154">In Cloud Connector versions 2.0 and later, that account can be a Microsoft 365 or Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="a1c46-155">Microsoft 365 또는 Office 365에서 관리자 계정 자격 증명이 변경 되는 경우 배포 된 각 클라우드 커넥터 기기에 대해 다음 관리자 PowerShell 명령을 실행 하 여 클라우드 커넥터에서 로컬로 캐싱된 자격 증명도 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-155">If your admin account credentials change in Microsoft 365 or Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="a1c46-156">호스트 서버에 대 한 암호 업데이트</span><span class="sxs-lookup"><span data-stu-id="a1c46-156">Update the password for the host server</span></span>
<span data-ttu-id="a1c46-157"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a1c46-157"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="a1c46-158">이 섹션은 클라우드 커넥터 버전 2.0 이상에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-158">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="a1c46-159">모든 클라우드 커넥터 자격 증명은 "%SystemDrive%\Programdata\Cloudconnector\credentials." 파일에 저장 됩니다 \<CurrentUser\> . xml "입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-159">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="a1c46-160">호스트 서버의 암호가 변경 되 면 로컬로 저장 된 자격 증명을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-160">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="a1c46-161">클라우드 커넥터 기기에서 로컬로 저장 된 자격 증명을 업데이트 하려면 [Get-cccredential](get-cccredential.md) 및 [-cccredential](set-cccredential.md) cmdlet을 사용 하 고 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-161">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="a1c46-162">나중에 필요한 암호를 검색 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-162">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="a1c46-163">Get-CcCredential-AccountType DomainAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="a1c46-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="a1c46-164">Get-CcCredential-AccountType VMAdmin-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="a1c46-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="a1c46-165">Get-CcCredential-AccountType CceService-DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="a1c46-165">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="a1c46-166">호스트 서버에서 계정의 암호를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-166">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="a1c46-167">호스트 서버를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-167">Restart the host server.</span></span>
    
4. <span data-ttu-id="a1c46-168">"%SystemDrive%\Programdata\Cloudconnector\credentials." 파일을 \<CurrentUser\> 삭제 합니다. xml "입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-168">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="a1c46-169">PowerShell 콘솔을 관리자 권한으로 시작한 다음 "레지스터-CcAppliance-Local"을 실행 하 여 설명에 해당 하는 암호를 다시 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-169">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="a1c46-170">클라우드 커넥터 배포 전에 입력 한 것과 동일한 암호를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-170">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="a1c46-171">기본적으로 VmAdmin 및 DomainAdmin은 CceService와 동일한 암호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-171">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="a1c46-172">1 단계에서 반환 된 DomainAdmin, VMAdmin 및 CceService 암호가 서로 다르면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-172">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="a1c46-173">Set-CcCredential-AccountType DomainAdmin을 다음과 같이 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-173">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="a1c46-174">이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-174">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="a1c46-175">새 계정 자격 증명을 묻는 메시지가 표시 되 면 1 단계에서 반환 된 DomainAdmin 암호의 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-175">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="a1c46-176">다음과 같이 Set-CcCredential-AccountType VmAdmin을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-176">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="a1c46-177">이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-177">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="a1c46-178">새 계정 자격 증명을 묻는 메시지가 표시 되 면 1 단계에서 반환 된 VmAdmin 암호의 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-178">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="a1c46-179">CceService 계정의 암호를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-179">Update the password for the CceService account</span></span>
<span data-ttu-id="a1c46-180"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a1c46-180"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="a1c46-181">이 섹션은 클라우드 커넥터 버전 2.0.1 이상에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-181">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="a1c46-182">클라우드 커넥터 서비스가 클라우드 커넥터 관리 서비스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-182">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="a1c46-183">CceService 계정은 클라우드 커넥터 에디션 배포 중에 만들어지고 "%SystemDrive%\Programdata\Cloudconnector\credentials. 파일에 저장 \<CurrentUser\> 됩니다. xml "및"% \Programdata\Cloudconnector\credentials..CceService.xml "</span><span class="sxs-lookup"><span data-stu-id="a1c46-183">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="a1c46-184">모든 기기가 사이트 디렉터리 공유에 액세스할 수 있도록 하려면 CceService 계정의 암호가 사이트 내에 배포 된 모든 기기에서 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-184">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="a1c46-185">다음 사항에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-185">Keep the following in mind:</span></span>
  
- <span data-ttu-id="a1c46-186">기본적으로 CceService 계정은 "암호 사용 기간 제한 없음"으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-186">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="a1c46-187">암호를 업데이트할 때이 구성을 유지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-187">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="a1c46-188">Bits 또는 Windows 업데이트에 대해 사용량이 많지 않은 기간 동안 및 자동 업데이트 시간 창 외부에서 암호를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-188">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="a1c46-189">암호를 업데이트할 때 기기를 다시 시작 하 고 약간의 시간을 소요 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-189">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="a1c46-190">기기를 다시 시작 하면 자동 업데이트 작업이 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-190">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="a1c46-191">CceService 계정 암호를 변경 하는 경우 모든 자격 증명을 지정 하 고 로컬로 저장 된 파일에 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-191">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="a1c46-192">동일한 PSTN 사이트에 속하는 각 기기에 대해 다음을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-192">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="a1c46-193">나중에 사용할 계정 이름 및 암호를 검색 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-193">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="a1c46-194">Enter-CcUpdate cmdlet을 실행 하 여 기기를 드레이닝 하 고 수동 유지 관리 모드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-194">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="a1c46-195">호스트 서버에서 CceService 계정의 암호를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-195">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="a1c46-196">호스트 서버를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-196">Restart the host server.</span></span>
    
5. <span data-ttu-id="a1c46-197">복원-CcCredentials cmdlet을 실행 하 여 설명 다음에 암호를 다시 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-197">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="a1c46-198">CceService 계정을 제외 하 고 클라우드 커넥터 배포 전에 입력 한 것과 동일한 암호를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-198">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="a1c46-199">CceService 계정에 대해 새 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-199">For the CceService account, enter your new password.</span></span> <span data-ttu-id="a1c46-200">CceService 계정의 새 암호가 PSTN 사이트의 모든 기기에서 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-200">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="a1c46-201">기본적으로 VmAdmin 및 DomainAdmin은 CceService와 동일한 암호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-201">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="a1c46-202">1 단계에서 반환 된 DomainAdmin, VMAdmin 및 CceService 암호가 서로 다르면 다음 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-202">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="a1c46-203">Set-CcCredential-AccountType DomainAdmin을 다음과 같이 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-203">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="a1c46-204">이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-204">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="a1c46-205">새 계정 자격 증명을 묻는 메시지가 표시 되 면 1 단계에서 반환 된 DomainAdmin 암호의 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-205">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="a1c46-206">다음과 같이 Set-CcCredential-AccountType VmAdmin을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-206">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="a1c46-207">이전 계정 자격 증명을 묻는 메시지가 표시 되 면 CceService 암호에 사용한 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-207">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="a1c46-208">새 계정 자격 증명을 묻는 메시지가 표시 되 면 1 단계에서 반환 된 VmAdmin 암호의 암호를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-208">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="a1c46-209">수동 유지 관리 모드에서 기기를 이동 하려면 엑시트-CcUpdate cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-209">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="a1c46-210">동일한 PSTN 사이트의 모든 기기에서 이러한 단계를 완료 한 후에는 사이트 루트 디렉터리에서 다음 파일을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-210">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="a1c46-211">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="a1c46-211">CcLockFile</span></span>
    
    - <span data-ttu-id="a1c46-212">Site_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="a1c46-212">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="a1c46-213">Tenant_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="a1c46-213">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="a1c46-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="a1c46-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="a1c46-215">새 SIP 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="a1c46-215">Add a new SIP domain</span></span>
<span data-ttu-id="a1c46-216"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a1c46-216"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="a1c46-217">새 SIP 도메인 (또는 여러 SIP 도메인)을 기존 클라우드 커넥터 배포에 추가 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-217">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="a1c46-218">Microsoft 365 또는 Office 365에서 도메인을 업데이트 하는 단계를 완료 했으며 DNS 레코드를 추가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-218">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="a1c46-219">Microsoft 365 또는 Office 365에서 도메인을 설정 하는 방법에 대 한 자세한 내용은 [microsoft 365 또는 office 365에 도메인 추가](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c46-219">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="a1c46-220">새 SIP 도메인 또는 도메인을 사용 하 여 클라우드 커넥터 구성 파일을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-220">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="a1c46-221">클라우드 커넥터 구성에 정의 된 각 SIP 도메인에 대해 추가 SAN 이름을 사용 하 여 새에 지 외부 인증서를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-221">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="a1c46-222">새에 지 외부 인증서의 경로를 다음과 같이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-222">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="a1c46-223">지침에 따라 [단일 사이트의 구성을 수정](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) 하거나 [여러 사이트의 구성을 수정](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-223">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="a1c46-224">기본 SIP 도메인 수정</span><span class="sxs-lookup"><span data-stu-id="a1c46-224">Modify the primary SIP domain</span></span>
<span data-ttu-id="a1c46-225"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a1c46-225"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="a1c46-226">클라우드 커넥터 배포에서 기본 SIP 도메인을 변경 해야 하는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-226">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="a1c46-227">Microsoft 365 또는 Office 365에서 도메인을 업데이트 하는 단계를 완료 했으며 DNS 레코드를 추가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-227">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="a1c46-228">Microsoft 365 또는 Office 365에서 도메인을 설정 하는 방법에 대 한 자세한 내용은 [microsoft 365 또는 office 365에 도메인 추가](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a1c46-228">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="a1c46-229">새 SIP 도메인을 사용 하 여 클라우드 커넥터 구성 파일을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-229">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="a1c46-230">클라우드 커넥터 구성에 정의 된 각 SIP 도메인에 대해 추가 SAN 이름을 사용 하 여 새에 지 외부 인증서를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-230">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="a1c46-231">새에 지 외부 인증서의 경로를 다음과 같이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-231">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="a1c46-232">클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행 하 여 사이트의 각 기기에 대 한 테 넌 트 등록을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-232">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="a1c46-233">비즈니스용 Skype Online PowerShell에서 다음 cmdlet을 실행 하 여 각 사이트에 대 한 사이트 등록을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-233">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="a1c46-234">클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행 하 여 각 기기를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-234">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="a1c46-235">클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행 하 여 각 기기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-235">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="a1c46-236">클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행 하 여 각 기기를 하나씩 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-236">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="a1c46-237">외부에 지 인증서를 새 인증서로 바꾸기</span><span class="sxs-lookup"><span data-stu-id="a1c46-237">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="a1c46-238"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="a1c46-238"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="a1c46-239">클라우드 커넥터 기기에서 외부에 지 인증서를 교체 해야 하는 경우에는 새에 지 인증서를 획득 하 고, 개인 키 및 전체 인증서 체인이 포함 된 PFX 파일을 준비 하 고, 각 기기에서 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-239">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="a1c46-240">Enter-CcUpdate cmdlet을 사용 하 여 기기를 유지 관리 모드로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-240">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="a1c46-241">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-241">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="a1c46-242">새 인증서의 암호가 이전 암호와 동일 하면 가져오기가 정상적으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-242">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="a1c46-243">암호가 다르면 암호가 잘못 되었다는 오류가 표시 되며,-Local 매개 변수를 사용 하 여 Register-CcAppliance cmdlet을 실행 하 고 2 단계를 반복 하 여 암호를 다시 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-243">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="a1c46-244">Exit-CcUpdate cmdlet을 사용 하 여 기기를 유지 관리 모드에서 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-244">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

