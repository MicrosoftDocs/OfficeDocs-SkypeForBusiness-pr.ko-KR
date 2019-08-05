---
title: 다이얼 플랜 만들기 및 관리
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Office 365에서 통화 다이얼 플랜 (PSTN 통화 다이얼 플랜)을 만들고 관리 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 5254a2d63abeffa0b3452ed309d49272affcaf05
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "36184367"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="ecb98-103">다이얼 플랜 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="ecb98-103">Create and manage dial plans</span></span>

<span data-ttu-id="ecb98-104">조직에 대 한 다이얼 플랜을 계획 하 고 통화 라우팅에 대해 만들어야 하는 모든 정규화 규칙을 확인 한 후에는 Windows PowerShell을 사용 하 여 다이얼 플랜을 만들고 설정을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-104">After you have planned the dial plans for your organization and figured out all of the normalization rules that need to be created for call routing, you will need to use Windows PowerShell to create the dial plans and make any setting changes.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ecb98-105">비즈니스용 Skype 관리 센터를 사용 하 여 다이얼 플랜을 만들고 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-105">The Skype for Business admin center can't be used for creating and managing dial plans.</span></span> 
  
## <a name="verifying-and-starting-remote-powershell"></a><span data-ttu-id="ecb98-106">원격 PowerShell 확인 및 시작</span><span class="sxs-lookup"><span data-stu-id="ecb98-106">Verifying and starting Remote PowerShell</span></span>

 <span data-ttu-id="ecb98-107">**Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**</span><span class="sxs-lookup"><span data-stu-id="ecb98-107">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="ecb98-108">버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-108">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ecb98-109">**Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-109">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="ecb98-110">버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-110">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="ecb98-111">Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-111">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="ecb98-112">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-112">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="ecb98-113">비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-113">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="ecb98-114">이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-114">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="ecb98-115">메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-115">Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="ecb98-116">자세한 정보를 알고 싶은 경우 [모든 Office 365 서비스에 단일 Windows PowerShell 창으로 연결](https://technet.microsoft.com/EN-US/library/dn568015.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ecb98-116">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="ecb98-117">**Windows PowerShell 세션 시작**</span><span class="sxs-lookup"><span data-stu-id="ecb98-117">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="ecb98-118">**시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ecb98-119">**Windows PowerShell** 창에서 다음을 실행 하 여 Office 365 조직에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-119">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ecb98-120">비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-120">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
>   ```
>     Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>     $credential = Get-Credential
>     $session = New-CsOnlineSession -Credential $credential
>     Import-PSSession $session
>   ```

<span data-ttu-id="ecb98-121">Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://technet.microsoft.com/EN-US/library/dn568015.aspx) 또는 [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online에](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)연결을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ecb98-121">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="creating-and-managing-your-dial-plans"></a><span data-ttu-id="ecb98-122">다이얼 플랜 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="ecb98-122">Creating and managing your dial plans</span></span>

<span data-ttu-id="ecb98-123">단일 cmdlet 또는 PowerShell 스크립트를 사용 하 여 테 넌 트 다이얼 플랜을 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-123">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
### <a name="using-single-cmdlets"></a><span data-ttu-id="ecb98-124">단일 cmdlet 사용</span><span class="sxs-lookup"><span data-stu-id="ecb98-124">Using single cmdlets</span></span>

