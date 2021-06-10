---
title: Microsoft Teams 룸 Exchange 배포
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
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: 이 항목을 참조하여 Microsoft Teams 룸 하이브리드 환경에서 배포하는 방법에 Exchange 있습니다.
ms.openlocfilehash: 3931ba89dd4ad0dfd994fdf27a3f209275850116
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117356"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Microsoft Teams 룸 Exchange 배포

이 항목에서는 온라인에서 Microsoft Teams 룸 및 Exchange 하이브리드 환경에서 Microsoft Teams 비즈니스용 Skype 참조하세요.
  
조직에 일부 호스팅되는 일부 프레미스 및 온라인에서 호스팅되는 서비스가 혼합된 경우 구성은 각 서비스가 호스트되는 위치에 따라 다릅니다. 이 항목에서는 프레미스에서 호스팅되는 Microsoft Teams 룸 Exchange 하이브리드 배포에 대해 설명합니다. 이 유형의 배포에는 다양한 변형이 있으므로 모든 배포에 대한 자세한 지침을 제공할 수 없습니다. 다음 프로세스는 여러 구성에 대해 작동할 것입니다. 프로세스가 설정에 맞지 않는 경우 여기에서 설명한 Windows PowerShell 및 다른 배포 옵션에 대해 동일한 최종 결과를 달성하기 위해 이 프로세스를 사용하는 것이 좋습니다.

