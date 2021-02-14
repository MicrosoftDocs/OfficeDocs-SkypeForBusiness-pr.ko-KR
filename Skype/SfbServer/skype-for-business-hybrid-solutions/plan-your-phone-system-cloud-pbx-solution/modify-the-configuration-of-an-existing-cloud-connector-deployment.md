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
description: 이 항목의 단계에 따라 기존 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1 이상 배포의 구성을 수정합니다.
ms.openlocfilehash: 2d70dfa9e25a0c89a31e25699e67a21f14e4f097
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359114"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a><span data-ttu-id="d300b-103">기존 클라우드 커넥터 배포의 구성 수정</span><span class="sxs-lookup"><span data-stu-id="d300b-103">Modify the configuration of an existing Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="d300b-104">Cloud Connector Edition은 2021년 7월 31일 비즈니스용 Skype Online과 함께 사용 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="d300b-105">조직이 Teams로 업그레이드한 후 직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 배워야 합니다.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="d300b-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="d300b-106">이 항목의 단계에 따라 기존 비즈니스용 Skype 클라우드 커넥터 버전 1.4.1 이상 배포의 구성을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-106">Follow the steps in this topic to modify the configuration of an existing Skype for Business Cloud Connector Edition 1.4.1 or later deployment.</span></span> 
  
## <a name="modify-the-configuration-of-a-single-site"></a><span data-ttu-id="d300b-107">단일 사이트의 구성 수정</span><span class="sxs-lookup"><span data-stu-id="d300b-107">Modify the configuration of a single site</span></span>
<span data-ttu-id="d300b-108"><a name="BKMK_SIngleSite"> </a></span><span class="sxs-lookup"><span data-stu-id="d300b-108"><a name="BKMK_SIngleSite"> </a></span></span>

<span data-ttu-id="d300b-109">사이트에 어플라이언스가 하나뿐인 경우 어플라이언스가 배포된 후 구성 설정을 변경하려는 경우 CloudConnector.ini 파일을 수정하고 배포를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-109">If there is only one appliance in the site, when you want to change the configuration settings after the appliance is deployed, you can modify the CloudConnector.ini file and start the deployment again.</span></span>
  
1. <span data-ttu-id="d300b-110">다음 cmdlet을 실행하여 호스트 서버에서 모든 기존 가상 컴퓨터를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-110">Run the following cmdlet to uninstall all existing virtual machines on the host server:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="d300b-111">다음 cmdlet을 실행하여 어플라이언스 등록을 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-111">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="d300b-112">Appliance 디렉터리에서 CloudConnector.ini 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-112">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="d300b-113">다음 cmdlet을 실행하여 구성을 업데이트합니다. (이 단계는 버전 2에만 적용되고 이전 버전에서는 다음 단계로 건너뜁습니다.)</span><span class="sxs-lookup"><span data-stu-id="d300b-113">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="d300b-114">다음 cmdlet을 실행하여 어플라이언스를 다시 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-114">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="d300b-115">다음 cmdlet을 실행하여 비즈니스용 Skype 클라우드 커넥터 Edition을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-115">Run the following cmdlet to install Skype for Business Cloud Connector Edition:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

<span data-ttu-id="d300b-116">사이트에 어플라이언스가 두 개 이상 있는 경우 다음 단계를 수행하여 CloudConnector.ini 파일을 수정한 다음 어플라이언스를 하나씩 다시 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-116">If there is more than one appliance in the site, you'll need to follow these steps, modify the CloudConnector.ini file, and redeploy the appliances one by one.</span></span>
  
1. <span data-ttu-id="d300b-117">다음 cmdlet을 실행하여 현재 어플라이언스에 있는 모든 기존 가상 컴퓨터를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-117">Run the following cmdlet to uninstall all existing virtual machines on the current appliance:</span></span> 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. <span data-ttu-id="d300b-118">다음 cmdlet을 실행하여 어플라이언스 등록을 해지합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-118">Run the following cmdlet to unregister the appliance:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

