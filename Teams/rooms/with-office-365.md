---
title: Microsoft Teams 룸 또는 Microsoft Teams 룸 Microsoft 365 배포합니다Office 365
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 이 항목을 참조하세요. Microsoft Teams 룸 또는 Microsoft 365 Office 365 또는 온라인 Teams 비즈니스용 Skype Exchange 참조하세요.
ms.openlocfilehash: e3f72c86f88ab449b48b80d6bef06d0858c44b53
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355647"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Microsoft Teams 룸 또는 Microsoft Teams 룸 Microsoft 365 배포합니다Office 365

이 항목에서는 Microsoft Teams 룸 또는 Microsoft 365 Office 365 배포하는 방법에 Microsoft Teams Exchange 참조하세요.

## <a name="requirements"></a>요구 사항

Microsoft Teams 룸 또는 Microsoft 365 Office 365 배포하기 전에 요구 사항을 충족해야 합니다. 자세한 내용은 요구 사항 [Microsoft Teams 룸 참조하세요.](requirements.md)

### <a name="add-a-resource-account"></a>리소스 계정 추가

1. 커넥트 PowerShell을 Exchange Online 수 있습니다. 지침은 [PowerShell을 커넥트 Exchange Online 참조하세요.](/powershell/exchange/connect-to-exchange-online-powershell)

2. PowerShell에서 새 Exchange Online 사서함을 만들거나 기존 방 사서함을 수정합니다. 기본적으로 룸 사서함에는 연결된 계정이 없습니다. 따라서 계정으로 인증할 수 있는 방 사서함을 만들거나 수정할 때 계정을 추가해야 Microsoft Teams.

   - 새 룸 사서함을 만들 경우 다음 구문을 사용 합니다.

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     이 예제에서는 다음 설정을 사용하여 새 룸 사서함을 만듭니다.

     - 계정: ConferenceRoom01@contoso.com
  
     - 이름: ConferenceRoom01

     - 별칭: ConferenceRoom01

     - 계정 암호: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 기존 룸 사서함을 수정하려면 다음 구문을 사용 합니다.

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     이 예제에서는 별칭 값이 ConferenceRoom02인 기존 회의실 사서함에 대한 계정을 사용할 수 있으며 암호를 9898P@$$W 0rd로 설정합니다. 기존 별칭 값으로 ConferenceRoom02@contoso.com 계정이 변경됩니다.

     ``` PowerShell
     Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   자세한 구문 및 매개 변수 정보는 [New-사서함](/powershell/module/exchange/mailboxes/new-mailbox) 및 [Set-사서함 을 참조하세요.](/powershell/module/exchange/mailboxes/set-mailbox)

3. PowerShell의 Exchange Online 회의실 사서함에서 다음 설정을 구성하여 모임 환경을 개선합니다.

   - AutomateProcessing: AutoAccept(모임 이끌이는 사람의 개입 없이 회의실 예약 결정을 직접 수신합니다.)

   - AddOrganizerToSubject: $false(모임 이끌이가 모임 요청의 제목에 추가되지 않습니다.)

   - DeleteComments: $false(들어오는 모임 요청의 메시지 본문에 텍스트를 보관합니다.)

   - DeleteSubject: $false(들어오는 모임 요청의 제목 유지)입니다.

   - RemovePrivateProperty: $false(원래 모임 요청에서 모임 이끌이가 보낸 개인 플래그가 지정된 상태로 유지되도록 합니다.)

   - AddAdditionalResponse: $true(AdditionalResponse 매개 변수에서 지정한 텍스트가 모임 요청에 추가됩니다.)

   - 추가Response: "이 회의실은 Microsoft Teams 있습니다!" (모임 요청에 추가할 추가 텍스트입니다.)

   이 예제에서는 ConferenceRoom01이라는 회의실 사서함에서 이러한 설정을 구성합니다.

   ``` PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   자세한 구문 및 매개 변수 정보는 [Set-CalendarProcessing 을 참조하세요.](/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. 커넥트 실행하여 Active Directory 설정을 만들기 위해 MS Online PowerShell으로 이동 `Connect-MsolService` PowerShell cmdlet입니다. Active Directory에 대한 자세한 내용은 [Azure ActiveDirectory(MSOnline) 1.0 을 참조하세요.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0은](/powershell/azure/active-directory/overview?view=azureadps-2.0) 지원되지 않습니다.

5. 다음 구문을 사용하여 암호를 만료하지 못하게 설정합니다.

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   이 예제에서는 계정의 암호를 ConferenceRoom01@contoso.onmicrosoft.com 만료되지 않습니다.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   다음 명령을 실행하여 계정에 대한 전화 번호를 설정할 수도 있습니다.

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > 암호가 만료되지 않은 것으로 설정되어 있지 않은 경우 계정이 만료 기간에 도달하면 더 이상 디바이스에 로그인하지 않습니다. 그런 다음 계정에 대해 암호를 변경하고 계정에서 로컬로 업데이트해야 Teams 룸. 암호가 만료된 Teams 룸 사용자가 모임에 참가할 수 없습니다.

6. 리소스 계정에 유효한 Microsoft 365 Office 365 라이선스가 있어야 Exchange Microsoft Teams 작동하지 않습니다. 라이선스가 있는 경우 리소스 계정에 사용 위치를 할당해야 합니다. 그러면 계정에 사용할 수 있는 라이선스 SKUS가 결정됩니다. 사용할 수 있습니다. `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 다음을 수행하여 조직 또는 조직에서 Microsoft 365 사용할 Office 365 목록을 검색합니다.

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   다음으로, `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet입니다. 이 예제에서는 계정에 미팅룸 라이선스를 추가합니다.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName "ConferenceRoom01@contoso.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   자세한 지침은 PowerShell을 통해 사용자 계정에 라이선스 [할당을 Office 365 참조하세요.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   이 계정에 전화 시스템 기능을 추가할 수도 있지만 먼저 구성해야 합니다. 자세한 [내용은 전화 시스템?를](../what-is-phone-system-in-office-365.md) 참조하세요. 이 예제에서는 PSTN 국내 및 국제 통화 계획을 추가합니다.

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName ConferenceRoom01@contoso.com -AddLicenses "Contoso:MCOPSTN2"
   ```


## <a name="validate"></a>유효성 검사

유효성 검사를 위해 모든 Microsoft Teams 클라이언트를 사용하여 만든 계정에 로그인할 수 있습니다.

## <a name="see-also"></a>참고 항목

[Microsoft Teams 룸](rooms-configure-accounts.md)

[Microsoft Teams 룸 계획](rooms-plan.md)

[Microsoft Teams 룸 배포](rooms-deploy.md)

[Microsoft Teams 룸 콘솔 구성](console.md)

[Microsoft Teams 룸 관리](rooms-manage.md)

[Microsoft Teams 룸 라이선스](rooms-licensing.md)
