---
title: 비즈니스용 Skype 라이선스 할당
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: '전화 시스템, 오디오 회의, 통화 계획 및 통신 크레딧에 대한 비즈니스용 Skype 라이선스를 할당하는 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: beb4fa46133aa7a09ce3d0de0a08392dbf2d2591
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106494"
---
# <a name="assign-skype-for-business-licenses"></a>비즈니스용 Skype 라이선스 할당

이 문서에서는 오디오 회의, 전화 시스템 및 통화 계획과 같은 기능에 대해 사용자에게 라이선스를 할당하는 방법에 대한 팁을 제공합니다. 또한 라이선스를 대량으로 할당하기 위한 스크립트도 제공합니다.

> [!IMPORTANT]
> Microsoft [](skype-for-business-and-microsoft-teams-add-on-licensing.md) 365 또는 Office 365 요금제에  따라 구매해야 하는 라이선스 및 구매 방법에 대한 자세한 내용은 비즈니스용 Skype 추가 기능 라이선스를 참조하세요. 따라서 사용자는 오디오 회의, 무료 전화 번호 및 비즈니스 외부에서 전화 번호를 호출할 수 있습니다.


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>전화 시스템 및 통화 계획: 라이선스 할당을 위한 팁 및 스크립트

오디오 회의, 전화 시스템 및 통화 계획 라이선스를 할당하기 전에 알아야 할 작업

- **하이브리드 사용자를 위해 프레미스 PSTN 연결을 사용하나요?** 이 경우 전화 시스템 라이선스만 **할당하면** 됩니다. 통화 **계획을** 할당하지 말아야 합니다.

