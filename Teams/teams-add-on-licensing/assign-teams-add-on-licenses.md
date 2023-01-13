---
title: 사용자에게 Teams 추가 기능 라이선스 할당
author: DaniEASmith
ms.author: danismith
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: 오디오 회의, 전화 시스템 및 통화 플랜과 같은 기능을 위해 사용자에게 Teams 추가 기능 라이선스를 할당하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 162169bd3aa7a1641133e8729d4872f8547b58ed
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69799934"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>사용자에게 Teams 추가 기능 라이선스 할당

추가 기능 라이선스는 오디오 회의, 전화 시스템 및 통화 플랜과 같은 특정 Teams 기능에 대한 라이선스입니다. 이 문서에서는 개별 사용자 및 대규모 사용자 집합에 추가 기능 라이선스를 대량으로 할당하는 방법을 설명합니다.

> [!NOTE]
> 추가 기능 [라이선스와](./microsoft-teams-add-on-licensing.md) 함께 사용할 수 있는 Teams 기능에 대한 Teams 추가 기능 라이선스를 참조하세요. 또한 플랜에 따라 구매해야 하는 라이선스와 구매 방법에 대한 정보를 찾을 수 있습니다. 사용자에게 원하는 기능을 결정한 후 라이선스를 할당합니다.

Microsoft 365 관리 센터 또는 PowerShell을 사용하여 조직의 사용자에게 라이선스를 할당할 수 있습니다. 라이선스를 관리하려면 전역 관리자 또는 사용자 관리 관리자여야 합니다.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>전화 시스템, 통화 플랜 및 통신 크레딧 라이선스를 할당하기 전에 알아야 할 사항

시작하기 전에 다음 요구 사항을 검토합니다.

- 사용자에 대해 온-프레미스 PSTN(공용 전환 전화 네트워크) 연결을 사용하는 경우 Teams 전화 표준 요금제 라이선스만 할당하면 됩니다. 통화 플랜 라이선스를 할당하지 마세요.

- 사용자에게 Microsoft 통화 플랜을 할당한 후 Teams 클라이언트에 다이얼 패드가 표시되기까지 최대 24시간이 걸릴 수 있습니다. 다이얼 패드가 24시간 안에 표시되지 않으면 [다이얼 패드 구성](../dial-pad-configuration.md)을 확인합니다. 필요한 경우 [지원에 문의할](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) 수도 있습니다.

- 올바른 라이선스 수를 구입하지 않은 경우 오류 메시지가 표시됩니다. 더 많은 통화 플랜 라이선스를 구입해야 하는 경우 더 많이 구입하는 옵션을 선택합니다.

- 사용자에게 Enterprise E5 라이선스가 할당된 경우에도 PSTN에 연결해야 합니다. Microsoft Teams 통화 플랜, 직접 라우팅 또는 운영자 연결을 비롯한 여러 [PSTN 연결 옵션이](../pstn-connectivity.md) 있습니다.

