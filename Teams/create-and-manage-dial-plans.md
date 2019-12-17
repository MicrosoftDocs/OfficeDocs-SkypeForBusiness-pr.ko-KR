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
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 통화 다이얼 플랜을 만들고 관리 하는 방법 (PSTN 통화 다이얼 플랜)과이를 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 7280614d2eab12dff30d17ad71a3ac213e94dcd4
ms.sourcegitcommit: dc240b123efb03d5ab0545d650a973bf60d04506
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2019
ms.locfileid: "40069439"
---
# <a name="create-and-manage-dial-plans"></a>다이얼 플랜 만들기 및 관리

조직에 대 한 다이얼 플랜을 계획 하 고 통화 라우팅에 대해 만들어야 하는 모든 정규화 규칙을 파악 한 후에는 다이얼 플랜을 만들 준비가 된 것입니다. Microsoft 팀 관리 센터 또는 Windows PowerShell을 사용 하 여 다이얼 플랜을 만들고 관리할 수 있습니다.  

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터 사용

### <a name="create-a-dial-plan"></a>다이얼 플랜 만들기

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성** > **다이얼 플랜**으로 이동 합니다.
2. **추가**를 클릭 한 다음 다이얼 플랜의 이름과 설명을 입력 합니다.
    ![다이얼 플랜을 만들기 위한 추가 페이지를 보여 주는 스크린샷](media/create-dial-plan.png)
