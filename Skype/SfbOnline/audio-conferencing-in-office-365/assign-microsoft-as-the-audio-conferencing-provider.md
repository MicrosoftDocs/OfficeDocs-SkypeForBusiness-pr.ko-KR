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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 비즈니스용 Skype에 대한 전화 접속 회의 공급자를 Microsoft에 할당하는 방법을 알아보습니다.
ms.openlocfilehash: b0276b0f5ed50e3c287bc872de45d6c1c4c69157
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110044"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="79153-103">Microsoft를 오디오 회의 공급자로 지정</span><span class="sxs-lookup"><span data-stu-id="79153-103">Assign Microsoft as the audio conferencing provider</span></span>

<span data-ttu-id="79153-104">Microsoft 365 또는 비즈니스용 Skype 및 Microsoft Teams에서 Office 365에서 오디오 회의를 사용하려면 조직의 사용자가 해당 사용자에게 오디오 회의 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79153-104">To use Audio Conferencing in Microsoft 365 or Office 365 with Skype for Business and Microsoft Teams, users in your organization need to have an Audio Conferencing license assigned to them.</span></span> <span data-ttu-id="79153-105">라이선스 및 비용에 대한 자세한 내용은 [Microsoft 365 또는 Office 365에서](try-or-purchase-audio-conferencing-in-office-365.md) 오디오 회의 시도 또는 구입을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79153-105">See [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365.md) to get more information on licensing and how much it costs.</span></span>

<span data-ttu-id="79153-106">Microsoft Audio Conferencing은 모임 참가자가 조직의 모임에 참가하는 데 사용할 수 있는 전화 접속 전화 번호, PINS 및 회의 아이디를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79153-106">Microsoft Audio Conferencing supplies dial-in phone numbers, PINs, and conference IDs that can be used by meeting participants to join the meetings of your organization.</span></span> <span data-ttu-id="79153-107">비즈니스용 Skype 또는 Microsoft Teams 모임을 예약하거나 이끌 사용자에게 오디오 회의 공급자로 Microsoft를 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79153-107">You only need to assign Microsoft as the audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a><span data-ttu-id="79153-108">Microsoft를 오디오 회의 공급자로 지정</span><span class="sxs-lookup"><span data-stu-id="79153-108">Assign Microsoft as the audio conferencing provider</span></span>

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![비즈니스용 Skype 로고가 표시된 아이콘](../images/sfb-logo-30x30.png) <span data-ttu-id="79153-110">비즈니스용 Skype 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="79153-110">Using the Skype for Business admin center</span></span>

1. <span data-ttu-id="79153-111">**Microsoft Teams** 관리 센터  >  **레거시 포털로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="79153-111">Go to the **Microsoft Teams admin center** > **Legacy portal**.</span></span>
    
2. <span data-ttu-id="79153-112">비즈니스용 Skype 관리 **센터** 의 왼쪽 탐색에서 오디오 회의 **으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="79153-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="79153-113">오디오 회의 라이선스가 할당되어 있지만 Microsoft가  아직 오디오 회의 공급자로 설정되지 않은 사용자에게 알리는 배너가 표시되어 있는 경우 여기를 클릭하여 **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="79153-113">If you see a banner notifying you that there are users who have an **Audio Conferencing** license assigned but don't have Microsoft set as their audio conferencing provider yet, click **Click here to move them**.</span></span> <span data-ttu-id="79153-114">배너가 표시되지 않는 경우 비즈니스용 Skype 관리  **센터에서** 사용자를 클릭한 다음 오디오 회의 필터로 이동할 준비가 된 사용자를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="79153-114">If you don't see the banner, in the **Skype for Business admin center** click **Users**, and then select the **Users ready to be moved to Audio Conferencing** filter.</span></span>
    
4. <span data-ttu-id="79153-115">사용자의 속성 페이지에서 공급자 **이름** 아래에서 **드롭다운** 목록에서 Microsoft를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="79153-115">On the properties page for the user, under **Provider name**, select **Microsoft** in the drop-down list.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="79153-116">Microsoft를 오디오 회의 공급자로 사용하고 있으며 전화 번호가 여러 개 있기  때문에 기본 전화 번호 드롭다운 목록을 사용하여 사용자의 기본 오디오 번호를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79153-116">Because you are using Microsoft as the audio conferencing provider and there are multiple phone numbers, you can use the **Default toll number** drop-down list to select a default audio number for the user.</span></span>
  
