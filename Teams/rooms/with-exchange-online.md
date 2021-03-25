---
title: Exchange Online을 통해 Microsoft Teams Rooms 배포
ms.author: dstrome
author: dstrome
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
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Exchange Online 및 비즈니스용 Skype 서버온-프레미스를 통해 Microsoft Teams Rooms를 배포하는 방법에 대한 자세한 내용은 이 항목을 참조하세요.
ms.openlocfilehash: 5e3446349be8aaef666c02c73370758027736181
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117346"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Exchange Online을 통해 Microsoft Teams Rooms 배포

Exchange Online 및 비즈니스용 Skype 서버온-프레미스를 통해 Microsoft Teams Rooms를 배포하는 방법에 대한 자세한 내용은 이 항목을 참조하세요.
  
조직에 일부 호스팅되는 일부 프레미스 및 온라인에서 호스팅되는 서비스가 혼합된 경우 구성은 각 서비스가 호스트되는 위치에 따라 다릅니다. 이 항목에서는 Exchange가 온라인으로 호스팅된 Microsoft Teams Rooms에 대한 하이브리드 배포에 대해 설명합니다. 이 유형의 배포에는 다양한 변형이 있으므로 모든 배포에 대한 자세한 지침을 제공할 수 없습니다. 다음 프로세스는 여러 구성에 대해 작동할 것입니다. 프로세스가 설정에 맞지 않는 경우 여기에서 설명한 Windows PowerShell 다른 배포 옵션과 동일한 최종 결과를 달성하기 위해 이 프로세스를 사용하는 것이 좋습니다.

