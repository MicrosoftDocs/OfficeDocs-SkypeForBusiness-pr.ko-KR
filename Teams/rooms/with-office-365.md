---
title: Office 365를 사용 하 여 Microsoft 팀 대화방 배포
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
description: Office 365를 사용 하 여 Microsoft 팀 회의실을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: d3fcfdd0b2aabc5d69946ba60b5b8c6fbc73f713
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827446"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Office 365를 사용 하 여 Microsoft 팀 대화방 배포

Microsoft 팀 또는 비즈니스용 Skype와 Exchange가 모두 온라인 상태에 있는 Microsoft 팀 대화방을 Office 365와 함께 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.

사용자 계정을 설정 하는 가장 쉬운 방법은 원격 Windows PowerShell을 사용 하 여 구성 하는 것입니다. Microsoft는 새 사용자 계정을 만들거나, 호환 되는 Microsoft 팀 대화방 사용자 계정으로 전환 하는 데 도움을 주는 기존 리소스 계정이 있는지 확인 하는 데 도움이 되는 [SkypeRoomProvisioningScript. ps1을 제공 합니다.](https://go.microsoft.com/fwlink/?linkid=870105) 원하는 경우 아래 단계에 따라 Microsoft 팀 대화방 장치에서 사용할 계정을 구성할 수 있습니다.

## <a name="requirements"></a>요구 사항

Microsoft 팀 회의실을 Office 365에 배포 하기 전에 요구 사항을 충족 해야 합니다. 자세한 내용은 [Microsoft 팀 공간 요구 사항을](requirements.md)참조 하세요.

비즈니스용 Skype를 사용 하도록 설정 하려면 다음이 필요 합니다.

- Office 365 요금제의 비즈니스용 Skype Online (계획 2 또는 엔터프라이즈 기반 계획) 이상 요금제는 전화 접속 회의 기능을 허용 해야 합니다.

- 모임에서 전화 접속 기능이 필요한 경우에는 오디오 회의 및 전화 시스템 라이선스가 필요 합니다.  모임에서 전화 접속 기능이 필요한 경우 국내 또는 국내 및 국제 통화 요금제가 필요 합니다.

- 테 넌 트 사용자에 게 Exchange 사서함이 있어야 합니다.

- Microsoft 팀 대화방 계정에는 최소한 비즈니스용 Skype Online (요금제 2) 라이선스가 필요 하지만 Exchange Online 라이선스는 필요 하지 않습니다. 자세한 내용은 [Microsoft 팀 대화방 라이선스](rooms-licensing.md) 를 참조 하세요.

비즈니스용 Skype Online 요금제에 대 한 자세한 내용은 [비즈니스용 Skype Online 서비스 설명을](https://technet.microsoft.com/library/jj822172.aspx)참조 하세요.

### <a name="add-a-device-account"></a>디바이스 계정 추가

1. Exchange Online PowerShell에 연결 합니다. 지침은 [Exchange Online PowerShell에 연결](https://go.microsoft.com/fwlink/p/?linkid=396554)을 참조 하세요.

2. Exchange Online PowerShell에서 새 회의실 사서함을 만들거나 기존 회의실 사서함을 수정 합니다. 기본적으로 회의실 사서함에는 연결 된 계정이 없으므로 Skype 대화방 시스템을 인증 하는 데 사용할 수 있는 채팅방 사서함을 만들거나 수정할 때 계정을 추가 해야 합니다.

   - 새 회의실 사서함을 만들려면 다음 구문을 사용 합니다.

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     이 예제에서는 다음 설정을 사용 하 여 새 채팅방 사서함을 만듭니다.

     - 이름: Project-Rigel-01

     - 별칭: ProjectRigel01

     - 계정: ProjectRigel01@contoso.onmicrosoft.com

     - 계정 암호: P@ $ $W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 기존 회의실 사서함을 수정 하려면 다음 구문을 사용 합니다.

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     이 예제에서는 별칭 값 ProjectRigel02를 가진 기존 회의실 사서함에 대 한 계정을 사용 하도록 설정 하 고 암호를 9898P@ $ $W 0rd으로 설정 합니다. 기존 별칭 값 때문에 계정이 ProjectRigel02@contoso.onmicrosoft.com 것을 참고 하세요.

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   자세한 구문 및 매개 변수 정보는 [새 사서함](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) 및 [설정 사서함](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)을 참조 하세요.


3. Exchange Online PowerShell에서 회의실 사서함에 다음 설정을 구성 하 여 모임 환경을 개선 합니다.

   - AutomateProcessing: AutoAccept (모임 이끌이는 사용자 간섭 없이 직접 회의실 예약 결정을 받습니다: 무료 = 수락; 사용 중 = 거절).

   - AddOrganizerToSubject: $false (모임 이끌이는 모임 요청의 제목에 추가 되지 않습니다.)

   - Deletecomdea: $false (받는 모임 요청의 메시지 본문에 있는 텍스트는 유지 합니다.)

   - DeleteSubject: $false (들어오는 모임 요청의 주제를 보관 합니다.)

   - RemovePrivateProperty: $false (원래 모임 이끌이가 보낸 개인 플래그가 지정 된 대로 유지 되도록 합니다.)

   - AddAdditionalResponse: $true (AdditionalResponse 매개 변수에서 지정한 텍스트가 모임 요청에 추가 됩니다.)

   - AdditionalResponse: "Skype 회의실입니다!" (모임 요청에 추가 하는 추가 텍스트입니다.)

   이 예제에서는 Rigel-01 이라는 대화방 사서함에서 이러한 설정을 구성 합니다.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   자세한 구문 및 매개 변수 정보는 [설정-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)를 참조 하세요.

4. `Connect-MsolService -Credential $cred` Powershell cmdlet을 실행 하 여 Active Directory 설정을 만들기 위해 MS Online PowerShell에 연결 합니다.   Active Directory에 대 한 자세한 내용은 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)을 참조 하세요. 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) 는 지원 되지 않습니다. 

5. 암호가 만료 되지 않도록 하려면 다음 구문을 사용 합니다.

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   이 예제에서는 계정 ProjectRigel01@contoso.onmicrosoft.com의 암호가 만료 되지 않도록 설정 합니다.

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   다음 명령을 실행 하 여 계정의 전화 번호를 설정할 수도 있습니다.

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. 장치 계정에 유효한 Office 365 라이선스가 있어야 하며, Exchange 및 Microsoft 팀 또는 비즈니스용 Skype가 작동 하지 않습니다. 라이선스가 있는 경우 사용 위치를 디바이스 계정에 할당 해야 하며,이는 계정에 사용할 수 있는 라이선스 Sku를 결정 하는 것입니다. 사용할 수 있는`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 다음과 같이 Office 365 테 넌 트에 대해 사용 가능한 Sku 목록을 검색 합니다.

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   다음으로, 다음을 사용 하 여 라이선스를 추가할 수 있습니다.`Set-MsolUserLicense` <!--Set-AzureADUserLicense --> 은. 이 경우 $strLicense는 사용자에 게 표시 되는 SKU 코드입니다 (예: contoso: STANDARDPACK).

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   자세한 지침은 [Office 365 PowerShell을 사용 하 여 사용자 계정에 라이선스 할당](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)을 참조 하세요.

7. 다음으로 비즈니스용 Skype를 사용 하 여 디바이스 계정을 사용 하도록 설정 해야 합니다. 환경이 [Microsoft 팀 회의실 요구 사항](requirements.md)에 정의 된 요구 사항을 충족 하는지 확인 합니다.

   다음과 같이 원격 [Windows PowerShell 세션](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 을 시작 합니다 (비즈니스용 [Skype Online PowerShell 구성 요소를 설치](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)해야 하는 경우).

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   다음 cmdlet을 실행 하 여 비즈니스용 Skype Server에 대해 Microsoft 팀 대화방 계정을 사용 하도록 설정 합니다.

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   이 예제에 표시 된 대로 새 사용자 계정을 설정 하 여 RegistrarPool 정보를 가져옵니다.

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > 새 사용자 계정이 테 넌 트에서 기존 사용자 계정과 동일한 등록자 풀에 만들어지지 않을 수 있습니다. 위의 명령은이 문제 때문에 계정 설정 오류를 방지 합니다.

Microsoft 팀 또는 비즈니스용 Skype Online에서 Microsoft 팀 회의실 계정을 사용할 수 있도록 앞의 단계를 완료 한 후에 Microsoft 팀 대화방 장치에 라이선스를 할당 해야 합니다. Office 365 관리 포털을 사용 하 여 비즈니스용 Skype Online (계획 2) 또는 비즈니스용 Skype Online (계획 3) 라이선스를 장치에 할당 합니다.

### <a name="assign-a-license-to-your-account"></a>계정에 라이선스 할당

1. 테 넌 트 관리자로 로그인 하 고, Office 365 관리 포털을 열고, 관리 앱을 클릭 합니다.

2. **사용자 및 그룹** 을 클릭 한 다음 **사용자 추가, 암호 다시 설정**등을 클릭 합니다.

3. Microsoft 팀 대화방 계정을 선택한 다음 펜 아이콘을 클릭 하거나 탭 하 여 편집을 의미 합니다.

4. **라이선스** 옵션을 클릭 합니다.

5. 라이선스 **할당** 섹션에서 사용권 및 Enterprise Voice 필요 조건에 따라 비즈니스용 skype Online (계획 2) 또는 비즈니스용 skype Online (계획 3)을 선택 해야 합니다. Microsoft 팀 방에 클라우드 PBX를 사용 하려면 요금제 3 라이선스를 사용 해야 합니다. 최소한 음성 연결에는 CloudPBX가 필요 합니다. 그런 다음 PSTN 연결 방법을 기반으로 하이브리드 음성 또는 PSTN 통화를 구성 합니다. 자세한 내용은 [Microsoft 팀 공간 라이선스](rooms-licensing.md) 를 참조 하세요.

6. **저장** 을 클릭 하 여 작업을 완료 합니다.

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>샘플: Exchange Online 및 비즈니스용 Skype Online의 채팅방 계정 설정

Exchange Online PowerShell 명령:

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Azure Active Directory PowerShell 명령:

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

비즈니스용 Skype PowerShell 명령:

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> 이렇게 하면 CloudPBX와 PSTNCallingDomesticAndInternational이 추가 됩니다. 또한 관리자 인터페이스를 사용 하 여 전화 번호를 할당 해야 합니다.

## <a name="validate"></a>Validate

유효성 검사를 위해 Skype for Business 클라이언트를 사용 하 여 만든 계정에 로그인 할 수 있습니다.

## <a name="see-also"></a>참고 항목

[Microsoft 팀 대화방 계정 구성](rooms-configure-accounts.md)

[Microsoft 팀 회의실 계획](rooms-plan.md)

[Microsoft 팀 대화방 배포](rooms-deploy.md)

[Microsoft 팀 대화방 콘솔 구성](console.md)

[Microsoft 팀 대화방 관리](rooms-manage.md)

[Microsoft 팀 대화방 라이선스](rooms-licensing.md)
