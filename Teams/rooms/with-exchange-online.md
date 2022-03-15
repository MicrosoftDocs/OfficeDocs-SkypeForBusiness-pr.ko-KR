---
title: Microsoft Teams 룸 Exchange Online
ms.author: czawideh
author: cazawideh
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
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 이 항목을 참조하여 Microsoft Teams 룸 배포하는 방법에 Exchange Online.
ms.openlocfilehash: ad3b621ef541fcec471e329d1696e4f7000f4cb5
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503745"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Microsoft Teams 룸 Exchange Online

이 항목을 참조하여 Microsoft Teams 룸 배포하는 방법에 Exchange Online.
  
조직에 일부 호스팅되는 일부 프레미스 및 온라인에서 호스팅되는 서비스가 혼합된 경우 구성은 각 서비스가 호스트되는 위치에 따라 다릅니다. 이 항목에서는 온라인에서 호스팅되는 Microsoft Teams 룸 하이브리드 Exchange 설명합니다. 이 유형의 배포에는 다양한 변형이 있으므로 모든 배포에 대한 자세한 지침을 제공할 수 없습니다. 다음 프로세스는 여러 구성에 대해 작동할 것입니다. 프로세스가 설정에 맞지 않는 경우 여기에서 설명한 Windows PowerShell 다른 배포 옵션과 동일한 최종 결과를 달성하기 위해 이 프로세스를 사용하는 것이 좋습니다.

## <a name="requirements"></a>요구 사항

Microsoft Teams 룸 배포하기 Exchange Online 요구 사항을 충족해야 합니다. 자세한 내용은 요구 사항을 Microsoft Teams 룸 [참조하세요](requirements.md).
  
Microsoft Teams 룸 배포 Exchange Online 다음 단계를 따릅니다. cmdlet을 실행할 수 있는 권한이 있는지 확인 합니다. 

   > [!NOTE]
   >  이 [Azure Active Directory cmdlet](/powershell/azure/active-directory/overview?view=azureadps-1.0)에 대한 Windows PowerShell 모듈(예: Set-MsolUser)은 Microsoft Teams 룸. 다른 cmdlet이 작동할 수 있습니다. 그러나 이 특정 시나리오에서는 테스트되지 않은 것입니다.

AD FS(Active Directory Federation Services)를 배포한 경우 이러한 단계를 수행하기 전에 사용자 계정을 관리 사용자로 변환한 다음, 이 단계를 완료한 후 사용자를 페더리드 사용자로 다시 변환해야 할 수 있습니다.
  
### <a name="create-an-account-and-set-exchange-properties"></a>계정 만들기 및 Exchange 설정

1. PC에서 원격 Windows PowerShell 세션을 시작하고 다음과 같이 Exchange Online 연결합니다.

    ``` Powershell
   Connect-ExchangeOnline
    ```

2. 세션을 설정한 후 새 사서함을 만들고 RoomMailboxAccount로 사용하도록 설정하거나 기존 방 사서함에 대한 설정을 변경합니다. 이렇게 하면 계정에서 인증할 수 Microsoft Teams 룸.

   기존 리소스 사서함을 변경하는 경우:

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoom01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    새 리소스 사서함을 만드는 경우:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -Alias ConferenceRoom01 -Name 'ConferenceRoom01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 모임 환경을 개선하려면 다음과 같이 사용자 계정에 Exchange 속성을 설정해야 합니다.

   ``` Powershell
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Rooms enabled  room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>프레미스 도메인 계정에 대한 전자 메일 주소 추가

1. **Active Directory 사용자** 및 컴퓨터 AD 도구에서 사용자 계정이 생성될 컨테이너 또는 조직 Microsoft Teams 룸 마우스 오른쪽 단추로 클릭하고 새로 고를 클릭한 **다음 사용자를** **클릭합니다**.
2. 이전 cmdlet(Set-사서함 또는 새로-사서함)의 표시 이름(- ID)을 전체 이름 상자에  입력하고 별칭을 사용자 로그온 이름 상자에 **입력** 합니다. 다음 **을 클릭합니다**.
3. 이 계정에 대한 암호를 입력합니다. 확인을 위해 다시 타이프해야 합니다. 암호 **가 만료** 되지 않는지 확인란만 선택해야 합니다.

    > [!NOTE]
    > 암호 **가 만료** 되지 않는 경우 암호를 선택하는 것이 Microsoft Teams 룸. 도메인 규칙은 만료되지 않는 암호를 금지할 수 있습니다. 그렇다면 각 사용자 계정에 대한 예외를 Microsoft Teams 룸 합니다.
  
4. 완료 **를** 클릭하여 계정을 만들 수 있습니다.
5. 계정을 만든 후 디렉터리 동기화를 실행합니다. PowerShell에서 [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) 을 사용하여 수행할 수 있습니다. 이 작업을 완료하면 사용자의 페이지로 이동하여 이전 단계에서 만든 두 계정이 병합된지 확인해야 합니다.

### <a name="assign-an-office-365-license"></a>라이선스 Office 365 할당

1. 먼저 Azure AD에 연결하여 일부 계정 설정을 적용합니다. 이 cmdlet을 실행하여 연결할 수 있습니다. Active Directory에 대한 자세한 내용은 [Azure ActiveDirectory(MSOnline) 1.0을 참조하세요](/powershell/azure/active-directory/overview?view=azureadps-1.0).

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0은](/powershell/azure/active-directory/overview?view=azureadps-2.0) 지원되지 않습니다.

    ``` PowerShell
   Connect-MsolService
    ```

2. 사용자 계정에 연결하려면 유효한 Office 365 라이선스가 Microsoft Teams. 라이선스가 있는 경우 사용자 계정에 사용 위치를 할당해야 합니다. 그러면 계정에 사용할 수 있는 라이선스 SKUS가 결정됩니다.
3. 'Get-MsolAccountSku'를 사용하여 테넌트에 사용할 수 있는 SKU 목록을 Office 365 있습니다.
4. SKUS를 나열하면 'Set-MsolUserLicense'를 사용하여 라이선스를 추가할 수 있습니다. <!-- Set-AzureADUserLicense--> cmdlet입니다. 

    ```PowerShell
     Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM
    ```

## <a name="validate"></a>유효성 검사

유효성 검사를 위해 모든 클라이언트를 사용하여 Microsoft Teams 계정에 로그인할 수 있습니다.
  
## <a name="see-also"></a>참고 항목

[더 나은 검색 및 룸 제안 환경을 제공하려면 추가 메타데이터로 룸 사서함 업데이트](/powershell/module/exchange/set-place)

[Microsoft Teams 룸](rooms-configure-accounts.md)

[Microsoft Teams 룸 계획](rooms-plan.md)
  
[Microsoft Teams 룸 배포](rooms-deploy.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)
