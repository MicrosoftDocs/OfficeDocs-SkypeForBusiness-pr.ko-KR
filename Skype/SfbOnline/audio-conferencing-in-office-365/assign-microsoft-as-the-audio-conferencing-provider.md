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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Microsoft에 전화 접속 회의 공급자를 할당하는 방법을 비즈니스용 Skype.
ms.openlocfilehash: 360d580b57ca9528eddf96d80b773c04c71c361b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727717"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Microsoft를 오디오 회의 공급자로 지정

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

오디오 회의를 Microsoft 365 Office 365 Office 365 비즈니스용 Skype Microsoft Teams 조직의 사용자에게 오디오 회의 라이선스가 할당되어야 합니다. 라이선스 [](try-or-purchase-audio-conferencing-in-office-365.md) 및 비용에 대한 자세한 내용은 Microsoft 365 또는 Office 365 오디오 회의 시도 또는 구매를 참조하세요.

Microsoft Audio Conferencing은 모임 참가자가 조직의 모임에 참가하는 데 사용할 수 있는 전화 접속 전화 번호, PINS 및 회의 아이디를 제공합니다. Microsoft를 오디오 회의 공급자로 할당하면 모임을 예약하거나 모임을 예약하거나 이끌 비즈니스용 Skype Microsoft Teams 합니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Microsoft를 오디오 회의 공급자로 지정

### <a name="an-icon-showing-the-skype-for-business-logo-using-the-skype-for-business-admin-center"></a>![로고가 비즈니스용 Skype 아이콘입니다.](../images/sfb-logo-30x30.png) 관리 비즈니스용 Skype 사용

1. 관리 센터 **Microsoft Teams**  >  **포털로 이동하세요.**
    
2. 관리 **비즈니스용 Skype** 왼쪽 탐색에서 오디오 회의 **으로 이동하세요.**
    
3. 오디오 회의 라이선스가 할당되어 있지만 Microsoft가  아직 오디오 회의 공급자로 설정되지 않은 사용자에게 알리는 배너가 표시되어 있는 경우 여기를 클릭하여 **이동합니다.** 배너가 표시되지 않는 경우 관리자 비즈니스용 Skype 센터에서 사용자를 클릭한 다음 오디오 회의 필터로 이동할 준비가 **된** 사용자를 **선택합니다.**
    
4. 사용자의 속성 페이지에서 공급자 **이름** 아래에서 **드롭다운** 목록에서 Microsoft를 선택합니다.
    
    > [!NOTE]
    > Microsoft를 오디오 회의 공급자로 사용하고 있으며 전화 번호가 여러 개 있기  때문에 기본 전화 번호 드롭다운 목록을 사용하여 사용자의 기본 오디오 번호를 선택할 수 있습니다.
  
5. **저장** 을 클릭합니다.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>소수의 Windows PowerShell 스크립트 사용

시간을 절약하거나 자동화하기 위해 다음 PowerShell 스크립트를 사용하여 Microsoft를 소수의 사용자에 대한 오디오 회의 공급자로 설정할 수 있습니다.

> [!NOTE]
> 공급자가 다른 공급자에서 **Microsoft로** 변경된 경우 사용자에 대한 오디오 회의 정보(컨퍼런스 ID, 무료 전화 번호 및 무료 전화 번호)가 대체됩니다. 공급자를 변경하기 전에 이 정보를 저장해야 합니다. 

  
공급자를 소수의 사용자에 대해 Microsoft로 변경하려면  [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/Enable-CsOnlineDialInConferencingUser) cmdlet을 사용할 수 있습니다.
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>많은 Windows PowerShell 스크립트 사용
시간을 절약하거나 자동화하기 위해 다음 PowerShell 스크립트를 사용하여 Microsoft를 많은 수의 사용자에 대한 오디오 회의 공급자로 설정할 수 있습니다.

공급자가 다른 공급자에서 **Microsoft로** 변경된 경우 사용자에 대한 오디오 회의 정보(컨퍼런스 ID, 무료 전화 번호 및 무료 전화 번호)가 대체됩니다. 공급자를 변경하기 전에 이 정보를 저장해야 합니다. 
  
다음 스크립트를 PowerShell 스크립트 파일로 저장한 다음 입력 매개 변수를 사용하여 실행할 수 있습니다.

**예제 1:** 업데이트할 사용자 목록을 제공하여 이 스크립트를 실행할 수 있습니다.
   
  ```PowerShell
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

**예제 2:** 업데이트하려는 각 .csv 전자 메일 주소(별칭)를 포함하는 .csv 파일을 제공하여 이 스크립트를 실행할 수 있습니다.
   
  ```PowerShell
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**예제 3:** 이 예제에서는 이 스크립트를 사용하여 조직의 많은 수의 사용자를 위해 오디오 회의 공급자를 Intercall(또는 다른 공급자)에서 **Microsoft로** 변경할 수 있습니다.
    
  ```PowerShell
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  스크립트는 다음과 같습니다.

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
Windows PowerShell 사용에 대한 자세한 내용은 Windows PowerShell 온라인 관리 비즈니스용 Skype [참조하세요.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>관련 항목
[오디오 회의를](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md) 시도하거나 Microsoft 365 또는 
 Office 365 [온라인 비즈니스용 Skype 설정](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
