---
title: 회의실 및 공유 Teams 디바이스에 대한 리소스 계정 만들기
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Microsoft Teams 룸, Surface Hub의 Teams 룸, Teams 디스플레이의 핫 데스크 등 회의실 및 공유 디바이스에 대한 리소스 계정을 만드는 방법에 대한 자세한 내용은 이 문서를 참조하세요.
ms.openlocfilehash: 213cd2019aa23c296706c70a66e3e873f7527ee9
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706635"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>회의실 및 공유 Teams 디바이스에 대한 리소스 계정 만들기 및 구성

이 문서에서는 공유 공간 및 디바이스에 대한 리소스 계정을 만드는 단계를 제공하며 Windows의 Microsoft Teams 룸, Android의 Teams 룸, Surface Hub의 Teams 룸, Teams 디스플레이의 핫 데스크에 대한 리소스 계정을 구성하는 단계를 포함합니다.

Microsoft 365 리소스 계정은 회의실 또는 프로젝터와 같은 특정 리소스 전용 사서함 및 Teams 계정입니다. 이러한 리소스 계정은 만들 때 정의하는 규칙을 사용하여 모임 초대에 자동으로 응답할 수 있습니다. 예를 들어 회의실과 같은 공통 리소스가 있는 경우 일정 가용성에 따라 모임 초대를 자동으로 수락하거나 거절하는 해당 회의실에 대한 리소스 계정을 설정할 수 있습니다. 

모든 리소스 계정은 단일 Microsoft Teams 룸 설치에 고유하거나 Teams에서 핫 데스크 구현을 표시합니다.

> [!NOTE]
> Microsoft Teams 패널을 사용하는 경우 Teams 룸 리소스 계정이 Teams 룸 및 연결된 Teams 패널 모두에 로그인합니다.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **비즈니스용 Skype** <br><br>
> 리소스 계정이 비즈니스용 Skype 작동하도록 설정해야 하는 경우 비즈니스용 Skype 서버 사용하여 [Microsoft Teams 룸 배포](with-skype-for-business-server-2015.md)를 참조하세요.

## <a name="before-you-begin"></a>시작하기 전에

### <a name="requirements"></a>요구 사항

사용자 환경에 따라 리소스 계정을 만들려면 하나 이상의 역할이 필요합니다.

|**환경**|**필수 역할**|
|-----|-----|
|Azure Active Directory Domain Services  <br/> |전역 관리자 또는 사용자 관리자  <br/> |
|Active Directory  <br/> |Active Directory Enterprise Admins, Domain Admins 또는 사용자를 만들기 위한 위임된 권한이 있습니다. Azure Active Directory Connect 동기화 권한.  <br/> |
|Exchange Online  <br/> |전역 관리자 또는 Exchange 관리자   <br/> |
|Exchange Server  <br/> |Exchange 조직 관리 또는 받는 사람 관리   <br/> |

Teams 룸 대한 리소스 계정을 만드는 경우 UPN은 리소스 계정의 SMTP 주소와 일치해야 합니다. Teams 룸 배포하기 전에 [Microsoft Teams 룸 요구 사항을](requirements.md) 참조하세요.

### <a name="what-license-do-you-need"></a>어떤 라이선스가 필요한가요?

Microsoft 365 리소스 계정을 만들기 전에 필요한 라이선스 종류를 확인합니다.

- **Teams 모임** Microsoft Teams 룸 또는 Teams 디스플레이와 같은 공유 디바이스와 리소스 계정을 핫 데스크에 연결하고 참석자가 이를 사용하여 비디오 및 오디오를 프레젠테이션할 수 있도록 Teams 모임에 참가하려면 회의실 라이선스가 필요합니다. 회의실 라이선스에 대한 자세한 내용은 [Teams 회의실 라이선스](rooms-licensing.md)를 참조하세요.

