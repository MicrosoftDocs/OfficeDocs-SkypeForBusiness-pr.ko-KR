---
title: PowerShell을 Microsoft Teams 공동 작업용 공동 작업 Microsoft Teams 리소스 계정 만들기
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 공동 작업 막대를 배포하는 방법에 대한 자세한 내용은 이 Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 812fb4704661aa11d3388048fa044030cdb1ce00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115606"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>PowerShell을 사용하여 Microsoft 365 리소스 계정 만들기

PowerShell을 사용하여 공동 작업용 공동 작업 막대에 Microsoft Teams 방법에 대한 자세한 내용은 이 항목을 참조하세요.

리소스 계정을 만드는 가장 쉬운 방법은 관리 센터를 Microsoft 365 것입니다. [이 작업을 하는 방법에 대한 이 문서를 참조하세요.](resource-account-ui.md)

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>요구 사항

Microsoft Teams 룸 배포하기 Office 365 요구 사항을 충족해야 합니다. 자세한 내용은 에 대한 공동 [작업 Microsoft Teams.](collab-bar-deploy.md)

- 공동 작업 표시줄에 PSTN 기능이 필요한 경우 라이선스가 전화 시스템 합니다.

- 리소스 계정에 사서함이 Exchange 있어야 합니다. 리소스 계정이기 때문에 라이선스가 Exchange 필요하지 않습니다. 리소스 계정에 회의실 라이선스를 사용 하는 것이 좋습니다.


### <a name="add-a-resource-account"></a>리소스 계정 추가

1. 커넥트 PowerShell을 Exchange Online 수 있습니다. 지침은 [PowerShell을 커넥트 Exchange Online 참조하세요.](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)

2. PowerShell에서 새 Exchange Online 사서함을 만들거나 기존 방 사서함을 수정합니다.

   - 새 룸 사서함을 만들 경우 다음 구문을 사용 합니다.

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     이 예제에서는 다음 설정을 사용하여 새 룸 사서함을 만듭니다.

     - 이름: Huddle-Room-01

     - 별칭: HuddleRoom01

     - 계정: huddleroom01@contoso.onmicrosoft.com

     - 계정 암호: P@$$W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - 기존 룸 사서함을 수정하려면 다음 구문을 사용 합니다.

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     이 예제에서는 별칭 값이 HuddleRoom02인 기존 회의실 사서함에 대한 계정을 사용할 수 있으며 암호를 808P@$$W 0rd로 설정합니다. 기존 별칭 값으로 HuddleRoom02@contoso.onmicrosoft.com 계정이 설정됩니다.

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   자세한 구문 및 매개 변수 정보는 [New-사서함](/powershell/module/exchange/mailboxes/new-mailbox) 및 [Set-사서함 을 참조하세요.](/powershell/module/exchange/mailboxes/set-mailbox)


3. PowerShell의 Exchange Online 회의실 사서함에서 다음 설정을 구성하여 모임 환경을 개선합니다.

   - AutomateProcessing: AutoAccept(모임 이끌이는 사용자 개입 없이 직접 회의실 예약 결정을 수신합니다. 무료 = 수락, 사용 중 = 거부).)

   - AddOrganizerToSubject: $false(모임 이끌이가 모임 요청의 제목에 추가되지 않습니다.)

   - DeleteComments: $false(들어오는 모임 요청의 메시지 본문에 텍스트를 보관합니다.)

   - DeleteSubject: $false(들어오는 모임 요청의 제목 유지)입니다.

   - RemovePrivateProperty: $false(원래 모임 요청에서 모임 이끌이가 보낸 개인 플래그가 지정된 상태로 유지되도록 합니다.)

   - AddAdditionalResponse: $true(AdditionalResponse 매개 변수에서 지정한 텍스트가 모임 요청에 추가됩니다.)

   - 추가Response: "이 방에는 공동 작업 표시줄이 Microsoft Teams!" (모임 요청에 추가할 추가 텍스트입니다.)

   이 예제에서는 Huddle-Room-01이라는 룸 사서함에서 이러한 설정을 구성합니다.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   자세한 구문 및 매개 변수 정보는 [Set-CalendarProcessing 을 참조하세요.](/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. 커넥트 powershell cmdlet을 실행하여 Active Directory 설정을 만들기 위해 MS Online `Connect-MsolService -Credential $cred` PowerShell으로 이동합니다.   Active Directory에 대한 자세한 내용은 [Azure ActiveDirectory(MSOnline) 1.0 을 참조하세요.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0은](/powershell/azure/active-directory/overview?view=azureadps-2.0) 지원되지 않습니다. 

5. 다음 구문을 사용하여 huddleroom01@contoso.onmicrosoft.com 암호가 만료되지 않는지 설정합니다.

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. 리소스 계정에 유효한 SKU Office 365 라이선스가 미팅룸 필요합니다. 또한 디바이스 계정에 사용 위치를 할당해야 합니다. 그러면 계정에 사용할 수 있는 라이선스 SKUS가 결정됩니다. 테넌트에 사용할 수 있는 SKUS 목록을 검색하는 `Get-MsolAccountSku` 데 Office 365 있습니다.

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    Set-MsolUserLicense를 사용하여 라이선스를 할당할 수 있습니다. 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   자세한 지침은 PowerShell을 통해 사용자 계정에 라이선스 [할당을 Office 365 참조하세요.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)




[PowerShell을 사용하여 공동 작업 Microsoft Teams 계정 구성](resource-account-ps.md)

[공동 작업용 공동 작업 Microsoft Teams](collab-bar-deploy.md)

[라이선스에 Microsoft Teams 공동 작업 막대](../rooms/rooms-licensing.md)