사용자 계정을 설정하는 가장 쉬운 방법은 원격 계정을 사용하여 Windows PowerShell. Microsoft는 [ ](https://go.microsoft.com/fwlink/?linkid=870105)SkypeRoomProvisioningScript.ps1Microsoft Teams Rooms 사용자 계정으로 전환할 수 있도록 새 사용자 계정을 만들거나 기존 리소스 계정의 유효성을 검사하는 데 도움이 되는 스크립트인 스크립트를 제공합니다. 원하는 경우 아래 단계를 수행하여 Microsoft Teams Rooms 디바이스에서 사용할 계정을 구성할 수 있습니다.

## <a name="requirements"></a>요구 사항

Exchange Online을 통해 Microsoft Teams Rooms를 배포하기 전에 요구 사항을 충족해야 합니다. 자세한 내용은 [Microsoft Teams Rooms 요구 사항 을 참조하세요.](requirements.md)
  
Exchange Online을 통해 Microsoft Teams Rooms를 배포하는 경우 아래 단계를 따릅니다. 연결된 cmdlet을 실행할 수 있는 권한이 있는지 확인 합니다. 

   > [!NOTE]
   >  이 섹션의 Windows PowerShell [cmdlet에](/powershell/azure/active-directory/overview?view=azureadps-1.0) 대한 Azure Active Directory 모듈(예: Set-MsolUser)은 Microsoft Teams Rooms 디바이스에 대한 계정을 설정하는 데 테스트되었습니다. 다른 cmdlet이 작동할 수 있습니다. 그러나 이 특정 시나리오에서는 테스트되지 않은 것입니다.

AD FS(Active Directory Federation Services)를 배포한 경우 이러한 단계를 수행하기 전에 사용자 계정을 관리 사용자로 변환한 다음, 이 단계를 완료한 후 사용자를 페더리드 사용자로 다시 변환해야 할 수 있습니다.
  
### <a name="create-an-account-and-set-exchange-properties"></a>계정 만들기 및 Exchange 속성 설정

1. PC에서 원격 Windows PowerShell 시작하고 다음과 같이 Exchange Online에 연결합니다.

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. 세션을 설정한 후 새 사서함을 만들고 RoomMailboxAccount로 사용하도록 설정하거나 기존 방 사서함에 대한 설정을 변경합니다. 이렇게 하면 계정이 Microsoft Teams Rooms에 인증할 수 있습니다.

   기존 리소스 사서함을 변경하는 경우:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    새 리소스 사서함을 만드는 경우:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 모임 환경을 개선하려면 다음과 같이 사용자 계정에서 Exchange 속성을 설정해야 합니다.

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>프레미스 도메인 계정에 대한 전자 메일 주소 추가

1. **Active Directory 사용자 및 컴퓨터 AD** 도구에서 Microsoft Teams Rooms 계정이 생성될 컨테이너 또는 조직 단위를 마우스 오른쪽 단추로 클릭하고 새 를 클릭한 다음 사용자 를 **클릭합니다.** 
2. 이전 cmdlet(Set-사서함 또는 새로-사서함)의 표시 이름(-  ID)을 전체 이름 상자에 입력하고 별칭을 사용자 로그온 이름 상자에 **입력합니다.** 다음 **을 클릭합니다.**
3. 이 계정에 대한 암호를 입력합니다. 확인을 위해 다시 타이프해야 합니다. 암호가 **만료되지** 않는지 확인란만 선택해야 합니다.

    > [!NOTE]
    > 암호가  만료되지 않는 경우 Microsoft Teams Rooms에서 비즈니스용 Skype 서버의 요구 사항입니다. 도메인 규칙은 만료되지 않는 암호를 금지할 수 있습니다. 그렇다면 각 Microsoft Teams Rooms 사용자 계정에 대한 예외를 만들어야 합니다.
  
4. **완료를** 클릭하여 계정을 만들 수 있습니다.
5. 계정을 만든 후 디렉터리 동기화를 실행합니다. PowerShell에서 [Set-MsolDirSyncConfiguration을](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) 사용하여 수행할 수 있습니다. 이 작업을 완료하면 사용자 페이지로 이동하여 이전 단계에서 만든 두 계정이 병합된지 확인해야 합니다.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Microsoft 365 또는 Office 365 라이선스 할당

1. 먼저 Azure AD에 연결하여 일부 계정 설정을 적용합니다. 이 cmdlet을 실행하여 연결할 수 있습니다. Active Directory에 대한 자세한 내용은 [Azure ActiveDirectory(MSOnline) 1.0 을 참조하세요.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0은](/powershell/azure/active-directory/overview?view=azureadps-2.0) 지원되지 않습니다.

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. 사용자 계정에는 Exchange 및 비즈니스용 Skype 서버가 작동하도록 유효한 Microsoft 365 또는 Office 365 라이선스가 있어야 합니다. 라이선스가 있는 경우 사용자 계정에 사용 위치를 할당해야 합니다. 그러면 계정에 사용할 수 있는 라이선스 SKUS가 결정됩니다. 다음 단계에서 과제를 지정합니다.
3. 다음으로, `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> Microsoft 365 또는 Office 365 조직에 사용할 수 있는 SK의 목록을 검색합니다.
4. SKUS를 나열하면 다음을 사용하여 라이선스를 추가할 수 있습니다. `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet입니다. 이 경우 $strLicense SKU 코드입니다(예: contoso:STANDARDPACK). 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>비즈니스용 Skype 서버로 사용자 계정 사용

1. 다음과 같이 pc에서 원격 Windows PowerShell 세션을 만들 수 있습니다.

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

2. 비즈니스용 Skype 서버용 Microsoft Teams Rooms 계정을 사용하도록 설정하려면 다음 명령을 실행합니다.

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    환경에서 RegistrarPool 매개 변수에 사용할 값이 확실하지 않은 경우 이 명령을 사용하여 기존 비즈니스용 Skype Server 사용자로부터 값을 얻을 수 있습니다.

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Microsoft Teams Rooms 계정에 비즈니스용 Skype 서버 라이선스 할당

1. 테넌트 관리자로 로그인하고 Microsoft 365 관리 센터를 열고 관리자 앱을 클릭합니다.
2. 사용자 및 **그룹을 클릭한** 다음 사용자 추가, 암호 재설정 **등 을 클릭합니다.**
3. Microsoft Teams Rooms 계정을 클릭한 다음 펜 아이콘을 클릭하여 계정 정보를 편집합니다.
4. 라이선스를 **클릭합니다.**
5. 라이선스 **할당에서** 라이선스 및 요구 사항에 따라 비즈니스용 Skype(계획 2) 또는 비즈니스용 Skype(계획 3)를 Enterprise Voice 선택합니다. Microsoft Teams Rooms에서 사용하려는 경우 계획 3 라이선스를 Enterprise Voice 합니다.
6. **저장** 을 클릭합니다.

유효성 검사를 위해 비즈니스용 Skype 클라이언트를 사용하여 이 계정에 로그인할 수 있습니다.

> [!NOTE]
> 현재 오디오 회의 또는 전화 시스템 및 전화 요금제와 함께 비즈니스용 Skype 계획 2에서 E1, E3, E4 또는 E5 SKUS를 사용하는 경우 이러한 SK는 계속 작동됩니다. 그러나 현재 라이선스가 만료된 후 Teams Meeting [Room 라이선스 업데이트에](rooms-licensing.md)설명된 바와 같이 더 간단한 라이선스 모델로 이동하는 것이 고려해야 합니다.

> [!IMPORTANT]
> 비즈니스용 Skype 요금제 2를 사용하는 경우 비즈니스용 Skype 전용 모드에서만 Microsoft Teams Rooms를 사용할 수 있습니다. 즉, 모든 모임은 비즈니스용 Skype 모임입니다. Microsoft Teams 모임에 회의실을 사용하도록 설정하려면 회의실 라이선스를 구입하는 것이 좋습니다.
  
## <a name="related-topics"></a>관련 항목

[Microsoft Teams Rooms에 대한 계정 구성](rooms-configure-accounts.md)

[Microsoft Teams 룸 계획](rooms-plan.md)
  
[Microsoft Teams 룸 배포](rooms-deploy.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)