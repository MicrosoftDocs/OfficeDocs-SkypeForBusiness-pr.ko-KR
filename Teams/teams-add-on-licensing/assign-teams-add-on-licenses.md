---
title: 사용자에게 Teams 추가 기능 라이선스 할당
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: 오디오 회의, 전화 시스템 및 통화 계획과 같은 기능에 대해 사용자에게 Teams 추가 기능 라이선스를 할당하는 방법을 배정합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f19060245a54012de1dbc1f38edd43365e4aaa6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809328"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>사용자에게 Teams 추가 기능 라이선스 할당

추가 기능 라이선스는 오디오 회의, 전화 시스템 및 통화 계획과 같은 특정 Teams 기능에 대한 라이선스입니다. 이 문서에서는 개별 사용자 및 대규모 사용자 집합에 추가 기능 라이선스를 대량으로 할당하는 방법을 설명하고 있습니다.

> [!NOTE]
> 추가 [기능 라이선스와](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) 함께 사용할 수 있는 Teams 기능에 대한 Teams 추가 기능 라이선스를 참조합니다. 또한 사용자가 오디오 회의, 무료 번호, 조직 외부 전화 번호와 같은 기능을 받을 수 있도록 구입해야 하는 라이선스 및 구입 방법(요금제에 따라)에 대한 정보도 찾을 수 있습니다. 사용자에게 원하는 기능을 결정한 후 사용자에게 라이선스를 할당합니다.

Microsoft 365 관리 센터 또는 PowerShell을 사용하여 조직의 사용자에게 라이선스를 할당할 수 있습니다. 라이선스를 관리하려면 전역 관리자 또는 사용자 관리 관리자해야 합니다.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>전화 시스템, 통화 요금제 및 통신 크레딧 라이선스를 할당하기 전에 알아야 할 정보

시작하기 전에 다음을 검토합니다.

- 하이브리드 사용자에 대해 PSTN(Public Switched Telephone Network) 연결을 사용하는 경우 전화 시스템 라이선스만 할당하면 됩니다. 통화 요금제 라이선스를 할당하지 않습니다.

