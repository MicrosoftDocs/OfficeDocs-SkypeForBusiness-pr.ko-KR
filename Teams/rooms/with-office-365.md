---
title: Microsoft 365 또는 Office 365를 통해 Microsoft Teams Rooms 배포
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Microsoft 365 또는 Office 365를 통해 Microsoft Teams Rooms를 배포하는 방법에 대한 자세한 내용은 비즈니스용 Teams 또는 Skype 및 Exchange가 모두 온라인인 경우 이 항목을 참조하세요.
ms.openlocfilehash: b5cfaab64840fe72dc989f00ed41760058afc765
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117336"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Microsoft 365 또는 Office 365를 통해 Microsoft Teams Rooms 배포

Microsoft Teams 또는 비즈니스용 Skype 및 Exchange가 모두 온라인인 Microsoft 365 또는 Office 365를 통해 Microsoft Teams Rooms를 배포하는 방법에 대한 자세한 내용은 이 항목을 참조하세요.

사용자 계정을 설정하는 가장 쉬운 방법은 원격 계정을 사용하여 Windows PowerShell. Microsoft는 [ ](https://go.microsoft.com/fwlink/?linkid=870105)SkypeRoomProvisioningScript.ps1Microsoft Teams Rooms 사용자 계정으로 전환할 수 있도록 새 사용자 계정을 만들거나 기존 리소스 계정의 유효성을 검사하는 데 도움이 되는 스크립트인 스크립트를 제공합니다. 원하는 경우 아래 단계를 수행하여 Microsoft Teams Rooms 디바이스에서 사용할 계정을 구성할 수 있습니다.

## <a name="requirements"></a>요구 사항

Microsoft 365 또는 Office 365를 통해 Microsoft Teams Rooms를 배포하기 전에 요구 사항을 충족해야 합니다. 자세한 내용은 [Microsoft Teams Rooms 요구 사항 을 참조하세요.](requirements.md)

비즈니스용 Skype를 사용하도록 설정하려면 다음이 있어야 합니다.

- Microsoft 365 또는 Office 365 계획에서 비즈니스용 Skype Online(계획 2 또는 엔터프라이즈 기반 계획) 이상입니다. 계획은 전화 접속 회의 기능을 허용해야 합니다.

- 모임에서 전화 접속 기능이 필요한 경우 오디오 회의 및 전화 시스템 라이선스가 필요합니다.  모임에서 전화 접속 기능이 필요한 경우 오디오 회의 라이선스가 필요합니다.

- 테넌트 사용자에게 Exchange 사서함이 있어야 합니다.

- Microsoft Teams Rooms 계정에는 최소 비즈니스용 Skype Online(계획 2) 라이선스가 필요하지만 Exchange Online 라이선스가 필요하지 않습니다. 자세한 내용은 [Microsoft Teams Rooms 라이선스를](rooms-licensing.md) 참조합니다.

비즈니스용 Skype 온라인 요금제에 대한 자세한 내용은 [비즈니스용 Skype 온라인 서비스 설명 을 참조하세요.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)

### <a name="add-a-device-account"></a>디바이스 계정 추가

1. Exchange Online PowerShell에 연결합니다. 지침은 [Exchange Online PowerShell에 연결 을 참조하세요.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Exchange Online PowerShell에서 새 룸 사서함을 만들거나 기존 방 사서함을 수정합니다. 기본적으로 룸 사서함에는 연결된 계정이 없습니다. Skype Room Systems v2를 사용하여 인증할 수 있는 방 사서함을 만들거나 수정할 때 계정을 추가해야 합니다.

   - 새 룸 사서함을 만들 경우 다음 구문을 사용 합니다.

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     이 예제에서는 다음 설정을 사용하여 새 룸 사서함을 만듭니다.

     - 이름: Rigel-01

     - 별칭: Rigel1

     - 계정: Rigel1@contoso.onmicrosoft.com

     - 계정 암호: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 기존 룸 사서함을 수정하려면 다음 구문을 사용 합니다.

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     이 예제에서는 별칭 값이 Rigel2인 기존 룸 사서함에 대한 계정을 사용할 수 있으며 암호를 9898P@$$W 0rd로 설정합니다. 기존 별칭 값으로 Rigel2@contoso.onmicrosoft.com 계정이 변경됩니다.

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   자세한 구문 및 매개 변수 정보는 [New-사서함](/powershell/module/exchange/mailboxes/new-mailbox) 및 [Set-사서함 을 참조하세요.](/powershell/module/exchange/mailboxes/set-mailbox)

3. Exchange Online PowerShell에서 회의실 사서함에서 다음 설정을 구성하여 모임 환경을 개선합니다.

   - AutomateProcessing: AutoAccept(모임 이끌이는 사용자 개입 없이 직접 회의실 예약 결정을 수신합니다. 무료 = 수락, 사용 중 = 거부).)

   - AddOrganizerToSubject: $false(모임 이끌이가 모임 요청의 제목에 추가되지 않습니다.)

   - DeleteComments: $false(들어오는 모임 요청의 메시지 본문에 텍스트를 보관합니다.)

   - DeleteSubject: $false(들어오는 모임 요청의 제목 유지)입니다.

   - RemovePrivateProperty: $false(원래 모임 요청에서 모임 이끌이가 보낸 개인 플래그가 지정된 상태로 유지되도록 합니다.)

   - AddAdditionalResponse: $true(AdditionalResponse 매개 변수에서 지정한 텍스트가 모임 요청에 추가됩니다.)

   - 추가Response: "이것은 Skype 회의실입니다!" (모임 요청에 추가할 추가 텍스트입니다.)

   이 예제에서는 Rigel-01이라는 룸 사서함에서 이러한 설정을 구성합니다.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   자세한 구문 및 매개 변수 정보는 [Set-CalendarProcessing 을 참조하세요.](/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. POWERShell cmdlet을 실행하여 Active Directory 설정을 만들 수 있도록 MS `Connect-MsolService -Credential $cred` Online PowerShell에 연결합니다. Active Directory에 대한 자세한 내용은 [Azure ActiveDirectory(MSOnline) 1.0 을 참조하세요.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0은](/powershell/azure/active-directory/overview?view=azureadps-2.0) 지원되지 않습니다.

5. 암호가 만료되지 않는 경우 다음 구문을 사용하세요.

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   이 예제에서는 계정 암호가 만료되지 Rigel1@contoso.onmicrosoft.com 설정합니다.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   다음 명령을 실행하여 계정에 대한 전화 번호를 설정할 수도 있습니다.

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

> [!NOTE]
> 암호가 만료되지 않은 것으로 설정되어 있지 않은 경우 계정이 만료 기간에 도달하면 더 이상 디바이스에 로그인하지 않습니다. 그러면 계정에 대한 암호를 변경하고 MTR 디바이스에서 로컬로 업데이트해야 합니다.

6. 디바이스 계정에 유효한 Microsoft 365 또는 Office 365 라이선스가 있어야 합니다. 또는 Exchange 및 Microsoft Teams 또는 비즈니스용 Skype가 작동하지 않습니다. 라이선스가 있는 경우 디바이스 계정에 사용 위치를 할당해야 합니다. 그러면 계정에 사용할 수 있는 라이선스 SKUS가 결정됩니다. 사용할 수 있습니다. `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> Microsoft 365 또는 Office 365 조직에 사용할 수 있는 SKUS 목록을 다음과 같이 검색합니다.

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   다음으로, `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet입니다. 이 예제에서는 계정에 회의실 라이선스를 추가합니다.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   자세한 지침은 [Office 365 PowerShell을](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)통해 사용자 계정에 라이선스 할당을 참조하세요.

   이 계정에 전화 시스템 기능을 추가할 수도 있지만 먼저 구성해야 합니다. 자세한 [내용은 전화 시스템이란?을](../what-is-phone-system-in-office-365.md) 참조하세요. 이 예제에서는 PSTN 국내 및 국제 통화 계획을 추가합니다.

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. 다음으로 비즈니스용 Skype를 사용하여 디바이스 계정을 사용하도록 설정해야 합니다. 환경이 Microsoft Teams Rooms 요구 사항에 정의된 요구 사항을 [충족하는지 확인합니다.](requirements.md)

   다음과 같이 [원격](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) Windows PowerShell 시작(비즈니스용 Skype [Online PowerShell 구성 요소를 설치해야 합니다.](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector))

> [!NOTE]
> 비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.
>
> 최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   이 예제와 같이 설정되는 새 사용자 계정에서 RegistrarPool 정보를 얻게 됩니다.

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   다음으로, 다음 cmdlet을 실행하여 비즈니스용 Skype 서버용 Microsoft Teams Rooms 계정을 사용하도록 설정합니다.

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > 테넌트의 기존 사용자 계정과 동일한 등록 기관 풀에서 새 사용자 계정을 만들 수 없습니다. 위의 명령은 이 상황으로 인해 계정 설정의 오류를 방지합니다.

## <a name="validate"></a>유효성 검사

유효성 검사를 위해 비즈니스용 Skype 클라이언트를 사용하여 만든 계정에 로그인할 수 있습니다.

## <a name="see-also"></a>참고 항목

[Microsoft Teams Rooms에 대한 계정 구성](rooms-configure-accounts.md)

[Microsoft Teams 룸 계획](rooms-plan.md)

[Microsoft Teams 룸 배포](rooms-deploy.md)

[Microsoft Teams 룸 콘솔 구성](console.md)

[Microsoft Teams 룸 관리](rooms-manage.md)

[Microsoft Teams Rooms 라이선스](rooms-licensing.md)