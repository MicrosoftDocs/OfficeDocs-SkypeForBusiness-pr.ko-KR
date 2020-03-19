---
title: Teams 라이선스 할당
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: 오디오 회의, 전화 시스템, 통화 요금제 등의 기능에 대 한 라이선스를 할당 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b962a29f163a094f5b7c74f7504a5d78e310561a
ms.sourcegitcommit: 86366b66b15870fe83cbb76e1ae7aa1ce9b3bfe1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42858561"
---
# <a name="assign-microsoft-teams-licenses"></a>Microsoft 팀 라이선스 할당

오디오 회의, 전화 시스템, 통화 요금제 등의 기능을 위해 사용자에 게 라이선스를 할당할 수 있습니다. 이 문서에서는 이러한 라이선스를 대량 및 개별 사용자에 게 추가 하는 방법에 대해 설명 합니다. 

> [!IMPORTANT]
> Office 365 요금제에 따라 구입 해야 하는 라이선스 및 구입 방법에 대 한 자세한 내용은 [Microsoft 팀 추가 기능 라이선스](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 를 참조 하세요. 사용자가 오디오 회의, 수신자 부담 전화 번호, 그리고 회사 외부의 전화 번호를 받을 수 있는 기능을 제공 합니다.

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>전화 시스템 및 통화 계획: 라이선스 할당을 위한 팁 및 스크립트

오디오 회의, 전화 시스템, 통화 계획 라이선스를 할당 하기 전에 알아야 할 사항에는 다음이 나와 있습니다.

- **하이브리드 사용자에 온-프레미스 PSTN 연결을 사용 하 고 계십니까?** 그렇다면 전화 시스템 라이선스를 할당 하기만 하면 됩니다. 통화 요금제는 배정 하지 않아야 합니다.

- **라이선스 할당 후 대기 시간**: Office 365와 Microsoft 팀 간의 지연 때문에 라이선스를 할당 한 후 사용자에 게 통화 요금제를 할당 하는 데 최대 24 시간이 걸릴 수 있습니다. 24 시간이 지난 후에는 사용자에 게 통화 요금제가 배정 되지 않은 경우 [비즈니스 제품에 대 한 고객 지원에 문의-관리자 도움말](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)을 참조 하세요.

- **오류 메시지**: 올바른 라이선스 수를 구입 하지 않은 경우 오류 메시지가 표시 됩니다. 추가 통화 계획 라이선스를 구입 해야 하는 경우에는 **추가 구입**을 선택 합니다.

- **다음 단계**: 사용자에 게 통화 계획 라이선스를 할당 한 후 조직의 전화 번호를 받은 후 조직의 사용자에 게 해당 번호를 할당 해야 합니다. 단계별 지침은 [통화 계획 설정을](set-up-calling-plans.md)참조 하세요.

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>한 사용자에 게 전화 시스템 및 통화 계획 라이선스 할당

단계는 Office 365 라이선스를 할당 하는 것과 동일 합니다. [비즈니스용 Office 365에 대 한 라이선스 할당 또는 제거를](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)참조 하세요.

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>전화 시스템 및 통화 계획 라이선스를 대량으로 할당

1. IT 전문가를 위한 Microsoft Online Services 로그인 도우미 (RTW)를 설치 합니다. 모듈이 설치 되어 있지 않은 경우 [It 전문가를 위한 Microsoft Online Services 로그인 도우미](https://go.microsoft.com/fwlink/?LinkId=625123) 를 참조 하세요 rtw를 다운로드 하 여 다운로드할 수 있습니다.

2. Windows Azure Active Directory 모듈을 설치 합니다. 모듈이 설치 되어 있지 않은 경우 다운로드 지침 및 cmdlet 구문에 대해 [Windows PowerShell을 사용 하 여 AZURE AD 관리](https://go.microsoft.com/fwlink/p/?LinkId=320628) 를 참조 하세요.

3. 모듈을 설치한 후에는 Windows PowerShell 명령 프롬프트 및 다음 구문을 사용 하 여 라이선스를 사용자에 게 할당 합니다.

이 예에서는 전화 시스템 및 국내 통화 요금제 라이선스와 함께 Enterprise E3 라이선스를 할당 합니다.

스크립트의 라이선스 또는 제품 이름 이름이 기울임꼴로 표시 됩니다 (예제 이후 스크립트 [에 사용 되는 전화 시스템 및 통화 계획 제품 이름 또는 sku](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting)참조).

```powershell
#Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.

#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline
#Authenticate to MSOLservice.
Connect-MSOLService
#File prompt to select the userlist txt file.
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
$OFD = New-Object System.Windows.Forms.OpenFileDialog
$OFD.filter = "text files (*.*)| *.txt"
$OFD.ShowDialog() | Out-Null
$OFD.filename
If ($OFD.filename -eq '')
{
 Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}
#Create a variable of all users.
$users = Get-Content $OFD.filename
#License each user in the $users variable.
#Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
International Calling.
for each ($user in $users)
 {
 Write-host "Assigning License: $user"
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
 Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
 }

```

## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>전화 시스템 및 통화 플랜 스크립트에 사용 되는 제품 이름 또는 Sku

| 제품 이름 | SKU 부품 이름 |
|--------------|---------------|
| Enterprise E5 (전화 시스템) | ENTERPRISEPREMIUM |
| Enterprise E3 | ENTERPRISEPACK | 
| Enterprise E1 | STANDARDPACK | 
| 전화 시스템 | MCOEV |
| 국내 & 국제 통화 요금제 | MCOPSTN2 |
| 국내 통화 계획 (US/PR/CA에 대 한 사용자 당 3000 분, EU 국가의 경우에는 사용자 당 1200 분) | MCOPSTN1 |
| 국내 통화 요금제 (각 국가의 사용자/월 120 분) </br>*참고:이 요금제는 미국에서 사용할 수 없습니다*. | MCOPSTN5 |
| 국내 통화 요금제 (각 국가의 사용자/월 240 분) </br>*참고:이 요금제는 미국에서 사용할 수 없습니다*. | MCOPSTN6 |
| 통신 크레딧 | MCOPSTNPP | 

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>한 사용자에 게 오디오 회의 라이선스 할당

단계는 Office 365 라이선스를 할당 하는 것과 동일 합니다. [비즈니스용 Office 365에 대 한 라이선스 할당 또는 제거를](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)참조 하세요.

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>대량으로 오디오 회의 라이선스 할당

1. [IT 전문가를 위한 Microsoft Online Services 로그인 도우미](https://go.microsoft.com/fwlink/?LinkId=625123)를 다운로드 하 여 설치 합니다 rtw.

2. Windows Azure Active Directory 모듈을 다운로드 하 고 설치 합니다. 다운로드 지침 및 cmdlet 구문에 대해 [Windows PowerShell을 사용 하 여 AZURE AD 관리](https://go.microsoft.com/fwlink/p/?LinkId=320628) 를 참조 하세요.

모듈을 설치한 후에는 Windows PowerShell 명령 프롬프트 및 다음 구문을 사용 하 여 라이선스를 사용자에 게 할당 합니다.

스크립트의 라이선스 또는 제품 이름 이름이 기울임꼴로 표시 됩니다. 모든 제품 이름에 대해 [스크립트에 사용 되는 오디오 회의 제품 이름 또는 sku](#audio-conferencing-product-names-or-skus-used-for-scripting) 를 참조 하세요.

이 예제에서는 음성 회의 라이선스와 함께 Enterprise E3 라이선스를 할당 합니다.

```powershell
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
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
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
    }
```

## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>스크립트에 사용 되는 오디오 회의 제품 이름 또는 SKU

| 제품 이름 | SKU 부품 이름 |
|--------------|---------------|
| 오디오 회의 (구독) | MCOMEETADV | 
| 오디오 회의 (분당 요금) (유료)</br>*참고: 통신 크레딧이 설정 및 활성화 되어 있어야*합니다. |    MCOMEETACPEA |
| Enterprise E1 | STANDARDPACK | 
| Enterprise E3 | ENTERPRISEPACK |
| Enterprise E5 (오디오 회의 없음) |     ENTERPRISEPREMIUM_NOPSTNCONF |
| Enterprise E5 (오디오 회의 포함) | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>통신 크레딧

다음은 통신 크레딧 라이선스를 지정 하기 전에 알아야 할 사항입니다.

- **Enterprise e5 고객**: 사용자에 게 Enterprise e5 라이선스가 할당 된 경우에도 통신 크레딧 라이선스를 할당 하는 것이 좋습니다.

- **다음 단계**: 이러한 라이선스를 할당 한 후 조직의 전화 번호를 얻은 다음 조직의 사용자에 게 해당 번호를 할당 해야 합니다. 단계별 지침은 [통화 계획 설정을](set-up-calling-plans.md)참조 하세요.

## <a name="assign-a-communications-credits-license-to-one-user"></a>한 명의 사용자에 게 통신 제작진 라이선스 할당

단계는 Office 365 라이선스를 할당 하는 것과 동일 합니다. [비즈니스용 Office 365에 대 한 라이선스 할당 또는 제거를](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)참조 하세요.

## <a name="assign-communications-credits-licenses-in-bulk"></a>의사 소통 제작진 라이선스를 대량으로 배정

오디오 회의 라이선스를 할당 하는 샘플 스크립트를 살펴보세요. 통신 제작진 라이선스를 할당 하는 정보로 업데이트 하세요.

## <a name="related-topics"></a>관련 항목

[통화 플랜 설정](set-up-calling-plans.md)
</br>
[자금 추가 및 통신 크레딧 관리](add-funds-and-manage-communications-credits.md)
