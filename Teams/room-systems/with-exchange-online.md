---
title: Exchange Online을 사용 하 여 Microsoft 팀 대화방 배포
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Exchange Online을 사용 하 여 Microsoft 팀 회의실을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: c9192dad3ffc8cb45a5b4a213865a1daa998075d
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952491"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Exchange Online을 사용 하 여 Microsoft 팀 대화방 배포

Exchange Online과 비즈니스용 Skype Server 온-프레미스를 사용 하 여 Microsoft 팀 회의실을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
  
조직에서 서비스를 혼합 하 여 온-프레미스 호스트와 일부 온라인 상태를 갖춘 경우 각 서비스가 호스팅되는 위치에 따라 구성이 달라 집니다. 이 항목에서는 Exchange에서 온라인으로 호스팅되는 Microsoft 팀 회의실에 대 한 하이브리드 배포에 대해 설명 합니다. 이러한 유형의 배포에는 다양 한 변형이 있기 때문에 모든 방법에 대 한 자세한 지침을 제공 하는 것은 불가능 합니다. 다음 프로세스는 여러 구성에서 작동 합니다. 프로세스가 설정에 적합 하지 않은 경우에는 Windows PowerShell을 사용 하 여 여기에 명시 된 것과 다른 배포 옵션에 대 한 동일한 최종 결과를 얻을 것을 권장 합니다.