Microsoft는 [ ](https://go.microsoft.com/fwlink/?linkid=870105)SkypeRoomProvisioningScript.ps1사용자 계정으로 전환할 수 있도록 새 사용자 계정을 만들거나 기존 리소스 계정의 유효성을 검사하는 데 도움이 되는 Microsoft Teams 룸 제공합니다. 원하는 경우 아래 단계를 수행하여 디바이스에서 사용할 계정을 Microsoft Teams 룸 수 있습니다.
  
## <a name="requirements"></a>요구 사항

Microsoft Teams 룸 Exchange 배포하기 전에 요구 사항을 충족해야 합니다. 자세한 내용은 요구 사항 [Microsoft Teams 룸 참조하세요.](requirements.md)
  
Microsoft Teams 룸 Exchange 배포하는 경우 Active Directory 관리 도구를 사용하여 프레미스 도메인 계정에 대한 전자 메일 주소를 추가합니다. 이 계정은 Microsoft 365 또는 Office 365. 다음이 필요합니다.
  
- 계정을 만들고 Active Directory와 계정을 동기화합니다.

- 원격 사서함을 사용하도록 설정하고 속성을 설정합니다.

- 라이선스 또는 Microsoft 365 Office 365 할당합니다.

- 디바이스 계정을 비즈니스용 Skype 서버. 디바이스 계정을 사용하도록 설정하려면 환경이 다음 요구 사항을 충족해야 합니다.

  - 온라인 또는 비즈니스용 Skype(계획 2) 이상이 Microsoft 365 Office 365 합니다. 계획은 회의 기능을 지원해야 합니다.
  
  - 전화 통신 서비스 공급자를 Enterprise Voice(PSTN 전화 통신)가 필요한 경우 Microsoft Teams 룸 온라인(계획 3)비즈니스용 Skype 필요합니다.

  - 온라인 또는 Microsoft Teams 비즈니스용 Skype 룸 계정을 구성할 경우, 계정이 룸 계정으로 사용하도록 설정하기 전에 전화 번호를 할당해야 합니다.
  
  - 테넌트 사용자에게 사서함이 Exchange 있어야 합니다.
  
  - Microsoft Teams 룸 계정에는 비즈니스용 Skype(계획 2) 또는 비즈니스용 Skype(계획 3) 라이선스가 필요하지만 라이선스가 Exchange Online 없습니다.

- 비즈니스용 Skype 서버 계정에 Microsoft Teams 룸 할당합니다.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>계정 만들기 및 Active Directory와 동기화

1. Active **Directory** 사용자 및 컴퓨터 도구에서 사용자 계정이 생성될 폴더 또는 조직 단위를 마우스 오른쪽 단추로 클릭하고 Microsoft Teams 룸 클릭한 다음 사용자 를 **클릭합니다.**

2. 이전 cmdlet의 표시 이름을 전체  이름 상자에 입력하고 별칭을 사용자 로그온 이름 상자에 **입력합니다.** 다음 **을 클릭합니다.**

3. 이 계정에 대한 암호를 입력합니다. 확인을 위해 다시 타이프해야 합니다. 암호가 **만료되지** 않는지 확인란만 선택해야 합니다.

    > [!NOTE]
    > 암호가  만료되지 않는 경우 암호를 선택해야 비즈니스용 Skype 서버 Microsoft Teams 룸. 도메인 규칙은 만료되지 않는 암호를 금지할 수 있습니다. 그렇다면 각 디바이스 계정에 대한 예외를 Microsoft Teams 룸 합니다.
  
4. 계정을 만든 후 디렉터리 동기화를 실행합니다. 완료되면 관리자 센터의 사용자 페이지로 Microsoft 365 이전 단계에서 만든 계정이 온라인에 병합되어 있는지 확인하십시오.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>원격 사서함 사용 및 속성 설정

1. [원격 PowerShell을](/powershell/exchange/exchange-server/open-the-exchange-management-shell) 사용하여 Exchange 관리 셸을 열거나 Exchange 서버에 [연결합니다.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. PowerShell의 Exchange 다음 명령을 실행하여 계정에 대한 사서함(사서함 사용 계정)을 생성합니다.

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   자세한 구문 및 매개 변수 정보는 [사용-사서함 을 참조하세요.](/powershell/module/exchange/mailboxes/enable-mailbox)

3. PowerShell의 Exchange 회의실 사서함에서 다음 설정을 구성하여 모임 환경을 개선합니다.

   - AutomateProcessing: AutoAccept(모임 이끌이는 사용자 개입 없이 직접 회의실 예약 결정을 수신합니다. 무료 = 수락, 사용 중 = 거부).)

   - AddOrganizerToSubject: $false(모임 이끌이가 모임 요청의 제목에 추가되지 않습니다.)

   - DeleteComments: $false(들어오는 모임 요청의 메시지 본문에 텍스트를 보관합니다.)

   - DeleteSubject: $false(들어오는 모임 요청의 제목 유지)입니다.

   - RemovePrivateProperty: $false(원래 모임 요청에서 모임 이끌이가 보낸 개인 플래그가 지정된 상태로 유지되도록 합니다.)

   - AddAdditionalResponse: $true(AdditionalResponse 매개 변수에서 지정한 텍스트가 모임 요청에 추가됩니다.)

   - AdditionalResponse: "이 방은 Skype 모임 방입니다!" (모임 요청에 추가할 추가 텍스트입니다.)

   이 예제에서는 Project-Rigel-01이라는 방 사서함에서 이러한 설정을 구성합니다.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   자세한 구문 및 매개 변수 정보는 [Set-CalendarProcessing 을 참조하세요.](/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="assign-a-microsoft-365-or-office-365-license"></a>라이선스 Microsoft 365 또는 Office 365 할당

1. 커넥트 Azure Active Directory. Active Directory에 대한 자세한 내용은 [Azure ActiveDirectory(MSOnline) 1.0 을 참조하세요.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0은](/powershell/azure/active-directory/overview?view=azureadps-2.0) 지원되지 않습니다. 

2. 디바이스 계정에 유효한 Microsoft 365 Office 365 라이선스가 있어야 Exchange Microsoft Teams 작동하지 않습니다. 라이선스가 있는 경우 디바이스 계정에 사용 위치를 할당해야 합니다. 그러면 계정에 사용할 수 있는 라이선스 SKUS가 결정됩니다. 사용할 수 있습니다. `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 를 사용하여 사용 가능한 SKUS 목록을 검색합니다.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. 다음으로, `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet입니다. 이 경우 $strLicense SKU 코드입니다(예: contoso:STANDARDPACK).

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   자세한 지침은 PowerShell을 통해 사용자 계정에 라이선스 [할당을 Office 365 참조하세요.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="enable-the-device-account"></a>디바이스 계정 사용

비즈니스용 Skype Online PowerShell은 온라인 및 Microsoft Teams 모두에 비즈니스용 Skype 사용됩니다.

1. 다음과 Windows PowerShell PC에서 원격 세션을 만들 수 있습니다.
> [!NOTE]
> 비즈니스용 Skype 온라인 커넥터는 현재 최신 PowerShell Teams 일부입니다.
>
> 최신 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 Teams 사용하는 경우 온라인 커넥터를 비즈니스용 Skype 필요가 없습니다.

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. 계정의 SIP 주소를 구합니다.

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. **선택 사항입니다.** 계정에 전화 번호를 할당하려면 이 시점에서 작업을 수행해야 합니다. 직접 라우팅 전화 번호를 할당하려는 경우:

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    Microsoft에서 제공한 전화 번호를 할당하는 경우 사용자를 호출 계획 라이선스로 프로비전한 후 아래 cmdlet을 사용하세요.
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. Microsoft Teams 룸 계정을 사용하도록 설정하려면 다음 명령을 실행합니다.

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   환경에서 RegistrarPool 매개 변수에 사용할 값이 확실하지 않은 경우 이 명령을 사용하여 기존 사용자로부터 값을 얻을 수 있습니다.

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>사용자 계정에 라이선스 Microsoft Teams 룸 할당

1. 테넌트 관리자로 로그인하고 관리자 Microsoft 365 센터를 열고 관리자 앱을 클릭합니다.
2. 사용자 및 **그룹을 클릭한** 다음 사용자 추가, 암호 재설정 **등 을 클릭합니다.**
3. 계정 Microsoft Teams 룸 클릭한 다음 펜 아이콘을 클릭하여 계정 정보를 편집합니다.
4. 라이선스를 **클릭합니다.**
5. 라이선스 **할당에서** 라이선스 비즈니스용 Skype 요구 사항에 따라 비즈니스용 Skype(계획 2) 또는 비즈니스용 Skype(계획 3)를 Enterprise Voice 선택합니다. 계획 3 라이선스를 사용하려는 경우 Enterprise Voice 라이선스를 Microsoft Teams 룸.
6. **저장** 을 클릭합니다.

유효성 검사의 경우 클라이언트를 사용하여 이 계정에 로그인할 수 있습니다.
  
## <a name="related-topics"></a>관련 항목

[Microsoft Teams 룸](rooms-configure-accounts.md)

[Microsoft Teams 룸 계획](rooms-plan.md)
  
[Microsoft Teams 룸 배포](rooms-deploy.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)