3. <span data-ttu-id="d300b-119">Appliance 디렉터리에서 CloudConnector.ini 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-119">Update the CloudConnector.ini file in the Appliance Directory.</span></span>
    
4. <span data-ttu-id="d300b-120">다음 cmdlet을 실행하여 구성을 업데이트합니다. (이 단계는 버전 2에만 적용되고 이전 버전에서는 다음 단계로 건너뜁습니다.)</span><span class="sxs-lookup"><span data-stu-id="d300b-120">Run the following cmdlet to update the configuration: (This step is only applicable for version 2; for previous versions, skip to the next step.)</span></span>
    
   ```powershell
   Import-CcConfiguration 
   ```

5. <span data-ttu-id="d300b-121">다음 cmdlet을 실행하여 어플라이언스를 다시 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-121">Run the following cmdlet to register the appliance again:</span></span>
    
   ```powershell
   Register-CcAppliance
   ```

6. <span data-ttu-id="d300b-122">사이트의 다른 모든 어플라이언스에서 다음 cmdlet을 실행하여 최신 구성을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="d300b-122">Run the following cmdlet on all other appliances in the site to pick up the latest configuration:</span></span>
    
   ```powershell
   Publish-CcAppliance
   ```

7. <span data-ttu-id="d300b-123">다음 cmdlet을 실행하여 현재 어플라이언스에서 클라우드 커넥터를 다시Eploy합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-123">Run the following cmdlet to redeploy Cloud Connector on the current appliance:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a><span data-ttu-id="d300b-124">여러 사이트의 구성 수정</span><span class="sxs-lookup"><span data-stu-id="d300b-124">Modify the configuration of multiple sites</span></span>
<span data-ttu-id="d300b-125"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="d300b-125"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="d300b-126">배포에서 여러 사이트에 대한 구성을 수정하려면 단일 사이트에 대한 단계를 수행하여 한 사이트에서 한 사이트씩 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-126">To modify the configuration for multiple sites in a deployment, follow the steps for a single site, updating one site at a time.</span></span>
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a><span data-ttu-id="d300b-127">자동 업데이트를 사용하도록 Microsoft 365 또는 Office 365 조직의 구성 수정</span><span class="sxs-lookup"><span data-stu-id="d300b-127">Modify the configuration of your Microsoft 365 or Office 365 organization to enable automatic updates</span></span>
<span data-ttu-id="d300b-128"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="d300b-128"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="d300b-129">운영 체제 자동 업데이트 및 비트 자동 업데이트를 사용하려면 온라인 관리를 위해 비즈니스용 Skype 테넌트 관리자 계정을 사용하고 다음과 같이 테넌트 원격 PowerShell을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-129">To enable operating system automatic updates and Bits automatic updates, you must use the Skype for Business tenant admin account for online management and use tenant remote PowerShell as follows.</span></span>
  
<span data-ttu-id="d300b-130">운영 체제 자동 업데이트 또는 비트 자동 업데이트를 사용하지 않도록 설정한 경우 호스트 및 가상 컴퓨터는 중요한 Windows 업데이트를 놓칠 수 있으며 클라우드 커넥터가 새 버전으로 자동으로 업그레이드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-130">If you disabled operating system automatic updates or Bits automatic updates, your host and virtual machine may miss important Windows updates, and Cloud Connector will not upgrade to the new version automatically.</span></span> <span data-ttu-id="d300b-131">자동 업데이트를 사용하도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-131">It is highly recommended that you enable automatic updates.</span></span>
  
