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
description: '비즈니스용 Skype, 오디오 회의, 통화 계획 및 통신 크레딧에 전화 시스템 라이선스를 할당하는 방법에 대해 자세히 알아보습니다. '
ms.openlocfilehash: 41f1788e4c562f3b4cc1f43d7875b64805b19ed8
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237494"
---
# <a name="assign-skype-for-business-licenses"></a>비즈니스용 Skype 라이선스 할당

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

이 문서에서는 오디오 회의, 회의 및 통화 계획과 같은 기능에 대해 사용자에게 라이선스를 전화 시스템 팁을 제공합니다. 또한 라이선스를 대량으로 할당하기 위한 스크립트도 제공합니다.

> [!IMPORTANT]
> 구매해야 [비즈니스용 Skype](skype-for-business-and-microsoft-teams-add-on-licensing.md) 라이선스 및 구매 방법에 대한 자세한 내용은 추가  기능 라이선스를 참조하세요. 사용자 Microsoft 365 Office 365 계획에 따라 사용자가 오디오 회의, 무료 전화 번호 및 비즈니스 외부에서 전화 번호를 호출할 수 있는 기능을 얻을 수 있습니다.


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>전화 시스템 및 호출 계획: 팁 할당을 위한 스크립트 및 스크립트

오디오 회의, 회의 및 통화 계획 라이선스를 할당하기 전에 알아야 전화 시스템 알아야 합니다.

- **하이브리드 사용자를 위해 프레미스 PSTN 연결을 사용하나요?** 이 경우 라이선스를 **할당하기만 전화 시스템** 합니다. 통화 **계획을** 할당하지 말아야 합니다.