- Microsoft 365와 Microsoft Teams 간의 대기 시간 때문에 라이선스를 할당한 후 사용자에게 통화 요금제가 할당되는 데 최대 24시간이 걸릴 수 있습니다. 24시간 후에 사용자에게 통화 요금제가 할당되지 않은 경우 비즈니스 제품에 대한 지원에 [문의하세요. 관리자 도움말.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

- 올바른 수의 라이선스를 구입하지 않은 경우 오류 메시지가 표시됩니다. 더 많은 통화 요금제 라이선스를 구입해야 하는 경우 더 구입하는 옵션을 선택합니다.

- 사용자에게 Enterprise E5 라이선스가 할당되어도 PSTN에서 전화를 걸거나 받으면 통신 크레딧 라이선스를 할당해야 합니다. [](../what-are-communications-credits.md)

- 사용자에게 통화 요금제 또는 통신 크레딧 라이선스를 할당한 후 조직의 전화 번호를 받은 다음 사용자에게 해당 번호를 할당해야 합니다. 단계별 지침은 통화 요금제 설정 [을 참조하세요.](../set-up-calling-plans.md)

## <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터 사용

Microsoft 365 관리 센터를 사용하여 개별 사용자 또는 소규모 사용자 집합에 라이선스를 할당합니다. 라이선스 페이지(한에  최대 20명까지) 또는 활성 사용자 페이지에서 라이선스를 **할당할 수** 있습니다. 선택하는 방법은 특정 사용자에 대한 제품 라이선스를 관리하거나 특정 제품에 대한 사용자 라이선스를 관리할지 여부에 따라 결정됩니다.

단계별 지침은 사용자에게 라이선스 [할당을 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

수백 또는 수천 명의 사용자와 같은 많은 수의 사용자에 대한 라이선스를 할당해야 하는 경우 [Azure AD(Azure Active](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)Directory)에서 Powershell 또는 그룹 기반 라이선스를 사용하세요.  

## <a name="using-powershell"></a>PowerShell 사용

PowerShell을 사용하여 사용자에게 라이선스를 일괄 할당합니다.  자세한 내용은 PowerShell을 통해 사용자 계정에 라이선스 [할당을 참조합니다.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)

### <a name="example-script"></a>예제 스크립트

다음은 스크립트를 사용하여 사용자에게 라이선스를 할당하는 방법의 예입니다.

1. IT 전문가 RTW용 Microsoft Online Services 로그인 도우미의 [64비트 버전을 설치합니다.](https://go.microsoft.com/fwlink/p/?LinkId=286152)
2. 다음을 위해 Microsoft Azure Active Directory 모듈을 Windows PowerShell.
    1. 관리자 권한 명령 Windows PowerShell(관리자 권한으로 Windows PowerShell 실행)
    2. 다음 명령을 실행합니다.
        ```powershell
        Install-Module MSOnline
        ```
    3. NuGet 공급자를 설치하라는 메시지가 표시될 경우 **Y를** 입력한 다음 Enter를 누르기만 합니다.
    4. PSGallery에서 모듈을 설치하라는 메시지가 표시될 경우 **Y를** 입력한 다음 Enter를 누르기만 합니다.
3. Windows PowerShell 명령 프롬프트에서 다음 스크립트를 실행하여 사용자에게 라이선스를 할당합니다. 조직 이름과 할당하려는 라이선스의 식별자는 \<CompanyName:License> 어디에 있습니다. 예: litwareinc:MCOMEETADV.

    식별자는 라이선스의 식별 이름과 다릅니다. 예를 들어 오디오 회의의 식별자는 MCOMEETADV입니다. 자세한 내용은 라이선스에 대한 제품 이름 및 [SKU 식별자를 참조하세요.](#product-names-and-sku-identifiers-for-licensing)

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
    #user1@domain.com
    #user2@domain.com

    #Import Module
    ipmo MSOnline

    #Authenticate to MSOLservice
    Connect-MSOLService
    #File prompt to select the userlist txt file
    [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
      $OFD = New-Object System.Windows.Forms.OpenFileDialog
      $OFD.filter = "text files (*.*)| *.txt"
      $OFD.ShowDialog() | Out-Null
      $OFD.filename

    If ($OFD.filename -eq '')
    {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
    }

    #Create a variable of all users
    $users = Get-Content $OFD.filename

    #License each user in the $users variable
    foreach ($user in $users)
        {
        Write-host "Assigning License: $user"
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    예를 들어 Microsoft 365 Enterprise 1 및 오디오 회의 라이선스를 할당하기 위해 스크립트에서 다음 구문을 사용 합니다.

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Microsoft Business Voice(통화 요금제 없이) 라이선스를 할당하기 위해 스크립트에서 다음 구문을 사용 합니다.

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>라이선스에 대한 제품 이름 및 SKU 식별자

다음은 PowerShell을 사용하여 Teams에서 라이선스를 관리할 때 참조로 사용할 수 있는 제품 이름 및 해당 SKU 파트 이름의 일부 목록입니다.

자세한 내용은 [PowerShell,](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)라이선스에 대한 제품 [](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)이름 및 서비스 계획 식별자 및 Education SKU 참조를 통해 라이선스 및 [서비스 보기를 참조하세요.](../sku-reference-edu.md)

| 제품 이름| SKU 파트 이름 |
|--------------|---------------|
| Microsoft Enterprise E5(전화 시스템 사용) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5(오디오 회의 없이) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5(오디오 회의 사용) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | SPB|
| Microsoft Business Voice(캐나다)| BUSINESS_VOICE_MED  |
| Microsoft Business Voice(영국) | BUSINESS_VOICE  |
| Microsoft Business Voice(미국) | BUSINESS_VOICE_MED2  |
| Microsoft Business Voice(통화 요금제 없이) | BUSINESS_VOICE_DIRECTROUTING  |
| 미국용 Microsoft Business Voice(통화 요금제 없이)| BUSINESS_VOICE_DIRECTROUTING _MED |
| 오디오 회의 | MCOMEETADV | 
| 분당 오디오 회의 결제(결제)</br>*통신 크레딧을 설정하고 사용하도록 설정해야 합니다.* | MCOMEETACPEA |
| 전화 시스템 | MCOEV |
| 국내 및 국제 통화 요금제 | MCOPSTN2 |
| 국내 통화 요금제(US/PR/CA의 경우 사용자/월 3000분, EU 국가의 경우 사용자/월 1200분) | MCOPSTN1 |
| 국내 통화 요금제(각 국가에 대해 사용자당 매월 120분) </br>*이 요금제는 미국에서 사용할 수 없습니다.* | MCOPSTN5 |
| 국내 통화 요금제(각 국가에 대해 사용자당 매월 240분) </br>*이 요금제는 미국에서 사용할 수 없습니다.* | MCOPSTN6 |
| 통신 크레딧 | MCOPSTNPP |

## <a name="related-topics"></a>관련 항목

- [Teams 추가 기능 라이선스](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [Teams에 대한 사용자 액세스 관리](../user-access.md)
- [PowerShell을 통해 라이선스 및 서비스 보기](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [라이선싱에 대한 제품 이름 및 서비스 계획 식별자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Education SKU 참조](../sku-reference-edu.md)