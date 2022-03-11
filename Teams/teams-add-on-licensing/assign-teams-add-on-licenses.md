---
title: 사용자에게 Teams 추가 기능 라이선스 할당
author: SerdarSoysal
ms.author: serdars
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
description: 오디오 회의, Teams 및 통화 계획과 같은 기능을 위해 사용자에게 추가 기능 라이선스를 전화 시스템 방법에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8668b31caf0dc10e8585a518a9c4c9be890d1d0d
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435842"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>사용자에게 Teams 추가 기능 라이선스 할당

추가 기능 라이선스는 오디오 회의, Teams 및 호출 계획과 같은 특정 전화 시스템 라이선스입니다. 이 문서에서는 개별 사용자 및 대규모 사용자 집합에 추가 기능 라이선스를 할당하는 방법을 일괄적으로 설명합니다.

> [!NOTE]
> 추가 [Teams](./microsoft-teams-add-on-licensing.md) 사용할 수 있는 Teams 기능에 대한 추가 기능 라이선스를 참조합니다. 또한 요금제에 따라 구매해야 하는 라이선스 및 구매 방법에 대한 정보를 찾을 수 있습니다. 사용자에게 어떤 기능을 사용할지 결정한 후 라이선스를 사용자에게 할당합니다.

사용자 또는 Microsoft 365 관리 센터 PowerShell을 사용하여 조직의 사용자에게 라이선스를 할당할 수 있습니다. 라이선스를 관리하려면 전역 관리자 또는 사용자 관리 관리자가 되어야 합니다.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>요금제, 통화 계획 및 통신 크레딧 전화 시스템 할당하기 전에 알아야 할 작업

시작하기 전에 다음 요구 사항을 검토합니다.

- 사용자에 대한 PSTN(공용 전환 전화 네트워크) 연결을 사용하는 경우 표준 라이선스를 Teams 전화 합니다. 통화 계획 라이선스를 할당하지 않습니다.