- **라이선스를** 할당한 후 대기 시간: Microsoft 365 또는 Office 365와 비즈니스용 Skype Online 간의 대기 시간 때문에 라이선스를 할당한 후 사용자가 통화 요금제에 할당되는 데 최대 24시간이 걸릴 수 있습니다. 24시간 후에 사용자에게 통화 계획이 할당되지 않은 경우 비즈니스 제품 지원 [- 관리자 도움말에 문의하세요.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

- **오류 메시지**: 올바른 라이선스 수를 구입하지 않은 경우 오류 메시지가 표시됩니다. 더 많은 통화 계획 라이선스를 구입해야 하는 경우 더 구입 **을 선택해야 합니다.**
    
- **다음 단계:** 사용자에게 통화 계획 라이선스를 할당한 후 조직의 전화 번호를 받은 다음 해당 번호를 조직의 사용자에게 할당해야 합니다. 단계별 지침은 통화 계획 설정 [을 참조하세요.](/microsoftteams/set-up-calling-plans)
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>전화 시스템 및 통화 계획 라이선스를 한 사용자에게 할당하는 방법

단계는 Microsoft 365 또는 Office 365 라이선스를 할당하는 경우와 동일합니다. 비즈니스용 Microsoft 365 라이선스 할당 또는 [제거를 참조합니다.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>전화 시스템 및 통화 계획 라이선스를 대량으로 할당하는 방법

1. IT **전문가 Microsoft Online Services Sign-In RTW에 대한 지원 도우미를 설치합니다.** 모듈이 설치되어 있지 않은가요? IT [Microsoft Online Services Sign-In RTW용](https://go.microsoft.com/fwlink/?LinkId=625123) 도우미를 참조하여 다운로드합니다.

2. Active **Directory Windows Azure 설치합니다.** 모듈이 설치되어 있지 않은가요? 다운로드 지침 및 cmdlet [구문은](/previous-versions/azure/jj151815(v=azure.100)) Windows PowerShell 사용하여 Azure AD 관리를 참조하세요.

3. 모듈을 설치하면 Windows PowerShell 명령 프롬프트 및 다음 구문을 사용하여 사용자에게 라이선스를 할당합니다.

   이 예제에서는 전화 시스템 및 국내  통화 계획 라이선스와 함께 **Enterprise E3** 라이선스를 **할당합니다.**

   스크립트의 라이선스 또는 제품 이름의 이름은 이탈식 텍스트에 나열됩니다(예제 다음의 스크립팅에 사용되는 전화 시스템 및 호출 계획 제품 이름 또는 **SKUS** 참조).

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>전화 시스템 및 통화 계획 제품 이름 또는 스크립팅에 사용되는 SKUS

|**제품 이름**|**SKU 부품 이름**|
|:-----|:-----|
|Enterprise E5(전화 시스템 사용)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|비즈니스용 Skype Online 독립 실행형 계획 2  <br/> |MCOSTANDARD  <br/> |
|전화 시스템  <br/> |MCOEV  <br/> |
|국제 통화 플랜  <br/> |MCOPSTN2  <br/> |
|국내 통화 계획(미국 3000분/ EU 1200분 요금제)  <br/> |MCOPSTN1  <br/> |
|국내 통화 계획(120분 통화 계획)  <br/> |MCOPSTN5  <br/> |
|국내 통화 계획(240분 통화 계획)  <br/> |MCOPSTN6  <br/> |
|통신 크레딧  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>오디오 회의: 라이선스 할당을 위한 팁 및 스크립트

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>오디오 회의 라이선스를 할당하기 전에 알아야 할 작업

- **타사** 오디오 회의 공급자: 다른 사용자가 타사 오디오 회의 공급자를 사용하기 위해 이미 설정되어 있는 경우 오디오  회의 라이선스를 할당하면 Microsoft를 오디오 회의 공급자로 사용하기로 변경됩니다. 타사 공급자로 다시 변경할 수 있습니다.

- 다음 단계: **오디오** 회의 라이선스를 할당한 후 오디오 회의 공급자를 할당해야 합니다. [Microsoft를 오디오 회의 공급자로 할당]을 참조하세요.

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>오디오 회의 라이선스를 한 사용자에게 할당하는 방법

단계는 Microsoft 365 또는 Office 365 라이선스를 할당하는 경우와 동일합니다. 비즈니스용 Microsoft 365 라이선스 할당 또는 [제거를 참조합니다.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>오디오 회의 라이선스를 대량으로 할당하는 방법

1. IT 전문가 [Microsoft Online Services Sign-In 도우미를 다운로드하여 설치합니다.](https://go.microsoft.com/fwlink/?LinkId=625123)

2. Active Directory **모듈을 Windows Azure 설치합니다.** 다운로드 지침 및 cmdlet[구문은](/previous-versions/azure/jj151815(v=azure.100)) Windows PowerShell 사용하여 Azure AD 관리를 참조하세요.

    모듈을 설치하면 Windows PowerShell 명령 프롬프트 및 다음 구문을 사용하여 사용자에게 라이선스를 할당합니다.

    스크립트의 라이선스 또는 제품 이름의 이름은 이탈리스크 텍스트에 나열됩니다. 모든 제품 이름에 대한 스크립팅에 사용되는 오디오 회의 제품 이름 또는 [SKUS를](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) 참조합니다.

    이 예제에서는 오디오 회의 라이선스와 함께 Enterprise E3 라이선스를 할당합니다.

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>스크립팅에 사용되는 오디오 회의 제품 이름 또는 SKUS
<a name="sku"> </a>

|**제품 이름**|**SKU 부품 이름**|
|:-----|:-----|
|오디오 회의  <br/> |MCOMEETADV  <br/> |
|비즈니스용 Skype Online 독립 실행형 계획 2  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E5(오디오 회의 없이)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise E5(오디오 회의 사용)  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>통신 크레딧

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>Communications Credits 라이선스를 할당하기 전에 알아야 할 작업

- **Enterprise E5 고객:** 사용자에게 Enterprise E5 라이선스가 할당되어 있는 경우에도 **Communications Credits** 라이선스를 할당하는 것이 좋습니다.
    
- **다음 단계**: 이러한 라이선스를 할당한 후 조직의 전화 번호를 받은 다음 해당 번호를 조직의 사용자에게 할당해야 합니다. 단계별 지침은 통화 계획 설정 [을 참조하세요.](/microsoftteams/set-up-calling-plans)
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>한 사용자에게 Communications 크레딧 라이선스를 할당하는 방법

단계는 Microsoft 365 또는 Office 365 라이선스를 할당하는 경우와 동일합니다. 비즈니스용 Microsoft 365 라이선스 할당 또는 [제거를 참조합니다.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>통신 크레딧 라이선스를 일괄 할당하는 방법

오디오 회의 라이선스를 할당하기 위한 샘플 **스크립트를** 살펴 봐야 합니다. **Communications Credits** 라이선스를 할당하기 위한 정보로 업데이트합니다.

## <a name="related-topics"></a>관련 항목
  
[통화 플랜 설정](/microsoftteams/set-up-calling-plans)
  
[자금 추가 및 커뮤니케이션 크레딧 관리](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
