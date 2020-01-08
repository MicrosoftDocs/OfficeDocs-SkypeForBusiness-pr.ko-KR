---
title: Microsoft를 오디오 회의 공급자로 지정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d935a90d-ea61-433d-a820-b400ed9c1f5d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 비즈니스용 Skype에 대 한 전화 접속 회의 공급자를 Microsoft에 할당 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: deaafe36948a6fe3a7eb9eaaf49295c37f627595
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962736"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="7cdeb-103">Microsoft를 오디오 회의 공급자로 지정</span><span class="sxs-lookup"><span data-stu-id="7cdeb-103">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="7cdeb-104">Office 365에서 비즈니스용 Skype 및 Microsoft 팀과 오디오 회의를 사용 하려면 조직의 사용자가 오디오 회의 라이선스를 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-104">To use Audio Conferencing in Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="7cdeb-105">라이선스에 대 한 자세한 내용과 비용을 얻으려면 [Office 365에서 오디오 회의 체험 또는 구입](try-or-purchase-audio-conferencing-in-office-365.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-105">See [Try or purchase Audio Conferencing in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="7cdeb-106">Microsoft 오디오 회의는 모임 참가자가 조직의 모임에 참가할 때 사용할 수 있는 전화 접속 전화 번호, Pin 및 전화 회의 Id를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="7cdeb-107">비즈니스용 Skype 또는 Microsoft 팀 모임을 예약 하거나 리드 하는 사용자에 게 Microsoft를 오디오 회의 공급자로 지정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="7cdeb-108">Microsoft를 오디오 회의 공급자로 지정</span><span class="sxs-lookup"><span data-stu-id="7cdeb-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="an-icon-showing-the-skype-for-business-logoimagessfb-logo-30x30png-using-the-skype-for-business-admin-center"></a>![비즈니스용 Skype 로고를 표시 하는 아이콘](../images/sfb-logo-30x30.png) <span data-ttu-id="7cdeb-110">비즈니스용 Skype 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="7cdeb-110">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="7cdeb-111">**Microsoft 팀 관리 센터** > **레거시 포털로**이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-111">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
2. <span data-ttu-id="7cdeb-112">**비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="7cdeb-113">**오디오 회의** 라이선스를 할당 했지만 오디오 회의 공급자로 Microsoft가 설정 되지 않았음을 알리는 배너가 표시 되는 경우 **여기를 클릭 하 여 이동**합니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="7cdeb-114">배너가 표시 되지 않는 경우 **비즈니스용 Skype 관리 센터** 에서 **사용자**를 클릭 한 다음 **오디오 회의 필터로 이동할 사용자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="7cdeb-115">사용자의 속성 페이지에서 **공급자 이름**아래의 드롭다운 목록에서 **Microsoft** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-115">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7cdeb-116">오디오 회의 공급자로 Microsoft를 사용 하 고 있으며 여러 개의 전화 번호가 있으므로 **기본 유료 번호** 드롭다운 목록을 사용 하 여 사용자의 기본 오디오 번호를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-116">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="7cdeb-117">**저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-117">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="7cdeb-118">적은 수의 사용자를 위해 Windows PowerShell 스크립트 사용</span><span class="sxs-lookup"><span data-stu-id="7cdeb-118">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="7cdeb-119">시간을 절약 하거나이를 자동화 하려면 다음 PowerShell 스크립트를 사용 하 여 Microsoft를 적은 수의 사용자에 대 한 오디오 회의 공급자로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-119">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="7cdeb-120">공급자가 다른 공급자에서 **Microsoft**로 변경 되 면 사용자에 대 한 오디오 회의 정보 (컨퍼런스 ID, 유료 및 무료 번호)가 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-120">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="7cdeb-121">공급자를 변경 하기 전에이 정보를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-121">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="7cdeb-122">소수의 사용자에 대해 공급자를 Microsoft로 변경 하려면 [Enable-get-csonlinedialinconferencinguser](https://technet.microsoft.com/library/mt243813.aspx) cmdlet을 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-122">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](https://technet.microsoft.com/library/mt243813.aspx) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="7cdeb-123">많은 수의 사용자를 위해 Windows PowerShell 스크립트 사용</span><span class="sxs-lookup"><span data-stu-id="7cdeb-123">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="7cdeb-124">시간을 절약 하거나이를 자동화 하려면 다음 PowerShell 스크립트를 사용 하 여 Microsoft를 다 수의 사용자를 위한 오디오 회의 공급자로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="7cdeb-125">공급자가 다른 공급자에서 **Microsoft**로 변경 되 면 사용자에 대 한 오디오 회의 정보 (컨퍼런스 ID, 유료 및 무료 번호)가 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-125">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="7cdeb-126">공급자를 변경 하기 전에이 정보를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-126">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="7cdeb-127">다음 스크립트를 PowerShell 스크립트 파일로 저장 한 다음 해당 입력 매개 변수를 사용 하 여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-127">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="7cdeb-128">**예제 1:** 업데이트 하려는 사용자의 목록을 제공 하 여이 스크립트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-128">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="7cdeb-129">**예제 2:** 업데이트 하려는 각 사용자의 전자 메일 주소 (별칭)를 포함 하는 .csv 파일을 제공 하 여이 스크립트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-129">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="7cdeb-130">**예제 3:** 이 예제에서는 조직의 대규모 사용자에 대해이 스크립트를 사용 하 여 오디오 회의 공급자를 상호 통화 (또는 다른 공급자)에서 **Microsoft** 로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-130">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="7cdeb-131">스크립트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-131">Here is the script:</span></span>

  ```PowerShell
  <#
  .SYNOPSIS

  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .DESCRIPTION
  This is a PowerShell script to set Microsoft as the audio conferencing provider of a set of users. It's required for applicable users to have a valid PSTN Conferencing license assigned before their provider is changed.

  .EXAMPLE
  
  ./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ./Script.ps1 -ACPProviderName ""Intercall""
  #>
  param (
  [Parameter(Mandatory = $true, ParameterSetName = "CsvFile")]
   [string]$CsvFile,
   [Parameter(Mandatory = $true, ParameterSetName = "UserList")]
   [string]$UserList,
   [Parameter(Mandatory = $true, ParameterSetName = "ACPProviderName")]
  [string]$ACPProviderName
  )
  if ($CsvFile)
  {
  if(!(Test-Path $CsvFile))
  {
  Write-Error "File does not exist."
  Exit
   }
  $users = Get-Content $CsvFile
  }
  if ($UserList)
  {
  $users = $UserList.Split(",")
  }
  if ($ACPProviderName)
  {
  $supportedACPProviders = Get-csAudioConferencingProvider
  $providerNameMatch = $supportedACPProviders | ?{$_.Identity -eq $ACPProviderName}
  if ($providerNameMatch -eq $null)
  {
  Write-Host "The provider name is not from a supported provider, please use any of the following values: "
  $supportedACPProviders      | %{$_.Identity}
  return
  }
  $allUsersInTenant = Get-csOnlineUser
  $users =  $allUsersInTenant | ?{$_.AcpInfo -ne $null -and $_.ACPInfo.Name -eq $ACPProviderName}
  }
  Write-Host "Number of users to have their audio conferencing provider set to Microsoft: " $users.count
  foreach ($user in $users)
  {
  if ($CsvFile -or $UserList)
  {
  try
  {
  $adUser = Get-csOnlineUser -Identity $user
  }
  catch
  {
  Write-Error "There was an exception while retrieving user: $user. "   $error[0].Exception.Message
  Continue
  }
  }
  else
  {
  $adUser = $user
  }
  if ($adUser -ne $null -and ($adUser.OnlineDialInConferencingPOlicy -ne $null))
  {
  if ($adUser.AcpInfo -eq $null -Or $adUser.AcpInfo.Name -ne "Microsoft")
  {
  try
  {
  $enableUser = Enable-CsOnlineDialInConferencingUser -Identity $adUser.ObjectId -Tenant $adUser.TenantId -ReplaceProvider
  Write-Host "The provider of $user has changed to Microsoft."
  $enableUser
  }
  catch
  {
  Write-Error "There was an exception while enabling user: $user. "  $error[0].Exception.Message
  continue;
  }
  }
   else
  {
  Write-Warning "The provider of $user is already set to Microsoft."
  }
  }
  else
              {
  Write-Error "$user does not have valid Audio Conferencing license assigned."
  }
  }
  ```
<span data-ttu-id="7cdeb-132">Windows PowerShell을 사용 하는 방법에 대 한 자세한 내용은 [Windows powershell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업](https://go.microsoft.com/fwlink/?LinkId=525038)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7cdeb-132">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7cdeb-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="7cdeb-133">Related topics</span></span>
<span data-ttu-id="7cdeb-134">[](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[비즈니스용 Skype Online 설정](../set-up-skype-for-business-online/set-up-skype-for-business-online.md) 또는 Office 365에서 오디오 회의 체험 또는 구매</span><span class="sxs-lookup"><span data-stu-id="7cdeb-134">[Try or purchase Audio Conferencing in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>