- 사용자에게 Microsoft 통화 계획을 할당한 후 해당 클라이언트에 다이얼 패드가 표시되기까지 최대 24시간이 Teams 있습니다. 다이얼 패드가 24시간 동안 표시되지 않는 경우 다이얼 패드 구성 [을 검사합니다](../dial-pad-configuration.md). 필요한 경우 지원에 [문의할 수 있습니다](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- 올바른 라이선스 수를 구입하지 않은 경우 오류 메시지가 표시됩니다. 더 많은 통화 요금제 라이선스를 구입해야 하는 경우 추가 구매 옵션을 선택합니다.

- 사용자가 E5 라이선스에 Enterprise 경우에도 PSTN에 연결해야 합니다. 통화 요금제, 직접 라우팅 또는 연산자 Microsoft Teams 등 여러 [PSTN](../pstn-connectivity.md) 연결 옵션이 커넥트.

- 사용자에게 통화 계획 또는 통신 크레딧 라이선스를 할당한 후 조직의 전화 번호를 받은 다음 사용자에게 해당 번호를 할당해야 합니다. 단계별 지침은 통화 계획 [설정을 참조하세요](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터

이 Microsoft 365 관리 센터 사용하여 개별 사용자 또는 소규모 사용자 집합에 라이선스를 할당합니다.

라이선스 페이지에서 라이선스(한 때  최대 20명) 또는 **활성** 사용자 페이지(한에 최대 40명까지)에 라이선스를 할당합니다. 선택한 방법은 특정 사용자에 대한 제품 라이선스를 관리하거나 특정 제품에 대한 사용자 라이선스를 관리할지 여부에 따라 결정됩니다.

단계별 지침은 사용자에게 라이선스 [할당을 참조하세요](/microsoft-365/admin/manage/assign-licenses-to-users).

수백 또는 수천 명의 사용자와 같은 많은 수의 사용자에게 라이선스를 할당해야 하는 경우 Azure AD(Azure AD)에서 Powershell [또는 그룹 Azure Active Directory 사용](/azure/active-directory/users-groups-roles/licensing-groups-assign)하세요.

## <a name="using-powershell"></a>PowerShell 사용

PowerShell을 사용하여 대량으로 사용자에게 라이선스를 할당합니다. 자세한 내용은 PowerShell을 통해 사용자 계정에 라이선스 [할당을 참조합니다](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>예제 스크립트

다음은 스크립트를 사용하여 사용자에게 라이선스를 할당하는 방법에 대한 예제입니다.

1. [IT 전문가 RTW](/collaborate/connect-redirect?DownloadID=59185)에 대한 64비트 Microsoft Online Services 로그인 도우미를 설치합니다.
2. 다음 Microsoft Azure Active Directory 모듈을 Windows PowerShell.
    1. 상승된 명령 프롬프트를 Windows PowerShell(관리자로 Windows PowerShell 실행).
    2. 다음 명령을 실행합니다.
        ```powershell
        Install-Module MSOnline
        ```
    3. 공급자를 설치하라는 메시지가 표시 NuGet **Y** 를 입력한 다음 Enter를 누를 수 있습니다.
    4. PSGallery에서 모듈을 설치하라는 메시지가 표시된 경우 **Y** 를 입력한 다음 Enter를 누를 수 있습니다.
3. Windows PowerShell 명령 프롬프트에서 다음 스크립트를 실행하여 사용자에게 라이선스를 할당합니다. 여기서 \<CompanyName:License> 는 조직 이름과 할당하려는 라이선스의 식별자입니다. 예를 들어 litwareinc:MCOMEETADV.

    식별자는 라이선스의 친숙한 이름과 다릅니다. 예를 들어 오디오 회의의 식별자는 MCOMEETADV입니다. 자세한 내용은 라이선스에 대한 [제품 이름 및 SKU 식별자를 참조하세요](#product-names-and-sku-identifiers-for-licensing).

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

    예를 들어 E1 및 Microsoft 365 Enterprise 라이선스를 할당하는 경우 스크립트에서 다음 구문을 사용 합니다.

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    호출 Teams 전화 라이선스를 할당하기 위해 스크립트에서 다음 구문을 사용 합니다.

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>라이선스에 대한 제품 이름 및 SKU 식별자

다음은 PowerShell을 사용하여 라이선스를 관리하는 데 사용할 때 참조할 수 있는 제품 이름 및 해당 SKU 부품 이름의 부분 Teams.

자세한 내용은 [PowerShell, 라이선스](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)에 대한 제품 이름 및 서비스 계획 식별[](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)자 및 Education SKU 참조를 통해 라이선스 및 서비스 [보기를 참조하세요](../sku-reference-edu.md).

| 제품 이름| SKU 부품 이름 |
|--------------|---------------|
| Microsoft Enterprise E5(전화 시스템) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5(오디오 회의 없이) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5(오디오 회의 사용) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | SPB|
| 오디오 회의 | MCOMEETADV |
| 오디오 회의 분당 지불(이동 시 지불) 통신 크레딧을 설정하고 사용하도록 설정해야 합니다.* | MCOMEETACPEA |
| Teams 전화 표준 | MCOEV |
| 통화 플랜이 포함된 Teams 전화 | MCOTEAMS_ESSENTIALS |
| 국내 및 국제 통화 계획 | MCOPSTN2 |
| 국내 통화 계획(US/PR/CA의 경우 사용자/월당 3000분, EU 국가의 경우 사용자/월당 1200분) | MCOPSTN1 |
| 국내 통화 요금제(각 국가의 사용자/월당 120분) </br>*이 요금제는 미국에서 사용할 수 없습니다.* | MCOPSTN5 |
| 국내 통화 요금제(각 국가의 사용자/월당 240분) </br>*이 요금제는 미국에서 사용할 수 없습니다.* | MCOPSTN6 |
| 통신 크레딧 | MCOPSTNPP |

## <a name="related-content"></a>관련 콘텐츠

- [Teams 추가 기능 라이선스](./microsoft-teams-add-on-licensing.md)
- [Teams에 대한 사용자 액세스 관리](../user-access.md)
- [PowerShell을 통해 라이선스 및 서비스 보기](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [라이선싱에 대한 제품 이름 및 서비스 계획 식별자](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [교육 SKU 참조](../sku-reference-edu.md)