- **PSTN 호출** 리소스가 외부 전화 번호(공중 전화망 또는 PSTN 통화라고 함)로부터 전화를 걸거나 받도록 하려면 Microsoft 365 전화 시스템 또는 Microsoft 365 Business Voice 라이선스가 필요합니다. 다음 개요에서 1단계만 완료하면 됩니다. 그런 다음, [자세한 내용은 Microsoft Teams 추가 기능 라이선스를 참조하세요](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) .

- 리소스 계정만 사용하여 리소스&mdash;를 예약하는 경우 모임에 리소스를 초대하고 리소스 계정에 라이선스를 할당할 필요가 없는 초대&mdash;를 자동으로 수락하거나 거절하도록 하며 다음 개요의 1단계만 완료하면 됩니다.  

## <a name="overview"></a>개요

**1단계 -** [새 리소스 계정을 만듭니](#create-a-resource-account)다. 또는 회의실 사서함이 이미 있고 리소스 계정으로 변환하려는 경우 [기존 Exchange Room 사서함을 수정](?tabs=existing-account#create-a-resource-account)할 수 있습니다.

**2단계 -**  그런 다음 Teams 모임에 대한 [계정을 구성](#configure-mailbox-properties) 합니다.

**3단계 -**  리소스 계정이 공유 디바이스와 연결될 경우(예: Teams가 핫 데스크로 표시됨) [암호 만료를 해제합니다](#turn-off-password-expiration).

**4단계 -**  마지막으로 계정이 Microsoft Teams에 액세스할 수 있도록 [회의실 라이선스를 할당](#assign-a-meeting-room-license) 합니다.

리소스 계정을 만들고 구성한 후 [다음 단계를](#next-steps) 참조하여 배포 그룹, 네트워크 기능 및 통화를 비롯한 추가 설정 작업을 검토합니다.

## <a name="create-a-resource-account"></a>리소스 계정 만들기

> [!TIP]
> 리소스 계정의 이름을 지정할 때는 전자 메일 주소의 시작 부분에 표준 명명 규칙을 사용하는 것이 좋습니다. 이렇게 하면 Azure Active Directory에서 쉽게 관리할 수 있는 동적 그룹을 만드는 데 도움이 됩니다. 예를 들어 Microsoft Teams 룸 연결할 모든 리소스 계정에 "mtr-"을 사용할 수 있습니다.

> [!TIP]
> Exchange Online 및 Azure Active Directory를 사용하여 모든 리소스 계정을 만드는 것이 좋습니다.

다음 탭 중 하나에서 메서드를 사용하여 리소스 계정을 만듭니다.

#### <a name="in-microsoft-365-admin-center"></a>[**Microsoft 365 관리 센터**](#tab/m365-admin-center)

1. Microsoft 365 관리 센터에 로그인합니다.

2. Microsoft 365 테넌트에 대한 관리자 자격 증명을 제공합니다.

3. 왼쪽 패널의 **리소스** 로 이동한 다음, **룸 & 장비를** 선택합니다. 왼쪽 패널에서 이러한 옵션을 사용할 수 없는 경우 **먼저 모두 표시** 를 선택해야 할 수 있습니다.

4. **리소스 추가** 를 선택하여 새 회의실 계정을 만듭니다. 계정의 표시 이름과 전자 메일 주소를 입력하고 **추가** 를 선택한 다음 **닫기를** 선택합니다.

5. 기본적으로 리소스 계정은 다음 설정으로 구성됩니다.

    - 반복 모임 허용
    - 다음 제한을 벗어나는 모임 자동 거부
      - 예약 기간(일): 180
      - 최대 기간(시간): 24
    - 모임 요청 자동 수락

    변경하려면 **닫기를** 선택하기 전에 **예약 옵션 편집** 을 선택합니다. 나중에 변경하려면 **리소스** > **룸 & 장비** 로 이동하여 리소스 계정을 선택합니다. 그런 다음 **예약 옵션** 에서 **편집** 을 선택합니다.

6. **사용자** > **활성 사용자** 로 이동하고 만든 회의실을 선택하여 속성 패널을 엽니다.

7. 다음으로, 리소스 계정에 암호를 할당합니다. 패널에서 **암호 재설정** 을 선택합니다.
 
8. 사용자가 공유 디바이스에서 암호를 변경하도록 요구하면 로그인 문제가 발생합니다. **이 사용자가 처음 로그인할 때 암호를 변경하도록 요구하고 암호** **재설정** 을 선택 취소합니다.

9. **라이선스 및 앱** 섹션에서 디바이스가 설치될 국가 또는 지역으로 **위치 선택을** 설정합니다. 그런 다음, 회의실과 같이 할당할 라이선스를 선택하고 **변경 내용 저장** 을 선택합니다. 라이선스는 조직에 따라 달라질 수 있습니다.

리소스 사서함의 설정을 변경하려면 [사서함 속성 구성](#configure-mailbox-properties) 을 참조하거나 Exchange 관리 센터를 사용합니다.

또한 이 계정에 대역폭 정책 또는 모임 정책을 적용해야 할 수도 있습니다. 자세한 내용은 [다음 단계를](#next-steps) 참조하세요.

#### <a name="with-exchange-online"></a>[**Exchange Online**](#tab/exchange-online)

1. [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)에 연결합니다.

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. 기본적으로 회의실 사서함에는 연결된 계정이 없습니다. Microsoft Teams에서 인증할 수 있도록 회의실 사서함을 만들 때 계정을 추가합니다.

    새 리소스 사서함을 만드는 경우:
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    이 예제에서는 다음 설정을 사용하여 새 회의실 사서함을 만듭니다.

    - 계정: ConferenceRoom01@contoso.com
          
    - 이름: ConferenceRoom01
        
     - 별칭: ConferenceRoom01
        
     - 계정 암호: P@$$W 0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Exchange 하이브리드 구성에 없는 경우 다음 단계인 [사서함 속성 구성](#configure-mailbox-properties)을 계속할 수 있습니다.

Exchange 하이브리드 구성을 사용하는 경우 온-프레미스 도메인 계정의 이메일 주소를 추가해야 합니다. 자세한 내용은 [온-프레미스 동기화 및 Office 365 사용자 계정 디렉터리를 참조하세요](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78).

#### <a name="with-exchange-server"></a>[**Exchange Server**](#tab/exchange-server)

  1. Exchange 관리 셸에 연결합니다. [Exchange 관리 셸을 열](/powershell/exchange/exchange-server/open-the-exchange-management-shell) 거나 [원격 PowerShell을 사용하여 Exchange 서버에 연결합니다](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

   2. 새 회의실 사서함을 만들려면 다음을 수행합니다.

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```
     
   이 예제에서는 다음 설정을 사용하여 새 회의실 사서함을 만듭니다.

   - 계정: ConferenceRoom01@contoso.com
  
   - 이름: ConferenceRoom01

   - 별칭: ConferenceRoom01

   - 계정 암호: P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**기존 Exchange Room 사서함 수정**](#tab/existing-account)

리소스 계정이 되도록 기존 회의실 사서함을 수정하려면 다음 구문을 사용합니다.

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

다음은 별칭 값이 ConferenceRoom02인 기존 회의실 사서함의 계정을 사용하도록 설정하고 암호를 9898P@$$W 0rd로 설정하는 예제입니다.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Exchange 하이브리드 구성을 사용하는 경우 온-프레미스 도메인 계정의 전자 메일 주소도 추가해야 합니다. 자세한 내용은 [온-프레미스 동기화 및 Office 365 사용자 계정 디렉터리를 참조하세요](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78).

자세한 구문 및 매개 변수 정보는 [새 사서함 및 Set-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) 를 참조 [하세요](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Surface Hub의 Teams 룸에 대해 이 계정을 만드는 경우 이 계정에서도 ActiveSync를 사용하도록 설정해야 합니다. 이렇게 하면 Surface Hub에서 직접 전자 메일을 보낼 수 있으며, 화이트보드와 같은 기능에 사용할 수 있습니다. 자세한 내용은 [디바이스 계정에 ActiveSync 정책 적용(Surface Hub)](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) 을 참조하세요.

---

> [!IMPORTANT]
> 이 리소스 계정만 사용하여 공간을 예약하고 초대를 자동으로 수락하거나 거절하는 경우 설정을 완료했습니다. PSTN 통화에 이 리소스 계정을 사용하는 경우 [Microsoft Teams 추가 기능 라이선스를](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 참조하여 필요한 라이선스를 확인하세요.
>
> 리소스 계정이 Windows의 Teams 룸, Android에서 Teams 룸, Surface Hub에서 Teams 룸 또는 핫 데스크가 있는 Teams 디스플레이에 대한 경우에만 다음 섹션으로 계속 진행합니다.

## <a name="configure-mailbox-properties"></a>사서함 속성 구성

Exchange PowerShell에서 온라인 또는 온-프레미스에서 회의실 사서함에서 다음 설정을 구성하여 모임 환경을 개선합니다.

- **AutomateProcessing: `AutoAccept`** 모임 이끌이는 사람의 개입 없이 회의실 예약 결정을 직접 받습니다.

- **AddOrganizerToSubject: `$false`** 모임 이끌이는 모임 요청의 제목에 추가되지 않습니다.

- **DeleteComments: `$false`** 들어오는 모임 요청의 메시지 본문에 텍스트를 보관합니다. 이는 외부 Teams 및 타사 모임을 처리하여 One Touch Join 환경을 제공하는 데 필요합니다.

- **DeleteSubject: `$false`** 들어오는 모임 요청의 제목을 유지합니다.

- **ProcessExternalMeetingMessages: `$true`** Exchange 조직 외부에서 발생하는 모임 요청을 처리할지 여부를 지정합니다. 외부 Teams 모임 및 [타사 모임에](/microsoftteams/rooms/third-party-join) 필요합니다.

- **RemovePrivateProperty: `$false`** 원래 모임 요청에서 모임 이끌이가 보낸 개인 플래그가 지정된 대로 유지되도록 합니다.

- **AddAdditionalResponse: `$true`** AdditionalResponse 매개 변수로 지정된 텍스트가 모임 요청에 추가됩니다.

- **AdditionalResponse: "Microsoft Teams 회의실입니다!"** 모임 수락 응답에 추가할 추가 텍스트입니다.

이 예제에서는 ConferenceRoom01이라는 회의실 사서함에서 이러한 설정을 구성합니다.

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

자세한 구문 및 매개 변수 정보는 [Set-CalendarProcessing을 참조하세요](/powershell/module/exchange/mailboxes/set-calendarprocessing).

## <a name="turn-off-password-expiration"></a>암호 만료 끄기

리소스 계정 암호가 만료되면 디바이스는 만료 날짜 이후에 로그인하지 않습니다. 그런 다음 리소스 계정에 대한 암호를 변경한 다음 각 디바이스에서 업데이트해야 합니다. 이를 방지하기 위해 암호 만료를 해제할 수 있습니다.
  
> [!NOTE]
> **암호가 만료되지 않도록** 설정하는 것은 공유 Microsoft Teams 디바이스에 대한 요구 사항입니다. 도메인 규칙이 만료되지 않는 암호를 금지하는 경우 각 Teams 디바이스 리소스 계정에 대한 예외를 만들어야 합니다.

다음 탭 중 하나의 단계에 따라 암호 만료를 해제합니다.

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

먼저 Active Directory PowerShell에 연결합니다.

```PowerShell
   Connect-AzureAD
```

그런 다음 [암호가 만료되지 않도록 설정을](/microsoft-365/admin/add-users/set-password-to-never-expire#set-a-password-to-never-expire) 참조하세요.

다음은 계정 ConferenceRoom01@contoso.com 암호가 만료되지 않도록 설정하는 예제입니다.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. MSOnline PowerShell에 연결:

       ```PowerShell
       Connect-MsolService
       ```

       Active Directory에 대한 자세한 내용은 [Azure Active Directory(MSOnline)](/powershell/azure/active-directory/overview?view=azureadps-1.0&preserve-view=true)를 참조하세요.

2. 다음 구문을 사용하여 암호가 만료되지 않도록 설정합니다.

    ```PowerShell
    Set-MsolUser -UserPrincipalName <userPrincipalName> -PasswordNeverExpires $true
    ```

    다음은 계정 ConferenceRoom01@contoso.com 암호가 만료되지 않도록 설정하는 예제입니다.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory(온-프레미스)**](#tab/active-directory1-password/)

1. Active Directory PowerShell에 연결:

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Active Directory PowerShell에 대한 자세한 내용은 [ActiveDirectory](/powershell/module/activedirectory/)를 참조하세요.

2. 다음 구문을 사용하여 암호가 만료되지 않도록 설정합니다.

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    다음은 계정 ConferenceRoom01@contoso.com 암호가 만료되지 않도록 설정하는 예제입니다.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>회의실 라이선스 할당

Microsoft Teams에 로그인하려면 리소스 계정에 Microsoft 365 또는 Office 365 라이선스가 필요합니다.

> [!NOTE]
> Microsoft Teams 룸 Basic 및 Microsoft Teams 룸 Pro는 Teams 룸 포함하여 공유 회의실 디바이스에 사용할 수 있는 두 가지 SKU입니다. 핫 데스크가 있는 Teams 디스플레이에는 회의실 라이선스가 필요합니다. 자세한 내용은 [Microsoft Teams 룸 라이선스를 참조하세요](rooms-licensing.md).

Microsoft 365 관리 센터 사용하여 라이선스를 할당하려면 [사용자에게 라이선스 할당을 참조하세요](/microsoft-365/admin/manage/assign-licenses-to-users). Azure AD 사용하여 라이선스를 할당하려면 다음 탭 중 하나를 참조하세요.

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. Azure AD 연결
  
    ```PowerShell
    Connect-AzureAD
    ```

     Active Directory에 대한 자세한 내용은 [Graph용 Azure Active Directory PowerShell을 참조하세요](/powershell/azure/active-directory/overview?view=azureadps-2.0&preserve-view=true).
    
2. cmdlet을 사용하여 `Set-AzureADUser` 리소스 계정에 사용 위치를 할당합니다. 이는 사용 가능한 라이선스 SKU를 결정합니다.

    이 예제에서 사용자는 미국(미국)에 있습니다.

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. 그런 다음 Microsoft 365 또는 Office 365 조직에 사용 가능한 SKU 목록을 검색하는 데 사용합니다`Get-AzureADSubscribedSku`.

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. 라이선스를 할당하려면 cmdlet을 `Set-AzureADUser` 사용하고 라이선스 SKU ID(2단계 참조)를 PowerShell 라이선스 유형 개체로 변환합니다. 그런 다음 해당 개체를 리소스 계정에 할당합니다. 다음 예제에서 라이선스 SKU ID는 6070a4c8-34c6-4937-8dfb-39bbc6397a60이며 계정 conferenceroom01@contoso.com 할당됩니다.

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

1. MSOnline PowerShell에 연결합니다.

   ```PowerShell
   Connect-MsolService
   ```

    Active Directory에 대한 자세한 내용은 [Azure Active Directory(MSOnline)](/powershell/azure/active-directory/overview?view=azureadps-1.0&preserve-view=true)를 참조하세요.

2.  cmdlet을 사용하여 `Set-MsolUser` 리소스 계정에 사용 위치를 할당합니다. 이는 사용 가능한 라이선스 SKU를 결정합니다.

    이 예제에서 사용자는 미국(미국)에 있습니다.
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    그런 다음 Microsoft 365 또는 Office 365 조직에 사용 가능한 SKU 목록을 검색하는 데 사용할 `Get-MsolAccountSku` 수 있습니다.

4. 라이선스를 할당하려면 cmdlet을 `Set-MsolUser` 사용합니다. 이 예제에서는 "contoso:MEETING_ROOM" 라이선스가 계정 conferenceroom01@contoso.com 할당됩니다.

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

계정 만들기 및 라이선스 할당의 유효성을 검사하려면 만든 계정을 사용하여 Teams 클라이언트에 로그인합니다.

## <a name="next-steps"></a>다음 단계

### <a name="meeting-policies"></a>모임 정책

사용자 지정 네트워크, 대역폭 또는 모임 정책을 이 계정에 적용해야 할 수 있습니다. 네트워크 및 대역폭 정책에 대한 자세한 내용은 [오디오 & 비디오에 대한 모임 정책 설정을](/microsoftteams/meeting-policies-audio-and-video) 참조하세요. Teams 룸 경우 모임 정책 대역폭을 10Mbps로 설정하는 것이 좋습니다.

공동 작업을 위해 PowerPoint Live, Whiteboard 및 공유 노트를 켭니다. 모임 정책 설정 "비공개 모임에서 지금 모임"을 사용하도록 설정하는 것이 좋습니다. Teams 룸 대한 참가자 및 게스트 설정을 조정하는 모임 정책을 만들 수 있습니다. 예를 들어 모임에 자동으로 허용할 참석자와 같은 로비 설정을 검토합니다. Teams 모임 정책에 대한 자세한 내용은 [Microsoft Teams에서 모임 정책 관리를 참조하세요](/microsoftteams/meeting-policies-overview).

### <a name="calling"></a>통화

리소스 계정으로 통화를 사용하도록 설정하는 고유한 요구 사항은 없습니다. 일반 사용자를 사용하도록 설정하는 것과 동일한 방식으로 호출에 리소스 계정을 사용하도록 설정합니다.

> [!NOTE]
> 디바이스 리소스 계정에 통화 정책을 할당하여 공유 디바이스에 대한 음성 메일을 해제하는 것이 좋습니다. 자세한 내용은 [Teams에서 통화 및 착신 전환(Call and call-forwarding](../teams-calling-policy.md) )을 참조하세요.

### <a name="configure-distribution-groups-for-teams-calendar"></a>Teams 일정에 대한 메일 그룹 구성

회의실 위치를 구성하려면 Exchange 메일 그룹에 디바이스 리소스 계정을 추가할 수 있습니다. 예를 들어 세 개의 서로 다른 지리적 위치에 사무실이 있는 경우 세 개의 배포 그룹을 만들고 각 위치에 적절한 리소스 계정을 추가할 수 있습니다. 자세한 내용은 [회의실 목록 만들기를 참조하세요](/exchange/recipients/room-mailboxes?view=exchserver-2019&preserve-view=true#create-a-room-list).

### <a name="configure-places-for-outlook-calendar"></a>Outlook 일정 위치 구성
회의실 위치가 Outlook 회의실 찾기에 표시되도록 하려면 Set-Place Exchange PowerShell cmdlet을 사용해야 합니다. Set-Place Outlook에서 회의실 찾기를 채울 뿐만 아니라 회의실의 용량 또는 회의실의 건물 바닥과 같은 추가 메타데이터를 추가할 수 있습니다. 자세한 내용은 [Set-Place](/powershell/module/exchange/set-place)를 참조하세요.

## <a name="related-articles"></a>관련 기사

[Microsoft Teams 룸 대한 계정 구성](rooms-configure-accounts.md)

[Microsoft Teams 룸 계획](rooms-plan.md)

[Microsoft Teams 룸 배포](rooms-deploy.md)

[Microsoft Teams 룸 관리](rooms-manage.md)

[Microsoft Teams 룸 라이선스](rooms-licensing.md)