사용자 계정을 설정 하는 가장 쉬운 방법은 원격 Windows PowerShell을 사용 하 여 구성 하는 것입니다. Microsoft는 새 사용자 계정을 만들거나, 호환 되는 Microsoft 팀 대화방 사용자 계정으로 전환 하는 데 도움을 주는 기존 리소스 계정이 있는지 확인 하는 데 도움이 되는 [SkypeRoomProvisioningScript. ps1을 제공 합니다.](https://go.microsoft.com/fwlink/?linkid=870105) 원하는 경우 아래 단계에 따라 Microsoft 팀 대화방 장치에서 사용할 계정을 구성할 수 있습니다.

## <a name="requirements"></a>요구 사항

Exchange Online을 사용 하 여 Microsoft 팀 회의실을 배포 하기 전에 요구 사항을 충족 해야 합니다. 자세한 내용은 [Microsoft 팀 공간 요구 사항을](requirements.md)참조 하세요.
  
Exchange Online을 사용 하 여 Microsoft 팀 대화방을 배포 하려면 아래 단계를 따르세요. 연결 된 cmdlet을 실행할 수 있는 권한이 있는지 확인 합니다. 

   > [!NOTE]
   >  이 섹션 (예: MsolUser)의 [Windows PowerShell 용 Azure Active Directory 모듈](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) 은 Microsoft 팀 회의실 장치에 대 한 계정 설정에서 테스트를 거쳤습니다. 그러나이 특정 시나리오에서 테스트 하지 않은 경우에도 다른 cmdlet이 작동할 수 있습니다.
  
### <a name="create-an-account-and-set-exchange-properties"></a>계정 만들기 및 Exchange 속성 설정

1. PC에서 원격 Windows PowerShell 세션을 시작 하 고 아래와 같이 Exchange Online에 연결 합니다.

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
Import-PSSession $Session -DisableNameChecking
```

2. 세션을 설정한 후 새 사서함을 만들고이를 RoomMailboxAccount 사용 하도록 설정 하거나 기존 회의실 사서함에 대 한 설정을 변경할 수 있습니다. 이렇게 하면 계정이 Microsoft 팀 방에 인증 될 수 있습니다.

   기존 리소스 사서함을 변경 하려면 다음을 수행 합니다.

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    새 리소스 사서함을 만드는 경우:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 모임 환경을 개선 하려면 다음과 같이 사용자 계정에 Exchange 속성을 설정 해야 합니다.

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>온-프레미스 도메인 계정에 대 한 전자 메일 주소 추가

1. **Active Directory 사용자 및 컴퓨터 광고** 도구에서 Microsoft 팀 대화방 계정이 생성 될 조직 구성 단위 또는 컨테이너를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 클릭 한 다음 **사용자**를 클릭 합니다.
2. 이전 cmdlet ((사서함 또는 새 사서함)의 표시 이름 (-Id)을 **전체 이름** 상자에 입력 하 고 별칭을 **사용자 로그온 이름** 상자에 설정 합니다. **다음**을 클릭 합니다.
3. 이 계정에 대 한 암호를 입력 합니다. 확인을 위해 암호를 다시 입력 해야 합니다. **암호 사용 기간 제한 없음** 확인란이 선택 되어 있는지 확인 합니다.

    > [!NOTE]
    > **암호 사용 기간 제한 없음** 선택은 Microsoft 팀 대화방의 비즈니스용 Skype 서버에 대 한 요구 사항입니다. 도메인 규칙에 따라 만료 되지 않는 암호가 금지 될 수 있습니다. 그렇다면 각 Microsoft 팀 대화방 사용자 계정에 대 한 예외를 만들어야 합니다.
  
4. **마침을** 클릭 하 여 계정을 만듭니다.
5. 계정을 만든 후 디렉터리 동기화를 실행 합니다. PowerShell에서 [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) 를 사용 하 여이 작업을 수행할 수 있습니다. 이 작업이 완료 되 면 사용자 페이지로 이동 하 여 이전 단계에서 만든 두 계정이 병합 되었는지 확인 합니다.

### <a name="assign-an-office-365-license"></a>Office 365 라이선스 할당

1. 먼저 Azure AD에 연결 하 여 일부 계정 설정을 적용 합니다. 이 cmdlet을 실행 하 여 연결할 수 있습니다. Active Directory에 대 한 자세한 내용은 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)을 참조 하세요. 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) 는 지원 되지 않습니다. 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. 사용자 계정에는 비즈니스용 Exchange 및 비즈니스용 Skype 서버를 사용할 수 있도록 유효한 Office 365 라이선스가 있어야 합니다. 라이선스가 있는 경우 사용 위치를 사용자 계정에 할당 해야 하며,이는 계정에 사용할 수 있는 라이선스 Sku를 결정 합니다. 다음 단계에서 과제를 만듭니다.
3. 다음으로 다음을 사용 합니다.`Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> Office 365 테 넌 트에 대해 사용 가능한 Sku 목록을 검색 합니다.
4. Sku를 나열 하면 다음을 사용 하 여 라이선스를 추가할 수 있습니다.`Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> 은. 이 경우 $strLicense는 사용자에 게 표시 되는 SKU 코드입니다 (예: contoso: STANDARDPACK). 

  ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>비즈니스용 Skype 서버에서 사용자 계정 사용

1. PC에서 원격 Windows PowerShell 세션을 다음과 같이 만듭니다.

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. 비즈니스용 Skype Server에 대해 Microsoft 팀 대화방 계정을 사용 하도록 설정 하려면 다음 명령을 실행 합니다.

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    환경에서 RegistrarPool 매개 변수에 어떤 값을 사용 해야 하는지 확실 하지 않은 경우이 명령을 사용 하 여 기존 비즈니스용 Skype Server 사용자의 값을 가져올 수 있습니다.

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Microsoft 팀 대화방 계정에 비즈니스용 Skype 서버 라이선스 할당

1. 테 넌 트 관리자로 로그인 하 고, Office 365 관리 포털을 열고, 관리 앱을 클릭 합니다.
2. **사용자 및 그룹** 을 클릭 한 다음 **사용자 추가, 암호 다시 설정**등을 클릭 합니다.
3. Microsoft 팀 대화방 계정을 클릭 한 다음 펜 아이콘을 클릭 하 여 계정 정보를 편집 합니다.
4. **라이선스**를 클릭 합니다.
5. 라이선스 **할당**에서 라이선스 및 엔터프라이즈 음성 요구 사항에 따라 비즈니스용 Skype (계획 2) 또는 비즈니스용 Skype (계획 3)를 선택 합니다. Microsoft 팀 방에 Enterprise 음성을 사용 하려면 요금제 3 라이선스를 사용 해야 합니다.
6. **저장**을 클릭 합니다.

유효성 검사를 위해 비즈니스용 Skype 클라이언트를 사용 하 여이 계정에 로그인 할 수 있습니다.
  
## <a name="see-also"></a>참고 항목

[Microsoft 팀 대화방 계정 구성](room-systems-v2-configure-accounts.md)

[Microsoft 팀 회의실 계획](skype-room-systems-v2-0.md)
  
[Microsoft 팀 대화방 배포](room-systems-v2.md)
  
[Microsoft 팀 대화방 콘솔 구성](console.md)
  
[Microsoft 팀 대화방 관리](skype-room-systems-v2.md)
