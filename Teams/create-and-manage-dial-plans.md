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
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: Microsoft Teams 관리 센터 또는 Windows PowerShell 사용하여 전화 요금제(PSTN 통화 전화 걸기 요금제)를 만들고 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: 0655f81df9c8ce25368a281a7f5b3392f7fe6ec3
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814787"
---
# <a name="create-and-manage-dial-plans"></a>다이얼 플랜 만들기 및 관리

조직에 대한 다이얼 플랜을 계획하고 통화 라우팅을 위해 만들어야 하는 모든 정규화 규칙을 확인한 후 다이얼 플랜을 만들 준비가 된 것입니다. Microsoft Teams 관리 센터 또는 Windows PowerShell 요금제 만들기 및 관리할 수 있습니다.  

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

### <a name="create-a-dial-plan"></a>다이얼 플랜 만들기

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Voice Dial **요금제로**  >  **이동하세요.**
2. **추가를** 클릭한 다음 다이얼 플랜의 이름과 설명을 입력합니다.
    ![다이얼 플랜을 만들기 위한 추가 페이지를 보여주는 스크린샷](media/create-dial-plan.png)
3. 전화 **걸기 계획** 세부 정보에서 사용자가 외부 선을 얻기 위해 한 자리 이상의 앞 자릿수(예: 9)에 전화를 걸 필요가 있는 경우 외부 전화 접속을 지정합니다. 이 작업을 위해:
    1. 외부 전화 **걸기** 사전 상자에 외부 전화 걸기 사전을 입력합니다. 이 경우 최대 4자(#,*, 0-9)까지 사용할 수 있습니다.
    2. 최적화된 **장치 전화 걸기를 니다.** 외부 전화 걸기 prefix를 지정하는 경우 조직 외부에서 전화를 걸 수 있도록 이 설정을 설정하여 해당 부호를 적용해야 합니다.
4. 정규화 **규칙에서** 다이얼 플랜에 대한 하나 이상의 정규화 [규칙을](what-are-dial-plans.md#normalization-rules) 구성하고 연결합니다. 각 다이얼 플랜에는 하나 이상의 정규화 규칙이 연결되어 있어야 합니다.  이 작업을 위해 다음 중 하나 이상을 합니다.
    - 새 정규화 규칙을 만들고 다이얼 플랜에 연결하려면 추가를 클릭한 다음 규칙을 정의합니다.
    - 다이얼 플랜과 이미 연결된 정규화 규칙을 편집하려면 규칙 이름 왼쪽을 클릭하여 규칙을 선택한 다음 편집을 **클릭합니다.** 원하는 내용을 변경한 다음 저장을 **클릭합니다.**
    - 다이얼 플랜에서 정규화 규칙을 제거하려면 규칙 이름 왼쪽을 클릭하여 규칙을 선택한 다음 제거를 **클릭합니다.**
5. 정규화 규칙을 원하는 순서대로 정렬합니다. 목록에서 **규칙의** 위치를 변경하려면 아래로 이동 또는 아래로 클릭합니다. 

    > [!NOTE]
    > Teams는 위쪽에서 아래로 정규화 규칙 목록을 트래버스하고 전화 걸기 번호와 일치하는 첫 번째 규칙을 사용 합니다. 전화 걸기 번호가 두 개 이상의 정규화 규칙과 일치하도록 다이얼 플랜을 설정한 경우 덜 제한적인 규칙보다 더 제한적인 규칙이 정렬되어 있는지를 확인 합니다.

6. **저장** 을 클릭합니다.
7. 다이얼 플랜을 테스트하려면 테스트 다이얼 플랜에서 전화 번호를 입력한 다음 테스트를 **클릭합니다.**

### <a name="edit-a-dial-plan"></a>다이얼 플랜 편집

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 Voice Dial **요금제로**  >  **이동하세요.**
2. 다이얼 플랜 이름 왼쪽을 클릭하여 다이얼 플랜을 선택한 다음 편집을 **클릭합니다.**
3. 원하는 내용을 변경한 다음 저장을 **클릭합니다.**

### <a name="assign-a-dial-plan-to-users"></a>사용자에게 다이얼 플랜 할당

정책을 할당하는 방법과 동일한 방식으로 다이얼 플랜을 할당합니다. [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a>PowerShell 사용
  
### <a name="verify-and-start-remote-powershell"></a>원격 PowerShell 확인 및 시작

 **버전 3.0 Windows PowerShell 실행 중인지 확인**
  
1. 버전 3.0 이상을 실행하고 있는지 확인: 시작 메뉴를  >  Windows PowerShell.
    
2. 웹 창에  _Get-Host를_ 입력하여 **Windows PowerShell** 확인
    
3. 버전 3.0 이상이 없는 경우 업데이트를 다운로드하여 설치하여 Windows PowerShell. 버전 [Windows Management Framework 4.0으로](https://go.microsoft.com/fwlink/?LinkId=716845) Windows PowerShell 다운로드하고 업데이트하려면 4.0을 참조합니다. 메시지가 표시될 때 컴퓨터를 다시 시작합니다.
    
4. 비즈니스용 Skype Online에 연결하는 원격 Windows PowerShell 세션을 만들 수 있는 비즈니스용 Skype Online용 Windows PowerShell 모듈을 설치해야 합니다. 비즈니스용 [Skype Online용](https://go.microsoft.com/fwlink/?LinkId=294688)Windows PowerShell 64비트 컴퓨터에서만 지원되는 이 모듈을 다운로드할 수 있습니다. 메시지가 표시될 경우 컴퓨터를 다시 시작합니다.
    
자세한 내용은 단일 창에서 모든 [Microsoft 365 또는 Office 365 서비스에 Windows PowerShell 참조합니다.](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)
  
 **세션 Windows PowerShell 시작**
  
1. 시작 **Windows PowerShell.**  >  
    
2. 다음 **Windows PowerShell** 실행하여 Microsoft 365 또는 Office 365에 연결합니다.
    
 
    > [!NOTE]
    > 비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.
    >
    > 최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.

    ```PowerShell
   Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a>다이얼 플랜 만들기 및 관리

단일 cmdlet 또는 PowerShell 스크립트를 사용하여 테넌트 다이얼 플랜을 만들고 관리할 수 있습니다.
  
#### <a name="using-single-cmdlets"></a>단일 cmdlet 사용

- 새 다이얼 플랜을 만들 경우 다음을 실행합니다.
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    다른 예제 및 매개 변수는 [New-CsTenantDialPlan을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan)
    
- 기존 다이얼 플랜의 설정을 편집하려면 다음을 실행합니다.
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    다른 예제 및 매개 변수는 [Set-CsTenantDialPlan을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan)
    
- 다이얼 플랜에 사용자를 추가하기 위해 다음을 실행합니다.
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    다른 예제 및 매개 변수는 [Grant-CsTenantDialPlan을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan)
    
- 다이얼 플랜에서 설정을 보기 위해 다음을 실행합니다.
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    다른 예제 및 매개 변수는 [Get-CsTenantDialPlan을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps)
    
- 다이얼 플랜을 삭제하려면 다음을 실행합니다.
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    다른 예제 및 매개 변수는 [Remove-CsTenantDialPlan을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps)
    
- 유효 다이얼 플랜의 설정을 표시하려면 다음을 실행합니다.
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    다른 예제 및 매개 변수는 [Get-CsEffectiveTenantDialPlan을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan)
    
- 다이얼 플랜의 유효 설정을 테스트하려면 다음을 실행합니다.
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    다른 예제 및 매개 변수는 [Test-CsEffectiveTenantDialPlan을 참조합니다.](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps)
    
#### <a name="using-a-powershell-script"></a>PowerShell 스크립트 사용

테넌트 다이얼 플랜을 먼저 삭제할 필요 없이 테넌트 다이얼 플랜과 연결된 정규화 규칙을 삭제하려면 이 규칙을 실행합니다.
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
이 기능을 실행하여 RedmondDialPlan이라는 기존 테넌트 다이얼 플랜에 다음 정규화 규칙을 추가합니다.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
이 기능을 실행하여 RedmondDialPlan이라는 기존 테넌트 다이얼 플랜에서 다음 정규화 규칙을 제거합니다.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

기존 정규화 규칙을 검사하고 삭제할 규칙을 결정한 다음 해당 인덱스를 사용하여 제거하려면 다음을 실행합니다. 정규화 규칙의 배열은 인덱스 0으로 시작합니다. 3자리 정규화 규칙을 제거하여 인덱스 1이 됐습니다.
  
```PowerShell
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

이 기능을 실행하여 RedmondDialPlan 테넌트 다이얼 플랜이 부여된 모든 사용자를 찾을 수 있습니다.
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

이 작업을 실행하여 할당된 TenantDialPlan을 HostingProvider가 있는 모든 사용자에서 sipfed.online.lync.com.
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

이 기능을 실행하여 조직의 테넌트 다이얼 플랜으로 OPDP1이라는 기존 다이얼 플랜을 추가합니다. 먼저 ,.xml 파일에는 프레미스 다이얼 플랜을 저장한 다음 이를 사용하여 새 테넌트 다이얼 플랜을 만들어야 합니다.
  
이 실행을 실행하여 .xml 파일에는 프레미스 다이얼 플랜을 저장합니다.
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

이 기능을 실행하여 새 테넌트 다이얼 플랜을 만들 수 있습니다.
  
```PowerShell
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
- [통화 요금제에 사용되는 다양한 종류의 전화 번호](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [긴급 통화 사용 약관](emergency-calling-terms-and-conditions.md)
- [긴급 통화 고지 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Teams PowerShell 개요](teams-powershell-overview.md)