1. <span data-ttu-id="d300b-132">사이트의 EnableAutoUpdate 속성을 true(기본값)로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-132">The EnableAutoUpdate property of the site needs to be set to true (the default value).</span></span> <span data-ttu-id="d300b-133">EnableAutoUpdate가 true로 설정되어 있는지 확인하려면 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-133">Run the following cmdlet to make sure EnableAutoUpdate is set to true:</span></span>
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. <span data-ttu-id="d300b-134">테넌트에 대한 자동 업데이트 시간 창을 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="d300b-134">Create auto update time window for the tenant.</span></span>
    
    <span data-ttu-id="d300b-135">시간 창은 일, 주 및 월간일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-135">The time window can be daily, weekly and monthly.</span></span> <span data-ttu-id="d300b-136">모든 시간 창에 시작 시간 및 기간이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-136">All the time windows need a start time and a duration.</span></span>
    
   - <span data-ttu-id="d300b-137">일별 기간의 경우 시작 시간 및 기간만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-137">For a daily time window, only start time and duration are needed.</span></span> 
    
   - <span data-ttu-id="d300b-138">주간 시간 창의 경우 하루 또는 여러 일일 수 있는 주 중 일 수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-138">For a weekly time window, days of week are needed, which can be a single day or multiple days.</span></span>
    
   - <span data-ttu-id="d300b-139">월별 기간의 경우 두 가지 유형이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-139">For a monthly time window, there can be two types.</span></span> <span data-ttu-id="d300b-140">첫 번째 형식은 하루가 될 수 있는 월의 날짜를 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-140">The first type is to specify the day of the month, which can be a single day.</span></span> <span data-ttu-id="d300b-141">두 번째 유형은 단일 항목 또는 여러 항목이 될 수 있는 주와 함께 주를 지정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-141">The second type is to specify the weeks of the month, along with days of the week, which both can be a single item or multiple items.</span></span>
    
   - <span data-ttu-id="d300b-142">각 테넌트에는 20시간의 기간이 정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-142">Each tenant can have 20 time windows defined.</span></span> <span data-ttu-id="d300b-143">운영 체제 업데이트 및 비트 업데이트의 기본 기간으로 새 테넌트에 대한 기본 시간 창이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-143">The default time window will be created for a new tenant as the default time window for operating system update and Bits update.</span></span> <span data-ttu-id="d300b-144">다음 cmdlet을 실행하여 일, 주 또는 월별 시간 창을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-144">Run the following cmdlet(s) to set the daily, weekly or monthly time window:</span></span>
    
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

   - <span data-ttu-id="d300b-145">사이트에 업데이트 시간 창을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-145">Assign update time windows to the site.</span></span> 
    
     <span data-ttu-id="d300b-146">비트 업데이트 시간 및 OS 업데이트 시간 창은 별도로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-146">The Bits update time and OS update time windows are configured separately.</span></span> <span data-ttu-id="d300b-147">둘 다 한 번 또는 여러 번 창을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-147">Both of them can be assigned single or multiple time windows.</span></span> <span data-ttu-id="d300b-148">각 기간을 다른 사이트 및 용도(비트 업데이트 및 OS 업데이트)에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-148">Each time window can be assigned to different sites and different purpose (Bits update and OS update).</span></span> <span data-ttu-id="d300b-149">다음 cmdlet을 실행하여 사이트의 시간 창을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-149">Run the following cmdlet to set the time window for the site:</span></span> 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a><span data-ttu-id="d300b-150">전용 테넌트 관리자 자격 증명 업데이트</span><span class="sxs-lookup"><span data-stu-id="d300b-150">Update the dedicated tenant admin credentials</span></span>
<span data-ttu-id="d300b-151"><a name="BKMK_MultipleSites"> </a></span><span class="sxs-lookup"><span data-stu-id="d300b-151"><a name="BKMK_MultipleSites"> </a></span></span>