5. <span data-ttu-id="79153-117">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="79153-117">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a><span data-ttu-id="79153-118">소수의 Windows PowerShell 스크립트 사용</span><span class="sxs-lookup"><span data-stu-id="79153-118">Using a Windows PowerShell script for a small number of users</span></span>

<span data-ttu-id="79153-119">시간을 절약하거나 자동화하기 위해 다음 PowerShell 스크립트를 사용하여 Microsoft를 소수의 사용자에 대한 오디오 회의 공급자로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79153-119">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a small number of users.</span></span>

> [!NOTE]
> <span data-ttu-id="79153-120">공급자가 다른 공급자에서 **Microsoft로** 변경된 경우 사용자에 대한 오디오 회의 정보(컨퍼런스 ID, 무료 전화 번호 및 무료 전화 번호)가 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="79153-120">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="79153-121">공급자를 변경하기 전에 이 정보를 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79153-121">You should save this information before changing the provider.</span></span> 

  
<span data-ttu-id="79153-122">공급자를 소수의 사용자에 대해 Microsoft로 변경하려면  [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79153-122">To change the provider to Microsoft for a small number of users, you can use the  [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) cmdlet.</span></span>
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a><span data-ttu-id="79153-123">많은 Windows PowerShell 스크립트 사용</span><span class="sxs-lookup"><span data-stu-id="79153-123">Using a Windows PowerShell script for a large number of users</span></span>
<span data-ttu-id="79153-124">시간을 절약하거나 자동화하기 위해 다음 PowerShell 스크립트를 사용하여 Microsoft를 많은 수의 사용자에 대한 오디오 회의 공급자로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79153-124">To save time or automate this, you can use the following PowerShell script to set Microsoft as the audio conferencing provider for a large number of users.</span></span>

<span data-ttu-id="79153-125">공급자가 다른 공급자에서 **Microsoft로** 변경된 경우 사용자에 대한 오디오 회의 정보(컨퍼런스 ID, 무료 전화 번호 및 무료 전화 번호)가 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="79153-125">When the provider is changed from another provider to **Microsoft**, the audio conferencing information for the user (Conference ID, Toll and Toll-free numbers) will be replaced.</span></span> <span data-ttu-id="79153-126">공급자를 변경하기 전에 이 정보를 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79153-126">You should save this information before changing the provider.</span></span> 
  
<span data-ttu-id="79153-127">다음 스크립트를 PowerShell 스크립트 파일로 저장한 다음 입력 매개 변수를 사용하여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79153-127">You can save the following script as a PowerShell script file and then run it using any of its input parameters.</span></span>

<span data-ttu-id="79153-128">**예제 1:** 업데이트할 사용자 목록을 제공하여 이 스크립트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79153-128">**Example 1:** You can run this script by providing a list of users that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

<span data-ttu-id="79153-129">**예제 2:** 업데이트하려는 각 사용자의 전자 메일 주소(별칭)를 포함하는 .csv 파일을 제공하여 이 스크립트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79153-129">**Example 2:** You can run this script by providing a .csv file that contains the email address (alias) of each user that you want updated.</span></span>
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

<span data-ttu-id="79153-130">**예제 3:** 이 예제에서는 이 스크립트를 사용하여 조직의 많은 수의 사용자를 위해 오디오 회의 공급자를 Intercall(또는 다른 공급자)에서 **Microsoft로** 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79153-130">**Example 3:** In this example, you can use this script to change the audio conferencing provider from Intercall (or another provider) to **Microsoft** for a large number users in your organization.</span></span>
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  <span data-ttu-id="79153-131">스크립트는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="79153-131">Here is the script:</span></span>

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
<span data-ttu-id="79153-132">웹 사이트 사용에 대한 Windows PowerShell 자세한 내용은 비즈니스용 Windows PowerShell Skype Online 관리 작업을 수행하는 방법을 [참조하세요.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="79153-132">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="79153-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="79153-133">Related topics</span></span>
<span data-ttu-id="79153-134">[Microsoft 365 또는 Office 365에서](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 오디오 회의 시도 또는 구매 
 [비즈니스용 Skype Online 설정](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="79153-134">[Try or purchase Audio Conferencing in Microsoft 365 or Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[Set up Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)</span></span>