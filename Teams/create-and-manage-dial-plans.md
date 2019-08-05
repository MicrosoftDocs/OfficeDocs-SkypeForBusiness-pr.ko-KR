---
title: 다이얼 플랜 만들기 및 관리
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Office 365에서 통화 다이얼 플랜 (PSTN 통화 다이얼 플랜)을 만들고 관리 하는 방법에 대해 알아봅니다. '
ms.openlocfilehash: 5254a2d63abeffa0b3452ed309d49272affcaf05
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "36184367"
---
# <a name="create-and-manage-dial-plans"></a>다이얼 플랜 만들기 및 관리

조직에 대 한 다이얼 플랜을 계획 하 고 통화 라우팅에 대해 만들어야 하는 모든 정규화 규칙을 확인 한 후에는 Windows PowerShell을 사용 하 여 다이얼 플랜을 만들고 설정을 변경 해야 합니다.
  
> [!NOTE]
> 비즈니스용 Skype 관리 센터를 사용 하 여 다이얼 플랜을 만들고 관리할 수 없습니다. 
  
## <a name="verifying-and-starting-remote-powershell"></a>원격 PowerShell 확인 및 시작

 **Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**
  
1. 버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.
    
2. **Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.
    
3. 버전 3.0 이상이 없는 경우 Windows PowerShell 업데이트를 다운로드 하 여 설치 해야 합니다. Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
4. 비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)의 Microsoft 다운로드 센터에서 다운로드할 수 있습니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
자세한 정보를 알고 싶은 경우 [모든 Office 365 서비스에 단일 Windows PowerShell 창으로 연결](https://technet.microsoft.com/EN-US/library/dn568015.aspx)을 참조 하세요.
  
 **Windows PowerShell 세션 시작**
  
1. **시작 메뉴** > 에서**Windows PowerShell**을 실행 합니다.
    
2. **Windows PowerShell** 창에서 다음을 실행 하 여 Office 365 조직에 연결 합니다.
    
    > [!NOTE]
    > 비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.
  
> 
>   ```
>     Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>     $credential = Get-Credential
>     $session = New-CsOnlineSession -Credential $credential
>     Import-PSSession $session
>   ```

Windows PowerShell을 시작 하는 방법에 대 한 자세한 내용은 [단일 Windows powershell 창에서 모든 Office 365 서비스에 연결](https://technet.microsoft.com/EN-US/library/dn568015.aspx) 또는 [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online에](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)연결을 참조 하세요.
  
## <a name="creating-and-managing-your-dial-plans"></a>다이얼 플랜 만들기 및 관리

단일 cmdlet 또는 PowerShell 스크립트를 사용 하 여 테 넌 트 다이얼 플랜을 만들고 관리할 수 있습니다.
  
### <a name="using-single-cmdlets"></a>단일 cmdlet 사용

- 새 다이얼 플랜을 만들려면 다음을 실행 합니다.
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    다른 예제 및 매개 변수는 [New-Csten앤틸리스 다이얼 플랜](https://technet.microsoft.com/library/mt775026.aspx)을 참조 하세요.
    
- 기존 다이얼 플랜에 대 한 설정을 변경 하려면 다음을 실행 합니다.
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    다른 예제 및 매개 변수는 [Set-Csten앤틸리스 다이얼 플랜](https://technet.microsoft.com/library/mt775023.aspx)을 참조 하세요.
    
- 다이얼 플랜에 사용자를 추가 하려면 다음을 실행 합니다.
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    다른 예제 및 매개 변수는 [-Csten앤틸리스 다이얼 플랜](https://technet.microsoft.com/library/mt775021.aspx)을 참조 하세요.
    
- 다이얼 플랜에 대 한 설정을 보려면 다음을 실행 합니다.
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    다른 예제 및 매개 변수는 [Get-Csten앤틸리스 다이얼 플랜](https://technet.microsoft.com/library/mt775024.aspx)을 참조 하세요.
    
- 다이얼 플랜을 삭제 하려면 다음을 실행 합니다.
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    다른 예제 및 매개 변수는 [제거-Csten앤틸리스 다이얼 플랜](https://technet.microsoft.com/library/mt775020.aspx)을 참조 하세요.
    
- 유효 다이얼 플랜의 설정을 보려면 다음을 실행 합니다.
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    다른 예제 및 매개 변수는 [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx)을 참조 하세요.
    
- 다이얼 플랜의 유효 설정을 테스트 하려면 다음을 실행 합니다.
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    다른 예제 및 매개 변수는 [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx)을 참조 하세요.
    
### <a name="using-a-powershell-script"></a>PowerShell 스크립트 사용

이 작업을 실행 하 여 테 넌 트 다이얼 플랜을 먼저 삭제할 필요 없이 테 넌 트 다이얼 플랜에 연결 된 정규화 규칙을 삭제 합니다.
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
이를 실행 하 여 RedmondDialPlan 이라는 기존 테 넌 트 다이얼 플랜에 다음 정규화 규칙을 추가 합니다.
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
이를 실행 하 여 RedmondDialPlan 이라는 기존 테 넌 트 다이얼 플랜에서 다음 정규화 규칙을 제거 합니다.
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

다음을 실행 하 여 기존 정규화 규칙을 검사 하 고 삭제 하려는 항목을 결정 한 다음 인덱스를 사용 하 여 제거 합니다. 정규화 규칙 배열은 index 0부터 시작 합니다. 3 자리 정규화 규칙을 제거 하 여 인덱스 1을 선택 합니다.
  
```
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[Number 1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

이를 실행 하 여 RedmondDialPlan 테 넌 트 다이얼 플랜을 부여한 모든 사용자를 찾습니다.
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

이를 실행 하 여 HostingProvider sipfed.online.lync.com 인 모든 사용자의 policyname를 삭제 합니다.
```
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

OPDP1 라는 기존 온-프레미스 다이얼 플랜을 조직의 테 넌 트 다이얼 플랜으로 추가 하려면 다음을 실행 합니다. 먼저 .xml 파일에 온-프레미스 다이얼 플랜을 저장 한 다음이를 사용 하 여 새 테 넌 트 다이얼 플랜을 만듭니다.
  
이를 실행 하 여 온-프레미스 다이얼 플랜을 .xml 파일에 저장 합니다.
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

새 테 넌 트 다이얼 플랜을 만들려면 다음을 실행 합니다.
  
```
$DPFileName = "dialplan.xml"
$DP = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" +$nr.Name
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
$NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
## <a name="want-to-know-more-about-windows-powershell"></a>Windows Powershell에 대 한 자세한 정보를 확인 하 고 싶으신가요?

- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하면 여러 작업을 수행할 때 일상 업무를 단순화할 수 있는 단일 관리 지점을 사용 하 여 Office 365 및 비즈니스용 Skype Online을 관리할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.
    
  - [Windows PowerShell 및 Lync Online 소개](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Office 365 PowerShell을 사용 해야 하는 이유](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell에는 한 번에 여러 사용자의 설정을 변경 하는 경우와 같이 Microsoft 365 관리 센터를 사용 하는 경우에만 속도, 단순성, 생산성 등 다양 한 이점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.
    
  - [Windows PowerShell을 사용 하 여 Office 365를 관리 하는 가장 좋은 방법](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Windows PowerShell을 사용 하 여 비즈니스용 Skype Online 관리](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell을 사용 하 여 일반적인 비즈니스용 Skype Online 관리 작업 수행](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>관련 항목
[전화 번호 전송 일반적인 질문](transferring-phone-numbers-common-questions.md)

[통화 요금제에 사용 되는 다른 종류의 전화 번호](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[비상 통화 약관](emergency-calling-terms-and-conditions.md)

[비즈니스용 Skype Online: 비상 전화 부인 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