<span data-ttu-id="d300b-152">클라우드 커넥터에 대한 Microsoft 365 또는 Office 365 조직의 관리 변경 사항은 필요한 권한이 있는 계정에서 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-152">Administrative changes in the Microsoft 365 or Office 365 organization for Cloud Connector are made from an account with the needed permissions.</span></span> <span data-ttu-id="d300b-153">2.0 이전의 클라우드 커넥터 버전에서 해당 계정은 전용 전역 테넌트 관리자 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-153">In Cloud Connector versions before 2.0, that account is a dedicated global tenant admin account.</span></span> <span data-ttu-id="d300b-154">클라우드 커넥터 버전 2.0 이상에서 해당 계정은 비즈니스용 Skype 관리자 권한이 있는 Microsoft 365 또는 Office 365 계정일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-154">In Cloud Connector versions 2.0 and later, that account can be a Microsoft 365 or Office 365 account with Skype for Business Administrator rights.</span></span>
  
<span data-ttu-id="d300b-155">Microsoft 365 또는 Office 365에서 관리자 계정 자격 증명이 변경되는 경우 배포한 각 클라우드 커넥터 어플라이언스에서 다음 관리자 PowerShell 명령을 실행하여 클라우드 커넥터에서 로컬로 캐시된 자격 증명을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-155">If your admin account credentials change in Microsoft 365 or Office 365, you also need to update the locally cached credentials in Cloud Connector by running the following Administrator PowerShell command on each Cloud Connector appliance you have deployed:</span></span>
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a><span data-ttu-id="d300b-156">호스트 서버의 암호 업데이트</span><span class="sxs-lookup"><span data-stu-id="d300b-156">Update the password for the host server</span></span>
<span data-ttu-id="d300b-157"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="d300b-157"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="d300b-158">이 섹션은 클라우드 커넥터 버전 2.0 이상에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-158">This section is applicable to Cloud Connector version 2.0 and later.</span></span> 
  
<span data-ttu-id="d300b-159">모든 클라우드 커넥터 자격 증명은 "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".</span><span class="sxs-lookup"><span data-stu-id="d300b-159">All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="d300b-160">호스트 서버의 암호가 변경되는 경우 로컬에 저장된 자격 증명을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-160">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
  
<span data-ttu-id="d300b-161">클라우드 커넥터 어플라이언스에서 로컬로 저장된 자격 증명을 업데이트하기 위해 [Get-CcCredential](get-cccredential.md) 및 [Set-CcCredential](set-cccredential.md) cmdlet을 사용하여 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-161">To update the locally stored credentials on the Cloud Connector appliance, use the [Get-CcCredential](get-cccredential.md) and [Set-CcCredential](set-cccredential.md) cmdlets and follow these steps:</span></span>
  
1. <span data-ttu-id="d300b-162">다음 명령을 실행하여 나중에 필요한 암호를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-162">Run the following commands to retrieve the passwords you will need later:</span></span> 
    
   - <span data-ttu-id="d300b-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="d300b-163">Get-CcCredential -AccountType DomainAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="d300b-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="d300b-164">Get-CcCredential -AccountType VMAdmin -DisplayPassword</span></span>
    
   - <span data-ttu-id="d300b-165">Get-CcCredential -AccountType CceService -DisplayPassword</span><span class="sxs-lookup"><span data-stu-id="d300b-165">Get-CcCredential -AccountType CceService -DisplayPassword</span></span>
    
2. <span data-ttu-id="d300b-166">호스트 서버에서 계정의 암호를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-166">Change the password of your account on the host server.</span></span>
    
3. <span data-ttu-id="d300b-167">호스트 서버를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-167">Restart the host server.</span></span>
    
4. <span data-ttu-id="d300b-168">다음 파일을 삭제합니다. "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> . xml".</span><span class="sxs-lookup"><span data-stu-id="d300b-168">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
5. <span data-ttu-id="d300b-169">관리자 권한으로 PowerShell 콘솔을 시작한 다음 "Register-CcAppliance -Local"을 실행하여 설명에 따라 암호를 다시 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-169">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="d300b-170">클라우드 커넥터 배포 전에 입력한 암호와 동일한 암호를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-170">Be sure you enter the same password you entered before for the Cloud Connector deployment.</span></span>
    