3. **다이얼 플랜 세부 정보**아래에서 사용자가 하나 이상의 추가 선행 번호 (예: 9)를 입력 하 여 외부 회선을 확보 해야 하는 경우 외부 전화 걸기 접두사를 지정 합니다. 실행할 작업:
    1. **외부 전화 걸기 접두 번호** 상자에 외부 전화 걸기 접두사를 입력 합니다. 접두사는 최대 4 자 (#, *, 0-9)로 구성 될 수 있습니다.
    2. 최적화 된 **장치 전화 걸기를**켭니다. 외부 전화 걸기 접두사를 지정 하는 경우에는이 설정을 사용 하 여 사용자가 조직 외부에서 전화를 걸 수 있도록 접두사를 적용 해야 합니다.
4. **정규화 규칙**에서 다이얼 플랜에 하나 이상의 [정규화 규칙](what-are-dial-plans.md#normalization-rules) 을 구성 하 고 연결 합니다. 각 다이얼 플랜에는 하나 이상의 정규화 규칙이 연결 되어 있어야 합니다.  이렇게 하려면 다음 중 하나 이상을 수행 합니다.
    - 새 정규화 규칙을 만들어 다이얼 플랜에 연결 하려면 **추가**를 클릭 한 다음 규칙을 정의 합니다.
    - 다이얼 플랜에 이미 연결 된 정규화 규칙을 편집 하려면 규칙 이름 왼쪽에 있는을 클릭 하 여 규칙을 선택한 다음 **편집**을 클릭 합니다. 원하는 대로 변경한 다음 **저장**을 클릭 합니다.
    - 다이얼 플랜에서 정규화 규칙을 제거 하려면 규칙 이름 왼쪽에 있는을 클릭 하 여 규칙을 선택한 다음 **제거**를 클릭 합니다.
5. 정규화 규칙을 원하는 순서 대로 정렬 합니다. **위로 이동** 또는 **아래로 이동을** 클릭 하 여 목록에서 규칙의 위치를 변경 합니다.

    > [!NOTE]
    > 팀은 정규화 규칙 목록을 위에서 아래로 이동 하 고, 전화 번호와 일치 하는 첫 번째 규칙을 사용 합니다. 전화 거는 번호가 둘 이상의 정규화 규칙을 사용할 수 있도록 다이얼 플랜을 설정 하는 경우 더 제한적인 규칙이 덜 제한적인 규칙 보다 위에 정렬 되어 있는지 확인 합니다.

6. **저장**을 클릭 합니다.
7. 다이얼 플랜을 테스트 하려면 **다이얼 플랜 테스트**에서 전화 번호를 입력 한 다음 **테스트**를 클릭 합니다.

### <a name="edit-a-dial-plan"></a>다이얼 플랜 편집

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성** > **다이얼 플랜**으로 이동 합니다.
2. 다이얼 플랜 이름 왼쪽을 클릭 하 여 다이얼 플랜을 선택 하 고 **편집**을 클릭 합니다.
3. 원하는 변경 작업을 수행한 다음 **저장**을 클릭 합니다.

### <a name="add-users-to-a-dial-plan"></a>다이얼 플랜에 사용자 추가

1. Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **음성** > **다이얼 플랜**으로 이동 합니다.
2. 다이얼 플랜 이름 왼쪽을 클릭 하 여 다이얼 플랜을 선택 합니다.
3. **사용자 관리**를 선택 합니다.
4. **사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 선택 합니다. 추가 하려는 각 사용자에 대해이 단계를 반복 합니다.
5. 사용자 추가를 마쳤으면 **적용**을 선택 합니다.

## <a name="using-powershell"></a>PowerShell 사용
  
### <a name="verify-and-start-remote-powershell"></a>원격 PowerShell 확인 및 시작

 **Windows PowerShell 버전 3.0 이상을 실행 하 고 있는지 확인**
  
1. 버전 3.0 이상을 실행 하 고 있는지 확인 하려면 **시작 메뉴** > 에서**Windows PowerShell**을 수행 합니다.
    
2. **Windows PowerShell** 창에서 _Get-Host_ 를 입력 하 여 버전을 확인 합니다.
    
3. 버전 3.0 이상이 없는 경우 Windows PowerShell에 업데이트를 다운로드 하 여 설치 합니다. Windows [Management 프레임 워크 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 를 참조 하 여 windows PowerShell을 버전 4.0로 다운로드 하 고 업데이트 합니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
4. 비즈니스용 skype Online에 연결 되는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online 용 Windows PowerShell 모듈을 설치 해야 합니다. 이 모듈은 64 비트 컴퓨터 에서만 지원 되며 비즈니스용 [Skype Online 용 Windows PowerShell 모듈](https://go.microsoft.com/fwlink/?LinkId=294688)에서 다운로드할 수 있습니다. 메시지가 표시 되 면 컴퓨터를 다시 시작 합니다.
    
자세한 내용은 [단일 Windows PowerShell 창에서 모든 Office 365 서비스에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)을 참조 하세요.
  
 **Windows PowerShell 세션 시작**
  
1. **Windows PowerShell** **시작** > 을 클릭 합니다.
    
2. **Windows PowerShell** 창에서 다음을 실행 하 여 Office 365 조직에 연결 합니다.
    
    > [!NOTE]
    > 비즈니스용 Skype Online Windows PowerShell 모듈을 처음 사용 하는 경우에만 **Import-Module** 명령을 실행 하면 됩니다.
  

    ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a>다이얼 플랜 만들기 및 관리

단일 cmdlet 또는 PowerShell 스크립트를 사용 하 여 테 넌 트 다이얼 플랜을 만들고 관리할 수 있습니다.
  
#### <a name="using-single-cmdlets"></a>단일 cmdlet 사용

- 새 다이얼 플랜을 만들려면 다음을 실행 합니다.
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    다른 예제 및 매개 변수는 [New-Csten앤틸리스 다이얼 플랜](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan)을 참조 하세요.
    
- 기존 다이얼 플랜의 설정을 편집 하려면 다음을 실행 합니다.
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    다른 예제 및 매개 변수는 [Set-Csten앤틸리스 다이얼 플랜](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan)을 참조 하세요.
    
- 다이얼 플랜에 사용자를 추가 하려면 다음을 실행 합니다.
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    다른 예제 및 매개 변수는 [-Csten앤틸리스 다이얼 플랜](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan)을 참조 하세요.
    
- 다이얼 플랜에 대 한 설정을 보려면 다음을 실행 합니다.
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    다른 예제 및 매개 변수는 [Get-Csten앤틸리스 다이얼 플랜](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps)을 참조 하세요.
    
- 다이얼 플랜을 삭제 하려면 다음을 실행 합니다.
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    다른 예제 및 매개 변수는 [제거-Csten앤틸리스 다이얼 플랜](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)을 참조 하세요.
    
- 유효 다이얼 플랜의 설정을 보려면 다음을 실행 합니다.
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    다른 예제 및 매개 변수는 [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan)을 참조 하세요.
    
- 다이얼 플랜의 유효 설정을 테스트 하려면 다음을 실행 합니다.
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    다른 예제 및 매개 변수는 [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)을 참조 하세요.
    
#### <a name="using-a-powershell-script"></a>PowerShell 스크립트 사용

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
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
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

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

이를 실행 하 여 RedmondDialPlan 테 넌 트 다이얼 플랜을 부여한 모든 사용자를 찾습니다.
  
```
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

이를 실행 하 여 sipfed.online.lync.com의 HostingProvider 있는 모든 사용자가 할당 된 TenantDialPlan 플랜을 제거 합니다.
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
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a>관련 항목

- [다이얼 플랜이 무엇인가요?](what-are-dial-plans.md)
- [전화 번호 전송 자주 묻는 질문](transferring-phone-numbers-common-questions.md)
- [통화 요금제에 사용 되는 다른 종류의 전화 번호](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)(조직의 전화 번호 관리)
- [긴급 통화 사용 약관](emergency-calling-terms-and-conditions.md)
- [비상 전화 고 지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [팀 PowerShell 개요](teams-powershell-overview.md)
