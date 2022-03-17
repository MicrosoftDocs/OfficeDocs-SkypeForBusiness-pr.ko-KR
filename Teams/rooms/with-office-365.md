---
title: 회의실 및 공유 디바이스에 Teams 계정 만들기
ms.author: czawideh
author: cazawideh
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
description: 이 문서에서는 회의실 및 공유 디바이스에 대한 리소스 계정을 만드는 방법에 대한 자세한 내용을 Microsoft Teams 룸 Teams 룸 Surface Hub 디스플레이에서 Teams 있습니다.
ms.openlocfilehash: e7525a9e9ec6737bab18de4351675d567b61611b
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514549"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>회의실 및 공유 디바이스에 대한 리소스 Teams 구성

이 문서에서는 공유 공간 및 디바이스에 대한 리소스 계정을 만드는 단계를 제공합니다. 여기에는 Microsoft Teams 룸 Windows android에서 Teams 룸, Teams 룸 Surface Hub 디스플레이에 Teams 단계가 포함되어 있습니다.

Microsoft 365 리소스 계정은 Teams 또는 프로젝터와 같은 특정 리소스 전용의 사서함 및 계정입니다. 이러한 리소스 계정은 사용자가 만들 때 정의한 규칙을 사용하여 모임 초대에 자동으로 응답할 수 있습니다. 예를 들어 회의실과 같은 공통 리소스가 있는 경우 일정 가용성에 따라 모임 초대를 자동으로 수락하거나 거부하는 해당 회의실에 대한 리소스 계정을 설정할 수 있습니다.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **비즈니스용 Skype** <br><br>
> 리소스 계정을 사용하여 작업하도록 설정해야 하는 경우 비즈니스용 Skype 사용 Microsoft Teams 룸 [비즈니스용 Skype 서버](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>시작하기 전에

### <a name="requirements"></a>요구 사항

환경에 따라 리소스 계정을 만들 때 하나 이상의 역할이 필요합니다.

|**환경**|**필수 역할**|
|-----|-----|
|Azure Active Directory Domain Services  <br/> |전역 관리자 또는 사용자 관리자  <br/> |
|Active Directory  <br/> |Active Directory Enterprise 관리자, 도메인 관리자 또는 사용자를 만들 수 있는 권한을 위임했습니다. Azure Active Directory 커넥트 동기화 권한입니다.  <br/> |
|Exchange Online  <br/> |전역 관리자 또는 Exchange 관리자   <br/> |
|Exchange Server  <br/> |Exchange 관리 또는 받는 사람 관리   <br/> |

사용자에 대한 리소스 계정을 만드는 Teams 룸 UPN은 리소스 계정의 SMTP 주소와 일치해야 합니다. 배포[하기 Microsoft Teams 룸](requirements.md) 요구 사항을 Teams 룸.

### <a name="what-license-do-you-need"></a>어떤 라이선스가 필요한가요?

리소스 계정을 Microsoft 365 전에 필요한 라이선스 종류를 확인하세요.

- **Teams** 모임에서 리소스 계정을 공유 디바이스와 연결하려는 경우(예: Microsoft Teams Teams 핫데스크링과 함께 표시하고 참석자들이 비디오 및 오디오를 표시하는 데 사용할 수 있도록 Teams 모임에 참가하려면 미팅룸 라이선스가 필요합니다. 회의실에 대한 라이선스에 대한 자세한 내용은 라이선스 Teams 미팅룸 [참조하세요](rooms-licensing.md).

- **PSTN 호출** 리소스가 외부 전화 번호(공용 전환 전화 네트워크 또는 PSTN 호출)에 대한 통화를 걸거나 받으려 하는 경우 Microsoft 365 전화 시스템 또는 Microsoft 365 Business Voice 라이선스가 필요합니다. 다음 개요에서 1단계만 완료하면됩니다. 그런 다음 추가 [Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 추가 기능 라이선스를 참조하세요.

- 리소스 계정을&mdash;&mdash; 사용하여 리소스를 예약하는 경우 모임에 리소스를 초대하고 초대를 자동으로 수락하거나 거부할 필요가 없습니다. 리소스 계정에 라이선스를 할당할 필요가 없습니다. 다음 개요에서 1단계만 완료하면 됩니다.  

## <a name="overview"></a>개요

**1단계 -** [새 리소스 계정 만들기](#create-a-resource-account) 또는 룸 사서함이 이미 있으며 리소스 계정으로 변환하려는 경우 기존 룸 사서함을 Exchange [수 있습니다](?tabs=existing-account#create-a-resource-account).

**2단계 -**  그런 다음 모임 [에 대한](#configure-mailbox-properties) 계정을 Teams 구성합니다.

**3단계 -**  리소스 계정이 공유 디바이스와 연결될 경우(예: 핫데스크킹이 Teams 표시) 암호 만료를 [해제합니다](#turn-off-password-expiration).

**4단계 -**  마지막으로, [계정에 액세스할](#assign-a-meeting-room-license) 수 있도록 회의실 라이선스를 Microsoft Teams.

리소스 계정을 만들고 구성한 후 다음 단계를 참조하여 [](#next-steps) 메일 그룹, 네트워크 기능 및 호출을 비롯한 추가 설치 작업을 검토합니다.

## <a name="create-a-resource-account"></a>리소스 계정 만들기

> [!TIP]
> 리소스 계정의 이름을 지을 때 전자 메일 주소의 시작에 표준 이름 규칙을 사용하는 것이 좋습니다. 이렇게 하면 동적 그룹을 만들어 관리하기가 Azure Active Directory. 예를 들어, 모든 리소스 계정에 "mtr-"를 사용할 수 Microsoft Teams 룸.

> [!TIP]
> 모든 리소스 계정을 Exchange Online Azure Active Directory.

다음 탭 중 하나에서 메서드를 사용하여 리소스 계정을 만들 수 있습니다.

#### <a name="in-microsoft-365-admin-center"></a>[**에서 Microsoft 365 관리 센터**](#tab/m365-admin-center)

1. Microsoft 365 관리 센터에 로그인합니다.

2. 테넌트에 대한 관리자 Microsoft 365 제공합니다.

3. 왼쪽 **패널의** 리소스로 이동한 다음, 장비의 & **선택합니다**. 왼쪽 패널에서 이러한 옵션을 사용할 수 없는 경우 먼저 모두 표시 **를 선택해야 할 수** 있습니다.

4. 리소스 **사서함 추가를 선택하여** 새 룸 계정을 만들 수 있습니다. 계정에 대한 표시 이름 및 전자 메일 주소를 입력하고 추가를 **선택한 다음 닫** 기를 **선택합니다**.

5. 기본적으로 리소스 계정은 다음 설정으로 구성됩니다.

    - 반복 모임 허용
    - 다음 제한을 초과하여 모임을 자동으로 거부합니다.
      - 예약 기간(일): 180
      - 최대 기간(시간): 24
    - 모임 요청 자동 수락

    변경하려는 경우 닫기 를 선택하기  전에 일주 옵션 설정을 **선택합니다**. 나중에 변경하려면 **ResourceRooms** >  & 장비로 이동하여 리소스 계정을 선택합니다. 그런 다음 **예약 옵션에서** 편집을 **선택합니다**.

6. **UsersActive** >  **사용자로 이동** 하고 만든 방을 선택하여 속성 패널을 니다.

7. 다음으로, 리소스 계정에 암호를 할당합니다. 패널에서 암호 재설정 **을 선택합니다**.
 
8. 사용자가 공유 디바이스에서 암호를 변경하도록 요구하면 로그인 문제가 발생할 수 있습니다. 이 사용자가 **처음** 로그인할 때 암호를 변경하도록 선택을 선택하지 않은 다음 재설정을 **선택합니다**.

9. 라이선스 및 **앱 섹션** 에서 디바이스가 설치된 국가  또는 지역에 위치 선택을 설정합니다. 그런 다음, 할당할 라이선스(예: 미팅룸)를 선택하고 변경 내용 저장 **을 선택합니다**. 라이선스는 조직에 따라 다를 수 있습니다.

리소스 사서함의 설정을 변경하려면 사서함 속성 구성을 참조[하거나](#configure-mailbox-properties) Exchange 관리 센터를 사용합니다.

이 계정에 대역폭 정책 또는 모임 정책을 적용해야 할 수도 있습니다. 자세한 [내용은 다음](#next-steps) 단계를 참조하세요.

#### <a name="with-exchange-online"></a>[**Exchange Online**](#tab/exchange-online)

1. 커넥트 [PowerShell을 Exchange Online 수 있습니다](/powershell/exchange/connect-to-exchange-online-powershell).

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. 기본적으로 룸 사서함에는 연결된 계정이 없습니다. 룸 사서함을 만들 때 계정을 추가하여 계정으로 인증할 Microsoft Teams.

    새 리소스 사서함을 만드는 경우:
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    이 예제에서는 다음 설정을 사용하여 새 룸 사서함을 만듭니다.

        - Account: ConferenceRoom01@contoso.com
          
        - Name: ConferenceRoom01
        
        - Alias: ConferenceRoom01
        
        - Account password: P@$$W0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

하이브리드 구성에 Exchange 경우 다음 단계인 사서함 속성 구성을 계속할 [수 있습니다](#configure-mailbox-properties).

하이브리드 구성의 경우 Exchange 도메인 계정에 대한 전자 메일 주소를 추가해야 합니다. 자세한 [내용은 Office 365 사용자 계정 Office 365 동기화](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)를 참조하세요.

#### <a name="with-exchange-server"></a>[**Exchange Server**](#tab/exchange-server)

  1. 커넥트 셸을 Exchange 합니다. [원격 PowerShell](/powershell/exchange/exchange-server/open-the-exchange-management-shell)을 사용하여 Exchange 관리 셸을 열거나 Exchange 서버에 [연결합니다](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

   2. 새 방 사서함을 만들 경우:

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```
     
   이 예제에서는 다음 설정을 사용하여 새 룸 사서함을 만듭니다.

   - 계정: ConferenceRoom01@contoso.com
  
   - 이름: ConferenceRoom01

   - 별칭: ConferenceRoom01

   - 계정 암호: P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**기존 Exchange 사서함 수정**](#tab/existing-account)

기존 룸 사서함을 리소스 계정으로 수정하려면 다음 구문을 사용하세요.

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

이 예제에서는 별칭 값이 ConferenceRoom02인 기존 회의실 사서함의 계정을 사용할 수 있으며 암호를 9898P@$$W 0rd로 설정합니다.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

하이브리드 구성에 Exchange 경우 프레미스 도메인 계정에 대한 전자 메일 주소를 추가해야 합니다. 자세한 [내용은 Office 365 사용자 계정 Office 365 동기화](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)를 참조하세요.

자세한 구문 및 매개 변수 정보는 [New-사서함](/powershell/module/exchange/mailboxes/new-mailbox) 및 [Set-사서함을 참조하세요](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> 이 계정의 Teams 룸에 Surface Hub 경우 이 계정에서도 ActiveSync를 사용하도록 설정해야 합니다. 이렇게 하면 화이트보드와 같은 기능에 사용할 수 있는 Surface Hub 전자 메일을 직접 보낼 수 있습니다. 자세한 [내용은 디바이스 계정에 ActiveSync](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) 정책 적용(Surface Hub)을 참조하세요.

---

> [!IMPORTANT]
> 이 리소스 계정만 사용하여 공간을 예약하고 초대를 자동으로 수락하거나 거부하는 경우 설정이 완료되었습니다. PSTN 호출에 이 리소스 계정을 사용하는 경우 추가 Microsoft Teams 라이선스를 참조하여 [](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 필요한 라이선스를 확인할 수 있습니다.
>
> 리소스 계정이 android에서 Teams 룸 Windows Teams 룸, Teams 룸 Surface Hub 또는 핫데스크가 Teams 표시하는 Teams 섹션으로 계속합니다.

## <a name="configure-mailbox-properties"></a>사서함 속성 구성

온라인 Exchange On-프레미스인 PowerShell에서 회의실 사서함에서 다음 설정을 구성하여 모임 환경을 개선합니다.

- **AutomateProcessing: `AutoAccept`** 모임 이끌이는 사람이 개입하지 않고 직접 회의실 예약 결정을 받게 됩니다.

- **AddOrganizerToSubject: `$false`** 모임 이끌이는 모임 요청의 제목에 추가되지 않습니다.

- **DeleteComments: `$false`** 들어오는 모임 요청의 메시지 본문에 텍스트를 보관합니다. One Touch Join 환경을 Teams 외부 모임 및 타사 모임을 처리해야 합니다.

- **DeleteSubject: `$false`** 들어오는 모임 요청의 제목을 유지합니다.

- **ProcessExternalMeetingMessages: `$true`** 조직 외부에서 시작되는 모임 요청을 처리할 Exchange 지정합니다. 외부 Teams 모임 및 [타사 모임에 필요합니다](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty: `$false`** 원래 모임 요청에서 모임 이끌이가 보낸 개인 플래그가 지정된 상태로 유지되도록 합니다.

- **AddAdditionalResponse: `$true`** AdditionalResponse 매개 변수에 의해 지정된 텍스트가 모임 요청에 추가됩니다.

- **추가Response: "이 회의실은 Microsoft Teams 있습니다!"** 모임 수락 응답에 추가할 추가 텍스트입니다.

이 예제에서는 ConferenceRoom01이라는 회의실 사서함에서 이러한 설정을 구성합니다.

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

자세한 구문 및 매개 변수 정보는 [Set-CalendarProcesssing을 참조하세요](/powershell/module/exchange/mailboxes/set-calendarprocessing).

## <a name="turn-off-password-expiration"></a>암호 만료 해제

리소스 계정 암호가 만료되면 디바이스는 만료 날짜 이후에 로그인하지 않습니다. 그러면 리소스 계정에 대한 암호를 변경한 다음 각 장치에서 업데이트해야 합니다. 이를 방지하기 위해 암호 만료를 해제할 수 있습니다.
  
> [!NOTE]
> 암호 **설정이 만료** 되지 않는 것은 공유 디바이스에 Microsoft Teams 요구 사항입니다. 도메인 규칙에서 만료되지 않는 암호를 금지하는 경우 각 디바이스 리소스 계정에 대한 예외를 Teams 합니다.

다음 탭 중 하나에서 단계에 따라 암호 만료를 해제합니다.

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

먼저 Active Directory powerShell에 커넥트 다음을 확인합니다.

```PowerShell
   Connect-AzureAD
```

그런 다음 만료되지 [않는 암호 설정 을 참조하세요](/microsoft-365/admin/add-users/set-password-to-never-expire?view=o365-worldwide#set-a-password-to-never-expire).

이 예제에서는 계정 암호가 만료되지 ConferenceRoom01@contoso.com 설정합니다.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. 커넥트 PowerShell에 대한 다음을 사용할 수 있습니다.

       ```PowerShell
       Connect-MsolService
       ```

       Active Directory에 대한 [자세한 내용은 MSOnline(Azure Active Directory)을 참조합니다](/powershell/azure/active-directory/overview?view=azureadps-1.0).

2. 다음 구문을 사용하여 암호를 만료하지 못하게 설정합니다.

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    이 예제에서는 계정 암호가 만료되지 ConferenceRoom01@contoso.com 설정합니다.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory(On-프레미스)**](#tab/active-directory1-password/)

1. 커넥트 PowerShell에 대한 정보:

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Active Directory PowerShell에 대한 자세한 내용은 [ActiveDirectory를 참조합니다](/powershell/module/activedirectory/?view=windowsserver2022-ps).

2. 다음 구문을 사용하여 암호를 만료하지 못하게 설정합니다.

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    이 예제에서는 계정 암호가 만료되지 ConferenceRoom01@contoso.com 설정합니다.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>회의실 라이선스 할당

리소스 계정에 로그인하려면 Microsoft 365 Office 365 라이선스가 Microsoft Teams.

> [!NOTE]
> Microsoft Teams 룸 스탠더드 및 Microsoft Teams 룸 프리미엄 S Teams 룸KUS는 공유 회의실 디바이스에 사용할 수 있는 두 개의 SKUS입니다. 핫 데스크링이 있는 Teams 회의실 라이선스가 필요합니다. 자세한 내용은 회의실 [Teams 참조하세요](rooms-licensing.md).

라이선스를 사용하여 라이선스를 할당 Microsoft 365 관리 센터 사용자에게 [라이선스 할당을 참조합니다](/microsoft-365/admin/manage/assign-licenses-to-users). Azure AD를 사용하여 라이선스를 할당하는 경우 다음 탭 중 하나를 참조하세요.

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. 커넥트 AD에 대한 설정
  
    ```PowerShell
    Connect-AzureAD
    ```

     Active Directory에 대한 자세한 내용은 Azure Active Directory [PowerShell을 참조 Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0).
    
2. cmdlet을 사용하여 리소스 계정에 사용 위치를 `Set-AzureADUser` 할당합니다. 그러면 사용할 수 있는 라이선스 SKUS가 결정됩니다.

    이 예제에서는 사용자가 미국(미국)에 있습니다.

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. 그런 다음, 사용자 `Get-AzureADSubscribedSku` 또는 조직에서 사용할 수 있는 SKUS 목록을 Microsoft 365 Office 365 합니다.

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. 라이선스를 할당하기 `Set-AzureADUser` 위해 cmdlet을 사용하여 라이선스 SKU ID(2단계 참조)를 PowerShell 라이선스 유형 개체로 변환합니다. 그런 다음 해당 개체를 리소스 계정에 할당합니다. 다음 예제에서 라이선스 SKU ID는 6070a4c8-34c6-4937-8dfb-39bbc6397a60입니다 conferenceroom01@contoso.com.

    ```PowerShell
    #Create an object for a single license type
    $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
    $License.SkuId = "6070a4c8-34c6-4937-8dfb-39bbc6397a60" 
       
    #Create an object for a multiple license type
    $Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
       
    #Add the single license object to the multiple license object
    $Licenses.AddLicenses = $License 
       
    #Assign the license to the resource account
    Set-AzureADUserLicense -ObjectId ConferenceRoom01@contoso.com -AssignedLicenses $Licenses
    ```

#### <a name="active-directory-10"></a>[**Active Directory 1.0**](#tab/active-directory1-license/)

1. 커넥트 PowerShell에 대한 모든 기능을 사용할 수 있습니다.

   ```PowerShell
   Connect-MsolService
   ```

    Active Directory에 대한 자세한 내용은 [MSOnline(Azure Active Directory)을 참조합니다.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2.  cmdlet을 사용하여 리소스 계정에 사용 위치를 `Set-MsolUser` 할당합니다. 그러면 사용할 수 있는 라이선스 SKUS가 결정됩니다.

    이 예제에서는 사용자가 미국(미국)에 있습니다.
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    그런 다음, `Get-MsolAccountSku` 조직 또는 조직에서 사용할 수 있는 SKUS 목록을 Microsoft 365 Office 365 있습니다.

4. 라이선스를 할당하기 위해 `Set-MsolUser` cmdlet을 사용 합니다. 이 예제에서는 "contoso:MEETING_ROOM" 라이선스가 다음과 같은 계정에 conferenceroom01@contoso.com.

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

계정 만들기 및 라이선스 할당의 유효성을 검사하려면 만든 계정을 사용하여 Teams 클라이언트에 로그인합니다.

## <a name="next-steps"></a>다음 단계

### <a name="network-and-bandwidth"></a>네트워크 및 대역폭

이 계정에 사용자 지정 네트워크, 대역폭 또는 모임 정책을 적용해야 할 수 있습니다. 네트워크 및 대역폭 정책에 대한 자세한 내용은 오디오 비디오에 대한 모임 정책 설정을 & [참조하세요](/microsoftteams/meeting-policies-audio-and-video). Teams 룸 모임 정책 대역폭을 10Mbps로 설정하는 것이 좋습니다.

공동 작업을 위해 라이브, 화이트보드 및 PowerPoint 노트를 끈다. 참가자 및 게스트 설정을 조정하기 위해 모임 정책을 만들 수 Teams 룸. 예를 들어 모임에 자동으로 참가할 참석자와 같은 로비 설정을 검토합니다. 모임 정책에 대한 자세한 내용은 Teams 모임 정책 관리를 [Microsoft Teams.](/microsoftteams/meeting-policies-overview)

### <a name="calling"></a>통화

리소스 계정으로 호출을 사용하도록 설정하는 고유한 요구 사항은 없습니다. 일반 사용자를 사용하도록 설정하는 방식과 동일한 방식으로 호출에 대한 리소스 계정을 사용하도록 설정합니다.

> [!NOTE]
> 디바이스 리소스 계정에 호출 정책을 할당하여 공유 디바이스에 대한 음성 메일을 해제하는 것이 좋습니다. 자세한 [내용은](../teams-calling-policy.md) 전화 통화 및 Teams 참조하세요.

### <a name="configure-distribution-groups"></a>메일 그룹 구성

회의실 위치를 구성하려면 디바이스 리소스 계정을 배포 그룹에 Exchange 있습니다. 예를 들어 세 개의 서로 다른 지리적 위치에 사무실이 있는 경우 세 개의 메일 그룹을 만들고 각 위치에 적절한 리소스 계정을 추가할 수 있습니다. 자세한 내용은 회의실 목록 [만들기를 참조하세요](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list).

## <a name="related-articles"></a>관련 기사

[Microsoft Teams 룸](rooms-configure-accounts.md)

[Microsoft Teams 룸 계획](rooms-plan.md)

[Microsoft Teams 룸 배포](rooms-deploy.md)

[Microsoft Teams 룸 관리](rooms-manage.md)

[Microsoft Teams 룸 라이선스](rooms-licensing.md)
