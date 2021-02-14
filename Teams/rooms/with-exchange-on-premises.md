---
title: Exchange를 통해 Microsoft Teams 회의실 배포
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
description: Exchange를 통해 하이브리드 환경에서 Microsoft Teams 회의실을 배포하는 방법에 대한 자세한 내용은 이 항목을 참조하세요.
ms.openlocfilehash: f9f80f5b993b9be95e35c8178d996973558e2512
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662323"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Exchange를 통해 Microsoft Teams 회의실 배포

Exchange On-Premises 및 Microsoft Teams 또는 비즈니스용 Skype Online을 통해 하이브리드 환경에서 Microsoft Teams 회의실을 배포하는 방법에 대한 자세한 내용은 이 항목을 참조하세요.
  
조직에 일부 호스팅된 일부 서비스가 온라인에서 호스팅되는 혼합 서비스가 있는 경우 구성은 각 서비스가 호스트되는 위치에 따라 다릅니다. 이 항목에서는 Exchange가 호스트된 Microsoft Teams Rooms의 하이브리드 배포에 대해 설명합니다. 이 유형의 배포에는 다양한 변형이 있으므로 모든 배포에 대한 자세한 지침을 제공할 수 없습니다. 다음 프로세스는 많은 구성에 대해 작동됩니다. 프로세스가 설정에 맞지 않는 경우 여기에서 설명한 Windows PowerShell 다른 배포 옵션에 대해 동일한 최종 결과를 달성하기 위해 이 프로세스를 사용하는 것이 좋습니다.

