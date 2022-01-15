---
title: Microsoft Teams 룸 Office 365
ms.author: v-lanac
author: lanachin
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
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 이 항목을 참조하여 Microsoft Teams 룸 배포하는 방법에 Office 365.
ms.openlocfilehash: d4c66fb863c5c41a717808ddca43002752510fb5
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62056028"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Microsoft Teams 룸 Office 365

이 항목을 참조하여 Microsoft Teams 룸 배포하는 방법에 Office 365.

## <a name="requirements"></a>요구 사항

Microsoft Teams 룸 배포하기 Office 365 요구 사항을 충족해야 합니다. 자세한 내용은 요구 사항 [Microsoft Teams 룸 참조하세요.](requirements.md)

### <a name="add-a-resource-account"></a>리소스 계정 추가

1. 커넥트 PowerShell을 Exchange Online 수 있습니다. 지침은 [PowerShell을 커넥트 Exchange Online 참조하세요.](https://go.microsoft.com/fwlink/p/?linkid=396554)

2. PowerShell에서 새 Exchange Online 사서함을 만들거나 기존 방 사서함을 수정합니다. 기본적으로 룸 사서함에는 연결된 계정이 없습니다. 인증할 수 있는 룸 사서함을 만들거나 수정할 때 계정을 추가해야 합니다.

   - 새 룸 사서함을 만들 경우 다음 구문을 사용 합니다.

     ``` PowerShell
     New-Mailbox -Name '<Unique Name>' -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     이 예제에서는 다음 설정을 사용하여 새 룸 사서함을 만듭니다.

     - 이름: 회의실 01

     - 별칭: ConferenceRoom01

     - 계정: ConferenceRoom01@contoso.com

     - 계정 암호: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name 'Conference Room 01' -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 기존 룸 사서함을 수정하려면 다음 구문을 사용 합니다.

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     이 예제에서는 별칭 값이 ConferenceRoom02인 기존 회의실 사서함에 대한 계정을 사용할 수 있으며 암호를 9898P@$$W 0rd로 설정합니다.

     ``` PowerShell
     Set-Mailbox -Identity 'ConferenceRoom02' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   자세한 구문 및 매개 변수 정보는 [New-사서함](/powershell/module/exchange/mailboxes/new-mailbox) 및 [Set-사서함 을 참조하세요.](/powershell/module/exchange/mailboxes/set-mailbox)


3. PowerShell의 Exchange Online 회의실 사서함에서 다음 설정을 구성하여 모임 환경을 개선합니다.

   - AutomateProcessing: AutoAccept(사서함은 자동으로 사람이 개입하지 않고 직접 예약 결정을 내릴 수 있습니다.)

   - AddOrganizerToSubject: $false(모임 이끌이가 모임 요청의 제목에 추가되지 않습니다.)

   - DeleteComments: $false(들어오는 모임 요청의 메시지 본문에 텍스트를 보관합니다.)

   - DeleteSubject: $false(들어오는 모임 요청의 제목 유지)입니다.

   - RemovePrivateProperty: $false(원래 모임 요청에서 모임 이끌이가 보낸 개인 플래그가 지정된 상태로 유지되도록 합니다.)

   - AddAdditionalResponse: $true(AdditionalResponse 매개 변수에서 지정한 텍스트가 모임 요청에 추가됩니다.)

   - AdditionalResponse: "이 회의실은 Microsoft Teams 있습니다!" (모임 요청에 추가할 추가 텍스트입니다.)

   이 예제에서는 Project-Rigel-01이라는 방 사서함에서 이러한 설정을 구성합니다.

   ``` PowerShell
   Set-CalendarProcessing -Identity 'ConferenceRoom01' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse 'This is a Microsoft Teams meeting room!'
   ```

   자세한 구문 및 매개 변수 정보는 [Set-CalendarProcessing 을 참조하세요.](/powershell/module/exchange/mailboxes/set-calendarprocessing)
   
4. 커넥트 '커넥트-MsolService -credential $cred' powershell cmdlet을 실행하여 ACTIVE Directory 값을 MS Online PowerShell에 설정합니다. Active Directory에 대한 자세한 내용은 [Azure ActiveDirectory(MSOnline) 1.0 을 참조하세요.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0은](/powershell/azure/active-directory/overview?view=azureadps-2.0) 지원되지 않습니다. 

5. 계정에서 암호 만료를 사용하지 않도록 설정하는 것이 Teams 룸 권장됩니다. 다음은 Account ConferenceRoom01에 대한 암호 만료를 사용하지 않도록 설정하는 방법의 예입니다.

    ``` PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```


1. 리소스 계정에 연결하려면 유효한 Office 365 라이선스가 Microsoft Teams. 또한 디바이스 계정에 사용 위치를 할당해야 합니다. 그러면 계정에 사용할 수 있는 라이선스 SKUS가 결정됩니다. 테넌트에 사용할 수 있는 SKUS 목록을 검색하는 `Get-MsolAccountSku` 데 Office 365 있습니다. cmdlet을 사용하여 라이선스를 `Set-MsolUserLicense` 추가할 수 있습니다.

   이 예제에서는 미팅룸 사용자에 대한 라이선스를 할당합니다.

  ``` PowerShell
   Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
  ``` 


   자세한 지침은 PowerShell을 통해 사용자 계정에 라이선스 [할당을 Office 365 참조하세요.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)


## <a name="validate"></a>유효성 검사

유효성 검사를 위해 모든 Microsoft Teams 클라이언트를 사용하여 만든 계정에 로그인할 수 있습니다.

## <a name="see-also"></a>참고 항목
[더 나은 검색 및 룸 제안 환경을 제공하려면 추가 메타데이터로 룸 사서함 업데이트](/powershell/module/exchange/set-place)

[Microsoft Teams 룸](rooms-configure-accounts.md)

[Microsoft Teams 룸 계획](rooms-plan.md)

[Microsoft Teams 룸 배포](rooms-deploy.md)

[Microsoft Teams 룸 콘솔 구성](console.md)

[Microsoft Teams 룸 관리](rooms-manage.md)

[Microsoft Teams 룸 라이선스](rooms-licensing.md)