- 통화 플랜 또는 통신 크레딧 라이선스를 사용자에게 할당한 후에는 조직의 전화 번호를 받은 다음 사용자에게 해당 번호를 할당해야 합니다. 단계별 지침은 [통화 플랜 설정을 참조하세요](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터 사용

Microsoft 365 관리 센터 사용하여 개별 사용자 또는 소규모 사용자 집합에 라이선스를 한 번에 할당합니다.

라이선스 페이지(한 번에 최대 20명의 사용자) 또는 **활성 사용자** 페이지(한 번에 최대 40명의 사용자)에 **라이선스** 를 할당합니다. 선택하는 방법은 특정 사용자의 제품 라이선스를 관리하거나 특정 제품에 대한 사용자 라이선스를 관리할지 여부에 따라 달라집니다.

단계별 지침은 [사용자에게 라이선스 할당을 참조하세요](/microsoft-365/admin/manage/assign-licenses-to-users).

수백 또는 수천 명의 사용자와 같은 많은 수의 사용자에 대한 라이선스를 할당해야 하는 경우 [Azure Active Directory(Azure AD)에서](/azure/active-directory/users-groups-roles/licensing-groups-assign) PowerShell 또는 그룹 기반 라이선스를 사용합니다.

## <a name="using-powershell"></a>PowerShell 사용

PowerShell을 사용하여 사용자에게 라이선스를 대량으로 할당합니다. 자세한 내용은 [PowerShell을 사용하여 사용자 계정에 라이선스 할당을](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell) 참조하세요.

### <a name="example-script"></a>예제 스크립트

다음은 스크립트를 사용하여 사용자에게 라이선스를 할당하는 방법의 예입니다.

1. [Windows PowerShell Microsoft Azure Active Directory 모듈을 설치](/powershell/azure/active-directory/install-msonlinev1)합니다.
2. Windows PowerShell 명령 프롬프트에서 다음 스크립트를 실행하여 사용자에게 라이선스를 할당합니다. 여기서 `CompanyName:License` 은 조직 이름과 할당하려는 라이선스의 식별자입니다. 예를 들어 입니다 `litwareinc:MCOMEETADV`.

    식별자는 라이선스의 식별자와 다릅니다. 예를 들어 오디오 회의의 식별자는 입니다 `MCOMEETADV`. 자세한 내용은 [라이선스에 대한 제품 이름 및 SKU 식별자를](#product-names-and-sku-identifiers-for-licensing) 참조하세요.

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

    예를 들어 Microsoft 365 Enterprise E1 및 오디오 회의 라이선스를 할당하려면 스크립트에서 다음 구문을 사용합니다.

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    통화 플랜 라이선스를 사용하여 Teams Phone을 할당하려면 스크립트에서 다음 구문을 사용합니다.

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>라이선스에 대한 제품 이름 및 SKU 식별자

다음은 PowerShell을 사용하여 Teams에서 라이선스를 관리할 때 참조할 수 있는 제품 이름 및 해당 SKU 부분 이름의 일부 목록입니다.

자세한 내용은 [PowerShell을 사용하여 라이선스 및 서비스 보기](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [라이선스에 대한 제품 이름 및 서비스 계획 식별자](/azure/active-directory/users-groups-roles/licensing-service-plan-reference) 및 [Education SKU 참조를 참조하세요](../sku-reference-edu.md).

| 제품 이름| SKU 파트 이름 |
|--------------|---------------|
| Microsoft Enterprise E5(전화 시스템 포함) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5(오디오 회의 없음) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5(오디오 회의 포함) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | Spb|
| 오디오 회의 | MCOMEETADV |
| 오디오 회의 분당 지불(종량제) 통신 크레딧을 설정하고 사용하도록 설정해야 합니다.* | MCOMEETACPEA |
| Teams 전화 표준 요금제 | MCOEV |
| 통화 플랜이 포함된 Teams 전화 | MCOTEAMS_ESSENTIALS |
| 국제 통화 플랜 | MCOPSTN2 |
| 국내 통화 플랜(미국/PR/CA의 경우 사용자/월 3,000분, EU 국가의 경우 사용자/월 1200분) | MCOPSTN1 |
| 국내 통화 플랜(각 국가의 사용자/월 120분) </br>*이 플랜은 미국 사용할 수 없습니다.* | MCOPSTN5 |
| 국내 통화 플랜(각 국가의 사용자/월 240분) </br>*이 플랜은 미국 사용할 수 없습니다.* | MCOPSTN6 |
| 통신 크레딧 | MCOPSTNPP |
| 종량제 통화 플랜(영역 1 국가) | MCOPSTN_PAYG_1 |
| 종량제 통화 플랜(영역 2 국가) | MCOPSTN_PAYG_2 |
| Microsoft Teams 룸 베이직 | Microsoft_Teams_Rooms_Basic |
| 오디오 회의 없이 Microsoft Teams 룸 베이직 | Microsoft_Teams_Rooms_Basic_without_Audio_Conferencing |
| Microsoft Teams 룸 Pro | Microsoft_Teams_Rooms_Pro |
| 오디오 회의 없이 Microsoft Teams 룸 Pro | Microsoft_Teams_Rooms_Pro_without_Audio_Conferencing |
| Microsoft Teams 공유 디바이스 | MCOCAP |
| Microsoft Teams Premium | Microsoft_Teams_Premium |

## <a name="related-content"></a>관련 콘텐츠

- [Teams 추가 기능 라이선스](./microsoft-teams-add-on-licensing.md)
- [Teams에 대한 사용자 액세스 관리](../user-access.md)
- [PowerShell을 사용하여 라이선스 및 서비스 보기](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [라이선싱에 대한 제품 이름 및 서비스 계획 식별자](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Education SKU 참조](../sku-reference-edu.md)