<span data-ttu-id="d300b-171">기본적으로 VmAdmin 및 DomainAdmin은 CceService와 동일한 암호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-171">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="d300b-172">1단계에서 반환된 DomainAdmin, VMAdmin 및 CceService 암호가 다른 경우 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-172">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
  
1. <span data-ttu-id="d300b-173">다음과 Set-CcCredential -AccountType DomainAdmin을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-173">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="d300b-174">이전 계정 자격 증명을 입력하라는 메시지가 표시될 때 CceService 암호에 사용한 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-174">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="d300b-175">새 계정 자격 증명을 입력하라는 메시지가 표시될 때 1단계에서 반환된 DomainAdmin 암호의 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-175">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
2. <span data-ttu-id="d300b-176">다음과 Set-CcCredential -AccountType VmAdmin을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-176">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="d300b-177">이전 계정 자격 증명을 입력하라는 메시지가 표시될 때 CceService 암호에 사용한 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-177">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="d300b-178">새 계정 자격 증명을 입력하라는 메시지가 표시될 때 1단계에서 반환된 VmAdmin 암호의 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-178">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
## <a name="update-the-password-for-the-cceservice-account"></a><span data-ttu-id="d300b-179">CceService 계정의 암호 업데이트</span><span class="sxs-lookup"><span data-stu-id="d300b-179">Update the password for the CceService account</span></span>
<span data-ttu-id="d300b-180"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="d300b-180"><a name="BKMK_UpdatePassword"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="d300b-181">이 섹션은 클라우드 커넥터 버전 2.0.1 이상에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-181">This section is applicable to Cloud Connector version 2.0.1 and later.</span></span> 
  
<span data-ttu-id="d300b-182">클라우드 커넥터 서비스가 클라우드 커넥터 관리 서비스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-182">The Cloud Connector service runs the Cloud Connector Management service.</span></span> <span data-ttu-id="d300b-183">CceService 계정은 Cloud Connector Edition 배포 중에 만들어지며 "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml" 및 "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span><span class="sxs-lookup"><span data-stu-id="d300b-183">The CceService account is created during the Cloud Connector Edition deployment and stored in the following files: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" and "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".</span></span>
  
<span data-ttu-id="d300b-184">모든 어플라이언스가 사이트 디렉터리 공유에 액세스할 수 있도록 CceService 계정의 암호는 사이트 내에 배포된 모든 어플라이언스에서 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-184">To ensure that all appliances can access the site directory share, the password for the CceService account must be the same on all appliances deployed within the site.</span></span> <span data-ttu-id="d300b-185">다음 사항에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-185">Keep the following in mind:</span></span>
  
- <span data-ttu-id="d300b-186">기본적으로 CceService 계정은 "암호가 만료되지 않습니다."로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-186">By default, the CceService account is configured as "Password never expires".</span></span> <span data-ttu-id="d300b-187">암호를 업데이트할 때 이 구성을 유지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-187">When you update the password, Microsoft recommends keeping this configuration.</span></span>
    
- <span data-ttu-id="d300b-188">사용량이 많은 기간에는 암호를 업데이트해야 합니다. 비트 또는 Windows 업데이트의 경우 자동 업데이트 기간을 밖으로 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-188">You should update the password during non-peak usage periods and outside of automatic update time windows for bits or Windows updates.</span></span> <span data-ttu-id="d300b-189">암호를 업데이트할 때 어플라이언스를 드레인했다가 다시 시작해야 합니다. 이 경우 시간이 오래 걸리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-189">When you update the password, the appliance needs to be drained and restarted, which takes some time.</span></span> <span data-ttu-id="d300b-190">어플라이언스를 다시 시작하면 자동 업데이트 작업이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-190">Restarting the appliance will interrupt automatic update operations.</span></span> 
    