Microsoft는 [ ](https://go.microsoft.com/fwlink/?linkid=870105)SkypeRoomProvisioningScript.ps1계정을 만들거나 호환되는 Microsoft Teams Rooms 사용자 계정으로 전환할 수 있도록 기존 리소스 계정의 유효성을 검사하는 데 도움이 되는 스크립트인 스크립트를 제공합니다. 원하는 경우 아래 단계에 따라 Microsoft Teams 회의실 장치에서 사용할 계정을 구성할 수 있습니다.
  
## <a name="requirements"></a>요구 사항

Exchange를 통해 Microsoft Teams Rooms를 배포하기 전에 요구 사항을 충족해야 합니다. 자세한 내용은 Microsoft Teams 회의실 요구 [사항을 참조하세요.](requirements.md)
  
Exchange가 있는 Microsoft Teams Rooms를 프레미스에 배포하는 경우 Active Directory 관리 도구를 사용하여 전자 메일 주소를 추가합니다. 이 계정은 Microsoft 365 또는 Office 365와 동기화됩니다. 다음이 필요합니다.
  
- 계정을 만들고 Active Directory와 계정을 동기화합니다.

- 원격 사서함을 사용하도록 설정하고 속성을 설정합니다.

- Microsoft 365 또는 Office 365 라이선스를 할당합니다.

- 비즈니스용 Skype Server에서 장치 계정을 사용하도록 설정 디바이스 계정을 사용하도록 설정하려면 환경이 다음 요구 사항을 충족해야 합니다.

  - Microsoft 365 또는 Office 365 요금제에는 비즈니스용 Skype Online(계획 2) 이상이 필요합니다. 계획은 회의 기능을 지원해야 합니다.
  
  - Microsoft Teams Enterprise Voice 통신 서비스 공급자를 사용하여 PSTN 전화 통신(PSTN 전화 통신)이 필요한 경우 비즈니스용 Skype Online(계획 3)이 필요합니다.
  
  - 테넌트 사용자에게 Exchange 사서함이 있어야 합니다.
  
  - Microsoft Teams 회의실 계정에는 비즈니스용 Skype Online(계획 2) 또는 비즈니스용 Skype Online(계획 3) 라이선스가 필요하지만 Exchange Online 라이선스가 필요하지 않습니다.

- Microsoft Teams Rooms 계정에 비즈니스용 Skype Server 라이선스를 할당합니다.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>계정 만들기 및 Active Directory와 동기화

1. Active **Directory** 사용자 및 컴퓨터 도구에서 Microsoft Teams 회의실 계정을 만들 폴더 또는 조직 구성 단위를 마우스 오른쪽 단추로 클릭하고 새로 고른 다음 사용자를 **클릭합니다.**

2. 이전 cmdlet의 표시 이름을 전체  이름 상자에 입력하고 사용자 로그온 이름 상자에 **별칭을 입력합니다.** 다음을 **클릭합니다.**

3. 이 계정의 암호를 입력합니다. 확인을 위해 다시 추가해야 합니다. 암호가 **만료되지** 않는지 확인란이 선택된 유일한 옵션인지 확인란을 선택합니다.

    > [!NOTE]
    > 암호 **선택은** Microsoft Teams 회의실의 비즈니스용 Skype Server에 대한 요구 사항입니다. 도메인 규칙은 만료되지 않는 암호를 금지할 수 있습니다. 그렇다면 각 Microsoft Teams Rooms 장치 계정에 대한 예외를 만들어야 합니다.
  
4. 계정을 만든 후 디렉터리 동기화를 실행합니다. 완료되면 Microsoft 365 관리 센터의 사용자 페이지로 이동하여 이전 단계에서 만든 계정이 온라인에 병합된 것을 확인할 수 있습니다.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>원격 사서함을 사용하도록 설정하고 속성 설정

1. [Exchange 관리 셸을 열거나](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) [원격 PowerShell을 사용하여 Exchange 서버에 연결합니다.](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. Exchange PowerShell에서 다음 명령을 실행하여 계정에 대한 사서함(사서함 사용 계정)을 생성합니다.

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   자세한 구문 및 매개 변수 정보는 [사용-사서함을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)

3. Exchange PowerShell에서 회의실 사서함에서 다음 설정을 구성하여 모임 환경을 개선합니다.

   - AutomateProcessing: AutoAccept(모임 이끌이는 사용자 개입 없이 바로 회의실 예약 결정을 수신합니다. 무료 = 수락, 사용 중 = 거절).

   - AddOrganizerToSubject: $false(모임 이끌이는 모임 요청의 제목에 추가되지 않습니다.)

   - DeleteComments: $false(들어오는 모임 요청의 메시지 본문에 텍스트를 보관합니다.)

   - DeleteSubject: $false(들어오는 모임 요청의 제목 유지)

   - RemovePrivateProperty: $false(원래 모임 요청에서 모임 이끌이가 보낸 개인 플래그가 지정된 상태로 유지되도록 합니다.)

   - AddAdditionalResponse: $true(AdditionalResponse 매개 변수로 지정된 텍스트가 모임 요청에 추가됩니다.)

   - AdditionalResponse: "Skype 회의실입니다!" (모임 요청에 추가할 추가 텍스트입니다.)

   이 예제에서는 Project-Rigel-01이라는 방 사서함에서 이러한 설정을 구성합니다.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   자세한 구문 및 매개 변수 정보는 [Set-CalendarProcessing을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="assign-a-microsoft-365-or-office-365-license"></a>Microsoft 365 또는 Office 365 라이선스 할당

1. Azure Active Directory에 연결합니다. Active Directory에 대한 자세한 내용은 [Azure ActiveDirectory(MSOnline) 1.0을 참조하세요.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0은](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) 지원되지 않습니다. 

2. 장치 계정에 유효한 Microsoft 365 또는 Office 365 라이선스가 있어야 합니다. 또는 Exchange 및 Microsoft Teams가 작동하지 않습니다. 라이선스가 있는 경우 사용 위치를 디바이스 계정에 할당해야 합니다. 그러면 계정에 사용할 수 있는 라이선스 SKUS가 결정됩니다. 다음을 사용할 수 있습니다. `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 를 사용하여 사용 가능한 SKUS 목록을 검색합니다.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. 다음으로, `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. 이 경우 $strLicense SKU 코드입니다(예: contoso:STANDARDPACK).

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

   자세한 지침은 [Office 365 PowerShell을](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)통해 사용자 계정에 라이선스 할당을 참조하세요.

### <a name="enable-the-device-account"></a>디바이스 계정 사용

비즈니스용 Skype Online PowerShell은 Microsoft Teams와 비즈니스용 Skype Online 모두에 대한 서비스를 관리하는 데 사용됩니다.

1. 다음과 같이 PC에서 Windows PowerShell 세션을 만들 수 있습니다.
> [!NOTE]
> 비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.
>
> 최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. 계정의 SIP 주소를 구합니다.

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. Microsoft Teams 회의실 계정을 사용하도록 설정하려면 다음 명령을 실행합니다.

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   사용자 환경에서 RegistrarPool 매개 변수에 사용할 값을 확실하지 않은 경우 다음 명령을 사용하여 기존 사용자로부터 값을 얻을 수 있습니다.

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Microsoft Teams 회의실 계정에 라이선스 할당

1. 테넌트 관리자로 로그인하고 Microsoft 365 관리 센터를 열고 관리 앱을 클릭합니다.
2. 사용자 및 **그룹을 클릭한** 다음 사용자 추가, 암호 재설정을 **클릭합니다.**
3. Microsoft Teams 회의실 계정을 클릭한 다음 펜 아이콘을 클릭하여 계정 정보를 편집합니다.
4. 라이선스를 **클릭합니다.**
5. 라이선스 **할당에서** 라이선스 및 라이선스 요구 사항에 따라 비즈니스용 Skype(계획 2) 또는 비즈니스용 Skype(계획 3)를 Enterprise Voice 선택합니다. Microsoft Teams 회의실에서 요금제 3 라이선스를 Enterprise Voice 합니다.
6. **저장** 을 클릭합니다.

유효성 검사를 위해 모든 클라이언트를 사용하여 이 계정에 로그인할 수 있습니다.
  
## <a name="related-topics"></a>관련 항목

[Microsoft Teams 회의실에 대한 계정 구성](rooms-configure-accounts.md)

[Microsoft Teams 룸 계획](rooms-plan.md)
  
[Microsoft Teams 룸 배포](rooms-deploy.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)
