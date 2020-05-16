---
title: PowerShell을 사용 하 여 Microsoft 팀의 공동 작업 모음에 대 한 Microsoft 팀 자원 계정 만들기
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
description: Microsoft 팀에 대 한 공동 작업 표시줄을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268050"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>PowerShell을 사용 하 여 Microsoft 365 리소스 계정 만들기

PowerShell을 사용 하 여 Microsoft 팀의 공동 작업 모음에 대 한 리소스 계정을 만드는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.

리소스 계정을 만드는 가장 쉬운 방법은 Microsoft 365 관리 센터를 사용 하는 것입니다. [이 작업을 수행 하는 방법에 대해서는이 문서를 참조](resource-account-ui.md)하세요.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>요구 사항

Microsoft 팀 회의실을 Office 365에 배포 하기 전에 요구 사항을 충족 해야 합니다. 자세한 내용은 [Microsoft 팀에 대 한 공동 작업 표시줄 배포](collab-bar-deploy.md)를 참조 하세요.

- 공동 작업 표시줄에 PSTN 기능이 필요한 경우에는 전화 시스템 라이선스가 필요 합니다.

- 리소스 계정에 Exchange 사서함이 있어야 합니다. 이러한 계정은 리소스 계정 이므로 Exchange 라이선스가 필요 하지 않습니다. 리소스 계정에 대해 회의실 라이선스를 사용 하는 것이 좋습니다.


### <a name="add-a-resource-account"></a>자원 계정 추가

1. Exchange Online PowerShell에 연결 합니다. 지침은 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)을 참조 하세요.

2. Exchange Online PowerShell에서 새 회의실 사서함을 만들거나 기존 회의실 사서함을 수정 합니다.

   - 새 회의실 사서함을 만들려면 다음 구문을 사용 합니다.

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     이 예제에서는 다음 설정을 사용 하 여 새 채팅방 사서함을 만듭니다.

     - 이름: Huddle--룸-01

     - 별칭: HuddleRoom01

     - 계정: huddleroom01@contoso.onmicrosoft.com

     - 계정 암호: P@ $ $W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - 기존 회의실 사서함을 수정 하려면 다음 구문을 사용 합니다.

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     이 예제에서는 별칭 값 HuddleRoom02를 가진 기존 회의실 사서함에 대 한 계정을 사용 하도록 설정 하 고 암호를 808P@ $ $W 0rd으로 설정 합니다. 기존 별칭 값 때문에 계정이 HuddleRoom02@contoso.onmicrosoft.com 것을 참고 하세요.

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   자세한 구문 및 매개 변수 정보는 [새 사서함](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) 및 [설정 사서함](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)을 참조 하세요.


3. Exchange Online PowerShell에서 회의실 사서함에 다음 설정을 구성 하 여 모임 환경을 개선 합니다.

   - AutomateProcessing: AutoAccept (모임 이끌이는 사용자 간섭 없이 직접 회의실 예약 결정을 받습니다: 무료 = 수락; 사용 중 = 거절).

   - AddOrganizerToSubject: $false (모임 이끌이는 모임 요청의 제목에 추가 되지 않습니다.)

   - Deletecomdea: $false (받는 모임 요청의 메시지 본문에 있는 텍스트는 유지 합니다.)

   - DeleteSubject: $false (들어오는 모임 요청의 주제를 보관 합니다.)

   - RemovePrivateProperty: $false (원래 모임 이끌이가 보낸 개인 플래그가 지정 된 대로 유지 되도록 합니다.)

   - AddAdditionalResponse: $true (AdditionalResponse 매개 변수에서 지정한 텍스트가 모임 요청에 추가 됩니다.)

   - AdditionalResponse: "이 채팅방에는 Microsoft 팀에 대 한 공동 작업 표시줄이 있습니다!" (모임 요청에 추가 하는 추가 텍스트입니다.)

   이 예제에서는 Huddle 라는 룸 사서함에서 이러한 설정을 구성 합니다.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   자세한 구문 및 매개 변수 정보는 [설정-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)를 참조 하세요.

4. Powershell cmdlet을 실행 하 여 Active Directory 설정을 만들기 위해 MS Online PowerShell에 연결 `Connect-MsolService -Credential $cred` 합니다.   Active Directory에 대 한 자세한 내용은 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)을 참조 하세요. 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) 는 지원 되지 않습니다. 

5. Huddleroom01@contoso.onmicrosoft.com의 암호가 만료 되지 않도록 설정 하려면 다음 구문을 사용 합니다.

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. 리소스 계정에는 유효한 Office 365 라이선스 (특히 회의실 SKU)가 있어야 합니다. 또한 장치 계정에 사용 위치를 할당 해야 하며,이는 계정에 사용할 수 있는 라이선스 Sku를 결정 하는 것입니다. `Get-MsolAccountSku`Office 365 테 넌 트에 대해 사용 가능한 sku 목록을 검색 하는 데 사용할 수 있습니다.

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    Set-MsolUserLicense를 사용 하 여 라이선스를 할당할 수 있습니다. 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   자세한 지침은 [Office 365 PowerShell을 사용 하 여 사용자 계정에 라이선스 할당](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)을 참조 하세요.




[PowerShell을 사용 하 여 Microsoft 팀의 공동 작업 모음에 대 한 계정 구성](resource-account-ps.md)

[Microsoft 팀을 위한 공동 작업 표시줄 배포](collab-bar-deploy.md)

[Microsoft 팀 라이선스에 대 한 공동 작업 표시줄](../rooms/rooms-licensing.md)