- <span data-ttu-id="d300b-191">CceService 계정 암호를 변경하는 경우 모든 자격 증명을 지정하고 로컬에 저장된 파일에서 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-191">When you change the CceService account password, you will need to specify all the credentials and update them in the locally stored file.</span></span> 
    
<span data-ttu-id="d300b-192">동일한 PSTN 사이트에 속하는 각 어플라이언스에 대해 다음을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-192">For each appliance that belongs to the same PSTN site, you will need to specify the following:</span></span> 
  
1. <span data-ttu-id="d300b-193">다음 명령을 실행하여 나중에 사용할 계정 이름 및 암호를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-193">Run the following commands to retrieve the account names and passwords that you will use later:</span></span>
    
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

2. <span data-ttu-id="d300b-194">Enter-CcUpdate cmdlet을 실행하여 어플라이언스를 드레인하고 수동 유지 관리 모드로 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-194">Run the Enter-CcUpdate cmdlet to drain the appliance and move it into manual maintenance mode.</span></span>
    
3. <span data-ttu-id="d300b-195">호스트 서버에서 CceService 계정의 암호를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-195">Update the password of the CceService account on the host server.</span></span>
    
4. <span data-ttu-id="d300b-196">호스트 서버를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-196">Restart the host server.</span></span>
    
5. <span data-ttu-id="d300b-197">Restore-CcCredentials cmdlet을 실행하여 설명 다음에 암호를 다시 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-197">Run the Restore-CcCredentials cmdlet to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="d300b-198">CceService 계정을 제외하고 클라우드 커넥터 배포 전에 입력한 암호를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-198">Be sure you enter the same password you entered before for the Cloud Connector deployment except for the CceService account.</span></span> <span data-ttu-id="d300b-199">CceService 계정의 경우 새 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-199">For the CceService account, enter your new password.</span></span> <span data-ttu-id="d300b-200">CceService 계정의 새 암호가 PSTN 사이트의 모든 어플라이언스에 대해 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-200">Be sure the new password for the CceService account is the same for all appliances in the PSTN site.</span></span>
    
6. <span data-ttu-id="d300b-201">기본적으로 VmAdmin 및 DomainAdmin은 CceService와 동일한 암호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-201">By default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="d300b-202">1단계에서 반환된 DomainAdmin, VMAdmin 및 CceService 암호가 다른 경우 다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-202">If the DomainAdmin, VMAdmin, and CceService passwords returned in step 1 are different, you must perform the following steps:</span></span>
    
7. <span data-ttu-id="d300b-203">다음과 Set-CcCredential -AccountType DomainAdmin을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-203">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
   - <span data-ttu-id="d300b-204">이전 계정 자격 증명을 입력하라는 메시지가 표시될 때 CceService 암호에 사용한 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-204">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="d300b-205">새 계정 자격 증명을 입력하라는 메시지가 표시될 때 1단계에서 반환된 DomainAdmin 암호의 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-205">When prompted for the new account credential, enter the password for the DomainAdmin password returned in step 1.</span></span>
    
8. <span data-ttu-id="d300b-206">다음과 Set-CcCredential -AccountType VmAdmin을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-206">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
   - <span data-ttu-id="d300b-207">이전 계정 자격 증명을 입력하라는 메시지가 표시될 때 CceService 암호에 사용한 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-207">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
   - <span data-ttu-id="d300b-208">새 계정 자격 증명을 입력하라는 메시지가 표시될 때 1단계에서 반환된 VmAdmin 암호의 암호를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-208">When prompted for the new account credential, enter the password for the VmAdmin password returned in step 1.</span></span> 
    
9. <span data-ttu-id="d300b-209">이 Exit-CcUpdate cmdlet을 실행하여 수동 유지 관리 모드에서 어플라이언스를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-209">Run the Exit-CcUpdate cmdlet to move the appliance out of manual maintenance mode.</span></span>
    