- **라이선스를** 할당한 후 대기 시간: 온라인에서 Microsoft 365 또는 Office 365 비즈니스용 Skype 대기 시간으로 인하여 사용자가 라이선스를 할당한 후 통화 요금제에 할당되는 데 최대 24시간이 걸릴 수 있습니다. 24시간 후에 사용자에게 통화 계획이 할당되지 않은 경우 비즈니스 제품 지원 [- 관리자 도움말에 문의하세요.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

- **오류 메시지**: 올바른 라이선스 수를 구입하지 않은 경우 오류 메시지가 표시됩니다. 더 많은 통화 계획 라이선스를 구입해야 하는 경우 더 구입 **을 선택해야 합니다.**
    
- **다음 단계:** 사용자에게 통화 계획 라이선스를 할당한 후 조직의 전화 번호를 받은 다음 해당 번호를 조직의 사용자에게 할당해야 합니다. 단계별 지침은 통화 계획 설정 [을 참조하세요.](/microsoftteams/set-up-calling-plans)
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>한 사용자에게 전화 시스템 및 통화 계획 라이선스를 할당하는 방법

단계는 라이선스 또는 라이선스를 Microsoft 365 Office 365 동일합니다. 비즈니스용 라이선스 할당 또는 [Microsoft 365 참조](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>대량으로 전화 시스템 계획 라이선스를 할당하는 방법

1. IT **전문가 Microsoft Online Services Sign-In RTW에 대한 지원 도우미를 설치합니다.** 모듈이 설치되어 있지 않은가요? IT [Microsoft Online Services Sign-In RTW용](https://go.microsoft.com/fwlink/?LinkId=625123) 도우미를 참조하여 다운로드합니다.

2. 모듈을 **Windows Azure Active Directory 설치합니다.** 모듈이 설치되어 있지 않은가요? 다운로드 지침 및 cmdlet [구문은](/previous-versions/azure/jj151815(v=azure.100)) Windows PowerShell 사용하여 Azure AD 관리를 참조하세요.

3. 모듈이 설치되면 Windows PowerShell 명령 프롬프트 및 다음 구문을 사용하여 사용자에게 라이선스를 할당합니다.

   이 예제에서는 Enterprise 및 전화 시스템 **E3** 라이선스를 **할당합니다.** 

   스크립트의 라이선스 또는 제품 이름의 이름은 이탈식 텍스트에 나열됩니다(예제 전화 시스템 스크립팅에 사용되는 **SKUS** 및 호출 계획 제품 이름 참조).

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>전화 시스템 및 호출 계획 제품 이름 또는 스크립팅에 사용되는 SKUS

|**제품 이름**|**SKU 부품 이름**|
|:-----|:-----|
|Enterprise E5(전화 시스템)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|비즈니스용 Skype 온라인 독립 실행형 계획 2  <br/> |MCOSTANDARD  <br/> |
|전화 시스템  <br/> |MCOEV  <br/> |
|국제 통화 플랜  <br/> |MCOPSTN2  <br/> |
|국내 통화 계획(미국 3000분/ EU 1200분 요금제)  <br/> |MCOPSTN1  <br/> |
|국내 통화 계획(120분 통화 계획)  <br/> |MCOPSTN5  <br/> |
|국내 통화 계획(240분 통화 계획)  <br/> |MCOPSTN6  <br/> |
|통신 크레딧  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>오디오 회의: 팁 할당하기 위한 스크립트 및 스크립트

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>오디오 회의 라이선스를 할당하기 전에 알아야 할 작업

- **타사** 오디오 회의 공급자: 다른 사용자가 타사 오디오 회의 공급자를 사용하기 위해 이미 설정되어 있는 경우 오디오  회의 라이선스를 할당하면 Microsoft를 오디오 회의 공급자로 사용하기로 변경됩니다. 타사 공급자로 다시 변경할 수 있습니다.

- 다음 단계: **오디오** 회의 라이선스를 할당한 후 오디오 회의 공급자를 할당해야 합니다. [Microsoft를 오디오 회의 공급자로 할당]을 참조하세요.

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>오디오 회의 라이선스를 한 사용자에게 할당하는 방법

단계는 라이선스 또는 라이선스를 Microsoft 365 Office 365 동일합니다. 비즈니스용 라이선스 할당 또는 [Microsoft 365 참조](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>오디오 회의 라이선스를 대량으로 할당하는 방법

1. IT 전문가 [Microsoft Online Services Sign-In 도우미를 다운로드하여 설치합니다.](https://go.microsoft.com/fwlink/?LinkId=625123)

2. 모듈을 **다운로드하고 Windows Azure Active Directory 설치합니다.** 다운로드 지침 및 cmdlet[구문은](/previous-versions/azure/jj151815(v=azure.100)) Windows PowerShell 사용하여 Azure AD 관리를 참조하세요.

    모듈이 설치되면 Windows PowerShell 명령 프롬프트 및 다음 구문을 사용하여 사용자에게 라이선스를 할당합니다.

    스크립트의 라이선스 또는 제품 이름의 이름은 이탈리스크 텍스트에 나열됩니다. 모든 제품 이름에 대한 스크립팅에 사용되는 오디오 회의 제품 이름 또는 [SKUS를](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) 참조합니다.

    이 예제에서는 오디오 Enterprise 라이선스와 함께 E3 라이선스를 할당합니다.

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
|비즈니스용 Skype 온라인 독립 실행형 계획 2  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E5(오디오 회의 없이)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Enterprise E5(오디오 회의 사용)  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>통신 크레딧

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>Communications Credits 라이선스를 할당하기 전에 알아야 할 작업

- **Enterprise E5** 고객: 사용자가 E5 Enterprise 할당된 경우에도 **Communications Credits** 라이선스를 할당하는 것이 좋습니다.
    
- **다음 단계**: 이러한 라이선스를 할당한 후 조직의 전화 번호를 받은 다음 해당 번호를 조직의 사용자에게 할당해야 합니다. 단계별 지침은 통화 계획 설정 [을 참조하세요.](/microsoftteams/set-up-calling-plans)
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>한 사용자에게 Communications 크레딧 라이선스를 할당하는 방법

단계는 라이선스 또는 라이선스를 Microsoft 365 Office 365 동일합니다. 비즈니스용 라이선스 할당 또는 [Microsoft 365 참조](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>통신 크레딧 라이선스를 일괄 할당하는 방법

오디오 회의 라이선스를 할당하기 위한 샘플 **스크립트를** 살펴 봐야 합니다. **Communications Credits** 라이선스를 할당하기 위한 정보로 업데이트합니다.

## <a name="related-topics"></a>관련 주제
  
[통화 플랜 설정](/microsoftteams/set-up-calling-plans)
  
[자금 추가 및 커뮤니케이션 크레딧 관리](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
