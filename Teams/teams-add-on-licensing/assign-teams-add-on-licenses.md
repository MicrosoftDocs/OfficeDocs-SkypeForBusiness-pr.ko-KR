---
title: 사용자에 게 팀 추가 기능 라이선스 할당
author: LanaChin
ms.author: v-lanac
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
description: 오디오 회의, 전화 시스템, 통화 요금제 등의 기능에 대해 사용자에 게 팀 추가 기능 라이선스를 할당 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dd09ae11104aa0297a12417d4c267edfc17cf3f
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788742"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>사용자에 게 팀 추가 기능 라이선스 할당

추가 기능 라이선스는 오디오 회의, 전화 시스템, 통화 계획 등의 특정 팀 기능에 대 한 라이선스입니다. 이 문서에서는 개별 사용자와 대규모 사용자 집합에 추가 기능 라이선스를 대량으로 할당 하는 방법에 대해 설명 합니다.

> [!NOTE]
> 추가 기능 라이선스와 함께 제공 되는 팀에 대 한 [팀 추가 기능 라이선스](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) 를 참조 하세요. 또한 사용자가 오디오 회의, 무료 전화 번호, 조직 외부의 전화 번호 착신 통화 등의 기능을 사용할 수 있도록 준비 해야 하는 라이선스에 대 한 정보를 제공 합니다 (요금제에 따라). 사용자에 대해 원하는 기능을 결정 한 후 라이선스를 할당 합니다.

Microsoft 365 관리 센터 또는 PowerShell을 사용 하 여 조직의 사용자에 게 라이선스를 할당할 수 있습니다. 라이선스를 관리 하려면 전역 관리자 또는 사용자 관리 관리자 여야 합니다.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>전화 시스템, 통화 요금제 및 통신 제작진 라이선스를 할당 하기 전에 알아야 할 사항

시작 하기 전에 다음을 검토 하세요.

- 하이브리드 사용자에 대해 온-프레미스 공공 전화망 (PSTN) 연결을 사용 하는 경우에는 전화 시스템 라이선스만 할당 하면 됩니다. 통화 요금제 라이선스를 할당 하지 마세요.

- Microsoft 365와 Microsoft 팀 간의 지연 때문에 라이선스를 할당 한 후 사용자에 게 통화 요금제를 할당 하는 데 최대 24 시간이 걸릴 수 있습니다. 24 시간 후에 사용자에 게 통화 요금제가 할당 되지 않은 경우 [비즈니스 제품에 대 한 고객 지원-관리자 도움말을 참조](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)하세요.

- 올바른 라이선스 수를 구입 하지 않은 경우 오류 메시지가 표시 됩니다. 추가 통화 계획 라이선스를 구입 해야 하는 경우 추가로 구입 하는 옵션을 선택 합니다.

- 사용자가 Enterprise E5 라이선스를 할당 한 경우에도 PSTN에서 전화를 걸거나 받을 수 있도록 [통신 크레딧](../what-are-communications-credits.md) 라이선스를 할당 해야 합니다.

- 사용자에 게 통화 요금제 또는 통신 제작진 라이선스를 배정한 후에는 조직의 전화 번호를 확인 한 다음 해당 번호를 사용자에 게 할당 해야 합니다. 단계별 지침은 [통화 계획 설정을](../set-up-calling-plans.md)참조 하세요.

## <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터 사용

Microsoft 365 관리 센터를 사용 하 여 개별 사용자 또는 작은 사용자 집합에 라이선스를 한 번에 할당할 수 있습니다. **라이선스 페이지 (** 한 번에 최대 20 명의 사용자) 또는 **활성 사용자** 페이지에서 라이선스를 할당할 수 있습니다. 특정 사용자에 대 한 제품 라이선스를 관리 하거나 특정 제품에 대 한 사용자 라이선스를 관리할 것인지 여부에 따라 다른 방법이 선택 됩니다.

단계별 지침은 [사용자에 게 라이선스 할당](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)을 참조 하세요.

수백 또는 수천 명의 사용자와 같은 많은 수의 사용자에 대해 라이선스를 할당 해야 하는 경우 azure [Active Directory (AZURE AD)에서 Powershell 또는 그룹 기반 라이선스](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)를 사용 합니다.  

## <a name="using-powershell"></a>PowerShell 사용

PowerShell을 사용 하 여 사용자에 게 라이선스를 대량으로 할당 합니다.  자세히 알아보려면 [PowerShell을 사용 하 여 사용자 계정에 라이선스 할당](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)을 참조 하세요.

### <a name="example-script"></a>예제 스크립트

