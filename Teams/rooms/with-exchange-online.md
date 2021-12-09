---
title: Microsoft Teams 룸 Exchange Online
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
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 이 항목을 참조하여 Microsoft Teams 룸 및 Exchange Online 비즈니스용 Skype 서버 정보를 참조하세요.
ms.openlocfilehash: 8f8511f4dd05b6d2eb073aaab0a14305c9d67831
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355637"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Microsoft Teams 룸 Exchange Online

이 항목을 참조하여 Microsoft Teams 룸 배포하는 방법에 Exchange Online.
  
조직에 일부 호스팅되는 일부 프레미스 및 온라인에서 호스팅되는 서비스가 혼합된 경우 구성은 각 서비스가 호스트되는 위치에 따라 다릅니다. 이 항목에서는 온라인에서 호스팅되는 Microsoft Teams 룸 하이브리드 Exchange 설명합니다. 이 유형의 배포에는 다양한 변형이 있으므로 모든 배포에 대한 자세한 지침을 제공할 수 없습니다. 다음 프로세스는 여러 구성에 대해 작동할 것입니다. 프로세스가 설정에 맞지 않는 경우 여기에서 설명한 Windows PowerShell 및 다른 배포 옵션에 대해 동일한 최종 결과를 달성하기 위해 이 프로세스를 사용하는 것이 좋습니다.

## <a name="requirements"></a>요구 사항

Microsoft Teams 룸 배포하기 Exchange Online 요구 사항을 충족해야 합니다. 자세한 내용은 요구 사항 [Microsoft Teams 룸 참조하세요.](requirements.md)
  
Microsoft Teams 룸 배포 Exchange Online 다음 단계를 따르세요. 연결된 cmdlet을 실행할 수 있는 권한이 있는지 확인 합니다. 

   > [!NOTE]
   >  이 [Azure Active Directory cmdlet에](/powershell/azure/active-directory/overview) 대한 Windows PowerShell 모듈(예: Set-MsolUser)은 디바이스에 대한 계정을 설정하는 Microsoft Teams 룸 테스트되었습니다. 다른 cmdlet이 작동할 수 있습니다. 그러나 이 특정 시나리오에서는 테스트되지 않은 것입니다.

AD FS(Active Directory Federation Services)를 배포한 경우 이러한 단계를 수행하기 전에 사용자 계정을 관리 사용자로 변환한 다음, 이 단계를 완료한 후 사용자를 페더리드 사용자로 다시 변환해야 할 수 있습니다.
  
### <a name="create-an-account-and-set-exchange-properties"></a>계정 만들기 및 Exchange 설정

1. PC에서 원격 Windows PowerShell 세션을 시작하고 다음과 같이 Exchange Online 연결합니다.

    ``` Powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline
    ```

2. 세션을 설정한 후 새 사서함을 만들고 RoomMailboxAccount로 사용하도록 설정하거나 기존 방 사서함에 대한 설정을 변경합니다. 이렇게 하면 계정에서 인증할 수 Microsoft Teams 룸.

   기존 리소스 사서함을 변경하는 경우:

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoom01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    새 리소스 사서함을 만드는 경우:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 모임 환경을 개선하려면 다음과 같이 사용자 계정에 Exchange 속성을 설정해야 합니다.

   ``` Powershell
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'ConferenceRoom01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>프레미스 도메인 계정에 대한 전자 메일 주소 추가

1. **Active Directory** 사용자 및 컴퓨터 AD 도구에서 사용자 계정이 생성될 컨테이너 또는 조직 Microsoft Teams 룸 마우스 오른쪽 단추로 클릭하고 새 을 클릭한 다음 사용자 를 **클릭합니다.**
2. 이전 cmdlet(Set-사서함 또는 새로-사서함)의 표시 이름(-  ID)을 전체 이름 상자에 입력하고 별칭을 사용자 로그온 이름 상자에 **입력합니다.** 다음 **을 클릭합니다.**
3. 이 계정에 대한 암호를 입력합니다. 확인을 위해 다시 타이프해야 합니다. 암호가 **만료되지** 않는지 확인란만 선택해야 합니다.

    > [!NOTE]
    > 암호가  만료되지 않는 경우 암호를 선택해야 비즈니스용 Skype 서버 Microsoft Teams 룸. 도메인 규칙은 만료되지 않는 암호를 금지할 수 있습니다. 그렇다면 각 사용자 계정에 대한 예외를 Microsoft Teams 룸 합니다.
  
4. **완료를** 클릭하여 계정을 만들 수 있습니다.
5. 계정을 만든 후 디렉터리 동기화를 실행합니다. PowerShell에서 [Set-MsolDirSyncConfiguration을](/powershell/module/msonline/set-msoldirsyncconfiguration) 사용하여 수행할 수 있습니다. 이 작업을 완료하면 사용자 페이지로 이동하여 이전 단계에서 만든 두 계정이 병합된지 확인해야 합니다.

### <a name="assign-a-microsoft-365-or-office-365-license"></a>라이선스 Microsoft 365 또는 Office 365 할당

1. 먼저 Azure AD에 연결하여 일부 계정 설정을 적용합니다. 이 cmdlet을 실행하여 연결할 수 있습니다. Active Directory에 대한 자세한 내용은 [Azure ActiveDirectory(MSOnline) 1.0 을 참조하세요.](/powershell/azure/active-directory/overview)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0은](/powershell/azure/active-directory/overview) 지원되지 않습니다.

    ``` PowerShell
   Connect-MsolService
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. 사용자 계정에 유효한 Microsoft 365 Office 365 라이선스가 있어야 Exchange 합니다. 라이선스가 있는 경우 사용자 계정에 사용 위치를 할당해야 합니다. 그러면 계정에 사용할 수 있는 라이선스 SKUS가 결정됩니다. 다음 단계에서 과제를 지정합니다.
3. 다음으로, `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> 를 사용하여 사용자 또는 조직에서 사용할 수 있는 SKUS Microsoft 365 Office 365 검색합니다.
4. 다음을 사용하여 라이선스를 추가할 수 있습니다. `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet입니다. 이 경우 Microsoft Teams 룸 스탠더드 라이선스가 적용됩니다. 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses "contoso:MEETING_ROOM"
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

## <a name="related-topics"></a>관련 항목

[Microsoft Teams 룸](rooms-configure-accounts.md)

[Microsoft Teams 룸 계획](rooms-plan.md)
  
[Microsoft Teams 룸 배포](rooms-deploy.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)
