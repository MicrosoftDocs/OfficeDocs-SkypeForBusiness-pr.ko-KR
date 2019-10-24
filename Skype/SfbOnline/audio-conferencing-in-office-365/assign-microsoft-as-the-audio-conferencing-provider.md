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
ms.openlocfilehash: 18792e87b83f9ee69030a6d83fecdbb9513c6f73
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "37642308"
---
# <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Microsoft를 오디오 회의 공급자로 지정

Office 365에서 비즈니스용 Skype 및 Microsoft 팀과 오디오 회의를 사용 하려면 조직의 사용자가 오디오 회의 라이선스를 할당 해야 합니다. 라이선스에 대 한 자세한 내용과 비용을 얻으려면 [Office 365에서 오디오 회의 체험 또는 구입](try-or-purchase-audio-conferencing-in-office-365.md) 을 참조 하세요.

Microsoft 오디오 회의는 모임 참가자가 조직의 모임에 참가할 때 사용할 수 있는 전화 접속 전화 번호, Pin 및 전화 회의 Id를 제공 합니다. 비즈니스용 Skype 또는 Microsoft 팀 모임을 예약 하거나 리드 하는 사용자에 게 Microsoft를 오디오 회의 공급자로 지정 하기만 하면 됩니다.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="assign-microsoft-as-the-audio-conferencing-provider"></a>Microsoft를 오디오 회의 공급자로 지정

### <a name="an-icon-showing-the-skype-for-business-logoimagessfb-logo-30x30png-using-the-skype-for-business-admin-center"></a>![비즈니스용 Skype 로고를 표시 하는 아이콘](../images/sfb-logo-30x30.png) 비즈니스용 Skype 관리 센터 사용

1. **Microsoft 팀 관리 센터** > **레거시 포털로**이동 합니다.
    
2. **비즈니스용 Skype 관리 센터**의 왼쪽 탐색 창에서 **오디오 회의**로 이동 합니다.
    
3. **오디오 회의** 라이선스를 할당 했지만 오디오 회의 공급자로 Microsoft가 설정 되지 않았음을 알리는 배너가 표시 되는 경우 **여기를 클릭 하 여 이동**합니다. 배너가 표시 되지 않는 경우 **비즈니스용 Skype 관리 센터** 에서 **사용자**를 클릭 한 다음 **오디오 회의 필터로 이동할 사용자** 를 선택 합니다.
    
4. 사용자의 속성 페이지에서 **공급자 이름**아래의 드롭다운 목록에서 **Microsoft** 를 선택 합니다.
    
    > [!NOTE]
    > 오디오 회의 공급자로 Microsoft를 사용 하 고 있으며 여러 개의 전화 번호가 있으므로 **기본 유료 번호** 드롭다운 목록을 사용 하 여 사용자의 기본 오디오 번호를 선택할 수 있습니다.
  
5. **저장**을 클릭 합니다.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
### <a name="using-a-windows-powershell-script-for-a-small-number-of-users"></a>적은 수의 사용자를 위해 Windows PowerShell 스크립트 사용

시간을 절약 하거나이를 자동화 하려면 다음 PowerShell 스크립트를 사용 하 여 Microsoft를 적은 수의 사용자에 대 한 오디오 회의 공급자로 설정할 수 있습니다.

> [!NOTE]
> 공급자가 다른 공급자에서 **Microsoft**로 변경 되 면 사용자에 대 한 오디오 회의 정보 (컨퍼런스 ID, 유료 및 무료 번호)가 바뀝니다. 공급자를 변경 하기 전에이 정보를 저장 해야 합니다. 

  
소수의 사용자에 대해 공급자를 Microsoft로 변경 하려면 [Enable-get-csonlinedialinconferencinguser](https://technet.microsoft.com/en-us/library/mt243813.aspx) cmdlet을 사용 하면 됩니다.
  

### <a name="using-a-windows-powershell-script-for-a-large-number-of-users"></a>많은 수의 사용자를 위해 Windows PowerShell 스크립트 사용
시간을 절약 하거나이를 자동화 하려면 다음 PowerShell 스크립트를 사용 하 여 Microsoft를 다 수의 사용자를 위한 오디오 회의 공급자로 설정할 수 있습니다.

공급자가 다른 공급자에서 **Microsoft**로 변경 되 면 사용자에 대 한 오디오 회의 정보 (컨퍼런스 ID, 유료 및 무료 번호)가 바뀝니다. 공급자를 변경 하기 전에이 정보를 저장 해야 합니다. 
  
다음 스크립트를 PowerShell 스크립트 파일로 저장 한 다음 해당 입력 매개 변수를 사용 하 여 실행할 수 있습니다.

**예제 1:** 업데이트 하려는 사용자의 목록을 제공 하 여이 스크립트를 실행할 수 있습니다.
   
  ```
Script.ps1 -UserList <List of users>
./Script.ps1 -UserList "user01@constoso.com, user02@contoso.com, user03@contoso.com"
  ```

**예제 2:** 업데이트 하려는 각 사용자의 전자 메일 주소 (별칭)를 포함 하는 .csv 파일을 제공 하 여이 스크립트를 실행할 수 있습니다.
   
  ```
Script.ps1 -CsvFile <Path of the csv file>
./Script.ps1 -CsvFile ".\\CsvFile.csv"
  ```

**예제 3:** 이 예제에서는 조직의 대규모 사용자에 대해이 스크립트를 사용 하 여 오디오 회의 공급자를 상호 통화 (또는 다른 공급자)에서 **Microsoft** 로 변경할 수 있습니다.
    
  ```
  Script.ps1 -ACPProviderName <Provider>
  ./Script.ps1 -ACPProviderName "Intercall"
  ```
  스크립트는 다음과 같습니다.

  ```
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
Windows PowerShell을 사용 하는 방법에 대 한 자세한 내용은 [Windows powershell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업](https://go.microsoft.com/fwlink/?LinkId=525038)을 참조 하세요.
  
## <a name="related-topics"></a>관련 항목
[](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
[비즈니스용 Skype Online 설정](../set-up-skype-for-business-online/set-up-skype-for-business-online.md) 또는 Office 365에서 오디오 회의 체험 또는 구매