10. <span data-ttu-id="d300b-210">동일한 PSTN 사이트의 모든 어플라이언스에서 이러한 단계를 완료한 후 사이트 루트 디렉터리에서 다음 파일을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-210">After you complete these steps on all appliances in the same PSTN site, delete the following files in the site root directory:</span></span>
    
    - <span data-ttu-id="d300b-211">CcLockFile</span><span class="sxs-lookup"><span data-stu-id="d300b-211">CcLockFile</span></span>
    
    - <span data-ttu-id="d300b-212">Site_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="d300b-212">Site_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="d300b-213">Tenant_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="d300b-213">Tenant_\<Edge External Sip Pool fqdn\></span></span>
    
    - <span data-ttu-id="d300b-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span><span class="sxs-lookup"><span data-stu-id="d300b-214">TenantConfigLock_\<Edge External Sip Pool fqdn\></span></span>
    
## <a name="add-a-new-sip-domain"></a><span data-ttu-id="d300b-215">새 SIP 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="d300b-215">Add a new SIP domain</span></span>
<span data-ttu-id="d300b-216"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="d300b-216"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="d300b-217">기존 클라우드 커넥터 배포에 새 SIP 도메인(또는 여러 SIP 도메인)을 추가하려면 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-217">To add a new SIP domain (or multiple SIP domains) to your existing Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="d300b-218">Microsoft 365 또는 Office 365에서 도메인을 업데이트하는 단계를 완료하고 DNS 레코드를 추가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-218">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="d300b-219">Microsoft 365 또는 Office 365에서 도메인을 설정하는 방법에 대한 자세한 내용은 [Microsoft 365 또는 Office 365에](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)도메인 추가를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d300b-219">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="d300b-220">클라우드 커넥터 구성 파일을 새 SIP 도메인 또는 도메인으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-220">Update the Cloud Connector configuration file with the new SIP domain or domains.</span></span>
    
3. <span data-ttu-id="d300b-221">클라우드 커넥터 구성에 정의된 각 SIP 도메인에 대해 sip.domain에 대한 추가 SAN 이름을 사용하여 새 에지 외부 인증서를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-221">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="d300b-222">새 에지 외부 인증서의 경로를 다음과 같이 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="d300b-222">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="d300b-223">지침에 따라 단일 사이트의 구성을 [수정하거나](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) 여러 사이트의 [구성을 수정합니다.](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)</span><span class="sxs-lookup"><span data-stu-id="d300b-223">Follow the instructions to [Modify the configuration of a single site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) or [Modify the configuration of multiple sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).</span></span>
    
## <a name="modify-the-primary-sip-domain"></a><span data-ttu-id="d300b-224">기본 SIP 도메인 수정</span><span class="sxs-lookup"><span data-stu-id="d300b-224">Modify the primary SIP domain</span></span>
<span data-ttu-id="d300b-225"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="d300b-225"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="d300b-226">클라우드 커넥터 배포에서 기본 SIP 도메인을 변경해야 하는 경우 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-226">If you need to change the primary SIP domain in your Cloud Connector deployment, do the following:</span></span>
  
1. <span data-ttu-id="d300b-227">Microsoft 365 또는 Office 365에서 도메인을 업데이트하는 단계를 완료하고 DNS 레코드를 추가할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-227">Make sure you've completed the steps to update your domain in Microsoft 365 or Office 365 and have the ability to add DNS records.</span></span> <span data-ttu-id="d300b-228">Microsoft 365 또는 Office 365에서 도메인을 설정하는 방법에 대한 자세한 내용은 [Microsoft 365 또는 Office 365에](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)도메인 추가를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d300b-228">For more information about how to set up your domain in Microsoft 365 or Office 365, see [Add a domain to Microsoft 365 or Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).</span></span>
    
2. <span data-ttu-id="d300b-229">클라우드 커넥터 구성 파일을 새 SIP 도메인으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-229">Update the Cloud Connector configuration file with the new SIP domain.</span></span>
    