- <span data-ttu-id="ecb98-125">새 다이얼 플랜을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-125">To create a new dial plan, run:</span></span>
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="ecb98-126">다른 예제 및 매개 변수는 [New-Csten앤틸리스 다이얼 플랜](https://technet.microsoft.com/library/mt775026.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ecb98-126">For other examples and parameters, see [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).</span></span>
    
- <span data-ttu-id="ecb98-127">기존 다이얼 플랜에 대 한 설정을 변경 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-127">To make setting changes to an existing dial plan, run:</span></span>
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="ecb98-128">다른 예제 및 매개 변수는 [Set-Csten앤틸리스 다이얼 플랜](https://technet.microsoft.com/library/mt775023.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ecb98-128">For other examples and parameters, see [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).</span></span>
    
- <span data-ttu-id="ecb98-129">다이얼 플랜에 사용자를 추가 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-129">To add users to a dial plan, run:</span></span>
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="ecb98-130">다른 예제 및 매개 변수는 [-Csten앤틸리스 다이얼 플랜](https://technet.microsoft.com/library/mt775021.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ecb98-130">For other examples and parameters, see [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).</span></span>
    
- <span data-ttu-id="ecb98-131">다이얼 플랜에 대 한 설정을 보려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-131">To view the settings on a dial plan, run:</span></span>
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="ecb98-132">다른 예제 및 매개 변수는 [Get-Csten앤틸리스 다이얼 플랜](https://technet.microsoft.com/library/mt775024.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ecb98-132">For other examples and parameters, see [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).</span></span>
    
- <span data-ttu-id="ecb98-133">다이얼 플랜을 삭제 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-133">To delete a dial plan, run:</span></span>
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="ecb98-134">다른 예제 및 매개 변수는 [제거-Csten앤틸리스 다이얼 플랜](https://technet.microsoft.com/library/mt775020.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ecb98-134">For other examples and parameters, see [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).</span></span>
    
- <span data-ttu-id="ecb98-135">유효 다이얼 플랜의 설정을 보려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-135">To see the settings of the effective dial plan, run:</span></span>
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="ecb98-136">다른 예제 및 매개 변수는 [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ecb98-136">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).</span></span>
    
- <span data-ttu-id="ecb98-137">다이얼 플랜의 유효 설정을 테스트 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-137">To test the effective settings of a dial plan, run:</span></span>
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    <span data-ttu-id="ecb98-138">다른 예제 및 매개 변수는 [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ecb98-138">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).</span></span>
    
### <a name="using-a-powershell-script"></a><span data-ttu-id="ecb98-139">PowerShell 스크립트 사용</span><span class="sxs-lookup"><span data-stu-id="ecb98-139">Using a PowerShell script</span></span>

<span data-ttu-id="ecb98-140">이 작업을 실행 하 여 테 넌 트 다이얼 플랜을 먼저 삭제할 필요 없이 테 넌 트 다이얼 플랜에 연결 된 정규화 규칙을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-140">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to deleting the tenant dial plan first:</span></span>
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="ecb98-141">이를 실행 하 여 RedmondDialPlan 이라는 기존 테 넌 트 다이얼 플랜에 다음 정규화 규칙을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-141">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="ecb98-142">이를 실행 하 여 RedmondDialPlan 이라는 기존 테 넌 트 다이얼 플랜에서 다음 정규화 규칙을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-142">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="ecb98-143">다음을 실행 하 여 기존 정규화 규칙을 검사 하 고 삭제 하려는 항목을 결정 한 다음 인덱스를 사용 하 여 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-143">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="ecb98-144">정규화 규칙 배열은 index 0부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-144">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="ecb98-145">3 자리 정규화 규칙을 제거 하 여 인덱스 1을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-145">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[Number 1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="ecb98-146">이를 실행 하 여 RedmondDialPlan 테 넌 트 다이얼 플랜을 부여한 모든 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-146">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="ecb98-147">이를 실행 하 여 HostingProvider sipfed.online.lync.com 인 모든 사용자의 policyname를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-147">Run this to delete policyname for all users who have HostingProvider sipfed.online.lync.com.</span></span>
```
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="ecb98-148">OPDP1 라는 기존 온-프레미스 다이얼 플랜을 조직의 테 넌 트 다이얼 플랜으로 추가 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-148">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="ecb98-149">먼저 .xml 파일에 온-프레미스 다이얼 플랜을 저장 한 다음이를 사용 하 여 새 테 넌 트 다이얼 플랜을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-149">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="ecb98-150">이를 실행 하 여 온-프레미스 다이얼 플랜을 .xml 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-150">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="ecb98-151">새 테 넌 트 다이얼 플랜을 만들려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-151">Run this to create the new tenant dial plan.</span></span>
  
```
$DPFileName = "dialplan.xml"
$DP = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" +$nr.Name
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
$NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ecb98-152">Windows Powershell에 대 한 자세한 정보를 확인 하 고 싶으신가요?</span><span class="sxs-lookup"><span data-stu-id="ecb98-152">Want to know more about Windows Powershell?</span></span>

- <span data-ttu-id="ecb98-153">Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ecb98-154">Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-154">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="ecb98-155">Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ecb98-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ecb98-156">Windows PowerShell 및 Lync Online 소개</span><span class="sxs-lookup"><span data-stu-id="ecb98-156">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ecb98-157">Office 365 PowerShell을 사용 해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="ecb98-157">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="ecb98-158">Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecb98-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ecb98-159">다음 항목에서 이러한 이점에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="ecb98-159">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="ecb98-160">Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법</span><span class="sxs-lookup"><span data-stu-id="ecb98-160">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="ecb98-161">Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리</span><span class="sxs-lookup"><span data-stu-id="ecb98-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ecb98-162">Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행</span><span class="sxs-lookup"><span data-stu-id="ecb98-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="ecb98-163">관련 항목</span><span class="sxs-lookup"><span data-stu-id="ecb98-163">Related topics</span></span>
[<span data-ttu-id="ecb98-164">전화 번호 전송 일반적인 질문</span><span class="sxs-lookup"><span data-stu-id="ecb98-164">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="ecb98-165">통화 요금제에 사용 되는 다른 종류의 전화 번호</span><span class="sxs-lookup"><span data-stu-id="ecb98-165">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="ecb98-166">조직의 전화 번호 관리</span><span class="sxs-lookup"><span data-stu-id="ecb98-166">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="ecb98-167">비상 통화 약관</span><span class="sxs-lookup"><span data-stu-id="ecb98-167">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

<span data-ttu-id="ecb98-168">[비즈니스용 Skype Online: 비상 전화 부인 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="ecb98-168">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