다음은 스크립트를 사용 하 여 사용자에 게 라이선스를 할당 하는 방법의 예입니다.

1. IT 전문가를 위한 64 비트 버전의 [Microsoft Online Services 로그인 도우미](https://go.microsoft.com/fwlink/p/?LinkId=286152)를 설치 합니다. rtw.
2. Windows PowerShell 용 Microsoft Azure Active Directory 모듈을 설치 합니다.
    1. 관리자 권한 Windows PowerShell 명령 프롬프트를 엽니다 (관리자로 Windows PowerShell 실행).
    2. 다음 명령을 실행 합니다.
        ```powershell
        Install-Module MSOnline
        ```
    3. NuGet 공급자를 설치 하 라는 메시지가 표시 되 면 **Y**를 입력 한 다음 enter 키를 누릅니다.
    4. PSGallery에서 모듈을 설치 하 라는 메시지가 표시 되 면 **Y**를 입력 한 다음 enter 키를 누릅니다.
3. Windows PowerShell 명령 프롬프트에서 다음 스크립트를 실행 하 여 사용자에 게 라이선스를 할당 \<CompanyName:License> 합니다. 여기서 조직 이름과 할당 하려는 라이선스의 식별자는 여기에 지정 됩니다. 예를 들어 litwareinc: MCOMEETADV.

    식별자가 라이선스의 식별 이름과 다릅니다. 예를 들어 오디오 회의에 대 한 식별자는 MCOMEETADV입니다. 자세한 정보는 [라이선스의 제품 이름 및 SKU 식별자](#product-names-and-sku-identifiers-for-licensing)를 참조 하세요.

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

    예를 들어 Microsoft 365 Enterprise 1 및 오디오 회의 라이선스를 할당 하려면 스크립트에서 다음 구문을 사용 합니다.

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Microsoft 비즈니스 음성 (통화 요금제 불포함) 라이선스를 할당 하려면 스크립트에서 다음 구문을 사용 합니다.

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>라이선스에 대 한 제품 이름 및 SKU 식별자

다음은 PowerShell을 사용 하 여 팀에서 라이선스를 관리할 때 참조할 수 있는 제품 이름 및 해당 SKU 부품 이름의 일부 목록입니다.

자세한 내용은 [PowerShell을 사용 하 여 라이선스 및 서비스 보기](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [라이선스에 대 한 제품 이름 및 서비스 계획 식별자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)및 [교육 SKU 참조](../sku-reference-edu.md)를 참조 하세요.

| 제품 이름| SKU 부품 이름 |
|--------------|---------------|
| Microsoft Enterprise E5 (전화 시스템) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (오디오 회의 없음) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (오디오 회의 포함) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 Business Basic | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 Business Standard | O365_BUSINESS_PREMIUM|
| Microsoft 365 Business | SPB|
| Microsoft Business Voice (캐나다)| BUSINESS_VOICE_MED  |
| Microsoft Business Voice (영국) | BUSINESS_VOICE  |
| Microsoft Business Voice (미국) | BUSINESS_VOICE_MED2  |
| Microsoft Business Voice (통화 요금제 불포함) | BUSINESS_VOICE_DIRECTROUTING  |
| 미국에 대 한 Microsoft Business Voice (통화 요금제 불포함)| BUSINESS_VOICE_DIRECTROUTING _MED |
| 오디오 회의 | MCOMEETADV | 
| 오디오 회의 (분당 요금) (유료)</br>*통신 크레딧을 설정 하 고 사용할 수 있어야 합니다.* | MCOMEETACPEA |
| 전화 시스템 | MCOEV |
| 국내 및 국제 통화 요금제 | MCOPSTN2 |
| 국내 통화 계획 (US/PR/CA에 대 한 사용자 당 3000 분, EU 국가의 경우에는 사용자 당 1200 분) | MCOPSTN1 |
| 국내 통화 요금제 (각 국가의 사용자/월 120 분) </br>*이 요금제는 미국에서 사용할 수 없습니다.* | MCOPSTN5 |
| 국내 통화 요금제 (각 국가의 사용자/월 240 분) </br>*이 요금제는 미국에서 사용할 수 없습니다.* | MCOPSTN6 |
| 통신 크레딧 | MCOPSTNPP |

## <a name="related-topics"></a>관련 항목

- [Teams 추가 기능 라이선스](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [Teams에 대한 사용자 액세스 관리](../user-access.md)
- [PowerShell을 사용 하 여 라이선스 및 서비스 보기](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [라이선싱에 대한 제품 이름 및 서비스 계획 식별자](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [교육 SKU 참조](../sku-reference-edu.md)