3. <span data-ttu-id="d300b-230">클라우드 커넥터 구성에 정의된 각 SIP 도메인에 대해 sip.domain에 대한 추가 SAN 이름을 사용하여 새 에지 외부 인증서를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-230">Request a new Edge external certificate with additional SAN names for sip.domain for each SIP domain defined in your Cloud Connector configuration.</span></span> 
    
4. <span data-ttu-id="d300b-231">새 에지 외부 인증서의 경로를 다음과 같이 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="d300b-231">Set the path for the new Edge external certificate as follows:</span></span>
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    <span data-ttu-id="d300b-232">클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행하여 사이트의 각 어플라이언스에 대한 테넌트 등록을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-232">Remove the tenant registration for each appliance in a site by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    <span data-ttu-id="d300b-233">비즈니스용 Skype Online PowerShell에서 다음 cmdlet을 실행하여 각 사이트에 대한 사이트 등록을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-233">Remove the site registration for each site by running the following cmdlet in Skype for Business Online PowerShell:</span></span>
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    <span data-ttu-id="d300b-234">클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행하여 각 어플라이언스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-234">Uninstall each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     <span data-ttu-id="d300b-235">클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행하여 각 어플라이언스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-235">Register each appliance by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     <span data-ttu-id="d300b-236">클라우드 커넥터의 관리자 PowerShell에서 다음 cmdlet을 실행하여 각 어플라이언스를 하나씩 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-236">Install each appliance, one by one, by running the following cmdlet in administrator PowerShell on Cloud Connector:</span></span>
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a><span data-ttu-id="d300b-237">외부 에지 인증서를 새 인증서로 바꾸기</span><span class="sxs-lookup"><span data-stu-id="d300b-237">Replace the external Edge certificate with a new certificate</span></span>
<span data-ttu-id="d300b-238"><a name="BKMK_UpdatePassword"> </a></span><span class="sxs-lookup"><span data-stu-id="d300b-238"><a name="BKMK_UpdatePassword"> </a></span></span>

<span data-ttu-id="d300b-239">클라우드 커넥터 어플라이언스에서 외부 에지 인증서를 교체해야 하는 경우 새 에지 인증서를 얻어 개인 키 및 전체 인증서 체인이 포함된 PFX 파일을 준비한 다음 각 어플라이언스에서 다음을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-239">When you need to replace the external Edge certificate on your Cloud Connector appliances, you will need to obtain a new Edge certificate, prepare the PFX file containing the Private Key and full certificate chain, and then do the following on each appliance:</span></span>
  
1. <span data-ttu-id="d300b-240">이 cmdlet을 사용하여 어플라이언스를 유지 관리 Enter-CcUpdate 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-240">Put the appliance in maintenance mode by using the Enter-CcUpdate cmdlet.</span></span>
    
2. <span data-ttu-id="d300b-241">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-241">Run the following command:</span></span> 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    <span data-ttu-id="d300b-242">새 인증서의 암호가 이전 인증서와 같을 경우 가져오기에 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-242">If the password of the new certificate is the same as the old, the import will be successful.</span></span> <span data-ttu-id="d300b-243">암호가 다른 경우 암호가 잘못했다는 오류가 표시되고 -Local 매개 변수를 사용하여 Register-CcAppliance cmdlet을 실행한 다음 2단계를 반복하여 암호를 다시 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-243">If the password is different, you will receive an error that the password is wrong, and you will need to reset the password by running the Register-CcAppliance cmdlet with the -Local parameter, and then repeating step 2.</span></span> 
    
4. <span data-ttu-id="d300b-244">Exit -CcUpdate cmdlet을 사용하여 어플라이언스를 유지 관리 모드에서 퇴장합니다.</span><span class="sxs-lookup"><span data-stu-id="d300b-244">Take the appliance out of maintenance mode by using the Exit -CcUpdate cmdlet.</span></span>
    

